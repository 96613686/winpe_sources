# CSdtEvent::UpdateStore(void)

- ea: `0x180049920`
- end: `0x180049d2e`
- name: `?UpdateStore@CSdtEvent@@UEAAJXZ`
- size: `1038`
- prototype: `__int64 __fastcall(CSdtEvent *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180044ad8`
- `0x180044bc8`
- `0x180044cd0`
- `0x180049920`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x1800499f9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x1800499f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049a5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049a8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049af7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049a5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049a8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049af7`

## pseudocode

```c
__int64 __fastcall CSdtEvent::UpdateStore(CSdtEvent *this)
{
  struct IEventSystem *pItf; // r15
  __int64 v3; // r12
  SubscriptionSaver *v4; // rdi
  COSERVERINFO *v5; // r9
  DWORD v6; // r8d
  int v7; // r13d
  HRESULT hr; // ebx
  int v9; // eax
  EventClassSaver *v10; // rax
  SubscriptionSaver *v11; // rax
  SubscriptionSaver *v12; // rax
  __int64 v13; // rcx
  LPVOID v14; // r10
  BOOL v15; // eax
  unsigned int i; // r14d
  int v17; // eax
  HRESULT v18; // eax
  int v20; // [rsp+44h] [rbp-B4h] BYREF
  SubscriptionSaver *v21; // [rsp+48h] [rbp-B0h]
  unsigned int v22; // [rsp+50h] [rbp-A8h]
  IUnknown *v23; // [rsp+58h] [rbp-A0h]
  __int64 v24; // [rsp+60h] [rbp-98h]
  MULTI_QI pResults; // [rsp+68h] [rbp-90h] BYREF
  GUID *v26; // [rsp+80h] [rbp-78h]
  __int128 v27; // [rsp+88h] [rbp-70h]
  __int128 v28; // [rsp+98h] [rbp-60h] BYREF
  __int128 v29; // [rsp+A8h] [rbp-50h]
  unsigned __int64 v30; // [rsp+B8h] [rbp-40h] BYREF
  int v31; // [rsp+C0h] [rbp-38h]

  v20 = 0;
  pItf = 0;
  v23 = 0;
  v3 = 0;
  v24 = 0;
  v4 = 0;
  v21 = 0;
  v28 = 0;
  v29 = 0;
  v5 = 0;
  v6 = 23;
  v30 = 0;
  v31 = 0;
  v7 = 0;
  if ( *((_QWORD *)this + 10) )
  {
    *((_QWORD *)&v28 + 1) = *((_QWORD *)this + 10);
    *(_QWORD *)&v29 = 0;
    LODWORD(v28) = 0;
    DWORD2(v29) = 0;
    v5 = (COSERVERINFO *)&v28;
    v6 = 16;
  }
  pResults.pItf = 0;
  *(_QWORD *)&pResults.hr = 0;
  v27 = 0;
  pResults.pIID = &IID_IEventSystem;
  v26 = &IID_IEventSystemInitialize;
  hr = CoCreateInstanceEx(&CLSID_CEventSystem, 0, v6, v5, 2u, &pResults);
  if ( hr < 0 || pResults.hr < 0 || SDWORD2(v27) < 0 )
  {
    if ( hr >= 0 )
    {
      if ( pResults.hr >= 0 )
      {
        if ( SDWORD2(v27) < 0 )
          hr = DWORD2(v27);
      }
      else
      {
        hr = pResults.hr;
      }
    }
    goto LABEL_50;
  }
  pItf = (struct IEventSystem *)pResults.pItf;
  v23 = pResults.pItf;
  v3 = v27;
  v24 = v27;
  (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v27 + 24LL))(v27, 1);
  v9 = *((_DWORD *)this + 12);
  if ( v9 )
  {
    if ( v9 == 1 )
    {
      v12 = (SubscriptionSaver *)CoTaskMemAlloc(0x30u);
      if ( v12 )
      {
        v13 = *((_QWORD *)this + 11) - tidTRANSIENTSUBSCRIPTIONS;
        if ( !v13 )
          v13 = *((_QWORD *)this + 12) - 0x432C75F800021B1LL;
        v11 = SubscriptionSaver::SubscriptionSaver(
                v12,
                pItf,
                *((struct ISimpleTableWrite **)this + 4),
                v13 == 0,
                *((unsigned __int16 **)this + 10),
                *((_DWORD *)this + 27));
        goto LABEL_24;
      }
    }
    else
    {
      if ( (unsigned int)(v9 - 2) > 1 )
      {
        hr = -2147418113;
        goto LABEL_50;
      }
      v14 = CoTaskMemAlloc(0x40u);
      if ( v14 )
      {
        v15 = *((_QWORD *)this + 11) == tidTRANSIENTSUBSCRIBERPROPERTIES
           && *((_QWORD *)this + 12) == 0x432C75F800023B1LL
           || *((_QWORD *)this + 11) == tidTRANSIENTPUBLISHERPROPERTIES && *((_QWORD *)this + 12) == 0x432C75F800023B1LL;
        v11 = (SubscriptionSaver *)PropertySaver::PropertySaver(
                                     (__int64)v14,
                                     pItf,
                                     *((struct ISimpleTableWrite **)this + 4),
                                     *((_DWORD *)this + 12),
                                     *((_QWORD *)this + 8),
                                     *((_QWORD *)this + 9),
                                     v15,
                                     *((_DWORD *)this + 27));
        goto LABEL_24;
      }
    }
  }
  else
  {
    v10 = (EventClassSaver *)CoTaskMemAlloc(0x20u);
    if ( v10 )
    {
      v11 = EventClassSaver::EventClassSaver(
              v10,
              pItf,
              *((struct ISimpleTableWrite **)this + 4),
              *((_DWORD *)this + 27));
LABEL_24:
      v4 = v11;
      goto LABEL_26;
    }
  }
  v4 = 0;
LABEL_26:
  v21 = v4;
  if ( !v4 )
  {
    hr = -2147024882;
    goto LABEL_50;
  }
  hr = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 104LL))(*((_QWORD *)this + 4));
  if ( hr >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      v22 = i;
      v17 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 4) + 112LL))(*((_QWORD *)this + 4), &v20);
      hr = v17;
      if ( v17 == -2146367487 )
      {
        hr = 0;
        break;
      }
      if ( v17 < 0 )
        break;
      if ( (*(int (__fastcall **)(SubscriptionSaver *))(*(_QWORD *)v4 + 24LL))(v4) < 0 )
      {
        v30 = i | 0x8011042A00000000uLL;
        v31 = 0;
        hr = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**((_QWORD **)this + 5) + 104LL))(
               *((_QWORD *)this + 5),
               &v30);
        if ( hr >= 0 )
          v7 = 1;
        break;
      }
      if ( v20 == 1 || v20 == 2 )
      {
        v18 = (*(__int64 (__fastcall **)(SubscriptionSaver *))(*(_QWORD *)v4 + 8LL))(v4);
      }
      else
      {
        if ( v20 != 3 )
        {
          hr = -2147418113;
          goto LABEL_43;
        }
        v18 = (*(__int64 (__fastcall **)(SubscriptionSaver *))(*(_QWORD *)v4 + 16LL))(v4);
      }
      hr = v18;
LABEL_43:
      if ( hr < 0 )
        break;
    }
  }
LABEL_50:
  if ( v4 )
    (**(void (__fastcall ***)(SubscriptionSaver *, __int64))v4)(v4, 1);
  if ( pItf )
    ((void (__fastcall *)(struct IEventSystem *))pItf->lpVtbl->Release)(pItf);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( hr >= 0 && v7 )
    return (unsigned int)-2146367486;
  return (unsigned int)hr;
}

```

## disassembly

```asm
0x180049920  mov     r11, rsp
0x180049923  mov     [r11+10h], rbx
0x180049927  mov     [r11+18h], rsi
0x18004992b  push    rdi
0x18004992c  push    r12
0x18004992e  push    r13
0x180049930  push    r14
0x180049932  push    r15
0x180049934  sub     rsp, 0D0h
0x18004993b  mov     rax, cs:__security_cookie
0x180049942  xor     rax, rsp
0x180049945  mov     [rsp+0F8h+var_30], rax
0x18004994d  mov     rsi, rcx
0x180049950  mov     [rsp+0F8h+var_B4], 0
0x180049958  xor     r15d, r15d
0x18004995b  mov     [rsp+0F8h+var_A0], r15
0x180049960  xor     r12d, r12d
0x180049963  mov     [rsp+0F8h+var_98], r12
0x180049968  xor     edi, edi
0x18004996a  mov     [rsp+0F8h+var_B0], rdi
0x18004996f  xorps   xmm0, xmm0
0x180049972  movups  xmmword ptr [r11-60h], xmm0
0x180049977  movups  xmmword ptr [r11-50h], xmm0
0x18004997c  xor     r9d, r9d
0x18004997f  xor     eax, eax
0x180049981  lea     r8d, [r15+17h]
0x180049985  mov     [r11-40h], rax
0x180049989  mov     [r11-38h], eax
0x18004998d  xor     r13d, r13d
0x180049990  mov     rax, [rcx+50h]
0x180049994  test    rax, rax
0x180049997  jz      short loc_1800499B1
0x180049999  mov     [r11-58h], rax
0x18004999d  mov     [r11-50h], r13
0x1800499a1  mov     [r11-60h], r13d
0x1800499a5  mov     [r11-48h], r13d
0x1800499a9  lea     r9, [r11-60h]; pServerInfo
0x1800499ad  lea     r8d, [r15+10h]; dwClsCtx
0x1800499b1  movups  xmmword ptr [rsp+0F8h+var_90.pIID], xmm0
0x1800499b6  movups  xmmword ptr [rsp+0F8h+var_90.hr], xmm0
0x1800499bb  movups  [rsp+0F8h+var_70], xmm0
0x1800499c3  lea     rax, IID_IEventSystem
0x1800499ca  mov     [rsp+0F8h+var_90.pIID], rax
0x1800499cf  lea     rax, IID_IEventSystemInitialize
0x1800499d6  mov     [rsp+0F8h+var_78], rax
0x1800499de  lea     rax, [rsp+0F8h+var_90]
0x1800499e3  mov     [rsp+0F8h+pResults], rax; pResults
0x1800499e8  mov     [rsp+0F8h+dwCount], 2; dwCount
0x1800499f0  xor     edx, edx; punkOuter
0x1800499f2  lea     rcx, CLSID_CEventSystem; Clsid
0x1800499f9  call    cs:__imp_CoCreateInstanceEx
0x1800499ff  mov     ebx, eax
0x180049a01  mov     [rsp+0F8h+var_B8], eax
0x180049a05  test    eax, eax
0x180049a07  js      loc_180049C8B
0x180049a0d  cmp     [rsp+0F8h+var_90.hr], 0
0x180049a12  jl      loc_180049C8B
0x180049a18  cmp     dword ptr [rsp+0F8h+var_70+8], 0
0x180049a20  jl      loc_180049C8B
0x180049a26  mov     r15, [rsp+0F8h+var_90.pItf]
0x180049a2b  mov     [rsp+0F8h+var_A0], r15
0x180049a30  mov     r12, qword ptr [rsp+0F8h+var_70]
0x180049a38  mov     [rsp+0F8h+var_98], r12
0x180049a3d  mov     rax, [r12]
0x180049a41  mov     edx, 1
0x180049a46  mov     rcx, r12
0x180049a49  mov     rax, [rax+18h]
0x180049a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a52  mov     eax, [rsi+30h]
0x180049a55  test    eax, eax
0x180049a57  jnz     short loc_180049A83
0x180049a59  lea     ecx, [rax+20h]; cb
0x180049a5c  call    cs:__imp_CoTaskMemAlloc
0x180049a62  test    rax, rax
0x180049a65  jz      loc_180049B77
0x180049a6b  mov     r9d, [rsi+6Ch]; int
0x180049a6f  mov     r8, [rsi+20h]; struct ISimpleTableWrite *
0x180049a73  mov     rdx, r15; struct IEventSystem *
0x180049a76  mov     rcx, rax; this
0x180049a79  call    ??0EventClassSaver@@QEAA@PEAUIEventSystem@@PEAUISimpleTableWrite@@H@Z; EventClassSaver::EventClassSaver(IEventSystem *,ISimpleTableWrite *,int)
0x180049a7e  jmp     loc_180049B72
0x180049a83  cmp     eax, 1
0x180049a86  jnz     short loc_180049AE0
0x180049a88  lea     ecx, [rax+2Fh]; cb
0x180049a8b  call    cs:__imp_CoTaskMemAlloc
0x180049a91  test    rax, rax
0x180049a94  jz      loc_180049B77
0x180049a9a  mov     edx, [rsi+6Ch]
0x180049a9d  mov     r8, [rsi+50h]
0x180049aa1  mov     rcx, [rsi+58h]
0x180049aa5  sub     rcx, cs:tidTRANSIENTSUBSCRIPTIONS
0x180049aac  jnz     short loc_180049AB9
0x180049aae  mov     rcx, [rsi+60h]
0x180049ab2  sub     rcx, cs:qword_180061388
0x180049ab9  xor     r9d, r9d
0x180049abc  test    rcx, rcx
0x180049abf  setz    r9b; int
0x180049ac3  mov     dword ptr [rsp+0F8h+pResults], edx; int
0x180049ac7  mov     qword ptr [rsp+0F8h+dwCount], r8; unsigned __int16 *
0x180049acc  mov     r8, [rsi+20h]; struct ISimpleTableWrite *
0x180049ad0  mov     rdx, r15; struct IEventSystem *
0x180049ad3  mov     rcx, rax; this
0x180049ad6  call    ??0SubscriptionSaver@@QEAA@PEAUIEventSystem@@PEAUISimpleTableWrite@@HPEAGH@Z; SubscriptionSaver::SubscriptionSaver(IEventSystem *,ISimpleTableWrite *,int,ushort *,int)
0x180049adb  jmp     loc_180049B72
0x180049ae0  add     eax, 0FFFFFFFEh
0x180049ae3  cmp     eax, 1
0x180049ae6  jbe     short loc_180049AF2
0x180049ae8  mov     ebx, 8000FFFFh
0x180049aed  jmp     loc_180049CAB
0x180049af2  mov     ecx, 40h ; '@'; cb
0x180049af7  call    cs:__imp_CoTaskMemAlloc
0x180049afd  mov     r10, rax
0x180049b00  test    rax, rax
0x180049b03  jz      short loc_180049B77
0x180049b05  mov     edx, [rsi+6Ch]
0x180049b08  mov     rcx, [rsi+58h]
0x180049b0c  cmp     rcx, cs:tidTRANSIENTSUBSCRIBERPROPERTIES
0x180049b13  jnz     short loc_180049B22
0x180049b15  mov     rcx, [rsi+60h]
0x180049b19  cmp     rcx, cs:qword_180062180
0x180049b20  jz      short loc_180049B3C
0x180049b22  mov     rax, [rsi+58h]
0x180049b26  cmp     rax, cs:tidTRANSIENTPUBLISHERPROPERTIES
0x180049b2d  jnz     short loc_180049B43
0x180049b2f  mov     rax, [rsi+60h]
0x180049b33  cmp     rax, cs:qword_180062170
0x180049b3a  jnz     short loc_180049B43
0x180049b3c  mov     eax, 1
0x180049b41  jmp     short loc_180049B45
0x180049b43  xor     eax, eax
0x180049b45  mov     [rsp+0F8h+var_C0], edx
0x180049b49  mov     [rsp+0F8h+var_C8], eax
0x180049b4d  mov     rax, [rsi+48h]
0x180049b51  mov     [rsp+0F8h+pResults], rax
0x180049b56  mov     rax, [rsi+40h]
0x180049b5a  mov     qword ptr [rsp+0F8h+dwCount], rax
0x180049b5f  mov     r9d, [rsi+30h]
0x180049b63  mov     r8, [rsi+20h]
0x180049b67  mov     rdx, r15
0x180049b6a  mov     rcx, r10
0x180049b6d  call    ??0PropertySaver@@QEAA@PEAUIEventSystem@@PEAUISimpleTableWrite@@W4EventObjectKind@@PEAUIEventSubscription2@@PEAUIEventSubscription3@@HH@Z; PropertySaver::PropertySaver(IEventSystem *,ISimpleTableWrite *,EventObjectKind,IEventSubscription2 *,IEventSubscription3 *,int,int)
0x180049b72  mov     rdi, rax
0x180049b75  jmp     short loc_180049B79
0x180049b77  xor     edi, edi
0x180049b79  mov     [rsp+0F8h+var_B0], rdi
0x180049b7e  test    rdi, rdi
0x180049b81  jnz     short loc_180049B8D
0x180049b83  mov     ebx, 8007000Eh
0x180049b88  jmp     loc_180049CAB
0x180049b8d  mov     rcx, [rsi+20h]
0x180049b91  mov     rax, [rcx]
0x180049b94  mov     rax, [rax+68h]
0x180049b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b9d  mov     ebx, eax
0x180049b9f  mov     [rsp+0F8h+var_B8], eax
0x180049ba3  test    eax, eax
0x180049ba5  js      loc_180049CAF
0x180049bab  xor     r14d, r14d
0x180049bae  mov     [rsp+0F8h+var_A8], r14d
0x180049bb3  mov     rcx, [rsi+20h]
0x180049bb7  mov     rax, [rcx]
0x180049bba  lea     rdx, [rsp+0F8h+var_B4]
0x180049bbf  mov     rax, [rax+70h]
0x180049bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049bc8  mov     ebx, eax
0x180049bca  mov     [rsp+0F8h+var_B8], eax
0x180049bce  cmp     eax, 80110801h
0x180049bd3  jnz     short loc_180049BDC
0x180049bd5  xor     ebx, ebx
0x180049bd7  jmp     loc_180049CAB
0x180049bdc  test    eax, eax
0x180049bde  js      loc_180049CAF
0x180049be4  mov     rax, [rdi]
0x180049be7  mov     rcx, rdi
0x180049bea  mov     rax, [rax+18h]
0x180049bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049bf3  mov     [rsp+0F8h+var_B8], eax
0x180049bf7  test    eax, eax
0x180049bf9  jns     short loc_180049C43
0x180049bfb  mov     [rsp+0F8h+var_40], r14d
0x180049c03  mov     [rsp+0F8h+var_38], 0
0x180049c0e  mov     [rsp+0F8h+var_3C], 8011042Ah
0x180049c19  mov     rcx, [rsi+28h]
0x180049c1d  mov     rax, [rcx]
0x180049c20  lea     rdx, [rsp+0F8h+var_40]
0x180049c28  mov     rax, [rax+68h]
0x180049c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c31  mov     ebx, eax
0x180049c33  mov     [rsp+0F8h+var_B8], eax
0x180049c37  test    eax, eax
0x180049c39  js      short loc_180049CAF
0x180049c3b  mov     r13d, 1
0x180049c41  jmp     short loc_180049CAF
0x180049c43  mov     eax, [rsp+0F8h+var_B4]
0x180049c47  sub     eax, 1
0x180049c4a  jz      short loc_180049C6A
0x180049c4c  sub     eax, 1
0x180049c4f  jz      short loc_180049C6A
0x180049c51  sub     eax, 1
0x180049c54  jz      short loc_180049C61
0x180049c56  mov     ebx, 8000FFFFh
0x180049c5b  mov     [rsp+0F8h+var_B8], ebx
0x180049c5f  jmp     short loc_180049C7F
0x180049c61  mov     rax, [rdi]
0x180049c64  mov     rax, [rax+10h]
0x180049c68  jmp     short loc_180049C71
0x180049c6a  mov     rax, [rdi]
0x180049c6d  mov     rax, [rax+8]
0x180049c71  mov     rcx, rdi
0x180049c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049c79  mov     [rsp+0F8h+var_B8], eax
0x180049c7d  mov     ebx, eax
0x180049c7f  test    ebx, ebx
0x180049c81  js      short loc_180049CAF
0x180049c83  inc     r14d
0x180049c86  jmp     loc_180049BAE
0x180049c8b  test    ebx, ebx
0x180049c8d  js      short loc_180049CAF
0x180049c8f  mov     eax, [rsp+0F8h+var_90.hr]
0x180049c93  test    eax, eax
0x180049c95  jns     short loc_180049C9F
0x180049c97  mov     ebx, eax
0x180049c99  mov     [rsp+0F8h+var_B8], eax
0x180049c9d  jmp     short loc_180049CAF
0x180049c9f  mov     eax, dword ptr [rsp+0F8h+var_70+8]
0x180049ca6  test    eax, eax
0x180049ca8  cmovs   ebx, eax
0x180049cab  mov     [rsp+0F8h+var_B8], ebx
0x180049caf  test    rdi, rdi
0x180049cb2  jz      short loc_180049CC7
0x180049cb4  mov     rax, [rdi]
0x180049cb7  mov     edx, 1
0x180049cbc  mov     rcx, rdi
0x180049cbf  mov     rax, [rax]
0x180049cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049cc7  test    r15, r15
0x180049cca  jz      short loc_180049CDB
0x180049ccc  mov     rax, [r15]
0x180049ccf  mov     rcx, r15
0x180049cd2  mov     rax, [rax+10h]
0x180049cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049cdb  test    r12, r12
0x180049cde  jz      short loc_180049CF0
0x180049ce0  mov     rax, [r12]
0x180049ce4  mov     rcx, r12
0x180049ce7  mov     rax, [rax+10h]
0x180049ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049cf0  test    ebx, ebx
0x180049cf2  js      short loc_180049CFF
0x180049cf4  mov     eax, 80110802h
0x180049cf9  test    r13d, r13d
0x180049cfc  cmovnz  ebx, eax
0x180049cff  mov     eax, ebx
0x180049d01  mov     rcx, [rsp+0F8h+var_30]
0x180049d09  xor     rcx, rsp; StackCookie
0x180049d0c  call    __security_check_cookie
0x180049d11  lea     r11, [rsp+0F8h+var_28]
0x180049d19  mov     rbx, [r11+38h]
0x180049d1d  mov     rsi, [r11+40h]
0x180049d21  mov     rsp, r11
0x180049d24  pop     r15
0x180049d26  pop     r14
0x180049d28  pop     r13
0x180049d2a  pop     r12
0x180049d2c  pop     rdi
0x180049d2d  retn
0x180056a28  push    rbp
0x180056a2a  sub     rsp, 40h
0x180056a2e  mov     rbp, rdx
0x180056a31  mov     rcx, [rbp+48h]
0x180056a35  test    rcx, rcx
0x180056a38  jz      short loc_180056A4B
0x180056a3a  mov     rax, [rcx]
0x180056a3d  mov     edx, 1
0x180056a42  mov     rax, [rax]
0x180056a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056a4a  nop
0x180056a4b  mov     rcx, [rbp+58h]
0x180056a4f  test    rcx, rcx
0x180056a52  jz      short loc_180056A61
0x180056a54  mov     rax, [rcx]
0x180056a57  mov     rax, [rax+10h]
0x180056a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056a60  nop
0x180056a61  mov     rcx, [rbp+60h]
0x180056a65  test    rcx, rcx
0x180056a68  jz      short loc_180056A77
0x180056a6a  mov     rax, [rcx]
0x180056a6d  mov     rax, [rax+10h]
0x180056a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056a76  nop
0x180056a77  add     rsp, 40h
0x180056a7b  pop     rbp
0x180056a7c  retn
```
