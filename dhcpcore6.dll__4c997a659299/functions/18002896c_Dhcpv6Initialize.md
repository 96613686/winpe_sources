# Dhcpv6Initialize

- ea: `0x18002896c`
- end: `0x180028a5d`
- name: `Dhcpv6Initialize`
- size: `241`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001bbe0`

## callees

- `0x18001907c`
- `0x18002896c`
- `0x18002e500`
- `0x18002ecb0`
- `0x1800338c0`
- `0x180033900`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800289c7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800289c7`

## pseudocode

```c
__int64 __fastcall Dhcpv6Initialize(_DWORD *a1)
{
  __int64 v2; // rcx
  unsigned int LastErrorOrUnknown; // ebx

  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    WPP_SF_(1028, 10, WPP_f70f226ecb013479b7a542e3ca07d188_Traceguids);
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_(1028, 11, WPP_f70f226ecb013479b7a542e3ca07d188_Traceguids);
  }
  Dhcpv6GlobalFirewallReadyEvent = CreateEventW(0, 1, 0, 0);
  if ( Dhcpv6GlobalFirewallReadyEvent )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_(1028, 12, WPP_f70f226ecb013479b7a542e3ca07d188_Traceguids);
    LastErrorOrUnknown = DhcpFirewallInit();
    if ( !LastErrorOrUnknown )
    {
      if ( (xmmword_1800423E0 & 0x10) != 0 )
        WPP_SF_(1028, 13, WPP_f70f226ecb013479b7a542e3ca07d188_Traceguids);
      PdcInitialize();
      if ( a1 )
        *a1 = 1;
    }
  }
  else
  {
    LastErrorOrUnknown = GetLastErrorOrUnknown(v2);
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 14, WPP_f70f226ecb013479b7a542e3ca07d188_Traceguids, LastErrorOrUnknown);
  return LastErrorOrUnknown;
}

```

## disassembly

```asm
0x18002896c  push    rbx
0x18002896e  push    rdi
0x18002896f  push    r14
0x180028971  push    r15
0x180028973  sub     rsp, 28h
0x180028977  mov     rdi, rcx
0x18002897a  mov     al, byte ptr cs:xmmword_1800423E0
0x180028980  lea     r15, WPP_f70f226ecb013479b7a542e3ca07d188_Traceguids
0x180028987  mov     r14d, 404h
0x18002898d  test    al, 10h
0x18002898f  jz      short loc_1800289BB
0x180028991  mov     edx, 0Ah
0x180028996  mov     ecx, r14d
0x180028999  mov     r8, r15
0x18002899c  call    WPP_SF_
0x1800289a1  mov     al, byte ptr cs:xmmword_1800423E0
0x1800289a7  test    al, 10h
0x1800289a9  jz      short loc_1800289BB
0x1800289ab  mov     edx, 0Bh
0x1800289b0  mov     ecx, r14d
0x1800289b3  mov     r8, r15
0x1800289b6  call    WPP_SF_
0x1800289bb  xor     r9d, r9d; lpName
0x1800289be  xor     r8d, r8d; bInitialState
0x1800289c1  xor     ecx, ecx; lpEventAttributes
0x1800289c3  lea     edx, [r9+1]; bManualReset
0x1800289c7  call    cs:__imp_CreateEventW
0x1800289ce  nop     dword ptr [rax+rax+00h]
0x1800289d3  mov     cs:Dhcpv6GlobalFirewallReadyEvent, rax
0x1800289da  test    rax, rax
0x1800289dd  jnz     short loc_1800289E8
0x1800289df  call    GetLastErrorOrUnknown
0x1800289e4  mov     ebx, eax
0x1800289e6  jmp     short loc_180028A33
0x1800289e8  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800289ef  jz      short loc_180028A01
0x1800289f1  mov     edx, 0Ch
0x1800289f6  mov     ecx, r14d
0x1800289f9  mov     r8, r15
0x1800289fc  call    WPP_SF_
0x180028a01  call    DhcpFirewallInit
0x180028a06  mov     ebx, eax
0x180028a08  test    eax, eax
0x180028a0a  jnz     short loc_180028A33
0x180028a0c  test    byte ptr cs:xmmword_1800423E0, 10h
0x180028a13  jz      short loc_180028A23
0x180028a15  lea     edx, [rax+0Dh]
0x180028a18  mov     ecx, r14d
0x180028a1b  mov     r8, r15
0x180028a1e  call    WPP_SF_
0x180028a23  call    PdcInitialize
0x180028a28  test    rdi, rdi
0x180028a2b  jz      short loc_180028A33
0x180028a2d  mov     dword ptr [rdi], 1
0x180028a33  test    byte ptr cs:xmmword_1800423E0, 10h
0x180028a3a  jz      short loc_180028A4F
0x180028a3c  mov     edx, 0Eh
0x180028a41  mov     ecx, r14d
0x180028a44  mov     r9d, ebx
0x180028a47  mov     r8, r15
0x180028a4a  call    WPP_SF_D
0x180028a4f  mov     eax, ebx
0x180028a51  add     rsp, 28h
0x180028a55  pop     r15
0x180028a57  pop     r14
0x180028a59  pop     rdi
0x180028a5a  pop     rbx
0x180028a5b  retn
```
