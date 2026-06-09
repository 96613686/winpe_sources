# DispatchDwmDiagnosticsControlMessage

- ea: `0x180203e84`
- end: `0x180203fb5`
- name: `DispatchDwmDiagnosticsControlMessage`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801bf200`

## callees

- `0x180203e84`
- `0x180204100`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180203f03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180203f03`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180203ea8`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180203ea8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180203e9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180203e9b`

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
0x180203e84  push    rbx
0x180203e86  sub     rsp, 20h
0x180203e8a  cmp     dword ptr [rcx+18h], 0FFFFFFFFh
0x180203e8e  mov     rbx, rcx
0x180203e91  jz      short loc_180203EBF
0x180203e93  mov     [rsp+28h+pSessionId], 0
0x180203e9b  call    cs:__imp_GetCurrentProcessId
0x180203ea1  mov     ecx, eax; dwProcessId
0x180203ea3  lea     rdx, [rsp+28h+pSessionId]; pSessionId
0x180203ea8  call    cs:__imp_ProcessIdToSessionId
0x180203eae  test    eax, eax
0x180203eb0  jz      short loc_180203F03
0x180203eb2  mov     eax, [rbx+18h]
0x180203eb5  cmp     [rsp+28h+pSessionId], eax
0x180203eb9  jnz     loc_180203FAF
0x180203ebf  cmp     byte ptr [rbx+2], 0
0x180203ec3  jnz     loc_180203FAF
0x180203ec9  movzx   ecx, word ptr [rbx]
0x180203ecc  test    ecx, ecx
0x180203ece  jz      short loc_180203F2C
0x180203ed0  cmp     ecx, 1
0x180203ed3  jnz     loc_180203FAF
0x180203ed9  cmp     dword ptr [rbx+10h], 28h ; '('
0x180203edd  jnz     loc_180203FAF
0x180203ee3  mov     eax, [rbx+1Ch]
0x180203ee6  mov     cs:?g_HeatMaps_TargetProcessId@@3IA, eax; uint g_HeatMaps_TargetProcessId
0x180203eec  mov     eax, [rbx+20h]
0x180203eef  mov     cs:?g_HeatMaps_Type@@3W4HeatMapTypes@Tools@@A, eax; Tools::HeatMapTypes g_HeatMaps_Type
0x180203ef5  mov     eax, [rbx+24h]
0x180203ef8  mov     cs:?g_HeatMaps_OverdrawContentKinds@@3W4FlagsEnum@MilHeatMapOverdrawContentKinds@@A, eax; MilHeatMapOverdrawContentKinds::FlagsEnum g_HeatMaps_OverdrawContentKinds
0x180203efe  jmp     loc_180203FAF
0x180203f03  call    cs:__imp_GetLastError
0x180203f09  test    eax, eax
0x180203f0b  jle     short loc_180203F15
0x180203f0d  movzx   eax, ax
0x180203f10  or      eax, 80070000h
0x180203f15  mov     rdx, [rsp+28h]; void *
0x180203f1a  mov     ecx, 88980003h
0x180203f1f  test    eax, eax
0x180203f21  cmovns  eax, ecx
0x180203f24  mov     ecx, eax; int
0x180203f26  call    ModuleFailFastForHRESULT
0x180203f2c  cmp     dword ptr [rbx+10h], 24h ; '$'
0x180203f30  jb      short loc_180203FAF
0x180203f32  mov     r9d, [rbx+1Ch]
0x180203f36  lea     eax, [r9-1]
0x180203f3a  movsxd  rcx, eax
0x180203f3d  mov     eax, [rbx+10h]
0x180203f40  lea     rcx, ds:24h[rcx*4]
0x180203f48  cmp     rax, rcx
0x180203f4b  jb      short loc_180203FAF
0x180203f4d  xor     r8d, r8d
0x180203f50  test    r9d, r9d
0x180203f53  jle     short loc_180203FAF
0x180203f55  mov     ecx, [rbx+r8*4+20h]
0x180203f5a  mov     edx, ecx
0x180203f5c  not     edx
0x180203f5e  btr     ecx, 1Fh
0x180203f62  shr     edx, 1Fh
0x180203f65  sub     ecx, 2
0x180203f68  jz      short loc_180203FA1
0x180203f6a  sub     ecx, 2
0x180203f6d  jz      short loc_180203F99
0x180203f6f  sub     ecx, 1
0x180203f72  jz      short loc_180203F91
0x180203f74  sub     ecx, 1
0x180203f77  jz      short loc_180203F86
0x180203f79  cmp     ecx, 1
0x180203f7c  jnz     short loc_180203FA7
0x180203f7e  mov     cs:?g_simulateDeviceLost@@3_NA, dl; bool g_simulateDeviceLost
0x180203f84  jmp     short loc_180203FA7
0x180203f86  xor     dl, 1
0x180203f89  mov     cs:?g_bUseOcclusion@@3_NA, dl; bool g_bUseOcclusion
0x180203f8f  jmp     short loc_180203FA7
0x180203f91  mov     cs:?g_fTelemetry_FramesReportFast@@3_NA, dl; bool g_fTelemetry_FramesReportFast
0x180203f97  jmp     short loc_180203FA7
0x180203f99  mov     cs:?g_ShowLightingHeatmap@@3_NA, dl; bool g_ShowLightingHeatmap
0x180203f9f  jmp     short loc_180203FA7
0x180203fa1  mov     cs:?m_fShowDirtyRegions@CCommonRegistryData@@0HA, edx; int CCommonRegistryData::m_fShowDirtyRegions
0x180203fa7  inc     r8d
0x180203faa  cmp     r8d, r9d
0x180203fad  jl      short loc_180203F55
0x180203faf  add     rsp, 20h
0x180203fb3  pop     rbx
0x180203fb4  retn
```
