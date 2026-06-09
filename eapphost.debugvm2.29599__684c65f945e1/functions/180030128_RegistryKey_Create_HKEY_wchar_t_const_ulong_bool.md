# RegistryKey::Create(HKEY__ *,wchar_t const *,ulong,bool)

- ea: `0x180030128`
- end: `0x1800301f4`
- name: `?Create@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK_N@Z`
- size: `204`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001b698`
- `0x180030080`

## callees

- `0x18002edf4`
- `0x1800300fc`
- `0x180030128`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030199`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180030199`

## string_xrefs

- `0x1800301af`: `RegCreateKeyExW`

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
0x180030128  mov     rax, rsp
0x18003012b  mov     [rax+8], rbx
0x18003012f  mov     [rax+10h], rsi
0x180030133  push    rdi
0x180030134  sub     rsp, 60h
0x180030138  mov     esi, r9d
0x18003013b  mov     r10, r8
0x18003013e  mov     r11, rdx
0x180030141  mov     rdi, rcx
0x180030144  mov     qword ptr [rax-18h], 0
0x18003014c  mov     dword ptr [rax-10h], 1
0x180030153  mov     dword ptr [rax+28h], 0
0x18003015a  mov     eax, r9d
0x18003015d  bts     eax, 8
0x180030161  lea     rcx, [rsp+68h+dwDisposition]
0x180030169  mov     [rsp+68h+lpdwDisposition], rcx; lpdwDisposition
0x18003016e  lea     rcx, [rsp+68h+var_18]
0x180030173  mov     [rsp+68h+phkResult], rcx; phkResult
0x180030178  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180030181  mov     [rsp+68h+samDesired], eax; samDesired
0x180030185  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18003018d  xor     r9d, r9d; lpClass
0x180030190  xor     r8d, r8d; Reserved
0x180030193  mov     rdx, r10; lpSubKey
0x180030196  mov     rcx, r11; hKey
0x180030199  call    cs:__imp_RegCreateKeyExW
0x18003019f  test    eax, eax
0x1800301a1  jz      short loc_1800301BC
0x1800301a3  jle     short loc_1800301AD
0x1800301a5  movzx   eax, ax
0x1800301a8  or      eax, 80070000h
0x1800301ad  mov     edx, eax; int
0x1800301af  lea     rcx, aRegcreatekeyex; "RegCreateKeyExW"
0x1800301b6  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x1800301bc  mov     rbx, [rsp+68h+var_18]
0x1800301c1  mov     [rsp+68h+var_18], 0
0x1800301ca  mov     rcx, rdi; this
0x1800301cd  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x1800301d2  mov     [rdi], rbx
0x1800301d5  mov     [rdi+8], esi
0x1800301d8  lea     rcx, [rsp+68h+var_18]; this
0x1800301dd  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x1800301e2  xor     eax, eax
0x1800301e4  mov     rbx, [rsp+68h+arg_0]
0x1800301e9  mov     rsi, [rsp+68h+arg_8]
0x1800301ee  add     rsp, 60h
0x1800301f2  pop     rdi
0x1800301f3  retn
```
