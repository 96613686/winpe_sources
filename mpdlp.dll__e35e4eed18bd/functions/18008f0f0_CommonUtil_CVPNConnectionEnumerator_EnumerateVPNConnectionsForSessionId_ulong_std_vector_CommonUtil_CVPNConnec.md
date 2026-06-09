# CommonUtil::CVPNConnectionEnumerator::EnumerateVPNConnectionsForSessionId(ulong,std::vector<CommonUtil::CVPNConnection,std::allocator<CommonUtil::CVPNConnection>> &)

- ea: `0x18008f0f0`
- end: `0x18008f21f`
- name: `?EnumerateVPNConnectionsForSessionId@CVPNConnectionEnumerator@CommonUtil@@QEBAJKAEAV?$vector@VCVPNConnection@CommonUtil@@V?$allocator@VCVPNConnection@CommonUtil@@@std@@@std@@@Z`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008e894`

## callees

- `0x1800809d0`
- `0x18008f0f0`
- `0x18008f220`
- `0x180106cc4`
- `0x18010cb40`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18008f13d`
- `KERNEL32!CloseHandle` at `0x18008f1ef`
- `KERNEL32!CloseHandle` at `0x18008f1fe`
- `KERNEL32!CloseHandle` at `0x18008f13d`
- `KERNEL32!CloseHandle` at `0x18008f1ef`
- `KERNEL32!CloseHandle` at `0x18008f1fe`
- `ADVAPI32!SetThreadToken` at `0x18008f18a`
- `ADVAPI32!SetThreadToken` at `0x18008f18a`
- `ADVAPI32!RevertToSelf` at `0x18008f1ab`
- `ADVAPI32!RevertToSelf` at `0x18008f1ab`
- `WTSAPI32!WTSQueryUserToken` at `0x18008f126`
- `WTSAPI32!WTSQueryUserToken` at `0x18008f126`

## pseudocode

```c
__int64 __fastcall CommonUtil::CVPNConnectionEnumerator::EnumerateVPNConnectionsForSessionId(
        __int64 a1,
        ULONG a2,
        __int64 a3)
{
  __int64 v4; // rcx
  int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  bool v8; // di
  HANDLE hObject; // [rsp+20h] [rbp-20h] BYREF
  void *phToken; // [rsp+28h] [rbp-18h] BYREF

  phToken = 0;
  hObject = 0;
  if ( WTSQueryUserToken(a2, &phToken)
    && (v5 = CommonUtil::UtilDuplicateToken(&hObject, phToken, SecurityImpersonation, 4u, (unsigned int)hObject), v5 < 0) )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 37;
LABEL_16:
      WPP_SF_d(v6[2], v7, WPP_a134d450411735483d7af4aa7407bce1_Traceguids, (unsigned int)v5);
    }
  }
  else
  {
    v8 = hObject && SetThreadToken(0, hObject);
    v5 = CommonUtil::CVPNConnectionEnumerator::EnumerateVPNConnections(v4, a3);
    if ( v8 )
      RevertToSelf();
    if ( v5 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 38;
        goto LABEL_16;
      }
    }
  }
  if ( hObject )
    CloseHandle(hObject);
  if ( phToken )
    CloseHandle(phToken);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18008f0f0  mov     [rsp-18h+arg_0], rbx
0x18008f0f5  push    rbp
0x18008f0f6  push    rsi
0x18008f0f7  push    rdi
0x18008f0f8  mov     rbp, rsp
0x18008f0fb  sub     rsp, 40h
0x18008f0ff  mov     rax, cs:__security_cookie
0x18008f106  xor     rax, rsp
0x18008f109  mov     [rbp+var_10], rax
0x18008f10d  mov     ecx, edx; SessionId
0x18008f10f  mov     [rbp+phToken], 0
0x18008f117  lea     rdx, [rbp+phToken]; phToken
0x18008f11b  mov     [rbp+hObject], 0
0x18008f123  mov     rsi, r8
0x18008f126  call    cs:__imp_WTSQueryUserToken
0x18008f12c  test    eax, eax
0x18008f12e  jz      short loc_18008F17F
0x18008f130  mov     rcx, [rbp+hObject]; hObject
0x18008f134  mov     rbx, [rbp+phToken]
0x18008f138  test    rcx, rcx
0x18008f13b  jz      short loc_18008F143
0x18008f13d  call    cs:__imp_CloseHandle
0x18008f143  mov     r9d, 4; dwDesiredAccess
0x18008f149  lea     rcx, [rbp+hObject]; phNewToken
0x18008f14d  mov     rdx, rbx; hExistingToken
0x18008f150  lea     r8d, [r9-2]; ImpersonationLevel
0x18008f154  call    ?UtilDuplicateToken@CommonUtil@@YAJPEAPEAXPEAXW4_SECURITY_IMPERSONATION_LEVEL@@K@Z; CommonUtil::UtilDuplicateToken(void * *,void *,_SECURITY_IMPERSONATION_LEVEL,ulong)
0x18008f159  mov     ebx, eax
0x18008f15b  test    eax, eax
0x18008f15d  jns     short loc_18008F17F
0x18008f15f  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f166  lea     rdx, WPP_GLOBAL_Control
0x18008f16d  cmp     rcx, rdx
0x18008f170  jz      short loc_18008F1E6
0x18008f172  test    byte ptr [rcx+1Ch], 1
0x18008f176  jz      short loc_18008F1E6
0x18008f178  mov     edx, 25h ; '%'
0x18008f17d  jmp     short loc_18008F1D3
0x18008f17f  mov     rdx, [rbp+hObject]; Token
0x18008f183  test    rdx, rdx
0x18008f186  jz      short loc_18008F199
0x18008f188  xor     ecx, ecx; Thread
0x18008f18a  call    cs:__imp_SetThreadToken
0x18008f190  test    eax, eax
0x18008f192  jz      short loc_18008F199
0x18008f194  mov     dil, 1
0x18008f197  jmp     short loc_18008F19C
0x18008f199  xor     dil, dil
0x18008f19c  mov     rdx, rsi
0x18008f19f  call    ?EnumerateVPNConnections@CVPNConnectionEnumerator@CommonUtil@@QEBAJAEAV?$vector@VCVPNConnection@CommonUtil@@V?$allocator@VCVPNConnection@CommonUtil@@@std@@@std@@@Z; CommonUtil::CVPNConnectionEnumerator::EnumerateVPNConnections(std::vector<CommonUtil::CVPNConnection> &)
0x18008f1a4  mov     ebx, eax
0x18008f1a6  test    dil, dil
0x18008f1a9  jz      short loc_18008F1B1
0x18008f1ab  call    cs:__imp_RevertToSelf
0x18008f1b1  test    ebx, ebx
0x18008f1b3  jns     short loc_18008F1E6
0x18008f1b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18008f1bc  lea     rdx, WPP_GLOBAL_Control
0x18008f1c3  cmp     rcx, rdx
0x18008f1c6  jz      short loc_18008F1E6
0x18008f1c8  test    byte ptr [rcx+1Ch], 1
0x18008f1cc  jz      short loc_18008F1E6
0x18008f1ce  mov     edx, 26h ; '&'
0x18008f1d3  mov     rcx, [rcx+10h]
0x18008f1d7  lea     r8, WPP_a134d450411735483d7af4aa7407bce1_Traceguids
0x18008f1de  mov     r9d, ebx
0x18008f1e1  call    WPP_SF_d
0x18008f1e6  mov     rcx, [rbp+hObject]; hObject
0x18008f1ea  test    rcx, rcx
0x18008f1ed  jz      short loc_18008F1F5
0x18008f1ef  call    cs:__imp_CloseHandle
0x18008f1f5  mov     rcx, [rbp+phToken]; hObject
0x18008f1f9  test    rcx, rcx
0x18008f1fc  jz      short loc_18008F204
0x18008f1fe  call    cs:__imp_CloseHandle
0x18008f204  mov     eax, ebx
0x18008f206  mov     rcx, [rbp+var_10]
0x18008f20a  xor     rcx, rsp; StackCookie
0x18008f20d  call    __security_check_cookie
0x18008f212  mov     rbx, [rsp+40h+arg_0]
0x18008f217  add     rsp, 40h
0x18008f21b  pop     rdi
0x18008f21c  pop     rsi
0x18008f21d  pop     rbp
0x18008f21e  retn
```
