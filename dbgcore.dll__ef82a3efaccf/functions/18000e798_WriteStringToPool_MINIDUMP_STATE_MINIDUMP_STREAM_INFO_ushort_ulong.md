# WriteStringToPool(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,ushort *,ulong *)

- ea: `0x18000e798`
- end: `0x18000e891`
- name: `?WriteStringToPool@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAGPEAK@Z`
- size: `249`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _MINIDUMP_STREAM_INFO *, unsigned __int16 *, unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e438`
- `0x18000e898`
- `0x18000ec70`
- `0x18000f180`

## callees

- `0x18000bcbc`
- `0x18000e798`
- `0x18002c010`

## string_xrefs

- `0x18000e85a`: `WriteStringToPool.Write(0x%x) failed, 0x%08x`

## pseudocode

```c
__int64 __fastcall WriteStringToPool(
        struct _MINIDUMP_STATE *a1,
        struct _MINIDUMP_STREAM_INFO *a2,
        unsigned __int16 *a3,
        unsigned int *a4)
{
  unsigned __int16 *v8; // r10
  unsigned int v10; // edi
  unsigned int v11; // ecx
  __int64 v12; // r10
  int v13; // r14d
  __int64 result; // rax
  __int64 v15; // rcx
  int v16; // eax
  unsigned int v17; // ebp
  unsigned int v18; // [rsp+68h] [rbp+10h] BYREF

  v8 = a3;
  while ( *v8++ )
    ;
  v10 = *((_DWORD *)a2 + 34);
  v11 = *((_DWORD *)a2 + 32) + *((_DWORD *)a2 + 33);
  v12 = v8 - a3;
  v13 = 2 * v12 - 2 + 6;
  v18 = 2 * v12 - 2;
  if ( v13 + v10 > v11 )
    return 2147942487LL;
  result = WriteAtOffset(a1, v10, &v18, 4u);
  if ( !(_DWORD)result )
  {
    v15 = *((_QWORD *)a1 + 3);
    v18 += 2;
    v16 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v15 + 32LL))(v15, a3);
    v17 = v16;
    if ( v16 )
    {
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        4,
        "WriteStringToPool.Write(0x%x) failed, 0x%08x",
        v18,
        v16);
      return v17;
    }
    else
    {
      if ( a4 )
        *a4 = v10;
      *((_DWORD *)a2 + 34) += v13;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e798  mov     [rsp+arg_0], rbx
0x18000e79d  mov     [rsp+arg_10], rbp
0x18000e7a2  push    rsi
0x18000e7a3  push    rdi
0x18000e7a4  push    r12
0x18000e7a6  push    r14
0x18000e7a8  push    r15
0x18000e7aa  sub     rsp, 30h
0x18000e7ae  mov     rsi, r9
0x18000e7b1  mov     rbp, r8
0x18000e7b4  mov     rbx, rdx
0x18000e7b7  mov     r15, rcx
0x18000e7ba  mov     r10, r8
0x18000e7bd  movzx   eax, word ptr [r10]
0x18000e7c1  add     r10, 2
0x18000e7c5  test    ax, ax
0x18000e7c8  jnz     short loc_18000E7BD
0x18000e7ca  mov     edi, [rdx+88h]
0x18000e7d0  sub     r10, rbp
0x18000e7d3  mov     ecx, [rdx+84h]
0x18000e7d9  add     ecx, [rdx+80h]
0x18000e7df  sar     r10, 1
0x18000e7e2  lea     eax, ds:0FFFFFFFFFFFFFFFEh[r10*2]
0x18000e7ea  lea     r14d, [rax+6]
0x18000e7ee  mov     [rsp+58h+arg_8], eax
0x18000e7f2  lea     eax, [r14+rdi]
0x18000e7f6  cmp     eax, ecx
0x18000e7f8  jbe     short loc_18000E801
0x18000e7fa  mov     eax, 80070057h
0x18000e7ff  jmp     short loc_18000E87A
0x18000e801  mov     r9d, 4; unsigned int
0x18000e807  lea     r8, [rsp+58h+arg_8]; void *
0x18000e80c  mov     edx, edi; unsigned int
0x18000e80e  mov     rcx, r15; struct _MINIDUMP_STATE *
0x18000e811  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000e816  test    eax, eax
0x18000e818  jnz     short loc_18000E87A
0x18000e81a  mov     r8d, [rsp+58h+arg_8]
0x18000e81f  mov     rdx, rbp
0x18000e822  mov     rcx, [r15+18h]
0x18000e826  add     r8d, 2
0x18000e82a  mov     [rsp+58h+arg_8], r8d
0x18000e82f  mov     rax, [rcx]
0x18000e832  mov     rax, [rax+20h]
0x18000e836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e83b  mov     ebp, eax
0x18000e83d  test    eax, eax
0x18000e83f  jz      short loc_18000E86A
0x18000e841  mov     rcx, [r15+28h]
0x18000e845  mov     edx, 4
0x18000e84a  mov     r9d, [rsp+58h+arg_8]
0x18000e84f  mov     [rsp+58h+var_38], ebp
0x18000e853  mov     r8, [rcx]
0x18000e856  mov     rax, [r8+8]
0x18000e85a  lea     r8, aWritestringtop; "WriteStringToPool.Write(0x%x) failed, 0"...
0x18000e861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e866  mov     eax, ebp
0x18000e868  jmp     short loc_18000E87A
0x18000e86a  test    rsi, rsi
0x18000e86d  jz      short loc_18000E871
0x18000e86f  mov     [rsi], edi
0x18000e871  add     [rbx+88h], r14d
0x18000e878  xor     eax, eax
0x18000e87a  mov     rbx, [rsp+58h+arg_0]
0x18000e87f  mov     rbp, [rsp+58h+arg_10]
0x18000e884  add     rsp, 30h
0x18000e888  pop     r15
0x18000e88a  pop     r14
0x18000e88c  pop     r12
0x18000e88e  pop     rdi
0x18000e88f  pop     rsi
0x18000e890  retn
```
