# LIST_NLST_HANDLER::SendFinalSuccessResponse(void)

- ea: `0x180042c50`
- end: `0x180042db8`
- name: `?SendFinalSuccessResponse@LIST_NLST_HANDLER@@MEAAXXZ`
- size: `360`
- prototype: `void __fastcall(LIST_NLST_HANDLER *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18002be4c`
- `0x18003e564`
- `0x180042c50`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180042c7e`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180042c7e`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180042d99`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180042d99`
- `iisutil!PuDbgPrintError` at `0x180042d1e`
- `iisutil!PuDbgPrintError` at `0x180042d1e`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180042d30`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180042d30`

## string_xrefs

- `0x180042d83`: `Transfer complete.`
- `0x180042d10`: `inetsrv\iis\iisrearc\ftp\server\ftp_protocol\list_nlst_handler.cxx`
- `0x180042d58`: `Directory has %s bytes of disk space available.\nTransfer complete.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LIST_NLST_HANDLER::SendFinalSuccessResponse(LIST_NLST_HANDLER *this)
{
  __int64 v2; // rax
  int v3; // edx
  const char *v4; // rdx
  const char *v5; // rdx
  unsigned __int64 v6; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v7[32]; // [rsp+48h] [rbp-60h] BYREF
  const char *v8; // [rsp+68h] [rbp-40h]
  char v9[16]; // [rsp+80h] [rbp-28h] BYREF

  STRA::STRA((STRA *)v7, v9, 0x10u);
  v6 = 0;
  v2 = *((_QWORD *)this + 2);
  if ( (*(_BYTE *)(v2 + 4784) & 0x10) != 0 )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64 *))(**((_QWORD **)this + 4) + 112LL))(
           *((_QWORD *)this + 4),
           *(_QWORD *)(*((_QWORD *)this + 1) + 656LL),
           &v6);
    if ( v3 < 0 || (v3 = FormatFileSizeA(v6, (struct STRA *)v7), v3 < 0) )
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_protocol\\list_nlst_handler.cxx",
          464,
          "LIST_NLST_HANDLER::SendFinalSuccessResponse",
          v3,
          "Failed to check available bytes at %S.\n",
          *(const wchar_t **)(*((_QWORD *)this + 1) + 656LL));
      STRA::Copy((STRA *)v7, "?");
    }
    v4 = "250";
    if ( !*(_DWORD *)(*((_QWORD *)this + 2) + 2128LL) )
      v4 = "226";
    FTP_COMMAND::WriteResponseAndLog(
      *((FTP_COMMAND **)this + 1),
      v4,
      "Directory has %s bytes of disk space available.\r\nTransfer complete.",
      v8);
  }
  else
  {
    v5 = "250";
    if ( !*(_DWORD *)(v2 + 2128) )
      v5 = "226";
    FTP_COMMAND::WriteResponseAndLog(*((FTP_COMMAND **)this + 1), v5, "Transfer complete.");
  }
  STRA::~STRA((STRA *)v7);
}

```

## disassembly

```asm
0x180042c50  mov     r11, rsp
0x180042c53  push    rbx
0x180042c54  sub     rsp, 0A0h
0x180042c5b  mov     rax, cs:__security_cookie
0x180042c62  xor     rax, rsp
0x180042c65  mov     [rsp+0A8h+var_18], rax
0x180042c6d  mov     rbx, rcx
0x180042c70  mov     r8d, 10h
0x180042c76  lea     rdx, [r11-28h]
0x180042c7a  lea     rcx, [r11-60h]
0x180042c7e  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180042c84  nop
0x180042c85  mov     [rsp+0A8h+var_68], 0
0x180042c8e  mov     rax, [rbx+10h]
0x180042c92  test    byte ptr [rax+12B0h], 10h
0x180042c99  jz      loc_180042D6A
0x180042c9f  mov     rcx, [rbx+20h]
0x180042ca3  mov     rax, [rcx]
0x180042ca6  mov     rdx, [rbx+8]
0x180042caa  lea     r8, [rsp+0A8h+var_68]
0x180042caf  mov     rdx, [rdx+290h]
0x180042cb6  mov     rax, [rax+70h]
0x180042cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042cbf  mov     edx, eax
0x180042cc1  test    eax, eax
0x180042cc3  js      short loc_180042CDA
0x180042cc5  lea     rdx, [rsp+0A8h+var_60]; struct STRA *
0x180042cca  mov     rcx, [rsp+0A8h+var_68]; unsigned __int64
0x180042ccf  call    ?FormatFileSizeA@@YAJ_KPEAVSTRA@@@Z; FormatFileSizeA(unsigned __int64,STRA *)
0x180042cd4  mov     edx, eax
0x180042cd6  test    eax, eax
0x180042cd8  jns     short loc_180042D36
0x180042cda  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180042ce1  jz      short loc_180042D24
0x180042ce3  mov     rax, [rbx+8]
0x180042ce7  mov     rcx, [rax+290h]
0x180042cee  mov     [rsp+0A8h+var_78], rcx
0x180042cf3  lea     rax, aFailedToCheckA; "Failed to check available bytes at %S."...
0x180042cfa  mov     [rsp+0A8h+var_80], rax
0x180042cff  mov     [rsp+0A8h+var_88], edx
0x180042d03  lea     r9, aListNlstHandle_1; "LIST_NLST_HANDLER::SendFinalSuccessResp"...
0x180042d0a  mov     r8d, 1D0h
0x180042d10  lea     rdx, aInetsrvIisIisr_7; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x180042d17  mov     rcx, cs:g_pDebug
0x180042d1e  call    cs:__imp_PuDbgPrintError
0x180042d24  lea     rdx, asc_18005482C; "?"
0x180042d2b  lea     rcx, [rsp+0A8h+var_60]
0x180042d30  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180042d36  mov     rax, [rbx+10h]
0x180042d3a  lea     rcx, a226; "226"
0x180042d41  lea     rdx, a250; "250"
0x180042d48  cmp     dword ptr [rax+850h], 0
0x180042d4f  cmovz   rdx, rcx; char *
0x180042d53  mov     r9, [rsp+0A8h+var_40]
0x180042d58  lea     r8, aDirectoryHasSB; "Directory has %s bytes of disk space av"...
0x180042d5f  mov     rcx, [rbx+8]; this
0x180042d63  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x180042d68  jmp     short loc_180042D94
0x180042d6a  lea     rcx, a226; "226"
0x180042d71  lea     rdx, a250; "250"
0x180042d78  cmp     dword ptr [rax+850h], 0
0x180042d7f  cmovz   rdx, rcx; char *
0x180042d83  lea     r8, aTransferComple; "Transfer complete."
0x180042d8a  mov     rcx, [rbx+8]; this
0x180042d8e  call    ?WriteResponseAndLog@FTP_COMMAND@@QEAAJPEBD0ZZ; FTP_COMMAND::WriteResponseAndLog(char const *,char const *,...)
0x180042d93  nop
0x180042d94  lea     rcx, [rsp+0A8h+var_60]
0x180042d99  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180042d9f  mov     rcx, [rsp+0A8h+var_18]
0x180042da7  xor     rcx, rsp; StackCookie
0x180042daa  call    __security_check_cookie
0x180042daf  add     rsp, 0A0h
0x180042db6  pop     rbx
0x180042db7  retn
```
