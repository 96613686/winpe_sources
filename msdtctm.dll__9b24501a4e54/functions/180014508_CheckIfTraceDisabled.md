# CheckIfTraceDisabled

- ea: `0x180014508`
- end: `0x18001460c`
- name: `CheckIfTraceDisabled`
- size: `260`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014198`
- `0x180014314`

## callees

- `0x1800063b0`
- `0x18000fb90`
- `0x180014508`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014540`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014540`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800145f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800145f9`

## string_xrefs

- `0x180014569`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x1800145c2`: `com\complus\dtc\dtc\trace\src\tracelib.cpp`
- `0x180014570`: `OpenTracingMiscKey`
- `0x18001455d`: `Failed to open the TRACE_REG_MISC_KEY key`

## pseudocode

```c
__int64 CheckIfTraceDisabled()
{
  unsigned int v0; // edi
  LSTATUS v1; // eax
  signed int v2; // ebx
  unsigned int v4; // [rsp+50h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+10h] BYREF

  v4 = -1;
  v0 = 0;
  hKey = 0;
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\MSDTC\\Misc",
         0,
         0x20119u,
         &hKey);
  v2 = v1;
  if ( !v1 )
    goto LABEL_5;
  if ( v1 > 0 )
    v2 = (unsigned __int16)v1 | 0x80070000;
  TraceStringInline(
    14,
    1,
    L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
    101,
    L"OpenTracingMiscKey",
    v2,
    L"Failed to open the TRACE_REG_MISC_KEY key");
  if ( v2 >= 0 )
  {
LABEL_5:
    RegQueryDword(hKey, L"DisableTracing", &v4, 0xFFFFFFFF);
    if ( v4 == 1 )
    {
      v0 = 1;
      TraceStringInline(
        14,
        3,
        L"com\\complus\\dtc\\dtc\\trace\\src\\tracelib.cpp",
        133,
        L"CheckIfTraceDisabled",
        0,
        L"The Tracing Feature has bee determined to have been disabled");
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180014508  mov     rax, rsp
0x18001450b  mov     [rax+18h], rbx
0x18001450f  push    rdi
0x180014510  sub     rsp, 40h
0x180014514  mov     dword ptr [rax+8], 0FFFFFFFFh
0x18001451b  lea     rax, [rax+10h]
0x18001451f  xor     edi, edi
0x180014521  mov     [rsp+48h+phkResult], rax; phkResult
0x180014526  mov     [rax], rdi
0x180014529  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180014530  mov     r9d, 20119h; samDesired
0x180014536  xor     r8d, r8d; ulOptions
0x180014539  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014540  call    cs:__imp_RegOpenKeyExW
0x180014546  mov     ebx, eax
0x180014548  test    eax, eax
0x18001454a  jz      short loc_180014590
0x18001454c  jle     short loc_180014557
0x18001454e  movzx   ebx, ax
0x180014551  or      ebx, 80070000h
0x180014557  mov     r9d, 65h ; 'e'
0x18001455d  lea     rax, aFailedToOpenTh_1; "Failed to open the TRACE_REG_MISC_KEY k"...
0x180014564  mov     [rsp+48h+var_18], rax
0x180014569  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x180014570  lea     rax, aOpentracingmis; "OpenTracingMiscKey"
0x180014577  mov     dword ptr [rsp+48h+var_20], ebx
0x18001457b  mov     [rsp+48h+phkResult], rax
0x180014580  lea     edx, [r9-64h]
0x180014584  lea     ecx, [rdx+0Dh]
0x180014587  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001458c  test    ebx, ebx
0x18001458e  js      short loc_1800145EF
0x180014590  mov     rcx, [rsp+48h+hKey]; HKEY
0x180014595  lea     r8, [rsp+48h+arg_0]; unsigned int *
0x18001459a  or      r9d, 0FFFFFFFFh; unsigned int
0x18001459e  lea     rdx, aDisabletracing; "DisableTracing"
0x1800145a5  call    ?RegQueryDword@@YAJPEAUHKEY__@@PEAGPEAKK@Z; RegQueryDword(HKEY__ *,ushort *,ulong *,ulong)
0x1800145aa  cmp     [rsp+48h+arg_0], 1
0x1800145af  jnz     short loc_1800145EF
0x1800145b1  mov     edi, 1
0x1800145b6  lea     rax, aTheTracingFeat; "The Tracing Feature has bee determined "...
0x1800145bd  mov     [rsp+48h+var_18], rax
0x1800145c2  lea     r8, aComComplusDtcD_22; "com\\complus\\dtc\\dtc\\trace\\src\\tra"...
0x1800145c9  lea     rax, aCheckiftracedi; "CheckIfTraceDisabled"
0x1800145d0  mov     [rsp+48h+var_20], 0
0x1800145d9  mov     r9d, 85h
0x1800145df  mov     [rsp+48h+phkResult], rax
0x1800145e4  lea     edx, [rdi+2]
0x1800145e7  lea     ecx, [rdi+0Dh]
0x1800145ea  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800145ef  mov     rcx, [rsp+48h+hKey]; hKey
0x1800145f4  test    rcx, rcx
0x1800145f7  jz      short loc_1800145FF
0x1800145f9  call    cs:__imp_RegCloseKey
0x1800145ff  mov     rbx, [rsp+48h+arg_10]
0x180014604  mov     eax, edi
0x180014606  add     rsp, 40h
0x18001460a  pop     rdi
0x18001460b  retn
```
