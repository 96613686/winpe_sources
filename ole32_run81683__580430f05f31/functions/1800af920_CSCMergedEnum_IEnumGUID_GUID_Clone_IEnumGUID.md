# CSCMergedEnum<IEnumGUID,_GUID>::Clone(IEnumGUID * *)

- ea: `0x1800af920`
- end: `0x1800afa2c`
- name: `?Clone@?$CSCMergedEnum@UIEnumGUID@@U_GUID@@@@UEAAJPEAPEAUIEnumGUID@@@Z`
- size: `268`
- prototype: `HRESULT __fastcall(CSCMergedEnum<IEnumGUID,_GUID> *this, IEnumGUID **ppenum)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800af604`
- `0x1800af920`
- `0x1800afe3c`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800af96f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800af96f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800af9fe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800af9fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af94a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af94a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afa10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800afa10`
- `RPCRT4!RpcImpersonateClient` at `0x1800af99f`
- `RPCRT4!RpcImpersonateClient` at `0x1800af99f`

## pseudocode

```c
__int64 __fastcall CSCMergedEnum<IEnumGUID,_GUID>::Clone(
        CSCMergedEnum<IEnumGUID,_GUID> *this,
        CSCMergedEnum<IEnumGUID,_GUID> **ppenum)
{
  unsigned __int64 v3; // rax
  IEnumGUID **v5; // rsi
  CSCMergedEnum<IEnumGUID,_GUID> *v7; // rax
  CSCMergedEnum<IEnumGUID,_GUID> *v8; // rax
  CSCMergedEnum<IEnumGUID,_GUID> *v9; // rbx
  RPC_STATUS v10; // eax
  unsigned int m_cTotalEnum; // r8d
  __int64 v12; // rbp
  RPC_STATUS i; // r15d
  IEnumGUID *v14; // rcx
  unsigned int v15; // ebx
  _GUID m_myiid; // [rsp+20h] [rbp-48h] BYREF

  v3 = 8LL * this->m_cTotalEnum;
  if ( v3 > 0xFFFFFFFF )
    return 2147942934LL;
  v5 = (IEnumGUID **)CoTaskMemAlloc((unsigned int)v3);
  if ( !v5 )
    return 2147942414LL;
  v7 = (CSCMergedEnum<IEnumGUID,_GUID> *)HeapAlloc(g_hHeap, 0, 0x30u);
  if ( v7
    && (m_myiid = this->m_myiid,
        CSCMergedEnum<IEnumGUID,_GUID>::CSCMergedEnum<IEnumGUID,_GUID>(v7, &m_myiid),
        (v9 = v8) != 0) )
  {
    v10 = RpcImpersonateClient(0);
    m_cTotalEnum = this->m_cTotalEnum;
    v12 = 0;
    for ( i = v10; (unsigned int)v12 < m_cTotalEnum; v12 = (unsigned int)(v12 + 1) )
    {
      v14 = this->m_pcsEnum[v12];
      ((void (__fastcall *)(IEnumGUID *, IEnumGUID **))v14->lpVtbl[2].QueryInterface)(v14, &v5[v12]);
      m_cTotalEnum = this->m_cTotalEnum;
    }
    CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>::Initialize(v9, v5, m_cTotalEnum);
    v9->m_CurrentEnum = this->m_CurrentEnum;
    *ppenum = v9;
    ((void (__fastcall *)(CSCMergedEnum<IEnumGUID,_GUID> *))v9->lpVtbl->AddRef)(v9);
    if ( !i )
      RevertToSelf();
    v15 = 0;
  }
  else
  {
    v15 = -2147024882;
  }
  CoTaskMemFree(v5);
  return v15;
}

```

## disassembly

```asm
0x1800af920  push    rbx
0x1800af922  push    rbp
0x1800af923  push    rsi
0x1800af924  push    rdi
0x1800af925  push    r14
0x1800af927  push    r15
0x1800af929  sub     rsp, 38h
0x1800af92d  mov     eax, [this+10h]
0x1800af930  mov     rdi, this
0x1800af933  shl     rax, 3
0x1800af937  mov     ecx, 0FFFFFFFFh
0x1800af93c  mov     r14, ppenum
0x1800af93f  cmp     rax, this
0x1800af942  ja      loc_1800AFA1A
0x1800af948  mov     ecx, eax; cb
0x1800af94a  call    cs:__imp_CoTaskMemAlloc
0x1800af950  mov     rsi, rax
0x1800af953  test    rax, rax
0x1800af956  jnz     short loc_1800AF962
0x1800af958  mov     eax, 8007000Eh
0x1800af95d  jmp     loc_1800AFA1F
0x1800af962  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800af969  xor     edx, edx; dwFlags
0x1800af96b  lea     r8d, [ppenum+30h]; dwBytes
0x1800af96f  call    cs:__imp_HeapAlloc
0x1800af975  test    rax, rax
0x1800af978  jz      loc_1800AFA08
0x1800af97e  movups  xmm0, xmmword ptr [rdi+1Ch]
0x1800af982  lea     ppenum, [rsp+68h+var_48]
0x1800af987  mov     this, rax
0x1800af98a  movdqu  [rsp+68h+var_48], xmm0
0x1800af990  call    ??0?$CSCMergedEnum@UIEnumGUID@@U_GUID@@@@QEAA@U_GUID@@@Z; CSCMergedEnum<IEnumGUID,_GUID>::CSCMergedEnum<IEnumGUID,_GUID>(_GUID)
0x1800af995  mov     rbx, rax
0x1800af998  test    rax, rax
0x1800af99b  jz      short loc_1800AFA08
0x1800af99d  xor     ecx, ecx; BindingHandle
0x1800af99f  call    cs:__imp_RpcImpersonateClient
0x1800af9a5  mov     r8d, [rdi+10h]
0x1800af9a9  xor     ebp, ebp
0x1800af9ab  mov     r15d, eax
0x1800af9ae  test    r8d, r8d
0x1800af9b1  jz      short loc_1800AF9D6
0x1800af9b3  mov     this, [rdi+8]
0x1800af9b7  lea     ppenum, [rsi+rbp*8]
0x1800af9bb  mov     this, [this+rbp*8]
0x1800af9bf  mov     rax, [this]
0x1800af9c2  mov     rax, [rax+30h]
0x1800af9c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af9cb  mov     r8d, [rdi+10h]; cEnum
0x1800af9cf  inc     ebp
0x1800af9d1  cmp     ebp, r8d
0x1800af9d4  jb      short loc_1800AF9B3
0x1800af9d6  mov     ppenum, rsi; pcsEnum
0x1800af9d9  mov     this, rbx; this
0x1800af9dc  call    ?Initialize@?$CSCMergedEnum@UIEnumCATEGORYINFO@@UtagCATEGORYINFO@@@@QEAAJPEAPEAUIEnumCATEGORYINFO@@K@Z; CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>::Initialize(IEnumCATEGORYINFO * *,ulong)
0x1800af9e1  mov     eax, [rdi+18h]
0x1800af9e4  mov     this, rbx
0x1800af9e7  mov     [rbx+18h], eax
0x1800af9ea  mov     [r14], rbx
0x1800af9ed  mov     rax, [rbx]
0x1800af9f0  mov     rax, [rax+8]
0x1800af9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af9f9  test    r15d, r15d
0x1800af9fc  jnz     short loc_1800AFA04
0x1800af9fe  call    cs:__imp_RevertToSelf
0x1800afa04  xor     ebx, ebx
0x1800afa06  jmp     short loc_1800AFA0D
0x1800afa08  mov     ebx, 8007000Eh
0x1800afa0d  mov     this, rsi; pv
0x1800afa10  call    cs:__imp_CoTaskMemFree
0x1800afa16  mov     eax, ebx
0x1800afa18  jmp     short loc_1800AFA1F
0x1800afa1a  mov     eax, 80070216h
0x1800afa1f  add     rsp, 38h
0x1800afa23  pop     r15
0x1800afa25  pop     r14
0x1800afa27  pop     rdi
0x1800afa28  pop     rsi
0x1800afa29  pop     rbp
0x1800afa2a  pop     rbx
0x1800afa2b  retn
```
