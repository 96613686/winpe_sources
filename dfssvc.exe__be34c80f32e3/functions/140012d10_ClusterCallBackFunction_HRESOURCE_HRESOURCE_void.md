# ClusterCallBackFunction(_HRESOURCE *,_HRESOURCE *,void *)

- ea: `0x140012d10`
- end: `0x140012ecb`
- name: `?ClusterCallBackFunction@@YAKPEAU_HRESOURCE@@0PEAX@Z`
- size: `443`
- prototype: `DWORD __stdcall(HRESOURCE, HRESOURCE, PVOID)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x140006bf0`
- `0x140012d10`
- `0x140013550`
- `0x1400586a8`
- `0x140058db8`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140012e09`
- `msvcrt!_wcsnicmp` at `0x140012e09`
- `ntdll!RtlEqualUnicodeString` at `0x140012e57`
- `ntdll!RtlEqualUnicodeString` at `0x140012e57`
- `ntdll!RtlInitUnicodeString` at `0x140012e1f`
- `ntdll!RtlInitUnicodeString` at `0x140012e7d`
- `ntdll!RtlInitUnicodeString` at `0x140012e1f`
- `ntdll!RtlInitUnicodeString` at `0x140012e7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012d6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012e95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012e95`
- `CLUSAPI!ClusterRegCloseKey` at `0x140012d9d`
- `CLUSAPI!ClusterRegCloseKey` at `0x140012ea5`
- `CLUSAPI!ClusterRegCloseKey` at `0x140012d9d`
- `CLUSAPI!ClusterRegCloseKey` at `0x140012ea5`
- `CLUSAPI!ClusterRegOpenKey` at `0x140012d8c`
- `CLUSAPI!ClusterRegOpenKey` at `0x140012d8c`
- `CLUSAPI!GetClusterResourceKey` at `0x140012d56`
- `CLUSAPI!GetClusterResourceKey` at `0x140012d56`
- `RESUTILS!ResUtilGetSzValue` at `0x140012dbf`
- `RESUTILS!ResUtilGetSzValue` at `0x140012dbf`

## string_xrefs

- `0x140012db8`: `ShareName`

## pseudocode

```c
DWORD __fastcall ClusterCallBackFunction(unsigned int *a1, HRESOURCE a2, PVOID a3)
{
  unsigned int inited; // esi
  unsigned __int8 v6; // r15
  HKEY ClusterResourceKey; // rax
  HKEY v8; // r14
  LONG v10; // ebx
  LPWSTR SzValue; // rax
  LPWSTR v12; // rbx
  __int64 v13; // rcx
  struct _UNICODE_STRING *p_DestinationString; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-20h] BYREF
  wchar_t *String2[2]; // [rsp+30h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp+40h] BYREF

  phkResult = 0;
  *(_OWORD *)String2 = 0;
  inited = 0;
  DestinationString = 0;
  v6 = *(_BYTE *)CConfigurationSettings::_GetInstance(a1);
  ClusterResourceKey = GetClusterResourceKey(a2, 0x20019u);
  v8 = ClusterResourceKey;
  if ( !ClusterResourceKey )
    return GetLastError();
  v10 = ClusterRegOpenKey(ClusterResourceKey, L"Parameters", 0x20019u, &phkResult);
  ClusterRegCloseKey(v8);
  if ( v10 )
    return 0;
  SzValue = ResUtilGetSzValue(phkResult, L"ShareName");
  v12 = SzValue;
  if ( SzValue )
  {
    inited = DfsRtlInitUnicodeStringEx(String2, SzValue);
    if ( !inited )
    {
      v13 = *((_QWORD *)a3 + 1);
      if ( *(_WORD *)v13 == LOWORD(String2[0])
        && !_wcsnicmp(*(const wchar_t **)(v13 + 8), String2[1], LOWORD(String2[0])) )
      {
        RtlInitUnicodeString(&DestinationString, 0);
        inited = DfsGetClusterResourceNetworkName(a2, *((struct _UNICODE_STRING **)a3 + 2), &DestinationString, v6);
        if ( !inited )
        {
          p_DestinationString = &DestinationString;
          if ( !v6 )
            p_DestinationString = (struct _UNICODE_STRING *)*((_QWORD *)a3 + 2);
          if ( RtlEqualUnicodeString(p_DestinationString, *(PCUNICODE_STRING *)a3, 1u) == 1 )
          {
            inited = 259;
          }
          else
          {
            DfsFreeUnicodeString(*((_QWORD *)a3 + 2));
            RtlInitUnicodeString(*((PUNICODE_STRING *)a3 + 2), 0);
          }
          DfsFreeUnicodeString(&DestinationString);
        }
      }
    }
    LocalFree(v12);
  }
  ClusterRegCloseKey(phkResult);
  return inited;
}

```

## disassembly

```asm
0x140012d10  mov     [rsp-28h+arg_0], rbx
0x140012d15  mov     [rsp-28h+arg_8], rsi
0x140012d1a  push    rbp
0x140012d1b  push    rdi
0x140012d1c  push    r12
0x140012d1e  push    r14
0x140012d20  push    r15
0x140012d22  mov     rbp, rsp
0x140012d25  sub     rsp, 40h
0x140012d29  and     [rbp+phkResult], 0
0x140012d2e  xorps   xmm0, xmm0
0x140012d31  xorps   xmm1, xmm1
0x140012d34  mov     rdi, r8
0x140012d37  movups  xmmword ptr [rbp+String2], xmm0
0x140012d3b  mov     r12, rdx
0x140012d3e  xor     esi, esi
0x140012d40  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x140012d44  call    ?_GetInstance@CConfigurationSettings@@SAPEAV1@PEAK@Z; CConfigurationSettings::_GetInstance(ulong *)
0x140012d49  mov     ebx, 20019h
0x140012d4e  mov     rcx, r12; hResource
0x140012d51  mov     edx, ebx; samDesired
0x140012d53  mov     r15b, [rax]
0x140012d56  call    cs:__imp_GetClusterResourceKey
0x140012d5d  nop     dword ptr [rax+rax+00h]
0x140012d62  mov     r14, rax
0x140012d65  test    rax, rax
0x140012d68  jnz     short loc_140012D7B
0x140012d6a  call    cs:__imp_GetLastError
0x140012d71  nop     dword ptr [rax+rax+00h]
0x140012d76  jmp     loc_140012EB3
0x140012d7b  lea     r9, [rbp+phkResult]; phkResult
0x140012d7f  mov     r8d, ebx; samDesired
0x140012d82  lea     rdx, szSubKey; "Parameters"
0x140012d89  mov     rcx, r14; hKey
0x140012d8c  call    cs:__imp_ClusterRegOpenKey
0x140012d93  nop     dword ptr [rax+rax+00h]
0x140012d98  mov     rcx, r14; hKey
0x140012d9b  mov     ebx, eax
0x140012d9d  call    cs:__imp_ClusterRegCloseKey
0x140012da4  nop     dword ptr [rax+rax+00h]
0x140012da9  test    ebx, ebx
0x140012dab  jz      short loc_140012DB4
0x140012dad  xor     eax, eax
0x140012daf  jmp     loc_140012EB3
0x140012db4  mov     rcx, [rbp+phkResult]; hkeyClusterKey
0x140012db8  lea     rdx, pszValueName; "ShareName"
0x140012dbf  call    cs:__imp_ResUtilGetSzValue
0x140012dc6  nop     dword ptr [rax+rax+00h]
0x140012dcb  mov     rbx, rax
0x140012dce  test    rax, rax
0x140012dd1  jz      loc_140012EA1
0x140012dd7  mov     rdx, rax
0x140012dda  lea     rcx, [rbp+String2]
0x140012dde  call    DfsRtlInitUnicodeStringEx
0x140012de3  mov     esi, eax
0x140012de5  test    eax, eax
0x140012de7  jnz     loc_140012E92
0x140012ded  mov     rcx, [rdi+8]
0x140012df1  movzx   eax, word ptr [rbp+String2]
0x140012df5  cmp     [rcx], ax
0x140012df8  jnz     loc_140012E92
0x140012dfe  mov     rdx, [rbp+String2+8]; String2
0x140012e02  mov     r8d, eax; MaxCount
0x140012e05  mov     rcx, [rcx+8]; String1
0x140012e09  call    cs:__imp__wcsnicmp
0x140012e10  nop     dword ptr [rax+rax+00h]
0x140012e15  test    eax, eax
0x140012e17  jnz     short loc_140012E92
0x140012e19  xor     edx, edx; SourceString
0x140012e1b  lea     rcx, [rbp+DestinationString]; DestinationString
0x140012e1f  call    cs:__imp_RtlInitUnicodeString
0x140012e26  nop     dword ptr [rax+rax+00h]
0x140012e2b  mov     rdx, [rdi+10h]; struct _UNICODE_STRING *
0x140012e2f  lea     r8, [rbp+DestinationString]; struct _UNICODE_STRING *
0x140012e33  mov     r9b, r15b; unsigned __int8
0x140012e36  mov     rcx, r12; struct _HRESOURCE *
0x140012e39  call    ?DfsGetClusterResourceNetworkName@@YAKPEAU_HRESOURCE@@PEAU_UNICODE_STRING@@1E@Z; DfsGetClusterResourceNetworkName(_HRESOURCE *,_UNICODE_STRING *,_UNICODE_STRING *,uchar)
0x140012e3e  mov     esi, eax
0x140012e40  test    eax, eax
0x140012e42  jnz     short loc_140012E92
0x140012e44  lea     rcx, [rbp+DestinationString]
0x140012e48  test    r15b, r15b
0x140012e4b  jnz     short loc_140012E51
0x140012e4d  mov     rcx, [rdi+10h]; String1
0x140012e51  mov     rdx, [rdi]; String2
0x140012e54  mov     r8b, 1; CaseInsensitive
0x140012e57  call    cs:__imp_RtlEqualUnicodeString
0x140012e5e  nop     dword ptr [rax+rax+00h]
0x140012e63  cmp     al, 1
0x140012e65  jnz     short loc_140012E6E
0x140012e67  mov     esi, 103h
0x140012e6c  jmp     short loc_140012E89
0x140012e6e  mov     rcx, [rdi+10h]
0x140012e72  call    DfsFreeUnicodeString
0x140012e77  mov     rcx, [rdi+10h]; DestinationString
0x140012e7b  xor     edx, edx; SourceString
0x140012e7d  call    cs:__imp_RtlInitUnicodeString
0x140012e84  nop     dword ptr [rax+rax+00h]
0x140012e89  lea     rcx, [rbp+DestinationString]
0x140012e8d  call    DfsFreeUnicodeString
0x140012e92  mov     rcx, rbx; hMem
0x140012e95  call    cs:__imp_LocalFree
0x140012e9c  nop     dword ptr [rax+rax+00h]
0x140012ea1  mov     rcx, [rbp+phkResult]; hKey
0x140012ea5  call    cs:__imp_ClusterRegCloseKey
0x140012eac  nop     dword ptr [rax+rax+00h]
0x140012eb1  mov     eax, esi
0x140012eb3  mov     rbx, [rsp+40h+arg_0]
0x140012eb8  mov     rsi, [rsp+40h+arg_8]
0x140012ebd  add     rsp, 40h
0x140012ec1  pop     r15
0x140012ec3  pop     r14
0x140012ec5  pop     r12
0x140012ec7  pop     rdi
0x140012ec8  pop     rbp
0x140012ec9  retn
```
