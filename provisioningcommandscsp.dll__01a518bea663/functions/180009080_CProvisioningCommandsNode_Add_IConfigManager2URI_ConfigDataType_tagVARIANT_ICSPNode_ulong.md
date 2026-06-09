# CProvisioningCommandsNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x180009080`
- end: `0x180009281`
- name: `?Add@CProvisioningCommandsNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `513`
- prototype: `__int64 __fastcall(__int64, __int64 *, unsigned int, __int128 *, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001248`
- `0x180006b10`
- `0x180009080`
- `0x180009910`
- `0x180009d7c`
- `0x18000e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800091b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800091c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800091b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800091c0`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::Add(
        __int64 a1,
        __int64 *a2,
        unsigned int a3,
        __int128 *a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  struct ICSPNode **v10; // rdi
  unsigned int *v11; // rsi
  __int64 result; // rax
  __int64 v13; // rax
  int v14; // r8d
  int v15; // r9d
  int v16; // ecx
  const struct CspNodeMapBase *v17; // rcx
  const struct CSP_NODE_DATA *NodeMapEntryForURI; // rax
  __int64 v19; // xmm1_8
  struct IConfigManager2URI *v20; // [rsp+40h] [rbp-29h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-21h] BYREF
  BSTR v22; // [rsp+50h] [rbp-19h] BYREF
  BSTR v23; // [rsp+58h] [rbp-11h] BYREF
  BSTR v24[2]; // [rsp+60h] [rbp-9h] BYREF
  __int128 v25; // [rsp+70h] [rbp+7h] BYREF
  __int64 v26; // [rsp+80h] [rbp+17h]
  int v27; // [rsp+C8h] [rbp+5Fh] BYREF

  v20 = 0;
  if ( !a2 )
    return 2147942487LL;
  v10 = a5;
  if ( !a5 )
    return 2147942487LL;
  v11 = a6;
  if ( !a6 )
    return 2147942487LL;
  *a5 = 0;
  *v11 = 0;
  result = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD, _QWORD, struct IConfigManager2URI **))(**(_QWORD **)(a1 + 24) + 168LL))(
             *(_QWORD *)(a1 + 24),
             a2,
             0,
             0,
             &v20);
  if ( (int)result >= 0 )
  {
    if ( (unsigned int)dword_180014230 > 4 )
    {
      v13 = *a2;
      v22 = 0;
      (*(void (__fastcall **)(__int64 *, _QWORD, __int64, BSTR *))(v13 + 120))(a2, 0, 47, &v22);
      v16 = (int)v20;
      bstrString = 0;
      if ( v20 )
        (*(void (__fastcall **)(struct IConfigManager2URI *, _QWORD, __int64, BSTR *))(*(_QWORD *)v20 + 120LL))(
          v20,
          0,
          47,
          &bstrString);
      if ( (unsigned int)dword_180014230 > 4 )
      {
        v27 = *(_DWORD *)(a1 + 44);
        v23 = bstrString;
        v24[0] = v22;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          v16,
          (unsigned int)&byte_180010A17,
          v14,
          v15,
          (__int64)v24,
          (__int64)&v23,
          (__int64)&v27);
      }
      SysFreeString(bstrString);
      SysFreeString(v22);
    }
    v17 = *(const struct CspNodeMapBase **)(*(_QWORD *)(a1 + 16) + 32LL);
    if ( v17 && (NodeMapEntryForURI = CspGetNodeMapEntryForURI(v17, v20)) != 0 )
    {
      if ( *(_DWORD *)(a1 + 44) == 1
        || *(_DWORD *)(a1 + 44) == 2
        || *(_DWORD *)(a1 + 44) == 3
        || *(_DWORD *)(a1 + 44) == 5
        || (unsigned int)(*(_DWORD *)(a1 + 44) - 6) < 2 )
      {
        return CProvisioningCommandsNode::CreateNodeInstance(
                 *(struct CConfigServiceProvider2Impl **)(a1 + 16),
                 v20,
                 NodeMapEntryForURI,
                 1,
                 v10,
                 v11);
      }
      else
      {
        v19 = *((_QWORD *)a4 + 2);
        v25 = *a4;
        v26 = v19;
        return CCSPNodeImpl::Add(a1, a2, a3, &v25, v10, v11);
      }
    }
    else
    {
      return 2248146946LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009080  mov     [rsp-8+arg_0], rbx
0x180009085  mov     [rsp-8+arg_10], rsi
0x18000908a  push    rbp
0x18000908b  push    rdi
0x18000908c  push    r12
0x18000908e  push    r14
0x180009090  push    r15
0x180009092  lea     rbp, [rsp-27h]
0x180009097  sub     rsp, 90h
0x18000909e  mov     [rbp+47h+var_70], 0
0x1800090a6  mov     r15, r9
0x1800090a9  mov     r12d, r8d
0x1800090ac  mov     r14, rdx
0x1800090af  mov     rbx, rcx
0x1800090b2  test    rdx, rdx
0x1800090b5  jz      loc_180009260
0x1800090bb  mov     rdi, [rbp+47h+arg_20]
0x1800090bf  test    rdi, rdi
0x1800090c2  jz      loc_180009260
0x1800090c8  mov     rsi, [rbp+47h+arg_28]
0x1800090cc  test    rsi, rsi
0x1800090cf  jz      loc_180009260
0x1800090d5  mov     qword ptr [rdi], 0
0x1800090dc  lea     rdx, [rbp+47h+var_70]
0x1800090e0  mov     dword ptr [rsi], 0
0x1800090e6  xor     r9d, r9d
0x1800090e9  mov     rcx, [rcx+18h]
0x1800090ed  xor     r8d, r8d
0x1800090f0  mov     [rsp+0B0h+var_90], rdx
0x1800090f5  mov     rdx, r14
0x1800090f8  mov     rax, [rcx]
0x1800090fb  mov     rax, [rax+0A8h]
0x180009102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009107  test    eax, eax
0x180009109  js      loc_180009265
0x18000910f  mov     eax, cs:dword_180014230
0x180009115  cmp     eax, 4
0x180009118  jbe     loc_1800091C6
0x18000911e  mov     rax, [r14]
0x180009121  lea     r9, [rbp+47h+var_60]
0x180009125  mov     r8d, 2Fh ; '/'
0x18000912b  mov     [rbp+47h+var_60], 0
0x180009133  xor     edx, edx
0x180009135  mov     rcx, r14
0x180009138  mov     rax, [rax+78h]
0x18000913c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009141  mov     rcx, [rbp+47h+var_70]
0x180009145  mov     [rbp+47h+bstrString], 0
0x18000914d  test    rcx, rcx
0x180009150  jz      short loc_18000916A
0x180009152  mov     rax, [rcx]
0x180009155  lea     r9, [rbp+47h+bstrString]
0x180009159  mov     r8d, 2Fh ; '/'
0x18000915f  xor     edx, edx
0x180009161  mov     rax, [rax+78h]
0x180009165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000916a  mov     eax, cs:dword_180014230
0x180009170  cmp     eax, 4
0x180009173  jbe     short loc_1800091B2
0x180009175  mov     eax, [rbx+2Ch]
0x180009178  lea     rdx, byte_180010A17
0x18000917f  mov     [rbp+47h+arg_8], eax
0x180009182  mov     rax, [rbp+47h+bstrString]
0x180009186  mov     [rbp+47h+var_58], rax
0x18000918a  mov     rax, [rbp+47h+var_60]
0x18000918e  mov     [rbp+47h+var_50], rax
0x180009192  lea     rax, [rbp+47h+arg_8]
0x180009196  mov     [rsp+0B0h+var_80], rax
0x18000919b  lea     rax, [rbp+47h+var_58]
0x18000919f  mov     [rsp+0B0h+var_88], rax
0x1800091a4  lea     rax, [rbp+47h+var_50]
0x1800091a8  mov     [rsp+0B0h+var_90], rax
0x1800091ad  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800091b2  mov     rcx, [rbp+47h+bstrString]; bstrString
0x1800091b6  call    cs:__imp_SysFreeString
0x1800091bc  mov     rcx, [rbp+47h+var_60]; bstrString
0x1800091c0  call    cs:__imp_SysFreeString
0x1800091c6  mov     rax, [rbx+10h]
0x1800091ca  mov     rcx, [rax+20h]; struct CspNodeMapBase *
0x1800091ce  test    rcx, rcx
0x1800091d1  jz      loc_180009259
0x1800091d7  mov     rdx, [rbp+47h+var_70]; struct IConfigManager2URI *
0x1800091db  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x1800091e0  test    rax, rax
0x1800091e3  jz      short loc_180009259
0x1800091e5  mov     edx, [rbx+2Ch]
0x1800091e8  sub     edx, 1
0x1800091eb  jz      short loc_180009237
0x1800091ed  sub     edx, 1
0x1800091f0  jz      short loc_180009237
0x1800091f2  sub     edx, 1
0x1800091f5  jz      short loc_180009237
0x1800091f7  sub     edx, 2
0x1800091fa  jz      short loc_180009237
0x1800091fc  sub     edx, 1
0x1800091ff  jz      short loc_180009237
0x180009201  cmp     edx, 1
0x180009204  jz      short loc_180009237
0x180009206  movups  xmm0, xmmword ptr [r15]
0x18000920a  lea     r9, [rbp+47h+var_40]
0x18000920e  mov     [rsp+0B0h+var_88], rsi
0x180009213  movsd   xmm1, qword ptr [r15+10h]
0x180009219  mov     r8d, r12d
0x18000921c  mov     rdx, r14
0x18000921f  movaps  [rbp+47h+var_40], xmm0
0x180009223  mov     rcx, rbx
0x180009226  movsd   [rbp+47h+var_30], xmm1
0x18000922b  mov     [rsp+0B0h+var_90], rdi
0x180009230  call    ?Add@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z; CCSPNodeImpl::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)
0x180009235  jmp     short loc_180009265
0x180009237  mov     rdx, [rbp+47h+var_70]; struct IConfigManager2URI *
0x18000923b  mov     r9d, 1; int
0x180009241  mov     rcx, [rbx+10h]; struct CConfigServiceProvider2Impl *
0x180009245  mov     r8, rax; struct CSP_NODE_DATA *
0x180009248  mov     [rsp+0B0h+var_88], rsi; unsigned int *
0x18000924d  mov     [rsp+0B0h+var_90], rdi; struct ICSPNode **
0x180009252  call    ?CreateNodeInstance@CProvisioningCommandsNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z; CProvisioningCommandsNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)
0x180009257  jmp     short loc_180009265
0x180009259  mov     eax, 86000002h
0x18000925e  jmp     short loc_180009265
0x180009260  mov     eax, 80070057h
0x180009265  lea     r11, [rsp+0B0h+var_20]
0x18000926d  mov     rbx, [r11+30h]
0x180009271  mov     rsi, [r11+40h]
0x180009275  mov     rsp, r11
0x180009278  pop     r15
0x18000927a  pop     r14
0x18000927c  pop     r12
0x18000927e  pop     rdi
0x18000927f  pop     rbp
0x180009280  retn
```
