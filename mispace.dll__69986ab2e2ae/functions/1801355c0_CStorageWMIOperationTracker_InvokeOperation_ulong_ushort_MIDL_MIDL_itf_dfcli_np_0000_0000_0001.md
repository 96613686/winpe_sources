# CStorageWMIOperationTracker::InvokeOperation(ulong,ushort *,__MIDL___MIDL_itf_dfcli_np_0000_0000_0001)

- ea: `0x1801355c0`
- end: `0x180135d96`
- name: `?InvokeOperation@CStorageWMIOperationTracker@@UEAAJKPEAGU__MIDL___MIDL_itf_dfcli_np_0000_0000_0001@@@Z`
- size: `2006`
- prototype: `int __high(unsigned int, unsigned __int16 *, struct __MIDL___MIDL_itf_dfcli_np_0000_0000_0001)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006350`
- `0x1801355c0`
- `0x1801b0a2c`
- `0x1801b0b88`
- `0x1801b0e90`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18013566a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18013566a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1801356db`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1801356db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180135cea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180135cea`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1801357d8`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1801357d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180135841`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180135cfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180135841`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180135cfa`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CStorageWMIOperationTracker::InvokeOperation(
        __int64 a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        _DWORD *a4)
{
  void *v8; // rcx
  HRESULT v9; // ebx
  _OWORD *v10; // r14
  __int64 v11; // rcx
  _BYTE *v12; // rax
  __int64 (__fastcall ***v13)(_QWORD, GUID *, _QWORD); // rbx
  __int64 (__fastcall *v14)(_QWORD, GUID *, _QWORD); // r13
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v17)(_QWORD, GUID *, IUnknown **); // r13
  IUnknown *v18; // rdx
  __int64 *v19; // r13
  __int64 v20; // rdx
  int v21; // esi
  void (__fastcall *v22)(__int64, __int128 *); // rax
  __int64 v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 (__fastcall ***v29)(_QWORD, _QWORD, _QWORD); // rcx
  IUnknown *v30; // rcx
  IUnknown *pProxy; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v33; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v34)(_QWORD, GUID *, IUnknown **); // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v35[2]; // [rsp+68h] [rbp-98h] BYREF
  int v36; // [rsp+78h] [rbp-88h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v38; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v39[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v40[2]; // [rsp+A0h] [rbp-60h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+B0h] [rbp-50h]
  __int128 v42; // [rsp+B8h] [rbp-48h]
  __int128 v43; // [rsp+C8h] [rbp-38h]
  __int128 v44; // [rsp+D8h] [rbp-28h]
  _OWORD v45[3]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v46; // [rsp+120h] [rbp+20h] BYREF

  v40[0] = qword_1802E5D80;
  v40[1] = 0;
  v35[0] = qword_1802E5D80;
  v35[1] = 0;
  v39[0] = qword_1802E5D80;
  v39[1] = 0;
  v8 = 0;
  v38 = 0;
  v36 = 0;
  pv = 0;
  pProxy = 0;
  v34 = 0;
  v46 = 0;
  HIDWORD(v43) = 0;
  HIDWORD(v44) = 0;
  if ( !a3 && a2 != 5 )
  {
    v9 = -2147024809;
    goto LABEL_88;
  }
  lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 184);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 184));
  if ( !*(_DWORD *)(a1 + 256) )
  {
    if ( a4[3] )
      v46 = *(_OWORD *)(a1 + 56);
    v10 = (_OWORD *)(a1 + 40);
    if ( a1 != -40 )
    {
      v11 = 16;
      v12 = (_BYTE *)(a1 + 40);
      do
      {
        *v12++ = 0;
        --v11;
      }
      while ( v11 );
    }
    *(_QWORD *)(a1 + 176) = 0;
    *(_QWORD *)(a1 + 224) = 0;
    *(_DWORD *)(a1 + 152) = 0;
    ResetEvent(*(HANDLE *)(a1 + 88));
    *(_QWORD *)(a1 + 124) = 0;
    *(_QWORD *)(a1 + 132) = 0;
    *(_DWORD *)(a1 + 232) = *a4;
    *(_DWORD *)(a1 + 236) = a4[1];
    v13 = *(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD))(a1 + 144);
    v14 = **v13;
    v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v34;
    if ( v34 )
    {
      v34 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v15)[2])(v15);
    }
    v9 = v14(v13, &IID_IUnknown, &v34);
    if ( v9 < 0 )
      goto LABEL_87;
    v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v34;
    v17 = **v34;
    v18 = pProxy;
    if ( pProxy )
    {
      pProxy = 0;
      ((void (__fastcall *)(IUnknown *))v18->lpVtbl->Release)(v18);
    }
    v9 = v17(v16, &IID_IDefragOptions, &pProxy);
    if ( v9 < 0 )
      goto LABEL_87;
    v9 = CoSetProxyBlanket(
           pProxy,
           0xFFFFFFFF,
           0xFFFFFFFF,
           (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
           0,
           3u,
           (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
           0x40u);
    if ( v9 < 0 )
      goto LABEL_87;
    if ( a3 )
    {
      v9 = CBsString::Set((CBsString *)(a1 + 160), a3);
      if ( v9 < 0 )
        goto LABEL_87;
      if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, LPVOID *))(*(_QWORD *)a1 + 72LL))(a1, a3, &pv) < 0 )
      {
        v9 = CBsString::Set((CBsString *)v39, a3);
        if ( v9 < 0 )
          goto LABEL_87;
      }
      else
      {
        v9 = CBsString::Set((CBsString *)v39, (const unsigned __int16 *)pv);
        if ( v9 < 0 )
          goto LABEL_87;
        CoTaskMemFree(pv);
        pv = 0;
      }
      v19 = (__int64 *)v39[0];
    }
    else
    {
      v19 = qword_1802E5D80;
    }
    *(_DWORD *)(a1 + 240) = 0;
    if ( a2 == 1 )
    {
      if ( !a4[2] )
      {
LABEL_29:
        v9 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, int *, LPVOID *))(**(_QWORD **)(a1 + 144)
                                                                                          + 128LL))(
               *(_QWORD *)(a1 + 144),
               a3,
               &v36,
               &v38);
        if ( v9 < 0 )
          goto LABEL_87;
        if ( v36 != 1 || !v38 || *((_DWORD *)v38 + 2) != 1 )
        {
          v9 = -1996488694;
          goto LABEL_87;
        }
        v21 = 0;
        *v10 = *(_OWORD *)((char *)v38 + 12);
        v26 = CBsString::FormatResource((CBsString *)v40, g_hInstance, 0x10Fu, v19);
LABEL_78:
        v9 = v26;
        if ( v26 >= 0 )
        {
          v28 = *(_QWORD *)(a1 + 264);
          if ( v28 )
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 24LL))(v28, v40[0]);
          if ( v21 == 1 )
          {
            v9 = -1996488704;
          }
          else
          {
            v9 = v21;
            if ( v21 >= 0 && *(_QWORD *)v10 == *(_QWORD *)(a1 + 72) && *(_QWORD *)(a1 + 48) == *(_QWORD *)(a1 + 80) )
              v9 = -1996488699;
          }
        }
        goto LABEL_87;
      }
    }
    else if ( !a4[2] )
    {
      v20 = 0;
LABEL_35:
      v9 = ((__int64 (__fastcall *)(IUnknown *, __int64))pProxy->lpVtbl[1].AddRef)(pProxy, v20);
      if ( v9 < 0 )
        goto LABEL_87;
      if ( a2 > 6 )
      {
        switch ( a2 )
        {
          case 7u:
            v9 = CBsString::FormatResource((CBsString *)v35, g_hInstance, 0x12Du);
            if ( v9 < 0 )
              goto LABEL_87;
            v24 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, __int128 *, __int64))(**(_QWORD **)(a1 + 144) + 96LL))(
                    *(_QWORD *)(a1 + 144),
                    a3,
                    (unsigned int)a4[4],
                    &v46,
                    a1 + 40);
            break;
          case 8u:
            v9 = CBsString::FormatResource((CBsString *)v35, g_hInstance, 0x12Eu);
            if ( v9 < 0 )
              goto LABEL_87;
            v24 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, __int128 *, __int64))(**(_QWORD **)(a1 + 144) + 112LL))(
                    *(_QWORD *)(a1 + 144),
                    a3,
                    (unsigned int)a4[4],
                    &v46,
                    a1 + 40);
            break;
          case 9u:
            v9 = CBsString::FormatResource((CBsString *)v35, g_hInstance, 0x12Eu);
            if ( v9 < 0 )
              goto LABEL_87;
            v24 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int128 *, __int64))(**(_QWORD **)(a1 + 144) + 120LL))(
                    *(_QWORD *)(a1 + 144),
                    a3,
                    &v46,
                    a1 + 40);
            break;
          case 0xAu:
            v9 = CBsString::FormatResource((CBsString *)v35, g_hInstance, 0x143u);
            if ( v9 < 0 )
              goto LABEL_87;
            *(_QWORD *)&v42 = 0;
            *((_QWORD *)&v42 + 1) = a3;
            *(_QWORD *)&v43 = &v46;
            DWORD2(v43) = 0;
            *(_QWORD *)&v44 = 0;
            DWORD2(v44) = 0;
            v27 = *(_QWORD *)(a1 + 144);
            v45[0] = v42;
            v45[1] = v43;
            v45[2] = v44;
            v24 = (*(__int64 (__fastcall **)(__int64, _OWORD *, __int64))(*(_QWORD *)v27 + 176LL))(v27, v45, a1 + 40);
            break;
          default:
LABEL_64:
            v21 = -1996488695;
            goto LABEL_77;
        }
      }
      else
      {
        switch ( a2 )
        {
          case 6u:
            v9 = CBsString::FormatResource((CBsString *)v35, g_hInstance, 0x12Eu);
            if ( v9 < 0 )
              goto LABEL_87;
            v24 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, __int128 *, __int64))(**(_QWORD **)(a1 + 144) + 104LL))(
                    *(_QWORD *)(a1 + 144),
                    a3,
                    (unsigned int)a4[4],
                    &v46,
                    a1 + 40);
            break;
          case 1u:
            goto LABEL_29;
          case 2u:
            v9 = CBsString::FormatResource((CBsString *)v35, g_hInstance, 0x110u);
            if ( v9 < 0 )
              goto LABEL_87;
            v21 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int128 *, __int64))(**(_QWORD **)(a1 + 144) + 24LL))(
                    *(_QWORD *)(a1 + 144),
                    a3,
                    &v46,
                    a1 + 40);
            if ( v21 >= 0 )
            {
              v25 = *(_QWORD *)(a1 + 144);
              v33 = *v10;
              (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v25 + 168LL))(v25, &v33);
            }
            *(_DWORD *)(a1 + 240) = 1;
            goto LABEL_77;
          case 3u:
            v9 = CBsString::FormatResource((CBsString *)v35, g_hInstance, 0x111u);
            if ( v9 < 0 )
              goto LABEL_87;
            v24 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, __int128 *, __int64))(**(_QWORD **)(a1 + 144) + 48LL))(
                    *(_QWORD *)(a1 + 144),
                    a3,
                    (unsigned int)a4[4],
                    &v46,
                    a1 + 40);
            break;
          case 4u:
            v9 = CBsString::FormatResource((CBsString *)v35, g_hInstance, 0x112u);
            if ( v9 < 0 )
              goto LABEL_87;
            v24 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int128 *, __int64))(**(_QWORD **)(a1 + 144) + 80LL))(
                    *(_QWORD *)(a1 + 144),
                    a3,
                    &v46,
                    a1 + 40);
            break;
          case 5u:
            v9 = CBsString::FormatResource((CBsString *)v35, g_hInstance, 0x113u);
            if ( v9 < 0 )
              goto LABEL_87;
            v21 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, __int128 *, __int64))(**(_QWORD **)(a1 + 144) + 32LL))(
                    *(_QWORD *)(a1 + 144),
                    a3,
                    &v46,
                    a1 + 40);
            if ( v21 < 0 )
              goto LABEL_77;
            v22 = *(void (__fastcall **)(__int64, __int128 *))(**(_QWORD **)(a1 + 144) + 168LL);
            v23 = *(_QWORD *)(a1 + 144);
            goto LABEL_76;
          default:
            goto LABEL_64;
        }
      }
      v21 = v24;
      if ( v24 >= 0 )
      {
        v23 = *(_QWORD *)(a1 + 144);
        v22 = *(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v23 + 168LL);
LABEL_76:
        v33 = *v10;
        v22(v23, &v33);
      }
LABEL_77:
      v26 = CBsString::FormatResource((CBsString *)v40, g_hInstance, 0xD2u, v35[0], v19);
      goto LABEL_78;
    }
    v20 = 1;
    goto LABEL_35;
  }
  v9 = -1996488698;
LABEL_87:
  LeaveCriticalSection(lpCriticalSection);
  v8 = v38;
LABEL_88:
  CoTaskMemFree(v8);
  v38 = 0;
  v29 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v34;
  if ( v34 )
  {
    v34 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v29)[2])(v29);
  }
  v30 = pProxy;
  if ( pProxy )
  {
    pProxy = 0;
    ((void (__fastcall *)(IUnknown *))v30->lpVtbl->Release)(v30);
  }
  CBsString::_Release((CBsString *)v39);
  CBsString::_Release((CBsString *)v35);
  CBsString::_Release((CBsString *)v40);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1801355c0  mov     [rsp-8+arg_8], rbx
0x1801355c5  push    rbp
0x1801355c6  push    rsi
0x1801355c7  push    rdi
0x1801355c8  push    r12
0x1801355ca  push    r13
0x1801355cc  push    r14
0x1801355ce  push    r15
0x1801355d0  lea     rbp, [rsp-40h]
0x1801355d5  sub     rsp, 140h
0x1801355dc  mov     rax, cs:__security_cookie
0x1801355e3  xor     rax, rsp
0x1801355e6  mov     [rbp+70h+var_40], rax
0x1801355ea  mov     r12, r9
0x1801355ed  mov     rsi, r8
0x1801355f0  mov     r15d, edx
0x1801355f3  mov     rdi, rcx
0x1801355f6  lea     rax, qword_1802E5D80
0x1801355fd  mov     [rbp+70h+var_D0], rax
0x180135601  mov     [rbp+70h+var_C8], 0
0x180135609  mov     [rsp+170h+var_108], rax
0x18013560e  mov     [rsp+170h+var_100], 0
0x180135617  mov     [rbp+70h+var_E0], rax
0x18013561b  mov     [rbp+70h+var_D8], 0
0x180135623  xor     ecx, ecx
0x180135625  mov     [rbp+70h+var_E8], rcx
0x180135629  mov     [rsp+170h+var_F8], ecx
0x18013562d  mov     [rbp+70h+pv], rcx
0x180135631  mov     [rsp+170h+pProxy], rcx
0x180135636  mov     [rsp+170h+var_110], rcx
0x18013563b  xorps   xmm0, xmm0
0x18013563e  movups  [rbp+70h+var_50], xmm0
0x180135642  mov     dword ptr [rbp+70h+var_A8+0Ch], ecx
0x180135645  mov     dword ptr [rbp+70h+var_98+0Ch], ecx
0x180135648  test    r8, r8
0x18013564b  jnz     short loc_18013565C
0x18013564d  cmp     edx, 5
0x180135650  jz      short loc_18013565C
0x180135652  mov     ebx, 80070057h
0x180135657  jmp     loc_180135CFA
0x18013565c  lea     rax, [rdi+0B8h]
0x180135663  mov     [rbp+70h+lpCriticalSection], rax
0x180135667  mov     rcx, rax; lpCriticalSection
0x18013566a  call    cs:__imp_EnterCriticalSection
0x180135671  nop     dword ptr [rax+rax+00h]
0x180135676  cmp     dword ptr [rdi+100h], 0
0x18013567d  jz      short loc_180135689
0x18013567f  mov     ebx, 89000006h
0x180135684  jmp     loc_180135CE6
0x180135689  cmp     dword ptr [r12+0Ch], 0
0x18013568f  jz      short loc_18013569A
0x180135691  movups  xmm0, xmmword ptr [rdi+38h]
0x180135695  movdqu  [rbp+70h+var_50], xmm0
0x18013569a  lea     r14, [rdi+28h]
0x18013569e  test    r14, r14
0x1801356a1  jz      short loc_1801356B7
0x1801356a3  mov     ecx, 10h
0x1801356a8  mov     rax, r14
0x1801356ab  mov     byte ptr [rax], 0
0x1801356ae  inc     rax
0x1801356b1  sub     rcx, 1
0x1801356b5  jnz     short loc_1801356AB
0x1801356b7  mov     qword ptr [rdi+0B0h], 0
0x1801356c2  mov     qword ptr [rdi+0E0h], 0
0x1801356cd  mov     dword ptr [rdi+98h], 0
0x1801356d7  mov     rcx, [rdi+58h]; hEvent
0x1801356db  call    cs:__imp_ResetEvent
0x1801356e2  nop     dword ptr [rax+rax+00h]
0x1801356e7  mov     qword ptr [rdi+7Ch], 0
0x1801356ef  mov     qword ptr [rdi+84h], 0
0x1801356fa  mov     eax, [r12]
0x1801356fe  mov     [rdi+0E8h], eax
0x180135704  mov     eax, [r12+4]
0x180135709  mov     [rdi+0ECh], eax
0x18013570f  mov     rbx, [rdi+90h]
0x180135716  mov     rax, [rbx]
0x180135719  mov     r13, [rax]
0x18013571c  mov     rcx, [rsp+170h+var_110]
0x180135721  test    rcx, rcx
0x180135724  jz      short loc_18013573C
0x180135726  mov     [rsp+170h+var_110], 0
0x18013572f  mov     rax, [rcx]
0x180135732  mov     rax, [rax+10h]
0x180135736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013573b  nop
0x18013573c  lea     r8, [rsp+170h+var_110]
0x180135741  lea     rdx, IID_IUnknown
0x180135748  mov     rcx, rbx
0x18013574b  mov     rax, r13
0x18013574e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135753  mov     ebx, eax
0x180135755  test    eax, eax
0x180135757  js      loc_180135CE6
0x18013575d  mov     rbx, [rsp+170h+var_110]
0x180135762  mov     rax, [rbx]
0x180135765  mov     r13, [rax]
0x180135768  mov     rdx, [rsp+170h+pProxy]
0x18013576d  test    rdx, rdx
0x180135770  jz      short loc_18013578B
0x180135772  mov     [rsp+170h+pProxy], 0
0x18013577b  mov     rcx, [rdx]
0x18013577e  mov     rax, [rcx+10h]
0x180135782  mov     rcx, rdx
0x180135785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013578a  nop
0x18013578b  lea     r8, [rsp+170h+pProxy]
0x180135790  lea     rdx, IID_IDefragOptions
0x180135797  mov     rcx, rbx
0x18013579a  mov     rax, r13
0x18013579d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801357a2  mov     ebx, eax
0x1801357a4  test    eax, eax
0x1801357a6  js      loc_180135CE6
0x1801357ac  mov     [rsp+170h+dwCapabilities], 40h ; '@'; dwCapabilities
0x1801357b4  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1801357b8  mov     [rsp+170h+pAuthInfo], r9; pAuthInfo
0x1801357bd  mov     [rsp+170h+dwImpLevel], 3; dwImpLevel
0x1801357c5  mov     [rsp+170h+dwAuthnLevel], 0; dwAuthnLevel
0x1801357cd  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1801357d0  mov     r8d, edx; dwAuthzSvc
0x1801357d3  mov     rcx, [rsp+170h+pProxy]; pProxy
0x1801357d8  call    cs:__imp_CoSetProxyBlanket
0x1801357df  nop     dword ptr [rax+rax+00h]
0x1801357e4  mov     ebx, eax
0x1801357e6  test    eax, eax
0x1801357e8  js      loc_180135CE6
0x1801357ee  test    rsi, rsi
0x1801357f1  jz      short loc_18013586F
0x1801357f3  lea     rcx, [rdi+0A0h]; this
0x1801357fa  mov     rdx, rsi; unsigned __int16 *
0x1801357fd  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180135802  mov     ebx, eax
0x180135804  test    eax, eax
0x180135806  js      loc_180135CE6
0x18013580c  mov     rax, [rdi]
0x18013580f  lea     r8, [rbp+70h+pv]
0x180135813  mov     rdx, rsi
0x180135816  mov     rcx, rdi
0x180135819  mov     rax, [rax+48h]
0x18013581d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135822  lea     rcx, [rbp+70h+var_E0]; this
0x180135826  test    eax, eax
0x180135828  js      short loc_18013585B
0x18013582a  mov     rdx, [rbp+70h+pv]; unsigned __int16 *
0x18013582e  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180135833  mov     ebx, eax
0x180135835  test    eax, eax
0x180135837  js      loc_180135CE6
0x18013583d  mov     rcx, [rbp+70h+pv]; pv
0x180135841  call    cs:__imp_CoTaskMemFree
0x180135848  nop     dword ptr [rax+rax+00h]
0x18013584d  mov     [rbp+70h+pv], 0
0x180135855  mov     r13, [rbp+70h+var_E0]
0x180135859  jmp     short loc_180135876
0x18013585b  mov     rdx, rsi; unsigned __int16 *
0x18013585e  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x180135863  mov     ebx, eax
0x180135865  test    eax, eax
0x180135867  js      loc_180135CE6
0x18013586d  jmp     short loc_180135855
0x18013586f  lea     r13, qword_1802E5D80
0x180135876  xor     eax, eax
0x180135878  mov     [rdi+0F0h], eax
0x18013587e  cmp     r15d, 1
0x180135882  jnz     short loc_1801358CC
0x180135884  cmp     [r12+8], eax
0x180135889  jnz     short loc_1801358D3
0x18013588b  mov     rcx, [rdi+90h]
0x180135892  mov     rax, [rcx]
0x180135895  lea     r9, [rbp+70h+var_E8]
0x180135899  lea     r8, [rsp+170h+var_F8]
0x18013589e  mov     rdx, rsi
0x1801358a1  mov     rax, [rax+80h]
0x1801358a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801358ad  mov     ebx, eax
0x1801358af  test    eax, eax
0x1801358b1  js      loc_180135CE6
0x1801358b7  cmp     [rsp+170h+var_F8], 1
0x1801358bc  jz      loc_180135A83
0x1801358c2  mov     ebx, 8900000Ah
0x1801358c7  jmp     loc_180135CE6
0x1801358cc  cmp     [r12+8], eax
0x1801358d1  jz      short loc_1801358DA
0x1801358d3  mov     edx, 1
0x1801358d8  jmp     short loc_1801358DC
0x1801358da  xor     edx, edx
0x1801358dc  mov     rcx, [rsp+170h+pProxy]
0x1801358e1  mov     rax, [rcx]
0x1801358e4  mov     rax, [rax+20h]
0x1801358e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801358ed  test    eax, eax
0x1801358ef  mov     ebx, eax
0x1801358f1  js      loc_180135CE6
0x1801358f7  cmp     r15d, 6
0x1801358fb  ja      loc_180135ADB
0x180135901  jz      loc_180135AA7
0x180135907  mov     eax, r15d
0x18013590a  sub     eax, 1
0x18013590d  jz      loc_18013588B
0x180135913  sub     eax, 1
0x180135916  jz      loc_180135A0B
0x18013591c  sub     eax, 1
0x18013591f  jz      loc_1801359D7
0x180135925  sub     eax, 1
0x180135928  jz      short loc_180135994
0x18013592a  cmp     eax, 1
0x18013592d  jnz     loc_180135AFE
0x180135933  mov     r8d, 113h; unsigned int
0x180135939  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180135940  lea     rcx, [rsp+170h+var_108]; this
0x180135945  call    ?FormatResource@CBsString@@QEAAJPEAUHINSTANCE__@@IZZ; CBsString::FormatResource(HINSTANCE__ *,uint,...)
0x18013594a  mov     ebx, eax
0x18013594c  test    eax, eax
0x18013594e  js      loc_180135CE6
0x180135954  mov     rcx, [rdi+90h]
0x18013595b  mov     rax, [rcx]
0x18013595e  mov     r9, r14
0x180135961  lea     r8, [rbp+70h+var_50]
0x180135965  mov     rdx, rsi
0x180135968  mov     rax, [rax+20h]
0x18013596c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135971  mov     esi, eax
0x180135973  test    eax, eax
0x180135975  js      loc_180135C7A
0x18013597b  mov     r8, [rdi+90h]
0x180135982  mov     rcx, [r8]
0x180135985  mov     rax, [rcx+0A8h]
0x18013598c  mov     rcx, r8
0x18013598f  jmp     loc_180135C66
0x180135994  mov     r8d, 112h; unsigned int
0x18013599a  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x1801359a1  lea     rcx, [rsp+170h+var_108]; this
0x1801359a6  call    ?FormatResource@CBsString@@QEAAJPEAUHINSTANCE__@@IZZ; CBsString::FormatResource(HINSTANCE__ *,uint,...)
0x1801359ab  mov     ebx, eax
0x1801359ad  test    eax, eax
0x1801359af  js      loc_180135CE6
0x1801359b5  mov     rcx, [rdi+90h]
0x1801359bc  mov     rax, [rcx]
0x1801359bf  mov     rax, [rax+50h]
0x1801359c3  mov     rdx, rsi
0x1801359c6  lea     r8, [rbp+70h+var_50]
0x1801359ca  mov     r9, r14
0x1801359cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801359d2  jmp     loc_180135C4F
0x1801359d7  mov     r8d, 111h; unsigned int
0x1801359dd  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x1801359e4  lea     rcx, [rsp+170h+var_108]; this
0x1801359e9  call    ?FormatResource@CBsString@@QEAAJPEAUHINSTANCE__@@IZZ; CBsString::FormatResource(HINSTANCE__ *,uint,...)
0x1801359ee  mov     ebx, eax
0x1801359f0  test    eax, eax
0x1801359f2  js      loc_180135CE6
0x1801359f8  mov     rcx, [rdi+90h]
0x1801359ff  mov     rax, [rcx]
0x180135a02  mov     rax, [rax+30h]
0x180135a06  jmp     loc_180135C39
0x180135a0b  mov     r8d, 110h; unsigned int
0x180135a11  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180135a18  lea     rcx, [rsp+170h+var_108]; this
0x180135a1d  call    ?FormatResource@CBsString@@QEAAJPEAUHINSTANCE__@@IZZ; CBsString::FormatResource(HINSTANCE__ *,uint,...)
0x180135a22  mov     ebx, eax
0x180135a24  test    eax, eax
0x180135a26  js      loc_180135CE6
0x180135a2c  mov     rcx, [rdi+90h]
0x180135a33  mov     rax, [rcx]
0x180135a36  mov     r9, r14
0x180135a39  lea     r8, [rbp+70h+var_50]
0x180135a3d  mov     rdx, rsi
0x180135a40  mov     rax, [rax+18h]
0x180135a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135a49  mov     esi, eax
0x180135a4b  test    eax, eax
0x180135a4d  js      short loc_180135A74
0x180135a4f  mov     rcx, [rdi+90h]
0x180135a56  movups  xmm0, xmmword ptr [r14]
0x180135a5a  movdqu  [rsp+170h+var_120], xmm0
0x180135a60  mov     rax, [rcx]
0x180135a63  lea     rdx, [rsp+170h+var_120]
0x180135a68  mov     rax, [rax+0A8h]
0x180135a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180135a74  mov     dword ptr [rdi+0F0h], 1
0x180135a7e  jmp     loc_180135C7A
0x180135a83  mov     rax, [rbp+70h+var_E8]
0x180135a87  test    rax, rax
0x180135a8a  jz      loc_1801358C2
0x180135a90  cmp     dword ptr [rax+8], 1
0x180135a94  jnz     loc_1801358C2
0x180135a9a  xor     esi, esi
0x180135a9c  movups  xmm0, xmmword ptr [rax+0Ch]
0x180135aa0  movdqu  xmmword ptr [r14], xmm0
0x180135aa5  jmp     short loc_180135B0D
0x180135aa7  mov     r8d, 12Eh; unsigned int
0x180135aad  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x180135ab4  lea     rcx, [rsp+170h+var_108]; this
0x180135ab9  call    ?FormatResource@CBsString@@QEAAJPEAUHINSTANCE__@@IZZ; CBsString::FormatResource(HINSTANCE__ *,uint,...)
0x180135abe  mov     ebx, eax
0x180135ac0  test    eax, eax
0x180135ac2  js      loc_180135CE6
0x180135ac8  mov     rcx, [rdi+90h]
0x180135acf  mov     rax, [rcx]
0x180135ad2  mov     rax, [rax+68h]
  ... truncated ...
```
