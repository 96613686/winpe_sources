# common_end_thread

- ea: `0x180344a78`
- end: `0x180344ad9`
- name: `common_end_thread`
- size: `97`
- prototype: `void __fastcall __noreturn(DWORD dwExitCode)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180344c20`

## callees

- `0x180344a78`
- `0x180354ca8`
- `0x180359838`

## import_xrefs

- `KERNEL32!FreeLibraryAndExitThread` at `0x180344ac9`
- `KERNEL32!FreeLibraryAndExitThread` at `0x180344ac9`
- `KERNEL32!ExitThread` at `0x180344ad2`
- `KERNEL32!ExitThread` at `0x180344ad2`
- `KERNEL32!CloseHandle` at `0x180344ab3`
- `KERNEL32!CloseHandle` at `0x180344ab3`

## pseudocode

```c
void __fastcall __noreturn common_end_thread(DWORD dwExitCode)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  char *v4; // rcx
  HMODULE v5; // rcx

  v2 = _acrt_getptd_noexit();
  if ( v2 )
  {
    v3 = *(_QWORD *)(v2 + 960);
    if ( v3 )
    {
      if ( *(_BYTE *)(v3 + 32) )
        _acrt_RoUninitialize();
      v4 = *(char **)(v3 + 16);
      if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v4);
      v5 = *(HMODULE *)(v3 + 24);
      if ( (unsigned __int64)v5 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        FreeLibraryAndExitThread(v5, dwExitCode);
    }
  }
  ExitThread(dwExitCode);
}

```

## disassembly

```asm
0x180344a78  mov     [rsp+arg_0], rbx
0x180344a7d  push    rdi
0x180344a7e  sub     rsp, 20h
0x180344a82  mov     edi, ecx
0x180344a84  call    __acrt_getptd_noexit
0x180344a89  test    rax, rax
0x180344a8c  jz      short loc_180344AD0
0x180344a8e  mov     rbx, [rax+3C0h]
0x180344a95  test    rbx, rbx
0x180344a98  jz      short loc_180344AD0
0x180344a9a  cmp     byte ptr [rbx+20h], 0
0x180344a9e  jz      short loc_180344AA5
0x180344aa0  call    __acrt_RoUninitialize
0x180344aa5  mov     rcx, [rbx+10h]; hObject
0x180344aa9  lea     rax, [rcx-1]
0x180344aad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180344ab1  ja      short loc_180344AB9
0x180344ab3  call    cs:__imp_CloseHandle
0x180344ab9  mov     rcx, [rbx+18h]; hLibModule
0x180344abd  lea     rax, [rcx-1]
0x180344ac1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180344ac5  ja      short loc_180344AD0
0x180344ac7  mov     edx, edi; dwExitCode
0x180344ac9  call    cs:__imp_FreeLibraryAndExitThread
0x180344ad0  mov     ecx, edi; dwExitCode
0x180344ad2  call    cs:__imp_ExitThread
```
