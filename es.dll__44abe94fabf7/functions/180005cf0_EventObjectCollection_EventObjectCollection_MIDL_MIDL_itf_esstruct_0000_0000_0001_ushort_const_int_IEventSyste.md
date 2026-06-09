# EventObjectCollection::EventObjectCollection(__MIDL___MIDL_itf_esstruct_0000_0000_0001,ushort const *,int *,IEventSystemTier2 *,bool,bool,int,int,long &)

- ea: `0x180005cf0`
- end: `0x18000610f`
- name: `??0EventObjectCollection@@AEAA@W4__MIDL___MIDL_itf_esstruct_0000_0000_0001@@PEBGPEAHPEAUIEventSystemTier2@@_N4HHAEAJ@Z`
- size: `1055`
- prototype: `__int64 __fastcall(__int64, int, _WORD *, __int64, struct IEventSystemTier2 *, int, unsigned __int8, int, int, int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180003df0`
- `0x180021e40`
- `0x180022e50`

## callees

- `0x180003d54`
- `0x180005cf0`
- `0x180006118`
- `0x180006220`
- `0x180043496`
- `0x1800434ba`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005d8e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180005d8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005ef4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005ef4`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180005e42`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180005f9a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180005e42`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180005f9a`

## string_xrefs

- `0x18000603d`: `com\complus\src\events\tier1\enum.cpp`
- `0x1800060d5`: `com\complus\src\events\tier1\enum.cpp`
- `0x1800060f7`: `com\complus\src\events\Shared\StringFuncs.h`

## pseudocode

```c
__int64 __fastcall EventObjectCollection::EventObjectCollection(
        __int64 a1,
        int a2,
        _WORD *a3,
        __int64 a4,
        struct IEventSystemTier2 *a5,
        int a6,
        unsigned __int8 a7,
        int a8,
        int a9,
        int *a10)
{
  __int64 v12; // r13
  __int64 v13; // rsi
  int v14; // eax
  HRESULT *v15; // rdi
  HRESULT v16; // eax
  int v17; // eax
  bool v18; // sf
  _QWORD *v19; // r14
  struct IEventSystemTier2 **v20; // r15
  __int64 v21; // rbx
  size_t v22; // rbx
  void *v23; // rsi
  HRESULT v25; // eax
  __int64 v26; // rax
  int v27; // eax
  unsigned __int16 *v28; // rdx
  __int64 v29; // [rsp+0h] [rbp-A8h] BYREF
  IUnknown *v30; // [rsp+40h] [rbp-68h] BYREF
  IUnknown *pProxy; // [rsp+48h] [rbp-60h] BYREF
  unsigned __int16 *v32; // [rsp+50h] [rbp-58h] BYREF
  struct IDispatch *v33; // [rsp+58h] [rbp-50h] BYREF
  _BYTE *v34; // [rsp+60h] [rbp-48h]
  _QWORD *v35; // [rsp+68h] [rbp-40h]
  struct IEventSystemTier2 **v36; // [rsp+70h] [rbp-38h]
  __int64 *v37; // [rsp+78h] [rbp-30h]

  v37 = &v29;
  v12 = a2;
  v13 = a1;
  *(_QWORD *)a1 = &EventObjectCollection::`vftable'{for `IEventObjectCollection'};
  *(_QWORD *)(a1 + 8) = &EventObjectCollection::`vftable'{for `ICollectionNotify'};
  *(_DWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 20) = a2;
  *(_QWORD *)(a1 + 24) = 0;
  v34 = (_BYTE *)(a1 + 32);
  *(_BYTE *)(a1 + 32) = a6;
  v35 = (_QWORD *)(a1 + 40);
  *(_QWORD *)(a1 + 40) = 0;
  v36 = (struct IEventSystemTier2 **)(a1 + 48);
  *(_QWORD *)(a1 + 48) = 0;
  Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::Map<unsigned short *,IDispatch *,HashWSTR,CNonFailFastingAllocator>((_QWORD *)(a1 + 56));
  *(_DWORD *)(v13 + 96) = 0;
  *(_DWORD *)(v13 + 144) = 0;
  *(_DWORD *)(v13 + 144) = InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v13 + 104), 0x1F4u);
  *(_DWORD *)(v13 + 152) = a8;
  *(_DWORD *)(v13 + 156) = a9;
  if ( *(_DWORD *)(v13 + 144) )
  {
    _InterlockedIncrement(&g_tier1ActiveObjects);
    if ( !a5 )
      InternalError(L"com\\complus\\src\\events\\tier1\\enum.cpp", 0x16Au, 0x80001203, 0x10u);
    pProxy = 0;
    v14 = (*(__int64 (__fastcall **)(struct IEventSystemTier2 *, _QWORD, _WORD *, _QWORD, __int64, IUnknown **))(*(_QWORD *)a5 + 48LL))(
            a5,
            (unsigned int)v12,
            a3,
            a7,
            a4,
            &pProxy);
    v15 = a10;
    *a10 = v14;
    if ( v14 >= 0 )
    {
      v16 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0);
      *v15 = v16;
      if ( (int)(v16 + 0x80000000) < 0 || v16 == -2147467262 )
      {
        while ( 1 )
        {
          v30 = 0;
          a6 = 0;
          v17 = ((__int64 (__fastcall *)(IUnknown *, __int64, IUnknown **, int *))pProxy->lpVtbl[1].QueryInterface)(
                  pProxy,
                  1,
                  &v30,
                  &a6);
          *v15 = v17;
          v18 = v17 < 0;
          if ( v17 )
            break;
          if ( !a6 )
          {
            v18 = 0;
            break;
          }
          v25 = CoSetProxyBlanket(v30, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 3u, 0, 0);
          *v15 = v25;
          if ( ((v25 + 0x80000000) & 0x80000000) != 0 || v25 == -2147467262 )
          {
            v33 = 0;
            v32 = 0;
            v26 = 32 * v12;
            if ( *(_DWORD *)(v13 + 156) )
              v27 = (*(__int64 (__fastcall **)(struct IEventSystemTier2 *, IUnknown *, unsigned __int16 **, _QWORD, struct IDispatch **))((char *)&off_1800635C0 + v26 + 8))(
                      a5,
                      v30,
                      &v32,
                      *(unsigned int *)(v13 + 152),
                      &v33);
            else
              v27 = (*(__int64 (__fastcall **)(struct IEventSystemTier2 *, struct IUnknown *, const unsigned __int16 **, struct IDispatch **))((char *)&off_1800635C0 + v26))(
                      a5,
                      v30,
                      (const unsigned __int16 **)&v32,
                      &v33);
            *v15 = v27;
            if ( v27 < 0 )
            {
              if ( v33 )
                ((void (__fastcall *)(struct IDispatch *))v33->lpVtbl->Release)(v33);
              *v15 = 0;
            }
            else
            {
              v28 = v32;
              if ( !v32 )
              {
                InternalError(L"com\\complus\\src\\events\\tier1\\enum.cpp", 0x1B3u, 0x80001203, 0x10u);
                v28 = v32;
              }
              *v15 = EventObjectCollection::AddItemToMap((EventObjectCollection *)v13, v28, v33);
            }
          }
          else
          {
            *v15 = 0;
          }
          if ( v30 )
            ((void (__fastcall *)(IUnknown *))v30->lpVtbl->Release)(v30);
        }
        if ( !v18 )
          *v15 = 0;
        local_unwind_0(v37, &loc_180005EB3);
        if ( *v34 )
        {
          v19 = v35;
          v20 = v36;
          if ( a3 )
          {
            v21 = -1;
            do
              ++v21;
            while ( a3[v21] );
          }
          else
          {
            LODWORD(v21) = 0;
          }
          v22 = 2LL * ((int)v21 + 1);
          v23 = CoTaskMemAlloc((unsigned int)v22);
          if ( !v23 )
            InternalError(L"com\\complus\\src\\events\\Shared\\StringFuncs.h", 0x13u, 0xC0001204, 0x10u);
          memcpy_0(v23, a3, v22);
          *v19 = v23;
          *v20 = a5;
          (*(void (__fastcall **)(struct IEventSystemTier2 *))(*(_QWORD *)a5 + 8LL))(a5);
        }
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
        return a1;
      }
      else
      {
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      }
    }
  }
  else
  {
    *a10 = -2147024882;
  }
  return v13;
}

```

## disassembly

```asm
0x180005cf0  mov     [rsp+arg_8], rbx
0x180005cf5  mov     [rsp+arg_18], rsi
0x180005cfa  mov     [rsp+Src], r8
0x180005cff  mov     [rsp+arg_0], rcx
0x180005d04  push    rdi
0x180005d05  push    r12
0x180005d07  push    r13
0x180005d09  push    r14
0x180005d0b  push    r15
0x180005d0d  sub     rsp, 80h
0x180005d14  mov     [rsp+0A8h+var_30], rsp
0x180005d19  mov     r15, r9
0x180005d1c  mov     r14, r8
0x180005d1f  movsxd  r13, edx
0x180005d22  mov     rsi, rcx
0x180005d25  lea     rax, ??_7EventObjectCollection@@6BIEventObjectCollection@@@; const EventObjectCollection::`vftable'{for `IEventObjectCollection'}
0x180005d2c  mov     [rcx], rax
0x180005d2f  lea     rax, ??_7EventObjectCollection@@6BICollectionNotify@@@; const EventObjectCollection::`vftable'{for `ICollectionNotify'}
0x180005d36  mov     [rcx+8], rax
0x180005d3a  xor     ebx, ebx
0x180005d3c  mov     [rcx+10h], ebx
0x180005d3f  mov     [rcx+14h], r13d
0x180005d43  mov     [rcx+18h], rbx
0x180005d47  lea     r9, [rcx+20h]
0x180005d4b  mov     [rsp+0A8h+var_48], r9
0x180005d50  movzx   eax, byte ptr [rsp+0A8h+arg_28]
0x180005d58  mov     [r9], al
0x180005d5b  lea     rax, [rcx+28h]
0x180005d5f  mov     [rsp+0A8h+var_40], rax
0x180005d64  mov     [rax], rbx
0x180005d67  lea     rax, [rcx+30h]
0x180005d6b  mov     [rsp+0A8h+var_38], rax
0x180005d70  mov     [rax], rbx
0x180005d73  add     rcx, 38h ; '8'
0x180005d77  call    ??0?$Map@PEAGPEAUIDispatch@@VHashWSTR@@VCNonFailFastingAllocator@@@@QEAA@I@Z; Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>::Map<ushort *,IDispatch *,HashWSTR,CNonFailFastingAllocator>(uint)
0x180005d7c  mov     [rsi+60h], ebx
0x180005d7f  mov     [rsi+90h], ebx
0x180005d85  mov     edx, 1F4h; dwSpinCount
0x180005d8a  lea     rcx, [rsi+68h]; lpCriticalSection
0x180005d8e  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180005d94  mov     [rsi+90h], eax
0x180005d9a  mov     eax, [rsp+0A8h+arg_38]
0x180005da1  mov     [rsi+98h], eax
0x180005da7  mov     eax, [rsp+0A8h+arg_40]
0x180005dae  mov     [rsi+9Ch], eax
0x180005db4  cmp     [rsi+90h], ebx
0x180005dba  jz      loc_180006090
0x180005dc0  lock inc cs:?g_tier1ActiveObjects@@3JA; long g_tier1ActiveObjects
0x180005dc7  mov     r12, [rsp+0A8h+arg_20]
0x180005dcf  test    r12, r12
0x180005dd2  jz      loc_1800060C4
0x180005dd8  mov     [rsp+0A8h+pProxy], rbx
0x180005ddd  mov     rax, [r12]
0x180005de1  movzx   r9d, [rsp+0A8h+arg_30]
0x180005dea  lea     rcx, [rsp+0A8h+pProxy]
0x180005def  mov     qword ptr [rsp+0A8h+dwImpLevel], rcx
0x180005df4  mov     qword ptr [rsp+0A8h+dwAuthnLevel], r15
0x180005df9  mov     r8, r14
0x180005dfc  mov     edx, r13d
0x180005dff  mov     rcx, r12
0x180005e02  mov     rax, [rax+30h]
0x180005e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e0b  mov     rdi, [rsp+0A8h+arg_48]
0x180005e13  mov     [rdi], eax
0x180005e15  test    eax, eax
0x180005e17  js      loc_180005F47
0x180005e1d  mov     [rsp+0A8h+dwCapabilities], ebx; dwCapabilities
0x180005e21  mov     [rsp+0A8h+pAuthInfo], rbx; pAuthInfo
0x180005e26  mov     [rsp+0A8h+dwImpLevel], 3; dwImpLevel
0x180005e2e  mov     [rsp+0A8h+dwAuthnLevel], ebx; dwAuthnLevel
0x180005e32  xor     r9d, r9d; pServerPrincName
0x180005e35  mov     edx, 0FFFFFFFFh; dwAuthnSvc
0x180005e3a  mov     r8d, edx; dwAuthzSvc
0x180005e3d  mov     rcx, [rsp+0A8h+pProxy]; pProxy
0x180005e42  call    cs:__imp_CoSetProxyBlanket
0x180005e48  mov     [rdi], eax
0x180005e4a  mov     r14d, 80000000h
0x180005e50  lea     ecx, [rax+r14]
0x180005e54  test    r14d, ecx
0x180005e57  jz      loc_1800060A3
0x180005e5d  lea     r15, off_1800635C0
0x180005e64  mov     [rsp+0A8h+var_68], rbx
0x180005e69  mov     [rsp+0A8h+arg_28], ebx
0x180005e70  mov     rcx, [rsp+0A8h+pProxy]
0x180005e75  mov     rax, [rcx]
0x180005e78  lea     r9, [rsp+0A8h+arg_28]
0x180005e80  lea     r8, [rsp+0A8h+var_68]
0x180005e85  mov     edx, 1
0x180005e8a  mov     rax, [rax+18h]
0x180005e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e93  mov     [rdi], eax
0x180005e95  test    eax, eax
0x180005e97  jz      loc_180005F67
0x180005e9d  js      short loc_180005EA1
0x180005e9f  mov     [rdi], ebx
0x180005ea1  lea     rdx, loc_180005EB3
0x180005ea8  mov     rcx, [rsp+0A8h+var_30]
0x180005ead  call    _local_unwind_0
0x180005eb2  nop
0x180005eb3  mov     rax, [rsp+0A8h+var_48]
0x180005eb8  cmp     byte ptr [rax], 0
0x180005ebb  jz      short loc_180005F2E
0x180005ebd  mov     r14, [rsp+0A8h+var_40]
0x180005ec2  mov     r15, [rsp+0A8h+var_38]
0x180005ec7  mov     rdi, [rsp+0A8h+Src]
0x180005ecf  test    rdi, rdi
0x180005ed2  jz      loc_180006108
0x180005ed8  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180005edf  nop
0x180005ee0  inc     rbx
0x180005ee3  cmp     word ptr [rdi+rbx*2], 0
0x180005ee8  jnz     short loc_180005EE0
0x180005eea  inc     ebx
0x180005eec  movsxd  rbx, ebx
0x180005eef  add     rbx, rbx
0x180005ef2  mov     ecx, ebx; cb
0x180005ef4  call    cs:__imp_CoTaskMemAlloc
0x180005efa  mov     rsi, rax
0x180005efd  test    rax, rax
0x180005f00  jz      loc_1800060E6
0x180005f06  mov     r8, rbx; Size
0x180005f09  mov     rdx, rdi; Src
0x180005f0c  mov     rcx, rsi; void *
0x180005f0f  call    memcpy_0
0x180005f14  mov     [r14], rsi
0x180005f17  mov     rcx, [rsp+0A8h+arg_20]
0x180005f1f  mov     [r15], rcx
0x180005f22  mov     rax, [rcx]
0x180005f25  mov     rax, [rax+8]
0x180005f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f2e  mov     rcx, [rsp+0A8h+pProxy]
0x180005f33  mov     rax, [rcx]
0x180005f36  mov     rax, [rax+10h]
0x180005f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f3f  mov     rsi, [rsp+0A8h+arg_0]
0x180005f47  mov     rax, rsi
0x180005f4a  lea     r11, [rsp+0A8h+var_28]
0x180005f52  mov     rbx, [r11+38h]
0x180005f56  mov     rsi, [r11+48h]
0x180005f5a  mov     rsp, r11
0x180005f5d  pop     r15
0x180005f5f  pop     r14
0x180005f61  pop     r13
0x180005f63  pop     r12
0x180005f65  pop     rdi
0x180005f66  retn
0x180005f67  cmp     [rsp+0A8h+arg_28], 0
0x180005f6f  jz      loc_18000606A
0x180005f75  mov     [rsp+0A8h+dwCapabilities], ebx; dwCapabilities
0x180005f79  mov     [rsp+0A8h+pAuthInfo], rbx; pAuthInfo
0x180005f7e  mov     [rsp+0A8h+dwImpLevel], 3; dwImpLevel
0x180005f86  mov     [rsp+0A8h+dwAuthnLevel], ebx; dwAuthnLevel
0x180005f8a  xor     r9d, r9d; pServerPrincName
0x180005f8d  mov     edx, 0FFFFFFFFh; dwAuthnSvc
0x180005f92  mov     r8d, edx; dwAuthzSvc
0x180005f95  mov     rcx, [rsp+0A8h+var_68]; pProxy
0x180005f9a  call    cs:__imp_CoSetProxyBlanket
0x180005fa0  mov     [rdi], eax
0x180005fa2  lea     ecx, [rax+r14]
0x180005fa6  test    r14d, ecx
0x180005fa9  jz      short loc_180006001
0x180005fab  mov     [rsp+0A8h+var_50], rbx
0x180005fb0  mov     [rsp+0A8h+var_58], rbx
0x180005fb5  mov     rax, r13
0x180005fb8  shl     rax, 5
0x180005fbc  lea     r8, [rsp+0A8h+var_58]
0x180005fc1  mov     rdx, [rsp+0A8h+var_68]
0x180005fc6  cmp     dword ptr [rsi+9Ch], 0
0x180005fcd  jnz     short loc_18000600C
0x180005fcf  lea     r9, [rsp+0A8h+var_50]
0x180005fd4  mov     rcx, r12
0x180005fd7  mov     rax, [rax+r15]
0x180005fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fe0  mov     [rdi], eax
0x180005fe2  test    eax, eax
0x180005fe4  js      short loc_180006050
0x180005fe6  mov     rdx, [rsp+0A8h+var_58]; unsigned __int16 *
0x180005feb  test    rdx, rdx
0x180005fee  jz      short loc_18000602C
0x180005ff0  mov     r8, [rsp+0A8h+var_50]; struct IDispatch *
0x180005ff5  mov     rcx, rsi; this
0x180005ff8  call    ?AddItemToMap@EventObjectCollection@@AEAAJPEBGPEAUIDispatch@@@Z; EventObjectCollection::AddItemToMap(ushort const *,IDispatch *)
0x180005ffd  mov     [rdi], eax
0x180005fff  jmp     short loc_180006071
0x180006001  cmp     eax, 80004002h
0x180006006  jz      short loc_180005FAB
0x180006008  mov     [rdi], ebx
0x18000600a  jmp     short loc_180005FFF
0x18000600c  lea     rcx, [rsp+0A8h+var_50]
0x180006011  mov     qword ptr [rsp+0A8h+dwAuthnLevel], rcx
0x180006016  mov     r9d, [rsi+98h]
0x18000601d  mov     rcx, r12
0x180006020  mov     rax, [rax+r15+8]
0x180006025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000602a  jmp     short loc_180005FE0
0x18000602c  mov     edx, 1B3h; unsigned int
0x180006031  mov     r9d, 10h; unsigned __int16
0x180006037  mov     r8d, 80001203h; unsigned int
0x18000603d  lea     rcx, aComComplusSrcE_21; "com\\complus\\src\\events\\tier1\\enum."...
0x180006044  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180006049  mov     rdx, [rsp+0A8h+var_58]
0x18000604e  jmp     short loc_180005FF0
0x180006050  mov     rcx, [rsp+0A8h+var_50]
0x180006055  test    rcx, rcx
0x180006058  jz      short loc_180006066
0x18000605a  mov     rax, [rcx]
0x18000605d  mov     rax, [rax+10h]
0x180006061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006066  mov     [rdi], ebx
0x180006068  jmp     short loc_180005FFF
0x18000606a  test    eax, eax
0x18000606c  jmp     loc_180005E9D
0x180006071  mov     rcx, [rsp+0A8h+var_68]
0x180006076  test    rcx, rcx
0x180006079  jz      loc_180005E64
0x18000607f  mov     rax, [rcx]
0x180006082  mov     rax, [rax+10h]
0x180006086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000608b  jmp     loc_180005E64
0x180006090  mov     rax, [rsp+0A8h+arg_48]
0x180006098  mov     dword ptr [rax], 8007000Eh
0x18000609e  jmp     loc_180005F47
0x1800060a3  cmp     eax, 80004002h
0x1800060a8  jz      loc_180005E5D
0x1800060ae  mov     rcx, [rsp+0A8h+pProxy]
0x1800060b3  mov     rax, [rcx]
0x1800060b6  mov     rax, [rax+10h]
0x1800060ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060bf  jmp     loc_180005F47
0x1800060c4  mov     edx, 16Ah; unsigned int
0x1800060c9  mov     r9d, 10h; unsigned __int16
0x1800060cf  mov     r8d, 80001203h; unsigned int
0x1800060d5  lea     rcx, aComComplusSrcE_21; "com\\complus\\src\\events\\tier1\\enum."...
0x1800060dc  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x1800060e1  jmp     loc_180005DD8
0x1800060e6  mov     edx, 13h; unsigned int
0x1800060eb  mov     r9d, 10h; unsigned __int16
0x1800060f1  mov     r8d, 0C0001204h; unsigned int
0x1800060f7  lea     rcx, aComComplusSrcE_1; "com\\complus\\src\\events\\Shared\\Stri"...
0x1800060fe  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180006103  jmp     loc_180005F06
0x180006108  xor     ebx, ebx
0x18000610a  jmp     loc_180005EEA
0x180043700  push    rbp
0x180043702  sub     rsp, 40h
0x180043706  mov     rbp, rdx
0x180043709  mov     rcx, [rbp+40h]
0x18004370d  test    rcx, rcx
0x180043710  jz      short loc_18004371F
0x180043712  mov     rax, [rcx]
0x180043715  mov     rax, [rax+10h]
0x180043719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004371e  nop
0x18004371f  add     rsp, 40h
0x180043723  pop     rbp
0x180043724  retn
```
