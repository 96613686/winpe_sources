# WriteMultipleKeyBlobsToRegistry(HKEY__ *,ulong,uchar const *,ulong)

- ea: `0x1800c961c`
- end: `0x1800c9843`
- name: `?WriteMultipleKeyBlobsToRegistry@@YAHPEAUHKEY__@@KPEBEK@Z`
- size: `551`
- prototype: `__int64 __fastcall(HKEY, unsigned int, const unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800c7a84`
- `0x1800c9554`

## callees

- `0x180021920`
- `0x180031b18`
- `0x1800b65a0`
- `0x1800bec20`
- `0x1800bf4f6`
- `0x1800c961c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c97aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c97aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c96a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c9813`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c96a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c9813`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800c97f7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800c9807`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800c97f7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800c9807`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c97e0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c97e0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c974f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c974f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c970f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c970f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c9764`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c9764`

## pseudocode

```c
__int64 __fastcall WriteMultipleKeyBlobsToRegistry(
        HKEY a1,
        unsigned int a2,
        const unsigned __int8 *a3,
        unsigned int a4)
{
  unsigned int v5; // r12d
  unsigned int v7; // r14d
  unsigned int v8; // ebx
  DWORD v9; // ecx
  LSTATUS v10; // eax
  unsigned int v11; // esi
  unsigned int j; // r15d
  DWORD v13; // r12d
  DWORD LastError; // r15d
  unsigned int i; // esi
  HKEY hKey; // [rsp+50h] [rbp-59h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-51h] BYREF
  unsigned int v19; // [rsp+5Ch] [rbp-4Dh]
  const unsigned __int8 *v20; // [rsp+60h] [rbp-49h]
  WCHAR SubKey; // [rsp+70h] [rbp-39h] BYREF
  wchar_t Buffer[36]; // [rsp+78h] [rbp-31h] BYREF

  v20 = a3;
  v19 = a2;
  v5 = a2;
  hKey = 0;
  v7 = 1;
  if ( !a4 )
  {
    v8 = 0;
    v9 = -2147418113;
LABEL_7:
    SetLastError(v9);
LABEL_17:
    LastError = GetLastError();
    ILS_CloseRegistryKey(hKey);
    for ( i = 0; i < v8; ++i )
    {
      ltow(i, Buffer, 10);
      RegDeleteKeyExW(a1, &SubKey, 0, 0);
    }
    RegDeleteValueW(a1, L"BlobCount");
    RegDeleteValueW(a1, L"BlobLength");
    v7 = 0;
    SetLastError(LastError);
    return v7;
  }
  v8 = (a4 >> 19) + 1;
  if ( (a4 & 0x7FFFF) == 0 )
    v8 = a4 >> 19;
  v10 = StringCchCopyW(&SubKey, 5u, L"Blob");
  if ( v10 < 0 )
  {
LABEL_6:
    v9 = v10;
    goto LABEL_7;
  }
  v11 = 0;
  for ( j = 0; j < v8; ++j )
  {
    dwDisposition = 0;
    ltow(j, Buffer, 10);
    v10 = RegCreateKeyExW(a1, &SubKey, 0, 0, (v5 >> 9) & 4, 0x20006u, 0, &hKey, &dwDisposition);
    if ( v10 )
      goto LABEL_6;
    v13 = a4 - v11;
    if ( a4 - v11 > 0x80000 )
      v13 = 0x80000;
    v10 = RegSetValueExW(hKey, L"Blob", 0, 3u, &v20[v11], v13);
    if ( v10 )
      goto LABEL_6;
    v11 += v13;
    RegCloseKey(hKey);
    v5 = v19;
    hKey = 0;
  }
  if ( !(unsigned int)WriteDWORDValueToRegistry(a1, L"BlobCount", v8)
    || !(unsigned int)WriteDWORDValueToRegistry(a1, L"BlobLength", v11) )
  {
    goto LABEL_17;
  }
  return v7;
}

```

## disassembly

```asm
0x1800c961c  mov     [rsp-8+arg_8], rbx
0x1800c9621  push    rbp
0x1800c9622  push    rsi
0x1800c9623  push    rdi
0x1800c9624  push    r12
0x1800c9626  push    r13
0x1800c9628  push    r14
0x1800c962a  push    r15
0x1800c962c  lea     rbp, [rsp-27h]
0x1800c9631  sub     rsp, 0D0h
0x1800c9638  mov     rax, cs:__security_cookie
0x1800c963f  xor     rax, rsp
0x1800c9642  mov     [rbp+57h+var_40], rax
0x1800c9646  mov     [rbp+57h+var_A0], r8
0x1800c964a  mov     r13d, r9d
0x1800c964d  mov     [rbp+57h+var_A4], edx
0x1800c9650  mov     r12d, edx
0x1800c9653  mov     [rbp+57h+hKey], 0
0x1800c965b  mov     rdi, rcx
0x1800c965e  mov     r14d, 1
0x1800c9664  test    r9d, r9d
0x1800c9667  jnz     short loc_1800C9672
0x1800c9669  xor     ebx, ebx
0x1800c966b  mov     ecx, 8000FFFFh
0x1800c9670  jmp     short loc_1800C96A0
0x1800c9672  mov     eax, r13d
0x1800c9675  lea     r8, aBlob; "Blob"
0x1800c967c  shr     eax, 13h
0x1800c967f  lea     rcx, [rbp+57h+SubKey]; unsigned __int16 *
0x1800c9683  test    r13d, 7FFFFh
0x1800c968a  mov     edx, 5; unsigned __int64
0x1800c968f  lea     ebx, [rax+1]
0x1800c9692  cmovz   ebx, eax
0x1800c9695  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800c969a  test    eax, eax
0x1800c969c  jns     short loc_1800C96AB
0x1800c969e  mov     ecx, eax; dwErrCode
0x1800c96a0  call    cs:__imp_SetLastError
0x1800c96a6  jmp     loc_1800C97AA
0x1800c96ab  xor     esi, esi
0x1800c96ad  xor     r15d, r15d
0x1800c96b0  cmp     r15d, ebx
0x1800c96b3  jnb     loc_1800C977E
0x1800c96b9  mov     r8d, 0Ah; Radix
0x1800c96bf  mov     [rbp+57h+dwDisposition], 0
0x1800c96c6  lea     rdx, [rbp+57h+Buffer]; Buffer
0x1800c96ca  mov     ecx, r15d; Value
0x1800c96cd  call    _ltow
0x1800c96d2  lea     rcx, [rbp+57h+dwDisposition]
0x1800c96d6  mov     eax, r12d
0x1800c96d9  mov     [rsp+100h+lpdwDisposition], rcx; lpdwDisposition
0x1800c96de  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x1800c96e2  lea     rcx, [rbp+57h+hKey]
0x1800c96e6  shr     eax, 9
0x1800c96e9  mov     [rsp+100h+phkResult], rcx; phkResult
0x1800c96ee  and     eax, 4
0x1800c96f1  mov     [rsp+100h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800c96fa  xor     r9d, r9d; lpClass
0x1800c96fd  mov     [rsp+100h+samDesired], 20006h; samDesired
0x1800c9705  xor     r8d, r8d; Reserved
0x1800c9708  mov     rcx, rdi; hKey
0x1800c970b  mov     [rsp+100h+dwOptions], eax; dwOptions
0x1800c970f  call    cs:__imp_RegCreateKeyExW
0x1800c9715  test    eax, eax
0x1800c9717  jnz     short loc_1800C969E
0x1800c9719  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c971d  lea     rdx, aBlob; "Blob"
0x1800c9724  mov     eax, 80000h
0x1800c9729  mov     r12d, r13d
0x1800c972c  sub     r12d, esi
0x1800c972f  mov     r9d, 3; dwType
0x1800c9735  cmp     r12d, eax
0x1800c9738  cmova   r12d, eax
0x1800c973c  mov     eax, esi
0x1800c973e  add     rax, [rbp+57h+var_A0]
0x1800c9742  xor     r8d, r8d; Reserved
0x1800c9745  mov     [rsp+100h+samDesired], r12d; cbData
0x1800c974a  mov     qword ptr [rsp+100h+dwOptions], rax; lpData
0x1800c974f  call    cs:__imp_RegSetValueExW
0x1800c9755  test    eax, eax
0x1800c9757  jnz     loc_1800C969E
0x1800c975d  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c9761  add     esi, r12d
0x1800c9764  call    cs:__imp_RegCloseKey
0x1800c976a  mov     r12d, [rbp+57h+var_A4]
0x1800c976e  add     r15d, r14d
0x1800c9771  mov     [rbp+57h+hKey], 0
0x1800c9779  jmp     loc_1800C96B0
0x1800c977e  mov     r8d, ebx; unsigned int
0x1800c9781  lea     rdx, aBlobcount; "BlobCount"
0x1800c9788  mov     rcx, rdi; HKEY
0x1800c978b  call    ?WriteDWORDValueToRegistry@@YAHPEAUHKEY__@@PEBGK@Z; WriteDWORDValueToRegistry(HKEY__ *,ushort const *,ulong)
0x1800c9790  test    eax, eax
0x1800c9792  jz      short loc_1800C97AA
0x1800c9794  mov     r8d, esi; unsigned int
0x1800c9797  lea     rdx, aBloblength; "BlobLength"
0x1800c979e  mov     rcx, rdi; HKEY
0x1800c97a1  call    ?WriteDWORDValueToRegistry@@YAHPEAUHKEY__@@PEBGK@Z; WriteDWORDValueToRegistry(HKEY__ *,ushort const *,ulong)
0x1800c97a6  test    eax, eax
0x1800c97a8  jnz     short loc_1800C9819
0x1800c97aa  call    cs:__imp_GetLastError
0x1800c97b0  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c97b4  mov     r15d, eax
0x1800c97b7  call    ?ILS_CloseRegistryKey@@YAXPEAUHKEY__@@@Z; ILS_CloseRegistryKey(HKEY__ *)
0x1800c97bc  xor     esi, esi
0x1800c97be  test    ebx, ebx
0x1800c97c0  jz      short loc_1800C97ED
0x1800c97c2  mov     r8d, 0Ah; Radix
0x1800c97c8  lea     rdx, [rbp+57h+Buffer]; Buffer
0x1800c97cc  mov     ecx, esi; Value
0x1800c97ce  call    _ltow
0x1800c97d3  xor     r9d, r9d; Reserved
0x1800c97d6  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x1800c97da  xor     r8d, r8d; samDesired
0x1800c97dd  mov     rcx, rdi; hKey
0x1800c97e0  call    cs:__imp_RegDeleteKeyExW
0x1800c97e6  add     esi, r14d
0x1800c97e9  cmp     esi, ebx
0x1800c97eb  jb      short loc_1800C97C2
0x1800c97ed  lea     rdx, aBlobcount; "BlobCount"
0x1800c97f4  mov     rcx, rdi; hKey
0x1800c97f7  call    cs:__imp_RegDeleteValueW
0x1800c97fd  lea     rdx, aBloblength; "BlobLength"
0x1800c9804  mov     rcx, rdi; hKey
0x1800c9807  call    cs:__imp_RegDeleteValueW
0x1800c980d  mov     ecx, r15d; dwErrCode
0x1800c9810  xor     r14d, r14d
0x1800c9813  call    cs:__imp_SetLastError
0x1800c9819  mov     eax, r14d
0x1800c981c  mov     rcx, [rbp+57h+var_40]
0x1800c9820  xor     rcx, rsp; StackCookie
0x1800c9823  call    __security_check_cookie
0x1800c9828  mov     rbx, [rsp+100h+arg_8]
0x1800c9830  add     rsp, 0D0h
0x1800c9837  pop     r15
0x1800c9839  pop     r14
0x1800c983b  pop     r13
0x1800c983d  pop     r12
0x1800c983f  pop     rdi
0x1800c9840  pop     rsi
0x1800c9841  pop     rbp
0x1800c9842  retn
```
