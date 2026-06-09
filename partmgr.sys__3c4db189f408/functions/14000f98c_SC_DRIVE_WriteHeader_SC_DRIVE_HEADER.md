# SC_DRIVE::WriteHeader(SC_DRIVE_HEADER *)

- ea: `0x14000f98c`
- end: `0x14000fa4d`
- name: `?WriteHeader@SC_DRIVE@@QEAAJPEAVSC_DRIVE_HEADER@@@Z`
- size: `193`
- prototype: `int(SC_DRIVE *__hidden this, struct SC_DRIVE_HEADER *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000f430`

## callees

- `0x14000a530`
- `0x14000f6e0`
- `0x14000f98c`
- `0x140010f60`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000fa35`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fa35`

## pseudocode

```c
__int64 __fastcall SC_DRIVE::WriteHeader(SC_DRIVE *this, struct SC_DRIVE_HEADER *a2, __int64 a3)
{
  __int64 v5; // rsi
  unsigned __int8 *v6; // rax
  unsigned int v7; // r8d
  unsigned __int8 *v8; // rbp
  int v9; // esi
  unsigned __int8 *v11; // [rsp+60h] [rbp+8h] BYREF

  v5 = (unsigned int)(1 << *((_DWORD *)this + 60));
  v6 = (unsigned __int8 *)SC_ENV::Allocate(v5, (__int64)a2, a3, 1);
  v8 = v6;
  if ( v6 )
  {
    v11 = v6;
    SC_DRIVE_HEADER::Format(a2, &v11, v7);
    v9 = (*(__int64 (__fastcall **)(SC_DRIVE *, _QWORD, _QWORD, unsigned __int8 *))(*(_QWORD *)this + 72LL))(
           this,
           *((_QWORD *)this + 57),
           (unsigned int)v5,
           v8);
    if ( v9 >= 0 )
    {
      *(_OWORD *)((char *)this + 488) = *(_OWORD *)a2;
      *(_OWORD *)((char *)this + 504) = *((_OWORD *)a2 + 1);
      *(_OWORD *)((char *)this + 520) = *((_OWORD *)a2 + 2);
      *(_OWORD *)((char *)this + 536) = *((_OWORD *)a2 + 3);
      *((_QWORD *)this + 69) = *((_QWORD *)a2 + 8);
    }
    ExFreePoolWithTag(v8, 0);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000f98c  push    rbx
0x14000f98e  push    rbp
0x14000f98f  push    rsi
0x14000f990  push    rdi
0x14000f991  sub     rsp, 38h
0x14000f995  mov     rbx, rcx
0x14000f998  mov     r9d, 1; unsigned int
0x14000f99e  mov     ecx, [rcx+0F0h]
0x14000f9a4  mov     eax, r9d
0x14000f9a7  shl     eax, cl
0x14000f9a9  mov     rdi, rdx
0x14000f9ac  mov     ecx, eax; unsigned __int64
0x14000f9ae  mov     esi, eax
0x14000f9b0  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x14000f9b5  mov     rbp, rax
0x14000f9b8  test    rax, rax
0x14000f9bb  jnz     short loc_14000F9C4
0x14000f9bd  mov     esi, 0C000009Ah
0x14000f9c2  jmp     short loc_14000FA41
0x14000f9c4  lea     rdx, [rsp+58h+arg_0]; unsigned __int8 **
0x14000f9c9  mov     [rsp+58h+arg_0], rbp
0x14000f9ce  mov     rcx, rdi; this
0x14000f9d1  call    ?Format@SC_DRIVE_HEADER@@QEAAXPEAPEAEK@Z; SC_DRIVE_HEADER::Format(uchar * *,ulong)
0x14000f9d6  mov     rax, [rbx]
0x14000f9d9  mov     r9, rbp
0x14000f9dc  mov     rdx, [rbx+1C8h]
0x14000f9e3  mov     r8d, esi
0x14000f9e6  mov     rcx, rbx
0x14000f9e9  mov     rax, [rax+48h]
0x14000f9ed  call    _guard_dispatch_icall
0x14000f9f2  mov     esi, eax
0x14000f9f4  test    eax, eax
0x14000f9f6  js      short loc_14000FA30
0x14000f9f8  movaps  xmm0, xmmword ptr [rdi]
0x14000f9fb  movups  xmmword ptr [rbx+1E8h], xmm0
0x14000fa02  movaps  xmm1, xmmword ptr [rdi+10h]
0x14000fa06  movups  xmmword ptr [rbx+1F8h], xmm1
0x14000fa0d  movaps  xmm0, xmmword ptr [rdi+20h]
0x14000fa11  movups  xmmword ptr [rbx+208h], xmm0
0x14000fa18  movaps  xmm1, xmmword ptr [rdi+30h]
0x14000fa1c  movups  xmmword ptr [rbx+218h], xmm1
0x14000fa23  movsd   xmm0, qword ptr [rdi+40h]
0x14000fa28  movsd   qword ptr [rbx+228h], xmm0
0x14000fa30  xor     edx, edx; Tag
0x14000fa32  mov     rcx, rbp; P
0x14000fa35  call    cs:__imp_ExFreePoolWithTag
0x14000fa3c  nop     dword ptr [rax+rax+00h]
0x14000fa41  mov     eax, esi
0x14000fa43  add     rsp, 38h
0x14000fa47  pop     rdi
0x14000fa48  pop     rsi
0x14000fa49  pop     rbp
0x14000fa4a  pop     rbx
0x14000fa4b  retn
```
