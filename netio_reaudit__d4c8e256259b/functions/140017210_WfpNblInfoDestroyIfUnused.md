# WfpNblInfoDestroyIfUnused

- ea: `0x140017210`
- end: `0x1400174b1`
- name: `WfpNblInfoDestroyIfUnused`
- size: `673`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter1)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140017010`

## callees

- `0x140017210`
- `0x14001771c`
- `0x1400511ac`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140017389`
- `ntoskrnl!KeBugCheckEx` at `0x1400173cf`
- `ntoskrnl!KeBugCheckEx` at `0x140017417`
- `ntoskrnl!KeBugCheckEx` at `0x140017456`
- `ntoskrnl!KeBugCheckEx` at `0x1400174a4`
- `ntoskrnl!KeBugCheckEx` at `0x14007a9fc`
- `ntoskrnl!KeBugCheckEx` at `0x140017389`
- `ntoskrnl!KeBugCheckEx` at `0x1400173cf`
- `ntoskrnl!KeBugCheckEx` at `0x140017417`
- `ntoskrnl!KeBugCheckEx` at `0x140017456`
- `ntoskrnl!KeBugCheckEx` at `0x1400174a4`
- `ntoskrnl!KeBugCheckEx` at `0x14007a9fc`
- `ntoskrnl!MmBadPointer` at `0x140017259`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001730e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14001730e`

## pseudocode

```c
void __fastcall WfpNblInfoDestroyIfUnused(ULONG_PTR BugCheckParameter1)
{
  unsigned int *v2; // rbx
  __int64 v3; // rdx
  ULONG_PTR v4; // r8
  __int64 v5; // rsi
  __int64 v6; // rdx
  unsigned int v7; // esi
  char *v8; // rbp

  v2 = (unsigned int *)(*(_QWORD *)(BugCheckParameter1 + 224) & 0xFFFFFFFFFFFFFFFCuLL);
  if ( gWFPFeature_Firewall_042024_IsEnabled )
  {
    if ( !v2 )
      return;
    v3 = *v2;
    if ( (_DWORD)v3 != 1852859991 )
      MicrosoftTelemetryAssertTriggeredArgsMsgKM(
        BugCheckParameter1,
        v3,
        1852859991,
        "WfpNblInfoValidate: WFP_NBL_INFO_CONTAINER signature has been corrupt");
    if ( gWfpVerifierEnabled && *v2 != 1852859991 )
      KeBugCheckEx(0xC4u, (ULONG_PTR)v2, *v2, 0, 0);
  }
  else
  {
    if ( !v2 )
      return;
    if ( (gVerifierFlags & 0x2000000) != 0 && *v2 != 1852859991 )
      KeBugCheckEx(0xC4u, *(_QWORD *)(BugCheckParameter1 + 224) & 0xFFFFFFFFFFFFFFFCuLL, *v2, 0, 0);
  }
  if ( v2 != MmBadPointer )
  {
    v4 = *((_QWORD *)v2 + 4);
    if ( v4 == BugCheckParameter1 )
    {
      if ( !*((_QWORD *)v2 + 3) && !*((_QWORD *)v2 + 1) && !*((_QWORD *)v2 + 2) && !v2[10] )
      {
        v5 = *(_QWORD *)(BugCheckParameter1 + 224);
        if ( gWFPFeature_Firewall_042024_IsEnabled )
        {
          v6 = *v2;
          if ( (_DWORD)v6 != 1852859991 )
            MicrosoftTelemetryAssertTriggeredArgsMsgKM(
              BugCheckParameter1,
              v6,
              1852859991,
              "WfpNblInfoValidate: WFP_NBL_INFO_CONTAINER signature has been corrupt");
          if ( gWfpVerifierEnabled && *v2 != 1852859991 )
            KeBugCheckEx(0xC4u, (ULONG_PTR)v2, *v2, 0, 0);
        }
        else if ( (gVerifierFlags & 0x2000000) != 0 && *v2 != 1852859991 )
        {
          KeBugCheckEx(0xC4u, (ULONG_PTR)v2, *v2, 0, 0);
        }
        *v2 = -1;
        v7 = v5 & 3;
        v8 = (char *)gWfpNblInfoPool + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
        if ( !v8[176] )
          PplpLazyInitializeLookasideList((__int64)gWfpNblInfoPool, (__int64)(v8 + 64));
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v8 + 64), v2);
        *(_QWORD *)(BugCheckParameter1 + 224) = 0;
        if ( v7 )
          *(_QWORD *)(BugCheckParameter1 + 224) = v7;
      }
    }
    else if ( gWFPFeature_Firewall_042024_IsEnabled )
    {
      MicrosoftTelemetryAssertTriggeredArgsMsgKM(
        BugCheckParameter1,
        0,
        0,
        "WfpNblInfoDestroyIfUnused: the owningNbl of the nbl != nbl");
      if ( gWfpVerifierEnabled )
        KeBugCheckEx(0x146u, BugCheckParameter1, *((_QWORD *)v2 + 4), 0, 0);
    }
    else if ( (gVerifierFlags & 0x2000000) != 0 )
    {
      KeBugCheckEx(0x146u, BugCheckParameter1, v4, 0, 0);
    }
  }
}

```

## disassembly

```asm
0x140017210  mov     [rsp+arg_10], rbx
0x140017215  push    rdi
0x140017216  sub     rsp, 30h
0x14001721a  mov     rbx, [rcx+0E0h]
0x140017221  mov     rdi, rcx
0x140017224  and     rbx, 0FFFFFFFFFFFFFFFCh
0x140017228  cmp     cs:gWFPFeature_Firewall_042024_IsEnabled, 0
0x14001722f  jz      loc_1400173DC
0x140017235  test    rbx, rbx
0x140017238  jz      loc_140017339
0x14001723e  mov     edx, [rbx]
0x140017240  cmp     edx, 6E706657h
0x140017246  jnz     loc_140017350
0x14001724c  cmp     cs:gWfpVerifierEnabled, 0
0x140017253  jnz     loc_140017367
0x140017259  mov     rax, cs:MmBadPointer
0x140017260  cmp     rbx, [rax]
0x140017263  jz      loc_140017339
0x140017269  mov     r8, [rbx+20h]; BugCheckParameter2
0x14001726d  cmp     r8, rdi
0x140017270  jnz     loc_140017463
0x140017276  cmp     qword ptr [rbx+18h], 0
0x14001727b  jnz     loc_140017339
0x140017281  cmp     qword ptr [rbx+8], 0
0x140017286  jnz     loc_140017339
0x14001728c  cmp     qword ptr [rbx+10h], 0
0x140017291  jnz     loc_140017339
0x140017297  cmp     dword ptr [rbx+28h], 0
0x14001729b  jnz     loc_140017339
0x1400172a1  cmp     cs:gWFPFeature_Firewall_042024_IsEnabled, 0
0x1400172a8  mov     [rsp+38h+arg_8], rsi
0x1400172ad  mov     rsi, [rdi+0E0h]
0x1400172b4  jz      loc_140017424
0x1400172ba  mov     edx, [rbx]
0x1400172bc  cmp     edx, 6E706657h
0x1400172c2  jnz     loc_140017396
0x1400172c8  cmp     cs:gWfpVerifierEnabled, 0
0x1400172cf  jnz     loc_1400173AD
0x1400172d5  mov     dword ptr [rbx], 0FFFFFFFFh
0x1400172db  and     esi, 3
0x1400172de  mov     eax, gs:1A4h
0x1400172e6  mov     rcx, cs:gWfpNblInfoPool
0x1400172ed  mov     [rsp+38h+arg_0], rbp
0x1400172f2  lea     ebp, [rax+1]
0x1400172f5  shl     rbp, 7
0x1400172f9  add     rbp, rcx
0x1400172fc  movzx   eax, byte ptr [rbp+0B0h]
0x140017303  test    al, al
0x140017305  jz      short loc_140017345
0x140017307  mov     rdx, rbx; Entry
0x14001730a  lea     rcx, [rbp+40h]; Lookaside
0x14001730e  call    cs:__imp_ExFreeToLookasideListEx
0x140017315  nop     dword ptr [rax+rax+00h]
0x14001731a  mov     rbp, [rsp+38h+arg_0]
0x14001731f  xor     eax, eax
0x140017321  mov     [rdi+0E0h], rax
0x140017328  test    rsi, rsi
0x14001732b  jz      short loc_140017334
0x14001732d  mov     [rdi+0E0h], rsi
0x140017334  mov     rsi, [rsp+38h+arg_8]
0x140017339  mov     rbx, [rsp+38h+arg_10]
0x14001733e  add     rsp, 30h
0x140017342  pop     rdi
0x140017343  retn
0x140017345  lea     rdx, [rbp+40h]
0x140017349  call    PplpLazyInitializeLookasideList
0x14001734e  jmp     short loc_140017307
0x140017350  lea     r9, aWfpnblinfovali; "WfpNblInfoValidate: WFP_NBL_INFO_CONTAI"...
0x140017357  mov     r8d, 6E706657h
0x14001735d  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x140017362  jmp     loc_14001724C
0x140017367  mov     eax, [rbx]
0x140017369  cmp     eax, 6E706657h
0x14001736e  jz      loc_140017259
0x140017374  mov     r8d, eax; BugCheckParameter2
0x140017377  xor     r9d, r9d; BugCheckParameter3
0x14001737a  xor     eax, eax
0x14001737c  mov     rdx, rbx; BugCheckParameter1
0x14001737f  mov     ecx, 0C4h; BugCheckCode
0x140017384  mov     [rsp+38h+BugCheckParameter4], rax; BugCheckParameter4
0x140017389  call    cs:__imp_KeBugCheckEx
0x140017396  lea     r9, aWfpnblinfovali; "WfpNblInfoValidate: WFP_NBL_INFO_CONTAI"...
0x14001739d  mov     r8d, 6E706657h
0x1400173a3  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x1400173a8  jmp     loc_1400172C8
0x1400173ad  mov     eax, [rbx]
0x1400173af  cmp     eax, 6E706657h
0x1400173b4  jz      loc_1400172D5
0x1400173ba  mov     r8d, eax; BugCheckParameter2
0x1400173bd  xor     r9d, r9d; BugCheckParameter3
0x1400173c0  xor     eax, eax
0x1400173c2  mov     rdx, rbx; BugCheckParameter1
0x1400173c5  mov     ecx, 0C4h; BugCheckCode
0x1400173ca  mov     [rsp+38h+BugCheckParameter4], rax; BugCheckParameter4
0x1400173cf  call    cs:__imp_KeBugCheckEx
0x1400173dc  test    rbx, rbx
0x1400173df  jz      loc_140017339
0x1400173e5  test    cs:gVerifierFlags, 2000000h
0x1400173ef  jz      loc_140017259
0x1400173f5  mov     eax, [rbx]
0x1400173f7  cmp     eax, 6E706657h
0x1400173fc  jz      loc_140017259
0x140017402  mov     r8d, eax; BugCheckParameter2
0x140017405  xor     r9d, r9d; BugCheckParameter3
0x140017408  xor     eax, eax
0x14001740a  mov     rdx, rbx; BugCheckParameter1
0x14001740d  mov     ecx, 0C4h; BugCheckCode
0x140017412  mov     [rsp+38h+BugCheckParameter4], rax; BugCheckParameter4
0x140017417  call    cs:__imp_KeBugCheckEx
0x140017424  test    cs:gVerifierFlags, 2000000h
0x14001742e  jz      loc_1400172D5
0x140017434  mov     eax, [rbx]
0x140017436  cmp     eax, 6E706657h
0x14001743b  jz      loc_1400172D5
0x140017441  mov     r8d, eax; BugCheckParameter2
0x140017444  xor     r9d, r9d; BugCheckParameter3
0x140017447  xor     eax, eax
0x140017449  mov     rdx, rbx; BugCheckParameter1
0x14001744c  mov     ecx, 0C4h; BugCheckCode
0x140017451  mov     [rsp+38h+BugCheckParameter4], rax; BugCheckParameter4
0x140017456  call    cs:__imp_KeBugCheckEx
0x140017463  cmp     cs:gWFPFeature_Firewall_042024_IsEnabled, 0
0x14001746a  jz      loc_14007A9DA
0x140017470  lea     r9, aWfpnblinfodest; "WfpNblInfoDestroyIfUnused: the owningNb"...
0x140017477  xor     r8d, r8d
0x14001747a  xor     edx, edx
0x14001747c  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x140017481  cmp     cs:gWfpVerifierEnabled, 0
0x140017488  jz      loc_140017339
0x14001748e  mov     r8, [rbx+20h]; BugCheckParameter2
0x140017492  xor     eax, eax
0x140017494  xor     r9d, r9d; BugCheckParameter3
0x140017497  mov     [rsp+38h+BugCheckParameter4], rax; BugCheckParameter4
0x14001749c  mov     rdx, rdi; BugCheckParameter1
0x14001749f  mov     ecx, 146h; BugCheckCode
0x1400174a4  call    cs:__imp_KeBugCheckEx
0x14007a9da  test    cs:gVerifierFlags, 2000000h
0x14007a9e4  jz      loc_140017339
0x14007a9ea  xor     eax, eax
0x14007a9ec  xor     r9d, r9d; BugCheckParameter3
0x14007a9ef  mov     rdx, rdi; BugCheckParameter1
0x14007a9f2  mov     [rsp+38h+BugCheckParameter4], rax; BugCheckParameter4
0x14007a9f7  mov     ecx, 146h; BugCheckCode
0x14007a9fc  call    cs:__imp_KeBugCheckEx
```
