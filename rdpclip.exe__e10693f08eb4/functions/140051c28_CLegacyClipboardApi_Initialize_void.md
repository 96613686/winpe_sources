# CLegacyClipboardApi::Initialize(void)

- ea: `0x140051c28`
- end: `0x140051d26`
- name: `?Initialize@CLegacyClipboardApi@@QEAAJXZ`
- size: `254`
- prototype: `__int64 __fastcall(CLegacyClipboardApi *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140051830`

## callees

- `0x140004b1c`
- `0x140005704`
- `0x140051c28`
- `0x1400577e8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051ca3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140051ca3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051cb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051c4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140051cb1`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140051c3c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140051c3c`

## string_xrefs

- `0x140051c35`: `user32.dll`
- `0x140051c97`: `GetOpenClipboardWindow`

## pseudocode

```c
__int64 __fastcall CLegacyClipboardApi::Initialize(CLegacyClipboardApi *this)
{
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  unsigned int v4; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v6; // rdx
  FARPROC ProcAddress; // rax
  signed int v8; // eax

  LibraryW = LoadLibraryW(L"user32.dll");
  *((_QWORD *)this + 1) = LibraryW;
  if ( !LibraryW )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_16;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 274;
    goto LABEL_15;
  }
  v4 = 0;
  ProcAddress = GetProcAddress(LibraryW, "GetOpenClipboardWindow");
  *(_QWORD *)this = ProcAddress;
  if ( ProcAddress )
    return v4;
  v8 = GetLastError();
  v4 = v8;
  if ( v8 > 0 )
    v4 = (unsigned __int16)v8 | 0x80070000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v6 = 275;
LABEL_15:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
      CurrentThreadActivityIdPrefix,
      v4);
  }
LABEL_16:
  if ( (v4 & 0x80000000) != 0 )
    CLegacyClipboardApi::Terminate(this);
  return v4;
}

```

## disassembly

```asm
0x140051c28  mov     [rsp+arg_0], rbx
0x140051c2d  push    rdi
0x140051c2e  sub     rsp, 30h
0x140051c32  mov     rdi, rcx
0x140051c35  lea     rcx, aUser32Dll_0; "user32.dll"
0x140051c3c  call    cs:__imp_LoadLibraryW
0x140051c42  mov     [rdi+8], rax
0x140051c46  test    rax, rax
0x140051c49  jnz     short loc_140051C97
0x140051c4b  call    cs:__imp_GetLastError
0x140051c51  mov     ebx, eax
0x140051c53  test    eax, eax
0x140051c55  jle     short loc_140051C60
0x140051c57  movzx   ebx, ax
0x140051c5a  or      ebx, 80070000h
0x140051c60  mov     rax, cs:WPP_GLOBAL_Control
0x140051c67  lea     rcx, WPP_GLOBAL_Control
0x140051c6e  cmp     rax, rcx
0x140051c71  jz      loc_140051D0D
0x140051c77  test    byte ptr [rax+1Ch], 1
0x140051c7b  jz      loc_140051D0D
0x140051c81  cmp     byte ptr [rax+19h], 2
0x140051c85  jb      loc_140051D0D
0x140051c8b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051c90  mov     edx, 112h
0x140051c95  jmp     short loc_140051CEF
0x140051c97  lea     rdx, aGetopenclipboa_0; "GetOpenClipboardWindow"
0x140051c9e  mov     rcx, rax; hModule
0x140051ca1  xor     ebx, ebx
0x140051ca3  call    cs:__imp_GetProcAddress
0x140051ca9  mov     [rdi], rax
0x140051cac  test    rax, rax
0x140051caf  jnz     short loc_140051D19
0x140051cb1  call    cs:__imp_GetLastError
0x140051cb7  mov     ebx, eax
0x140051cb9  test    eax, eax
0x140051cbb  jle     short loc_140051CC6
0x140051cbd  movzx   ebx, ax
0x140051cc0  or      ebx, 80070000h
0x140051cc6  mov     rax, cs:WPP_GLOBAL_Control
0x140051ccd  lea     rcx, WPP_GLOBAL_Control
0x140051cd4  cmp     rax, rcx
0x140051cd7  jz      short loc_140051D0D
0x140051cd9  test    byte ptr [rax+1Ch], 1
0x140051cdd  jz      short loc_140051D0D
0x140051cdf  cmp     byte ptr [rax+19h], 3
0x140051ce3  jb      short loc_140051D0D
0x140051ce5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051cea  mov     edx, 113h
0x140051cef  mov     rcx, cs:WPP_GLOBAL_Control
0x140051cf6  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x140051cfd  mov     r9d, eax
0x140051d00  mov     [rsp+38h+var_18], ebx
0x140051d04  mov     rcx, [rcx+10h]
0x140051d08  call    WPP_SF_Dd
0x140051d0d  test    ebx, ebx
0x140051d0f  jns     short loc_140051D19
0x140051d11  mov     rcx, rdi; this
0x140051d14  call    ?Terminate@CLegacyClipboardApi@@QEAAJXZ; CLegacyClipboardApi::Terminate(void)
0x140051d19  mov     eax, ebx
0x140051d1b  mov     rbx, [rsp+38h+arg_0]
0x140051d20  add     rsp, 30h
0x140051d24  pop     rdi
0x140051d25  retn
```
