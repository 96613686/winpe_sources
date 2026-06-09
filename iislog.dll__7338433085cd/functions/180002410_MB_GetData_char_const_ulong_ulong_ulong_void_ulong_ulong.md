# MB::GetData(char const *,ulong,ulong,ulong,void *,ulong *,ulong)

- ea: `0x180002410`
- end: `0x1800024c4`
- name: `?GetData@MB@@QEAAHPEBDKKKPEAXPEAKK@Z`
- size: `180`
- prototype: `__int64 __fastcall(MB *__hidden this, const char *, unsigned int, unsigned int, unsigned int, void *, unsigned int *, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800024d0`
- `0x180004810`
- `0x180005b34`
- `0x180006618`
- `0x18000a978`

## callees

- `0x180002410`
- `0x180010010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800024b1`
- `KERNEL32!SetLastError` at `0x1800024b1`

## pseudocode

```c
__int64 __fastcall MB::GetData(
        MB *this,
        const char *a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        void *a6,
        unsigned int *a7,
        unsigned int a8)
{
  unsigned int *v8; // rbx
  __int64 v10; // rcx
  signed int v11; // ecx
  __int64 result; // rax
  _DWORD v13[4]; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v14; // [rsp+40h] [rbp-20h]
  int v15; // [rsp+44h] [rbp-1Ch]
  void *v16; // [rsp+48h] [rbp-18h]
  __int64 v17; // [rsp+50h] [rbp-10h]
  unsigned int v18; // [rsp+88h] [rbp+28h] BYREF

  v18 = a4;
  v8 = a7;
  v10 = *(_QWORD *)this;
  v13[1] = a8;
  v13[3] = a5;
  v14 = *a7;
  v13[0] = a3;
  v16 = a6;
  v15 = 0;
  v17 = 0;
  v18 = 0;
  v13[2] = 1;
  v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, const char *, _DWORD *, unsigned int *))(*(_QWORD *)v10 + 160LL))(
          v10,
          *((unsigned int *)this + 2),
          a2,
          v13,
          &v18);
  if ( v11 < 0 )
  {
    *v8 = v18;
    if ( (v11 & 0x1FFF0000) == 0x70000 )
      v11 = (unsigned __int16)v11;
    SetLastError(v11);
    return 0;
  }
  else
  {
    result = 1;
    *v8 = v14;
  }
  return result;
}

```

## disassembly

```asm
0x180002410  mov     [rsp-8+arg_0], rbx
0x180002415  mov     [rsp-8+arg_18], r9d
0x18000241a  push    rbp
0x18000241b  mov     rbp, rsp
0x18000241e  sub     rsp, 60h
0x180002422  mov     eax, [rbp+arg_38]
0x180002425  lea     r9, [rbp+var_30]
0x180002429  mov     rbx, [rbp+arg_30]
0x18000242d  mov     r10, rcx
0x180002430  mov     rcx, [rcx]
0x180002433  mov     [rbp+var_2C], eax
0x180002436  mov     eax, [rbp+arg_20]
0x180002439  mov     [rbp+var_24], eax
0x18000243c  mov     eax, [rbx]
0x18000243e  mov     [rbp+var_20], eax
0x180002441  mov     rax, [rbp+arg_28]
0x180002445  mov     [rbp+var_30], r8d
0x180002449  lea     r8, [rbp+arg_18]
0x18000244d  mov     [rbp+var_18], rax
0x180002451  mov     [rbp+var_1C], 0
0x180002458  mov     [rbp+var_10], 0
0x180002460  mov     [rbp+arg_18], 0
0x180002467  mov     [rbp+var_28], 1
0x18000246e  mov     rax, [rcx]
0x180002471  mov     [rsp+60h+var_40], r8
0x180002476  mov     r8, rdx
0x180002479  mov     edx, [r10+8]
0x18000247d  mov     rax, [rax+0A0h]
0x180002484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002489  mov     ecx, eax
0x18000248b  test    eax, eax
0x18000248d  js      short loc_18000249B
0x18000248f  mov     ecx, [rbp+var_20]
0x180002492  mov     eax, 1
0x180002497  mov     [rbx], ecx
0x180002499  jmp     short loc_1800024B9
0x18000249b  mov     eax, [rbp+arg_18]
0x18000249e  mov     [rbx], eax
0x1800024a0  mov     eax, ecx
0x1800024a2  and     eax, 1FFF0000h
0x1800024a7  cmp     eax, 70000h
0x1800024ac  jnz     short loc_1800024B1
0x1800024ae  movzx   ecx, cx; dwErrCode
0x1800024b1  call    cs:__imp_SetLastError
0x1800024b7  xor     eax, eax
0x1800024b9  mov     rbx, [rsp+60h+arg_0]
0x1800024be  add     rsp, 60h
0x1800024c2  pop     rbp
0x1800024c3  retn
```
