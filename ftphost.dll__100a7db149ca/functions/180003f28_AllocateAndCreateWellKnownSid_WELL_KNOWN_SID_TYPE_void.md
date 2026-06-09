# AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)

- ea: `0x180003f28`
- end: `0x1800040c0`
- name: `?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z`
- size: `408`
- prototype: `__int64 __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800040c8`

## callees

- `0x180003f28`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180003fb0`
- `KERNEL32!GetLastError` at `0x180004041`
- `KERNEL32!GetLastError` at `0x180003fb0`
- `KERNEL32!GetLastError` at `0x180004041`
- `KERNEL32!GlobalAlloc` at `0x180003fee`
- `KERNEL32!GlobalAlloc` at `0x180003fee`
- `KERNEL32!GlobalFree` at `0x1800040a7`
- `KERNEL32!GlobalFree` at `0x1800040a7`
- `ADVAPI32!CreateWellKnownSid` at `0x180003f5d`
- `ADVAPI32!CreateWellKnownSid` at `0x180004033`
- `ADVAPI32!CreateWellKnownSid` at `0x180003f5d`
- `ADVAPI32!CreateWellKnownSid` at `0x180004033`
- `iisutil!PuDbgPrintError` at `0x180003fa0`
- `iisutil!PuDbgPrintError` at `0x18000408d`
- `iisutil!PuDbgPrintError` at `0x180003fa0`
- `iisutil!PuDbgPrintError` at `0x18000408d`

## string_xrefs

- `0x180003f73`: `Creating a sid worked with no memory allocated for it. ( This is not good )\n`
- `0x180003f92`: `AllocateAndCreateWellKnownSid`
- `0x18000406f`: `AllocateAndCreateWellKnownSid`
- `0x180003fd6`: `Getting the SID length failed, can't create the sid (Type = %d)\n`
- `0x180004008`: `Failed to allocate space for SID\n`
- `0x18000405e`: `Creating SID failed ( SidType = %d )\n`

## pseudocode

```c
__int64 __fastcall AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE WellKnownSidType, void **a2)
{
  void *v4; // rdi
  unsigned int v5; // ebx
  signed int LastError; // eax
  const char *v8; // rcx
  __int64 v9; // r8
  HGLOBAL v10; // rax
  DWORD cbSid; // [rsp+78h] [rbp+10h] BYREF

  cbSid = 0;
  if ( a2 && !*a2 )
  {
    v4 = 0;
    if ( CreateWellKnownSid(WellKnownSidType, 0, 0, &cbSid) )
    {
      v5 = 50;
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\extensibility\\ftphost\\secfcns.cxx",
          71,
          "AllocateAndCreateWellKnownSid",
          -2147024846,
          "Creating a sid worked with no memory allocated for it. ( This is not good )\n");
      goto LABEL_6;
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError == 122 )
    {
      v10 = GlobalAlloc(0, cbSid);
      v4 = v10;
      if ( !v10 )
      {
        v5 = 14;
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrintError(
            g_pDebug,
            "inetsrv\\iis\\iisrearc\\ftp\\server\\extensibility\\ftphost\\secfcns.cxx",
            113,
            "AllocateAndCreateWellKnownSid",
            -2147024882,
            "Failed to allocate space for SID\n");
        goto LABEL_6;
      }
      v5 = 0;
      if ( CreateWellKnownSid(WellKnownSidType, 0, v10, &cbSid) )
      {
LABEL_6:
        *a2 = v4;
        return v5;
      }
      LastError = GetLastError();
      v5 = LastError;
      if ( (g_dwDebugFlags & 0xF) != 0 )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v8 = "Creating SID failed ( SidType = %d )\n";
        v9 = 129;
        goto LABEL_21;
      }
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v8 = "Getting the SID length failed, can't create the sid (Type = %d)\n";
      v9 = 89;
LABEL_21:
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\extensibility\\ftphost\\secfcns.cxx",
        v9,
        "AllocateAndCreateWellKnownSid",
        LastError,
        v8);
    }
    if ( v5 && v4 )
    {
      GlobalFree(v4);
      return v5;
    }
    goto LABEL_6;
  }
  return 87;
}

```

## disassembly

```asm
0x180003f28  push    rbx
0x180003f2a  push    rbp
0x180003f2b  push    rsi
0x180003f2c  push    rdi
0x180003f2d  sub     rsp, 48h
0x180003f31  mov     [rsp+68h+cbSid], 0
0x180003f39  mov     rsi, rdx
0x180003f3c  mov     ebp, ecx
0x180003f3e  test    rdx, rdx
0x180003f41  jz      loc_1800040B2
0x180003f47  cmp     qword ptr [rdx], 0
0x180003f4b  jnz     loc_1800040B2
0x180003f51  lea     r9, [rsp+68h+cbSid]; cbSid
0x180003f56  xor     r8d, r8d; pSid
0x180003f59  xor     edx, edx; DomainSid
0x180003f5b  xor     edi, edi
0x180003f5d  call    cs:__imp_CreateWellKnownSid
0x180003f63  test    eax, eax
0x180003f65  jz      short loc_180003FB0
0x180003f67  test    cs:g_dwDebugFlags, 0Fh
0x180003f6e  lea     ebx, [rdi+32h]
0x180003f71  jz      short loc_180003FA6
0x180003f73  lea     rax, aCreatingASidWo; "Creating a sid worked with no memory al"...
0x180003f7a  mov     [rsp+68h+var_40], rax
0x180003f7f  lea     r8d, [rdi+47h]
0x180003f83  mov     [rsp+68h+var_48], 80070032h
0x180003f8b  mov     rcx, cs:g_pDebug
0x180003f92  lea     r9, aAllocateandcre; "AllocateAndCreateWellKnownSid"
0x180003f99  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\ftp\\server\\ex"...
0x180003fa0  call    cs:__imp_PuDbgPrintError
0x180003fa6  mov     [rsi], rdi
0x180003fa9  mov     eax, ebx
0x180003fab  jmp     loc_1800040B7
0x180003fb0  call    cs:__imp_GetLastError
0x180003fb6  mov     ebx, eax
0x180003fb8  cmp     eax, 7Ah ; 'z'
0x180003fbb  jz      short loc_180003FE8
0x180003fbd  test    cs:g_dwDebugFlags, 0Fh
0x180003fc4  jz      loc_180004093
0x180003fca  test    eax, eax
0x180003fcc  jle     short loc_180003FD6
0x180003fce  movzx   eax, ax
0x180003fd1  or      eax, 80070000h
0x180003fd6  lea     rcx, aGettingTheSidL; "Getting the SID length failed, can't cr"...
0x180003fdd  mov     r8d, 59h ; 'Y'
0x180003fe3  jmp     loc_18000406B
0x180003fe8  mov     edx, [rsp+68h+cbSid]; dwBytes
0x180003fec  xor     ecx, ecx; uFlags
0x180003fee  call    cs:__imp_GlobalAlloc
0x180003ff4  mov     rdi, rax
0x180003ff7  test    rax, rax
0x180003ffa  jnz     short loc_180004025
0x180003ffc  test    cs:g_dwDebugFlags, 0Fh
0x180004003  lea     ebx, [rax+0Eh]
0x180004006  jz      short loc_180003FA6
0x180004008  lea     rax, aFailedToAlloca; "Failed to allocate space for SID\n"
0x18000400f  mov     [rsp+68h+var_40], rax
0x180004014  lea     r8d, [rdi+71h]
0x180004018  mov     [rsp+68h+var_48], 8007000Eh
0x180004020  jmp     loc_180003F8B
0x180004025  lea     r9, [rsp+68h+cbSid]; cbSid
0x18000402a  mov     r8, rax; pSid
0x18000402d  xor     edx, edx; DomainSid
0x18000402f  mov     ecx, ebp; WellKnownSidType
0x180004031  xor     ebx, ebx
0x180004033  call    cs:__imp_CreateWellKnownSid
0x180004039  test    eax, eax
0x18000403b  jnz     loc_180003FA6
0x180004041  call    cs:__imp_GetLastError
0x180004047  test    cs:g_dwDebugFlags, 0Fh
0x18000404e  mov     ebx, eax
0x180004050  jz      short loc_180004093
0x180004052  test    eax, eax
0x180004054  jle     short loc_18000405E
0x180004056  movzx   eax, ax
0x180004059  or      eax, 80070000h
0x18000405e  lea     rcx, aCreatingSidFai; "Creating SID failed ( SidType = %d )\n"
0x180004065  mov     r8d, 81h
0x18000406b  mov     [rsp+68h+var_38], ebp
0x18000406f  lea     r9, aAllocateandcre; "AllocateAndCreateWellKnownSid"
0x180004076  mov     [rsp+68h+var_40], rcx
0x18000407b  lea     rdx, aInetsrvIisIisr; "inetsrv\\iis\\iisrearc\\ftp\\server\\ex"...
0x180004082  mov     rcx, cs:g_pDebug
0x180004089  mov     [rsp+68h+var_48], eax
0x18000408d  call    cs:__imp_PuDbgPrintError
0x180004093  test    ebx, ebx
0x180004095  jz      loc_180003FA6
0x18000409b  test    rdi, rdi
0x18000409e  jz      loc_180003FA6
0x1800040a4  mov     rcx, rdi; hMem
0x1800040a7  call    cs:__imp_GlobalFree
0x1800040ad  jmp     loc_180003FA9
0x1800040b2  mov     eax, 57h ; 'W'
0x1800040b7  add     rsp, 48h
0x1800040bb  pop     rdi
0x1800040bc  pop     rsi
0x1800040bd  pop     rbp
0x1800040be  pop     rbx
0x1800040bf  retn
```
