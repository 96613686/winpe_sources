# SetSddlOnPerfmonResources(ITmInstance *)

- ea: `0x180073c54`
- end: `0x180073e60`
- name: `?SetSddlOnPerfmonResources@@YAJPEAUITmInstance@@@Z`
- size: `524`
- prototype: `__int64 __fastcall(struct ITmInstance *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180074200`

## callees

- `0x180003cf0`
- `0x18001ce20`
- `0x180073c54`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073e02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073e0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073e16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073e20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073e02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073e0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073e16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180073e20`

## string_xrefs

- `0x180073c85`: `com\complus\dtc\shared\util\msdtcsecurity.cpp`

## pseudocode

```c
__int64 __fastcall SetSddlOnPerfmonResources(struct ITmInstance *a1)
{
  int v2; // ebx
  const wchar_t *v3; // rax
  __int64 v4; // r9
  int v5; // eax
  int v6; // eax
  __int64 v8; // [rsp+28h] [rbp-20h]
  LPVOID pv; // [rsp+80h] [rbp+38h] BYREF
  LPWSTR pObjectName; // [rsp+88h] [rbp+40h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+90h] [rbp+48h] BYREF
  LPCWSTR v12; // [rsp+98h] [rbp+50h] BYREF

  pv = 0;
  pObjectName = 0;
  StringSecurityDescriptor = 0;
  v12 = 0;
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
    879,
    L"SetSddlOnPerfmonResources",
    0,
    L"In");
  v2 = (*(__int64 (__fastcall **)(struct ITmInstance *, LPVOID *, LPCWSTR *))(*(_QWORD *)a1 + 432LL))(
         a1,
         &pv,
         &StringSecurityDescriptor);
  if ( v2 < 0 )
  {
    v3 = L"Error from pTmInstance->PerfCounterFileMappingName";
    v4 = 884;
LABEL_13:
    LODWORD(v8) = v2;
    TraceStringInline(
      7,
      1,
      L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
      v4,
      L"SetSddlOnPerfmonResources",
      v8,
      v3);
    goto LABEL_14;
  }
  v2 = (*(__int64 (__fastcall **)(struct ITmInstance *, LPWSTR *, LPCWSTR *))(*(_QWORD *)a1 + 440LL))(
         a1,
         &pObjectName,
         &v12);
  if ( v2 < 0 )
  {
    v3 = L"Error from pTmInstance->PerfCounterMutexName";
    v4 = 891;
    goto LABEL_13;
  }
  v5 = SetObjectSddl((LPWSTR)pv, SE_KERNEL_OBJECT, StringSecurityDescriptor);
  v2 = v5;
  if ( v5 < 0 )
  {
    if ( v5 != -2147024894 )
    {
      v3 = L"SetObjectSddl(wszMappedFileName) failed";
      v4 = 905;
      goto LABEL_13;
    }
    LODWORD(v8) = -2147024894;
    TraceStringInline(
      7,
      4,
      L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
      900,
      L"SetSddlOnPerfmonResources",
      v8,
      L"SetObjectSddl(wszMappedFileName) failed, deliberately ignoring failure");
  }
  v6 = SetObjectSddl(pObjectName, SE_KERNEL_OBJECT, v12);
  v2 = v6;
  if ( v6 < 0 )
  {
    if ( v6 != -2147024894 )
    {
      v3 = L"SetObjectSddl(wszMutexName) failed";
      v4 = 919;
      goto LABEL_13;
    }
    LODWORD(v8) = -2147024894;
    TraceStringInline(
      7,
      4,
      L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
      914,
      L"SetSddlOnPerfmonResources",
      v8,
      L"SetObjectSddl(wszMutexName) failed, deliberately ignoring failure");
    v2 = 0;
  }
LABEL_14:
  CoTaskMemFree(pv);
  CoTaskMemFree(pObjectName);
  CoTaskMemFree((LPVOID)StringSecurityDescriptor);
  CoTaskMemFree((LPVOID)v12);
  LODWORD(v8) = v2;
  TraceStringInline(
    7,
    6,
    L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
    930,
    L"SetSddlOnPerfmonResources",
    v8,
    L"Out");
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180073c54  push    rbp
0x180073c56  push    rbx
0x180073c57  push    rsi
0x180073c58  push    rdi
0x180073c59  push    r14
0x180073c5b  push    r15
0x180073c5d  mov     rbp, rsp
0x180073c60  sub     rsp, 48h
0x180073c64  mov     edx, 6
0x180073c69  mov     [rbp+pv], 0
0x180073c71  lea     rax, aIn_0; "In"
0x180073c78  mov     [rbp+pObjectName], 0
0x180073c80  mov     [rsp+48h+var_18], rax
0x180073c85  lea     rsi, aComComplusDtcS_12; "com\\complus\\dtc\\shared\\util\\msdtcs"...
0x180073c8c  mov     rdi, rcx
0x180073c8f  mov     [rsp+48h+var_20], 0
0x180073c98  lea     r14d, [rdx+1]
0x180073c9c  mov     [rbp+StringSecurityDescriptor], 0
0x180073ca4  lea     r15, aSetsddlonperfm; "SetSddlOnPerfmonResources"
0x180073cab  mov     [rbp+arg_18], 0
0x180073cb3  mov     ecx, r14d
0x180073cb6  mov     [rsp+48h+var_28], r15
0x180073cbb  mov     r9d, 36Fh
0x180073cc1  mov     r8, rsi
0x180073cc4  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180073cc9  mov     rax, [rdi]
0x180073ccc  lea     r8, [rbp+StringSecurityDescriptor]
0x180073cd0  lea     rdx, [rbp+pv]
0x180073cd4  mov     rcx, rdi
0x180073cd7  mov     rax, [rax+1B0h]
0x180073cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073ce3  mov     ebx, eax
0x180073ce5  test    eax, eax
0x180073ce7  jns     short loc_180073CFB
0x180073ce9  lea     rax, aErrorFromPtmin; "Error from pTmInstance->PerfCounterFile"...
0x180073cf0  mov     r9d, 374h
0x180073cf6  jmp     loc_180073DE0
0x180073cfb  mov     rax, [rdi]
0x180073cfe  lea     r8, [rbp+arg_18]
0x180073d02  lea     rdx, [rbp+pObjectName]
0x180073d06  mov     rcx, rdi
0x180073d09  mov     rax, [rax+1B8h]
0x180073d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d15  mov     ebx, eax
0x180073d17  test    eax, eax
0x180073d19  jns     short loc_180073D2D
0x180073d1b  lea     rax, aErrorFromPtmin_0; "Error from pTmInstance->PerfCounterMute"...
0x180073d22  mov     r9d, 37Bh
0x180073d28  jmp     loc_180073DE0
0x180073d2d  mov     r8, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x180073d31  mov     edx, 6; ObjectType
0x180073d36  mov     rcx, [rbp+pv]; pObjectName
0x180073d3a  call    ?SetObjectSddl@@YAJPEBGW4_SE_OBJECT_TYPE@@0@Z; SetObjectSddl(ushort const *,_SE_OBJECT_TYPE,ushort const *)
0x180073d3f  mov     ebx, eax
0x180073d41  mov     edi, 80070002h
0x180073d46  test    eax, eax
0x180073d48  jns     short loc_180073D79
0x180073d4a  mov     r8, rsi
0x180073d4d  mov     ecx, r14d
0x180073d50  cmp     eax, edi
0x180073d52  jnz     short loc_180073DC4
0x180073d54  lea     rax, aSetobjectsddlW; "SetObjectSddl(wszMappedFileName) failed"...
0x180073d5b  mov     r9d, 384h
0x180073d61  mov     [rsp+48h+var_18], rax
0x180073d66  mov     edx, 4
0x180073d6b  mov     dword ptr [rsp+48h+var_20], edi
0x180073d6f  mov     [rsp+48h+var_28], r15
0x180073d74  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180073d79  mov     r8, [rbp+arg_18]; StringSecurityDescriptor
0x180073d7d  mov     edx, 6; ObjectType
0x180073d82  mov     rcx, [rbp+pObjectName]; pObjectName
0x180073d86  call    ?SetObjectSddl@@YAJPEBGW4_SE_OBJECT_TYPE@@0@Z; SetObjectSddl(ushort const *,_SE_OBJECT_TYPE,ushort const *)
0x180073d8b  mov     ebx, eax
0x180073d8d  test    eax, eax
0x180073d8f  jns     short loc_180073DFE
0x180073d91  cmp     eax, edi
0x180073d93  jnz     short loc_180073DD3
0x180073d95  lea     rax, aSetobjectsddlW_1; "SetObjectSddl(wszMutexName) failed, del"...
0x180073d9c  mov     r9d, 392h
0x180073da2  mov     [rsp+48h+var_18], rax
0x180073da7  mov     r8, rsi
0x180073daa  mov     dword ptr [rsp+48h+var_20], edi
0x180073dae  mov     edx, 4
0x180073db3  mov     ecx, r14d
0x180073db6  mov     [rsp+48h+var_28], r15
0x180073dbb  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180073dc0  xor     ebx, ebx
0x180073dc2  jmp     short loc_180073DFE
0x180073dc4  lea     rax, aSetobjectsddlW_3; "SetObjectSddl(wszMappedFileName) failed"
0x180073dcb  mov     r9d, 389h
0x180073dd1  jmp     short loc_180073DE6
0x180073dd3  lea     rax, aSetobjectsddlW_0; "SetObjectSddl(wszMutexName) failed"
0x180073dda  mov     r9d, 397h
0x180073de0  mov     r8, rsi
0x180073de3  mov     ecx, r14d
0x180073de6  mov     [rsp+48h+var_18], rax
0x180073deb  mov     edx, 1
0x180073df0  mov     dword ptr [rsp+48h+var_20], ebx
0x180073df4  mov     [rsp+48h+var_28], r15
0x180073df9  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180073dfe  mov     rcx, [rbp+pv]; pv
0x180073e02  call    cs:__imp_CoTaskMemFree
0x180073e08  mov     rcx, [rbp+pObjectName]; pv
0x180073e0c  call    cs:__imp_CoTaskMemFree
0x180073e12  mov     rcx, [rbp+StringSecurityDescriptor]; pv
0x180073e16  call    cs:__imp_CoTaskMemFree
0x180073e1c  mov     rcx, [rbp+arg_18]; pv
0x180073e20  call    cs:__imp_CoTaskMemFree
0x180073e26  lea     rax, aOut; "Out"
0x180073e2d  mov     r9d, 3A2h
0x180073e33  mov     [rsp+48h+var_18], rax
0x180073e38  mov     r8, rsi
0x180073e3b  mov     dword ptr [rsp+48h+var_20], ebx
0x180073e3f  mov     edx, 6
0x180073e44  mov     ecx, r14d
0x180073e47  mov     [rsp+48h+var_28], r15
0x180073e4c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180073e51  mov     eax, ebx
0x180073e53  add     rsp, 48h
0x180073e57  pop     r15
0x180073e59  pop     r14
0x180073e5b  pop     rdi
0x180073e5c  pop     rsi
0x180073e5d  pop     rbx
0x180073e5e  pop     rbp
0x180073e5f  retn
```
