# AslRegistryGetUInt32_UStr

- ea: `0x140012e54`
- end: `0x140012f3b`
- name: `AslRegistryGetUInt32_UStr`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140012dd0`

## callees

- `0x140001ba0`
- `0x140012e54`
- `0x1400151b0`

## import_xrefs

- `ntdll!ZwQueryValueKey` at `0x140012eac`
- `ntdll!ZwQueryValueKey` at `0x140012eac`

## string_xrefs

- `0x140012ed0`: `AslRegistryGetUInt32_UStr`
- `0x140012f08`: `AslRegistryGetUInt32_UStr`

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
0x140012e54  mov     r11, rsp
0x140012e57  mov     [r11+20h], rbx
0x140012e5b  push    rdi
0x140012e5c  sub     rsp, 60h
0x140012e60  mov     rax, cs:__security_cookie
0x140012e67  xor     rax, rsp
0x140012e6a  mov     [rsp+68h+var_18], rax
0x140012e6f  mov     rdi, rcx
0x140012e72  lea     r9, [r11-30h]; KeyValueInformation
0x140012e76  xor     ecx, ecx
0x140012e78  mov     r10, r8
0x140012e7b  mov     [rsp+68h+var_20], ecx
0x140012e7f  mov     rax, rdx
0x140012e82  mov     [rsp+68h+var_38], ecx
0x140012e86  xorps   xmm0, xmm0
0x140012e89  mov     [rdi], ecx
0x140012e8b  mov     r8d, 2; KeyValueInformationClass
0x140012e91  lea     rcx, [r11-38h]
0x140012e95  mov     rdx, r10; ValueName
0x140012e98  mov     [r11-40h], rcx
0x140012e9c  mov     rcx, rax; KeyHandle
0x140012e9f  movups  [rsp+68h+var_30], xmm0
0x140012ea4  mov     [rsp+68h+Length], 14h; Length
0x140012eac  call    cs:__imp_ZwQueryValueKey
0x140012eb2  mov     ebx, eax
0x140012eb4  test    eax, eax
0x140012eb6  jns     short loc_140012EE3
0x140012eb8  cmp     eax, 0C0000034h
0x140012ebd  jz      short loc_140012F1E
0x140012ebf  lea     r9, aFailedToQueryK; "Failed to query key value [%x]"
0x140012ec6  mov     [rsp+68h+Length], eax
0x140012eca  mov     r8d, 443h
0x140012ed0  lea     rdx, aAslregistryget_0; "AslRegistryGetUInt32_UStr"
0x140012ed7  mov     ecx, 1
0x140012edc  call    AslLogCallPrintf
0x140012ee1  jmp     short loc_140012F1E
0x140012ee3  cmp     dword ptr [rsp+68h+var_30+4], 4
0x140012ee8  jnz     short loc_140012EFB
0x140012eea  cmp     dword ptr [rsp+68h+var_30+8], 4
0x140012eef  jnz     short loc_140012EFB
0x140012ef1  mov     eax, dword ptr [rsp+68h+var_30+0Ch]
0x140012ef5  xor     ebx, ebx
0x140012ef7  mov     [rdi], eax
0x140012ef9  jmp     short loc_140012F1E
0x140012efb  lea     r9, aInvalidValueTy; "Invalid value type"
0x140012f02  mov     r8d, 44Ah
0x140012f08  lea     rdx, aAslregistryget_0; "AslRegistryGetUInt32_UStr"
0x140012f0f  mov     ecx, 1
0x140012f14  call    AslLogCallPrintf
0x140012f19  mov     ebx, 0C0000024h
0x140012f1e  mov     eax, ebx
0x140012f20  mov     rcx, [rsp+68h+var_18]
0x140012f25  xor     rcx, rsp; StackCookie
0x140012f28  call    __security_check_cookie
0x140012f2d  mov     rbx, [rsp+68h+arg_18]
0x140012f35  add     rsp, 60h
0x140012f39  pop     rdi
0x140012f3a  retn
```
