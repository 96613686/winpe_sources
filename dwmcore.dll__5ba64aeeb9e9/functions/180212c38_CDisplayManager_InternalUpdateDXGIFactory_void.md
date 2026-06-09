# CDisplayManager::InternalUpdateDXGIFactory(void)

- ea: `0x180212c38`
- end: `0x180212e10`
- name: `?InternalUpdateDXGIFactory@CDisplayManager@@AEAAJXZ`
- size: `472`
- prototype: `__int64 __fastcall(CDisplayManager *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18012cba8`
- `0x18021a6b0`

## callees

- `0x18001c840`
- `0x180026eac`
- `0x180027940`
- `0x180049390`
- `0x18004fce4`
- `0x18015ab60`
- `0x1801700e0`
- `0x1801e53d0`
- `0x180212c38`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180212d1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180212d1a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180212ded`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180212ded`
- `dxgi!CreateDXGIFactory1` at `0x180212c85`
- `dxgi!CreateDXGIFactory1` at `0x180212c85`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180212dce`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180212dce`

## pseudocode

```c
__int64 __fastcall CDisplayManager::InternalUpdateDXGIFactory(CDisplayManager *this)
{
  int CurrentFrameId; // eax
  int v2; // ecx
  HRESULT v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  CDisplayManager *v6; // rcx
  CComposition *v7; // rcx
  int v9; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+8h]
  CDisplayManager *v11; // [rsp+40h] [rbp+10h] BYREF
  void *ppFactory; // [rsp+48h] [rbp+18h] BYREF
  _RTL_CRITICAL_SECTION *v13; // [rsp+50h] [rbp+20h] BYREF

  v11 = this;
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 2) != 0 )
  {
    CurrentFrameId = GetCurrentFrameId();
    McTemplateU0qqq_EventWriteTransfer(v2, (unsigned int)EVTDESC_SCHEDULE_DERIVEDISPLAYSET, 0, CurrentFrameId, 0);
  }
  ppFactory = 0;
  v3 = CreateDXGIFactory1(&GUID_a4966eed_76db_44da_84c1_ee9a7afb20a8, &ppFactory);
  v4 = v3;
  if ( v3 >= 0 )
  {
    LODWORD(v11) = 0;
    v5 = (*(__int64 (__fastcall **)(void *, __int64, CDisplayManager **))(*(_QWORD *)ppFactory + 240LL))(
           ppFactory,
           qword_1803BB0C8,
           &v11);
    v4 = v5;
    if ( v5 >= 0 )
    {
      v13 = &g_DisplayManager;
      EnterCriticalSection(&g_DisplayManager);
      v6 = qword_1803BB0B8;
      if ( qword_1803BB0B8 )
      {
        if ( (_DWORD)qword_1803BB0D8 )
        {
          (*(void (**)(void))(*(_QWORD *)qword_1803BB0B8 + 248LL))();
          v6 = qword_1803BB0B8;
          LODWORD(qword_1803BB0D8) = 0;
        }
        if ( (unsigned __int64)(qword_1803BB0D0 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !byte_1803BB0E2 )
        {
          (*(void (__fastcall **)(CDisplayManager *, _QWORD))(*(_QWORD *)v6 + 184LL))(v6, HIDWORD(qword_1803BB0D8));
          HIDWORD(qword_1803BB0D8) = 0;
        }
      }
      LODWORD(qword_1803BB0D8) = (_DWORD)v11;
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(&qword_1803BB0D0);
      ReleaseInterface<ID2D1Geometry>(&qword_1803BB0B8);
      qword_1803BB0B8 = (CDisplayManager *)ppFactory;
      ppFactory = 0;
      LOBYTE(word_1803BB0E0) = 0;
      byte_1803BB0E2 = GetSystemMetrics(4096) != 0;
      CGuard<CCriticalSection>::~CGuard<CCriticalSection>(&v13);
      QueryPerformanceCounter(&PerformanceCount);
      CComposition::ResetTokenThread(v7);
      v4 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x199,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\hw\\displaymanager.cpp",
        (const char *)(unsigned int)v5,
        v9);
    }
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&ppFactory);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x195,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\hw\\displaymanager.cpp",
      (const char *)(unsigned int)v3,
      v9);
    if ( ppFactory )
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppFactory + 16LL))(ppFactory);
  }
  return v4;
}

```

## disassembly

```asm
0x180212c38  mov     [rsp-8+arg_18], rbx
0x180212c3d  mov     [rsp-8+arg_0], rcx
0x180212c42  push    rbp
0x180212c43  mov     rbp, rsp
0x180212c46  sub     rsp, 30h
0x180212c4a  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 2
0x180212c51  jz      short loc_180212C72
0x180212c53  call    ?GetCurrentFrameId@@YA_KXZ; GetCurrentFrameId(void)
0x180212c58  mov     r9, rax
0x180212c5b  mov     [rsp+30h+var_10], 0; int
0x180212c63  xor     r8d, r8d
0x180212c66  lea     rdx, EVTDESC_SCHEDULE_DERIVEDISPLAYSET
0x180212c6d  call    McTemplateU0qqq_EventWriteTransfer
0x180212c72  lea     rdx, [rbp+ppFactory]; ppFactory
0x180212c76  mov     [rbp+ppFactory], 0
0x180212c7e  lea     rcx, _GUID_a4966eed_76db_44da_84c1_ee9a7afb20a8; riid
0x180212c85  call    cs:__imp_CreateDXGIFactory1
0x180212c8b  mov     ebx, eax
0x180212c8d  test    eax, eax
0x180212c8f  jns     short loc_180212CC7
0x180212c91  mov     rcx, [rbp+8]; this
0x180212c95  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x180212c9c  mov     r9d, eax; char *
0x180212c9f  mov     edx, 195h; void *
0x180212ca4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180212ca9  mov     rcx, [rbp+ppFactory]
0x180212cad  test    rcx, rcx
0x180212cb0  jz      loc_180212E03
0x180212cb6  mov     rdx, [rcx]
0x180212cb9  mov     rax, [rdx+10h]
0x180212cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180212cc2  jmp     loc_180212E03
0x180212cc7  mov     rcx, [rbp+ppFactory]
0x180212ccb  lea     r8, [rbp+arg_0]
0x180212ccf  mov     rdx, cs:qword_1803BB0C8
0x180212cd6  mov     dword ptr [rbp+arg_0], 0
0x180212cdd  mov     rax, [rcx]
0x180212ce0  mov     rax, [rax+0F0h]
0x180212ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180212cec  mov     ebx, eax
0x180212cee  test    eax, eax
0x180212cf0  jns     short loc_180212D0F
0x180212cf2  mov     rcx, [rbp+8]; this
0x180212cf6  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\dwm\\dwmcore\\hw\\"...
0x180212cfd  mov     r9d, eax; char *
0x180212d00  mov     edx, 199h; void *
0x180212d05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180212d0a  jmp     loc_180212DFA
0x180212d0f  lea     rcx, ?g_DisplayManager@@3VCDisplayManager@@A; lpCriticalSection
0x180212d16  mov     [rbp+arg_10], rcx
0x180212d1a  call    cs:__imp_EnterCriticalSection
0x180212d20  mov     rcx, cs:qword_1803BB0B8
0x180212d27  test    rcx, rcx
0x180212d2a  jz      short loc_180212D8E
0x180212d2c  mov     edx, dword ptr cs:qword_1803BB0D8
0x180212d32  test    edx, edx
0x180212d34  jz      short loc_180212D56
0x180212d36  mov     rax, [rcx]
0x180212d39  mov     rax, [rax+0F8h]
0x180212d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180212d45  mov     rcx, cs:qword_1803BB0B8
0x180212d4c  mov     dword ptr cs:qword_1803BB0D8, 0
0x180212d56  mov     rax, cs:qword_1803BB0D0
0x180212d5d  dec     rax
0x180212d60  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180212d64  ja      short loc_180212D8E
0x180212d66  cmp     cs:byte_1803BB0E2, 0
0x180212d6d  jnz     short loc_180212D8E
0x180212d6f  mov     rax, [rcx]
0x180212d72  mov     edx, dword ptr cs:qword_1803BB0D8+4
0x180212d78  mov     rax, [rax+0B8h]
0x180212d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180212d84  mov     dword ptr cs:qword_1803BB0D8+4, 0
0x180212d8e  mov     eax, dword ptr [rbp+arg_0]
0x180212d91  lea     rcx, qword_1803BB0D0
0x180212d98  mov     dword ptr cs:qword_1803BB0D8, eax
0x180212d9e  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$T@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(std::nullptr_t)
0x180212da3  lea     rcx, qword_1803BB0B8
0x180212daa  call    ??$ReleaseInterface@UID2D1Geometry@@@@YAXAEAPEAUID2D1Geometry@@@Z; ReleaseInterface<ID2D1Geometry>(ID2D1Geometry * &)
0x180212daf  mov     rax, [rbp+ppFactory]
0x180212db3  mov     ecx, 1000h; nIndex
0x180212db8  mov     cs:qword_1803BB0B8, rax
0x180212dbf  mov     [rbp+ppFactory], 0
0x180212dc7  mov     byte ptr cs:word_1803BB0E0, 0
0x180212dce  call    cs:__imp_GetSystemMetrics
0x180212dd4  test    eax, eax
0x180212dd6  lea     rcx, [rbp+arg_10]
0x180212dda  setnz   cs:byte_1803BB0E2
0x180212de1  call    ??1?$CGuard@VCCriticalSection@@@@QEAA@XZ; CGuard<CCriticalSection>::~CGuard<CCriticalSection>(void)
0x180212de6  lea     rcx, PerformanceCount; lpPerformanceCount
0x180212ded  call    cs:__imp_QueryPerformanceCounter
0x180212df3  call    ?ResetTokenThread@CComposition@@QEAAJXZ; CComposition::ResetTokenThread(void)
0x180212df8  xor     ebx, ebx
0x180212dfa  lea     rcx, [rbp+ppFactory]
0x180212dfe  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x180212e03  mov     eax, ebx
0x180212e05  mov     rbx, [rsp+30h+arg_18]
0x180212e0a  add     rsp, 30h
0x180212e0e  pop     rbp
0x180212e0f  retn
```
