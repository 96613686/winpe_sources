# NGENService::ServiceControl(__MIDL___MIDL_itf_mscorsvc_0000_0001_0001,_COR_SERVICE_STATUS *)

- ea: `0x18001bf08`
- end: `0x18001c318`
- name: `?ServiceControl@NGENService@@YAJW4__MIDL___MIDL_itf_mscorsvc_0000_0001_0001@@PEAU_COR_SERVICE_STATUS@@@Z`
- size: `1040`
- prototype: `__int64 __fastcall(NGENService *, __int64, bool)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x180008500`
- `0x18001bf08`

## callees

- `0x180007914`
- `0x18001a690`
- `0x18001aca8`
- `0x18001ae6c`
- `0x18001afbc`
- `0x18001bf08`
- `0x18002e1d0`
- `0x18003069c`
- `0x1800364c0`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18001c0c5`
- `KERNEL32!LoadLibraryExW` at `0x18001c0c5`
- `KERNEL32!CloseHandle` at `0x18001bfc7`
- `KERNEL32!CloseHandle` at `0x18001c035`
- `KERNEL32!CloseHandle` at `0x18001c1df`
- `KERNEL32!CloseHandle` at `0x18001c2b7`
- `KERNEL32!CloseHandle` at `0x18001bfc7`
- `KERNEL32!CloseHandle` at `0x18001c035`
- `KERNEL32!CloseHandle` at `0x18001c1df`
- `KERNEL32!CloseHandle` at `0x18001c2b7`
- `KERNEL32!GetLastError` at `0x18001c110`
- `KERNEL32!GetLastError` at `0x18001c119`
- `KERNEL32!GetLastError` at `0x18001c2c8`
- `KERNEL32!GetLastError` at `0x18001c110`
- `KERNEL32!GetLastError` at `0x18001c119`
- `KERNEL32!GetLastError` at `0x18001c2c8`
- `KERNEL32!GetProcAddress` at `0x18001c0da`
- `KERNEL32!GetProcAddress` at `0x18001c0da`

## string_xrefs

- `0x18001c0be`: `advapi32.dll`
- `0x18001c0d0`: `ControlService`
- `0x18001bf90`: `ngenservicelock.dat`
- `0x18001c1a2`: `ngenservicelock.dat`
- `0x18001bfa7`: `DoneWork(): Failed to acquire service lock\n`
- `0x18001c29b`: `DoneWork(): Failed to acquire service lock\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=52
__int64 __fastcall NGENService::ServiceControl(NGENService *a1, __int64 a2, bool a3)
{
  int v4; // r12d
  struct SC_HANDLE__ *v5; // r15
  __int64 result; // rax
  struct _COR_SERVICE_STATUS *v7; // rdx
  const unsigned __int16 *v8; // rdx
  NGENService *v9; // rcx
  signed int CLRServiceStatus; // ebx
  struct _COR_SERVICE_STATUS *v11; // rdx
  bool v12; // r8
  unsigned int v13; // esi
  int v14; // edi
  FARPROC ProcAddress; // rax
  HMODULE Library; // rax
  DWORD LastError; // r14d
  signed int v18; // eax
  int v19; // edx
  int v20; // edi
  int v21; // edx
  const unsigned __int16 *v22; // rdx
  NGENService *v23; // rcx
  bool v24; // zf
  bool v25; // zf
  struct _COR_SERVICE_STATUS *v26; // rdx
  signed int v27; // eax
  struct SC_HANDLE__ *v28; // [rsp+28h] [rbp-A9h] BYREF
  HANDLE hObject; // [rsp+30h] [rbp-A1h]
  _BYTE v30[32]; // [rsp+38h] [rbp-99h] BYREF
  wchar_t Buffer[66]; // [rsp+58h] [rbp-79h] BYREF
  int v32; // [rsp+DCh] [rbp+Bh]

  v4 = (int)a1;
  v5 = 0;
  v28 = 0;
  if ( !(_DWORD)a1 )
  {
    result = NGENService::StartServiceW(a1, 0, a3);
    if ( (int)result < 0 )
      return result;
    goto LABEL_42;
  }
  if ( (_DWORD)a1 != 5 )
  {
    if ( (_DWORD)a1 == 4 )
      return NGENService::GetCLRServiceStatus((wchar_t *)a2, (struct _COR_SERVICE_STATUS *)a2);
    CLRServiceStatus = NGENService::OpenNGENService((NGENService *)&v28, (struct SC_HANDLE__ **)a2);
    if ( CLRServiceStatus < 0 )
    {
LABEL_20:
      v5 = v28;
      goto LABEL_75;
    }
    switch ( v4 )
    {
      case 1:
        v13 = 1;
        break;
      case 2:
        v13 = 2;
        break;
      case 3:
        v13 = 3;
        break;
      default:
        CLRServiceStatus = 160;
        goto LABEL_20;
    }
    v14 = 0;
    v5 = v28;
    while ( 1 )
    {
      ProcAddress = (FARPROC)qword_18006FF30;
      if ( qword_18006FF30
        || !bControlServiceProbed
        && ((Library = LoadLibraryExW(L"advapi32.dll", 0, 0)) == 0
          ? (ProcAddress = (FARPROC)qword_18006FF30)
          : (FARPROC)(ProcAddress = GetProcAddress(Library, "ControlService"), qword_18006FF30 = (__int64)ProcAddress),
            bControlServiceProbed = 1,
            ProcAddress) )
      {
        if ( ((unsigned int (__fastcall *)(struct SC_HANDLE__ *, _QWORD, _BYTE *))ProcAddress)(v5, v13, v30) )
          goto LABEL_42;
      }
      LastError = GetLastError();
      v18 = GetLastError();
      CLRServiceStatus = (unsigned __int16)v18 | 0x80070000;
      if ( v18 <= 0 )
        CLRServiceStatus = v18;
      if ( LastError != 1061 && LastError != 1052 || v14 >= 60 )
        goto LABEL_75;
      ClrSleepEx(0x1F4u, v19);
      ++v14;
    }
  }
  hObject = (HANDLE)-1LL;
  v28 = (struct SC_HANDLE__ *)&VersionedMutexHolder::`vftable';
  CLRServiceStatus = FileLockHolder::AcquireNoThrow((FileLockHolder *)&v28, L"ngenservicelock.dat", 0, 0);
  if ( CLRServiceStatus < 0 )
  {
    NGENService::DebugLog((NGENService *)L"DoneWork(): Failed to acquire service lock\n", v8);
    goto LABEL_7;
  }
  CLRServiceStatus = NGENService::WaitForServiceShutdown(v9);
  if ( CLRServiceStatus < 0 || (CLRServiceStatus = NGENService::GetCLRServiceStatus(Buffer, v11), CLRServiceStatus < 0) )
  {
LABEL_7:
    v28 = (struct SC_HANDLE__ *)&FileLockHolder::`vftable';
    if ( hObject != (HANDLE)-1LL )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
    }
    return (unsigned int)CLRServiceStatus;
  }
  if ( v32 == 1 )
  {
    CLRServiceStatus = NGENService::StartServiceW(0, 1, v12);
    if ( CLRServiceStatus < 0 )
      goto LABEL_7;
  }
  else
  {
    CLRServiceStatus = NGENService::ServiceControl(2, Buffer);
    if ( CLRServiceStatus < 0 )
      goto LABEL_7;
  }
  v28 = (struct SC_HANDLE__ *)&FileLockHolder::`vftable';
  if ( hObject != (HANDLE)-1LL )
  {
    CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
  }
LABEL_42:
  v20 = 0;
  if ( (int)NGENService::GetCLRServiceStatus((wchar_t *)a2, v7) < 0 )
  {
LABEL_73:
    v27 = GetLastError();
    CLRServiceStatus = (unsigned __int16)v27 | 0x80070000;
    if ( v27 <= 0 )
      CLRServiceStatus = v27;
    goto LABEL_75;
  }
  while ( 1 )
  {
    v21 = *(_DWORD *)(a2 + 132);
    if ( v21 == 3 )
      break;
    if ( v21 == 1 )
      goto LABEL_72;
    switch ( v4 )
    {
      case 0:
        goto LABEL_53;
      case 1:
        goto LABEL_60;
      case 3:
LABEL_53:
        v24 = v21 == 4;
        break;
      default:
        v24 = v21 == 7;
        break;
    }
    if ( v24 )
    {
LABEL_72:
      CLRServiceStatus = 0;
      goto LABEL_75;
    }
    switch ( v4 )
    {
      case 0:
        v25 = v21 == 2;
LABEL_64:
        if ( !v25 )
          goto LABEL_60;
        goto LABEL_65;
      case 2:
        v25 = v21 == 6;
        goto LABEL_64;
      case 3:
        v25 = v21 == 5;
        goto LABEL_64;
    }
    if ( ((v21 - 2) & 0xFFFFFFF9) != 0 || v21 == 8 )
    {
LABEL_60:
      CLRServiceStatus = -2147467259;
      goto LABEL_75;
    }
LABEL_65:
    if ( v20 >= 60 )
      goto LABEL_60;
    ++v20;
    ClrSleepEx(0x1F4u, v21);
    if ( (int)NGENService::GetCLRServiceStatus((wchar_t *)a2, v26) < 0 )
      goto LABEL_73;
  }
  hObject = (HANDLE)-1LL;
  v28 = (struct SC_HANDLE__ *)&VersionedMutexHolder::`vftable';
  CLRServiceStatus = FileLockHolder::AcquireNoThrow((FileLockHolder *)&v28, L"ngenservicelock.dat", 0, 0);
  if ( CLRServiceStatus >= 0 )
  {
    CLRServiceStatus = NGENService::WaitForServiceShutdown(v23);
    if ( CLRServiceStatus < 0 )
      goto LABEL_70;
    v28 = (struct SC_HANDLE__ *)&FileLockHolder::`vftable';
    if ( hObject != (HANDLE)-1LL )
    {
      CloseHandle(hObject);
      hObject = (HANDLE)-1LL;
    }
    goto LABEL_65;
  }
  NGENService::DebugLog((NGENService *)L"DoneWork(): Failed to acquire service lock\n", v22);
LABEL_70:
  v28 = (struct SC_HANDLE__ *)&FileLockHolder::`vftable';
  if ( hObject != (HANDLE)-1LL )
  {
    CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
  }
LABEL_75:
  if ( v5 )
    CLRCloseServiceHandle(v5);
  return (unsigned int)CLRServiceStatus;
}

```

## disassembly

```asm
0x18001bf08  mov     rax, rsp
0x18001bf0b  mov     [rax+8], rbx
0x18001bf0f  mov     [rax+18h], rsi
0x18001bf13  mov     [rax+20h], rdi
0x18001bf17  push    rbp
0x18001bf18  push    r12
0x18001bf1a  push    r13
0x18001bf1c  push    r14
0x18001bf1e  push    r15
0x18001bf20  lea     rbp, [rax-5Fh]
0x18001bf24  sub     rsp, 100h
0x18001bf2b  mov     rax, cs:__security_cookie
0x18001bf32  xor     rax, rsp
0x18001bf35  mov     [rbp+57h+var_30], rax
0x18001bf39  mov     r13, rdx
0x18001bf3c  mov     r12d, ecx
0x18001bf3f  xor     r15d, r15d
0x18001bf42  mov     [rsp+120h+var_100], r15
0x18001bf47  lea     r14, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x18001bf4e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001bf52  lea     rbx, ??_7VersionedMutexHolder@@6B@; const VersionedMutexHolder::`vftable'
0x18001bf59  test    ecx, ecx
0x18001bf5b  jnz     short loc_18001BF71
0x18001bf5d  xor     edx, edx; bool
0x18001bf5f  call    ?StartServiceW@NGENService@@YAJ_N0@Z; NGENService::StartServiceW(bool,bool)
0x18001bf64  test    eax, eax
0x18001bf66  jns     loc_18001C16F
0x18001bf6c  jmp     loc_18001C2EB
0x18001bf71  cmp     r12d, 5
0x18001bf75  jnz     loc_18001C045
0x18001bf7b  mov     [rsp+120h+var_100], r14
0x18001bf80  mov     [rsp+120h+hObject], rsi
0x18001bf85  mov     [rsp+120h+var_100], rbx
0x18001bf8a  xor     r9d, r9d; int *
0x18001bf8d  xor     r8d, r8d; void *
0x18001bf90  lea     rdx, aNgenserviceloc; "ngenservicelock.dat"
0x18001bf97  lea     rcx, [rsp+120h+var_100]; this
0x18001bf9c  call    ?AcquireNoThrow@FileLockHolder@@QEAAJPEBGPEAXPEAH@Z; FileLockHolder::AcquireNoThrow(ushort const *,void *,int *)
0x18001bfa1  mov     ebx, eax
0x18001bfa3  test    eax, eax
0x18001bfa5  jns     short loc_18001BFD7
0x18001bfa7  lea     rcx, aDoneworkFailed_0; "DoneWork(): Failed to acquire service l"...
0x18001bfae  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18001bfb3  nop
0x18001bfb4  mov     [rsp+120h+var_100], r14
0x18001bfb9  mov     rcx, [rsp+120h+hObject]; hObject
0x18001bfbe  cmp     rcx, rsi
0x18001bfc1  jz      loc_18001C2E9
0x18001bfc7  call    cs:__imp_CloseHandle
0x18001bfcd  mov     [rsp+120h+hObject], rsi
0x18001bfd2  jmp     loc_18001C2E9
0x18001bfd7  call    ?WaitForServiceShutdown@NGENService@@YAJXZ; NGENService::WaitForServiceShutdown(void)
0x18001bfdc  mov     ebx, eax
0x18001bfde  test    eax, eax
0x18001bfe0  jns     short loc_18001BFE4
0x18001bfe2  jmp     short loc_18001BFB4
0x18001bfe4  lea     rcx, [rbp+57h+Buffer]; Buffer
0x18001bfe8  call    ?GetCLRServiceStatus@NGENService@@YAJPEAU_COR_SERVICE_STATUS@@@Z; NGENService::GetCLRServiceStatus(_COR_SERVICE_STATUS *)
0x18001bfed  mov     ebx, eax
0x18001bfef  test    eax, eax
0x18001bff1  jns     short loc_18001BFF5
0x18001bff3  jmp     short loc_18001BFB4
0x18001bff5  cmp     [rbp+57h+var_4C], 1
0x18001bff9  jnz     short loc_18001C00C
0x18001bffb  mov     dl, 1; bool
0x18001bffd  xor     ecx, ecx; this
0x18001bfff  call    ?StartServiceW@NGENService@@YAJ_N0@Z; NGENService::StartServiceW(bool,bool)
0x18001c004  mov     ebx, eax
0x18001c006  test    eax, eax
0x18001c008  jns     short loc_18001C022
0x18001c00a  jmp     short loc_18001BFB4
0x18001c00c  lea     rdx, [rbp+57h+Buffer]
0x18001c010  mov     ecx, 2
0x18001c015  call    ?ServiceControl@NGENService@@YAJW4__MIDL___MIDL_itf_mscorsvc_0000_0001_0001@@PEAU_COR_SERVICE_STATUS@@@Z; NGENService::ServiceControl(__MIDL___MIDL_itf_mscorsvc_0000_0001_0001,_COR_SERVICE_STATUS *)
0x18001c01a  mov     ebx, eax
0x18001c01c  test    eax, eax
0x18001c01e  jns     short loc_18001C022
0x18001c020  jmp     short loc_18001BFB4
0x18001c022  mov     [rsp+120h+var_100], r14
0x18001c027  mov     rcx, [rsp+120h+hObject]; hObject
0x18001c02c  cmp     rcx, rsi
0x18001c02f  jz      loc_18001C168
0x18001c035  call    cs:__imp_CloseHandle
0x18001c03b  mov     [rsp+120h+hObject], rsi
0x18001c040  jmp     loc_18001C168
0x18001c045  cmp     r12d, 4
0x18001c049  jnz     short loc_18001C058
0x18001c04b  mov     rcx, r13; Buffer
0x18001c04e  call    ?GetCLRServiceStatus@NGENService@@YAJPEAU_COR_SERVICE_STATUS@@@Z; NGENService::GetCLRServiceStatus(_COR_SERVICE_STATUS *)
0x18001c053  jmp     loc_18001C2EB
0x18001c058  lea     rcx, [rsp+120h+var_100]; this
0x18001c05d  call    ?OpenNGENService@NGENService@@YAJPEAPEAUSC_HANDLE__@@@Z; NGENService::OpenNGENService(SC_HANDLE__ * *)
0x18001c062  mov     ebx, eax
0x18001c064  test    eax, eax
0x18001c066  jns     short loc_18001C072
0x18001c068  mov     r15, [rsp+120h+var_100]
0x18001c06d  jmp     loc_18001C2DC
0x18001c072  mov     ecx, r12d
0x18001c075  sub     ecx, 1
0x18001c078  jz      short loc_18001C099
0x18001c07a  sub     ecx, 1
0x18001c07d  jz      short loc_18001C092
0x18001c07f  cmp     ecx, 1
0x18001c082  jz      short loc_18001C08B
0x18001c084  mov     ebx, 0A0h
0x18001c089  jmp     short loc_18001C068
0x18001c08b  mov     esi, 3
0x18001c090  jmp     short loc_18001C09E
0x18001c092  mov     esi, 2
0x18001c097  jmp     short loc_18001C09E
0x18001c099  mov     esi, 1
0x18001c09e  xor     edi, edi
0x18001c0a0  mov     r15, [rsp+120h+var_100]
0x18001c0a5  mov     rax, cs:qword_18006FF30
0x18001c0ac  test    rax, rax
0x18001c0af  jnz     short loc_18001C0FC
0x18001c0b1  cmp     cs:?bControlServiceProbed@@3_NA, al; bool bControlServiceProbed
0x18001c0b7  jnz     short loc_18001C110
0x18001c0b9  xor     r8d, r8d; dwFlags
0x18001c0bc  xor     edx, edx; hFile
0x18001c0be  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x18001c0c5  call    cs:__imp_LoadLibraryExW
0x18001c0cb  test    rax, rax
0x18001c0ce  jz      short loc_18001C0E9
0x18001c0d0  lea     rdx, aControlservice; "ControlService"
0x18001c0d7  mov     rcx, rax; hModule
0x18001c0da  call    cs:__imp_GetProcAddress
0x18001c0e0  mov     cs:qword_18006FF30, rax
0x18001c0e7  jmp     short loc_18001C0F0
0x18001c0e9  mov     rax, cs:qword_18006FF30
0x18001c0f0  mov     cs:?bControlServiceProbed@@3_NA, 1; bool bControlServiceProbed
0x18001c0f7  test    rax, rax
0x18001c0fa  jz      short loc_18001C110
0x18001c0fc  lea     r8, [rsp+120h+var_F0]
0x18001c101  mov     edx, esi
0x18001c103  mov     rcx, r15
0x18001c106  call    cs:__guard_dispatch_icall_fptr
0x18001c10c  test    eax, eax
0x18001c10e  jnz     short loc_18001C15D
0x18001c110  call    cs:__imp_GetLastError
0x18001c116  mov     r14d, eax
0x18001c119  call    cs:__imp_GetLastError
0x18001c11f  movzx   ebx, ax
0x18001c122  or      ebx, 80070000h
0x18001c128  test    eax, eax
0x18001c12a  cmovle  ebx, eax
0x18001c12d  cmp     r14d, 425h
0x18001c134  jz      short loc_18001C143
0x18001c136  cmp     r14d, 41Ch
0x18001c13d  jnz     loc_18001C2DC
0x18001c143  cmp     edi, 3Ch ; '<'
0x18001c146  jge     loc_18001C2DC
0x18001c14c  mov     ecx, 1F4h; unsigned int
0x18001c151  call    ?ClrSleepEx@@YAKKH@Z; ClrSleepEx(ulong,int)
0x18001c156  inc     edi
0x18001c158  jmp     loc_18001C0A5
0x18001c15d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001c161  lea     r14, ??_7FileLockHolder@@6B@; const FileLockHolder::`vftable'
0x18001c168  lea     rbx, ??_7VersionedMutexHolder@@6B@; const VersionedMutexHolder::`vftable'
0x18001c16f  xor     edi, edi
0x18001c171  mov     rcx, r13; Buffer
0x18001c174  call    ?GetCLRServiceStatus@NGENService@@YAJPEAU_COR_SERVICE_STATUS@@@Z; NGENService::GetCLRServiceStatus(_COR_SERVICE_STATUS *)
0x18001c179  test    eax, eax
0x18001c17b  js      loc_18001C2C8
0x18001c181  mov     edx, [r13+84h]; int
0x18001c188  cmp     edx, 3
0x18001c18b  jnz     short loc_18001C1EF
0x18001c18d  mov     [rsp+120h+var_100], r14
0x18001c192  mov     [rsp+120h+hObject], rsi
0x18001c197  mov     [rsp+120h+var_100], rbx
0x18001c19c  xor     r9d, r9d; int *
0x18001c19f  xor     r8d, r8d; void *
0x18001c1a2  lea     rdx, aNgenserviceloc; "ngenservicelock.dat"
0x18001c1a9  lea     rcx, [rsp+120h+var_100]; this
0x18001c1ae  call    ?AcquireNoThrow@FileLockHolder@@QEAAJPEBGPEAXPEAH@Z; FileLockHolder::AcquireNoThrow(ushort const *,void *,int *)
0x18001c1b3  mov     ebx, eax
0x18001c1b5  test    eax, eax
0x18001c1b7  js      loc_18001C29B
0x18001c1bd  call    ?WaitForServiceShutdown@NGENService@@YAJXZ; NGENService::WaitForServiceShutdown(void)
0x18001c1c2  mov     ebx, eax
0x18001c1c4  test    eax, eax
0x18001c1c6  js      loc_18001C299
0x18001c1cc  mov     [rsp+120h+var_100], r14
0x18001c1d1  mov     rcx, [rsp+120h+hObject]; hObject
0x18001c1d6  cmp     rcx, rsi
0x18001c1d9  jz      loc_18001C270
0x18001c1df  call    cs:__imp_CloseHandle
0x18001c1e5  mov     [rsp+120h+hObject], rsi
0x18001c1ea  jmp     loc_18001C270
0x18001c1ef  cmp     edx, 1
0x18001c1f2  jz      loc_18001C2C4
0x18001c1f8  mov     ecx, r12d
0x18001c1fb  test    r12d, r12d
0x18001c1fe  jz      short loc_18001C219
0x18001c200  sub     ecx, 1
0x18001c203  jz      short loc_18001C252
0x18001c205  sub     ecx, 1
0x18001c208  jz      short loc_18001C214
0x18001c20a  sub     ecx, 1
0x18001c20d  jz      short loc_18001C219
0x18001c20f  cmp     ecx, 2
0x18001c212  jnz     short loc_18001C227
0x18001c214  cmp     edx, 7
0x18001c217  jmp     short loc_18001C21C
0x18001c219  cmp     edx, 4
0x18001c21c  setz    al
0x18001c21f  test    al, al
0x18001c221  jnz     loc_18001C2C4
0x18001c227  mov     ecx, r12d
0x18001c22a  test    r12d, r12d
0x18001c22d  jz      short loc_18001C266
0x18001c22f  sub     ecx, 1
0x18001c232  jz      short loc_18001C252
0x18001c234  sub     ecx, 1
0x18001c237  jz      short loc_18001C261
0x18001c239  sub     ecx, 1
0x18001c23c  jz      short loc_18001C25C
0x18001c23e  cmp     ecx, 2
0x18001c241  jnz     short loc_18001C252
0x18001c243  lea     eax, [rdx-2]
0x18001c246  test    eax, 0FFFFFFF9h
0x18001c24b  jnz     short loc_18001C252
0x18001c24d  cmp     edx, 8
0x18001c250  jnz     short loc_18001C270
0x18001c252  mov     ebx, 80004005h
0x18001c257  jmp     loc_18001C2DC
0x18001c25c  cmp     edx, 5
0x18001c25f  jmp     short loc_18001C269
0x18001c261  cmp     edx, 6
0x18001c264  jmp     short loc_18001C269
0x18001c266  cmp     edx, 2
0x18001c269  setnz   al
0x18001c26c  test    al, al
0x18001c26e  jnz     short loc_18001C252
0x18001c270  cmp     edi, 3Ch ; '<'
0x18001c273  jge     short loc_18001C252
0x18001c275  inc     edi
0x18001c277  mov     ecx, 1F4h; unsigned int
0x18001c27c  call    ?ClrSleepEx@@YAKKH@Z; ClrSleepEx(ulong,int)
0x18001c281  mov     rcx, r13; Buffer
0x18001c284  call    ?GetCLRServiceStatus@NGENService@@YAJPEAU_COR_SERVICE_STATUS@@@Z; NGENService::GetCLRServiceStatus(_COR_SERVICE_STATUS *)
0x18001c289  test    eax, eax
0x18001c28b  js      short loc_18001C2C8
0x18001c28d  lea     rbx, ??_7VersionedMutexHolder@@6B@; const VersionedMutexHolder::`vftable'
0x18001c294  jmp     loc_18001C181
0x18001c299  jmp     short loc_18001C2A8
0x18001c29b  lea     rcx, aDoneworkFailed_0; "DoneWork(): Failed to acquire service l"...
0x18001c2a2  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x18001c2a7  nop
0x18001c2a8  mov     [rsp+120h+var_100], r14
0x18001c2ad  mov     rcx, [rsp+120h+hObject]; hObject
0x18001c2b2  cmp     rcx, rsi
0x18001c2b5  jz      short loc_18001C2DC
0x18001c2b7  call    cs:__imp_CloseHandle
0x18001c2bd  mov     [rsp+120h+hObject], rsi
0x18001c2c2  jmp     short loc_18001C2DC
0x18001c2c4  xor     ebx, ebx
0x18001c2c6  jmp     short loc_18001C2DC
0x18001c2c8  call    cs:__imp_GetLastError
0x18001c2ce  movzx   ebx, ax
0x18001c2d1  or      ebx, 80070000h
0x18001c2d7  test    eax, eax
0x18001c2d9  cmovle  ebx, eax
0x18001c2dc  test    r15, r15
0x18001c2df  jz      short loc_18001C2E9
0x18001c2e1  mov     rcx, r15; struct SC_HANDLE__ *
0x18001c2e4  call    ?CLRCloseServiceHandle@@YAHPEAUSC_HANDLE__@@@Z; CLRCloseServiceHandle(SC_HANDLE__ *)
0x18001c2e9  mov     eax, ebx
0x18001c2eb  mov     rcx, [rbp+57h+var_30]
0x18001c2ef  xor     rcx, rsp; StackCookie
0x18001c2f2  call    __security_check_cookie
0x18001c2f7  lea     r11, [rsp+120h+var_20]
0x18001c2ff  mov     rbx, [r11+30h]
0x18001c303  mov     rsi, [r11+40h]
0x18001c307  mov     rdi, [r11+48h]
0x18001c30b  mov     rsp, r11
0x18001c30e  pop     r15
0x18001c310  pop     r14
0x18001c312  pop     r13
0x18001c314  pop     r12
0x18001c316  pop     rbp
0x18001c317  retn
```
