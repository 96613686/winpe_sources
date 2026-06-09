# RegistryKey::QueryValue(wchar_t const *,uint &,TempBuffer<0> &,uint)

- ea: `0x1800302fc`
- end: `0x180030444`
- name: `?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAIAEAV?$TempBuffer@$0A@@@I@Z`
- size: `328`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180030294`
- `0x18003044c`

## callees

- `0x180002a90`
- `0x1800072cc`
- `0x18002edf4`
- `0x18002fd44`
- `0x1800302fc`
- `0x180030718`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030388`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180030388`

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
0x1800302fc  push    rbp
0x1800302fe  push    rbx
0x1800302ff  push    rsi
0x180030300  push    rdi
0x180030301  push    r14
0x180030303  lea     rbp, [rsp-170h]
0x18003030b  sub     rsp, 270h
0x180030312  mov     rax, cs:__security_cookie
0x180030319  xor     rax, rsp
0x18003031c  mov     [rbp+190h+var_30], rax
0x180030323  mov     rdi, r9
0x180030326  mov     rbx, r8
0x180030329  mov     r14, rdx
0x18003032c  mov     rsi, rcx
0x18003032f  lea     rax, [rsp+290h+var_240]
0x180030334  mov     [rsp+290h+var_250], rax
0x180030339  mov     eax, 200h
0x18003033e  mov     [rsp+290h+var_248], rax
0x180030343  mov     [rbp+190h+var_40], 0
0x18003034e  mov     [rsp+290h+cbData], eax
0x180030352  mov     [rsp+290h+Type], 0
0x18003035a  mov     edx, eax
0x18003035c  lea     rcx, [rsp+290h+var_250]
0x180030361  call    ?Reserve@?$PodVector@E$0?0@@QEAAX_K@Z; PodVector<uchar,-1>::Reserve(unsigned __int64)
0x180030366  mov     rax, [rsp+290h+var_250]
0x18003036b  lea     rcx, [rsp+290h+cbData]
0x180030370  mov     [rsp+290h+lpcbData], rcx; lpcbData
0x180030375  mov     [rsp+290h+lpData], rax; lpData
0x18003037a  lea     r9, [rsp+290h+Type]; lpType
0x18003037f  xor     r8d, r8d; lpReserved
0x180030382  mov     rdx, r14; lpValueName
0x180030385  mov     rcx, [rsi]; hKey
0x180030388  call    cs:__imp_RegQueryValueExW
0x18003038e  test    eax, eax
0x180030390  jz      short loc_1800303FA
0x180030392  cmp     eax, 2
0x180030395  jz      short loc_1800303DF
0x180030397  cmp     eax, 0EAh
0x18003039c  jnz     short loc_1800303C4
0x18003039e  mov     eax, [rsp+290h+cbData]
0x1800303a2  cmp     eax, 0FFFh
0x1800303a7  jbe     short loc_18003035A
0x1800303a9  lea     rax, [rsp+290h+var_240]
0x1800303ae  mov     rcx, [rsp+290h+var_250]; void *
0x1800303b3  cmp     rcx, rax
0x1800303b6  jz      short loc_1800303BD
0x1800303b8  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800303bd  mov     eax, 4
0x1800303c2  jmp     short loc_180030427
0x1800303c4  test    eax, eax
0x1800303c6  jle     short loc_1800303D0
0x1800303c8  movzx   eax, ax
0x1800303cb  or      eax, 80070000h
0x1800303d0  mov     edx, eax; int
0x1800303d2  lea     rcx, aRegqueryvaluee; "RegQueryValueExW"
0x1800303d9  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x1800303df  lea     rax, [rsp+290h+var_240]
0x1800303e4  mov     rcx, [rsp+290h+var_250]; void *
0x1800303e9  cmp     rcx, rax
0x1800303ec  jz      short loc_1800303F3
0x1800303ee  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800303f3  mov     eax, 1
0x1800303f8  jmp     short loc_180030427
0x1800303fa  mov     edx, [rsp+290h+cbData]
0x1800303fe  mov     r8, [rsp+290h+var_250]
0x180030403  mov     rcx, rdi
0x180030406  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18003040b  mov     eax, [rsp+290h+Type]
0x18003040f  mov     [rbx], eax
0x180030411  lea     rax, [rsp+290h+var_240]
0x180030416  mov     rcx, [rsp+290h+var_250]; void *
0x18003041b  cmp     rcx, rax
0x18003041e  jz      short loc_180030425
0x180030420  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180030425  xor     eax, eax
0x180030427  mov     rcx, [rbp+190h+var_30]
0x18003042e  xor     rcx, rsp; StackCookie
0x180030431  call    __security_check_cookie
0x180030436  add     rsp, 270h
0x18003043d  pop     r14
0x18003043f  pop     rdi
0x180030440  pop     rsi
0x180030441  pop     rbx
0x180030442  pop     rbp
0x180030443  retn
```
