# HvSocketXboxSetupConnection

- ea: `0x140026330`
- end: `0x14002668b`
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
- `0x140025bc4`
- `0x140026330`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002665c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002665c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140026646`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140026646`

## pseudocode

```c
__int64 __fastcall HvSocketXboxSetupConnection(__int64 a1, __int64 a2, char a3)
{
  __int64 v5; // rdx
  __int64 v6; // r15
  __int64 v7; // rbx
  __int64 *v8; // r13
  int Pipe; // eax
  int v10; // edi
  int v11; // edx
  __int128 v12; // xmm1
  __int64 v13; // rcx
  __int128 v14; // xmm0
  __int64 v15; // r14
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // eax
  signed __int64 v19; // rax
  bool v20; // cc
  signed __int64 v21; // rax
  void (__fastcall *v22)(__int64); // rax
  __int64 v24; // [rsp+20h] [rbp-89h]
  char v25; // [rsp+28h] [rbp-81h]
  __int64 v26; // [rsp+40h] [rbp-69h] BYREF
  _DWORD v27[24]; // [rsp+50h] [rbp-59h] BYREF

  memset(v27, 0, 0x58u);
  v6 = *(_QWORD *)(a2 + 736);
  v7 = 0;
  v26 = 0;
  if ( !v6 || !a3 )
  {
    v10 = -1073741808;
    if ( (unsigned int)dword_140013058 > 2 )
    {
      v11 = 197;
      goto LABEL_24;
    }
LABEL_26:
    if ( *(_QWORD *)(a2 + 696) )
    {
      *(_DWORD *)(a2 + 704) = 1;
      (*(void (**)(void))(*(_QWORD *)(v6 + 504) + 80LL))();
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)(v6 + 504) + 8LL))(*(_QWORD *)(a2 + 696));
      *(_QWORD *)(a2 + 696) = 0;
    }
    if ( v7 )
    {
      if ( (unsigned int)dword_140013058 > 5 )
        HvsocketTraceReferenceCount(
          (unsigned int)"HvSocketXboxSetupConnection",
          306,
          v7,
          *(_QWORD *)(v7 + 8),
          (__int64)"Dereference object");
      v19 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v7 + 8), 0xFFFFFFFFFFFFFFFFuLL);
      v20 = v19 <= 1;
      v21 = v19 - 1;
      if ( v20 )
      {
        if ( v21 )
          __fastfail(0xEu);
        v22 = *(void (__fastcall **)(__int64))(v7 + 80);
        if ( v22 )
          v22(v7);
        if ( *(_DWORD *)(v7 + 88) == 1 )
        {
          ExFreePoolWithTag((PVOID)v7, 0x69706E56u);
        }
        else if ( *(_DWORD *)(v7 + 88) == 2 )
        {
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v7 + 96), (PVOID)v7);
        }
      }
    }
    return (unsigned int)v10;
  }
  v8 = (__int64 *)(a2 + 696);
  LOBYTE(v5) = 1;
  Pipe = HvSocketXboxCreatePipe(a2, v5, a2 + 696);
  v10 = Pipe;
  if ( Pipe < 0 )
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointGuidError((unsigned int)"HvSocketXboxSetupConnection", 205, Pipe, a2, a2 + 140);
    goto LABEL_26;
  }
  memset(v27, 0, 0x58u);
  v10 = VmbusTlSetupConnectionId(a2);
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_140013058 > 2 )
    {
      v11 = 215;
LABEL_24:
      v24 = a2 + 140;
      goto LABEL_25;
    }
    goto LABEL_26;
  }
  v25 = 1;
  v12 = *(_OWORD *)(a2 + 464);
  v13 = *v8;
  *(_OWORD *)&v27[9] = *(_OWORD *)(a2 + 156);
  v14 = *(_OWORD *)(a2 + 140);
  *(_OWORD *)&v27[1] = v12;
  *(_OWORD *)&v27[5] = v14;
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _DWORD *, _DWORD *, char))(*(_QWORD *)(v6 + 504) + 88LL))(
          v13,
          *(_QWORD *)(v6 + 96),
          0,
          &v27[5],
          v27,
          v25);
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_26;
    v24 = a2 + 140;
    v11 = 233;
LABEL_25:
    HvsocketTraceEndpointGuidError((unsigned int)"HvSocketXboxSetupConnection", v11, v10, a2, v24);
    goto LABEL_26;
  }
  v10 = VmbusTlCreateIrp(*(_QWORD *)(v6 + 96), &v26);
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointGuidError((unsigned int)"HvSocketXboxSetupConnection", 242, v10, a2, a2 + 140);
    v7 = v26;
    goto LABEL_26;
  }
  v7 = v26;
  v15 = *(_QWORD *)(v26 + 96);
  v16 = *(_QWORD *)(v15 + 184);
  *(_QWORD *)(v16 - 16) = HvsocketXboxConnectRequestCompleted;
  *(_QWORD *)(v16 - 8) = a2;
  *(_BYTE *)(v16 - 69) = -32;
  --*(_BYTE *)(v15 + 67);
  *(_QWORD *)(v15 + 184) -= 72LL;
  v17 = *v8;
  *(_QWORD *)(a2 + 688) = v7;
  v18 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)(v6 + 504) + 96LL))(v17, v15);
  v10 = v18;
  if ( v18 < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_26;
    v24 = a2 + 140;
    v11 = 264;
    goto LABEL_25;
  }
  if ( v18 != 259 )
  {
    *(_DWORD *)(v15 + 48) = v18;
    HvsocketXboxConnectRequestCompleted(0, v15, a2);
  }
  return 259;
}

```

## disassembly

```asm
0x140026330  push    rbp
0x140026332  push    rbx
0x140026333  push    rsi
0x140026334  push    rdi
0x140026335  push    r12
0x140026337  push    r13
0x140026339  push    r14
0x14002633b  push    r15
0x14002633d  lea     rbp, [rsp-1Fh]
0x140026342  sub     rsp, 0C8h
0x140026349  mov     rax, cs:__security_cookie
0x140026350  xor     rax, rsp
0x140026353  mov     [rbp+57h+var_50], rax
0x140026357  mov     dil, r8b
0x14002635a  lea     rcx, [rbp+57h+var_B0]; void *
0x14002635e  mov     rsi, rdx
0x140026361  mov     r12d, 58h ; 'X'
0x140026367  mov     r8d, r12d; Size
0x14002636a  xor     edx, edx; Val
0x14002636c  call    memset
0x140026371  mov     r15, [rsi+2E0h]
0x140026378  lea     r14, aHvsocketxboxse; "HvSocketXboxSetupConnection"
0x14002637f  xor     ebx, ebx
0x140026381  mov     [rbp+57h+var_C0], rbx
0x140026385  test    r15, r15
0x140026388  jz      loc_140026558
0x14002638e  test    dil, dil
0x140026391  jz      loc_140026558
0x140026397  lea     r13, [rsi+2B8h]
0x14002639e  mov     dl, 1
0x1400263a0  mov     r8, r13
0x1400263a3  mov     rcx, rsi
0x1400263a6  call    HvSocketXboxCreatePipe
0x1400263ab  mov     edi, eax
0x1400263ad  test    eax, eax
0x1400263af  jns     short loc_1400263D9
0x1400263b1  mov     ecx, cs:dword_140013058
0x1400263b7  cmp     ecx, 2
0x1400263ba  jbe     loc_140026587
0x1400263c0  lea     rcx, [rsi+8Ch]
0x1400263c7  mov     r8d, eax
0x1400263ca  mov     [rsp+100h+var_E0], rcx
0x1400263cf  lea     edx, [r12+75h]
0x1400263d4  jmp     loc_14002657C
0x1400263d9  mov     r8, r12; Size
0x1400263dc  lea     rcx, [rbp+57h+var_B0]; void *
0x1400263e0  xor     edx, edx; Val
0x1400263e2  call    memset
0x1400263e7  mov     rcx, rsi
0x1400263ea  call    VmbusTlSetupConnectionId
0x1400263ef  mov     edi, eax
0x1400263f1  test    eax, eax
0x1400263f3  jns     short loc_14002640E
0x1400263f5  mov     eax, cs:dword_140013058
0x1400263fb  cmp     eax, 2
0x1400263fe  jbe     loc_140026587
0x140026404  mov     edx, 0D7h
0x140026409  jmp     loc_14002656D
0x14002640e  movups  xmm0, xmmword ptr [rsi+9Ch]
0x140026415  lea     rcx, [rbp+57h+var_B0]
0x140026419  mov     [rsp+100h+var_D8], 1
0x14002641e  movups  xmm1, xmmword ptr [rsi+1D0h]
0x140026425  mov     [rsp+100h+var_E0], rcx
0x14002642a  lea     r12, [rsi+8Ch]
0x140026431  mov     rcx, [r13+0]
0x140026435  lea     r9, [rbp+57h+var_9C]
0x140026439  movdqu  [rbp+57h+var_8C], xmm0
0x14002643e  xor     r8d, r8d
0x140026441  movups  xmm0, xmmword ptr [r12]
0x140026446  movdqu  [rbp+57h+var_AC], xmm1
0x14002644b  movdqu  [rbp+57h+var_9C], xmm0
0x140026450  mov     rax, [r15+1F8h]
0x140026457  mov     rdx, [r15+60h]
0x14002645b  mov     rax, [rax+58h]
0x14002645f  call    _guard_dispatch_icall
0x140026464  mov     edi, eax
0x140026466  test    eax, eax
0x140026468  jns     short loc_140026488
0x14002646a  mov     eax, cs:dword_140013058
0x140026470  cmp     eax, 2
0x140026473  jbe     loc_140026587
0x140026479  mov     [rsp+100h+var_E0], r12
0x14002647e  mov     edx, 0E9h
0x140026483  jmp     loc_140026579
0x140026488  mov     rcx, [r15+60h]
0x14002648c  lea     rdx, [rbp+57h+var_C0]
0x140026490  call    VmbusTlCreateIrp
0x140026495  mov     edi, eax
0x140026497  test    eax, eax
0x140026499  jns     short loc_1400264C7
0x14002649b  mov     eax, cs:dword_140013058
0x1400264a1  cmp     eax, 2
0x1400264a4  jbe     short loc_1400264BE
0x1400264a6  mov     r9, rsi
0x1400264a9  mov     [rsp+100h+var_E0], r12
0x1400264ae  mov     r8d, edi
0x1400264b1  mov     edx, 0F2h
0x1400264b6  mov     rcx, r14
0x1400264b9  call    HvsocketTraceEndpointGuidError
0x1400264be  mov     rbx, [rbp+57h+var_C0]
0x1400264c2  jmp     loc_140026587
0x1400264c7  mov     rbx, [rbp+57h+var_C0]
0x1400264cb  lea     rcx, HvsocketXboxConnectRequestCompleted
0x1400264d2  mov     r14, [rbx+60h]
0x1400264d6  mov     rdx, r14
0x1400264d9  mov     rax, [r14+0B8h]
0x1400264e0  mov     [rax-10h], rcx
0x1400264e4  mov     [rax-8], rsi
0x1400264e8  mov     byte ptr [rax-45h], 0E0h
0x1400264ec  dec     byte ptr [r14+43h]
0x1400264f0  add     qword ptr [r14+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400264f8  mov     rcx, [r13+0]
0x1400264fc  mov     [rsi+2B0h], rbx
0x140026503  mov     rax, [r15+1F8h]
0x14002650a  mov     rax, [rax+60h]
0x14002650e  call    _guard_dispatch_icall
0x140026513  mov     edi, eax
0x140026515  test    eax, eax
0x140026517  jns     short loc_140026537
0x140026519  mov     eax, cs:dword_140013058
0x14002651f  lea     r14, aHvsocketxboxse; "HvSocketXboxSetupConnection"
0x140026526  cmp     eax, 2
0x140026529  jbe     short loc_140026587
0x14002652b  mov     [rsp+100h+var_E0], r12
0x140026530  mov     edx, 108h
0x140026535  jmp     short loc_140026579
0x140026537  mov     ebx, 103h
0x14002653c  cmp     edi, ebx
0x14002653e  jz      short loc_140026551
0x140026540  mov     r8, rsi
0x140026543  mov     [r14+30h], edi
0x140026547  mov     rdx, r14
0x14002654a  xor     ecx, ecx
0x14002654c  call    HvsocketXboxConnectRequestCompleted
0x140026551  mov     edi, ebx
0x140026553  jmp     loc_140026668
0x140026558  mov     eax, cs:dword_140013058
0x14002655e  mov     edi, 0C0000010h
0x140026563  cmp     eax, 2
0x140026566  jbe     short loc_140026587
0x140026568  mov     edx, 0C5h
0x14002656d  lea     rax, [rsi+8Ch]
0x140026574  mov     [rsp+100h+var_E0], rax
0x140026579  mov     r8d, edi
0x14002657c  mov     r9, rsi
0x14002657f  mov     rcx, r14
0x140026582  call    HvsocketTraceEndpointGuidError
0x140026587  mov     rcx, [rsi+2B8h]
0x14002658e  test    rcx, rcx
0x140026591  jz      short loc_1400265CF
0x140026593  mov     dword ptr [rsi+2C0h], 1
0x14002659d  mov     rax, [r15+1F8h]
0x1400265a4  mov     rax, [rax+50h]
0x1400265a8  call    _guard_dispatch_icall
0x1400265ad  mov     rax, [r15+1F8h]
0x1400265b4  mov     rcx, [rsi+2B8h]
0x1400265bb  mov     rax, [rax+8]
0x1400265bf  call    _guard_dispatch_icall
0x1400265c4  mov     qword ptr [rsi+2B8h], 0
0x1400265cf  test    rbx, rbx
0x1400265d2  jz      loc_140026668
0x1400265d8  mov     eax, cs:dword_140013058
0x1400265de  cmp     eax, 5
0x1400265e1  jbe     short loc_140026603
0x1400265e3  mov     r9, [rbx+8]
0x1400265e7  lea     rax, aDereferenceObj; "Dereference object"
0x1400265ee  mov     r8, rbx
0x1400265f1  mov     [rsp+100h+var_E0], rax
0x1400265f6  mov     edx, 132h
0x1400265fb  mov     rcx, r14
0x1400265fe  call    HvsocketTraceReferenceCount
0x140026603  or      rax, 0FFFFFFFFFFFFFFFFh
0x140026607  lock xadd [rbx+8], rax
0x14002660d  sub     rax, 1
0x140026611  jg      short loc_140026668
0x140026613  test    rax, rax
0x140026616  jz      short loc_140026621
0x140026618  mov     ecx, 0Eh
0x14002661d  int     29h; Win8: RtlFailFast(ecx)
0x14002661f  jmp     short loc_140026668
0x140026621  mov     rax, [rbx+50h]
0x140026625  test    rax, rax
0x140026628  jz      short loc_140026632
0x14002662a  mov     rcx, rbx
0x14002662d  call    _guard_dispatch_icall
0x140026632  mov     ecx, [rbx+58h]
0x140026635  sub     ecx, 1
0x140026638  jz      short loc_140026654
0x14002663a  cmp     ecx, 1
0x14002663d  jnz     short loc_140026668
0x14002663f  mov     rcx, [rbx+60h]; Lookaside
0x140026643  mov     rdx, rbx; Entry
0x140026646  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002664d  nop     dword ptr [rax+rax+00h]
0x140026652  jmp     short loc_140026668
0x140026654  mov     edx, 69706E56h; Tag
0x140026659  mov     rcx, rbx; P
0x14002665c  call    cs:__imp_ExFreePoolWithTag
0x140026663  nop     dword ptr [rax+rax+00h]
0x140026668  mov     eax, edi
0x14002666a  mov     rcx, [rbp+57h+var_50]
0x14002666e  xor     rcx, rsp; StackCookie
0x140026671  call    __security_check_cookie
0x140026676  add     rsp, 0C8h
0x14002667d  pop     r15
0x14002667f  pop     r14
0x140026681  pop     r13
0x140026683  pop     r12
0x140026685  pop     rdi
0x140026686  pop     rsi
0x140026687  pop     rbx
0x140026688  pop     rbp
0x140026689  retn
```
