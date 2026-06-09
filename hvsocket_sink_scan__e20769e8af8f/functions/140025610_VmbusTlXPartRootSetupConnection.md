# VmbusTlXPartRootSetupConnection

- ea: `0x140025610`
- end: `0x140025a02`
- name: `VmbusTlXPartRootSetupConnection`
- size: `1010`
- prototype: `__int64 __fastcall(__int64, __int64, char)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140002f34`
- `0x140008774`
- `0x1400098f4`
- `0x14000a048`
- `0x14000af30`
- `0x14000bfa0`
- `0x14000bfe0`
- `0x14000c1c0`
- `0x14000c4c0`
- `0x140024e3c`
- `0x140025610`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400259b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400259b2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002599c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002599c`

## pseudocode

```c
__int64 __fastcall VmbusTlXPartRootSetupConnection(__int64 a1, __int64 a2, char a3)
{
  __int64 v5; // rdi
  _QWORD *v6; // r15
  __int64 v7; // rdx
  int v8; // esi
  int v9; // edx
  _QWORD *v10; // r13
  int Pipe; // eax
  __int128 v12; // xmm1
  int v13; // eax
  __int128 v14; // xmm0
  __int64 v15; // r14
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // eax
  signed __int64 v19; // rax
  bool v20; // cc
  signed __int64 v21; // rax
  void (__fastcall *v22)(__int64, __int64); // rax
  __int64 v24; // [rsp+20h] [rbp-E0h]
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v26[76]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD Src[2]; // [rsp+180h] [rbp+80h] BYREF
  int v28; // [rsp+1A0h] [rbp+A0h]

  memset(v26, 0, 0x128u);
  v5 = 0;
  v6 = *(_QWORD **)(a2 + 736);
  v28 = *(_DWORD *)L"r";
  v25 = 0;
  Src[0] = *(_OWORD *)L"GuestHostProvider";
  v7 = 1;
  Src[1] = *(_OWORD *)L"tProvider";
  if ( !v6 )
  {
    v8 = -1073741808;
    if ( (unsigned int)dword_140013058 <= 2 )
    {
LABEL_25:
      if ( *(_QWORD *)(a2 + 696) )
      {
        *(_DWORD *)(a2 + 704) = 1;
        (*(void (**)(void))(v6[63] + 80LL))();
        (*(void (__fastcall **)(_QWORD))(v6[63] + 8LL))(*(_QWORD *)(a2 + 696));
        *(_QWORD *)(a2 + 696) = 0;
      }
      if ( v5 )
      {
        if ( (unsigned int)dword_140013058 > 5 )
          HvsocketTraceReferenceCount(
            (unsigned int)"VmbusTlXPartRootSetupConnection",
            334,
            v5,
            *(_QWORD *)(v5 + 8),
            (__int64)"Dereference object");
        v19 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v5 + 8), 0xFFFFFFFFFFFFFFFFuLL);
        v20 = v19 <= 1;
        v21 = v19 - 1;
        if ( v20 )
        {
          if ( v21 )
            __fastfail(0xEu);
          v22 = *(void (__fastcall **)(__int64, __int64))(v5 + 80);
          if ( v22 )
            v22(v5, v7);
          if ( *(_DWORD *)(v5 + 88) == 1 )
          {
            ExFreePoolWithTag((PVOID)v5, 0x69706E56u);
          }
          else if ( *(_DWORD *)(v5 + 88) == 2 )
          {
            ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v5 + 96), (PVOID)v5);
          }
        }
      }
      return (unsigned int)v8;
    }
    v9 = 209;
    v24 = a2 + 140;
    goto LABEL_23;
  }
  v10 = (_QWORD *)(a2 + 696);
  Pipe = VmbusTlXPartCreatePipe(a2, 1, (_QWORD *)(a2 + 696));
  v8 = Pipe;
  if ( Pipe < 0 )
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointGuidError((unsigned int)"VmbusTlXPartRootSetupConnection", 217, Pipe, a2, a2 + 140);
    goto LABEL_24;
  }
  memset(v26, 0, 0x128u);
  v8 = VmbusTlSetupConnectionId(a2);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_140013058 > 2 )
    {
      v9 = 227;
      v24 = a2 + 140;
LABEL_23:
      HvsocketTraceEndpointGuidError((unsigned int)"VmbusTlXPartRootSetupConnection", v9, v8, a2, v24);
    }
LABEL_24:
    v7 = 1;
    goto LABEL_25;
  }
  LOWORD(v26[2]) = 257;
  v12 = *(_OWORD *)(a2 + 464);
  *(_OWORD *)&v26[3] = *(_OWORD *)(a2 + 156);
  *(_OWORD *)&v26[7] = v12;
  if ( *(_BYTE *)(a2 + 186) )
    HIWORD(v26[12]) |= 1u;
  v13 = *(_DWORD *)(a2 + 516);
  v14 = *(_OWORD *)(a2 + 896);
  *(_DWORD *)((char *)&v26[13] + 2) = 1;
  LOBYTE(v26[13]) = a3 != 0;
  BYTE1(v26[13]) = (v13 & 4) != 0;
  *(_OWORD *)((char *)&v26[14] + 2) = v14;
  memmove((char *)&v26[41] + 2, Src, 0x22u);
  LOWORD(v26[41]) = 17;
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _DWORD *, char))(v6[63] + 88LL))(
         *v10,
         v6[12],
         v6[52],
         a2 + 140,
         v26,
         1);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_24;
    v9 = 260;
LABEL_22:
    v24 = a2 + 140;
    goto LABEL_23;
  }
  v8 = VmbusTlCreateIrp(v6[12], &v25);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointGuidError((unsigned int)"VmbusTlXPartRootSetupConnection", 269, v8, a2, a2 + 140);
    v5 = v25;
    goto LABEL_24;
  }
  v5 = v25;
  v15 = *(_QWORD *)(v25 + 96);
  v16 = *(_QWORD *)(v15 + 184);
  *(_QWORD *)(v16 - 16) = VmbusTlXPartRootConnectRequestCompleted;
  *(_QWORD *)(v16 - 8) = a2;
  *(_BYTE *)(v16 - 69) = -32;
  --*(_BYTE *)(v15 + 67);
  *(_QWORD *)(v15 + 184) -= 72LL;
  v17 = *v10;
  *(_QWORD *)(a2 + 688) = v5;
  v18 = (*(__int64 (__fastcall **)(__int64, __int64))(v6[63] + 96LL))(v17, v15);
  v8 = v18;
  if ( v18 < 0 )
  {
    if ( (unsigned int)dword_140013058 <= 2 )
      goto LABEL_24;
    v9 = 292;
    goto LABEL_22;
  }
  if ( v18 != 259 )
  {
    *(_DWORD *)(v15 + 48) = v18;
    VmbusTlXPartRootConnectRequestCompleted(0, v15, a2);
  }
  return 259;
}

```

## disassembly

```asm
0x140025610  push    rbp
0x140025612  push    rbx
0x140025613  push    rsi
0x140025614  push    rdi
0x140025615  push    r12
0x140025617  push    r13
0x140025619  push    r14
0x14002561b  push    r15
0x14002561d  lea     rbp, [rsp-0B8h]
0x140025625  sub     rsp, 1B8h
0x14002562c  mov     rax, cs:__security_cookie
0x140025633  xor     rax, rsp
0x140025636  mov     [rbp+0F0h+var_48], rax
0x14002563d  mov     r12b, r8b
0x140025640  lea     rcx, [rsp+1F0h+var_1A0]; void *
0x140025645  mov     rbx, rdx
0x140025648  mov     r8d, 128h; Size
0x14002564e  xor     edx, edx; Val
0x140025650  call    memset
0x140025655  mov     eax, dword ptr cs:aGuesthostprovi+20h; "r"
0x14002565b  xor     edi, edi
0x14002565d  movups  xmm0, xmmword ptr cs:aGuesthostprovi; "GuestHostProvider"
0x140025664  mov     r15, [rbx+2E0h]
0x14002566b  movups  xmm1, xmmword ptr cs:aGuesthostprovi+10h; "tProvider"
0x140025672  mov     [rbp+0F0h+var_50], eax
0x140025678  xor     eax, eax
0x14002567a  mov     dword ptr [rsp+1F0h+var_1B0+4], eax
0x14002567e  mov     [rsp+40h], rdi
0x140025683  movups  [rbp+0F0h+Src], xmm0
0x14002568a  lea     r14d, [rax+22h]
0x14002568e  lea     edx, [rax+1]
0x140025691  movups  [rbp+0F0h+var_60], xmm1
0x140025698  test    r15, r15
0x14002569b  jnz     short loc_1400256C7
0x14002569d  mov     eax, cs:dword_140013058
0x1400256a3  mov     esi, 0C0000010h
0x1400256a8  cmp     eax, 2
0x1400256ab  jbe     loc_1400258DD
0x1400256b1  lea     rax, [rbx+8Ch]
0x1400256b8  mov     edx, 0D1h
0x1400256bd  mov     [rsp+1F0h+var_1D0], rax
0x1400256c2  jmp     loc_1400258C6
0x1400256c7  lea     r13, [rbx+2B8h]
0x1400256ce  mov     rcx, rbx
0x1400256d1  mov     r8, r13
0x1400256d4  call    VmbusTlXPartCreatePipe
0x1400256d9  mov     esi, eax
0x1400256db  test    eax, eax
0x1400256dd  jns     short loc_140025707
0x1400256df  mov     ecx, cs:dword_140013058
0x1400256e5  cmp     ecx, 2
0x1400256e8  jbe     loc_1400258D8
0x1400256ee  lea     rcx, [rbx+8Ch]
0x1400256f5  mov     r8d, eax
0x1400256f8  mov     [rsp+1F0h+var_1D0], rcx
0x1400256fd  mov     edx, 0D9h
0x140025702  jmp     loc_1400258C9
0x140025707  xor     edx, edx; Val
0x140025709  lea     rcx, [rsp+1F0h+var_1A0]; void *
0x14002570e  mov     r8d, 128h; Size
0x140025714  call    memset
0x140025719  mov     rcx, rbx
0x14002571c  call    VmbusTlSetupConnectionId
0x140025721  mov     esi, eax
0x140025723  test    eax, eax
0x140025725  jns     short loc_14002574C
0x140025727  mov     eax, cs:dword_140013058
0x14002572d  cmp     eax, 2
0x140025730  jbe     loc_1400258D8
0x140025736  lea     rax, [rbx+8Ch]
0x14002573d  mov     edx, 0E3h
0x140025742  mov     [rsp+1F0h+var_1D0], rax
0x140025747  jmp     loc_1400258C6
0x14002574c  mov     esi, 1
0x140025751  mov     [rsp+1F0h+var_198], 101h
0x140025758  movups  xmm0, xmmword ptr [rbx+9Ch]
0x14002575f  movups  xmm1, xmmword ptr [rbx+1D0h]
0x140025766  movdqu  [rsp+1F0h+var_194], xmm0
0x14002576c  movdqu  [rsp+1F0h+var_184], xmm1
0x140025772  cmp     [rbx+0BAh], dil
0x140025779  jz      short loc_14002577F
0x14002577b  or      [rbp+0F0h+var_16E], si
0x14002577f  mov     eax, [rbx+204h]
0x140025785  lea     rdx, [rbp+0F0h+Src]; Src
0x14002578c  movups  xmm0, xmmword ptr [rbx+380h]
0x140025793  test    r12b, r12b
0x140025796  movzx   r8d, r14w; Size
0x14002579a  lea     rcx, [rbp+0F0h+var_FA]; void *
0x14002579e  mov     [rbp+0F0h+var_16A], esi
0x1400257a1  setnz   [rbp+0F0h+var_16C]
0x1400257a5  shr     eax, 2
0x1400257a8  and     al, sil
0x1400257ab  mov     [rbp+0F0h+var_16B], al
0x1400257ae  movdqu  [rbp+0F0h+var_166], xmm0
0x1400257b3  call    memmove
0x1400257b8  lea     rcx, [rsp+1F0h+var_1A0]
0x1400257bd  shr     r14w, 1
0x1400257c1  mov     [rbp+0F0h+var_FC], r14w
0x1400257c6  lea     r12, [rbx+8Ch]
0x1400257cd  mov     rax, [r15+1F8h]
0x1400257d4  mov     r9, r12
0x1400257d7  mov     r8, [r15+1A0h]
0x1400257de  mov     rdx, [r15+60h]
0x1400257e2  mov     [rsp+1F0h+var_1C8], sil
0x1400257e7  mov     rax, [rax+58h]
0x1400257eb  mov     [rsp+1F0h+var_1D0], rcx
0x1400257f0  mov     rcx, [r13+0]
0x1400257f4  call    _guard_dispatch_icall
0x1400257f9  mov     esi, eax
0x1400257fb  test    eax, eax
0x1400257fd  jns     short loc_140025818
0x1400257ff  mov     eax, cs:dword_140013058
0x140025805  cmp     eax, 2
0x140025808  jbe     loc_1400258D8
0x14002580e  mov     edx, 104h
0x140025813  jmp     loc_1400258C1
0x140025818  mov     rcx, [r15+60h]
0x14002581c  lea     rdx, [rsp+1F0h+var_1B0]
0x140025821  call    VmbusTlCreateIrp
0x140025826  mov     esi, eax
0x140025828  test    eax, eax
0x14002582a  jns     short loc_14002585A
0x14002582c  mov     eax, cs:dword_140013058
0x140025832  cmp     eax, 2
0x140025835  jbe     short loc_140025853
0x140025837  mov     r9, rbx
0x14002583a  mov     [rsp+1F0h+var_1D0], r12
0x14002583f  mov     r8d, esi
0x140025842  lea     rcx, aVmbustlxpartro_0; "VmbusTlXPartRootSetupConnection"
0x140025849  mov     edx, 10Dh
0x14002584e  call    HvsocketTraceEndpointGuidError
0x140025853  mov     rdi, [rsp+1F0h+var_1B0]
0x140025858  jmp     short loc_1400258D8
0x14002585a  mov     rdi, [rsp+1F0h+var_1B0]
0x14002585f  lea     rcx, VmbusTlXPartRootConnectRequestCompleted
0x140025866  mov     r14, [rdi+60h]
0x14002586a  mov     rdx, r14
0x14002586d  mov     rax, [r14+0B8h]
0x140025874  mov     [rax-10h], rcx
0x140025878  mov     [rax-8], rbx
0x14002587c  mov     byte ptr [rax-45h], 0E0h
0x140025880  dec     byte ptr [r14+43h]
0x140025884  add     qword ptr [r14+0B8h], 0FFFFFFFFFFFFFFB8h
0x14002588c  mov     rcx, [r13+0]
0x140025890  mov     [rbx+2B0h], rdi
0x140025897  mov     rax, [r15+1F8h]
0x14002589e  mov     rax, [rax+60h]
0x1400258a2  call    _guard_dispatch_icall
0x1400258a7  mov     esi, eax
0x1400258a9  test    eax, eax
0x1400258ab  jns     loc_1400259C0
0x1400258b1  mov     eax, cs:dword_140013058
0x1400258b7  cmp     eax, 2
0x1400258ba  jbe     short loc_1400258D8
0x1400258bc  mov     edx, 124h
0x1400258c1  mov     [rsp+1F0h+var_1D0], r12
0x1400258c6  mov     r8d, esi
0x1400258c9  mov     r9, rbx
0x1400258cc  lea     rcx, aVmbustlxpartro_0; "VmbusTlXPartRootSetupConnection"
0x1400258d3  call    HvsocketTraceEndpointGuidError
0x1400258d8  mov     edx, 1
0x1400258dd  mov     rcx, [rbx+2B8h]
0x1400258e4  test    rcx, rcx
0x1400258e7  jz      short loc_140025921
0x1400258e9  mov     [rbx+2C0h], edx
0x1400258ef  mov     rax, [r15+1F8h]
0x1400258f6  mov     rax, [rax+50h]
0x1400258fa  call    _guard_dispatch_icall
0x1400258ff  mov     rax, [r15+1F8h]
0x140025906  mov     rcx, [rbx+2B8h]
0x14002590d  mov     rax, [rax+8]
0x140025911  call    _guard_dispatch_icall
0x140025916  mov     qword ptr [rbx+2B8h], 0
0x140025921  test    rdi, rdi
0x140025924  jz      loc_1400259DC
0x14002592a  mov     eax, cs:dword_140013058
0x140025930  cmp     eax, 5
0x140025933  jbe     short loc_140025959
0x140025935  mov     r9, [rdi+8]
0x140025939  lea     rax, aDereferenceObj; "Dereference object"
0x140025940  mov     r8, rdi
0x140025943  mov     [rsp+1F0h+var_1D0], rax
0x140025948  mov     edx, 14Eh
0x14002594d  lea     rcx, aVmbustlxpartro_0; "VmbusTlXPartRootSetupConnection"
0x140025954  call    HvsocketTraceReferenceCount
0x140025959  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002595d  lock xadd [rdi+8], rax
0x140025963  sub     rax, 1
0x140025967  jg      short loc_1400259DC
0x140025969  test    rax, rax
0x14002596c  jz      short loc_140025977
0x14002596e  mov     ecx, 0Eh
0x140025973  int     29h; Win8: RtlFailFast(ecx)
0x140025975  jmp     short loc_1400259DC
0x140025977  mov     rax, [rdi+50h]
0x14002597b  test    rax, rax
0x14002597e  jz      short loc_140025988
0x140025980  mov     rcx, rdi
0x140025983  call    _guard_dispatch_icall
0x140025988  mov     ecx, [rdi+58h]
0x14002598b  sub     ecx, 1
0x14002598e  jz      short loc_1400259AA
0x140025990  cmp     ecx, 1
0x140025993  jnz     short loc_1400259DC
0x140025995  mov     rcx, [rdi+60h]; Lookaside
0x140025999  mov     rdx, rdi; Entry
0x14002599c  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400259a3  nop     dword ptr [rax+rax+00h]
0x1400259a8  jmp     short loc_1400259DC
0x1400259aa  mov     edx, 69706E56h; Tag
0x1400259af  mov     rcx, rdi; P
0x1400259b2  call    cs:__imp_ExFreePoolWithTag
0x1400259b9  nop     dword ptr [rax+rax+00h]
0x1400259be  jmp     short loc_1400259DC
0x1400259c0  mov     edi, 103h
0x1400259c5  cmp     esi, edi
0x1400259c7  jz      short loc_1400259DA
0x1400259c9  mov     r8, rbx
0x1400259cc  mov     [r14+30h], esi
0x1400259d0  mov     rdx, r14
0x1400259d3  xor     ecx, ecx
0x1400259d5  call    VmbusTlXPartRootConnectRequestCompleted
0x1400259da  mov     esi, edi
0x1400259dc  mov     eax, esi
0x1400259de  mov     rcx, [rbp+0F0h+var_48]
0x1400259e5  xor     rcx, rsp; StackCookie
0x1400259e8  call    __security_check_cookie
0x1400259ed  add     rsp, 1B8h
0x1400259f4  pop     r15
0x1400259f6  pop     r14
0x1400259f8  pop     r13
0x1400259fa  pop     r12
0x1400259fc  pop     rdi
0x1400259fd  pop     rsi
0x1400259fe  pop     rbx
0x1400259ff  pop     rbp
0x140025a00  retn
```
