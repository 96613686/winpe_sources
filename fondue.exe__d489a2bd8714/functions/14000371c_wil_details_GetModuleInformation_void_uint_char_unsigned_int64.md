# wil::details::GetModuleInformation(void *,uint *,char *,unsigned __int64)

- ea: `0x14000371c`
- end: `0x140003840`
- name: `?GetModuleInformation@details@wil@@YA_NPEAXPEAIPEAD_K@Z`
- size: `292`
- prototype: `bool __fastcall(LPCWSTR lpModuleName, void *, unsigned int *, char *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003360`

## callees

- `0x14000371c`
- `0x140004cd0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x140003762`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x140003762`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x14000379c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x14000379c`

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
0x14000371c  mov     [rsp+arg_18], rbx
0x140003721  push    rbp
0x140003722  push    rsi
0x140003723  push    rdi
0x140003724  sub     rsp, 150h
0x14000372b  mov     rax, cs:__security_cookie
0x140003732  xor     rax, rsp
0x140003735  mov     [rsp+168h+var_28], rax
0x14000373d  mov     rbx, rcx
0x140003740  mov     rbp, r9
0x140003743  xor     ecx, ecx
0x140003745  mov     rdi, r8
0x140003748  mov     [rsp+168h+phModule], rcx
0x14000374d  mov     rsi, rdx
0x140003750  test    rbx, rbx
0x140003753  jz      short loc_14000377A
0x140003755  lea     r8, [rsp+168h+phModule]; phModule
0x14000375a  mov     rdx, rbx; lpModuleName
0x14000375d  mov     ecx, 6; dwFlags
0x140003762  call    cs:__imp_GetModuleHandleExW
0x140003768  test    eax, eax
0x14000376a  jnz     short loc_140003775
0x14000376c  test    rsi, rsi
0x14000376f  jz      short loc_1400037A6
0x140003771  mov     [rsi], eax
0x140003773  jmp     short loc_1400037A6
0x140003775  mov     rcx, [rsp+168h+phModule]; hModule
0x14000377a  test    rsi, rsi
0x14000377d  jz      short loc_140003788
0x14000377f  test    rbx, rbx
0x140003782  jz      short loc_140003786
0x140003784  sub     ebx, ecx
0x140003786  mov     [rsi], ebx
0x140003788  test    rdi, rdi
0x14000378b  jz      loc_14000381B
0x140003791  mov     r8d, 104h; nSize
0x140003797  lea     rdx, [rsp+168h+Filename]; lpFilename
0x14000379c  call    cs:__imp_GetModuleFileNameA
0x1400037a2  test    eax, eax
0x1400037a4  jnz     short loc_1400037AA
0x1400037a6  xor     al, al
0x1400037a8  jmp     short loc_14000381D
0x1400037aa  lea     rcx, [rsp+168h+Filename]
0x1400037af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400037b3  inc     rax
0x1400037b6  cmp     byte ptr [rcx+rax], 0
0x1400037ba  jnz     short loc_1400037B3
0x1400037bc  lea     rcx, [rsp+168h+Filename]
0x1400037c1  add     rax, rcx
0x1400037c4  jmp     short loc_1400037CF
0x1400037c6  cmp     byte ptr [rax-1], 5Ch ; '\'
0x1400037ca  jz      short loc_1400037D9
0x1400037cc  dec     rax
0x1400037cf  lea     rcx, [rsp+168h+Filename]
0x1400037d4  cmp     rax, rcx
0x1400037d7  ja      short loc_1400037C6
0x1400037d9  test    rbp, rbp
0x1400037dc  jz      short loc_14000381B
0x1400037de  cmp     rbp, 7FFFFFFFh
0x1400037e5  jbe     short loc_1400037EC
0x1400037e7  mov     byte ptr [rdi], 0
0x1400037ea  jmp     short loc_14000381B
0x1400037ec  mov     ecx, 7FFFFFFEh
0x1400037f1  test    rcx, rcx
0x1400037f4  jz      short loc_14000380D
0x1400037f6  mov     dl, [rax]
0x1400037f8  test    dl, dl
0x1400037fa  jz      short loc_14000380D
0x1400037fc  mov     [rdi], dl
0x1400037fe  inc     rax
0x140003801  inc     rdi
0x140003804  dec     rcx
0x140003807  sub     rbp, 1
0x14000380b  jnz     short loc_1400037F1
0x14000380d  test    rbp, rbp
0x140003810  lea     rcx, [rdi-1]
0x140003814  cmovnz  rcx, rdi
0x140003818  mov     byte ptr [rcx], 0
0x14000381b  mov     al, 1
0x14000381d  mov     rcx, [rsp+168h+var_28]
0x140003825  xor     rcx, rsp; StackCookie
0x140003828  call    __security_check_cookie
0x14000382d  mov     rbx, [rsp+168h+arg_18]
0x140003835  add     rsp, 150h
0x14000383c  pop     rdi
0x14000383d  pop     rsi
0x14000383e  pop     rbp
0x14000383f  retn
```
