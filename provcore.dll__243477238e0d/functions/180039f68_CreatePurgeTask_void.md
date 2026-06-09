# CreatePurgeTask(void)

- ea: `0x180039f68`
- end: `0x18003a332`
- name: `?CreatePurgeTask@@YAJXZ`
- size: `970`
- prototype: `HRESULT __fastcall()`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003abb8`

## callees

- `0x180002790`
- `0x180008388`
- `0x18000b1e4`
- `0x18000b2f4`
- `0x180010c34`
- `0x180011cfc`
- `0x180012748`
- `0x180012770`
- `0x180039b0c`
- `0x180039f68`
- `0x18003a6e0`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003a0c3`
- `OLEAUT32!__imp_VariantInit` at `0x18003a25c`
- `OLEAUT32!__imp_VariantInit` at `0x18003a0c3`
- `OLEAUT32!__imp_VariantInit` at `0x18003a25c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003a050`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003a050`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CreatePurgeTask()
{
  int v0; // eax
  HRESULT Instance; // esi
  WPP_PROJECT_CONTROL_BLOCK *v2; // rcx
  unsigned __int16 v3; // dx
  ITaskService *p; // rsi
  HRESULT (__fastcall *GetFolder)(ITaskService *, wchar_t *, ITaskFolder **); // r14
  wchar_t **v6; // rax
  wchar_t *v7; // rdx
  const wchar_t *v8; // r8
  int v9; // eax
  PurgeUtil::RemovePurgeTask::__l2::<lambda_1> f; // [rsp+30h] [rbp-D0h] BYREF
  tagVARIANT v12; // [rsp+40h] [rbp-C0h] BYREF
  tagVARIANT v13; // [rsp+60h] [rbp-A0h] BYREF
  tagVARIANT v14; // [rsp+80h] [rbp-80h] BYREF
  tagVARIANT v15; // [rsp+A0h] [rbp-60h] BYREF
  ATL::CComPtr<ITaskService> spTaskService; // [rsp+C0h] [rbp-40h] BYREF
  ATL::CComPtr<ITaskFolder> spRootFolder; // [rsp+C8h] [rbp-38h] BYREF
  std::wstring userSid; // [rsp+D0h] [rbp-30h] BYREF
  tagVARIANT vtEmpty; // [rsp+F0h] [rbp-10h] BYREF
  tagVARIANT varEmpty; // [rsp+108h] [rbp+8h] BYREF
  std::wstring path; // [rsp+120h] [rbp+20h] BYREF

  userSid._Mypair._Myval2._Bx = 0;
  *(__m128i *)&userSid._Mypair._Myval2._Mysize = _mm_load_si128((const __m128i *)&_xmm);
  userSid._Mypair._Myval2._Bx._Buf[0] = 0;
  f.userSid = &userSid;
  v0 = ExecuteAndConvertAnyException__PurgeUtil::RemovePurgeTask_::_2_::_lambda_1___(&f);
  Instance = v0;
  if ( v0 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Cu, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids);
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
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x1Eu, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids);
      }
      memset(&vtEmpty, 0, sizeof(vtEmpty));
      VariantInit(&vtEmpty);
      v14 = vtEmpty;
      v15 = vtEmpty;
      v12 = vtEmpty;
      v13 = vtEmpty;
      Instance = ((__int64 (__fastcall *)(ITaskService *, tagVARIANT *, tagVARIANT *, tagVARIANT *))spTaskService.p->Connect)(
                   spTaskService.p,
                   &v13,
                   &v12,
                   &v15);
      if ( Instance >= 0 )
      {
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x20u, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids);
        }
        spRootFolder.p = 0;
        p = spTaskService.p;
        GetFolder = spTaskService.p->GetFolder;
        _bstr_t::_bstr_t((_bstr_t *)&f, L"\\");
        v7 = *v6;
        if ( *v6 )
          v7 = *(wchar_t **)v7;
        Instance = GetFolder(p, v7, &spRootFolder.p);
        _bstr_t::_Free((_bstr_t *)&f);
        if ( Instance >= 0 )
        {
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x22u, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids);
          }
          std::operator+<unsigned short>(&path, L"Microsoft\\Windows\\WCM\\Provisioning\\Purge.", &userSid);
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x23u, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids);
          }
          memset(&varEmpty, 0, sizeof(varEmpty));
          VariantInit(&varEmpty);
          v13 = varEmpty;
          v12 = varEmpty;
          v9 = RegisterPurgeTask(spRootFolder.p, &path, v8, &v12, (_TASK_LOGON_TYPE)&v14, &v13);
          Instance = v9;
          if ( v9 >= 0 )
          {
            if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x25u, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids);
            }
          }
          else if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
                 && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x24u, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids, v9);
          }
          std::wstring::_Tidy_deallocate(&path);
        }
        else if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
               && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x21u, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids, Instance);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spRootFolder);
        goto LABEL_44;
      }
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->ReserveSpace[28] & 2) == 0 )
      {
LABEL_44:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spTaskService);
        goto LABEL_45;
      }
      v3 = 31;
    }
    else
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control->ReserveSpace[28] & 2) == 0 )
      {
        goto LABEL_44;
      }
      v3 = 29;
    }
    WPP_SF_d(v2->Control.Logger, v3, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids, Instance);
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x1Bu, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids, v0);
  }
LABEL_45:
  std::wstring::_Tidy_deallocate(&userSid);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180039f68  push    rbp
0x180039f6a  push    rbx
0x180039f6b  push    rsi
0x180039f6c  push    rdi
0x180039f6d  push    r14
0x180039f6f  lea     rbp, [rsp-50h]
0x180039f74  sub     rsp, 150h
0x180039f7b  mov     rax, cs:__security_cookie
0x180039f82  xor     rax, rsp
0x180039f85  mov     [rbp+70h+var_30], rax
0x180039f89  xorps   xmm0, xmm0
0x180039f8c  movups  xmmword ptr [rbp+70h+userSid._Mypair._Myval2._Bx], xmm0
0x180039f90  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180039f98  movdqu  xmmword ptr [rbp+70h+userSid._Mypair._Myval2._Mysize], xmm1
0x180039f9d  xor     eax, eax
0x180039f9f  mov     word ptr [rbp+70h+userSid._Mypair._Myval2._Bx], ax
0x180039fa3  lea     rax, [rbp+70h+userSid]
0x180039fa7  mov     [rsp+170h+f.userSid], rax
0x180039fac  lea     rcx, [rsp+170h+f]; f
0x180039fb1  call    ExecuteAndConvertAnyException__PurgeUtil__RemovePurgeTask____2____lambda_1___
0x180039fb6  mov     esi, eax
0x180039fb8  test    eax, eax
0x180039fba  jns     short loc_180039FFA
0x180039fbc  lea     rbx, WPP_GLOBAL_Control; __annotation("TMF:",
0x180039fc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180039fca  cmp     rcx, rbx
0x180039fcd  jz      loc_18003A30D
0x180039fd3  test    byte ptr [rcx+1Ch], 2
0x180039fd7  jz      loc_18003A30D
0x180039fdd  mov     edx, 1Bh; id
0x180039fe2  mov     r9d, eax; _a1
0x180039fe5  lea     r8, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids; TraceGuid
0x180039fec  mov     rcx, [rcx+10h]; Logger
0x180039ff0  call    WPP_SF_d
0x180039ff5  jmp     loc_18003A30D
0x180039ffa  lea     rbx, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a001  lea     rdi, WPP_a4c9b1d0837a312d457a88259d95db07_Traceguids
0x18003a008  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a00f  cmp     rcx, rbx
0x18003a012  jz      short loc_18003A02B
0x18003a014  test    byte ptr [rcx+1Ch], 10h
0x18003a018  jz      short loc_18003A02B
0x18003a01a  mov     edx, 1Ch; id
0x18003a01f  mov     r8, rdi; TraceGuid
0x18003a022  mov     rcx, [rcx+10h]; Logger
0x18003a026  call    WPP_SF_
0x18003a02b  mov     [rbp+70h+spTaskService.p], 0
0x18003a033  lea     rax, [rbp+70h+spTaskService]
0x18003a037  mov     [rsp+170h+ppv], rax; ppv
0x18003a03c  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18003a043  xor     edx, edx; pUnkOuter
0x18003a045  lea     r8d, [rdx+17h]; dwClsContext
0x18003a049  lea     rcx, CLSID_TaskScheduler; rclsid
0x18003a050  call    cs:__imp_CoCreateInstance
0x18003a056  mov     esi, eax
0x18003a058  test    eax, eax
0x18003a05a  jns     short loc_18003A08F
0x18003a05c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a063  cmp     rcx, rbx
0x18003a066  jz      loc_18003A303
0x18003a06c  test    byte ptr [rcx+1Ch], 2
0x18003a070  jz      loc_18003A303
0x18003a076  mov     edx, 1Dh; id
0x18003a07b  mov     r9d, esi; _a1
0x18003a07e  mov     r8, rdi; TraceGuid
0x18003a081  mov     rcx, [rcx+10h]; Logger
0x18003a085  call    WPP_SF_d
0x18003a08a  jmp     loc_18003A303
0x18003a08f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a096  cmp     rcx, rbx
0x18003a099  jz      short loc_18003A0B2
0x18003a09b  test    byte ptr [rcx+1Ch], 10h
0x18003a09f  jz      short loc_18003A0B2
0x18003a0a1  mov     edx, 1Eh; id
0x18003a0a6  mov     r8, rdi; TraceGuid
0x18003a0a9  mov     rcx, [rcx+10h]; Logger
0x18003a0ad  call    WPP_SF_
0x18003a0b2  xorps   xmm0, xmm0
0x18003a0b5  xor     eax, eax
0x18003a0b7  movups  xmmword ptr [rbp+70h+vtEmpty.___u0], xmm0
0x18003a0bb  mov     [rbp+70h+vtEmpty.pRecInfo], rax
0x18003a0bf  lea     rcx, [rbp+70h+vtEmpty]; pvarg
0x18003a0c3  call    cs:__imp_VariantInit
0x18003a0c9  mov     rcx, [rbp+70h+spTaskService.p]
0x18003a0cd  movups  xmm1, xmmword ptr [rbp+70h+vtEmpty.___u0]
0x18003a0d1  movsd   xmm0, [rbp+70h+vtEmpty.pRecInfo]
0x18003a0d6  movaps  [rbp+70h+var_F0], xmm1
0x18003a0da  movsd   [rbp+70h+var_E0], xmm0
0x18003a0df  movaps  [rbp+70h+var_D0], xmm1
0x18003a0e3  movsd   [rbp+70h+var_C0], xmm0
0x18003a0e8  movaps  [rsp+170h+var_130], xmm1
0x18003a0ed  movsd   [rsp+170h+var_120], xmm0
0x18003a0f3  movaps  [rsp+170h+var_110], xmm1
0x18003a0f8  movsd   [rsp+170h+var_100], xmm0
0x18003a0fe  mov     rax, [rcx]
0x18003a101  lea     rdx, [rbp+70h+var_F0]
0x18003a105  mov     [rsp+170h+ppv], rdx
0x18003a10a  lea     r9, [rbp+70h+var_D0]
0x18003a10e  lea     r8, [rsp+170h+var_130]
0x18003a113  lea     rdx, [rsp+170h+var_110]
0x18003a118  mov     rax, [rax+50h]
0x18003a11c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a121  mov     esi, eax
0x18003a123  test    eax, eax
0x18003a125  jns     short loc_18003A14B
0x18003a127  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a12e  cmp     rcx, rbx
0x18003a131  jz      loc_18003A303
0x18003a137  test    byte ptr [rcx+1Ch], 2
0x18003a13b  jz      loc_18003A303
0x18003a141  mov     edx, 1Fh
0x18003a146  jmp     loc_18003A07B
0x18003a14b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a152  cmp     rcx, rbx
0x18003a155  jz      short loc_18003A16E
0x18003a157  test    byte ptr [rcx+1Ch], 10h
0x18003a15b  jz      short loc_18003A16E
0x18003a15d  mov     edx, 20h ; ' '; id
0x18003a162  mov     r8, rdi; TraceGuid
0x18003a165  mov     rcx, [rcx+10h]; Logger
0x18003a169  call    WPP_SF_
0x18003a16e  mov     [rbp+70h+spRootFolder.p], 0
0x18003a176  mov     rsi, [rbp+70h+spTaskService.p]
0x18003a17a  mov     rax, [rsi]
0x18003a17d  mov     r14, [rax+38h]
0x18003a181  lea     rdx, s; "\\"
0x18003a188  lea     rcx, [rsp+170h+f]; this
0x18003a18d  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x18003a192  nop
0x18003a193  mov     rdx, [rax]
0x18003a196  test    rdx, rdx
0x18003a199  jz      short loc_18003A19E
0x18003a19b  mov     rdx, [rdx]
0x18003a19e  lea     r8, [rbp+70h+spRootFolder]
0x18003a1a2  mov     rcx, rsi
0x18003a1a5  mov     rax, r14
0x18003a1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1ad  mov     esi, eax
0x18003a1af  lea     rcx, [rsp+170h+f]; this
0x18003a1b4  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18003a1b9  test    esi, esi
0x18003a1bb  jns     short loc_18003A1F0
0x18003a1bd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a1c4  cmp     rcx, rbx
0x18003a1c7  jz      loc_18003A2F9
0x18003a1cd  test    byte ptr [rcx+1Ch], 2
0x18003a1d1  jz      loc_18003A2F9
0x18003a1d7  mov     edx, 21h ; '!'; id
0x18003a1dc  mov     r9d, esi; _a1
0x18003a1df  mov     r8, rdi; TraceGuid
0x18003a1e2  mov     rcx, [rcx+10h]; Logger
0x18003a1e6  call    WPP_SF_d
0x18003a1eb  jmp     loc_18003A2F9
0x18003a1f0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a1f7  cmp     rcx, rbx
0x18003a1fa  jz      short loc_18003A213
0x18003a1fc  test    byte ptr [rcx+1Ch], 10h
0x18003a200  jz      short loc_18003A213
0x18003a202  mov     edx, 22h ; '"'; id
0x18003a207  mov     r8, rdi; TraceGuid
0x18003a20a  mov     rcx, [rcx+10h]; Logger
0x18003a20e  call    WPP_SF_
0x18003a213  lea     r8, [rbp+70h+userSid]; _Right
0x18003a217  lea     rdx, aMicrosoftWindo_0; "Microsoft\\Windows\\WCM\\Provisioning\\"...
0x18003a21e  lea     rcx, [rbp+70h+path]; result
0x18003a222  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x18003a227  nop
0x18003a228  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a22f  cmp     rcx, rbx
0x18003a232  jz      short loc_18003A24B
0x18003a234  test    byte ptr [rcx+1Ch], 10h
0x18003a238  jz      short loc_18003A24B
0x18003a23a  mov     edx, 23h ; '#'; id
0x18003a23f  mov     r8, rdi; TraceGuid
0x18003a242  mov     rcx, [rcx+10h]; Logger
0x18003a246  call    WPP_SF_
0x18003a24b  xorps   xmm0, xmm0
0x18003a24e  xor     eax, eax
0x18003a250  movups  xmmword ptr [rbp+70h+varEmpty.___u0], xmm0
0x18003a254  mov     [rbp+70h+varEmpty.pRecInfo], rax
0x18003a258  lea     rcx, [rbp+70h+varEmpty]; pvarg
0x18003a25c  call    cs:__imp_VariantInit
0x18003a262  movups  xmm1, xmmword ptr [rbp+70h+varEmpty.___u0]
0x18003a266  movsd   xmm0, [rbp+70h+varEmpty.pRecInfo]
0x18003a26b  movaps  [rsp+170h+var_110], xmm1
0x18003a270  movsd   [rsp+170h+var_100], xmm0
0x18003a276  movaps  [rsp+170h+var_130], xmm1
0x18003a27b  movsd   [rsp+170h+var_120], xmm0
0x18003a281  lea     rax, [rsp+170h+var_110]
0x18003a286  mov     [rsp+170h+var_148], rax
0x18003a28b  lea     r9, [rsp+170h+var_130]
0x18003a290  lea     rdx, [rbp+70h+path]
0x18003a294  mov     rcx, [rbp+70h+spRootFolder.p]
0x18003a298  call    ?RegisterPurgeTask@@YAJPEAUITaskFolder@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGUtagVARIANT@@W4_TASK_LOGON_TYPE@@3@Z; RegisterPurgeTask(ITaskFolder *,std::wstring &,ushort const *,tagVARIANT,_TASK_LOGON_TYPE,tagVARIANT)
0x18003a29d  mov     esi, eax
0x18003a29f  test    eax, eax
0x18003a2a1  jns     short loc_18003A2CB
0x18003a2a3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a2aa  cmp     rcx, rbx
0x18003a2ad  jz      short loc_18003A2EF
0x18003a2af  test    byte ptr [rcx+1Ch], 2
0x18003a2b3  jz      short loc_18003A2EF
0x18003a2b5  mov     edx, 24h ; '$'; id
0x18003a2ba  mov     r9d, eax; _a1
0x18003a2bd  mov     r8, rdi; TraceGuid
0x18003a2c0  mov     rcx, [rcx+10h]; Logger
0x18003a2c4  call    WPP_SF_d
0x18003a2c9  jmp     short loc_18003A2EF
0x18003a2cb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003a2d2  cmp     rcx, rbx
0x18003a2d5  jz      short loc_18003A2EF
0x18003a2d7  test    byte ptr [rcx+1Ch], 10h
0x18003a2db  jz      short loc_18003A2EF
0x18003a2dd  mov     edx, 25h ; '%'; id
0x18003a2e2  mov     r8, rdi; TraceGuid
0x18003a2e5  mov     rcx, [rcx+10h]; Logger
0x18003a2e9  call    WPP_SF_
0x18003a2ee  nop
0x18003a2ef  lea     rcx, [rbp+70h+path]; this
0x18003a2f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a2f8  nop
0x18003a2f9  lea     rcx, [rbp+70h+spRootFolder]; this
0x18003a2fd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a302  nop
0x18003a303  lea     rcx, [rbp+70h+spTaskService]; this
0x18003a307  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a30c  nop
0x18003a30d  lea     rcx, [rbp+70h+userSid]; this
0x18003a311  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a316  mov     eax, esi
0x18003a318  mov     rcx, [rbp+70h+var_30]
0x18003a31c  xor     rcx, rsp; StackCookie
0x18003a31f  call    __security_check_cookie
0x18003a324  add     rsp, 150h
0x18003a32b  pop     r14
0x18003a32d  pop     rdi
0x18003a32e  pop     rsi
0x18003a32f  pop     rbx
0x18003a330  pop     rbp
0x18003a331  retn
```
