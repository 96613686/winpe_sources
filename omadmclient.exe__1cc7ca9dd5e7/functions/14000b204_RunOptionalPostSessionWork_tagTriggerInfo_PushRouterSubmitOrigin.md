# RunOptionalPostSessionWork(tagTriggerInfo *,PushRouterSubmitOrigin)

- ea: `0x14000b204`
- end: `0x14000b31d`
- name: `?RunOptionalPostSessionWork@@YAJPEAUtagTriggerInfo@@W4PushRouterSubmitOrigin@@@Z`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x14000d860`

## callees

- `0x14000b204`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b2c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b2c1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000b2fe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000b2fe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000b2a3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000b2a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b2e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b2e0`

## string_xrefs

- `0x14000b296`: `OmaDmAgent.dll`

## pseudocode

```c
__int64 __fastcall RunOptionalPostSessionWork(__int64 a1, unsigned int a2)
{
  _WORD *v4; // rax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  HMODULE Library; // rax
  HMODULE v8; // rsi
  FARPROC ProcAddress; // rax
  signed int LastError; // eax

  if ( *(_DWORD *)(a1 + 4) > 0xFFFFu )
    return 2147942487LL;
  if ( *(_BYTE *)(a1 + 8) > 4u )
    return 2147942487LL;
  if ( *(_BYTE *)(a1 + 9) > 1u )
    return 2147942487LL;
  v4 = *(_WORD **)(a1 + 16);
  if ( !v4 || *(_DWORD *)(a1 + 24) > 2u )
    return 2147942487LL;
  v5 = 256;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v5;
  }
  while ( v5 );
  v6 = v5 == 0 ? 0x80070057 : 0;
  if ( !v5 || ((256 - v5) & ((unsigned __int128)-(__int128)(unsigned __int64)v5 >> 64)) == 0 )
    return 2147942487LL;
  Library = LoadLibraryExW(L"OmaDmAgent.dll", 0, 0x800u);
  v8 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "OmaDmRunPostSessionWork");
    if ( ProcAddress )
    {
      v6 = ((__int64 (__fastcall *)(__int64, _QWORD))ProcAddress)(a1, a2);
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    FreeLibrary(v8);
  }
  return v6;
}

```

## disassembly

```asm
0x14000b204  push    rbx
0x14000b206  push    rbp
0x14000b207  push    rsi
0x14000b208  push    rdi
0x14000b209  push    r14
0x14000b20b  sub     rsp, 20h
0x14000b20f  cmp     dword ptr [rcx+4], 0FFFFh
0x14000b216  mov     ebp, edx
0x14000b218  mov     rdi, rcx
0x14000b21b  mov     r9d, 80070057h
0x14000b221  ja      loc_14000B30E
0x14000b227  cmp     byte ptr [rcx+8], 4
0x14000b22b  ja      loc_14000B30E
0x14000b231  cmp     byte ptr [rcx+9], 1
0x14000b235  ja      loc_14000B30E
0x14000b23b  mov     rax, [rcx+10h]
0x14000b23f  xor     r14d, r14d
0x14000b242  test    rax, rax
0x14000b245  jz      loc_14000B30E
0x14000b24b  cmp     dword ptr [rcx+18h], 2
0x14000b24f  ja      loc_14000B30E
0x14000b255  mov     r8d, 100h
0x14000b25b  mov     ecx, r8d
0x14000b25e  cmp     [rax], r14w
0x14000b262  jz      short loc_14000B26E
0x14000b264  add     rax, 2
0x14000b268  sub     rcx, 1
0x14000b26c  jnz     short loc_14000B25E
0x14000b26e  mov     rax, rcx
0x14000b271  neg     rax
0x14000b274  mov     rax, rcx
0x14000b277  sbb     ebx, ebx
0x14000b279  sub     r8, rcx
0x14000b27c  not     ebx
0x14000b27e  and     ebx, r9d
0x14000b281  neg     rax
0x14000b284  sbb     rdx, rdx
0x14000b287  and     rdx, r8
0x14000b28a  test    rcx, rcx
0x14000b28d  jz      short loc_14000B30E
0x14000b28f  test    rdx, rdx
0x14000b292  jz      short loc_14000B30E
0x14000b294  xor     edx, edx; hFile
0x14000b296  lea     rcx, LibFileName; "OmaDmAgent.dll"
0x14000b29d  mov     r8d, 800h; dwFlags
0x14000b2a3  call    cs:__imp_LoadLibraryExW
0x14000b2aa  nop     dword ptr [rax+rax+00h]
0x14000b2af  mov     rsi, rax
0x14000b2b2  test    rax, rax
0x14000b2b5  jz      short loc_14000B30A
0x14000b2b7  lea     rdx, aOmadmrunpostse; "OmaDmRunPostSessionWork"
0x14000b2be  mov     rcx, rax; hModule
0x14000b2c1  call    cs:__imp_GetProcAddress
0x14000b2c8  nop     dword ptr [rax+rax+00h]
0x14000b2cd  test    rax, rax
0x14000b2d0  jz      short loc_14000B2E0
0x14000b2d2  mov     edx, ebp
0x14000b2d4  mov     rcx, rdi
0x14000b2d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b2dc  mov     ebx, eax
0x14000b2de  jmp     short loc_14000B2FB
0x14000b2e0  call    cs:__imp_GetLastError
0x14000b2e7  nop     dword ptr [rax+rax+00h]
0x14000b2ec  mov     ebx, eax
0x14000b2ee  test    eax, eax
0x14000b2f0  jle     short loc_14000B2FB
0x14000b2f2  movzx   ebx, ax
0x14000b2f5  or      ebx, 80070000h
0x14000b2fb  mov     rcx, rsi; hLibModule
0x14000b2fe  call    cs:__imp_FreeLibrary
0x14000b305  nop     dword ptr [rax+rax+00h]
0x14000b30a  mov     eax, ebx
0x14000b30c  jmp     short loc_14000B311
0x14000b30e  mov     eax, r9d
0x14000b311  add     rsp, 20h
0x14000b315  pop     r14
0x14000b317  pop     rdi
0x14000b318  pop     rsi
0x14000b319  pop     rbp
0x14000b31a  pop     rbx
0x14000b31b  retn
```
