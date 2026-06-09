# CSimpleRegWrapper::RegistryKey::EnumBlobValues(ulong,SString *,SBuffer *)

- ea: `0x180018b90`
- end: `0x180018d63`
- name: `?EnumBlobValues@RegistryKey@CSimpleRegWrapper@@UEAA_NKPEAVSString@@PEAVSBuffer@@@Z`
- size: `467`
- prototype: `bool __fastcall(HKEY *this, DWORD, struct SString *, void **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180001da0`
- `0x180018b90`
- `0x180030ab8`
- `0x18003303c`
- `0x180034fd4`
- `0x1800350c4`
- `0x18003dc30`
- `0x18003f263`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x180018c0f`
- `ADVAPI32!RegEnumValueW` at `0x180018ce0`
- `ADVAPI32!RegEnumValueW` at `0x180018c0f`
- `ADVAPI32!RegEnumValueW` at `0x180018ce0`

## string_xrefs

- `0x180018d43`: `Consistency error: registry key is of wrong type`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
bool __fastcall CSimpleRegWrapper::RegistryKey::EnumBlobValues(HKEY *this, DWORD a2, struct SString *a3, void **a4)
{
  LSTATUS v8; // eax
  LSTATUS v9; // edi
  size_t v10; // r14
  DWORD v11; // edi
  BYTE *lpData; // rax
  __int64 v13; // rdx
  unsigned int v15; // ecx
  const struct SString *v16; // rax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v20[32]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ValueName[264]; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[528]; // [rsp+280h] [rbp+180h] BYREF

  Type = 0;
  cchValueName = 260;
  cbData = 522;
  v8 = RegEnumValueW(this[2], a2, ValueName, &cchValueName, 0, &Type, Data, &cbData);
  v9 = v8;
  if ( !v8 )
  {
    v10 = cbData;
    if ( cbData > *((_DWORD *)a4 + 1) )
      SBuffer::ReallocateBuffer(a4, cbData, 1);
    *(_DWORD *)a4 = v10;
    if ( ((_BYTE)a4[1] & 0x10) != 0 )
      SBuffer::ReallocateBuffer(a4, *((unsigned int *)a4 + 1), 1);
    memcpy_0(a4[2], Data, v10);
LABEL_13:
    SString::Set(a3, ValueName);
    if ( Type != 3 )
    {
      v16 = (const struct SString *)SString::SString(v20, v13, L"Consistency error: registry key is of wrong type");
      ThrowHR(-2147418113, v16);
    }
    return v9 == 0;
  }
  if ( v8 == 234 )
  {
    v11 = cbData;
    if ( cbData > *((_DWORD *)a4 + 1) )
      SBuffer::ReallocateBuffer(a4, cbData, 1);
    *(_DWORD *)a4 = v11;
    if ( ((_BYTE)a4[1] & 0x10) != 0 )
      SBuffer::ReallocateBuffer(a4, *((unsigned int *)a4 + 1), 1);
    lpData = (BYTE *)a4[2];
    cchValueName = 260;
    v9 = RegEnumValueW(this[2], a2, ValueName, &cchValueName, 0, &Type, lpData, &cbData);
    if ( !v9 )
      goto LABEL_13;
  }
  if ( v9 != 259 )
  {
    v15 = (unsigned __int16)v9 | 0x80070000;
    if ( v9 <= 0 )
      v15 = v9;
    ThrowHR(v15);
  }
  return v9 == 0;
}

```

## disassembly

```asm
0x180018b90  push    rbp
0x180018b92  push    rbx
0x180018b93  push    rdi
0x180018b94  push    r12
0x180018b96  push    r14
0x180018b98  push    r15
0x180018b9a  lea     rbp, [rsp-3A8h]
0x180018ba2  sub     rsp, 4A8h
0x180018ba9  mov     rax, cs:__security_cookie
0x180018bb0  xor     rax, rsp
0x180018bb3  mov     [rbp+3D0h+var_40], rax
0x180018bba  mov     rbx, r9
0x180018bbd  mov     r12, r8
0x180018bc0  mov     r15d, edx
0x180018bc3  mov     r14, rcx
0x180018bc6  and     [rsp+4D0h+Type], 0
0x180018bcb  mov     [rsp+4D0h+cchValueName], 104h
0x180018bd3  mov     [rsp+4D0h+cbData], 20Ah
0x180018bdb  lea     rax, [rsp+4D0h+cbData]
0x180018be0  mov     [rsp+4D0h+lpcbData], rax; lpcbData
0x180018be5  lea     rax, [rbp+3D0h+Data]
0x180018bec  mov     [rsp+4D0h+lpData], rax; lpData
0x180018bf1  lea     rax, [rsp+4D0h+Type]
0x180018bf6  mov     [rsp+4D0h+lpType], rax; lpType
0x180018bfb  and     [rsp+4D0h+var_4B0], 0
0x180018c01  lea     r9, [rsp+4D0h+cchValueName]; lpcchValueName
0x180018c06  lea     r8, [rsp+4D0h+ValueName]; lpValueName
0x180018c0b  mov     rcx, [rcx+10h]; hKey
0x180018c0f  call    cs:__imp_RegEnumValueW
0x180018c15  mov     edi, eax
0x180018c17  test    eax, eax
0x180018c19  jnz     short loc_180018C67
0x180018c1b  mov     r14d, [rsp+4D0h+cbData]
0x180018c20  cmp     r14d, [rbx+4]
0x180018c24  jbe     short loc_180018C35
0x180018c26  lea     r8d, [rax+1]
0x180018c2a  mov     edx, r14d
0x180018c2d  mov     rcx, rbx
0x180018c30  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x180018c35  mov     [rbx], r14d
0x180018c38  test    byte ptr [rbx+8], 10h
0x180018c3c  jz      short loc_180018C4F
0x180018c3e  mov     r8d, 1
0x180018c44  mov     edx, [rbx+4]
0x180018c47  mov     rcx, rbx
0x180018c4a  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x180018c4f  mov     r8, r14; Size
0x180018c52  lea     rdx, [rbp+3D0h+Data]; Src
0x180018c59  mov     rcx, [rbx+10h]; void *
0x180018c5d  call    memcpy_0
0x180018c62  jmp     loc_180018CEC
0x180018c67  cmp     eax, 0EAh
0x180018c6c  jnz     loc_180018D02
0x180018c72  mov     edi, [rsp+4D0h+cbData]
0x180018c76  cmp     edi, [rbx+4]
0x180018c79  jbe     short loc_180018C8B
0x180018c7b  mov     r8d, 1
0x180018c81  mov     edx, edi
0x180018c83  mov     rcx, rbx
0x180018c86  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x180018c8b  mov     [rbx], edi
0x180018c8d  test    byte ptr [rbx+8], 10h
0x180018c91  jz      short loc_180018CA4
0x180018c93  mov     r8d, 1
0x180018c99  mov     edx, [rbx+4]
0x180018c9c  mov     rcx, rbx
0x180018c9f  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x180018ca4  mov     rax, [rbx+10h]
0x180018ca8  mov     [rsp+4D0h+cchValueName], 104h
0x180018cb0  lea     rcx, [rsp+4D0h+cbData]
0x180018cb5  mov     [rsp+4D0h+lpcbData], rcx; lpcbData
0x180018cba  mov     [rsp+4D0h+lpData], rax; lpData
0x180018cbf  lea     rax, [rsp+4D0h+Type]
0x180018cc4  mov     [rsp+4D0h+lpType], rax; lpType
0x180018cc9  and     [rsp+4D0h+var_4B0], 0
0x180018ccf  lea     r9, [rsp+4D0h+cchValueName]; lpcchValueName
0x180018cd4  lea     r8, [rsp+4D0h+ValueName]; lpValueName
0x180018cd9  mov     edx, r15d; dwIndex
0x180018cdc  mov     rcx, [r14+10h]; hKey
0x180018ce0  call    cs:__imp_RegEnumValueW
0x180018ce6  mov     edi, eax
0x180018ce8  test    eax, eax
0x180018cea  jnz     short loc_180018D02
0x180018cec  lea     rdx, [rsp+4D0h+ValueName]; unsigned __int16 *
0x180018cf1  mov     rcx, r12; this
0x180018cf4  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180018cf9  cmp     [rsp+4D0h+Type], 3
0x180018cfe  jnz     short loc_180018D43
0x180018d00  jmp     short loc_180018D0A
0x180018d02  cmp     edi, 103h
0x180018d08  jnz     short loc_180018D2F
0x180018d0a  test    edi, edi
0x180018d0c  setz    al
0x180018d0f  mov     rcx, [rbp+3D0h+var_40]
0x180018d16  xor     rcx, rsp; StackCookie
0x180018d19  call    __security_check_cookie
0x180018d1e  add     rsp, 4A8h
0x180018d25  pop     r15
0x180018d27  pop     r14
0x180018d29  pop     r12
0x180018d2b  pop     rdi
0x180018d2c  pop     rbx
0x180018d2d  pop     rbp
0x180018d2e  retn
0x180018d2f  movzx   ecx, di
0x180018d32  or      ecx, 80070000h
0x180018d38  test    edi, edi
0x180018d3a  cmovle  ecx, edi; int
0x180018d3d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180018d43  lea     r8, aConsistencyErr_1; "Consistency error: registry key is of w"...
0x180018d4a  lea     rcx, [rsp+4D0h+var_480]
0x180018d4f  call    ??0SString@@QEAA@W4tagLiteral@0@PEBG@Z; SString::SString(SString::tagLiteral,ushort const *)
0x180018d54  nop
0x180018d55  mov     rdx, rax; struct SString *
0x180018d58  mov     ecx, 8000FFFFh; int
0x180018d5d  call    ?ThrowHR@@YAXJAEBVSString@@@Z; ThrowHR(long,SString const &)
```
