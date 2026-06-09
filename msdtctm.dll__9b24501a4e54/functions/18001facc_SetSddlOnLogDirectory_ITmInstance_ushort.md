# SetSddlOnLogDirectory(ITmInstance *,ushort *)

- ea: `0x18001facc`
- end: `0x18001fd19`
- name: `?SetSddlOnLogDirectory@@YAJPEAUITmInstance@@PEAG@Z`
- size: `589`
- prototype: `__int64 __fastcall(struct ITmInstance *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180085ae8`

## callees

- `0x1800063b0`
- `0x180016f3c`
- `0x18001d268`
- `0x18001facc`
- `0x180023d98`
- `0x1800b83ee`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fcbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001fcbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc09`
- `msvcrt!_wcsnicmp` at `0x18001fc42`
- `msvcrt!_wcsnicmp` at `0x18001fc42`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001fbff`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001fbff`

## string_xrefs

- `0x18001fbd7`: `GetDtcLogPath failed`
- `0x18001fc1e`: `GetFullPathNameW(wszLogPath) failed`
- `0x18001fb58`: `com\complus\dtc\shared\util\msdtcsecurity.cpp`
- `0x18001fb5f`: `SetSddlOnLogDirectory`
- `0x18001fba6`: `StringCchCopyW failed`
- `0x18001fc6b`: `TmInstance->GetNonDefaultLogPathSddl failed`
- `0x18001fc8f`: `SetObjectSddl(wszLogPath) failed`

## pseudocode

```c
__int64 __fastcall SetSddlOnLogDirectory(struct ITmInstance *a1, unsigned __int16 *a2)
{
  signed int v4; // ebx
  const wchar_t *v5; // rax
  __int64 v6; // r9
  signed int LastError; // eax
  const wchar_t *DefaultLogPath; // rax
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR FilePart; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR FileName; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v13[526]; // [rsp+52h] [rbp-AEh] BYREF
  WCHAR Buffer; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v15[526]; // [rsp+262h] [rbp+162h] BYREF

  FileName = 0;
  memset_0(v13, 0, 0x208u);
  Buffer = 0;
  memset_0(v15, 0, 0x208u);
  FilePart = 0;
  pv = 0;
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
    286,
    L"SetSddlOnLogDirectory",
    0,
    L"In");
  if ( a2 )
  {
    v4 = StringCchCopyW(&FileName, 0x105u, a2);
    if ( v4 < 0 )
    {
      v5 = L"StringCchCopyW failed";
      v6 = 292;
LABEL_15:
      TraceStringInline(
        7,
        1,
        L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
        v6,
        L"SetSddlOnLogDirectory",
        v4,
        v5);
      goto LABEL_16;
    }
  }
  else
  {
    v4 = (*(__int64 (__fastcall **)(struct ITmInstance *, __int64, WCHAR *))(*(_QWORD *)a1 + 96LL))(a1, 261, &FileName);
    if ( v4 < 0 )
    {
      v5 = (const wchar_t *)L"GetDtcLogPath failed";
      v6 = 302;
      goto LABEL_15;
    }
  }
  if ( !GetFullPathNameW(&FileName, 0x105u, &Buffer, &FilePart) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = L"GetFullPathNameW(wszLogPath) failed";
    v6 = 309;
    goto LABEL_15;
  }
  DefaultLogPath = GetDefaultLogPath();
  if ( _wcsnicmp(&Buffer, DefaultLogPath, 0x105u) )
  {
    v4 = (*(__int64 (__fastcall **)(struct ITmInstance *, LPVOID *))(*(_QWORD *)a1 + 80LL))(a1, &pv);
    if ( v4 < 0 )
    {
      v5 = L"TmInstance->GetNonDefaultLogPathSddl failed";
      v6 = 318;
      goto LABEL_15;
    }
    v4 = SetObjectSddl(&FileName, SE_FILE_OBJECT, (LPCWSTR)pv);
    if ( v4 < 0 )
    {
      v5 = L"SetObjectSddl(wszLogPath) failed";
      v6 = 325;
      goto LABEL_15;
    }
  }
LABEL_16:
  CoTaskMemFree(pv);
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
    331,
    L"SetSddlOnLogDirectory",
    v4,
    L"Out");
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001facc  mov     [rsp-8+arg_10], rbx
0x18001fad1  push    rbp
0x18001fad2  push    rsi
0x18001fad3  push    r12
0x18001fad5  push    r13
0x18001fad7  push    r15
0x18001fad9  lea     rbp, [rsp-380h]
0x18001fae1  sub     rsp, 480h
0x18001fae8  mov     rax, cs:__security_cookie
0x18001faef  xor     rax, rsp
0x18001faf2  mov     [rbp+3A0h+var_30], rax
0x18001faf9  mov     rbx, rdx
0x18001fafc  mov     rsi, rcx
0x18001faff  xor     eax, eax
0x18001fb01  lea     rcx, [rsp+4A0h+var_44E]; void *
0x18001fb06  xor     edx, edx; Val
0x18001fb08  mov     [rsp+4A0h+FileName], ax
0x18001fb0d  mov     r8d, 208h; Size
0x18001fb13  call    memset_0
0x18001fb18  xor     eax, eax
0x18001fb1a  lea     rcx, [rbp+3A0h+var_23E]; void *
0x18001fb21  xor     edx, edx; Val
0x18001fb23  mov     [rbp+3A0h+Buffer], ax
0x18001fb2a  mov     r8d, 208h; Size
0x18001fb30  call    memset_0
0x18001fb35  mov     edx, 6
0x18001fb3a  mov     [rsp+4A0h+FilePart], 0
0x18001fb43  lea     rax, aIn_0; "In"
0x18001fb4a  mov     [rsp+4A0h+pv], 0
0x18001fb53  mov     [rsp+4A0h+var_470], rax
0x18001fb58  lea     r15, aComComplusDtcS_8; "com\\complus\\dtc\\shared\\util\\msdtcs"...
0x18001fb5f  lea     r13, aSetsddlonlogdi; "SetSddlOnLogDirectory"
0x18001fb66  mov     [rsp+4A0h+var_478], 0
0x18001fb6f  lea     r12d, [rdx+1]
0x18001fb73  mov     [rsp+4A0h+var_480], r13
0x18001fb78  mov     ecx, r12d
0x18001fb7b  mov     r9d, 11Eh
0x18001fb81  mov     r8, r15
0x18001fb84  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001fb89  test    rbx, rbx
0x18001fb8c  jz      short loc_18001FBB8
0x18001fb8e  mov     r8, rbx; unsigned __int16 *
0x18001fb91  lea     rcx, [rsp+4A0h+FileName]; unsigned __int16 *
0x18001fb96  mov     edx, 105h; unsigned __int64
0x18001fb9b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001fba0  mov     ebx, eax
0x18001fba2  test    eax, eax
0x18001fba4  jns     short loc_18001FBE9
0x18001fba6  lea     rax, aStringcchcopyw; "StringCchCopyW failed"
0x18001fbad  mov     r9d, 124h
0x18001fbb3  jmp     loc_18001FC9C
0x18001fbb8  mov     rax, [rsi]
0x18001fbbb  lea     r8, [rsp+4A0h+FileName]
0x18001fbc0  mov     edx, 105h
0x18001fbc5  mov     rcx, rsi
0x18001fbc8  mov     rax, [rax+60h]
0x18001fbcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbd1  mov     ebx, eax
0x18001fbd3  test    eax, eax
0x18001fbd5  jns     short loc_18001FBE9
0x18001fbd7  lea     rax, aGetdtclogpathF; "GetDtcLogPath failed"
0x18001fbde  mov     r9d, 12Eh
0x18001fbe4  jmp     loc_18001FC9C
0x18001fbe9  lea     r9, [rsp+4A0h+FilePart]; lpFilePart
0x18001fbee  mov     edx, 105h; nBufferLength
0x18001fbf3  lea     r8, [rbp+3A0h+Buffer]; lpBuffer
0x18001fbfa  lea     rcx, [rsp+4A0h+FileName]; lpFileName
0x18001fbff  call    cs:__imp_GetFullPathNameW
0x18001fc05  test    eax, eax
0x18001fc07  jnz     short loc_18001FC2D
0x18001fc09  call    cs:__imp_GetLastError
0x18001fc0f  mov     ebx, eax
0x18001fc11  test    eax, eax
0x18001fc13  jle     short loc_18001FC1E
0x18001fc15  movzx   ebx, ax
0x18001fc18  or      ebx, 80070000h
0x18001fc1e  lea     rax, aGetfullpathnam; "GetFullPathNameW(wszLogPath) failed"
0x18001fc25  mov     r9d, 135h
0x18001fc2b  jmp     short loc_18001FC9C
0x18001fc2d  call    ?GetDefaultLogPath@@YAPEAGXZ; GetDefaultLogPath(void)
0x18001fc32  mov     rdx, rax; String2
0x18001fc35  lea     rcx, [rbp+3A0h+Buffer]; String1
0x18001fc3c  mov     r8d, 105h; MaxCount
0x18001fc42  call    cs:__imp__wcsnicmp
0x18001fc48  test    eax, eax
0x18001fc4a  jz      short loc_18001FCBA
0x18001fc4c  mov     rax, [rsi]
0x18001fc4f  lea     rdx, [rsp+4A0h+pv]
0x18001fc54  mov     rcx, rsi
0x18001fc57  mov     rax, [rax+50h]
0x18001fc5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc60  mov     ebx, eax
0x18001fc62  mov     edx, 1; ObjectType
0x18001fc67  test    eax, eax
0x18001fc69  jns     short loc_18001FC7A
0x18001fc6b  lea     rax, aTminstanceGetn; "TmInstance->GetNonDefaultLogPathSddl fa"...
0x18001fc72  mov     r9d, 13Eh
0x18001fc78  jmp     short loc_18001FCA1
0x18001fc7a  mov     r8, [rsp+4A0h+pv]; StringSecurityDescriptor
0x18001fc7f  lea     rcx, [rsp+4A0h+FileName]; pObjectName
0x18001fc84  call    ?SetObjectSddl@@YAJPEBGW4_SE_OBJECT_TYPE@@0@Z; SetObjectSddl(ushort const *,_SE_OBJECT_TYPE,ushort const *)
0x18001fc89  mov     ebx, eax
0x18001fc8b  test    eax, eax
0x18001fc8d  jns     short loc_18001FCBA
0x18001fc8f  lea     rax, aSetobjectsddlW_4; "SetObjectSddl(wszLogPath) failed"
0x18001fc96  mov     r9d, 145h
0x18001fc9c  mov     edx, 1
0x18001fca1  mov     [rsp+4A0h+var_470], rax
0x18001fca6  mov     r8, r15
0x18001fca9  mov     dword ptr [rsp+4A0h+var_478], ebx
0x18001fcad  mov     ecx, r12d
0x18001fcb0  mov     [rsp+4A0h+var_480], r13
0x18001fcb5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001fcba  mov     rcx, [rsp+4A0h+pv]; pv
0x18001fcbf  call    cs:__imp_CoTaskMemFree
0x18001fcc5  lea     rax, aOut; "Out"
0x18001fccc  mov     r9d, 14Bh
0x18001fcd2  mov     [rsp+4A0h+var_470], rax
0x18001fcd7  mov     r8, r15
0x18001fcda  mov     dword ptr [rsp+4A0h+var_478], ebx
0x18001fcde  mov     edx, 6
0x18001fce3  mov     ecx, r12d
0x18001fce6  mov     [rsp+4A0h+var_480], r13
0x18001fceb  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001fcf0  mov     eax, ebx
0x18001fcf2  mov     rcx, [rbp+3A0h+var_30]
0x18001fcf9  xor     rcx, rsp; StackCookie
0x18001fcfc  call    __security_check_cookie
0x18001fd01  mov     rbx, [rsp+4A0h+arg_10]
0x18001fd09  add     rsp, 480h
0x18001fd10  pop     r15
0x18001fd12  pop     r13
0x18001fd14  pop     r12
0x18001fd16  pop     rsi
0x18001fd17  pop     rbp
0x18001fd18  retn
```
