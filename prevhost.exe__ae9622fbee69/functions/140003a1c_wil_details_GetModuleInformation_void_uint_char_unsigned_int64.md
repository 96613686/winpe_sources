# wil::details::GetModuleInformation(void *,uint *,char *,unsigned __int64)

- ea: `0x140003a1c`
- end: `0x140003b40`
- name: `?GetModuleInformation@details@wil@@YA_NPEAXPEAIPEAD_K@Z`
- size: `292`
- prototype: `bool __fastcall(LPCWSTR lpModuleName, void *, unsigned int *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003660`

## callees

- `0x140001470`
- `0x140003a1c`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x140003a62`
- `KERNEL32!GetModuleHandleExW` at `0x140003a62`
- `KERNEL32!GetModuleFileNameA` at `0x140003a9c`
- `KERNEL32!GetModuleFileNameA` at `0x140003a9c`

## pseudocode

```c
char __fastcall wil::details::GetModuleInformation(LPCWSTR lpModuleName, _DWORD *a2, unsigned int *a3, char *a4)
{
  HMODULE v6; // rcx
  __int64 v10; // rax
  CHAR *i; // rax
  __int64 v12; // rcx
  unsigned int *v13; // rcx
  HMODULE phModule; // [rsp+20h] [rbp-148h] BYREF
  CHAR Filename[272]; // [rsp+30h] [rbp-138h] BYREF

  v6 = 0;
  phModule = 0;
  if ( lpModuleName )
  {
    if ( !GetModuleHandleExW(6u, lpModuleName, &phModule) )
    {
      if ( a2 )
        *a2 = 0;
      return 0;
    }
    v6 = phModule;
  }
  if ( a2 )
  {
    if ( lpModuleName )
      LODWORD(lpModuleName) = (_DWORD)lpModuleName - (_DWORD)v6;
    *a2 = (_DWORD)lpModuleName;
  }
  if ( a3 )
  {
    if ( !GetModuleFileNameA(v6, Filename, 0x104u) )
      return 0;
    v10 = -1;
    do
      ++v10;
    while ( Filename[v10] );
    for ( i = &Filename[v10]; i > Filename && *(i - 1) != 92; --i )
      ;
    if ( a4 )
    {
      if ( (unsigned __int64)a4 <= 0x7FFFFFFF )
      {
        v12 = 2147483646;
        do
        {
          if ( !v12 )
            break;
          if ( !*i )
            break;
          *(_BYTE *)a3 = *i++;
          a3 = (unsigned int *)((char *)a3 + 1);
          --v12;
          --a4;
        }
        while ( a4 );
        v13 = (unsigned int *)((char *)a3 - 1);
        if ( a4 )
          v13 = a3;
        *(_BYTE *)v13 = 0;
      }
      else
      {
        *(_BYTE *)a3 = 0;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140003a1c  mov     [rsp+arg_18], rbx
0x140003a21  push    rbp
0x140003a22  push    rsi
0x140003a23  push    rdi
0x140003a24  sub     rsp, 150h
0x140003a2b  mov     rax, cs:__security_cookie
0x140003a32  xor     rax, rsp
0x140003a35  mov     [rsp+168h+var_28], rax
0x140003a3d  mov     rbx, rcx
0x140003a40  mov     rbp, r9
0x140003a43  xor     ecx, ecx
0x140003a45  mov     rdi, r8
0x140003a48  mov     [rsp+168h+phModule], rcx
0x140003a4d  mov     rsi, rdx
0x140003a50  test    rbx, rbx
0x140003a53  jz      short loc_140003A7A
0x140003a55  lea     r8, [rsp+168h+phModule]; phModule
0x140003a5a  mov     rdx, rbx; lpModuleName
0x140003a5d  mov     ecx, 6; dwFlags
0x140003a62  call    cs:__imp_GetModuleHandleExW
0x140003a68  test    eax, eax
0x140003a6a  jnz     short loc_140003A75
0x140003a6c  test    rsi, rsi
0x140003a6f  jz      short loc_140003AA6
0x140003a71  mov     [rsi], eax
0x140003a73  jmp     short loc_140003AA6
0x140003a75  mov     rcx, [rsp+168h+phModule]; hModule
0x140003a7a  test    rsi, rsi
0x140003a7d  jz      short loc_140003A88
0x140003a7f  test    rbx, rbx
0x140003a82  jz      short loc_140003A86
0x140003a84  sub     ebx, ecx
0x140003a86  mov     [rsi], ebx
0x140003a88  test    rdi, rdi
0x140003a8b  jz      loc_140003B1B
0x140003a91  mov     r8d, 104h; nSize
0x140003a97  lea     rdx, [rsp+168h+Filename]; lpFilename
0x140003a9c  call    cs:__imp_GetModuleFileNameA
0x140003aa2  test    eax, eax
0x140003aa4  jnz     short loc_140003AAA
0x140003aa6  xor     al, al
0x140003aa8  jmp     short loc_140003B1D
0x140003aaa  lea     rcx, [rsp+168h+Filename]
0x140003aaf  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003ab3  inc     rax
0x140003ab6  cmp     byte ptr [rcx+rax], 0
0x140003aba  jnz     short loc_140003AB3
0x140003abc  lea     rcx, [rsp+168h+Filename]
0x140003ac1  add     rax, rcx
0x140003ac4  jmp     short loc_140003ACF
0x140003ac6  cmp     byte ptr [rax-1], 5Ch ; '\'
0x140003aca  jz      short loc_140003AD9
0x140003acc  dec     rax
0x140003acf  lea     rcx, [rsp+168h+Filename]
0x140003ad4  cmp     rax, rcx
0x140003ad7  ja      short loc_140003AC6
0x140003ad9  test    rbp, rbp
0x140003adc  jz      short loc_140003B1B
0x140003ade  cmp     rbp, 7FFFFFFFh
0x140003ae5  jbe     short loc_140003AEC
0x140003ae7  mov     byte ptr [rdi], 0
0x140003aea  jmp     short loc_140003B1B
0x140003aec  mov     ecx, 7FFFFFFEh
0x140003af1  test    rcx, rcx
0x140003af4  jz      short loc_140003B0D
0x140003af6  mov     dl, [rax]
0x140003af8  test    dl, dl
0x140003afa  jz      short loc_140003B0D
0x140003afc  mov     [rdi], dl
0x140003afe  inc     rax
0x140003b01  inc     rdi
0x140003b04  dec     rcx
0x140003b07  sub     rbp, 1
0x140003b0b  jnz     short loc_140003AF1
0x140003b0d  test    rbp, rbp
0x140003b10  lea     rcx, [rdi-1]
0x140003b14  cmovnz  rcx, rdi
0x140003b18  mov     byte ptr [rcx], 0
0x140003b1b  mov     al, 1
0x140003b1d  mov     rcx, [rsp+168h+var_28]
0x140003b25  xor     rcx, rsp; StackCookie
0x140003b28  call    __security_check_cookie
0x140003b2d  mov     rbx, [rsp+168h+arg_18]
0x140003b35  add     rsp, 150h
0x140003b3c  pop     rdi
0x140003b3d  pop     rsi
0x140003b3e  pop     rbp
0x140003b3f  retn
```
