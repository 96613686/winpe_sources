# CResourceManager::SaveInFile(wchar_t const *,ulong,int)

- ea: `0x1800751b0`
- end: `0x1800752c0`
- name: `?SaveInFile@CResourceManager@@UEAAJPEB_WKH@Z`
- size: `272`
- prototype: `__int64 __fastcall(CResourceManager *__hidden this, LPCWSTR lpFileName, unsigned int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x18000e558`
- `0x18002c61c`
- `0x18002c6c8`
- `0x180074f78`
- `0x1800751b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800751f5`
- `KERNEL32!GetLastError` at `0x18007523f`
- `KERNEL32!GetLastError` at `0x1800751f5`
- `KERNEL32!GetLastError` at `0x18007523f`
- `KERNEL32!CloseHandle` at `0x18007526c`
- `KERNEL32!CloseHandle` at `0x18007526c`
- `KERNEL32!CreateFileW` at `0x1800751e6`
- `KERNEL32!CreateFileW` at `0x1800751e6`
- `KERNEL32!FlushFileBuffers` at `0x180075235`
- `KERNEL32!FlushFileBuffers` at `0x180075235`

## pseudocode

```c
__int64 __fastcall CResourceManager::SaveInFile(CResourceManager *this, LPCWSTR lpFileName)
{
  HANDLE FileW; // rax
  void *v4; // rdi
  DWORD LastError; // eax
  unsigned int v6; // ebx
  signed int v7; // eax
  bool v8; // sf

  FileW = CreateFileW(lpFileName, 0x40000000u, 0, 0, 4u, 0x80000080, 0);
  v4 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError )
      LogMsgNTStatus(LastError, (wchar_t *)L"xactrm", 0x53Cu);
    v6 = -1072824319;
  }
  else
  {
    v6 = (unsigned int)CResourceManager::Save(this, FileW) == 0 ? 0xC00E0001 : 0;
    if ( !FlushFileBuffers(v4) )
    {
      v7 = GetLastError();
      v8 = v7 < 0;
      if ( v7 > 0 )
      {
        v7 = (unsigned __int16)v7 | 0x80070000;
        v8 = v7 < 0;
      }
      if ( v8 )
        LogMsgHR(v7, (wchar_t *)L"xactrm", 0x5C8u);
    }
    CloseHandle(v4);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 4) != 0 )
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 42), *((_DWORD *)this + 32));
  return v6;
}

```

## disassembly

```asm
0x1800751b0  push    rbx
0x1800751b2  push    rbp
0x1800751b3  push    rsi
0x1800751b4  push    rdi
0x1800751b5  sub     rsp, 48h
0x1800751b9  mov     rbp, rdx
0x1800751bc  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1800751c5  mov     rsi, rcx
0x1800751c8  mov     [rsp+68h+dwFlagsAndAttributes], 80000080h; dwFlagsAndAttributes
0x1800751d0  mov     rcx, rbp; lpFileName
0x1800751d3  mov     [rsp+68h+dwCreationDisposition], 4; dwCreationDisposition
0x1800751db  xor     r9d, r9d; lpSecurityAttributes
0x1800751de  xor     r8d, r8d; dwShareMode
0x1800751e1  mov     edx, 40000000h; dwDesiredAccess
0x1800751e6  call    cs:__imp_CreateFileW
0x1800751ec  mov     rdi, rax
0x1800751ef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800751f3  jnz     short loc_18007521A
0x1800751f5  call    cs:__imp_GetLastError
0x1800751fb  test    eax, eax
0x1800751fd  jz      short loc_180075213
0x1800751ff  mov     r8d, 53Ch; unsigned __int16
0x180075205  lea     rdx, aXactrm; "xactrm"
0x18007520c  mov     ecx, eax; int
0x18007520e  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180075213  mov     ebx, 0C00E0001h
0x180075218  jmp     short loc_180075272
0x18007521a  mov     rdx, rdi; void *
0x18007521d  mov     rcx, rsi; this
0x180075220  call    ?Save@CResourceManager@@QEAAHPEAX@Z; CResourceManager::Save(void *)
0x180075225  neg     eax
0x180075227  mov     ebx, 0C00E0001h
0x18007522c  sbb     ecx, ecx
0x18007522e  not     ecx
0x180075230  and     ebx, ecx
0x180075232  mov     rcx, rdi; hFile
0x180075235  call    cs:__imp_FlushFileBuffers
0x18007523b  test    eax, eax
0x18007523d  jnz     short loc_180075269
0x18007523f  call    cs:__imp_GetLastError
0x180075245  test    eax, eax
0x180075247  jle     short loc_180075253
0x180075249  movzx   eax, ax
0x18007524c  or      eax, 80070000h
0x180075251  test    eax, eax
0x180075253  jns     short loc_180075269
0x180075255  mov     r8d, 5C8h; unsigned __int16
0x18007525b  lea     rdx, aXactrm; "xactrm"
0x180075262  mov     ecx, eax; int
0x180075264  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180075269  mov     rcx, rdi; hObject
0x18007526c  call    cs:__imp_CloseHandle
0x180075272  mov     rcx, cs:WPP_GLOBAL_Control
0x180075279  lea     rax, WPP_GLOBAL_Control
0x180075280  cmp     rcx, rax
0x180075283  jz      short loc_1800752B5
0x180075285  test    byte ptr [rcx+15Ch], 4
0x18007528c  jz      short loc_1800752B5
0x18007528e  mov     r8d, [rsi+80h]
0x180075295  mov     edx, 2Bh ; '+'
0x18007529a  mov     rcx, [rcx+150h]; LoggerHandle
0x1800752a1  mov     r9, rbp
0x1800752a4  mov     [rsp+68h+dwCreationDisposition], r8d; char
0x1800752a9  lea     r8, WPP_09ce049e916c32aad14de9fd9a07b5ac_Traceguids
0x1800752b0  call    WPP_SF_Sd
0x1800752b5  mov     eax, ebx
0x1800752b7  add     rsp, 48h
0x1800752bb  pop     rdi
0x1800752bc  pop     rsi
0x1800752bd  pop     rbp
0x1800752be  pop     rbx
0x1800752bf  retn
```
