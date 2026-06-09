# CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>::Clone(IEnumCATEGORYINFO * *)

- ea: `0x1800b79a0`
- end: `0x1800b7af0`
- name: `?Clone@?$CSCMergedEnum@UIEnumCATEGORYINFO@@UtagCATEGORYINFO@@@@UEAAJPEAPEAUIEnumCATEGORYINFO@@@Z`
- size: `336`
- prototype: `HRESULT __fastcall(CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO> *this, IEnumCATEGORYINFO **ppenum)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800b7768`
- `0x1800b79a0`
- `0x1800b80d4`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b7a07`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b7a07`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800b7aa5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800b7aa5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b79da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b79da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b7abb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b7abb`
- `RPCRT4!RpcImpersonateClient` at `0x1800b7a3d`
- `RPCRT4!RpcImpersonateClient` at `0x1800b7a3d`

## pseudocode

```c
__int64 __fastcall CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>::Clone(
        CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO> *this,
        CSCMergedEnum<IEnumGUID,_GUID> **ppenum)
{
  unsigned __int64 v3; // rax
  unsigned int v5; // ebx
  IEnumGUID **v6; // r14
  CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO> *v8; // rax
  CSCMergedEnum<IEnumGUID,_GUID> *v9; // rax
  CSCMergedEnum<IEnumGUID,_GUID> *v10; // rdi
  RPC_STATUS v11; // eax
  unsigned int m_cTotalEnum; // r8d
  unsigned int v13; // ebp
  RPC_STATUS i; // r15d
  IEnumCATEGORYINFO *v15; // rcx
  _GUID m_myiid; // [rsp+20h] [rbp-28h] BYREF

  v3 = 8LL * this->m_cTotalEnum;
  if ( v3 > 0xFFFFFFFF )
    return 2147942934LL;
  v5 = 0;
  v6 = (IEnumGUID **)CoTaskMemAlloc((unsigned int)v3);
  if ( !v6 )
    return 2147942414LL;
  v8 = (CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO> *)HeapAlloc(g_hHeap, 0, 0x30u);
  if ( v8
    && (m_myiid = this->m_myiid,
        CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>::CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>(v8, &m_myiid),
        (v10 = v9) != 0) )
  {
    v11 = RpcImpersonateClient(0);
    m_cTotalEnum = this->m_cTotalEnum;
    v13 = 0;
    for ( i = v11; v13 < m_cTotalEnum; ++v13 )
    {
      v15 = this->m_pcsEnum[v13];
      ((void (__fastcall *)(IEnumCATEGORYINFO *, IEnumGUID **))v15->lpVtbl[2].QueryInterface)(v15, &v6[v13]);
      m_cTotalEnum = this->m_cTotalEnum;
    }
    CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>::Initialize(v10, v6, m_cTotalEnum);
    v10->m_CurrentEnum = this->m_CurrentEnum;
    *ppenum = v10;
    ((void (__fastcall *)(CSCMergedEnum<IEnumGUID,_GUID> *))v10->lpVtbl->AddRef)(v10);
    if ( !i )
      RevertToSelf();
  }
  else
  {
    v5 = -2147024882;
  }
  CoTaskMemFree(v6);
  return v5;
}

```

## disassembly

```asm
0x1800b79a0  mov     rax, rsp
0x1800b79a3  mov     [rax+8], rbx
0x1800b79a7  mov     [rax+10h], rbp
0x1800b79ab  mov     [rax+18h], rsi
0x1800b79af  mov     [rax+20h], rdi
0x1800b79b3  push    r12
0x1800b79b5  push    r14
0x1800b79b7  push    r15
0x1800b79b9  sub     rsp, 30h
0x1800b79bd  mov     eax, [this+10h]
0x1800b79c0  mov     rsi, this
0x1800b79c3  shl     rax, 3
0x1800b79c7  mov     ecx, 0FFFFFFFFh
0x1800b79cc  mov     r12, ppenum
0x1800b79cf  cmp     rax, this
0x1800b79d2  ja      loc_1800B7ACB
0x1800b79d8  mov     ecx, eax; cb
0x1800b79da  call    cs:__imp_CoTaskMemAlloc
0x1800b79e1  nop     dword ptr [rax+rax+00h]
0x1800b79e6  xor     ebx, ebx
0x1800b79e8  mov     r14, rax
0x1800b79eb  test    rax, rax
0x1800b79ee  jnz     short loc_1800B79FA
0x1800b79f0  mov     eax, 8007000Eh
0x1800b79f5  jmp     loc_1800B7AD0
0x1800b79fa  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800b7a01  xor     edx, edx; dwFlags
0x1800b7a03  lea     r8d, [ppenum+30h]; dwBytes
0x1800b7a07  call    cs:__imp_HeapAlloc
0x1800b7a0e  nop     dword ptr [rax+rax+00h]
0x1800b7a13  test    rax, rax
0x1800b7a16  jz      loc_1800B7AB3
0x1800b7a1c  movups  xmm0, xmmword ptr [rsi+1Ch]
0x1800b7a20  lea     ppenum, [rsp+48h+var_28]
0x1800b7a25  mov     this, rax
0x1800b7a28  movdqu  [rsp+48h+var_28], xmm0
0x1800b7a2e  call    ??0?$CSCMergedEnum@UIEnumCATEGORYINFO@@UtagCATEGORYINFO@@@@QEAA@U_GUID@@@Z; CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>::CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>(_GUID)
0x1800b7a33  mov     rdi, rax
0x1800b7a36  test    rax, rax
0x1800b7a39  jz      short loc_1800B7AB3
0x1800b7a3b  xor     ecx, ecx; BindingHandle
0x1800b7a3d  call    cs:__imp_RpcImpersonateClient
0x1800b7a44  nop     dword ptr [rax+rax+00h]
0x1800b7a49  mov     r8d, [rsi+10h]
0x1800b7a4d  mov     ebp, ebx
0x1800b7a4f  mov     r15d, eax
0x1800b7a52  test    r8d, r8d
0x1800b7a55  jz      short loc_1800B7A7C
0x1800b7a57  mov     rax, [rsi+8]
0x1800b7a5b  mov     edx, ebp
0x1800b7a5d  mov     this, [rax+ppenum*8]
0x1800b7a61  lea     ppenum, [r14+ppenum*8]
0x1800b7a65  mov     rax, [this]
0x1800b7a68  mov     rax, [rax+30h]
0x1800b7a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7a71  mov     r8d, [rsi+10h]; cEnum
0x1800b7a75  inc     ebp
0x1800b7a77  cmp     ebp, r8d
0x1800b7a7a  jb      short loc_1800B7A57
0x1800b7a7c  mov     ppenum, r14; pcsEnum
0x1800b7a7f  mov     this, rdi; this
0x1800b7a82  call    ?Initialize@?$CSCMergedEnum@UIEnumCATEGORYINFO@@UtagCATEGORYINFO@@@@QEAAJPEAPEAUIEnumCATEGORYINFO@@K@Z; CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>::Initialize(IEnumCATEGORYINFO * *,ulong)
0x1800b7a87  mov     eax, [rsi+18h]
0x1800b7a8a  mov     this, rdi
0x1800b7a8d  mov     [rdi+18h], eax
0x1800b7a90  mov     [r12], rdi
0x1800b7a94  mov     rax, [rdi]
0x1800b7a97  mov     rax, [rax+8]
0x1800b7a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7aa0  test    r15d, r15d
0x1800b7aa3  jnz     short loc_1800B7AB8
0x1800b7aa5  call    cs:__imp_RevertToSelf
0x1800b7aac  nop     dword ptr [rax+rax+00h]
0x1800b7ab1  jmp     short loc_1800B7AB8
0x1800b7ab3  mov     ebx, 8007000Eh
0x1800b7ab8  mov     this, r14; pv
0x1800b7abb  call    cs:__imp_CoTaskMemFree
0x1800b7ac2  nop     dword ptr [rax+rax+00h]
0x1800b7ac7  mov     eax, ebx
0x1800b7ac9  jmp     short loc_1800B7AD0
0x1800b7acb  mov     eax, 80070216h
0x1800b7ad0  mov     rbx, [rsp+48h+arg_0]
0x1800b7ad5  mov     rbp, [rsp+48h+arg_8]
0x1800b7ada  mov     rsi, [rsp+48h+arg_10]
0x1800b7adf  mov     rdi, [rsp+48h+arg_18]
0x1800b7ae4  add     rsp, 30h
0x1800b7ae8  pop     r15
0x1800b7aea  pop     r14
0x1800b7aec  pop     r12
0x1800b7aee  retn
```
