# VmbusTlXPartRootSetupConnection

- ea: `0x1400256b0`
- end: `0x140025aa2`
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
- `0x140024edc`
- `0x1400256b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140025a52`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025a52`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025a3c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140025a3c`

## pseudocode

```c
__int64 __fastcall VmbusTlXPartRootSetupConnection(__int64 a1, __int64 a2, char a3)
{
  __int64 v5; // rdi
  __int64 *v6; // r15
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
  v6 = *(__int64 **)(a2 + 736);
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
        (*(void (**)(void))(v6[63] + 80))();
        (*(void (__fastcall **)(_QWORD))(v6[63] + 8))(*(_QWORD *)(a2 + 696));
        *(_QWORD *)(a2 + 696) = 0;
      }
      if ( v5 )
      {
        if ( (unsigned int)dword_140013058 > 5 )
          HvsocketTraceReferenceCount(
            (const int *)"VmbusTlXPartRootSetupConnection",
            334,
            v5,
            *(_QWORD *)(v5 + 8),
            (const int *)"Dereference object");
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
      HvsocketTraceEndpointGuidError(
        (const int *)"VmbusTlXPartRootSetupConnection",
        217,
        (unsigned int)Pipe,
        a2,
        a2 + 140);
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
      HvsocketTraceEndpointGuidError((const int *)"VmbusTlXPartRootSetupConnection", v9, (unsigned int)v8, a2, v24);
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
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64, _DWORD *, char))(v6[63] + 88))(
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
      HvsocketTraceEndpointGuidError(
        (const int *)"VmbusTlXPartRootSetupConnection",
        269,
        (unsigned int)v8,
        a2,
        a2 + 140);
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
  v18 = (*(__int64 (__fastcall **)(__int64, __int64))(v6[63] + 96))(v17, v15);
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
0x1400256b0  push    rbp
0x1400256b2  push    rbx
0x1400256b3  push    rsi
0x1400256b4  push    rdi
0x1400256b5  push    r12
0x1400256b7  push    r13
0x1400256b9  push    r14
0x1400256bb  push    r15
0x1400256bd  lea     rbp, [rsp-0B8h]
0x1400256c5  sub     rsp, 1B8h
0x1400256cc  mov     rax, cs:__security_cookie
0x1400256d3  xor     rax, rsp
0x1400256d6  mov     [rbp+0F0h+var_48], rax
0x1400256dd  mov     r12b, r8b
0x1400256e0  lea     rcx, [rsp+1F0h+var_1A0]; void *
0x1400256e5  mov     rbx, rdx
0x1400256e8  mov     r8d, 128h; Size
0x1400256ee  xor     edx, edx; Val
0x1400256f0  call    memset
0x1400256f5  mov     eax, dword ptr cs:aGuesthostprovi+20h; "r"
0x1400256fb  xor     edi, edi
0x1400256fd  movups  xmm0, xmmword ptr cs:aGuesthostprovi; "GuestHostProvider"
0x140025704  mov     r15, [rbx+2E0h]
0x14002570b  movups  xmm1, xmmword ptr cs:aGuesthostprovi+10h; "tProvider"
0x140025712  mov     [rbp+0F0h+var_50], eax
0x140025718  xor     eax, eax
0x14002571a  mov     dword ptr [rsp+1F0h+var_1B0+4], eax
0x14002571e  mov     [rsp+40h], rdi
0x140025723  movups  [rbp+0F0h+Src], xmm0
0x14002572a  lea     r14d, [rax+22h]
0x14002572e  lea     edx, [rax+1]
0x140025731  movups  [rbp+0F0h+var_60], xmm1
0x140025738  test    r15, r15
0x14002573b  jnz     short loc_140025767
0x14002573d  mov     eax, cs:dword_140013058
0x140025743  mov     esi, 0C0000010h
0x140025748  cmp     eax, 2
0x14002574b  jbe     loc_14002597D
0x140025751  lea     rax, [rbx+8Ch]
0x140025758  mov     edx, 0D1h
0x14002575d  mov     [rsp+1F0h+var_1D0], rax
0x140025762  jmp     loc_140025966
0x140025767  lea     r13, [rbx+2B8h]
0x14002576e  mov     rcx, rbx
0x140025771  mov     r8, r13
0x140025774  call    VmbusTlXPartCreatePipe
0x140025779  mov     esi, eax
0x14002577b  test    eax, eax
0x14002577d  jns     short loc_1400257A7
0x14002577f  mov     ecx, cs:dword_140013058
0x140025785  cmp     ecx, 2
0x140025788  jbe     loc_140025978
0x14002578e  lea     rcx, [rbx+8Ch]
0x140025795  mov     r8d, eax
0x140025798  mov     [rsp+1F0h+var_1D0], rcx
0x14002579d  mov     edx, 0D9h
0x1400257a2  jmp     loc_140025969
0x1400257a7  xor     edx, edx; Val
0x1400257a9  lea     rcx, [rsp+1F0h+var_1A0]; void *
0x1400257ae  mov     r8d, 128h; Size
0x1400257b4  call    memset
0x1400257b9  mov     rcx, rbx
0x1400257bc  call    VmbusTlSetupConnectionId
0x1400257c1  mov     esi, eax
0x1400257c3  test    eax, eax
0x1400257c5  jns     short loc_1400257EC
0x1400257c7  mov     eax, cs:dword_140013058
0x1400257cd  cmp     eax, 2
0x1400257d0  jbe     loc_140025978
0x1400257d6  lea     rax, [rbx+8Ch]
0x1400257dd  mov     edx, 0E3h
0x1400257e2  mov     [rsp+1F0h+var_1D0], rax
0x1400257e7  jmp     loc_140025966
0x1400257ec  mov     esi, 1
0x1400257f1  mov     [rsp+1F0h+var_198], 101h
0x1400257f8  movups  xmm0, xmmword ptr [rbx+9Ch]
0x1400257ff  movups  xmm1, xmmword ptr [rbx+1D0h]
0x140025806  movdqu  [rsp+1F0h+var_194], xmm0
0x14002580c  movdqu  [rsp+1F0h+var_184], xmm1
0x140025812  cmp     [rbx+0BAh], dil
0x140025819  jz      short loc_14002581F
0x14002581b  or      [rbp+0F0h+var_16E], si
0x14002581f  mov     eax, [rbx+204h]
0x140025825  lea     rdx, [rbp+0F0h+Src]; Src
0x14002582c  movups  xmm0, xmmword ptr [rbx+380h]
0x140025833  test    r12b, r12b
0x140025836  movzx   r8d, r14w; Size
0x14002583a  lea     rcx, [rbp+0F0h+var_FA]; void *
0x14002583e  mov     [rbp+0F0h+var_16A], esi
0x140025841  setnz   [rbp+0F0h+var_16C]
0x140025845  shr     eax, 2
0x140025848  and     al, sil
0x14002584b  mov     [rbp+0F0h+var_16B], al
0x14002584e  movdqu  [rbp+0F0h+var_166], xmm0
0x140025853  call    memmove
0x140025858  lea     rcx, [rsp+1F0h+var_1A0]
0x14002585d  shr     r14w, 1
0x140025861  mov     [rbp+0F0h+var_FC], r14w
0x140025866  lea     r12, [rbx+8Ch]
0x14002586d  mov     rax, [r15+1F8h]
0x140025874  mov     r9, r12
0x140025877  mov     r8, [r15+1A0h]
0x14002587e  mov     rdx, [r15+60h]
0x140025882  mov     [rsp+1F0h+var_1C8], sil
0x140025887  mov     rax, [rax+58h]
0x14002588b  mov     [rsp+1F0h+var_1D0], rcx
0x140025890  mov     rcx, [r13+0]
0x140025894  call    _guard_dispatch_icall
0x140025899  mov     esi, eax
0x14002589b  test    eax, eax
0x14002589d  jns     short loc_1400258B8
0x14002589f  mov     eax, cs:dword_140013058
0x1400258a5  cmp     eax, 2
0x1400258a8  jbe     loc_140025978
0x1400258ae  mov     edx, 104h
0x1400258b3  jmp     loc_140025961
0x1400258b8  mov     rcx, [r15+60h]
0x1400258bc  lea     rdx, [rsp+1F0h+var_1B0]
0x1400258c1  call    VmbusTlCreateIrp
0x1400258c6  mov     esi, eax
0x1400258c8  test    eax, eax
0x1400258ca  jns     short loc_1400258FA
0x1400258cc  mov     eax, cs:dword_140013058
0x1400258d2  cmp     eax, 2
0x1400258d5  jbe     short loc_1400258F3
0x1400258d7  mov     r9, rbx
0x1400258da  mov     [rsp+1F0h+var_1D0], r12
0x1400258df  mov     r8d, esi
0x1400258e2  lea     rcx, aVmbustlxpartro_0; "VmbusTlXPartRootSetupConnection"
0x1400258e9  mov     edx, 10Dh
0x1400258ee  call    HvsocketTraceEndpointGuidError
0x1400258f3  mov     rdi, [rsp+1F0h+var_1B0]
0x1400258f8  jmp     short loc_140025978
0x1400258fa  mov     rdi, [rsp+1F0h+var_1B0]
0x1400258ff  lea     rcx, VmbusTlXPartRootConnectRequestCompleted
0x140025906  mov     r14, [rdi+60h]
0x14002590a  mov     rdx, r14
0x14002590d  mov     rax, [r14+0B8h]
0x140025914  mov     [rax-10h], rcx
0x140025918  mov     [rax-8], rbx
0x14002591c  mov     byte ptr [rax-45h], 0E0h
0x140025920  dec     byte ptr [r14+43h]
0x140025924  add     qword ptr [r14+0B8h], 0FFFFFFFFFFFFFFB8h
0x14002592c  mov     rcx, [r13+0]
0x140025930  mov     [rbx+2B0h], rdi
0x140025937  mov     rax, [r15+1F8h]
0x14002593e  mov     rax, [rax+60h]
0x140025942  call    _guard_dispatch_icall
0x140025947  mov     esi, eax
0x140025949  test    eax, eax
0x14002594b  jns     loc_140025A60
0x140025951  mov     eax, cs:dword_140013058
0x140025957  cmp     eax, 2
0x14002595a  jbe     short loc_140025978
0x14002595c  mov     edx, 124h
0x140025961  mov     [rsp+1F0h+var_1D0], r12
0x140025966  mov     r8d, esi
0x140025969  mov     r9, rbx
0x14002596c  lea     rcx, aVmbustlxpartro_0; "VmbusTlXPartRootSetupConnection"
0x140025973  call    HvsocketTraceEndpointGuidError
0x140025978  mov     edx, 1
0x14002597d  mov     rcx, [rbx+2B8h]
0x140025984  test    rcx, rcx
0x140025987  jz      short loc_1400259C1
0x140025989  mov     [rbx+2C0h], edx
0x14002598f  mov     rax, [r15+1F8h]
0x140025996  mov     rax, [rax+50h]
0x14002599a  call    _guard_dispatch_icall
0x14002599f  mov     rax, [r15+1F8h]
0x1400259a6  mov     rcx, [rbx+2B8h]
0x1400259ad  mov     rax, [rax+8]
0x1400259b1  call    _guard_dispatch_icall
0x1400259b6  mov     qword ptr [rbx+2B8h], 0
0x1400259c1  test    rdi, rdi
0x1400259c4  jz      loc_140025A7C
0x1400259ca  mov     eax, cs:dword_140013058
0x1400259d0  cmp     eax, 5
0x1400259d3  jbe     short loc_1400259F9
0x1400259d5  mov     r9, [rdi+8]
0x1400259d9  lea     rax, aDereferenceObj; "Dereference object"
0x1400259e0  mov     r8, rdi
0x1400259e3  mov     [rsp+1F0h+var_1D0], rax
0x1400259e8  mov     edx, 14Eh
0x1400259ed  lea     rcx, aVmbustlxpartro_0; "VmbusTlXPartRootSetupConnection"
0x1400259f4  call    HvsocketTraceReferenceCount
0x1400259f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400259fd  lock xadd [rdi+8], rax
0x140025a03  sub     rax, 1
0x140025a07  jg      short loc_140025A7C
0x140025a09  test    rax, rax
0x140025a0c  jz      short loc_140025A17
0x140025a0e  mov     ecx, 0Eh
0x140025a13  int     29h; Win8: RtlFailFast(ecx)
0x140025a15  jmp     short loc_140025A7C
0x140025a17  mov     rax, [rdi+50h]
0x140025a1b  test    rax, rax
0x140025a1e  jz      short loc_140025A28
0x140025a20  mov     rcx, rdi
0x140025a23  call    _guard_dispatch_icall
0x140025a28  mov     ecx, [rdi+58h]
0x140025a2b  sub     ecx, 1
0x140025a2e  jz      short loc_140025A4A
0x140025a30  cmp     ecx, 1
0x140025a33  jnz     short loc_140025A7C
0x140025a35  mov     rcx, [rdi+60h]; Lookaside
0x140025a39  mov     rdx, rdi; Entry
0x140025a3c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140025a43  nop     dword ptr [rax+rax+00h]
0x140025a48  jmp     short loc_140025A7C
0x140025a4a  mov     edx, 69706E56h; Tag
0x140025a4f  mov     rcx, rdi; P
0x140025a52  call    cs:__imp_ExFreePoolWithTag
0x140025a59  nop     dword ptr [rax+rax+00h]
0x140025a5e  jmp     short loc_140025A7C
0x140025a60  mov     edi, 103h
0x140025a65  cmp     esi, edi
0x140025a67  jz      short loc_140025A7A
0x140025a69  mov     r8, rbx
0x140025a6c  mov     [r14+30h], esi
0x140025a70  mov     rdx, r14
0x140025a73  xor     ecx, ecx
0x140025a75  call    VmbusTlXPartRootConnectRequestCompleted
0x140025a7a  mov     esi, edi
0x140025a7c  mov     eax, esi
0x140025a7e  mov     rcx, [rbp+0F0h+var_48]
0x140025a85  xor     rcx, rsp; StackCookie
0x140025a88  call    __security_check_cookie
0x140025a8d  add     rsp, 1B8h
0x140025a94  pop     r15
0x140025a96  pop     r14
0x140025a98  pop     r13
0x140025a9a  pop     r12
0x140025a9c  pop     rdi
0x140025a9d  pop     rsi
0x140025a9e  pop     rbx
0x140025a9f  pop     rbp
0x140025aa0  retn
```
