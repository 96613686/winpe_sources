# SuexUpdateFirmwareDrive(_SU_DRIVE_OBJECT *,ushort *,ushort)

- ea: `0x18003845c`
- end: `0x180038a51`
- name: `?SuexUpdateFirmwareDrive@@YAXPEAU_SU_DRIVE_OBJECT@@PEAGG@Z`
- size: `1525`
- prototype: `void(struct _SU_DRIVE_OBJECT *, unsigned __int16 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, installer_update`

## callers

- `0x18009cb84`

## callees

- `0x1800011b0`
- `0x1800014ec`
- `0x1800015b8`
- `0x180001f0c`
- `0x180006290`
- `0x180006cf4`
- `0x18000b964`
- `0x18000bb68`
- `0x18000cd44`
- `0x18000cd6c`
- `0x18000ce3c`
- `0x18003845c`
- `0x18019673c`
- `0x18019aa94`
- `0x18019e2c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003854d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800386b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003882c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003854d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800386b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003882c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800389ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800389d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800389ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800389d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038996`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800389b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038996`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800389b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800389e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800389e4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003853a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003853a`

## string_xrefs

- `0x18003848d`: `SuexUpdateFirmwareDrive`
- `0x1800385a0`: `SuexUpdateFirmwareDrive`
- `0x1800387d8`: `SuexUpdateFirmwareDrive`

## pseudocode

```c
void __fastcall SuexUpdateFirmwareDrive(struct _SU_DRIVE_OBJECT *a1, unsigned __int16 *a2, __int64 a3, __int64 a4)
{
  __int16 v4; // r12
  struct _STORAGE_HW_FIRMWARE_INFO *v7; // rdi
  __int64 v8; // r9
  char *FileW; // rax
  char *v10; // r14
  DWORD v11; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rcx
  char *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  unsigned __int8 *v19; // rbx
  unsigned __int8 *v20; // rcx
  DWORD v21; // eax
  __int64 v22; // r8
  __int64 v23; // r9
  char *v24; // rdx
  int v25; // ebx
  DWORD v26; // eax
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rcx
  char *v30; // rdx
  int v31; // ebx
  DWORD LastError; // eax
  BYTE *Revision; // rcx
  __int64 v34; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE v36; // rax
  int v37; // [rsp+80h] [rbp-80h] BYREF
  int v38; // [rsp+84h] [rbp-7Ch]
  unsigned __int64 v39; // [rsp+88h] [rbp-78h] BYREF
  struct _STORAGE_HW_FIRMWARE_INFO *v40; // [rsp+90h] [rbp-70h] BYREF
  LPVOID lpMem; // [rsp+98h] [rbp-68h] BYREF
  const char *v42; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 *v43; // [rsp+A8h] [rbp-58h] BYREF
  BYTE *v44; // [rsp+B0h] [rbp-50h] BYREF
  char *v45; // [rsp+B8h] [rbp-48h] BYREF
  char *v46; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v47; // [rsp+C8h] [rbp-38h] BYREF
  char *v48; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v49[4]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v50[5]; // [rsp+F8h] [rbp-8h] BYREF
  WCHAR FileName[264]; // [rsp+120h] [rbp+20h] BYREF

  v4 = a3;
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    v37 = 10405;
    lpMem = "SuexUpdateFirmwareDrive";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)a1,
      (__int64)byte_180300951,
      a3,
      a4,
      &lpMem);
  }
  memset_0(FileName, 0, 0x208u);
  v7 = 0;
  v40 = 0;
  lpMem = 0;
  CSmTimer::CSmTimer((CSmTimer *)v50);
  CSmTimer::CSmTimer((CSmTimer *)v49);
  v8 = *((unsigned int *)a1 + 28);
  *((_DWORD *)a1 + 4) = 0;
  StringCchPrintfW(FileName, 0x104u, L"\\\\.\\PhysicalDrive%d", v8);
  FileW = (char *)CreateFileW(FileName, 0xC0000000, 7u, 0, 3u, 0x80u, 0);
  v10 = FileW;
  if ( FileW != (char *)-1LL )
  {
    if ( (unsigned int)PuGetFirmware(FileW, (enum _STORAGE_BUS_TYPE)*((_DWORD *)a1 + 676), &v40) )
    {
      v7 = v40;
      if ( !a2
        || (CSmTimer::Start((CSmTimer *)v50),
            v25 = PuDownloadFirmware(v10, v7, a2, v4),
            CSmTimer::Stop((CSmTimer *)v50),
            v25) )
      {
        CSmTimer::Start((CSmTimer *)v49);
        v31 = PuActivateFirmware(v10, v7, a2, v4);
        CSmTimer::Stop((CSmTimer *)v49);
        if ( v31 )
          goto LABEL_8;
        LastError = GetLastError();
        v29 = LastError;
        *((_DWORD *)a1 + 4) = LastError;
        if ( LastError )
        {
          if ( LastError == 122 )
          {
            if ( (unsigned int)dword_180397B68 <= 3 )
              goto LABEL_8;
            v38 = 122;
            v30 = &byte_1802F9787;
            v37 = 10475;
          }
          else
          {
            if ( (unsigned int)dword_180397B68 <= 2 )
              goto LABEL_8;
            v38 = LastError;
            v30 = (char *)&dword_1802FE634;
            v37 = 10475;
          }
        }
        else
        {
          if ( (unsigned int)dword_180397B68 <= 4 )
            goto LABEL_8;
          v38 = 0;
          v30 = byte_1802FFF83;
          v37 = 10475;
        }
      }
      else
      {
        v26 = GetLastError();
        v29 = v26;
        *((_DWORD *)a1 + 4) = v26;
        if ( v26 )
        {
          if ( v26 == 122 )
          {
            if ( (unsigned int)dword_180397B68 <= 3 )
              goto LABEL_8;
            v38 = 122;
            v30 = byte_1802F6D25;
          }
          else
          {
            if ( (unsigned int)dword_180397B68 <= 2 )
              goto LABEL_8;
            v38 = v26;
            v30 = (char *)qword_1802F84F0;
          }
        }
        else
        {
          if ( (unsigned int)dword_180397B68 <= 4 )
            goto LABEL_8;
          v38 = 0;
          v30 = &byte_1802F4EEF;
        }
        v37 = 10459;
      }
      v39 = (unsigned __int64)"SuexUpdateFirmwareDrive";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v29,
        (__int64)v30,
        v27,
        v28,
        &v39);
      goto LABEL_8;
    }
    v21 = GetLastError();
    *((_DWORD *)a1 + 4) = v21;
    if ( v21 )
    {
      if ( v21 == 122 )
      {
        if ( (unsigned int)dword_180397B68 <= 3 )
          goto LABEL_22;
        v38 = 122;
        v24 = byte_1802F753B;
      }
      else
      {
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_22;
        v38 = v21;
        v24 = (char *)&word_1802FC1B6;
      }
    }
    else
    {
      if ( (unsigned int)dword_180397B68 <= 4 )
      {
LABEL_22:
        v7 = v40;
        goto LABEL_8;
      }
      v38 = 0;
      v24 = &byte_1802FED8F;
    }
    v37 = 10442;
    v39 = (unsigned __int64)"SuexUpdateFirmwareDrive";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v21,
      (__int64)v24,
      v22,
      v23,
      &v39);
    goto LABEL_22;
  }
  v11 = GetLastError();
  *((_DWORD *)a1 + 4) = v11;
  v14 = v11;
  if ( v11 )
  {
    if ( v11 == 122 )
    {
      if ( (unsigned int)dword_180397B68 <= 3 )
        goto LABEL_8;
      v38 = 122;
      v15 = byte_1802FF79D;
      v37 = 10432;
    }
    else
    {
      if ( (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_8;
      v38 = v11;
      v15 = (char *)qword_1802FC528;
      v37 = 10432;
    }
    goto LABEL_7;
  }
  v14 = (unsigned int)dword_180397B68;
  if ( (unsigned int)dword_180397B68 > 4 )
  {
    v37 = 0;
    v15 = &byte_1802FCE3F;
    v38 = 10432;
LABEL_7:
    v40 = (struct _STORAGE_HW_FIRMWARE_INFO *)"SuexUpdateFirmwareDrive";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v14,
      (__int64)v15,
      v12,
      v13,
      &v40);
  }
LABEL_8:
  PuGetFirmware(v10, *((enum _STORAGE_BUS_TYPE *)a1 + 676), (struct _STORAGE_HW_FIRMWARE_INFO **)&lpMem);
  v19 = (unsigned __int8 *)lpMem;
  if ( (unsigned int)dword_180397B68 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180397B68, 0x400000000000LL) )
  {
    v38 = *((_DWORD *)a1 + 4);
    v39 = (unsigned __int64)(1000LL * (v49[1] - v49[0])) / v49[2];
    lpMem = (LPVOID)((unsigned __int64)(1000LL * (v50[1] - v50[0])) / v50[2]);
    if ( v19 )
      v20 = &v19[32 * v19[10] + 40];
    else
      v20 = 0;
    v43 = v20;
    if ( v7 )
      Revision = v7->Slot[v7->ActiveSlot].Revision;
    else
      Revision = 0;
    LODWORD(v40) = *((_DWORD *)a1 + 676);
    v48 = (char *)a1 + 96;
    v42 = (const char *)L"PhysicalDisk";
    v44 = Revision;
    v34 = *((unsigned int *)a1 + 673);
    LOWORD(v37) = v4;
    v45 = (char *)a1 + v34 + 72;
    v46 = (char *)a1 + *((unsigned int *)a1 + 671) + 72;
    v47 = (__int64)a1 + *((unsigned int *)a1 + 670) + 72;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v47,
      (__int64)&byte_1802FB787,
      v17,
      v18,
      &v42,
      (__int64)&v48,
      &v47,
      &v46,
      &v45,
      (__int64)&v40,
      (__int64)&v37,
      &v44,
      &v43);
  }
  if ( v19 )
  {
    ProcessHeap = GetProcessHeap();
    if ( ProcessHeap )
      HeapFree(ProcessHeap, 0, v19);
  }
  if ( v7 )
  {
    v36 = GetProcessHeap();
    if ( v36 )
      HeapFree(v36, 0, v7);
  }
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v10);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v40) = 10510;
    v42 = "SuexUpdateFirmwareDrive";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v16,
      (__int64)byte_1802FD6F9,
      v17,
      v18,
      &v42);
  }
  CSmTimer::~CSmTimer((CSmTimer *)v49);
  CSmTimer::~CSmTimer((CSmTimer *)v50);
}

```

## disassembly

```asm
0x18003845c  push    rbp
0x18003845e  push    rbx
0x18003845f  push    rsi
0x180038460  push    rdi
0x180038461  push    r12
0x180038463  push    r14
0x180038465  push    r15
0x180038467  lea     rbp, [rsp-240h]
0x18003846f  sub     rsp, 340h
0x180038476  mov     rax, cs:__security_cookie
0x18003847d  xor     rax, rsp
0x180038480  mov     [rbp+270h+var_40], rax
0x180038487  mov     eax, cs:dword_180397B68
0x18003848d  lea     rbx, aSuexupdatefirm; "SuexUpdateFirmwareDrive"
0x180038494  movzx   r12d, r8w
0x180038498  mov     r15, rdx
0x18003849b  mov     rsi, rcx
0x18003849e  cmp     eax, 5
0x1800384a1  jbe     short loc_1800384CC
0x1800384a3  lea     rax, [rbp+270h+var_2F0]
0x1800384a7  mov     [rbp+270h+var_2F0], 28A5h
0x1800384ae  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x1800384b3  lea     rdx, byte_180300951
0x1800384ba  lea     rax, [rbp+270h+lpMem]
0x1800384be  mov     [rbp+270h+lpMem], rbx
0x1800384c2  mov     qword ptr [rsp+370h+dwCreationDisposition], rax
0x1800384c7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800384cc  xor     edx, edx; Val
0x1800384ce  lea     rcx, [rbp+270h+FileName]; void *
0x1800384d2  mov     r8d, 208h; Size
0x1800384d8  call    memset_0
0x1800384dd  xor     edi, edi
0x1800384df  lea     rcx, [rbp+270h+var_278]; this
0x1800384e3  mov     [rbp+270h+var_2E0], rdi
0x1800384e7  mov     [rbp+270h+lpMem], rdi
0x1800384eb  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x1800384f0  lea     rcx, [rbp+270h+var_298]; this
0x1800384f4  call    ??0CSmTimer@@QEAA@XZ; CSmTimer::CSmTimer(void)
0x1800384f9  mov     r9d, [rsi+70h]
0x1800384fd  lea     r8, aPhysicaldriveD_0; "\\\\.\\PhysicalDrive%d"
0x180038504  mov     edx, 104h; unsigned __int64
0x180038509  mov     [rsi+10h], edi
0x18003850c  lea     rcx, [rbp+270h+FileName]; unsigned __int16 *
0x180038510  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180038515  mov     [rsp+370h+hTemplateFile], rdi; hTemplateFile
0x18003851a  lea     r8d, [rdi+7]; dwShareMode
0x18003851e  mov     [rsp+370h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180038526  lea     rcx, [rbp+270h+FileName]; lpFileName
0x18003852a  xor     r9d, r9d; lpSecurityAttributes
0x18003852d  mov     [rsp+370h+dwCreationDisposition], 3; dwCreationDisposition
0x180038535  mov     edx, 0C0000000h; dwDesiredAccess
0x18003853a  call    cs:__imp_CreateFileW
0x180038540  mov     r14, rax
0x180038543  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180038547  jnz     loc_1800386A2
0x18003854d  call    cs:__imp_GetLastError
0x180038553  mov     [rsi+10h], eax
0x180038556  mov     ecx, eax
0x180038558  test    eax, eax
0x18003855a  jnz     loc_18003863F
0x180038560  mov     ecx, cs:dword_180397B68
0x180038566  cmp     ecx, 4
0x180038569  jbe     short loc_1800385A0
0x18003856b  lea     rax, [rbp+270h+var_2F0]
0x18003856f  mov     [rbp+270h+var_2F0], edi
0x180038572  mov     [rsp+370h+hTemplateFile], rax
0x180038577  lea     rdx, byte_1802FCE3F
0x18003857e  lea     rax, [rbp+270h+var_2EC]
0x180038582  mov     [rbp+270h+var_2EC], 28C0h
0x180038589  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x18003858e  lea     rax, [rbp+270h+var_2E0]
0x180038592  mov     qword ptr [rsp+370h+dwCreationDisposition], rax
0x180038597  mov     [rbp+270h+var_2E0], rbx
0x18003859b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800385a0  lea     r15, aSuexupdatefirm; "SuexUpdateFirmwareDrive"
0x1800385a7  mov     edx, [rsi+0A90h]; enum _STORAGE_BUS_TYPE
0x1800385ad  lea     r8, [rbp+270h+lpMem]; struct _STORAGE_HW_FIRMWARE_INFO **
0x1800385b1  mov     rcx, r14; hDevice
0x1800385b4  call    ?PuGetFirmware@@YAHPEAXW4_STORAGE_BUS_TYPE@@PEAPEAU_STORAGE_HW_FIRMWARE_INFO@@@Z; PuGetFirmware(void *,_STORAGE_BUS_TYPE,_STORAGE_HW_FIRMWARE_INFO * *)
0x1800385b9  mov     eax, cs:dword_180397B68
0x1800385bf  mov     rbx, [rbp+270h+lpMem]
0x1800385c3  cmp     eax, 5
0x1800385c6  jbe     loc_180038991
0x1800385cc  mov     rdx, 400000000000h
0x1800385d6  lea     rcx, dword_180397B68
0x1800385dd  call    _tlgKeywordOn
0x1800385e2  test    al, al
0x1800385e4  jz      loc_180038991
0x1800385ea  mov     eax, [rsi+10h]
0x1800385ed  xor     edx, edx
0x1800385ef  mov     [rbp+270h+var_2EC], eax
0x1800385f2  mov     rax, [rbp+270h+var_290]
0x1800385f6  sub     rax, [rbp+270h+var_298]
0x1800385fa  imul    rax, 3E8h
0x180038601  div     [rbp+270h+var_288]
0x180038605  xor     edx, edx
0x180038607  mov     [rbp+270h+var_2E8], rax
0x18003860b  mov     rax, [rbp+270h+var_270]
0x18003860f  sub     rax, [rbp+270h+var_278]
0x180038613  imul    rax, 3E8h
0x18003861a  div     [rbp+270h+var_268]
0x18003861e  mov     [rbp+270h+lpMem], rax
0x180038622  test    rbx, rbx
0x180038625  jz      loc_1800388A3
0x18003862b  movzx   ecx, byte ptr [rbx+0Ah]
0x18003862f  shl     rcx, 5
0x180038633  add     rcx, 28h ; '('
0x180038637  add     rcx, rbx
0x18003863a  jmp     loc_1800388A5
0x18003863f  mov     eax, cs:dword_180397B68
0x180038645  cmp     ecx, 7Ah ; 'z'
0x180038648  jnz     short loc_180038676
0x18003864a  cmp     eax, 3
0x18003864d  jbe     loc_1800385A0
0x180038653  lea     rax, [rbp+270h+var_2EC]
0x180038657  mov     [rbp+270h+var_2EC], ecx
0x18003865a  mov     [rsp+370h+hTemplateFile], rax
0x18003865f  lea     rdx, byte_1802FF79D
0x180038666  lea     rax, [rbp+270h+var_2F0]
0x18003866a  mov     [rbp+270h+var_2F0], 28C0h
0x180038671  jmp     loc_180038589
0x180038676  cmp     eax, 2
0x180038679  jbe     loc_1800385A0
0x18003867f  lea     rax, [rbp+270h+var_2EC]
0x180038683  mov     [rbp+270h+var_2EC], ecx
0x180038686  mov     [rsp+370h+hTemplateFile], rax
0x18003868b  lea     rdx, qword_1802FC528
0x180038692  lea     rax, [rbp+270h+var_2F0]
0x180038696  mov     [rbp+270h+var_2F0], 28C0h
0x18003869d  jmp     loc_180038589
0x1800386a2  mov     edx, [rsi+0A90h]; enum _STORAGE_BUS_TYPE
0x1800386a8  lea     r8, [rbp+270h+var_2E0]; struct _STORAGE_HW_FIRMWARE_INFO **
0x1800386ac  mov     rcx, r14; hDevice
0x1800386af  call    ?PuGetFirmware@@YAHPEAXW4_STORAGE_BUS_TYPE@@PEAPEAU_STORAGE_HW_FIRMWARE_INFO@@@Z; PuGetFirmware(void *,_STORAGE_BUS_TYPE,_STORAGE_HW_FIRMWARE_INFO * *)
0x1800386b4  test    eax, eax
0x1800386b6  jnz     short loc_180038737
0x1800386b8  call    cs:__imp_GetLastError
0x1800386be  mov     ecx, eax
0x1800386c0  mov     [rsi+10h], eax
0x1800386c3  test    eax, eax
0x1800386c5  mov     eax, cs:dword_180397B68
0x1800386cb  jnz     short loc_180038710
0x1800386cd  cmp     eax, 4
0x1800386d0  jbe     short loc_180038707
0x1800386d2  mov     [rbp+270h+var_2EC], edi
0x1800386d5  lea     rdx, byte_1802FED8F
0x1800386dc  lea     rax, [rbp+270h+var_2EC]
0x1800386e0  mov     [rbp+270h+var_2F0], 28CAh
0x1800386e7  mov     [rsp+370h+hTemplateFile], rax
0x1800386ec  lea     rax, [rbp+270h+var_2F0]
0x1800386f0  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x1800386f5  lea     rax, [rbp+270h+var_2E8]
0x1800386f9  mov     qword ptr [rsp+370h+dwCreationDisposition], rax
0x1800386fe  mov     [rbp+270h+var_2E8], rbx
0x180038702  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180038707  mov     rdi, [rbp+270h+var_2E0]
0x18003870b  jmp     loc_1800385A0
0x180038710  cmp     ecx, 7Ah ; 'z'
0x180038713  jnz     short loc_180038726
0x180038715  cmp     eax, 3
0x180038718  jbe     short loc_180038707
0x18003871a  mov     [rbp+270h+var_2EC], ecx
0x18003871d  lea     rdx, byte_1802F753B
0x180038724  jmp     short loc_1800386DC
0x180038726  cmp     eax, 2
0x180038729  jbe     short loc_180038707
0x18003872b  mov     [rbp+270h+var_2EC], ecx
0x18003872e  lea     rdx, word_1802FC1B6
0x180038735  jmp     short loc_1800386DC
0x180038737  mov     rdi, [rbp+270h+var_2E0]
0x18003873b  test    r15, r15
0x18003873e  jz      loc_1800387FF
0x180038744  lea     rcx, [rbp+270h+var_278]; this
0x180038748  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x18003874d  mov     r9b, r12b; unsigned __int8
0x180038750  mov     r8, r15; unsigned __int16 *
0x180038753  mov     rdx, rdi; struct _STORAGE_HW_FIRMWARE_INFO *
0x180038756  mov     rcx, r14; hDevice
0x180038759  call    ?PuDownloadFirmware@@YAHPEAXPEAU_STORAGE_HW_FIRMWARE_INFO@@PEBGE@Z; PuDownloadFirmware(void *,_STORAGE_HW_FIRMWARE_INFO *,ushort const *,uchar)
0x18003875e  lea     rcx, [rbp+270h+var_278]; this
0x180038762  mov     ebx, eax
0x180038764  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180038769  test    ebx, ebx
0x18003876b  jnz     loc_1800387FF
0x180038771  call    cs:__imp_GetLastError
0x180038777  mov     ecx, eax
0x180038779  mov     [rsi+10h], eax
0x18003877c  test    eax, eax
0x18003877e  mov     eax, cs:dword_180397B68
0x180038784  jnz     short loc_18003879B
0x180038786  cmp     eax, 4
0x180038789  jbe     loc_1800385A0
0x18003878f  mov     [rbp+270h+var_2EC], ebx
0x180038792  lea     rdx, byte_1802F4EEF
0x180038799  jmp     short loc_1800387C8
0x18003879b  cmp     ecx, 7Ah ; 'z'
0x18003879e  jnz     short loc_1800387B5
0x1800387a0  cmp     eax, 3
0x1800387a3  jbe     loc_1800385A0
0x1800387a9  mov     [rbp+270h+var_2EC], ecx
0x1800387ac  lea     rdx, byte_1802F6D25
0x1800387b3  jmp     short loc_1800387C8
0x1800387b5  cmp     eax, 2
0x1800387b8  jbe     loc_1800385A0
0x1800387be  mov     [rbp+270h+var_2EC], ecx
0x1800387c1  lea     rdx, qword_1802F84F0
0x1800387c8  mov     [rbp+270h+var_2F0], 28DBh
0x1800387cf  lea     rax, [rbp+270h+var_2EC]
0x1800387d3  mov     [rsp+370h+hTemplateFile], rax
0x1800387d8  lea     r15, aSuexupdatefirm; "SuexUpdateFirmwareDrive"
0x1800387df  lea     rax, [rbp+270h+var_2F0]
0x1800387e3  mov     [rbp+270h+var_2E8], r15
0x1800387e7  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], rax
0x1800387ec  lea     rax, [rbp+270h+var_2E8]
0x1800387f0  mov     qword ptr [rsp+370h+dwCreationDisposition], rax
0x1800387f5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800387fa  jmp     loc_1800385A7
0x1800387ff  lea     rcx, [rbp+270h+var_298]; this
0x180038803  call    ?Start@CSmTimer@@QEAAXXZ; CSmTimer::Start(void)
0x180038808  mov     r9b, r12b; unsigned __int8
0x18003880b  mov     r8, r15; unsigned __int16 *
0x18003880e  mov     rdx, rdi; struct _STORAGE_HW_FIRMWARE_INFO *
0x180038811  mov     rcx, r14; hDevice
0x180038814  call    ?PuActivateFirmware@@YAHPEAXPEAU_STORAGE_HW_FIRMWARE_INFO@@PEBGE@Z; PuActivateFirmware(void *,_STORAGE_HW_FIRMWARE_INFO *,ushort const *,uchar)
0x180038819  lea     rcx, [rbp+270h+var_298]; this
0x18003881d  mov     ebx, eax
0x18003881f  call    ?Stop@CSmTimer@@QEAAXXZ; CSmTimer::Stop(void)
0x180038824  test    ebx, ebx
0x180038826  jnz     loc_1800385A0
0x18003882c  call    cs:__imp_GetLastError
0x180038832  mov     ecx, eax
0x180038834  mov     [rsi+10h], eax
0x180038837  test    eax, eax
0x180038839  mov     eax, cs:dword_180397B68
0x18003883f  jnz     short loc_180038860
0x180038841  cmp     eax, 4
0x180038844  jbe     loc_1800385A0
0x18003884a  mov     [rbp+270h+var_2EC], ebx
0x18003884d  lea     rdx, byte_1802FFF83
0x180038854  mov     [rbp+270h+var_2F0], 28EBh
0x18003885b  jmp     loc_1800387CF
0x180038860  cmp     ecx, 7Ah ; 'z'
0x180038863  jnz     short loc_180038884
0x180038865  cmp     eax, 3
0x180038868  jbe     loc_1800385A0
0x18003886e  mov     [rbp+270h+var_2EC], ecx
0x180038871  lea     rdx, byte_1802F9787
0x180038878  mov     [rbp+270h+var_2F0], 28EBh
0x18003887f  jmp     loc_1800387CF
0x180038884  cmp     eax, 2
0x180038887  jbe     loc_1800385A0
0x18003888d  mov     [rbp+270h+var_2EC], ecx
0x180038890  lea     rdx, dword_1802FE634
0x180038897  mov     [rbp+270h+var_2F0], 28EBh
0x18003889e  jmp     loc_1800387CF
0x1800388a3  xor     ecx, ecx
0x1800388a5  mov     [rbp+270h+var_2C8], rcx
0x1800388a9  test    rdi, rdi
0x1800388ac  jz      short loc_1800388BF
0x1800388ae  movzx   ecx, byte ptr [rdi+0Ah]
0x1800388b2  shl     rcx, 5
0x1800388b6  add     rcx, 28h ; '('
0x1800388ba  add     rcx, rdi
0x1800388bd  jmp     short loc_1800388C1
0x1800388bf  xor     ecx, ecx
0x1800388c1  mov     eax, [rsi+0A90h]
0x1800388c7  lea     rdx, byte_1802FB787
0x1800388ce  mov     dword ptr [rbp+270h+var_2E0], eax
0x1800388d1  lea     rax, [rsi+60h]
0x1800388d5  mov     [rbp+270h+var_2A0], rax
0x1800388d9  lea     rax, aPhysicaldisk; "PhysicalDisk"
0x1800388e0  mov     [rbp+270h+var_2D0], rax
0x1800388e4  lea     rax, [rbp+270h+var_2EC]
0x1800388e8  mov     [rsp+370h+var_2F8], rax
0x1800388ed  lea     rax, [rbp+270h+var_2E8]
0x1800388f1  mov     [rsp+370h+var_300], rax
0x1800388f6  lea     rax, [rbp+270h+lpMem]
0x1800388fa  mov     [rsp+370h+var_308], rax
0x1800388ff  lea     rax, [rbp+270h+var_2C8]
0x180038903  mov     [rsp+370h+var_310], rax
0x180038908  lea     rax, [rbp+270h+var_2C0]
0x18003890c  mov     [rsp+370h+var_318], rax
0x180038911  lea     rax, [rbp+270h+var_2F0]
0x180038915  mov     [rsp+370h+var_320], rax
0x18003891a  lea     rax, [rbp+270h+var_2E0]
0x18003891e  mov     [rsp+370h+var_328], rax
0x180038923  lea     rax, [rbp+270h+var_2B8]
0x180038927  mov     [rbp+270h+var_2C0], rcx
0x18003892b  mov     ecx, [rsi+0A84h]
0x180038931  mov     [rsp+370h+var_330], rax
0x180038936  add     rcx, 48h ; 'H'
0x18003893a  add     rcx, rsi
0x18003893d  mov     word ptr [rbp+270h+var_2F0], r12w
0x180038942  mov     [rbp+270h+var_2B8], rcx
0x180038946  lea     rax, [rbp+270h+var_2B0]
0x18003894a  mov     ecx, [rsi+0A7Ch]
0x180038950  mov     [rsp+370h+var_338], rax
0x180038955  add     rcx, 48h ; 'H'
0x180038959  add     rcx, rsi
0x18003895c  lea     rax, [rbp+270h+var_2A8]
  ... truncated ...
```
