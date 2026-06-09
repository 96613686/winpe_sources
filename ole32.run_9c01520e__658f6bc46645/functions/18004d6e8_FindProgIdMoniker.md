# FindProgIdMoniker

- ea: `0x18004d6e8`
- end: `0x18004d9a3`
- name: `FindProgIdMoniker`
- size: `699`
- prototype: `HRESULT __fastcall(IBindCtx *pbc, const wchar_t *pszDisplayName, unsigned int *pcchEaten, IMoniker **ppmk)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800073e0`

## callees

- `0x180046460`
- `0x18004d6e8`
- `0x18004d9ac`
- `0x1800ce967`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d95c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004d95c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004d818`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004d818`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18004d8dc`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18004d8dc`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18004d876`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x18004d876`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004d908`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004d908`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18004d744`
- `api-ms-win-core-com-private-l1-1-0!InternalTlsAllocData` at `0x18004d744`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18004d890`
- `api-ms-win-core-com-private-l1-3-1!CoIsOle1Class` at `0x18004d890`

## pseudocode

```c
__int64 __fastcall FindProgIdMoniker(
        IBindCtx *pbc,
        const wchar_t *pszDisplayName,
        unsigned int *pcchEaten,
        IMoniker **ppmk)
{
  _DWORD *ReservedForOle; // rax
  HRESULT v6; // edi
  int v7; // ebx
  const wchar_t *v8; // r12
  int v9; // ecx
  const wchar_t *v10; // rsi
  _DWORD *v11; // rax
  __int64 v13; // r8
  __int64 v14; // r14
  OLECHAR *v15; // rax
  OLECHAR *v16; // r15
  _DWORD *v17; // rax
  _DWORD *v18; // rax
  IParseDisplayName *pPDN; // [rsp+30h] [rbp-48h] BYREF
  _DWORD *v20; // [rsp+38h] [rbp-40h] BYREF
  IMoniker **v21; // [rsp+40h] [rbp-38h]
  const wchar_t *v22; // [rsp+48h] [rbp-30h]
  IBindCtx *v23; // [rsp+50h] [rbp-28h]
  _GUID cid; // [rsp+58h] [rbp-20h] BYREF

  v21 = ppmk;
  pPDN = 0;
  cid = 0;
  v22 = pszDisplayName;
  v23 = pbc;
  ReservedForOle = NtCurrentTeb()->ReservedForOle;
  v20 = ReservedForOle;
  if ( !ReservedForOle )
  {
    v6 = InternalTlsAllocData(&v20);
    if ( v6 < 0 )
    {
      v7 = (int)pPDN;
      goto LABEL_26;
    }
    ReservedForOle = v20;
    ppmk = v21;
    pszDisplayName = v22;
  }
  v7 = ReservedForOle[128];
  ReservedForOle[128] = v7 | 1;
  if ( (v20[5] & 0x2000000) != 0 )
  {
    v6 = -2147467231;
LABEL_26:
    v18 = NtCurrentTeb()->ReservedForOle;
    if ( v18 )
      v18[128] = v7;
    return (unsigned int)v6;
  }
  *pcchEaten = 0;
  *ppmk = 0;
  v8 = pszDisplayName + 1;
  v9 = pszDisplayName[1];
  v10 = pszDisplayName + 1;
  if ( (unsigned __int16)(v9 - 48) > 9u )
  {
    while ( 1 )
    {
      if ( (unsigned __int16)(v9 - 46) > 0x2Cu || (v13 = 0x1FFFFFF80FFDLL, !_bittest64(&v13, (unsigned int)(v9 - 46))) )
      {
        if ( (unsigned __int16)(v9 - 97) > 0x19u )
          break;
      }
      v9 = *++v10;
    }
    v14 = v10 - pszDisplayName;
    v15 = (OLECHAR *)HeapAlloc(g_hHeap, 0, 2LL * (int)v14);
    v16 = v15;
    if ( v15 )
    {
      memcpy_0(v15, v8, 2LL * (int)v14 - 2);
      v16[(int)v14 - 1] = 0;
      v6 = CLSIDFromProgID(v16, &cid);
      if ( !v6 )
      {
        if ( CoIsOle1Class(&cid) )
        {
          v6 = Parse10DisplayName(&cid, v10 + 1, pcchEaten, v14 + 1, v21);
        }
        else if ( !CoGetClassObject(&cid, 0x417u, 0, &IID_IParseDisplayName, (LPVOID *)&pPDN)
               || (v6 = CoCreateInstance(&cid, 0, 0x403u, &IID_IParseDisplayName, (LPVOID *)&pPDN)) == 0 )
        {
          v6 = ((__int64 (__fastcall *)(IParseDisplayName *, IBindCtx *, const wchar_t *, unsigned int *, IMoniker **))pPDN->lpVtbl[1].QueryInterface)(
                 pPDN,
                 v23,
                 v22,
                 pcchEaten,
                 v21);
          ((void (__fastcall *)(IParseDisplayName *))pPDN->lpVtbl->Release)(pPDN);
        }
      }
      HeapFree(g_hHeap, 0, v16);
      goto LABEL_26;
    }
    v17 = NtCurrentTeb()->ReservedForOle;
    if ( v17 )
      v17[128] = v7;
    return 2147942414LL;
  }
  else
  {
    v11 = NtCurrentTeb()->ReservedForOle;
    if ( v11 )
      v11[128] = v7;
    return 2147746276LL;
  }
}

```

## disassembly

```asm
0x18004d6e8  push    rbp
0x18004d6ea  push    rbx
0x18004d6eb  push    rsi
0x18004d6ec  push    rdi
0x18004d6ed  push    r12
0x18004d6ef  push    r13
0x18004d6f1  push    r14
0x18004d6f3  push    r15
0x18004d6f5  mov     rbp, rsp
0x18004d6f8  sub     rsp, 78h
0x18004d6fc  mov     rax, cs:__security_cookie
0x18004d703  xor     rax, rsp
0x18004d706  mov     [rbp+var_10], rax
0x18004d70a  xor     r12d, r12d
0x18004d70d  mov     [rbp+var_38], ppmk
0x18004d711  mov     [rbp+pPDN], r12
0x18004d715  xorps   xmm0, xmm0
0x18004d718  movups  xmmword ptr [rbp+cid.Data1], xmm0
0x18004d71c  mov     rax, gs:30h
0x18004d725  mov     r13, pcchEaten
0x18004d728  mov     [rbp+var_30], pszDisplayName
0x18004d72c  mov     [rbp+var_28], pbc
0x18004d730  mov     rax, [rax+1758h]
0x18004d737  mov     [rbp+var_40], rax
0x18004d73b  test    rax, rax
0x18004d73e  jnz     short loc_18004D762
0x18004d740  lea     pbc, [rbp+var_40]
0x18004d744  call    cs:__imp_InternalTlsAllocData
0x18004d74b  nop     dword ptr [rax+rax+00h]
0x18004d750  mov     edi, eax
0x18004d752  test    eax, eax
0x18004d754  js      short loc_18004D78A
0x18004d756  mov     rax, [rbp+var_40]
0x18004d75a  mov     ppmk, [rbp+var_38]
0x18004d75e  mov     pszDisplayName, [rbp+var_30]
0x18004d762  mov     ebx, [rax+200h]
0x18004d768  mov     ecx, ebx
0x18004d76a  or      ecx, 1
0x18004d76d  mov     [rax+200h], ecx
0x18004d773  mov     rax, [rbp+var_40]
0x18004d777  test    dword ptr [rax+14h], 2000000h
0x18004d77e  jz      short loc_18004D792
0x18004d780  mov     edi, 80004021h
0x18004d785  jmp     loc_18004D968
0x18004d78a  mov     ebx, dword ptr [rbp+pPDN]
0x18004d78d  jmp     loc_18004D968
0x18004d792  mov     [r13+0], r12d
0x18004d796  mov     [ppmk], r12
0x18004d799  lea     r12, [pszDisplayName+2]
0x18004d79d  movzx   ecx, word ptr [r12]
0x18004d7a2  mov     rsi, r12
0x18004d7a5  lea     eax, [pbc-30h]
0x18004d7a8  cmp     ax, 9
0x18004d7ac  ja      short loc_18004D7D3
0x18004d7ae  mov     rax, gs:30h
0x18004d7b7  mov     rax, [rax+1758h]
0x18004d7be  test    rax, rax
0x18004d7c1  jz      short loc_18004D7C9
0x18004d7c3  mov     [rax+200h], ebx
0x18004d7c9  mov     eax, 800401E4h
0x18004d7ce  jmp     loc_18004D985
0x18004d7d3  lea     eax, [pbc-2Eh]
0x18004d7d6  cmp     ax, 2Ch ; ','
0x18004d7da  ja      short loc_18004D7EC
0x18004d7dc  mov     pcchEaten, 1FFFFFF80FFDh
0x18004d7e6  bt      pcchEaten, rax
0x18004d7ea  jb      short loc_18004D7F6
0x18004d7ec  sub     cx, 61h ; 'a'
0x18004d7f0  cmp     cx, 19h
0x18004d7f4  ja      short loc_18004D7FF
0x18004d7f6  add     rsi, 2
0x18004d7fa  movzx   ecx, word ptr [rsi]
0x18004d7fd  jmp     short loc_18004D7D3
0x18004d7ff  mov     pbc, cs:?g_hHeap@@3QEAXEA; hHeap
0x18004d806  mov     r14, rsi
0x18004d809  sub     r14, pszDisplayName
0x18004d80c  xor     edx, edx; dwFlags
0x18004d80e  sar     r14, 1
0x18004d811  movsxd  rdi, r14d
0x18004d814  lea     pcchEaten, [rdi+rdi]; dwBytes
0x18004d818  call    cs:__imp_HeapAlloc
0x18004d81f  nop     dword ptr [rax+rax+00h]
0x18004d824  mov     r15, rax
0x18004d827  test    rax, rax
0x18004d82a  jnz     short loc_18004D851
0x18004d82c  mov     rax, gs:30h
0x18004d835  mov     rax, [rax+1758h]
0x18004d83c  test    rax, rax
0x18004d83f  jz      short loc_18004D847
0x18004d841  mov     [rax+200h], ebx
0x18004d847  mov     eax, 8007000Eh
0x18004d84c  jmp     loc_18004D985
0x18004d851  lea     rdi, ds:0FFFFFFFFFFFFFFFEh[rdi*2]
0x18004d859  mov     pszDisplayName, r12; Src
0x18004d85c  mov     pcchEaten, rdi; Size
0x18004d85f  mov     pbc, r15; void *
0x18004d862  call    memcpy_0
0x18004d867  xor     r12d, r12d
0x18004d86a  lea     pszDisplayName, [rbp+cid]; lpclsid
0x18004d86e  mov     pbc, r15; lpszProgID
0x18004d871  mov     [rdi+r15], r12w
0x18004d876  call    cs:__imp_CLSIDFromProgID
0x18004d87d  nop     dword ptr [rax+rax+00h]
0x18004d882  mov     edi, eax
0x18004d884  test    eax, eax
0x18004d886  jnz     $errRet_16
0x18004d88c  lea     pbc, [rbp+cid]; rclsid
0x18004d890  call    cs:__imp_CoIsOle1Class
0x18004d897  nop     dword ptr [rax+rax+00h]
0x18004d89c  lea     pbc, [rbp+cid]; rclsid
0x18004d8a0  test    eax, eax
0x18004d8a2  jz      short loc_18004D8C4
0x18004d8a4  mov     pcchEaten, [rbp+var_38]
0x18004d8a8  lea     r9d, [r14+1]; cchEatenSoFar
0x18004d8ac  mov     [rsp+78h+ppv], pcchEaten; ppmk
0x18004d8b1  lea     pszDisplayName, [rsi+2]; szDisplayName
0x18004d8b5  mov     pcchEaten, r13; pcchEaten
0x18004d8b8  call    Parse10DisplayName
0x18004d8bd  mov     edi, eax
0x18004d8bf  jmp     $errRet_16
0x18004d8c4  lea     rax, [rbp+pPDN]
0x18004d8c8  xor     r8d, r8d; pvReserved
0x18004d8cb  lea     ppmk, IID_IParseDisplayName; riid
0x18004d8d2  mov     [rsp+78h+ppv], rax; ppv
0x18004d8d7  mov     edx, 417h; dwClsContext
0x18004d8dc  call    cs:__imp_CoGetClassObject
0x18004d8e3  nop     dword ptr [rax+rax+00h]
0x18004d8e8  test    eax, eax
0x18004d8ea  jz      short loc_18004D91A
0x18004d8ec  lea     rax, [rbp+pPDN]
0x18004d8f0  xor     edx, edx; pUnkOuter
0x18004d8f2  lea     ppmk, IID_IParseDisplayName; riid
0x18004d8f9  mov     [rsp+78h+ppv], rax; ppv
0x18004d8fe  mov     r8d, 403h; dwClsContext
0x18004d904  lea     pbc, [rbp+cid]; rclsid
0x18004d908  call    cs:__imp_CoCreateInstance
0x18004d90f  nop     dword ptr [rax+rax+00h]
0x18004d914  mov     edi, eax
0x18004d916  test    eax, eax
0x18004d918  jnz     short $errRet_16
0x18004d91a  mov     pbc, [rbp+pPDN]
0x18004d91e  mov     ppmk, r13
0x18004d921  mov     pcchEaten, [rbp+var_38]
0x18004d925  mov     pszDisplayName, [rbp+var_28]
0x18004d929  mov     [rsp+78h+ppv], pcchEaten
0x18004d92e  mov     rax, [pbc]
0x18004d931  mov     pcchEaten, [rbp+var_30]
0x18004d935  mov     rax, [rax+18h]
0x18004d939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d93e  mov     pbc, [rbp+pPDN]
0x18004d942  mov     edi, eax
0x18004d944  mov     rax, [pbc]
0x18004d947  mov     rax, [rax+10h]
0x18004d94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d950  mov     pbc, cs:?g_hHeap@@3QEAXEA; hHeap
0x18004d957  mov     pcchEaten, r15; lpMem
0x18004d95a  xor     edx, edx; dwFlags
0x18004d95c  call    cs:__imp_HeapFree
0x18004d963  nop     dword ptr [rax+rax+00h]
0x18004d968  mov     rax, gs:30h
0x18004d971  mov     rax, [rax+1758h]
0x18004d978  test    rax, rax
0x18004d97b  jz      short loc_18004D983
0x18004d97d  mov     [rax+200h], ebx
0x18004d983  mov     eax, edi
0x18004d985  mov     pbc, [rbp+var_10]
0x18004d989  xor     pbc, rsp; StackCookie
0x18004d98c  call    __security_check_cookie
0x18004d991  add     rsp, 78h
0x18004d995  pop     r15
0x18004d997  pop     r14
0x18004d999  pop     r13
0x18004d99b  pop     r12
0x18004d99d  pop     rdi
0x18004d99e  pop     rsi
0x18004d99f  pop     rbx
0x18004d9a0  pop     rbp
0x18004d9a1  retn
```
