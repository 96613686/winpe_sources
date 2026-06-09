# RegistryKey::QueryValue(wchar_t const *,uint &,TempBuffer<0> &,uint)

- ea: `0x18002a9dc`
- end: `0x18002ab24`
- name: `?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAIAEAV?$TempBuffer@$0A@@@I@Z`
- size: `328`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002a974`
- `0x18002ab2c`

## callees

- `0x1800017a0`
- `0x18000439c`
- `0x1800126f8`
- `0x180012a70`
- `0x18002a9dc`
- `0x18002adf8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002aa68`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002aa68`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegistryKey::QueryValue(HKEY *a1, const WCHAR *a2, DWORD *a3, __int64 a4)
{
  DWORD v8; // eax
  int v9; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type[3]; // [rsp+34h] [rbp-CCh] BYREF
  LPBYTE lpData[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[512]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v15; // [rsp+250h] [rbp+150h]

  lpData[0] = v14;
  v8 = 512;
  lpData[1] = (LPBYTE)512;
  v15 = 0;
  cbData = 512;
  Type[0] = 0;
  while ( 1 )
  {
    PodVector<unsigned char,-1>::Reserve(lpData, v8);
    v9 = RegQueryValueExW(*a1, a2, 0, Type, lpData[0], &cbData);
    if ( !v9 )
      break;
    if ( v9 == 2 )
    {
      if ( lpData[0] != v14 )
        HeapAllocator::Free(lpData[0]);
      return 1;
    }
    if ( v9 != 234 )
    {
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      SystemError::ThrowHelper(L"RegQueryValueExW", v9);
    }
    v8 = cbData;
    if ( cbData > 0xFFF )
    {
      if ( lpData[0] != v14 )
        HeapAllocator::Free(lpData[0]);
      return 4;
    }
  }
  TempBuffer<0>::Assign(a4, cbData, lpData[0]);
  *a3 = Type[0];
  if ( lpData[0] != v14 )
    HeapAllocator::Free(lpData[0]);
  return 0;
}

```

## disassembly

```asm
0x18002a9dc  push    rbp
0x18002a9de  push    rbx
0x18002a9df  push    rsi
0x18002a9e0  push    rdi
0x18002a9e1  push    r14
0x18002a9e3  lea     rbp, [rsp-170h]
0x18002a9eb  sub     rsp, 270h
0x18002a9f2  mov     rax, cs:__security_cookie
0x18002a9f9  xor     rax, rsp
0x18002a9fc  mov     [rbp+190h+var_30], rax
0x18002aa03  mov     rdi, r9
0x18002aa06  mov     rbx, r8
0x18002aa09  mov     r14, rdx
0x18002aa0c  mov     rsi, rcx
0x18002aa0f  lea     rax, [rsp+290h+var_240]
0x18002aa14  mov     [rsp+290h+var_250], rax
0x18002aa19  mov     eax, 200h
0x18002aa1e  mov     [rsp+290h+var_248], rax
0x18002aa23  mov     [rbp+190h+var_40], 0
0x18002aa2e  mov     [rsp+290h+cbData], eax
0x18002aa32  mov     [rsp+290h+Type], 0
0x18002aa3a  mov     edx, eax
0x18002aa3c  lea     rcx, [rsp+290h+var_250]
0x18002aa41  call    ?Reserve@?$PodVector@E$0?0@@QEAAX_K@Z; PodVector<uchar,-1>::Reserve(unsigned __int64)
0x18002aa46  mov     rax, [rsp+290h+var_250]
0x18002aa4b  lea     rcx, [rsp+290h+cbData]
0x18002aa50  mov     [rsp+290h+lpcbData], rcx; lpcbData
0x18002aa55  mov     [rsp+290h+lpData], rax; lpData
0x18002aa5a  lea     r9, [rsp+290h+Type]; lpType
0x18002aa5f  xor     r8d, r8d; lpReserved
0x18002aa62  mov     rdx, r14; lpValueName
0x18002aa65  mov     rcx, [rsi]; hKey
0x18002aa68  call    cs:__imp_RegQueryValueExW
0x18002aa6e  test    eax, eax
0x18002aa70  jz      short loc_18002AADA
0x18002aa72  cmp     eax, 2
0x18002aa75  jz      short loc_18002AABF
0x18002aa77  cmp     eax, 0EAh
0x18002aa7c  jnz     short loc_18002AAA4
0x18002aa7e  mov     eax, [rsp+290h+cbData]
0x18002aa82  cmp     eax, 0FFFh
0x18002aa87  jbe     short loc_18002AA3A
0x18002aa89  lea     rax, [rsp+290h+var_240]
0x18002aa8e  mov     rcx, [rsp+290h+var_250]; void *
0x18002aa93  cmp     rcx, rax
0x18002aa96  jz      short loc_18002AA9D
0x18002aa98  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002aa9d  mov     eax, 4
0x18002aaa2  jmp     short loc_18002AB07
0x18002aaa4  test    eax, eax
0x18002aaa6  jle     short loc_18002AAB0
0x18002aaa8  movzx   eax, ax
0x18002aaab  or      eax, 80070000h
0x18002aab0  mov     edx, eax; int
0x18002aab2  lea     rcx, aRegqueryvaluee; "RegQueryValueExW"
0x18002aab9  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x18002aabf  lea     rax, [rsp+290h+var_240]
0x18002aac4  mov     rcx, [rsp+290h+var_250]; void *
0x18002aac9  cmp     rcx, rax
0x18002aacc  jz      short loc_18002AAD3
0x18002aace  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002aad3  mov     eax, 1
0x18002aad8  jmp     short loc_18002AB07
0x18002aada  mov     edx, [rsp+290h+cbData]
0x18002aade  mov     r8, [rsp+290h+var_250]
0x18002aae3  mov     rcx, rdi
0x18002aae6  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18002aaeb  mov     eax, [rsp+290h+Type]
0x18002aaef  mov     [rbx], eax
0x18002aaf1  lea     rax, [rsp+290h+var_240]
0x18002aaf6  mov     rcx, [rsp+290h+var_250]; void *
0x18002aafb  cmp     rcx, rax
0x18002aafe  jz      short loc_18002AB05
0x18002ab00  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18002ab05  xor     eax, eax
0x18002ab07  mov     rcx, [rbp+190h+var_30]
0x18002ab0e  xor     rcx, rsp; StackCookie
0x18002ab11  call    __security_check_cookie
0x18002ab16  add     rsp, 270h
0x18002ab1d  pop     r14
0x18002ab1f  pop     rdi
0x18002ab20  pop     rsi
0x18002ab21  pop     rbx
0x18002ab22  pop     rbp
0x18002ab23  retn
```
