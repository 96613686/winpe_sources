# HvSocketXboxSetupConnection

- ea: `0x1400263d0`
- end: `0x14002672b`
- name: `HvSocketXboxSetupConnection`
- size: `859`
- prototype: `__int64 __fastcall(__int64, __int64, char)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140002f34`
- `0x140008774`
- `0x1400098f4`
- `0x14000a048`
- `0x14000b5f0`
- `0x14000bfa0`
- `0x14000bfe0`
- `0x14000c4c0`
- `0x140025c64`
- `0x1400263d0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400266fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400266fc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400266e6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400266e6`

## pseudocode

```c
__int64 __fastcall HvSocketXboxSetupConnection(__int64 a1, __int64 a2, char a3)
{
  __int64 v5; // r15
  __int64 v6; // rbx
  __int64 *v7; // r13
  int Pipe; // eax
  int v9; // edi
  int v10; // edx
  __int128 v11; // xmm1
  __int64 v12; // rcx
  __int128 v13; // xmm0
  __int64 v14; // r14
  __int64 v15; // rax
  __int64 v16; // rcx
  int v17; // eax
  signed __int64 v18; // rax
  bool v19; // cc
  signed __int64 v20; // rax
  void (__fastcall *v21)(__int64); // rax
  __int64 v23; // [rsp+20h] [rbp-89h]
  char v24; // [rsp+28h] [rbp-81h]
  __int64 v25; // [rsp+40h] [rbp-69h] BYREF
  _DWORD v26[24]; // [rsp+50h] [rbp-59h] BYREF

  memset(v26, 0, 0x58u);
  v5 = *(_QWORD *)(a2 + 736);
  v6 = 0;
  v25 = 0;
  if ( !v5 || !a3 )
  {
    v9 = -1073741808;
    if ( (unsigned int)dword_140013058 > 2 )
    {
      v10 = 197;
      goto LABEL_24;
    }
LABEL_26:
    if ( *(_QWORD *)(a2 + 696) )
    {
      *(_DWORD *)(a2 + 704) = 1;
      (*(void (**)(void))(*(_QWORD *)(v5 + 504) + 80LL))();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(v5 + 504) + 8LL))(*(_QWORD *)(a2 + 696));
      *(_QWORD *)(a2 + 696) = 0;
    }
    if ( v6 )
    {
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (const int *)"HvSocketXboxSetupConnection",
          306,
          v6,
          *(_QWORD *)(v6 + 8),
          (const int *)"Dereference object");
      v18 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v6 + 8), 0xFFFFFFFFFFFFFFFFuLL);
      v19 = v18 <= 1;
      v20 = v18 - 1;
      if ( v19 )
      {
        if ( v20 )
          __fastfail(0xEu);
        v21 = *(void (__fastcall **)(__int64))(v6 + 80);
        if ( v21 )
          v21(v6);
        if ( *(_DWORD *)(v6 + 88) == 1 )
        {
          ExFreePoolWithTag((PVOID)v6, 0x69706E56u);
        }
        else if ( *(_DWORD *)(v6 + 88) == 2 )
        {
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v6 + 96), (PVOID)v6);
        }
      }
    }
    return (unsigned int)v9;
  }
  v7 = (__int64 *)(a2 + 696);
  Pipe = HvSocketXboxCreatePipe(a2, 1, (_QWORD *)(a2 + 696));
  v9 = Pipe;
  if ( Pipe < 0 )
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointGuidError((const int *)"HvSocketXboxSetupConnection", 205, (unsigned int)Pipe, a2, a2 + 140);
    goto LABEL_26;
  }
  memset(v26, 0, 0x58u);
  v9 = VmbusTlSetupConnectionId(a2);
  if ( v9 < 0 )
  {
    if ( (unsigned int)dword_140013058 > 2 )
    {
      v10 = 215;
LABEL_24:
      v23 = a2 + 140;
      goto LABEL_25;
    }
    goto LABEL_26;
  }
  v24 = 1;
  v11 = *(_OWORD *)(a2 + 464);
  v12 = *v7;
  *(_OWORD *)&v26[9] = *(_OWORD *)(a2 + 156);
  v13 = *(_OWORD *)(a2 + 140);
  *(_OWORD *)&v26[1] = v11;
  *(_OWORD *)&v26[5] = v13;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _DWORD *, _DWORD *, char))(*(_QWORD *)(v5 + 504) + 88LL))(
         v12,
         *(_QWORD *)(v5 + 96),
         0,
         &v26[5],
         v26,
         v24);
  if ( v9 < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_26;
    v23 = a2 + 140;
    v10 = 233;
LABEL_25:
    HvsocketTraceEndpointGuidError((const int *)"HvSocketXboxSetupConnection", v10, (unsigned int)v9, a2, v23);
    goto LABEL_26;
  }
  v9 = VmbusTlCreateIrp(*(_QWORD *)(v5 + 96), &v25);
  if ( v9 < 0 )
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointGuidError((const int *)"HvSocketXboxSetupConnection", 242, (unsigned int)v9, a2, a2 + 140);
    v6 = v25;
    goto LABEL_26;
  }
  v6 = v25;
  v14 = *(_QWORD *)(v25 + 96);
  v15 = *(_QWORD *)(v14 + 184);
  *(_QWORD *)(v15 - 16) = HvsocketXboxConnectRequestCompleted;
  *(_QWORD *)(v15 - 8) = a2;
  *(_BYTE *)(v15 - 69) = -32;
  --*(_BYTE *)(v14 + 67);
  *(_QWORD *)(v14 + 184) -= 72LL;
  v16 = *v7;
  *(_QWORD *)(a2 + 688) = v6;
  v17 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)(v5 + 504) + 96LL))(v16, v14);
  v9 = v17;
  if ( v17 < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_26;
    v23 = a2 + 140;
    v10 = 264;
    goto LABEL_25;
  }
  if ( v17 != 259 )
  {
    *(_DWORD *)(v14 + 48) = v17;
    HvsocketXboxConnectRequestCompleted(0, v14, (KSPIN_LOCK *)a2);
  }
  return 259;
}

```

## disassembly

```asm
0x1400263d0  push    rbp
0x1400263d2  push    rbx
0x1400263d3  push    rsi
0x1400263d4  push    rdi
0x1400263d5  push    r12
0x1400263d7  push    r13
0x1400263d9  push    r14
0x1400263db  push    r15
0x1400263dd  lea     rbp, [rsp-1Fh]
0x1400263e2  sub     rsp, 0C8h
0x1400263e9  mov     rax, cs:__security_cookie
0x1400263f0  xor     rax, rsp
0x1400263f3  mov     [rbp+57h+var_50], rax
0x1400263f7  mov     dil, r8b
0x1400263fa  lea     rcx, [rbp+57h+var_B0]; void *
0x1400263fe  mov     rsi, rdx
0x140026401  mov     r12d, 58h ; 'X'
0x140026407  mov     r8d, r12d; Size
0x14002640a  xor     edx, edx; Val
0x14002640c  call    memset
0x140026411  mov     r15, [rsi+2E0h]
0x140026418  lea     r14, aHvsocketxboxse; "HvSocketXboxSetupConnection"
0x14002641f  xor     ebx, ebx
0x140026421  mov     [rbp+57h+var_C0], rbx
0x140026425  test    r15, r15
0x140026428  jz      loc_1400265F8
0x14002642e  test    dil, dil
0x140026431  jz      loc_1400265F8
0x140026437  lea     r13, [rsi+2B8h]
0x14002643e  mov     dl, 1
0x140026440  mov     r8, r13
0x140026443  mov     rcx, rsi
0x140026446  call    HvSocketXboxCreatePipe
0x14002644b  mov     edi, eax
0x14002644d  test    eax, eax
0x14002644f  jns     short loc_140026479
0x140026451  mov     ecx, cs:dword_140013058
0x140026457  cmp     ecx, 2
0x14002645a  jbe     loc_140026627
0x140026460  lea     rcx, [rsi+8Ch]
0x140026467  mov     r8d, eax
0x14002646a  mov     [rsp+100h+var_E0], rcx
0x14002646f  lea     edx, [r12+75h]
0x140026474  jmp     loc_14002661C
0x140026479  mov     r8, r12; Size
0x14002647c  lea     rcx, [rbp+57h+var_B0]; void *
0x140026480  xor     edx, edx; Val
0x140026482  call    memset
0x140026487  mov     rcx, rsi
0x14002648a  call    VmbusTlSetupConnectionId
0x14002648f  mov     edi, eax
0x140026491  test    eax, eax
0x140026493  jns     short loc_1400264AE
0x140026495  mov     eax, cs:dword_140013058
0x14002649b  cmp     eax, 2
0x14002649e  jbe     loc_140026627
0x1400264a4  mov     edx, 0D7h
0x1400264a9  jmp     loc_14002660D
0x1400264ae  movups  xmm0, xmmword ptr [rsi+9Ch]
0x1400264b5  lea     rcx, [rbp+57h+var_B0]
0x1400264b9  mov     [rsp+100h+var_D8], 1
0x1400264be  movups  xmm1, xmmword ptr [rsi+1D0h]
0x1400264c5  mov     [rsp+100h+var_E0], rcx
0x1400264ca  lea     r12, [rsi+8Ch]
0x1400264d1  mov     rcx, [r13+0]
0x1400264d5  lea     r9, [rbp+57h+var_9C]
0x1400264d9  movdqu  [rbp+57h+var_8C], xmm0
0x1400264de  xor     r8d, r8d
0x1400264e1  movups  xmm0, xmmword ptr [r12]
0x1400264e6  movdqu  [rbp+57h+var_AC], xmm1
0x1400264eb  movdqu  [rbp+57h+var_9C], xmm0
0x1400264f0  mov     rax, [r15+1F8h]
0x1400264f7  mov     rdx, [r15+60h]
0x1400264fb  mov     rax, [rax+58h]
0x1400264ff  call    _guard_dispatch_icall
0x140026504  mov     edi, eax
0x140026506  test    eax, eax
0x140026508  jns     short loc_140026528
0x14002650a  mov     eax, cs:dword_140013058
0x140026510  cmp     eax, 2
0x140026513  jbe     loc_140026627
0x140026519  mov     [rsp+100h+var_E0], r12
0x14002651e  mov     edx, 0E9h
0x140026523  jmp     loc_140026619
0x140026528  mov     rcx, [r15+60h]
0x14002652c  lea     rdx, [rbp+57h+var_C0]
0x140026530  call    VmbusTlCreateIrp
0x140026535  mov     edi, eax
0x140026537  test    eax, eax
0x140026539  jns     short loc_140026567
0x14002653b  mov     eax, cs:dword_140013058
0x140026541  cmp     eax, 2
0x140026544  jbe     short loc_14002655E
0x140026546  mov     r9, rsi
0x140026549  mov     [rsp+100h+var_E0], r12
0x14002654e  mov     r8d, edi
0x140026551  mov     edx, 0F2h
0x140026556  mov     rcx, r14
0x140026559  call    HvsocketTraceEndpointGuidError
0x14002655e  mov     rbx, [rbp+57h+var_C0]
0x140026562  jmp     loc_140026627
0x140026567  mov     rbx, [rbp+57h+var_C0]
0x14002656b  lea     rcx, HvsocketXboxConnectRequestCompleted
0x140026572  mov     r14, [rbx+60h]
0x140026576  mov     rdx, r14
0x140026579  mov     rax, [r14+0B8h]
0x140026580  mov     [rax-10h], rcx
0x140026584  mov     [rax-8], rsi
0x140026588  mov     byte ptr [rax-45h], 0E0h
0x14002658c  dec     byte ptr [r14+43h]
0x140026590  add     qword ptr [r14+0B8h], 0FFFFFFFFFFFFFFB8h
0x140026598  mov     rcx, [r13+0]
0x14002659c  mov     [rsi+2B0h], rbx
0x1400265a3  mov     rax, [r15+1F8h]
0x1400265aa  mov     rax, [rax+60h]
0x1400265ae  call    _guard_dispatch_icall
0x1400265b3  mov     edi, eax
0x1400265b5  test    eax, eax
0x1400265b7  jns     short loc_1400265D7
0x1400265b9  mov     eax, cs:dword_140013058
0x1400265bf  lea     r14, aHvsocketxboxse; "HvSocketXboxSetupConnection"
0x1400265c6  cmp     eax, 2
0x1400265c9  jbe     short loc_140026627
0x1400265cb  mov     [rsp+100h+var_E0], r12
0x1400265d0  mov     edx, 108h
0x1400265d5  jmp     short loc_140026619
0x1400265d7  mov     ebx, 103h
0x1400265dc  cmp     edi, ebx
0x1400265de  jz      short loc_1400265F1
0x1400265e0  mov     r8, rsi
0x1400265e3  mov     [r14+30h], edi
0x1400265e7  mov     rdx, r14
0x1400265ea  xor     ecx, ecx
0x1400265ec  call    HvsocketXboxConnectRequestCompleted
0x1400265f1  mov     edi, ebx
0x1400265f3  jmp     loc_140026708
0x1400265f8  mov     eax, cs:dword_140013058
0x1400265fe  mov     edi, 0C0000010h
0x140026603  cmp     eax, 2
0x140026606  jbe     short loc_140026627
0x140026608  mov     edx, 0C5h
0x14002660d  lea     rax, [rsi+8Ch]
0x140026614  mov     [rsp+100h+var_E0], rax
0x140026619  mov     r8d, edi
0x14002661c  mov     r9, rsi
0x14002661f  mov     rcx, r14
0x140026622  call    HvsocketTraceEndpointGuidError
0x140026627  mov     rcx, [rsi+2B8h]
0x14002662e  test    rcx, rcx
0x140026631  jz      short loc_14002666F
0x140026633  mov     dword ptr [rsi+2C0h], 1
0x14002663d  mov     rax, [r15+1F8h]
0x140026644  mov     rax, [rax+50h]
0x140026648  call    _guard_dispatch_icall
0x14002664d  mov     rax, [r15+1F8h]
0x140026654  mov     rcx, [rsi+2B8h]
0x14002665b  mov     rax, [rax+8]
0x14002665f  call    _guard_dispatch_icall
0x140026664  mov     qword ptr [rsi+2B8h], 0
0x14002666f  test    rbx, rbx
0x140026672  jz      loc_140026708
0x140026678  mov     eax, cs:dword_140013058
0x14002667e  cmp     eax, 5
0x140026681  jbe     short loc_1400266A3
0x140026683  mov     r9, [rbx+8]
0x140026687  lea     rax, aDereferenceObj; "Dereference object"
0x14002668e  mov     r8, rbx
0x140026691  mov     [rsp+100h+var_E0], rax
0x140026696  mov     edx, 132h
0x14002669b  mov     rcx, r14
0x14002669e  call    HvsocketTraceReferenceCount
0x1400266a3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400266a7  lock xadd [rbx+8], rax
0x1400266ad  sub     rax, 1
0x1400266b1  jg      short loc_140026708
0x1400266b3  test    rax, rax
0x1400266b6  jz      short loc_1400266C1
0x1400266b8  mov     ecx, 0Eh
0x1400266bd  int     29h; Win8: RtlFailFast(ecx)
0x1400266bf  jmp     short loc_140026708
0x1400266c1  mov     rax, [rbx+50h]
0x1400266c5  test    rax, rax
0x1400266c8  jz      short loc_1400266D2
0x1400266ca  mov     rcx, rbx
0x1400266cd  call    _guard_dispatch_icall
0x1400266d2  mov     ecx, [rbx+58h]
0x1400266d5  sub     ecx, 1
0x1400266d8  jz      short loc_1400266F4
0x1400266da  cmp     ecx, 1
0x1400266dd  jnz     short loc_140026708
0x1400266df  mov     rcx, [rbx+60h]; Lookaside
0x1400266e3  mov     rdx, rbx; Entry
0x1400266e6  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400266ed  nop     dword ptr [rax+rax+00h]
0x1400266f2  jmp     short loc_140026708
0x1400266f4  mov     edx, 69706E56h; Tag
0x1400266f9  mov     rcx, rbx; P
0x1400266fc  call    cs:__imp_ExFreePoolWithTag
0x140026703  nop     dword ptr [rax+rax+00h]
0x140026708  mov     eax, edi
0x14002670a  mov     rcx, [rbp+57h+var_50]
0x14002670e  xor     rcx, rsp; StackCookie
0x140026711  call    __security_check_cookie
0x140026716  add     rsp, 0C8h
0x14002671d  pop     r15
0x14002671f  pop     r14
0x140026721  pop     r13
0x140026723  pop     r12
0x140026725  pop     rdi
0x140026726  pop     rsi
0x140026727  pop     rbx
0x140026728  pop     rbp
0x140026729  retn
```
