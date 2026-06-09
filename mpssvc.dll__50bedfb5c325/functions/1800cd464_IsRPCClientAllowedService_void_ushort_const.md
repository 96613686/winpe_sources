# IsRPCClientAllowedService(void *,ushort const *)

- ea: `0x1800cd464`
- end: `0x1800cd5ed`
- name: `?IsRPCClientAllowedService@@YAHPEAXPEBG@Z`
- size: `393`
- prototype: `int(void *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800cdc50`
- `0x1800cddf0`
- `0x1800cdf60`
- `0x1800ce0b0`

## callees

- `0x18000a710`
- `0x1800414d0`
- `0x1800729c0`
- `0x180073488`
- `0x1800cd464`

## import_xrefs

- `ntdll!RtlCreateServiceSid` at `0x1800cd515`
- `ntdll!RtlCreateServiceSid` at `0x1800cd515`
- `ntdll!RtlInitUnicodeString` at `0x1800cd4c2`
- `ntdll!RtlInitUnicodeString` at `0x1800cd4c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd56f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cd56f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800cd55f`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800cd55f`
- `fwbase!FwNtStatusToHResult` at `0x1800cd523`
- `fwbase!FwNtStatusToHResult` at `0x1800cd523`
- `fwbase!FwCloseHandle` at `0x1800cd5bc`
- `fwbase!FwCloseHandle` at `0x1800cd5bc`

## pseudocode

```c
__int64 __fastcall IsRPCClientAllowedService(void *a1, const unsigned __int16 *a2)
{
  __int64 v4; // rdx
  int AccessTokenFromClientBinding; // eax
  __int64 v6; // rcx
  __int64 v7; // rdx
  unsigned int v8; // eax
  HANDLE TokenHandle; // [rsp+20h] [rbp-29h] BYREF
  WINBOOL IsMember; // [rsp+28h] [rbp-21h] BYREF
  ULONG ServiceSidLength; // [rsp+2Ch] [rbp-1Dh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-19h] BYREF
  _BYTE ServiceSid[80]; // [rsp+40h] [rbp-9h] BYREF

  TokenHandle = 0;
  IsMember = 0;
  DestinationString = 0;
  memset_0(ServiceSid, 0, 0x44u);
  ServiceSidLength = 68;
  RtlInitUnicodeString(&DestinationString, a2);
  AccessTokenFromClientBinding = FwRpcAPIsGetAccessTokenFromClientBinding(a1, v4, &TokenHandle);
  if ( AccessTokenFromClientBinding >= 0 )
  {
    v8 = RtlCreateServiceSid(&DestinationString, ServiceSid, &ServiceSidLength);
    AccessTokenFromClientBinding = FwNtStatusToHResult(v8);
    if ( AccessTokenFromClientBinding >= 0 )
    {
      if ( !CheckTokenMembership(TokenHandle, ServiceSid, &IsMember) )
      {
        AccessTokenFromClientBinding = GetLastError();
        if ( AccessTokenFromClientBinding > 0 )
          AccessTokenFromClientBinding = (unsigned __int16)AccessTokenFromClientBinding | 0x80070000;
        v6 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v7 = 93;
          goto LABEL_15;
        }
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v7 = 92;
        goto LABEL_15;
      }
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v7 = 91;
LABEL_15:
      WPP_SF_d(
        *(_QWORD *)(v6 + 16),
        v7,
        WPP_3b1e4392722f3ffab86eacb96e939df9_Traceguids,
        (unsigned int)AccessTokenFromClientBinding);
    }
  }
  FwCloseHandle(TokenHandle);
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x1800cd464  mov     [rsp-8+arg_10], rbx
0x1800cd469  mov     [rsp-8+arg_18], rdi
0x1800cd46e  push    rbp
0x1800cd46f  lea     rbp, [rsp-57h]
0x1800cd474  sub     rsp, 0A0h
0x1800cd47b  mov     rax, cs:__security_cookie
0x1800cd482  xor     rax, rsp
0x1800cd485  mov     [rbp+57h+var_10], rax
0x1800cd489  mov     rbx, rdx
0x1800cd48c  mov     [rbp+57h+TokenHandle], 0
0x1800cd494  xor     edx, edx; Val
0x1800cd496  mov     [rbp+57h+IsMember], 0
0x1800cd49d  mov     rdi, rcx
0x1800cd4a0  xorps   xmm0, xmm0
0x1800cd4a3  lea     rcx, [rbp+57h+ServiceSid]; void *
0x1800cd4a7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800cd4ab  lea     r8d, [rdx+44h]; Size
0x1800cd4af  call    memset_0
0x1800cd4b4  mov     rdx, rbx; SourceString
0x1800cd4b7  mov     [rbp+57h+ServiceSidLength], 44h ; 'D'
0x1800cd4be  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800cd4c2  call    cs:__imp_RtlInitUnicodeString
0x1800cd4c9  nop     dword ptr [rax+rax+00h]
0x1800cd4ce  lea     r8, [rbp+57h+TokenHandle]
0x1800cd4d2  mov     rcx, rdi
0x1800cd4d5  call    FwRpcAPIsGetAccessTokenFromClientBinding
0x1800cd4da  test    eax, eax
0x1800cd4dc  jns     short loc_1800CD509
0x1800cd4de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cd4e5  lea     rdx, WPP_GLOBAL_Control
0x1800cd4ec  cmp     rcx, rdx
0x1800cd4ef  jz      loc_1800CD5B8
0x1800cd4f5  test    byte ptr [rcx+1Ch], 1
0x1800cd4f9  jz      loc_1800CD5B8
0x1800cd4ff  mov     edx, 5Bh ; '['
0x1800cd504  jmp     loc_1800CD5A5
0x1800cd509  lea     r8, [rbp+57h+ServiceSidLength]; ServiceSidLength
0x1800cd50d  lea     rdx, [rbp+57h+ServiceSid]; ServiceSid
0x1800cd511  lea     rcx, [rbp+57h+DestinationString]; ServiceName
0x1800cd515  call    cs:__imp_RtlCreateServiceSid
0x1800cd51c  nop     dword ptr [rax+rax+00h]
0x1800cd521  mov     ecx, eax
0x1800cd523  call    cs:__imp_FwNtStatusToHResult
0x1800cd52a  nop     dword ptr [rax+rax+00h]
0x1800cd52f  test    eax, eax
0x1800cd531  jns     short loc_1800CD553
0x1800cd533  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cd53a  lea     rdx, WPP_GLOBAL_Control
0x1800cd541  cmp     rcx, rdx
0x1800cd544  jz      short loc_1800CD5B8
0x1800cd546  test    byte ptr [rcx+1Ch], 1
0x1800cd54a  jz      short loc_1800CD5B8
0x1800cd54c  mov     edx, 5Ch ; '\'
0x1800cd551  jmp     short loc_1800CD5A5
0x1800cd553  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800cd557  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800cd55b  lea     rdx, [rbp+57h+ServiceSid]; SidToCheck
0x1800cd55f  call    cs:__imp_CheckTokenMembership
0x1800cd566  nop     dword ptr [rax+rax+00h]
0x1800cd56b  test    eax, eax
0x1800cd56d  jnz     short loc_1800CD5B8
0x1800cd56f  call    cs:__imp_GetLastError
0x1800cd576  nop     dword ptr [rax+rax+00h]
0x1800cd57b  test    eax, eax
0x1800cd57d  jle     short loc_1800CD587
0x1800cd57f  movzx   eax, ax
0x1800cd582  or      eax, 80070000h
0x1800cd587  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cd58e  lea     rdx, WPP_GLOBAL_Control
0x1800cd595  cmp     rcx, rdx
0x1800cd598  jz      short loc_1800CD5B8
0x1800cd59a  test    byte ptr [rcx+1Ch], 1
0x1800cd59e  jz      short loc_1800CD5B8
0x1800cd5a0  mov     edx, 5Dh ; ']'
0x1800cd5a5  mov     rcx, [rcx+10h]
0x1800cd5a9  lea     r8, WPP_3b1e4392722f3ffab86eacb96e939df9_Traceguids
0x1800cd5b0  mov     r9d, eax
0x1800cd5b3  call    WPP_SF_d
0x1800cd5b8  mov     rcx, [rbp+57h+TokenHandle]
0x1800cd5bc  call    cs:__imp_FwCloseHandle
0x1800cd5c3  nop     dword ptr [rax+rax+00h]
0x1800cd5c8  mov     eax, [rbp+57h+IsMember]
0x1800cd5cb  mov     rcx, [rbp+57h+var_10]
0x1800cd5cf  xor     rcx, rsp; StackCookie
0x1800cd5d2  call    __security_check_cookie
0x1800cd5d7  lea     r11, [rsp+0A0h+var_s0]
0x1800cd5df  mov     rbx, [r11+20h]
0x1800cd5e3  mov     rdi, [r11+28h]
0x1800cd5e7  mov     rsp, r11
0x1800cd5ea  pop     rbp
0x1800cd5eb  retn
```
