# NsiSetAllParametersEx

- ea: `0x140022080`
- end: `0x1400223db`
- name: `NsiSetAllParametersEx`
- size: `859`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140020e30`

## callees

- `0x140021588`
- `0x140022080`
- `0x1400223f0`
- `0x140023a40`
- `0x140023c30`
- `0x140026fac`
- `0x14004f3bc`
- `0x140050ea4`
- `0x14005f0b0`
- `0x14005f1c4`
- `0x140077fa0`
- `0x140078080`
- `0x140078400`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14007b07e`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007b07e`
- `ntoskrnl!KeGetCurrentIrql` at `0x140022106`
- `ntoskrnl!KeGetCurrentIrql` at `0x140022106`

## pseudocode

```c
__int64 __fastcall NsiSetAllParametersEx(__int64 a1)
{
  int v2; // r8d
  unsigned int v3; // r14d
  __int64 v4; // r9
  __int64 v5; // r8
  int v6; // ebx
  __int64 NmpContext; // rax
  __int64 v8; // rsi
  __int64 v9; // r15
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int64 v12; // rdx
  int v13; // eax
  int v15; // eax
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rax
  int v18; // r15d
  int v19; // r12d
  __int128 *v20; // rbx
  __int64 v21; // rdx
  __int64 v22; // rax
  __int128 *v23; // rdx
  char CurrentProcessId; // si
  size_t Size; // [rsp+28h] [rbp-91h]
  int v26; // [rsp+60h] [rbp-59h] BYREF
  int v27; // [rsp+68h] [rbp-51h] BYREF
  _OWORD v28[4]; // [rsp+70h] [rbp-49h] BYREF
  __int128 v29; // [rsp+B0h] [rbp-9h] BYREF

  memset(v28, 0, sizeof(v28));
  v3 = *(_DWORD *)(a1 + 36);
  v26 = 0;
  v27 = 0;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    v17 = *(_QWORD *)(a1 + 16);
    v18 = *(_DWORD *)(a1 + 32);
    v19 = *(_DWORD *)(a1 + 24);
    v29 = 0;
    v20 = (__int128 *)(v17 + 8);
    if ( !v17 )
      v20 = &v29;
    CurrentProcessId = (unsigned __int8)PsGetCurrentProcessId();
    NdisGetCurrentThreadCompartmentScope(&v26, &v27);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_s_guid_dddqdd(
        WPP_GLOBAL_Control->AttachedDevice,
        v26,
        v2,
        (unsigned int)"NsiSetAllParametersEx",
        (__int64)v20,
        v19,
        v18,
        CurrentProcessId,
        0,
        v27,
        v26);
    }
  }
  v4 = *(unsigned int *)(a1 + 32);
  if ( (unsigned int)v4 > 2 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
    {
      goto LABEL_24;
    }
    v21 = 41;
LABEL_60:
    WPP_SF_d(v16->AttachedDevice, v21, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids, v4);
    goto LABEL_24;
  }
  if ( v3 > 7 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
    {
      goto LABEL_24;
    }
    v21 = 42;
    v4 = v3;
    goto LABEL_60;
  }
  if ( (_DWORD)v4 )
  {
    if ( KeGetCurrentIrql() < 2u )
    {
      LOBYTE(v5) = *(_DWORD *)(a1 + 36) == 4;
      v6 = NsipAccessCheck(a1 + 8, 0, v5);
      if ( v6 < 0 )
        goto LABEL_14;
    }
    NmpContext = NsipGetNmpContext(a1 + 8);
    v8 = NmpContext;
    if ( !NmpContext )
    {
      v6 = -1073741637;
      goto LABEL_14;
    }
    v9 = *(_QWORD *)(NmpContext + 48);
    v6 = NsipValidateSetAllParametersRequest(v9, a1);
    if ( v6 < 0 )
      goto LABEL_13;
    v10 = *(_OWORD *)(a1 + 40);
    *(_QWORD *)&v28[3] = *(unsigned int *)(a1 + 36);
    v11 = *(_OWORD *)(a1 + 56);
    v28[1] = v10;
    v28[2] = v11;
    *(_QWORD *)&v28[0] = *(_QWORD *)(v8 + 40);
    v12 = 104LL * *(unsigned int *)(a1 + 24);
    *((_QWORD *)&v28[0] + 1) = *(_QWORD *)(v12 + *(_QWORD *)(v9 + 8) + 24);
    v6 = (*(__int64 (__fastcall **)(_OWORD *))(v12 + *(_QWORD *)(v9 + 8) + 56))(v28);
    if ( v6 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        43,
        WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids,
        (unsigned int)v6);
    }
  }
  else
  {
    v8 = 0;
    v6 = 0;
  }
  v13 = *(_DWORD *)(a1 + 32);
  if ( v13 )
  {
    if ( v13 != 2 )
      goto LABEL_12;
    if ( v6 < 0 )
    {
      if ( v6 != -1073741275 || v3 != 3 )
        goto LABEL_12;
    }
    else if ( !v3 )
    {
      v3 = 2;
    }
  }
  if ( !*(_QWORD *)(a1 + 16) )
  {
    if ( v8 || (v8 = NsipGetNmpContext(a1 + 8)) != 0 )
    {
      *(_QWORD *)(a1 + 16) = *(_QWORD *)(v8 + 24);
      goto LABEL_21;
    }
LABEL_24:
    v6 = -1073741811;
    goto LABEL_14;
  }
LABEL_21:
  LODWORD(Size) = *(_DWORD *)(a1 + 64);
  v15 = NsipWritePersistentData((int)a1 + 8, v3, (int)a1 + 40, *(_QWORD *)(a1 + 56), 0, Size, 0, v3 != 3);
  if ( v3 != 3 || *(_DWORD *)(a1 + 32) != 2 || v15 != -1073741275 && v15 != -1073741766 && v15 != -1073741772 )
    v6 = v15;
LABEL_12:
  if ( v8 )
LABEL_13:
    NsipDereferenceNmpContext(v8);
LABEL_14:
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
  {
    v22 = *(_QWORD *)(a1 + 16);
    v29 = 0;
    v23 = (__int128 *)(v22 + 8);
    if ( !v22 )
      v23 = &v29;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_s_guid_dddqddD(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v23,
        v2,
        (unsigned int)"NsiSetAllParametersEx",
        (__int64)v23,
        *(_DWORD *)(a1 + 24),
        *(_DWORD *)(a1 + 32),
        0,
        0,
        0,
        0,
        v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140022080  push    rbp
0x140022082  push    rbx
0x140022083  push    rsi
0x140022084  push    rdi
0x140022085  push    r12
0x140022087  push    r13
0x140022089  push    r14
0x14002208b  push    r15
0x14002208d  lea     rbp, [rsp-1Fh]
0x140022092  sub     rsp, 0D8h
0x140022099  mov     rax, cs:__security_cookie
0x1400220a0  xor     rax, rsp
0x1400220a3  mov     [rbp+57h+var_50], rax
0x1400220a7  xor     edx, edx; Val
0x1400220a9  mov     rdi, rcx
0x1400220ac  lea     rcx, [rbp+57h+var_A0]; void *
0x1400220b0  lea     r8d, [rdx+40h]; Size
0x1400220b4  call    memset
0x1400220b9  mov     rax, cs:WPP_GLOBAL_Control
0x1400220c0  lea     rdx, WPP_GLOBAL_Control
0x1400220c7  mov     r14d, [rdi+24h]
0x1400220cb  xor     r13d, r13d
0x1400220ce  mov     [rbp+57h+var_B0], r13d
0x1400220d2  mov     [rbp+57h+var_A8], r13d
0x1400220d6  cmp     byte ptr [rax+29h], 5
0x1400220da  jnb     loc_1400222AB
0x1400220e0  mov     r9d, [rdi+20h]
0x1400220e4  mov     r12d, 2
0x1400220ea  cmp     r9d, r12d
0x1400220ed  ja      loc_140022291
0x1400220f3  cmp     r14d, 7
0x1400220f7  ja      loc_14002235E
0x1400220fd  test    r9d, r9d
0x140022100  jz      loc_1400222E9
0x140022106  call    cs:__imp_KeGetCurrentIrql
0x14002210d  nop     dword ptr [rax+rax+00h]
0x140022112  cmp     al, r12b
0x140022115  jnb     short loc_140022134
0x140022117  cmp     dword ptr [rdi+24h], 4
0x14002211b  lea     rcx, [rdi+8]
0x14002211f  setz    r8b
0x140022123  xor     edx, edx
0x140022125  call    NsipAccessCheck
0x14002212a  mov     ebx, eax
0x14002212c  test    eax, eax
0x14002212e  js      loc_1400221D5
0x140022134  lea     rcx, [rdi+8]
0x140022138  call    NsipGetNmpContext
0x14002213d  mov     rsi, rax
0x140022140  test    rax, rax
0x140022143  jz      loc_1400222DF
0x140022149  mov     r15, [rax+30h]
0x14002214d  mov     rdx, rdi
0x140022150  mov     rcx, r15
0x140022153  call    NsipValidateSetAllParametersRequest
0x140022158  mov     ebx, eax
0x14002215a  test    eax, eax
0x14002215c  js      short loc_1400221CD
0x14002215e  mov     eax, [rdi+24h]
0x140022161  movups  xmm0, xmmword ptr [rdi+28h]
0x140022165  mov     [rbp+57h+var_70], eax
0x140022168  movups  xmm1, xmmword ptr [rdi+38h]
0x14002216c  mov     [rbp+57h+var_6C], r13d
0x140022170  movdqu  [rbp+57h+var_90], xmm0
0x140022175  movdqu  [rbp+57h+var_80], xmm1
0x14002217a  mov     rax, [rsi+28h]
0x14002217e  mov     [rbp+57h+var_A0], rax
0x140022182  mov     eax, [rdi+18h]
0x140022185  imul    rdx, rax, 68h ; 'h'
0x140022189  mov     rax, [r15+8]
0x14002218d  mov     rcx, [rdx+rax+18h]
0x140022192  mov     [rbp+57h+var_98], rcx
0x140022196  lea     rcx, [rbp+57h+var_A0]
0x14002219a  mov     rax, [r15+8]
0x14002219e  mov     rax, [rdx+rax+38h]
0x1400221a3  call    _guard_dispatch_icall
0x1400221a8  mov     ebx, eax
0x1400221aa  test    eax, eax
0x1400221ac  js      short loc_140022209
0x1400221ae  mov     eax, [rdi+20h]
0x1400221b1  mov     r15d, 0C0000225h
0x1400221b7  test    eax, eax
0x1400221b9  jz      loc_140022246
0x1400221bf  cmp     eax, r12d
0x1400221c2  jz      loc_1400222F4
0x1400221c8  test    rsi, rsi
0x1400221cb  jz      short loc_1400221D5
0x1400221cd  mov     rcx, rsi
0x1400221d0  call    NsipDereferenceNmpContext
0x1400221d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400221dc  cmp     byte ptr [rcx+29h], 5
0x1400221e0  jnb     loc_1400223AF
0x1400221e6  mov     eax, ebx
0x1400221e8  mov     rcx, [rbp+57h+var_50]
0x1400221ec  xor     rcx, rsp; StackCookie
0x1400221ef  call    __security_check_cookie
0x1400221f4  add     rsp, 0D8h
0x1400221fb  pop     r15
0x1400221fd  pop     r14
0x1400221ff  pop     r13
0x140022201  pop     r12
0x140022203  pop     rdi
0x140022204  pop     rsi
0x140022205  pop     rbx
0x140022206  pop     rbp
0x140022207  retn
0x140022209  mov     rcx, cs:WPP_GLOBAL_Control
0x140022210  lea     rax, WPP_GLOBAL_Control
0x140022217  cmp     rcx, rax
0x14002221a  jz      short loc_1400221AE
0x14002221c  cmp     [rcx+29h], r12b
0x140022220  jb      short loc_1400221AE
0x140022222  mov     eax, [rcx+2Ch]
0x140022225  test    al, 10h
0x140022227  jz      short loc_1400221AE
0x140022229  mov     rcx, [rcx+18h]
0x14002222d  lea     r8, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids
0x140022234  mov     edx, 2Bh ; '+'
0x140022239  mov     r9d, ebx
0x14002223c  call    WPP_SF_d
0x140022241  jmp     loc_1400221AE
0x140022246  cmp     [rdi+10h], r13
0x14002224a  jz      loc_14002230D
0x140022250  mov     r9, [rdi+38h]; int
0x140022254  lea     r8, [rdi+28h]; int
0x140022258  cmp     r14d, 3
0x14002225c  lea     rcx, [rdi+8]; int
0x140022260  mov     edx, r14d; int
0x140022263  setnz   al
0x140022266  mov     [rsp+110h+var_D8], al; char
0x14002226a  mov     eax, [rdi+40h]
0x14002226d  mov     [rsp+110h+var_E0], r13d; int
0x140022272  mov     dword ptr [rsp+110h+Size], eax; Size
0x140022276  mov     [rsp+110h+var_F0], r13; void *
0x14002227b  call    NsipWritePersistentData
0x140022280  cmp     r14d, 3
0x140022284  jz      loc_140022330
0x14002228a  mov     ebx, eax
0x14002228c  jmp     loc_1400221C8
0x140022291  mov     rcx, cs:WPP_GLOBAL_Control
0x140022298  cmp     rcx, rdx
0x14002229b  jnz     loc_140022390
0x1400222a1  mov     ebx, 0C000000Dh
0x1400222a6  jmp     loc_1400221D5
0x1400222ab  mov     eax, [rax+2Ch]
0x1400222ae  test    al, 10h
0x1400222b0  jz      loc_1400220E0
0x1400222b6  mov     rax, [rdi+10h]
0x1400222ba  xorps   xmm0, xmm0
0x1400222bd  mov     r15d, [rdi+20h]
0x1400222c1  mov     r12d, [rdi+18h]
0x1400222c5  movups  [rbp+57h+var_60], xmm0
0x1400222c9  lea     rbx, [rax+8]
0x1400222cd  test    rax, rax
0x1400222d0  jnz     loc_14007B07E
0x1400222d6  lea     rbx, [rbp+57h+var_60]
0x1400222da  jmp     loc_14007B07E
0x1400222df  mov     ebx, 0C00000BBh
0x1400222e4  jmp     loc_1400221D5
0x1400222e9  mov     rsi, r13
0x1400222ec  mov     ebx, r13d
0x1400222ef  jmp     loc_1400221AE
0x1400222f4  test    ebx, ebx
0x1400222f6  js      loc_14007B109
0x1400222fc  test    r14d, r14d
0x1400222ff  jnz     loc_140022246
0x140022305  mov     r14d, r12d
0x140022308  jmp     loc_140022246
0x14002230d  test    rsi, rsi
0x140022310  jnz     loc_14007B121
0x140022316  lea     rcx, [rdi+8]
0x14002231a  call    NsipGetNmpContext
0x14002231f  mov     rsi, rax
0x140022322  test    rax, rax
0x140022325  jz      loc_1400222A1
0x14002232b  jmp     loc_14007B121
0x140022330  cmp     [rdi+20h], r12d
0x140022334  jnz     loc_14002228A
0x14002233a  cmp     eax, r15d
0x14002233d  jz      loc_1400221C8
0x140022343  cmp     eax, 0C000003Ah
0x140022348  jz      loc_1400221C8
0x14002234e  cmp     eax, 0C0000034h
0x140022353  jz      loc_1400221C8
0x140022359  jmp     loc_14002228A
0x14002235e  mov     rcx, cs:WPP_GLOBAL_Control
0x140022365  cmp     rcx, rdx
0x140022368  jz      loc_1400222A1
0x14002236e  cmp     [rcx+29h], r12b
0x140022372  jb      loc_1400222A1
0x140022378  mov     eax, [rcx+2Ch]
0x14002237b  test    al, 10h
0x14002237d  jz      loc_1400222A1
0x140022383  mov     edx, 2Ah ; '*'
0x140022388  mov     r9d, r14d
0x14002238b  jmp     loc_14007B12E
0x140022390  cmp     [rcx+29h], r12b
0x140022394  jb      loc_1400222A1
0x14002239a  mov     eax, [rcx+2Ch]
0x14002239d  test    al, 10h
0x14002239f  jz      loc_1400222A1
0x1400223a5  mov     edx, 29h ; ')'
0x1400223aa  jmp     loc_14007B12E
0x1400223af  mov     eax, [rcx+2Ch]
0x1400223b2  test    al, 10h
0x1400223b4  jz      loc_1400221E6
0x1400223ba  mov     rax, [rdi+10h]
0x1400223be  xorps   xmm0, xmm0
0x1400223c1  movups  [rbp+57h+var_60], xmm0
0x1400223c5  lea     rdx, [rax+8]
0x1400223c9  test    rax, rax
0x1400223cc  jnz     loc_14007B144
0x1400223d2  lea     rdx, [rbp+57h+var_60]
0x1400223d6  jmp     loc_14007B144
0x14007b07e  call    cs:__imp_PsGetCurrentProcessId
0x14007b085  nop     dword ptr [rax+rax+00h]
0x14007b08a  mov     edx, [rbp+57h+var_B0]
0x14007b08d  mov     rsi, rax
0x14007b090  test    edx, edx
0x14007b092  jnz     short loc_14007B0AA
0x14007b094  cmp     [rbp+57h+var_A8], r13d
0x14007b098  jnz     short loc_14007B0AA
0x14007b09a  lea     rdx, [rbp+57h+var_A8]
0x14007b09e  lea     rcx, [rbp+57h+var_B0]
0x14007b0a2  call    NdisGetCurrentThreadCompartmentScope
0x14007b0a7  mov     edx, [rbp+57h+var_B0]
0x14007b0aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14007b0b1  lea     rax, WPP_GLOBAL_Control
0x14007b0b8  cmp     rcx, rax
0x14007b0bb  jz      short loc_14007B0FD
0x14007b0bd  cmp     byte ptr [rcx+29h], 5
0x14007b0c1  jb      short loc_14007B0FD
0x14007b0c3  mov     eax, [rcx+2Ch]
0x14007b0c6  test    al, 10h
0x14007b0c8  jz      short loc_14007B0FD
0x14007b0ca  mov     eax, [rbp+57h+var_A8]
0x14007b0cd  lea     r9, aNsisetallparam; "NsiSetAllParametersEx"
0x14007b0d4  mov     rcx, [rcx+18h]
0x14007b0d8  mov     [rsp+110h+var_C0], edx
0x14007b0dc  mov     [rsp+110h+var_C8], eax
0x14007b0e0  mov     [rsp+110h+var_D0], r13
0x14007b0e5  mov     dword ptr [rsp+110h+var_D8], esi
0x14007b0e9  mov     [rsp+110h+var_E0], r15d
0x14007b0ee  mov     dword ptr [rsp+110h+Size], r12d
0x14007b0f3  mov     [rsp+110h+var_F0], rbx
0x14007b0f8  call    WPP_SF_s_guid_dddqdd
0x14007b0fd  lea     rdx, WPP_GLOBAL_Control
0x14007b104  jmp     loc_1400220E0
0x14007b109  cmp     ebx, r15d
0x14007b10c  jnz     loc_1400221C8
0x14007b112  cmp     r14d, 3
0x14007b116  jnz     loc_1400221C8
0x14007b11c  jmp     loc_140022246
0x14007b121  mov     rax, [rsi+18h]
0x14007b125  mov     [rdi+10h], rax
0x14007b129  jmp     loc_140022250
0x14007b12e  mov     rcx, [rcx+18h]
0x14007b132  lea     r8, WPP_b802283a6c2b3e3c6b570e68b8145ddd_Traceguids
0x14007b139  call    WPP_SF_d
0x14007b13e  nop
0x14007b13f  jmp     loc_1400222A1
0x14007b144  lea     rax, WPP_GLOBAL_Control
0x14007b14b  cmp     rcx, rax
0x14007b14e  jz      loc_1400221E6
0x14007b154  mov     eax, [rdi+20h]
0x14007b157  lea     r9, aNsisetallparam; "NsiSetAllParametersEx"
0x14007b15e  mov     rcx, [rcx+18h]
0x14007b162  mov     [rsp+110h+var_B8], ebx
0x14007b166  mov     [rsp+110h+var_C0], r13d
0x14007b16b  mov     [rsp+110h+var_C8], r13d
0x14007b170  mov     [rsp+110h+var_D0], r13
0x14007b175  mov     dword ptr [rsp+110h+var_D8], r13d
0x14007b17a  mov     [rsp+110h+var_E0], eax
0x14007b17e  mov     eax, [rdi+18h]
0x14007b181  mov     dword ptr [rsp+110h+Size], eax
0x14007b185  mov     [rsp+110h+var_F0], rdx
0x14007b18a  call    WPP_SF_s_guid_dddqddD
0x14007b18f  nop
0x14007b190  jmp     loc_1400221E6
```
