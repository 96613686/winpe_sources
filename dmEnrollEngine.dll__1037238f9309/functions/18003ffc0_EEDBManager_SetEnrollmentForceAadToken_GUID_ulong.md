# EEDBManager::SetEnrollmentForceAadToken(_GUID,ulong)

- ea: `0x18003ffc0`
- end: `0x180040070`
- name: `?SetEnrollmentForceAadToken@EEDBManager@@SAJU_GUID@@K@Z`
- size: `176`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180040c40`

## callees

- `0x180005cf0`
- `0x1800071c0`
- `0x18003ffc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004003a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004003a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040011`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040062`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040011`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040062`

## string_xrefs

- `0x18004002b`: `ForceAadToken`

## pseudocode

```c
__int64 __fastcall EEDBManager::SetEnrollmentForceAadToken(struct _GUID *a1, int a2)
{
  LSTATUS v3; // eax
  HKEY v4; // rcx
  unsigned int v5; // ebx
  LSTATUS v7; // eax
  struct _GUID v8; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF
  int Data; // [rsp+58h] [rbp+10h] BYREF

  Data = a2;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v8 = *a1;
  v3 = EEDBManager::OpenEnrollmentKey(&v8, 131078, 0, &hKey);
  v4 = hKey;
  v5 = v3;
  if ( v3 < 0 )
  {
LABEL_2:
    if ( v4 )
      RegCloseKey(v4);
    return v5;
  }
  v7 = RegSetValueExW(hKey, L"ForceAadToken", 0, 4u, (const BYTE *)&Data, 4u);
  v5 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    v4 = hKey;
    goto LABEL_2;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18003ffc0  mov     [rsp+Data], edx
0x18003ffc4  push    rbx
0x18003ffc5  sub     rsp, 40h
0x18003ffc9  mov     rbx, rcx
0x18003ffcc  mov     [rsp+48h+hKey], 0
0x18003ffd5  lea     rcx, [rsp+48h+hKey]
0x18003ffda  xor     edx, edx
0x18003ffdc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003ffe1  movaps  xmm0, xmmword ptr [rbx]
0x18003ffe4  lea     r9, [rsp+48h+hKey]; HKEY *
0x18003ffe9  xor     r8d, r8d; unsigned __int16 *
0x18003ffec  movdqa  xmmword ptr [rsp+48h+var_18.Data1], xmm0
0x18003fff2  mov     edx, 20006h; unsigned int
0x18003fff7  lea     rcx, [rsp+48h+var_18]; struct _GUID
0x18003fffc  call    ?OpenEnrollmentKey@EEDBManager@@CAJU_GUID@@KPEBGPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentKey(_GUID,ulong,ushort const *,HKEY__ * *)
0x180040001  mov     rcx, [rsp+48h+hKey]; hKey
0x180040006  mov     ebx, eax
0x180040008  test    eax, eax
0x18004000a  jns     short loc_18004001B
0x18004000c  test    rcx, rcx
0x18004000f  jz      short loc_180040017
0x180040011  call    cs:__imp_RegCloseKey
0x180040017  mov     eax, ebx
0x180040019  jmp     short loc_18004006A
0x18004001b  mov     r9d, 4; dwType
0x180040021  lea     rax, [rsp+48h+Data]
0x180040026  mov     [rsp+48h+cbData], r9d; cbData
0x18004002b  lea     rdx, aForceaadtoken; "ForceAadToken"
0x180040032  xor     r8d, r8d; Reserved
0x180040035  mov     [rsp+48h+lpData], rax; lpData
0x18004003a  call    cs:__imp_RegSetValueExW
0x180040040  mov     ebx, eax
0x180040042  test    eax, eax
0x180040044  jz      short loc_180040058
0x180040046  jle     short loc_180040051
0x180040048  movzx   ebx, ax
0x18004004b  or      ebx, 80070000h
0x180040051  mov     rcx, [rsp+48h+hKey]
0x180040056  jmp     short loc_18004000C
0x180040058  mov     rcx, [rsp+48h+hKey]; hKey
0x18004005d  test    rcx, rcx
0x180040060  jz      short loc_180040068
0x180040062  call    cs:__imp_RegCloseKey
0x180040068  xor     eax, eax
0x18004006a  add     rsp, 40h
0x18004006e  pop     rbx
0x18004006f  retn
```
