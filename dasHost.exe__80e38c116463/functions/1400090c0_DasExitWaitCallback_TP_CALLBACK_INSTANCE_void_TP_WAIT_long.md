# DasExitWaitCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x1400090c0`
- end: `0x140009155`
- name: `?DasExitWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `149`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, __int64 WaitResult)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140008eec`
- `0x1400090c0`
- `0x140009240`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14000911b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x14000911b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000910e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000910e`

## pseudocode

```c
void __fastcall DasExitWaitCallback(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, __int64 WaitResult)
{
  int v5; // edx
  int v6; // r8d

  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)Context,
      (int)Wait,
      12,
      &WPP_6dd9e3daa83c383c742cfcb4a96fedc2_Traceguids);
  DasHostShutdown(0, Context, Wait, WaitResult);
  CloseHandle(Context);
  CloseThreadpoolWait(g_hDasExitWait);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 5), v5, v6, 13, &WPP_6dd9e3daa83c383c742cfcb4a96fedc2_Traceguids);
}

```

## disassembly

```asm
0x1400090c0  mov     [rsp+arg_0], rbx
0x1400090c5  mov     [rsp+arg_8], rsi
0x1400090ca  push    rdi
0x1400090cb  sub     rsp, 30h
0x1400090cf  mov     rbx, rdx
0x1400090d2  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400090d9  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400090e0  lea     rdi, WPP_6dd9e3daa83c383c742cfcb4a96fedc2_Traceguids
0x1400090e7  jz      short loc_140009104
0x1400090e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400090f0  mov     r9d, 0Ch; int
0x1400090f6  mov     [rsp+38h+MessageGuid], rdi; MessageGuid
0x1400090fb  mov     rcx, [rcx+28h]; int
0x1400090ff  call    WPP_RECORDER_SF_s
0x140009104  xor     ecx, ecx
0x140009106  call    DasHostShutdown
0x14000910b  mov     rcx, rbx; hObject
0x14000910e  call    cs:__imp_CloseHandle
0x140009114  mov     rcx, cs:?g_hDasExitWait@@3PEAU_TP_WAIT@@EA; pwa
0x14000911b  call    cs:__imp_CloseThreadpoolWait
0x140009121  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140009128  jz      short loc_140009145
0x14000912a  mov     rcx, cs:WPP_GLOBAL_Control
0x140009131  mov     r9d, 0Dh; int
0x140009137  mov     [rsp+38h+MessageGuid], rdi; MessageGuid
0x14000913c  mov     rcx, [rcx+28h]; int
0x140009140  call    WPP_RECORDER_SF_s
0x140009145  mov     rbx, [rsp+38h+arg_0]
0x14000914a  mov     rsi, [rsp+38h+arg_8]
0x14000914f  add     rsp, 30h
0x140009153  pop     rdi
0x140009154  retn
```
