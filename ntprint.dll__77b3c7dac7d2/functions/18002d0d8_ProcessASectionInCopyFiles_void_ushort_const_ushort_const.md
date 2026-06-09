# ProcessASectionInCopyFiles(void *,ushort const *,ushort const *)

- ea: `0x18002d0d8`
- end: `0x18002d2fa`
- name: `?ProcessASectionInCopyFiles@@YAJPEAXPEBG1@Z`
- size: `546`
- prototype: `__int64 __fastcall(HINF InfHandle, LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x18002d50c`

## callees

- `0x18000b200`
- `0x180018d18`
- `0x18002c89c`
- `0x18002d0d8`
- `0x18002ddd0`
- `0x18002e0a4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d2de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d2de`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002d1f0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18002d1f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d1c7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d1c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d2b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d2b5`
- `SETUPAPI!SetupFindNextLine` at `0x18002d285`
- `SETUPAPI!SetupFindNextLine` at `0x18002d285`
- `SETUPAPI!SetupFindFirstLineW` at `0x18002d15d`
- `SETUPAPI!SetupFindFirstLineW` at `0x18002d15d`

## pseudocode

```c
__int64 __fastcall ProcessASectionInCopyFiles(char *InfHandle, LPCWSTR lpFileName, const unsigned __int16 *a3)
{
  int v6; // edi
  __int64 FileW; // rsi
  NCoreLibrary *v8; // rcx
  int LastErrorAsFailHR; // ebx
  NCoreLibrary *v10; // rcx
  struct _INFCONTEXT Context; // [rsp+40h] [rbp-38h] BYREF
  struct _INFCONTEXT ContextOut; // [rsp+58h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+B0h] [rbp+38h] BYREF

  if ( (unsigned __int64)(InfHandle - 1) <= 0xFFFFFFFFFFFFFFFDuLL && lpFileName && a3 )
  {
    v6 = ProcessSectionIfExists(InfHandle, lpFileName, L"DestinationDirs", a3, 0, 0);
    if ( v6 >= 0 )
    {
      hMem = 0;
      memset(&Context, 0, sizeof(Context));
      FileW = -1;
      if ( SetupFindFirstLineW(InfHandle, a3, 0, &Context) )
        LastErrorAsFailHR = 0;
      else
        LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v8);
      if ( LastErrorAsFailHR < 0 )
        goto LABEL_24;
      do
      {
        LastErrorAsFailHR = GetLineText(&Context, (unsigned __int16 **)&hMem);
        if ( LastErrorAsFailHR >= 0 )
        {
          if ( FileW != -1
            || ((FileW = (__int64)CreateFileW(lpFileName, 0x40000000u, 2u, 0, 3u, 0x80u, 0), FileW != -1)
             || (LastErrorAsFailHR = GetLastErrorAsHResult(), LastErrorAsFailHR >= 0))
            && (SetFilePointer((HANDLE)FileW, 0, 0, 2u) != -1
             || (LastErrorAsFailHR = GetLastErrorAsHResult(), LastErrorAsFailHR >= 0))
            && (LastErrorAsFailHR = WriteToFile((HANDLE)FileW, L"\n["), LastErrorAsFailHR >= 0)
            && (LastErrorAsFailHR = WriteToFile((HANDLE)FileW, a3), LastErrorAsFailHR >= 0)
            && (LastErrorAsFailHR = WriteToFile((HANDLE)FileW, L"]\n"), LastErrorAsFailHR >= 0) )
          {
            LastErrorAsFailHR = WriteToFile((HANDLE)FileW, (LPCWCH)hMem);
            if ( LastErrorAsFailHR >= 0 )
            {
              LastErrorAsFailHR = WriteToFile((HANDLE)FileW, L"\n");
              if ( LastErrorAsFailHR >= 0 )
              {
                memset(&ContextOut, 0, sizeof(ContextOut));
                if ( SetupFindNextLine(&Context, &ContextOut) )
                  LastErrorAsFailHR = 0;
                else
                  LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v10);
                Context = ContextOut;
              }
            }
          }
        }
LABEL_24:
        if ( hMem )
        {
          LocalFree(hMem);
          hMem = 0;
        }
      }
      while ( LastErrorAsFailHR >= 0 );
      v6 = 0;
      if ( (_WORD)LastErrorAsFailHR != 258 )
        v6 = LastErrorAsFailHR;
      if ( FileW != -1 )
        CloseHandle((HANDLE)FileW);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002d0d8  push    rbp
0x18002d0da  push    rbx
0x18002d0db  push    rsi
0x18002d0dc  push    rdi
0x18002d0dd  push    r14
0x18002d0df  push    r15
0x18002d0e1  mov     rbp, rsp
0x18002d0e4  sub     rsp, 78h
0x18002d0e8  lea     rax, [rcx-1]
0x18002d0ec  mov     r14, r8
0x18002d0ef  mov     r15, rdx
0x18002d0f2  mov     rbx, rcx
0x18002d0f5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002d0f9  ja      loc_18002D2E6
0x18002d0ff  test    rdx, rdx
0x18002d102  jz      loc_18002D2E6
0x18002d108  test    r8, r8
0x18002d10b  jz      loc_18002D2E6
0x18002d111  mov     r9, r8; unsigned __int16 *
0x18002d114  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], 0; unsigned __int16 *
0x18002d11d  lea     r8, cszDestinationDirs; "DestinationDirs"
0x18002d124  mov     [rsp+78h+dwCreationDisposition], 0; int
0x18002d12c  call    ?ProcessSectionIfExists@@YAJPEAXPEBG11H1@Z; ProcessSectionIfExists(void *,ushort const *,ushort const *,ushort const *,int,ushort const *)
0x18002d131  mov     edi, eax
0x18002d133  test    eax, eax
0x18002d135  js      loc_18002D2EB
0x18002d13b  xor     eax, eax
0x18002d13d  lea     r9, [rbp+Context]; Context
0x18002d141  xorps   xmm0, xmm0
0x18002d144  mov     qword ptr [rbp+Context.Section], rax
0x18002d148  xor     r8d, r8d; Key
0x18002d14b  mov     [rbp+hMem], rax
0x18002d14f  mov     rdx, r14; Section
0x18002d152  mov     rcx, rbx; InfHandle
0x18002d155  movups  xmmword ptr [rbp+Context.Inf], xmm0
0x18002d159  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002d15d  call    cs:__imp_SetupFindFirstLineW
0x18002d163  test    eax, eax
0x18002d165  jz      short loc_18002D16B
0x18002d167  xor     ebx, ebx
0x18002d169  jmp     short loc_18002D172
0x18002d16b  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002d170  mov     ebx, eax
0x18002d172  mov     edi, 2
0x18002d177  test    ebx, ebx
0x18002d179  js      loc_18002D2AC
0x18002d17f  lea     rdx, [rbp+hMem]; unsigned __int16 **
0x18002d183  lea     rcx, [rbp+Context]; struct _INFCONTEXT *
0x18002d187  call    ?GetLineText@@YAJPEAU_INFCONTEXT@@PEAPEAG@Z; GetLineText(_INFCONTEXT *,ushort * *)
0x18002d18c  mov     ebx, eax
0x18002d18e  test    eax, eax
0x18002d190  js      loc_18002D2AC
0x18002d196  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002d19a  jnz     loc_18002D249
0x18002d1a0  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18002d1a9  xor     r9d, r9d; lpSecurityAttributes
0x18002d1ac  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002d1b4  mov     r8d, edi; dwShareMode
0x18002d1b7  mov     edx, 40000000h; dwDesiredAccess
0x18002d1bc  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18002d1c4  mov     rcx, r15; lpFileName
0x18002d1c7  call    cs:__imp_CreateFileW
0x18002d1cd  mov     rsi, rax
0x18002d1d0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d1d4  jnz     short loc_18002D1E5
0x18002d1d6  call    GetLastErrorAsHResult
0x18002d1db  mov     ebx, eax
0x18002d1dd  test    eax, eax
0x18002d1df  js      loc_18002D2AC
0x18002d1e5  mov     r9d, edi; dwMoveMethod
0x18002d1e8  xor     r8d, r8d; lpDistanceToMoveHigh
0x18002d1eb  xor     edx, edx; lDistanceToMove
0x18002d1ed  mov     rcx, rsi; hFile
0x18002d1f0  call    cs:__imp_SetFilePointer
0x18002d1f6  cmp     eax, 0FFFFFFFFh
0x18002d1f9  jnz     short loc_18002D20A
0x18002d1fb  call    GetLastErrorAsHResult
0x18002d200  mov     ebx, eax
0x18002d202  test    eax, eax
0x18002d204  js      loc_18002D2AC
0x18002d20a  lea     rdx, WideCharStr; "\n["
0x18002d211  mov     rcx, rsi; hFile
0x18002d214  call    ?WriteToFile@@YAJPEAXPEBG@Z; WriteToFile(void *,ushort const *)
0x18002d219  mov     ebx, eax
0x18002d21b  test    eax, eax
0x18002d21d  js      loc_18002D2AC
0x18002d223  mov     rdx, r14; lpWideCharStr
0x18002d226  mov     rcx, rsi; hFile
0x18002d229  call    ?WriteToFile@@YAJPEAXPEBG@Z; WriteToFile(void *,ushort const *)
0x18002d22e  mov     ebx, eax
0x18002d230  test    eax, eax
0x18002d232  js      short loc_18002D2AC
0x18002d234  lea     rdx, asc_18004A924; "]\n"
0x18002d23b  mov     rcx, rsi; hFile
0x18002d23e  call    ?WriteToFile@@YAJPEAXPEBG@Z; WriteToFile(void *,ushort const *)
0x18002d243  mov     ebx, eax
0x18002d245  test    eax, eax
0x18002d247  js      short loc_18002D2AC
0x18002d249  mov     rdx, [rbp+hMem]; lpWideCharStr
0x18002d24d  mov     rcx, rsi; hFile
0x18002d250  call    ?WriteToFile@@YAJPEAXPEBG@Z; WriteToFile(void *,ushort const *)
0x18002d255  mov     ebx, eax
0x18002d257  test    eax, eax
0x18002d259  js      short loc_18002D2AC
0x18002d25b  lea     rdx, asc_18003C588; "\n"
0x18002d262  mov     rcx, rsi; hFile
0x18002d265  call    ?WriteToFile@@YAJPEAXPEBG@Z; WriteToFile(void *,ushort const *)
0x18002d26a  mov     ebx, eax
0x18002d26c  test    eax, eax
0x18002d26e  js      short loc_18002D2AC
0x18002d270  xorps   xmm0, xmm0
0x18002d273  lea     rdx, [rbp+ContextOut]; ContextOut
0x18002d277  xor     eax, eax
0x18002d279  lea     rcx, [rbp+Context]; ContextIn
0x18002d27d  movups  xmmword ptr [rbp+ContextOut.Inf], xmm0
0x18002d281  mov     qword ptr [rbp+ContextOut.Section], rax
0x18002d285  call    cs:__imp_SetupFindNextLine
0x18002d28b  test    eax, eax
0x18002d28d  jz      short loc_18002D293
0x18002d28f  xor     ebx, ebx
0x18002d291  jmp     short loc_18002D29A
0x18002d293  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002d298  mov     ebx, eax
0x18002d29a  movups  xmm0, xmmword ptr [rbp+ContextOut.Inf]
0x18002d29e  movsd   xmm1, qword ptr [rbp+ContextOut.Section]
0x18002d2a3  movups  xmmword ptr [rbp+Context.Inf], xmm0
0x18002d2a7  movsd   qword ptr [rbp+Context.Section], xmm1
0x18002d2ac  mov     rcx, [rbp+hMem]; hMem
0x18002d2b0  test    rcx, rcx
0x18002d2b3  jz      short loc_18002D2C3
0x18002d2b5  call    cs:__imp_LocalFree
0x18002d2bb  mov     [rbp+hMem], 0
0x18002d2c3  test    ebx, ebx
0x18002d2c5  jns     loc_18002D17F
0x18002d2cb  xor     edi, edi
0x18002d2cd  cmp     bx, 102h
0x18002d2d2  cmovnz  edi, ebx
0x18002d2d5  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002d2d9  jz      short loc_18002D2EB
0x18002d2db  mov     rcx, rsi; hObject
0x18002d2de  call    cs:__imp_CloseHandle
0x18002d2e4  jmp     short loc_18002D2EB
0x18002d2e6  mov     edi, 80070057h
0x18002d2eb  mov     eax, edi
0x18002d2ed  add     rsp, 78h
0x18002d2f1  pop     r15
0x18002d2f3  pop     r14
0x18002d2f5  pop     rdi
0x18002d2f6  pop     rsi
0x18002d2f7  pop     rbx
0x18002d2f8  pop     rbp
0x18002d2f9  retn
```
