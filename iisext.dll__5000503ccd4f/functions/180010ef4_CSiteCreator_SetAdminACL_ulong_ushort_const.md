# CSiteCreator::SetAdminACL(ulong,ushort const *)

- ea: `0x180010ef4`
- end: `0x180011088`
- name: `?SetAdminACL@CSiteCreator@@AEAAJKPEBG@Z`
- size: `404`
- prototype: `__int64 __fastcall(CSiteCreator *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010638`

## callees

- `0x180010e80`
- `0x180010ef4`
- `0x180012010`

## import_xrefs

- `ADVAPI32!IsValidSecurityDescriptor` at `0x18001101a`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x18001101a`
- `KERNEL32!LocalFree` at `0x180011064`
- `KERNEL32!LocalFree` at `0x180011064`
- `KERNEL32!LocalAlloc` at `0x180010f9a`
- `KERNEL32!LocalAlloc` at `0x180010f9a`

## pseudocode

```c
__int64 __fastcall CSiteCreator::SetAdminACL(CSiteCreator *this, unsigned int a2, const unsigned __int16 *a3)
{
  __int64 v5; // rcx
  unsigned int v7; // ebx
  unsigned __int8 *v8; // rax
  unsigned __int8 *v9; // rdi
  __int64 v10; // rcx
  int v11; // eax
  __int64 v13; // [rsp+50h] [rbp-30h] BYREF
  int v14; // [rsp+58h] [rbp-28h]
  int v15; // [rsp+5Ch] [rbp-24h]
  unsigned int v16[2]; // [rsp+60h] [rbp-20h]
  unsigned __int8 *v17; // [rsp+68h] [rbp-18h]
  __int64 v18; // [rsp+70h] [rbp-10h]
  SIZE_T uBytes; // [rsp+B0h] [rbp+30h] BYREF
  int v20; // [rsp+C8h] [rbp+48h] BYREF

  v13 = 6027;
  *(_QWORD *)v16 = 0;
  v18 = 0;
  LODWORD(uBytes) = 0;
  v5 = *((_QWORD *)this + 7);
  v20 = 0;
  v14 = 0;
  v15 = 3;
  v17 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, __int64 *, SIZE_T *))(*(_QWORD *)v5 + 80LL))(
         v5,
         a2,
         L"filters/",
         &v13,
         &uBytes);
  if ( (int)(v7 + 0x80000000) < 0 || v7 == -2147024774 )
  {
    v8 = (unsigned __int8 *)LocalAlloc(0x40u, (unsigned int)uBytes);
    v9 = v8;
    if ( v8 )
    {
      v10 = *((_QWORD *)this + 7);
      v16[0] = uBytes;
      v13 = 6027;
      v14 = 0;
      v15 = 3;
      v17 = v8;
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, __int64 *, int *))(*(_QWORD *)v10 + 80LL))(
              v10,
              a2,
              L"filters/",
              &v13,
              &v20);
      if ( v11 >= 0 )
      {
        v7 = -2147418113;
        if ( v17 && v16[0] && IsValidSecurityDescriptor(v9) )
          v7 = CSiteCreator::InternalSetData(this, a2, a3, 0x178Bu, v17, v16[0], 0xDu, 3u, 1u);
      }
      else
      {
        v7 = 0;
        if ( v11 != -2146646015 )
          v7 = v11;
      }
      LocalFree(v9);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else if ( v7 == -2146646015 )
  {
    return 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180010ef4  mov     [rsp-28h+arg_8], rbx
0x180010ef9  mov     [rsp-28h+arg_10], rsi
0x180010efe  push    rbp
0x180010eff  push    rdi
0x180010f00  push    r12
0x180010f02  push    r14
0x180010f04  push    r15
0x180010f06  mov     rbp, rsp
0x180010f09  sub     rsp, 80h
0x180010f10  xor     r12d, r12d
0x180010f13  mov     [rbp+var_30], 178Bh
0x180010f1b  mov     esi, edx
0x180010f1d  mov     qword ptr [rbp+var_20], r12
0x180010f21  lea     rdx, [rbp+uBytes]
0x180010f25  mov     [rbp+var_10], r12
0x180010f29  mov     r14, rcx
0x180010f2c  mov     dword ptr [rbp+uBytes], r12d
0x180010f30  mov     rcx, [rcx+38h]
0x180010f34  lea     r9, [rbp+var_30]
0x180010f38  mov     [rbp+arg_18], r12d
0x180010f3c  mov     r15, r8
0x180010f3f  mov     [rbp+var_28], r12d
0x180010f43  lea     r8, aFilters_0; "filters/"
0x180010f4a  mov     [rbp+var_24], 3
0x180010f51  mov     [rbp+var_18], r12
0x180010f55  mov     rax, [rcx]
0x180010f58  mov     [rsp+80h+var_60], rdx
0x180010f5d  mov     edx, esi
0x180010f5f  mov     rax, [rax+50h]
0x180010f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f68  mov     ebx, eax
0x180010f6a  mov     eax, 80000000h
0x180010f6f  lea     ecx, [rbx+rax]
0x180010f72  test    eax, ecx
0x180010f74  jnz     short loc_180010F92
0x180010f76  cmp     ebx, 8007007Ah
0x180010f7c  jz      short loc_180010F92
0x180010f7e  cmp     ebx, 800CC801h
0x180010f84  jnz     loc_18001106A
0x180010f8a  mov     ebx, r12d
0x180010f8d  jmp     loc_18001106A
0x180010f92  mov     edx, dword ptr [rbp+uBytes]; uBytes
0x180010f95  mov     ecx, 40h ; '@'; uFlags
0x180010f9a  call    cs:__imp_LocalAlloc
0x180010fa0  mov     rdi, rax
0x180010fa3  test    rax, rax
0x180010fa6  jnz     short loc_180010FB2
0x180010fa8  mov     ebx, 8007000Eh
0x180010fad  jmp     loc_18001106A
0x180010fb2  mov     eax, dword ptr [rbp+uBytes]
0x180010fb5  lea     rdx, [rbp+arg_18]
0x180010fb9  mov     rcx, [r14+38h]
0x180010fbd  lea     r9, [rbp+var_30]
0x180010fc1  mov     [rbp+var_20], eax
0x180010fc4  lea     r8, aFilters_0; "filters/"
0x180010fcb  mov     [rbp+var_30], 178Bh
0x180010fd3  mov     [rbp+var_28], r12d
0x180010fd7  mov     [rbp+var_24], 3
0x180010fde  mov     [rbp+var_18], rdi
0x180010fe2  mov     rax, [rcx]
0x180010fe5  mov     [rsp+80h+var_60], rdx
0x180010fea  mov     edx, esi
0x180010fec  mov     rax, [rax+50h]
0x180010ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ff5  test    eax, eax
0x180010ff7  jns     short loc_180011006
0x180010ff9  cmp     eax, 800CC801h
0x180010ffe  mov     ebx, r12d
0x180011001  cmovnz  ebx, eax
0x180011004  jmp     short loc_180011061
0x180011006  mov     ebx, 8000FFFFh
0x18001100b  cmp     [rbp+var_18], r12
0x18001100f  jz      short loc_180011061
0x180011011  cmp     [rbp+var_20], r12d
0x180011015  jbe     short loc_180011061
0x180011017  mov     rcx, rdi; pSecurityDescriptor
0x18001101a  call    cs:__imp_IsValidSecurityDescriptor
0x180011020  test    eax, eax
0x180011022  jz      short loc_180011061
0x180011024  mov     eax, [rbp+var_20]
0x180011027  mov     r9d, 178Bh; unsigned int
0x18001102d  mov     [rsp+80h+var_40], 1; unsigned int
0x180011035  mov     r8, r15; unsigned __int16 *
0x180011038  mov     [rsp+80h+var_48], 3; unsigned int
0x180011040  mov     edx, esi; unsigned int
0x180011042  mov     [rsp+80h+var_50], 0Dh; unsigned int
0x18001104a  mov     rcx, r14; this
0x18001104d  mov     [rsp+80h+var_58], eax; unsigned int
0x180011051  mov     rax, [rbp+var_18]
0x180011055  mov     [rsp+80h+var_60], rax; unsigned __int8 *
0x18001105a  call    ?InternalSetData@CSiteCreator@@AEAAJKPEBGKPEAEKKKK@Z; CSiteCreator::InternalSetData(ulong,ushort const *,ulong,uchar *,ulong,ulong,ulong,ulong)
0x18001105f  mov     ebx, eax
0x180011061  mov     rcx, rdi; hMem
0x180011064  call    cs:__imp_LocalFree
0x18001106a  lea     r11, [rsp+80h+var_s0]
0x180011072  mov     eax, ebx
0x180011074  mov     rbx, [r11+38h]
0x180011078  mov     rsi, [r11+40h]
0x18001107c  mov     rsp, r11
0x18001107f  pop     r15
0x180011081  pop     r14
0x180011083  pop     r12
0x180011085  pop     rdi
0x180011086  pop     rbp
0x180011087  retn
```
