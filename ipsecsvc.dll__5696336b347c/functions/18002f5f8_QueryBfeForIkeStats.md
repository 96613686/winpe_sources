# QueryBfeForIkeStats

- ea: `0x18002f5f8`
- end: `0x18002f6bf`
- name: `QueryBfeForIkeStats`
- size: `199`
- prototype: `__int64 __fastcall(IKEEXT_STATISTICS0 *ikeextStatistics)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002f984`

## callees

- `0x18000e510`
- `0x18002f5f8`

## import_xrefs

- `fwpuclnt!FwpmEngineClose0` at `0x18002f6ac`
- `fwpuclnt!FwpmEngineClose0` at `0x18002f6ac`
- `fwpuclnt!IkeextGetStatistics0` at `0x18002f66a`
- `fwpuclnt!IkeextGetStatistics0` at `0x18002f66a`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002f623`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002f623`

## pseudocode

```c
__int64 __fastcall QueryBfeForIkeStats(IKEEXT_STATISTICS0 *ikeextStatistics)
{
  DWORD Statistics0; // ebx
  HANDLE engineHandle; // [rsp+48h] [rbp+10h] BYREF

  engineHandle = 0;
  Statistics0 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  if ( Statistics0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids, Statistics0);
  }
  else
  {
    Statistics0 = IkeextGetStatistics0(engineHandle, ikeextStatistics);
    if ( Statistics0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids, Statistics0);
    }
    FwpmEngineClose0(engineHandle);
  }
  return Statistics0;
}

```

## disassembly

```asm
0x18002f5f8  mov     r11, rsp
0x18002f5fb  mov     [r11+8], rbx
0x18002f5ff  push    rdi
0x18002f600  sub     rsp, 30h
0x18002f604  xor     r9d, r9d; session
0x18002f607  mov     qword ptr [r11+10h], 0
0x18002f60f  mov     rdi, rcx
0x18002f612  lea     rax, [r11+10h]
0x18002f616  xor     r8d, r8d; authIdentity
0x18002f619  mov     [r11-18h], rax
0x18002f61d  xor     ecx, ecx; serverName
0x18002f61f  lea     edx, [r9+0Ah]; authnService
0x18002f623  call    cs:__imp_FwpmEngineOpen0
0x18002f629  mov     ebx, eax
0x18002f62b  test    eax, eax
0x18002f62d  jz      short loc_18002F662
0x18002f62f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f636  lea     rax, WPP_GLOBAL_Control
0x18002f63d  cmp     rcx, rax
0x18002f640  jz      short loc_18002F6B2
0x18002f642  test    byte ptr [rcx+1Ch], 10h
0x18002f646  jz      short loc_18002F6B2
0x18002f648  mov     rcx, [rcx+10h]
0x18002f64c  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002f653  mov     edx, 11h
0x18002f658  mov     r9d, ebx
0x18002f65b  call    WPP_SF_d
0x18002f660  jmp     short loc_18002F6B2
0x18002f662  mov     rcx, [rsp+38h+engineHandle]; engineHandle
0x18002f667  mov     rdx, rdi; ikeextStatistics
0x18002f66a  call    cs:__imp_IkeextGetStatistics0
0x18002f670  mov     ebx, eax
0x18002f672  test    eax, eax
0x18002f674  jz      short loc_18002F6A7
0x18002f676  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f67d  lea     rax, WPP_GLOBAL_Control
0x18002f684  cmp     rcx, rax
0x18002f687  jz      short loc_18002F6A7
0x18002f689  test    byte ptr [rcx+1Ch], 10h
0x18002f68d  jz      short loc_18002F6A7
0x18002f68f  mov     rcx, [rcx+10h]
0x18002f693  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002f69a  mov     edx, 12h
0x18002f69f  mov     r9d, ebx
0x18002f6a2  call    WPP_SF_d
0x18002f6a7  mov     rcx, [rsp+38h+engineHandle]; engineHandle
0x18002f6ac  call    cs:__imp_FwpmEngineClose0
0x18002f6b2  mov     eax, ebx
0x18002f6b4  mov     rbx, [rsp+38h+arg_0]
0x18002f6b9  add     rsp, 30h
0x18002f6bd  pop     rdi
0x18002f6be  retn
```
