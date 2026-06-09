# CLegacyClipboardApi::Initialize(void)

- ea: `0x1800d0b08`
- end: `0x1800d0c06`
- name: `?Initialize@CLegacyClipboardApi@@QEAAJXZ`
- size: `254`
- prototype: `__int64 __fastcall(CLegacyClipboardApi *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800d0710`

## callees

- `0x1800091a8`
- `0x180032f60`
- `0x1800d0b08`
- `0x1800d6510`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d0b83`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800d0b83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d0b2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d0b91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d0b2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d0b91`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800d0b1c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800d0b1c`

## string_xrefs

- `0x1800d0b15`: `user32.dll`
- `0x1800d0b77`: `GetOpenClipboardWindow`

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
0x1800d0b08  mov     [rsp+arg_0], rbx
0x1800d0b0d  push    rdi
0x1800d0b0e  sub     rsp, 30h
0x1800d0b12  mov     rdi, rcx
0x1800d0b15  lea     rcx, aUser32Dll_0; "user32.dll"
0x1800d0b1c  call    cs:__imp_LoadLibraryW
0x1800d0b22  mov     [rdi+8], rax
0x1800d0b26  test    rax, rax
0x1800d0b29  jnz     short loc_1800D0B77
0x1800d0b2b  call    cs:__imp_GetLastError
0x1800d0b31  mov     ebx, eax
0x1800d0b33  test    eax, eax
0x1800d0b35  jle     short loc_1800D0B40
0x1800d0b37  movzx   ebx, ax
0x1800d0b3a  or      ebx, 80070000h
0x1800d0b40  mov     rax, cs:WPP_GLOBAL_Control
0x1800d0b47  lea     rcx, WPP_GLOBAL_Control
0x1800d0b4e  cmp     rax, rcx
0x1800d0b51  jz      loc_1800D0BED
0x1800d0b57  test    byte ptr [rax+1Ch], 1
0x1800d0b5b  jz      loc_1800D0BED
0x1800d0b61  cmp     byte ptr [rax+19h], 2
0x1800d0b65  jb      loc_1800D0BED
0x1800d0b6b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d0b70  mov     edx, 112h
0x1800d0b75  jmp     short loc_1800D0BCF
0x1800d0b77  lea     rdx, aGetopenclipboa_0; "GetOpenClipboardWindow"
0x1800d0b7e  mov     rcx, rax; hModule
0x1800d0b81  xor     ebx, ebx
0x1800d0b83  call    cs:__imp_GetProcAddress
0x1800d0b89  mov     [rdi], rax
0x1800d0b8c  test    rax, rax
0x1800d0b8f  jnz     short loc_1800D0BF9
0x1800d0b91  call    cs:__imp_GetLastError
0x1800d0b97  mov     ebx, eax
0x1800d0b99  test    eax, eax
0x1800d0b9b  jle     short loc_1800D0BA6
0x1800d0b9d  movzx   ebx, ax
0x1800d0ba0  or      ebx, 80070000h
0x1800d0ba6  mov     rax, cs:WPP_GLOBAL_Control
0x1800d0bad  lea     rcx, WPP_GLOBAL_Control
0x1800d0bb4  cmp     rax, rcx
0x1800d0bb7  jz      short loc_1800D0BED
0x1800d0bb9  test    byte ptr [rax+1Ch], 1
0x1800d0bbd  jz      short loc_1800D0BED
0x1800d0bbf  cmp     byte ptr [rax+19h], 3
0x1800d0bc3  jb      short loc_1800D0BED
0x1800d0bc5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d0bca  mov     edx, 113h
0x1800d0bcf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0bd6  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x1800d0bdd  mov     r9d, eax
0x1800d0be0  mov     [rsp+38h+var_18], ebx
0x1800d0be4  mov     rcx, [rcx+10h]
0x1800d0be8  call    WPP_SF_Dd
0x1800d0bed  test    ebx, ebx
0x1800d0bef  jns     short loc_1800D0BF9
0x1800d0bf1  mov     rcx, rdi; this
0x1800d0bf4  call    ?Terminate@CLegacyClipboardApi@@QEAAJXZ; CLegacyClipboardApi::Terminate(void)
0x1800d0bf9  mov     eax, ebx
0x1800d0bfb  mov     rbx, [rsp+38h+arg_0]
0x1800d0c00  add     rsp, 30h
0x1800d0c04  pop     rdi
0x1800d0c05  retn
```
