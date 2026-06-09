# AslRegistryGetUInt32_UStr

- ea: `0x18000eb90`
- end: `0x18000ec77`
- name: `AslRegistryGetUInt32_UStr`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000eb0c`

## callees

- `0x18000e240`
- `0x18000eb90`
- `0x1800191f0`

## import_xrefs

- `ntdll!ZwQueryValueKey` at `0x18000ebe8`
- `ntdll!ZwQueryValueKey` at `0x18000ebe8`

## string_xrefs

- `0x18000ec0c`: `AslRegistryGetUInt32_UStr`
- `0x18000ec44`: `AslRegistryGetUInt32_UStr`

## pseudocode

```c
__int64 __fastcall AslRegistryGetUInt32_UStr(_DWORD *a1, void *a2, struct _UNICODE_STRING *a3)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  ULONG v7; // [rsp+30h] [rbp-38h] BYREF
  __int128 v8; // [rsp+38h] [rbp-30h] BYREF
  int v9; // [rsp+48h] [rbp-20h]

  v9 = 0;
  v7 = 0;
  *a1 = 0;
  v8 = 0;
  v4 = ZwQueryValueKey(a2, a3, KeyValuePartialInformation, &v8, 0x14u, &v7);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( *(_QWORD *)((char *)&v8 + 4) == 0x400000004LL )
    {
      v5 = 0;
      *a1 = HIDWORD(v8);
    }
    else
    {
      AslLogCallPrintf(1, "AslRegistryGetUInt32_UStr", 1098, "Invalid value type");
      return (unsigned int)-1073741788;
    }
  }
  else if ( v4 != -1073741772 )
  {
    AslLogCallPrintf(1, "AslRegistryGetUInt32_UStr", 1091, "Failed to query key value [%x]", v4);
  }
  return v5;
}

```

## disassembly

```asm
0x18000eb90  mov     r11, rsp
0x18000eb93  mov     [r11+20h], rbx
0x18000eb97  push    rdi
0x18000eb98  sub     rsp, 60h
0x18000eb9c  mov     rax, cs:__security_cookie
0x18000eba3  xor     rax, rsp
0x18000eba6  mov     [rsp+68h+var_18], rax
0x18000ebab  mov     rdi, rcx
0x18000ebae  lea     r9, [r11-30h]; KeyValueInformation
0x18000ebb2  xor     ecx, ecx
0x18000ebb4  mov     r10, r8
0x18000ebb7  mov     [rsp+68h+var_20], ecx
0x18000ebbb  mov     rax, rdx
0x18000ebbe  mov     [rsp+68h+var_38], ecx
0x18000ebc2  xorps   xmm0, xmm0
0x18000ebc5  mov     [rdi], ecx
0x18000ebc7  mov     r8d, 2; KeyValueInformationClass
0x18000ebcd  lea     rcx, [r11-38h]
0x18000ebd1  mov     rdx, r10; ValueName
0x18000ebd4  mov     [r11-40h], rcx
0x18000ebd8  mov     rcx, rax; KeyHandle
0x18000ebdb  movups  [rsp+68h+var_30], xmm0
0x18000ebe0  mov     [rsp+68h+Length], 14h; Length
0x18000ebe8  call    cs:__imp_ZwQueryValueKey
0x18000ebee  mov     ebx, eax
0x18000ebf0  test    eax, eax
0x18000ebf2  jns     short loc_18000EC1F
0x18000ebf4  cmp     eax, 0C0000034h
0x18000ebf9  jz      short loc_18000EC5A
0x18000ebfb  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x18000ec02  mov     [rsp+68h+Length], eax
0x18000ec06  mov     r8d, 443h
0x18000ec0c  lea     rdx, aAslregistryget_0; "AslRegistryGetUInt32_UStr"
0x18000ec13  mov     ecx, 1
0x18000ec18  call    AslLogCallPrintf
0x18000ec1d  jmp     short loc_18000EC5A
0x18000ec1f  cmp     dword ptr [rsp+68h+var_30+4], 4
0x18000ec24  jnz     short loc_18000EC37
0x18000ec26  cmp     dword ptr [rsp+68h+var_30+8], 4
0x18000ec2b  jnz     short loc_18000EC37
0x18000ec2d  mov     eax, dword ptr [rsp+68h+var_30+0Ch]
0x18000ec31  xor     ebx, ebx
0x18000ec33  mov     [rdi], eax
0x18000ec35  jmp     short loc_18000EC5A
0x18000ec37  lea     r9, aInvalidValueTy; "Invalid value type"
0x18000ec3e  mov     r8d, 44Ah
0x18000ec44  lea     rdx, aAslregistryget_0; "AslRegistryGetUInt32_UStr"
0x18000ec4b  mov     ecx, 1
0x18000ec50  call    AslLogCallPrintf
0x18000ec55  mov     ebx, 0C0000024h
0x18000ec5a  mov     eax, ebx
0x18000ec5c  mov     rcx, [rsp+68h+var_18]
0x18000ec61  xor     rcx, rsp; StackCookie
0x18000ec64  call    __security_check_cookie
0x18000ec69  mov     rbx, [rsp+68h+arg_18]
0x18000ec71  add     rsp, 60h
0x18000ec75  pop     rdi
0x18000ec76  retn
```
