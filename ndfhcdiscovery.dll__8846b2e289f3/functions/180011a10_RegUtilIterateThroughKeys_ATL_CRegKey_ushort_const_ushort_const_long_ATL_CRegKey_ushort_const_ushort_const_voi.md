# RegUtilIterateThroughKeys(ATL::CRegKey &,ushort const *,ushort const *,long (*)(ATL::CRegKey &,ushort const *,ushort const *,void *),void *)

- ea: `0x180011a10`
- end: `0x180011cad`
- name: `?RegUtilIterateThroughKeys@@YAJAEAVCRegKey@ATL@@PEBG1P6AJ011PEAX@Z2@Z`
- size: `669`
- prototype: `__int64 __fastcall(struct ATL::CRegKey *, const unsigned __int16 *, const unsigned __int16 *, int (*)(struct ATL::CRegKey *, const unsigned __int16 *, const unsigned __int16 *, void *), void *)`
- caller_count: `6`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180007a20`
- `0x180008460`
- `0x18000bdf4`
- `0x18000ea98`
- `0x18000fd18`
- `0x18000fe80`

## callees

- `0x180003414`
- `0x180011a10`
- `0x180013686`
- `0x1800136b0`
- `0x180015010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180011be7`
- `ADVAPI32!RegCloseKey` at `0x180011c3a`
- `ADVAPI32!RegCloseKey` at `0x180011c7b`
- `ADVAPI32!RegCloseKey` at `0x180011be7`
- `ADVAPI32!RegCloseKey` at `0x180011c3a`
- `ADVAPI32!RegCloseKey` at `0x180011c7b`
- `ADVAPI32!RegOpenKeyExW` at `0x180011a87`
- `ADVAPI32!RegOpenKeyExW` at `0x180011bcb`
- `ADVAPI32!RegOpenKeyExW` at `0x180011a87`
- `ADVAPI32!RegOpenKeyExW` at `0x180011bcb`
- `ADVAPI32!RegEnumKeyExW` at `0x180011afe`
- `ADVAPI32!RegEnumKeyExW` at `0x180011afe`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LSTATUS __fastcall RegUtilIterateThroughKeys(
        HKEY *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int (*a4)(struct ATL::CRegKey *, const unsigned __int16 *, const unsigned __int16 *, void *),
        void *a5)
{
  HKEY *v7; // r15
  LSTATUS result; // eax
  int v9; // ebx
  DWORD v10; // r12d
  __int64 (__fastcall *v11)(HKEY *, WCHAR *, unsigned __int16 *, void *); // rsi
  LSTATUS v12; // eax
  int v13; // eax
  const unsigned __int16 *v14; // r9
  HKEY v15; // rcx
  bool v16; // cc
  int v17; // eax
  int v18; // edi
  struct _FILETIME ftLastWriteTime; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey[3]; // [rsp+50h] [rbp-B0h] BYREF
  void *v22; // [rsp+68h] [rbp-98h]
  HKEY v23[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v25[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  ftLastWriteTime = (struct _FILETIME)a4;
  v7 = a1;
  v22 = a5;
  memset(v23, 0, 24);
  if ( !a2 )
    goto LABEL_4;
  phkResult = 0;
  result = RegOpenKeyExW(*a1, a2, 0, 0x20019u, &phkResult);
  if ( !result )
  {
    v23[0] = phkResult;
    v7 = v23;
LABEL_4:
    v9 = 0;
    v10 = 0;
    v11 = (__int64 (__fastcall *)(HKEY *, WCHAR *, unsigned __int16 *, void *))ftLastWriteTime;
    while ( 1 )
    {
      LODWORD(phkResult) = 260;
      ftLastWriteTime = 0;
      v12 = RegEnumKeyExW(*v7, v10, Name, (LPDWORD)&phkResult, 0, 0, 0, &ftLastWriteTime);
      if ( v12 )
      {
        if ( v12 == 259 )
          goto LABEL_33;
        if ( v12 > 0 )
          v9 = (unsigned __int16)v12 | 0x80070000;
        else
          v9 = v12;
        goto LABEL_32;
      }
      memset_0(v25, 0, 0x208u);
      if ( a2 )
      {
        if ( a3 )
        {
          v13 = StringCchPrintfW(v25, 0x104u, L"%s\\%s\\%s", a3, a2, Name);
          goto LABEL_15;
        }
        v14 = a2;
      }
      else
      {
        v14 = a3;
      }
      v13 = StringCchPrintfW(v25, 0x104u, L"%s\\%s", v14, Name);
LABEL_15:
      v9 = v13;
      if ( v13 >= 0 )
      {
        memset(hKey, 0, sizeof(hKey));
        ftLastWriteTime = 0;
        v9 = RegOpenKeyExW(*v7, Name, 0, 0x20019u, (PHKEY)&ftLastWriteTime);
        v15 = hKey[0];
        if ( v9 )
        {
          v16 = v9 < 0;
        }
        else
        {
          if ( hKey[0] )
            v9 = RegCloseKey(hKey[0]);
          v15 = (HKEY)ftLastWriteTime;
          hKey[0] = (HKEY)ftLastWriteTime;
          v16 = v9 <= 0;
          if ( !v9 )
          {
            v17 = v11(hKey, Name, v25, v22);
            if ( v17 >= 0 )
              v9 = v17;
            v15 = hKey[0];
LABEL_26:
            if ( v15 )
              RegCloseKey(v15);
            goto LABEL_32;
          }
        }
        if ( !v16 )
          v9 = (unsigned __int16)v9 | 0x80070000;
        goto LABEL_26;
      }
LABEL_32:
      ++v10;
      if ( v9 < 0 )
      {
LABEL_33:
        v18 = 0;
        if ( v9 >= 0 )
          v18 = v9;
        if ( v23[0] )
          RegCloseKey(v23[0]);
        return v18;
      }
    }
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180011a10  push    rbp
0x180011a12  push    rbx
0x180011a13  push    rsi
0x180011a14  push    rdi
0x180011a15  push    r12
0x180011a17  push    r13
0x180011a19  push    r14
0x180011a1b  push    r15
0x180011a1d  lea     rbp, [rsp-3C8h]
0x180011a25  sub     rsp, 4C8h
0x180011a2c  mov     rax, cs:__security_cookie
0x180011a33  xor     rax, rsp
0x180011a36  mov     [rbp+400h+var_50], rax
0x180011a3d  mov     qword ptr [rsp+500h+ftLastWriteTime.dwLowDateTime], r9
0x180011a42  mov     r13, r8
0x180011a45  mov     r14, rdx
0x180011a48  mov     r15, rcx
0x180011a4b  mov     rax, [rbp+400h+arg_20]
0x180011a52  mov     [rsp+500h+var_498], rax
0x180011a57  xor     esi, esi
0x180011a59  mov     [rsp+500h+var_490], rsi
0x180011a5e  mov     [rsp+500h+var_488], rsi
0x180011a63  mov     [rbp+400h+var_480], rsi
0x180011a67  test    rdx, rdx
0x180011a6a  jz      short loc_180011AAA
0x180011a6c  mov     [rsp+500h+var_4B8], rsi
0x180011a71  lea     rax, [rsp+500h+var_4B8]
0x180011a76  mov     [rsp+500h+phkResult], rax; phkResult
0x180011a7b  mov     r9d, 20019h; samDesired
0x180011a81  xor     r8d, r8d; ulOptions
0x180011a84  mov     rcx, [rcx]; hKey
0x180011a87  call    cs:__imp_RegOpenKeyExW
0x180011a8e  nop     dword ptr [rax+rax+00h]
0x180011a93  test    eax, eax
0x180011a95  jnz     loc_180011B5B
0x180011a9b  mov     rsi, [rsp+500h+var_4B8]
0x180011aa0  mov     [rsp+500h+var_490], rsi
0x180011aa5  lea     r15, [rsp+500h+var_490]
0x180011aaa  xor     ebx, ebx
0x180011aac  xor     r12d, r12d
0x180011aaf  mov     edi, 80070000h
0x180011ab4  mov     rsi, qword ptr [rsp+500h+ftLastWriteTime.dwLowDateTime]
0x180011ab9  mov     dword ptr [rsp+500h+var_4B8], 104h
0x180011ac1  mov     qword ptr [rsp+500h+ftLastWriteTime.dwLowDateTime], 0
0x180011aca  lea     rax, [rsp+500h+ftLastWriteTime]
0x180011acf  mov     [rsp+500h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180011ad4  mov     [rsp+500h+lpcchClass], 0; lpcchClass
0x180011add  mov     [rsp+500h+lpClass], 0; lpClass
0x180011ae6  mov     [rsp+500h+phkResult], 0; lpReserved
0x180011aef  lea     r9, [rsp+500h+var_4B8]; lpcchName
0x180011af4  lea     r8, [rbp+400h+Name]; lpName
0x180011af8  mov     edx, r12d; dwIndex
0x180011afb  mov     rcx, [r15]; hKey
0x180011afe  call    cs:__imp_RegEnumKeyExW
0x180011b05  nop     dword ptr [rax+rax+00h]
0x180011b0a  test    eax, eax
0x180011b0c  jnz     loc_180011C48
0x180011b12  xor     edx, edx; Val
0x180011b14  mov     r8d, 208h; Size
0x180011b1a  lea     rcx, [rbp+400h+var_260]; void *
0x180011b21  call    memset_0
0x180011b26  lea     rax, [rbp+400h+Name]
0x180011b2a  mov     edx, 104h; unsigned __int64
0x180011b2f  lea     rcx, [rbp+400h+var_260]; unsigned __int16 *
0x180011b36  test    r14, r14
0x180011b39  jz      short loc_180011B6F
0x180011b3b  test    r13, r13
0x180011b3e  jz      short loc_180011B6A
0x180011b40  mov     [rsp+500h+lpClass], rax
0x180011b45  mov     [rsp+500h+phkResult], r14
0x180011b4a  mov     r9, r13
0x180011b4d  lea     r8, aSSS; "%s\\%s\\%s"
0x180011b54  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011b59  jmp     short loc_180011B83
0x180011b5b  jle     short loc_180011B65
0x180011b5d  movzx   eax, ax
0x180011b60  or      eax, 80070000h
0x180011b65  jmp     loc_180011C89
0x180011b6a  mov     r9, r14
0x180011b6d  jmp     short loc_180011B72
0x180011b6f  mov     r9, r13
0x180011b72  mov     [rsp+500h+phkResult], rax
0x180011b77  lea     r8, aSS; "%s\\%s"
0x180011b7e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011b83  mov     ebx, eax
0x180011b85  test    eax, eax
0x180011b87  js      loc_180011C5C
0x180011b8d  mov     [rsp+500h+hKey], 0
0x180011b96  mov     [rsp+500h+var_4A8], 0
0x180011b9f  mov     [rsp+500h+var_4A0], 0
0x180011ba8  mov     qword ptr [rsp+500h+ftLastWriteTime.dwLowDateTime], 0
0x180011bb1  lea     rax, [rsp+500h+ftLastWriteTime]
0x180011bb6  mov     [rsp+500h+phkResult], rax; phkResult
0x180011bbb  mov     r9d, 20019h; samDesired
0x180011bc1  xor     r8d, r8d; ulOptions
0x180011bc4  lea     rdx, [rbp+400h+Name]; lpSubKey
0x180011bc8  mov     rcx, [r15]; hKey
0x180011bcb  call    cs:__imp_RegOpenKeyExW
0x180011bd2  nop     dword ptr [rax+rax+00h]
0x180011bd7  mov     ebx, eax
0x180011bd9  mov     rcx, [rsp+500h+hKey]; hKey
0x180011bde  test    eax, eax
0x180011be0  jnz     short loc_180011C2C
0x180011be2  test    rcx, rcx
0x180011be5  jz      short loc_180011BF5
0x180011be7  call    cs:__imp_RegCloseKey
0x180011bee  nop     dword ptr [rax+rax+00h]
0x180011bf3  mov     ebx, eax
0x180011bf5  mov     rcx, qword ptr [rsp+500h+ftLastWriteTime.dwLowDateTime]
0x180011bfa  mov     [rsp+500h+hKey], rcx
0x180011bff  test    ebx, ebx
0x180011c01  jnz     short loc_180011C2E
0x180011c03  mov     r9, [rsp+500h+var_498]
0x180011c08  lea     r8, [rbp+400h+var_260]
0x180011c0f  lea     rdx, [rbp+400h+Name]
0x180011c13  lea     rcx, [rsp+500h+hKey]
0x180011c18  mov     rax, rsi
0x180011c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c20  test    eax, eax
0x180011c22  cmovns  ebx, eax
0x180011c25  mov     rcx, [rsp+500h+hKey]
0x180011c2a  jmp     short loc_180011C35
0x180011c2c  test    ebx, ebx
0x180011c2e  jle     short loc_180011C35
0x180011c30  movzx   ebx, bx
0x180011c33  or      ebx, edi
0x180011c35  test    rcx, rcx
0x180011c38  jz      short loc_180011C5C
0x180011c3a  call    cs:__imp_RegCloseKey
0x180011c41  nop     dword ptr [rax+rax+00h]
0x180011c46  jmp     short loc_180011C5C
0x180011c48  cmp     eax, 103h
0x180011c4d  jz      short loc_180011C67
0x180011c4f  test    eax, eax
0x180011c51  jg      short loc_180011C57
0x180011c53  mov     ebx, eax
0x180011c55  jmp     short loc_180011C5C
0x180011c57  movzx   ebx, ax
0x180011c5a  or      ebx, edi
0x180011c5c  inc     r12d
0x180011c5f  test    ebx, ebx
0x180011c61  jns     loc_180011AB9
0x180011c67  xor     edi, edi
0x180011c69  test    ebx, ebx
0x180011c6b  cmovns  edi, ebx
0x180011c6e  mov     rsi, [rsp+500h+var_490]
0x180011c73  test    rsi, rsi
0x180011c76  jz      short loc_180011C87
0x180011c78  mov     rcx, rsi; hKey
0x180011c7b  call    cs:__imp_RegCloseKey
0x180011c82  nop     dword ptr [rax+rax+00h]
0x180011c87  mov     eax, edi
0x180011c89  mov     rcx, [rbp+400h+var_50]
0x180011c90  xor     rcx, rsp; StackCookie
0x180011c93  call    __security_check_cookie
0x180011c98  add     rsp, 4C8h
0x180011c9f  pop     r15
0x180011ca1  pop     r14
0x180011ca3  pop     r13
0x180011ca5  pop     r12
0x180011ca7  pop     rdi
0x180011ca8  pop     rsi
0x180011ca9  pop     rbx
0x180011caa  pop     rbp
0x180011cab  retn
```
