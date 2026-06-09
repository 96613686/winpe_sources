# DestroyChallengeServices(void)

- ea: `0x180049ecc`
- end: `0x18004a04a`
- name: `?DestroyChallengeServices@@YAXXZ`
- size: `382`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180049330`

## callees

- `0x180007500`
- `0x18002d764`
- `0x180033f14`
- `0x1800471cc`
- `0x180049cb8`
- `0x180049d18`
- `0x180049ecc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049f0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049f26`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049f0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049f26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049f1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049fc5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049f1d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180049fc5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004a00b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004a00b`

## pseudocode

```c
void DestroyChallengeServices(void)
{
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v1; // rcx
  int v2; // eax
  int v3; // edx
  int v4; // r8d
  int v5; // eax
  int v6; // edx
  int v7; // r8d
  _QWORD v8[2]; // [rsp+40h] [rbp-30h] BYREF
  void *v9[4]; // [rsp+50h] [rbp-20h] BYREF
  struct _LIST_ENTRY *v10; // [rsp+90h] [rbp+20h] BYREF
  void **v11; // [rsp+98h] [rbp+28h] BYREF

  std::vector<std::wstring>::vector<std::wstring>(v9);
  v10 = 0;
  if ( g_bChallengeListInitialized )
  {
    EnterCriticalSection(&g_csChallengeList);
    g_bChallengeSubsystemStopping = 1;
    LeaveCriticalSection(&g_csChallengeList);
    EnterCriticalSection(&g_csChallengeList);
    while ( 1 )
    {
      Flink = g_ChallengeList.Flink;
      if ( g_ChallengeList.Flink == &g_ChallengeList )
        break;
      if ( g_ChallengeList.Flink->Blink != &g_ChallengeList
        || (v1 = g_ChallengeList.Flink->Flink, g_ChallengeList.Flink->Flink->Blink != g_ChallengeList.Flink) )
      {
        __fastfail(3u);
      }
      g_ChallengeList.Flink = g_ChallengeList.Flink->Flink;
      v1->Blink = &g_ChallengeList;
      v10 = Flink;
      v8[0] = v9;
      v8[1] = &v10;
      v2 = wil::ResultFromException__lambda_dc4ad1ac3f976f071df7be86e8dbe9ae___(v8);
      if ( v2 < 0 && *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_Dq(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v3,
          v4,
          10,
          &WPP_81de2895065d361e58f8368cb287efef_Traceguids,
          v2,
          (char)v10);
    }
    LeaveCriticalSection(&g_csChallengeList);
    v11 = v9;
    v5 = wil::ResultFromException__lambda_0039052c59ea6021c1ec2b03b16f4c3d___(&v11);
    if ( v5 < 0 && *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v6,
        v7,
        11,
        &WPP_81de2895065d361e58f8368cb287efef_Traceguids,
        v5);
    DeleteCriticalSection(&g_csChallengeList);
    g_bChallengeListInitialized = 0;
  }
  if ( v9[0] )
    std::_Deallocate<16>(v9[0], ((char *)v9[2] - (char *)v9[0]) & 0xFFFFFFFFFFFFFFF8uLL);
}

```

## disassembly

```asm
0x180049ecc  mov     [rsp-18h+arg_10], rsi
0x180049ed1  mov     [rsp-18h+arg_18], rdi
0x180049ed6  push    rbp
0x180049ed7  push    r14
0x180049ed9  push    r15
0x180049edb  mov     rbp, rsp
0x180049ede  sub     rsp, 70h
0x180049ee2  lea     rcx, [rbp+var_20]
0x180049ee6  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::vector<std::wstring>(void)
0x180049eeb  cmp     cs:?g_bChallengeListInitialized@@3HA, 0; int g_bChallengeListInitialized
0x180049ef2  mov     [rbp+arg_0], 0
0x180049efa  jz      loc_18004A01B
0x180049f00  lea     rdi, ?g_csChallengeList@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csChallengeList
0x180049f07  mov     rcx, rdi; lpCriticalSection
0x180049f0a  call    cs:__imp_EnterCriticalSection
0x180049f10  mov     rcx, rdi; lpCriticalSection
0x180049f13  mov     cs:?g_bChallengeSubsystemStopping@@3HA, 1; int g_bChallengeSubsystemStopping
0x180049f1d  call    cs:__imp_LeaveCriticalSection
0x180049f23  mov     rcx, rdi; lpCriticalSection
0x180049f26  call    cs:__imp_EnterCriticalSection
0x180049f2c  lea     rsi, ?g_ChallengeList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ChallengeList
0x180049f33  lea     r14, WPP_RECORDER_INITIALIZED
0x180049f3a  lea     r15, WPP_81de2895065d361e58f8368cb287efef_Traceguids
0x180049f41  mov     rax, cs:?g_ChallengeList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_ChallengeList
0x180049f48  cmp     rax, rsi
0x180049f4b  jz      short loc_180049FC2
0x180049f4d  cmp     [rax+8], rsi
0x180049f51  jnz     short loc_180049FBB
0x180049f53  mov     rcx, [rax]
0x180049f56  cmp     [rcx+8], rax
0x180049f5a  jnz     short loc_180049FBB
0x180049f5c  mov     cs:?g_ChallengeList@@3U_LIST_ENTRY@@A, rcx; _LIST_ENTRY g_ChallengeList
0x180049f63  mov     [rcx+8], rsi
0x180049f67  lea     rcx, [rbp+var_30]
0x180049f6b  mov     [rbp+arg_0], rax
0x180049f6f  lea     rax, [rbp+var_20]
0x180049f73  mov     [rbp+var_30], rax
0x180049f77  lea     rax, [rbp+arg_0]
0x180049f7b  mov     [rbp+var_28], rax
0x180049f7f  call    wil__ResultFromException__lambda_dc4ad1ac3f976f071df7be86e8dbe9ae___
0x180049f84  test    eax, eax
0x180049f86  jns     short loc_180049F41
0x180049f88  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180049f8f  jz      short loc_180049F41
0x180049f91  mov     rcx, [rbp+arg_0]
0x180049f95  mov     r9d, 0Ah; int
0x180049f9b  mov     qword ptr [rsp+70h+var_40], rcx; char
0x180049fa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180049fa7  mov     dword ptr [rsp+70h+var_48], eax; char
0x180049fab  mov     [rsp+70h+MessageGuid], r15; MessageGuid
0x180049fb0  mov     rcx, [rcx+28h]; int
0x180049fb4  call    WPP_RECORDER_SF_Dq
0x180049fb9  jmp     short loc_180049F41
0x180049fbb  mov     ecx, 3
0x180049fc0  int     29h; Win8: RtlFailFast(ecx)
0x180049fc2  mov     rcx, rdi; lpCriticalSection
0x180049fc5  call    cs:__imp_LeaveCriticalSection
0x180049fcb  lea     rax, [rbp+var_20]
0x180049fcf  lea     rcx, [rbp+arg_8]
0x180049fd3  mov     [rbp+arg_8], rax
0x180049fd7  call    wil__ResultFromException__lambda_0039052c59ea6021c1ec2b03b16f4c3d___
0x180049fdc  test    eax, eax
0x180049fde  jns     short loc_18004A008
0x180049fe0  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180049fe7  jz      short loc_18004A008
0x180049fe9  mov     rcx, cs:WPP_GLOBAL_Control
0x180049ff0  mov     r9d, 0Bh; int
0x180049ff6  mov     dword ptr [rsp+70h+var_48], eax; char
0x180049ffa  mov     [rsp+70h+MessageGuid], r15; MessageGuid
0x180049fff  mov     rcx, [rcx+28h]; int
0x18004a003  call    WPP_RECORDER_SF_D
0x18004a008  mov     rcx, rdi; lpCriticalSection
0x18004a00b  call    cs:__imp_DeleteCriticalSection
0x18004a011  mov     cs:?g_bChallengeListInitialized@@3HA, 0; int g_bChallengeListInitialized
0x18004a01b  mov     rcx, [rbp+var_20]
0x18004a01f  test    rcx, rcx
0x18004a022  jz      short loc_18004A034
0x18004a024  mov     rdx, [rbp+var_10]
0x18004a028  sub     rdx, rcx
0x18004a02b  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18004a02f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18004a034  lea     r11, [rsp+70h+var_s0]
0x18004a039  mov     rsi, [r11+30h]
0x18004a03d  mov     rdi, [r11+38h]
0x18004a041  mov     rsp, r11
0x18004a044  pop     r15
0x18004a046  pop     r14
0x18004a048  pop     rbp
0x18004a049  retn
```
