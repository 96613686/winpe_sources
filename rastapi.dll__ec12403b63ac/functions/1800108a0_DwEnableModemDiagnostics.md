# DwEnableModemDiagnostics

- ea: `0x1800108a0`
- end: `0x1800109ff`
- name: `DwEnableModemDiagnostics`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180013ccc`

## callees

- `0x18000d92c`
- `0x1800108a0`
- `0x1800292b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010925`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010925`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800109c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800109c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010933`
- `ext-ms-win-ras-tapi32-l1-1-1!lineSetDevConfigA` at `0x1800109a3`
- `ext-ms-win-ras-tapi32-l1-1-1!lineSetDevConfigA` at `0x1800109a3`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetDevConfigA` at `0x1800108f9`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetDevConfigA` at `0x180010953`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetDevConfigA` at `0x1800108f9`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetDevConfigA` at `0x180010953`

## pseudocode

```c
__int64 __fastcall DwEnableModemDiagnostics(__int64 a1)
{
  __int64 v2; // rcx
  unsigned int DevConfigA; // edi
  struct varstring_tag *p_DeviceConfig; // rbx
  DWORD dwNeededSize; // edi
  struct varstring_tag *v6; // rax
  DWORD LastError; // eax
  _DWORD *v8; // rdi
  struct varstring_tag DeviceConfig; // [rsp+20h] [rbp-408h] BYREF

  RasTapiTrace("DwEnableModemDiagnostics");
  v2 = *(_QWORD *)(a1 + 216);
  DeviceConfig.dwTotalSize = 1000;
  DeviceConfig.dwStringSize = 0;
  DevConfigA = lineGetDevConfigA(*(_DWORD *)(v2 + 8), &DeviceConfig, "tapi/line/diagnostics");
  if ( DevConfigA == -2147483571 || DeviceConfig.dwNeededSize > DeviceConfig.dwTotalSize )
  {
    dwNeededSize = DeviceConfig.dwNeededSize;
    v6 = (struct varstring_tag *)LocalAlloc(0x40u, DeviceConfig.dwNeededSize);
    p_DeviceConfig = v6;
    if ( !v6 )
    {
      LastError = GetLastError();
LABEL_6:
      DevConfigA = LastError;
      goto LABEL_15;
    }
    v6->dwTotalSize = dwNeededSize;
    DevConfigA = lineGetDevConfigA(*(_DWORD *)(*(_QWORD *)(a1 + 216) + 8LL), v6, "tapi/line/diagnostics");
  }
  else
  {
    p_DeviceConfig = &DeviceConfig;
  }
  if ( !DevConfigA )
  {
    if ( p_DeviceConfig->dwStringFormat == 4 && p_DeviceConfig->dwStringSize >= 0x14 )
    {
      v8 = (DWORD *)((char *)&p_DeviceConfig->dwTotalSize + p_DeviceConfig->dwStringOffset);
      if ( *v8 != -1292399230 )
        RasTapiTrace("Invalid LineDiagnostics sig. 0x%x");
      v8[4] |= 1u;
      LastError = lineSetDevConfigA(
                    *(_DWORD *)(*(_QWORD *)(a1 + 216) + 8LL),
                    v8,
                    p_DeviceConfig->dwStringSize,
                    "tapi/line/diagnostics");
      goto LABEL_6;
    }
    RasTapiTrace("No diagnostics information available");
  }
LABEL_15:
  if ( &DeviceConfig != p_DeviceConfig )
    LocalFree(p_DeviceConfig);
  RasTapiTrace("DwEnableModemDiagnostics. 0x%x");
  return DevConfigA;
}

```

## disassembly

```asm
0x1800108a0  mov     [rsp+arg_8], rbx
0x1800108a5  mov     [rsp+arg_10], rsi
0x1800108aa  push    rdi
0x1800108ab  sub     rsp, 420h
0x1800108b2  mov     rax, cs:__security_cookie
0x1800108b9  xor     rax, rsp
0x1800108bc  mov     [rsp+428h+var_18], rax
0x1800108c4  mov     rsi, rcx
0x1800108c7  lea     rcx, aDwenablemodemd_1; "DwEnableModemDiagnostics"
0x1800108ce  call    RasTapiTrace
0x1800108d3  mov     rcx, [rsi+0D8h]
0x1800108da  lea     r8, szDeviceClass; "tapi/line/diagnostics"
0x1800108e1  mov     [rsp+428h+DeviceConfig.dwTotalSize], 3E8h
0x1800108e9  lea     rdx, [rsp+428h+DeviceConfig]; lpDeviceConfig
0x1800108ee  mov     [rsp+428h+DeviceConfig.dwStringSize], 0
0x1800108f6  mov     ecx, [rcx+8]; dwDeviceID
0x1800108f9  call    cs:__imp_lineGetDevConfigA
0x1800108ff  mov     edi, eax
0x180010901  mov     eax, [rsp+428h+DeviceConfig.dwNeededSize]
0x180010905  cmp     edi, 8000004Dh
0x18001090b  jz      short loc_18001091A
0x18001090d  cmp     eax, [rsp+428h+DeviceConfig.dwTotalSize]
0x180010911  ja      short loc_18001091A
0x180010913  lea     rbx, [rsp+428h+DeviceConfig]
0x180010918  jmp     short loc_18001095B
0x18001091a  mov     rdx, rax; uBytes
0x18001091d  mov     ecx, 40h ; '@'; uFlags
0x180010922  mov     rdi, rax
0x180010925  call    cs:__imp_LocalAlloc
0x18001092b  mov     rbx, rax
0x18001092e  test    rax, rax
0x180010931  jnz     short loc_18001093D
0x180010933  call    cs:__imp_GetLastError
0x180010939  mov     edi, eax
0x18001093b  jmp     short loc_1800109B7
0x18001093d  mov     [rax], edi
0x18001093f  lea     r8, szDeviceClass; "tapi/line/diagnostics"
0x180010946  mov     rcx, [rsi+0D8h]
0x18001094d  mov     rdx, rax; lpDeviceConfig
0x180010950  mov     ecx, [rcx+8]; dwDeviceID
0x180010953  call    cs:__imp_lineGetDevConfigA
0x180010959  mov     edi, eax
0x18001095b  test    edi, edi
0x18001095d  jnz     short loc_1800109B7
0x18001095f  cmp     dword ptr [rbx+0Ch], 4
0x180010963  jnz     short loc_1800109AB
0x180010965  cmp     dword ptr [rbx+10h], 14h
0x180010969  jb      short loc_1800109AB
0x18001096b  mov     edi, [rbx+14h]
0x18001096e  add     rdi, rbx
0x180010971  cmp     dword ptr [rdi], 0B2F78D82h
0x180010977  jz      short loc_180010987
0x180010979  mov     edx, [rdi]
0x18001097b  lea     rcx, aInvalidLinedia; "Invalid LineDiagnostics sig. 0x%x"
0x180010982  call    RasTapiTrace
0x180010987  or      dword ptr [rdi+10h], 1
0x18001098b  lea     r9, szDeviceClass; "tapi/line/diagnostics"
0x180010992  mov     rcx, [rsi+0D8h]
0x180010999  mov     rdx, rdi; lpDeviceConfig
0x18001099c  mov     r8d, [rbx+10h]; dwSize
0x1800109a0  mov     ecx, [rcx+8]; dwDeviceID
0x1800109a3  call    cs:__imp_lineSetDevConfigA
0x1800109a9  jmp     short loc_180010939
0x1800109ab  lea     rcx, aNoDiagnosticsI; "No diagnostics information available"
0x1800109b2  call    RasTapiTrace
0x1800109b7  lea     rax, [rsp+428h+DeviceConfig]
0x1800109bc  cmp     rax, rbx
0x1800109bf  jz      short loc_1800109CA
0x1800109c1  mov     rcx, rbx; hMem
0x1800109c4  call    cs:__imp_LocalFree
0x1800109ca  mov     edx, edi
0x1800109cc  lea     rcx, aDwenablemodemd; "DwEnableModemDiagnostics. 0x%x"
0x1800109d3  call    RasTapiTrace
0x1800109d8  mov     eax, edi
0x1800109da  mov     rcx, [rsp+428h+var_18]
0x1800109e2  xor     rcx, rsp; StackCookie
0x1800109e5  call    __security_check_cookie
0x1800109ea  lea     r11, [rsp+428h+var_8]
0x1800109f2  mov     rbx, [r11+18h]
0x1800109f6  mov     rsi, [r11+20h]
0x1800109fa  mov     rsp, r11
0x1800109fd  pop     rdi
0x1800109fe  retn
```
