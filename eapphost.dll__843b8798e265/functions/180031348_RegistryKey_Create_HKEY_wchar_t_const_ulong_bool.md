# RegistryKey::Create(HKEY__ *,wchar_t const *,ulong,bool)

- ea: `0x180031348`
- end: `0x18003141b`
- name: `?Create@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK_N@Z`
- size: `211`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001c0a8`
- `0x180031294`

## callees

- `0x18002fef4`
- `0x180031314`
- `0x180031348`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800313b9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800313b9`

## string_xrefs

- `0x1800313d5`: `RegCreateKeyExW`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegistryKey::Create(RegistryKey *a1, HKEY a2, const WCHAR *a3, int a4, DWORD dwDisposition)
{
  int v7; // eax
  HKEY v8; // rbx
  HKEY phkResult; // [rsp+50h] [rbp-18h] BYREF
  int v11; // [rsp+58h] [rbp-10h]

  phkResult = 0;
  v11 = 1;
  dwDisposition = 0;
  v7 = RegCreateKeyExW(a2, a3, 0, 0, 0, a4 | 0x100, 0, &phkResult, &dwDisposition);
  if ( v7 )
  {
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    SystemError::ThrowHelper(L"RegCreateKeyExW", v7);
  }
  v8 = phkResult;
  phkResult = 0;
  RegistryKey::Clear(a1);
  *(_QWORD *)a1 = v8;
  *((_DWORD *)a1 + 2) = a4;
  RegistryKey::Clear((RegistryKey *)&phkResult);
  return 0;
}

```

## disassembly

```asm
0x180031348  mov     rax, rsp
0x18003134b  mov     [rax+8], rbx
0x18003134f  mov     [rax+10h], rsi
0x180031353  push    rdi
0x180031354  sub     rsp, 60h
0x180031358  mov     esi, r9d
0x18003135b  mov     r10, r8
0x18003135e  mov     r11, rdx
0x180031361  mov     rdi, rcx
0x180031364  mov     qword ptr [rax-18h], 0
0x18003136c  mov     dword ptr [rax-10h], 1
0x180031373  mov     dword ptr [rax+28h], 0
0x18003137a  mov     eax, r9d
0x18003137d  bts     eax, 8
0x180031381  lea     rcx, [rsp+68h+dwDisposition]
0x180031389  mov     [rsp+68h+lpdwDisposition], rcx; lpdwDisposition
0x18003138e  lea     rcx, [rsp+68h+var_18]
0x180031393  mov     [rsp+68h+phkResult], rcx; phkResult
0x180031398  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800313a1  mov     [rsp+68h+samDesired], eax; samDesired
0x1800313a5  mov     [rsp+68h+dwOptions], 0; dwOptions
0x1800313ad  xor     r9d, r9d; lpClass
0x1800313b0  xor     r8d, r8d; Reserved
0x1800313b3  mov     rdx, r10; lpSubKey
0x1800313b6  mov     rcx, r11; hKey
0x1800313b9  call    cs:__imp_RegCreateKeyExW
0x1800313c0  nop     dword ptr [rax+rax+00h]
0x1800313c5  test    eax, eax
0x1800313c7  jz      short loc_1800313E2
0x1800313c9  jle     short loc_1800313D3
0x1800313cb  movzx   eax, ax
0x1800313ce  or      eax, 80070000h
0x1800313d3  mov     edx, eax; int
0x1800313d5  lea     rcx, aRegcreatekeyex; "RegCreateKeyExW"
0x1800313dc  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x1800313e2  mov     rbx, [rsp+68h+var_18]
0x1800313e7  mov     [rsp+68h+var_18], 0
0x1800313f0  mov     rcx, rdi; this
0x1800313f3  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x1800313f8  mov     [rdi], rbx
0x1800313fb  mov     [rdi+8], esi
0x1800313fe  lea     rcx, [rsp+68h+var_18]; this
0x180031403  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x180031408  xor     eax, eax
0x18003140a  mov     rbx, [rsp+68h+arg_0]
0x18003140f  mov     rsi, [rsp+68h+arg_8]
0x180031414  add     rsp, 60h
0x180031418  pop     rdi
0x180031419  retn
```
