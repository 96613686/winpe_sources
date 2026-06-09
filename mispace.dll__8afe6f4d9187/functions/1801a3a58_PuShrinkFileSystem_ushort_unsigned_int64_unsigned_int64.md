# PuShrinkFileSystem(ushort *,unsigned __int64,unsigned __int64 *)

- ea: `0x1801a3a58`
- end: `0x1801a3dfb`
- name: `?PuShrinkFileSystem@@YAJPEAG_KPEA_K@Z`
- size: `931`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1801a22f0`

## callees

- `0x180006290`
- `0x180006cf4`
- `0x1801195bc`
- `0x18012f41c`
- `0x1801a3a58`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801a3ad6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801a3ad6`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1801a3b10`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1801a3b10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a3c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a3c75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a3c9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a3cca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a3cf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a3d1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a3c4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a3c75`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a3c9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a3cca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a3cf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a3d1e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801a3b7f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801a3bd3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801a3b7f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1801a3bd3`

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
0x1801a3a58  push    rbp
0x1801a3a5a  push    rbx
0x1801a3a5b  push    rsi
0x1801a3a5c  push    rdi
0x1801a3a5d  push    r13
0x1801a3a5f  push    r14
0x1801a3a61  push    r15
0x1801a3a63  lea     rbp, [rsp-200h]
0x1801a3a6b  sub     rsp, 300h
0x1801a3a72  mov     rax, cs:__security_cookie
0x1801a3a79  xor     rax, rsp
0x1801a3a7c  mov     [rbp+230h+var_40], rax
0x1801a3a83  mov     r14, rcx
0x1801a3a86  mov     r15, r8
0x1801a3a89  lea     rcx, [rsp+330h+pProxy]
0x1801a3a8e  mov     rsi, rdx
0x1801a3a91  call    ??0?$CComPtr@UIDefragClient@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefragClient>::CComPtr<IDefragClient>(void)
0x1801a3a96  xorps   xmm0, xmm0
0x1801a3a99  lea     rcx, [rsp+330h+var_2C0]; void *
0x1801a3a9e  xor     edx, edx; Val
0x1801a3aa0  mov     r8d, 280h; Size
0x1801a3aa6  movups  [rsp+330h+var_2D0], xmm0
0x1801a3aab  call    memset_0
0x1801a3ab0  xor     edx, edx; pUnkOuter
0x1801a3ab2  mov     [rsp+330h+var_2D4], 0
0x1801a3aba  lea     rax, [rsp+330h+pProxy]
0x1801a3abf  lea     r9, IID_IDefragEngine; riid
0x1801a3ac6  mov     [rsp+330h+ppv], rax; ppv
0x1801a3acb  lea     rcx, CLSID_CDefragEngine; rclsid
0x1801a3ad2  lea     r8d, [rdx+4]; dwClsContext
0x1801a3ad6  call    cs:__imp_CoCreateInstance
0x1801a3adc  mov     ebx, eax
0x1801a3ade  test    eax, eax
0x1801a3ae0  js      loc_1801A3DCE
0x1801a3ae6  mov     rcx, [rsp+330h+pProxy]; pProxy
0x1801a3aeb  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1801a3aef  mov     [rsp+330h+dwCapabilities], 40h ; '@'; dwCapabilities
0x1801a3af7  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1801a3afa  mov     [rsp+330h+pAuthInfo], r9; pAuthInfo
0x1801a3aff  xor     edi, edi
0x1801a3b01  mov     [rsp+330h+dwImpLevel], 3; dwImpLevel
0x1801a3b09  mov     r8d, edx; dwAuthzSvc
0x1801a3b0c  mov     dword ptr [rsp+330h+ppv], edi; dwAuthnLevel
0x1801a3b10  call    cs:__imp_CoSetProxyBlanket
0x1801a3b16  mov     ebx, eax
0x1801a3b18  test    eax, eax
0x1801a3b1a  js      loc_1801A3DCE
0x1801a3b20  lea     r13d, [rdi+1]
0x1801a3b24  mov     rcx, [rsp+330h+pProxy]
0x1801a3b29  lea     rdx, [rsp+330h+var_2D0]
0x1801a3b2e  mov     [rsp+330h+ppv], rdx
0x1801a3b33  mov     r9, rsi
0x1801a3b36  mov     r8, rsi
0x1801a3b39  mov     rdx, r14
0x1801a3b3c  mov     rax, [rcx]
0x1801a3b3f  mov     rax, [rax+58h]
0x1801a3b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3b48  mov     ebx, eax
0x1801a3b4a  cmp     eax, r13d
0x1801a3b4d  jnz     short loc_1801A3B97
0x1801a3b4f  mov     rcx, [rsp+330h+pProxy]
0x1801a3b54  lea     rdx, [rsp+330h+pv]
0x1801a3b59  movaps  xmm0, [rsp+330h+var_2D0]
0x1801a3b5e  movdqa  xmmword ptr [rsp+330h+pv], xmm0
0x1801a3b64  mov     rax, [rcx]
0x1801a3b67  mov     rax, [rax+28h]
0x1801a3b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3b70  mov     ebx, eax
0x1801a3b72  test    eax, eax
0x1801a3b74  js      loc_1801A3DCE
0x1801a3b7a  mov     ecx, 1F4h; dwMilliseconds
0x1801a3b7f  call    cs:__imp_Sleep
0x1801a3b85  add     edi, r13d
0x1801a3b88  cmp     edi, 0Ah
0x1801a3b8b  jb      short loc_1801A3B24
0x1801a3b8d  mov     ebx, 80040229h
0x1801a3b92  jmp     loc_1801A3DCE
0x1801a3b97  test    ebx, ebx
0x1801a3b99  jns     short loc_1801A3BBD
0x1801a3b9b  cmp     ebx, 89000015h
0x1801a3ba1  jnz     short loc_1801A3BAD
0x1801a3ba3  mov     ebx, 8004022Ah
0x1801a3ba8  jmp     loc_1801A3DCE
0x1801a3bad  mov     eax, 80040234h
0x1801a3bb2  cmp     ebx, 89000006h
0x1801a3bb8  jmp     loc_1801A3D99
0x1801a3bbd  mov     ecx, 1F4h; dwMilliseconds
0x1801a3bc2  mov     [rsp+330h+pv], 0
0x1801a3bcb  mov     [rsp+330h+var_2D8], 0
0x1801a3bd3  call    cs:__imp_Sleep
0x1801a3bd9  mov     rcx, [rsp+330h+pProxy]
0x1801a3bde  lea     r9, [rsp+330h+pv]
0x1801a3be3  lea     r8, [rsp+330h+var_2D8]
0x1801a3be8  mov     rdx, r14
0x1801a3beb  mov     rax, [rcx]
0x1801a3bee  mov     rax, [rax+80h]
0x1801a3bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3bfa  test    eax, eax
0x1801a3bfc  js      loc_1801A3D2C
0x1801a3c02  mov     rcx, [rsp+330h+pv]
0x1801a3c07  xor     edi, edi
0x1801a3c09  xor     esi, esi
0x1801a3c0b  cmp     [rsp+330h+var_2D8], esi
0x1801a3c0f  jbe     loc_1801A3D19
0x1801a3c15  mov     eax, esi
0x1801a3c17  imul    rbx, rax, 0D0h
0x1801a3c1e  mov     rax, [rbx+rcx+0Ch]
0x1801a3c23  sub     rax, qword ptr [rsp+330h+var_2D0]
0x1801a3c28  jnz     short loc_1801A3C34
0x1801a3c2a  mov     rax, [rbx+rcx+14h]
0x1801a3c2f  sub     rax, qword ptr [rsp+330h+var_2D0+8]
0x1801a3c34  test    rax, rax
0x1801a3c37  jnz     short loc_1801A3C42
0x1801a3c39  cmp     [rbx+rcx+8], r13d
0x1801a3c3e  cmovz   edi, r13d
0x1801a3c42  mov     rax, [rbx+rcx+68h]
0x1801a3c47  test    rax, rax
0x1801a3c4a  jz      short loc_1801A3C68
0x1801a3c4c  mov     rcx, rax; pv
0x1801a3c4f  call    cs:__imp_CoTaskMemFree
0x1801a3c55  mov     rax, [rsp+330h+pv]
0x1801a3c5a  mov     qword ptr [rbx+rax+68h], 0
0x1801a3c63  mov     rcx, [rsp+330h+pv]
0x1801a3c68  mov     rax, [rbx+rcx+78h]
0x1801a3c6d  test    rax, rax
0x1801a3c70  jz      short loc_1801A3C8E
0x1801a3c72  mov     rcx, rax; pv
0x1801a3c75  call    cs:__imp_CoTaskMemFree
0x1801a3c7b  mov     rax, [rsp+330h+pv]
0x1801a3c80  mov     qword ptr [rbx+rax+78h], 0
0x1801a3c89  mov     rcx, [rsp+330h+pv]
0x1801a3c8e  mov     rax, [rbx+rcx+90h]
0x1801a3c96  test    rax, rax
0x1801a3c99  jz      short loc_1801A3CBA
0x1801a3c9b  mov     rcx, rax; pv
0x1801a3c9e  call    cs:__imp_CoTaskMemFree
0x1801a3ca4  mov     rax, [rsp+330h+pv]
0x1801a3ca9  mov     qword ptr [rbx+rax+90h], 0
0x1801a3cb5  mov     rcx, [rsp+330h+pv]
0x1801a3cba  mov     rax, [rbx+rcx+88h]
0x1801a3cc2  test    rax, rax
0x1801a3cc5  jz      short loc_1801A3CE6
0x1801a3cc7  mov     rcx, rax; pv
0x1801a3cca  call    cs:__imp_CoTaskMemFree
0x1801a3cd0  mov     rax, [rsp+330h+pv]
0x1801a3cd5  mov     qword ptr [rbx+rax+88h], 0
0x1801a3ce1  mov     rcx, [rsp+330h+pv]
0x1801a3ce6  mov     rax, [rbx+rcx+70h]
0x1801a3ceb  test    rax, rax
0x1801a3cee  jz      short loc_1801A3D0C
0x1801a3cf0  mov     rcx, rax; pv
0x1801a3cf3  call    cs:__imp_CoTaskMemFree
0x1801a3cf9  mov     rax, [rsp+330h+pv]
0x1801a3cfe  mov     qword ptr [rbx+rax+70h], 0
0x1801a3d07  mov     rcx, [rsp+330h+pv]; pv
0x1801a3d0c  add     esi, r13d
0x1801a3d0f  cmp     esi, [rsp+330h+var_2D8]
0x1801a3d13  jb      loc_1801A3C15
0x1801a3d19  test    rcx, rcx
0x1801a3d1c  jz      short loc_1801A3D24
0x1801a3d1e  call    cs:__imp_CoTaskMemFree
0x1801a3d24  test    edi, edi
0x1801a3d26  jnz     loc_1801A3BBD
0x1801a3d2c  mov     rcx, [rsp+330h+pProxy]
0x1801a3d31  lea     r8, [rsp+330h+var_2D4]
0x1801a3d36  movaps  xmm0, [rsp+330h+var_2D0]
0x1801a3d3b  lea     rdx, [rsp+330h+pv]
0x1801a3d40  movdqa  xmmword ptr [rsp+330h+pv], xmm0
0x1801a3d46  mov     rax, [rcx]
0x1801a3d49  mov     rax, [rax+0A0h]
0x1801a3d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3d55  mov     ebx, eax
0x1801a3d57  test    eax, eax
0x1801a3d59  js      short loc_1801A3DCE
0x1801a3d5b  mov     ebx, [rsp+330h+var_2D4]
0x1801a3d5f  test    ebx, ebx
0x1801a3d61  jns     short loc_1801A3DA5
0x1801a3d63  cmp     ebx, 89000021h
0x1801a3d69  jnz     short loc_1801A3D72
0x1801a3d6b  mov     ebx, 8004023Ah
0x1801a3d70  jmp     short loc_1801A3DCE
0x1801a3d72  cmp     ebx, 89000015h
0x1801a3d78  jz      loc_1801A3BA3
0x1801a3d7e  cmp     ebx, 89000006h
0x1801a3d84  jz      short loc_1801A3D9E
0x1801a3d86  cmp     ebx, 89000012h
0x1801a3d8c  jz      short loc_1801A3D9E
0x1801a3d8e  mov     eax, 80040228h
0x1801a3d93  cmp     ebx, 89000020h
0x1801a3d99  cmovz   ebx, eax
0x1801a3d9c  jmp     short loc_1801A3DCE
0x1801a3d9e  mov     ebx, 80040234h
0x1801a3da3  jmp     short loc_1801A3DCE
0x1801a3da5  mov     rcx, [rsp+330h+pProxy]
0x1801a3daa  lea     r8, [rsp+330h+var_2C0]
0x1801a3daf  mov     rdx, r14
0x1801a3db2  mov     rax, [rcx]
0x1801a3db5  mov     rax, [rax+88h]
0x1801a3dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a3dc1  mov     ebx, eax
0x1801a3dc3  test    eax, eax
0x1801a3dc5  js      short loc_1801A3DCE
0x1801a3dc7  mov     rax, [rbp+230h+var_1D8]
0x1801a3dcb  mov     [r15], rax
0x1801a3dce  lea     rcx, [rsp+330h+pProxy]
0x1801a3dd3  call    ??1?$CComPtr@UIDefragClient@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefragClient>::~CComPtr<IDefragClient>(void)
0x1801a3dd8  mov     eax, ebx
0x1801a3dda  mov     rcx, [rbp+230h+var_40]
0x1801a3de1  xor     rcx, rsp; StackCookie
0x1801a3de4  call    __security_check_cookie
0x1801a3de9  add     rsp, 300h
0x1801a3df0  pop     r15
0x1801a3df2  pop     r14
0x1801a3df4  pop     r13
0x1801a3df6  pop     rdi
0x1801a3df7  pop     rsi
0x1801a3df8  pop     rbx
0x1801a3df9  pop     rbp
0x1801a3dfa  retn
```
