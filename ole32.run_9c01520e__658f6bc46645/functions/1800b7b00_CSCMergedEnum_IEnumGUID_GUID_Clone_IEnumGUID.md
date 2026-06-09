# CSCMergedEnum<IEnumGUID,_GUID>::Clone(IEnumGUID * *)

- ea: `0x1800b7b00`
- end: `0x1800b7c50`
- name: `?Clone@?$CSCMergedEnum@UIEnumGUID@@U_GUID@@@@UEAAJPEAPEAUIEnumGUID@@@Z`
- size: `336`
- prototype: `HRESULT __fastcall(CSCMergedEnum<IEnumGUID,_GUID> *this, IEnumGUID **ppenum)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800b7794`
- `0x1800b7b00`
- `0x1800b80d4`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b7b67`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b7b67`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800b7c05`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800b7c05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b7b3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b7b3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b7c1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800b7c1b`
- `RPCRT4!RpcImpersonateClient` at `0x1800b7b9d`
- `RPCRT4!RpcImpersonateClient` at `0x1800b7b9d`

## pseudocode

```c
__int64 __fastcall CSCMergedEnum<IEnumGUID,_GUID>::Clone(
        CSCMergedEnum<IEnumGUID,_GUID> *this,
        CSCMergedEnum<IEnumGUID,_GUID> **ppenum)
{
  unsigned __int64 v3; // rax
  unsigned int v5; // ebx
  IEnumGUID **v6; // r14
  CSCMergedEnum<IEnumGUID,_GUID> *v8; // rax
  CSCMergedEnum<IEnumGUID,_GUID> *v9; // rax
  CSCMergedEnum<IEnumGUID,_GUID> *v10; // rdi
  RPC_STATUS v11; // eax
  unsigned int m_cTotalEnum; // r8d
  unsigned int v13; // ebp
  RPC_STATUS i; // r15d
  IEnumGUID *v15; // rcx
  _GUID m_myiid; // [rsp+20h] [rbp-28h] BYREF

  v3 = 8LL * this->m_cTotalEnum;
  if ( v3 > 0xFFFFFFFF )
    return 2147942934LL;
  v5 = 0;
  v6 = (IEnumGUID **)CoTaskMemAlloc((unsigned int)v3);
  if ( !v6 )
    return 2147942414LL;
  v8 = (CSCMergedEnum<IEnumGUID,_GUID> *)HeapAlloc(g_hHeap, 0, 0x30u);
  if ( v8
    && (m_myiid = this->m_myiid,
        CSCMergedEnum<IEnumGUID,_GUID>::CSCMergedEnum<IEnumGUID,_GUID>(v8, &m_myiid),
        (v10 = v9) != 0) )
  {
    v11 = RpcImpersonateClient(0);
    m_cTotalEnum = this->m_cTotalEnum;
    v13 = 0;
    for ( i = v11; v13 < m_cTotalEnum; ++v13 )
    {
      v15 = this->m_pcsEnum[v13];
      ((void (__fastcall *)(IEnumGUID *, IEnumGUID **))v15->lpVtbl[2].QueryInterface)(v15, &v6[v13]);
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
0x1800b7b00  mov     rax, rsp
0x1800b7b03  mov     [rax+8], rbx
0x1800b7b07  mov     [rax+10h], rbp
0x1800b7b0b  mov     [rax+18h], rsi
0x1800b7b0f  mov     [rax+20h], rdi
0x1800b7b13  push    r12
0x1800b7b15  push    r14
0x1800b7b17  push    r15
0x1800b7b19  sub     rsp, 30h
0x1800b7b1d  mov     eax, [this+10h]
0x1800b7b20  mov     rsi, this
0x1800b7b23  shl     rax, 3
0x1800b7b27  mov     ecx, 0FFFFFFFFh
0x1800b7b2c  mov     r12, ppenum
0x1800b7b2f  cmp     rax, this
0x1800b7b32  ja      loc_1800B7C2B
0x1800b7b38  mov     ecx, eax; cb
0x1800b7b3a  call    cs:__imp_CoTaskMemAlloc
0x1800b7b41  nop     dword ptr [rax+rax+00h]
0x1800b7b46  xor     ebx, ebx
0x1800b7b48  mov     r14, rax
0x1800b7b4b  test    rax, rax
0x1800b7b4e  jnz     short loc_1800B7B5A
0x1800b7b50  mov     eax, 8007000Eh
0x1800b7b55  jmp     loc_1800B7C30
0x1800b7b5a  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800b7b61  xor     edx, edx; dwFlags
0x1800b7b63  lea     r8d, [ppenum+30h]; dwBytes
0x1800b7b67  call    cs:__imp_HeapAlloc
0x1800b7b6e  nop     dword ptr [rax+rax+00h]
0x1800b7b73  test    rax, rax
0x1800b7b76  jz      loc_1800B7C13
0x1800b7b7c  movups  xmm0, xmmword ptr [rsi+1Ch]
0x1800b7b80  lea     ppenum, [rsp+48h+var_28]
0x1800b7b85  mov     this, rax
0x1800b7b88  movdqu  [rsp+48h+var_28], xmm0
0x1800b7b8e  call    ??0?$CSCMergedEnum@UIEnumGUID@@U_GUID@@@@QEAA@U_GUID@@@Z; CSCMergedEnum<IEnumGUID,_GUID>::CSCMergedEnum<IEnumGUID,_GUID>(_GUID)
0x1800b7b93  mov     rdi, rax
0x1800b7b96  test    rax, rax
0x1800b7b99  jz      short loc_1800B7C13
0x1800b7b9b  xor     ecx, ecx; BindingHandle
0x1800b7b9d  call    cs:__imp_RpcImpersonateClient
0x1800b7ba4  nop     dword ptr [rax+rax+00h]
0x1800b7ba9  mov     r8d, [rsi+10h]
0x1800b7bad  mov     ebp, ebx
0x1800b7baf  mov     r15d, eax
0x1800b7bb2  test    r8d, r8d
0x1800b7bb5  jz      short loc_1800B7BDC
0x1800b7bb7  mov     rax, [rsi+8]
0x1800b7bbb  mov     edx, ebp
0x1800b7bbd  mov     this, [rax+ppenum*8]
0x1800b7bc1  lea     ppenum, [r14+ppenum*8]
0x1800b7bc5  mov     rax, [this]
0x1800b7bc8  mov     rax, [rax+30h]
0x1800b7bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7bd1  mov     r8d, [rsi+10h]; cEnum
0x1800b7bd5  inc     ebp
0x1800b7bd7  cmp     ebp, r8d
0x1800b7bda  jb      short loc_1800B7BB7
0x1800b7bdc  mov     ppenum, r14; pcsEnum
0x1800b7bdf  mov     this, rdi; this
0x1800b7be2  call    ?Initialize@?$CSCMergedEnum@UIEnumCATEGORYINFO@@UtagCATEGORYINFO@@@@QEAAJPEAPEAUIEnumCATEGORYINFO@@K@Z; CSCMergedEnum<IEnumCATEGORYINFO,tagCATEGORYINFO>::Initialize(IEnumCATEGORYINFO * *,ulong)
0x1800b7be7  mov     eax, [rsi+18h]
0x1800b7bea  mov     this, rdi
0x1800b7bed  mov     [rdi+18h], eax
0x1800b7bf0  mov     [r12], rdi
0x1800b7bf4  mov     rax, [rdi]
0x1800b7bf7  mov     rax, [rax+8]
0x1800b7bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7c00  test    r15d, r15d
0x1800b7c03  jnz     short loc_1800B7C18
0x1800b7c05  call    cs:__imp_RevertToSelf
0x1800b7c0c  nop     dword ptr [rax+rax+00h]
0x1800b7c11  jmp     short loc_1800B7C18
0x1800b7c13  mov     ebx, 8007000Eh
0x1800b7c18  mov     this, r14; pv
0x1800b7c1b  call    cs:__imp_CoTaskMemFree
0x1800b7c22  nop     dword ptr [rax+rax+00h]
0x1800b7c27  mov     eax, ebx
0x1800b7c29  jmp     short loc_1800B7C30
0x1800b7c2b  mov     eax, 80070216h
0x1800b7c30  mov     rbx, [rsp+48h+arg_0]
0x1800b7c35  mov     rbp, [rsp+48h+arg_8]
0x1800b7c3a  mov     rsi, [rsp+48h+arg_10]
0x1800b7c3f  mov     rdi, [rsp+48h+arg_18]
0x1800b7c44  add     rsp, 30h
0x1800b7c48  pop     r15
0x1800b7c4a  pop     r14
0x1800b7c4c  pop     r12
0x1800b7c4e  retn
```
