# GetClientPrivilege(void *)

- ea: `0x180008670`
- end: `0x18000878c`
- name: `?GetClientPrivilege@@YAKPEAX@Z`
- size: `284`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180010f80`

## callees

- `0x180008670`
- `0x18001ad48`
- `0x18001ae3c`
- `0x180022e58`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800086c5`
- `RPCRT4!RpcImpersonateClient` at `0x1800086c5`
- `RPCRT4!RpcRevertToSelfEx` at `0x180008713`
- `RPCRT4!RpcRevertToSelfEx` at `0x180008713`

## string_xrefs

- `0x1800086af`: `GetClientPrivilege`
- `0x180008761`: `GetClientPrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetClientPrivilege(RPC_BINDING_HANDLE BindingHandle)
{
  unsigned int v2; // ebx
  PVOID *v3; // rcx
  WINBOOL IsMember; // [rsp+38h] [rbp+10h] BYREF

  IsMember = 0;
  v2 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      85,
      &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids,
      L"GetClientPrivilege");
  if ( !RpcImpersonateClient(BindingHandle) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids);
    IsAdmin(&IsMember);
    v2 = (IsMember != 0) + 1;
    RpcRevertToSelfEx(BindingHandle);
    goto LABEL_12;
  }
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v2;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids);
LABEL_12:
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 7) & 0x1000) != 0 )
    WPP_SF_S(v3[2], 88, &WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids, L"GetClientPrivilege");
  return v2;
}

```

## disassembly

```asm
0x180008670  mov     [rsp+arg_0], rbx
0x180008675  mov     [rsp+arg_10], rsi
0x18000867a  push    rdi
0x18000867b  sub     rsp, 20h
0x18000867f  and     [rsp+28h+IsMember], 0
0x180008684  mov     rdi, rcx
0x180008687  mov     ebx, 1
0x18000868c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008693  lea     rsi, WPP_GLOBAL_Control
0x18000869a  cmp     rcx, rsi
0x18000869d  jz      short loc_1800086C2
0x18000869f  test    dword ptr [rcx+1Ch], 1000h
0x1800086a6  jz      short loc_1800086C2
0x1800086a8  mov     rcx, [rcx+10h]
0x1800086ac  lea     edx, [rbx+54h]
0x1800086af  lea     r9, aGetclientprivi; "GetClientPrivilege"
0x1800086b6  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x1800086bd  call    WPP_SF_S
0x1800086c2  mov     rcx, rdi; BindingHandle
0x1800086c5  call    cs:__imp_RpcImpersonateClient
0x1800086cc  nop     dword ptr [rax+rax+00h]
0x1800086d1  test    eax, eax
0x1800086d3  jnz     short loc_180008721
0x1800086d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086dc  cmp     rcx, rsi
0x1800086df  jz      short loc_1800086FA
0x1800086e1  test    byte ptr [rcx+1Ch], 20h
0x1800086e5  jz      short loc_1800086FA
0x1800086e7  mov     rcx, [rcx+10h]
0x1800086eb  lea     edx, [rax+56h]
0x1800086ee  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x1800086f5  call    WPP_SF_
0x1800086fa  lea     rcx, [rsp+28h+IsMember]; IsMember
0x1800086ff  call    IsAdmin
0x180008704  mov     eax, [rsp+28h+IsMember]
0x180008708  neg     eax
0x18000870a  sbb     ecx, ecx
0x18000870c  neg     ecx
0x18000870e  add     ebx, ecx
0x180008710  mov     rcx, rdi; BindingHandle
0x180008713  call    cs:__imp_RpcRevertToSelfEx
0x18000871a  nop     dword ptr [rax+rax+00h]
0x18000871f  jmp     short loc_180008748
0x180008721  mov     rcx, cs:WPP_GLOBAL_Control
0x180008728  cmp     rcx, rsi
0x18000872b  jz      short loc_180008779
0x18000872d  test    byte ptr [rcx+1Ch], 20h
0x180008731  jz      short loc_18000874F
0x180008733  mov     rcx, [rcx+10h]
0x180008737  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x18000873e  mov     edx, 57h ; 'W'
0x180008743  call    WPP_SF_
0x180008748  mov     rcx, cs:WPP_GLOBAL_Control
0x18000874f  cmp     rcx, rsi
0x180008752  jz      short loc_180008779
0x180008754  test    dword ptr [rcx+1Ch], 1000h
0x18000875b  jz      short loc_180008779
0x18000875d  mov     rcx, [rcx+10h]
0x180008761  lea     r9, aGetclientprivi; "GetClientPrivilege"
0x180008768  mov     edx, 58h ; 'X'
0x18000876d  lea     r8, WPP_14f402b3e7783efa9cd4a35c63de2b16_Traceguids
0x180008774  call    WPP_SF_S
0x180008779  mov     rsi, [rsp+28h+arg_10]
0x18000877e  mov     eax, ebx
0x180008780  mov     rbx, [rsp+28h+arg_0]
0x180008785  add     rsp, 20h
0x180008789  pop     rdi
0x18000878a  retn
```
