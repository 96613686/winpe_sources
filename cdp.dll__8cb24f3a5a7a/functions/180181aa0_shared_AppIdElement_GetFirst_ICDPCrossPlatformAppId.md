# shared::AppIdElement::GetFirst(ICDPCrossPlatformAppId *)

- ea: `0x180181aa0`
- end: `0x180181dec`
- name: `?GetFirst@AppIdElement@shared@@SA?AU12@PEAVICDPCrossPlatformAppId@@@Z`
- size: `844`
- prototype: `static struct shared::AppIdElement __high(struct ICDPCrossPlatformAppId *)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x180042cd0`
- `0x1802ddd10`
- `0x1802f1bb0`

## callees

- `0x180013da0`
- `0x180054ba4`
- `0x18008539c`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800f66d8`
- `0x180143248`
- `0x180181aa0`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180181b6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180181c26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180181cce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180181b6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180181c26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180181cce`

## string_xrefs

- `0x180181b9a`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180181c54`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x180181cfc`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall shared::AppIdElement::GetFirst(__int64 a1, shared *a2)
{
  __int64 v4; // rsi
  int v5; // edi
  DWORD CurrentThreadId; // ecx
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // edi
  DWORD v13; // eax
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  int v18; // ecx
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rax
  const char *v23; // rax
  const char *v24; // rdi
  __int64 v26; // rax
  int v27; // edx
  int v28; // r8d
  _BYTE v29[32]; // [rsp+0h] [rbp-138h] BYREF
  const char *v30; // [rsp+30h] [rbp-108h] BYREF
  std::_Ref_count_base **v31; // [rsp+38h] [rbp-100h] BYREF
  __int64 v32; // [rsp+40h] [rbp-F8h] BYREF
  int v33; // [rsp+48h] [rbp-F0h]
  int v34; // [rsp+4Ch] [rbp-ECh]
  std::_Ref_count_base *v35[2]; // [rsp+50h] [rbp-E8h] BYREF
  _BYTE v36[24]; // [rsp+60h] [rbp-D8h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-C0h] BYREF
  _BYTE v38[56]; // [rsp+B0h] [rbp-88h] BYREF
  _BYTE v39[80]; // [rsp+E8h] [rbp-50h] BYREF
  int v40; // [rsp+150h] [rbp+18h] BYREF
  __int64 v41; // [rsp+158h] [rbp+20h] BYREF

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 15;
  *(_BYTE *)a1 = 0;
  v4 = a1 + 32;
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 15;
  *(_BYTE *)(a1 + 32) = 0;
  v33 = 1;
  if ( shared::IsValidCrossPlatformAppId(a2, a2) )
  {
    v34 = 0;
    *(_OWORD *)v35 = 0;
    v30 = 0;
    v31 = v35;
    v5 = (*(__int64 (__fastcall **)(shared *, const char **))(*(_QWORD *)a2 + 40LL))(a2, &v30);
    cdp::detail::address_of<ICDPCrossPlatformAppIdEnumerator>::~address_of<ICDPCrossPlatformAppIdEnumerator>(&v30);
    try
    {
      if ( v5 < 0 )
      {
        v30 = "onecoreuap\\windows\\cdp\\shared\\CrossPlatformAppId.h";
        LODWORD(v31) = 219;
        LODWORD(v41) = v5;
        CurrentThreadId = GetCurrentThreadId();
        v32 = CurrentThreadId;
        Log<long &,char const * &,int &,unsigned __int64>(
          CurrentThreadId,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v41,
          (unsigned int)&v30,
          (__int64)&v31,
          (__int64)&v32);
        v7 = cdp::ExceptionStackFromSourceLocationInfo(v36, &v30);
        v10 = cdp::ErrorCodeToString((unsigned int)v5, v8, v9, v7);
        ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v5, v10);
        throw (ConnectedDevices::Exception *)pExceptionObject;
      }
      LOBYTE(v40) = 0;
      v11 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, int *))(*(_QWORD *)v35[0] + 24LL))(v35[0], &v40);
      v12 = v11;
      if ( v11 < 0 )
      {
        v30 = "onecoreuap\\windows\\cdp\\shared\\CrossPlatformAppId.h";
        LODWORD(v31) = 221;
        LODWORD(v41) = v11;
        v13 = GetCurrentThreadId();
        v32 = v13;
        Log<long &,char const * &,int &,unsigned __int64>(
          v13,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v41,
          (unsigned int)&v30,
          (__int64)&v31,
          (__int64)&v32);
        v14 = cdp::ExceptionStackFromSourceLocationInfo(v36, &v30);
        v17 = cdp::ErrorCodeToString(v12, v15, v16, v14);
        ConnectedDevices::Exception::Exception(v38, v12, v17);
        throw (ConnectedDevices::Exception *)v38;
      }
      if ( !(_BYTE)v40 )
      {
        v30 = "onecoreuap\\windows\\cdp\\shared\\CrossPlatformAppId.h";
        LODWORD(v31) = 222;
        LODWORD(v41) = -2147418113;
        v32 = GetCurrentThreadId();
        Log<long &,char const * &,int &,unsigned __int64>(
          v18,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v41,
          (unsigned int)&v30,
          (__int64)&v31,
          (__int64)&v32);
        v19 = cdp::ExceptionStackFromSourceLocationInfo(v36, &v30);
        v22 = cdp::ErrorCodeToString(2147549183LL, v20, v21, v19);
        ConnectedDevices::Exception::Exception(v39, 2147549183LL, v22);
        throw (ConnectedDevices::Exception *)v39;
      }
      if ( (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v35[0] + 40LL))(v35[0]) )
      {
        v23 = (const char *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v35[0] + 40LL))(v35[0]);
        v24 = qword_1803986E0;
      }
      else
      {
        v24 = qword_1803986E0;
        v23 = qword_1803986E0;
      }
      std::string::assign(a1, v23);
      if ( (*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v35[0] + 48LL))(v35[0]) )
        v24 = (const char *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v35[0] + 48LL))(v35[0]);
      std::string::assign(v4, v24);
      if ( v35[1] )
        std::_Ref_count_base::_Decref(v35[1]);
    }
    catch ( ... )
    {
      LODWORD(v26) = GetCurrentThreadId();
      v41 = v26;
      v40 = 226;
      cdp::CatchAllToHR<char const (&)[51],int,unsigned __int64>(
        (unsigned int)v29 + 76,
        v27,
        v28,
        (unsigned int)v29 + 336,
        (__int64)&v41);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180181aa0  mov     [rsp+arg_0], rcx
0x180181aa5  push    rbx
0x180181aa6  push    rsi
0x180181aa7  push    rdi
0x180181aa8  sub     rsp, 120h
0x180181aaf  mov     rdi, rdx
0x180181ab2  mov     rbx, rcx
0x180181ab5  mov     [rsp+138h+var_F0], 0
0x180181abd  xorps   xmm0, xmm0
0x180181ac0  movups  xmmword ptr [rcx], xmm0
0x180181ac3  mov     qword ptr [rcx+10h], 0
0x180181acb  mov     eax, 0Fh
0x180181ad0  mov     [rcx+18h], rax
0x180181ad4  mov     byte ptr [rcx], 0
0x180181ad7  lea     rsi, [rcx+20h]
0x180181adb  movups  xmmword ptr [rsi], xmm0
0x180181ade  mov     qword ptr [rsi+10h], 0
0x180181ae6  mov     [rsi+18h], rax
0x180181aea  mov     byte ptr [rsi], 0
0x180181aed  mov     [rsp+138h+var_F0], 1
0x180181af5  mov     rcx, rdx; this
0x180181af8  call    ?IsValidCrossPlatformAppId@shared@@YA_NPEBVICDPCrossPlatformAppId@@@Z; shared::IsValidCrossPlatformAppId(ICDPCrossPlatformAppId const *)
0x180181afd  test    al, al
0x180181aff  jz      loc_180181DDD
0x180181b05  mov     [rsp+138h+var_EC], 0
0x180181b0d  xorps   xmm0, xmm0
0x180181b10  movdqu  xmmword ptr [rsp+138h+var_E8], xmm0
0x180181b16  mov     [rsp+138h+var_108], 0
0x180181b1f  lea     rax, [rsp+138h+var_E8]
0x180181b24  mov     [rsp+138h+var_100], rax
0x180181b29  mov     rax, [rdi]
0x180181b2c  lea     rdx, [rsp+138h+var_108]
0x180181b31  mov     rcx, rdi
0x180181b34  mov     rax, [rax+28h]
0x180181b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180181b3d  mov     edi, eax
0x180181b3f  lea     rcx, [rsp+138h+var_108]
0x180181b44  call    ??1?$address_of@VICDPCrossPlatformAppIdEnumerator@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPCrossPlatformAppIdEnumerator>::~address_of<ICDPCrossPlatformAppIdEnumerator>(void)
0x180181b49  test    edi, edi
0x180181b4b  jns     loc_180181BE0
0x180181b51  lea     rcx, aOnecoreuapWind_21; "onecoreuap\\windows\\cdp\\shared\\Cross"...
0x180181b58  mov     [rsp+138h+var_108], rcx
0x180181b5d  mov     dword ptr [rsp+138h+var_100], 0DBh
0x180181b65  mov     dword ptr [rsp+138h+arg_18], edi
0x180181b6c  call    cs:__imp_GetCurrentThreadId
0x180181b72  mov     ecx, eax
0x180181b74  mov     [rsp+138h+var_F8], rcx
0x180181b79  lea     rax, [rsp+138h+var_F8]
0x180181b7e  mov     [rsp+138h+var_110], rax
0x180181b83  lea     rax, [rsp+138h+var_100]
0x180181b88  mov     [rsp+138h+var_118], rax
0x180181b8d  lea     r9, [rsp+138h+var_108]
0x180181b92  lea     r8, [rsp+138h+arg_18]
0x180181b9a  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180181ba1  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180181ba6  lea     rdx, [rsp+138h+var_108]
0x180181bab  lea     rcx, [rsp+138h+var_D8]
0x180181bb0  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180181bb5  mov     r9, rax
0x180181bb8  mov     ecx, edi
0x180181bba  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180181bbf  mov     r8, rax
0x180181bc2  mov     edx, edi
0x180181bc4  lea     rcx, [rsp+138h+pExceptionObject]
0x180181bc9  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180181bce  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180181bd5  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x180181bda  call    _CxxThrowException_0
0x180181be0  mov     byte ptr [rsp+138h+arg_10], 0
0x180181be8  mov     rcx, [rsp+138h+var_E8]
0x180181bed  mov     rax, [rcx]
0x180181bf0  lea     rdx, [rsp+138h+arg_10]
0x180181bf8  mov     rax, [rax+18h]
0x180181bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180181c01  mov     edi, eax
0x180181c03  test    eax, eax
0x180181c05  jns     loc_180181CA0
0x180181c0b  lea     rcx, aOnecoreuapWind_21; "onecoreuap\\windows\\cdp\\shared\\Cross"...
0x180181c12  mov     [rsp+138h+var_108], rcx
0x180181c17  mov     dword ptr [rsp+138h+var_100], 0DDh
0x180181c1f  mov     dword ptr [rsp+138h+arg_18], eax
0x180181c26  call    cs:__imp_GetCurrentThreadId
0x180181c2c  mov     ecx, eax
0x180181c2e  mov     [rsp+138h+var_F8], rcx
0x180181c33  lea     rax, [rsp+138h+var_F8]
0x180181c38  mov     [rsp+138h+var_110], rax
0x180181c3d  lea     rax, [rsp+138h+var_100]
0x180181c42  mov     [rsp+138h+var_118], rax
0x180181c47  lea     r9, [rsp+138h+var_108]
0x180181c4c  lea     r8, [rsp+138h+arg_18]
0x180181c54  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180181c5b  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180181c60  lea     rdx, [rsp+138h+var_108]
0x180181c65  lea     rcx, [rsp+138h+var_D8]
0x180181c6a  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180181c6f  mov     r9, rax
0x180181c72  mov     ecx, edi
0x180181c74  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180181c79  mov     r8, rax
0x180181c7c  mov     edx, edi
0x180181c7e  lea     rcx, [rsp+138h+var_88]
0x180181c86  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180181c8b  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180181c92  lea     rcx, [rsp+138h+var_88]; pExceptionObject
0x180181c9a  call    _CxxThrowException_0
0x180181ca0  cmp     byte ptr [rsp+138h+arg_10], 0
0x180181ca8  jnz     loc_180181D48
0x180181cae  lea     rcx, aOnecoreuapWind_21; "onecoreuap\\windows\\cdp\\shared\\Cross"...
0x180181cb5  mov     [rsp+138h+var_108], rcx
0x180181cba  mov     dword ptr [rsp+138h+var_100], 0DEh
0x180181cc2  mov     ebx, 8000FFFFh
0x180181cc7  mov     dword ptr [rsp+138h+arg_18], ebx
0x180181cce  call    cs:__imp_GetCurrentThreadId
0x180181cd4  mov     eax, eax
0x180181cd6  mov     [rsp+138h+var_F8], rax
0x180181cdb  lea     rax, [rsp+138h+var_F8]
0x180181ce0  mov     [rsp+138h+var_110], rax
0x180181ce5  lea     rax, [rsp+138h+var_100]
0x180181cea  mov     [rsp+138h+var_118], rax
0x180181cef  lea     r9, [rsp+138h+var_108]
0x180181cf4  lea     r8, [rsp+138h+arg_18]
0x180181cfc  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180181d03  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180181d08  lea     rdx, [rsp+138h+var_108]
0x180181d0d  lea     rcx, [rsp+138h+var_D8]
0x180181d12  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180181d17  mov     r9, rax
0x180181d1a  mov     ecx, ebx
0x180181d1c  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180181d21  mov     r8, rax
0x180181d24  mov     edx, ebx
0x180181d26  lea     rcx, [rsp+138h+var_50]
0x180181d2e  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180181d33  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180181d3a  lea     rcx, [rsp+138h+var_50]; pExceptionObject
0x180181d42  call    _CxxThrowException_0
0x180181d48  mov     rcx, [rsp+138h+var_E8]
0x180181d4d  mov     rax, [rcx]
0x180181d50  mov     rax, [rax+28h]
0x180181d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180181d59  test    rax, rax
0x180181d5c  jz      short loc_180181D78
0x180181d5e  mov     rcx, [rsp+138h+var_E8]
0x180181d63  mov     rax, [rcx]
0x180181d66  mov     rax, [rax+28h]
0x180181d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180181d6f  lea     rdi, qword_1803986E0
0x180181d76  jmp     short loc_180181D82
0x180181d78  lea     rdi, qword_1803986E0
0x180181d7f  mov     rax, rdi
0x180181d82  mov     rdx, rax
0x180181d85  mov     rcx, rbx
0x180181d88  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x180181d8d  mov     rcx, [rsp+138h+var_E8]
0x180181d92  mov     rax, [rcx]
0x180181d95  mov     rax, [rax+30h]
0x180181d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180181d9e  test    rax, rax
0x180181da1  jz      short loc_180181DB7
0x180181da3  mov     rcx, [rsp+138h+var_E8]
0x180181da8  mov     rax, [rcx]
0x180181dab  mov     rax, [rax+30h]
0x180181daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180181db4  mov     rdi, rax
0x180181db7  mov     rdx, rdi
0x180181dba  mov     rcx, rsi
0x180181dbd  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x180181dc2  nop
0x180181dc3  mov     rcx, [rsp+138h+var_E8+8]; this
0x180181dc8  test    rcx, rcx
0x180181dcb  jz      short loc_180181DD3
0x180181dcd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180181dd2  nop
0x180181dd3  jmp     short loc_180181DDD
0x180181dd5  mov     rbx, [rsp+138h+arg_0]
0x180181ddd  mov     rax, rbx
0x180181de0  add     rsp, 120h
0x180181de7  pop     rdi
0x180181de8  pop     rsi
0x180181de9  pop     rbx
0x180181dea  retn
```
