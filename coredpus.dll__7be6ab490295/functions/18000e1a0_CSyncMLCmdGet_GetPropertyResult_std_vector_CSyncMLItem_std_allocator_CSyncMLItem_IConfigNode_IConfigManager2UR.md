# CSyncMLCmdGet::GetPropertyResult(std::vector<CSyncMLItem *,std::allocator<CSyncMLItem *>> &,IConfigNode *,IConfigManager2URI *,SyncMLProp,ConfigDataType)

- ea: `0x18000e1a0`
- end: `0x18000e488`
- name: `?GetPropertyResult@CSyncMLCmdGet@@AEAAJAEAV?$vector@PEAVCSyncMLItem@@V?$allocator@PEAVCSyncMLItem@@@std@@@std@@PEAUIConfigNode@@PEAUIConfigManager2URI@@W4SyncMLProp@@W4ConfigDataType@@@Z`
- size: `744`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000b560`

## callees

- `0x18000a760`
- `0x18000e020`
- `0x18000e1a0`
- `0x180014330`
- `0x180030010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e424`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000e424`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e340`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e340`
- `OLEAUT32!__imp_VariantInit` at `0x18000e201`
- `OLEAUT32!__imp_VariantInit` at `0x18000e201`
- `OLEAUT32!__imp_VariantClear` at `0x18000e330`
- `OLEAUT32!__imp_VariantClear` at `0x18000e330`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e350`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e350`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdGet::GetPropertyResult(
        __int64 a1,
        const void **a2,
        __int64 a3,
        __int64 a4,
        int a5,
        unsigned int a6)
{
  __int64 v6; // r12
  __int64 v10; // rcx
  unsigned __int16 *v11; // rcx
  int PropFromNode; // ebx
  HLOCAL hMem; // [rsp+48h] [rbp-69h] BYREF
  _DWORD v15[2]; // [rsp+50h] [rbp-61h] BYREF
  BSTR bstrString[2]; // [rsp+58h] [rbp-59h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+68h] [rbp-49h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-21h] BYREF
  void *v20; // [rsp+A0h] [rbp-11h]
  int v21; // [rsp+A8h] [rbp-9h]
  int v22; // [rsp+ACh] [rbp-5h]
  _DWORD *v23; // [rsp+B0h] [rbp-1h]
  __int64 v24; // [rsp+B8h] [rbp+7h]
  __int64 v25; // [rsp+D8h] [rbp+27h]

  v25 = v6;
  hMem = 0;
  bstrString[0] = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  switch ( a5 )
  {
    case 0:
      if ( a6 <= 0xD )
      {
        v11 = (&c_rgszCfgNodeDataType)[a6];
        if ( v11 )
          goto LABEL_13;
      }
      PropFromNode = -2147418113;
      break;
    case 1:
    case 3:
    case 4:
    case 5:
    case 8:
    case 9:
    case 10:
    case 11:
    case 12:
    case 13:
    case 14:
      EventDescriptor = (EVENT_DESCRIPTOR)*((_OWORD *)&gc_pgmPropsToGuid + a5);
      PropFromNode = CSyncMLCmdGet::GetPropFromNode(
                       v10,
                       a3,
                       (__int64)&EventDescriptor,
                       a5,
                       &pvarg,
                       (unsigned __int16 **)&hMem);
      if ( PropFromNode >= 0 )
      {
        v11 = (unsigned __int16 *)hMem;
        goto LABEL_13;
      }
      break;
    case 2:
      PropFromNode = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)a3 + 128LL))(a3, bstrString);
      if ( PropFromNode >= 0 )
      {
        v11 = bstrString[0];
        goto LABEL_13;
      }
      break;
    case 6:
      EventDescriptor = (EVENT_DESCRIPTOR)CFGMGR_PROPERTY_SEMANTICTYPE;
      PropFromNode = CSyncMLCmdGet::GetPropFromNode(
                       v10,
                       a3,
                       (__int64)&EventDescriptor,
                       6,
                       &pvarg,
                       (unsigned __int16 **)&hMem);
      if ( PropFromNode >= 0 )
      {
        v11 = (unsigned __int16 *)hMem;
        if ( !*(_WORD *)hMem && a6 != 8 )
          v11 = L"text/plain";
LABEL_13:
        PropFromNode = CSyncMLCmdGet::AppendResultItem((__int64)v11, a2, a4, 1, L"text/plain", v11, 1);
      }
      break;
    default:
      PropFromNode = -2147467263;
      break;
  }
  VariantClear(&pvarg);
  SysFreeString(bstrString[0]);
  LocalFree(hMem);
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v15[0] = PropFromNode;
    v23 = v15;
    *(_DWORD *)&EventDescriptor.Level = 5;
    UserData.Ptr = (ULONGLONG)off_18003E050;
    v24 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_18003E050;
    v20 = &unk_180036920;
    UserData.Reserved = 2;
    v21 = 30;
    v22 = 1;
    v15[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return (unsigned int)PropFromNode;
}

```

## disassembly

```asm
0x18000e1a0  mov     r11, rsp
0x18000e1a3  push    rbp
0x18000e1a4  push    rbx
0x18000e1a5  push    r13
0x18000e1a7  lea     rbp, [r11-4Fh]
0x18000e1ab  sub     rsp, 0E0h
0x18000e1b2  mov     rax, cs:__security_cookie
0x18000e1b9  xor     rax, rsp
0x18000e1bc  mov     [rbp+47h+var_38], rax
0x18000e1c0  mov     [r11+8], rsi
0x18000e1c4  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18000e1c8  movsxd  rsi, [rbp+47h+arg_20]
0x18000e1cc  xor     r13d, r13d
0x18000e1cf  mov     [r11-20h], rdi
0x18000e1d3  xorps   xmm0, xmm0
0x18000e1d6  movsxd  rdi, [rbp+47h+arg_28]
0x18000e1da  xor     eax, eax
0x18000e1dc  mov     [r11-28h], r12
0x18000e1e0  mov     rbx, r8
0x18000e1e3  mov     [r11-30h], r14
0x18000e1e7  mov     r14, rdx
0x18000e1ea  mov     [r11-38h], r15
0x18000e1ee  mov     r15, r9
0x18000e1f1  mov     [rbp+47h+hMem], r13
0x18000e1f5  mov     [rbp+47h+bstrString], r13
0x18000e1f9  movups  xmmword ptr [rbp+47h+pvarg], xmm0
0x18000e1fd  mov     qword ptr [rbp+47h+pvarg+10h], rax
0x18000e201  call    cs:__imp_VariantInit
0x18000e208  nop     dword ptr [rax+rax+00h]
0x18000e20d  cmp     esi, 0Eh; switch 15 cases
0x18000e210  ja      def_18000E22E; jumptable 000000018000E22E default case, case 7
0x18000e216  lea     rdx, __ImageBase
0x18000e21d  mov     ecx, ds:(jpt_18000E22E - 180000000h)[rdx+rsi*4]
0x18000e224  lea     r12, ?gc_szDefaultType@@3QBGB; "text/plain"
0x18000e22b  add     rcx, rdx
0x18000e22e  jmp     rcx; switch jump
0x18000e234  cmp     edi, 0Dh; jumptable 000000018000E22E case 0
0x18000e237  ja      short loc_18000E24A
0x18000e239  mov     rcx, rva ?c_rgszCfgNodeDataType@@3PAPEBGA[rdx+rdi*8]; ushort const * near * c_rgszCfgNodeDataType ...
0x18000e241  test    rcx, rcx
0x18000e244  jnz     loc_18000E300
0x18000e24a  mov     ebx, 8000FFFFh
0x18000e24f  jmp     loc_18000E32C
0x18000e254  movups  xmm0, cs:CFGMGR_PROPERTY_SEMANTICTYPE; jumptable 000000018000E22E case 6
0x18000e25b  lea     rax, [rbp+47h+hMem]
0x18000e25f  mov     r9d, 6
0x18000e265  mov     [rsp+0F0h+UserData], rax
0x18000e26a  lea     r8, [rbp+47h+EventDescriptor]
0x18000e26e  lea     rax, [rbp+47h+pvarg]
0x18000e272  movaps  xmmword ptr [rbp+47h+EventDescriptor.Id], xmm0
0x18000e276  mov     rdx, rbx
0x18000e279  mov     qword ptr [rsp+0F0h+UserDataCount], rax
0x18000e27e  call    ?GetPropFromNode@CSyncMLCmdGet@@AEBAJPEAUIConfigNode@@U_GUID@@W4SyncMLProp@@PEAUtagVARIANT@@PEAPEAG@Z; CSyncMLCmdGet::GetPropFromNode(IConfigNode *,_GUID,SyncMLProp,tagVARIANT *,ushort * *)
0x18000e283  mov     ebx, eax
0x18000e285  test    eax, eax
0x18000e287  js      loc_18000E32C
0x18000e28d  mov     rcx, [rbp+47h+hMem]
0x18000e291  cmp     r13w, [rcx]
0x18000e295  jnz     short loc_18000E300
0x18000e297  cmp     edi, 8
0x18000e29a  jz      short loc_18000E300
0x18000e29c  mov     rcx, r12
0x18000e29f  jmp     short loc_18000E300
0x18000e2a1  mov     rax, rsi; jumptable 000000018000E22E cases 1,3-5,8-14
0x18000e2a4  lea     r8, [rbp+47h+EventDescriptor]
0x18000e2a8  add     rax, rax
0x18000e2ab  mov     r9d, esi
0x18000e2ae  movups  xmm0, xmmword ptr rva ?gc_pgmPropsToGuid@@3QBU_GUID@@B.Data1[rdx+rax*8]; _GUID const near * const gc_pgmPropsToGuid ...
0x18000e2b6  lea     rax, [rbp+47h+hMem]
0x18000e2ba  mov     rdx, rbx
0x18000e2bd  mov     [rsp+0F0h+UserData], rax
0x18000e2c2  lea     rax, [rbp+47h+pvarg]
0x18000e2c6  mov     qword ptr [rsp+0F0h+UserDataCount], rax
0x18000e2cb  movaps  xmmword ptr [rbp+47h+EventDescriptor.Id], xmm0
0x18000e2cf  call    ?GetPropFromNode@CSyncMLCmdGet@@AEBAJPEAUIConfigNode@@U_GUID@@W4SyncMLProp@@PEAUtagVARIANT@@PEAPEAG@Z; CSyncMLCmdGet::GetPropFromNode(IConfigNode *,_GUID,SyncMLProp,tagVARIANT *,ushort * *)
0x18000e2d4  mov     ebx, eax
0x18000e2d6  test    eax, eax
0x18000e2d8  js      short loc_18000E32C
0x18000e2da  mov     rcx, [rbp+47h+hMem]
0x18000e2de  jmp     short loc_18000E300
0x18000e2e0  mov     rax, [rbx]; jumptable 000000018000E22E case 2
0x18000e2e3  lea     rdx, [rbp+47h+bstrString]
0x18000e2e7  mov     rcx, rbx
0x18000e2ea  mov     rax, [rax+80h]
0x18000e2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2f6  mov     ebx, eax
0x18000e2f8  test    eax, eax
0x18000e2fa  js      short loc_18000E32C
0x18000e2fc  mov     rcx, [rbp+47h+bstrString]; int
0x18000e300  mov     dword ptr [rsp+30h], 1; int
0x18000e308  mov     r9d, 1; int
0x18000e30e  mov     [rsp+0F0h+UserData], rcx; unsigned __int16 *
0x18000e313  mov     r8, r15; int
0x18000e316  mov     rdx, r14; int
0x18000e319  mov     qword ptr [rsp+0F0h+UserDataCount], r12; __int64
0x18000e31e  call    ?AppendResultItem@CSyncMLCmdGet@@AEAAJAEAV?$vector@PEAVCSyncMLItem@@V?$allocator@PEAVCSyncMLItem@@@std@@@std@@PEAUIConfigManager2URI@@W4ConfigDataType@@PEBG3H@Z; CSyncMLCmdGet::AppendResultItem(std::vector<CSyncMLItem *> &,IConfigManager2URI *,ConfigDataType,ushort const *,ushort const *,int)
0x18000e323  mov     ebx, eax
0x18000e325  jmp     short loc_18000E32C
0x18000e327  mov     ebx, 80004001h; jumptable 000000018000E22E default case, case 7
0x18000e32c  lea     rcx, [rbp+47h+pvarg]; pvarg
0x18000e330  call    cs:__imp_VariantClear
0x18000e337  nop     dword ptr [rax+rax+00h]
0x18000e33c  mov     rcx, [rbp+47h+bstrString]; bstrString
0x18000e340  call    cs:__imp_SysFreeString
0x18000e347  nop     dword ptr [rax+rax+00h]
0x18000e34c  mov     rcx, [rbp+47h+hMem]; hMem
0x18000e350  call    cs:__imp_LocalFree
0x18000e357  nop     dword ptr [rax+rax+00h]
0x18000e35c  mov     eax, cs:dword_18003E048
0x18000e362  mov     r15, [rsp+0F0h+var_30]
0x18000e36a  mov     r14, [rsp+0F0h+var_28]
0x18000e372  mov     r12, [rsp+0F0h+var_20]
0x18000e37a  mov     rdi, [rsp+0D8h]
0x18000e382  mov     rsi, [rsp+0F0h+arg_0]
0x18000e38a  cmp     eax, 5
0x18000e38d  jbe     loc_18000E430
0x18000e393  lea     rax, [rbp+47h+var_A8]
0x18000e397  mov     [rbp+47h+var_A8], ebx
0x18000e39a  mov     [rbp+47h+var_48], rax
0x18000e39e  lea     rcx, _TraceLoggingMetadata
0x18000e3a5  movzx   eax, cs:word_180036916
0x18000e3ac  lea     rdx, [rbp+47h+EventDescriptor]; EventDescriptor
0x18000e3b0  mov     dword ptr [rbp+47h+EventDescriptor.Level], eax
0x18000e3b3  xor     r9d, r9d; RelatedActivityId
0x18000e3b6  mov     rax, cs:off_18003E050
0x18000e3bd  xor     r8d, r8d; ActivityId
0x18000e3c0  mov     [rbp+47h+var_68.Ptr], rax
0x18000e3c4  mov     [rbp+47h+var_40], 4
0x18000e3cc  mov     dword ptr [rbp+47h+EventDescriptor.Id], 0B000000h
0x18000e3d3  mov     [rbp+47h+EventDescriptor.Keyword], r13
0x18000e3d7  movzx   eax, word ptr [rax]
0x18000e3da  mov     [rbp+47h+var_68.Size], eax
0x18000e3dd  lea     rax, unk_180036920
0x18000e3e4  mov     [rbp+47h+var_58], rax
0x18000e3e8  lea     rax, _TraceLoggingMetadataEnd
0x18000e3ef  sub     eax, ecx
0x18000e3f1  mov     dword ptr [rbp+47h+var_68.0Ch], 2
0x18000e3f8  mov     [rbp+47h+var_50], 1Eh
0x18000e3ff  mov     [rbp+47h+var_4C], 1
0x18000e406  mov     [rbp+47h+var_A4], eax
0x18000e409  mov     eax, [rbp+47h+var_A4]
0x18000e40c  mov     rcx, cs:RegHandle; RegHandle
0x18000e413  lea     rax, [rbp+47h+var_68]
0x18000e417  mov     [rsp+0F0h+UserData], rax; UserData
0x18000e41c  mov     [rsp+0F0h+UserDataCount], 3; UserDataCount
0x18000e424  call    cs:__imp_EventWriteTransfer
0x18000e42b  nop     dword ptr [rax+rax+00h]
0x18000e430  mov     eax, ebx
0x18000e432  mov     rcx, [rbp+47h+var_38]
0x18000e436  xor     rcx, rsp; StackCookie
0x18000e439  call    __security_check_cookie
0x18000e43e  add     rsp, 0E0h
0x18000e445  pop     r13
0x18000e447  pop     rbx
0x18000e448  pop     rbp
0x18000e449  retn
```
