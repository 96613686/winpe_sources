# GetUserSidFromSidString(ushort const *,void * *)

- ea: `0x180053324`
- end: `0x1800533fb`
- name: `?GetUserSidFromSidString@@YAJPEBGPEAPEAX@Z`
- size: `215`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800522f8`

## callees

- `0x18003ea2c`
- `0x180053324`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180053370`
- `ntdll!RtlCopySid` at `0x180053370`
- `ntdll!RtlLengthSid` at `0x18005334e`
- `ntdll!RtlLengthSid` at `0x18005334e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800533c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800533c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800533bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800533bb`
- `SPOOLSS!DllFreeSplMem` at `0x1800533a2`
- `SPOOLSS!DllFreeSplMem` at `0x1800533a2`
- `SPOOLSS!DllAllocSplMem` at `0x180053358`
- `SPOOLSS!DllAllocSplMem` at `0x180053358`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18005333f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18005333f`

## string_xrefs

- `0x18005338c`: `RtlCopySid failed with hr: 0x%x`
- `0x180053393`: `GetUserSidFromSidString`
- `0x1800533e2`: `GetUserSidFromSidString`
- `0x1800533db`: `ConvertStringSidToSid failed with hr: 0x%x`

## pseudocode

```c
__int64 __fastcall GetUserSidFromSidString(const unsigned __int16 *a1, void **a2)
{
  ULONG v3; // ebx
  void *v4; // rax
  NTSTATUS v5; // eax
  unsigned int v6; // ebx
  signed int LastError; // eax
  PSID Sid; // [rsp+40h] [rbp+18h] BYREF

  Sid = 0;
  if ( ConvertStringSidToSidW(a1, &Sid) )
  {
    v3 = RtlLengthSid(Sid);
    v4 = (void *)DllAllocSplMem(v3);
    *a2 = v4;
    if ( v4 )
    {
      v5 = RtlCopySid(v3, v4, Sid);
      v6 = v5;
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      if ( (v6 & 0x80000000) != 0 )
      {
        LocalSpoolerTelemetry::WriteDbgTraceError("GetUserSidFromSidString", L"RtlCopySid failed with hr: 0x%x", v6);
        DllFreeSplMem(*a2);
        *a2 = 0;
      }
    }
    else
    {
      v6 = -2147024882;
    }
    LocalFree(Sid);
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "GetUserSidFromSidString",
      L"ConvertStringSidToSid failed with hr: 0x%x",
      v6);
  }
  return v6;
}

```

## disassembly

```asm
0x180053324  mov     [rsp+arg_0], rbx
0x180053329  push    rdi
0x18005332a  sub     rsp, 20h
0x18005332e  mov     rdi, rdx
0x180053331  mov     [rsp+28h+Sid], 0
0x18005333a  lea     rdx, [rsp+28h+Sid]; Sid
0x18005333f  call    cs:__imp_ConvertStringSidToSidW
0x180053345  test    eax, eax
0x180053347  jz      short loc_1800533C3
0x180053349  mov     rcx, [rsp+28h+Sid]; Sid
0x18005334e  call    cs:__imp_RtlLengthSid
0x180053354  mov     ecx, eax
0x180053356  mov     ebx, eax
0x180053358  call    cs:__imp_DllAllocSplMem
0x18005335e  mov     [rdi], rax
0x180053361  test    rax, rax
0x180053364  jz      short loc_1800533B1
0x180053366  mov     r8, [rsp+28h+Sid]; SourceSid
0x18005336b  mov     rdx, rax; DestinationSid
0x18005336e  mov     ecx, ebx; DestinationSidLength
0x180053370  call    cs:__imp_RtlCopySid
0x180053376  mov     ebx, eax
0x180053378  test    eax, eax
0x18005337a  jle     short loc_180053385
0x18005337c  movzx   ebx, ax
0x18005337f  or      ebx, 80070000h
0x180053385  test    ebx, ebx
0x180053387  jns     short loc_1800533B6
0x180053389  mov     r8d, ebx
0x18005338c  lea     rdx, aRtlcopysidFail_0; "RtlCopySid failed with hr: 0x%x"
0x180053393  lea     rcx, aGetusersidfrom; "GetUserSidFromSidString"
0x18005339a  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18005339f  mov     rcx, [rdi]
0x1800533a2  call    cs:__imp_DllFreeSplMem
0x1800533a8  mov     qword ptr [rdi], 0
0x1800533af  jmp     short loc_1800533B6
0x1800533b1  mov     ebx, 8007000Eh
0x1800533b6  mov     rcx, [rsp+28h+Sid]; hMem
0x1800533bb  call    cs:__imp_LocalFree
0x1800533c1  jmp     short loc_1800533EE
0x1800533c3  call    cs:__imp_GetLastError
0x1800533c9  mov     ebx, eax
0x1800533cb  test    eax, eax
0x1800533cd  jle     short loc_1800533D8
0x1800533cf  movzx   ebx, ax
0x1800533d2  or      ebx, 80070000h
0x1800533d8  mov     r8d, ebx
0x1800533db  lea     rdx, aConvertstrings_2; "ConvertStringSidToSid failed with hr: 0"...
0x1800533e2  lea     rcx, aGetusersidfrom; "GetUserSidFromSidString"
0x1800533e9  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800533ee  mov     eax, ebx
0x1800533f0  mov     rbx, [rsp+28h+arg_0]
0x1800533f5  add     rsp, 20h
0x1800533f9  pop     rdi
0x1800533fa  retn
```
