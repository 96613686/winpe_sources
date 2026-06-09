# StartManagementTimer::TimerCallback(void)

- ea: `0x18000faa0`
- end: `0x18000fbc1`
- name: `?TimerCallback@StartManagementTimer@@QEAAXXZ`
- size: `289`
- prototype: `void __fastcall(StartManagementTimer *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000f9d0`

## callees

- `0x18000c308`
- `0x18000c348`
- `0x18000e5a4`
- `0x18000f3ec`
- `0x18000faa0`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fb4b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fbb0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fb4b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fbb0`

## pseudocode

```c
void __fastcall StartManagementTimer::TimerCallback(StartManagementTimer *this)
{
  int IsDeviceReady; // eax
  _QWORD *v3; // rcx
  int started; // r8d
  bool v5; // [rsp+40h] [rbp+8h] BYREF

  ++*((_DWORD *)this + 2);
  v5 = 0;
  IsDeviceReady = CWiGigDAFProviderDevnodeManagement::IsDeviceReady(
                    *((CWiGigDAFProviderDevnodeManagement **)this + 3),
                    &v5);
  if ( IsDeviceReady >= 0 )
    goto LABEL_6;
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids,
      this,
      IsDeviceReady);
LABEL_6:
    v3 = WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    if ( v3 != &WPP_GLOBAL_Control && *((_BYTE *)v3 + 25) >= 3u && (*((_BYTE *)v3 + 28) & 1) != 0 )
      WPP_SF_qD(v3[2], 11, &WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids, this, *((_DWORD *)this + 2));
    SetThreadpoolTimer(*(PTP_TIMER *)this, 0, 0, 0);
    started = CWiGigDAFProviderDevnodeManagement::StartManagement(*((CWiGigDAFProviderDevnodeManagement **)this + 3));
    if ( started < 0 )
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 2) + 24LL))(
        *((_QWORD *)this + 2),
        (unsigned int)started);
  }
  else if ( *((_DWORD *)this + 2) == 30 )
  {
    if ( v3 != &WPP_GLOBAL_Control && *((_BYTE *)v3 + 25) && (*((_BYTE *)v3 + 28) & 1) != 0 )
      WPP_SF_q(v3[2], 12, &WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids, this);
    SetThreadpoolTimer(*(PTP_TIMER *)this, 0, 0, 0);
  }
}

```

## disassembly

```asm
0x18000faa0  mov     [rsp+arg_8], rbx
0x18000faa5  push    rsi
0x18000faa6  sub     rsp, 30h
0x18000faaa  inc     dword ptr [rcx+8]
0x18000faad  lea     rdx, [rsp+38h+arg_0]; bool *
0x18000fab2  mov     rbx, rcx
0x18000fab5  mov     [rsp+38h+arg_0], 0
0x18000faba  mov     rcx, [rcx+18h]; this
0x18000fabe  call    ?IsDeviceReady@CWiGigDAFProviderDevnodeManagement@@QEAAJPEA_N@Z; CWiGigDAFProviderDevnodeManagement::IsDeviceReady(bool *)
0x18000fac3  lea     rsi, WPP_GLOBAL_Control
0x18000faca  test    eax, eax
0x18000facc  jns     short loc_18000FB02
0x18000face  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fad5  cmp     rcx, rsi
0x18000fad8  jz      short loc_18000FB09
0x18000fada  cmp     byte ptr [rcx+19h], 1
0x18000fade  jb      short loc_18000FB09
0x18000fae0  test    byte ptr [rcx+1Ch], 1
0x18000fae4  jz      short loc_18000FB09
0x18000fae6  mov     rcx, [rcx+10h]
0x18000faea  lea     r8, WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids
0x18000faf1  mov     edx, 0Ah
0x18000faf6  mov     [rsp+38h+var_18], eax
0x18000fafa  mov     r9, rbx
0x18000fafd  call    WPP_SF_qD
0x18000fb02  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb09  cmp     [rsp+38h+arg_0], 0
0x18000fb0e  jz      short loc_18000FB76
0x18000fb10  cmp     rcx, rsi
0x18000fb13  jz      short loc_18000FB40
0x18000fb15  cmp     byte ptr [rcx+19h], 3
0x18000fb19  jb      short loc_18000FB40
0x18000fb1b  test    byte ptr [rcx+1Ch], 1
0x18000fb1f  jz      short loc_18000FB40
0x18000fb21  mov     eax, [rbx+8]
0x18000fb24  lea     r8, WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids
0x18000fb2b  mov     rcx, [rcx+10h]
0x18000fb2f  mov     edx, 0Bh
0x18000fb34  mov     r9, rbx
0x18000fb37  mov     [rsp+38h+var_18], eax
0x18000fb3b  call    WPP_SF_qD
0x18000fb40  mov     rcx, [rbx]; pti
0x18000fb43  xor     r9d, r9d; msWindowLength
0x18000fb46  xor     r8d, r8d; msPeriod
0x18000fb49  xor     edx, edx; pftDueTime
0x18000fb4b  call    cs:__imp_SetThreadpoolTimer
0x18000fb51  mov     rcx, [rbx+18h]; this
0x18000fb55  call    ?StartManagement@CWiGigDAFProviderDevnodeManagement@@QEAAJXZ; CWiGigDAFProviderDevnodeManagement::StartManagement(void)
0x18000fb5a  mov     r8d, eax
0x18000fb5d  test    eax, eax
0x18000fb5f  jns     short loc_18000FBB6
0x18000fb61  mov     rcx, [rbx+10h]
0x18000fb65  mov     rdx, [rcx]
0x18000fb68  mov     rax, [rdx+18h]
0x18000fb6c  mov     edx, r8d
0x18000fb6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb74  jmp     short loc_18000FBB6
0x18000fb76  cmp     dword ptr [rbx+8], 1Eh
0x18000fb7a  jnz     short loc_18000FBB6
0x18000fb7c  cmp     rcx, rsi
0x18000fb7f  jz      short loc_18000FBA5
0x18000fb81  cmp     byte ptr [rcx+19h], 1
0x18000fb85  jb      short loc_18000FBA5
0x18000fb87  test    byte ptr [rcx+1Ch], 1
0x18000fb8b  jz      short loc_18000FBA5
0x18000fb8d  mov     rcx, [rcx+10h]
0x18000fb91  lea     r8, WPP_1e392510015231dbb7e523a39e1e58fb_Traceguids
0x18000fb98  mov     edx, 0Ch
0x18000fb9d  mov     r9, rbx
0x18000fba0  call    WPP_SF_q
0x18000fba5  mov     rcx, [rbx]; pti
0x18000fba8  xor     r9d, r9d; msWindowLength
0x18000fbab  xor     r8d, r8d; msPeriod
0x18000fbae  xor     edx, edx; pftDueTime
0x18000fbb0  call    cs:__imp_SetThreadpoolTimer
0x18000fbb6  mov     rbx, [rsp+38h+arg_8]
0x18000fbbb  add     rsp, 30h
0x18000fbbf  pop     rsi
0x18000fbc0  retn
```
