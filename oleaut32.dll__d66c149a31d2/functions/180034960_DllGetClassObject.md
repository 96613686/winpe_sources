# DllGetClassObject

- ea: `0x180034960`
- end: `0x180034ab0`
- name: `DllGetClassObject`
- size: `336`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180034960`
- `0x180034ab8`
- `0x180034b1c`
- `0x180037c20`
- `0x180049270`
- `0x18004a530`
- `0x18004e87c`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180034a62`
- `RPCRT4!NdrDllGetClassObject` at `0x180034a62`
- `ext-ms-win-ole32-oleautomation-l1-1-0!StdTypesGetClassObject` at `0x180034a94`
- `ext-ms-win-ole32-oleautomation-l1-1-0!StdTypesGetClassObject` at `0x180034a94`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const struct _GUID *v6; // rcx
  const struct _GUID *v7; // rdx
  const IID *v8; // rcx
  void **v9; // r8
  __int64 v10; // rax
  void *WrapperPSFactory_Imp; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  struct IPSFactoryBuffer *v16; // rax

  *ppv = 0;
  if ( (unsigned int)IsTypesCLSID(rclsid) )
  {
    if ( (unsigned __int8)IsMonikerLoadTypeLibPresent() )
      return StdTypesGetClassObject(rclsid, riid, ppv);
    else
      return -2147024846;
  }
  else if ( (unsigned int)IsAutomationCLSID(v6) )
  {
    v10 = *(_QWORD *)&v7->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1;
    if ( *(_QWORD *)&v7->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data1 )
      v10 = *(_QWORD *)v7->Data4 - *(_QWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4;
    if ( !v10 )
      goto LABEL_6;
    v13 = *(_QWORD *)&v7->Data1 - *(_QWORD *)&GUID_d5f569d0_593b_101a_b569_08002b2dbf7a.Data1;
    if ( *(_QWORD *)&v7->Data1 == *(_QWORD *)&GUID_d5f569d0_593b_101a_b569_08002b2dbf7a.Data1 )
      v13 = *(_QWORD *)v7->Data4 - *(_QWORD *)GUID_d5f569d0_593b_101a_b569_08002b2dbf7a.Data4;
    if ( !v13 )
      goto LABEL_6;
    v14 = *(_QWORD *)&v7->Data1 - *(_QWORD *)&GUID_21d1ca69_d24a_40fd_892c_5fbe36933b6f.Data1;
    if ( *(_QWORD *)&v7->Data1 == *(_QWORD *)&GUID_21d1ca69_d24a_40fd_892c_5fbe36933b6f.Data1 )
      v14 = *(_QWORD *)v7->Data4 - *(_QWORD *)GUID_21d1ca69_d24a_40fd_892c_5fbe36933b6f.Data4;
    if ( v14 )
    {
      return -2147467262;
    }
    else
    {
LABEL_6:
      WrapperPSFactory_Imp = (void *)GetWrapperPSFactory_Imp();
      *ppv = WrapperPSFactory_Imp;
      if ( WrapperPSFactory_Imp )
        return 0;
      v16 = COleAutomationPSFactory::Create();
      *ppv = v16;
      if ( v16 )
      {
        return 0;
      }
      else
      {
        *ppv = 0;
        return -2147024882;
      }
    }
  }
  else
  {
    v15 = *(_QWORD *)&v8->Data1 - *(_QWORD *)&CLSID_RecordInfo.Data1;
    if ( *(_QWORD *)&v8->Data1 == *(_QWORD *)&CLSID_RecordInfo.Data1 )
      v15 = *(_QWORD *)v8->Data4 - *(_QWORD *)CLSID_RecordInfo.Data4;
    if ( v15 )
      return NdrDllGetClassObject(
               v8,
               v7,
               v9,
               (const ProxyFileInfo **)&aProxyFileList,
               &IID_IProvideClassInfo,
               &gPFactory);
    else
      return CStubRecordInfoCF::QueryInterface((CStubRecordInfoCF *)off_1800C26D0, v7, v9);
  }
}

```

## disassembly

```asm
0x180034960  mov     [rsp+arg_0], rbx
0x180034965  mov     [rsp+arg_8], rsi
0x18003496a  push    rdi
0x18003496b  sub     rsp, 30h
0x18003496f  mov     rdi, r8
0x180034972  mov     qword ptr [r8], 0
0x180034979  mov     rbx, rdx
0x18003497c  mov     rsi, rcx
0x18003497f  call    ?IsTypesCLSID@@YAHAEBU_GUID@@@Z; IsTypesCLSID(_GUID const &)
0x180034984  test    eax, eax
0x180034986  jnz     short loc_1800349D4
0x180034988  call    ?IsAutomationCLSID@@YAHAEBU_GUID@@@Z; IsAutomationCLSID(_GUID const &)
0x18003498d  test    eax, eax
0x18003498f  jz      loc_180034A27
0x180034995  mov     rax, [rdx]
0x180034998  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data1
0x18003499f  jnz     short loc_1800349AC
0x1800349a1  mov     rax, [rdx+8]
0x1800349a5  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x1800349ac  test    rax, rax
0x1800349af  jnz     short loc_1800349E8
0x1800349b1  call    GetWrapperPSFactory_Imp
0x1800349b6  mov     [rdi], rax
0x1800349b9  test    rax, rax
0x1800349bc  jz      loc_180034A6D
0x1800349c2  xor     eax, eax
0x1800349c4  mov     rbx, [rsp+38h+arg_0]
0x1800349c9  mov     rsi, [rsp+38h+arg_8]
0x1800349ce  add     rsp, 30h
0x1800349d2  pop     rdi
0x1800349d3  retn
0x1800349d4  call    IsMonikerLoadTypeLibPresent
0x1800349d9  test    al, al
0x1800349db  jnz     loc_180034A8B
0x1800349e1  mov     eax, 80070032h
0x1800349e6  jmp     short loc_1800349C4
0x1800349e8  mov     rax, [rdx]
0x1800349eb  sub     rax, qword ptr cs:_GUID_d5f569d0_593b_101a_b569_08002b2dbf7a.Data1
0x1800349f2  jnz     short loc_1800349FF
0x1800349f4  mov     rax, [rdx+8]
0x1800349f8  sub     rax, qword ptr cs:_GUID_d5f569d0_593b_101a_b569_08002b2dbf7a.Data4
0x1800349ff  test    rax, rax
0x180034a02  jz      short loc_1800349B1
0x180034a04  mov     rax, [rdx]
0x180034a07  sub     rax, qword ptr cs:_GUID_21d1ca69_d24a_40fd_892c_5fbe36933b6f.Data1
0x180034a0e  jnz     short loc_180034A1B
0x180034a10  mov     rax, [rdx+8]
0x180034a14  sub     rax, qword ptr cs:_GUID_21d1ca69_d24a_40fd_892c_5fbe36933b6f.Data4
0x180034a1b  test    rax, rax
0x180034a1e  jz      short loc_1800349B1
0x180034a20  mov     eax, 80004002h
0x180034a25  jmp     short loc_1800349C4
0x180034a27  mov     rax, [rcx]
0x180034a2a  sub     rax, qword ptr cs:CLSID_RecordInfo.Data1
0x180034a31  jnz     short loc_180034A3E
0x180034a33  mov     rax, [rcx+8]
0x180034a37  sub     rax, qword ptr cs:CLSID_RecordInfo.Data4
0x180034a3e  test    rax, rax
0x180034a41  jz      short loc_180034A9F
0x180034a43  lea     rax, gPFactory
0x180034a4a  mov     [rsp+38h+pPSFactoryBuffer], rax; pPSFactoryBuffer
0x180034a4f  lea     r9, aProxyFileList; pProxyFileList
0x180034a56  lea     rax, IID_IProvideClassInfo
0x180034a5d  mov     [rsp+38h+pclsid], rax; pclsid
0x180034a62  call    cs:__imp_NdrDllGetClassObject
0x180034a68  jmp     loc_1800349C4
0x180034a6d  call    ?Create@COleAutomationPSFactory@@SAPEAUIPSFactoryBuffer@@XZ; COleAutomationPSFactory::Create(void)
0x180034a72  mov     [rdi], rax
0x180034a75  test    rax, rax
0x180034a78  jnz     loc_1800349C2
0x180034a7e  mov     [rdi], rax
0x180034a81  mov     eax, 8007000Eh
0x180034a86  jmp     loc_1800349C4
0x180034a8b  mov     r8, rdi
0x180034a8e  mov     rdx, rbx
0x180034a91  mov     rcx, rsi
0x180034a94  call    cs:__imp_StdTypesGetClassObject
0x180034a9a  jmp     loc_1800349C4
0x180034a9f  lea     rcx, off_1800C26D0; this
0x180034aa6  call    ?QueryInterface@CStubRecordInfoCF@@UEAAJAEBU_GUID@@PEAPEAX@Z; CStubRecordInfoCF::QueryInterface(_GUID const &,void * *)
0x180034aab  jmp     loc_1800349C4
```
