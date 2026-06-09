# SuexUpdateFirmwareEnclosure(_SU_ENCLOSURE_OBJECT *,ushort *,ushort)

- ea: `0x180039bf4`
- end: `0x18003a1c2`
- name: `?SuexUpdateFirmwareEnclosure@@YA?AV_status_t@@PEAU_SU_ENCLOSURE_OBJECT@@PEAGG@Z`
- size: `1486`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, installer_update`

## callers

- `0x1800a607c`

## callees

- `0x1800011c4`
- `0x180001504`
- `0x1800015d8`
- `0x180001f38`
- `0x180006350`
- `0x18000b840`
- `0x18000ba50`
- `0x18000cc78`
- `0x18000cca4`
- `0x18000ccd4`
- `0x18000cdb0`
- `0x18000f484`
- `0x18001b2b8`
- `0x1800298d0`
- `0x180029b04`
- `0x18002bfbc`
- `0x18002dadc`
- `0x180039bf4`
- `0x18003a1c8`
- `0x1801a31cc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a0f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a115`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a0f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a115`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a139`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a139`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039db4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039db4`

## string_xrefs

- `0x180039c32`: `SuexUpdateFirmwareEnclosure`
- `0x180039ce9`: `SuexUpdateFirmwareEnclosure`
- `0x180039d62`: `SuexUpdateFirmwareEnclosure`
- `0x180039de9`: `SuexUpdateFirmwareEnclosure`
- `0x180039e4e`: `SuexUpdateFirmwareEnclosure`
- `0x180039f3c`: `SuexUpdateFirmwareEnclosure`
- `0x18003a160`: `SuexUpdateFirmwareEnclosure`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int *__fastcall SuexUpdateFirmwareEnclosure(int *a1, __int64 a2, __int64 a3, __int16 a4)
{
  __int64 v8; // rsi
  struct _STORAGE_HW_FIRMWARE_INFO *v9; // rdi
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int LastError; // ecx
  int v14; // r8d
  int v15; // r9d
  struct _STORAGE_HW_FIRMWARE_INFO **v16; // rax
  char *v17; // rdx
  HANDLE FileW; // rax
  int Firmware; // eax
  int v20; // r8d
  int v21; // r9d
  int v22; // ecx
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // rax
  struct _STORAGE_HW_FIRMWARE_INFO *v26; // r14
  int v27; // r8d
  int v28; // r9d
  BYTE *Revision; // rcx
  BYTE *v30; // rcx
  HANDLE ProcessHeap; // rax
  unsigned int v32; // edx
  HANDLE v33; // rax
  unsigned int v34; // edx
  int v35; // ecx
  int v36; // r8d
  __int16 v37; // r9
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int v40; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v41; // [rsp+84h] [rbp-7Ch] BYREF
  struct _STORAGE_HW_FIRMWARE_INFO *v42; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v43; // [rsp+90h] [rbp-70h] BYREF
  struct _STORAGE_HW_FIRMWARE_INFO *v44; // [rsp+98h] [rbp-68h] BYREF
  struct _GUID v45; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v46; // [rsp+B0h] [rbp-50h] BYREF
  BYTE *v47; // [rsp+B8h] [rbp-48h] BYREF
  BYTE *v48; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v49; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v50; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v51; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v52; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v53[4]; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v54[5]; // [rsp+108h] [rbp+8h] BYREF
  WCHAR FileName[256]; // [rsp+130h] [rbp+30h] BYREF

  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v40 = 4728;
    v44 = (struct _STORAGE_HW_FIRMWARE_INFO *)"SuexUpdateFirmwareEnclosure";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"SuexUpdateFirmwareEnclosure",
      (unsigned int)byte_1802FDAF5,
      a3,
      a4,
      (__int64)&v44,
      (__int64)&v40);
  }
  CSmTimer::CSmTimer((CSmTimer *)v54);
  CSmTimer::CSmTimer((CSmTimer *)v53);
  v46 = 0;
  v8 = -1;
  v44 = 0;
  v9 = 0;
  v42 = 0;
  *(_QWORD *)a1 = 0;
  *((_BYTE *)a1 + 8) = 0;
  v45 = *(struct _GUID *)(a2 + 40);
  v10 = SmGuidToString(&v45, &v46);
  *a1 = v10;
  a1[1] = 0;
  *((_BYTE *)a1 + 8) = 0;
  *(_WORD *)((char *)a1 + 9) = *(_WORD *)&v45.Data4[1];
  *((_BYTE *)a1 + 11) = v45.Data4[3];
  if ( v10 < 0 )
  {
    if ( (unsigned int)dword_18039EB68 > 2 )
    {
      v40 = v10;
      v41 = 4743;
      v42 = (struct _STORAGE_HW_FIRMWARE_INFO *)"SuexUpdateFirmwareEnclosure";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)byte_180302533,
        v11,
        v12,
        (__int64)&v42,
        (__int64)&v41,
        (__int64)&v40);
    }
    goto LABEL_25;
  }
  LastError = StringCchPrintfW(FileName, 0x100u, L"\\\\.\\StorageEnclosure#%s", v46);
  *a1 = LastError;
  a1[1] = 0;
  *((_BYTE *)a1 + 8) = 0;
  *(_WORD *)((char *)a1 + 9) = *(_WORD *)&v45.Data4[1];
  *((_BYTE *)a1 + 11) = v45.Data4[3];
  if ( LastError < 0 )
  {
    if ( (unsigned int)dword_18039EB68 <= 2 )
      goto LABEL_25;
    v40 = 4754;
    v42 = (struct _STORAGE_HW_FIRMWARE_INFO *)"SuexUpdateFirmwareEnclosure";
    v16 = &v42;
    v17 = (char *)&dword_1802FEDF4;
    goto LABEL_24;
  }
  FileW = CreateFileW(FileName, 0xC0000000, 7u, 0, 3u, 0x80u, 0);
  v8 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = _status_t::GetLastError((_status_t *)a1);
    if ( (unsigned int)dword_18039EB68 <= 2 )
      goto LABEL_25;
    v40 = 4768;
    v42 = (struct _STORAGE_HW_FIRMWARE_INFO *)"SuexUpdateFirmwareEnclosure";
    v16 = &v42;
    v17 = &byte_180303DFF;
    goto LABEL_24;
  }
  Firmware = PuGetFirmware(FileW, (enum _STORAGE_BUS_TYPE)*(_DWORD *)(a2 + 2664), &v42);
  _status_t::SetBoolGle((_status_t *)a1, Firmware);
  v22 = *a1;
  if ( *a1 >= 0 )
  {
    v9 = v42;
    if ( a3
      && (CSmTimer::Start((CSmTimer *)v53),
          LOBYTE(dwCreationDisposition) = a4,
          v23 = SuexDownloadFirmware(&v45, v8, v9, a3, dwCreationDisposition),
          *(_QWORD *)a1 = *(_QWORD *)v23,
          a1[2] = *(_DWORD *)(v23 + 8),
          CSmTimer::Stop((CSmTimer *)v53),
          LastError = *a1,
          *a1 < 0) )
    {
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_25;
      v40 = 4795;
      v17 = (char *)word_18030471A;
    }
    else
    {
      CSmTimer::Start((CSmTimer *)v54);
      LOBYTE(v24) = a4;
      v25 = SuexActivateFirmware(&v45, v8, v24);
      *(_QWORD *)a1 = *(_QWORD *)v25;
      a1[2] = *(_DWORD *)(v25 + 8);
      CSmTimer::Stop((CSmTimer *)v54);
      LastError = *a1;
      if ( *a1 >= 0 || (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_25;
      v40 = 4809;
      v17 = &byte_180303A57;
    }
    v43 = (unsigned __int64)"SuexUpdateFirmwareEnclosure";
    v16 = (struct _STORAGE_HW_FIRMWARE_INFO **)&v43;
LABEL_24:
    v41 = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      LastError,
      (_DWORD)v17,
      v14,
      v15,
      (__int64)v16,
      (__int64)&v40,
      (__int64)&v41);
    goto LABEL_25;
  }
  if ( (unsigned int)dword_18039EB68 > 2 )
  {
    v41 = *a1;
    v40 = 4778;
    v43 = (unsigned __int64)"SuexUpdateFirmwareEnclosure";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v22,
      (unsigned int)&byte_1802FDEE7,
      v20,
      v21,
      (__int64)&v43,
      (__int64)&v40,
      (__int64)&v41);
  }
  v9 = v42;
LABEL_25:
  PuGetFirmware((HANDLE)v8, *(enum _STORAGE_BUS_TYPE *)(a2 + 2664), &v44);
  v26 = v44;
  if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
  {
    v41 = _status_t::ToWin32((_status_t *)a1);
    v43 = (unsigned __int64)(1000LL * (v54[1] - v54[0])) / v54[2];
    v44 = (struct _STORAGE_HW_FIRMWARE_INFO *)((unsigned __int64)(1000LL * (v53[1] - v53[0])) / v53[2]);
    if ( v26 )
      Revision = v26->Slot[v26->ActiveSlot].Revision;
    else
      Revision = 0;
    v47 = Revision;
    if ( v9 )
      v30 = v9->Slot[v9->ActiveSlot].Revision;
    else
      v30 = 0;
    v48 = v30;
    LOWORD(v40) = a4;
    LODWORD(v42) = *(_DWORD *)(a2 + 2664);
    v49 = a2 + *(unsigned int *)(a2 + 2660) + 56LL;
    v50 = a2 + *(unsigned int *)(a2 + 2652) + 56LL;
    v51 = a2 + *(unsigned int *)(a2 + 2648) + 56LL;
    v52 = a2 + 64;
    *(_QWORD *)&v45.Data1 = L"StorageEnclosure";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v51,
      (unsigned int)byte_1802FD101,
      v27,
      v28,
      (__int64)&v45,
      (__int64)&v52,
      (__int64)&v51,
      (__int64)&v50,
      (__int64)&v49,
      (__int64)&v42,
      (__int64)&v40,
      (__int64)&v48,
      (__int64)&v47,
      (__int64)&v44,
      (__int64)&v43,
      (__int64)&v41);
  }
  if ( v26 )
  {
    ProcessHeap = GetProcessHeap();
    PmHeapFree(ProcessHeap, v32, v26);
  }
  if ( v9 )
  {
    v33 = GetProcessHeap();
    PmHeapFree(v33, v34, v9);
  }
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v8);
  SmFreeString(&v46);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v42) = 4844;
    *(_QWORD *)&v45.Data1 = "SuexUpdateFirmwareEnclosure";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v35,
      (unsigned int)&byte_1802FC6DF,
      v36,
      v37,
      (__int64)&v45,
      (__int64)&v42);
  }
  CSmTimer::~CSmTimer((CSmTimer *)v53);
  CSmTimer::~CSmTimer((CSmTimer *)v54);
  return a1;
}

```

## disassembly

```asm
0x180039bf4  push    rbp
0x180039bf6  push    rbx
0x180039bf7  push    rsi
0x180039bf8  push    rdi
0x180039bf9  push    r12
0x180039bfb  push    r14
0x180039bfd  push    r15
0x180039bff  lea     rbp, [rsp-240h]
0x180039c07  sub     rsp, 340h
0x180039c0e  mov     rax, cs:__security_cookie
0x180039c15  xor     rax, rsp
0x180039c18  mov     [rbp+270h+var_40], rax
0x180039c1f  movzx   r12d, r9w
0x180039c23  mov     r14, r8
0x180039c26  mov     r15, rdx
0x180039c29  mov     rbx, rcx
0x180039c2c  mov     eax, cs:dword_18039EB68
0x180039c32  lea     rcx, aSuexupdatefirm_0; "SuexUpdateFirmwareEnclosure"
0x180039c39  cmp     eax, 5
0x180039c3c  jbe     short loc_180039C67
0x180039c3e  mov     [rbp+270h+var_2F0], 1278h
0x180039c45  mov     [rbp+270h+var_2D8], rcx
0x180039c49  lea     rax, [rbp+270h+var_2F0]
0x180039c4d  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x180039c52  lea     rax, [rbp+270h+var_2D8]
0x180039c56  mov     qword ptr [rsp+370h+dwCreationDisposition], rax
0x180039c5b  lea     rdx, byte_1802FDAF5
0x180039c62  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180039c67  lea     rcx, [rbp+270h+var_268]; this
0x180039c6b  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180039c70  nop
0x180039c71  lea     rcx, [rbp+270h+var_288]; this
0x180039c75  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180039c7a  nop
0x180039c7b  mov     [rbp+270h+var_2C0], 0
0x180039c83  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180039c87  mov     [rbp+270h+var_2D8], 0
0x180039c8f  xor     edi, edi
0x180039c91  mov     [rbp+270h+var_2E8], rdi
0x180039c95  mov     [rbx], rdi
0x180039c98  mov     [rbx+8], dil
0x180039c9c  movups  xmm0, xmmword ptr [r15+28h]
0x180039ca1  movdqu  xmmword ptr [rbp+270h+var_2D0.Data1], xmm0
0x180039ca6  lea     rdx, [rbp+270h+var_2C0]; unsigned __int16 **
0x180039caa  lea     rcx, [rbp+270h+var_2D0]; struct _GUID
0x180039cae  call    ?SmGuidToString@@YAJU_GUID@@PEAPEAG@Z; SmGuidToString(_GUID,ushort * *)
0x180039cb3  mov     ecx, eax
0x180039cb5  mov     [rbx], eax
0x180039cb7  mov     [rbx+4], edi
0x180039cba  mov     [rbx+8], dil
0x180039cbe  movzx   eax, word ptr [rbp+270h+var_2D0.Data4+1]
0x180039cc2  mov     [rbx+9], ax
0x180039cc6  mov     al, [rbp+270h+var_2D0.Data4+3]
0x180039cc9  mov     [rbx+0Bh], al
0x180039ccc  test    ecx, ecx
0x180039cce  jns     short loc_180039D16
0x180039cd0  mov     eax, cs:dword_18039EB68
0x180039cd6  cmp     eax, 2
0x180039cd9  jbe     loc_180039F6A
0x180039cdf  mov     [rbp+270h+var_2F0], ecx
0x180039ce2  mov     [rbp+270h+var_2EC], 1287h
0x180039ce9  lea     rax, aSuexupdatefirm_0; "SuexUpdateFirmwareEnclosure"
0x180039cf0  mov     [rbp+270h+var_2E8], rax
0x180039cf4  lea     rax, [rbp+270h+var_2F0]
0x180039cf8  mov     [rsp+370h+hTemplateFile], rax
0x180039cfd  lea     rax, [rbp+270h+var_2EC]
0x180039d01  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x180039d06  lea     rax, [rbp+270h+var_2E8]
0x180039d0a  lea     rdx, byte_180302533
0x180039d11  jmp     loc_180039F60
0x180039d16  mov     r9, [rbp+270h+var_2C0]
0x180039d1a  lea     r8, aStorageenclosu_1; "\\\\.\\StorageEnclosure#%s"
0x180039d21  mov     edx, 100h; unsigned __int64
0x180039d26  lea     rcx, [rbp+270h+FileName]; unsigned __int16 *
0x180039d2a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180039d2f  mov     ecx, eax
0x180039d31  mov     [rbx], eax
0x180039d33  mov     [rbx+4], edi
0x180039d36  mov     [rbx+8], dil
0x180039d3a  movzx   eax, word ptr [rbp+270h+var_2D0.Data4+1]
0x180039d3e  mov     [rbx+9], ax
0x180039d42  mov     al, [rbp+270h+var_2D0.Data4+3]
0x180039d45  mov     [rbx+0Bh], al
0x180039d48  test    ecx, ecx
0x180039d4a  jns     short loc_180039D8F
0x180039d4c  mov     eax, cs:dword_18039EB68
0x180039d52  cmp     eax, 2
0x180039d55  jbe     loc_180039F6A
0x180039d5b  mov     [rbp+270h+var_2F0], 1292h
0x180039d62  lea     rax, aSuexupdatefirm_0; "SuexUpdateFirmwareEnclosure"
0x180039d69  mov     [rbp+270h+var_2E8], rax
0x180039d6d  lea     rax, [rbp+270h+var_2EC]
0x180039d71  mov     [rsp+370h+hTemplateFile], rax
0x180039d76  lea     rax, [rbp+270h+var_2F0]
0x180039d7a  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x180039d7f  lea     rax, [rbp+270h+var_2E8]
0x180039d83  lea     rdx, dword_1802FEDF4
0x180039d8a  jmp     loc_180039F5D
0x180039d8f  mov     [rsp+370h+hTemplateFile], rdi; hTemplateFile
0x180039d94  mov     [rsp+370h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180039d9c  mov     [rsp+370h+dwCreationDisposition], 3; dwCreationDisposition
0x180039da4  xor     r9d, r9d; lpSecurityAttributes
0x180039da7  mov     edx, 0C0000000h; dwDesiredAccess
0x180039dac  lea     r8d, [r9+7]; dwShareMode
0x180039db0  lea     rcx, [rbp+270h+FileName]; lpFileName
0x180039db4  call    cs:__imp_CreateFileW
0x180039dbb  nop     dword ptr [rax+rax+00h]
0x180039dc0  mov     rsi, rax
0x180039dc3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180039dc7  jnz     short loc_180039E16
0x180039dc9  mov     rcx, rbx; this
0x180039dcc  call    ?GetLastError@_status_t@@QEAAJXZ; _status_t::GetLastError(void)
0x180039dd1  mov     ecx, eax
0x180039dd3  mov     eax, cs:dword_18039EB68
0x180039dd9  cmp     eax, 2
0x180039ddc  jbe     loc_180039F6A
0x180039de2  mov     [rbp+270h+var_2F0], 12A0h
0x180039de9  lea     rax, aSuexupdatefirm_0; "SuexUpdateFirmwareEnclosure"
0x180039df0  mov     [rbp+270h+var_2E8], rax
0x180039df4  lea     rax, [rbp+270h+var_2EC]
0x180039df8  mov     [rsp+370h+hTemplateFile], rax
0x180039dfd  lea     rax, [rbp+270h+var_2F0]
0x180039e01  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x180039e06  lea     rax, [rbp+270h+var_2E8]
0x180039e0a  lea     rdx, byte_180303DFF
0x180039e11  jmp     loc_180039F5D
0x180039e16  lea     r8, [rbp+270h+var_2E8]; struct _STORAGE_HW_FIRMWARE_INFO **
0x180039e1a  mov     edx, [r15+0A68h]; enum _STORAGE_BUS_TYPE
0x180039e21  mov     rcx, rsi; hDevice
0x180039e24  call    ?PuGetFirmware@@YAHPEAXW4_STORAGE_BUS_TYPE@@PEAPEAU_STORAGE_HW_FIRMWARE_INFO@@@Z; PuGetFirmware(void *,_STORAGE_BUS_TYPE,_STORAGE_HW_FIRMWARE_INFO * *)
0x180039e29  mov     edx, eax; int
0x180039e2b  mov     rcx, rbx; this
0x180039e2e  call    ?SetBoolGle@_status_t@@QEAAJH@Z; _status_t::SetBoolGle(int)
0x180039e33  mov     ecx, [rbx]
0x180039e35  test    ecx, ecx
0x180039e37  jns     short loc_180039E89
0x180039e39  mov     eax, cs:dword_18039EB68
0x180039e3f  cmp     eax, 2
0x180039e42  jbe     short loc_180039E80
0x180039e44  mov     [rbp+270h+var_2EC], ecx
0x180039e47  mov     [rbp+270h+var_2F0], 12AAh
0x180039e4e  lea     rax, aSuexupdatefirm_0; "SuexUpdateFirmwareEnclosure"
0x180039e55  mov     [rbp+270h+var_2E0], rax
0x180039e59  lea     rax, [rbp+270h+var_2EC]
0x180039e5d  mov     [rsp+370h+hTemplateFile], rax
0x180039e62  lea     rax, [rbp+270h+var_2F0]
0x180039e66  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x180039e6b  lea     rax, [rbp+270h+var_2E0]
0x180039e6f  mov     qword ptr [rsp+370h+dwCreationDisposition], rax
0x180039e74  lea     rdx, byte_1802FDEE7
0x180039e7b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180039e80  mov     rdi, [rbp+270h+var_2E8]
0x180039e84  jmp     loc_180039F6A
0x180039e89  mov     rdi, [rbp+270h+var_2E8]
0x180039e8d  test    r14, r14
0x180039e90  jz      short loc_180039EEE
0x180039e92  lea     rcx, [rbp+270h+var_288]; this
0x180039e96  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180039e9b  mov     byte ptr [rsp+370h+dwCreationDisposition], r12b
0x180039ea0  mov     r9, r14
0x180039ea3  mov     r8, rdi
0x180039ea6  mov     rdx, rsi
0x180039ea9  lea     rcx, [rbp+270h+var_2D0]
0x180039ead  call    ?SuexDownloadFirmware@@YA?AV_status_t@@PEAXPEAU_STORAGE_HW_FIRMWARE_INFO@@PEAGE@Z; SuexDownloadFirmware(void *,_STORAGE_HW_FIRMWARE_INFO *,ushort *,uchar)
0x180039eb2  movsd   xmm0, qword ptr [rax]
0x180039eb6  movsd   qword ptr [rbx], xmm0
0x180039eba  mov     eax, [rax+8]
0x180039ebd  mov     [rbx+8], eax
0x180039ec0  lea     rcx, [rbp+270h+var_288]; this
0x180039ec4  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180039ec9  mov     ecx, [rbx]
0x180039ecb  test    ecx, ecx
0x180039ecd  jns     short loc_180039EEE
0x180039ecf  mov     eax, cs:dword_18039EB68
0x180039ed5  cmp     eax, 2
0x180039ed8  jbe     loc_180039F6A
0x180039ede  mov     [rbp+270h+var_2F0], 12BBh
0x180039ee5  lea     rdx, word_18030471A
0x180039eec  jmp     short loc_180039F3C
0x180039eee  lea     rcx, [rbp+270h+var_268]; this
0x180039ef2  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180039ef7  mov     r8b, r12b
0x180039efa  mov     rdx, rsi
0x180039efd  lea     rcx, [rbp+270h+var_2D0]
0x180039f01  call    ?SuexActivateFirmware@@YA?AV_status_t@@PEAXE@Z; SuexActivateFirmware(void *,uchar)
0x180039f06  movsd   xmm0, qword ptr [rax]
0x180039f0a  movsd   qword ptr [rbx], xmm0
0x180039f0e  mov     eax, [rax+8]
0x180039f11  mov     [rbx+8], eax
0x180039f14  lea     rcx, [rbp+270h+var_268]; this
0x180039f18  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180039f1d  mov     ecx, [rbx]
0x180039f1f  test    ecx, ecx
0x180039f21  jns     short loc_180039F6A
0x180039f23  mov     eax, cs:dword_18039EB68
0x180039f29  cmp     eax, 2
0x180039f2c  jbe     short loc_180039F6A
0x180039f2e  mov     [rbp+270h+var_2F0], 12C9h
0x180039f35  lea     rdx, byte_180303A57
0x180039f3c  lea     rax, aSuexupdatefirm_0; "SuexUpdateFirmwareEnclosure"
0x180039f43  mov     [rbp+270h+var_2E0], rax
0x180039f47  lea     rax, [rbp+270h+var_2EC]
0x180039f4b  mov     [rsp+370h+hTemplateFile], rax
0x180039f50  lea     rax, [rbp+270h+var_2F0]
0x180039f54  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x180039f59  lea     rax, [rbp+270h+var_2E0]
0x180039f5d  mov     [rbp+270h+var_2EC], ecx
0x180039f60  mov     qword ptr [rsp+370h+dwCreationDisposition], rax
0x180039f65  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180039f6a  lea     r8, [rbp+270h+var_2D8]; struct _STORAGE_HW_FIRMWARE_INFO **
0x180039f6e  mov     edx, [r15+0A68h]; enum _STORAGE_BUS_TYPE
0x180039f75  mov     rcx, rsi; hDevice
0x180039f78  call    ?PuGetFirmware@@YAHPEAXW4_STORAGE_BUS_TYPE@@PEAPEAU_STORAGE_HW_FIRMWARE_INFO@@@Z; PuGetFirmware(void *,_STORAGE_BUS_TYPE,_STORAGE_HW_FIRMWARE_INFO * *)
0x180039f7d  mov     eax, cs:dword_18039EB68
0x180039f83  mov     r14, [rbp+270h+var_2D8]
0x180039f87  cmp     eax, 5
0x180039f8a  jbe     loc_18003A0F4
0x180039f90  mov     rdx, 400000000000h
0x180039f9a  lea     rcx, dword_18039EB68
0x180039fa1  call    _tlgKeywordOn
0x180039fa6  test    al, al
0x180039fa8  jz      loc_18003A0F4
0x180039fae  mov     rcx, rbx; this
0x180039fb1  call    ?ToWin32@_status_t@@QEAAKXZ; _status_t::ToWin32(void)
0x180039fb6  mov     [rbp+270h+var_2EC], eax
0x180039fb9  mov     rax, [rbp+270h+var_260]
0x180039fbd  sub     rax, [rbp+270h+var_268]
0x180039fc1  imul    rax, 3E8h
0x180039fc8  xor     edx, edx
0x180039fca  div     [rbp+270h+var_258]
0x180039fce  mov     [rbp+270h+var_2E0], rax
0x180039fd2  mov     rax, [rbp+270h+var_280]
0x180039fd6  sub     rax, [rbp+270h+var_288]
0x180039fda  imul    rax, 3E8h
0x180039fe1  xor     edx, edx
0x180039fe3  div     [rbp+270h+var_278]
0x180039fe7  mov     [rbp+270h+var_2D8], rax
0x180039feb  test    r14, r14
0x180039fee  jz      short loc_18003A002
0x180039ff0  movzx   ecx, byte ptr [r14+0Ah]
0x180039ff5  shl     rcx, 5
0x180039ff9  add     rcx, 28h ; '('
0x180039ffd  add     rcx, r14
0x18003a000  jmp     short loc_18003A004
0x18003a002  xor     ecx, ecx
0x18003a004  mov     [rbp+270h+var_2B8], rcx
0x18003a008  test    rdi, rdi
0x18003a00b  jz      short loc_18003A01E
0x18003a00d  movzx   ecx, byte ptr [rdi+0Ah]
0x18003a011  shl     rcx, 5
0x18003a015  add     rcx, 28h ; '('
0x18003a019  add     rcx, rdi
0x18003a01c  jmp     short loc_18003A020
0x18003a01e  xor     ecx, ecx
0x18003a020  mov     [rbp+270h+var_2B0], rcx
0x18003a024  mov     word ptr [rbp+270h+var_2F0], r12w
0x18003a029  mov     eax, [r15+0A68h]
0x18003a030  mov     dword ptr [rbp+270h+var_2E8], eax
0x18003a033  mov     ecx, [r15+0A64h]
0x18003a03a  add     rcx, 38h ; '8'
0x18003a03e  add     rcx, r15
0x18003a041  mov     [rbp+270h+var_2A8], rcx
0x18003a045  mov     ecx, [r15+0A5Ch]
0x18003a04c  add     rcx, 38h ; '8'
0x18003a050  add     rcx, r15
0x18003a053  mov     [rbp+270h+var_2A0], rcx
0x18003a057  mov     ecx, [r15+0A58h]
0x18003a05e  add     rcx, 38h ; '8'
0x18003a062  add     rcx, r15
0x18003a065  mov     [rbp+270h+var_298], rcx
0x18003a069  lea     rax, [r15+40h]
0x18003a06d  mov     [rbp+270h+var_290], rax
0x18003a071  lea     rax, aStorageenclosu_0; "StorageEnclosure"
0x18003a078  mov     qword ptr [rbp+270h+var_2D0.Data1], rax
0x18003a07c  lea     rax, [rbp+270h+var_2EC]
0x18003a080  mov     [rsp+370h+var_2F8], rax
0x18003a085  lea     rax, [rbp+270h+var_2E0]
0x18003a089  mov     [rsp+370h+var_300], rax
0x18003a08e  lea     rax, [rbp+270h+var_2D8]
0x18003a092  mov     [rsp+370h+var_308], rax
0x18003a097  lea     rax, [rbp+270h+var_2B8]
0x18003a09b  mov     [rsp+370h+var_310], rax
0x18003a0a0  lea     rax, [rbp+270h+var_2B0]
0x18003a0a4  mov     [rsp+370h+var_318], rax
0x18003a0a9  lea     rax, [rbp+270h+var_2F0]
0x18003a0ad  mov     [rsp+370h+var_320], rax
0x18003a0b2  lea     rax, [rbp+270h+var_2E8]
0x18003a0b6  mov     [rsp+370h+var_328], rax
0x18003a0bb  lea     rax, [rbp+270h+var_2A8]
0x18003a0bf  mov     [rsp+370h+var_330], rax
0x18003a0c4  lea     rax, [rbp+270h+var_2A0]
0x18003a0c8  mov     [rsp+370h+var_338], rax
0x18003a0cd  lea     rax, [rbp+270h+var_298]
0x18003a0d1  mov     [rsp+370h+hTemplateFile], rax
0x18003a0d6  lea     rax, [rbp+270h+var_290]
0x18003a0da  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x18003a0df  lea     rax, [rbp+270h+var_2D0]
0x18003a0e3  mov     qword ptr [rsp+370h+dwCreationDisposition], rax
0x18003a0e8  lea     rdx, byte_1802FD101
0x18003a0ef  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U1@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@U?$_tlgWrapSz@D@@U5@U?$_tlgWrapperByVal@$07@@U6@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@333AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@AEBU?$_tlgWrapSz@D@@7AEBU?$_tlgWrapperByVal@$07@@85@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
  ... truncated ...
```
