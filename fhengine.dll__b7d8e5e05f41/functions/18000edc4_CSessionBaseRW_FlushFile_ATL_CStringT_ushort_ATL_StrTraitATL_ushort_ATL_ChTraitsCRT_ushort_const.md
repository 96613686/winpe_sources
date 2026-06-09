# CSessionBaseRW::FlushFile(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x18000edc4`
- end: `0x18000eed2`
- name: `?FlushFile@CSessionBaseRW@@IEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(__int64, LPCWSTR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000e078`
- `0x1800196f8`

## callees

- `0x180009258`
- `0x18000edc4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000ee0a`
- `KERNEL32!GetLastError` at `0x18000ee6d`
- `KERNEL32!GetLastError` at `0x18000ee0a`
- `KERNEL32!GetLastError` at `0x18000ee6d`
- `KERNEL32!CloseHandle` at `0x18000eeba`
- `KERNEL32!CloseHandle` at `0x18000eeba`
- `KERNEL32!CreateFileW` at `0x18000edfb`
- `KERNEL32!CreateFileW` at `0x18000edfb`
- `KERNEL32!FlushFileBuffers` at `0x18000ee63`
- `KERNEL32!FlushFileBuffers` at `0x18000ee63`

## pseudocode

```c
__int64 __fastcall CSessionBaseRW::FlushFile(__int64 a1, LPCWSTR *a2)
{
  HANDLE FileW; // rax
  void *v4; // rdi
  signed int LastError; // eax
  unsigned int v6; // ebx
  signed int v7; // eax

  FileW = CreateFileW(*a2, 0x40000000u, 3u, 0, 3u, 0, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        195,
        (int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
        (int)*a2,
        v6);
  }
  else
  {
    v6 = 0;
    if ( !FlushFileBuffers(FileW) )
    {
      v7 = GetLastError();
      v6 = v7;
      if ( v7 > 0 )
        v6 = (unsigned __int16)v7 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          196,
          (int)&WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids,
          (int)*a2,
          v6);
    }
    CloseHandle(v4);
  }
  return v6;
}

```

## disassembly

```asm
0x18000edc4  mov     rax, rsp
0x18000edc7  mov     [rax+8], rbx
0x18000edcb  mov     [rax+10h], rsi
0x18000edcf  push    rdi
0x18000edd0  sub     rsp, 40h
0x18000edd4  mov     rsi, rdx
0x18000edd7  mov     qword ptr [rax-18h], 0
0x18000eddf  mov     r8d, 3; dwShareMode
0x18000ede5  mov     dword ptr [rax-20h], 0
0x18000edec  xor     r9d, r9d; lpSecurityAttributes
0x18000edef  mov     [rax-28h], r8d
0x18000edf3  mov     edx, 40000000h; dwDesiredAccess
0x18000edf8  mov     rcx, [rsi]; lpFileName
0x18000edfb  call    cs:__imp_CreateFileW
0x18000ee01  mov     rdi, rax
0x18000ee04  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ee08  jnz     short loc_18000EE5E
0x18000ee0a  call    cs:__imp_GetLastError
0x18000ee10  mov     ebx, eax
0x18000ee12  test    eax, eax
0x18000ee14  jle     short loc_18000EE1F
0x18000ee16  movzx   ebx, ax
0x18000ee19  or      ebx, 80070000h
0x18000ee1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee26  lea     rax, WPP_GLOBAL_Control
0x18000ee2d  cmp     rcx, rax
0x18000ee30  jz      loc_18000EEC0
0x18000ee36  test    byte ptr [rcx+1Ch], 1
0x18000ee3a  jz      loc_18000EEC0
0x18000ee40  mov     r9, [rsi]
0x18000ee43  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000ee4a  mov     rcx, [rcx+10h]
0x18000ee4e  mov     edx, 0C3h
0x18000ee53  mov     [rsp+48h+var_28], ebx
0x18000ee57  call    WPP_SF_Sd
0x18000ee5c  jmp     short loc_18000EEC0
0x18000ee5e  mov     rcx, rdi; hFile
0x18000ee61  xor     ebx, ebx
0x18000ee63  call    cs:__imp_FlushFileBuffers
0x18000ee69  test    eax, eax
0x18000ee6b  jnz     short loc_18000EEB7
0x18000ee6d  call    cs:__imp_GetLastError
0x18000ee73  mov     ebx, eax
0x18000ee75  test    eax, eax
0x18000ee77  jle     short loc_18000EE82
0x18000ee79  movzx   ebx, ax
0x18000ee7c  or      ebx, 80070000h
0x18000ee82  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee89  lea     rax, WPP_GLOBAL_Control
0x18000ee90  cmp     rcx, rax
0x18000ee93  jz      short loc_18000EEB7
0x18000ee95  test    byte ptr [rcx+1Ch], 1
0x18000ee99  jz      short loc_18000EEB7
0x18000ee9b  mov     r9, [rsi]
0x18000ee9e  lea     r8, WPP_83c6165ab0fb3bdef44b8a5849b9f405_Traceguids
0x18000eea5  mov     rcx, [rcx+10h]
0x18000eea9  mov     edx, 0C4h
0x18000eeae  mov     [rsp+48h+var_28], ebx
0x18000eeb2  call    WPP_SF_Sd
0x18000eeb7  mov     rcx, rdi; hObject
0x18000eeba  call    cs:__imp_CloseHandle
0x18000eec0  mov     rsi, [rsp+48h+arg_8]
0x18000eec5  mov     eax, ebx
0x18000eec7  mov     rbx, [rsp+48h+arg_0]
0x18000eecc  add     rsp, 40h
0x18000eed0  pop     rdi
0x18000eed1  retn
```
