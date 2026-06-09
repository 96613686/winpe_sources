# GenerateSDFromSDDL(IMsiString const &,IMsiStream * &)

- ea: `0x1800d8584`
- end: `0x1800d8738`
- name: `?GenerateSDFromSDDL@@YA_NAEBVIMsiString@@AEAPEAVIMsiStream@@@Z`
- size: `436`
- prototype: `bool(const struct IMsiString *, struct IMsiStream **)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800d79e0`
- `0x180172b40`
- `0x1801e7568`
- `0x1801ff400`
- `0x180200180`

## callees

- `0x18000c4bc`
- `0x180018d44`
- `0x1800d8584`
- `0x1800d8aa4`
- `0x1802651d2`
- `0x180266010`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800d8602`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800d8602`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1800d861a`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x1800d861a`
- `KERNEL32!GetProcessHeap` at `0x1800d86c6`
- `KERNEL32!GetProcessHeap` at `0x1800d86c6`
- `KERNEL32!HeapFree` at `0x1800d86db`
- `KERNEL32!HeapFree` at `0x1800d86db`
- `KERNEL32!GetLastError` at `0x1800d865d`
- `KERNEL32!GetLastError` at `0x1800d865d`
- `KERNEL32!LocalFree` at `0x1800d86f0`
- `KERNEL32!LocalFree` at `0x1800d86f0`

## pseudocode

```c
char __fastcall GenerateSDFromSDDL(const struct IMsiString *a1, struct IMsiStream **a2)
{
  char v4; // bl
  char *MemoryStream; // rsi
  const unsigned __int16 *v6; // rbx
  DWORD LastError; // eax
  HANDLE ProcessHeap; // rax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-10h] BYREF
  void *v11; // [rsp+68h] [rbp-8h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+A0h] [rbp+30h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+A8h] [rbp+38h] BYREF

  StringSecurityDescriptor = 0;
  v11 = &MsiString::s_NullString;
  (*(void (__fastcall **)(void *, _QWORD, void **))(MsiString::s_NullString + 120LL))(&MsiString::s_NullString, 0, &v11);
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  v4 = 0;
  if ( ResolveSDDL(a1, (unsigned __int16 **)&StringSecurityDescriptor)
    && ConvertStringSecurityDescriptorToSecurityDescriptorW(
         StringSecurityDescriptor,
         1u,
         &SecurityDescriptor,
         &SecurityDescriptorSize)
    && IsValidSecurityDescriptor(SecurityDescriptor) )
  {
    v4 = 1;
    MemoryStream = AllocateMemoryStream(SecurityDescriptorSize, a2);
    if ( !MemoryStream )
    {
      if ( g_dmDiagnosticMode )
      {
        v6 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)a1 + 80LL))(a1);
        LastError = GetLastError();
        DebugString(
          9,
          0,
          0,
          L"Error: %d. Failed to allocate memory while trying to resolve SDDLText string %s",
          (const unsigned __int16 *)LastError,
          v6,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      v4 = 0;
    }
    memcpy_0(MemoryStream, SecurityDescriptor, SecurityDescriptorSize);
  }
  if ( StringSecurityDescriptor )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)StringSecurityDescriptor);
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  return v4;
}

```

## disassembly

```asm
0x1800d8584  mov     [rsp-18h+arg_0], rbx
0x1800d8589  mov     [rsp-18h+arg_8], rsi
0x1800d858e  push    rbp
0x1800d858f  push    r12
0x1800d8591  push    r14
0x1800d8593  mov     rbp, rsp
0x1800d8596  sub     rsp, 70h
0x1800d859a  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800d85a1  lea     r12, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800d85a8  mov     rsi, rdx
0x1800d85ab  mov     [rbp+StringSecurityDescriptor], 0
0x1800d85b3  mov     r14, rcx
0x1800d85b6  mov     [rbp+var_8], r12
0x1800d85ba  lea     r8, [rbp+var_8]
0x1800d85be  xor     edx, edx
0x1800d85c0  mov     rax, [rax+78h]
0x1800d85c4  mov     rcx, r12
0x1800d85c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d85cc  lea     rdx, [rbp+StringSecurityDescriptor]; unsigned __int16 **
0x1800d85d0  mov     [rbp+SecurityDescriptor], 0
0x1800d85d8  mov     rcx, r14; struct IMsiString *
0x1800d85db  mov     [rbp+SecurityDescriptorSize], 0
0x1800d85e2  xor     bl, bl
0x1800d85e4  call    ?ResolveSDDL@@YA_NAEBVIMsiString@@PEAPEAG@Z; ResolveSDDL(IMsiString const &,ushort * *)
0x1800d85e9  test    al, al
0x1800d85eb  jz      loc_1800D86BF
0x1800d85f1  mov     rcx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800d85f5  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800d85f9  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800d85fd  mov     edx, 1; StringSDRevision
0x1800d8602  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800d8609  nop     dword ptr [rax+rax+00h]
0x1800d860e  test    eax, eax
0x1800d8610  jz      loc_1800D86BF
0x1800d8616  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x1800d861a  call    cs:__imp_IsValidSecurityDescriptor
0x1800d8621  nop     dword ptr [rax+rax+00h]
0x1800d8626  test    eax, eax
0x1800d8628  jz      loc_1800D86BF
0x1800d862e  mov     ecx, [rbp+SecurityDescriptorSize]; unsigned int
0x1800d8631  mov     rdx, rsi; struct IMsiStream **
0x1800d8634  mov     bl, 1
0x1800d8636  call    ?AllocateMemoryStream@@YAPEADIAEAPEAVIMsiStream@@@Z; AllocateMemoryStream(uint,IMsiStream * &)
0x1800d863b  mov     rsi, rax
0x1800d863e  test    rax, rax
0x1800d8641  jnz     short loc_1800D86AF
0x1800d8643  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x1800d8649  jz      short loc_1800D86AD
0x1800d864b  mov     rcx, [r14]
0x1800d864e  mov     rax, [rcx+50h]
0x1800d8652  mov     rcx, r14
0x1800d8655  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d865a  mov     rbx, rax
0x1800d865d  call    cs:__imp_GetLastError
0x1800d8664  nop     dword ptr [rax+rax+00h]
0x1800d8669  mov     ecx, eax
0x1800d866b  xor     edx, edx; unsigned __int16
0x1800d866d  mov     [rsp+70h+var_18], rdx; void *
0x1800d8672  lea     r9, aErrorDFailedTo; "Error: %d. Failed to allocate memory wh"...
0x1800d8679  mov     [rsp+70h+var_20], edx; unsigned int
0x1800d867d  lea     rax, aNull; "(NULL)"
0x1800d8684  mov     [rsp+70h+var_28], rax; unsigned __int16 *
0x1800d8689  xor     r8d, r8d; int
0x1800d868c  mov     [rsp+70h+var_30], rax; unsigned __int16 *
0x1800d8691  mov     [rsp+70h+var_38], rax; unsigned __int16 *
0x1800d8696  mov     [rsp+70h+var_40], rax; unsigned __int16 *
0x1800d869b  mov     [rsp+70h+var_48], rbx; unsigned __int16 *
0x1800d86a0  mov     [rsp+70h+var_50], rcx; unsigned __int16 *
0x1800d86a5  lea     ecx, [rsi+9]; int
0x1800d86a8  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800d86ad  xor     bl, bl
0x1800d86af  mov     r8d, [rbp+SecurityDescriptorSize]; Size
0x1800d86b3  mov     rcx, rsi; void *
0x1800d86b6  mov     rdx, [rbp+SecurityDescriptor]; Src
0x1800d86ba  call    memcpy_0
0x1800d86bf  cmp     [rbp+StringSecurityDescriptor], 0
0x1800d86c4  jz      short loc_1800D86E7
0x1800d86c6  call    cs:__imp_GetProcessHeap
0x1800d86cd  nop     dword ptr [rax+rax+00h]
0x1800d86d2  mov     r8, [rbp+StringSecurityDescriptor]; lpMem
0x1800d86d6  xor     edx, edx; dwFlags
0x1800d86d8  mov     rcx, rax; hHeap
0x1800d86db  call    cs:__imp_HeapFree
0x1800d86e2  nop     dword ptr [rax+rax+00h]
0x1800d86e7  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800d86eb  test    rcx, rcx
0x1800d86ee  jz      short loc_1800D86FC
0x1800d86f0  call    cs:__imp_LocalFree
0x1800d86f7  nop     dword ptr [rax+rax+00h]
0x1800d86fc  mov     rcx, [rbp+var_8]
0x1800d8700  mov     rdx, [rcx]
0x1800d8703  mov     rax, [rdx+10h]
0x1800d8707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d870c  mov     rdx, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800d8713  mov     rcx, r12
0x1800d8716  mov     rax, [rdx+10h]
0x1800d871a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d871f  lea     r11, [rsp+70h+var_s0]
0x1800d8724  mov     al, bl
0x1800d8726  mov     rbx, [r11+20h]
0x1800d872a  mov     rsi, [r11+28h]
0x1800d872e  mov     rsp, r11
0x1800d8731  pop     r14
0x1800d8733  pop     r12
0x1800d8735  pop     rbp
0x1800d8736  retn
```
