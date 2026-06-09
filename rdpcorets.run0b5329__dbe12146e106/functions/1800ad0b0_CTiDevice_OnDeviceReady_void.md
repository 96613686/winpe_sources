# CTiDevice::OnDeviceReady(void)

- ea: `0x1800ad0b0`
- end: `0x1800ad328`
- name: `?OnDeviceReady@CTiDevice@@MEAAJXZ`
- size: `632`
- prototype: `__int64 __fastcall(CTiDevice *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1800091a8`
- `0x18000ea1c`
- `0x18002e600`
- `0x180032f60`
- `0x180033da0`
- `0x1800ac9a4`
- `0x1800ad0b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad29f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad29f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ad1ed`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ad27a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ad1ed`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ad27a`
- `RDPBASE!PAL_System_CritSecIsLockedByCurrentThread` at `0x1800ad0dc`
- `RDPBASE!PAL_System_CritSecIsLockedByCurrentThread` at `0x1800ad0dc`

## pseudocode

```c
__int64 __fastcall CTiDevice::OnDeviceReady(CTiDevice *this)
{
  signed int PdoName; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v4; // edx
  const char *v5; // rcx
  HANDLE FileW; // rax
  unsigned int v7; // eax
  __int64 v8; // rdx
  HANDLE v9; // rax
  bool v10; // sf
  WCHAR FileName[1024]; // [rsp+40h] [rbp-818h] BYREF

  if ( *((_DWORD *)this + 4) )
    PAL_System_CritSecIsLockedByCurrentThread(*((_QWORD *)this + 1));
  PdoName = CTiDevice::GetPdoName(this);
  if ( PdoName < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v4 = 12;
      v5 = "GetPdoName failed";
LABEL_8:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v4,
        (unsigned int)WPP_fd865464e7493a5a9d2a62f99a95d94a_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v5,
        PdoName);
      return (unsigned int)PdoName;
    }
    return (unsigned int)PdoName;
  }
  PdoName = StringCbPrintfW(
              FileName,
              0x800u,
              L"\\\\.\\TermInptCDO\\%d%s",
              *((unsigned int *)this + 161),
              *((_QWORD *)this + 73));
  if ( PdoName >= 0 )
  {
    FileW = CreateFileW(FileName, 2u, 7u, 0, 3u, 0, 0);
    *((_QWORD *)this + 75) = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      *((_QWORD *)this + 75) = 0;
    }
    else if ( FileW )
    {
      v9 = CreateFileW(FileName, 2u, 7u, 0, 3u, 0x40000000u, 0);
      *((_QWORD *)this + 76) = v9;
      if ( v9 == (HANDLE)-1LL )
      {
        *((_QWORD *)this + 76) = 0;
      }
      else if ( v9 )
      {
        return (unsigned int)PdoName;
      }
      PdoName = GetLastError();
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_29;
      }
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 15;
      goto LABEL_28;
    }
    PdoName = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_29;
    }
    v7 = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 14;
LABEL_28:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_fd865464e7493a5a9d2a62f99a95d94a_Traceguids, v7, PdoName);
LABEL_29:
    v10 = PdoName < 0;
    if ( PdoName > 0 )
    {
      PdoName = (unsigned __int16)PdoName | 0x80070000;
      v10 = PdoName < 0;
    }
    if ( !v10 )
      return (unsigned int)-2147467259;
    return (unsigned int)PdoName;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v4 = 13;
    v5 = "StringCbPrintf failed";
    goto LABEL_8;
  }
  return (unsigned int)PdoName;
}

```

## disassembly

```asm
0x1800ad0b0  mov     [rsp+arg_8], rbx
0x1800ad0b5  push    rdi
0x1800ad0b6  sub     rsp, 850h
0x1800ad0bd  mov     rax, cs:__security_cookie
0x1800ad0c4  xor     rax, rsp
0x1800ad0c7  mov     [rsp+858h+var_18], rax
0x1800ad0cf  cmp     dword ptr [rcx+10h], 0
0x1800ad0d3  mov     rdi, rcx
0x1800ad0d6  jz      short loc_1800AD0E2
0x1800ad0d8  mov     rcx, [rcx+8]
0x1800ad0dc  call    cs:__imp_PAL_System_CritSecIsLockedByCurrentThread
0x1800ad0e2  mov     rcx, rdi; this
0x1800ad0e5  call    ?GetPdoName@CTiDevice@@IEAAJXZ; CTiDevice::GetPdoName(void)
0x1800ad0ea  mov     ebx, eax
0x1800ad0ec  test    eax, eax
0x1800ad0ee  jns     short loc_1800AD154
0x1800ad0f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad0f7  lea     rax, WPP_GLOBAL_Control
0x1800ad0fe  cmp     rcx, rax
0x1800ad101  jz      loc_1800AD305
0x1800ad107  test    byte ptr [rcx+1Ch], 8
0x1800ad10b  jz      loc_1800AD305
0x1800ad111  cmp     byte ptr [rcx+19h], 2
0x1800ad115  jb      loc_1800AD305
0x1800ad11b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ad120  mov     edx, 0Ch
0x1800ad125  lea     rcx, aGetpdonameFail; "GetPdoName failed"
0x1800ad12c  mov     [rsp+858h+dwFlagsAndAttributes], ebx
0x1800ad130  lea     r8, WPP_fd865464e7493a5a9d2a62f99a95d94a_Traceguids
0x1800ad137  mov     qword ptr [rsp+858h+dwCreationDisposition], rcx
0x1800ad13c  mov     r9d, eax
0x1800ad13f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad146  mov     rcx, [rcx+10h]
0x1800ad14a  call    WPP_SF_DsD
0x1800ad14f  jmp     loc_1800AD305
0x1800ad154  mov     rax, [rdi+248h]
0x1800ad15b  lea     r8, aTerminptcdoDS; "\\\\.\\TermInptCDO\\%d%s"
0x1800ad162  mov     r9d, [rdi+284h]
0x1800ad169  lea     rcx, [rsp+858h+FileName]; unsigned __int16 *
0x1800ad16e  mov     edx, 800h; unsigned __int64
0x1800ad173  mov     qword ptr [rsp+858h+dwCreationDisposition], rax
0x1800ad178  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ad17d  mov     ebx, eax
0x1800ad17f  test    eax, eax
0x1800ad181  jns     short loc_1800AD1C4
0x1800ad183  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad18a  lea     rax, WPP_GLOBAL_Control
0x1800ad191  cmp     rcx, rax
0x1800ad194  jz      loc_1800AD305
0x1800ad19a  test    byte ptr [rcx+1Ch], 8
0x1800ad19e  jz      loc_1800AD305
0x1800ad1a4  cmp     byte ptr [rcx+19h], 2
0x1800ad1a8  jb      loc_1800AD305
0x1800ad1ae  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ad1b3  mov     edx, 0Dh
0x1800ad1b8  lea     rcx, aStringcbprintf; "StringCbPrintf failed"
0x1800ad1bf  jmp     loc_1800AD12C
0x1800ad1c4  xor     r9d, r9d; lpSecurityAttributes
0x1800ad1c7  mov     [rsp+858h+hTemplateFile], 0; hTemplateFile
0x1800ad1d0  mov     [rsp+858h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800ad1d8  lea     rcx, [rsp+858h+FileName]; lpFileName
0x1800ad1dd  mov     [rsp+858h+dwCreationDisposition], 3; dwCreationDisposition
0x1800ad1e5  lea     edx, [r9+2]; dwDesiredAccess
0x1800ad1e9  lea     r8d, [r9+7]; dwShareMode
0x1800ad1ed  call    cs:__imp_CreateFileW
0x1800ad1f3  mov     [rdi+258h], rax
0x1800ad1fa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ad1fe  jnz     short loc_1800AD20D
0x1800ad200  mov     qword ptr [rdi+258h], 0
0x1800ad20b  jmp     short loc_1800AD212
0x1800ad20d  test    rax, rax
0x1800ad210  jnz     short loc_1800AD251
0x1800ad212  call    cs:__imp_GetLastError
0x1800ad218  mov     ebx, eax
0x1800ad21a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad221  lea     rax, WPP_GLOBAL_Control
0x1800ad228  cmp     rcx, rax
0x1800ad22b  jz      loc_1800AD2EE
0x1800ad231  test    byte ptr [rcx+1Ch], 8
0x1800ad235  jz      loc_1800AD2EE
0x1800ad23b  cmp     byte ptr [rcx+19h], 2
0x1800ad23f  jb      loc_1800AD2EE
0x1800ad245  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ad24a  mov     edx, 0Eh
0x1800ad24f  jmp     short loc_1800AD2D0
0x1800ad251  xor     r9d, r9d; lpSecurityAttributes
0x1800ad254  mov     [rsp+858h+hTemplateFile], 0; hTemplateFile
0x1800ad25d  mov     [rsp+858h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x1800ad265  lea     rcx, [rsp+858h+FileName]; lpFileName
0x1800ad26a  mov     [rsp+858h+dwCreationDisposition], 3; dwCreationDisposition
0x1800ad272  lea     edx, [r9+2]; dwDesiredAccess
0x1800ad276  lea     r8d, [r9+7]; dwShareMode
0x1800ad27a  call    cs:__imp_CreateFileW
0x1800ad280  mov     [rdi+260h], rax
0x1800ad287  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ad28b  jnz     short loc_1800AD29A
0x1800ad28d  mov     qword ptr [rdi+260h], 0
0x1800ad298  jmp     short loc_1800AD29F
0x1800ad29a  test    rax, rax
0x1800ad29d  jnz     short loc_1800AD305
0x1800ad29f  call    cs:__imp_GetLastError
0x1800ad2a5  mov     ebx, eax
0x1800ad2a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad2ae  lea     rax, WPP_GLOBAL_Control
0x1800ad2b5  cmp     rcx, rax
0x1800ad2b8  jz      short loc_1800AD2EE
0x1800ad2ba  test    byte ptr [rcx+1Ch], 8
0x1800ad2be  jz      short loc_1800AD2EE
0x1800ad2c0  cmp     byte ptr [rcx+19h], 2
0x1800ad2c4  jb      short loc_1800AD2EE
0x1800ad2c6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ad2cb  mov     edx, 0Fh
0x1800ad2d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ad2d7  lea     r8, WPP_fd865464e7493a5a9d2a62f99a95d94a_Traceguids
0x1800ad2de  mov     r9d, eax
0x1800ad2e1  mov     [rsp+858h+dwCreationDisposition], ebx
0x1800ad2e5  mov     rcx, [rcx+10h]
0x1800ad2e9  call    WPP_SF_Dd
0x1800ad2ee  test    ebx, ebx
0x1800ad2f0  jle     short loc_1800AD2FD
0x1800ad2f2  movzx   ebx, bx
0x1800ad2f5  or      ebx, 80070000h
0x1800ad2fb  test    ebx, ebx
0x1800ad2fd  mov     eax, 80004005h
0x1800ad302  cmovns  ebx, eax
0x1800ad305  mov     eax, ebx
0x1800ad307  mov     rcx, [rsp+858h+var_18]
0x1800ad30f  xor     rcx, rsp; StackCookie
0x1800ad312  call    __security_check_cookie
0x1800ad317  mov     rbx, [rsp+858h+arg_8]
0x1800ad31f  add     rsp, 850h
0x1800ad326  pop     rdi
0x1800ad327  retn
```
