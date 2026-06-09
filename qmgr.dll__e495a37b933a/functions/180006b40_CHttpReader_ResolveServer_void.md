# CHttpReader::ResolveServer(void)

- ea: `0x180006b40`
- end: `0x1800073e8`
- name: `?ResolveServer@CHttpReader@@IEAAXXZ`
- size: `2216`
- prototype: `void __fastcall(CHttpReader *__hidden this)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180072eb0`

## callees

- `0x1800066f0`
- `0x180006a78`
- `0x180006b40`
- `0x18000815c`
- `0x180008b70`
- `0x180008cc0`
- `0x18000db20`
- `0x18000e370`
- `0x180014310`
- `0x1800377b8`
- `0x180054ea0`
- `0x1800554b0`
- `0x18005579c`
- `0x180081adc`
- `0x18009c97c`
- `0x18009d024`
- `0x18009e9c8`
- `0x1800a1114`
- `0x1800a3444`
- `0x1800f6ee8`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006baa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006ccf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006d8c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800072ee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006baa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006ccf`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006d8c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800072ee`
- `ntdll!RtlAdjustPrivilege` at `0x180007002`
- `ntdll!RtlAdjustPrivilege` at `0x1800070aa`
- `ntdll!RtlAdjustPrivilege` at `0x180007002`
- `ntdll!RtlAdjustPrivilege` at `0x1800070aa`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180006e8d`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180006e8d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800070f8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800070f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006faa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000710c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007114`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007230`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000723a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007242`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006faa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007102`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000710c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007114`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007230`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000723a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007242`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180007397`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180007397`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180006e31`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180006e31`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006f8e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180006f8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall CHttpReader::ResolveServer(CHttpReader *this)
{
  LPVOID v2; // rax
  __int64 v3; // rcx
  __int64 v4; // r8
  void (__fastcall ***v5)(_QWORD, _QWORD); // rcx
  void **v6; // rsi
  char v7; // r12
  struct IHttpInterface *v8; // r13
  PROXY_SETTINGS_CONTAINER *v9; // rax
  _QWORD *v10; // rbx
  _DWORD *v11; // rax
  signed int LastError; // eax
  const WCHAR *v13; // rbx
  EVENT_LOG *v14; // rcx
  void **v15; // rax
  void *v16; // rcx
  _WORD *v17; // rbx
  unsigned int v18; // eax
  NTSTATUS v19; // eax
  int v20; // eax
  HANDLE *v21; // rbx
  NTSTATUS v22; // eax
  int v23; // eax
  NTSTATUS v24; // eax
  int v25; // eax
  unsigned int v26; // eax
  struct IHttpSession *Session; // rax
  int v28; // eax
  void *v29; // r8
  unsigned int v30; // eax
  unsigned __int16 *v31; // rsi
  const unsigned __int16 *v32; // rcx
  __int64 v33; // rbx
  PROXY_SETTINGS_CONTAINER *v34; // rax
  PROXY_SETTINGS_CONTAINER *v35; // rax
  void **v36; // [rsp+40h] [rbp-99h] BYREF
  __int128 v37; // [rsp+48h] [rbp-91h]
  int v38; // [rsp+58h] [rbp-81h]
  int v39; // [rsp+5Ch] [rbp-7Dh]
  int v40; // [rsp+60h] [rbp-79h]
  void **pExceptionObject; // [rsp+A0h] [rbp-39h] BYREF
  __int128 v42; // [rsp+A8h] [rbp-31h]
  __int64 v43; // [rsp+B8h] [rbp-21h]
  _DWORD *v44; // [rsp+C0h] [rbp-19h]
  __int64 v45; // [rsp+C8h] [rbp-11h]
  __int64 *v46; // [rsp+D0h] [rbp-9h]
  LPVOID OldValue; // [rsp+148h] [rbp+6Fh] BYREF
  HANDLE *v48; // [rsp+150h] [rbp+77h] BYREF

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids,
      *((_QWORD *)this + 13) + 12LL);
  v2 = HeapAlloc(hBitsHeap, 8u, 0x470u);
  if ( !v2 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 1136);
    v42 = 0;
    pExceptionObject = &ComError::`vftable';
    v43 = 2147942414LL;
    LODWORD(v44) = 1;
    throw (ComError *)&pExceptionObject;
  }
  OldValue = v2;
  v3 = 263312;
  if ( (*((_BYTE *)this + 263320) & 2) == 0 )
    v3 = 263304;
  v4 = URL_INFO::URL_INFO(
         (__int64)v2,
         (__int64)this + 104,
         (__int64)this + 676,
         *((_QWORD *)this + 99),
         (__int64)this + v3,
         *((_DWORD *)this + 65831),
         *((_BYTE *)this + 263328),
         0);
  *((_QWORD *)this + 80) = v4;
  v5 = (void (__fastcall ***)(_QWORD, _QWORD))*((_QWORD *)this + 33);
  if ( v5 )
    (**v5)(v5, *(_QWORD *)(v4 + 1120));
  v6 = (void **)*((_QWORD *)this + 80);
  v7 = *((_BYTE *)this + 263099);
  v8 = (struct IHttpInterface *)*((_QWORD *)this + 82);
  if ( !v6[8] )
  {
    v9 = (PROXY_SETTINGS_CONTAINER *)HeapAlloc(hBitsHeap, 8u, 0x90u);
    if ( !v9 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 144);
      v42 = 0;
      pExceptionObject = &ComError::`vftable';
      v43 = 2147942414LL;
      LODWORD(v44) = 1;
      throw (ComError *)&pExceptionObject;
    }
    OldValue = v9;
    v6[8] = PROXY_SETTINGS_CONTAINER::PROXY_SETTINGS_CONTAINER(v9, (__int64)(v6 + 5), (__int64 *)v6[6], (__int64)v6[9]);
  }
  v10 = v6[6];
  CSaveThreadToken::CSaveThreadToken((CSaveThreadToken *)&pExceptionObject);
  LOBYTE(v42) = 0;
  *((_QWORD *)&v42 + 1) = *v10;
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v42 + 1) + 8LL));
  v43 = 0;
  v11 = HeapAlloc(hBitsHeap, 8u, 4u);
  if ( !v11 )
  {
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 4);
    v37 = 0;
    v36 = &ComError::`vftable';
    v38 = -2147024882;
    v39 = 0;
    v40 = 1;
    throw (ComError *)&v36;
  }
  *v11 = 1;
  v44 = v11;
  v45 = 0;
  _InterlockedIncrement(&dword_180145058);
  v46 = &GenericStringHandle<unsigned short>::s_EmptyString;
  if ( !(_BYTE)v42 )
  {
    if ( !ImpersonateLoggedOnUser(**((HANDLE **)&v42 + 1)) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v37 = 0;
      v36 = &ComError::`vftable';
      v38 = LastError;
      v39 = 0;
      v40 = 1;
      throw (ComError *)&v36;
    }
    LOBYTE(v42) = 1;
  }
  v13 = (const WCHAR *)v6[140];
  if ( !(unsigned int)RtlGetCurrentServiceSessionId() )
  {
    v15 = v6 + 4;
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_16528e1573683c34a7ff296cba86f7f8_Traceguids, v13);
      v15 = v6 + 4;
    }
    v16 = *v15;
    *v15 = 0;
    if ( v16 )
      operator delete(v16, 2u);
    EidAsyncHelper::StartGetEidAsync((LPCRITICAL_SECTION)((char *)this + 263136), v13);
    EidAsyncHelper::WaitForEnterpriseId((LPCRITICAL_SECTION)((char *)this + 263136));
    goto LABEL_41;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_16528e1573683c34a7ff296cba86f7f8_Traceguids);
LABEL_41:
    v14 = WPP_GLOBAL_Control;
  }
  v17 = v6[4];
  if ( v14 != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)v14 + 2), 26, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids, v6[4]);
  if ( v17 && *v17 )
  {
    CopyThreadToken(&v48);
    if ( !RevertToSelf() )
    {
      if ( (int)GetLastError() > 0 )
        v18 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v18 = GetLastError();
      v37 = 0;
      v36 = &ComError::`vftable';
      v38 = v18;
      v39 = 584;
      v40 = 1;
      throw (ComError *)&v36;
    }
    LOBYTE(OldValue) = 0;
    v19 = RtlAdjustPrivilege(7u, 1u, 0, (PBOOLEAN)&OldValue);
    v20 = NtStatusToHResult(v19);
    if ( v20 < 0 )
    {
      v37 = 0;
      v36 = &ComError::`vftable';
      v38 = v20;
      v39 = 588;
      v40 = 1;
      throw (ComError *)&v36;
    }
    v21 = v48;
    v22 = SrpSetTokenEnterpriseExempt(*v48);
    v23 = NtStatusToHResult(v22);
    if ( v23 < 0 )
    {
      v37 = 0;
      v36 = &ComError::`vftable';
      v38 = v23;
      v39 = 590;
      v40 = 1;
      throw (ComError *)&v36;
    }
    v24 = RtlAdjustPrivilege(7u, (BOOLEAN)OldValue, 0, (PBOOLEAN)&OldValue);
    v25 = NtStatusToHResult(v24);
    if ( v25 < 0 )
    {
      v37 = 0;
      v36 = &ComError::`vftable';
      v38 = v25;
      v39 = 593;
      v40 = 1;
      throw (ComError *)&v36;
    }
    if ( !SetThreadToken(0, *v21) )
    {
      if ( (int)GetLastError() > 0 )
        v26 = (unsigned __int16)GetLastError() | 0x80070000;
      else
        v26 = GetLastError();
      v37 = 0;
      v36 = &ComError::`vftable';
      v38 = v26;
      v39 = 597;
      v40 = 1;
      throw (ComError *)&v36;
    }
    TokenHandle::Decrement((TokenHandle *)&v48);
  }
  Session = HttpSessionCache::GetSession(
              v14,
              (CHttpReader *)((char *)this + 676),
              v8,
              (const unsigned __int16 *)v6[4],
              v7);
  *v6 = Session;
  EnablePassport(Session);
  v6[1] = (void *)(*(__int64 (__fastcall **)(void *, void *, _QWORD))(*(_QWORD *)*v6 + 8LL))(
                    *v6,
                    v6[140],
                    *((unsigned __int16 *)v6 + 30));
  CNestedImpersonation::~CNestedImpersonation((CNestedImpersonation *)&pExceptionObject);
  if ( *((_BYTE *)v6 + 18) )
  {
    if ( *(_DWORD *)v6[8] )
    {
      v28 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)*v6 + 24LL))(*v6);
      if ( v28 < 0 )
      {
        v37 = 0;
        v36 = &ComError::`vftable';
        v38 = v28;
        v39 = 5057;
        v40 = 1;
        throw (ComError *)&v36;
      }
    }
  }
  v29 = v6[10];
  if ( v29
    && !(*(unsigned int (__fastcall **)(void *, __int64, void *, __int64))(*(_QWORD *)v6[1] + 16LL))(
          v6[1],
          131,
          v29,
          232) )
  {
    if ( (int)GetLastError() > 0 )
      v30 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v30 = GetLastError();
    v37 = 0;
    v36 = &ComError::`vftable';
    v38 = v30;
    v39 = 5064;
    v40 = 1;
    throw (ComError *)&v36;
  }
  v31 = 0;
  v32 = *(const unsigned __int16 **)(*((_QWORD *)this + 80) + 32LL);
  if ( v32 && *v32 )
    v31 = CopyString(v32, 0xFFFFFFFFFFFFFFFFuLL);
  OldValue = v31;
  (*(void (__fastcall **)(CHttpReader *, unsigned __int16 *))(*(_QWORD *)this + 416LL))(this, v31);
  v33 = *((_QWORD *)this + 80);
  v34 = *(PROXY_SETTINGS_CONTAINER **)(v33 + 64);
  if ( !v34 )
  {
    v35 = (PROXY_SETTINGS_CONTAINER *)HeapAlloc(hBitsHeap, 8u, 0x90u);
    if ( !v35 )
    {
      if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids, 144);
      v37 = 0;
      v36 = &ComError::`vftable';
      v38 = -2147024882;
      v39 = 0;
      v40 = 1;
      throw (ComError *)&v36;
    }
    v48 = (HANDLE *)v35;
    v34 = PROXY_SETTINGS_CONTAINER::PROXY_SETTINGS_CONTAINER(
            v35,
            v33 + 40,
            *(__int64 **)(v33 + 48),
            *(_QWORD *)(v33 + 72));
    *(_QWORD *)(v33 + 64) = v34;
  }
  if ( *(_DWORD *)v34 )
  {
    CHttpReader::RecalcProxyStats(this);
    *((_BYTE *)this + 56) = 1;
    (*(void (__fastcall **)(CHttpReader *))(*(_QWORD *)this + 584LL))(this);
  }
  else
  {
    CHttpReader::IncrementPendingAsyncOpsCount(this);
    SubmitThreadpoolWork(*((PTP_WORK *)this + 81));
  }
  if ( v31 )
    operator delete(v31, 2u);
}

```

## disassembly

```asm
0x180006b40  mov     [rsp-8+arg_0], rbx
0x180006b45  push    rbp
0x180006b46  push    rsi
0x180006b47  push    rdi
0x180006b48  push    r12
0x180006b4a  push    r13
0x180006b4c  push    r14
0x180006b4e  push    r15
0x180006b50  lea     rbp, [rsp-27h]
0x180006b55  sub     rsp, 100h
0x180006b5c  mov     rdi, rcx
0x180006b5f  lea     rbx, WPP_GLOBAL_Control
0x180006b66  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b6d  cmp     rcx, rbx
0x180006b70  jz      short loc_180006B98
0x180006b72  test    dword ptr [rcx+1Ch], 800h
0x180006b79  jz      short loc_180006B98
0x180006b7b  mov     r9, [rdi+68h]
0x180006b7f  add     r9, 0Ch
0x180006b83  mov     edx, 18h
0x180006b88  lea     r8, WPP_f564cdc5d2433e52f9a3270eb457e218_Traceguids
0x180006b8f  mov     rcx, [rcx+10h]
0x180006b93  call    WPP_SF_S
0x180006b98  mov     edx, 8; dwFlags
0x180006b9d  mov     r8d, 470h; dwBytes
0x180006ba3  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x180006baa  call    cs:__imp_HeapAlloc
0x180006bb0  mov     r10, rax
0x180006bb3  test    rax, rax
0x180006bb6  jnz     short loc_180006C1D
0x180006bb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bbf  cmp     rcx, rbx
0x180006bc2  jz      short loc_180006BE5
0x180006bc4  test    byte ptr [rcx+1Ch], 4
0x180006bc8  jz      short loc_180006BE5
0x180006bca  mov     edx, 0Ah
0x180006bcf  mov     r9d, 470h
0x180006bd5  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x180006bdc  mov     rcx, [rcx+10h]
0x180006be0  call    WPP_SF_d
0x180006be5  xorps   xmm0, xmm0
0x180006be8  movups  [rbp+57h+var_88], xmm0
0x180006bec  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180006bf3  mov     [rbp+57h+pExceptionObject], rcx
0x180006bf7  mov     dword ptr [rbp+57h+var_78], 8007000Eh
0x180006bfe  xor     r14d, r14d
0x180006c01  mov     dword ptr [rbp+57h+var_78+4], r14d
0x180006c05  mov     dword ptr [rbp+57h+var_70], 1
0x180006c0c  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180006c13  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180006c17  call    _CxxThrowException_0
0x180006c1d  mov     [rbp+57h+OldValue], r10
0x180006c21  test    byte ptr [rdi+40498h], 2
0x180006c28  mov     ecx, 40490h
0x180006c2d  mov     eax, 40488h
0x180006c32  cmovz   ecx, eax
0x180006c35  add     rcx, rdi
0x180006c38  lea     rdx, [rdi+68h]; int
0x180006c3c  xor     r14d, r14d
0x180006c3f  mov     [rsp+130h+var_F8], r14; unsigned __int16 *
0x180006c44  movzx   eax, byte ptr [rdi+404A0h]
0x180006c4b  mov     [rsp+130h+var_100], al; char
0x180006c4f  mov     eax, [rdi+4049Ch]
0x180006c55  mov     [rsp+130h+var_108], eax; int
0x180006c59  mov     qword ptr [rsp+130h+var_110], rcx; __int64
0x180006c5e  mov     r9, [rdi+318h]; int
0x180006c65  lea     r8, [rdi+2A4h]; int
0x180006c6c  mov     rcx, r10; int
0x180006c6f  call    ??0URL_INFO@@QEAA@AEBV?$GenericStringHandle@G@@AEBUHttpSecurityData@@PEBUPROXY_SETTINGS@@AEBVTokenHandle@@K_NPEBG@Z; URL_INFO::URL_INFO(GenericStringHandle<ushort> const &,HttpSecurityData const &,PROXY_SETTINGS const *,TokenHandle const &,ulong,bool,ushort const *)
0x180006c74  mov     r8, rax
0x180006c77  mov     [rdi+280h], rax
0x180006c7e  mov     rcx, [rdi+108h]
0x180006c85  test    rcx, rcx
0x180006c88  jz      short loc_180006C9C
0x180006c8a  mov     rdx, [rcx]
0x180006c8d  mov     rax, [rdx]
0x180006c90  mov     rdx, [r8+460h]
0x180006c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c9c  mov     rsi, [rdi+280h]
0x180006ca3  movzx   r12d, byte ptr [rdi+403BBh]
0x180006cab  mov     r13, [rdi+290h]
0x180006cb2  cmp     qword ptr [rsi+40h], 0
0x180006cb7  jnz     loc_180006D59
0x180006cbd  mov     edx, 8; dwFlags
0x180006cc2  mov     r8d, 90h; dwBytes
0x180006cc8  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x180006ccf  call    cs:__imp_HeapAlloc
0x180006cd5  test    rax, rax
0x180006cd8  jnz     short loc_180006D3C
0x180006cda  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ce1  cmp     rcx, rbx
0x180006ce4  jz      short loc_180006D07
0x180006ce6  test    byte ptr [rcx+1Ch], 4
0x180006cea  jz      short loc_180006D07
0x180006cec  mov     edx, 0Ah
0x180006cf1  mov     r9d, 90h
0x180006cf7  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x180006cfe  mov     rcx, [rcx+10h]
0x180006d02  call    WPP_SF_d
0x180006d07  xorps   xmm0, xmm0
0x180006d0a  movups  [rbp+57h+var_88], xmm0
0x180006d0e  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180006d15  mov     [rbp+57h+pExceptionObject], rcx
0x180006d19  mov     dword ptr [rbp+57h+var_78], 8007000Eh
0x180006d20  mov     dword ptr [rbp+57h+var_78+4], r14d
0x180006d24  mov     dword ptr [rbp+57h+var_70], 1
0x180006d2b  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180006d32  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180006d36  call    _CxxThrowException_0
0x180006d3c  mov     [rbp+57h+OldValue], rax
0x180006d40  lea     rdx, [rsi+28h]
0x180006d44  mov     r9, [rsi+48h]
0x180006d48  mov     r8, [rsi+30h]
0x180006d4c  mov     rcx, rax; this
0x180006d4f  call    ??0PROXY_SETTINGS_CONTAINER@@QEAA@AEBV?$GenericStringHandle@G@@AEBVTokenHandle@@PEBUPROXY_SETTINGS@@@Z; PROXY_SETTINGS_CONTAINER::PROXY_SETTINGS_CONTAINER(GenericStringHandle<ushort> const &,TokenHandle const &,PROXY_SETTINGS const *)
0x180006d54  nop
0x180006d55  mov     [rsi+40h], rax
0x180006d59  mov     rbx, [rsi+30h]
0x180006d5d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180006d61  call    ??0CSaveThreadToken@@QEAA@XZ; CSaveThreadToken::CSaveThreadToken(void)
0x180006d66  nop
0x180006d67  mov     byte ptr [rbp+57h+var_88], 0
0x180006d6b  mov     rax, [rbx]
0x180006d6e  mov     qword ptr [rbp+57h+var_88+8], rax
0x180006d72  lock inc dword ptr [rax+8]
0x180006d76  mov     [rbp+57h+var_78], r14
0x180006d7a  mov     edx, 8; dwFlags
0x180006d7f  mov     r8d, 4; dwBytes
0x180006d85  mov     rcx, cs:?hBitsHeap@@3PEAXEA; hHeap
0x180006d8c  call    cs:__imp_HeapAlloc
0x180006d92  test    rax, rax
0x180006d95  jnz     short loc_180006E04
0x180006d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d9e  lea     rax, WPP_GLOBAL_Control
0x180006da5  cmp     rcx, rax
0x180006da8  jz      short loc_180006DCB
0x180006daa  test    byte ptr [rcx+1Ch], 4
0x180006dae  jz      short loc_180006DCB
0x180006db0  mov     edx, 0Ah
0x180006db5  mov     r9d, 4
0x180006dbb  lea     r8, WPP_deb7ee1652453f20adcd23cf0ee1001c_Traceguids
0x180006dc2  mov     rcx, [rcx+10h]
0x180006dc6  call    WPP_SF_d
0x180006dcb  xorps   xmm0, xmm0
0x180006dce  movups  [rsp+130h+var_E8], xmm0
0x180006dd3  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180006dda  mov     [rsp+130h+var_F0], rcx
0x180006ddf  mov     [rsp+130h+var_D8], 8007000Eh
0x180006de7  mov     [rbp+57h+var_D4], r14d
0x180006deb  mov     [rbp+57h+var_D0], 1
0x180006df2  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180006df9  lea     rcx, [rsp+130h+var_F0]; pExceptionObject
0x180006dfe  call    _CxxThrowException_0
0x180006e04  mov     dword ptr [rax], 1
0x180006e0a  mov     [rbp+57h+var_70], rax
0x180006e0e  mov     [rbp+57h+var_68], r14
0x180006e12  lock inc cs:dword_180145058
0x180006e19  lea     rax, ?s_EmptyString@?$GenericStringHandle@G@@0UStringData@1@A; GenericStringHandle<ushort>::StringData GenericStringHandle<ushort>::s_EmptyString
0x180006e20  mov     [rbp+57h+var_60], rax
0x180006e24  cmp     byte ptr [rbp+57h+var_88], 0
0x180006e28  jnz     short loc_180006E86
0x180006e2a  mov     rcx, qword ptr [rbp+57h+var_88+8]
0x180006e2e  mov     rcx, [rcx]; hToken
0x180006e31  call    cs:__imp_ImpersonateLoggedOnUser
0x180006e37  test    eax, eax
0x180006e39  jnz     short loc_180006E82
0x180006e3b  call    cs:__imp_GetLastError
0x180006e41  test    eax, eax
0x180006e43  jle     short loc_180006E4D
0x180006e45  movzx   eax, ax
0x180006e48  or      eax, 80070000h
0x180006e4d  xorps   xmm0, xmm0
0x180006e50  movups  [rsp+130h+var_E8], xmm0
0x180006e55  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180006e5c  mov     [rsp+130h+var_F0], rcx
0x180006e61  mov     [rsp+130h+var_D8], eax
0x180006e65  mov     [rbp+57h+var_D4], r14d
0x180006e69  mov     [rbp+57h+var_D0], 1
0x180006e70  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180006e77  lea     rcx, [rsp+130h+var_F0]; pExceptionObject
0x180006e7c  call    _CxxThrowException_0
0x180006e82  mov     byte ptr [rbp+57h+var_88], 1
0x180006e86  mov     rbx, [rsi+460h]
0x180006e8d  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180006e93  test    eax, eax
0x180006e95  jz      short loc_180006ECF
0x180006e97  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e9e  lea     rbx, WPP_GLOBAL_Control
0x180006ea5  cmp     rcx, rbx
0x180006ea8  jz      loc_180006F43
0x180006eae  test    byte ptr [rcx+1Ch], 2
0x180006eb2  jz      loc_180006F43
0x180006eb8  mov     edx, 0Ah
0x180006ebd  lea     r8, WPP_16528e1573683c34a7ff296cba86f7f8_Traceguids
0x180006ec4  mov     rcx, [rcx+10h]
0x180006ec8  call    WPP_SF_
0x180006ecd  jmp     short loc_180006F3C
0x180006ecf  lea     rax, [rsi+20h]
0x180006ed3  mov     rcx, cs:WPP_GLOBAL_Control
0x180006eda  lea     rdx, WPP_GLOBAL_Control
0x180006ee1  cmp     rcx, rdx
0x180006ee4  jz      short loc_180006F08
0x180006ee6  test    byte ptr [rcx+1Ch], 1
0x180006eea  jz      short loc_180006F08
0x180006eec  mov     edx, 0Bh
0x180006ef1  mov     r9, rbx
0x180006ef4  lea     r8, WPP_16528e1573683c34a7ff296cba86f7f8_Traceguids
0x180006efb  mov     rcx, [rcx+10h]
0x180006eff  call    WPP_SF_S
0x180006f04  lea     rax, [rsi+20h]
0x180006f08  mov     rcx, [rax]; void *
0x180006f0b  mov     [rax], r14
0x180006f0e  test    rcx, rcx
0x180006f11  jz      short loc_180006F1D
0x180006f13  mov     edx, 2; unsigned __int64
0x180006f18  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006f1d  mov     rdx, rbx; wszServerName
0x180006f20  lea     rcx, [rdi+403E0h]; lpCriticalSection
0x180006f27  call    ?StartGetEidAsync@EidAsyncHelper@@QEAA_NPEBG@Z; EidAsyncHelper::StartGetEidAsync(ushort const *)
0x180006f2c  lea     rdx, [rsi+20h]
0x180006f30  lea     rcx, [rdi+403E0h]; lpCriticalSection
0x180006f37  call    ?WaitForEnterpriseId@EidAsyncHelper@@QEAA_NAEAV?$unique_ptr@GU?$default_delete@G@std@@@std@@@Z; EidAsyncHelper::WaitForEnterpriseId(std::unique_ptr<ushort> &)
0x180006f3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f43  mov     rbx, [rsi+20h]
0x180006f47  lea     rax, WPP_GLOBAL_Control
0x180006f4e  cmp     rcx, rax
0x180006f51  jz      short loc_180006F71
0x180006f53  test    byte ptr [rcx+1Ch], 1
0x180006f57  jz      short loc_180006F71
0x180006f59  mov     edx, 1Ah
0x180006f5e  mov     r9, rbx
0x180006f61  lea     r8, WPP_b9000fab88dc3f5ae282b07efafe8d39_Traceguids
0x180006f68  mov     rcx, [rcx+10h]
0x180006f6c  call    WPP_SF_S
0x180006f71  test    rbx, rbx
0x180006f74  jz      loc_180007163
0x180006f7a  cmp     word ptr [rbx], 0
0x180006f7e  jz      loc_180007163
0x180006f84  lea     rcx, [rbp+57h+arg_10]
0x180006f88  call    ?CopyThreadToken@@YA?AVTokenHandle@@XZ; CopyThreadToken(void)
0x180006f8d  nop
0x180006f8e  call    cs:__imp_RevertToSelf
0x180006f94  test    eax, eax
0x180006f96  jnz     short loc_180006FF0
0x180006f98  call    cs:__imp_GetLastError
0x180006f9e  test    eax, eax
0x180006fa0  jg      short loc_180006FAA
0x180006fa2  call    cs:__imp_GetLastError
0x180006fa8  jmp     short loc_180006FB8
0x180006faa  call    cs:__imp_GetLastError
0x180006fb0  movzx   eax, ax
0x180006fb3  or      eax, 80070000h
0x180006fb8  xorps   xmm0, xmm0
0x180006fbb  movups  [rsp+130h+var_E8], xmm0
0x180006fc0  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180006fc7  mov     [rsp+130h+var_F0], rcx
0x180006fcc  mov     [rsp+130h+var_D8], eax
0x180006fd0  mov     [rbp+57h+var_D4], 248h
0x180006fd7  mov     [rbp+57h+var_D0], 1
0x180006fde  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180006fe5  lea     rcx, [rsp+130h+var_F0]; pExceptionObject
0x180006fea  call    _CxxThrowException_0
0x180006ff0  mov     byte ptr [rbp+57h+OldValue], 0
0x180006ff4  lea     r9, [rbp+57h+OldValue]; OldValue
0x180006ff8  xor     r8d, r8d; ForThread
0x180006ffb  mov     dl, 1; NewValue
0x180006ffd  mov     ecx, 7; Privilege
0x180007002  call    cs:__imp_RtlAdjustPrivilege
0x180007008  mov     ecx, eax; Status
0x18000700a  call    ?NtStatusToHResult@@YAJJ@Z; NtStatusToHResult(long)
0x18000700f  test    eax, eax
0x180007011  jns     short loc_18000704B
0x180007013  xorps   xmm0, xmm0
0x180007016  movups  [rsp+130h+var_E8], xmm0
0x18000701b  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180007022  mov     [rsp+130h+var_F0], rcx
0x180007027  mov     [rsp+130h+var_D8], eax
0x18000702b  mov     [rbp+57h+var_D4], 24Ch
0x180007032  mov     [rbp+57h+var_D0], 1
0x180007039  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180007040  lea     rcx, [rsp+130h+var_F0]; pExceptionObject
0x180007045  call    _CxxThrowException_0
0x18000704b  mov     rbx, [rbp+57h+arg_10]
0x18000704f  mov     rcx, [rbx]; TokenHandle
0x180007052  call    SrpSetTokenEnterpriseExempt
0x180007057  mov     ecx, eax; Status
0x180007059  call    ?NtStatusToHResult@@YAJJ@Z; NtStatusToHResult(long)
0x18000705e  test    eax, eax
0x180007060  jns     short loc_18000709A
0x180007062  xorps   xmm0, xmm0
0x180007065  movups  [rsp+130h+var_E8], xmm0
0x18000706a  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180007071  mov     [rsp+130h+var_F0], rcx
0x180007076  mov     [rsp+130h+var_D8], eax
0x18000707a  mov     [rbp+57h+var_D4], 24Eh
0x180007081  mov     [rbp+57h+var_D0], 1
0x180007088  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18000708f  lea     rcx, [rsp+130h+var_F0]; pExceptionObject
0x180007094  call    _CxxThrowException_0
0x18000709a  lea     r9, [rbp+57h+OldValue]; OldValue
  ... truncated ...
```
