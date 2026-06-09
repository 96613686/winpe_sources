# RegisterPurgeTask(ITaskFolder *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,ushort const *,tagVARIANT,_TASK_LOGON_TYPE,tagVARIANT)

- ea: `0x18003a6e0`
- end: `0x18003a850`
- name: `?RegisterPurgeTask@@YAJPEAUITaskFolder@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGUtagVARIANT@@W4_TASK_LOGON_TYPE@@3@Z`
- size: `368`
- prototype: `HRESULT __fastcall(ITaskFolder *RootFolder, std::wstring *Path, const wchar_t *UserId, tagVARIANT Sddl, _TASK_LOGON_TYPE RootFolder, tagVARIANT Path)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180039f68`

## callees

- `0x180002790`
- `0x18000b1e4`
- `0x18000b2f4`
- `0x180010c34`
- `0x180011844`
- `0x18003a6e0`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003a732`
- `OLEAUT32!__imp_VariantInit` at `0x18003a732`
- `OLEAUT32!__imp_VariantClear` at `0x18003a812`
- `OLEAUT32!__imp_VariantClear` at `0x18003a812`

## string_xrefs

- `0x18003a744`: `<?xml version="1.0" ?>\n<Task xmlns="http://schemas.microsoft.com/windows/2004/02/mit/task">\n    <RegistrationInfo>\n        <Author>Microsoft</Author>\n        <Version>1.0.0</Version>\n    </RegistrationInfo>\n    <Triggers>\n    </Triggers>\n    <Settings>\n        <Enabled>true</Enabled>\n        <AllowStartOnDemand>true</AllowStartOnDemand>\n        <UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine>\n        <DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries>\n       `

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RegisterPurgeTask(
        ITaskFolder *RootFolder,
        std::wstring *Path,
        const wchar_t *UserId,
        tagVARIANT *Sddl,
        _TASK_LOGON_TYPE a5,
        tagVARIANT *a6)
{
  HRESULT (__fastcall *RegisterTask)(ITaskFolder *, wchar_t *, wchar_t *, int, tagVARIANT, tagVARIANT, _TASK_LOGON_TYPE, tagVARIANT, IRegisteredTask **); // r12
  __int128 v10; // xmm6
  __int64 v11; // xmm7_8
  _QWORD **v12; // rax
  _QWORD *v13; // rbx
  const wchar_t *v14; // rax
  __int64 **v15; // rax
  __int64 v16; // rdx
  unsigned int v17; // ebx
  _bstr_t v19; // [rsp+58h] [rbp-B0h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v21; // [rsp+78h] [rbp-90h]
  tagVARIANT v22; // [rsp+88h] [rbp-80h] BYREF
  __int128 v23; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v24; // [rsp+B8h] [rbp-50h]
  $098DB7A1025FD79723C31AABD315313E v25; // [rsp+C8h] [rbp-40h] BYREF
  IRecordInfo *pRecInfo; // [rsp+D8h] [rbp-30h]
  ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> v27; // [rsp+E8h] [rbp-20h] BYREF

  v27.p = 0;
  RegisterTask = RootFolder->RegisterTask;
  VariantInit((VARIANTARG *)&pvarg.boolVal);
  v10 = *(__int128 *)((char *)&pvarg.0 + 8);
  v11 = v21;
  _bstr_t::_bstr_t(
    (_bstr_t *)&pvarg,
    L"<?xml version=\"1.0\" ?>\n"
     "<Task xmlns=\"http://schemas.microsoft.com/windows/2004/02/mit/task\">\n"
     "    <RegistrationInfo>\n"
     "        <Author>Microsoft</Author>\n"
     "        <Version>1.0.0</Version>\n"
     "    </RegistrationInfo>\n"
     "    <Triggers>\n"
     "    </Triggers>\n"
     "    <Settings>\n"
     "        <Enabled>true</Enabled>\n"
     "        <AllowStartOnDemand>true</AllowStartOnDemand>\n"
     "        <UseUnifiedSchedulingEngine>true</UseUnifiedSchedulingEngine>\n"
     "        <DisallowStartIfOnBatteries>false</DisallowStartIfOnBatteries>\n"
     "        <StopIfGoingOnBatteries>false</StopIfGoingOnBatteries>\n"
     "        <MaintenanceSettings>\n"
     "            <Period>P30D</Period>\n"
     "        </MaintenanceSettings>\n"
     "    </Settings>\n"
     "    <Actions>\n"
     "        <ComHandler>\n"
     "            <ClassId>{217700E0-2005-11DF-ADB9-F4CE462D9137}</ClassId>\n"
     "            <Data></Data>\n"
     "        </ComHandler>\n"
     "    </Actions>\n"
     "</Task>\n");
  v13 = *v12;
  if ( *v12 )
    v13 = (_QWORD *)*v13;
  v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Path->_Mypair._Myval2);
  _bstr_t::_bstr_t(&v19, v14);
  if ( *v15 )
    v16 = **v15;
  else
    v16 = 0;
  v22 = *a6;
  v23 = v10;
  v24 = v11;
  v25 = Sddl->0;
  pRecInfo = Sddl->pRecInfo;
  v17 = ((__int64 (__fastcall *)(ITaskFolder *, __int64, _QWORD *, __int64, $098DB7A1025FD79723C31AABD315313E *, __int128 *, int, tagVARIANT *, ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *))RegisterTask)(
          RootFolder,
          v16,
          v13,
          6,
          &v25,
          &v23,
          3,
          &v22,
          &v27);
  _bstr_t::_Free(&v19);
  _bstr_t::_Free((_bstr_t *)&pvarg);
  VariantClear((VARIANTARG *)&pvarg.boolVal);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
  return v17;
}

```

## disassembly

```asm
0x18003a6e0  mov     rax, rsp
0x18003a6e3  push    rbp
0x18003a6e4  push    rbx
0x18003a6e5  push    rsi
0x18003a6e6  push    rdi
0x18003a6e7  push    r12
0x18003a6e9  push    r14
0x18003a6eb  push    r15
0x18003a6ed  lea     rbp, [rax-48h]
0x18003a6f1  sub     rsp, 110h
0x18003a6f8  movaps  xmmword ptr [rax-48h], xmm6
0x18003a6fc  movaps  xmmword ptr [rax-58h], xmm7
0x18003a700  mov     rax, cs:__security_cookie
0x18003a707  xor     rax, rsp
0x18003a70a  mov     [rbp+40h+var_58], rax
0x18003a70e  mov     r14, UserId
0x18003a711  mov     rdi, Path
0x18003a714  mov     rsi, RootFolder
0x18003a717  mov     r15, [rbp+40h+arg_28]
0x18003a71b  mov     [rbp+40h+var_60.p], 0
0x18003a723  mov     rax, [RootFolder]
0x18003a726  mov     r12, [rax+80h]
0x18003a72d  lea     RootFolder, [rsp+140h+pvarg.___u0+8]; pvarg
0x18003a732  call    cs:__imp_VariantInit
0x18003a738  nop
0x18003a739  movups  xmm6, xmmword ptr [rsp+140h+pvarg.___u0+8]
0x18003a73e  movsd   xmm7, [rsp+140h+var_D0]
0x18003a744  lea     Path, aXmlVersion10Ta_0; "<?xml version=\"1.0\" ?>\n<Task xmlns="...
0x18003a74b  lea     RootFolder, [rsp+140h+pvarg]; this
0x18003a750  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003a755  nop
0x18003a756  mov     rbx, [rax]
0x18003a759  test    rbx, rbx
0x18003a75c  jz      short loc_18003A761
0x18003a75e  mov     rbx, [rbx]
0x18003a761  mov     RootFolder, rdi; this
0x18003a764  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003a769  mov     Path, rax; s
0x18003a76c  lea     RootFolder, [rsp+140h+var_F0]; this
0x18003a771  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003a776  nop
0x18003a777  mov     RootFolder, [rax]
0x18003a77a  test    RootFolder, RootFolder
0x18003a77d  jz      short loc_18003A784
0x18003a77f  mov     Path, [RootFolder]
0x18003a782  jmp     short loc_18003A786
0x18003a784  xor     edx, edx
0x18003a786  movaps  xmm0, xmmword ptr [r15]
0x18003a78a  movaps  [rbp+40h+var_C0], xmm0
0x18003a78e  movsd   xmm1, qword ptr [r15+10h]
0x18003a794  movsd   [rbp+40h+var_B0], xmm1
0x18003a799  movaps  [rbp+40h+var_A0], xmm6
0x18003a79d  movsd   [rbp+40h+var_90], xmm7
0x18003a7a2  movaps  xmm0, xmmword ptr [r14]
0x18003a7a6  movaps  [rbp+40h+var_80], xmm0
0x18003a7aa  movsd   xmm1, qword ptr [r14+10h]
0x18003a7b0  movsd   [rbp+40h+var_70], xmm1
0x18003a7b5  lea     rax, [rbp+40h+var_60]
0x18003a7b9  mov     [rsp+140h+var_100], rax
0x18003a7be  lea     rax, [rbp+40h+var_C0]
0x18003a7c2  mov     [rsp+140h+var_108], rax
0x18003a7c7  mov     dword ptr [rsp+140h+var_110], 3
0x18003a7cf  lea     rax, [rbp+40h+var_A0]
0x18003a7d3  mov     qword ptr [rsp+140h+var_118], rax
0x18003a7d8  lea     rax, [rbp+40h+var_80]
0x18003a7dc  mov     [rsp+140h+var_120], rax
0x18003a7e1  mov     r9d, 6
0x18003a7e7  mov     r8, rbx
0x18003a7ea  mov     RootFolder, rsi
0x18003a7ed  mov     rax, r12
0x18003a7f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a7f5  mov     ebx, eax
0x18003a7f7  lea     RootFolder, [rsp+140h+var_F0]; this
0x18003a7fc  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003a801  nop
0x18003a802  lea     RootFolder, [rsp+140h+pvarg]; this
0x18003a807  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003a80c  nop
0x18003a80d  lea     RootFolder, [rsp+140h+pvarg.___u0+8]; pvarg
0x18003a812  call    cs:__imp_VariantClear
0x18003a818  nop
0x18003a819  lea     RootFolder, [rbp+40h+var_60]; this
0x18003a81d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a822  mov     eax, ebx
0x18003a824  mov     RootFolder, [rbp+40h+var_58]
0x18003a828  xor     RootFolder, rsp; StackCookie
0x18003a82b  call    __security_check_cookie
0x18003a830  lea     r11, [rsp+140h+var_30]
0x18003a838  movaps  xmm6, xmmword ptr [r11-10h]
0x18003a83d  movaps  xmm7, xmmword ptr [r11-20h]
0x18003a842  mov     rsp, r11
0x18003a845  pop     r15
0x18003a847  pop     r14
0x18003a849  pop     r12
0x18003a84b  pop     rdi
0x18003a84c  pop     rsi
0x18003a84d  pop     rbx
0x18003a84e  pop     rbp
0x18003a84f  retn
```
