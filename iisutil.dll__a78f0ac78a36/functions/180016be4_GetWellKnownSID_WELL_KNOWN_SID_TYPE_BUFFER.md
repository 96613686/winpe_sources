# GetWellKnownSID(WELL_KNOWN_SID_TYPE,BUFFER *)

- ea: `0x180016be4`
- end: `0x180016cd5`
- name: `?GetWellKnownSID@@YAKW4WELL_KNOWN_SID_TYPE@@PEAVBUFFER@@@Z`
- size: `241`
- prototype: `unsigned int __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType, struct BUFFER *this)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800224a8`
- `0x180022eb0`
- `0x180022f20`

## callees

- `0x180002470`
- `0x180016be4`
- `0x180016ce0`
- `0x1800180c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c6e`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180016c1b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180016c1b`

## string_xrefs

- `0x180016ca8`: `GetWellKnownSID`
- `0x180016c8b`: `Could not create wellknown  sid\n`
- `0x180016caf`: `servercommon\inetsrv\iis\iisrearc\core\common\util\useracl.cxx`
- `0x180016c54`: `Failed to allocate appropriate space for the sid\n`

## pseudocode

```c
__int64 __fastcall GetWellKnownSID(WELL_KNOWN_SID_TYPE WellKnownSidType, struct BUFFER *this)
{
  DWORD LastError; // ebx
  int dwMessageId; // eax
  char v7; // [rsp+30h] [rbp-8h]
  DWORD cbSid; // [rsp+48h] [rbp+10h] BYREF

  if ( !this )
    return 87;
  LastError = 0;
  cbSid = *((_DWORD *)this + 10);
  while ( !CreateWellKnownSid(WellKnownSidType, 0, *((PSID *)this + 4), &cbSid) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      dwMessageId = GetLastError();
      LastError = dwMessageId;
      if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
      {
        if ( dwMessageId > 0 )
          dwMessageId = (unsigned __int16)dwMessageId | 0x80070000;
        PuDbgPrintError(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\useracl.cxx",
          0x4Eu,
          "GetWellKnownSID",
          dwMessageId,
          "Could not create wellknown  sid\n",
          v7);
      }
      goto LABEL_13;
    }
    if ( !BUFFER::Resize(this, cbSid) )
    {
      LastError = 8;
      if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
        PuDbgPrintError(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\useracl.cxx",
          0x5Bu,
          "GetWellKnownSID",
          0x80070008,
          "Failed to allocate appropriate space for the sid\n",
          v7);
LABEL_13:
      BUFFER::FreeMemory(this);
      return LastError;
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x180016be4  mov     [rsp+arg_0], rbx
0x180016be9  mov     [rsp+arg_10], rsi
0x180016bee  push    rdi; char
0x180016bef  sub     rsp, 30h
0x180016bf3  mov     rdi, rdx
0x180016bf6  mov     esi, ecx
0x180016bf8  test    rdx, rdx
0x180016bfb  jnz     short loc_180016C05
0x180016bfd  lea     eax, [rdx+57h]
0x180016c00  jmp     loc_180016CC5
0x180016c05  mov     eax, [rdx+28h]
0x180016c08  xor     ebx, ebx
0x180016c0a  mov     [rsp+38h+cbSid], eax
0x180016c0e  mov     r8, [rdi+20h]; pSid
0x180016c12  lea     r9, [rsp+38h+cbSid]; cbSid
0x180016c17  xor     edx, edx; DomainSid
0x180016c19  mov     ecx, esi; WellKnownSidType
0x180016c1b  call    cs:__imp_CreateWellKnownSid
0x180016c21  test    eax, eax
0x180016c23  jnz     loc_180016CC3
0x180016c29  call    cs:__imp_GetLastError
0x180016c2f  mov     ebx, eax
0x180016c31  cmp     eax, 7Ah ; 'z'
0x180016c34  jnz     short loc_180016C6E
0x180016c36  mov     edx, [rsp+38h+cbSid]; unsigned int
0x180016c3a  mov     rcx, rdi; this
0x180016c3d  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180016c42  test    al, al
0x180016c44  jnz     short loc_180016C0E
0x180016c46  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180016c4d  mov     ebx, 8
0x180016c52  jz      short loc_180016CBB
0x180016c54  lea     rax, aFailedToAlloca; "Failed to allocate appropriate space fo"...
0x180016c5b  mov     [rsp+38h+var_10], rax
0x180016c60  lea     r8d, [rbx+53h]
0x180016c64  mov     [rsp+38h+dwMessageId], 80070008h
0x180016c6c  jmp     short loc_180016CA1
0x180016c6e  call    cs:__imp_GetLastError
0x180016c74  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180016c7b  mov     ebx, eax
0x180016c7d  jz      short loc_180016CBB
0x180016c7f  test    eax, eax
0x180016c81  jle     short loc_180016C8B
0x180016c83  movzx   eax, ax
0x180016c86  or      eax, 80070000h
0x180016c8b  lea     rcx, aCouldNotCreate; "Could not create wellknown  sid\n"
0x180016c92  mov     r8d, 4Eh ; 'N'; unsigned int
0x180016c98  mov     [rsp+38h+var_10], rcx; char *
0x180016c9d  mov     [rsp+38h+dwMessageId], eax; dwMessageId
0x180016ca1  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180016ca8  lea     r9, aGetwellknownsi; "GetWellKnownSID"
0x180016caf  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180016cb6  call    PuDbgPrintError
0x180016cbb  mov     rcx, rdi; this
0x180016cbe  call    ?FreeMemory@BUFFER@@QEAAXXZ; BUFFER::FreeMemory(void)
0x180016cc3  mov     eax, ebx
0x180016cc5  mov     rbx, [rsp+38h+arg_0]
0x180016cca  mov     rsi, [rsp+38h+arg_10]
0x180016ccf  add     rsp, 30h
0x180016cd3  pop     rdi
0x180016cd4  retn
```
