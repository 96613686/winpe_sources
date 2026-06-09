# DispatchDwmDiagnosticsControlMessage

- ea: `0x180203ea4`
- end: `0x180203fd5`
- name: `DispatchDwmDiagnosticsControlMessage`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801c16a0`

## callees

- `0x180203ea4`
- `0x180204120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180203f23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180203f23`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180203ec8`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180203ec8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180203ebb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180203ebb`

## pseudocode

```c
void __fastcall DispatchDwmDiagnosticsControlMessage(__int64 a1)
{
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  int v4; // r9d
  __int64 i; // r8
  void *retaddr; // [rsp+28h] [rbp+0h]
  DWORD pSessionId; // [rsp+30h] [rbp+8h] BYREF

  if ( *(_DWORD *)(a1 + 24) == -1 )
    goto LABEL_30;
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2003304445;
    ModuleFailFastForHRESULT(LastError, retaddr);
  }
  if ( pSessionId == *(_DWORD *)(a1 + 24) )
  {
LABEL_30:
    if ( !*(_BYTE *)(a1 + 2) )
    {
      if ( *(_WORD *)a1 )
      {
        if ( *(_WORD *)a1 == 1 && *(_DWORD *)(a1 + 16) == 40 )
        {
          g_HeatMaps_TargetProcessId = *(_DWORD *)(a1 + 28);
          g_HeatMaps_Type = *(_DWORD *)(a1 + 32);
          g_HeatMaps_OverdrawContentKinds = *(_DWORD *)(a1 + 36);
        }
      }
      else if ( *(_DWORD *)(a1 + 16) >= 0x24u )
      {
        v4 = *(_DWORD *)(a1 + 28);
        if ( *(unsigned int *)(a1 + 16) >= (unsigned __int64)(4LL * (v4 - 1) + 36) )
        {
          for ( i = 0; (int)i < v4; i = (unsigned int)(i + 1) )
          {
            switch ( *(_DWORD *)(a1 + 4 * i + 32) & 0x7FFFFFFF )
            {
              case 2:
                CCommonRegistryData::m_fShowDirtyRegions = *(_DWORD *)(a1 + 4 * i + 32) >= 0;
                break;
              case 4:
                g_ShowLightingHeatmap = *(_DWORD *)(a1 + 4 * i + 32) >= 0;
                break;
              case 5:
                g_fTelemetry_FramesReportFast = *(_DWORD *)(a1 + 4 * i + 32) >= 0;
                break;
              case 6:
                g_bUseOcclusion = *(int *)(a1 + 4 * i + 32) < 0;
                break;
              case 7:
                g_simulateDeviceLost = *(_DWORD *)(a1 + 4 * i + 32) >= 0;
                break;
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180203ea4  push    rbx
0x180203ea6  sub     rsp, 20h
0x180203eaa  cmp     dword ptr [rcx+18h], 0FFFFFFFFh
0x180203eae  mov     rbx, rcx
0x180203eb1  jz      short loc_180203EDF
0x180203eb3  mov     [rsp+28h+pSessionId], 0
0x180203ebb  call    cs:__imp_GetCurrentProcessId
0x180203ec1  mov     ecx, eax; dwProcessId
0x180203ec3  lea     rdx, [rsp+28h+pSessionId]; pSessionId
0x180203ec8  call    cs:__imp_ProcessIdToSessionId
0x180203ece  test    eax, eax
0x180203ed0  jz      short loc_180203F23
0x180203ed2  mov     eax, [rbx+18h]
0x180203ed5  cmp     [rsp+28h+pSessionId], eax
0x180203ed9  jnz     loc_180203FCF
0x180203edf  cmp     byte ptr [rbx+2], 0
0x180203ee3  jnz     loc_180203FCF
0x180203ee9  movzx   ecx, word ptr [rbx]
0x180203eec  test    ecx, ecx
0x180203eee  jz      short loc_180203F4C
0x180203ef0  cmp     ecx, 1
0x180203ef3  jnz     loc_180203FCF
0x180203ef9  cmp     dword ptr [rbx+10h], 28h ; '('
0x180203efd  jnz     loc_180203FCF
0x180203f03  mov     eax, [rbx+1Ch]
0x180203f06  mov     cs:?g_HeatMaps_TargetProcessId@@3IA, eax; uint g_HeatMaps_TargetProcessId
0x180203f0c  mov     eax, [rbx+20h]
0x180203f0f  mov     cs:?g_HeatMaps_Type@@3W4HeatMapTypes@Tools@@A, eax; Tools::HeatMapTypes g_HeatMaps_Type
0x180203f15  mov     eax, [rbx+24h]
0x180203f18  mov     cs:?g_HeatMaps_OverdrawContentKinds@@3W4FlagsEnum@MilHeatMapOverdrawContentKinds@@A, eax; MilHeatMapOverdrawContentKinds::FlagsEnum g_HeatMaps_OverdrawContentKinds
0x180203f1e  jmp     loc_180203FCF
0x180203f23  call    cs:__imp_GetLastError
0x180203f29  test    eax, eax
0x180203f2b  jle     short loc_180203F35
0x180203f2d  movzx   eax, ax
0x180203f30  or      eax, 80070000h
0x180203f35  mov     rdx, [rsp+28h]; void *
0x180203f3a  mov     ecx, 88980003h
0x180203f3f  test    eax, eax
0x180203f41  cmovns  eax, ecx
0x180203f44  mov     ecx, eax; int
0x180203f46  call    ModuleFailFastForHRESULT
0x180203f4c  cmp     dword ptr [rbx+10h], 24h ; '$'
0x180203f50  jb      short loc_180203FCF
0x180203f52  mov     r9d, [rbx+1Ch]
0x180203f56  lea     eax, [r9-1]
0x180203f5a  movsxd  rcx, eax
0x180203f5d  mov     eax, [rbx+10h]
0x180203f60  lea     rcx, ds:24h[rcx*4]
0x180203f68  cmp     rax, rcx
0x180203f6b  jb      short loc_180203FCF
0x180203f6d  xor     r8d, r8d
0x180203f70  test    r9d, r9d
0x180203f73  jle     short loc_180203FCF
0x180203f75  mov     ecx, [rbx+r8*4+20h]
0x180203f7a  mov     edx, ecx
0x180203f7c  not     edx
0x180203f7e  btr     ecx, 1Fh
0x180203f82  shr     edx, 1Fh
0x180203f85  sub     ecx, 2
0x180203f88  jz      short loc_180203FC1
0x180203f8a  sub     ecx, 2
0x180203f8d  jz      short loc_180203FB9
0x180203f8f  sub     ecx, 1
0x180203f92  jz      short loc_180203FB1
0x180203f94  sub     ecx, 1
0x180203f97  jz      short loc_180203FA6
0x180203f99  cmp     ecx, 1
0x180203f9c  jnz     short loc_180203FC7
0x180203f9e  mov     cs:?g_simulateDeviceLost@@3_NA, dl; bool g_simulateDeviceLost
0x180203fa4  jmp     short loc_180203FC7
0x180203fa6  xor     dl, 1
0x180203fa9  mov     cs:?g_bUseOcclusion@@3_NA, dl; bool g_bUseOcclusion
0x180203faf  jmp     short loc_180203FC7
0x180203fb1  mov     cs:?g_fTelemetry_FramesReportFast@@3_NA, dl; bool g_fTelemetry_FramesReportFast
0x180203fb7  jmp     short loc_180203FC7
0x180203fb9  mov     cs:?g_ShowLightingHeatmap@@3_NA, dl; bool g_ShowLightingHeatmap
0x180203fbf  jmp     short loc_180203FC7
0x180203fc1  mov     cs:?m_fShowDirtyRegions@CCommonRegistryData@@0HA, edx; int CCommonRegistryData::m_fShowDirtyRegions
0x180203fc7  inc     r8d
0x180203fca  cmp     r8d, r9d
0x180203fcd  jl      short loc_180203F75
0x180203fcf  add     rsp, 20h
0x180203fd3  pop     rbx
0x180203fd4  retn
```
