# NcaRpcAPIsIsAccessGranted

- ea: `0x18001c8e0`
- end: `0x18001c9df`
- name: `NcaRpcAPIsIsAccessGranted`
- size: `255`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, RPC_BINDING_HANDLE BindingHandle, DWORD DesiredAccess, WINBOOL *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b160`
- `0x18001c4e0`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x180018fd4`
- `0x18001bd68`
- `0x18001bec4`
- `0x18001c8e0`

## pseudocode

```c
__int64 __fastcall NcaRpcAPIsIsAccessGranted(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        RPC_BINDING_HANDLE BindingHandle,
        DWORD DesiredAccess,
        WINBOOL *a4)
{
  int AccessTokenFromClientBinding; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  HANDLE ClientToken; // [rsp+20h] [rbp-38h] BYREF

  ClientToken = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids);
  AccessTokenFromClientBinding = NcaRpcAPIsGetAccessTokenFromClientBinding(
                                   BindingHandle,
                                   (__int64)BindingHandle,
                                   &ClientToken);
  v9 = AccessTokenFromClientBinding;
  if ( AccessTokenFromClientBinding >= 0 )
  {
    AccessTokenFromClientBinding = NcaAPIsIsAccessGranted(pSecurityDescriptor, ClientToken, DesiredAccess, a4);
    v9 = AccessTokenFromClientBinding;
    if ( AccessTokenFromClientBinding < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 40;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 39;
LABEL_12:
      WPP_SF_d(v10[2], v11, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids, (unsigned int)AccessTokenFromClientBinding);
    }
  }
  NcaCloseHandle(ClientToken);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18001c8e0  push    rbx
0x18001c8e2  push    rbp
0x18001c8e3  push    rsi
0x18001c8e4  push    rdi
0x18001c8e5  push    r14
0x18001c8e7  sub     rsp, 30h
0x18001c8eb  mov     rdi, r9
0x18001c8ee  mov     [rsp+58h+ClientToken], 0
0x18001c8f7  mov     esi, r8d
0x18001c8fa  mov     rbx, rdx
0x18001c8fd  mov     rbp, rcx
0x18001c900  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c907  lea     r14, WPP_GLOBAL_Control
0x18001c90e  cmp     rcx, r14
0x18001c911  jz      short loc_18001C92E
0x18001c913  test    byte ptr [rcx+1Ch], 8
0x18001c917  jz      short loc_18001C92E
0x18001c919  mov     rcx, [rcx+10h]
0x18001c91d  lea     r8, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids
0x18001c924  mov     edx, 26h ; '&'
0x18001c929  call    WPP_SF_
0x18001c92e  lea     r8, [rsp+58h+ClientToken]
0x18001c933  mov     rcx, rbx; BindingHandle
0x18001c936  call    NcaRpcAPIsGetAccessTokenFromClientBinding
0x18001c93b  mov     ebx, eax
0x18001c93d  test    eax, eax
0x18001c93f  jns     short loc_18001C95A
0x18001c941  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c948  cmp     rcx, r14
0x18001c94b  jz      short loc_18001C99D
0x18001c94d  test    byte ptr [rcx+1Ch], 1
0x18001c951  jz      short loc_18001C99D
0x18001c953  mov     edx, 27h ; '''
0x18001c958  jmp     short loc_18001C98A
0x18001c95a  mov     rdx, [rsp+58h+ClientToken]; ClientToken
0x18001c95f  mov     r9, rdi
0x18001c962  mov     r8d, esi; DesiredAccess
0x18001c965  mov     rcx, rbp; pSecurityDescriptor
0x18001c968  call    NcaAPIsIsAccessGranted
0x18001c96d  mov     ebx, eax
0x18001c96f  test    eax, eax
0x18001c971  jns     short loc_18001C99D
0x18001c973  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c97a  cmp     rcx, r14
0x18001c97d  jz      short loc_18001C99D
0x18001c97f  test    byte ptr [rcx+1Ch], 1
0x18001c983  jz      short loc_18001C99D
0x18001c985  mov     edx, 28h ; '('
0x18001c98a  mov     rcx, [rcx+10h]
0x18001c98e  lea     r8, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids
0x18001c995  mov     r9d, eax
0x18001c998  call    WPP_SF_d
0x18001c99d  mov     rcx, [rsp+58h+ClientToken]
0x18001c9a2  call    NcaCloseHandle
0x18001c9a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c9ae  cmp     rcx, r14
0x18001c9b1  jz      short loc_18001C9D1
0x18001c9b3  test    byte ptr [rcx+1Ch], 8
0x18001c9b7  jz      short loc_18001C9D1
0x18001c9b9  mov     rcx, [rcx+10h]
0x18001c9bd  lea     r8, WPP_9f7a842726f93338d2583c3e545f4309_Traceguids
0x18001c9c4  mov     edx, 29h ; ')'
0x18001c9c9  mov     r9d, ebx
0x18001c9cc  call    WPP_SF_d
0x18001c9d1  mov     eax, ebx
0x18001c9d3  add     rsp, 30h
0x18001c9d7  pop     r14
0x18001c9d9  pop     rdi
0x18001c9da  pop     rsi
0x18001c9db  pop     rbp
0x18001c9dc  pop     rbx
0x18001c9dd  retn
```
