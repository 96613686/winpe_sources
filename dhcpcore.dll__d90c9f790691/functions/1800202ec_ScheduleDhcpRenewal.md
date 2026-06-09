# ScheduleDhcpRenewal

- ea: `0x1800202ec`
- end: `0x1800203fb`
- name: `ScheduleDhcpRenewal`
- size: `271`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024ff8`
- `0x1800259f4`
- `0x18002ed30`
- `0x180031c6c`
- `0x1800327f0`
- `0x180032f50`
- `0x18003f2d0`
- `0x18003ff30`
- `0x1800407c0`
- `0x180040dc4`

## callees

- `0x1800197f0`
- `0x18001f0d8`
- `0x18001f100`
- `0x1800202ec`
- `0x180020404`
- `0x1800251a4`
- `0x18004984c`
- `0x18004d1e0`
- `0x18004d4c0`
- `0x18004dbc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800203e2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800203e2`

## pseudocode

```c
__int64 __fastcall ScheduleDhcpRenewal(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  unsigned int v8; // edi
  unsigned int IsMachineInCs; // r15d
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  unsigned int IsMachineInDs; // r12d

  v8 = 0;
  IsMachineInCs = DhcpIsMachineInCs();
  IsMachineInDs = DhcpIsMachineInDs();
  if ( *(_DWORD *)(v11 + 816) )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF__guid_(v11, v10, v12, v11 + 2112);
  }
  else
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_q(1028, 24, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids, *(_QWORD *)(a1 + 24));
    if ( (unsigned int)DhcpStandbyCheckRenewalAllowed(a1 + 2016, IsMachineInCs, IsMachineInDs) )
    {
      TrySetRenewalFunction(a1, a3, a4);
      if ( (xmmword_1800616A0 & 0x10) != 0 )
        WPP_SF_dJ(1028, 26, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids, a2, *(_QWORD *)(a1 + 24));
      ScheduleWakeUp(a1, a2);
      return SetEvent(DhcpGlobalRecomputeTimerEvent);
    }
    else if ( (xmmword_1800616A0 & 0x10) != 0 )
    {
      WPP_SF_(1028, 25, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800202ec  push    rbx
0x1800202ee  push    rbp
0x1800202ef  push    rsi
0x1800202f0  push    rdi
0x1800202f1  push    r12
0x1800202f3  push    r14
0x1800202f5  push    r15
0x1800202f7  sub     rsp, 30h
0x1800202fb  mov     rbp, r9
0x1800202fe  mov     r14, r8
0x180020301  mov     esi, edx
0x180020303  mov     rbx, rcx
0x180020306  xor     edi, edi
0x180020308  call    DhcpIsMachineInCs
0x18002030d  mov     r15d, eax
0x180020310  call    DhcpIsMachineInDs
0x180020315  mov     r12d, eax
0x180020318  mov     eax, [rcx+330h]
0x18002031e  test    eax, eax
0x180020320  jz      short loc_180020340
0x180020322  test    byte ptr cs:xmmword_1800616A0, 10h
0x180020329  jz      loc_1800203EA
0x18002032f  lea     r9, [rcx+840h]
0x180020336  call    WPP_SF__guid_
0x18002033b  jmp     loc_1800203EA
0x180020340  test    byte ptr cs:xmmword_1800616A0, 10h
0x180020347  jz      short loc_180020363
0x180020349  mov     r9, [rbx+18h]
0x18002034d  lea     r8, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids
0x180020354  mov     edx, 18h
0x180020359  mov     ecx, 404h
0x18002035e  call    WPP_SF_q
0x180020363  lea     rcx, [rbx+7E0h]
0x18002036a  mov     r8d, r12d
0x18002036d  mov     edx, r15d
0x180020370  call    DhcpStandbyCheckRenewalAllowed
0x180020375  test    eax, eax
0x180020377  jnz     short loc_180020398
0x180020379  test    byte ptr cs:xmmword_1800616A0, 10h
0x180020380  jz      short loc_1800203EA
0x180020382  lea     edx, [rax+19h]
0x180020385  mov     ecx, 404h
0x18002038a  lea     r8, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids
0x180020391  call    WPP_SF_
0x180020396  jmp     short loc_1800203EA
0x180020398  mov     r8, rbp
0x18002039b  mov     rdx, r14
0x18002039e  mov     rcx, rbx
0x1800203a1  call    TrySetRenewalFunction
0x1800203a6  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800203ad  jz      short loc_1800203D1
0x1800203af  mov     rax, [rbx+18h]
0x1800203b3  lea     r8, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids
0x1800203ba  mov     edx, 1Ah
0x1800203bf  mov     [rsp+68h+var_48], rax
0x1800203c4  mov     ecx, 404h
0x1800203c9  mov     r9d, esi
0x1800203cc  call    WPP_SF_dJ
0x1800203d1  mov     edx, esi
0x1800203d3  mov     rcx, rbx
0x1800203d6  call    ScheduleWakeUp
0x1800203db  mov     rcx, cs:DhcpGlobalRecomputeTimerEvent; hEvent
0x1800203e2  call    cs:__imp_SetEvent
0x1800203e8  mov     edi, eax
0x1800203ea  mov     eax, edi
0x1800203ec  add     rsp, 30h
0x1800203f0  pop     r15
0x1800203f2  pop     r14
0x1800203f4  pop     r12
0x1800203f6  pop     rdi
0x1800203f7  pop     rsi
0x1800203f8  pop     rbp
0x1800203f9  pop     rbx
0x1800203fa  retn
```
