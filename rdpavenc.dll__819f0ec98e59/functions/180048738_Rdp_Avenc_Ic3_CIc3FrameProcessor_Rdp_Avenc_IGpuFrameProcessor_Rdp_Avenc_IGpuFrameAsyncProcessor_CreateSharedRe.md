# Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::CreateSharedResources(std::span<Rdp::Avenc::AVENC_SHARED_RESOURCE,-1> &&,Rdp::Avenc::AVENC_RESOURCE_TYPE)

- ea: `0x180048738`
- end: `0x180048f23`
- name: `?CreateSharedResources@?$CIc3FrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@UIGpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAAJ$$QEAV?$span@UAVENC_SHARED_RESOURCE@Avenc@Rdp@@$0?0@std@@W4AVENC_RESOURCE_TYPE@34@@Z`
- size: `2027`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180049198`
- `0x18004a6f0`

## callees

- `0x18000154c`
- `0x1800021e4`
- `0x180006580`
- `0x1800080cc`
- `0x18000e848`
- `0x18000ec04`
- `0x180019998`
- `0x1800199cc`
- `0x1800241ac`
- `0x180048738`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048bf3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048d3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048bf3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180048d3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048be0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048d2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048be0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048d2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180048dcc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180048dcc`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180048df2`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180048df2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048beb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048d36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048e1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048e3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048beb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048d36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048e1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048e3b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180048838`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180048838`

## string_xrefs

- `0x180048ed6`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180048c5f`: `Failed to create shared GPU texture handle`
- `0x180048795`: `CreateSharedResources`
- `0x180048e4d`: `Unable to create resources for stopped frame processor.`
- `0x180048f0d`: `Failed to open WUDFHost process`
- `0x1800487a1`: `Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyncProcessor>::CreateSharedResources`
- `0x180048811`: `Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyncProcessor>::CreateSharedResources`
- `0x180048b5f`: `Failed to create shared texture`
- `0x180048ada`: `Failed to create texture desc for shared resources`
- `0x180048d8e`: `Failed to create shared GPU fence handle`
- `0x180048ce4`: `Failed to create shared fence.`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::CreateSharedResources(
        __int64 a1,
        __int64 *a2,
        int a3,
        int a4)
{
  char *v6; // rbx
  __int64 v7; // rdx
  int v8; // ecx
  bool v9; // cl
  unsigned int v10; // eax
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rdi
  int v14; // edi
  __int64 v15; // rcx
  unsigned int v16; // eax
  int v17; // ecx
  __int64 v18; // rax
  int v19; // ecx
  __int64 v20; // r14
  __int64 v21; // rax
  __int64 *v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // eax
  int v25; // eax
  HANDLE v26; // r13
  DWORD v27; // edi
  unsigned int v28; // edi
  __int64 *v29; // rcx
  __int64 v30; // rax
  unsigned int v31; // eax
  HANDLE v32; // r13
  DWORD LastError; // edi
  unsigned int v34; // eax
  HANDLE v35; // rdi
  HANDLE CurrentProcess; // rax
  HANDLE v37; // rax
  const char *v39; // r9
  int v40; // edx
  const char *dwDesiredAccess; // [rsp+20h] [rbp-128h]
  int dwDesiredAccessa; // [rsp+20h] [rbp-128h]
  const char *dwDesiredAccessb; // [rsp+20h] [rbp-128h]
  const char *bInheritHandle; // [rsp+28h] [rbp-120h]
  const char *bInheritHandlea; // [rsp+28h] [rbp-120h]
  const char *bInheritHandleb; // [rsp+28h] [rbp-120h]
  const char *bInheritHandlec; // [rsp+28h] [rbp-120h]
  HANDLE hObject; // [rsp+60h] [rbp-E8h] BYREF
  const char *v49; // [rsp+68h] [rbp-E0h] BYREF
  int v50; // [rsp+70h] [rbp-D8h]
  HANDLE TargetHandle; // [rsp+78h] [rbp-D0h] BYREF
  __int64 v52; // [rsp+80h] [rbp-C8h] BYREF
  int v53; // [rsp+88h] [rbp-C0h]
  const char *v54; // [rsp+90h] [rbp-B8h] BYREF
  const char *v55; // [rsp+98h] [rbp-B0h] BYREF
  _QWORD v56[2]; // [rsp+A0h] [rbp-A8h] BYREF
  _OWORD v57[3]; // [rsp+B0h] [rbp-98h] BYREF
  _DWORD v58[12]; // [rsp+E0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v50 = a3;
  v53 = 0;
  if ( *(_QWORD *)(a1 + 176) )
  {
    if ( (unsigned int)dword_1800C1058 > 4 )
    {
      LODWORD(TargetHandle) = a3;
      hObject = "CreateSharedResources";
      v49 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyncP"
            "rocessor>::CreateSharedResources";
      LODWORD(v52) = 467;
      v54 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)byte_1800B0C6D,
        a3,
        a4,
        (__int64)&v54,
        (__int64)&v52,
        (__int64)&v49,
        (__int64)&hObject,
        (__int64)&TargetHandle);
    }
    v6 = (char *)OpenProcess(0x1040u, 0, *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 176) + 104LL) + 280LL));
    v56[1] = v6;
    if ( (unsigned __int64)(v6 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::in1diag3::Throw_GetLastErrorMsg(
        retaddr,
        (void *)0x1DF,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
        "Failed to open WUDFHost process",
        dwDesiredAccess);
    v7 = *(_QWORD *)(a1 + 176);
    v8 = *(_DWORD *)(*(_QWORD *)(v7 + 104) + 284LL);
    LODWORD(hObject) = 8;
    HIWORD(hObject) = 0;
    v9 = v8 == 2;
    BYTE4(hObject) = v9;
    BYTE5(hObject) = v9;
    if ( *(_BYTE *)(*(_QWORD *)(v7 + 104) + 289LL) && v9 )
      *(_WORD *)((char *)&hObject + 5) = 256;
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64, HANDLE *))(**(_QWORD **)(a1 + 192) + 280LL))(
            *(_QWORD *)(a1 + 192),
            qword_18009A1C8,
            8,
            &hObject);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x1F1,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
      (const char *)v10,
      (int)"Failed to set FrameProcessorPrivateDataId private data on encoder device",
      bInheritHandle);
    v13 = *(_QWORD *)(a1 + 208);
    if ( v13 )
    {
      v14 = *(_DWORD *)(v13 + 272);
    }
    else
    {
      v15 = *(_QWORD *)(a1 + 216);
      if ( v15 )
      {
        memset(v58, 0, 28);
        v16 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v15 + 128LL))(v15, v58);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x1FF,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
          (const char *)v16,
          (int)"Failed to get video format from video source provider",
          bInheritHandlea);
        if ( v58[0] == 842094158 )
        {
          v14 = 103;
        }
        else
        {
          if ( v58[0] != 1095911234 )
          {
            v39 = (const char *)(unsigned int)wil::verify_hresult<long>(2147942450LL);
            LODWORD(bInheritHandlea) = v40;
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x20B,
              (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
              v39,
              (int)"The given fcc format is not supported: %08X",
              bInheritHandlea);
          }
          v14 = 87;
        }
      }
      else
      {
        v14 = 0;
      }
    }
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      LODWORD(v52) = v50;
      LODWORD(TargetHandle) = v14;
      LODWORD(v49) = *((_DWORD *)a2 + 2);
      v54 = "Creating resources";
      v55 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyncP"
            "rocessor>::CreateSharedResources";
      LODWORD(hObject) = 532;
      v56[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)byte_1800B0C19,
        v11,
        v12,
        (__int64)v56,
        (__int64)&hObject,
        (__int64)&v55,
        (__int64)&v54,
        (__int64)&v49,
        (__int64)&TargetHandle,
        (__int64)&v52);
    }
    memset(v57, 0, 44);
    v17 = v50;
    if ( !v50 )
    {
      v18 = *(_QWORD *)(a1 + 176);
      v19 = *(_DWORD *)(v18 + 144);
      LODWORD(v57[0]) = (*(_DWORD *)(v18 + 140) + 1) & 0xFFFFFFFE;
      DWORD1(v57[0]) = (v19 + 1) & 0xFFFFFFFE;
      LODWORD(v57[1]) = v14;
      HIDWORD(v57[1]) = 0;
      *((_QWORD *)&v57[0] + 1) = 0x100000001LL;
      *(_QWORD *)&v57[2] = 136;
      *(_QWORD *)((char *)&v57[1] + 4) = 1;
      DWORD2(v57[2]) = 2050;
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x21E,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
        0,
        (int)"Failed to create texture desc for shared resources",
        bInheritHandlea);
      v17 = v50;
    }
    v20 = *a2;
    v21 = *a2 + 32 * a2[1];
    v54 = (const char *)v21;
    while ( v20 != v21 )
    {
      hObject = 0;
      if ( v17 )
      {
        if ( v17 == 1 )
        {
          v49 = 0;
          v29 = *(__int64 **)(a1 + 192);
          v30 = *v29;
          v49 = 0;
          v31 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, GUID *, const char **))(v30 + 544))(
                  v29,
                  0,
                  2,
                  &GUID_affde9d1_1df7_4bb7_8a34_0f46251dab80,
                  &v49);
          wil::details::in1diag3::Throw_IfFailedMsg(
            retaddr,
            (void *)0x250,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
            (const char *)v31,
            (int)"Failed to create shared fence.",
            bInheritHandlea);
          v56[0] = v49;
          v55 = *(const char **)(*(_QWORD *)v49 + 56LL);
          v32 = hObject;
          if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          {
            LastError = GetLastError();
            CloseHandle(v32);
            SetLastError(LastError);
          }
          hObject = 0;
          v34 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, HANDLE *))v55)(
                  v56[0],
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 176) + 104LL) + 296LL),
                  0x10000000,
                  0,
                  &hObject);
          wil::details::in1diag3::Throw_IfFailedMsg(
            retaddr,
            (void *)0x25B,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
            (const char *)v34,
            (int)"Failed to create shared GPU fence handle",
            bInheritHandlec);
          *(_DWORD *)v20 = 32;
          *(_QWORD *)(v20 + 16) = v49;
          *(_DWORD *)(v20 + 24) = 1;
        }
      }
      else
      {
        v49 = 0;
        v22 = *(__int64 **)(a1 + 192);
        v23 = *v22;
        v49 = 0;
        v24 = (*(__int64 (__fastcall **)(__int64 *, _OWORD *, _QWORD, const char **))(v23 + 40))(v22, v57, 0, &v49);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x230,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
          (const char *)v24,
          (int)"Failed to create shared texture",
          bInheritHandlea);
        v52 = 0;
        v25 = (**(__int64 (__fastcall ***)(const char *, GUID *, __int64 *))v49)(
                v49,
                &GUID_30961379_4609_4a41_998e_54fe567ee0c1,
                &v52);
        if ( v25 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1CBE,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
            (const char *)(unsigned int)v25,
            dwDesiredAccessa);
        v56[0] = v52;
        v55 = *(const char **)(*(_QWORD *)v52 + 104LL);
        v26 = hObject;
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          v27 = GetLastError();
          CloseHandle(v26);
          SetLastError(v27);
        }
        hObject = 0;
        v28 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, HANDLE *))v55)(
                v56[0],
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 176) + 104LL) + 296LL),
                2147483649LL,
                0,
                &hObject);
        if ( v52 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
        wil::details::in1diag3::Throw_IfFailedMsg(
          retaddr,
          (void *)0x23B,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
          (const char *)v28,
          (int)"Failed to create shared GPU texture handle",
          bInheritHandleb);
        *(_DWORD *)v20 = 32;
        *(_QWORD *)(v20 + 16) = v49;
        *(_DWORD *)(v20 + 24) = 0;
        v53 |= 1u;
      }
      TargetHandle = 0;
      v35 = hObject;
      CurrentProcess = GetCurrentProcess();
      if ( !DuplicateHandle(CurrentProcess, v35, v6, &TargetHandle, 0, 0, 2u) )
        wil::details::in1diag3::Throw_GetLastErrorMsg(
          retaddr,
          (void *)0x275,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
          "Failed to duplicate shared resource handle while creating shared resources",
          dwDesiredAccessb);
      v37 = TargetHandle;
      TargetHandle = 0;
      *(_QWORD *)(v20 + 8) = v37;
      if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      v20 += 32;
      v21 = (__int64)v54;
      v17 = v50;
    }
    CloseHandle(v6);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x1CC,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
      (const char *)0x8000FFFFLL,
      (int)"Unable to create resources for stopped frame processor.",
      bInheritHandle);
    return 0;
  }
}

```

## disassembly

```asm
0x180048738  mov     r11, rsp
0x18004873b  mov     [r11+18h], rbx
0x18004873f  push    rsi
0x180048740  push    rdi
0x180048741  push    r13
0x180048743  push    r14
0x180048745  push    r15
0x180048747  sub     rsp, 120h
0x18004874e  mov     rax, cs:__security_cookie
0x180048755  xor     rax, rsp
0x180048758  mov     [rsp+148h+var_38], rax
0x180048760  mov     [rsp+148h+var_D8], r8d
0x180048765  mov     r13, rdx
0x180048768  mov     r15, rcx
0x18004876b  xor     edi, edi
0x18004876d  mov     [rsp+148h+var_C0], edi
0x180048774  cmp     [rcx+0B0h], rdi
0x18004877b  jz      loc_180048E45
0x180048781  mov     eax, cs:dword_1800C1058
0x180048787  cmp     eax, 4
0x18004878a  jbe     loc_180048811
0x180048790  mov     dword ptr [rsp+148h+TargetHandle], r8d
0x180048795  lea     rax, aCreatesharedre; "CreateSharedResources"
0x18004879c  mov     [rsp+148h+hObject], rax
0x1800487a1  lea     r14, aRdpAvencIc3Cic_11; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x1800487a8  mov     [rsp+148h+var_E0], r14
0x1800487ad  mov     dword ptr [rsp+148h+var_C8], 1D3h
0x1800487b8  lea     rsi, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800487bf  mov     [r11-0B8h], rsi
0x1800487c6  lea     rax, [rsp+148h+TargetHandle]
0x1800487cb  mov     [rsp+148h+var_108], rax
0x1800487d0  lea     rax, [rsp+148h+hObject]
0x1800487d5  mov     [rsp+148h+var_110], rax
0x1800487da  lea     rax, [rsp+148h+var_E0]
0x1800487df  mov     qword ptr [rsp+148h+dwOptions], rax
0x1800487e4  lea     rax, [r11-0C8h]
0x1800487eb  mov     qword ptr [rsp+148h+bInheritHandle], rax
0x1800487f0  lea     rax, [r11-0B8h]
0x1800487f7  mov     qword ptr [rsp+148h+dwDesiredAccess], rax
0x1800487fc  lea     rdx, byte_1800B0C6D
0x180048803  lea     rcx, dword_1800C1058
0x18004880a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18004880f  jmp     short loc_18004881F
0x180048811  lea     r14, aRdpAvencIc3Cic_11; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x180048818  lea     rsi, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004881f  mov     rax, [r15+0B0h]
0x180048826  mov     r8, [rax+68h]
0x18004882a  mov     r8d, [r8+118h]; dwProcessId
0x180048831  xor     edx, edx; bInheritHandle
0x180048833  mov     ecx, 1040h; dwDesiredAccess
0x180048838  call    cs:__imp_OpenProcess
0x18004883e  mov     rbx, rax
0x180048841  mov     [rsp+148h+var_A0], rax
0x180048849  dec     rax
0x18004884c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180048850  ja      loc_180048F05
0x180048856  mov     rdx, [r15+0B0h]
0x18004885d  mov     rax, [rdx+68h]
0x180048861  mov     ecx, [rax+11Ch]
0x180048867  mov     r8d, 8
0x18004886d  mov     dword ptr [rsp+148h+hObject], r8d
0x180048872  mov     word ptr [rsp+148h+hObject+6], di
0x180048877  cmp     ecx, 2
0x18004887a  setz    cl
0x18004887d  mov     byte ptr [rsp+148h+hObject+4], cl
0x180048881  mov     byte ptr [rsp+148h+hObject+5], cl
0x180048885  mov     rax, [rdx+68h]
0x180048889  cmp     [rax+121h], dil
0x180048890  jz      short loc_18004889D
0x180048892  test    cl, cl
0x180048894  jz      short loc_18004889D
0x180048896  mov     word ptr [rsp+148h+hObject+5], 100h
0x18004889d  mov     rcx, [r15+0C0h]
0x1800488a4  mov     rax, [rcx]
0x1800488a7  lea     r9, [rsp+148h+hObject]
0x1800488ac  lea     rdx, qword_18009A1C8
0x1800488b3  mov     rax, [rax+118h]
0x1800488ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488bf  mov     rcx, [rsp+148h]; this
0x1800488c7  lea     rdx, aFailedToSetFra; "Failed to set FrameProcessorPrivateData"...
0x1800488ce  mov     qword ptr [rsp+148h+dwDesiredAccess], rdx; int
0x1800488d3  mov     r9d, eax; char *
0x1800488d6  mov     r8, rsi; unsigned int
0x1800488d9  mov     edx, 1F1h; void *
0x1800488de  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800488e3  mov     rdi, [r15+0D0h]
0x1800488ea  test    rdi, rdi
0x1800488ed  jz      short loc_1800488FA
0x1800488ef  mov     edi, [rdi+110h]
0x1800488f5  jmp     loc_18004897F
0x1800488fa  mov     rcx, [r15+0D8h]
0x180048901  test    rcx, rcx
0x180048904  jz      short loc_18004897D
0x180048906  xorps   xmm0, xmm0
0x180048909  movups  xmmword ptr [rsp+148h+var_68], xmm0
0x180048911  movups  xmmword ptr [rsp+148h+var_68+0Ch], xmm0
0x180048919  mov     rax, [rcx]
0x18004891c  lea     rdx, [rsp+148h+var_68]
0x180048924  mov     rax, [rax+80h]
0x18004892b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048930  mov     rcx, [rsp+148h]; this
0x180048938  lea     rdx, aFailedToGetVid; "Failed to get video format from video s"...
0x18004893f  mov     qword ptr [rsp+148h+dwDesiredAccess], rdx; int
0x180048944  mov     r9d, eax; char *
0x180048947  mov     r8, rsi; unsigned int
0x18004894a  mov     edx, 1FFh; void *
0x18004894f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180048954  mov     edx, [rsp+148h+var_68]
0x18004895b  cmp     edx, 3231564Eh
0x180048961  jz      short loc_180048976
0x180048963  cmp     edx, 41524742h
0x180048969  jnz     loc_180048EA0
0x18004896f  mov     edi, 57h ; 'W'
0x180048974  jmp     short loc_18004897F
0x180048976  mov     edi, 67h ; 'g'
0x18004897b  jmp     short loc_18004897F
0x18004897d  xor     edi, edi
0x18004897f  mov     eax, cs:dword_1800C1058
0x180048985  cmp     eax, 5
0x180048988  jbe     loc_180048A31
0x18004898e  mov     eax, [rsp+148h+var_D8]
0x180048992  mov     dword ptr [rsp+148h+var_C8], eax
0x180048999  mov     dword ptr [rsp+148h+TargetHandle], edi
0x18004899d  mov     eax, [r13+8]
0x1800489a1  mov     dword ptr [rsp+148h+var_E0], eax
0x1800489a5  lea     rax, aCreatingResour; "Creating resources"
0x1800489ac  mov     [rsp+148h+var_B8], rax
0x1800489b4  mov     [rsp+148h+var_B0], r14
0x1800489bc  mov     dword ptr [rsp+148h+hObject], 214h
0x1800489c4  mov     [rsp+148h+var_A8], rsi
0x1800489cc  lea     rax, [rsp+148h+var_C8]
0x1800489d4  mov     [rsp+148h+var_F8], rax
0x1800489d9  lea     rax, [rsp+148h+TargetHandle]
0x1800489de  mov     [rsp+148h+var_100], rax
0x1800489e3  lea     rax, [rsp+148h+var_E0]
0x1800489e8  mov     [rsp+148h+var_108], rax
0x1800489ed  lea     rax, [rsp+148h+var_B8]
0x1800489f5  mov     [rsp+148h+var_110], rax
0x1800489fa  lea     rax, [rsp+148h+var_B0]
0x180048a02  mov     qword ptr [rsp+148h+dwOptions], rax
0x180048a07  lea     rax, [rsp+148h+hObject]
0x180048a0c  mov     qword ptr [rsp+148h+bInheritHandle], rax; char *
0x180048a11  lea     rax, [rsp+148h+var_A8]
0x180048a19  mov     qword ptr [rsp+148h+dwDesiredAccess], rax
0x180048a1e  lea     rdx, byte_1800B0C19
0x180048a25  lea     rcx, dword_1800C1058
0x180048a2c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180048a31  xorps   xmm0, xmm0
0x180048a34  movups  [rsp+148h+var_98], xmm0
0x180048a3c  movups  [rsp+148h+var_88], xmm0
0x180048a44  movups  [rsp+148h+var_88+0Ch], xmm0
0x180048a4c  mov     ecx, [rsp+148h+var_D8]
0x180048a50  xor     r8d, r8d
0x180048a53  test    ecx, ecx
0x180048a55  jnz     loc_180048AFA
0x180048a5b  mov     rax, [r15+0B0h]
0x180048a62  mov     ecx, [rax+90h]
0x180048a68  mov     eax, [rax+8Ch]
0x180048a6e  inc     eax
0x180048a70  mov     edx, 0FFFFFFFEh
0x180048a75  and     eax, edx
0x180048a77  mov     dword ptr [rsp+148h+var_98], eax
0x180048a7e  lea     eax, [rcx+1]
0x180048a81  and     eax, edx
0x180048a83  mov     dword ptr [rsp+148h+var_98+4], eax
0x180048a8a  mov     dword ptr [rsp+148h+var_88], edi
0x180048a91  mov     dword ptr [rsp+148h+var_88+0Ch], r8d
0x180048a99  mov     dword ptr [rsp+148h+var_98+0Ch], 1
0x180048aa4  mov     dword ptr [rsp+148h+var_98+8], 1
0x180048aaf  mov     [rsp+148h+var_78], 88h
0x180048abb  mov     qword ptr [rsp+148h+var_88+4], 1
0x180048ac7  mov     [rsp+148h+var_70], 802h
0x180048ad2  mov     rcx, [rsp+148h]; this
0x180048ada  lea     rax, aFailedToCreate_7; "Failed to create texture desc for share"...
0x180048ae1  mov     qword ptr [rsp+148h+dwDesiredAccess], rax; int
0x180048ae6  xor     r9d, r9d; char *
0x180048ae9  mov     r8, rsi; unsigned int
0x180048aec  mov     edx, 21Eh; void *
0x180048af1  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180048af6  mov     ecx, [rsp+148h+var_D8]
0x180048afa  mov     r14, [r13+0]
0x180048afe  mov     rax, [r13+8]
0x180048b02  shl     rax, 5
0x180048b06  add     rax, r14
0x180048b09  mov     [rsp+148h+var_B8], rax
0x180048b11  xor     r13d, r13d
0x180048b14  cmp     r14, rax
0x180048b17  jz      loc_180048E38
0x180048b1d  mov     [rsp+148h+hObject], r13
0x180048b22  test    ecx, ecx
0x180048b24  jnz     loc_180048C9C
0x180048b2a  mov     [rsp+148h+var_E0], r13
0x180048b2f  mov     rcx, [r15+0C0h]
0x180048b36  mov     rax, [rcx]
0x180048b39  mov     [rsp+148h+var_E0], r13
0x180048b3e  lea     r9, [rsp+148h+var_E0]
0x180048b43  xor     r8d, r8d
0x180048b46  lea     rdx, [rsp+148h+var_98]
0x180048b4e  mov     rax, [rax+28h]
0x180048b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b57  mov     rcx, [rsp+148h]; this
0x180048b5f  lea     rdx, aFailedToCreate_5; "Failed to create shared texture"
0x180048b66  mov     qword ptr [rsp+148h+dwDesiredAccess], rdx; int
0x180048b6b  mov     r9d, eax; char *
0x180048b6e  mov     r8, rsi; unsigned int
0x180048b71  mov     edx, 230h; void *
0x180048b76  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180048b7b  mov     rcx, [rsp+148h+var_E0]
0x180048b80  mov     [rsp+148h+var_C8], r13
0x180048b88  mov     rax, [rcx]
0x180048b8b  lea     r8, [rsp+148h+var_C8]
0x180048b93  lea     rdx, _GUID_30961379_4609_4a41_998e_54fe567ee0c1
0x180048b9a  mov     rax, [rax]
0x180048b9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ba2  mov     rcx, [rsp+148h]; this
0x180048baa  test    eax, eax
0x180048bac  js      loc_180048ED3
0x180048bb2  mov     rax, [rsp+148h+var_C8]
0x180048bba  mov     [rsp+148h+var_A8], rax
0x180048bc2  mov     rax, [rax]
0x180048bc5  mov     rax, [rax+68h]
0x180048bc9  mov     [rsp+148h+var_B0], rax
0x180048bd1  mov     r13, [rsp+148h+hObject]
0x180048bd6  lea     rax, [r13-1]
0x180048bda  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180048bde  ja      short loc_180048BF9
0x180048be0  call    cs:__imp_GetLastError
0x180048be6  mov     edi, eax
0x180048be8  mov     rcx, r13; hObject
0x180048beb  call    cs:__imp_CloseHandle
0x180048bf1  mov     ecx, edi; dwErrCode
0x180048bf3  call    cs:__imp_SetLastError
0x180048bf9  xor     r13d, r13d
0x180048bfc  mov     [rsp+148h+hObject], r13
0x180048c01  mov     rdx, [r15+0B0h]
0x180048c08  mov     rdx, [rdx+68h]
0x180048c0c  lea     rax, [rsp+148h+hObject]
0x180048c11  mov     qword ptr [rsp+148h+dwDesiredAccess], rax
0x180048c16  xor     r9d, r9d
0x180048c19  mov     r8d, 80000001h
0x180048c1f  mov     rdx, [rdx+128h]
0x180048c26  mov     rcx, [rsp+148h+var_A8]
0x180048c2e  mov     rax, [rsp+148h+var_B0]
0x180048c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c3b  mov     edi, eax
0x180048c3d  mov     rcx, [rsp+148h+var_C8]
0x180048c45  test    rcx, rcx
0x180048c48  jz      short loc_180048C57
0x180048c4a  mov     rdx, [rcx]
0x180048c4d  mov     rax, [rdx+10h]
0x180048c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048c56  nop
0x180048c57  mov     rcx, [rsp+148h]; this
0x180048c5f  lea     rax, aFailedToCreate_6; "Failed to create shared GPU texture han"...
0x180048c66  mov     qword ptr [rsp+148h+dwDesiredAccess], rax; int
0x180048c6b  mov     r9d, edi; char *
0x180048c6e  mov     r8, rsi; unsigned int
0x180048c71  mov     edx, 23Bh; void *
0x180048c76  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180048c7b  mov     dword ptr [r14], 20h ; ' '
0x180048c82  mov     rax, [rsp+148h+var_E0]
0x180048c87  mov     [r14+10h], rax
0x180048c8b  mov     [r14+18h], r13d
0x180048c8f  or      [rsp+148h+var_C0], 1
0x180048c97  jmp     loc_180048DC2
0x180048c9c  cmp     ecx, 1
0x180048c9f  jnz     loc_180048DC2
0x180048ca5  mov     [rsp+148h+var_E0], r13
0x180048caa  mov     rcx, [r15+0C0h]
0x180048cb1  mov     rax, [rcx]
0x180048cb4  mov     [rsp+148h+var_E0], r13
0x180048cb9  lea     rdx, [rsp+148h+var_E0]
0x180048cbe  mov     qword ptr [rsp+148h+dwDesiredAccess], rdx
0x180048cc3  lea     r9, _GUID_affde9d1_1df7_4bb7_8a34_0f46251dab80
0x180048cca  xor     edx, edx
0x180048ccc  lea     r8d, [rdx+2]
0x180048cd0  mov     rax, [rax+220h]
0x180048cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048cdc  mov     rcx, [rsp+148h]; this
0x180048ce4  lea     rdx, aFailedToCreate_11; "Failed to create shared fence."
0x180048ceb  mov     qword ptr [rsp+148h+dwDesiredAccess], rdx; int
0x180048cf0  mov     r9d, eax; char *
0x180048cf3  mov     r8, rsi; unsigned int
0x180048cf6  mov     edx, 250h; void *
0x180048cfb  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180048d00  mov     rax, [rsp+148h+var_E0]
0x180048d05  mov     [rsp+148h+var_A8], rax
0x180048d0d  mov     rax, [rax]
0x180048d10  mov     rax, [rax+38h]
0x180048d14  mov     [rsp+148h+var_B0], rax
0x180048d1c  mov     r13, [rsp+148h+hObject]
0x180048d21  lea     rax, [r13-1]
0x180048d25  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180048d29  ja      short loc_180048D44
0x180048d2b  call    cs:__imp_GetLastError
0x180048d31  mov     edi, eax
0x180048d33  mov     rcx, r13; hObject
0x180048d36  call    cs:__imp_CloseHandle
0x180048d3c  mov     ecx, edi; dwErrCode
0x180048d3e  call    cs:__imp_SetLastError
  ... truncated ...
```
