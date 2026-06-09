# RegReadBinaryValue(HKEY__ *,ushort const *,ushort const *,ushort const *,uchar * *,ulong *)

- ea: `0x18008be1c`
- end: `0x18008c045`
- name: `?RegReadBinaryValue@@YAKPEAUHKEY__@@PEBG11PEAPEAEPEAK@Z`
- size: `553`
- prototype: `unsigned int __usercall@<eax>(HKEY hkey@<rcx>, LPCWSTR lpSubKey@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18009ecd4`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x180012cf0`
- `0x18003334c`
- `0x18008be1c`
- `0x18008cf68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008bed2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008bfa0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008bed2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18008bfa0`

## string_xrefs

- `0x18008bf02`: `%s: The registry key value "%s@%s" does not exist. Using default value NULL. Error code: 0x%08x.`
- `0x18008bfec`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x18008be62`: `RegReadBinaryValue`
- `0x18008befb`: `RegReadBinaryValue`
- `0x18008bf34`: `RegReadBinaryValue`
- `0x18008bfe5`: `RegReadBinaryValue`
- `0x18008c028`: `RegReadBinaryValue`
- `0x18008bf3f`: `%s: The registry key value "%s@%s" is not of type REG_BINARY. Using default value NULL.`

## pseudocode

```c
__int64 __fastcall RegReadBinaryValue(
        HKEY hkey,
        LPCWSTR lpSubKey,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  void **v6; // rdi
  const wchar_t *v10; // r8
  unsigned int *v12; // rsi
  LSTATUS ValueW; // eax
  unsigned int v14; // ebx
  int v15; // eax
  const wchar_t *v16; // r9
  int v17; // eax
  const wchar_t *v18; // r9
  void *pvData; // rax
  int v20; // eax
  const wchar_t *v21; // r9
  LPDWORD pdwType; // [rsp+20h] [rbp-58h]
  DWORD v23[4]; // [rsp+40h] [rbp-38h] BYREF
  DWORD pcbData; // [rsp+90h] [rbp+18h] BYREF
  int v25; // [rsp+94h] [rbp+1Ch]

  v25 = HIDWORD(a3);
  v6 = (void **)a5;
  v23[0] = 0;
  pcbData = 0;
  if ( !a5 )
  {
    v10 = L"pData";
LABEL_3:
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegReadBinaryValue", v10);
    return 87;
  }
  v12 = a6;
  if ( !a6 )
  {
    v10 = L"byteCount";
    goto LABEL_3;
  }
  *a5 = 0;
  *v12 = 0;
  ValueW = RegGetValueW(hkey, lpSubKey, L"MutexName", 8u, v23, 0, &pcbData);
  v14 = ValueW;
  if ( ValueW == 2 )
  {
    v15 = IsEmptyString(L"MutexName");
    LODWORD(pdwType) = 2;
    v16 = L"(default)";
    if ( !v15 )
      v16 = L"MutexName";
    Logger::TraceWarning(
      (wchar_t *)L"%s: The registry key value \"%s@%s\" does not exist. Using default value NULL. Error code: 0x%08x.",
      L"RegReadBinaryValue",
      a4,
      v16,
      pdwType);
    return 0;
  }
  if ( ValueW )
  {
    if ( ValueW != 234 )
      goto LABEL_20;
  }
  else if ( v23[0] != 3 )
  {
    v17 = IsEmptyString(L"MutexName");
    v18 = L"(default)";
    if ( !v17 )
      v18 = L"MutexName";
    Logger::TraceWarning(
      (wchar_t *)L"%s: The registry key value \"%s@%s\" is not of type REG_BINARY. Using default value NULL.",
      L"RegReadBinaryValue",
      a4,
      v18);
    return v14;
  }
  if ( pcbData )
  {
    pvData = SafeAlloc(pcbData);
    *v6 = pvData;
    if ( !pvData )
    {
      v14 = 14;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"RegReadBinaryValue");
      goto LABEL_20;
    }
    v14 = RegGetValueW(hkey, lpSubKey, L"MutexName", 8u, v23, pvData, &pcbData);
    *v12 = pcbData;
  }
  if ( v14 )
  {
LABEL_20:
    Logger::WriteRegistryFailureEvent(v14, L"RegGetValueW", a4, L"MutexName");
    v20 = IsEmptyString(L"MutexName");
    LODWORD(pdwType) = v14;
    v21 = L"(default)";
    if ( !v20 )
      v21 = L"MutexName";
    Logger::TraceWarning(
      (wchar_t *)L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
      L"RegReadBinaryValue",
      a4,
      v21,
      pdwType);
    SafeFree(*v6);
    *v6 = 0;
    *v12 = 0;
  }
  return v14;
}

```

## disassembly

```asm
0x18008be1c  mov     rax, rsp
0x18008be1f  mov     [rax+8], rbx
0x18008be23  mov     [rax+10h], rbp
0x18008be27  mov     [rax+18h], r8
0x18008be2b  push    rsi
0x18008be2c  push    rdi
0x18008be2d  push    r13
0x18008be2f  push    r14
0x18008be31  push    r15
0x18008be33  sub     rsp, 50h
0x18008be37  mov     rdi, [rsp+78h+arg_20]
0x18008be3f  mov     rbp, r9
0x18008be42  mov     dword ptr [rax-38h], 0
0x18008be49  mov     r14, rdx
0x18008be4c  mov     dword ptr [rax+18h], 0
0x18008be53  mov     r15, rcx
0x18008be56  test    rdi, rdi
0x18008be59  jnz     short loc_18008BE7F
0x18008be5b  lea     r8, aPdata; "pData"
0x18008be62  lea     rdx, aRegreadbinaryv; "RegReadBinaryValue"
0x18008be69  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18008be70  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008be75  mov     eax, 57h ; 'W'
0x18008be7a  jmp     loc_18008C00F
0x18008be7f  mov     rsi, [rsp+78h+arg_28]
0x18008be87  test    rsi, rsi
0x18008be8a  jnz     short loc_18008BE95
0x18008be8c  lea     r8, aBytecount; "byteCount"
0x18008be93  jmp     short loc_18008BE62
0x18008be95  lea     rax, [rsp+78h+arg_10]
0x18008be9d  mov     qword ptr [rdi], 0
0x18008bea4  mov     [rsp+78h+pcbData], rax; pcbData
0x18008bea9  lea     r13, aMutexname; "MutexName"
0x18008beb0  lea     rax, [rsp+78h+var_38]
0x18008beb5  mov     [rsp+78h+pvData], 0; pvData
0x18008bebe  mov     r9d, 8; dwFlags
0x18008bec4  mov     [rsp+78h+pdwType], rax; pdwType
0x18008bec9  mov     r8, r13; lpValue
0x18008becc  mov     dword ptr [rsi], 0
0x18008bed2  call    cs:__imp_RegGetValueW
0x18008bed8  mov     ebx, eax
0x18008beda  cmp     eax, 2
0x18008bedd  jnz     short loc_18008BF15
0x18008bedf  mov     rcx, r13; unsigned __int16 *
0x18008bee2  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18008bee7  test    eax, eax
0x18008bee9  mov     dword ptr [rsp+78h+pdwType], ebx
0x18008beed  lea     r9, aDefault; "(default)"
0x18008bef4  mov     r8, rbp
0x18008bef7  cmovz   r9, r13
0x18008befb  lea     rdx, aRegreadbinaryv; "RegReadBinaryValue"
0x18008bf02  lea     rcx, aSTheRegistryKe; "%s: The registry key value \"%s@%s\" do"...
0x18008bf09  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18008bf0e  xor     ebx, ebx
0x18008bf10  jmp     loc_18008C00D
0x18008bf15  test    eax, eax
0x18008bf17  jnz     short loc_18008BF50
0x18008bf19  cmp     [rsp+78h+var_38], 3
0x18008bf1e  jz      short loc_18008BF57
0x18008bf20  mov     rcx, r13; unsigned __int16 *
0x18008bf23  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18008bf28  test    eax, eax
0x18008bf2a  lea     r9, aDefault; "(default)"
0x18008bf31  mov     r8, rbp
0x18008bf34  lea     rdx, aRegreadbinaryv; "RegReadBinaryValue"
0x18008bf3b  cmovz   r9, r13
0x18008bf3f  lea     rcx, aSTheRegistryKe_7; "%s: The registry key value \"%s@%s\" is"...
0x18008bf46  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18008bf4b  jmp     loc_18008C00D
0x18008bf50  cmp     eax, 0EAh
0x18008bf55  jnz     short loc_18008BFB5
0x18008bf57  mov     eax, [rsp+78h+arg_10]
0x18008bf5e  test    eax, eax
0x18008bf60  jz      short loc_18008BFB1
0x18008bf62  mov     ecx, eax; unsigned __int64
0x18008bf64  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x18008bf69  mov     [rdi], rax
0x18008bf6c  test    rax, rax
0x18008bf6f  jz      loc_18008C028
0x18008bf75  lea     rcx, [rsp+78h+arg_10]
0x18008bf7d  mov     r9d, 8; dwFlags
0x18008bf83  mov     [rsp+78h+pcbData], rcx; pcbData
0x18008bf88  mov     r8, r13; lpValue
0x18008bf8b  mov     [rsp+78h+pvData], rax; pvData
0x18008bf90  mov     rdx, r14; lpSubKey
0x18008bf93  lea     rax, [rsp+78h+var_38]
0x18008bf98  mov     rcx, r15; hkey
0x18008bf9b  mov     [rsp+78h+pdwType], rax; pdwType
0x18008bfa0  call    cs:__imp_RegGetValueW
0x18008bfa6  mov     ebx, eax
0x18008bfa8  mov     eax, [rsp+78h+arg_10]
0x18008bfaf  mov     [rsi], eax
0x18008bfb1  test    ebx, ebx
0x18008bfb3  jz      short loc_18008C00D
0x18008bfb5  mov     r9, r13; unsigned __int16 *
0x18008bfb8  lea     rdx, aReggetvaluew; "RegGetValueW"
0x18008bfbf  mov     r8, rbp; unsigned __int16 *
0x18008bfc2  mov     ecx, ebx; unsigned int
0x18008bfc4  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x18008bfc9  mov     rcx, r13; unsigned __int16 *
0x18008bfcc  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18008bfd1  test    eax, eax
0x18008bfd3  mov     dword ptr [rsp+78h+pdwType], ebx
0x18008bfd7  lea     r9, aDefault; "(default)"
0x18008bfde  mov     r8, rbp
0x18008bfe1  cmovz   r9, r13
0x18008bfe5  lea     rdx, aRegreadbinaryv; "RegReadBinaryValue"
0x18008bfec  lea     rcx, aSCannotReadReg_0; "%s: Cannot read registry key value \"%s"...
0x18008bff3  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18008bff8  mov     rcx, [rdi]; lpMem
0x18008bffb  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008c000  mov     qword ptr [rdi], 0
0x18008c007  mov     dword ptr [rsi], 0
0x18008c00d  mov     eax, ebx
0x18008c00f  lea     r11, [rsp+78h+var_28]
0x18008c014  mov     rbx, [r11+30h]
0x18008c018  mov     rbp, [r11+38h]
0x18008c01c  mov     rsp, r11
0x18008c01f  pop     r15
0x18008c021  pop     r14
0x18008c023  pop     r13
0x18008c025  pop     rdi
0x18008c026  pop     rsi
0x18008c027  retn
0x18008c028  lea     rdx, aRegreadbinaryv; "RegReadBinaryValue"
0x18008c02f  mov     ebx, 0Eh
0x18008c034  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18008c03b  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18008c040  jmp     loc_18008BFB5
```
