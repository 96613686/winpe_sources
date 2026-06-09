# PROTOCOL_MESSAGING_HANDLER::CreatePipeSecDesc(void *,void * *)

- ea: `0x18002a020`
- end: `0x18002a20c`
- name: `?CreatePipeSecDesc@PROTOCOL_MESSAGING_HANDLER@@AEAAJPEAXPEAPEAX@Z`
- size: `492`
- prototype: `__int64 __fastcall(PROTOCOL_MESSAGING_HANDLER *this, void *, struct _ACL **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180029da0`

## callees

- `0x18002a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a15e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a056`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a0c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a15e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1a0`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002a0bd`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18002a0bd`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002a154`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18002a154`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002a196`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18002a196`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002a10c`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18002a10c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002a034`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002a034`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a048`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a048`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a1f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a1f2`
- `iisutil!PuDbgPrintError` at `0x18002a0a3`
- `iisutil!PuDbgPrintError` at `0x18002a1e9`
- `iisutil!PuDbgPrintError` at `0x18002a0a3`
- `iisutil!PuDbgPrintError` at `0x18002a1e9`

## string_xrefs

- `0x18002a09c`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002a1de`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\protocol_messaging_handler.cxx`
- `0x18002a0e9`: `Error initializing ACL\n`
- `0x18002a138`: `Error adding ACE to ACL\n`
- `0x18002a17c`: `Error initializing security descriptor\n`
- `0x18002a1be`: `Error setting security descriptor on ACL\n`
- `0x18002a08b`: `PROTOCOL_MESSAGING_HANDLER::CreatePipeSecDesc`
- `0x18002a1d2`: `PROTOCOL_MESSAGING_HANDLER::CreatePipeSecDesc`

## pseudocode

```c
__int64 __fastcall PROTOCOL_MESSAGING_HANDLER::CreatePipeSecDesc(
        PROTOCOL_MESSAGING_HANDLER *this,
        void *a2,
        struct _ACL **a3)
{
  DWORD v5; // esi
  struct _ACL *v6; // rax
  struct _ACL *v7; // rdi
  signed int v8; // eax
  unsigned int v9; // ebx
  struct _ACL *v10; // rbx
  signed int v11; // eax
  const char *v12; // rax
  __int64 v13; // r8
  signed int v14; // eax
  signed int v15; // eax
  signed int LastError; // eax

  v5 = GetLengthSid(a2) + 16;
  v6 = (struct _ACL *)LocalAlloc(0x40u, v5 + 40LL);
  v7 = v6;
  if ( v6 )
  {
    v10 = v6 + 5;
    if ( InitializeAcl(v6 + 5, v5, 2u) )
    {
      if ( AddAccessAllowedAce(v10, 2u, 0x120183u, a2) )
      {
        if ( InitializeSecurityDescriptor(v7, 1u) )
        {
          if ( SetSecurityDescriptorDacl(v7, 1, v10, 0) )
          {
            v9 = 0;
            *a3 = v7;
            return v9;
          }
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_27;
          v12 = "Error setting security descriptor on ACL\n";
          v13 = 564;
        }
        else
        {
          v15 = GetLastError();
          v9 = v15;
          if ( v15 > 0 )
            v9 = (unsigned __int16)v15 | 0x80070000;
          if ( (g_dwDebugFlags & 0xF) == 0 )
            goto LABEL_27;
          v12 = "Error initializing security descriptor\n";
          v13 = 552;
        }
      }
      else
      {
        v14 = GetLastError();
        v9 = v14;
        if ( v14 > 0 )
          v9 = (unsigned __int16)v14 | 0x80070000;
        if ( (g_dwDebugFlags & 0xF) == 0 )
          goto LABEL_27;
        v12 = "Error adding ACE to ACL\n";
        v13 = 540;
      }
    }
    else
    {
      v11 = GetLastError();
      v9 = v11;
      if ( v11 > 0 )
        v9 = (unsigned __int16)v11 | 0x80070000;
      if ( (g_dwDebugFlags & 0xF) == 0 )
        goto LABEL_27;
      v12 = "Error initializing ACL\n";
      v13 = 519;
    }
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
      v13,
      "PROTOCOL_MESSAGING_HANDLER::CreatePipeSecDesc",
      v9,
      v12);
LABEL_27:
    LocalFree(v7);
    return v9;
  }
  v8 = GetLastError();
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\protocol_messaging_handler.cxx",
      504,
      "PROTOCOL_MESSAGING_HANDLER::CreatePipeSecDesc",
      v9,
      "Failed to allocate memory for SD\n");
  return v9;
}

```

## disassembly

```asm
0x18002a020  push    rbx
0x18002a022  push    rbp
0x18002a023  push    rsi
0x18002a024  push    rdi
0x18002a025  push    r14
0x18002a027  sub     rsp, 30h
0x18002a02b  mov     rcx, rdx; pSid
0x18002a02e  mov     r14, r8
0x18002a031  mov     rbp, rdx
0x18002a034  call    cs:__imp_GetLengthSid
0x18002a03a  mov     ecx, 40h ; '@'; uFlags
0x18002a03f  lea     esi, [rax+10h]
0x18002a042  mov     edx, esi
0x18002a044  add     rdx, 28h ; '('; uBytes
0x18002a048  call    cs:__imp_LocalAlloc
0x18002a04e  mov     rdi, rax
0x18002a051  test    rax, rax
0x18002a054  jnz     short loc_18002A0AE
0x18002a056  call    cs:__imp_GetLastError
0x18002a05c  mov     ebx, eax
0x18002a05e  test    eax, eax
0x18002a060  jle     short loc_18002A06B
0x18002a062  movzx   ebx, ax
0x18002a065  or      ebx, 80070000h
0x18002a06b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002a072  jz      loc_18002A1FF
0x18002a078  mov     rcx, cs:g_pDebug
0x18002a07f  lea     rax, aFailedToAlloca_0; "Failed to allocate memory for SD\n"
0x18002a086  mov     [rsp+58h+var_30], rax
0x18002a08b  lea     r9, aProtocolMessag_11; "PROTOCOL_MESSAGING_HANDLER::CreatePipeS"...
0x18002a092  mov     r8d, 1F8h
0x18002a098  mov     [rsp+58h+var_38], ebx
0x18002a09c  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002a0a3  call    cs:__imp_PuDbgPrintError
0x18002a0a9  jmp     loc_18002A1FF
0x18002a0ae  lea     rbx, [rax+28h]
0x18002a0b2  mov     r8d, 2; dwAclRevision
0x18002a0b8  mov     rcx, rbx; pAcl
0x18002a0bb  mov     edx, esi; nAclLength
0x18002a0bd  call    cs:__imp_InitializeAcl
0x18002a0c3  test    eax, eax
0x18002a0c5  jnz     short loc_18002A0FB
0x18002a0c7  call    cs:__imp_GetLastError
0x18002a0cd  mov     ebx, eax
0x18002a0cf  test    eax, eax
0x18002a0d1  jle     short loc_18002A0DC
0x18002a0d3  movzx   ebx, ax
0x18002a0d6  or      ebx, 80070000h
0x18002a0dc  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002a0e3  jz      loc_18002A1EF
0x18002a0e9  lea     rax, aErrorInitializ_1; "Error initializing ACL\n"
0x18002a0f0  mov     r8d, 207h
0x18002a0f6  jmp     loc_18002A1CB
0x18002a0fb  mov     r9, rbp; pSid
0x18002a0fe  mov     edx, 2; dwAceRevision
0x18002a103  mov     r8d, 120183h; AccessMask
0x18002a109  mov     rcx, rbx; pAcl
0x18002a10c  call    cs:__imp_AddAccessAllowedAce
0x18002a112  test    eax, eax
0x18002a114  jnz     short loc_18002A14A
0x18002a116  call    cs:__imp_GetLastError
0x18002a11c  mov     ebx, eax
0x18002a11e  test    eax, eax
0x18002a120  jle     short loc_18002A12B
0x18002a122  movzx   ebx, ax
0x18002a125  or      ebx, 80070000h
0x18002a12b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002a132  jz      loc_18002A1EF
0x18002a138  lea     rax, aErrorAddingAce; "Error adding ACE to ACL\n"
0x18002a13f  mov     r8d, 21Ch
0x18002a145  jmp     loc_18002A1CB
0x18002a14a  mov     esi, 1
0x18002a14f  mov     rcx, rdi; pSecurityDescriptor
0x18002a152  mov     edx, esi; dwRevision
0x18002a154  call    cs:__imp_InitializeSecurityDescriptor
0x18002a15a  test    eax, eax
0x18002a15c  jnz     short loc_18002A18B
0x18002a15e  call    cs:__imp_GetLastError
0x18002a164  mov     ebx, eax
0x18002a166  test    eax, eax
0x18002a168  jle     short loc_18002A173
0x18002a16a  movzx   ebx, ax
0x18002a16d  or      ebx, 80070000h
0x18002a173  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002a17a  jz      short loc_18002A1EF
0x18002a17c  lea     rax, aErrorInitializ_2; "Error initializing security descriptor"...
0x18002a183  mov     r8d, 228h
0x18002a189  jmp     short loc_18002A1CB
0x18002a18b  xor     r9d, r9d; bDaclDefaulted
0x18002a18e  mov     r8, rbx; pDacl
0x18002a191  mov     edx, esi; bDaclPresent
0x18002a193  mov     rcx, rdi; pSecurityDescriptor
0x18002a196  call    cs:__imp_SetSecurityDescriptorDacl
0x18002a19c  test    eax, eax
0x18002a19e  jnz     short loc_18002A1FA
0x18002a1a0  call    cs:__imp_GetLastError
0x18002a1a6  mov     ebx, eax
0x18002a1a8  test    eax, eax
0x18002a1aa  jle     short loc_18002A1B5
0x18002a1ac  movzx   ebx, ax
0x18002a1af  or      ebx, 80070000h
0x18002a1b5  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18002a1bc  jz      short loc_18002A1EF
0x18002a1be  lea     rax, aErrorSettingSe; "Error setting security descriptor on AC"...
0x18002a1c5  mov     r8d, 234h
0x18002a1cb  mov     rcx, cs:g_pDebug
0x18002a1d2  lea     r9, aProtocolMessag_11; "PROTOCOL_MESSAGING_HANDLER::CreatePipeS"...
0x18002a1d9  mov     [rsp+58h+var_30], rax
0x18002a1de  lea     rdx, aServercommonIn_60; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002a1e5  mov     [rsp+58h+var_38], ebx
0x18002a1e9  call    cs:__imp_PuDbgPrintError
0x18002a1ef  mov     rcx, rdi; hMem
0x18002a1f2  call    cs:__imp_LocalFree
0x18002a1f8  jmp     short loc_18002A1FF
0x18002a1fa  xor     ebx, ebx
0x18002a1fc  mov     [r14], rdi
0x18002a1ff  mov     eax, ebx
0x18002a201  add     rsp, 30h
0x18002a205  pop     r14
0x18002a207  pop     rdi
0x18002a208  pop     rsi
0x18002a209  pop     rbp
0x18002a20a  pop     rbx
0x18002a20b  retn
```
