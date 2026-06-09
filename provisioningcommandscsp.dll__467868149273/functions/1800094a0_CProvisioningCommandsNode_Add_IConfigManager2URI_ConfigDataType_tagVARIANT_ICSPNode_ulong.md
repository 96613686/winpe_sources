# CProvisioningCommandsNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x1800094a0`
- end: `0x1800096ae`
- name: `?Add@CProvisioningCommandsNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `526`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001254`
- `0x180006e40`
- `0x1800094a0`
- `0x180009da0`
- `0x18000a240`
- `0x18000e010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800095d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800095e6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800095d6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800095e6`

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
0x1800094a0  mov     [rsp-8+arg_0], rbx
0x1800094a5  mov     [rsp-8+arg_10], rsi
0x1800094aa  push    rbp
0x1800094ab  push    rdi
0x1800094ac  push    r12
0x1800094ae  push    r14
0x1800094b0  push    r15
0x1800094b2  lea     rbp, [rsp-27h]
0x1800094b7  sub     rsp, 90h
0x1800094be  mov     [rbp+47h+var_70], 0
0x1800094c6  mov     r15, r9
0x1800094c9  mov     r12d, r8d
0x1800094cc  mov     r14, rdx
0x1800094cf  mov     rbx, rcx
0x1800094d2  test    rdx, rdx
0x1800094d5  jz      loc_18000968C
0x1800094db  mov     rdi, [rbp+47h+arg_20]
0x1800094df  test    rdi, rdi
0x1800094e2  jz      loc_18000968C
0x1800094e8  mov     rsi, [rbp+47h+arg_28]
0x1800094ec  test    rsi, rsi
0x1800094ef  jz      loc_18000968C
0x1800094f5  mov     qword ptr [rdi], 0
0x1800094fc  lea     rdx, [rbp+47h+var_70]
0x180009500  mov     dword ptr [rsi], 0
0x180009506  xor     r9d, r9d
0x180009509  mov     rcx, [rcx+18h]
0x18000950d  xor     r8d, r8d
0x180009510  mov     [rsp+0B0h+var_90], rdx
0x180009515  mov     rdx, r14
0x180009518  mov     rax, [rcx]
0x18000951b  mov     rax, [rax+0A8h]
0x180009522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009527  test    eax, eax
0x180009529  js      loc_180009691
0x18000952f  mov     eax, cs:dword_180014230
0x180009535  cmp     eax, 4
0x180009538  jbe     loc_1800095F2
0x18000953e  mov     rax, [r14]
0x180009541  lea     r9, [rbp+47h+var_60]
0x180009545  mov     r8d, 2Fh ; '/'
0x18000954b  mov     [rbp+47h+var_60], 0
0x180009553  xor     edx, edx
0x180009555  mov     rcx, r14
0x180009558  mov     rax, [rax+78h]
0x18000955c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009561  mov     rcx, [rbp+47h+var_70]
0x180009565  mov     [rbp+47h+bstrString], 0
0x18000956d  test    rcx, rcx
0x180009570  jz      short loc_18000958A
0x180009572  mov     rax, [rcx]
0x180009575  lea     r9, [rbp+47h+bstrString]
0x180009579  mov     r8d, 2Fh ; '/'
0x18000957f  xor     edx, edx
0x180009581  mov     rax, [rax+78h]
0x180009585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000958a  mov     eax, cs:dword_180014230
0x180009590  cmp     eax, 4
0x180009593  jbe     short loc_1800095D2
0x180009595  mov     eax, [rbx+2Ch]
0x180009598  lea     rdx, byte_180010A17
0x18000959f  mov     [rbp+47h+arg_8], eax
0x1800095a2  mov     rax, [rbp+47h+bstrString]
0x1800095a6  mov     [rbp+47h+var_58], rax
0x1800095aa  mov     rax, [rbp+47h+var_60]
0x1800095ae  mov     [rbp+47h+var_50], rax
0x1800095b2  lea     rax, [rbp+47h+arg_8]
0x1800095b6  mov     [rsp+0B0h+var_80], rax
0x1800095bb  lea     rax, [rbp+47h+var_58]
0x1800095bf  mov     [rsp+0B0h+var_88], rax
0x1800095c4  lea     rax, [rbp+47h+var_50]
0x1800095c8  mov     [rsp+0B0h+var_90], rax
0x1800095cd  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800095d2  mov     rcx, [rbp+47h+bstrString]; bstrString
0x1800095d6  call    cs:__imp_SysFreeString
0x1800095dd  nop     dword ptr [rax+rax+00h]
0x1800095e2  mov     rcx, [rbp+47h+var_60]; bstrString
0x1800095e6  call    cs:__imp_SysFreeString
0x1800095ed  nop     dword ptr [rax+rax+00h]
0x1800095f2  mov     rax, [rbx+10h]
0x1800095f6  mov     rcx, [rax+20h]; struct CspNodeMapBase *
0x1800095fa  test    rcx, rcx
0x1800095fd  jz      loc_180009685
0x180009603  mov     rdx, [rbp+47h+var_70]; struct IConfigManager2URI *
0x180009607  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x18000960c  test    rax, rax
0x18000960f  jz      short loc_180009685
0x180009611  mov     edx, [rbx+2Ch]
0x180009614  sub     edx, 1
0x180009617  jz      short loc_180009663
0x180009619  sub     edx, 1
0x18000961c  jz      short loc_180009663
0x18000961e  sub     edx, 1
0x180009621  jz      short loc_180009663
0x180009623  sub     edx, 2
0x180009626  jz      short loc_180009663
0x180009628  sub     edx, 1
0x18000962b  jz      short loc_180009663
0x18000962d  cmp     edx, 1
0x180009630  jz      short loc_180009663
0x180009632  movups  xmm0, xmmword ptr [r15]
0x180009636  lea     r9, [rbp+47h+var_40]
0x18000963a  mov     [rsp+0B0h+var_88], rsi
0x18000963f  movsd   xmm1, qword ptr [r15+10h]
0x180009645  mov     r8d, r12d
0x180009648  mov     rdx, r14
0x18000964b  movaps  [rbp+47h+var_40], xmm0
0x18000964f  mov     rcx, rbx
0x180009652  movsd   [rbp+47h+var_30], xmm1
0x180009657  mov     [rsp+0B0h+var_90], rdi
0x18000965c  call    ?Add@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z; CCSPNodeImpl::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)
0x180009661  jmp     short loc_180009691
0x180009663  mov     rdx, [rbp+47h+var_70]; struct IConfigManager2URI *
0x180009667  mov     r9d, 1; int
0x18000966d  mov     rcx, [rbx+10h]; struct CConfigServiceProvider2Impl *
0x180009671  mov     r8, rax; struct CSP_NODE_DATA *
0x180009674  mov     [rsp+0B0h+var_88], rsi; unsigned int *
0x180009679  mov     [rsp+0B0h+var_90], rdi; struct ICSPNode **
0x18000967e  call    ?CreateNodeInstance@CProvisioningCommandsNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z; CProvisioningCommandsNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)
0x180009683  jmp     short loc_180009691
0x180009685  mov     eax, 86000002h
0x18000968a  jmp     short loc_180009691
0x18000968c  mov     eax, 80070057h
0x180009691  lea     r11, [rsp+0B0h+var_20]
0x180009699  mov     rbx, [r11+30h]
0x18000969d  mov     rsi, [r11+40h]
0x1800096a1  mov     rsp, r11
0x1800096a4  pop     r15
0x1800096a6  pop     r14
0x1800096a8  pop     r12
0x1800096aa  pop     rdi
0x1800096ab  pop     rbp
0x1800096ac  retn
```
