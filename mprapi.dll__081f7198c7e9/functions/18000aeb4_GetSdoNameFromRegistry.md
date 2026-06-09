# GetSdoNameFromRegistry

- ea: `0x18000aeb4`
- end: `0x18000af87`
- name: `GetSdoNameFromRegistry`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18001555c`

## callees

- `0x18000aeb4`
- `0x1800152ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000af54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000af62`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000af62`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000af40`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000af40`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000aef4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000aef4`
- `OLEAUT32!__imp_SysAllocString` at `0x18000af24`
- `OLEAUT32!__imp_SysAllocString` at `0x18000af24`

## string_xrefs

- `0x18000aeed`: `System\CurrentControlSet\Services\RemoteAccess\Authentication`

## pseudocode

```c
__int64 __fastcall GetSdoNameFromRegistry(BSTR *a1)
{
  OLECHAR *v2; // rdi
  LSTATUS StringValue; // ebx
  BSTR v4; // rax
  HANDLE ProcessHeap; // rax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  OLECHAR *psz; // [rsp+50h] [rbp+18h]

  hKey = 0;
  v2 = 0;
  psz = 0;
  StringValue = RegOpenKeyExW(
                  HKEY_LOCAL_MACHINE,
                  L"System\\CurrentControlSet\\Services\\RemoteAccess\\Authentication",
                  0,
                  0x20019u,
                  &hKey);
  if ( !StringValue )
  {
    StringValue = QueryStringValue(hKey, L"CRPName");
    v2 = psz;
    if ( !StringValue )
    {
      v4 = SysAllocString(psz);
      *a1 = v4;
      if ( !v4 )
        StringValue = 14;
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  if ( StringValue > 0 )
    return (unsigned __int16)StringValue | 0x80070000;
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x18000aeb4  mov     r11, rsp
0x18000aeb7  mov     [r11+8], rbx
0x18000aebb  mov     [r11+20h], rsi
0x18000aebf  push    rdi
0x18000aec0  sub     rsp, 30h
0x18000aec4  mov     rsi, rcx
0x18000aec7  mov     qword ptr [r11+10h], 0
0x18000aecf  lea     rax, [r11+10h]
0x18000aed3  xor     edi, edi
0x18000aed5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000aedc  mov     [r11+18h], rdi
0x18000aee0  mov     r9d, 20019h; samDesired
0x18000aee6  mov     [r11-18h], rax
0x18000aeea  xor     r8d, r8d; ulOptions
0x18000aeed  lea     rdx, c_szRegKeyAuthentication; "System\\CurrentControlSet\\Services\\Re"...
0x18000aef4  call    cs:__imp_RegOpenKeyExW
0x18000aefa  mov     ebx, eax
0x18000aefc  test    eax, eax
0x18000aefe  jnz     short loc_18000AF36
0x18000af00  mov     rcx, [rsp+38h+hKey]; hKey
0x18000af05  lea     r8, [rsp+38h+psz]
0x18000af0a  lea     rdx, c_szRegValSdoCrpName; "CRPName"
0x18000af11  call    QueryStringValue
0x18000af16  mov     ebx, eax
0x18000af18  mov     rdi, [rsp+38h+psz]
0x18000af1d  test    eax, eax
0x18000af1f  jnz     short loc_18000AF36
0x18000af21  mov     rcx, rdi; psz
0x18000af24  call    cs:__imp_SysAllocString
0x18000af2a  test    rax, rax
0x18000af2d  mov     [rsi], rax
0x18000af30  lea     ecx, [rbx+0Eh]
0x18000af33  cmovz   ebx, ecx
0x18000af36  mov     rcx, [rsp+38h+hKey]; hKey
0x18000af3b  test    rcx, rcx
0x18000af3e  jz      short loc_18000AF4F
0x18000af40  call    cs:__imp_RegCloseKey
0x18000af46  mov     [rsp+38h+hKey], 0
0x18000af4f  test    rdi, rdi
0x18000af52  jz      short loc_18000AF68
0x18000af54  call    cs:__imp_GetProcessHeap
0x18000af5a  mov     r8, rdi; lpMem
0x18000af5d  xor     edx, edx; dwFlags
0x18000af5f  mov     rcx, rax; hHeap
0x18000af62  call    cs:__imp_HeapFree
0x18000af68  test    ebx, ebx
0x18000af6a  jle     short loc_18000AF75
0x18000af6c  movzx   ebx, bx
0x18000af6f  or      ebx, 80070000h
0x18000af75  mov     rsi, [rsp+38h+arg_18]
0x18000af7a  mov     eax, ebx
0x18000af7c  mov     rbx, [rsp+38h+arg_0]
0x18000af81  add     rsp, 30h
0x18000af85  pop     rdi
0x18000af86  retn
```
