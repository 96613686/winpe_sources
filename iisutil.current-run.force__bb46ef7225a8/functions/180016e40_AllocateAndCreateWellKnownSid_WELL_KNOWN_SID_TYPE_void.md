# AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)

- ea: `0x180016e40`
- end: `0x180016fd6`
- name: `?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z`
- size: `406`
- prototype: `unsigned int __fastcall(enum WELL_KNOWN_SID_TYPE, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016d20`
- `0x180017640`

## callees

- `0x180016e40`
- `0x1800180c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ec7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ec7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f58`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180016fbd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180016fbd`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180016f05`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180016f05`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180016e75`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180016f4a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180016e75`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180016f4a`

## string_xrefs

- `0x180016eb1`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x180016f92`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x180016eaa`: `AllocateAndCreateWellKnownSid`
- `0x180016f86`: `AllocateAndCreateWellKnownSid`
- `0x180016f75`: `Creating SID failed ( SidType = %d )\n`
- `0x180016eed`: `Getting the SID length failed, can't create the sid (Type = %d)\n`
- `0x180016e8b`: `Creating a sid worked with no memory allocated for it. ( This is not good )\n`
- `0x180016f1f`: `Failed to allocate space for SID\n`

## pseudocode

```c
__int64 __fastcall AllocateAndCreateWellKnownSid(__int32 a1, void **a2)
{
  void *v4; // rdi
  unsigned int v5; // ebx
  int dwMessageId; // eax
  char *v8; // rcx
  unsigned int v9; // r8d
  HGLOBAL v10; // rax
  char v11; // [rsp+30h] [rbp-38h]
  DWORD cbSid; // [rsp+78h] [rbp+10h] BYREF

  cbSid = 0;
  if ( a2 && !*a2 )
  {
    v4 = 0;
    if ( CreateWellKnownSid((WELL_KNOWN_SID_TYPE)a1, 0, 0, &cbSid) )
    {
      v5 = 50;
      if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
        PuDbgPrintError(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
          0x4Du,
          "AllocateAndCreateWellKnownSid",
          0x80070032,
          "Creating a sid worked with no memory allocated for it. ( This is not good )\n",
          v11);
      goto LABEL_6;
    }
    dwMessageId = GetLastError();
    v5 = dwMessageId;
    if ( dwMessageId == 122 )
    {
      v10 = GlobalAlloc(0, cbSid);
      v4 = v10;
      if ( !v10 )
      {
        v5 = 14;
        if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
          PuDbgPrintError(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
            0x77u,
            "AllocateAndCreateWellKnownSid",
            0x8007000E,
            "Failed to allocate space for SID\n",
            v11);
        goto LABEL_6;
      }
      v5 = 0;
      if ( CreateWellKnownSid((WELL_KNOWN_SID_TYPE)a1, 0, v10, &cbSid) )
      {
LABEL_6:
        *a2 = v4;
        return v5;
      }
      dwMessageId = GetLastError();
      v5 = dwMessageId;
      if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
      {
        if ( dwMessageId > 0 )
          dwMessageId = (unsigned __int16)dwMessageId | 0x80070000;
        v8 = "Creating SID failed ( SidType = %d )\n";
        v9 = 135;
        goto LABEL_21;
      }
    }
    else if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
    {
      if ( dwMessageId > 0 )
        dwMessageId = (unsigned __int16)dwMessageId | 0x80070000;
      v8 = "Getting the SID length failed, can't create the sid (Type = %d)\n";
      v9 = 95;
LABEL_21:
      PuDbgPrintError(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\secfcns.cxx",
        v9,
        "AllocateAndCreateWellKnownSid",
        dwMessageId,
        v8,
        a1);
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
0x180016e40  push    rbx
0x180016e42  push    rbp
0x180016e43  push    rsi
0x180016e44  push    rdi
0x180016e45  sub     rsp, 48h
0x180016e49  mov     [rsp+68h+cbSid], 0
0x180016e51  mov     rsi, rdx
0x180016e54  mov     ebp, ecx
0x180016e56  test    rdx, rdx
0x180016e59  jz      loc_180016FC8
0x180016e5f  cmp     qword ptr [rdx], 0
0x180016e63  jnz     loc_180016FC8
0x180016e69  lea     r9, [rsp+68h+cbSid]; cbSid
0x180016e6e  xor     r8d, r8d; pSid
0x180016e71  xor     edx, edx; DomainSid
0x180016e73  xor     edi, edi
0x180016e75  call    cs:__imp_CreateWellKnownSid
0x180016e7b  test    eax, eax
0x180016e7d  jz      short loc_180016EC7
0x180016e7f  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180016e86  lea     ebx, [rdi+32h]
0x180016e89  jz      short loc_180016EBD
0x180016e8b  lea     rax, aCreatingASidWo; "Creating a sid worked with no memory al"...
0x180016e92  mov     [rsp+68h+var_40], rax; char *
0x180016e97  lea     r8d, [rdi+4Dh]; unsigned int
0x180016e9b  mov     [rsp+68h+dwMessageId], 80070032h; dwMessageId
0x180016ea3  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180016eaa  lea     r9, aAllocateandcre_2; "AllocateAndCreateWellKnownSid"
0x180016eb1  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180016eb8  call    PuDbgPrintError
0x180016ebd  mov     [rsi], rdi
0x180016ec0  mov     eax, ebx
0x180016ec2  jmp     loc_180016FCD
0x180016ec7  call    cs:__imp_GetLastError
0x180016ecd  mov     ebx, eax
0x180016ecf  cmp     eax, 7Ah ; 'z'
0x180016ed2  jz      short loc_180016EFF
0x180016ed4  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180016edb  jz      loc_180016FA9
0x180016ee1  test    eax, eax
0x180016ee3  jle     short loc_180016EED
0x180016ee5  movzx   eax, ax
0x180016ee8  or      eax, 80070000h
0x180016eed  lea     rcx, aGettingTheSidL; "Getting the SID length failed, can't cr"...
0x180016ef4  mov     r8d, 5Fh ; '_'
0x180016efa  jmp     loc_180016F82
0x180016eff  mov     edx, [rsp+68h+cbSid]; dwBytes
0x180016f03  xor     ecx, ecx; uFlags
0x180016f05  call    cs:__imp_GlobalAlloc
0x180016f0b  mov     rdi, rax
0x180016f0e  test    rax, rax
0x180016f11  jnz     short loc_180016F3C
0x180016f13  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180016f1a  lea     ebx, [rax+0Eh]
0x180016f1d  jz      short loc_180016EBD
0x180016f1f  lea     rax, aFailedToAlloca_0; "Failed to allocate space for SID\n"
0x180016f26  mov     [rsp+68h+var_40], rax
0x180016f2b  lea     r8d, [rdi+77h]
0x180016f2f  mov     [rsp+68h+dwMessageId], 8007000Eh
0x180016f37  jmp     loc_180016EA3
0x180016f3c  lea     r9, [rsp+68h+cbSid]; cbSid
0x180016f41  mov     r8, rax; pSid
0x180016f44  xor     edx, edx; DomainSid
0x180016f46  mov     ecx, ebp; WellKnownSidType
0x180016f48  xor     ebx, ebx
0x180016f4a  call    cs:__imp_CreateWellKnownSid
0x180016f50  test    eax, eax
0x180016f52  jnz     loc_180016EBD
0x180016f58  call    cs:__imp_GetLastError
0x180016f5e  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180016f65  mov     ebx, eax
0x180016f67  jz      short loc_180016FA9
0x180016f69  test    eax, eax
0x180016f6b  jle     short loc_180016F75
0x180016f6d  movzx   eax, ax
0x180016f70  or      eax, 80070000h
0x180016f75  lea     rcx, aCreatingSidFai; "Creating SID failed ( SidType = %d )\n"
0x180016f7c  mov     r8d, 87h; unsigned int
0x180016f82  mov     dword ptr [rsp+68h+var_38], ebp; char
0x180016f86  lea     r9, aAllocateandcre_2; "AllocateAndCreateWellKnownSid"
0x180016f8d  mov     [rsp+68h+var_40], rcx; char *
0x180016f92  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180016f99  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180016fa0  mov     [rsp+68h+dwMessageId], eax; dwMessageId
0x180016fa4  call    PuDbgPrintError
0x180016fa9  test    ebx, ebx
0x180016fab  jz      loc_180016EBD
0x180016fb1  test    rdi, rdi
0x180016fb4  jz      loc_180016EBD
0x180016fba  mov     rcx, rdi; hMem
0x180016fbd  call    cs:__imp_GlobalFree
0x180016fc3  jmp     loc_180016EC0
0x180016fc8  mov     eax, 57h ; 'W'
0x180016fcd  add     rsp, 48h
0x180016fd1  pop     rdi
0x180016fd2  pop     rsi
0x180016fd3  pop     rbp
0x180016fd4  pop     rbx
0x180016fd5  retn
```
