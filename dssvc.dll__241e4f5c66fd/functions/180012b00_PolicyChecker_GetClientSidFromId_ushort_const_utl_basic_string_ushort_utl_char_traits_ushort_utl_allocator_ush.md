# PolicyChecker::GetClientSidFromId(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x180012b00`
- end: `0x180012c69`
- name: `?GetClientSidFromId@PolicyChecker@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `361`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000e364`

## callees

- `0x180003134`
- `0x180006e2c`
- `0x180006f78`
- `0x18000bf80`
- `0x18000c93c`
- `0x180012364`
- `0x1800123d8`
- `0x180012b00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bef`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012be5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012be5`
- `ext-ms-win-security-chambers-l1-1-0!GetChamberSidFromId` at `0x180012b37`
- `ext-ms-win-security-chambers-l1-1-0!GetChamberSidFromId` at `0x180012b37`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x180012b8c`
- `USERENV!DeriveAppContainerSidFromAppContainerName` at `0x180012b8c`

## string_xrefs

- `0x180012b4c`: `Unable to get SID from ID %s! HR=0x%x`
- `0x180012b62`: `PolicyChecker::GetClientSidFromId`
- `0x180012bb3`: `PolicyChecker::GetClientSidFromId`
- `0x180012c3e`: `PolicyChecker::GetClientSidFromId`
- `0x180012b9d`: `Unable to DeriveAppContainerSidFromAppContainerName (ID=%s, hr=0x%x)`
- `0x180012c2d`: `Unable to get SID from ID HR=0x%x`

## pseudocode

```c
__int64 __fastcall PolicyChecker::GetClientSidFromId(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rcx
  signed int ChamberSidFromId; // ebx
  int *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  int *v10; // rax
  LPWSTR *v11; // rax
  signed int LastError; // eax
  int *v13; // rax
  __int64 v15; // [rsp+20h] [rbp-18h]
  signed int v16; // [rsp+28h] [rbp-10h]
  signed int v17; // [rsp+28h] [rbp-10h]
  PSID Sid; // [rsp+50h] [rbp+18h] BYREF
  __int64 v19; // [rsp+58h] [rbp+20h] BYREF

  v19 = 0;
  if ( !(unsigned __int8)IsGetChamberSidFromIdPresent() )
  {
    Sid = 0;
    ChamberSidFromId = DeriveAppContainerSidFromAppContainerName(a1, &Sid);
    if ( ChamberSidFromId >= 0 )
    {
      v11 = (LPWSTR *)tlx::replace<void *,void * (*)(void *),&void * LocalFree(void *),0>(&v19);
      if ( ConvertSidToStringSidW(Sid, v11) )
        goto LABEL_11;
      LastError = GetLastError();
      ChamberSidFromId = LastError;
      if ( LastError > 0 )
        ChamberSidFromId = (unsigned __int16)LastError | 0x80070000;
      if ( ChamberSidFromId >= 0 )
      {
LABEL_11:
        tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>(&Sid);
        goto LABEL_12;
      }
    }
    else
    {
      v10 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v9);
      v17 = ChamberSidFromId;
      DSLogger::LogError(
        (DSLogger *)v10,
        L"PolicyChecker::GetClientSidFromId",
        0xB5u,
        L"Unable to DeriveAppContainerSidFromAppContainerName (ID=%s, hr=0x%x)",
        a1,
        v17);
      ChamberSidFromId = -1055719415;
    }
    tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>(&Sid);
    goto LABEL_14;
  }
  v4 = tlx::replace<void *,void * (*)(void *),&void * LocalFree(void *),0>(&v19);
  ChamberSidFromId = GetChamberSidFromId(a1, v4);
  if ( ChamberSidFromId < 0 )
  {
    v7 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v5);
    v16 = ChamberSidFromId;
    DSLogger::LogError(
      (DSLogger *)v7,
      L"PolicyChecker::GetClientSidFromId",
      0xA9u,
      L"Unable to get SID from ID %s! HR=0x%x",
      a1,
      v16);
    ChamberSidFromId = -1055719415;
LABEL_14:
    v13 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v8);
    LODWORD(v15) = ChamberSidFromId;
    DSLogger::LogError(
      (DSLogger *)v13,
      L"PolicyChecker::GetClientSidFromId",
      0xC5u,
      L"Unable to get SID from ID HR=0x%x",
      v15);
    goto LABEL_15;
  }
LABEL_12:
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           a2,
                           v19) )
  {
    ChamberSidFromId = -2147024882;
    goto LABEL_14;
  }
LABEL_15:
  tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete((void **)&v19);
  return (unsigned int)ChamberSidFromId;
}

```

## disassembly

```asm
0x180012b00  mov     [rsp+arg_0], rbx
0x180012b05  mov     [rsp+arg_8], rsi
0x180012b0a  push    rdi
0x180012b0b  sub     rsp, 30h
0x180012b0f  mov     rsi, rdx
0x180012b12  mov     [rsp+38h+arg_18], 0
0x180012b1b  mov     rdi, rcx
0x180012b1e  call    IsGetChamberSidFromIdPresent
0x180012b23  test    al, al
0x180012b25  jz      short loc_180012B7B
0x180012b27  lea     rcx, [rsp+38h+arg_18]
0x180012b2c  call    ??$replace@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@0@@Z; tlx::replace<void *,void * (*)(void *),&LocalFree(void *),0>(tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0> &)
0x180012b31  mov     rdx, rax
0x180012b34  mov     rcx, rdi
0x180012b37  call    cs:__imp_GetChamberSidFromId
0x180012b3d  mov     ebx, eax
0x180012b3f  test    eax, eax
0x180012b41  jns     loc_180012C12
0x180012b47  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180012b4c  lea     r9, aUnableToGetSid_1; "Unable to get SID from ID %s! HR=0x%x"
0x180012b53  mov     [rsp+38h+var_10], ebx
0x180012b57  mov     r8d, 0A9h; unsigned int
0x180012b5d  mov     [rsp+38h+var_18], rdi
0x180012b62  lea     rdx, aPolicycheckerG; "PolicyChecker::GetClientSidFromId"
0x180012b69  mov     rcx, rax; this
0x180012b6c  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180012b71  mov     ebx, 0C1130009h
0x180012b76  jmp     loc_180012C28
0x180012b7b  lea     rdx, [rsp+38h+Sid]
0x180012b80  mov     [rsp+38h+Sid], 0
0x180012b89  mov     rcx, rdi
0x180012b8c  call    cs:__imp_DeriveAppContainerSidFromAppContainerName
0x180012b92  mov     ebx, eax
0x180012b94  test    eax, eax
0x180012b96  jns     short loc_180012BD3
0x180012b98  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180012b9d  lea     r9, aUnableToDerive; "Unable to DeriveAppContainerSidFromAppC"...
0x180012ba4  mov     [rsp+38h+var_10], ebx
0x180012ba8  mov     r8d, 0B5h; unsigned int
0x180012bae  mov     [rsp+38h+var_18], rdi
0x180012bb3  lea     rdx, aPolicycheckerG; "PolicyChecker::GetClientSidFromId"
0x180012bba  mov     rcx, rax; this
0x180012bbd  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180012bc2  mov     ebx, 0C1130009h
0x180012bc7  lea     rcx, [rsp+38h+Sid]
0x180012bcc  call    ??1?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>(void)
0x180012bd1  jmp     short loc_180012C28
0x180012bd3  lea     rcx, [rsp+38h+arg_18]
0x180012bd8  call    ??$replace@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@0@@Z; tlx::replace<void *,void * (*)(void *),&LocalFree(void *),0>(tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0> &)
0x180012bdd  mov     rcx, [rsp+38h+Sid]; Sid
0x180012be2  mov     rdx, rax; StringSid
0x180012be5  call    cs:__imp_ConvertSidToStringSidW
0x180012beb  test    eax, eax
0x180012bed  jnz     short loc_180012C08
0x180012bef  call    cs:__imp_GetLastError
0x180012bf5  mov     ebx, eax
0x180012bf7  test    eax, eax
0x180012bf9  jle     short loc_180012C04
0x180012bfb  movzx   ebx, ax
0x180012bfe  or      ebx, 80070000h
0x180012c04  test    ebx, ebx
0x180012c06  js      short loc_180012BC7
0x180012c08  lea     rcx, [rsp+38h+Sid]
0x180012c0d  call    ??1?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>(void)
0x180012c12  mov     rdx, [rsp+38h+arg_18]
0x180012c17  mov     rcx, rsi
0x180012c1a  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180012c1f  test    al, al
0x180012c21  jnz     short loc_180012C4D
0x180012c23  mov     ebx, 8007000Eh
0x180012c28  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180012c2d  lea     r9, aUnableToGetSid; "Unable to get SID from ID HR=0x%x"
0x180012c34  mov     dword ptr [rsp+38h+var_18], ebx
0x180012c38  mov     r8d, 0C5h; unsigned int
0x180012c3e  lea     rdx, aPolicycheckerG; "PolicyChecker::GetClientSidFromId"
0x180012c45  mov     rcx, rax; this
0x180012c48  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180012c4d  lea     rcx, [rsp+38h+arg_18]
0x180012c52  call    ?_Delete@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::_Delete(void)
0x180012c57  mov     rsi, [rsp+38h+arg_8]
0x180012c5c  mov     eax, ebx
0x180012c5e  mov     rbx, [rsp+38h+arg_0]
0x180012c63  add     rsp, 30h
0x180012c67  pop     rdi
0x180012c68  retn
```
