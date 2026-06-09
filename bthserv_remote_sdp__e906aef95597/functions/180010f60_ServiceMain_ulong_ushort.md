# ServiceMain(ulong,ushort * *)

- ea: `0x180010f60`
- end: `0x180011264`
- name: `?ServiceMain@@YAXKPEAPEAG@Z`
- size: `772`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callees

- `0x18000270c`
- `0x18000ce48`
- `0x18000e594`
- `0x18000e848`
- `0x18000ed70`
- `0x18000f0e0`
- `0x1800101a4`
- `0x180010f60`
- `0x180012004`
- `0x1800120b8`
- `0x18001268c`
- `0x180014464`
- `0x18001dd58`
- `0x180022a74`
- `0x180032b34`

## import_xrefs

- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001105b`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18001105b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011083`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011083`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800110ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800110ac`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001100e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180011021`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001100e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180011021`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800111f9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800111f9`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2)
{
  char v2; // bl
  bool v3; // dl
  int v4; // edx
  int v5; // edi
  int v6; // r8d
  _QWORD *v7; // rcx
  int v8; // edx
  int v9; // r8d
  unsigned int v10; // [rsp+90h] [rbp+18h] BYREF
  unsigned int v11; // [rsp+98h] [rbp+20h] BYREF

  v11 = 0;
  v10 = 0;
  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  InitializeGlobals();
  if ( Globals )
  {
    memset_0(&g_Policies, 0, 0x50u);
    g_PolicyStorePath = 0;
    InitializeCriticalSection(&g_PolicyLock);
    InitializeCriticalSection(&g_CallbackLock);
    v5 = RtlSubscribeWnfStateChangeNotification(
           &qword_1800472D8,
           WNF_ENTR_BLUETOOTH_POLICY_VALUE_CHANGED,
           0,
           CallbackInternal);
    if ( v5 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      LOBYTE(v4) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)v4 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_26;
    }
    else
    {
      v5 = BthSyncWithPolicyManager();
      if ( v5 >= 0 )
      {
        EnterCriticalSection(&g_CallbackLock);
        g_CallbackContext = 0;
        g_Callback = (void (*)(void *))BthServPoliciesUpdatedCallback;
        LeaveCriticalSection(&g_CallbackLock);
LABEL_26:
        BthServRegister();
        BthServSetState(2u);
        BthServInit();
        BthServRadioInterfaceWatcher::Start((BthServRadioInterfaceWatcher *)qword_180046FF0);
        BthServStartRPC();
        BthServSetState(4u);
        if ( v5 >= 0 )
          BthServPushPolicies();
        DafBthSynchronize(&v11, &v10);
        LOBYTE(v8) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
        if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sdd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v8,
            v9,
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            0);
        }
        WaitForSingleObjectEx(Globals, 0xFFFFFFFF, 0);
        BthServStop();
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
          v2 = 0;
        if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v2,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            *((_QWORD *)WPP_GLOBAL_Control + 5));
        return;
      }
      v7 = WPP_GLOBAL_Control;
      LOBYTE(v4) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !(_BYTE)v4 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_26;
    }
    WPP_RECORDER_AND_TRACE_SF_sD(v7[2], v4, v6, v7[5]);
    goto LABEL_26;
  }
}

```

## disassembly

```asm
0x180010f60  mov     rax, rsp
0x180010f63  mov     [rax+8], rbx
0x180010f67  mov     [rax+10h], rbp
0x180010f6b  push    rdi
0x180010f6c  push    r12
0x180010f6e  push    r14
0x180010f70  sub     rsp, 60h
0x180010f74  and     dword ptr [rax+20h], 0
0x180010f78  and     dword ptr [rax+18h], 0
0x180010f7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010f83  lea     rbp, WPP_GLOBAL_Control
0x180010f8a  mov     bl, 1
0x180010f8c  cmp     rcx, rbp
0x180010f8f  jz      short loc_180010F9B
0x180010f91  cmp     byte ptr [rcx+19h], 5
0x180010f95  jb      short loc_180010F9B
0x180010f97  mov     dl, bl
0x180010f99  jmp     short loc_180010F9D
0x180010f9b  xor     dl, dl
0x180010f9d  lea     r14, WPP_RECORDER_INITIALIZED
0x180010fa4  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180010fab  lea     r12, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x180010fb2  setnz   r8b
0x180010fb6  test    dl, dl
0x180010fb8  jnz     short loc_180010FBF
0x180010fba  test    r8b, r8b
0x180010fbd  jz      short loc_180010FD8
0x180010fbf  mov     r9, [rcx+28h]
0x180010fc3  mov     rcx, [rcx+10h]
0x180010fc7  mov     [rsp+78h+var_40], r12
0x180010fcc  mov     word ptr [rsp+78h+var_48], 1Ah
0x180010fd3  call    WPP_RECORDER_AND_TRACE_SF_s
0x180010fd8  call    ?InitializeGlobals@@YAXXZ; InitializeGlobals(void)
0x180010fdd  cmp     cs:?Globals@@3VBthServGlobals@@A, 0; BthServGlobals Globals
0x180010fe5  jz      loc_18001124D
0x180010feb  xor     edx, edx; Val
0x180010fed  lea     rcx, ?g_Policies@@3UPolicies@@A; void *
0x180010ff4  lea     r8d, [rdx+50h]; Size
0x180010ff8  call    memset_0
0x180010ffd  xorps   xmm0, xmm0
0x180011000  lea     rcx, ?g_PolicyLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180011007  movups  xmmword ptr cs:?g_PolicyStorePath@@3U_UNICODE_STRING@@A, xmm0; _UNICODE_STRING g_PolicyStorePath
0x18001100e  call    cs:__imp_InitializeCriticalSection
0x180011015  nop     dword ptr [rax+rax+00h]
0x18001101a  lea     rcx, ?g_CallbackLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180011021  call    cs:__imp_InitializeCriticalSection
0x180011028  nop     dword ptr [rax+rax+00h]
0x18001102d  and     dword ptr [rsp+78h+var_40], 0
0x180011032  lea     r9, ?CallbackInternal@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CallbackInternal(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180011039  and     [rsp+78h+var_48], 0
0x18001103e  lea     rcx, qword_1800472D8
0x180011045  and     [rsp+78h+var_50], 0
0x18001104b  xor     r8d, r8d
0x18001104e  mov     rdx, cs:WNF_ENTR_BLUETOOTH_POLICY_VALUE_CHANGED
0x180011055  and     [rsp+78h+var_58], 0
0x18001105b  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180011062  nop     dword ptr [rax+rax+00h]
0x180011067  mov     edi, eax
0x180011069  test    eax, eax
0x18001106b  js      loc_1800110FB
0x180011071  call    BthSyncWithPolicyManager
0x180011076  mov     edi, eax
0x180011078  test    eax, eax
0x18001107a  js      short loc_1800110BD
0x18001107c  lea     rcx, ?g_CallbackLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180011083  call    cs:__imp_EnterCriticalSection
0x18001108a  nop     dword ptr [rax+rax+00h]
0x18001108f  and     cs:?g_CallbackContext@@3PEAXEA, 0; void * g_CallbackContext
0x180011097  lea     rax, ?BthServPoliciesUpdatedCallback@@YAXPEAX@Z; BthServPoliciesUpdatedCallback(void *)
0x18001109e  lea     rcx, ?g_CallbackLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800110a5  mov     cs:?g_Callback@@3P6AXPEAX@ZEA, rax; void (*g_Callback)(void *)
0x1800110ac  call    cs:__imp_LeaveCriticalSection
0x1800110b3  nop     dword ptr [rax+rax+00h]
0x1800110b8  jmp     loc_180011144
0x1800110bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110c4  cmp     rcx, rbp
0x1800110c7  jz      short loc_1800110D3
0x1800110c9  cmp     byte ptr [rcx+19h], 2
0x1800110cd  jb      short loc_1800110D3
0x1800110cf  mov     dl, bl
0x1800110d1  jmp     short loc_1800110D5
0x1800110d3  xor     dl, dl
0x1800110d5  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800110dc  setnz   r8b
0x1800110e0  test    dl, dl
0x1800110e2  jnz     short loc_1800110E9
0x1800110e4  test    r8b, r8b
0x1800110e7  jz      short loc_180011144
0x1800110e9  mov     [rsp+78h+var_30], eax
0x1800110ed  mov     [rsp+78h+var_40], r12
0x1800110f2  mov     word ptr [rsp+78h+var_48], 1Bh
0x1800110f9  jmp     short loc_180011137
0x1800110fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180011102  cmp     rcx, rbp
0x180011105  jz      short loc_180011111
0x180011107  cmp     byte ptr [rcx+19h], 2
0x18001110b  jb      short loc_180011111
0x18001110d  mov     dl, bl
0x18001110f  jmp     short loc_180011113
0x180011111  xor     dl, dl
0x180011113  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18001111a  setnz   r8b
0x18001111e  test    dl, dl
0x180011120  jnz     short loc_180011127
0x180011122  test    r8b, r8b
0x180011125  jz      short loc_180011144
0x180011127  mov     [rsp+78h+var_30], eax
0x18001112b  mov     [rsp+78h+var_40], r12
0x180011130  mov     word ptr [rsp+78h+var_48], 1Ch
0x180011137  mov     r9, [rcx+28h]
0x18001113b  mov     rcx, [rcx+10h]
0x18001113f  call    WPP_RECORDER_AND_TRACE_SF_sD
0x180011144  call    ?BthServRegister@@YAXXZ; BthServRegister(void)
0x180011149  mov     ecx, 2; unsigned int
0x18001114e  call    ?BthServSetState@@YAHK@Z; BthServSetState(ulong)
0x180011153  call    ?BthServInit@@YAHXZ; BthServInit(void)
0x180011158  lea     rcx, qword_180046FF0; this
0x18001115f  call    ?Start@BthServRadioInterfaceWatcher@@QEAAXXZ; BthServRadioInterfaceWatcher::Start(void)
0x180011164  call    ?BthServStartRPC@@YAKXZ; BthServStartRPC(void)
0x180011169  mov     ecx, 4; unsigned int
0x18001116e  call    ?BthServSetState@@YAHK@Z; BthServSetState(ulong)
0x180011173  test    edi, edi
0x180011175  js      short loc_18001117C
0x180011177  call    ?BthServPushPolicies@@YAXXZ; BthServPushPolicies(void)
0x18001117c  lea     rdx, [rsp+78h+arg_10]; unsigned int *
0x180011184  lea     rcx, [rsp+78h+arg_18]; unsigned int *
0x18001118c  call    ?DafBthSynchronize@@YAJPEAK0@Z; DafBthSynchronize(ulong *,ulong *)
0x180011191  mov     rcx, cs:WPP_GLOBAL_Control
0x180011198  cmp     rcx, rbp
0x18001119b  jz      short loc_1800111A7
0x18001119d  cmp     byte ptr [rcx+19h], 4
0x1800111a1  jb      short loc_1800111A7
0x1800111a3  mov     dl, bl
0x1800111a5  jmp     short loc_1800111A9
0x1800111a7  xor     dl, dl
0x1800111a9  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800111b0  setnz   r8b
0x1800111b4  test    dl, dl
0x1800111b6  jnz     short loc_1800111BD
0x1800111b8  test    r8b, r8b
0x1800111bb  jz      short loc_1800111EC
0x1800111bd  mov     eax, [rsp+78h+arg_10]
0x1800111c4  mov     r9, [rcx+28h]
0x1800111c8  mov     rcx, [rcx+10h]
0x1800111cc  mov     [rsp+78h+var_28], eax
0x1800111d0  mov     eax, [rsp+78h+arg_18]
0x1800111d7  mov     [rsp+78h+var_30], eax
0x1800111db  mov     [rsp+78h+var_40], r12
0x1800111e0  mov     word ptr [rsp+78h+var_48], 1Dh
0x1800111e7  call    WPP_RECORDER_AND_TRACE_SF_sdd
0x1800111ec  mov     rcx, cs:?Globals@@3VBthServGlobals@@A; hHandle
0x1800111f3  xor     r8d, r8d; bAlertable
0x1800111f6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800111f9  call    cs:__imp_WaitForSingleObjectEx
0x180011200  nop     dword ptr [rax+rax+00h]
0x180011205  call    ?BthServStop@@YAXXZ; BthServStop(void)
0x18001120a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011211  cmp     rcx, rbp
0x180011214  jz      short loc_18001121C
0x180011216  cmp     byte ptr [rcx+19h], 5
0x18001121a  jnb     short loc_18001121E
0x18001121c  xor     bl, bl
0x18001121e  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180011225  setnz   r8b
0x180011229  test    bl, bl
0x18001122b  jnz     short loc_180011232
0x18001122d  test    r8b, r8b
0x180011230  jz      short loc_18001124D
0x180011232  mov     r9, [rcx+28h]
0x180011236  mov     dl, bl
0x180011238  mov     rcx, [rcx+10h]
0x18001123c  mov     [rsp+78h+var_40], r12
0x180011241  mov     word ptr [rsp+78h+var_48], 1Eh
0x180011248  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001124d  lea     r11, [rsp+78h+var_18]
0x180011252  mov     rbx, [r11+20h]
0x180011256  mov     rbp, [r11+28h]
0x18001125a  mov     rsp, r11
0x18001125d  pop     r14
0x18001125f  pop     r12
0x180011261  pop     rdi
0x180011262  retn
```
