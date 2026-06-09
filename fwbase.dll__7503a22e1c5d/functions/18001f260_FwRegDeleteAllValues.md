# FwRegDeleteAllValues

- ea: `0x18001f260`
- end: `0x18001f398`
- name: `FwRegDeleteAllValues`
- size: `312`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180004750`
- `0x1800047e0`
- `0x180004840`
- `0x180012960`
- `0x180017d1c`
- `0x18001e1d0`
- `0x18001f260`
- `0x18001f3a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001f313`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001f313`

## string_xrefs

- `0x18001f2d6`: `FwRegDeleteAllValues`
- `0x18001f339`: `FwRegDeleteAllValues`
- `0x18001f34b`: `FwRegDeleteAllValues`
- `0x18001f369`: `FwRegDeleteAllValues`
- `0x18001f332`: `RegDeleteValue`

## pseudocode

```c
__int64 __fastcall FwRegDeleteAllValues(HKEY hKey)
{
  int v2; // eax
  int v3; // ebx
  DWORD cValues; // [rsp+30h] [rbp-10h] BYREF

  cValues = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ca8ecc87028c3f8cbe9deeea65f7fdbd_Traceguids);
  v2 = FwRegQueryNumValues(hKey, &cValues);
  v3 = v2;
  if ( v2 < 0 || cValues && (v2 = FwRegEnumValueName(hKey, 0), v3 = v2, v2 < 0) )
    FwReportReturnError("FwRegDeleteAllValues", (unsigned int)v2);
  FwFree(0);
  if ( v3 < 0 )
    return (unsigned int)FwReportReturnError("FwRegDeleteAllValues", (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001f260  mov     [rsp-18h+arg_8], rbx
0x18001f265  mov     [rsp-18h+arg_10], rsi
0x18001f26a  push    rbp
0x18001f26b  push    rdi
0x18001f26c  push    r14
0x18001f26e  mov     rbp, rsp
0x18001f271  sub     rsp, 40h
0x18001f275  mov     rax, cs:__security_cookie
0x18001f27c  xor     rax, rsp
0x18001f27f  mov     [rbp+var_8], rax
0x18001f283  xor     edi, edi
0x18001f285  mov     [rbp+cValues], 0
0x18001f28c  mov     [rbp+lpValueName], rdi
0x18001f290  mov     r14, rcx
0x18001f293  mov     [rbp+var_20], edi
0x18001f296  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f29d  lea     rax, WPP_GLOBAL_Control
0x18001f2a4  cmp     rcx, rax
0x18001f2a7  jz      short loc_18001F2C2
0x18001f2a9  test    byte ptr [rcx+1Ch], 8
0x18001f2ad  jz      short loc_18001F2C2
0x18001f2af  mov     rcx, [rcx+10h]
0x18001f2b3  lea     edx, [rdi+0Ch]
0x18001f2b6  lea     r8, WPP_ca8ecc87028c3f8cbe9deeea65f7fdbd_Traceguids
0x18001f2bd  call    WPP_SF_
0x18001f2c2  lea     rdx, [rbp+cValues]; lpcValues
0x18001f2c6  mov     rcx, r14; hKey
0x18001f2c9  call    FwRegQueryNumValues
0x18001f2ce  mov     ebx, eax
0x18001f2d0  test    eax, eax
0x18001f2d2  jns     short loc_18001F2E4
0x18001f2d4  mov     edx, eax
0x18001f2d6  lea     rcx, aFwregdeleteall_0; "FwRegDeleteAllValues"
0x18001f2dd  call    FwReportReturnError
0x18001f2e2  jmp     short loc_18001F35B
0x18001f2e4  xor     esi, esi
0x18001f2e6  cmp     esi, [rbp+cValues]
0x18001f2e9  jnb     short loc_18001F35B
0x18001f2eb  lea     r9, [rbp+var_20]
0x18001f2ef  xor     edx, edx; dwIndex
0x18001f2f1  lea     r8, [rbp+lpValueName]
0x18001f2f5  mov     rcx, r14; hKey
0x18001f2f8  call    FwRegEnumValueName
0x18001f2fd  mov     ebx, eax
0x18001f2ff  test    eax, eax
0x18001f301  js      short loc_18001F349
0x18001f303  cmp     [rbp+var_20], 0
0x18001f307  mov     rdi, [rbp+lpValueName]
0x18001f30b  jz      short loc_18001F35B
0x18001f30d  mov     rdx, rdi; lpValueName
0x18001f310  mov     rcx, r14; hKey
0x18001f313  call    cs:__imp_RegDeleteValueW
0x18001f319  test    eax, eax
0x18001f31b  jnz     short loc_18001F32F
0x18001f31d  mov     rcx, rdi
0x18001f320  call    FwFree
0x18001f325  xor     edi, edi
0x18001f327  mov     [rbp+lpValueName], rdi
0x18001f32b  inc     esi
0x18001f32d  jmp     short loc_18001F2E6
0x18001f32f  mov     r8d, eax
0x18001f332  lea     rdx, aRegdeletevalue; "RegDeleteValue"
0x18001f339  lea     rcx, aFwregdeleteall_0; "FwRegDeleteAllValues"
0x18001f340  call    FwReportErrorAsWinError
0x18001f345  mov     ebx, eax
0x18001f347  jmp     short loc_18001F35B
0x18001f349  mov     edx, eax
0x18001f34b  lea     rcx, aFwregdeleteall_0; "FwRegDeleteAllValues"
0x18001f352  call    FwReportReturnError
0x18001f357  mov     rdi, [rbp+lpValueName]
0x18001f35b  mov     rcx, rdi
0x18001f35e  call    FwFree
0x18001f363  test    ebx, ebx
0x18001f365  jns     short loc_18001F377
0x18001f367  mov     edx, ebx
0x18001f369  lea     rcx, aFwregdeleteall_0; "FwRegDeleteAllValues"
0x18001f370  call    FwReportReturnError
0x18001f375  mov     ebx, eax
0x18001f377  mov     eax, ebx
0x18001f379  mov     rcx, [rbp+var_8]
0x18001f37d  xor     rcx, rsp; StackCookie
0x18001f380  call    __security_check_cookie
0x18001f385  mov     rbx, [rsp+40h+arg_8]
0x18001f38a  mov     rsi, [rsp+40h+arg_10]
0x18001f38f  add     rsp, 40h
0x18001f393  pop     r14
0x18001f395  pop     rdi
0x18001f396  pop     rbp
0x18001f397  retn
```
