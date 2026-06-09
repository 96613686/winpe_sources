# SuexUpdateFirmwareDrive(_SU_DRIVE_OBJECT *,ushort *,ushort)

- ea: `0x1800395dc`
- end: `0x180039bec`
- name: `?SuexUpdateFirmwareDrive@@YAXPEAU_SU_DRIVE_OBJECT@@PEAGG@Z`
- size: `1552`
- prototype: `void(struct _SU_DRIVE_OBJECT *, unsigned __int16 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, installer_update`

## callers

- `0x18009f4d0`

## callees

- `0x1800011c4`
- `0x180001504`
- `0x1800015d8`
- `0x180001f38`
- `0x180006350`
- `0x180006dd4`
- `0x18000b840`
- `0x18000ba50`
- `0x18000cca4`
- `0x18000ccd4`
- `0x18000cdb0`
- `0x1800298d0`
- `0x1800395dc`
- `0x18019b1e0`
- `0x18019f7e0`
- `0x1801a31cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800396d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039907`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800399c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800396d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039907`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800399c8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039b38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039b54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039b38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180039b54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039b78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039b78`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800396ba`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800396ba`

## string_xrefs

- `0x18003960d`: `SuexUpdateFirmwareDrive`
- `0x18003972c`: `SuexUpdateFirmwareDrive`
- `0x180039974`: `SuexUpdateFirmwareDrive`

## pseudocode

```c
void __fastcall SuexUpdateFirmwareDrive(struct _SU_DRIVE_OBJECT *a1, unsigned __int16 *a2, __int16 a3, int a4)
{
  struct _STORAGE_HW_FIRMWARE_INFO *v7; // rdi
  __int64 v8; // r9
  char *FileW; // rax
  char *v10; // r14
  DWORD v11; // eax
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  char *v15; // rdx
  int *v16; // rax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  struct _STORAGE_HW_FIRMWARE_INFO *v20; // rbx
  BYTE *Revision; // rcx
  DWORD v22; // ecx
  int v23; // r8d
  int v24; // r9d
  char *v25; // rdx
  int v26; // ebx
  DWORD LastError; // ecx
  int v28; // r8d
  int v29; // r9d
  char *v30; // rdx
  int v31; // ebx
  BYTE *v32; // rcx
  __int64 v33; // rcx
  HANDLE ProcessHeap; // rax
  unsigned int v35; // edx
  HANDLE v36; // rax
  unsigned int v37; // edx
  int *hTemplateFile; // [rsp+30h] [rbp-D0h]
  int v39; // [rsp+80h] [rbp-80h] BYREF
  int v40; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned __int64 v41; // [rsp+88h] [rbp-78h] BYREF
  struct _STORAGE_HW_FIRMWARE_INFO *v42; // [rsp+90h] [rbp-70h] BYREF
  struct _STORAGE_HW_FIRMWARE_INFO *v43; // [rsp+98h] [rbp-68h] BYREF
  const char *v44; // [rsp+A0h] [rbp-60h] BYREF
  BYTE *v45; // [rsp+A8h] [rbp-58h] BYREF
  BYTE *v46; // [rsp+B0h] [rbp-50h] BYREF
  char *v47; // [rsp+B8h] [rbp-48h] BYREF
  char *v48; // [rsp+C0h] [rbp-40h] BYREF
  char *v49; // [rsp+C8h] [rbp-38h] BYREF
  char *v50; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v51[4]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v52[5]; // [rsp+F8h] [rbp-8h] BYREF
  WCHAR FileName[264]; // [rsp+120h] [rbp+20h] BYREF

  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v39 = 10405;
    v43 = (struct _STORAGE_HW_FIRMWARE_INFO *)"SuexUpdateFirmwareDrive";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)a1,
      (unsigned int)byte_1803078D9,
      a3,
      a4,
      (__int64)&v43,
      (__int64)&v39);
  }
  memset_0(FileName, 0, 0x208u);
  v7 = 0;
  v42 = 0;
  v43 = 0;
  CSmTimer::CSmTimer((CSmTimer *)v52);
  CSmTimer::CSmTimer((CSmTimer *)v51);
  v8 = *((unsigned int *)a1 + 28);
  *((_DWORD *)a1 + 4) = 0;
  StringCchPrintfW(FileName, 0x104u, L"\\\\.\\PhysicalDrive%d", v8);
  FileW = (char *)CreateFileW(FileName, 0xC0000000, 7u, 0, 3u, 0x80u, 0);
  v10 = FileW;
  if ( FileW != (char *)-1LL )
  {
    if ( (unsigned int)PuGetFirmware(FileW, (enum _STORAGE_BUS_TYPE)*((_DWORD *)a1 + 676), &v42) )
    {
      v7 = v42;
      if ( !a2
        || (CSmTimer::Start((CSmTimer *)v52),
            v26 = PuDownloadFirmware(v10, v7, a2, a3),
            CSmTimer::Stop((CSmTimer *)v52),
            v26) )
      {
        CSmTimer::Start((CSmTimer *)v51);
        v31 = PuActivateFirmware(v10, v7, a2, a3);
        CSmTimer::Stop((CSmTimer *)v51);
        if ( v31 )
          goto LABEL_8;
        LastError = GetLastError();
        *((_DWORD *)a1 + 4) = LastError;
        if ( LastError )
        {
          if ( LastError == 122 )
          {
            if ( (unsigned int)dword_18039EB68 <= 3 )
              goto LABEL_8;
            v40 = 122;
            v30 = &byte_18030070F;
            v39 = 10475;
          }
          else
          {
            if ( (unsigned int)dword_18039EB68 <= 2 )
              goto LABEL_8;
            v40 = LastError;
            v30 = (char *)&dword_1803055BC;
            v39 = 10475;
          }
        }
        else
        {
          if ( (unsigned int)dword_18039EB68 <= 4 )
            goto LABEL_8;
          v40 = 0;
          v30 = byte_180306F0B;
          v39 = 10475;
        }
      }
      else
      {
        LastError = GetLastError();
        *((_DWORD *)a1 + 4) = LastError;
        if ( LastError )
        {
          if ( LastError == 122 )
          {
            if ( (unsigned int)dword_18039EB68 <= 3 )
              goto LABEL_8;
            v40 = 122;
            v30 = byte_1802FDCAD;
          }
          else
          {
            if ( (unsigned int)dword_18039EB68 <= 2 )
              goto LABEL_8;
            v40 = LastError;
            v30 = (char *)qword_1802FF478;
          }
        }
        else
        {
          if ( (unsigned int)dword_18039EB68 <= 4 )
            goto LABEL_8;
          v40 = 0;
          v30 = &byte_1802FBE77;
        }
        v39 = 10459;
      }
      v41 = (unsigned __int64)"SuexUpdateFirmwareDrive";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        LastError,
        (_DWORD)v30,
        v28,
        v29,
        (__int64)&v41,
        (__int64)&v39,
        (__int64)&v40);
      goto LABEL_8;
    }
    v22 = GetLastError();
    *((_DWORD *)a1 + 4) = v22;
    if ( v22 )
    {
      if ( v22 == 122 )
      {
        if ( (unsigned int)dword_18039EB68 <= 3 )
          goto LABEL_22;
        v40 = 122;
        v25 = byte_1802FE4C3;
      }
      else
      {
        if ( (unsigned int)dword_18039EB68 <= 2 )
          goto LABEL_22;
        v40 = v22;
        v25 = (char *)&word_18030313E;
      }
    }
    else
    {
      if ( (unsigned int)dword_18039EB68 <= 4 )
      {
LABEL_22:
        v7 = v42;
        goto LABEL_8;
      }
      v40 = 0;
      v25 = &byte_180305D17;
    }
    v39 = 10442;
    v41 = (unsigned __int64)"SuexUpdateFirmwareDrive";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v22,
      (_DWORD)v25,
      v23,
      v24,
      (__int64)&v41,
      (__int64)&v39,
      (__int64)&v40);
    goto LABEL_22;
  }
  v11 = GetLastError();
  *((_DWORD *)a1 + 4) = v11;
  v14 = v11;
  if ( v11 )
  {
    if ( v11 == 122 )
    {
      if ( (unsigned int)dword_18039EB68 <= 3 )
        goto LABEL_8;
      v40 = 122;
      hTemplateFile = &v40;
      v15 = byte_180306725;
      v16 = &v39;
      v39 = 10432;
    }
    else
    {
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_8;
      v40 = v11;
      hTemplateFile = &v40;
      v15 = (char *)qword_1803034B0;
      v16 = &v39;
      v39 = 10432;
    }
    goto LABEL_7;
  }
  v14 = dword_18039EB68;
  if ( (unsigned int)dword_18039EB68 > 4 )
  {
    v39 = 0;
    hTemplateFile = &v39;
    v15 = &byte_180303DC7;
    v16 = &v40;
    v40 = 10432;
LABEL_7:
    v42 = (struct _STORAGE_HW_FIRMWARE_INFO *)"SuexUpdateFirmwareDrive";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v14,
      (_DWORD)v15,
      v12,
      v13,
      (__int64)&v42,
      (__int64)v16,
      (__int64)hTemplateFile);
  }
LABEL_8:
  PuGetFirmware(v10, *((enum _STORAGE_BUS_TYPE *)a1 + 676), &v43);
  v20 = v43;
  if ( (unsigned int)dword_18039EB68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18039EB68, 0x400000000000LL) )
  {
    v40 = *((_DWORD *)a1 + 4);
    v41 = (unsigned __int64)(1000LL * (v51[1] - v51[0])) / v51[2];
    v43 = (struct _STORAGE_HW_FIRMWARE_INFO *)((unsigned __int64)(1000LL * (v52[1] - v52[0])) / v52[2]);
    if ( v20 )
      Revision = v20->Slot[v20->ActiveSlot].Revision;
    else
      Revision = 0;
    v45 = Revision;
    if ( v7 )
      v32 = v7->Slot[v7->ActiveSlot].Revision;
    else
      v32 = 0;
    LODWORD(v42) = *((_DWORD *)a1 + 676);
    v50 = (char *)a1 + 96;
    v44 = (const char *)L"PhysicalDisk";
    v46 = v32;
    v33 = *((unsigned int *)a1 + 673);
    LOWORD(v39) = a3;
    v47 = (char *)a1 + v33 + 72;
    v48 = (char *)a1 + *((unsigned int *)a1 + 671) + 72;
    v49 = (char *)a1 + *((unsigned int *)a1 + 670) + 72;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (_DWORD)v49,
      (unsigned int)&byte_18030270F,
      v18,
      v19,
      (__int64)&v44,
      (__int64)&v50,
      (__int64)&v49,
      (__int64)&v48,
      (__int64)&v47,
      (__int64)&v42,
      (__int64)&v39,
      (__int64)&v46,
      (__int64)&v45,
      (__int64)&v43,
      (__int64)&v41,
      (__int64)&v40);
  }
  if ( v20 )
  {
    ProcessHeap = GetProcessHeap();
    PmHeapFree(ProcessHeap, v35, v20);
  }
  if ( v7 )
  {
    v36 = GetProcessHeap();
    PmHeapFree(v36, v37, v7);
  }
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v10);
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(v42) = 10510;
    v44 = "SuexUpdateFirmwareDrive";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v17,
      (unsigned int)byte_180304681,
      (_WORD)v18,
      v19,
      (__int64)&v44,
      (__int64)&v42);
  }
  CSmTimer::~CSmTimer((CSmTimer *)v51);
  CSmTimer::~CSmTimer((CSmTimer *)v52);
}

```

## disassembly

```asm
0x1800395dc  push    rbp
0x1800395de  push    rbx
0x1800395df  push    rsi
0x1800395e0  push    rdi
0x1800395e1  push    r12
0x1800395e3  push    r14
0x1800395e5  push    r15
0x1800395e7  lea     rbp, [rsp-240h]
0x1800395ef  sub     rsp, 340h
0x1800395f6  mov     rax, cs:__security_cookie
0x1800395fd  xor     rax, rsp
0x180039600  mov     [rbp+270h+var_40], rax
0x180039607  mov     eax, cs:dword_18039EB68
0x18003960d  lea     rbx, aSuexupdatefirm; "SuexUpdateFirmwareDrive"
0x180039614  movzx   r12d, r8w
0x180039618  mov     r15, rdx
0x18003961b  mov     rsi, rcx
0x18003961e  cmp     eax, 5
0x180039621  jbe     short loc_18003964C
0x180039623  lea     rax, [rbp+270h+var_2F0]
0x180039627  mov     [rbp+270h+var_2F0], 28A5h
0x18003962e  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x180039633  lea     rdx, byte_1803078D9
0x18003963a  lea     rax, [rbp+270h+var_2D8]
0x18003963e  mov     [rbp+270h+var_2D8], rbx
0x180039642  mov     qword ptr [rsp+370h+dwCreationDisposition], rax
0x180039647  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003964c  xor     edx, edx; Val
0x18003964e  lea     rcx, [rbp+270h+FileName]; void *
0x180039652  mov     r8d, 208h; Size
0x180039658  call    memset_0
0x18003965d  xor     edi, edi
0x18003965f  lea     rcx, [rbp+270h+var_278]; this
0x180039663  mov     [rbp+270h+var_2E0], rdi
0x180039667  mov     [rbp+270h+var_2D8], rdi
0x18003966b  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180039670  lea     rcx, [rbp+270h+var_298]; this
0x180039674  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x180039679  mov     r9d, [rsi+70h]
0x18003967d  lea     r8, aPhysicaldriveD_0; "\\\\.\\PhysicalDrive%d"
0x180039684  mov     edx, 104h; unsigned __int64
0x180039689  mov     [rsi+10h], edi
0x18003968c  lea     rcx, [rbp+270h+FileName]; unsigned __int16 *
0x180039690  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180039695  mov     [rsp+370h+hTemplateFile], rdi; hTemplateFile
0x18003969a  lea     r8d, [rdi+7]; dwShareMode
0x18003969e  mov     [rsp+370h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800396a6  lea     rcx, [rbp+270h+FileName]; lpFileName
0x1800396aa  xor     r9d, r9d; lpSecurityAttributes
0x1800396ad  mov     [rsp+370h+dwCreationDisposition], 3; dwCreationDisposition
0x1800396b5  mov     edx, 0C0000000h; dwDesiredAccess
0x1800396ba  call    cs:__imp_CreateFileW
0x1800396c1  nop     dword ptr [rax+rax+00h]
0x1800396c6  mov     r14, rax
0x1800396c9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800396cd  jnz     loc_18003982E
0x1800396d3  call    cs:__imp_GetLastError
0x1800396da  nop     dword ptr [rax+rax+00h]
0x1800396df  mov     [rsi+10h], eax
0x1800396e2  mov     ecx, eax
0x1800396e4  test    eax, eax
0x1800396e6  jnz     loc_1800397CB
0x1800396ec  mov     ecx, cs:dword_18039EB68
0x1800396f2  cmp     ecx, 4
0x1800396f5  jbe     short loc_18003972C
0x1800396f7  lea     rax, [rbp+270h+var_2F0]
0x1800396fb  mov     [rbp+270h+var_2F0], edi
0x1800396fe  mov     [rsp+370h+hTemplateFile], rax
0x180039703  lea     rdx, byte_180303DC7
0x18003970a  lea     rax, [rbp+270h+var_2EC]
0x18003970e  mov     [rbp+270h+var_2EC], 28C0h
0x180039715  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x18003971a  lea     rax, [rbp+270h+var_2E0]
0x18003971e  mov     qword ptr [rsp+370h+dwCreationDisposition], rax
0x180039723  mov     [rbp+270h+var_2E0], rbx
0x180039727  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003972c  lea     r15, aSuexupdatefirm; "SuexUpdateFirmwareDrive"
0x180039733  mov     edx, [rsi+0A90h]; enum _STORAGE_BUS_TYPE
0x180039739  lea     r8, [rbp+270h+var_2D8]; struct _STORAGE_HW_FIRMWARE_INFO **
0x18003973d  mov     rcx, r14; hDevice
0x180039740  call    ?PuGetFirmware@@YAHPEAXW4_STORAGE_BUS_TYPE@@PEAPEAU_STORAGE_HW_FIRMWARE_INFO@@@Z; PuGetFirmware(void *,_STORAGE_BUS_TYPE,_STORAGE_HW_FIRMWARE_INFO * *)
0x180039745  mov     eax, cs:dword_18039EB68
0x18003974b  mov     rbx, [rbp+270h+var_2D8]
0x18003974f  cmp     eax, 5
0x180039752  jbe     loc_180039B33
0x180039758  mov     rdx, 400000000000h
0x180039762  lea     rcx, dword_18039EB68
0x180039769  call    _tlgKeywordOn
0x18003976e  test    al, al
0x180039770  jz      loc_180039B33
0x180039776  mov     eax, [rsi+10h]
0x180039779  xor     edx, edx
0x18003977b  mov     [rbp+270h+var_2EC], eax
0x18003977e  mov     rax, [rbp+270h+var_290]
0x180039782  sub     rax, [rbp+270h+var_298]
0x180039786  imul    rax, 3E8h
0x18003978d  div     [rbp+270h+var_288]
0x180039791  xor     edx, edx
0x180039793  mov     [rbp+270h+var_2E8], rax
0x180039797  mov     rax, [rbp+270h+var_270]
0x18003979b  sub     rax, [rbp+270h+var_278]
0x18003979f  imul    rax, 3E8h
0x1800397a6  div     [rbp+270h+var_268]
0x1800397aa  mov     [rbp+270h+var_2D8], rax
0x1800397ae  test    rbx, rbx
0x1800397b1  jz      loc_180039A45
0x1800397b7  movzx   ecx, byte ptr [rbx+0Ah]
0x1800397bb  shl     rcx, 5
0x1800397bf  add     rcx, 28h ; '('
0x1800397c3  add     rcx, rbx
0x1800397c6  jmp     loc_180039A47
0x1800397cb  mov     eax, cs:dword_18039EB68
0x1800397d1  cmp     ecx, 7Ah ; 'z'
0x1800397d4  jnz     short loc_180039802
0x1800397d6  cmp     eax, 3
0x1800397d9  jbe     loc_18003972C
0x1800397df  lea     rax, [rbp+270h+var_2EC]
0x1800397e3  mov     [rbp+270h+var_2EC], ecx
0x1800397e6  mov     [rsp+370h+hTemplateFile], rax
0x1800397eb  lea     rdx, byte_180306725
0x1800397f2  lea     rax, [rbp+270h+var_2F0]
0x1800397f6  mov     [rbp+270h+var_2F0], 28C0h
0x1800397fd  jmp     loc_180039715
0x180039802  cmp     eax, 2
0x180039805  jbe     loc_18003972C
0x18003980b  lea     rax, [rbp+270h+var_2EC]
0x18003980f  mov     [rbp+270h+var_2EC], ecx
0x180039812  mov     [rsp+370h+hTemplateFile], rax
0x180039817  lea     rdx, qword_1803034B0
0x18003981e  lea     rax, [rbp+270h+var_2F0]
0x180039822  mov     [rbp+270h+var_2F0], 28C0h
0x180039829  jmp     loc_180039715
0x18003982e  mov     edx, [rsi+0A90h]; enum _STORAGE_BUS_TYPE
0x180039834  lea     r8, [rbp+270h+var_2E0]; struct _STORAGE_HW_FIRMWARE_INFO **
0x180039838  mov     rcx, r14; hDevice
0x18003983b  call    ?PuGetFirmware@@YAHPEAXW4_STORAGE_BUS_TYPE@@PEAPEAU_STORAGE_HW_FIRMWARE_INFO@@@Z; PuGetFirmware(void *,_STORAGE_BUS_TYPE,_STORAGE_HW_FIRMWARE_INFO * *)
0x180039840  test    eax, eax
0x180039842  jnz     loc_1800398CD
0x180039848  call    cs:__imp_GetLastError
0x18003984f  nop     dword ptr [rax+rax+00h]
0x180039854  mov     ecx, eax
0x180039856  mov     [rsi+10h], eax
0x180039859  test    eax, eax
0x18003985b  mov     eax, cs:dword_18039EB68
0x180039861  jnz     short loc_1800398A6
0x180039863  cmp     eax, 4
0x180039866  jbe     short loc_18003989D
0x180039868  mov     [rbp+270h+var_2EC], edi
0x18003986b  lea     rdx, byte_180305D17
0x180039872  lea     rax, [rbp+270h+var_2EC]
0x180039876  mov     [rbp+270h+var_2F0], 28CAh
0x18003987d  mov     [rsp+370h+hTemplateFile], rax
0x180039882  lea     rax, [rbp+270h+var_2F0]
0x180039886  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x18003988b  lea     rax, [rbp+270h+var_2E8]
0x18003988f  mov     qword ptr [rsp+370h+dwCreationDisposition], rax
0x180039894  mov     [rbp+270h+var_2E8], rbx
0x180039898  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003989d  mov     rdi, [rbp+270h+var_2E0]
0x1800398a1  jmp     loc_18003972C
0x1800398a6  cmp     ecx, 7Ah ; 'z'
0x1800398a9  jnz     short loc_1800398BC
0x1800398ab  cmp     eax, 3
0x1800398ae  jbe     short loc_18003989D
0x1800398b0  mov     [rbp+270h+var_2EC], ecx
0x1800398b3  lea     rdx, byte_1802FE4C3
0x1800398ba  jmp     short loc_180039872
0x1800398bc  cmp     eax, 2
0x1800398bf  jbe     short loc_18003989D
0x1800398c1  mov     [rbp+270h+var_2EC], ecx
0x1800398c4  lea     rdx, word_18030313E
0x1800398cb  jmp     short loc_180039872
0x1800398cd  mov     rdi, [rbp+270h+var_2E0]
0x1800398d1  test    r15, r15
0x1800398d4  jz      loc_18003999B
0x1800398da  lea     rcx, [rbp+270h+var_278]; this
0x1800398de  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x1800398e3  mov     r9b, r12b; unsigned __int8
0x1800398e6  mov     r8, r15; unsigned __int16 *
0x1800398e9  mov     rdx, rdi; struct _STORAGE_HW_FIRMWARE_INFO *
0x1800398ec  mov     rcx, r14; hDevice
0x1800398ef  call    ?PuDownloadFirmware@@YAHPEAXPEAU_STORAGE_HW_FIRMWARE_INFO@@PEBGE@Z; PuDownloadFirmware(void *,_STORAGE_HW_FIRMWARE_INFO *,ushort const *,uchar)
0x1800398f4  lea     rcx, [rbp+270h+var_278]; this
0x1800398f8  mov     ebx, eax
0x1800398fa  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x1800398ff  test    ebx, ebx
0x180039901  jnz     loc_18003999B
0x180039907  call    cs:__imp_GetLastError
0x18003990e  nop     dword ptr [rax+rax+00h]
0x180039913  mov     ecx, eax
0x180039915  mov     [rsi+10h], eax
0x180039918  test    eax, eax
0x18003991a  mov     eax, cs:dword_18039EB68
0x180039920  jnz     short loc_180039937
0x180039922  cmp     eax, 4
0x180039925  jbe     loc_18003972C
0x18003992b  mov     [rbp+270h+var_2EC], ebx
0x18003992e  lea     rdx, byte_1802FBE77
0x180039935  jmp     short loc_180039964
0x180039937  cmp     ecx, 7Ah ; 'z'
0x18003993a  jnz     short loc_180039951
0x18003993c  cmp     eax, 3
0x18003993f  jbe     loc_18003972C
0x180039945  mov     [rbp+270h+var_2EC], ecx
0x180039948  lea     rdx, byte_1802FDCAD
0x18003994f  jmp     short loc_180039964
0x180039951  cmp     eax, 2
0x180039954  jbe     loc_18003972C
0x18003995a  mov     [rbp+270h+var_2EC], ecx
0x18003995d  lea     rdx, qword_1802FF478
0x180039964  mov     [rbp+270h+var_2F0], 28DBh
0x18003996b  lea     rax, [rbp+270h+var_2EC]
0x18003996f  mov     [rsp+370h+hTemplateFile], rax
0x180039974  lea     r15, aSuexupdatefirm; "SuexUpdateFirmwareDrive"
0x18003997b  lea     rax, [rbp+270h+var_2F0]
0x18003997f  mov     [rbp+270h+var_2E8], r15
0x180039983  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x180039988  lea     rax, [rbp+270h+var_2E8]
0x18003998c  mov     qword ptr [rsp+370h+dwCreationDisposition], rax
0x180039991  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180039996  jmp     loc_180039733
0x18003999b  lea     rcx, [rbp+270h+var_298]; this
0x18003999f  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x1800399a4  mov     r9b, r12b; unsigned __int8
0x1800399a7  mov     r8, r15; unsigned __int16 *
0x1800399aa  mov     rdx, rdi; struct _STORAGE_HW_FIRMWARE_INFO *
0x1800399ad  mov     rcx, r14; hDevice
0x1800399b0  call    ?PuActivateFirmware@@YAHPEAXPEAU_STORAGE_HW_FIRMWARE_INFO@@PEBGE@Z; PuActivateFirmware(void *,_STORAGE_HW_FIRMWARE_INFO *,ushort const *,uchar)
0x1800399b5  lea     rcx, [rbp+270h+var_298]; this
0x1800399b9  mov     ebx, eax
0x1800399bb  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x1800399c0  test    ebx, ebx
0x1800399c2  jnz     loc_18003972C
0x1800399c8  call    cs:__imp_GetLastError
0x1800399cf  nop     dword ptr [rax+rax+00h]
0x1800399d4  mov     ecx, eax
0x1800399d6  mov     [rsi+10h], eax
0x1800399d9  test    eax, eax
0x1800399db  mov     eax, cs:dword_18039EB68
0x1800399e1  jnz     short loc_180039A02
0x1800399e3  cmp     eax, 4
0x1800399e6  jbe     loc_18003972C
0x1800399ec  mov     [rbp+270h+var_2EC], ebx
0x1800399ef  lea     rdx, byte_180306F0B
0x1800399f6  mov     [rbp+270h+var_2F0], 28EBh
0x1800399fd  jmp     loc_18003996B
0x180039a02  cmp     ecx, 7Ah ; 'z'
0x180039a05  jnz     short loc_180039A26
0x180039a07  cmp     eax, 3
0x180039a0a  jbe     loc_18003972C
0x180039a10  mov     [rbp+270h+var_2EC], ecx
0x180039a13  lea     rdx, byte_18030070F
0x180039a1a  mov     [rbp+270h+var_2F0], 28EBh
0x180039a21  jmp     loc_18003996B
0x180039a26  cmp     eax, 2
0x180039a29  jbe     loc_18003972C
0x180039a2f  mov     [rbp+270h+var_2EC], ecx
0x180039a32  lea     rdx, dword_1803055BC
0x180039a39  mov     [rbp+270h+var_2F0], 28EBh
0x180039a40  jmp     loc_18003996B
0x180039a45  xor     ecx, ecx
0x180039a47  mov     [rbp+270h+var_2C8], rcx
0x180039a4b  test    rdi, rdi
0x180039a4e  jz      short loc_180039A61
0x180039a50  movzx   ecx, byte ptr [rdi+0Ah]
0x180039a54  shl     rcx, 5
0x180039a58  add     rcx, 28h ; '('
0x180039a5c  add     rcx, rdi
0x180039a5f  jmp     short loc_180039A63
0x180039a61  xor     ecx, ecx
0x180039a63  mov     eax, [rsi+0A90h]
0x180039a69  lea     rdx, byte_18030270F
0x180039a70  mov     dword ptr [rbp+270h+var_2E0], eax
0x180039a73  lea     rax, [rsi+60h]
0x180039a77  mov     [rbp+270h+var_2A0], rax
0x180039a7b  lea     rax, aPhysicaldisk; "PhysicalDisk"
0x180039a82  mov     [rbp+270h+var_2D0], rax
0x180039a86  lea     rax, [rbp+270h+var_2EC]
0x180039a8a  mov     [rsp+370h+var_2F8], rax
0x180039a8f  lea     rax, [rbp+270h+var_2E8]
0x180039a93  mov     [rsp+370h+var_300], rax
0x180039a98  lea     rax, [rbp+270h+var_2D8]
0x180039a9c  mov     [rsp+370h+var_308], rax
0x180039aa1  lea     rax, [rbp+270h+var_2C8]
0x180039aa5  mov     [rsp+370h+var_310], rax
0x180039aaa  lea     rax, [rbp+270h+var_2C0]
0x180039aae  mov     [rsp+370h+var_318], rax
0x180039ab3  lea     rax, [rbp+270h+var_2F0]
0x180039ab7  mov     [rsp+370h+var_320], rax
0x180039abc  lea     rax, [rbp+270h+var_2E0]
0x180039ac0  mov     [rsp+370h+var_328], rax
0x180039ac5  lea     rax, [rbp+270h+var_2B8]
0x180039ac9  mov     [rbp+270h+var_2C0], rcx
0x180039acd  mov     ecx, [rsi+0A84h]
0x180039ad3  mov     [rsp+370h+var_330], rax
0x180039ad8  add     rcx, 48h ; 'H'
0x180039adc  add     rcx, rsi
0x180039adf  mov     word ptr [rbp+270h+var_2F0], r12w
0x180039ae4  mov     [rbp+270h+var_2B8], rcx
0x180039ae8  lea     rax, [rbp+270h+var_2B0]
  ... truncated ...
```
