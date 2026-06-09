# CEnhancedStorageActEnumerator::GetACTs(IEnhancedStorageACT * * *,ulong *)

- ea: `0x180004380`
- end: `0x1800046ad`
- name: `?GetACTs@CEnhancedStorageActEnumerator@@UEAAJPEAPEAPEAUIEnhancedStorageACT@@PEAK@Z`
- size: `813`
- prototype: `__int64 __fastcall(CEnhancedStorageActEnumerator *__hidden this, struct IEnhancedStorageACT ***, unsigned int *)`
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002d68`
- `0x180003c54`
- `0x180003ce0`
- `0x180003df0`
- `0x180003e58`
- `0x180003ed0`
- `0x180003ff4`
- `0x180004220`
- `0x180004380`
- `0x1800046b4`
- `0x1800060a0`
- `0x180006208`
- `0x18000c4f0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180004475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800045f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800045f3`

## pseudocode

```c
__int64 __fastcall CEnhancedStorageActEnumerator::GetACTs(
        CEnhancedStorageActEnumerator *this,
        struct IEnhancedStorageACT ***a2,
        unsigned int *a3)
{
  __int64 v5; // rcx
  struct IEnhancedStorageACT **v6; // rbx
  __int64 v7; // r14
  int DeviceList; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  unsigned __int64 v11; // rsi
  const unsigned __int16 **v12; // rax
  CEnhancedStorageAct *v13; // rdi
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 i; // rdi
  unsigned int v17; // ebx
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  CEnhancedStorageAct *v20; // [rsp+38h] [rbp-C8h] BYREF
  struct IEnhancedStorageACT *v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v23; // [rsp+50h] [rbp-B0h]
  __int64 v24; // [rsp+58h] [rbp-A8h]
  int v25; // [rsp+60h] [rbp-A0h]
  _BYTE v26[272]; // [rsp+70h] [rbp-90h] BYREF

  v19 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids, a2, a3);
  CESTTrackFn::CESTTrackFn((CESTTrackFn *)v26, "CEnhancedStorageActEnumerator::GetACTs", &v19);
  if ( a2 && a3 )
  {
    v6 = 0;
    *a3 = 0;
    v7 = 0;
    DeviceList = CEnhancedStorageActEnumerator::GetDeviceList(v5, &v22);
    v11 = v23;
    v19 = DeviceList;
    if ( v23 )
    {
      v21 = 0;
      v20 = 0;
      v6 = (struct IEnhancedStorageACT **)CoTaskMemAlloc(8 * v23);
      if ( !v6 )
      {
        v19 = -2147024882;
LABEL_38:
        v17 = v19;
        CESTTrackFn::~CESTTrackFn((CESTTrackFn *)v26);
        ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>::~CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>(&v22);
        return v17;
      }
      while ( 1 )
      {
        if ( (unsigned int)v7 >= v11 )
          goto LABEL_30;
        v19 = ATL::CComObject<CEnhancedStorageAct>::CreateInstance(&v20);
        if ( v19 < 0 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v15 = 14;
            goto LABEL_23;
          }
          goto LABEL_30;
        }
        v12 = (const unsigned __int16 **)ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>::operator[](
                                           &v22,
                                           (unsigned int)v7);
        v13 = v20;
        v19 = CEnhancedStorageAct::Initialize(v20, *v12);
        if ( v19 < 0 )
        {
          if ( v13 )
            (*(void (__fastcall **)(CEnhancedStorageAct *, __int64))(*(_QWORD *)v13 + 112LL))(v13, 1);
          if ( v19 < 0 )
            break;
        }
        v19 = (**(__int64 (__fastcall ***)(CEnhancedStorageAct *, GUID *, struct IEnhancedStorageACT **))v13)(
                v13,
                &IID_IEnhancedStorageACT,
                &v21);
        if ( v19 < 0 )
        {
          if ( v13 )
            (*(void (__fastcall **)(CEnhancedStorageAct *, __int64))(*(_QWORD *)v13 + 112LL))(v13, 1);
          if ( v19 < 0 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v15 = 16;
              goto LABEL_23;
            }
            goto LABEL_30;
          }
        }
        v6[v7] = v21;
        v7 = (unsigned int)(v7 + 1);
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v15 = 15;
LABEL_23:
        WPP_SF_d(v14[2], v15, &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids, (unsigned int)v19);
      }
    }
LABEL_30:
    if ( v19 >= 0 )
    {
      *a2 = v6;
      *a3 = v11;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, v11);
    }
    else
    {
      for ( i = 0; (unsigned int)i < (unsigned int)v7; i = (unsigned int)(i + 1) )
        ((void (__fastcall *)(struct IEnhancedStorageACT *))v6[i]->lpVtbl->Release)(v6[i]);
      if ( v6 )
        CoTaskMemFree(v6);
    }
    goto LABEL_38;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      &WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids,
      "pppIEnhancedStorageACTs && pcEnhancedStorageACTs");
  CESTTrackFn::~CESTTrackFn((CESTTrackFn *)v26);
  ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>::~CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>(&v22);
  return 2147942487LL;
}

```

## disassembly

```asm
0x180004380  mov     [rsp-8+arg_0], rbx
0x180004385  push    rbp
0x180004386  push    rsi
0x180004387  push    rdi
0x180004388  push    r12
0x18000438a  push    r13
0x18000438c  push    r14
0x18000438e  push    r15
0x180004390  lea     rbp, [rsp-90h]
0x180004398  sub     rsp, 190h
0x18000439f  mov     rax, cs:__security_cookie
0x1800043a6  xor     rax, rsp
0x1800043a9  mov     [rbp+0C0h+var_40], rax
0x1800043b0  mov     r15, r8
0x1800043b3  mov     [rsp+1C0h+var_190], 0
0x1800043bb  mov     r13, rdx
0x1800043be  mov     [rsp+1C0h+var_178], 0
0x1800043c7  mov     [rsp+1C0h+var_170], 0
0x1800043d0  mov     [rsp+1C0h+var_168], 0
0x1800043d9  mov     [rsp+1C0h+var_160], 0
0x1800043e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800043e8  lea     rdi, WPP_GLOBAL_Control
0x1800043ef  cmp     rcx, rdi
0x1800043f2  jz      short loc_180004417
0x1800043f4  test    byte ptr [rcx+1Ch], 10h
0x1800043f8  jz      short loc_180004417
0x1800043fa  mov     rcx, [rcx+10h]
0x1800043fe  mov     edx, 0Ch
0x180004403  mov     [rsp+1C0h+var_1A0], r8
0x180004408  mov     r9, r13
0x18000440b  lea     r8, WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids
0x180004412  call    WPP_SF_qq
0x180004417  lea     r8, [rsp+1C0h+var_190]; int *
0x18000441c  lea     rdx, aCenhancedstora_14; "CEnhancedStorageActEnumerator::GetACTs"
0x180004423  lea     rcx, [rsp+1C0h+var_150]; this
0x180004428  call    ??0CESTTrackFn@@QEAA@PEBDPEAJ@Z; CESTTrackFn::CESTTrackFn(char const *,long *)
0x18000442d  test    r13, r13
0x180004430  jz      loc_18000463C
0x180004436  test    r15, r15
0x180004439  jz      loc_18000463C
0x18000443f  xor     ebx, ebx
0x180004441  lea     rdx, [rsp+1C0h+var_178]
0x180004446  mov     [r15], ebx
0x180004449  xor     r14d, r14d
0x18000444c  call    ?GetDeviceList@CEnhancedStorageActEnumerator@@AEAAJAEAV?$CAtlArray@VDeviceData@@V?$CElementTraits@VDeviceData@@@ATL@@@ATL@@@Z; CEnhancedStorageActEnumerator::GetDeviceList(ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>> &)
0x180004451  mov     rsi, [rsp+1C0h+var_170]
0x180004456  mov     [rsp+1C0h+var_190], eax
0x18000445a  test    rsi, rsi
0x18000445d  jz      loc_1800045C6
0x180004463  lea     rcx, ds:0[rsi*8]; cb
0x18000446b  mov     [rsp+1C0h+var_180], rbx
0x180004470  mov     [rsp+1C0h+var_188], rbx
0x180004475  call    cs:__imp_CoTaskMemAlloc
0x18000447b  mov     rbx, rax
0x18000447e  test    rax, rax
0x180004481  jnz     short loc_180004490
0x180004483  mov     [rsp+1C0h+var_190], 8007000Eh
0x18000448b  jmp     loc_180004620
0x180004490  mov     r12d, r14d
0x180004493  cmp     r12, rsi
0x180004496  jnb     loc_1800045BF
0x18000449c  lea     rcx, [rsp+1C0h+var_188]
0x1800044a1  call    ?CreateInstance@?$CComObject@VCEnhancedStorageAct@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CEnhancedStorageAct>::CreateInstance(ATL::CComObject<CEnhancedStorageAct> * *)
0x1800044a6  mov     [rsp+1C0h+var_190], eax
0x1800044aa  test    eax, eax
0x1800044ac  js      loc_18000459F
0x1800044b2  mov     edx, r12d
0x1800044b5  lea     rcx, [rsp+1C0h+var_178]
0x1800044ba  call    ??A?$CAtlArray@VDeviceData@@V?$CElementTraits@VDeviceData@@@ATL@@@ATL@@QEAAAEAVDeviceData@@_K@Z; ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>::operator[](unsigned __int64)
0x1800044bf  mov     rdi, [rsp+1C0h+var_188]
0x1800044c4  mov     rcx, rdi; this
0x1800044c7  mov     rdx, [rax]; unsigned __int16 *
0x1800044ca  call    ?Initialize@CEnhancedStorageAct@@AEAAJPEBG@Z; CEnhancedStorageAct::Initialize(ushort const *)
0x1800044cf  mov     [rsp+1C0h+var_190], eax
0x1800044d3  test    eax, eax
0x1800044d5  jns     short loc_1800044F7
0x1800044d7  test    rdi, rdi
0x1800044da  jz      short loc_1800044F0
0x1800044dc  mov     rax, [rdi]
0x1800044df  mov     edx, 1
0x1800044e4  mov     rcx, rdi
0x1800044e7  mov     rax, [rax+70h]
0x1800044eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044f0  cmp     [rsp+1C0h+var_190], 0
0x1800044f5  jl      short loc_18000454A
0x1800044f7  mov     rax, [rdi]
0x1800044fa  lea     r8, [rsp+1C0h+var_180]
0x1800044ff  lea     rdx, IID_IEnhancedStorageACT
0x180004506  mov     rcx, rdi
0x180004509  mov     rax, [rax]
0x18000450c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004511  mov     [rsp+1C0h+var_190], eax
0x180004515  test    eax, eax
0x180004517  jns     short loc_180004539
0x180004519  test    rdi, rdi
0x18000451c  jz      short loc_180004532
0x18000451e  mov     rax, [rdi]
0x180004521  mov     edx, 1
0x180004526  mov     rcx, rdi
0x180004529  mov     rax, [rax+70h]
0x18000452d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004532  cmp     [rsp+1C0h+var_190], 0
0x180004537  jl      short loc_18000457F
0x180004539  mov     rax, [rsp+1C0h+var_180]
0x18000453e  mov     [rbx+r14*8], rax
0x180004542  inc     r14d
0x180004545  jmp     loc_180004490
0x18000454a  mov     rcx, cs:WPP_GLOBAL_Control
0x180004551  lea     rdi, WPP_GLOBAL_Control
0x180004558  cmp     rcx, rdi
0x18000455b  jz      short loc_1800045C6
0x18000455d  test    byte ptr [rcx+1Ch], 2
0x180004561  jz      short loc_1800045C6
0x180004563  mov     edx, 0Fh
0x180004568  mov     r9d, [rsp+1C0h+var_190]
0x18000456d  lea     r8, WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids
0x180004574  mov     rcx, [rcx+10h]
0x180004578  call    WPP_SF_d
0x18000457d  jmp     short loc_1800045C6
0x18000457f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004586  lea     rdi, WPP_GLOBAL_Control
0x18000458d  cmp     rcx, rdi
0x180004590  jz      short loc_1800045C6
0x180004592  test    byte ptr [rcx+1Ch], 2
0x180004596  jz      short loc_1800045C6
0x180004598  mov     edx, 10h
0x18000459d  jmp     short loc_180004568
0x18000459f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045a6  lea     rdi, WPP_GLOBAL_Control
0x1800045ad  cmp     rcx, rdi
0x1800045b0  jz      short loc_1800045C6
0x1800045b2  test    byte ptr [rcx+1Ch], 2
0x1800045b6  jz      short loc_1800045C6
0x1800045b8  mov     edx, 0Eh
0x1800045bd  jmp     short loc_180004568
0x1800045bf  lea     rdi, WPP_GLOBAL_Control
0x1800045c6  cmp     [rsp+1C0h+var_190], 0
0x1800045cb  jge     short loc_1800045FB
0x1800045cd  xor     edi, edi
0x1800045cf  test    r14d, r14d
0x1800045d2  jz      short loc_1800045EB
0x1800045d4  mov     rcx, [rbx+rdi*8]
0x1800045d8  mov     rax, [rcx]
0x1800045db  mov     rax, [rax+10h]
0x1800045df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045e4  inc     edi
0x1800045e6  cmp     edi, r14d
0x1800045e9  jb      short loc_1800045D4
0x1800045eb  test    rbx, rbx
0x1800045ee  jz      short loc_180004620
0x1800045f0  mov     rcx, rbx; pv
0x1800045f3  call    cs:__imp_CoTaskMemFree
0x1800045f9  jmp     short loc_180004620
0x1800045fb  mov     [r13+0], rbx
0x1800045ff  mov     [r15], esi
0x180004602  mov     rcx, cs:WPP_GLOBAL_Control
0x180004609  cmp     rcx, rdi
0x18000460c  jz      short loc_180004620
0x18000460e  test    byte ptr [rcx+1Ch], 20h
0x180004612  jz      short loc_180004620
0x180004614  mov     rcx, [rcx+10h]
0x180004618  mov     r9, rsi
0x18000461b  call    WPP_SF_P
0x180004620  mov     ebx, [rsp+1C0h+var_190]
0x180004624  lea     rcx, [rsp+1C0h+var_150]; this
0x180004629  call    ??1CESTTrackFn@@QEAA@XZ; CESTTrackFn::~CESTTrackFn(void)
0x18000462e  lea     rcx, [rsp+1C0h+var_178]
0x180004633  call    ??1?$CAtlArray@VDeviceData@@V?$CElementTraits@VDeviceData@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>::~CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>(void)
0x180004638  mov     eax, ebx
0x18000463a  jmp     short loc_180004683
0x18000463c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004643  cmp     rcx, rdi
0x180004646  jz      short loc_18000466A
0x180004648  test    byte ptr [rcx+1Ch], 2
0x18000464c  jz      short loc_18000466A
0x18000464e  mov     rcx, [rcx+10h]
0x180004652  lea     r9, aPppienhancedst; "pppIEnhancedStorageACTs && pcEnhancedSt"...
0x180004659  mov     edx, 0Dh
0x18000465e  lea     r8, WPP_5b4d9d83854732f416e1e83a2d1e50cf_Traceguids
0x180004665  call    WPP_SF_s
0x18000466a  lea     rcx, [rsp+1C0h+var_150]; this
0x18000466f  call    ??1CESTTrackFn@@QEAA@XZ; CESTTrackFn::~CESTTrackFn(void)
0x180004674  lea     rcx, [rsp+1C0h+var_178]
0x180004679  call    ??1?$CAtlArray@VDeviceData@@V?$CElementTraits@VDeviceData@@@ATL@@@ATL@@QEAA@XZ; ATL::CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>::~CAtlArray<DeviceData,ATL::CElementTraits<DeviceData>>(void)
0x18000467e  mov     eax, 80070057h
0x180004683  mov     rcx, [rbp+0C0h+var_40]
0x18000468a  xor     rcx, rsp; StackCookie
0x18000468d  call    __security_check_cookie
0x180004692  mov     rbx, [rsp+1C0h+arg_0]
0x18000469a  add     rsp, 190h
0x1800046a1  pop     r15
0x1800046a3  pop     r14
0x1800046a5  pop     r13
0x1800046a7  pop     r12
0x1800046a9  pop     rdi
0x1800046aa  pop     rsi
0x1800046ab  pop     rbp
0x1800046ac  retn
```
