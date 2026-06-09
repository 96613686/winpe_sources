# AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)

- ea: `0x180017ac0`
- end: `0x180017c7b`
- name: `?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z`
- size: `443`
- prototype: `unsigned int __fastcall(enum WELL_KNOWN_SID_TYPE, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800179a0`
- `0x180018380`

## callees

- `0x180017ac0`
- `0x180018ec0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017bf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017bf0`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180017c5b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180017c5b`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180017b91`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180017b91`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180017af5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180017bdc`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180017af5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180017bdc`

## string_xrefs

- `0x180017b37`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x180017c30`: `servercommon\inetsrv\iis\iisrearc\core\common\util\secfcns.cxx`
- `0x180017b30`: `AllocateAndCreateWellKnownSid`
- `0x180017c24`: `AllocateAndCreateWellKnownSid`
- `0x180017c13`: `Creating SID failed ( SidType = %d )\n`
- `0x180017b79`: `Getting the SID length failed, can't create the sid (Type = %d)\n`
- `0x180017b11`: `Creating a sid worked with no memory allocated for it. ( This is not good )\n`
- `0x180017bb1`: `Failed to allocate space for SID\n`

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
0x180017ac0  push    rbx
0x180017ac2  push    rbp
0x180017ac3  push    rsi
0x180017ac4  push    rdi
0x180017ac5  sub     rsp, 48h
0x180017ac9  mov     [rsp+68h+cbSid], 0
0x180017ad1  mov     rsi, rdx
0x180017ad4  mov     ebp, ecx
0x180017ad6  test    rdx, rdx
0x180017ad9  jz      loc_180017C6C
0x180017adf  cmp     qword ptr [rdx], 0
0x180017ae3  jnz     loc_180017C6C
0x180017ae9  lea     r9, [rsp+68h+cbSid]; cbSid
0x180017aee  xor     r8d, r8d; pSid
0x180017af1  xor     edx, edx; DomainSid
0x180017af3  xor     edi, edi
0x180017af5  call    cs:__imp_CreateWellKnownSid
0x180017afc  nop     dword ptr [rax+rax+00h]
0x180017b01  test    eax, eax
0x180017b03  jz      short loc_180017B4D
0x180017b05  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017b0c  lea     ebx, [rdi+32h]
0x180017b0f  jz      short loc_180017B43
0x180017b11  lea     rax, aCreatingASidWo; "Creating a sid worked with no memory al"...
0x180017b18  mov     [rsp+68h+var_40], rax; char *
0x180017b1d  lea     r8d, [rdi+4Dh]; unsigned int
0x180017b21  mov     [rsp+68h+dwMessageId], 80070032h; dwMessageId
0x180017b29  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180017b30  lea     r9, aAllocateandcre_2; "AllocateAndCreateWellKnownSid"
0x180017b37  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180017b3e  call    PuDbgPrintError
0x180017b43  mov     [rsi], rdi
0x180017b46  mov     eax, ebx
0x180017b48  jmp     loc_180017C71
0x180017b4d  call    cs:__imp_GetLastError
0x180017b54  nop     dword ptr [rax+rax+00h]
0x180017b59  mov     ebx, eax
0x180017b5b  cmp     eax, 7Ah ; 'z'
0x180017b5e  jz      short loc_180017B8B
0x180017b60  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017b67  jz      loc_180017C47
0x180017b6d  test    eax, eax
0x180017b6f  jle     short loc_180017B79
0x180017b71  movzx   eax, ax
0x180017b74  or      eax, 80070000h
0x180017b79  lea     rcx, aGettingTheSidL; "Getting the SID length failed, can't cr"...
0x180017b80  mov     r8d, 5Fh ; '_'
0x180017b86  jmp     loc_180017C20
0x180017b8b  mov     edx, [rsp+68h+cbSid]; dwBytes
0x180017b8f  xor     ecx, ecx; uFlags
0x180017b91  call    cs:__imp_GlobalAlloc
0x180017b98  nop     dword ptr [rax+rax+00h]
0x180017b9d  mov     rdi, rax
0x180017ba0  test    rax, rax
0x180017ba3  jnz     short loc_180017BCE
0x180017ba5  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017bac  lea     ebx, [rax+0Eh]
0x180017baf  jz      short loc_180017B43
0x180017bb1  lea     rax, aFailedToAlloca_0; "Failed to allocate space for SID\n"
0x180017bb8  mov     [rsp+68h+var_40], rax
0x180017bbd  lea     r8d, [rdi+77h]
0x180017bc1  mov     [rsp+68h+dwMessageId], 8007000Eh
0x180017bc9  jmp     loc_180017B29
0x180017bce  lea     r9, [rsp+68h+cbSid]; cbSid
0x180017bd3  mov     r8, rax; pSid
0x180017bd6  xor     edx, edx; DomainSid
0x180017bd8  mov     ecx, ebp; WellKnownSidType
0x180017bda  xor     ebx, ebx
0x180017bdc  call    cs:__imp_CreateWellKnownSid
0x180017be3  nop     dword ptr [rax+rax+00h]
0x180017be8  test    eax, eax
0x180017bea  jnz     loc_180017B43
0x180017bf0  call    cs:__imp_GetLastError
0x180017bf7  nop     dword ptr [rax+rax+00h]
0x180017bfc  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017c03  mov     ebx, eax
0x180017c05  jz      short loc_180017C47
0x180017c07  test    eax, eax
0x180017c09  jle     short loc_180017C13
0x180017c0b  movzx   eax, ax
0x180017c0e  or      eax, 80070000h
0x180017c13  lea     rcx, aCreatingSidFai; "Creating SID failed ( SidType = %d )\n"
0x180017c1a  mov     r8d, 87h; unsigned int
0x180017c20  mov     dword ptr [rsp+68h+var_38], ebp; char
0x180017c24  lea     r9, aAllocateandcre_2; "AllocateAndCreateWellKnownSid"
0x180017c2b  mov     [rsp+68h+var_40], rcx; char *
0x180017c30  lea     rdx, aServercommonIn_10; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180017c37  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180017c3e  mov     [rsp+68h+dwMessageId], eax; dwMessageId
0x180017c42  call    PuDbgPrintError
0x180017c47  test    ebx, ebx
0x180017c49  jz      loc_180017B43
0x180017c4f  test    rdi, rdi
0x180017c52  jz      loc_180017B43
0x180017c58  mov     rcx, rdi; hMem
0x180017c5b  call    cs:__imp_GlobalFree
0x180017c62  nop     dword ptr [rax+rax+00h]
0x180017c67  jmp     loc_180017B46
0x180017c6c  mov     eax, 57h ; 'W'
0x180017c71  add     rsp, 48h
0x180017c75  pop     rdi
0x180017c76  pop     rsi
0x180017c77  pop     rbp
0x180017c78  pop     rbx
0x180017c79  retn
```
