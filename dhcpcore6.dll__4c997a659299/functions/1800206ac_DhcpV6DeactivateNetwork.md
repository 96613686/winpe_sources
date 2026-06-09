# DhcpV6DeactivateNetwork

- ea: `0x1800206ac`
- end: `0x18002081c`
- name: `DhcpV6DeactivateNetwork`
- size: `368`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180008a70`
- `0x180008f80`
- `0x180014070`
- `0x180014590`
- `0x180020d50`
- `0x180021150`
- `0x1800216a4`
- `0x1800218e0`
- `0x180021b58`
- `0x1800225c8`
- `0x180022b80`
- `0x180023c2c`
- `0x180025094`

## callees

- `0x180016d50`
- `0x1800206ac`
- `0x18002ec28`
- `0x18002f648`
- `0x1800311c4`
- `0x180032254`
- `0x180033900`
- `0x180033de4`

## pseudocode

```c
void __fastcall DhcpV6DeactivateNetwork(__int64 *a1, _QWORD *a2, __int64 a3, unsigned int a4)
{
  int v8; // eax
  int v9; // r9d

  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_qqdJ(a1, a2, a3, *a1, *a2, a4, *(_QWORD *)(a3 + 24));
  if ( Dhcpv6GlobalDsFeatureEnabled && *a1 )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_(1028, 0x1Bu, (ULONGLONG)WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
    if ( (unsigned int)DhcpWcmReleaseRef(a1) && (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_(1025, 0x1Cu, (ULONGLONG)WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
  }
  if ( !*a2 )
  {
    if ( !g_PdcActivationDisabled )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( !*a2 )
    {
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_(1025, 0x1Du, (ULONGLONG)WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
      goto LABEL_24;
    }
  }
  if ( *a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v8 = PdcDeactivateNetwork(*a2, a2, a4);
  *a2 = 0;
  if ( v8 )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_(1025, 0x1Eu, (ULONGLONG)WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
    MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v9 = _InterlockedDecrement(&Dhcpv6GlobalPdcCount);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    WPP_SF_d(1028, 0x1Fu, (ULONGLONG)WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, v9);
LABEL_24:
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_dJ(1028, 32, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, a4, *(_QWORD *)(a3 + 24));
  }
}

```

## disassembly

```asm
0x1800206ac  push    rbx
0x1800206ae  push    rbp
0x1800206af  push    rsi
0x1800206b0  push    rdi
0x1800206b1  push    r15
0x1800206b3  sub     rsp, 40h
0x1800206b7  mov     esi, r9d
0x1800206ba  mov     rbp, r8
0x1800206bd  mov     rbx, rdx
0x1800206c0  mov     rdi, rcx
0x1800206c3  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800206ca  jz      short loc_1800206EA
0x1800206cc  mov     rax, [r8+18h]
0x1800206d0  mov     [rsp+68h+var_38], rax
0x1800206d5  mov     rax, [rdx]
0x1800206d8  mov     [rsp+68h+var_40], r9d
0x1800206dd  mov     r9, [rcx]
0x1800206e0  mov     [rsp+68h+var_48], rax
0x1800206e5  call    WPP_SF_qqdJ
0x1800206ea  cmp     cs:Dhcpv6GlobalDsFeatureEnabled, 0
0x1800206f1  lea     r15, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x1800206f8  jz      short loc_180020742
0x1800206fa  cmp     qword ptr [rdi], 0
0x1800206fe  jz      short loc_180020742
0x180020700  test    byte ptr cs:xmmword_1800423E0, 10h
0x180020707  jz      short loc_18002071B
0x180020709  mov     edx, 1Bh
0x18002070e  mov     ecx, 404h
0x180020713  mov     r8, r15
0x180020716  call    WPP_SF_
0x18002071b  mov     rcx, rdi
0x18002071e  call    DhcpWcmReleaseRef
0x180020723  test    eax, eax
0x180020725  jz      short loc_180020742
0x180020727  test    byte ptr cs:xmmword_1800423E0, 2
0x18002072e  jz      short loc_180020742
0x180020730  mov     edx, 1Ch
0x180020735  mov     ecx, 401h
0x18002073a  mov     r8, r15
0x18002073d  call    WPP_SF_
0x180020742  cmp     qword ptr [rbx], 0
0x180020746  jnz     short loc_18002077D
0x180020748  cmp     cs:g_PdcActivationDisabled, 0
0x18002074f  jnz     short loc_180020756
0x180020751  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180020756  cmp     qword ptr [rbx], 0
0x18002075a  jnz     short loc_18002077D
0x18002075c  test    byte ptr cs:xmmword_1800423E0, 2
0x180020763  jz      loc_1800207E9
0x180020769  mov     edx, 1Dh
0x18002076e  mov     ecx, 401h
0x180020773  mov     r8, r15
0x180020776  call    WPP_SF_
0x18002077b  jmp     short loc_1800207E9
0x18002077d  cmp     qword ptr [rdi], 0
0x180020781  jz      short loc_180020788
0x180020783  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180020788  mov     rcx, [rbx]
0x18002078b  mov     r8d, esi
0x18002078e  call    PdcDeactivateNetwork
0x180020793  mov     qword ptr [rbx], 0
0x18002079a  test    eax, eax
0x18002079c  jz      short loc_1800207BE
0x18002079e  test    byte ptr cs:xmmword_1800423E0, 2
0x1800207a5  jz      short loc_1800207B9
0x1800207a7  mov     edx, 1Eh
0x1800207ac  mov     ecx, 401h
0x1800207b1  mov     r8, r15
0x1800207b4  call    WPP_SF_
0x1800207b9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800207be  or      r9d, 0FFFFFFFFh
0x1800207c2  lock xadd cs:Dhcpv6GlobalPdcCount, r9d
0x1800207cb  dec     r9d
0x1800207ce  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800207d5  jz      short loc_180020810
0x1800207d7  mov     edx, 1Fh
0x1800207dc  mov     ecx, 404h
0x1800207e1  mov     r8, r15
0x1800207e4  call    WPP_SF_d
0x1800207e9  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800207f0  jz      short loc_180020810
0x1800207f2  mov     rax, [rbp+18h]
0x1800207f6  mov     edx, 20h ; ' '
0x1800207fb  mov     ecx, 404h
0x180020800  mov     [rsp+68h+var_48], rax
0x180020805  mov     r9d, esi
0x180020808  mov     r8, r15
0x18002080b  call    WPP_SF_dJ
0x180020810  add     rsp, 40h
0x180020814  pop     r15
0x180020816  pop     rdi
0x180020817  pop     rsi
0x180020818  pop     rbp
0x180020819  pop     rbx
0x18002081a  retn
```
