# CHNetConn::RefreshNetConnectionsUI(int)

- ea: `0x18001e954`
- end: `0x18001ee34`
- name: `?RefreshNetConnectionsUI@CHNetConn@@IEAAJH@Z`
- size: `1248`
- prototype: `__int64 __fastcall(CHNetConn *__hidden this, int)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001a820`
- `0x1800203b0`
- `0x180020930`
- `0x1800274d0`
- `0x1800275a0`
- `0x180027860`

## callees

- `0x18000a45c`
- `0x18000a484`
- `0x18001e954`
- `0x18002a6a0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ea37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ea37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e9c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e9c0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e9e6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e9e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ede1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ede1`

## pseudocode

```c
__int64 __fastcall CHNetConn::RefreshNetConnectionsUI(CHNetConn *this, int a2)
{
  struct IUnknown **v4; // r14
  HRESULT Instance; // ebx
  int v6; // eax
  PVOID *v7; // rcx
  int v8; // eax
  __int64 (__fastcall **v9)(CHNetConn *, LPVOID *); // rax
  int v10; // eax
  __int64 (__fastcall **v11)(CHNetConn *, GUID *, _QWORD *); // rax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  __int64 v18; // [rsp+30h] [rbp-30h] BYREF
  __int64 v19; // [rsp+38h] [rbp-28h] BYREF
  __int64 v20; // [rsp+40h] [rbp-20h] BYREF
  __int64 v21; // [rsp+48h] [rbp-18h] BYREF
  LPVOID pv[2]; // [rsp+50h] [rbp-10h] BYREF
  int v23; // [rsp+90h] [rbp+30h] BYREF
  __int64 v24; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v25; // [rsp+A8h] [rbp+48h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 334, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids);
  }
  v4 = (struct IUnknown **)((char *)this + 144);
  v24 = 0;
  if ( !*((_QWORD *)this + 18) )
  {
    Instance = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    if ( !*v4 )
    {
      Instance = CoCreateInstance(
                   &CLSID_ConnectionManager,
                   0,
                   0x8405u,
                   &GUID_faedcf5f_31fe_11d1_aad2_00805fc1270e,
                   (LPVOID *)this + 18);
      if ( Instance >= 0 )
      {
        SetProxyBlanket(*v4);
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          335,
          WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
          (unsigned int)Instance);
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    if ( Instance < 0 )
      goto LABEL_67;
  }
  v6 = (*(__int64 (__fastcall **)(CHNetConn *, __int64 *))(*(_QWORD *)this + 24LL))(this, &v24);
  Instance = v6;
  if ( v6 >= 0 )
  {
    v8 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))(*v4)->lpVtbl[2].QueryInterface)(*v4, v24);
    Instance = v8;
    if ( v8 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        337,
        WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
        (unsigned int)v8);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    goto LABEL_25;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      336,
      WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
      (unsigned int)v6);
LABEL_25:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    v9 = *(__int64 (__fastcall ***)(CHNetConn *, LPVOID *))this;
    pv[0] = 0;
    v10 = v9[7](this, pv);
    Instance = v10;
    if ( v10 >= 0 )
    {
      if ( *((_BYTE *)pv[0] + 4) == 1 )
      {
        v11 = *(__int64 (__fastcall ***)(CHNetConn *, GUID *, _QWORD *))this;
        v21 = 0;
        v12 = v11[8](this, &IID_IHNetBridge, &v21);
        Instance = v12;
        if ( v12 >= 0 )
        {
          v20 = 0;
          v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 24LL))(v21, &v20);
          Instance = v13;
          if ( v13 >= 0 )
          {
            v19 = 0;
            v23 = 0;
            while ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v20 + 24LL))(
                       v20,
                       1,
                       &v19,
                       &v23)
                 && v23 == 1 )
            {
              v18 = 0;
              v14 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v19)(v19, &IID_IHNetConnection, &v18);
              Instance = v14;
              if ( v14 >= 0 )
              {
                v25 = 0;
                v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 24LL))(v18, &v25);
                Instance = v15;
                if ( v15 >= 0 )
                {
                  v16 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))(*v4)->lpVtbl[2].QueryInterface)(*v4, v25);
                  Instance = v16;
                  if ( v16 < 0
                    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      343,
                      WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
                      (unsigned int)v16);
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    342,
                    WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
                    (unsigned int)v15);
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
              }
              else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  341,
                  WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
                  (unsigned int)v14);
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              340,
              WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
              (unsigned int)v13);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            339,
            WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
            (unsigned int)v12);
        }
      }
      CoTaskMemFree(pv[0]);
      goto LABEL_67;
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        338,
        WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids,
        (unsigned int)v10);
LABEL_67:
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 && *((_BYTE *)v7 + 25) >= 6u )
    WPP_SF_d(v7[2], 344, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids, (unsigned int)Instance);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18001e954  mov     [rsp-28h+arg_8], rbx
0x18001e959  push    rbp
0x18001e95a  push    rsi
0x18001e95b  push    rdi
0x18001e95c  push    r14
0x18001e95e  push    r15
0x18001e960  mov     rbp, rsp
0x18001e963  sub     rsp, 60h
0x18001e967  mov     r15d, edx
0x18001e96a  mov     rdi, rcx
0x18001e96d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e974  lea     rsi, WPP_GLOBAL_Control
0x18001e97b  cmp     rcx, rsi
0x18001e97e  jz      short loc_18001E9A1
0x18001e980  test    byte ptr [rcx+1Ch], 8
0x18001e984  jz      short loc_18001E9A1
0x18001e986  cmp     byte ptr [rcx+19h], 6
0x18001e98a  jb      short loc_18001E9A1
0x18001e98c  mov     rcx, [rcx+10h]
0x18001e990  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001e997  mov     edx, 14Eh
0x18001e99c  call    WPP_SF_
0x18001e9a1  lea     r14, [rdi+90h]
0x18001e9a8  mov     [rbp+arg_10], 0
0x18001e9b0  cmp     qword ptr [r14], 0
0x18001e9b4  jnz     loc_18001EA4C
0x18001e9ba  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001e9be  xor     ebx, ebx
0x18001e9c0  call    cs:__imp_EnterCriticalSection
0x18001e9c6  cmp     [r14], rbx
0x18001e9c9  jnz     short loc_18001EA33
0x18001e9cb  lea     r9, _GUID_faedcf5f_31fe_11d1_aad2_00805fc1270e; riid
0x18001e9d2  mov     [rsp+60h+ppv], r14; ppv
0x18001e9d7  xor     edx, edx; pUnkOuter
0x18001e9d9  lea     rcx, CLSID_ConnectionManager; rclsid
0x18001e9e0  mov     r8d, 8405h; dwClsContext
0x18001e9e6  call    cs:__imp_CoCreateInstance
0x18001e9ec  mov     ebx, eax
0x18001e9ee  test    eax, eax
0x18001e9f0  jns     short loc_18001EA2B
0x18001e9f2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e9f9  lea     rax, WPP_GLOBAL_Control
0x18001ea00  cmp     rcx, rax
0x18001ea03  jz      short loc_18001EA33
0x18001ea05  test    byte ptr [rcx+1Ch], 8
0x18001ea09  jz      short loc_18001EA33
0x18001ea0b  cmp     byte ptr [rcx+19h], 2
0x18001ea0f  jb      short loc_18001EA33
0x18001ea11  mov     rcx, [rcx+10h]
0x18001ea15  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001ea1c  mov     edx, 14Fh
0x18001ea21  mov     r9d, ebx
0x18001ea24  call    WPP_SF_d
0x18001ea29  jmp     short loc_18001EA33
0x18001ea2b  mov     rcx, [r14]; struct IUnknown *
0x18001ea2e  call    ?SetProxyBlanket@@YAXPEAUIUnknown@@@Z; SetProxyBlanket(IUnknown *)
0x18001ea33  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001ea37  call    cs:__imp_LeaveCriticalSection
0x18001ea3d  test    ebx, ebx
0x18001ea3f  js      loc_18001EDE7
0x18001ea45  lea     rsi, WPP_GLOBAL_Control
0x18001ea4c  mov     rax, [rdi]
0x18001ea4f  lea     rdx, [rbp+arg_10]
0x18001ea53  mov     rcx, rdi
0x18001ea56  mov     rax, [rax+18h]
0x18001ea5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea5f  mov     ebx, eax
0x18001ea61  test    eax, eax
0x18001ea63  jns     short loc_18001EA9F
0x18001ea65  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ea6c  cmp     rcx, rsi
0x18001ea6f  jz      loc_18001EAFF
0x18001ea75  test    byte ptr [rcx+1Ch], 8
0x18001ea79  jz      loc_18001EAFF
0x18001ea7f  cmp     byte ptr [rcx+19h], 2
0x18001ea83  jb      short loc_18001EAFF
0x18001ea85  mov     rcx, [rcx+10h]
0x18001ea89  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001ea90  mov     edx, 150h
0x18001ea95  mov     r9d, eax
0x18001ea98  call    WPP_SF_d
0x18001ea9d  jmp     short loc_18001EAF8
0x18001ea9f  mov     rcx, [r14]
0x18001eaa2  mov     rdx, [rbp+arg_10]
0x18001eaa6  mov     rax, [rcx]
0x18001eaa9  mov     rax, [rax+30h]
0x18001eaad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eab2  mov     ebx, eax
0x18001eab4  test    eax, eax
0x18001eab6  jns     short loc_18001EAE8
0x18001eab8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eabf  cmp     rcx, rsi
0x18001eac2  jz      short loc_18001EAE8
0x18001eac4  test    byte ptr [rcx+1Ch], 8
0x18001eac8  jz      short loc_18001EAE8
0x18001eaca  cmp     byte ptr [rcx+19h], 2
0x18001eace  jb      short loc_18001EAE8
0x18001ead0  mov     rcx, [rcx+10h]
0x18001ead4  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001eadb  mov     edx, 151h
0x18001eae0  mov     r9d, eax
0x18001eae3  call    WPP_SF_d
0x18001eae8  mov     rcx, [rbp+arg_10]
0x18001eaec  mov     rax, [rcx]
0x18001eaef  mov     rax, [rax+10h]
0x18001eaf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eaf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eaff  test    r15d, r15d
0x18001eb02  jz      loc_18001EDEE
0x18001eb08  mov     rax, [rdi]
0x18001eb0b  lea     rdx, [rbp+pv]
0x18001eb0f  mov     rcx, rdi
0x18001eb12  mov     [rbp+pv], 0
0x18001eb1a  mov     rax, [rax+38h]
0x18001eb1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb23  mov     ebx, eax
0x18001eb25  test    eax, eax
0x18001eb27  jns     short loc_18001EB6A
0x18001eb29  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb30  cmp     rcx, rsi
0x18001eb33  jz      loc_18001EDEE
0x18001eb39  test    byte ptr [rcx+1Ch], 8
0x18001eb3d  jz      loc_18001EDEE
0x18001eb43  cmp     byte ptr [rcx+19h], 2
0x18001eb47  jb      loc_18001EDEE
0x18001eb4d  mov     rcx, [rcx+10h]
0x18001eb51  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001eb58  mov     edx, 152h
0x18001eb5d  mov     r9d, eax
0x18001eb60  call    WPP_SF_d
0x18001eb65  jmp     loc_18001EDE7
0x18001eb6a  mov     rax, [rbp+pv]
0x18001eb6e  cmp     byte ptr [rax+4], 1
0x18001eb72  jnz     loc_18001EDDD
0x18001eb78  mov     rax, [rdi]
0x18001eb7b  lea     r8, [rbp+var_18]
0x18001eb7f  lea     rdx, IID_IHNetBridge
0x18001eb86  mov     [rbp+var_18], 0
0x18001eb8e  mov     rcx, rdi
0x18001eb91  mov     rax, [rax+40h]
0x18001eb95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb9a  mov     ebx, eax
0x18001eb9c  test    eax, eax
0x18001eb9e  jns     short loc_18001EBE1
0x18001eba0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eba7  cmp     rcx, rsi
0x18001ebaa  jz      loc_18001EDDD
0x18001ebb0  test    byte ptr [rcx+1Ch], 8
0x18001ebb4  jz      loc_18001EDDD
0x18001ebba  cmp     byte ptr [rcx+19h], 2
0x18001ebbe  jb      loc_18001EDDD
0x18001ebc4  mov     rcx, [rcx+10h]
0x18001ebc8  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001ebcf  mov     edx, 153h
0x18001ebd4  mov     r9d, eax
0x18001ebd7  call    WPP_SF_d
0x18001ebdc  jmp     loc_18001EDDD
0x18001ebe1  mov     rcx, [rbp+var_18]
0x18001ebe5  lea     rdx, [rbp+var_20]
0x18001ebe9  mov     [rbp+var_20], 0
0x18001ebf1  mov     rax, [rcx]
0x18001ebf4  mov     rax, [rax+18h]
0x18001ebf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebfd  mov     ebx, eax
0x18001ebff  test    eax, eax
0x18001ec01  jns     short loc_18001EC44
0x18001ec03  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec0a  cmp     rcx, rsi
0x18001ec0d  jz      loc_18001EDCD
0x18001ec13  test    byte ptr [rcx+1Ch], 8
0x18001ec17  jz      loc_18001EDCD
0x18001ec1d  cmp     byte ptr [rcx+19h], 2
0x18001ec21  jb      loc_18001EDCD
0x18001ec27  mov     rcx, [rcx+10h]
0x18001ec2b  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001ec32  mov     edx, 154h
0x18001ec37  mov     r9d, eax
0x18001ec3a  call    WPP_SF_d
0x18001ec3f  jmp     loc_18001EDCD
0x18001ec44  mov     [rbp+var_28], 0
0x18001ec4c  mov     [rbp+arg_0], 0
0x18001ec53  mov     rcx, [rbp+var_20]
0x18001ec57  lea     r9, [rbp+arg_0]
0x18001ec5b  lea     r8, [rbp+var_28]
0x18001ec5f  mov     edx, 1
0x18001ec64  mov     rax, [rcx]
0x18001ec67  mov     rax, [rax+18h]
0x18001ec6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec70  test    eax, eax
0x18001ec72  jnz     loc_18001EDBD
0x18001ec78  cmp     [rbp+arg_0], 1
0x18001ec7c  jnz     loc_18001EDBD
0x18001ec82  mov     rcx, [rbp+var_28]
0x18001ec86  lea     r8, [rbp+var_30]
0x18001ec8a  mov     [rbp+var_30], 0
0x18001ec92  lea     rdx, IID_IHNetConnection
0x18001ec99  mov     rax, [rcx]
0x18001ec9c  mov     rax, [rax]
0x18001ec9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eca4  mov     ebx, eax
0x18001eca6  test    eax, eax
0x18001eca8  jns     short loc_18001ECEB
0x18001ecaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ecb1  cmp     rcx, rsi
0x18001ecb4  jz      loc_18001EDA8
0x18001ecba  test    byte ptr [rcx+1Ch], 8
0x18001ecbe  jz      loc_18001EDA8
0x18001ecc4  cmp     byte ptr [rcx+19h], 2
0x18001ecc8  jb      loc_18001EDA8
0x18001ecce  mov     rcx, [rcx+10h]
0x18001ecd2  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001ecd9  mov     edx, 155h
0x18001ecde  mov     r9d, eax
0x18001ece1  call    WPP_SF_d
0x18001ece6  jmp     loc_18001EDA8
0x18001eceb  mov     rcx, [rbp+var_30]
0x18001ecef  lea     rdx, [rbp+arg_18]
0x18001ecf3  mov     [rbp+arg_18], 0
0x18001ecfb  mov     rax, [rcx]
0x18001ecfe  mov     rax, [rax+18h]
0x18001ed02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed07  mov     ebx, eax
0x18001ed09  test    eax, eax
0x18001ed0b  jns     short loc_18001ED3F
0x18001ed0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed14  cmp     rcx, rsi
0x18001ed17  jz      short loc_18001ED98
0x18001ed19  test    byte ptr [rcx+1Ch], 8
0x18001ed1d  jz      short loc_18001ED98
0x18001ed1f  cmp     byte ptr [rcx+19h], 2
0x18001ed23  jb      short loc_18001ED98
0x18001ed25  mov     rcx, [rcx+10h]
0x18001ed29  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001ed30  mov     edx, 156h
0x18001ed35  mov     r9d, eax
0x18001ed38  call    WPP_SF_d
0x18001ed3d  jmp     short loc_18001ED98
0x18001ed3f  mov     rcx, [r14]
0x18001ed42  mov     rdx, [rbp+arg_18]
0x18001ed46  mov     rax, [rcx]
0x18001ed49  mov     rax, [rax+30h]
0x18001ed4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed52  mov     ebx, eax
0x18001ed54  test    eax, eax
0x18001ed56  jns     short loc_18001ED88
0x18001ed58  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed5f  cmp     rcx, rsi
0x18001ed62  jz      short loc_18001ED88
0x18001ed64  test    byte ptr [rcx+1Ch], 8
0x18001ed68  jz      short loc_18001ED88
0x18001ed6a  cmp     byte ptr [rcx+19h], 2
0x18001ed6e  jb      short loc_18001ED88
0x18001ed70  mov     rcx, [rcx+10h]
0x18001ed74  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001ed7b  mov     edx, 157h
0x18001ed80  mov     r9d, eax
0x18001ed83  call    WPP_SF_d
0x18001ed88  mov     rcx, [rbp+arg_18]
0x18001ed8c  mov     rax, [rcx]
0x18001ed8f  mov     rax, [rax+10h]
0x18001ed93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed98  mov     rcx, [rbp+var_30]
0x18001ed9c  mov     rax, [rcx]
0x18001ed9f  mov     rax, [rax+10h]
0x18001eda3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eda8  mov     rcx, [rbp+var_28]
0x18001edac  mov     rax, [rcx]
0x18001edaf  mov     rax, [rax+10h]
0x18001edb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edb8  jmp     loc_18001EC53
0x18001edbd  mov     rcx, [rbp+var_20]
0x18001edc1  mov     rax, [rcx]
0x18001edc4  mov     rax, [rax+10h]
0x18001edc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edcd  mov     rcx, [rbp+var_18]
0x18001edd1  mov     rax, [rcx]
0x18001edd4  mov     rax, [rax+10h]
0x18001edd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eddd  mov     rcx, [rbp+pv]; pv
0x18001ede1  call    cs:__imp_CoTaskMemFree
0x18001ede7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001edee  lea     rax, WPP_GLOBAL_Control
0x18001edf5  cmp     rcx, rax
0x18001edf8  jz      short loc_18001EE1E
0x18001edfa  test    byte ptr [rcx+1Ch], 8
0x18001edfe  jz      short loc_18001EE1E
0x18001ee00  cmp     byte ptr [rcx+19h], 6
0x18001ee04  jb      short loc_18001EE1E
0x18001ee06  mov     rcx, [rcx+10h]
0x18001ee0a  lea     r8, WPP_ee0bdfb5a0b6313f59a385a748f2d742_Traceguids
0x18001ee11  mov     edx, 158h
0x18001ee16  mov     r9d, ebx
0x18001ee19  call    WPP_SF_d
0x18001ee1e  mov     eax, ebx
0x18001ee20  mov     rbx, [rsp+60h+arg_8]
0x18001ee28  add     rsp, 60h
0x18001ee2c  pop     r15
0x18001ee2e  pop     r14
0x18001ee30  pop     rdi
0x18001ee31  pop     rsi
  ... truncated ...
```
