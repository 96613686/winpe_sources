# PuShrinkFileSystem(ushort *,unsigned __int64,unsigned __int64 *)

- ea: `0x1801a8e54`
- end: `0x1801a9234`
- name: `?PuShrinkFileSystem@@YAJPEAG_KPEA_K@Z`
- size: `992`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1801a75e4`

## callees

- `0x180006350`
- `0x180006dd4`
- `0x18011d1d4`
- `0x1801332fc`
- `0x1801a8e54`
- `0x1801ff010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801a8ed2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801a8ed2`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1801a8f12`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1801a8f12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a9063`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a908f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a90be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a90f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a911f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a9150`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a9063`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a908f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a90be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a90f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a911f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a9150`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801a8f87`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801a8fe1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801a8f87`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801a8fe1`

## pseudocode

```c
__int64 __fastcall PuShrinkFileSystem(unsigned __int16 *a1, __int64 a2, unsigned __int64 *a3)
{
  HRESULT Instance; // ebx
  int v7; // edi
  int v8; // eax
  bool v9; // zf
  char *v10; // rcx
  int v11; // edi
  unsigned int i; // esi
  __int64 v13; // rbx
  __int64 v14; // rax
  LPVOID pv[2]; // [rsp+40h] [rbp-C0h] BYREF
  IUnknown *pProxy; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v18; // [rsp+58h] [rbp-A8h] BYREF
  int v19; // [rsp+5Ch] [rbp-A4h] BYREF
  __int128 v20; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v21[232]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v22; // [rsp+158h] [rbp+58h]

  ATL::CComPtr<IDefragClient>::CComPtr<IDefragClient>(&pProxy);
  v20 = 0;
  memset_0(v21, 0, 0x280u);
  v19 = 0;
  Instance = CoCreateInstance(&CLSID_CDefragEngine, 0, 4u, &IID_IDefragEngine, (LPVOID *)&pProxy);
  if ( Instance < 0 )
    goto LABEL_46;
  v7 = 0;
  Instance = CoSetProxyBlanket(
               pProxy,
               0xFFFFFFFF,
               0xFFFFFFFF,
               (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
               0,
               3u,
               (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
               0x40u);
  if ( Instance < 0 )
    goto LABEL_46;
  while ( 1 )
  {
    Instance = ((__int64 (__fastcall *)(IUnknown *, unsigned __int16 *, __int64, __int64, __int128 *))pProxy->lpVtbl[3].Release)(
                 pProxy,
                 a1,
                 a2,
                 a2,
                 &v20);
    if ( Instance != 1 )
      break;
    *(_OWORD *)pv = v20;
    Instance = ((__int64 (__fastcall *)(IUnknown *, LPVOID *))pProxy->lpVtbl[1].Release)(pProxy, pv);
    if ( Instance < 0 )
      goto LABEL_46;
    Sleep(0x1F4u);
    if ( (unsigned int)++v7 >= 0xA )
    {
      Instance = -2147220951;
      goto LABEL_46;
    }
  }
  if ( Instance < 0 )
  {
    if ( Instance == -1996488683 )
    {
LABEL_9:
      Instance = -2147220950;
      goto LABEL_46;
    }
    v8 = -2147220940;
    v9 = Instance == -1996488698;
    goto LABEL_40;
  }
  do
  {
    pv[0] = 0;
    v18 = 0;
    Sleep(0x1F4u);
    if ( ((int (__fastcall *)(IUnknown *, unsigned __int16 *, unsigned int *, LPVOID *))pProxy->lpVtbl[5].AddRef)(
           pProxy,
           a1,
           &v18,
           pv) < 0 )
      break;
    v10 = (char *)pv[0];
    v11 = 0;
    for ( i = 0; i < v18; ++i )
    {
      v13 = 208LL * i;
      v14 = *(_QWORD *)&v10[v13 + 12] - v20;
      if ( !v14 )
        v14 = *(_QWORD *)&v10[v13 + 20] - *((_QWORD *)&v20 + 1);
      if ( !v14 && *(_DWORD *)&v10[v13 + 8] == 1 )
        v11 = 1;
      if ( *(_QWORD *)&v10[v13 + 104] )
      {
        CoTaskMemFree(*(LPVOID *)&v10[v13 + 104]);
        *(_QWORD *)((char *)pv[0] + v13 + 104) = 0;
        v10 = (char *)pv[0];
      }
      if ( *(_QWORD *)&v10[v13 + 120] )
      {
        CoTaskMemFree(*(LPVOID *)&v10[v13 + 120]);
        *(_QWORD *)((char *)pv[0] + v13 + 120) = 0;
        v10 = (char *)pv[0];
      }
      if ( *(_QWORD *)&v10[v13 + 144] )
      {
        CoTaskMemFree(*(LPVOID *)&v10[v13 + 144]);
        *(_QWORD *)((char *)pv[0] + v13 + 144) = 0;
        v10 = (char *)pv[0];
      }
      if ( *(_QWORD *)&v10[v13 + 136] )
      {
        CoTaskMemFree(*(LPVOID *)&v10[v13 + 136]);
        *(_QWORD *)((char *)pv[0] + v13 + 136) = 0;
        v10 = (char *)pv[0];
      }
      if ( *(_QWORD *)&v10[v13 + 112] )
      {
        CoTaskMemFree(*(LPVOID *)&v10[v13 + 112]);
        *(_QWORD *)((char *)pv[0] + v13 + 112) = 0;
        v10 = (char *)pv[0];
      }
    }
    if ( v10 )
      CoTaskMemFree(v10);
  }
  while ( v11 );
  *(_OWORD *)pv = v20;
  Instance = ((__int64 (__fastcall *)(IUnknown *, LPVOID *, int *))pProxy->lpVtbl[6].Release)(pProxy, pv, &v19);
  if ( Instance >= 0 )
  {
    Instance = v19;
    if ( v19 < 0 )
    {
      switch ( v19 )
      {
        case -1996488671:
          Instance = -2147220934;
          goto LABEL_46;
        case -1996488683:
          goto LABEL_9;
        case -1996488698:
        case -1996488686:
          Instance = -2147220940;
          goto LABEL_46;
      }
      v8 = -2147220952;
      v9 = v19 == -1996488672;
LABEL_40:
      if ( v9 )
        Instance = v8;
      goto LABEL_46;
    }
    Instance = ((__int64 (__fastcall *)(IUnknown *, unsigned __int16 *, _BYTE *))pProxy->lpVtbl[5].Release)(
                 pProxy,
                 a1,
                 v21);
    if ( Instance >= 0 )
      *a3 = v22;
  }
LABEL_46:
  ATL::CComPtr<IDefragClient>::~CComPtr<IDefragClient>(&pProxy);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1801a8e54  push    rbp
0x1801a8e56  push    rbx
0x1801a8e57  push    rsi
0x1801a8e58  push    rdi
0x1801a8e59  push    r13
0x1801a8e5b  push    r14
0x1801a8e5d  push    r15
0x1801a8e5f  lea     rbp, [rsp-200h]
0x1801a8e67  sub     rsp, 300h
0x1801a8e6e  mov     rax, cs:__security_cookie
0x1801a8e75  xor     rax, rsp
0x1801a8e78  mov     [rbp+230h+var_40], rax
0x1801a8e7f  mov     r14, rcx
0x1801a8e82  mov     r15, r8
0x1801a8e85  lea     rcx, [rsp+330h+pProxy]
0x1801a8e8a  mov     rsi, rdx
0x1801a8e8d  call    ??0?$CComPtr@UIDefragClient@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefragClient>::CComPtr<IDefragClient>(void)
0x1801a8e92  xorps   xmm0, xmm0
0x1801a8e95  lea     rcx, [rsp+330h+var_2C0]; void *
0x1801a8e9a  xor     edx, edx; Val
0x1801a8e9c  mov     r8d, 280h; Size
0x1801a8ea2  movups  [rsp+330h+var_2D0], xmm0
0x1801a8ea7  call    memset_0
0x1801a8eac  xor     edx, edx; pUnkOuter
0x1801a8eae  mov     [rsp+330h+var_2D4], 0
0x1801a8eb6  lea     rax, [rsp+330h+pProxy]
0x1801a8ebb  lea     r9, IID_IDefragEngine; riid
0x1801a8ec2  mov     [rsp+330h+ppv], rax; ppv
0x1801a8ec7  lea     rcx, CLSID_CDefragEngine; rclsid
0x1801a8ece  lea     r8d, [rdx+4]; dwClsContext
0x1801a8ed2  call    cs:__imp_CoCreateInstance
0x1801a8ed9  nop     dword ptr [rax+rax+00h]
0x1801a8ede  mov     ebx, eax
0x1801a8ee0  test    eax, eax
0x1801a8ee2  js      loc_1801A9206
0x1801a8ee8  mov     rcx, [rsp+330h+pProxy]; pProxy
0x1801a8eed  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1801a8ef1  mov     [rsp+330h+dwCapabilities], 40h ; '@'; dwCapabilities
0x1801a8ef9  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1801a8efc  mov     [rsp+330h+pAuthInfo], r9; pAuthInfo
0x1801a8f01  xor     edi, edi
0x1801a8f03  mov     [rsp+330h+dwImpLevel], 3; dwImpLevel
0x1801a8f0b  mov     r8d, edx; dwAuthzSvc
0x1801a8f0e  mov     dword ptr [rsp+330h+ppv], edi; dwAuthnLevel
0x1801a8f12  call    cs:__imp_CoSetProxyBlanket
0x1801a8f19  nop     dword ptr [rax+rax+00h]
0x1801a8f1e  mov     ebx, eax
0x1801a8f20  test    eax, eax
0x1801a8f22  js      loc_1801A9206
0x1801a8f28  lea     r13d, [rdi+1]
0x1801a8f2c  mov     rcx, [rsp+330h+pProxy]
0x1801a8f31  lea     rdx, [rsp+330h+var_2D0]
0x1801a8f36  mov     [rsp+330h+ppv], rdx
0x1801a8f3b  mov     r9, rsi
0x1801a8f3e  mov     r8, rsi
0x1801a8f41  mov     rdx, r14
0x1801a8f44  mov     rax, [rcx]
0x1801a8f47  mov     rax, [rax+58h]
0x1801a8f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8f50  mov     ebx, eax
0x1801a8f52  cmp     eax, r13d
0x1801a8f55  jnz     short loc_1801A8FA5
0x1801a8f57  mov     rcx, [rsp+330h+pProxy]
0x1801a8f5c  lea     rdx, [rsp+330h+pv]
0x1801a8f61  movaps  xmm0, [rsp+330h+var_2D0]
0x1801a8f66  movdqa  xmmword ptr [rsp+330h+pv], xmm0
0x1801a8f6c  mov     rax, [rcx]
0x1801a8f6f  mov     rax, [rax+28h]
0x1801a8f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a8f78  mov     ebx, eax
0x1801a8f7a  test    eax, eax
0x1801a8f7c  js      loc_1801A9206
0x1801a8f82  mov     ecx, 1F4h; dwMilliseconds
0x1801a8f87  call    cs:__imp_Sleep
0x1801a8f8e  nop     dword ptr [rax+rax+00h]
0x1801a8f93  add     edi, r13d
0x1801a8f96  cmp     edi, 0Ah
0x1801a8f99  jb      short loc_1801A8F2C
0x1801a8f9b  mov     ebx, 80040229h
0x1801a8fa0  jmp     loc_1801A9206
0x1801a8fa5  test    ebx, ebx
0x1801a8fa7  jns     short loc_1801A8FCB
0x1801a8fa9  cmp     ebx, 89000015h
0x1801a8faf  jnz     short loc_1801A8FBB
0x1801a8fb1  mov     ebx, 8004022Ah
0x1801a8fb6  jmp     loc_1801A9206
0x1801a8fbb  mov     eax, 80040234h
0x1801a8fc0  cmp     ebx, 89000006h
0x1801a8fc6  jmp     loc_1801A91D1
0x1801a8fcb  mov     ecx, 1F4h; dwMilliseconds
0x1801a8fd0  mov     [rsp+330h+pv], 0
0x1801a8fd9  mov     [rsp+330h+var_2D8], 0
0x1801a8fe1  call    cs:__imp_Sleep
0x1801a8fe8  nop     dword ptr [rax+rax+00h]
0x1801a8fed  mov     rcx, [rsp+330h+pProxy]
0x1801a8ff2  lea     r9, [rsp+330h+pv]
0x1801a8ff7  lea     r8, [rsp+330h+var_2D8]
0x1801a8ffc  mov     rdx, r14
0x1801a8fff  mov     rax, [rcx]
0x1801a9002  mov     rax, [rax+80h]
0x1801a9009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a900e  test    eax, eax
0x1801a9010  js      loc_1801A9164
0x1801a9016  mov     rcx, [rsp+330h+pv]
0x1801a901b  xor     edi, edi
0x1801a901d  xor     esi, esi
0x1801a901f  cmp     [rsp+330h+var_2D8], esi
0x1801a9023  jbe     loc_1801A914B
0x1801a9029  mov     eax, esi
0x1801a902b  imul    rbx, rax, 0D0h
0x1801a9032  mov     rax, [rbx+rcx+0Ch]
0x1801a9037  sub     rax, qword ptr [rsp+330h+var_2D0]
0x1801a903c  jnz     short loc_1801A9048
0x1801a903e  mov     rax, [rbx+rcx+14h]
0x1801a9043  sub     rax, qword ptr [rsp+330h+var_2D0+8]
0x1801a9048  test    rax, rax
0x1801a904b  jnz     short loc_1801A9056
0x1801a904d  cmp     [rbx+rcx+8], r13d
0x1801a9052  cmovz   edi, r13d
0x1801a9056  mov     rax, [rbx+rcx+68h]
0x1801a905b  test    rax, rax
0x1801a905e  jz      short loc_1801A9082
0x1801a9060  mov     rcx, rax; pv
0x1801a9063  call    cs:__imp_CoTaskMemFree
0x1801a906a  nop     dword ptr [rax+rax+00h]
0x1801a906f  mov     rax, [rsp+330h+pv]
0x1801a9074  mov     qword ptr [rbx+rax+68h], 0
0x1801a907d  mov     rcx, [rsp+330h+pv]
0x1801a9082  mov     rax, [rbx+rcx+78h]
0x1801a9087  test    rax, rax
0x1801a908a  jz      short loc_1801A90AE
0x1801a908c  mov     rcx, rax; pv
0x1801a908f  call    cs:__imp_CoTaskMemFree
0x1801a9096  nop     dword ptr [rax+rax+00h]
0x1801a909b  mov     rax, [rsp+330h+pv]
0x1801a90a0  mov     qword ptr [rbx+rax+78h], 0
0x1801a90a9  mov     rcx, [rsp+330h+pv]
0x1801a90ae  mov     rax, [rbx+rcx+90h]
0x1801a90b6  test    rax, rax
0x1801a90b9  jz      short loc_1801A90E0
0x1801a90bb  mov     rcx, rax; pv
0x1801a90be  call    cs:__imp_CoTaskMemFree
0x1801a90c5  nop     dword ptr [rax+rax+00h]
0x1801a90ca  mov     rax, [rsp+330h+pv]
0x1801a90cf  mov     qword ptr [rbx+rax+90h], 0
0x1801a90db  mov     rcx, [rsp+330h+pv]
0x1801a90e0  mov     rax, [rbx+rcx+88h]
0x1801a90e8  test    rax, rax
0x1801a90eb  jz      short loc_1801A9112
0x1801a90ed  mov     rcx, rax; pv
0x1801a90f0  call    cs:__imp_CoTaskMemFree
0x1801a90f7  nop     dword ptr [rax+rax+00h]
0x1801a90fc  mov     rax, [rsp+330h+pv]
0x1801a9101  mov     qword ptr [rbx+rax+88h], 0
0x1801a910d  mov     rcx, [rsp+330h+pv]
0x1801a9112  mov     rax, [rbx+rcx+70h]
0x1801a9117  test    rax, rax
0x1801a911a  jz      short loc_1801A913E
0x1801a911c  mov     rcx, rax; pv
0x1801a911f  call    cs:__imp_CoTaskMemFree
0x1801a9126  nop     dword ptr [rax+rax+00h]
0x1801a912b  mov     rax, [rsp+330h+pv]
0x1801a9130  mov     qword ptr [rbx+rax+70h], 0
0x1801a9139  mov     rcx, [rsp+330h+pv]; pv
0x1801a913e  add     esi, r13d
0x1801a9141  cmp     esi, [rsp+330h+var_2D8]
0x1801a9145  jb      loc_1801A9029
0x1801a914b  test    rcx, rcx
0x1801a914e  jz      short loc_1801A915C
0x1801a9150  call    cs:__imp_CoTaskMemFree
0x1801a9157  nop     dword ptr [rax+rax+00h]
0x1801a915c  test    edi, edi
0x1801a915e  jnz     loc_1801A8FCB
0x1801a9164  mov     rcx, [rsp+330h+pProxy]
0x1801a9169  lea     r8, [rsp+330h+var_2D4]
0x1801a916e  movaps  xmm0, [rsp+330h+var_2D0]
0x1801a9173  lea     rdx, [rsp+330h+pv]
0x1801a9178  movdqa  xmmword ptr [rsp+330h+pv], xmm0
0x1801a917e  mov     rax, [rcx]
0x1801a9181  mov     rax, [rax+0A0h]
0x1801a9188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a918d  mov     ebx, eax
0x1801a918f  test    eax, eax
0x1801a9191  js      short loc_1801A9206
0x1801a9193  mov     ebx, [rsp+330h+var_2D4]
0x1801a9197  test    ebx, ebx
0x1801a9199  jns     short loc_1801A91DD
0x1801a919b  cmp     ebx, 89000021h
0x1801a91a1  jnz     short loc_1801A91AA
0x1801a91a3  mov     ebx, 8004023Ah
0x1801a91a8  jmp     short loc_1801A9206
0x1801a91aa  cmp     ebx, 89000015h
0x1801a91b0  jz      loc_1801A8FB1
0x1801a91b6  cmp     ebx, 89000006h
0x1801a91bc  jz      short loc_1801A91D6
0x1801a91be  cmp     ebx, 89000012h
0x1801a91c4  jz      short loc_1801A91D6
0x1801a91c6  mov     eax, 80040228h
0x1801a91cb  cmp     ebx, 89000020h
0x1801a91d1  cmovz   ebx, eax
0x1801a91d4  jmp     short loc_1801A9206
0x1801a91d6  mov     ebx, 80040234h
0x1801a91db  jmp     short loc_1801A9206
0x1801a91dd  mov     rcx, [rsp+330h+pProxy]
0x1801a91e2  lea     r8, [rsp+330h+var_2C0]
0x1801a91e7  mov     rdx, r14
0x1801a91ea  mov     rax, [rcx]
0x1801a91ed  mov     rax, [rax+88h]
0x1801a91f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a91f9  mov     ebx, eax
0x1801a91fb  test    eax, eax
0x1801a91fd  js      short loc_1801A9206
0x1801a91ff  mov     rax, [rbp+230h+var_1D8]
0x1801a9203  mov     [r15], rax
0x1801a9206  lea     rcx, [rsp+330h+pProxy]
0x1801a920b  call    ??1?$CComPtr@UIDefragClient@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefragClient>::~CComPtr<IDefragClient>(void)
0x1801a9210  mov     eax, ebx
0x1801a9212  mov     rcx, [rbp+230h+var_40]
0x1801a9219  xor     rcx, rsp; StackCookie
0x1801a921c  call    __security_check_cookie
0x1801a9221  add     rsp, 300h
0x1801a9228  pop     r15
0x1801a922a  pop     r14
0x1801a922c  pop     r13
0x1801a922e  pop     rdi
0x1801a922f  pop     rsi
0x1801a9230  pop     rbx
0x1801a9231  pop     rbp
0x1801a9232  retn
```
