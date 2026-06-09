# GenerateSDFromSDDL(IMsiString const &,IMsiStream * &)

- ea: `0x1800861d4`
- end: `0x180086363`
- name: `?GenerateSDFromSDDL@@YA_NAEBVIMsiString@@AEAPEAVIMsiStream@@@Z`
- size: `399`
- prototype: `bool(const struct IMsiString *, struct IMsiStream **)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180086370`
- `0x18016ca80`
- `0x1801de630`
- `0x1801f62d0`
- `0x1801f7020`

## callees

- `0x180025a18`
- `0x180060580`
- `0x1800861d4`
- `0x180132d38`
- `0x18025ab12`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180086252`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180086252`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x180086264`
- `ADVAPI32!IsValidSecurityDescriptor` at `0x180086264`
- `KERNEL32!GetProcessHeap` at `0x180086304`
- `KERNEL32!GetProcessHeap` at `0x180086304`
- `KERNEL32!HeapFree` at `0x180086313`
- `KERNEL32!HeapFree` at `0x180086313`
- `KERNEL32!GetLastError` at `0x1800862a1`
- `KERNEL32!GetLastError` at `0x1800862a1`
- `KERNEL32!LocalFree` at `0x180086322`
- `KERNEL32!LocalFree` at `0x180086322`

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
0x1800861d4  mov     [rsp-18h+arg_0], rbx
0x1800861d9  mov     [rsp-18h+arg_8], rsi
0x1800861de  push    rbp
0x1800861df  push    r12
0x1800861e1  push    r14
0x1800861e3  mov     rbp, rsp
0x1800861e6  sub     rsp, 70h
0x1800861ea  mov     rax, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800861f1  lea     r12, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1800861f8  mov     rsi, rdx
0x1800861fb  mov     [rbp+StringSecurityDescriptor], 0
0x180086203  mov     r14, rcx
0x180086206  mov     [rbp+var_8], r12
0x18008620a  lea     r8, [rbp+var_8]
0x18008620e  xor     edx, edx
0x180086210  mov     rax, [rax+78h]
0x180086214  mov     rcx, r12
0x180086217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008621c  lea     rdx, [rbp+StringSecurityDescriptor]; unsigned __int16 **
0x180086220  mov     [rbp+SecurityDescriptor], 0
0x180086228  mov     rcx, r14; struct IMsiString *
0x18008622b  mov     [rbp+SecurityDescriptorSize], 0
0x180086232  xor     bl, bl
0x180086234  call    ?ResolveSDDL@@YA_NAEBVIMsiString@@PEAPEAG@Z; ResolveSDDL(IMsiString const &,ushort * *)
0x180086239  test    al, al
0x18008623b  jz      loc_1800862FD
0x180086241  mov     rcx, [rbp+StringSecurityDescriptor]; StringSecurityDescriptor
0x180086245  lea     r9, [rbp+SecurityDescriptorSize]; SecurityDescriptorSize
0x180086249  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18008624d  mov     edx, 1; StringSDRevision
0x180086252  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180086258  test    eax, eax
0x18008625a  jz      loc_1800862FD
0x180086260  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x180086264  call    cs:__imp_IsValidSecurityDescriptor
0x18008626a  test    eax, eax
0x18008626c  jz      loc_1800862FD
0x180086272  mov     ecx, [rbp+SecurityDescriptorSize]; unsigned int
0x180086275  mov     rdx, rsi; struct IMsiStream **
0x180086278  mov     bl, 1
0x18008627a  call    ?AllocateMemoryStream@@YAPEADIAEAPEAVIMsiStream@@@Z; AllocateMemoryStream(uint,IMsiStream * &)
0x18008627f  mov     rsi, rax
0x180086282  test    rax, rax
0x180086285  jnz     short loc_1800862ED
0x180086287  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18008628d  jz      short loc_1800862EB
0x18008628f  mov     rcx, [r14]
0x180086292  mov     rax, [rcx+50h]
0x180086296  mov     rcx, r14
0x180086299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008629e  mov     rbx, rax
0x1800862a1  call    cs:__imp_GetLastError
0x1800862a7  mov     ecx, eax
0x1800862a9  xor     edx, edx; unsigned __int16
0x1800862ab  mov     [rsp+70h+var_18], rdx; void *
0x1800862b0  lea     r9, aErrorDFailedTo; "Error: %d. Failed to allocate memory wh"...
0x1800862b7  mov     [rsp+70h+var_20], edx; unsigned int
0x1800862bb  lea     rax, aNull; "(NULL)"
0x1800862c2  mov     [rsp+70h+var_28], rax; unsigned __int16 *
0x1800862c7  xor     r8d, r8d; int
0x1800862ca  mov     [rsp+70h+var_30], rax; unsigned __int16 *
0x1800862cf  mov     [rsp+70h+var_38], rax; unsigned __int16 *
0x1800862d4  mov     [rsp+70h+var_40], rax; unsigned __int16 *
0x1800862d9  mov     [rsp+70h+var_48], rbx; unsigned __int16 *
0x1800862de  mov     [rsp+70h+var_50], rcx; unsigned __int16 *
0x1800862e3  lea     ecx, [rsi+9]; int
0x1800862e6  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800862eb  xor     bl, bl
0x1800862ed  mov     r8d, [rbp+SecurityDescriptorSize]; Size
0x1800862f1  mov     rcx, rsi; void *
0x1800862f4  mov     rdx, [rbp+SecurityDescriptor]; Src
0x1800862f8  call    memcpy_0
0x1800862fd  cmp     [rbp+StringSecurityDescriptor], 0
0x180086302  jz      short loc_180086319
0x180086304  call    cs:__imp_GetProcessHeap
0x18008630a  mov     r8, [rbp+StringSecurityDescriptor]; lpMem
0x18008630e  xor     edx, edx; dwFlags
0x180086310  mov     rcx, rax; hHeap
0x180086313  call    cs:__imp_HeapFree
0x180086319  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18008631d  test    rcx, rcx
0x180086320  jz      short loc_180086328
0x180086322  call    cs:__imp_LocalFree
0x180086328  mov     rcx, [rbp+var_8]
0x18008632c  mov     rdx, [rcx]
0x18008632f  mov     rax, [rdx+10h]
0x180086333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086338  mov     rdx, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x18008633f  mov     rcx, r12
0x180086342  mov     rax, [rdx+10h]
0x180086346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008634b  lea     r11, [rsp+70h+var_s0]
0x180086350  mov     al, bl
0x180086352  mov     rbx, [r11+20h]
0x180086356  mov     rsi, [r11+28h]
0x18008635a  mov     rsp, r11
0x18008635d  pop     r14
0x18008635f  pop     r12
0x180086361  pop     rbp
0x180086362  retn
```
