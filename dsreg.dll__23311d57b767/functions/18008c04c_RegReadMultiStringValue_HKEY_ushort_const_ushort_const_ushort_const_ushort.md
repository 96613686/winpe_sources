# RegReadMultiStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x18008c04c`
- end: `0x18008c231`
- name: `?RegReadMultiStringValue@@YAKPEAUHKEY__@@PEBG11PEAPEAG@Z`
- size: `485`
- prototype: `unsigned int __usercall@<eax>(HKEY hkey@<rcx>, LPCWSTR lpSubKey@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18005f7fc`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x180012cf0`
- `0x18003334c`
- `0x18008c04c`
- `0x18008cf68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008c0dc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008c1aa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008c0dc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008c1aa`

## string_xrefs

- `0x18008c10c`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x18008c0b9`: `Extensions`
- `0x18008c149`: `%s: The registry key value "%s@%s" is not of type REG_MULTI_SZ. Using default value NULL.`
- `0x18008c08a`: `RegReadMultiStringValue`
- `0x18008c105`: `RegReadMultiStringValue`
- `0x18008c13e`: `RegReadMultiStringValue`
- `0x18008c1e6`: `RegReadMultiStringValue`
- `0x18008c217`: `RegReadMultiStringValue`
- `0x18008c1ed`: `%s: Cannot read REG_MULTI_SZ registry key value "%s@%s". Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall RegReadMultiStringValue(
        HKEY hkey,
        LPCWSTR lpSubKey,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 **a5)
{
  void **v5; // rdi
  LSTATUS ValueW; // eax
  unsigned int v11; // ebx
  int v12; // eax
  const wchar_t *v13; // r9
  int v14; // eax
  const wchar_t *v15; // r9
  void *pvData; // rax
  int v17; // eax
  const wchar_t *v18; // r9
  LPDWORD pdwType; // [rsp+20h] [rbp-68h]
  DWORD v20[18]; // [rsp+40h] [rbp-48h] BYREF
  DWORD pcbData; // [rsp+A0h] [rbp+18h] BYREF
  int v22; // [rsp+A4h] [rbp+1Ch]

  v22 = HIDWORD(a3);
  v5 = (void **)a5;
  v20[0] = 0;
  pcbData = 0;
  if ( !a5 )
  {
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegReadMultiStringValue", L"pData");
    return 87;
  }
  *a5 = 0;
  ValueW = RegGetValueW(hkey, lpSubKey, L"Extensions", 0xFFFFu, v20, 0, &pcbData);
  v11 = ValueW;
  if ( ValueW == 2 )
  {
    v12 = IsEmptyString(L"Extensions");
    LODWORD(pdwType) = 2;
    v13 = L"(default)";
    if ( !v12 )
      v13 = L"Extensions";
    Logger::TraceWarning(
      (wchar_t *)L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.",
      L"RegReadMultiStringValue",
      a4,
      v13,
      pdwType);
    return 0;
  }
  if ( ValueW )
  {
    if ( ValueW != 234 )
      goto LABEL_17;
  }
  else if ( v20[0] != 7 )
  {
    v14 = IsEmptyString(L"Extensions");
    v15 = L"(default)";
    if ( !v14 )
      v15 = L"Extensions";
    Logger::TraceWarning(
      (wchar_t *)L"%s: The registry key value \"%s@%s\" is not of type REG_MULTI_SZ. Using default value NULL.",
      L"RegReadMultiStringValue",
      a4,
      v15);
    return v11;
  }
  if ( pcbData )
  {
    pvData = SafeAlloc(pcbData);
    *v5 = pvData;
    if ( !pvData )
    {
      v11 = 14;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadMultiStringValue");
      goto LABEL_17;
    }
    v11 = RegGetValueW(hkey, lpSubKey, L"Extensions", 0x20u, v20, pvData, &pcbData);
  }
  if ( v11 )
  {
LABEL_17:
    Logger::WriteRegistryFailureEvent(v11, L"RegGetValueW", a4, L"Extensions");
    v17 = IsEmptyString(L"Extensions");
    LODWORD(pdwType) = v11;
    v18 = L"(default)";
    if ( !v17 )
      v18 = L"Extensions";
    Logger::TraceWarning(
      (wchar_t *)L"%s: Cannot read REG_MULTI_SZ registry key value \"%s@%s\". Error code: 0x%08x.",
      L"RegReadMultiStringValue",
      a4,
      v18,
      pdwType);
    SafeFree(*v5);
    *v5 = 0;
  }
  return v11;
}

```

## disassembly

```asm
0x18008c04c  mov     rax, rsp
0x18008c04f  mov     [rax+18h], r8
0x18008c053  push    rbx
0x18008c054  push    rbp
0x18008c055  push    rsi
0x18008c056  push    rdi
0x18008c057  push    r12
0x18008c059  push    r14
0x18008c05b  sub     rsp, 58h
0x18008c05f  mov     rdi, [rsp+88h+arg_20]
0x18008c067  mov     rsi, r9
0x18008c06a  mov     dword ptr [rax-48h], 0
0x18008c071  mov     rbp, rdx
0x18008c074  mov     dword ptr [rax+18h], 0
0x18008c07b  mov     r14, rcx
0x18008c07e  test    rdi, rdi
0x18008c081  jnz     short loc_18008C0A5
0x18008c083  lea     r8, aPdata; "pData"
0x18008c08a  lea     rdx, aRegreadmultist; "RegReadMultiStringValue"
0x18008c091  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18008c098  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008c09d  lea     eax, [rdi+57h]
0x18008c0a0  jmp     loc_18008C20A
0x18008c0a5  lea     rax, [rsp+88h+arg_10]
0x18008c0ad  mov     qword ptr [rdi], 0
0x18008c0b4  mov     [rsp+88h+pcbData], rax; pcbData
0x18008c0b9  lea     r12, aExtensions_0; "Extensions"
0x18008c0c0  lea     rax, [rsp+88h+var_48]
0x18008c0c5  mov     [rsp+88h+pvData], 0; pvData
0x18008c0ce  mov     r9d, 0FFFFh; dwFlags
0x18008c0d4  mov     [rsp+88h+pdwType], rax; pdwType
0x18008c0d9  mov     r8, r12; lpValue
0x18008c0dc  call    cs:__imp_RegGetValueW
0x18008c0e2  mov     ebx, eax
0x18008c0e4  cmp     eax, 2
0x18008c0e7  jnz     short loc_18008C11F
0x18008c0e9  mov     rcx, r12; unsigned __int16 *
0x18008c0ec  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18008c0f1  test    eax, eax
0x18008c0f3  mov     dword ptr [rsp+88h+pdwType], ebx
0x18008c0f7  lea     r9, aDefault; "(default)"
0x18008c0fe  mov     r8, rsi
0x18008c101  cmovz   r9, r12
0x18008c105  lea     rdx, aRegreadmultist; "RegReadMultiStringValue"
0x18008c10c  lea     rcx, aSTheRegistryKe; "%s: The registry key value \"%s@%s\" do"...
0x18008c113  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18008c118  xor     ebx, ebx
0x18008c11a  jmp     loc_18008C208
0x18008c11f  test    eax, eax
0x18008c121  jnz     short loc_18008C15A
0x18008c123  cmp     [rsp+88h+var_48], 7
0x18008c128  jz      short loc_18008C161
0x18008c12a  mov     rcx, r12; unsigned __int16 *
0x18008c12d  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18008c132  test    eax, eax
0x18008c134  lea     r9, aDefault; "(default)"
0x18008c13b  mov     r8, rsi
0x18008c13e  lea     rdx, aRegreadmultist; "RegReadMultiStringValue"
0x18008c145  cmovz   r9, r12
0x18008c149  lea     rcx, aSTheRegistryKe_11; "%s: The registry key value \"%s@%s\" is"...
0x18008c150  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18008c155  jmp     loc_18008C208
0x18008c15a  cmp     eax, 0EAh
0x18008c15f  jnz     short loc_18008C1B6
0x18008c161  mov     eax, [rsp+88h+arg_10]
0x18008c168  test    eax, eax
0x18008c16a  jz      short loc_18008C1B2
0x18008c16c  mov     ecx, eax; unsigned __int64
0x18008c16e  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x18008c173  mov     [rdi], rax
0x18008c176  test    rax, rax
0x18008c179  jz      loc_18008C217
0x18008c17f  lea     rcx, [rsp+88h+arg_10]
0x18008c187  mov     r9d, 20h ; ' '; dwFlags
0x18008c18d  mov     [rsp+88h+pcbData], rcx; pcbData
0x18008c192  mov     r8, r12; lpValue
0x18008c195  mov     [rsp+88h+pvData], rax; pvData
0x18008c19a  mov     rdx, rbp; lpSubKey
0x18008c19d  lea     rax, [rsp+88h+var_48]
0x18008c1a2  mov     rcx, r14; hkey
0x18008c1a5  mov     [rsp+88h+pdwType], rax; pdwType
0x18008c1aa  call    cs:__imp_RegGetValueW
0x18008c1b0  mov     ebx, eax
0x18008c1b2  test    ebx, ebx
0x18008c1b4  jz      short loc_18008C208
0x18008c1b6  mov     r9, r12; unsigned __int16 *
0x18008c1b9  lea     rdx, aReggetvaluew; "RegGetValueW"
0x18008c1c0  mov     r8, rsi; unsigned __int16 *
0x18008c1c3  mov     ecx, ebx; unsigned int
0x18008c1c5  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x18008c1ca  mov     rcx, r12; unsigned __int16 *
0x18008c1cd  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18008c1d2  test    eax, eax
0x18008c1d4  mov     dword ptr [rsp+88h+pdwType], ebx
0x18008c1d8  lea     r9, aDefault; "(default)"
0x18008c1df  mov     r8, rsi
0x18008c1e2  cmovz   r9, r12
0x18008c1e6  lea     rdx, aRegreadmultist; "RegReadMultiStringValue"
0x18008c1ed  lea     rcx, aSCannotReadReg; "%s: Cannot read REG_MULTI_SZ registry k"...
0x18008c1f4  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18008c1f9  mov     rcx, [rdi]; lpMem
0x18008c1fc  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008c201  mov     qword ptr [rdi], 0
0x18008c208  mov     eax, ebx
0x18008c20a  add     rsp, 58h
0x18008c20e  pop     r14
0x18008c210  pop     r12
0x18008c212  pop     rdi
0x18008c213  pop     rsi
0x18008c214  pop     rbp
0x18008c215  pop     rbx
0x18008c216  retn
0x18008c217  lea     rdx, aRegreadmultist; "RegReadMultiStringValue"
0x18008c21e  mov     ebx, 0Eh
0x18008c223  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18008c22a  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18008c22f  jmp     short loc_18008C1B6
```
