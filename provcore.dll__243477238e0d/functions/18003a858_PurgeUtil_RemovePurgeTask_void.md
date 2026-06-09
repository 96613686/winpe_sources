# PurgeUtil::RemovePurgeTask(void)

- ea: `0x18003a858`
- end: `0x18003abb0`
- name: `?RemovePurgeTask@PurgeUtil@@YAXXZ`
- size: `856`
- prototype: `void __fastcall(PurgeUtil *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180037bb4`

## callees

- `0x180002790`
- `0x180008388`
- `0x18000b1e4`
- `0x18000b2f4`
- `0x18000d114`
- `0x180010c34`
- `0x180011cfc`
- `0x180012748`
- `0x180012770`
- `0x180039b0c`
- `0x18003a858`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003a9a0`
- `OLEAUT32!__imp_VariantInit` at `0x18003a9a0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003a93e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003a93e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall PurgeUtil::RemovePurgeTask(PurgeUtil *this)
{
  int v1; // eax
  HRESULT Instance; // eax
  WPP_PROJECT_CONTROL_BLOCK *v3; // rcx
  unsigned __int16 v4; // dx
  ITaskService *p; // rsi
  HRESULT (__fastcall *GetFolder)(ITaskService *, wchar_t *, ITaskFolder **); // r14
  wchar_t **v7; // rax
  wchar_t *v8; // rdx
  int v9; // esi
  int v10; // eax
  PurgeUtil::RemovePurgeTask::__l2::<lambda_1> f; // [rsp+30h] [rbp-D0h] BYREF
  tagVARIANT v12; // [rsp+40h] [rbp-C0h] BYREF
  tagVARIANT v13; // [rsp+60h] [rbp-A0h] BYREF
  tagVARIANT v14; // [rsp+80h] [rbp-80h] BYREF
  tagVARIANT v15; // [rsp+A0h] [rbp-60h] BYREF
  ATL::CComPtr<ITaskService> spTaskService; // [rsp+C0h] [rbp-40h] BYREF
  ATL::CComPtr<ITaskFolder> spFolder; // [rsp+C8h] [rbp-38h] BYREF
  tagVARIANT vtEmpty; // [rsp+D0h] [rbp-30h] BYREF
  std::wstring userSid; // [rsp+E8h] [rbp-18h] BYREF
  std::wstring taskPath; // [rsp+108h] [rbp+8h] BYREF

  userSid._Mypair._Myval2._Bx = 0;
  *(__m128i *)&userSid._Mypair._Myval2._Mysize = _mm_load_si128((const __m128i *)&_xmm);
  userSid._Mypair._Myval2._Bx._Buf[0] = 0;
  f.userSid = &userSid;
  v1 = ExecuteAndConvertAnyException__PurgeUtil::RemovePurgeTask_::_2_::_lambda_1___(&f);
  if ( v1 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x12u, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids);
    }
    spTaskService.p = 0;
    Instance = CoCreateInstance(
                 &CLSID_TaskScheduler,
                 0,
                 0x17u,
                 &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85,
                 (LPVOID *)&spTaskService.p);
    if ( Instance >= 0 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x14u, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids);
      }
      memset(&vtEmpty, 0, sizeof(vtEmpty));
      VariantInit(&vtEmpty);
      v12 = vtEmpty;
      v13 = vtEmpty;
      v14 = vtEmpty;
      v15 = vtEmpty;
      Instance = ((__int64 (__fastcall *)(ITaskService *, tagVARIANT *, tagVARIANT *, tagVARIANT *, tagVARIANT *))spTaskService.p->Connect)(
                   spTaskService.p,
                   &v15,
                   &v14,
                   &v13,
                   &v12);
      if ( Instance >= 0 )
      {
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x16u, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids);
        }
        spFolder.p = 0;
        p = spTaskService.p;
        GetFolder = spTaskService.p->GetFolder;
        _bstr_t::_bstr_t((_bstr_t *)&f, L"\\");
        v8 = *v7;
        if ( *v7 )
          v8 = *(wchar_t **)v8;
        v9 = GetFolder(p, v8, &spFolder.p);
        _bstr_t::_Free((_bstr_t *)&f);
        if ( v9 >= 0 )
        {
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x18u, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids);
          }
          std::operator+<unsigned short>(&taskPath, L"Microsoft\\Windows\\WCM\\Provisioning\\Purge.", &userSid);
          v10 = DeletePurgeTask(spFolder.p, &taskPath);
          if ( v10 >= 0 )
          {
            if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Au, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids);
            }
          }
          else if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
                 && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x19u, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids, v10);
          }
          std::wstring::_Tidy_deallocate(&taskPath);
        }
        else if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
               && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x17u, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids, v9);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spFolder);
        goto LABEL_41;
      }
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->ReserveSpace[28] & 4) == 0 )
      {
LABEL_41:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spTaskService);
        goto LABEL_42;
      }
      v4 = 21;
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->ReserveSpace[28] & 4) == 0 )
      {
        goto LABEL_41;
      }
      v4 = 19;
    }
    WPP_SF_d(v3->Control.Logger, v4, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids, Instance);
    goto LABEL_41;
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x11u, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids, v1);
  }
LABEL_42:
  std::wstring::_Tidy_deallocate(&userSid);
}

```

## disassembly

```asm
0x18003a858  push    rbp
0x18003a85a  push    rbx
0x18003a85b  push    rsi
0x18003a85c  push    rdi
0x18003a85d  push    r14
0x18003a85f  lea     rbp, [rsp-30h]
0x18003a864  sub     rsp, 130h
0x18003a86b  mov     rax, cs:__security_cookie
0x18003a872  xor     rax, rsp
0x18003a875  mov     [rbp+50h+var_28], rax
0x18003a879  xorps   xmm0, xmm0
0x18003a87c  movups  xmmword ptr [rbp+50h+userSid._Mypair._Myval2._Bx], xmm0
0x18003a880  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003a888  movdqu  xmmword ptr [rbp+50h+userSid._Mypair._Myval2._Mysize], xmm1
0x18003a88d  xor     eax, eax
0x18003a88f  mov     word ptr [rbp+50h+userSid._Mypair._Myval2._Bx], ax
0x18003a893  lea     rax, [rbp+50h+userSid]
0x18003a897  mov     [rsp+150h+f.userSid], rax
0x18003a89c  lea     rcx, [rsp+150h+f]; f
0x18003a8a1  call    ExecuteAndConvertAnyException__PurgeUtil__RemovePurgeTask____2____lambda_1___
0x18003a8a6  test    eax, eax
0x18003a8a8  jns     short loc_18003A8E8
0x18003a8aa  lea     rbx, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a8b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a8b8  cmp     rcx, rbx
0x18003a8bb  jz      loc_18003AB8D
0x18003a8c1  test    byte ptr [rcx+1Ch], 4
0x18003a8c5  jz      loc_18003AB8D
0x18003a8cb  mov     edx, 11h; id
0x18003a8d0  mov     r9d, eax; _a1
0x18003a8d3  lea     r8, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids; TraceGuid
0x18003a8da  mov     rcx, [rcx+10h]; Logger
0x18003a8de  call    WPP_SF_d
0x18003a8e3  jmp     loc_18003AB8D
0x18003a8e8  lea     rbx, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a8ef  lea     rdi, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids
0x18003a8f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a8fd  cmp     rcx, rbx
0x18003a900  jz      short loc_18003A919
0x18003a902  test    byte ptr [rcx+1Ch], 10h
0x18003a906  jz      short loc_18003A919
0x18003a908  mov     edx, 12h; id
0x18003a90d  mov     r8, rdi; TraceGuid
0x18003a910  mov     rcx, [rcx+10h]; Logger
0x18003a914  call    WPP_SF_
0x18003a919  mov     [rbp+50h+spTaskService.p], 0
0x18003a921  lea     rax, [rbp+50h+spTaskService]
0x18003a925  mov     [rsp+150h+ppv], rax; ppv
0x18003a92a  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18003a931  xor     edx, edx; pUnkOuter
0x18003a933  lea     r8d, [rdx+17h]; dwClsContext
0x18003a937  lea     rcx, CLSID_TaskScheduler; rclsid
0x18003a93e  call    cs:__imp_CoCreateInstance
0x18003a944  test    eax, eax
0x18003a946  jns     short loc_18003A96C
0x18003a948  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a94f  cmp     rcx, rbx
0x18003a952  jz      loc_18003AB83
0x18003a958  test    byte ptr [rcx+1Ch], 4
0x18003a95c  jz      loc_18003AB83
0x18003a962  mov     edx, 13h
0x18003a967  jmp     loc_18003AA21
0x18003a96c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a973  cmp     rcx, rbx
0x18003a976  jz      short loc_18003A98F
0x18003a978  test    byte ptr [rcx+1Ch], 10h
0x18003a97c  jz      short loc_18003A98F
0x18003a97e  mov     edx, 14h; id
0x18003a983  mov     r8, rdi; TraceGuid
0x18003a986  mov     rcx, [rcx+10h]; Logger
0x18003a98a  call    WPP_SF_
0x18003a98f  xorps   xmm0, xmm0
0x18003a992  xor     eax, eax
0x18003a994  movups  xmmword ptr [rbp+50h+vtEmpty.___u0], xmm0
0x18003a998  mov     [rbp+50h+vtEmpty.pRecInfo], rax
0x18003a99c  lea     rcx, [rbp+50h+vtEmpty]; pvarg
0x18003a9a0  call    cs:__imp_VariantInit
0x18003a9a6  mov     rcx, [rbp+50h+spTaskService.p]
0x18003a9aa  movups  xmm1, xmmword ptr [rbp+50h+vtEmpty.___u0]
0x18003a9ae  movsd   xmm0, [rbp+50h+vtEmpty.pRecInfo]
0x18003a9b3  movaps  [rsp+150h+var_110], xmm1
0x18003a9b8  movsd   [rsp+150h+var_100], xmm0
0x18003a9be  movaps  [rsp+150h+var_F0], xmm1
0x18003a9c3  movsd   [rsp+150h+var_E0], xmm0
0x18003a9c9  movaps  [rbp+50h+var_D0], xmm1
0x18003a9cd  movsd   [rbp+50h+var_C0], xmm0
0x18003a9d2  movaps  [rbp+50h+var_B0], xmm1
0x18003a9d6  movsd   [rbp+50h+var_A0], xmm0
0x18003a9db  mov     rax, [rcx]
0x18003a9de  lea     rdx, [rsp+150h+var_110]
0x18003a9e3  mov     [rsp+150h+ppv], rdx
0x18003a9e8  lea     r9, [rsp+150h+var_F0]
0x18003a9ed  lea     r8, [rbp+50h+var_D0]
0x18003a9f1  lea     rdx, [rbp+50h+var_B0]
0x18003a9f5  mov     rax, [rax+50h]
0x18003a9f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a9fe  test    eax, eax
0x18003aa00  jns     short loc_18003AA35
0x18003aa02  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003aa09  cmp     rcx, rbx
0x18003aa0c  jz      loc_18003AB83
0x18003aa12  test    byte ptr [rcx+1Ch], 4
0x18003aa16  jz      loc_18003AB83
0x18003aa1c  mov     edx, 15h; id
0x18003aa21  mov     r9d, eax; _a1
0x18003aa24  mov     r8, rdi; TraceGuid
0x18003aa27  mov     rcx, [rcx+10h]; Logger
0x18003aa2b  call    WPP_SF_d
0x18003aa30  jmp     loc_18003AB83
0x18003aa35  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003aa3c  cmp     rcx, rbx
0x18003aa3f  jz      short loc_18003AA58
0x18003aa41  test    byte ptr [rcx+1Ch], 10h
0x18003aa45  jz      short loc_18003AA58
0x18003aa47  mov     edx, 16h; id
0x18003aa4c  mov     r8, rdi; TraceGuid
0x18003aa4f  mov     rcx, [rcx+10h]; Logger
0x18003aa53  call    WPP_SF_
0x18003aa58  mov     [rbp+50h+spFolder.p], 0
0x18003aa60  mov     rsi, [rbp+50h+spTaskService.p]
0x18003aa64  mov     rax, [rsi]
0x18003aa67  mov     r14, [rax+38h]
0x18003aa6b  lea     rdx, s; "\\"
0x18003aa72  lea     rcx, [rsp+150h+f]; this
0x18003aa77  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003aa7c  nop
0x18003aa7d  mov     rdx, [rax]
0x18003aa80  test    rdx, rdx
0x18003aa83  jz      short loc_18003AA88
0x18003aa85  mov     rdx, [rdx]
0x18003aa88  lea     r8, [rbp+50h+spFolder]
0x18003aa8c  mov     rcx, rsi
0x18003aa8f  mov     rax, r14
0x18003aa92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa97  mov     esi, eax
0x18003aa99  lea     rcx, [rsp+150h+f]; this
0x18003aa9e  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003aaa3  test    esi, esi
0x18003aaa5  jns     short loc_18003AADA
0x18003aaa7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003aaae  cmp     rcx, rbx
0x18003aab1  jz      loc_18003AB79
0x18003aab7  test    byte ptr [rcx+1Ch], 4
0x18003aabb  jz      loc_18003AB79
0x18003aac1  mov     edx, 17h; id
0x18003aac6  mov     r9d, esi; _a1
0x18003aac9  mov     r8, rdi; TraceGuid
0x18003aacc  mov     rcx, [rcx+10h]; Logger
0x18003aad0  call    WPP_SF_d
0x18003aad5  jmp     loc_18003AB79
0x18003aada  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003aae1  cmp     rcx, rbx
0x18003aae4  jz      short loc_18003AAFD
0x18003aae6  test    byte ptr [rcx+1Ch], 10h
0x18003aaea  jz      short loc_18003AAFD
0x18003aaec  mov     edx, 18h; id
0x18003aaf1  mov     r8, rdi; TraceGuid
0x18003aaf4  mov     rcx, [rcx+10h]; Logger
0x18003aaf8  call    WPP_SF_
0x18003aafd  lea     r8, [rbp+50h+userSid]; _Right
0x18003ab01  lea     rdx, aMicrosoftWindo_0; "Microsoft\\Windows\\WCM\\Provisioning\\"...
0x18003ab08  lea     rcx, [rbp+50h+taskPath]; result
0x18003ab0c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18003ab11  nop
0x18003ab12  lea     rdx, [rbp+50h+taskPath]; Path
0x18003ab16  mov     rcx, [rbp+50h+spFolder.p]; Folder
0x18003ab1a  call    ?DeletePurgeTask@@YAJPEAUITaskFolder@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DeletePurgeTask(ITaskFolder *,std::wstring &)
0x18003ab1f  test    eax, eax
0x18003ab21  jns     short loc_18003AB4B
0x18003ab23  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003ab2a  cmp     rcx, rbx
0x18003ab2d  jz      short loc_18003AB6F
0x18003ab2f  test    byte ptr [rcx+1Ch], 4
0x18003ab33  jz      short loc_18003AB6F
0x18003ab35  mov     edx, 19h; id
0x18003ab3a  mov     r9d, eax; _a1
0x18003ab3d  mov     r8, rdi; TraceGuid
0x18003ab40  mov     rcx, [rcx+10h]; Logger
0x18003ab44  call    WPP_SF_d
0x18003ab49  jmp     short loc_18003AB6F
0x18003ab4b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003ab52  cmp     rcx, rbx
0x18003ab55  jz      short loc_18003AB6F
0x18003ab57  test    byte ptr [rcx+1Ch], 10h
0x18003ab5b  jz      short loc_18003AB6F
0x18003ab5d  mov     edx, 1Ah; id
0x18003ab62  mov     r8, rdi; TraceGuid
0x18003ab65  mov     rcx, [rcx+10h]; Logger
0x18003ab69  call    WPP_SF_
0x18003ab6e  nop
0x18003ab6f  lea     rcx, [rbp+50h+taskPath]; this
0x18003ab73  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ab78  nop
0x18003ab79  lea     rcx, [rbp+50h+spFolder]; this
0x18003ab7d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003ab82  nop
0x18003ab83  lea     rcx, [rbp+50h+spTaskService]; this
0x18003ab87  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003ab8c  nop
0x18003ab8d  lea     rcx, [rbp+50h+userSid]; this
0x18003ab91  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003ab96  mov     rcx, [rbp+50h+var_28]
0x18003ab9a  xor     rcx, rsp; StackCookie
0x18003ab9d  call    __security_check_cookie
0x18003aba2  add     rsp, 130h
0x18003aba9  pop     r14
0x18003abab  pop     rdi
0x18003abac  pop     rsi
0x18003abad  pop     rbx
0x18003abae  pop     rbp
0x18003abaf  retn
```
