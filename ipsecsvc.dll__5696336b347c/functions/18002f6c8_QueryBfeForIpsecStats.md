# QueryBfeForIpsecStats

- ea: `0x18002f6c8`
- end: `0x18002f79b`
- name: `QueryBfeForIpsecStats`
- size: `211`
- prototype: `__int64 __fastcall(IPSEC_STATISTICS0 *ipsecStatistics)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002f7a4`

## callees

- `0x18000e510`
- `0x18002f6c8`

## import_xrefs

- `fwpuclnt!FwpmEngineClose0` at `0x18002f788`
- `fwpuclnt!FwpmEngineClose0` at `0x18002f788`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002f6f3`
- `fwpuclnt!FwpmEngineOpen0` at `0x18002f6f3`
- `fwpuclnt!IPsecGetStatistics0` at `0x18002f73a`
- `fwpuclnt!IPsecGetStatistics0` at `0x18002f73a`

## pseudocode

```c
__int64 __fastcall QueryBfeForIpsecStats(IPSEC_STATISTICS0 *ipsecStatistics)
{
  DWORD v2; // ebx
  DWORD Statistics0; // eax
  HANDLE engineHandle; // [rsp+48h] [rbp+10h] BYREF

  engineHandle = 0;
  v2 = FwpmEngineOpen0(0, 0xAu, 0, 0, &engineHandle);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids, v2);
  }
  else
  {
    Statistics0 = IPsecGetStatistics0(engineHandle, ipsecStatistics);
    v2 = 0;
    if ( Statistics0 != 1753 )
      v2 = Statistics0;
    if ( v2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids, v2);
    }
    else
    {
      v2 = 0;
    }
    FwpmEngineClose0(engineHandle);
  }
  return v2;
}

```

## disassembly

```asm
0x18002f6c8  mov     r11, rsp
0x18002f6cb  mov     [r11+8], rbx
0x18002f6cf  push    rdi
0x18002f6d0  sub     rsp, 30h
0x18002f6d4  xor     r9d, r9d; session
0x18002f6d7  mov     qword ptr [r11+10h], 0
0x18002f6df  mov     rdi, rcx
0x18002f6e2  lea     rax, [r11+10h]
0x18002f6e6  xor     r8d, r8d; authIdentity
0x18002f6e9  mov     [r11-18h], rax
0x18002f6ed  xor     ecx, ecx; serverName
0x18002f6ef  lea     edx, [r9+0Ah]; authnService
0x18002f6f3  call    cs:__imp_FwpmEngineOpen0
0x18002f6f9  mov     ebx, eax
0x18002f6fb  test    eax, eax
0x18002f6fd  jz      short loc_18002F732
0x18002f6ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f706  lea     rax, WPP_GLOBAL_Control
0x18002f70d  cmp     rcx, rax
0x18002f710  jz      short loc_18002F78E
0x18002f712  test    byte ptr [rcx+1Ch], 10h
0x18002f716  jz      short loc_18002F78E
0x18002f718  mov     rcx, [rcx+10h]
0x18002f71c  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002f723  mov     edx, 0Dh
0x18002f728  mov     r9d, ebx
0x18002f72b  call    WPP_SF_d
0x18002f730  jmp     short loc_18002F78E
0x18002f732  mov     rcx, [rsp+38h+engineHandle]; engineHandle
0x18002f737  mov     rdx, rdi; ipsecStatistics
0x18002f73a  call    cs:__imp_IPsecGetStatistics0
0x18002f740  xor     ebx, ebx
0x18002f742  cmp     eax, 6D9h
0x18002f747  cmovnz  ebx, eax
0x18002f74a  test    ebx, ebx
0x18002f74c  jz      short loc_18002F781
0x18002f74e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f755  lea     rax, WPP_GLOBAL_Control
0x18002f75c  cmp     rcx, rax
0x18002f75f  jz      short loc_18002F783
0x18002f761  test    byte ptr [rcx+1Ch], 10h
0x18002f765  jz      short loc_18002F783
0x18002f767  mov     rcx, [rcx+10h]
0x18002f76b  lea     r8, WPP_c57b73e384023a72e58561d5d38b8882_Traceguids
0x18002f772  mov     edx, 0Eh
0x18002f777  mov     r9d, ebx
0x18002f77a  call    WPP_SF_d
0x18002f77f  jmp     short loc_18002F783
0x18002f781  xor     ebx, ebx
0x18002f783  mov     rcx, [rsp+38h+engineHandle]; engineHandle
0x18002f788  call    cs:__imp_FwpmEngineClose0
0x18002f78e  mov     eax, ebx
0x18002f790  mov     rbx, [rsp+38h+arg_0]
0x18002f795  add     rsp, 30h
0x18002f799  pop     rdi
0x18002f79a  retn
```
