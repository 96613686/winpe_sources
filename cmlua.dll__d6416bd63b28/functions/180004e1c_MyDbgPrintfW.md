# MyDbgPrintfW

- ea: `0x180004e1c`
- end: `0x180004ff3`
- name: `MyDbgPrintfW`
- size: `471`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `5`
- tags: ``

## callers

- `0x180002144`
- `0x180002420`
- `0x1800026b0`
- `0x1800029d4`
- `0x180002af0`
- `0x180003090`
- `0x180003150`
- `0x1800035ec`
- `0x1800038d0`
- `0x1800039c0`
- `0x180003ab0`
- `0x180003ba0`
- `0x180003cd0`
- `0x1800044c8`
- `0x180004564`
- `0x1800047e0`
- `0x180004aac`

## callees

- `0x180004c60`
- `0x180004e1c`
- `0x180005486`
- `0x1800054b0`
- `0x180006010`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x180004f6d`
- `msvcrt!_vsnprintf` at `0x180004f6d`
- `KERNEL32!WideCharToMultiByte` at `0x180004e9f`
- `KERNEL32!WideCharToMultiByte` at `0x180004eef`
- `KERNEL32!WideCharToMultiByte` at `0x180004e9f`
- `KERNEL32!WideCharToMultiByte` at `0x180004eef`
- `KERNEL32!LocalAlloc` at `0x180004eb4`
- `KERNEL32!LocalAlloc` at `0x180004eb4`
- `KERNEL32!LocalFree` at `0x180004f9d`
- `KERNEL32!LocalFree` at `0x180004f9d`
- `KERNEL32!lstrlenA` at `0x180004f8a`
- `KERNEL32!lstrlenA` at `0x180004f8a`

## pseudocode

```c
HLOCAL __fastcall MyDbgPrintfW(unsigned int a1, const WCHAR *a2, __int64 a3, __int64 a4)
{
  char *v6; // rdi
  unsigned int v7; // eax
  int cbMultiByte; // esi
  CHAR *lpMultiByteStr; // rax
  char v10; // al
  char *v11; // rdx
  BOOL v12; // ecx
  unsigned int v13; // eax
  HLOCAL result; // rax
  __int64 (__fastcall *v15)(_QWORD, __int64, char *); // rbx
  char Buffer[1535]; // [rsp+50h] [rbp-638h] BYREF
  char v17; // [rsp+64Fh] [rbp-39h]
  __int64 ArgList; // [rsp+6A0h] [rbp+18h] BYREF
  __int64 v19; // [rsp+6A8h] [rbp+20h]

  ArgList = a3;
  v19 = a4;
  memset_0(Buffer, 0, 0x600u);
  v6 = 0;
  if ( a2 )
  {
    if ( *a2 )
    {
      v7 = WideCharToMultiByte(0, 0x400u, a2, -1, 0, 0, 0, 0);
      cbMultiByte = v7;
      if ( v7 )
      {
        lpMultiByteStr = (CHAR *)LocalAlloc(0x40u, v7);
        v6 = lpMultiByteStr;
        if ( lpMultiByteStr )
        {
          if ( WideCharToMultiByte(0, 0x400u, a2, -1, lpMultiByteStr, cbMultiByte, 0, 0) )
          {
            v10 = *v6;
            if ( *v6 )
            {
              v11 = v6;
              v12 = 0;
              do
              {
                switch ( v10 )
                {
                  case '%':
                    v12 = !v12;
                    break;
                  case 'C':
                    if ( v12 )
                      *v11 = 99;
                    break;
                  case 'S':
                    if ( v12 )
                      *v11 = 115;
                    break;
                  case 'c':
                    if ( v12 )
                      *v11 = 67;
                    break;
                  case 's':
                    if ( v12 )
                      *v11 = 83;
                    break;
                  default:
                    v12 = 0;
                    break;
                }
                v10 = *++v11;
              }
              while ( *v11 );
            }
            v13 = _vsnprintf(Buffer, 0x5FFu, v6, (va_list)&ArgList);
            if ( v13 >= 0x600 )
            {
              v17 = 0;
            }
            else
            {
              if ( v13 == 1535 )
                v17 = 0;
              lstrlenA(Buffer);
            }
          }
        }
      }
    }
  }
  result = LocalFree(v6);
  if ( a1 != -1 )
  {
    v15 = (__int64 (__fastcall *)(_QWORD, __int64, char *))g_pTracePrintfEx;
    if ( g_pTracePrintfEx )
    {
      DuplicatePercentileSymbol(Buffer, 1536);
      return (HLOCAL)v15(a1, 12, Buffer);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004e1c  mov     [rsp+arg_8], rdx
0x180004e21  mov     [rsp+ArgList], r8
0x180004e26  mov     [rsp+arg_18], r9
0x180004e2b  push    rbx
0x180004e2c  push    rbp
0x180004e2d  push    rsi
0x180004e2e  push    rdi
0x180004e2f  sub     rsp, 668h
0x180004e36  mov     rax, cs:__security_cookie
0x180004e3d  xor     rax, rsp
0x180004e40  mov     [rsp+688h+var_38], rax
0x180004e48  mov     rbx, rdx
0x180004e4b  mov     [rsp+688h+var_648], 0
0x180004e54  mov     ebp, ecx
0x180004e56  xor     edx, edx; Val
0x180004e58  lea     rcx, [rsp+688h+Buffer]; void *
0x180004e5d  mov     r8d, 600h; Size
0x180004e63  call    memset_0
0x180004e68  xor     edi, edi
0x180004e6a  test    rbx, rbx
0x180004e6d  jz      loc_180004F9A
0x180004e73  xor     eax, eax
0x180004e75  cmp     ax, [rbx]
0x180004e78  jz      loc_180004F9A
0x180004e7e  mov     [rsp+688h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x180004e83  or      r9d, 0FFFFFFFFh; cchWideChar
0x180004e87  mov     [rsp+688h+lpDefaultChar], rax; lpDefaultChar
0x180004e8c  mov     r8, rbx; lpWideCharStr
0x180004e8f  mov     [rsp+688h+cbMultiByte], eax; cbMultiByte
0x180004e93  mov     edx, 400h; dwFlags
0x180004e98  xor     ecx, ecx; CodePage
0x180004e9a  mov     [rsp+688h+lpMultiByteStr], rax; lpMultiByteStr
0x180004e9f  call    cs:__imp_WideCharToMultiByte
0x180004ea5  mov     esi, eax
0x180004ea7  test    eax, eax
0x180004ea9  jz      loc_180004F9A
0x180004eaf  mov     edx, esi; uBytes
0x180004eb1  lea     ecx, [rdi+40h]; uFlags
0x180004eb4  call    cs:__imp_LocalAlloc
0x180004eba  mov     rdi, rax
0x180004ebd  test    rax, rax
0x180004ec0  jz      loc_180004F9A
0x180004ec6  mov     [rsp+688h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180004ecf  or      r9d, 0FFFFFFFFh; cchWideChar
0x180004ed3  mov     [rsp+688h+lpDefaultChar], 0; lpDefaultChar
0x180004edc  mov     r8, rbx; lpWideCharStr
0x180004edf  mov     [rsp+688h+cbMultiByte], esi; cbMultiByte
0x180004ee3  mov     edx, 400h; dwFlags
0x180004ee8  xor     ecx, ecx; CodePage
0x180004eea  mov     [rsp+688h+lpMultiByteStr], rax; lpMultiByteStr
0x180004eef  call    cs:__imp_WideCharToMultiByte
0x180004ef5  test    eax, eax
0x180004ef7  jz      loc_180004F9A
0x180004efd  mov     al, [rdi]
0x180004eff  test    al, al
0x180004f01  jz      short loc_180004F56
0x180004f03  mov     rdx, rdi
0x180004f06  xor     ecx, ecx
0x180004f08  cmp     al, 25h ; '%'
0x180004f0a  jz      short loc_180004F44
0x180004f0c  cmp     al, 43h ; 'C'
0x180004f0e  jz      short loc_180004F3B
0x180004f10  cmp     al, 53h ; 'S'
0x180004f12  jz      short loc_180004F32
0x180004f14  cmp     al, 63h ; 'c'
0x180004f16  jz      short loc_180004F29
0x180004f18  cmp     al, 73h ; 's'
0x180004f1a  jz      short loc_180004F20
0x180004f1c  xor     ecx, ecx
0x180004f1e  jmp     short loc_180004F4D
0x180004f20  test    ecx, ecx
0x180004f22  jz      short loc_180004F4D
0x180004f24  mov     byte ptr [rdx], 53h ; 'S'
0x180004f27  jmp     short loc_180004F4D
0x180004f29  test    ecx, ecx
0x180004f2b  jz      short loc_180004F4D
0x180004f2d  mov     byte ptr [rdx], 43h ; 'C'
0x180004f30  jmp     short loc_180004F4D
0x180004f32  test    ecx, ecx
0x180004f34  jz      short loc_180004F4D
0x180004f36  mov     byte ptr [rdx], 73h ; 's'
0x180004f39  jmp     short loc_180004F4D
0x180004f3b  test    ecx, ecx
0x180004f3d  jz      short loc_180004F4D
0x180004f3f  mov     byte ptr [rdx], 63h ; 'c'
0x180004f42  jmp     short loc_180004F4D
0x180004f44  xor     eax, eax
0x180004f46  test    ecx, ecx
0x180004f48  setz    al
0x180004f4b  mov     ecx, eax
0x180004f4d  inc     rdx
0x180004f50  mov     al, [rdx]
0x180004f52  test    al, al
0x180004f54  jnz     short loc_180004F08
0x180004f56  mov     ebx, 5FFh
0x180004f5b  lea     r9, [rsp+688h+ArgList]; ArgList
0x180004f63  mov     edx, ebx; BufferCount
0x180004f65  lea     rcx, [rsp+688h+Buffer]; Buffer
0x180004f6a  mov     r8, rdi; Format
0x180004f6d  call    cs:__imp__vsnprintf
0x180004f73  test    eax, eax
0x180004f75  js      short loc_180004F92
0x180004f77  cmp     eax, ebx
0x180004f79  ja      short loc_180004F92
0x180004f7b  jnz     short loc_180004F85
0x180004f7d  mov     [rsp+688h+var_39], 0
0x180004f85  lea     rcx, [rsp+688h+Buffer]; lpString
0x180004f8a  call    cs:__imp_lstrlenA
0x180004f90  jmp     short loc_180004F9A
0x180004f92  mov     [rsp+688h+var_39], 0
0x180004f9a  mov     rcx, rdi; hMem
0x180004f9d  call    cs:__imp_LocalFree
0x180004fa3  cmp     ebp, 0FFFFFFFFh
0x180004fa6  jz      short loc_180004FD7
0x180004fa8  mov     rbx, cs:g_pTracePrintfEx
0x180004faf  test    rbx, rbx
0x180004fb2  jz      short loc_180004FD7
0x180004fb4  mov     edx, 600h
0x180004fb9  lea     rcx, [rsp+688h+Buffer]
0x180004fbe  call    DuplicatePercentileSymbol
0x180004fc3  lea     r8, [rsp+688h+Buffer]
0x180004fc8  mov     edx, 0Ch
0x180004fcd  mov     ecx, ebp
0x180004fcf  mov     rax, rbx
0x180004fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fd7  mov     rcx, [rsp+688h+var_38]
0x180004fdf  xor     rcx, rsp; StackCookie
0x180004fe2  call    __security_check_cookie
0x180004fe7  add     rsp, 668h
0x180004fee  pop     rdi
0x180004fef  pop     rsi
0x180004ff0  pop     rbp
0x180004ff1  pop     rbx
0x180004ff2  retn
```
