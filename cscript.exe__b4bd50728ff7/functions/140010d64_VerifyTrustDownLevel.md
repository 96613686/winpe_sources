# VerifyTrustDownLevel

- ea: `0x140010d64`
- end: `0x140010fcc`
- name: `VerifyTrustDownLevel`
- size: `616`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x14000ed30`

## callees

- `0x14000929c`
- `0x140010a20`
- `0x140010d64`
- `0x14001619a`
- `0x1400161d0`
- `0x140017010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x140010e7e`
- `msvcrt!wcsrchr` at `0x140010e7e`
- `KERNEL32!CloseHandle` at `0x140010f93`
- `KERNEL32!CloseHandle` at `0x140010f93`
- `KERNEL32!GetProcAddress` at `0x140010e11`
- `KERNEL32!GetProcAddress` at `0x140010e49`
- `KERNEL32!GetProcAddress` at `0x140010e63`
- `KERNEL32!GetProcAddress` at `0x140010e11`
- `KERNEL32!GetProcAddress` at `0x140010e49`
- `KERNEL32!GetProcAddress` at `0x140010e63`
- `KERNEL32!GetLastError` at `0x140010e1f`
- `KERNEL32!GetLastError` at `0x140010e1f`
- `KERNEL32!FreeLibrary` at `0x140010fa6`
- `KERNEL32!FreeLibrary` at `0x140010fa6`

## string_xrefs

- `0x140010dd2`: `wintrust.dll`

## pseudocode

```c
__int64 __fastcall VerifyTrustDownLevel(wchar_t *a1, const void *a2, int a3, __int64 a4, int a5)
{
  void *v5; // rdi
  FARPROC v6; // r15
  unsigned int v7; // esi
  int v8; // ebx
  FARPROC ProcAddress; // r13
  signed int LastError; // eax
  FARPROC v11; // r12
  wchar_t *v12; // rdi
  wchar_t *v13; // rax
  int v14; // eax
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  HMODULE hModule; // [rsp+38h] [rbp-C8h] BYREF
  int v18; // [rsp+40h] [rbp-C0h]
  void *v19; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *Str; // [rsp+50h] [rbp-B0h]
  LPCVOID lpBuffer; // [rsp+58h] [rbp-A8h]
  __int64 v22; // [rsp+60h] [rbp-A0h]
  __int128 v23; // [rsp+68h] [rbp-98h] BYREF
  __int128 v24; // [rsp+78h] [rbp-88h]
  _DWORD v25[10]; // [rsp+90h] [rbp-70h] BYREF
  __int128 *v26; // [rsp+B8h] [rbp-48h]
  int v27; // [rsp+C0h] [rbp-40h]
  __int64 v28; // [rsp+C8h] [rbp-38h]
  __int64 v29; // [rsp+D0h] [rbp-30h]
  int v30; // [rsp+D8h] [rbp-28h]
  _DWORD v31[4]; // [rsp+F0h] [rbp-10h] BYREF

  lpBuffer = a2;
  v18 = a3;
  Str = a1;
  v22 = a4;
  v31[0] = 11191659;
  v31[1] = 298896708;
  v31[2] = -1073692020;
  v31[3] = -292175281;
  memset_0(v25, 0, 0x58u);
  v5 = 0;
  v23 = 0;
  v19 = 0;
  v6 = 0;
  v24 = 0;
  hModule = 0;
  v7 = 0;
  v16 = 0;
  v8 = SafeLoadLibrary("wintrust.dll", &hModule);
  if ( v8 >= 0 )
  {
    ProcAddress = GetProcAddress(hModule, "WinVerifyTrust");
    if ( ProcAddress
      && (v11 = GetProcAddress(hModule, "WintrustGetRegPolicyFlags")) != 0
      && (v6 = GetProcAddress(hModule, "WintrustSetRegPolicyFlags")) != 0 )
    {
      v12 = Str;
      v13 = wcsrchr(Str, 0x2Eu);
      v8 = SafeCreateTempFile(v13, lpBuffer, v18, &v19, 0);
      if ( v8 < 0 )
      {
        v5 = v19;
      }
      else
      {
        memset_0(v25, 0, 0x58u);
        *((_QWORD *)&v23 + 1) = v12;
        v5 = v19;
        v25[0] = 88;
        v26 = &v23;
        v25[7] = 0;
        v27 = 0;
        v28 = 0;
        v29 = 0;
        v25[6] = 2 - (a5 != 0);
        v30 = 0;
        v25[8] = 1;
        *(_QWORD *)&v23 = 32;
        *((_QWORD *)&v24 + 1) = v22;
        *(_QWORD *)&v24 = v19;
        if ( a5
          || (((void (__fastcall *)(int *))v11)(&v16), v7 = v16 | 0x40000, (v16 | 0x40000) == v16)
          || ((unsigned int (__fastcall *)(_QWORD))v6)(v7) )
        {
          v14 = ((__int64 (__fastcall *)(_QWORD, _DWORD *, _DWORD *))ProcAddress)(0, v31, v25);
          v8 = v14;
          if ( !v14 )
            goto LABEL_16;
          if ( v14 > 0 )
            v8 = (unsigned __int16)v14 | 0x80070000;
          if ( v8 >= 0 )
LABEL_16:
            v8 = 0;
        }
        else
        {
          v8 = -2147467259;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  if ( v16 != v7 )
    v6();
  if ( v5 )
    CloseHandle(v5);
  if ( hModule )
    FreeLibrary(hModule);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140010d64  push    rbp
0x140010d66  push    rbx
0x140010d67  push    rsi
0x140010d68  push    rdi
0x140010d69  push    r12
0x140010d6b  push    r13
0x140010d6d  push    r15
0x140010d6f  lea     rbp, [rsp-10h]
0x140010d74  sub     rsp, 110h
0x140010d7b  mov     rax, cs:__security_cookie
0x140010d82  xor     rax, rsp
0x140010d85  mov     [rbp+40h+var_40], rax
0x140010d89  mov     [rsp+140h+lpBuffer], rdx
0x140010d8e  xor     edx, edx; Val
0x140010d90  mov     [rsp+140h+var_100], r8d
0x140010d95  mov     [rsp+140h+Str], rcx
0x140010d9a  lea     rcx, [rbp+40h+var_B0]; void *
0x140010d9e  mov     [rsp+140h+var_E0], r9
0x140010da3  lea     r8d, [rdx+58h]; Size
0x140010da7  mov     [rbp+40h+var_50], 0AAC56Bh
0x140010dae  mov     [rbp+40h+var_4C], 11D0CD44h
0x140010db5  mov     [rbp+40h+var_48], 0C000C28Ch
0x140010dbc  mov     [rbp+40h+var_44], 0EE95C24Fh
0x140010dc3  call    memset_0
0x140010dc8  xorps   xmm0, xmm0
0x140010dcb  lea     rdx, [rsp+140h+hModule]
0x140010dd0  xor     edi, edi
0x140010dd2  lea     rcx, aWintrustDll; "wintrust.dll"
0x140010dd9  movups  [rsp+140h+var_D8], xmm0
0x140010dde  mov     [rsp+140h+var_F8], rdi
0x140010de3  xor     r15d, r15d
0x140010de6  movups  [rsp+140h+var_C8], xmm0
0x140010deb  mov     [rsp+140h+hModule], rdi
0x140010df0  xor     esi, esi
0x140010df2  mov     [rsp+140h+var_110], edi
0x140010df6  call    SafeLoadLibrary
0x140010dfb  mov     ebx, eax
0x140010dfd  test    eax, eax
0x140010dff  js      loc_140010F7B
0x140010e05  mov     rcx, [rsp+140h+hModule]; hModule
0x140010e0a  lea     rdx, aWinverifytrust; "WinVerifyTrust"
0x140010e11  call    cs:__imp_GetProcAddress
0x140010e17  mov     r13, rax
0x140010e1a  test    rax, rax
0x140010e1d  jnz     short loc_140010E3D
0x140010e1f  call    cs:__imp_GetLastError
0x140010e25  mov     ebx, eax
0x140010e27  test    eax, eax
0x140010e29  jle     loc_140010F7B
0x140010e2f  movzx   ebx, ax
0x140010e32  or      ebx, 80070000h
0x140010e38  jmp     loc_140010F7B
0x140010e3d  mov     rcx, [rsp+140h+hModule]; hModule
0x140010e42  lea     rdx, aWintrustgetreg; "WintrustGetRegPolicyFlags"
0x140010e49  call    cs:__imp_GetProcAddress
0x140010e4f  mov     r12, rax
0x140010e52  test    rax, rax
0x140010e55  jz      short loc_140010E1F
0x140010e57  mov     rcx, [rsp+140h+hModule]; hModule
0x140010e5c  lea     rdx, aWintrustsetreg; "WintrustSetRegPolicyFlags"
0x140010e63  call    cs:__imp_GetProcAddress
0x140010e69  mov     r15, rax
0x140010e6c  test    rax, rax
0x140010e6f  jz      short loc_140010E1F
0x140010e71  mov     rdi, [rsp+140h+Str]
0x140010e76  mov     edx, 2Eh ; '.'; Ch
0x140010e7b  mov     rcx, rdi; Str
0x140010e7e  call    cs:__imp_wcsrchr
0x140010e84  mov     r8d, [rsp+140h+var_100]
0x140010e89  lea     r9, [rsp+140h+var_F8]
0x140010e8e  mov     rdx, [rsp+140h+lpBuffer]; lpBuffer
0x140010e93  mov     rcx, rax; lpWideCharStr
0x140010e96  mov     [rsp+140h+lpPathName], rsi; lpPathName
0x140010e9b  call    SafeCreateTempFile
0x140010ea0  mov     ebx, eax
0x140010ea2  test    eax, eax
0x140010ea4  js      loc_140010F76
0x140010eaa  mov     ebx, 58h ; 'X'
0x140010eaf  lea     rcx, [rbp+40h+var_B0]; void *
0x140010eb3  mov     r8d, ebx; Size
0x140010eb6  xor     edx, edx; Val
0x140010eb8  call    memset_0
0x140010ebd  mov     edx, [rbp+40h+arg_20]
0x140010ec0  xor     r8d, r8d
0x140010ec3  mov     eax, edx
0x140010ec5  mov     qword ptr [rsp+140h+var_D8+8], rdi
0x140010eca  mov     rdi, [rsp+140h+var_F8]
0x140010ecf  neg     eax
0x140010ed1  lea     rax, [rsp+140h+var_D8]
0x140010ed6  mov     [rbp+40h+var_B0], ebx
0x140010ed9  sbb     ecx, ecx
0x140010edb  mov     [rbp+40h+var_88], rax
0x140010edf  mov     rax, [rsp+140h+var_E0]
0x140010ee4  add     ecx, 2
0x140010ee7  mov     [rbp+40h+var_94], r8d
0x140010eeb  mov     [rbp+40h+var_80], r8d
0x140010eef  mov     [rbp+40h+var_78], r8
0x140010ef3  mov     [rbp+40h+var_70], r8
0x140010ef7  mov     [rbp+40h+var_98], ecx
0x140010efa  mov     [rbp+40h+var_68], r8d
0x140010efe  mov     [rbp+40h+var_90], 1
0x140010f05  mov     qword ptr [rsp+140h+var_D8], 20h ; ' '
0x140010f0e  mov     qword ptr [rbp+40h+var_C8+8], rax
0x140010f12  mov     qword ptr [rsp+140h+var_C8], rdi
0x140010f17  test    edx, edx
0x140010f19  jnz     short loc_140010F4B
0x140010f1b  lea     rcx, [rsp+140h+var_110]
0x140010f20  mov     rax, r12
0x140010f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010f28  mov     esi, [rsp+140h+var_110]
0x140010f2c  bts     esi, 12h
0x140010f30  cmp     esi, [rsp+140h+var_110]
0x140010f34  jz      short loc_140010F4B
0x140010f36  mov     ecx, esi
0x140010f38  mov     rax, r15
0x140010f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010f40  test    eax, eax
0x140010f42  jnz     short loc_140010F4B
0x140010f44  mov     ebx, 80004005h
0x140010f49  jmp     short loc_140010F7B
0x140010f4b  lea     r8, [rbp+40h+var_B0]
0x140010f4f  xor     ecx, ecx
0x140010f51  lea     rdx, [rbp+40h+var_50]
0x140010f55  mov     rax, r13
0x140010f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010f5d  mov     ebx, eax
0x140010f5f  test    eax, eax
0x140010f61  jz      short loc_140010F72
0x140010f63  jle     short loc_140010F6E
0x140010f65  movzx   ebx, ax
0x140010f68  or      ebx, 80070000h
0x140010f6e  test    ebx, ebx
0x140010f70  js      short loc_140010F7B
0x140010f72  xor     ebx, ebx
0x140010f74  jmp     short loc_140010F7B
0x140010f76  mov     rdi, [rsp+140h+var_F8]
0x140010f7b  mov     ecx, [rsp+140h+var_110]
0x140010f7f  cmp     ecx, esi
0x140010f81  jz      short loc_140010F8B
0x140010f83  mov     rax, r15
0x140010f86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010f8b  test    rdi, rdi
0x140010f8e  jz      short loc_140010F99
0x140010f90  mov     rcx, rdi; hObject
0x140010f93  call    cs:__imp_CloseHandle
0x140010f99  cmp     [rsp+140h+hModule], 0
0x140010f9f  jz      short loc_140010FAC
0x140010fa1  mov     rcx, [rsp+140h+hModule]; hLibModule
0x140010fa6  call    cs:__imp_FreeLibrary
0x140010fac  mov     eax, ebx
0x140010fae  mov     rcx, [rbp+40h+var_40]
0x140010fb2  xor     rcx, rsp; StackCookie
0x140010fb5  call    __security_check_cookie
0x140010fba  add     rsp, 110h
0x140010fc1  pop     r15
0x140010fc3  pop     r13
0x140010fc5  pop     r12
0x140010fc7  pop     rdi
0x140010fc8  pop     rsi
0x140010fc9  pop     rbx
0x140010fca  pop     rbp
0x140010fcb  retn
```
