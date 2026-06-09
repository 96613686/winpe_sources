# EEDBManager::CreateEnrollment(Enrollment *,BeginScopeInfoTag *,EnrollmentEnrollType)

- ea: `0x18003df5c`
- end: `0x18003e033`
- name: `?CreateEnrollment@EEDBManager@@QEAAJPEAVEnrollment@@PEAUBeginScopeInfoTag@@W4EnrollmentEnrollType@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034824`

## callees

- `0x1800071c0`
- `0x18003df5c`
- `0x18003e570`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dffb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003dffb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e01e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e01e`

## pseudocode

```c
__int64 __fastcall EEDBManager::CreateEnrollment(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  signed int v7; // ebx
  __int64 v8; // rcx
  LSTATUS v9; // eax
  __int128 v11; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v12; // [rsp+60h] [rbp+8h] BYREF
  int v13; // [rsp+64h] [rbp+Ch]
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  v13 = HIDWORD(a1);
  hKey = 0;
  v12 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a2 + 56LL))(a2, &v12);
  if ( v7 >= 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v11 = *(_OWORD *)(a2 + 28);
    v7 = EEDBManager::CreateEnrollmentCommon(v8, &v11, v12, a4, &hKey);
    if ( v7 >= 0 )
    {
      v9 = RegSetValueExW(hKey, L"Altitude", 0, 4u, (const BYTE *)(a3 + 4), 4u);
      if ( v9 )
      {
        if ( v9 > 0 )
          v7 = (unsigned __int16)v9 | 0x80070000;
        else
          v7 = v9;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003df5c  mov     rax, rsp
0x18003df5f  mov     [rax+18h], rbx
0x18003df63  mov     [rax+8], rcx
0x18003df67  push    rbp
0x18003df68  push    rsi
0x18003df69  push    rdi
0x18003df6a  sub     rsp, 40h
0x18003df6e  mov     ebp, r9d
0x18003df71  mov     rsi, r8
0x18003df74  mov     rdi, rdx
0x18003df77  mov     qword ptr [rax+10h], 0
0x18003df7f  mov     dword ptr [rax+8], 0
0x18003df86  mov     rax, [rdx]
0x18003df89  lea     rdx, [rsp+58h+arg_0]
0x18003df8e  mov     rcx, rdi
0x18003df91  mov     rax, [rax+38h]
0x18003df95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003df9a  mov     ebx, eax
0x18003df9c  test    eax, eax
0x18003df9e  js      short loc_18003E014
0x18003dfa0  xor     edx, edx
0x18003dfa2  lea     rcx, [rsp+58h+hKey]
0x18003dfa7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003dfac  movups  xmm0, xmmword ptr [rdi+1Ch]
0x18003dfb0  movdqu  [rsp+58h+var_28], xmm0
0x18003dfb6  lea     rax, [rsp+58h+hKey]
0x18003dfbb  mov     [rsp+58h+lpData], rax
0x18003dfc0  mov     r9d, ebp
0x18003dfc3  mov     r8d, [rsp+58h+arg_0]
0x18003dfc8  lea     rdx, [rsp+58h+var_28]
0x18003dfcd  call    ?CreateEnrollmentCommon@EEDBManager@@AEAAJU_GUID@@W4EnrollmentStateTag@@W4EnrollmentEnrollType@@PEAPEAUHKEY__@@@Z; EEDBManager::CreateEnrollmentCommon(_GUID,EnrollmentStateTag,EnrollmentEnrollType,HKEY__ * *)
0x18003dfd2  mov     ebx, eax
0x18003dfd4  test    eax, eax
0x18003dfd6  js      short loc_18003E014
0x18003dfd8  lea     rax, [rsi+4]
0x18003dfdc  mov     r9d, 4; dwType
0x18003dfe2  mov     [rsp+58h+cbData], r9d; cbData
0x18003dfe7  mov     [rsp+58h+lpData], rax; lpData
0x18003dfec  xor     r8d, r8d; Reserved
0x18003dfef  lea     rdx, aAltitude; "Altitude"
0x18003dff6  mov     rcx, [rsp+58h+hKey]; hKey
0x18003dffb  call    cs:__imp_RegSetValueExW
0x18003e001  test    eax, eax
0x18003e003  jz      short loc_18003E014
0x18003e005  jg      short loc_18003E00B
0x18003e007  mov     ebx, eax
0x18003e009  jmp     short loc_18003E014
0x18003e00b  movzx   ebx, ax
0x18003e00e  or      ebx, 80070000h
0x18003e014  mov     rcx, [rsp+58h+hKey]; hKey
0x18003e019  test    rcx, rcx
0x18003e01c  jz      short loc_18003E024
0x18003e01e  call    cs:__imp_RegCloseKey
0x18003e024  mov     eax, ebx
0x18003e026  mov     rbx, [rsp+58h+arg_10]
0x18003e02b  add     rsp, 40h
0x18003e02f  pop     rdi
0x18003e030  pop     rsi
0x18003e031  pop     rbp
0x18003e032  retn
```
