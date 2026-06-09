# CngAdtLogEvent(ushort,_AUDIT_PARAMS *,ushort)

- ea: `0x180075a60`
- end: `0x180075cb7`
- name: `?CngAdtLogEvent@@YAJGPEAU_AUDIT_PARAMS@@G@Z`
- size: `599`
- prototype: `__int64 __fastcall(unsigned __int16, struct _AUDIT_PARAMS *)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180075100`
- `0x180075360`
- `0x180075600`
- `0x1800fb3c0`
- `0x1800fb530`
- `0x1800fb680`

## callees

- `0x180075a60`
- `0x180075cc0`
- `0x180075dd8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075c1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075c59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075c1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075c59`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180075c0c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180075c0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180075a9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180075a9d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180075ab8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180075ab8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075bc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180075bc5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180075ac8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180075ac8`
- `AUTHZ!AuthziInitializeAuditEvent` at `0x180075b89`
- `AUTHZ!AuthziInitializeAuditEvent` at `0x180075b89`
- `AUTHZ!AuthziLogAuditEvent` at `0x180075ba6`
- `AUTHZ!AuthziLogAuditEvent` at `0x180075ba6`
- `AUTHZ!AuthzFreeAuditEvent` at `0x180075be2`
- `AUTHZ!AuthzFreeAuditEvent` at `0x180075be2`

## pseudocode

```c
__int64 __fastcall CngAdtLogEvent(unsigned __int16 a1, struct _AUDIT_PARAMS *a2)
{
  int v3; // esi
  int v4; // edi
  HANDLE CurrentThread; // rax
  signed int LastError; // ebx
  struct AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *v7; // r8
  AUTHZ_AUDIT_EVENT_HANDLE hAuditEvent[2]; // [rsp+60h] [rbp-10h] BYREF
  int v10; // [rsp+A0h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+A8h] [rbp+38h] BYREF

  v3 = a1;
  TokenHandle = 0;
  v4 = 1;
  v10 = 0;
  hAuditEvent[0] = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
  {
    RevertToSelf();
    v4 = 0;
  }
  LastError = CngAdtCheckTCB(&v10);
  if ( LastError >= 0 )
  {
    if ( !v10 )
    {
      LastError = -1073741244;
      goto LABEL_17;
    }
    LastError = CngAdtInitialize();
    if ( LastError >= 0 )
    {
      switch ( v3 )
      {
        case 5056:
          v7 = qword_1801A0D30;
          break;
        case 5057:
          v7 = qword_1801A0D28;
          break;
        case 5058:
          v7 = qword_1801A0D20;
          break;
        case 5059:
          v7 = qword_1801A0D18;
          break;
        case 5060:
          v7 = qword_1801A0D10;
          break;
        case 5061:
          v7 = g_hAdtEventTypes;
          break;
        default:
          goto LABEL_31;
      }
      if ( v7 )
      {
        if ( (unsigned int)AuthziInitializeAuditEvent(
                             0,
                             0,
                             v7,
                             a2,
                             0,
                             -1,
                             &cchOriginalDestLength,
                             &cchOriginalDestLength,
                             &cchOriginalDestLength,
                             &cchOriginalDestLength,
                             hAuditEvent)
          && (unsigned int)AuthziLogAuditEvent(0, hAuditEvent[0], 0) )
        {
          LastError = 0;
        }
        else if ( (int)GetLastError() > 0 )
        {
          LastError = (unsigned __int16)GetLastError() | 0xC0070000;
        }
        else
        {
          LastError = GetLastError();
        }
        goto LABEL_17;
      }
LABEL_31:
      LastError = -1073741822;
    }
  }
LABEL_17:
  if ( !v4 && !SetThreadToken(0, TokenHandle) )
    GetLastError();
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( hAuditEvent[0] )
    AuthzFreeAuditEvent(hAuditEvent[0]);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180075a60  mov     [rsp-18h+arg_0], rbx
0x180075a65  mov     [rsp-18h+arg_8], rsi
0x180075a6a  mov     word ptr [rsp-18h+arg_10], r8w
0x180075a70  push    rbp
0x180075a71  push    rdi
0x180075a72  push    r14
0x180075a74  mov     rbp, rsp
0x180075a77  sub     rsp, 70h
0x180075a7b  mov     r14, rdx
0x180075a7e  movzx   esi, cx
0x180075a81  mov     [rbp+TokenHandle], 0
0x180075a89  mov     edi, 1
0x180075a8e  mov     [rbp+arg_10], 0
0x180075a95  mov     [rbp+hAuditEvent], 0
0x180075a9d  call    cs:__imp_GetCurrentThread
0x180075aa4  nop     dword ptr [rax+rax+00h]
0x180075aa9  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180075aad  mov     r8d, edi; OpenAsSelf
0x180075ab0  mov     rcx, rax; ThreadHandle
0x180075ab3  mov     edx, 0F01FFh; DesiredAccess
0x180075ab8  call    cs:__imp_OpenThreadToken
0x180075abf  nop     dword ptr [rax+rax+00h]
0x180075ac4  test    eax, eax
0x180075ac6  jz      short loc_180075AD6
0x180075ac8  call    cs:__imp_RevertToSelf
0x180075acf  nop     dword ptr [rax+rax+00h]
0x180075ad4  xor     edi, edi
0x180075ad6  lea     rcx, [rbp+arg_10]; int *
0x180075ada  call    ?CngAdtCheckTCB@@YAJPEAH@Z; CngAdtCheckTCB(int *)
0x180075adf  mov     ebx, eax
0x180075ae1  test    eax, eax
0x180075ae3  js      loc_180075BB8
0x180075ae9  cmp     [rbp+arg_10], 0
0x180075aed  jz      loc_180075C7F
0x180075af3  call    ?CngAdtInitialize@@YAJXZ; CngAdtInitialize(void)
0x180075af8  mov     ebx, eax
0x180075afa  test    eax, eax
0x180075afc  js      loc_180075BB8
0x180075b02  mov     ecx, esi
0x180075b04  sub     ecx, 13C0h
0x180075b0a  jz      loc_180075CAB
0x180075b10  sub     ecx, 1
0x180075b13  jz      loc_180075C9F
0x180075b19  sub     ecx, 1
0x180075b1c  jz      loc_180075C4D
0x180075b22  sub     ecx, 1
0x180075b25  jz      loc_180075C73
0x180075b2b  sub     ecx, 1
0x180075b2e  jz      loc_180075C93
0x180075b34  cmp     ecx, 1
0x180075b37  jnz     loc_180075C89
0x180075b3d  mov     r8, cs:?g_hAdtEventTypes@@3PAPEAUAUTHZ_AUDIT_EVENT_TYPE_HANDLE__@@A; AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ * near * g_hAdtEventTypes
0x180075b44  test    r8, r8
0x180075b47  jz      loc_180075C89
0x180075b4d  lea     rax, [rbp+hAuditEvent]
0x180075b51  mov     r9, r14
0x180075b54  mov     [rsp+70h+var_20], rax
0x180075b59  xor     edx, edx
0x180075b5b  lea     rax, cchOriginalDestLength
0x180075b62  xor     ecx, ecx
0x180075b64  mov     [rsp+70h+var_28], rax
0x180075b69  mov     [rsp+70h+var_30], rax
0x180075b6e  mov     [rsp+70h+var_38], rax
0x180075b73  mov     [rsp+70h+var_40], rax
0x180075b78  mov     [rsp+70h+var_48], 0FFFFFFFFh
0x180075b80  mov     [rsp+70h+var_50], 0
0x180075b89  call    cs:__imp_AuthziInitializeAuditEvent
0x180075b90  nop     dword ptr [rax+rax+00h]
0x180075b95  test    eax, eax
0x180075b97  jz      loc_180075C2A
0x180075b9d  mov     rdx, [rbp+hAuditEvent]
0x180075ba1  xor     r8d, r8d
0x180075ba4  xor     ecx, ecx
0x180075ba6  call    cs:__imp_AuthziLogAuditEvent
0x180075bad  nop     dword ptr [rax+rax+00h]
0x180075bb2  test    eax, eax
0x180075bb4  jz      short loc_180075C2A
0x180075bb6  xor     ebx, ebx
0x180075bb8  test    edi, edi
0x180075bba  jz      short loc_180075C06
0x180075bbc  mov     rcx, [rbp+TokenHandle]; hObject
0x180075bc0  test    rcx, rcx
0x180075bc3  jz      short loc_180075BD9
0x180075bc5  call    cs:__imp_CloseHandle
0x180075bcc  nop     dword ptr [rax+rax+00h]
0x180075bd1  mov     [rbp+TokenHandle], 0
0x180075bd9  mov     rcx, [rbp+hAuditEvent]; hAuditEvent
0x180075bdd  test    rcx, rcx
0x180075be0  jz      short loc_180075BEE
0x180075be2  call    cs:__imp_AuthzFreeAuditEvent
0x180075be9  nop     dword ptr [rax+rax+00h]
0x180075bee  lea     r11, [rsp+70h+var_s0]
0x180075bf3  mov     eax, ebx
0x180075bf5  mov     rbx, [r11+20h]
0x180075bf9  mov     rsi, [r11+28h]
0x180075bfd  mov     rsp, r11
0x180075c00  pop     r14
0x180075c02  pop     rdi
0x180075c03  pop     rbp
0x180075c04  retn
0x180075c06  mov     rdx, [rbp+TokenHandle]; Token
0x180075c0a  xor     ecx, ecx; Thread
0x180075c0c  call    cs:__imp_SetThreadToken
0x180075c13  nop     dword ptr [rax+rax+00h]
0x180075c18  test    eax, eax
0x180075c1a  jnz     short loc_180075BBC
0x180075c1c  call    cs:__imp_GetLastError
0x180075c23  nop     dword ptr [rax+rax+00h]
0x180075c28  jmp     short loc_180075BBC
0x180075c2a  call    cs:__imp_GetLastError
0x180075c31  nop     dword ptr [rax+rax+00h]
0x180075c36  test    eax, eax
0x180075c38  jg      short loc_180075C59
0x180075c3a  call    cs:__imp_GetLastError
0x180075c41  nop     dword ptr [rax+rax+00h]
0x180075c46  mov     ebx, eax
0x180075c48  jmp     loc_180075BB8
0x180075c4d  mov     r8, cs:qword_1801A0D20
0x180075c54  jmp     loc_180075B44
0x180075c59  call    cs:__imp_GetLastError
0x180075c60  nop     dword ptr [rax+rax+00h]
0x180075c65  movzx   ebx, ax
0x180075c68  or      ebx, 0C0070000h
0x180075c6e  jmp     loc_180075BB8
0x180075c73  mov     r8, cs:qword_1801A0D18
0x180075c7a  jmp     loc_180075B44
0x180075c7f  mov     ebx, 0C0000244h
0x180075c84  jmp     loc_180075BB8
0x180075c89  mov     ebx, 0C0000002h
0x180075c8e  jmp     loc_180075BB8
0x180075c93  mov     r8, cs:qword_1801A0D10
0x180075c9a  jmp     loc_180075B44
0x180075c9f  mov     r8, cs:qword_1801A0D28
0x180075ca6  jmp     loc_180075B44
0x180075cab  mov     r8, cs:qword_1801A0D30
0x180075cb2  jmp     loc_180075B44
```
