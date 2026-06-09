# WSTComputeVerifyMessageByKey(basessp::_WST_ENCRYPTION_KEY *,_WST_CONTEXT *,_GUID *,_WST_VERIFY_MESSAGE *,_WST_MESSAGE * *)

- ea: `0x18000bf1c`
- end: `0x18000c51f`
- name: `?WSTComputeVerifyMessageByKey@@YAJPEAU_WST_ENCRYPTION_KEY@basessp@@PEAU_WST_CONTEXT@@PEAU_GUID@@PEAU_WST_VERIFY_MESSAGE@@PEAPEAU_WST_MESSAGE@@@Z`
- size: `1539`
- prototype: `__int64 __fastcall(struct basessp::_WST_ENCRYPTION_KEY *, struct _WST_CONTEXT *, struct _GUID *, struct _WST_VERIFY_MESSAGE *, struct _WST_MESSAGE **)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000be70`

## callees

- `0x1800027e4`
- `0x18000285c`
- `0x1800028a0`
- `0x18000ba90`
- `0x18000bb08`
- `0x18000bf1c`
- `0x18000c528`
- `0x18000ebcc`
- `0x18000ec28`
- `0x18000ffa4`
- `0x1800157d8`
- `0x18001c3d8`
- `0x18001ecd6`
- `0x18001ed20`
- `0x18001edb0`
- `0x180020010`

## import_xrefs

- `cryptdll!CDLocateCheckSum` at `0x18000c006`
- `cryptdll!CDLocateCheckSum` at `0x18000c006`
- `cryptdll!CDLocateCSystem` at `0x18000bfb0`
- `cryptdll!CDLocateCSystem` at `0x18000bfb0`

## pseudocode

```c
__int64 __fastcall WSTComputeVerifyMessageByKey(
        struct basessp::_WST_ENCRYPTION_KEY *a1,
        struct _WST_CONTEXT *a2,
        struct _GUID *a3,
        struct _WST_VERIFY_MESSAGE *a4,
        struct _WST_MESSAGE **a5)
{
  unsigned __int8 *v8; // r12
  struct _WST_MESSAGE **v9; // rdi
  struct _GUID *v10; // rdx
  __int64 v11; // r9
  int v12; // ebx
  __int64 v13; // r8
  _QWORD *v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rdx
  unsigned int v17; // r13d
  int v18; // eax
  __int64 **i; // r15
  __int64 **j; // r15
  __int64 **k; // r15
  __int64 v22; // r9
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  int v25; // r8d
  __int64 v26; // r9
  unsigned __int64 v27; // rbx
  __int64 v28; // rcx
  unsigned __int64 v29; // rcx
  void *v30; // rsp
  void *v31; // rsp
  _DWORD *v32; // rax
  unsigned int v33; // ecx
  unsigned int v34; // ebx
  unsigned __int8 *v35; // rax
  int v36; // ecx
  struct _GUID *v37; // rax
  int v38; // eax
  struct _WST_MESSAGE *v39; // rsi
  __int64 v41; // [rsp+0h] [rbp-30h] BYREF
  unsigned int *v42; // [rsp+30h] [rbp+0h] BYREF
  struct _WST_MESSAGE *v43; // [rsp+38h] [rbp+8h] BYREF
  __int64 v44; // [rsp+40h] [rbp+10h] BYREF
  unsigned int v45; // [rsp+48h] [rbp+18h] BYREF
  struct _WST_MESSAGE *v46; // [rsp+50h] [rbp+20h] BYREF
  unsigned __int8 *v47; // [rsp+58h] [rbp+28h] BYREF
  __int64 v48; // [rsp+60h] [rbp+30h] BYREF
  struct _GUID *v49; // [rsp+68h] [rbp+38h]

  v49 = a3;
  v48 = 0;
  v43 = 0;
  v46 = 0;
  v42 = 0;
  v8 = 0;
  v44 = 0;
  v9 = 0;
  if ( a5 )
    *a5 = 0;
  if ( !WSTGetActiveContextByAuthScheme(a2, (struct _GUID *)((char *)a2 + 228))
    || !*((_DWORD *)WSTGetActiveContextByAuthScheme(a2, v10) + 24) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_2c71e2299e853e517959ad87a3f04733_Traceguids, v11);
    v12 = -1073741637;
    goto LABEL_85;
  }
  v12 = CDLocateCSystem(*(unsigned int *)a1, &v48);
  if ( v12 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_85;
    v15 = *(unsigned int *)a1;
    v16 = 11;
    goto LABEL_9;
  }
  v17 = *(_DWORD *)(v48 + 20);
  v12 = CDLocateCheckSum(v17, &v42);
  if ( v12 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_85;
    v16 = 12;
    v15 = v17;
LABEL_9:
    WPP_SF_dD(v14[2], v16, v13, v15, v12);
LABEL_85:
    v39 = v43;
    goto LABEL_86;
  }
  if ( a4 )
    v18 = *((_DWORD *)a2 + 34) == 0;
  else
    v18 = *((_DWORD *)a2 + 34);
  v12 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))v42 + 6))(
          *((_QWORD *)a1 + 2),
          *((unsigned int *)a1 + 2),
          v18 != 0 ? 25 : 23,
          &v44);
  if ( v12 < 0 )
    goto LABEL_85;
  for ( i = (__int64 **)*((_QWORD *)a2 + 9);
        i != (__int64 **)((char *)a2 + 72) && (!a4 || *((_DWORD *)i[3] + 3) < *((_DWORD *)a4 + 3));
        i = (__int64 **)*i )
  {
    v12 = (*((__int64 (__fastcall **)(__int64, _QWORD, __int64 *))v42 + 3))(v44, *((unsigned int *)i + 8), i[3]);
    if ( v12 < 0 )
      goto LABEL_85;
  }
  for ( j = (__int64 **)*((_QWORD *)a2 + 13);
        j != (__int64 **)((char *)a2 + 104) && (!a4 || *((_DWORD *)j[3] + 3) < *((_DWORD *)a4 + 3));
        j = (__int64 **)*j )
  {
    v12 = (*((__int64 (__fastcall **)(__int64, _QWORD, __int64 *))v42 + 3))(v44, *((unsigned int *)j + 8), j[3]);
    if ( v12 < 0 )
      goto LABEL_85;
  }
  for ( k = (__int64 **)*((_QWORD *)a2 + 11); k != (__int64 **)((char *)a2 + 88); k = (__int64 **)*k )
  {
    if ( a4 && *((_DWORD *)k[3] + 3) >= *((_DWORD *)a4 + 3) )
      goto LABEL_37;
    v12 = (*((__int64 (__fastcall **)(__int64, _QWORD, __int64 *))v42 + 3))(v44, *((unsigned int *)k + 8), k[3]);
    if ( v12 < 0 )
      goto LABEL_85;
  }
  if ( a4 )
  {
LABEL_37:
    v22 = *((unsigned int *)a4 + 14);
    if ( (unsigned int)v22 < 0x14 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_42;
      v24 = 13;
LABEL_41:
      WPP_SF_d(v23[2], v24, &WPP_2c71e2299e853e517959ad87a3f04733_Traceguids, v22);
LABEL_42:
      v12 = -1073741715;
      goto LABEL_85;
    }
    v22 = *((unsigned int *)a4 + 15);
    if ( (_DWORD)v22 != 1 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_42;
      v24 = 14;
      goto LABEL_41;
    }
    v25 = *((_DWORD *)a4 + 16);
    v26 = *v42;
    if ( (_DWORD)v26 != v25 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_2c71e2299e853e517959ad87a3f04733_Traceguids, v26, v25);
LABEL_51:
      v12 = -2146893041;
      goto LABEL_85;
    }
    v27 = v42[1];
    if ( !v42[1]
      || v27 > g_ulMaxStackAllocSize
      || v27 + g_ulAdditionalProbeSize + 8 < v27
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_99;
    }
    v28 = v27 + 23;
    if ( v27 + 23 <= v27 + 8 )
      v28 = 0xFFFFFFFFFFFFFF0LL;
    v29 = v28 & 0xFFFFFFFFFFFFFFF0uLL;
    v30 = alloca(v29);
    v31 = alloca(v29);
    v9 = (struct _WST_MESSAGE **)&v42;
    if ( &v41 == (__int64 *)-48LL || (LODWORD(v42) = 1801679955, (v9 = &v43) == 0) )
    {
LABEL_99:
      if ( v27 + 8 >= v27 )
      {
        v32 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        v9 = (struct _WST_MESSAGE **)v32;
        if ( v32 )
        {
          *v32 = 1885431112;
          v9 = (struct _WST_MESSAGE **)(v32 + 2);
        }
      }
    }
    if ( v9 )
    {
      v12 = (*((__int64 (__fastcall **)(__int64, struct _WST_MESSAGE **))v42 + 4))(v44, v9);
      if ( v12 < 0 )
        goto LABEL_85;
      v33 = v42[1];
      if ( *((_DWORD *)a4 + 18) == v33 && !memcmp_0((char *)a4 + *((unsigned int *)a4 + 17), v9, v33) )
        goto LABEL_85;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          &WPP_2c71e2299e853e517959ad87a3f04733_Traceguids,
          *((unsigned int *)a4 + 3));
      goto LABEL_51;
    }
LABEL_64:
    v12 = -1073741801;
    goto LABEL_85;
  }
  if ( !a5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_2c71e2299e853e517959ad87a3f04733_Traceguids);
    v12 = -1073741811;
    goto LABEL_85;
  }
  v45 = v42[1] + 80;
  v34 = v45;
  v35 = (unsigned __int8 *)basessp::BaseSSP::WSTAllocate(WSTGlobalBaseSSP, v45);
  v47 = v35;
  v8 = v35;
  if ( !v35 )
    goto LABEL_64;
  *((_DWORD *)v35 + 4) = 80;
  *((_DWORD *)v35 + 5) = v34;
  *(_QWORD *)v35 = 0x535458454F47454ELL;
  v36 = *((_DWORD *)a2 + 35);
  *((_DWORD *)a2 + 35) = v36 + 1;
  v37 = v49;
  *((_DWORD *)v8 + 3) = v36;
  *(_OWORD *)(v8 + 24) = *((_OWORD *)a2 + 2);
  *((_DWORD *)v8 + 2) = 6;
  *(struct _GUID *)(v8 + 40) = *v37;
  *((_DWORD *)v8 + 14) = 20;
  *((_DWORD *)v8 + 15) = 1;
  *((_DWORD *)v8 + 16) = *v42;
  *((_DWORD *)v8 + 18) = v42[1];
  *((_DWORD *)v8 + 17) = 80;
  v12 = (*((__int64 (__fastcall **)(__int64, unsigned __int8 *))v42 + 4))(v44, v8 + 80);
  if ( v12 < 0 )
    goto LABEL_85;
  v38 = WSTAllocateWstMessage(&v47, &v45, &v46);
  v8 = v47;
  v12 = v38;
  if ( v38 < 0 )
  {
    v39 = v46;
  }
  else
  {
    *a5 = v46;
    v39 = 0;
  }
LABEL_86:
  if ( v42 && v44 )
    (*((void (__fastcall **)(__int64 *))v42 + 5))(&v44);
  if ( v8 )
    WSTFree(v8);
  if ( v39 )
    WSTFreeWstMessage(v39);
  if ( v9 && *((_DWORD *)v9 - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000bf1c  push    rbp
0x18000bf1e  push    rbx
0x18000bf1f  push    rsi
0x18000bf20  push    rdi
0x18000bf21  push    r12
0x18000bf23  push    r13
0x18000bf25  push    r14
0x18000bf27  push    r15
0x18000bf29  sub     rsp, 88h
0x18000bf30  lea     rbp, [rsp+30h]
0x18000bf35  mov     rax, cs:__security_cookie
0x18000bf3c  xor     rax, rbp
0x18000bf3f  mov     [rbp+90h+var_50], rax
0x18000bf43  xor     r13d, r13d
0x18000bf46  mov     [rbp+90h+var_58], r8
0x18000bf4a  mov     eax, r13d
0x18000bf4d  mov     [rbp+90h+var_60], r13
0x18000bf51  mov     [rbp+90h+var_88], rax
0x18000bf55  mov     rsi, r9
0x18000bf58  mov     [rbp+90h+var_70], rax
0x18000bf5c  mov     r14, rdx
0x18000bf5f  mov     rax, [rbp+90h+arg_20]
0x18000bf66  mov     r15, rcx
0x18000bf69  mov     [rbp+90h+var_90], r13
0x18000bf6d  mov     r12d, r13d
0x18000bf70  mov     [rbp+90h+var_80], r13
0x18000bf74  mov     edi, r13d
0x18000bf77  test    rax, rax
0x18000bf7a  jz      short loc_18000BF7F
0x18000bf7c  mov     [rax], r13
0x18000bf7f  add     rdx, 0E4h; struct _GUID *
0x18000bf86  mov     rcx, r14; struct _WST_CONTEXT *
0x18000bf89  call    ?WSTGetActiveContextByAuthScheme@@YAPEAU_WST_ACTIVE_ENGINE_CONTEXT@@PEAU_WST_CONTEXT@@PEAU_GUID@@@Z; WSTGetActiveContextByAuthScheme(_WST_CONTEXT *,_GUID *)
0x18000bf8e  test    rax, rax
0x18000bf91  jz      loc_18000C475
0x18000bf97  mov     rcx, r14; struct _WST_CONTEXT *
0x18000bf9a  call    ?WSTGetActiveContextByAuthScheme@@YAPEAU_WST_ACTIVE_ENGINE_CONTEXT@@PEAU_WST_CONTEXT@@PEAU_GUID@@@Z; WSTGetActiveContextByAuthScheme(_WST_CONTEXT *,_GUID *)
0x18000bf9f  cmp     [rax+60h], r13d
0x18000bfa3  jz      loc_18000C475
0x18000bfa9  mov     ecx, [r15]
0x18000bfac  lea     rdx, [rbp+90h+var_60]
0x18000bfb0  call    cs:__imp_CDLocateCSystem
0x18000bfb6  mov     ebx, eax
0x18000bfb8  test    eax, eax
0x18000bfba  jns     short loc_18000BFF7
0x18000bfbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bfc3  lea     rax, WPP_GLOBAL_Control
0x18000bfca  cmp     rcx, rax
0x18000bfcd  jz      loc_18000C4A8
0x18000bfd3  test    byte ptr [rcx+1Ch], 1
0x18000bfd7  jz      loc_18000C4A8
0x18000bfdd  mov     r9d, [r15]
0x18000bfe0  mov     edx, 0Bh
0x18000bfe5  mov     rcx, [rcx+10h]
0x18000bfe9  mov     [rsp+0C0h+var_A0], ebx
0x18000bfed  call    WPP_SF_dD
0x18000bff2  jmp     loc_18000C4A8
0x18000bff7  mov     rax, [rbp+90h+var_60]
0x18000bffb  lea     rdx, [rbp+90h+var_90]
0x18000bfff  mov     r13d, [rax+14h]
0x18000c003  mov     ecx, r13d
0x18000c006  call    cs:__imp_CDLocateCheckSum
0x18000c00c  mov     ebx, eax
0x18000c00e  test    eax, eax
0x18000c010  jns     short loc_18000C03D
0x18000c012  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c019  lea     rax, WPP_GLOBAL_Control
0x18000c020  cmp     rcx, rax
0x18000c023  jz      loc_18000C4A8
0x18000c029  test    byte ptr [rcx+1Ch], 1
0x18000c02d  jz      loc_18000C4A8
0x18000c033  mov     edx, 0Ch
0x18000c038  mov     r9d, r13d
0x18000c03b  jmp     short loc_18000BFE5
0x18000c03d  mov     rax, [rbp+90h+var_90]
0x18000c041  mov     ecx, [r14+88h]
0x18000c048  mov     r10, [rax+30h]
0x18000c04c  test    rsi, rsi
0x18000c04f  jz      short loc_18000C05A
0x18000c051  xor     eax, eax
0x18000c053  test    ecx, ecx
0x18000c055  setz    al
0x18000c058  jmp     short loc_18000C05C
0x18000c05a  mov     eax, ecx
0x18000c05c  mov     edx, [r15+8]
0x18000c060  lea     r9, [rbp+90h+var_80]
0x18000c064  mov     rcx, [r15+10h]
0x18000c068  neg     eax
0x18000c06a  mov     rax, r10
0x18000c06d  sbb     r8d, r8d
0x18000c070  and     r8d, 2
0x18000c074  add     r8d, 17h
0x18000c078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c07d  mov     ebx, eax
0x18000c07f  test    eax, eax
0x18000c081  js      loc_18000C4A8
0x18000c087  lea     r13, [r14+48h]
0x18000c08b  mov     r15, [r13+0]
0x18000c08f  cmp     r15, r13
0x18000c092  jz      short loc_18000C0CD
0x18000c094  test    rsi, rsi
0x18000c097  jz      short loc_18000C0A5
0x18000c099  mov     rcx, [r15+18h]
0x18000c09d  mov     eax, [rsi+0Ch]
0x18000c0a0  cmp     [rcx+0Ch], eax
0x18000c0a3  jnb     short loc_18000C0CD
0x18000c0a5  mov     rax, [rbp+90h+var_90]
0x18000c0a9  mov     r8, [r15+18h]
0x18000c0ad  mov     edx, [r15+20h]
0x18000c0b1  mov     rcx, [rbp+90h+var_80]
0x18000c0b5  mov     rax, [rax+18h]
0x18000c0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0be  mov     ebx, eax
0x18000c0c0  test    eax, eax
0x18000c0c2  js      loc_18000C4A8
0x18000c0c8  mov     r15, [r15]
0x18000c0cb  jmp     short loc_18000C08F
0x18000c0cd  lea     r13, [r14+68h]
0x18000c0d1  mov     r15, [r13+0]
0x18000c0d5  cmp     r15, r13
0x18000c0d8  jz      short loc_18000C113
0x18000c0da  test    rsi, rsi
0x18000c0dd  jz      short loc_18000C0EB
0x18000c0df  mov     rcx, [r15+18h]
0x18000c0e3  mov     eax, [rsi+0Ch]
0x18000c0e6  cmp     [rcx+0Ch], eax
0x18000c0e9  jnb     short loc_18000C113
0x18000c0eb  mov     rax, [rbp+90h+var_90]
0x18000c0ef  mov     r8, [r15+18h]
0x18000c0f3  mov     edx, [r15+20h]
0x18000c0f7  mov     rcx, [rbp+90h+var_80]
0x18000c0fb  mov     rax, [rax+18h]
0x18000c0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c104  mov     ebx, eax
0x18000c106  test    eax, eax
0x18000c108  js      loc_18000C4A8
0x18000c10e  mov     r15, [r15]
0x18000c111  jmp     short loc_18000C0D5
0x18000c113  lea     r13, [r14+58h]
0x18000c117  mov     r15, [r13+0]
0x18000c11b  cmp     r15, r13
0x18000c11e  jz      short loc_18000C159
0x18000c120  test    rsi, rsi
0x18000c123  jz      short loc_18000C131
0x18000c125  mov     rcx, [r15+18h]
0x18000c129  mov     eax, [rsi+0Ch]
0x18000c12c  cmp     [rcx+0Ch], eax
0x18000c12f  jnb     short loc_18000C162
0x18000c131  mov     rax, [rbp+90h+var_90]
0x18000c135  mov     r8, [r15+18h]
0x18000c139  mov     edx, [r15+20h]
0x18000c13d  mov     rcx, [rbp+90h+var_80]
0x18000c141  mov     rax, [rax+18h]
0x18000c145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c14a  mov     ebx, eax
0x18000c14c  test    eax, eax
0x18000c14e  js      loc_18000C4A8
0x18000c154  mov     r15, [r15]
0x18000c157  jmp     short loc_18000C11B
0x18000c159  test    rsi, rsi
0x18000c15c  jz      loc_18000C340
0x18000c162  mov     r9d, [rsi+38h]
0x18000c166  cmp     r9d, 14h
0x18000c16a  jnb     short loc_18000C1A4
0x18000c16c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c173  lea     rax, WPP_GLOBAL_Control
0x18000c17a  cmp     rcx, rax
0x18000c17d  jz      short loc_18000C19A
0x18000c17f  test    byte ptr [rcx+1Ch], 1
0x18000c183  jz      short loc_18000C19A
0x18000c185  mov     edx, 0Dh
0x18000c18a  mov     rcx, [rcx+10h]
0x18000c18e  lea     r8, WPP_2c71e2299e853e517959ad87a3f04733_Traceguids
0x18000c195  call    WPP_SF_d
0x18000c19a  mov     ebx, 0C000006Dh
0x18000c19f  jmp     loc_18000C4A8
0x18000c1a4  mov     r9d, [rsi+3Ch]
0x18000c1a8  cmp     r9d, 1
0x18000c1ac  jz      short loc_18000C1CE
0x18000c1ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1b5  lea     rax, WPP_GLOBAL_Control
0x18000c1bc  cmp     rcx, rax
0x18000c1bf  jz      short loc_18000C19A
0x18000c1c1  test    byte ptr [rcx+1Ch], 1
0x18000c1c5  jz      short loc_18000C19A
0x18000c1c7  mov     edx, 0Eh
0x18000c1cc  jmp     short loc_18000C18A
0x18000c1ce  mov     rax, [rbp+90h+var_90]
0x18000c1d2  mov     r8d, [rsi+40h]
0x18000c1d6  mov     r9d, [rax]
0x18000c1d9  cmp     r9d, r8d
0x18000c1dc  jz      short loc_18000C21B
0x18000c1de  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1e5  lea     rax, WPP_GLOBAL_Control
0x18000c1ec  cmp     rcx, rax
0x18000c1ef  jz      short loc_18000C211
0x18000c1f1  test    byte ptr [rcx+1Ch], 1
0x18000c1f5  jz      short loc_18000C211
0x18000c1f7  mov     rcx, [rcx+10h]
0x18000c1fb  mov     edx, 0Fh
0x18000c200  mov     [rsp+0C0h+var_A0], r8d
0x18000c205  lea     r8, WPP_2c71e2299e853e517959ad87a3f04733_Traceguids
0x18000c20c  call    WPP_SF_Dd
0x18000c211  mov     ebx, 8009030Fh
0x18000c216  jmp     loc_18000C4A8
0x18000c21b  mov     rax, [rbp+90h+var_90]
0x18000c21f  mov     ebx, [rax+4]
0x18000c222  test    rbx, rbx
0x18000c225  jz      short loc_18000C288
0x18000c227  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18000c22e  ja      short loc_18000C288
0x18000c230  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000c237  add     rcx, 8
0x18000c23b  add     rcx, rbx
0x18000c23e  cmp     rcx, rbx
0x18000c241  jb      short loc_18000C288
0x18000c243  call    VerifyStackAvailable
0x18000c248  test    eax, eax
0x18000c24a  jz      short loc_18000C288
0x18000c24c  lea     rax, [rbx+8]
0x18000c250  lea     rcx, [rax+0Fh]
0x18000c254  cmp     rcx, rax
0x18000c257  ja      short loc_18000C263
0x18000c259  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000c263  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000c267  mov     rax, rcx
0x18000c26a  call    _alloca_probe
0x18000c26f  sub     rsp, rcx
0x18000c272  lea     rdi, [rsp+0C0h+var_90]
0x18000c277  test    rdi, rdi
0x18000c27a  jz      short loc_18000C288
0x18000c27c  mov     dword ptr [rdi], 6B637453h
0x18000c282  add     rdi, 8
0x18000c286  jnz     short loc_18000C2AF
0x18000c288  lea     rcx, [rbx+8]
0x18000c28c  cmp     rcx, rbx
0x18000c28f  jb      short loc_18000C2AF
0x18000c291  mov     rax, cs:g_pfnAllocate
0x18000c298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c29d  mov     rdi, rax
0x18000c2a0  test    rax, rax
0x18000c2a3  jz      short loc_18000C2AF
0x18000c2a5  mov     dword ptr [rax], 70616548h
0x18000c2ab  add     rdi, 8
0x18000c2af  test    rdi, rdi
0x18000c2b2  jnz     short loc_18000C2BE
0x18000c2b4  mov     ebx, 0C0000017h
0x18000c2b9  jmp     loc_18000C4A8
0x18000c2be  mov     rax, [rbp+90h+var_90]
0x18000c2c2  mov     rdx, rdi
0x18000c2c5  mov     rcx, [rbp+90h+var_80]
0x18000c2c9  mov     rax, [rax+20h]
0x18000c2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2d2  mov     ebx, eax
0x18000c2d4  test    eax, eax
0x18000c2d6  js      loc_18000C4A8
0x18000c2dc  mov     rax, [rbp+90h+var_90]
0x18000c2e0  mov     ecx, [rax+4]
0x18000c2e3  cmp     [rsi+48h], ecx
0x18000c2e6  jnz     short loc_18000C301
0x18000c2e8  mov     r8d, ecx; Size
0x18000c2eb  mov     rdx, rdi; Buf2
0x18000c2ee  mov     ecx, [rsi+44h]
0x18000c2f1  add     rcx, rsi; Buf1
0x18000c2f4  call    memcmp_0
0x18000c2f9  test    eax, eax
0x18000c2fb  jz      loc_18000C4A8
0x18000c301  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c308  lea     rax, WPP_GLOBAL_Control
0x18000c30f  cmp     rcx, rax
0x18000c312  jz      loc_18000C211
0x18000c318  test    byte ptr [rcx+1Ch], 1
0x18000c31c  jz      loc_18000C211
0x18000c322  mov     r9d, [rsi+0Ch]
0x18000c326  lea     r8, WPP_2c71e2299e853e517959ad87a3f04733_Traceguids
0x18000c32d  mov     rcx, [rcx+10h]
0x18000c331  mov     edx, 10h
0x18000c336  call    WPP_SF_d
0x18000c33b  jmp     loc_18000C211
0x18000c340  mov     rsi, [rbp+90h+arg_20]
0x18000c347  test    rsi, rsi
0x18000c34a  jnz     short loc_18000C382
0x18000c34c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c353  lea     rax, WPP_GLOBAL_Control
0x18000c35a  cmp     rcx, rax
0x18000c35d  jz      short loc_18000C378
0x18000c35f  test    byte ptr [rcx+1Ch], 1
0x18000c363  jz      short loc_18000C378
0x18000c365  mov     rcx, [rcx+10h]
0x18000c369  lea     edx, [rsi+11h]
0x18000c36c  lea     r8, WPP_2c71e2299e853e517959ad87a3f04733_Traceguids
0x18000c373  call    WPP_SF_
0x18000c378  mov     ebx, 0C000000Dh
0x18000c37d  jmp     loc_18000C4A8
0x18000c382  mov     rax, [rbp+90h+var_90]
0x18000c386  mov     rcx, cs:?WSTGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18000c38d  mov     ebx, [rax+4]
0x18000c390  add     ebx, 50h ; 'P'
0x18000c393  mov     edx, ebx; unsigned __int64
0x18000c395  mov     [rbp+90h+var_78], ebx
  ... truncated ...
```
