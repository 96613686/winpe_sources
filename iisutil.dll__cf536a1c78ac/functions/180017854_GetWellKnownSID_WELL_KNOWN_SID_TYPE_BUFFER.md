# GetWellKnownSID(WELL_KNOWN_SID_TYPE,BUFFER *)

- ea: `0x180017854`
- end: `0x180017958`
- name: `?GetWellKnownSID@@YAKW4WELL_KNOWN_SID_TYPE@@PEAVBUFFER@@@Z`
- size: `260`
- prototype: `unsigned int __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType, struct BUFFER *this)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023c24`
- `0x180024740`
- `0x1800247b0`

## callees

- `0x180002da0`
- `0x180017854`
- `0x180017960`
- `0x180018ec0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001789f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001789f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800178ea`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001788b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18001788b`

## string_xrefs

- `0x18001792a`: `GetWellKnownSID`
- `0x18001790d`: `Could not create wellknown  sid\n`
- `0x180017931`: `servercommon\inetsrv\iis\iisrearc\core\common\util\useracl.cxx`
- `0x1800178d0`: `Failed to allocate appropriate space for the sid\n`

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
0x180017854  mov     [rsp+arg_0], rbx
0x180017859  mov     [rsp+arg_10], rsi
0x18001785e  push    rdi; char
0x18001785f  sub     rsp, 30h
0x180017863  mov     rdi, rdx
0x180017866  mov     esi, ecx
0x180017868  test    rdx, rdx
0x18001786b  jnz     short loc_180017875
0x18001786d  lea     eax, [rdx+57h]
0x180017870  jmp     loc_180017947
0x180017875  mov     eax, [rdx+28h]
0x180017878  xor     ebx, ebx
0x18001787a  mov     [rsp+38h+cbSid], eax
0x18001787e  mov     r8, [rdi+20h]; pSid
0x180017882  lea     r9, [rsp+38h+cbSid]; cbSid
0x180017887  xor     edx, edx; DomainSid
0x180017889  mov     ecx, esi; WellKnownSidType
0x18001788b  call    cs:__imp_CreateWellKnownSid
0x180017892  nop     dword ptr [rax+rax+00h]
0x180017897  test    eax, eax
0x180017899  jnz     loc_180017945
0x18001789f  call    cs:__imp_GetLastError
0x1800178a6  nop     dword ptr [rax+rax+00h]
0x1800178ab  mov     ebx, eax
0x1800178ad  cmp     eax, 7Ah ; 'z'
0x1800178b0  jnz     short loc_1800178EA
0x1800178b2  mov     edx, [rsp+38h+cbSid]; unsigned int
0x1800178b6  mov     rcx, rdi; this
0x1800178b9  call    ?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800178be  test    al, al
0x1800178c0  jnz     short loc_18001787E
0x1800178c2  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800178c9  mov     ebx, 8
0x1800178ce  jz      short loc_18001793D
0x1800178d0  lea     rax, aFailedToAlloca; "Failed to allocate appropriate space fo"...
0x1800178d7  mov     [rsp+38h+var_10], rax
0x1800178dc  lea     r8d, [rbx+53h]
0x1800178e0  mov     [rsp+38h+dwMessageId], 80070008h
0x1800178e8  jmp     short loc_180017923
0x1800178ea  call    cs:__imp_GetLastError
0x1800178f1  nop     dword ptr [rax+rax+00h]
0x1800178f6  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800178fd  mov     ebx, eax
0x1800178ff  jz      short loc_18001793D
0x180017901  test    eax, eax
0x180017903  jle     short loc_18001790D
0x180017905  movzx   eax, ax
0x180017908  or      eax, 80070000h
0x18001790d  lea     rcx, aCouldNotCreate; "Could not create wellknown  sid\n"
0x180017914  mov     r8d, 4Eh ; 'N'; unsigned int
0x18001791a  mov     [rsp+38h+var_10], rcx; char *
0x18001791f  mov     [rsp+38h+dwMessageId], eax; dwMessageId
0x180017923  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001792a  lea     r9, aGetwellknownsi; "GetWellKnownSID"
0x180017931  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180017938  call    PuDbgPrintError
0x18001793d  mov     rcx, rdi; this
0x180017940  call    ?FreeMemory@BUFFER@@QEAAXXZ; BUFFER::FreeMemory(void)
0x180017945  mov     eax, ebx
0x180017947  mov     rbx, [rsp+38h+arg_0]
0x18001794c  mov     rsi, [rsp+38h+arg_10]
0x180017951  add     rsp, 30h
0x180017955  pop     rdi
0x180017956  retn
```
