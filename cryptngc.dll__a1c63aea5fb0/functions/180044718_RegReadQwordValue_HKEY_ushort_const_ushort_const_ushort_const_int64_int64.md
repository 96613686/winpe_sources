# RegReadQwordValue(HKEY__ *,ushort const *,ushort const *,ushort const *,__int64 *,__int64)

- ea: `0x180044718`
- end: `0x180044868`
- name: `?RegReadQwordValue@@YAKPEAUHKEY__@@PEBG11PEA_J_J@Z`
- size: `336`
- prototype: `unsigned int(HKEY, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800273dc`

## callees

- `0x18000c190`
- `0x180027448`
- `0x18002c23c`
- `0x180044718`
- `0x180044a9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800447a4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800447a4`

## string_xrefs

- `0x18004485a`: `%s: Cannot read registry key value "%s@%s". Error code: 0x%08x.`
- `0x180044755`: `RegReadQwordValue`
- `0x180044808`: `RegReadQwordValue`
- `0x180044853`: `RegReadQwordValue`
- `0x1800447bd`: `%s: The registry key value "%s@%s" does not exist. Using default value %I64d. Error code: 0x%08x.`
- `0x1800447e8`: `%s: The registry key value "%s@%s" is not of type QWORD. Using default value %I64d. Error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall RegReadQwordValue(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        __int64 *a5,
        __int64 pcbData)
{
  __int64 *v6; // rdi
  LSTATUS ValueW; // eax
  const unsigned __int16 *v10; // rdx
  unsigned int v11; // ebx
  int v12; // eax
  const unsigned __int16 *v13; // rcx
  const wchar_t *v14; // r9
  int v15; // eax
  const wchar_t *v16; // r9
  LPDWORD pdwType; // [rsp+20h] [rbp-58h]
  PVOID pvData; // [rsp+28h] [rbp-50h]
  __int64 v19[7]; // [rsp+40h] [rbp-38h] BYREF
  DWORD v20; // [rsp+90h] [rbp+18h] BYREF
  int v21; // [rsp+94h] [rbp+1Ch]

  v21 = HIDWORD(a3);
  v6 = a5;
  v20 = 0;
  LODWORD(pcbData) = 8;
  v19[0] = 0;
  if ( !a5 )
  {
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"RegReadQwordValue", L"pData");
    return 87;
  }
  ValueW = RegGetValueW(a1, a2, L"LastSyncTime", 0xFFFFu, &v20, v19, (LPDWORD)&pcbData);
  v11 = ValueW;
  if ( ValueW == 2 )
  {
    v12 = IsEmptyString(L"LastSyncTime");
    LODWORD(pvData) = 2;
    v13 = L"%s: The registry key value \"%s@%s\" does not exist. Using default value %I64d. Error code: 0x%08x.";
LABEL_9:
    v14 = L"(default)";
    if ( !v12 )
      v14 = L"LastSyncTime";
    Logger::TraceWarning(v13, L"RegReadQwordValue", a4, v14, 0, pvData);
    v11 = 0;
    goto LABEL_12;
  }
  if ( ValueW == 234 )
    goto LABEL_8;
  if ( ValueW )
  {
    Logger::WriteRegistryFailureEvent(ValueW, v10, a4, L"LastSyncTime");
    v15 = IsEmptyString(L"LastSyncTime");
    LODWORD(pdwType) = v11;
    v16 = L"(default)";
    if ( !v15 )
      v16 = L"LastSyncTime";
    Logger::TraceWarning(
      L"%s: Cannot read registry key value \"%s@%s\". Error code: 0x%08x.",
      L"RegReadQwordValue",
      a4,
      v16,
      pdwType);
    goto LABEL_12;
  }
  if ( v20 != 11 )
  {
LABEL_8:
    v12 = IsEmptyString(L"LastSyncTime");
    LODWORD(pvData) = v11;
    v13 = L"%s: The registry key value \"%s@%s\" is not of type QWORD. Using default value %I64d. Error code: 0x%08x.";
    goto LABEL_9;
  }
LABEL_12:
  *v6 = v19[0];
  return v11;
}

```

## disassembly

```asm
0x180044718  mov     rax, rsp
0x18004471b  mov     [rax+18h], r8
0x18004471f  push    rbx
0x180044720  push    rsi
0x180044721  push    rdi
0x180044722  push    r14
0x180044724  sub     rsp, 58h
0x180044728  mov     rdi, [rsp+78h+arg_20]
0x180044730  mov     rsi, r9
0x180044733  mov     dword ptr [rax+18h], 0
0x18004473a  mov     dword ptr [rax+30h], 8
0x180044741  mov     qword ptr [rax-38h], 0
0x180044749  test    rdi, rdi
0x18004474c  jnz     short loc_180044770
0x18004474e  lea     r8, aPdata; "pData"
0x180044755  lea     rdx, aRegreadqwordva; "RegReadQwordValue"
0x18004475c  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x180044763  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180044768  lea     eax, [rdi+57h]
0x18004476b  jmp     loc_180044820
0x180044770  lea     rax, [rsp+78h+arg_28]
0x180044778  mov     r9d, 0FFFFh; dwFlags
0x18004477e  mov     [rsp+78h+pcbData], rax; pcbData
0x180044783  lea     r14, aLastsynctime; "LastSyncTime"
0x18004478a  lea     rax, [rsp+78h+var_38]
0x18004478f  mov     r8, r14; lpValue
0x180044792  mov     [rsp+78h+pvData], rax; pvData
0x180044797  lea     rax, [rsp+78h+arg_10]
0x18004479f  mov     [rsp+78h+pdwType], rax; pdwType
0x1800447a4  call    cs:__imp_RegGetValueW
0x1800447aa  mov     ebx, eax
0x1800447ac  cmp     eax, 2
0x1800447af  jnz     short loc_1800447C6
0x1800447b1  mov     rcx, r14; unsigned __int16 *
0x1800447b4  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800447b9  mov     dword ptr [rsp+78h+pvData], ebx
0x1800447bd  lea     rcx, aSTheRegistryKe_1; "%s: The registry key value \"%s@%s\" do"...
0x1800447c4  jmp     short loc_1800447EF
0x1800447c6  cmp     ebx, 0EAh
0x1800447cc  jz      short loc_1800447DC
0x1800447ce  test    ebx, ebx
0x1800447d0  jnz     short loc_18004482A
0x1800447d2  cmp     [rsp+78h+arg_10], 0Bh
0x1800447da  jz      short loc_180044816
0x1800447dc  mov     rcx, r14; unsigned __int16 *
0x1800447df  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x1800447e4  mov     dword ptr [rsp+78h+pvData], ebx
0x1800447e8  lea     rcx, aSTheRegistryKe_3; "%s: The registry key value \"%s@%s\" is"...
0x1800447ef  test    eax, eax
0x1800447f1  mov     [rsp+78h+pdwType], 0
0x1800447fa  lea     r9, aDefault; "(default)"
0x180044801  mov     r8, rsi
0x180044804  cmovz   r9, r14
0x180044808  lea     rdx, aRegreadqwordva; "RegReadQwordValue"
0x18004480f  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180044814  xor     ebx, ebx
0x180044816  mov     rax, [rsp+78h+var_38]
0x18004481b  mov     [rdi], rax
0x18004481e  mov     eax, ebx
0x180044820  add     rsp, 58h
0x180044824  pop     r14
0x180044826  pop     rdi
0x180044827  pop     rsi
0x180044828  pop     rbx
0x180044829  retn
0x18004482a  mov     r9, r14; unsigned __int16 *
0x18004482d  mov     r8, rsi; unsigned __int16 *
0x180044830  mov     ecx, ebx; unsigned int
0x180044832  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG00@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *,ushort const *)
0x180044837  mov     rcx, r14; unsigned __int16 *
0x18004483a  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18004483f  test    eax, eax
0x180044841  mov     dword ptr [rsp+78h+pdwType], ebx
0x180044845  lea     r9, aDefault; "(default)"
0x18004484c  mov     r8, rsi
0x18004484f  cmovz   r9, r14
0x180044853  lea     rdx, aRegreadqwordva; "RegReadQwordValue"
0x18004485a  lea     rcx, aSCannotReadReg; "%s: Cannot read registry key value \"%s"...
0x180044861  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180044866  jmp     short loc_180044816
```
