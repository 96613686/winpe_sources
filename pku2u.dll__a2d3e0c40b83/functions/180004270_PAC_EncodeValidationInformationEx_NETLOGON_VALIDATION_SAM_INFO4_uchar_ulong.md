# PAC_EncodeValidationInformationEx(_NETLOGON_VALIDATION_SAM_INFO4 *,uchar * *,ulong *)

- ea: `0x180004270`
- end: `0x180004438`
- name: `?PAC_EncodeValidationInformationEx@@YAJPEAU_NETLOGON_VALIDATION_SAM_INFO4@@PEAPEAEPEAK@Z`
- size: `456`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO4 *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002e40`
- `0x1800044f0`

## callees

- `0x180004270`
- `0x1800057f0`
- `0x180021a54`
- `0x180046010`

## import_xrefs

- `RPCRT4!NdrMesTypeEncode3` at `0x1800043d2`
- `RPCRT4!NdrMesTypeEncode3` at `0x1800043d2`
- `RPCRT4!MesIncrementalHandleReset` at `0x18000438a`
- `RPCRT4!MesIncrementalHandleReset` at `0x18000438a`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x1800042f9`
- `RPCRT4!NdrMesTypeAlignSize3` at `0x1800042f9`
- `RPCRT4!MesHandleFree` at `0x18000441b`
- `RPCRT4!MesHandleFree` at `0x18000441b`
- `RPCRT4!I_RpcMapWin32Status` at `0x180004396`
- `RPCRT4!I_RpcMapWin32Status` at `0x180004396`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x1800042b9`
- `RPCRT4!MesEncodeIncrementalHandleCreate` at `0x1800042b9`

## pseudocode

```c
__int64 __fastcall PAC_EncodeValidationInformationEx(
        struct _NETLOGON_VALIDATION_SAM_INFO4 *a1,
        unsigned __int8 **a2,
        unsigned int *a3)
{
  unsigned __int8 *v5; // rbx
  unsigned int v6; // esi
  unsigned __int8 *v7; // rax
  unsigned int v8; // edi
  RPC_STATUS v9; // eax
  __int128 v11; // [rsp+40h] [rbp-38h] BYREF
  struct _NETLOGON_VALIDATION_SAM_INFO4 *pObject; // [rsp+80h] [rbp+8h] BYREF
  handle_t Handle; // [rsp+98h] [rbp+20h] BYREF

  pObject = a1;
  Handle = 0;
  v11 = 0;
  v5 = 0;
  if ( MesEncodeIncrementalHandleCreate(
         &v11,
         PacReadFcn,
         wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy,
         &Handle) )
  {
    goto LABEL_10;
  }
  v6 = NdrMesTypeAlignSize3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 4u, &pObject);
  if ( *((_DWORD *)Pku2uGlobalBaseSSP + 52) == 1 )
  {
    v5 = (unsigned __int8 *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)Pku2uGlobalBaseSSP + 30) + 384LL))(v6);
  }
  else
  {
    v7 = (unsigned __int8 *)(**((__int64 (__fastcall ***)(_QWORD))Pku2uGlobalBaseSSP + 31))(v6);
    v5 = v7;
    if ( v7 )
      memset_0(v7, 0, v6);
  }
  if ( !v5 )
  {
LABEL_10:
    v8 = -1073741670;
  }
  else
  {
    v8 = 0;
    DWORD2(v11) = v6;
    *(_QWORD *)&v11 = v5;
    v9 = MesIncrementalHandleReset(Handle, 0, 0, 0, 0, MES_ENCODE);
    if ( v9 )
    {
      v8 = I_RpcMapWin32Status(v9);
    }
    else
    {
      NdrMesTypeEncode3(Handle, &pPicklingInfo, &pProxyInfo, (const unsigned int **)&ArrTypeOffset, 4u, &pObject);
      *a2 = v5;
      *a3 = v6;
      v5 = 0;
    }
  }
  if ( v5 )
    Pku2uFree(v5);
  if ( Handle )
    MesHandleFree(Handle);
  return v8;
}

```

## disassembly

```asm
0x180004270  mov     rax, rsp
0x180004273  mov     [rax+10h], rbx
0x180004277  mov     [rax+8], rcx
0x18000427b  push    rsi
0x18000427c  push    rdi
0x18000427d  push    r12
0x18000427f  push    r14
0x180004281  push    r15
0x180004283  sub     rsp, 50h
0x180004287  mov     r14, r8
0x18000428a  mov     r15, rdx
0x18000428d  xor     r12d, r12d
0x180004290  mov     [rax+20h], r12
0x180004294  xorps   xmm0, xmm0
0x180004297  movups  xmmword ptr [rax-38h], xmm0
0x18000429b  mov     ebx, r12d
0x18000429e  mov     [rsp+78h+var_40], rbx
0x1800042a3  lea     r9, [rax+20h]; pHandle
0x1800042a7  lea     r8, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; WriteFn
0x1800042ae  lea     rdx, ?PacReadFcn@@YAXPEAXPEAPEADPEAI@Z; AllocFn
0x1800042b5  lea     rcx, [rax-38h]; UserState
0x1800042b9  call    cs:__imp_MesEncodeIncrementalHandleCreate
0x1800042bf  test    eax, eax
0x1800042c1  jnz     loc_1800043FC
0x1800042c7  lea     rax, [rsp+78h+arg_0]
0x1800042cf  mov     [rsp+78h+pObject], rax; pObject
0x1800042d4  mov     [rsp+78h+nTypeIndex], 4; nTypeIndex
0x1800042dc  lea     r9, ArrTypeOffset; ArrTypeOffset
0x1800042e3  lea     r8, pProxyInfo; pProxyInfo
0x1800042ea  lea     rdx, pPicklingInfo; pPicklingInfo
0x1800042f1  mov     rcx, [rsp+78h+Handle]; Handle
0x1800042f9  call    cs:__imp_NdrMesTypeAlignSize3
0x1800042ff  mov     rsi, rax
0x180004302  mov     [rsp+78h+var_48], esi
0x180004306  mov     rax, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; basessp::BaseSSP * Pku2uGlobalBaseSSP
0x18000430d  cmp     dword ptr [rax+0D0h], 1
0x180004314  jnz     short loc_180004330
0x180004316  mov     rax, [rax+0F0h]
0x18000431d  mov     ecx, esi
0x18000431f  mov     rax, [rax+180h]
0x180004326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000432b  mov     rbx, rax
0x18000432e  jmp     short loc_180004356
0x180004330  mov     rax, [rax+0F8h]
0x180004337  mov     ecx, esi
0x180004339  mov     rax, [rax]
0x18000433c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004341  mov     rbx, rax
0x180004344  test    rax, rax
0x180004347  jz      short loc_180004356
0x180004349  mov     r8d, esi; Size
0x18000434c  xor     edx, edx; Val
0x18000434e  mov     rcx, rax; void *
0x180004351  call    memset_0
0x180004356  mov     [rsp+78h+var_40], rbx
0x18000435b  test    rbx, rbx
0x18000435e  jz      loc_1800043FC
0x180004364  mov     edi, r12d
0x180004367  mov     [rsp+78h+var_30], esi
0x18000436b  mov     [rsp+78h+var_38], rbx
0x180004370  mov     dword ptr [rsp+78h+pObject], r12d; Operation
0x180004375  mov     qword ptr [rsp+78h+nTypeIndex], r12; ReadFn
0x18000437a  xor     r9d, r9d; WriteFn
0x18000437d  xor     r8d, r8d; AllocFn
0x180004380  xor     edx, edx; UserState
0x180004382  mov     rcx, [rsp+78h+Handle]; Handle
0x18000438a  call    cs:__imp_MesIncrementalHandleReset
0x180004390  test    eax, eax
0x180004392  jz      short loc_1800043A0
0x180004394  mov     ecx, eax; Status
0x180004396  call    cs:__imp_I_RpcMapWin32Status
0x18000439c  mov     edi, eax
0x18000439e  jmp     short loc_180004401
0x1800043a0  lea     rax, [rsp+78h+arg_0]
0x1800043a8  mov     [rsp+78h+pObject], rax; pObject
0x1800043ad  mov     [rsp+78h+nTypeIndex], 4; nTypeIndex
0x1800043b5  lea     r9, ArrTypeOffset; ArrTypeOffset
0x1800043bc  lea     r8, pProxyInfo; pProxyInfo
0x1800043c3  lea     rdx, pPicklingInfo; pPicklingInfo
0x1800043ca  mov     rcx, [rsp+78h+Handle]; Handle
0x1800043d2  call    cs:__imp_NdrMesTypeEncode3
0x1800043d8  nop
0x1800043d9  mov     [r15], rbx
0x1800043dc  mov     [r14], esi
0x1800043df  mov     rbx, r12
0x1800043e2  jmp     short loc_180004401
0x1800043e4  mov     edi, 0C000000Dh
0x1800043e9  mov     rbx, [rsp+78h+var_40]
0x1800043ee  jmp     short loc_180004401
0x1800043f0  mov     edi, 0C000000Dh
0x1800043f5  mov     rbx, [rsp+78h+var_40]
0x1800043fa  jmp     short loc_180004401
0x1800043fc  mov     edi, 0C000009Ah
0x180004401  test    rbx, rbx
0x180004404  jz      short loc_18000440E
0x180004406  mov     rcx, rbx; void *
0x180004409  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18000440e  mov     rcx, [rsp+78h+Handle]; Handle
0x180004416  test    rcx, rcx
0x180004419  jz      short loc_180004421
0x18000441b  call    cs:__imp_MesHandleFree
0x180004421  mov     eax, edi
0x180004423  mov     rbx, [rsp+78h+arg_8]
0x18000442b  add     rsp, 50h
0x18000442f  pop     r15
0x180004431  pop     r14
0x180004433  pop     r12
0x180004435  pop     rdi
0x180004436  pop     rsi
0x180004437  retn
```
