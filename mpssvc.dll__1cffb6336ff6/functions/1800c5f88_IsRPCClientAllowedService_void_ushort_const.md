# IsRPCClientAllowedService(void *,ushort const *)

- ea: `0x1800c5f88`
- end: `0x1800c60ec`
- name: `?IsRPCClientAllowedService@@YAHPEAXPEBG@Z`
- size: `356`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c6780`
- `0x1800c6910`
- `0x1800c6a70`
- `0x1800c6bb0`

## callees

- `0x18000af3c`
- `0x180040f30`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800c5f88`

## import_xrefs

- `ntdll!RtlCreateServiceSid` at `0x1800c6033`
- `ntdll!RtlCreateServiceSid` at `0x1800c6033`
- `ntdll!RtlInitUnicodeString` at `0x1800c5fe6`
- `ntdll!RtlInitUnicodeString` at `0x1800c5fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c607b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c607b`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800c6071`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800c6071`
- `fwbase!FwNtStatusToHResult` at `0x1800c603b`
- `fwbase!FwNtStatusToHResult` at `0x1800c603b`
- `fwbase!FwCloseHandle` at `0x1800c60c2`
- `fwbase!FwCloseHandle` at `0x1800c60c2`

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
        WPP_b7c33e85cf4d34b1ab1e131583d2c8f9_Traceguids,
        (unsigned int)AccessTokenFromClientBinding);
    }
  }
  FwCloseHandle(TokenHandle);
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x1800c5f88  mov     [rsp-8+arg_10], rbx
0x1800c5f8d  mov     [rsp-8+arg_18], rdi
0x1800c5f92  push    rbp
0x1800c5f93  lea     rbp, [rsp-57h]
0x1800c5f98  sub     rsp, 0A0h
0x1800c5f9f  mov     rax, cs:__security_cookie
0x1800c5fa6  xor     rax, rsp
0x1800c5fa9  mov     [rbp+57h+var_10], rax
0x1800c5fad  mov     rbx, rdx
0x1800c5fb0  mov     [rbp+57h+TokenHandle], 0
0x1800c5fb8  xor     edx, edx; Val
0x1800c5fba  mov     [rbp+57h+IsMember], 0
0x1800c5fc1  mov     rdi, rcx
0x1800c5fc4  xorps   xmm0, xmm0
0x1800c5fc7  lea     rcx, [rbp+57h+ServiceSid]; void *
0x1800c5fcb  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800c5fcf  lea     r8d, [rdx+44h]; Size
0x1800c5fd3  call    memset_0
0x1800c5fd8  mov     rdx, rbx; SourceString
0x1800c5fdb  mov     [rbp+57h+ServiceSidLength], 44h ; 'D'
0x1800c5fe2  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800c5fe6  call    cs:__imp_RtlInitUnicodeString
0x1800c5fec  lea     r8, [rbp+57h+TokenHandle]
0x1800c5ff0  mov     rcx, rdi
0x1800c5ff3  call    FwRpcAPIsGetAccessTokenFromClientBinding
0x1800c5ff8  test    eax, eax
0x1800c5ffa  jns     short loc_1800C6027
0x1800c5ffc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6003  lea     rdx, WPP_GLOBAL_Control
0x1800c600a  cmp     rcx, rdx
0x1800c600d  jz      loc_1800C60BE
0x1800c6013  test    byte ptr [rcx+1Ch], 1
0x1800c6017  jz      loc_1800C60BE
0x1800c601d  mov     edx, 5Bh ; '['
0x1800c6022  jmp     loc_1800C60AB
0x1800c6027  lea     r8, [rbp+57h+ServiceSidLength]; ServiceSidLength
0x1800c602b  lea     rdx, [rbp+57h+ServiceSid]; ServiceSid
0x1800c602f  lea     rcx, [rbp+57h+DestinationString]; ServiceName
0x1800c6033  call    cs:__imp_RtlCreateServiceSid
0x1800c6039  mov     ecx, eax
0x1800c603b  call    cs:__imp_FwNtStatusToHResult
0x1800c6041  test    eax, eax
0x1800c6043  jns     short loc_1800C6065
0x1800c6045  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c604c  lea     rdx, WPP_GLOBAL_Control
0x1800c6053  cmp     rcx, rdx
0x1800c6056  jz      short loc_1800C60BE
0x1800c6058  test    byte ptr [rcx+1Ch], 1
0x1800c605c  jz      short loc_1800C60BE
0x1800c605e  mov     edx, 5Ch ; '\'
0x1800c6063  jmp     short loc_1800C60AB
0x1800c6065  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800c6069  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800c606d  lea     rdx, [rbp+57h+ServiceSid]; SidToCheck
0x1800c6071  call    cs:__imp_CheckTokenMembership
0x1800c6077  test    eax, eax
0x1800c6079  jnz     short loc_1800C60BE
0x1800c607b  call    cs:__imp_GetLastError
0x1800c6081  test    eax, eax
0x1800c6083  jle     short loc_1800C608D
0x1800c6085  movzx   eax, ax
0x1800c6088  or      eax, 80070000h
0x1800c608d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6094  lea     rdx, WPP_GLOBAL_Control
0x1800c609b  cmp     rcx, rdx
0x1800c609e  jz      short loc_1800C60BE
0x1800c60a0  test    byte ptr [rcx+1Ch], 1
0x1800c60a4  jz      short loc_1800C60BE
0x1800c60a6  mov     edx, 5Dh ; ']'
0x1800c60ab  mov     rcx, [rcx+10h]
0x1800c60af  lea     r8, WPP_b7c33e85cf4d34b1ab1e131583d2c8f9_Traceguids
0x1800c60b6  mov     r9d, eax
0x1800c60b9  call    WPP_SF_d
0x1800c60be  mov     rcx, [rbp+57h+TokenHandle]
0x1800c60c2  call    cs:__imp_FwCloseHandle
0x1800c60c8  mov     eax, [rbp+57h+IsMember]
0x1800c60cb  mov     rcx, [rbp+57h+var_10]
0x1800c60cf  xor     rcx, rsp; StackCookie
0x1800c60d2  call    __security_check_cookie
0x1800c60d7  lea     r11, [rsp+0A0h+var_s0]
0x1800c60df  mov     rbx, [r11+20h]
0x1800c60e3  mov     rdi, [r11+28h]
0x1800c60e7  mov     rsp, r11
0x1800c60ea  pop     rbp
0x1800c60eb  retn
```
