# Rdp::Avenc::Umrdp::CRdpSharedTextureSurface::CreateDxSharedTexture(wil::com_ptr_t<ID3D11Device,wil::err_exception_policy> const &,uint,uint)

- ea: `0x18001fd14`
- end: `0x18002018f`
- name: `?CreateDxSharedTexture@CRdpSharedTextureSurface@Umrdp@Avenc@Rdp@@AEAAXAEBV?$com_ptr_t@UID3D11Device@@Uerr_exception_policy@wil@@@wil@@II@Z`
- size: `1147`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800203c0`

## callees

- `0x1800025bc`
- `0x180006580`
- `0x18000e848`
- `0x18000ec04`
- `0x1800153f8`
- `0x180019998`
- `0x18001fd14`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ff86`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ff86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001feaa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001feaa`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001fecf`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001fecf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ff7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800200ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800200b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800200ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ff7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800200ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800200b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800200ca`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001fe86`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001fe86`

## string_xrefs

- `0x18002014f`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180020164`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18001fd9c`: `Failed to create shared GPU texture`
- `0x18001fe5f`: `Failed to create shared GPU texture handle`
- `0x18002017a`: `Failed to open Termsrv process`
- `0x18001ffa0`: `Rdp::Avenc::Umrdp::CRdpSharedTextureSurface::CreateDxSharedTexture`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
int __fastcall Rdp::Avenc::Umrdp::CRdpSharedTextureSurface::CreateDxSharedTexture(
        __int64 a1,
        __int64 **a2,
        int a3,
        int a4)
{
  __int64 *v6; // rcx
  __int64 v7; // rax
  unsigned int v8; // eax
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 **); // rcx
  int v10; // eax
  int v11; // eax
  __int64 *v12; // rcx
  __int64 v13; // rax
  unsigned int v14; // eax
  HANDLE v15; // rbx
  HANDLE v16; // rdi
  HANDLE CurrentProcess; // rax
  int v18; // r8d
  int v19; // r9d
  __int64 *v20; // rcx
  __int64 v21; // rdi
  __int64 (__fastcall ***v22)(_QWORD, GUID *, _QWORD *); // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rcx
  void **v26; // r14
  HANDLE v27; // r12
  void *v28; // r15
  DWORD LastError; // edi
  int result; // eax
  int dwDesiredAccess; // [rsp+20h] [rbp-E0h]
  const char *dwDesiredAccessa; // [rsp+20h] [rbp-E0h]
  const char *dwDesiredAccessb; // [rsp+20h] [rbp-E0h]
  const char *bInheritHandle; // [rsp+28h] [rbp-D8h]
  const char *bInheritHandlea; // [rsp+28h] [rbp-D8h]
  BOOL bInheritHandleb[2]; // [rsp+28h] [rbp-D8h]
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64 *); // [rsp+80h] [rbp-80h] BYREF
  HANDLE TargetHandle; // [rsp+88h] [rbp-78h] BYREF
  __int64 v39; // [rsp+90h] [rbp-70h] BYREF
  HANDLE hSourceHandle; // [rsp+98h] [rbp-68h] BYREF
  __int64 *v41; // [rsp+A0h] [rbp-60h] BYREF
  int v42; // [rsp+A8h] [rbp-58h] BYREF
  int v43; // [rsp+ACh] [rbp-54h] BYREF
  int v44; // [rsp+B0h] [rbp-50h] BYREF
  int v45; // [rsp+B4h] [rbp-4Ch] BYREF
  int v46; // [rsp+B8h] [rbp-48h] BYREF
  int v47; // [rsp+BCh] [rbp-44h] BYREF
  void *v48; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v49; // [rsp+C8h] [rbp-38h] BYREF
  const char *v50; // [rsp+D0h] [rbp-30h] BYREF
  const char *v51; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v52[2]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v53[6]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v54; // [rsp+108h] [rbp+8h]
  int v55; // [rsp+110h] [rbp+10h]
  int v56; // [rsp+114h] [rbp+14h]
  int v57; // [rsp+118h] [rbp+18h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v54 = 0;
  v53[0] = a3;
  v53[1] = a4;
  v53[4] = 87;
  v53[3] = 1;
  v53[2] = 1;
  v56 = 0;
  v57 = 2304;
  v53[5] = 1;
  v55 = 40;
  v37 = 0;
  v6 = *a2;
  v7 = **a2;
  v37 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, _DWORD *, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(v7 + 40))(
         v6,
         v53,
         0,
         &v37);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x31C,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\surface.cpp",
    (const char *)v8,
    (int)"Failed to create shared GPU texture",
    bInheritHandle);
  v39 = 0;
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 **))v37;
  if ( v37 )
  {
    v10 = (**v37)(v37, &GUID_9d8e1289_d7b3_465f_8126_250e349af85d, &v39);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v10,
        dwDesiredAccess);
    v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 **))v37;
  }
  else
  {
    v39 = 0;
  }
  v41 = 0;
  if ( v9 )
  {
    v11 = (**v9)(v9, &GUID_30961379_4609_4a41_998e_54fe567ee0c1, &v41);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v11,
        dwDesiredAccess);
    v12 = v41;
  }
  else
  {
    v12 = 0;
    v41 = 0;
  }
  hSourceHandle = 0;
  v13 = *v12;
  hSourceHandle = 0;
  v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD, HANDLE *))(v13 + 104))(
          v12,
          *(_QWORD *)(a1 + 96),
          2147483649LL,
          0,
          &hSourceHandle);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x331,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\surface.cpp",
    (const char *)v14,
    (int)"Failed to create shared GPU texture handle",
    bInheritHandlea);
  v15 = OpenProcess(0x1040u, 0, *(_DWORD *)(a1 + 88));
  v52[1] = v15;
  if ( (((unsigned __int64)v15 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0x33B,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\surface.cpp",
      "Failed to open Termsrv process",
      dwDesiredAccessa);
  TargetHandle = 0;
  v16 = hSourceHandle;
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(CurrentProcess, v16, v15, &TargetHandle, 0, 0, 2u) )
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0x34A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\surface.cpp",
      "Failed to Duplicate handle",
      dwDesiredAccessb);
  v20 = *a2;
  v21 = *(_QWORD *)(a1 + 120);
  *(_QWORD *)(a1 + 120) = *a2;
  if ( v20 )
    (*(void (__fastcall **)(__int64 *))(*v20 + 8))(v20);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  v22 = v37;
  v37 = 0;
  v23 = *(_QWORD *)(a1 + 104);
  *(_QWORD *)(a1 + 104) = v22;
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  v24 = v39;
  v39 = 0;
  v25 = *(_QWORD *)(a1 + 112);
  *(_QWORD *)(a1 + 112) = v24;
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  v26 = (void **)(a1 + 128);
  if ( (HANDLE *)(a1 + 128) != &TargetHandle )
  {
    v27 = TargetHandle;
    v28 = *v26;
    if ( (char *)*v26 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v28);
      SetLastError(LastError);
    }
    *v26 = v27;
    TargetHandle = 0;
  }
  if ( (unsigned int)dword_1800C1058 > 4 )
  {
    v48 = *v26;
    v42 = *(_DWORD *)(a1 + 80);
    v43 = *(_DWORD *)(a1 + 76);
    v44 = *(_DWORD *)(a1 + 72);
    v49 = *(_QWORD *)(a1 + 64);
    v45 = *(_DWORD *)(a1 + 56);
    v46 = *(_DWORD *)(*(_QWORD *)(a1 + 48) + 196LL);
    v50 = "Shared GPU texture";
    v51 = "Rdp::Avenc::Umrdp::CRdpSharedTextureSurface::CreateDxSharedTexture";
    v47 = 861;
    v52[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\surface.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)&word_1800AD8EE,
      v18,
      v19,
      (__int64)v52,
      (__int64)&v47,
      (__int64)&v51,
      (__int64)&v50,
      (__int64)&v46,
      (__int64)&v45,
      (__int64)&v49,
      (__int64)&v44,
      (__int64)&v43,
      (__int64)&v42,
      (__int64)&v48);
  }
  bInheritHandleb[0] = *(_DWORD *)(a1 + 56);
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"Shared GPU texture, Id %d",
    "Rdp::Avenc::Umrdp::CRdpSharedTextureSurface::CreateDxSharedTexture",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\surface.cpp",
    0x35Eu,
    *(_QWORD *)bInheritHandleb);
  if ( (char *)TargetHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TargetHandle);
  CloseHandle(v15);
  result = (_DWORD)hSourceHandle - 1;
  if ( (char *)hSourceHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    result = CloseHandle(hSourceHandle);
  if ( v41 )
    result = (*(__int64 (__fastcall **)(__int64 *))(*v41 + 16))(v41);
  if ( v39 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( v37 )
    return ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v37)[2])(v37);
  return result;
}

```

## disassembly

```asm
0x18001fd14  push    rbp
0x18001fd16  push    rbx
0x18001fd17  push    rsi
0x18001fd18  push    rdi
0x18001fd19  push    r12
0x18001fd1b  push    r13
0x18001fd1d  push    r14
0x18001fd1f  push    r15
0x18001fd21  lea     rbp, [rsp-38h]
0x18001fd26  sub     rsp, 138h
0x18001fd2d  mov     rax, cs:__security_cookie
0x18001fd34  xor     rax, rsp
0x18001fd37  mov     [rbp+70h+var_50], rax
0x18001fd3b  mov     r14, rdx
0x18001fd3e  mov     rsi, rcx
0x18001fd41  xor     r13d, r13d
0x18001fd44  mov     [rbp+70h+var_68], r13
0x18001fd48  mov     [rbp+70h+var_80], r8d
0x18001fd4c  mov     [rbp+70h+var_7C], r9d
0x18001fd50  mov     [rbp+70h+var_70], 57h ; 'W'
0x18001fd57  lea     eax, [r13+1]
0x18001fd5b  mov     [rbp+70h+var_74], eax
0x18001fd5e  mov     [rbp+70h+var_78], eax
0x18001fd61  mov     [rbp+70h+var_5C], r13d
0x18001fd65  mov     [rbp+70h+var_58], 900h
0x18001fd6c  mov     [rbp+70h+var_6C], eax
0x18001fd6f  mov     [rbp+70h+var_60], 28h ; '('
0x18001fd76  mov     [rbp+70h+var_F0], r13
0x18001fd7a  mov     rcx, [rdx]
0x18001fd7d  mov     rax, [rcx]
0x18001fd80  mov     [rbp+70h+var_F0], r13
0x18001fd84  lea     r9, [rbp+70h+var_F0]
0x18001fd88  xor     r8d, r8d
0x18001fd8b  lea     rdx, [rbp+70h+var_80]
0x18001fd8f  mov     rax, [rax+28h]
0x18001fd93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd98  mov     rcx, [rbp+78h]; this
0x18001fd9c  lea     rdx, aFailedToCreate_0; "Failed to create shared GPU texture"
0x18001fda3  mov     qword ptr [rsp+170h+dwDesiredAccess], rdx; int
0x18001fda8  mov     r9d, eax; char *
0x18001fdab  lea     r15, aOnecoreuapTerm_28; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001fdb2  mov     r8, r15; unsigned int
0x18001fdb5  mov     edx, 31Ch; void *
0x18001fdba  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001fdbf  nop
0x18001fdc0  mov     [rbp+70h+var_E0], r13
0x18001fdc4  mov     rcx, [rbp+70h+var_F0]
0x18001fdc8  test    rcx, rcx
0x18001fdcb  jz      short loc_18001FDF5
0x18001fdcd  mov     rax, [rcx]
0x18001fdd0  lea     r8, [rbp+70h+var_E0]
0x18001fdd4  lea     rdx, _GUID_9d8e1289_d7b3_465f_8126_250e349af85d
0x18001fddb  mov     rax, [rax]
0x18001fdde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fde3  mov     rcx, [rbp+78h]; this
0x18001fde7  test    eax, eax
0x18001fde9  js      loc_18002014C
0x18001fdef  mov     rcx, [rbp+70h+var_F0]
0x18001fdf3  jmp     short loc_18001FDF9
0x18001fdf5  mov     [rbp+70h+var_E0], r13
0x18001fdf9  mov     [rbp+70h+var_D0], r13
0x18001fdfd  test    rcx, rcx
0x18001fe00  jz      short loc_18001FE2A
0x18001fe02  mov     rax, [rcx]
0x18001fe05  lea     r8, [rbp+70h+var_D0]
0x18001fe09  lea     rdx, _GUID_30961379_4609_4a41_998e_54fe567ee0c1
0x18001fe10  mov     rax, [rax]
0x18001fe13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe18  mov     rcx, [rbp+78h]; this
0x18001fe1c  test    eax, eax
0x18001fe1e  js      loc_180020161
0x18001fe24  mov     rcx, [rbp+70h+var_D0]
0x18001fe28  jmp     short loc_18001FE31
0x18001fe2a  mov     rcx, r13
0x18001fe2d  mov     [rbp+70h+var_D0], rcx
0x18001fe31  mov     [rbp+70h+hSourceHandle], r13
0x18001fe35  mov     rax, [rcx]
0x18001fe38  mov     [rbp+70h+hSourceHandle], r13
0x18001fe3c  lea     rdx, [rbp+70h+hSourceHandle]
0x18001fe40  mov     qword ptr [rsp+170h+dwDesiredAccess], rdx
0x18001fe45  xor     r9d, r9d
0x18001fe48  mov     r8d, 80000001h
0x18001fe4e  mov     rdx, [rsi+60h]
0x18001fe52  mov     rax, [rax+68h]
0x18001fe56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe5b  mov     rcx, [rbp+78h]; this
0x18001fe5f  lea     rdx, aFailedToCreate_6; "Failed to create shared GPU texture han"...
0x18001fe66  mov     qword ptr [rsp+170h+dwDesiredAccess], rdx; char *
0x18001fe6b  mov     r9d, eax; char *
0x18001fe6e  mov     r8, r15; unsigned int
0x18001fe71  mov     edx, 331h; void *
0x18001fe76  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001fe7b  mov     r8d, [rsi+58h]; dwProcessId
0x18001fe7f  xor     edx, edx; bInheritHandle
0x18001fe81  mov     ecx, 1040h; dwDesiredAccess
0x18001fe86  call    cs:__imp_OpenProcess
0x18001fe8c  mov     rbx, rax
0x18001fe8f  mov     [rbp+70h+var_88], rax
0x18001fe93  inc     rax
0x18001fe96  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001fe9c  jz      loc_180020176
0x18001fea2  mov     [rbp+70h+TargetHandle], r13
0x18001fea6  mov     rdi, [rbp+70h+hSourceHandle]
0x18001feaa  call    cs:__imp_GetCurrentProcess
0x18001feb0  mov     [rsp+170h+dwOptions], 2; dwOptions
0x18001feb8  mov     [rsp+170h+bInheritHandle], r13d; bInheritHandle
0x18001febd  mov     [rsp+170h+dwDesiredAccess], r13d; char *
0x18001fec2  lea     r9, [rbp+70h+TargetHandle]; lpTargetHandle
0x18001fec6  mov     r8, rbx; hTargetProcessHandle
0x18001fec9  mov     rdx, rdi; hSourceHandle
0x18001fecc  mov     rcx, rax; hSourceProcessHandle
0x18001fecf  call    cs:__imp_DuplicateHandle
0x18001fed5  test    eax, eax
0x18001fed7  jz      loc_180020133
0x18001fedd  mov     rcx, [r14]
0x18001fee0  mov     rdi, [rsi+78h]
0x18001fee4  mov     [rsi+78h], rcx
0x18001fee8  test    rcx, rcx
0x18001feeb  jz      short loc_18001FEF9
0x18001feed  mov     rax, [rcx]
0x18001fef0  mov     rax, [rax+8]
0x18001fef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fef9  test    rdi, rdi
0x18001fefc  jz      short loc_18001FF0E
0x18001fefe  mov     rax, [rdi]
0x18001ff01  mov     rcx, rdi
0x18001ff04  mov     rax, [rax+10h]
0x18001ff08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff0d  nop
0x18001ff0e  mov     rax, [rbp+70h+var_F0]
0x18001ff12  mov     [rbp+70h+var_F0], r13
0x18001ff16  mov     rcx, [rsi+68h]
0x18001ff1a  mov     [rsi+68h], rax
0x18001ff1e  test    rcx, rcx
0x18001ff21  jz      short loc_18001FF30
0x18001ff23  mov     rax, [rcx]
0x18001ff26  mov     rax, [rax+10h]
0x18001ff2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff2f  nop
0x18001ff30  mov     rax, [rbp+70h+var_E0]
0x18001ff34  mov     [rbp+70h+var_E0], r13
0x18001ff38  mov     rcx, [rsi+70h]
0x18001ff3c  mov     [rsi+70h], rax
0x18001ff40  test    rcx, rcx
0x18001ff43  jz      short loc_18001FF52
0x18001ff45  mov     rax, [rcx]
0x18001ff48  mov     rax, [rax+10h]
0x18001ff4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff51  nop
0x18001ff52  lea     r14, [rsi+80h]
0x18001ff59  lea     rax, [rbp+70h+TargetHandle]
0x18001ff5d  cmp     r14, rax
0x18001ff60  jz      short loc_18001FF9A
0x18001ff62  mov     r12, [rbp+70h+TargetHandle]
0x18001ff66  mov     r15, [r14]
0x18001ff69  lea     rax, [r15-1]
0x18001ff6d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001ff71  ja      short loc_18001FF8C
0x18001ff73  call    cs:__imp_GetLastError
0x18001ff79  mov     edi, eax
0x18001ff7b  mov     rcx, r15; hObject
0x18001ff7e  call    cs:__imp_CloseHandle
0x18001ff84  mov     ecx, edi; dwErrCode
0x18001ff86  call    cs:__imp_SetLastError
0x18001ff8c  mov     [r14], r12
0x18001ff8f  mov     [rbp+70h+TargetHandle], r13
0x18001ff93  lea     r15, aOnecoreuapTerm_28; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001ff9a  mov     eax, cs:dword_1800C1058
0x18001ffa0  lea     rdi, aRdpAvencUmrdpC_5; "Rdp::Avenc::Umrdp::CRdpSharedTextureSur"...
0x18001ffa7  cmp     eax, 4
0x18001ffaa  jbe     loc_180020074
0x18001ffb0  mov     rax, [r14]
0x18001ffb3  mov     [rbp+70h+var_B0], rax
0x18001ffb7  mov     eax, [rsi+50h]
0x18001ffba  mov     [rbp+70h+var_C8], eax
0x18001ffbd  mov     eax, [rsi+4Ch]
0x18001ffc0  mov     [rbp+70h+var_C4], eax
0x18001ffc3  mov     eax, [rsi+48h]
0x18001ffc6  mov     [rbp+70h+var_C0], eax
0x18001ffc9  mov     rax, [rsi+40h]
0x18001ffcd  mov     [rbp+70h+var_A8], rax
0x18001ffd1  mov     eax, [rsi+38h]
0x18001ffd4  mov     [rbp+70h+var_BC], eax
0x18001ffd7  mov     rax, [rsi+30h]
0x18001ffdb  mov     ecx, [rax+0C4h]
0x18001ffe1  mov     [rbp+70h+var_B8], ecx
0x18001ffe4  lea     rax, aSharedGpuTextu_0; "Shared GPU texture"
0x18001ffeb  mov     [rbp+70h+var_A0], rax
0x18001ffef  mov     [rbp+70h+var_98], rdi
0x18001fff3  mov     [rbp+70h+var_B4], 35Dh
0x18001fffa  mov     [rbp+70h+var_90], r15
0x18001fffe  lea     rax, [rbp+70h+var_B0]
0x180020002  mov     [rsp+170h+var_100], rax
0x180020007  lea     rax, [rbp+70h+var_C8]
0x18002000b  mov     [rsp+170h+var_108], rax
0x180020010  lea     rax, [rbp+70h+var_C4]
0x180020014  mov     [rsp+170h+var_110], rax
0x180020019  lea     rax, [rbp+70h+var_C0]
0x18002001d  mov     [rsp+170h+var_118], rax
0x180020022  lea     rax, [rbp+70h+var_A8]
0x180020026  mov     [rsp+170h+var_120], rax
0x18002002b  lea     rax, [rbp+70h+var_BC]
0x18002002f  mov     [rsp+170h+var_128], rax
0x180020034  lea     rax, [rbp+70h+var_B8]
0x180020038  mov     [rsp+170h+var_130], rax
0x18002003d  lea     rax, [rbp+70h+var_A0]
0x180020041  mov     [rsp+170h+var_138], rax
0x180020046  lea     rax, [rbp+70h+var_98]
0x18002004a  mov     qword ptr [rsp+170h+dwOptions], rax
0x18002004f  lea     rax, [rbp+70h+var_B4]
0x180020053  mov     qword ptr [rsp+170h+bInheritHandle], rax
0x180020058  lea     rax, [rbp+70h+var_90]
0x18002005c  mov     qword ptr [rsp+170h+dwDesiredAccess], rax
0x180020061  lea     rdx, word_1800AD8EE
0x180020068  lea     rcx, dword_1800C1058
0x18002006f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByVal@$07@@U2@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByVal@$07@@4445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180020074  mov     eax, [rsi+38h]
0x180020077  mov     [rsp+170h+bInheritHandle], eax
0x18002007b  mov     [rsp+170h+dwDesiredAccess], 35Eh; unsigned int
0x180020083  mov     r9, r15; char *
0x180020086  mov     r8, rdi; char *
0x180020089  lea     rdx, aSharedGpuTextu; "Shared GPU texture, Id %d"
0x180020090  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180020097  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18002009c  nop
0x18002009d  mov     rcx, [rbp+70h+TargetHandle]; hObject
0x1800200a1  lea     rax, [rcx-1]
0x1800200a5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800200a9  ja      short loc_1800200B2
0x1800200ab  call    cs:__imp_CloseHandle
0x1800200b1  nop
0x1800200b2  mov     rcx, rbx; hObject
0x1800200b5  call    cs:__imp_CloseHandle
0x1800200bb  nop
0x1800200bc  mov     rcx, [rbp+70h+hSourceHandle]; hObject
0x1800200c0  lea     rax, [rcx-1]
0x1800200c4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800200c8  ja      short loc_1800200D1
0x1800200ca  call    cs:__imp_CloseHandle
0x1800200d0  nop
0x1800200d1  mov     rcx, [rbp+70h+var_D0]
0x1800200d5  test    rcx, rcx
0x1800200d8  jz      short loc_1800200E7
0x1800200da  mov     rax, [rcx]
0x1800200dd  mov     rax, [rax+10h]
0x1800200e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200e6  nop
0x1800200e7  mov     rcx, [rbp+70h+var_E0]
0x1800200eb  test    rcx, rcx
0x1800200ee  jz      short loc_1800200FD
0x1800200f0  mov     rax, [rcx]
0x1800200f3  mov     rax, [rax+10h]
0x1800200f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200fc  nop
0x1800200fd  mov     rcx, [rbp+70h+var_F0]
0x180020101  test    rcx, rcx
0x180020104  jz      short loc_180020113
0x180020106  mov     rax, [rcx]
0x180020109  mov     rax, [rax+10h]
0x18002010d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020112  nop
0x180020113  mov     rcx, [rbp+70h+var_50]
0x180020117  xor     rcx, rsp; StackCookie
0x18002011a  call    __security_check_cookie
0x18002011f  add     rsp, 138h
0x180020126  pop     r15
0x180020128  pop     r14
0x18002012a  pop     r13
0x18002012c  pop     r12
0x18002012e  pop     rdi
0x18002012f  pop     rsi
0x180020130  pop     rbx
0x180020131  pop     rbp
0x180020132  retn
0x180020133  mov     rcx, [rbp+78h]; this
0x180020137  lea     r9, aFailedToDuplic_0; "Failed to Duplicate handle"
0x18002013e  mov     r8, r15; unsigned int
0x180020141  mov     edx, 34Ah; void *
0x180020146  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18002014c  mov     r9d, eax; char *
0x18002014f  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180020156  mov     edx, 1CBEh; void *
0x18002015b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020161  mov     r9d, eax; char *
0x180020164  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002016b  mov     edx, 1CBEh; void *
0x180020170  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180020176  mov     rcx, [rbp+78h]; this
0x18002017a  lea     r9, aFailedToOpenTe; "Failed to open Termsrv process"
0x180020181  mov     r8, r15; unsigned int
0x180020184  mov     edx, 33Bh; void *
0x180020189  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
```
