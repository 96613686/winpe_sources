# CHNetConn::GetINetConnection(INetConnection * *)

- ea: `0x18001c070`
- end: `0x18001c43f`
- name: `?GetINetConnection@CHNetConn@@UEAAJPEAPEAUINetConnection@@@Z`
- size: `975`
- prototype: `__int64 __fastcall(CHNetConn *this, struct IUnknown **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18001be10`
- `0x18001c070`
- `0x18001cf24`
- `0x180028d74`
- `0x18002a6a0`
- `0x18002d200`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c3b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c3b4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c0f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c0f1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c199`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c199`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c371`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c37a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c371`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001c37a`

## pseudocode

```c
__int64 __fastcall CHNetConn::GetINetConnection(CHNetConn *this, struct IUnknown **a2)
{
  PVOID *v4; // rcx
  struct INetConnection *v5; // rcx
  int INetConnectionByGuid; // ebx
  HRESULT GuidInternal; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  int RasConnectionName; // eax
  int v11; // eax
  unsigned __int16 *v12; // r14
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  struct IUnknown *v15; // rcx
  struct IUnknown *ppv; // [rsp+30h] [rbp-50h] BYREF
  struct _GUID *v18; // [rsp+38h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 *v20; // [rsp+48h] [rbp-38h] BYREF
  _QWORD v21[2]; // [rsp+50h] [rbp-30h] BYREF
  struct _GUID v22; // [rsp+60h] [rbp-20h]

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v18 = 0;
  if ( a2 )
  {
    *a2 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v5 = (struct INetConnection *)*((_QWORD *)this + 11);
    if ( v5 )
    {
      *a2 = (struct IUnknown *)v5;
      INetConnectionByGuid = 0;
      ((void (__fastcall *)(struct INetConnection *))v5->lpVtbl->AddRef)(v5);
LABEL_51:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
LABEL_56:
      v4 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_57;
    }
    GuidInternal = CHNetConn::GetGuidInternal(this, &v18);
    INetConnectionByGuid = GuidInternal;
    if ( GuidInternal < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_51;
      }
      v9 = 44;
      goto LABEL_21;
    }
    if ( GuidInternal )
      goto LABEL_51;
    if ( *((_BYTE *)this + 96) )
    {
      INetConnectionByGuid = FindINetConnectionByGuid(v18, a2);
      goto LABEL_49;
    }
    ppv = 0;
    GuidInternal = CoCreateInstance(
                     &CLSID_DialupConnection,
                     0,
                     0x8005u,
                     &GUID_faedcf57_31fe_11d1_aad2_00805fc1270e,
                     (LPVOID *)&ppv);
    INetConnectionByGuid = GuidInternal;
    if ( GuidInternal < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_51;
      }
      v9 = 45;
LABEL_21:
      WPP_SF_d(v8[2], v9, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)GuidInternal);
      goto LABEL_51;
    }
    v20 = 0;
    pv = 0;
    SetProxyBlanket(ppv);
    RasConnectionName = CHNetConn::GetRasConnectionName(this, &v20);
    INetConnectionByGuid = RasConnectionName;
    if ( RasConnectionName < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          46,
          WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
          (unsigned int)RasConnectionName);
      }
      goto LABEL_48;
    }
    if ( RasConnectionName )
    {
LABEL_48:
      ((void (__fastcall *)(struct IUnknown *))ppv->lpVtbl->Release)(ppv);
LABEL_49:
      if ( INetConnectionByGuid >= 0 )
      {
        v15 = *a2;
        *((_QWORD *)this + 11) = *a2;
        ((void (__fastcall *)(struct IUnknown *))v15->lpVtbl->AddRef)(v15);
        INetConnectionByGuid = 0;
      }
      goto LABEL_51;
    }
    v11 = (*(__int64 (__fastcall **)(CHNetConn *, LPVOID *))(*(_QWORD *)this + 48LL))(this, &pv);
    INetConnectionByGuid = v11;
    if ( v11 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
        (unsigned int)v11);
    }
    v12 = v20;
    if ( INetConnectionByGuid )
    {
LABEL_47:
      CoTaskMemFree(v12);
      goto LABEL_48;
    }
    v21[0] = pv;
    v22 = 0;
    v21[1] = v20;
    v22 = *v18;
    INetConnectionByGuid = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD *))ppv->lpVtbl[1].AddRef)(ppv, v21);
    if ( INetConnectionByGuid >= 0 )
    {
      INetConnectionByGuid = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))ppv->lpVtbl->QueryInterface)(
                               ppv,
                               &GUID_c08956a1_1cd3_11d1_b1c5_00805fc1270e,
                               a2);
      if ( INetConnectionByGuid >= 0 )
      {
        SetProxyBlanket(*a2);
        goto LABEL_46;
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_46;
      }
      v14 = 49;
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_46;
      }
      v14 = 48;
    }
    WPP_SF_d(v13[2], v14, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)INetConnectionByGuid);
LABEL_46:
    CoTaskMemFree(pv);
    goto LABEL_47;
  }
  INetConnectionByGuid = -2147467261;
  if ( v4 == &WPP_GLOBAL_Control )
    return (unsigned int)INetConnectionByGuid;
  if ( (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 2u )
  {
    WPP_SF_d(v4[2], 43, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, 2147500035LL);
    goto LABEL_56;
  }
LABEL_57:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 6u )
    WPP_SF_d(v4[2], 50, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)INetConnectionByGuid);
  return (unsigned int)INetConnectionByGuid;
}

```

## disassembly

```asm
0x18001c070  mov     [rsp-28h+arg_10], rbx
0x18001c075  push    rbp
0x18001c076  push    rsi
0x18001c077  push    rdi
0x18001c078  push    r14
0x18001c07a  push    r15
0x18001c07c  mov     rbp, rsp
0x18001c07f  sub     rsp, 80h
0x18001c086  mov     rax, cs:__security_cookie
0x18001c08d  xor     rax, rsp
0x18001c090  mov     [rbp+var_10], rax
0x18001c094  mov     rsi, rdx
0x18001c097  mov     rdi, rcx
0x18001c09a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0a1  lea     r14, WPP_GLOBAL_Control
0x18001c0a8  cmp     rcx, r14
0x18001c0ab  jz      short loc_18001C0D5
0x18001c0ad  test    byte ptr [rcx+1Ch], 8
0x18001c0b1  jz      short loc_18001C0D5
0x18001c0b3  cmp     byte ptr [rcx+19h], 6
0x18001c0b7  jb      short loc_18001C0D5
0x18001c0b9  mov     rcx, [rcx+10h]
0x18001c0bd  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001c0c4  mov     edx, 2Ah ; '*'
0x18001c0c9  call    WPP_SF_
0x18001c0ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0d5  mov     [rbp+var_48], 0
0x18001c0dd  test    rsi, rsi
0x18001c0e0  jz      loc_18001C3BC
0x18001c0e6  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001c0ea  mov     qword ptr [rsi], 0
0x18001c0f1  call    cs:__imp_EnterCriticalSection
0x18001c0f7  mov     rcx, [rdi+58h]
0x18001c0fb  test    rcx, rcx
0x18001c0fe  jz      short loc_18001C116
0x18001c100  mov     [rsi], rcx
0x18001c103  xor     ebx, ebx
0x18001c105  mov     rax, [rcx]
0x18001c108  mov     rax, [rax+8]
0x18001c10c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c111  jmp     loc_18001C3B0
0x18001c116  lea     rdx, [rbp+var_48]; struct _GUID **
0x18001c11a  mov     rcx, rdi; this
0x18001c11d  call    ?GetGuidInternal@CHNetConn@@IEAAJPEAPEAU_GUID@@@Z; CHNetConn::GetGuidInternal(_GUID * *)
0x18001c122  mov     ebx, eax
0x18001c124  test    eax, eax
0x18001c126  jns     short loc_18001C153
0x18001c128  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c12f  cmp     rcx, r14
0x18001c132  jz      loc_18001C3B0
0x18001c138  test    byte ptr [rcx+1Ch], 8
0x18001c13c  jz      loc_18001C3B0
0x18001c142  cmp     byte ptr [rcx+19h], 2
0x18001c146  jb      loc_18001C3B0
0x18001c14c  mov     edx, 2Ch ; ','
0x18001c151  jmp     short loc_18001C1CE
0x18001c153  jnz     loc_18001C3B0
0x18001c159  cmp     byte ptr [rdi+60h], 0
0x18001c15d  jz      short loc_18001C172
0x18001c15f  mov     rcx, [rbp+var_48]; struct _GUID *
0x18001c163  mov     rdx, rsi; struct INetConnection **
0x18001c166  call    ?FindINetConnectionByGuid@@YAJPEAU_GUID@@PEAPEAUINetConnection@@@Z; FindINetConnectionByGuid(_GUID *,INetConnection * *)
0x18001c16b  mov     ebx, eax
0x18001c16d  jmp     loc_18001C397
0x18001c172  lea     rax, [rbp+var_50]
0x18001c176  mov     [rbp+var_50], 0
0x18001c17e  lea     r9, _GUID_faedcf57_31fe_11d1_aad2_00805fc1270e; riid
0x18001c185  mov     [rsp+80h+ppv], rax; ppv
0x18001c18a  xor     edx, edx; pUnkOuter
0x18001c18c  lea     rcx, CLSID_DialupConnection; rclsid
0x18001c193  mov     r8d, 8005h; dwClsContext
0x18001c199  call    cs:__imp_CoCreateInstance
0x18001c19f  mov     ebx, eax
0x18001c1a1  test    eax, eax
0x18001c1a3  jns     short loc_18001C1E6
0x18001c1a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c1ac  cmp     rcx, r14
0x18001c1af  jz      loc_18001C3B0
0x18001c1b5  test    byte ptr [rcx+1Ch], 8
0x18001c1b9  jz      loc_18001C3B0
0x18001c1bf  cmp     byte ptr [rcx+19h], 2
0x18001c1c3  jb      loc_18001C3B0
0x18001c1c9  mov     edx, 2Dh ; '-'
0x18001c1ce  mov     rcx, [rcx+10h]
0x18001c1d2  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001c1d9  mov     r9d, eax
0x18001c1dc  call    WPP_SF_d
0x18001c1e1  jmp     loc_18001C3B0
0x18001c1e6  mov     rcx, [rbp+var_50]; struct IUnknown *
0x18001c1ea  mov     [rbp+var_38], 0
0x18001c1f2  mov     [rbp+pv], 0
0x18001c1fa  call    ?SetProxyBlanket@@YAXPEAUIUnknown@@@Z; SetProxyBlanket(IUnknown *)
0x18001c1ff  lea     rdx, [rbp+var_38]; unsigned __int16 **
0x18001c203  mov     rcx, rdi; this
0x18001c206  call    ?GetRasConnectionName@CHNetConn@@IEAAJPEAPEAG@Z; CHNetConn::GetRasConnectionName(ushort * *)
0x18001c20b  mov     ebx, eax
0x18001c20d  test    eax, eax
0x18001c20f  jns     short loc_18001C252
0x18001c211  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c218  cmp     rcx, r14
0x18001c21b  jz      loc_18001C387
0x18001c221  test    byte ptr [rcx+1Ch], 8
0x18001c225  jz      loc_18001C387
0x18001c22b  cmp     byte ptr [rcx+19h], 2
0x18001c22f  jb      loc_18001C387
0x18001c235  mov     rcx, [rcx+10h]
0x18001c239  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001c240  mov     edx, 2Eh ; '.'
0x18001c245  mov     r9d, eax
0x18001c248  call    WPP_SF_d
0x18001c24d  jmp     loc_18001C387
0x18001c252  jnz     loc_18001C387
0x18001c258  mov     rax, [rdi]
0x18001c25b  lea     rdx, [rbp+pv]
0x18001c25f  mov     rcx, rdi
0x18001c262  mov     rax, [rax+30h]
0x18001c266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c26b  mov     ebx, eax
0x18001c26d  test    eax, eax
0x18001c26f  jns     short loc_18001C2A1
0x18001c271  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c278  cmp     rcx, r14
0x18001c27b  jz      short loc_18001C2A1
0x18001c27d  test    byte ptr [rcx+1Ch], 8
0x18001c281  jz      short loc_18001C2A1
0x18001c283  cmp     byte ptr [rcx+19h], 2
0x18001c287  jb      short loc_18001C2A1
0x18001c289  mov     rcx, [rcx+10h]
0x18001c28d  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001c294  mov     edx, 2Fh ; '/'
0x18001c299  mov     r9d, eax
0x18001c29c  call    WPP_SF_d
0x18001c2a1  mov     r14, [rbp+var_38]
0x18001c2a5  test    ebx, ebx
0x18001c2a7  jnz     loc_18001C377
0x18001c2ad  mov     rax, [rbp+pv]
0x18001c2b1  lea     rdx, [rbp+var_30]
0x18001c2b5  mov     rcx, [rbp+var_50]
0x18001c2b9  xorps   xmm0, xmm0
0x18001c2bc  mov     [rbp+var_30], rax
0x18001c2c0  mov     rax, [rbp+var_48]
0x18001c2c4  movdqu  [rbp+var_20], xmm0
0x18001c2c9  mov     [rbp+var_28], r14
0x18001c2cd  movups  xmm0, xmmword ptr [rax]
0x18001c2d0  movdqu  [rbp+var_20], xmm0
0x18001c2d5  mov     rax, [rcx]
0x18001c2d8  mov     rax, [rax+20h]
0x18001c2dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2e1  mov     ebx, eax
0x18001c2e3  test    eax, eax
0x18001c2e5  jns     short loc_18001C30D
0x18001c2e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2ee  lea     rax, WPP_GLOBAL_Control
0x18001c2f5  cmp     rcx, rax
0x18001c2f8  jz      short loc_18001C36D
0x18001c2fa  test    byte ptr [rcx+1Ch], 8
0x18001c2fe  jz      short loc_18001C36D
0x18001c300  cmp     byte ptr [rcx+19h], 2
0x18001c304  jb      short loc_18001C36D
0x18001c306  mov     edx, 30h ; '0'
0x18001c30b  jmp     short loc_18001C350
0x18001c30d  mov     rcx, [rbp+var_50]
0x18001c311  lea     rdx, _GUID_c08956a1_1cd3_11d1_b1c5_00805fc1270e
0x18001c318  mov     r8, rsi
0x18001c31b  mov     rax, [rcx]
0x18001c31e  mov     rax, [rax]
0x18001c321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c326  mov     ebx, eax
0x18001c328  test    eax, eax
0x18001c32a  jns     short loc_18001C365
0x18001c32c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c333  lea     rax, WPP_GLOBAL_Control
0x18001c33a  cmp     rcx, rax
0x18001c33d  jz      short loc_18001C36D
0x18001c33f  test    byte ptr [rcx+1Ch], 8
0x18001c343  jz      short loc_18001C36D
0x18001c345  cmp     byte ptr [rcx+19h], 2
0x18001c349  jb      short loc_18001C36D
0x18001c34b  mov     edx, 31h ; '1'
0x18001c350  mov     rcx, [rcx+10h]
0x18001c354  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001c35b  mov     r9d, ebx
0x18001c35e  call    WPP_SF_d
0x18001c363  jmp     short loc_18001C36D
0x18001c365  mov     rcx, [rsi]; struct IUnknown *
0x18001c368  call    ?SetProxyBlanket@@YAXPEAUIUnknown@@@Z; SetProxyBlanket(IUnknown *)
0x18001c36d  mov     rcx, [rbp+pv]; pv
0x18001c371  call    cs:__imp_CoTaskMemFree
0x18001c377  mov     rcx, r14; pv
0x18001c37a  call    cs:__imp_CoTaskMemFree
0x18001c380  lea     r14, WPP_GLOBAL_Control
0x18001c387  mov     rcx, [rbp+var_50]
0x18001c38b  mov     rax, [rcx]
0x18001c38e  mov     rax, [rax+10h]
0x18001c392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c397  test    ebx, ebx
0x18001c399  js      short loc_18001C3B0
0x18001c39b  mov     rcx, [rsi]
0x18001c39e  mov     [rdi+58h], rcx
0x18001c3a2  mov     rax, [rcx]
0x18001c3a5  mov     rax, [rax+8]
0x18001c3a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3ae  xor     ebx, ebx
0x18001c3b0  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001c3b4  call    cs:__imp_LeaveCriticalSection
0x18001c3ba  jmp     short loc_18001C3EA
0x18001c3bc  mov     ebx, 80004003h
0x18001c3c1  cmp     rcx, r14
0x18001c3c4  jz      short loc_18001C41A
0x18001c3c6  test    byte ptr [rcx+1Ch], 8
0x18001c3ca  jz      short loc_18001C3F1
0x18001c3cc  cmp     byte ptr [rcx+19h], 2
0x18001c3d0  jb      short loc_18001C3F1
0x18001c3d2  mov     rcx, [rcx+10h]
0x18001c3d6  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001c3dd  mov     edx, 2Bh ; '+'
0x18001c3e2  mov     r9d, ebx
0x18001c3e5  call    WPP_SF_d
0x18001c3ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c3f1  cmp     rcx, r14
0x18001c3f4  jz      short loc_18001C41A
0x18001c3f6  test    byte ptr [rcx+1Ch], 8
0x18001c3fa  jz      short loc_18001C41A
0x18001c3fc  cmp     byte ptr [rcx+19h], 6
0x18001c400  jb      short loc_18001C41A
0x18001c402  mov     rcx, [rcx+10h]
0x18001c406  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001c40d  mov     edx, 32h ; '2'
0x18001c412  mov     r9d, ebx
0x18001c415  call    WPP_SF_d
0x18001c41a  mov     eax, ebx
0x18001c41c  mov     rcx, [rbp+var_10]
0x18001c420  xor     rcx, rsp; StackCookie
0x18001c423  call    __security_check_cookie
0x18001c428  mov     rbx, [rsp+80h+arg_10]
0x18001c430  add     rsp, 80h
0x18001c437  pop     r15
0x18001c439  pop     r14
0x18001c43b  pop     rdi
0x18001c43c  pop     rsi
0x18001c43d  pop     rbp
0x18001c43e  retn
```
