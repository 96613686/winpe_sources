# FwPlumber::CreateCallouts

- ea: `0x1800e63f0`
- end: `0x1800e664d`
- name: `FwPlumber::CreateCallouts`
- size: `605`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800e6b0c`

## callees

- `0x1800089bc`
- `0x1800192e0`
- `0x1800238f4`
- `0x180023910`
- `0x1800729c0`
- `0x180073488`
- `0x1800e63f0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800e64b4`
- `ntdll!EtwEventWrite` at `0x1800e6501`
- `ntdll!EtwEventWrite` at `0x1800e65eb`
- `ntdll!EtwEventWrite` at `0x1800e6621`
- `ntdll!EtwEventWrite` at `0x1800e64b4`
- `ntdll!EtwEventWrite` at `0x1800e6501`
- `ntdll!EtwEventWrite` at `0x1800e65eb`
- `ntdll!EtwEventWrite` at `0x1800e6621`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800e64da`
- `fwpuclnt!FwpmEngineOpen0` at `0x1800e64da`
- `fwpuclnt!FwpmEngineClose0` at `0x1800e65fc`
- `fwpuclnt!FwpmEngineClose0` at `0x1800e65fc`
- `fwpuclnt!FwpmCalloutAdd0` at `0x1800e6595`
- `fwpuclnt!FwpmCalloutAdd0` at `0x1800e6595`

## pseudocode

```c
DWORD FwPlumber::CreateCallouts()
{
  unsigned int v0; // edx
  DWORD v1; // ebx
  __int64 v2; // rbx
  __int64 v3; // rdi
  __int64 v4; // rcx
  GUID **v5; // rax
  __int64 v6; // rdx
  DWORD v7; // eax
  DWORD v8; // esi
  unsigned int v9; // edx
  DWORD result; // eax
  HANDLE engineHandle; // [rsp+30h] [rbp-A8h] BYREF
  FWPM_CALLOUT0 callout; // [rsp+40h] [rbp-98h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 108, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids);
  engineHandle = 0;
  memset_0(&callout.calloutKey.Data2, 0, 0x54u);
  callout.displayData.name = L"Windows Firewall: callout";
  callout.providerKey = (GUID *)qword_180131D00;
  *(_QWORD *)&callout.calloutKey.Data1 = *(_QWORD *)&FW_PLUMBER_CALLOUT_KEY.Data1;
  *(_DWORD *)callout.calloutKey.Data4 = *(_DWORD *)FW_PLUMBER_CALLOUT_KEY.Data4;
  *(_WORD *)&callout.calloutKey.Data4[4] = *(_WORD *)&FW_PLUMBER_CALLOUT_KEY.Data4[4];
  *(_WORD *)&callout.calloutKey.Data4[6] = 0;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_BFE_EngineOpen_Enter, 0, 0);
  v1 = FwpmEngineOpen0(0, 0xAu, 0, &stru_1800F9CD0, &engineHandle);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_BFE_EngineOpen_Exit, 0, 0);
  FwPlumber::ThrowIf32Error((FwPlumber *)v1, v0);
  v2 = 0;
  while ( (unsigned int)v2 < 5 )
  {
    callout.calloutKey.Data4[6] = v2;
    callout.displayData.description = *(wchar_t **)((char *)&qword_1800F9AE0[3] + 36 * v2 + 4);
    v3 = 0;
    try
    {
      while ( 1 )
      {
        v4 = *(__int64 *)((char *)&qword_1800F9AE0[2] + 36 * v2 + 4);
        v5 = *(GUID ***)(v4 + 12 * v3);
        if ( !v5 )
          break;
        callout.applicableLayer = **v5;
        if ( *(_WORD *)(*(_QWORD *)(v4 + 12 * v3) + 8LL) > 0xFFu )
          MicrosoftTelemetryAssertTriggeredNoArgs(255);
        v6 = *(__int64 *)((char *)&qword_1800F9AE0[2] + 36 * v2 + 4);
        callout.calloutKey.Data4[7] = *(_BYTE *)(*(_QWORD *)(v6 + 12 * v3) + 8LL);
        v7 = FwpmCalloutAdd0(engineHandle, &callout, 0, (UINT32 *)(v6 + 8 + 12 * v3));
        v8 = v7;
        if ( v7 != -2144206839 )
        {
          FwPlumberTrackObjError(
            v7,
            callout.displayData.name,
            (struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)&g_FwCalloutError);
          FwPlumber::ThrowIf32Error((FwPlumber *)v8, v9);
        }
        v3 = (unsigned int)(v3 + 1);
      }
      v2 = (unsigned int)(v2 + 1);
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
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_BFE_EngineClose_Enter, 0, 0);
  result = FwpmEngineClose0(engineHandle);
  if ( g_Provider )
    return EtwEventWrite(g_Provider, MPS_SVC_BFE_EngineClose_Exit, 0, 0);
  return result;
}

```

## disassembly

```asm
0x1800e63f0  push    rbx
0x1800e63f2  push    rsi
0x1800e63f3  push    rdi
0x1800e63f4  push    r12
0x1800e63f6  push    r14
0x1800e63f8  sub     rsp, 0B0h
0x1800e63ff  mov     rax, cs:__security_cookie
0x1800e6406  xor     rax, rsp
0x1800e6409  mov     [rsp+0D8h+var_38], rax
0x1800e6411  lea     rax, WPP_GLOBAL_Control
0x1800e6418  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e641f  cmp     rcx, rax
0x1800e6422  jz      short loc_1800E643F
0x1800e6424  test    byte ptr [rcx+1Ch], 8
0x1800e6428  jz      short loc_1800E643F
0x1800e642a  mov     edx, 6Ch ; 'l'
0x1800e642f  lea     r8, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids
0x1800e6436  mov     rcx, [rcx+10h]
0x1800e643a  call    WPP_SF_
0x1800e643f  mov     [rsp+0D8h+var_A8], 0
0x1800e6448  xor     edx, edx; Val
0x1800e644a  lea     r8d, [rdx+54h]; Size
0x1800e644e  lea     rcx, [rsp+0D8h+callout.calloutKey.Data2]; void *
0x1800e6453  call    memset_0
0x1800e6458  lea     rax, aWindowsFirewal; "Windows Firewall: callout"
0x1800e645f  mov     [rsp+0D8h+callout.displayData.name], rax
0x1800e6464  lea     rax, qword_180131D00
0x1800e646b  mov     [rsp+0D8h+callout.providerKey], rax
0x1800e6470  movsd   xmm0, qword ptr cs:?FW_PLUMBER_CALLOUT_KEY@@3U_GUID@@B.Data1; _GUID const FW_PLUMBER_CALLOUT_KEY ...
0x1800e6478  movsd   qword ptr [rsp+40h], xmm0
0x1800e647e  mov     eax, dword ptr cs:?FW_PLUMBER_CALLOUT_KEY@@3U_GUID@@B.Data4; _GUID const FW_PLUMBER_CALLOUT_KEY ...
0x1800e6484  mov     dword ptr [rsp+0D8h+callout.calloutKey.Data4], eax
0x1800e6488  movzx   eax, word ptr cs:?FW_PLUMBER_CALLOUT_KEY@@3U_GUID@@B.Data4+4; _GUID const FW_PLUMBER_CALLOUT_KEY ...
0x1800e648f  mov     word ptr [rsp+0D8h+callout.calloutKey.Data4+4], ax
0x1800e6494  mov     word ptr [rsp+0D8h+callout.calloutKey.Data4+6], 0
0x1800e649b  mov     rcx, cs:g_Provider
0x1800e64a2  test    rcx, rcx
0x1800e64a5  jz      short loc_1800E64C0
0x1800e64a7  xor     r9d, r9d
0x1800e64aa  xor     r8d, r8d
0x1800e64ad  lea     rdx, MPS_SVC_BFE_EngineOpen_Enter
0x1800e64b4  call    cs:__imp_EtwEventWrite
0x1800e64bb  nop     dword ptr [rax+rax+00h]
0x1800e64c0  lea     rax, [rsp+0D8h+var_A8]
0x1800e64c5  mov     [rsp+0D8h+engineHandle], rax; engineHandle
0x1800e64ca  lea     r9, stru_1800F9CD0; session
0x1800e64d1  xor     r8d, r8d; authIdentity
0x1800e64d4  lea     edx, [r8+0Ah]; authnService
0x1800e64d8  xor     ecx, ecx; serverName
0x1800e64da  call    cs:__imp_FwpmEngineOpen0
0x1800e64e1  nop     dword ptr [rax+rax+00h]
0x1800e64e6  mov     ebx, eax
0x1800e64e8  mov     rcx, cs:g_Provider
0x1800e64ef  test    rcx, rcx
0x1800e64f2  jz      short loc_1800E650D
0x1800e64f4  xor     r9d, r9d
0x1800e64f7  xor     r8d, r8d
0x1800e64fa  lea     rdx, MPS_SVC_BFE_EngineOpen_Exit
0x1800e6501  call    cs:__imp_EtwEventWrite
0x1800e6508  nop     dword ptr [rax+rax+00h]
0x1800e650d  mov     ecx, ebx; this
0x1800e650f  call    ?ThrowIf32Error@FwPlumber@@YAXK@Z; FwPlumber::ThrowIf32Error(ulong)
0x1800e6514  nop
0x1800e6515  xor     ebx, ebx
0x1800e6517  lea     r12, qword_1800F9AE0
0x1800e651e  cmp     ebx, 5
0x1800e6521  jnb     loc_1800E65D2
0x1800e6527  mov     [rsp+0D8h+callout.calloutKey.Data4+6], bl
0x1800e652b  lea     r14, [rbx+rbx*8]
0x1800e652f  mov     rax, [r12+r14*4+1Ch]
0x1800e6534  mov     [rsp+0D8h+callout.displayData.description], rax
0x1800e6539  xor     edi, edi
0x1800e653b  lea     rsi, [rdi+rdi*2]
0x1800e653f  mov     rcx, [r12+r14*4+14h]
0x1800e6544  mov     rax, [rcx+rsi*4]
0x1800e6548  test    rax, rax
0x1800e654b  jz      short loc_1800E65CB
0x1800e654d  mov     rax, [rax]
0x1800e6550  movups  xmm0, xmmword ptr [rax]
0x1800e6553  movdqu  xmmword ptr [rsp+0D8h+callout.applicableLayer.Data1], xmm0
0x1800e655c  mov     rax, [rcx+rsi*4]
0x1800e6560  mov     ecx, 0FFh
0x1800e6565  cmp     [rax+8], cx
0x1800e6569  jbe     short loc_1800E6570
0x1800e656b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800e6570  mov     rdx, [r12+r14*4+14h]
0x1800e6575  mov     rax, [rdx+rsi*4]
0x1800e6579  mov     cl, [rax+8]
0x1800e657c  mov     [rsp+0D8h+callout.calloutKey.Data4+7], cl
0x1800e6580  lea     r9, [rdx+8]
0x1800e6584  lea     r9, [r9+rsi*4]; id
0x1800e6588  xor     r8d, r8d; sd
0x1800e658b  lea     rdx, [rsp+0D8h+callout]; callout
0x1800e6590  mov     rcx, [rsp+0D8h+var_A8]; engineHandle
0x1800e6595  call    cs:__imp_FwpmCalloutAdd0
0x1800e659c  nop     dword ptr [rax+rax+00h]
0x1800e65a1  mov     esi, eax
0x1800e65a3  cmp     eax, 80320009h
0x1800e65a8  jz      short loc_1800E65C4
0x1800e65aa  lea     r8, ?g_FwCalloutError@@3U_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@A; struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *
0x1800e65b1  mov     rdx, [rsp+0D8h+callout.displayData.name]; unsigned __int16 *
0x1800e65b6  mov     ecx, eax; unsigned int
0x1800e65b8  call    ?FwPlumberTrackObjError@@YAXKPEAGPEAU_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@@Z; FwPlumberTrackObjError(ulong,ushort *,_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)
0x1800e65bd  mov     ecx, esi; this
0x1800e65bf  call    ?ThrowIf32Error@FwPlumber@@YAXK@Z; FwPlumber::ThrowIf32Error(ulong)
0x1800e65c4  inc     edi
0x1800e65c6  jmp     loc_1800E653B
0x1800e65cb  inc     ebx
0x1800e65cd  jmp     loc_1800E651E
0x1800e65d2  mov     rcx, cs:g_Provider
0x1800e65d9  test    rcx, rcx
0x1800e65dc  jz      short loc_1800E65F7
0x1800e65de  xor     r9d, r9d
0x1800e65e1  xor     r8d, r8d
0x1800e65e4  lea     rdx, MPS_SVC_BFE_EngineClose_Enter
0x1800e65eb  call    cs:__imp_EtwEventWrite
0x1800e65f2  nop     dword ptr [rax+rax+00h]
0x1800e65f7  mov     rcx, [rsp+0D8h+var_A8]; engineHandle
0x1800e65fc  call    cs:__imp_FwpmEngineClose0
0x1800e6603  nop     dword ptr [rax+rax+00h]
0x1800e6608  mov     rcx, cs:g_Provider
0x1800e660f  test    rcx, rcx
0x1800e6612  jz      short loc_1800E662D
0x1800e6614  xor     r9d, r9d
0x1800e6617  xor     r8d, r8d
0x1800e661a  lea     rdx, MPS_SVC_BFE_EngineClose_Exit
0x1800e6621  call    cs:__imp_EtwEventWrite
0x1800e6628  nop     dword ptr [rax+rax+00h]
0x1800e662d  mov     rcx, [rsp+0D8h+var_38]
0x1800e6635  xor     rcx, rsp; StackCookie
0x1800e6638  call    __security_check_cookie
0x1800e663d  add     rsp, 0B0h
0x1800e6644  pop     r14
0x1800e6646  pop     r12
0x1800e6648  pop     rdi
0x1800e6649  pop     rsi
0x1800e664a  pop     rbx
0x1800e664b  retn
```
