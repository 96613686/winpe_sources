# AslRegistryGetUInt32_UStr

- ea: `0x1400078bc`
- end: `0x1400079a3`
- name: `AslRegistryGetUInt32_UStr`
- size: `231`
- prototype: `__int64 __fastcall(_DWORD *, void *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140007838`

## callees

- `0x140007074`
- `0x1400078bc`
- `0x1400115f0`

## import_xrefs

- `ntdll!ZwQueryValueKey` at `0x140007914`
- `ntdll!ZwQueryValueKey` at `0x140007914`

## string_xrefs

- `0x140007938`: `AslRegistryGetUInt32_UStr`
- `0x140007970`: `AslRegistryGetUInt32_UStr`

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
0x1400078bc  mov     r11, rsp
0x1400078bf  mov     [r11+20h], rbx
0x1400078c3  push    rdi
0x1400078c4  sub     rsp, 60h
0x1400078c8  mov     rax, cs:__security_cookie
0x1400078cf  xor     rax, rsp
0x1400078d2  mov     [rsp+68h+var_18], rax
0x1400078d7  mov     rdi, rcx
0x1400078da  lea     r9, [r11-30h]; KeyValueInformation
0x1400078de  xor     ecx, ecx
0x1400078e0  mov     r10, r8
0x1400078e3  mov     [rsp+68h+var_20], ecx
0x1400078e7  mov     rax, rdx
0x1400078ea  mov     [rsp+68h+var_38], ecx
0x1400078ee  xorps   xmm0, xmm0
0x1400078f1  mov     [rdi], ecx
0x1400078f3  mov     r8d, 2; KeyValueInformationClass
0x1400078f9  lea     rcx, [r11-38h]
0x1400078fd  mov     rdx, r10; ValueName
0x140007900  mov     [r11-40h], rcx
0x140007904  mov     rcx, rax; KeyHandle
0x140007907  movups  [rsp+68h+var_30], xmm0
0x14000790c  mov     [rsp+68h+Length], 14h; Length
0x140007914  call    cs:__imp_ZwQueryValueKey
0x14000791a  mov     ebx, eax
0x14000791c  test    eax, eax
0x14000791e  jns     short loc_14000794B
0x140007920  cmp     eax, 0C0000034h
0x140007925  jz      short loc_140007986
0x140007927  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x14000792e  mov     [rsp+68h+Length], eax
0x140007932  mov     r8d, 443h
0x140007938  lea     rdx, aAslregistryget_0; "AslRegistryGetUInt32_UStr"
0x14000793f  mov     ecx, 1
0x140007944  call    AslLogCallPrintf
0x140007949  jmp     short loc_140007986
0x14000794b  cmp     dword ptr [rsp+68h+var_30+4], 4
0x140007950  jnz     short loc_140007963
0x140007952  cmp     dword ptr [rsp+68h+var_30+8], 4
0x140007957  jnz     short loc_140007963
0x140007959  mov     eax, dword ptr [rsp+68h+var_30+0Ch]
0x14000795d  xor     ebx, ebx
0x14000795f  mov     [rdi], eax
0x140007961  jmp     short loc_140007986
0x140007963  lea     r9, aInvalidValueTy; "Invalid value type"
0x14000796a  mov     r8d, 44Ah
0x140007970  lea     rdx, aAslregistryget_0; "AslRegistryGetUInt32_UStr"
0x140007977  mov     ecx, 1
0x14000797c  call    AslLogCallPrintf
0x140007981  mov     ebx, 0C0000024h
0x140007986  mov     eax, ebx
0x140007988  mov     rcx, [rsp+68h+var_18]
0x14000798d  xor     rcx, rsp; StackCookie
0x140007990  call    __security_check_cookie
0x140007995  mov     rbx, [rsp+68h+arg_18]
0x14000799d  add     rsp, 60h
0x1400079a1  pop     rdi
0x1400079a2  retn
```
