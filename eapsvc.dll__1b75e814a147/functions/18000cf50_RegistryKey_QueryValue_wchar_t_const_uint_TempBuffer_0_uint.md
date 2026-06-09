# RegistryKey::QueryValue(wchar_t const *,uint &,TempBuffer<0> &,uint)

- ea: `0x18000cf50`
- end: `0x18000d0ef`
- name: `?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAIAEAV?$TempBuffer@$0A@@@I@Z`
- size: `415`
- prototype: `__int64 __fastcall(HKEY *, const struct std::nothrow_t *, DWORD *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x18000cee8`

## callees

- `0x180001f60`
- `0x18000a5ac`
- `0x18000ab3c`
- `0x18000ab70`
- `0x18000cf50`
- `0x18000e4ac`
- `0x18000e4c4`
- `0x180014e8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d018`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000d018`

## pseudocode

```c
__int64 __fastcall RegistryKey::QueryValue(HKEY *a1, const struct std::nothrow_t *a2, DWORD *a3, __int64 a4)
{
  void *lpData; // rbx
  unsigned __int64 v9; // r9
  size_t v10; // rsi
  DWORD v11; // eax
  __int64 v12; // rdi
  void *v13; // rax
  LSTATUS v14; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type[3]; // [rsp+34h] [rbp-CCh] BYREF
  void *Src; // [rsp+40h] [rbp-C0h]
  __int64 v19; // [rsp+48h] [rbp-B8h]
  BYTE Data[512]; // [rsp+50h] [rbp-B0h] BYREF
  size_t v21; // [rsp+250h] [rbp+150h]

  lpData = Data;
  Src = Data;
  v9 = 512;
  v19 = 512;
  v10 = 0;
  v21 = 0;
  v11 = 512;
  cbData = 512;
  Type[0] = 0;
  while ( 1 )
  {
    v12 = v11;
    if ( v11 > v9 )
    {
      v13 = operator new(v11, a2);
      lpData = v13;
      if ( !v13 )
        ThrowNewFailure();
      memcpy_0(v13, Src, v10);
      if ( Src != Data )
        operator delete(Src);
      Src = lpData;
      v19 = v12;
    }
    v14 = RegQueryValueExW(*a1, (LPCWSTR)a2, 0, Type, (LPBYTE)lpData, &cbData);
    if ( !v14 )
      break;
    if ( v14 == 2 )
    {
      if ( Src != Data )
        operator delete(Src);
      return 1;
    }
    if ( v14 != 234 )
      SystemError::Throw<long>((__int64)L"RegQueryValueExW", v14);
    v11 = cbData;
    if ( cbData > 0xFFF )
    {
      if ( Src != Data )
        operator delete(Src);
      return 4;
    }
    v10 = v21;
    v9 = v19;
    lpData = Src;
  }
  TempBuffer<0>::Assign(a4, cbData, Src);
  *a3 = Type[0];
  if ( Src != Data )
    operator delete(Src);
  return 0;
}

```

## disassembly

```asm
0x18000cf50  push    rbp
0x18000cf52  push    rbx
0x18000cf53  push    rsi
0x18000cf54  push    rdi
0x18000cf55  push    r12
0x18000cf57  push    r13
0x18000cf59  push    r14
0x18000cf5b  push    r15
0x18000cf5d  lea     rbp, [rsp-178h]
0x18000cf65  sub     rsp, 278h
0x18000cf6c  mov     rax, cs:__security_cookie
0x18000cf73  xor     rax, rsp
0x18000cf76  mov     [rbp+1B0h+var_50], rax
0x18000cf7d  mov     r15, r9
0x18000cf80  mov     r14, r8
0x18000cf83  mov     r13, rdx
0x18000cf86  mov     r12, rcx
0x18000cf89  lea     rbx, [rsp+2B0h+Data]
0x18000cf8e  mov     [rsp+2B0h+Src], rbx
0x18000cf93  mov     r9d, 200h
0x18000cf99  mov     [rsp+2B0h+var_268], r9
0x18000cf9e  xor     esi, esi
0x18000cfa0  mov     [rbp+1B0h+var_60], rsi
0x18000cfa7  mov     eax, r9d
0x18000cfaa  mov     [rsp+2B0h+cbData], eax
0x18000cfae  mov     [rsp+2B0h+Type], esi
0x18000cfb2  mov     edi, eax
0x18000cfb4  cmp     rdi, r9
0x18000cfb7  jbe     short loc_18000CFFA
0x18000cfb9  mov     ecx, edi; dwBytes
0x18000cfbb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000cfc0  mov     rbx, rax
0x18000cfc3  test    rax, rax
0x18000cfc6  jz      loc_18000D0E9
0x18000cfcc  mov     r8, rsi; Size
0x18000cfcf  mov     rdx, [rsp+2B0h+Src]; Src
0x18000cfd4  mov     rcx, rax; void *
0x18000cfd7  call    memcpy_0
0x18000cfdc  lea     rax, [rsp+2B0h+Data]
0x18000cfe1  mov     rcx, [rsp+2B0h+Src]; lpMem
0x18000cfe6  cmp     rcx, rax
0x18000cfe9  jz      short loc_18000CFF0
0x18000cfeb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000cff0  mov     [rsp+2B0h+Src], rbx
0x18000cff5  mov     [rsp+2B0h+var_268], rdi
0x18000cffa  lea     rax, [rsp+2B0h+cbData]
0x18000cfff  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18000d004  mov     [rsp+2B0h+lpData], rbx; lpData
0x18000d009  lea     r9, [rsp+2B0h+Type]; lpType
0x18000d00e  xor     r8d, r8d; lpReserved
0x18000d011  mov     rdx, r13; lpValueName
0x18000d014  mov     rcx, [r12]; hKey
0x18000d018  call    cs:__imp_RegQueryValueExW
0x18000d01e  test    eax, eax
0x18000d020  jz      short loc_18000D089
0x18000d022  cmp     eax, 2
0x18000d025  jz      short loc_18000D06E
0x18000d027  cmp     eax, 0EAh
0x18000d02c  jnz     loc_18000D0DA
0x18000d032  mov     eax, [rsp+2B0h+cbData]
0x18000d036  cmp     eax, 0FFFh
0x18000d03b  ja      short loc_18000D053
0x18000d03d  mov     rsi, [rbp+1B0h+var_60]
0x18000d044  mov     r9, [rsp+2B0h+var_268]
0x18000d049  mov     rbx, [rsp+2B0h+Src]
0x18000d04e  jmp     loc_18000CFB2
0x18000d053  lea     rax, [rsp+2B0h+Data]
0x18000d058  mov     rcx, [rsp+2B0h+Src]; lpMem
0x18000d05d  cmp     rcx, rax
0x18000d060  jz      short loc_18000D067
0x18000d062  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d067  mov     eax, 4
0x18000d06c  jmp     short loc_18000D0B7
0x18000d06e  lea     rax, [rsp+2B0h+Data]
0x18000d073  mov     rcx, [rsp+2B0h+Src]; lpMem
0x18000d078  cmp     rcx, rax
0x18000d07b  jz      short loc_18000D082
0x18000d07d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d082  mov     eax, 1
0x18000d087  jmp     short loc_18000D0B7
0x18000d089  mov     edx, [rsp+2B0h+cbData]
0x18000d08d  mov     r8, [rsp+2B0h+Src]
0x18000d092  mov     rcx, r15
0x18000d095  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18000d09a  mov     eax, [rsp+2B0h+Type]
0x18000d09e  mov     [r14], eax
0x18000d0a1  lea     rax, [rsp+2B0h+Data]
0x18000d0a6  mov     rcx, [rsp+2B0h+Src]; lpMem
0x18000d0ab  cmp     rcx, rax
0x18000d0ae  jz      short loc_18000D0B5
0x18000d0b0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d0b5  xor     eax, eax
0x18000d0b7  mov     rcx, [rbp+1B0h+var_50]
0x18000d0be  xor     rcx, rsp; StackCookie
0x18000d0c1  call    __security_check_cookie
0x18000d0c6  add     rsp, 278h
0x18000d0cd  pop     r15
0x18000d0cf  pop     r14
0x18000d0d1  pop     r13
0x18000d0d3  pop     r12
0x18000d0d5  pop     rdi
0x18000d0d6  pop     rsi
0x18000d0d7  pop     rbx
0x18000d0d8  pop     rbp
0x18000d0d9  retn
0x18000d0da  mov     edx, eax
0x18000d0dc  lea     rcx, aRegqueryvaluee; "RegQueryValueExW"
0x18000d0e3  call    ??$Throw@J@SystemError@@SAXPEB_WJ@Z; SystemError::Throw<long>(wchar_t const *,long)
0x18000d0e9  call    ?ThrowNewFailure@@YAXXZ; ThrowNewFailure(void)
```
