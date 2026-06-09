# FwPlumber::CreateCallouts

- ea: `0x180068ff4`
- end: `0x180069239`
- name: `FwPlumber::CreateCallouts`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180068860`

## callees

- `0x1800093b0`
- `0x180017110`
- `0x180021584`
- `0x180068dec`
- `0x180068ff4`
- `0x18006f520`
- `0x18006ffc8`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800690b8`
- `ntdll!EtwEventWrite` at `0x1800690f9`
- `ntdll!EtwEventWrite` at `0x1800691ea`
- `ntdll!EtwEventWrite` at `0x180069214`
- `ntdll!EtwEventWrite` at `0x1800690b8`
- `ntdll!EtwEventWrite` at `0x1800690f9`
- `ntdll!EtwEventWrite` at `0x1800691ea`
- `ntdll!EtwEventWrite` at `0x180069214`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800690d8`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800690d8`
- `fwpuclnt!FwpmEngineClose0` at `0x1800691f5`
- `fwpuclnt!FwpmEngineClose0` at `0x1800691f5`
- `fwpuclnt!FwpmCalloutAdd0` at `0x180069196`
- `fwpuclnt!FwpmCalloutAdd0` at `0x180069196`

## pseudocode

```c
DWORD FwPlumber::CreateCallouts()
{
  unsigned int v0; // edx
  DWORD v1; // ebx
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rsi
  __int64 v7; // rdx
  GUID **v8; // rax
  __int64 v9; // rdx
  DWORD v10; // eax
  DWORD v11; // edi
  unsigned int v12; // edx
  DWORD result; // eax
  HANDLE engineHandle; // [rsp+30h] [rbp-A8h] BYREF
  FWPM_CALLOUT0 callout; // [rsp+40h] [rbp-98h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 108, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids);
  engineHandle = 0;
  memset_0(&callout.calloutKey.Data2, 0, 0x54u);
  callout.displayData.name = L"Windows Firewall: callout";
  callout.providerKey = (GUID *)qword_18012BB10;
  *(_QWORD *)&callout.calloutKey.Data1 = *(_QWORD *)&FW_PLUMBER_CALLOUT_KEY.Data1;
  *(_DWORD *)callout.calloutKey.Data4 = *(_DWORD *)FW_PLUMBER_CALLOUT_KEY.Data4;
  *(_WORD *)&callout.calloutKey.Data4[4] = *(_WORD *)&FW_PLUMBER_CALLOUT_KEY.Data4[4];
  *(_WORD *)&callout.calloutKey.Data4[6] = 0;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_BFE_EngineOpen_Enter, 0, 0);
  v1 = FwpmEngineOpen0(0, 0xAu, 0, &stru_1800F3D20, &engineHandle);
  v4 = g_Provider;
  if ( g_Provider )
  {
    EtwEventWrite(g_Provider, MPS_SVC_BFE_EngineOpen_Exit, 0, 0);
    v4 = g_Provider;
  }
  if ( v1 )
    FwPlumber::ThrowWin32((FwPlumber *)v1, v0);
  v5 = 0;
  while ( (unsigned int)v5 < 5 )
  {
    callout.calloutKey.Data4[6] = v5;
    callout.displayData.description = *(wchar_t **)((char *)&qword_1800E70F0[3] + 36 * v5 + 4);
    v6 = 0;
    try
    {
      while ( 1 )
      {
        v7 = *(__int64 *)((char *)&qword_1800E70F0[2] + 36 * v5 + 4);
        v8 = *(GUID ***)(v7 + 12 * v6);
        if ( !v8 )
          break;
        callout.applicableLayer = **v8;
        if ( *(_WORD *)(*(_QWORD *)(v7 + 12 * v6) + 8LL) > 0xFFu )
          MicrosoftTelemetryAssertTriggeredNoArgs(255, v7, v2, v3);
        v9 = *(__int64 *)((char *)&qword_1800E70F0[2] + 36 * v5 + 4);
        callout.calloutKey.Data4[7] = *(_BYTE *)(*(_QWORD *)(v9 + 12 * v6) + 8LL);
        v10 = FwpmCalloutAdd0(engineHandle, &callout, 0, (UINT32 *)(v9 + 8 + 12 * v6));
        v11 = v10;
        if ( v10 != -2144206839 )
        {
          FwPlumberTrackObjError(
            v10,
            callout.displayData.name,
            (struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)&g_FwCalloutError);
          if ( v11 )
            FwPlumber::ThrowWin32((FwPlumber *)v11, v12);
        }
        v6 = (unsigned int)(v6 + 1);
        v4 = g_Provider;
      }
      v5 = (unsigned int)(v5 + 1);
    }
    catch ( FwPlumber::Exception )
    {
      if ( g_Provider )
        EtwEventWrite(g_Provider, MPS_SVC_BFE_EngineClose_Enter, 0, 0);
      FwpmEngineClose0(engineHandle);
      if ( g_Provider )
        EtwEventWrite(g_Provider, MPS_SVC_BFE_EngineClose_Exit, 0, 0);
      throw;
    }
  }
  if ( v4 )
    EtwEventWrite(v4, MPS_SVC_BFE_EngineClose_Enter, 0, 0);
  result = FwpmEngineClose0(engineHandle);
  if ( g_Provider )
    return EtwEventWrite(g_Provider, MPS_SVC_BFE_EngineClose_Exit, 0, 0);
  return result;
}

```

## disassembly

```asm
0x180068ff4  push    rbx
0x180068ff6  push    rsi
0x180068ff7  push    rdi
0x180068ff8  push    r12
0x180068ffa  push    r14
0x180068ffc  sub     rsp, 0B0h
0x180069003  mov     rax, cs:__security_cookie
0x18006900a  xor     rax, rsp
0x18006900d  mov     [rsp+0D8h+var_38], rax
0x180069015  lea     rax, WPP_GLOBAL_Control
0x18006901c  mov     rcx, cs:WPP_GLOBAL_Control
0x180069023  cmp     rcx, rax
0x180069026  jz      short loc_180069043
0x180069028  test    byte ptr [rcx+1Ch], 8
0x18006902c  jz      short loc_180069043
0x18006902e  mov     edx, 6Ch ; 'l'
0x180069033  lea     r8, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids
0x18006903a  mov     rcx, [rcx+10h]
0x18006903e  call    WPP_SF_
0x180069043  mov     [rsp+0D8h+var_A8], 0
0x18006904c  xor     edx, edx; Val
0x18006904e  lea     r8d, [rdx+54h]; Size
0x180069052  lea     rcx, [rsp+0D8h+callout.calloutKey.Data2]; void *
0x180069057  call    memset_0
0x18006905c  lea     rax, aWindowsFirewal; "Windows Firewall: callout"
0x180069063  mov     [rsp+0D8h+callout.displayData.name], rax
0x180069068  lea     rax, qword_18012BB10
0x18006906f  mov     [rsp+0D8h+callout.providerKey], rax
0x180069074  movsd   xmm0, qword ptr cs:?FW_PLUMBER_CALLOUT_KEY@@3U_GUID@@B.Data1; _GUID const FW_PLUMBER_CALLOUT_KEY ...
0x18006907c  movsd   qword ptr [rsp+40h], xmm0
0x180069082  mov     eax, dword ptr cs:?FW_PLUMBER_CALLOUT_KEY@@3U_GUID@@B.Data4; _GUID const FW_PLUMBER_CALLOUT_KEY ...
0x180069088  mov     dword ptr [rsp+0D8h+callout.calloutKey.Data4], eax
0x18006908c  movzx   eax, word ptr cs:?FW_PLUMBER_CALLOUT_KEY@@3U_GUID@@B.Data4+4; _GUID const FW_PLUMBER_CALLOUT_KEY ...
0x180069093  mov     word ptr [rsp+0D8h+callout.calloutKey.Data4+4], ax
0x180069098  mov     word ptr [rsp+0D8h+callout.calloutKey.Data4+6], 0
0x18006909f  mov     rcx, cs:g_Provider
0x1800690a6  test    rcx, rcx
0x1800690a9  jz      short loc_1800690BE
0x1800690ab  xor     r9d, r9d
0x1800690ae  xor     r8d, r8d
0x1800690b1  lea     rdx, MPS_SVC_BFE_EngineOpen_Enter
0x1800690b8  call    cs:__imp_EtwEventWrite
0x1800690be  lea     rax, [rsp+0D8h+var_A8]
0x1800690c3  mov     [rsp+0D8h+engineHandle], rax; engineHandle
0x1800690c8  lea     r9, stru_1800F3D20; session
0x1800690cf  xor     r8d, r8d; authIdentity
0x1800690d2  lea     edx, [r8+0Ah]; authnService
0x1800690d6  xor     ecx, ecx; serverName
0x1800690d8  call    cs:__imp_FwpmEngineOpen0
0x1800690de  mov     ebx, eax
0x1800690e0  mov     rcx, cs:g_Provider
0x1800690e7  test    rcx, rcx
0x1800690ea  jz      short loc_180069106
0x1800690ec  xor     r9d, r9d
0x1800690ef  xor     r8d, r8d
0x1800690f2  lea     rdx, MPS_SVC_BFE_EngineOpen_Exit
0x1800690f9  call    cs:__imp_EtwEventWrite
0x1800690ff  mov     rcx, cs:g_Provider
0x180069106  test    ebx, ebx
0x180069108  jz      short loc_180069112
0x18006910a  mov     ecx, ebx; this
0x18006910c  call    ?ThrowWin32@FwPlumber@@YAXK@Z; FwPlumber::ThrowWin32(ulong)
0x180069112  xor     ebx, ebx
0x180069114  lea     r12, qword_1800E70F0
0x18006911b  cmp     ebx, 5
0x18006911e  jnb     loc_1800691D8
0x180069124  mov     [rsp+0D8h+callout.calloutKey.Data4+6], bl
0x180069128  lea     r14, [rbx+rbx*8]
0x18006912c  mov     rax, [r12+r14*4+1Ch]
0x180069131  mov     [rsp+0D8h+callout.displayData.description], rax
0x180069136  xor     esi, esi
0x180069138  lea     rdi, [rsi+rsi*2]
0x18006913c  mov     rdx, [r12+r14*4+14h]
0x180069141  mov     rax, [rdx+rdi*4]
0x180069145  test    rax, rax
0x180069148  jz      loc_1800691D1
0x18006914e  mov     rax, [rax]
0x180069151  movups  xmm0, xmmword ptr [rax]
0x180069154  movdqu  xmmword ptr [rsp+0D8h+callout.applicableLayer.Data1], xmm0
0x18006915d  mov     rax, [rdx+rdi*4]
0x180069161  mov     ecx, 0FFh
0x180069166  cmp     [rax+8], cx
0x18006916a  jbe     short loc_180069171
0x18006916c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180069171  mov     rdx, [r12+r14*4+14h]
0x180069176  mov     rax, [rdx+rdi*4]
0x18006917a  mov     cl, [rax+8]
0x18006917d  mov     [rsp+0D8h+callout.calloutKey.Data4+7], cl
0x180069181  lea     r9, [rdx+8]
0x180069185  lea     r9, [r9+rdi*4]; id
0x180069189  xor     r8d, r8d; sd
0x18006918c  lea     rdx, [rsp+0D8h+callout]; callout
0x180069191  mov     rcx, [rsp+0D8h+var_A8]; engineHandle
0x180069196  call    cs:__imp_FwpmCalloutAdd0
0x18006919c  mov     edi, eax
0x18006919e  cmp     eax, 80320009h
0x1800691a3  jz      short loc_1800691C3
0x1800691a5  lea     r8, ?g_FwCalloutError@@3U_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@A; struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *
0x1800691ac  mov     rdx, [rsp+0D8h+callout.displayData.name]; unsigned __int16 *
0x1800691b1  mov     ecx, eax; unsigned int
0x1800691b3  call    ?FwPlumberTrackObjError@@YAXKPEAGPEAU_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@@Z; FwPlumberTrackObjError(ulong,ushort *,_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)
0x1800691b8  test    edi, edi
0x1800691ba  jz      short loc_1800691C3
0x1800691bc  mov     ecx, edi; this
0x1800691be  call    ?ThrowWin32@FwPlumber@@YAXK@Z; FwPlumber::ThrowWin32(ulong)
0x1800691c3  inc     esi
0x1800691c5  mov     rcx, cs:g_Provider
0x1800691cc  jmp     loc_180069138
0x1800691d1  inc     ebx
0x1800691d3  jmp     loc_18006911B
0x1800691d8  test    rcx, rcx
0x1800691db  jz      short loc_1800691F0
0x1800691dd  xor     r9d, r9d
0x1800691e0  xor     r8d, r8d
0x1800691e3  lea     rdx, MPS_SVC_BFE_EngineClose_Enter
0x1800691ea  call    cs:__imp_EtwEventWrite
0x1800691f0  mov     rcx, [rsp+0D8h+var_A8]; engineHandle
0x1800691f5  call    cs:__imp_FwpmEngineClose0
0x1800691fb  mov     rcx, cs:g_Provider
0x180069202  test    rcx, rcx
0x180069205  jz      short loc_18006921A
0x180069207  xor     r9d, r9d
0x18006920a  xor     r8d, r8d
0x18006920d  lea     rdx, MPS_SVC_BFE_EngineClose_Exit
0x180069214  call    cs:__imp_EtwEventWrite
0x18006921a  mov     rcx, [rsp+0D8h+var_38]
0x180069222  xor     rcx, rsp; StackCookie
0x180069225  call    __security_check_cookie
0x18006922a  add     rsp, 0B0h
0x180069231  pop     r14
0x180069233  pop     r12
0x180069235  pop     rdi
0x180069236  pop     rsi
0x180069237  pop     rbx
0x180069238  retn
```
