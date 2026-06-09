# wil::details::GetModuleInformation(void *,uint *,char *,unsigned __int64)

- ea: `0x140002630`
- end: `0x140002754`
- name: `?GetModuleInformation@details@wil@@YA_NPEAXPEAIPEAD_K@Z`
- size: `292`
- prototype: `bool __fastcall(LPCWSTR lpModuleName, void *, unsigned int *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002330`

## callees

- `0x140001380`
- `0x140002630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x1400026b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x1400026b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x140002676`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x140002676`

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
0x140002630  mov     [rsp+arg_18], rbx
0x140002635  push    rbp
0x140002636  push    rsi
0x140002637  push    rdi
0x140002638  sub     rsp, 150h
0x14000263f  mov     rax, cs:__security_cookie
0x140002646  xor     rax, rsp
0x140002649  mov     [rsp+168h+var_28], rax
0x140002651  mov     rbx, rcx
0x140002654  mov     rbp, r9
0x140002657  xor     ecx, ecx
0x140002659  mov     rdi, r8
0x14000265c  mov     [rsp+168h+phModule], rcx
0x140002661  mov     rsi, rdx
0x140002664  test    rbx, rbx
0x140002667  jz      short loc_14000268E
0x140002669  lea     r8, [rsp+168h+phModule]; phModule
0x14000266e  mov     rdx, rbx; lpModuleName
0x140002671  mov     ecx, 6; dwFlags
0x140002676  call    cs:__imp_GetModuleHandleExW
0x14000267c  test    eax, eax
0x14000267e  jnz     short loc_140002689
0x140002680  test    rsi, rsi
0x140002683  jz      short loc_1400026BA
0x140002685  mov     [rsi], eax
0x140002687  jmp     short loc_1400026BA
0x140002689  mov     rcx, [rsp+168h+phModule]; hModule
0x14000268e  test    rsi, rsi
0x140002691  jz      short loc_14000269C
0x140002693  test    rbx, rbx
0x140002696  jz      short loc_14000269A
0x140002698  sub     ebx, ecx
0x14000269a  mov     [rsi], ebx
0x14000269c  test    rdi, rdi
0x14000269f  jz      loc_14000272F
0x1400026a5  mov     r8d, 104h; nSize
0x1400026ab  lea     rdx, [rsp+168h+Filename]; lpFilename
0x1400026b0  call    cs:__imp_GetModuleFileNameA
0x1400026b6  test    eax, eax
0x1400026b8  jnz     short loc_1400026BE
0x1400026ba  xor     al, al
0x1400026bc  jmp     short loc_140002731
0x1400026be  lea     rcx, [rsp+168h+Filename]
0x1400026c3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400026c7  inc     rax
0x1400026ca  cmp     byte ptr [rcx+rax], 0
0x1400026ce  jnz     short loc_1400026C7
0x1400026d0  lea     rcx, [rsp+168h+Filename]
0x1400026d5  add     rax, rcx
0x1400026d8  jmp     short loc_1400026E3
0x1400026da  cmp     byte ptr [rax-1], 5Ch ; '\'
0x1400026de  jz      short loc_1400026ED
0x1400026e0  dec     rax
0x1400026e3  lea     rcx, [rsp+168h+Filename]
0x1400026e8  cmp     rax, rcx
0x1400026eb  ja      short loc_1400026DA
0x1400026ed  test    rbp, rbp
0x1400026f0  jz      short loc_14000272F
0x1400026f2  cmp     rbp, 7FFFFFFFh
0x1400026f9  jbe     short loc_140002700
0x1400026fb  mov     byte ptr [rdi], 0
0x1400026fe  jmp     short loc_14000272F
0x140002700  mov     ecx, 7FFFFFFEh
0x140002705  test    rcx, rcx
0x140002708  jz      short loc_140002721
0x14000270a  mov     dl, [rax]
0x14000270c  test    dl, dl
0x14000270e  jz      short loc_140002721
0x140002710  mov     [rdi], dl
0x140002712  inc     rax
0x140002715  inc     rdi
0x140002718  dec     rcx
0x14000271b  sub     rbp, 1
0x14000271f  jnz     short loc_140002705
0x140002721  test    rbp, rbp
0x140002724  lea     rcx, [rdi-1]
0x140002728  cmovnz  rcx, rdi
0x14000272c  mov     byte ptr [rcx], 0
0x14000272f  mov     al, 1
0x140002731  mov     rcx, [rsp+168h+var_28]
0x140002739  xor     rcx, rsp; StackCookie
0x14000273c  call    __security_check_cookie
0x140002741  mov     rbx, [rsp+168h+arg_18]
0x140002749  add     rsp, 150h
0x140002750  pop     rdi
0x140002751  pop     rsi
0x140002752  pop     rbp
0x140002753  retn
```
