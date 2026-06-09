# RegistryKey::QueryValue(wchar_t const *,uint &,TempBuffer<0> &,uint)

- ea: `0x18003152c`
- end: `0x180031655`
- name: `?QueryValue@RegistryKey@@QEBA?AW4ResultType@ResultValue@1@PEB_WAEAIAEAV?$TempBuffer@$0A@@@I@Z`
- size: `297`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800314c4`
- `0x18003165c`

## callees

- `0x180002af0`
- `0x18002fef4`
- `0x180030c84`
- `0x180030f54`
- `0x18003152c`
- `0x1800318cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800315b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800315b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RegistryKey::QueryValue(HKEY *a1, const WCHAR *a2, DWORD *a3, __int64 a4)
{
  DWORD v8; // eax
  int v9; // eax
  unsigned int v10; // ebx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type[3]; // [rsp+34h] [rbp-CCh] BYREF
  LPBYTE lpData[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v15; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v16; // [rsp+250h] [rbp+150h]

  lpData[0] = (LPBYTE)&v15;
  v8 = 512;
  lpData[1] = (LPBYTE)512;
  v16 = 0;
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
      v10 = 1;
      goto LABEL_11;
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
      v10 = 4;
LABEL_11:
      TempBuffer<520>::Destroy(lpData);
      return v10;
    }
  }
  TempBuffer<0>::Assign(a4, cbData, lpData[0]);
  *a3 = Type[0];
  TempBuffer<520>::Destroy(lpData);
  return 0;
}

```

## disassembly

```asm
0x18003152c  push    rbp
0x18003152e  push    rbx
0x18003152f  push    rsi
0x180031530  push    rdi
0x180031531  push    r14
0x180031533  lea     rbp, [rsp-170h]
0x18003153b  sub     rsp, 270h
0x180031542  mov     rax, cs:__security_cookie
0x180031549  xor     rax, rsp
0x18003154c  mov     [rbp+190h+var_30], rax
0x180031553  mov     rdi, r9
0x180031556  mov     rbx, r8
0x180031559  mov     r14, rdx
0x18003155c  mov     rsi, rcx
0x18003155f  lea     rax, [rsp+290h+var_240]
0x180031564  mov     [rsp+290h+var_250], rax
0x180031569  mov     eax, 200h
0x18003156e  mov     [rsp+290h+var_248], rax
0x180031573  mov     [rbp+190h+var_40], 0
0x18003157e  mov     [rsp+290h+cbData], eax
0x180031582  mov     [rsp+290h+Type], 0
0x18003158a  mov     edx, eax
0x18003158c  lea     rcx, [rsp+290h+var_250]
0x180031591  call    ?Reserve@?$PodVector@E$0?0@@QEAAX_K@Z; PodVector<uchar,-1>::Reserve(unsigned __int64)
0x180031596  mov     rax, [rsp+290h+var_250]
0x18003159b  lea     rcx, [rsp+290h+cbData]
0x1800315a0  mov     [rsp+290h+lpcbData], rcx; lpcbData
0x1800315a5  mov     [rsp+290h+lpData], rax; lpData
0x1800315aa  lea     r9, [rsp+290h+Type]; lpType
0x1800315af  xor     r8d, r8d; lpReserved
0x1800315b2  mov     rdx, r14; lpValueName
0x1800315b5  mov     rcx, [rsi]; hKey
0x1800315b8  call    cs:__imp_RegQueryValueExW
0x1800315bf  nop     dword ptr [rax+rax+00h]
0x1800315c4  test    eax, eax
0x1800315c6  jz      short loc_180031614
0x1800315c8  cmp     eax, 2
0x1800315cb  jz      short loc_180031601
0x1800315cd  cmp     eax, 0EAh
0x1800315d2  jnz     short loc_1800315E6
0x1800315d4  mov     eax, [rsp+290h+cbData]
0x1800315d8  cmp     eax, 0FFFh
0x1800315dd  jbe     short loc_18003158A
0x1800315df  mov     ebx, 4
0x1800315e4  jmp     short loc_180031606
0x1800315e6  test    eax, eax
0x1800315e8  jle     short loc_1800315F2
0x1800315ea  movzx   eax, ax
0x1800315ed  or      eax, 80070000h
0x1800315f2  mov     edx, eax; int
0x1800315f4  lea     rcx, aRegqueryvaluee; "RegQueryValueExW"
0x1800315fb  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x180031601  mov     ebx, 1
0x180031606  lea     rcx, [rsp+290h+var_250]
0x18003160b  call    ?Destroy@?$TempBuffer@$0CAI@@@AEAAXXZ; TempBuffer<520>::Destroy(void)
0x180031610  mov     eax, ebx
0x180031612  jmp     short loc_180031637
0x180031614  mov     edx, [rsp+290h+cbData]
0x180031618  mov     r8, [rsp+290h+var_250]
0x18003161d  mov     rcx, rdi
0x180031620  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x180031625  mov     eax, [rsp+290h+Type]
0x180031629  mov     [rbx], eax
0x18003162b  lea     rcx, [rsp+290h+var_250]
0x180031630  call    ?Destroy@?$TempBuffer@$0CAI@@@AEAAXXZ; TempBuffer<520>::Destroy(void)
0x180031635  xor     eax, eax
0x180031637  mov     rcx, [rbp+190h+var_30]
0x18003163e  xor     rcx, rsp; StackCookie
0x180031641  call    __security_check_cookie
0x180031646  add     rsp, 270h
0x18003164d  pop     r14
0x18003164f  pop     rdi
0x180031650  pop     rsi
0x180031651  pop     rbx
0x180031652  pop     rbp
0x180031653  retn
```
