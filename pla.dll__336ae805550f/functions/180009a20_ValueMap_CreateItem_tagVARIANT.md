# ValueMap::CreateItem(tagVARIANT)

- ea: `0x180009a20`
- end: `0x18000a392`
- name: `?CreateItem@ValueMap@@IEAAJUtagVARIANT@@@Z`
- size: `2418`
- prototype: `int(ValueMap *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180006ca0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180009240`
- `0x180009a20`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009bec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009bec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009b7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009b7d`
- `OLEAUT32!__imp_VariantInit` at `0x180009a67`
- `OLEAUT32!__imp_VariantInit` at `0x180009a67`
- `OLEAUT32!__imp_VariantClear` at `0x180009a89`
- `OLEAUT32!__imp_VariantClear` at `0x180009c0e`
- `OLEAUT32!__imp_VariantClear` at `0x180009c84`
- `OLEAUT32!__imp_VariantClear` at `0x180009d9b`
- `OLEAUT32!__imp_VariantClear` at `0x180009a89`
- `OLEAUT32!__imp_VariantClear` at `0x180009c0e`
- `OLEAUT32!__imp_VariantClear` at `0x180009c84`
- `OLEAUT32!__imp_VariantClear` at `0x180009d9b`
- `OLEAUT32!__imp_VariantCopy` at `0x180009bcf`
- `OLEAUT32!__imp_VariantCopy` at `0x180009bcf`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009afb`
- `OLEAUT32!__imp_VariantChangeType` at `0x180009afb`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180009dd2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180009dd2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180009bac`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180009bac`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180009bfc`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180009bfc`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180009e62`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180009e62`

## string_xrefs

- `0x18000a037`: `ValueMap::CreateItem`
- `0x18000a0f4`: `ValueMap::CreateItem`
- `0x18000a298`: `ValueMap::CreateItem`

## pseudocode

```c
__int64 __fastcall ValueMap::CreateItem(ValueMap *this, struct tagVARIANT *a2)
{
  unsigned __int64 v4; // rdx
  LONGLONG Class; // rbx
  int v6; // eax
  unsigned __int64 v7; // rdx
  int v8; // edi
  __int64 v9; // r15
  int v10; // eax
  unsigned __int64 v11; // rdx
  HRESULT v12; // eax
  unsigned __int64 v13; // rdx
  __int64 v14; // rax
  IRecordInfo *pRecInfo; // xmm1_8
  __int64 (__fastcall *v16)(LONGLONG, __int128 *); // rax
  int v17; // eax
  unsigned __int64 v18; // rdx
  __int64 v19; // rsi
  unsigned int v20; // eax
  SAFEARRAY **v21; // r14
  HRESULT v22; // eax
  unsigned __int64 v23; // rdx
  HRESULT v24; // eax
  __int64 v26; // rax
  bool v27; // zf
  SAFEARRAY *v28; // rcx
  SAFEARRAY *v29; // rax
  __int64 v30; // rax
  HRESULT v31; // eax
  __int64 v32; // rax
  __int64 v33; // r15
  __int64 v34; // r15
  __int64 v35; // rax
  int v36; // [rsp+70h] [rbp-90h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+98h] [rbp-68h] BYREF
  void *ppvData; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v41; // [rsp+B0h] [rbp-50h] BYREF
  IRecordInfo *v42; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v43[64]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v44[64]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v45[64]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int16 v46[64]; // [rsp+250h] [rbp+150h] BYREF
  unsigned __int16 v47[64]; // [rsp+2D0h] [rbp+1D0h] BYREF
  unsigned __int16 v48[64]; // [rsp+350h] [rbp+250h] BYREF
  unsigned __int16 v49[64]; // [rsp+3D0h] [rbp+2D0h] BYREF
  unsigned __int16 v50[64]; // [rsp+450h] [rbp+350h] BYREF
  unsigned __int16 v51[64]; // [rsp+4D0h] [rbp+3D0h] BYREF
  unsigned __int16 v52[64]; // [rsp+550h] [rbp+450h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  pvarg.llVal = 0;
  Class = CreateClassObject<ValueMapItem>();
  if ( Class )
  {
    VariantClear(&pvarg);
    pvarg.llVal = Class;
    pvarg.vt = 9;
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)Class + 8LL))(Class);
    v6 = (*(__int64 (__fastcall **)(LONGLONG, _QWORD))(*(_QWORD *)Class + 128LL))(Class, *((unsigned int *)this + 22));
    v8 = v6;
    if ( v6 < 0 )
    {
      v36 = 0;
      LODWORD(v37) = v6;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_19;
      }
      PlaiWhoAmI(v44, v7);
      v33 = -1;
      do
        v27 = v44[++v33] == 0;
      while ( !v27 );
      goto LABEL_80;
    }
    v9 = -1;
    v10 = (*(__int64 (__fastcall **)(LONGLONG, __int64))(*(_QWORD *)Class + 80LL))(Class, 0xFFFFFFFFLL);
    v8 = v10;
    if ( v10 < 0 )
    {
      v36 = 0;
      LODWORD(v37) = v10;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_19;
      }
      PlaiWhoAmI(v45, v11);
      do
        v27 = v45[++v9] == 0;
      while ( !v27 );
      goto LABEL_80;
    }
    v12 = VariantChangeType(a2, a2, 0, *((_WORD *)this + 36));
    v8 = v12;
    if ( v12 < 0 )
    {
      v36 = 0;
      LODWORD(v37) = v12;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_19;
      }
      PlaiWhoAmI(v46, v13);
      do
        v27 = v46[++v9] == 0;
      while ( !v27 );
      goto LABEL_80;
    }
    v14 = *(_QWORD *)Class;
    pRecInfo = a2->pRecInfo;
    v41 = *(_OWORD *)&a2->vt;
    v16 = *(__int64 (__fastcall **)(LONGLONG, __int128 *))(v14 + 112);
    v42 = pRecInfo;
    v17 = v16(Class, &v41);
    v8 = v17;
    if ( v17 < 0 )
    {
      v36 = 0;
      LODWORD(v37) = v17;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_19;
      }
      PlaiWhoAmI(v47, v18);
      do
        v27 = v47[++v9] == 0;
      while ( !v27 );
LABEL_80:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v37, 4, byte_180147320, 1, &v36, 4);
LABEL_19:
      VariantClear(&pvarg);
      pvarg.llVal = 0;
      (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)Class + 16LL))(Class);
      return (unsigned int)v8;
    }
    v19 = *((_QWORD *)this + 12);
    ppvData = 0;
    rgsabound = 0;
    v37 = v19;
    v36 = *(_DWORD *)(v19 + 56);
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
    {
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_METHOD, 3, "Enumerator::Add", 16, &v37, 8, &v36, 4);
    }
    if ( *(_DWORD *)(v19 + 8) )
      EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
    v20 = *(_DWORD *)(v19 + 80);
    if ( *(_DWORD *)(v19 + 76) >= v20 )
    {
      v28 = *(SAFEARRAY **)(v19 + 64);
      v21 = (SAFEARRAY **)(v19 + 64);
      rgsabound.lLbound = 0;
      rgsabound.cElements = v20 + 16;
      if ( v28 )
      {
        v31 = SafeArrayRedim(v28, &rgsabound);
        v8 = v31;
        if ( v31 < 0 )
        {
          v36 = 0;
          LODWORD(v37) = v31;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_14;
          }
          PlaiWhoAmI(v48, v23);
          v32 = -1;
          do
            v27 = v48[++v32] == 0;
          while ( !v27 );
          goto LABEL_29;
        }
      }
      else
      {
        v29 = SafeArrayCreate(0xCu, 1u, &rgsabound);
        *v21 = v29;
        if ( !v29 )
        {
          v8 = -2147024882;
          LODWORD(v37) = -2147024882;
          v36 = 0;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_14;
          }
          PlaiWhoAmI(v49, v23);
          v30 = -1;
          do
            v27 = v49[++v30] == 0;
          while ( !v27 );
          goto LABEL_29;
        }
      }
      *(_DWORD *)(v19 + 80) = rgsabound.cElements;
    }
    v21 = (SAFEARRAY **)(v19 + 64);
    v22 = SafeArrayAccessData(*(SAFEARRAY **)(v19 + 64), &ppvData);
    v8 = v22;
    if ( v22 < 0 )
    {
      v36 = 0;
      LODWORD(v37) = v22;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_14;
      }
      PlaiWhoAmI(v50, v23);
      v35 = -1;
      do
        v27 = v50[++v35] == 0;
      while ( !v27 );
    }
    else
    {
      v24 = VariantCopy((VARIANTARG *)ppvData + *(unsigned int *)(v19 + 76), &pvarg);
      v8 = v24;
      if ( v24 >= 0 )
      {
        ++*(_DWORD *)(v19 + 76);
LABEL_14:
        if ( *(_DWORD *)(v19 + 8) )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 16));
        if ( ppvData )
          SafeArrayUnaccessData(*v21);
        if ( v8 >= 0 )
          goto LABEL_19;
        v36 = 0;
        LODWORD(v37) = v8;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_19;
        }
        PlaiWhoAmI(v52, v23);
        do
          v27 = v52[++v9] == 0;
        while ( !v27 );
        goto LABEL_80;
      }
      v36 = 0;
      LODWORD(v37) = v24;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_14;
      }
      PlaiWhoAmI(v51, v23);
      v26 = -1;
      do
        v27 = v51[++v26] == 0;
      while ( !v27 );
    }
LABEL_29:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v37, 4, byte_180147320, 1, &v36, 4);
    goto LABEL_14;
  }
  v8 = -2147024882;
  v36 = -2147024882;
  LODWORD(v37) = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v43, v4);
    v34 = -1;
    do
      v27 = v43[++v34] == 0;
    while ( !v27 );
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v36, 4, byte_180147320, 1, &v37, 4);
  }
  VariantClear(&pvarg);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180009a20  mov     [rsp-8+arg_10], rbx
0x180009a25  push    rbp
0x180009a26  push    rsi
0x180009a27  push    rdi
0x180009a28  push    r12
0x180009a2a  push    r13
0x180009a2c  push    r14
0x180009a2e  push    r15
0x180009a30  lea     rbp, [rsp-4E0h]
0x180009a38  sub     rsp, 5E0h
0x180009a3f  mov     rax, cs:__security_cookie
0x180009a46  xor     rax, rsp
0x180009a49  mov     [rbp+510h+var_40], rax
0x180009a50  mov     rsi, rcx
0x180009a53  xorps   xmm0, xmm0
0x180009a56  xor     eax, eax
0x180009a58  lea     rcx, [rbp+510h+pvarg]; pvarg
0x180009a5c  movups  xmmword ptr [rbp+510h+pvarg], xmm0
0x180009a60  mov     qword ptr [rbp+510h+pvarg+10h], rax
0x180009a64  mov     r14, rdx
0x180009a67  call    cs:__imp_VariantInit
0x180009a6d  xor     r13d, r13d
0x180009a70  mov     qword ptr [rbp+510h+pvarg+8], r13
0x180009a74  call    ??$CreateClassObject@VValueMapItem@@@@YAPEAVValueMapItem@@PEBDH@Z; CreateClassObject<ValueMapItem>(char const *,int)
0x180009a79  mov     rbx, rax
0x180009a7c  test    rax, rax
0x180009a7f  jz      loc_180009D69
0x180009a85  lea     rcx, [rbp+510h+pvarg]; pvarg
0x180009a89  call    cs:__imp_VariantClear
0x180009a8f  mov     eax, 9
0x180009a94  mov     qword ptr [rbp+510h+pvarg+8], rbx
0x180009a98  mov     word ptr [rbp+510h+pvarg], ax
0x180009a9c  mov     rcx, rbx
0x180009a9f  mov     rax, [rbx]
0x180009aa2  mov     rax, [rax+8]
0x180009aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aab  mov     rax, [rbx]
0x180009aae  mov     rcx, rbx
0x180009ab1  mov     edx, [rsi+58h]
0x180009ab4  mov     rax, [rax+80h]
0x180009abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ac0  mov     edi, eax
0x180009ac2  test    eax, eax
0x180009ac4  js      loc_180009EEB
0x180009aca  mov     rax, [rbx]
0x180009acd  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180009ad4  mov     edx, r15d
0x180009ad7  mov     rcx, rbx
0x180009ada  mov     rax, [rax+50h]
0x180009ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ae3  mov     edi, eax
0x180009ae5  test    eax, eax
0x180009ae7  js      loc_180009C57
0x180009aed  movzx   r9d, word ptr [rsi+48h]; vt
0x180009af2  xor     r8d, r8d; wFlags
0x180009af5  mov     rdx, r14; pvarSrc
0x180009af8  mov     rcx, r14; pvargDest
0x180009afb  call    cs:__imp_VariantChangeType
0x180009b01  mov     edi, eax
0x180009b03  test    eax, eax
0x180009b05  js      loc_18000A2D8
0x180009b0b  mov     rax, [rbx]
0x180009b0e  lea     rdx, [rbp+510h+var_560]
0x180009b12  movaps  xmm0, xmmword ptr [r14]
0x180009b16  mov     rcx, rbx
0x180009b19  movsd   xmm1, qword ptr [r14+10h]
0x180009b1f  movaps  [rbp+510h+var_560], xmm0
0x180009b23  mov     rax, [rax+70h]
0x180009b27  movsd   [rbp+510h+var_550], xmm1
0x180009b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b31  mov     edi, eax
0x180009b33  test    eax, eax
0x180009b35  js      loc_18000A30A
0x180009b3b  cmp     dword ptr cs:xmmword_180169738, r13d
0x180009b42  mov     rsi, [rsi+60h]
0x180009b46  mov     [rbp+510h+ppvData], r13
0x180009b4a  mov     qword ptr [rbp+510h+rgsabound.cElements], r13
0x180009b4e  mov     [rsp+610h+var_598], rsi
0x180009b53  mov     eax, [rsi+38h]
0x180009b56  mov     [rsp+610h+var_5A0], eax
0x180009b5a  jz      short loc_180009B73
0x180009b5c  mov     rdx, 4000000000000400h
0x180009b66  test    qword ptr cs:xmmword_180169738+8, rdx
0x180009b6d  jnz     loc_180009F58
0x180009b73  cmp     [rsi+8], r13d
0x180009b77  jz      short loc_180009B83
0x180009b79  lea     rcx, [rsi+10h]; lpCriticalSection
0x180009b7d  call    cs:__imp_EnterCriticalSection
0x180009b83  mov     eax, [rsi+50h]
0x180009b86  lea     r13, byte_180147320
0x180009b8d  mov     r12, 4000000000000800h
0x180009b97  cmp     [rsi+4Ch], eax
0x180009b9a  jnb     loc_180009DA6
0x180009ba0  mov     rcx, [rsi+40h]; psa
0x180009ba4  lea     r14, [rsi+40h]
0x180009ba8  lea     rdx, [rbp+510h+ppvData]; ppvData
0x180009bac  call    cs:__imp_SafeArrayAccessData
0x180009bb2  mov     edi, eax
0x180009bb4  test    eax, eax
0x180009bb6  js      loc_18000A33C
0x180009bbc  mov     eax, [rsi+4Ch]
0x180009bbf  lea     rdx, [rbp+510h+pvarg]; pvargSrc
0x180009bc3  lea     rcx, [rax+rax*2]
0x180009bc7  mov     rax, [rbp+510h+ppvData]
0x180009bcb  lea     rcx, [rax+rcx*8]; pvargDest
0x180009bcf  call    cs:__imp_VariantCopy
0x180009bd5  mov     edi, eax
0x180009bd7  test    eax, eax
0x180009bd9  js      loc_180009C90
0x180009bdf  inc     dword ptr [rsi+4Ch]
0x180009be2  cmp     dword ptr [rsi+8], 0
0x180009be6  jz      short loc_180009BF2
0x180009be8  lea     rcx, [rsi+10h]; lpCriticalSection
0x180009bec  call    cs:__imp_LeaveCriticalSection
0x180009bf2  cmp     [rbp+510h+ppvData], 0
0x180009bf7  jz      short loc_180009C02
0x180009bf9  mov     rcx, [r14]; psa
0x180009bfc  call    cs:__imp_SafeArrayUnaccessData
0x180009c02  test    edi, edi
0x180009c04  js      loc_18000A367
0x180009c0a  lea     rcx, [rbp+510h+pvarg]; pvarg
0x180009c0e  call    cs:__imp_VariantClear
0x180009c14  mov     qword ptr [rbp+510h+pvarg+8], 0
0x180009c1c  mov     rax, [rbx]
0x180009c1f  mov     rcx, rbx
0x180009c22  mov     rax, [rax+10h]
0x180009c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c2b  mov     eax, edi
0x180009c2d  mov     rcx, [rbp+510h+var_40]
0x180009c34  xor     rcx, rsp; StackCookie
0x180009c37  call    __security_check_cookie
0x180009c3c  mov     rbx, [rsp+610h+arg_10]
0x180009c44  add     rsp, 5E0h
0x180009c4b  pop     r15
0x180009c4d  pop     r14
0x180009c4f  pop     r13
0x180009c51  pop     r12
0x180009c53  pop     rdi
0x180009c54  pop     rsi
0x180009c55  pop     rbp
0x180009c56  retn
0x180009c57  cmp     dword ptr cs:xmmword_180169738, r13d
0x180009c5e  mov     [rsp+610h+var_5A0], r13d
0x180009c63  mov     dword ptr [rsp+610h+var_598], eax
0x180009c67  jz      short loc_180009C80
0x180009c69  mov     r12, 4000000000000800h
0x180009c73  test    qword ptr cs:xmmword_180169738+8, r12
0x180009c7a  jnz     loc_180009FC3
0x180009c80  lea     rcx, [rbp+510h+pvarg]; pvarg
0x180009c84  call    cs:__imp_VariantClear
0x180009c8a  mov     qword ptr [rbp+510h+pvarg+8], r13
0x180009c8e  jmp     short loc_180009C1C
0x180009c90  cmp     dword ptr cs:xmmword_180169738, 0
0x180009c97  mov     [rsp+610h+var_5A0], 0
0x180009c9f  mov     dword ptr [rsp+610h+var_598], eax
0x180009ca3  jz      loc_180009BE2
0x180009ca9  test    qword ptr cs:xmmword_180169738+8, r12
0x180009cb0  jz      loc_180009BE2
0x180009cb6  mov     rax, cs:qword_180169748
0x180009cbd  and     rax, r12
0x180009cc0  cmp     cs:qword_180169748, rax
0x180009cc7  jnz     loc_180009BE2
0x180009ccd  lea     rcx, [rbp+510h+var_140]; unsigned __int16 *
0x180009cd4  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180009cd9  lea     rcx, [rbp+510h+var_140]
0x180009ce0  mov     rax, r15
0x180009ce3  cmp     word ptr [rcx+rax*2+2], 0
0x180009ce9  lea     rax, [rax+1]
0x180009ced  jnz     short loc_180009CE3
0x180009cef  lea     ecx, [rax+rax]
0x180009cf2  lea     rax, [rbp+510h+var_140]
0x180009cf9  add     rcx, 2
0x180009cfd  lea     r9, [rsp+610h+var_598]
0x180009d02  mov     [rsp+610h+var_5B0], rcx
0x180009d07  lea     rdx, PLA_EVENT_ERROR
0x180009d0e  mov     [rsp+610h+var_5B8], rax
0x180009d13  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180009d1a  mov     [rsp+610h+var_5C0], 10h
0x180009d23  lea     rax, aEnumeratorAdd; "Enumerator::Add"
0x180009d2a  mov     [rsp+610h+var_5C8], rax
0x180009d2f  mov     r8d, 5
0x180009d35  mov     [rsp+610h+var_5D0], 4
0x180009d3e  lea     rax, [rsp+610h+var_5A0]
0x180009d43  mov     [rsp+610h+var_5D8], rax
0x180009d48  mov     [rsp+610h+var_5E0], 1
0x180009d51  mov     [rsp+610h+var_5E8], r13
0x180009d56  mov     [rsp+610h+var_5F0], 4
0x180009d5f  call    EventingWriteEvent
0x180009d64  jmp     loc_180009BE2
0x180009d69  cmp     dword ptr cs:xmmword_180169738, r13d
0x180009d70  mov     edi, 8007000Eh
0x180009d75  mov     [rsp+610h+var_5A0], edi
0x180009d79  mov     dword ptr [rsp+610h+var_598], r13d
0x180009d7e  jz      short loc_180009D97
0x180009d80  mov     r12, 4000000000000800h
0x180009d8a  test    qword ptr cs:xmmword_180169738+8, r12
0x180009d91  jnz     loc_18000A081
0x180009d97  lea     rcx, [rbp+510h+pvarg]; pvarg
0x180009d9b  call    cs:__imp_VariantClear
0x180009da1  jmp     loc_180009C2B
0x180009da6  mov     rcx, [rsi+40h]; psa
0x180009daa  lea     r14, [rsi+40h]
0x180009dae  add     eax, 10h
0x180009db1  mov     [rbp+510h+rgsabound.lLbound], 0
0x180009db8  mov     [rbp+510h+rgsabound.cElements], eax
0x180009dbb  test    rcx, rcx
0x180009dbe  jnz     loc_180009E5E
0x180009dc4  mov     ecx, 0Ch; vt
0x180009dc9  lea     r8, [rbp+510h+rgsabound]; rgsabound
0x180009dcd  mov     edx, 1; cDims
0x180009dd2  call    cs:__imp_SafeArrayCreate
0x180009dd8  mov     [r14], rax
0x180009ddb  test    rax, rax
0x180009dde  jz      short loc_180009DEB
0x180009de0  mov     eax, [rbp+510h+rgsabound.cElements]
0x180009de3  mov     [rsi+50h], eax
0x180009de6  jmp     loc_180009BA0
0x180009deb  cmp     dword ptr cs:xmmword_180169738, 0
0x180009df2  mov     edi, 8007000Eh
0x180009df7  mov     dword ptr [rsp+610h+var_598], edi
0x180009dfb  mov     [rsp+610h+var_5A0], 0
0x180009e03  jz      loc_180009BE2
0x180009e09  test    qword ptr cs:xmmword_180169738+8, r12
0x180009e10  jz      loc_180009BE2
0x180009e16  mov     rax, cs:qword_180169748
0x180009e1d  and     rax, r12
0x180009e20  cmp     cs:qword_180169748, rax
0x180009e27  jnz     loc_180009BE2
0x180009e2d  lea     rcx, [rbp+510h+var_240]; unsigned __int16 *
0x180009e34  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180009e39  lea     rcx, [rbp+510h+var_240]
0x180009e40  mov     rax, r15
0x180009e43  cmp     word ptr [rcx+rax*2+2], 0
0x180009e49  lea     rax, [rax+1]
0x180009e4d  jnz     short loc_180009E43
0x180009e4f  lea     ecx, [rax+rax]
0x180009e52  lea     rax, [rbp+510h+var_240]
0x180009e59  jmp     loc_180009CF9
0x180009e5e  lea     rdx, [rbp+510h+rgsabound]; psaboundNew
0x180009e62  call    cs:__imp_SafeArrayRedim
0x180009e68  mov     edi, eax
0x180009e6a  test    eax, eax
0x180009e6c  jns     loc_180009DE0
0x180009e72  cmp     dword ptr cs:xmmword_180169738, 0
0x180009e79  mov     [rsp+610h+var_5A0], 0
0x180009e81  mov     dword ptr [rsp+610h+var_598], eax
0x180009e85  jz      loc_180009BE2
0x180009e8b  test    qword ptr cs:xmmword_180169738+8, r12
0x180009e92  jz      loc_180009BE2
0x180009e98  mov     rax, cs:qword_180169748
0x180009e9f  and     rax, r12
0x180009ea2  cmp     cs:qword_180169748, rax
0x180009ea9  jnz     loc_180009BE2
0x180009eaf  lea     rcx, [rbp+510h+var_2C0]; unsigned __int16 *
0x180009eb6  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180009ebb  lea     rcx, [rbp+510h+var_2C0]
0x180009ec2  mov     rax, r15
0x180009ec5  nop     word ptr [rax+rax+00000000h]
0x180009ed0  cmp     word ptr [rcx+rax*2+2], 0
0x180009ed6  lea     rax, [rax+1]
0x180009eda  jnz     short loc_180009ED0
0x180009edc  lea     ecx, [rax+rax]
0x180009edf  lea     rax, [rbp+510h+var_2C0]
0x180009ee6  jmp     loc_180009CF9
0x180009eeb  cmp     dword ptr cs:xmmword_180169738, r13d
0x180009ef2  mov     [rsp+610h+var_5A0], r13d
0x180009ef7  mov     dword ptr [rsp+610h+var_598], eax
0x180009efb  jz      loc_180009C80
0x180009f01  mov     r12, 4000000000000800h
0x180009f0b  test    qword ptr cs:xmmword_180169738+8, r12
0x180009f12  jz      loc_180009C80
0x180009f18  mov     rax, cs:qword_180169748
0x180009f1f  and     rax, r12
0x180009f22  cmp     cs:qword_180169748, rax
0x180009f29  jnz     loc_180009C80
0x180009f2f  lea     rcx, [rbp+510h+var_4C0]; unsigned __int16 *
0x180009f33  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180009f38  lea     rax, [rbp+510h+var_4C0]
0x180009f3c  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180009f43  cmp     [rax+r15*2+2], r13w
0x180009f49  lea     r15, [r15+1]
0x180009f4d  jnz     short loc_180009F43
0x180009f4f  lea     rax, [rbp+510h+var_4C0]
0x180009f53  jmp     loc_18000A003
0x180009f58  mov     rax, cs:qword_180169748
0x180009f5f  and     rax, rdx
0x180009f62  cmp     cs:qword_180169748, rax
0x180009f69  jnz     loc_180009B73
0x180009f6f  mov     [rsp+610h+var_5D0], 4
0x180009f78  lea     rax, [rsp+610h+var_5A0]
0x180009f7d  mov     [rsp+610h+var_5D8], rax
0x180009f82  lea     r9, aEnumeratorAdd; "Enumerator::Add"
0x180009f89  lea     rax, [rsp+610h+var_598]
0x180009f8e  mov     [rsp+610h+var_5E0], 8
0x180009f97  mov     [rsp+610h+var_5E8], rax
0x180009f9c  lea     rdx, PLA_EVENT_METHOD
0x180009fa3  mov     r8d, 3
0x180009fa9  mov     [rsp+610h+var_5F0], 10h
0x180009fb2  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180009fb9  call    EventingWriteEvent
  ... truncated ...
```
