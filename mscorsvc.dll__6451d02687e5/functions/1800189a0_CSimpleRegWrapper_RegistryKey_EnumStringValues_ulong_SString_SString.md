# CSimpleRegWrapper::RegistryKey::EnumStringValues(ulong,SString *,SString *)

- ea: `0x1800189a0`
- end: `0x180018b83`
- name: `?EnumStringValues@RegistryKey@CSimpleRegWrapper@@UEAA_NKPEAVSString@@0@Z`
- size: `483`
- prototype: `bool __fastcall(HKEY *this, DWORD, struct SString *, BYTE **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180001da0`
- `0x1800189a0`
- `0x180030ab8`
- `0x180032f44`
- `0x18003303c`
- `0x180034fd4`
- `0x1800350c4`
- `0x18003dc30`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x180018a22`
- `ADVAPI32!RegEnumValueW` at `0x180018ae8`
- `ADVAPI32!RegEnumValueW` at `0x180018a22`
- `ADVAPI32!RegEnumValueW` at `0x180018ae8`

## string_xrefs

- `0x180018b63`: `Consistency error: registry key is of wrong type`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
bool __fastcall CSimpleRegWrapper::RegistryKey::EnumStringValues(HKEY *this, DWORD a2, struct SString *a3, BYTE **a4)
{
  LSTATUS v8; // eax
  LSTATUS v9; // ebx
  DWORD v10; // ebx
  int v11; // edx
  unsigned int v12; // ebx
  BYTE *lpData; // rax
  BYTE *v14; // rax
  __int64 v15; // rdx
  unsigned int v17; // ecx
  const struct SString *v18; // rax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  char v22[32]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ValueName[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 Data[264]; // [rsp+280h] [rbp+180h] BYREF

  Type = 0;
  cchValueName = 260;
  cbData = 522;
  v8 = RegEnumValueW(this[2], a2, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData);
  v9 = v8;
  if ( !v8 )
  {
    SString::Set((SString *)a4, Data);
LABEL_15:
    SString::Set(a3, ValueName);
    if ( Type != 1 )
    {
      v18 = (const struct SString *)SString::SString(v22, v15, L"Consistency error: registry key is of wrong type");
      ThrowHR(-2147418113, v18);
    }
    return v9 == 0;
  }
  if ( v8 == 234 )
  {
    if ( cbData )
      v10 = (cbData - 1) >> 1;
    else
      v10 = 0;
    SString::Resize(a4, v10, 4);
    v11 = *((_DWORD *)a4 + 2);
    v12 = (v10 + 1) << ((v11 & 1) == 0);
    if ( v12 > *((_DWORD *)a4 + 1) )
    {
      SBuffer::ReallocateBuffer(a4, v12, 1);
      v11 = *((_DWORD *)a4 + 2);
    }
    *(_DWORD *)a4 = v12;
    if ( (v11 & 0x10) != 0 )
      SBuffer::ReallocateBuffer(a4, *((unsigned int *)a4 + 1), 1);
    lpData = a4[2];
    cchValueName = 260;
    v9 = RegEnumValueW(this[2], a2, ValueName, &cchValueName, 0, &Type, lpData, &cbData);
    v14 = &a4[2][*(unsigned int *)a4];
    if ( ((_BYTE)a4[1] & 1) != 0 )
      *(v14 - 1) = 0;
    else
      *((_WORD *)v14 - 1) = 0;
    if ( !v9 )
      goto LABEL_15;
  }
  if ( v9 != 259 )
  {
    v17 = (unsigned __int16)v9 | 0x80070000;
    if ( v9 <= 0 )
      v17 = v9;
    ThrowHR(v17);
  }
  return v9 == 0;
}

```

## disassembly

```asm
0x1800189a0  push    rbp
0x1800189a2  push    rbx
0x1800189a3  push    rsi
0x1800189a4  push    rdi
0x1800189a5  push    r12
0x1800189a7  push    r14
0x1800189a9  push    r15
0x1800189ab  lea     rbp, [rsp-3A0h]
0x1800189b3  sub     rsp, 4A0h
0x1800189ba  mov     rax, cs:__security_cookie
0x1800189c1  xor     rax, rsp
0x1800189c4  mov     [rbp+3D0h+var_40], rax
0x1800189cb  mov     rdi, r9
0x1800189ce  mov     rsi, r8
0x1800189d1  mov     r15d, edx
0x1800189d4  mov     r14, rcx
0x1800189d7  xor     r12d, r12d
0x1800189da  mov     [rsp+4D0h+Type], r12d
0x1800189df  mov     [rsp+4D0h+cchValueName], 104h
0x1800189e7  mov     [rsp+4D0h+cbData], 20Ah
0x1800189ef  lea     rax, [rsp+4D0h+cbData]
0x1800189f4  mov     [rsp+4D0h+lpcbData], rax; lpcbData
0x1800189f9  lea     rax, [rbp+3D0h+Data]
0x180018a00  mov     [rsp+4D0h+lpData], rax; lpData
0x180018a05  lea     rax, [rsp+4D0h+Type]
0x180018a0a  mov     [rsp+4D0h+lpType], rax; lpType
0x180018a0f  mov     [rsp+4D0h+lpReserved], r12; lpReserved
0x180018a14  lea     r9, [rsp+4D0h+cchValueName]; lpcchValueName
0x180018a19  lea     r8, [rsp+4D0h+ValueName]; lpValueName
0x180018a1e  mov     rcx, [rcx+10h]; hKey
0x180018a22  call    cs:__imp_RegEnumValueW
0x180018a28  mov     ebx, eax
0x180018a2a  test    eax, eax
0x180018a2c  jnz     short loc_180018A42
0x180018a2e  lea     rdx, [rbp+3D0h+Data]; unsigned __int16 *
0x180018a35  mov     rcx, rdi; this
0x180018a38  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180018a3d  jmp     loc_180018B0B
0x180018a42  cmp     eax, 0EAh
0x180018a47  jnz     loc_180018B21
0x180018a4d  mov     ebx, [rsp+4D0h+cbData]
0x180018a51  test    ebx, ebx
0x180018a53  jnz     short loc_180018A5A
0x180018a55  mov     ebx, r12d
0x180018a58  jmp     short loc_180018A5E
0x180018a5a  dec     ebx
0x180018a5c  shr     ebx, 1
0x180018a5e  xor     r9d, r9d
0x180018a61  lea     r8d, [r9+4]
0x180018a65  mov     edx, ebx
0x180018a67  mov     rcx, rdi
0x180018a6a  call    ?Resize@SString@@AEAAXIW4Representation@1@W4Preserve@SBuffer@@@Z; SString::Resize(uint,SString::Representation,SBuffer::Preserve)
0x180018a6f  mov     edx, [rdi+8]
0x180018a72  mov     ecx, edx
0x180018a74  not     ecx
0x180018a76  and     ecx, 1
0x180018a79  inc     ebx
0x180018a7b  shl     ebx, cl
0x180018a7d  cmp     ebx, [rdi+4]
0x180018a80  jbe     short loc_180018A95
0x180018a82  mov     r8d, 1
0x180018a88  mov     edx, ebx
0x180018a8a  mov     rcx, rdi
0x180018a8d  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x180018a92  mov     edx, [rdi+8]
0x180018a95  mov     [rdi], ebx
0x180018a97  test    dl, 10h
0x180018a9a  jz      short loc_180018AAD
0x180018a9c  mov     r8d, 1
0x180018aa2  mov     edx, [rdi+4]
0x180018aa5  mov     rcx, rdi
0x180018aa8  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x180018aad  mov     rax, [rdi+10h]
0x180018ab1  mov     [rsp+4D0h+cchValueName], 104h
0x180018ab9  lea     rcx, [rsp+4D0h+cbData]
0x180018abe  mov     [rsp+4D0h+lpcbData], rcx; lpcbData
0x180018ac3  mov     [rsp+4D0h+lpData], rax; lpData
0x180018ac8  lea     rax, [rsp+4D0h+Type]
0x180018acd  mov     [rsp+4D0h+lpType], rax; lpType
0x180018ad2  mov     [rsp+4D0h+lpReserved], r12; lpReserved
0x180018ad7  lea     r9, [rsp+4D0h+cchValueName]; lpcchValueName
0x180018adc  lea     r8, [rsp+4D0h+ValueName]; lpValueName
0x180018ae1  mov     edx, r15d; dwIndex
0x180018ae4  mov     rcx, [r14+10h]; hKey
0x180018ae8  call    cs:__imp_RegEnumValueW
0x180018aee  mov     ebx, eax
0x180018af0  mov     eax, [rdi]
0x180018af2  add     rax, [rdi+10h]
0x180018af6  test    byte ptr [rdi+8], 1
0x180018afa  jz      short loc_180018B02
0x180018afc  mov     [rax-1], r12b
0x180018b00  jmp     short loc_180018B07
0x180018b02  mov     [rax-2], r12w
0x180018b07  test    ebx, ebx
0x180018b09  jnz     short loc_180018B21
0x180018b0b  lea     rdx, [rsp+4D0h+ValueName]; unsigned __int16 *
0x180018b10  mov     rcx, rsi; this
0x180018b13  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180018b18  cmp     [rsp+4D0h+Type], 1
0x180018b1d  jnz     short loc_180018B63
0x180018b1f  jmp     short loc_180018B29
0x180018b21  cmp     ebx, 103h
0x180018b27  jnz     short loc_180018B4F
0x180018b29  test    ebx, ebx
0x180018b2b  setz    al
0x180018b2e  mov     rcx, [rbp+3D0h+var_40]
0x180018b35  xor     rcx, rsp; StackCookie
0x180018b38  call    __security_check_cookie
0x180018b3d  add     rsp, 4A0h
0x180018b44  pop     r15
0x180018b46  pop     r14
0x180018b48  pop     r12
0x180018b4a  pop     rdi
0x180018b4b  pop     rsi
0x180018b4c  pop     rbx
0x180018b4d  pop     rbp
0x180018b4e  retn
0x180018b4f  movzx   ecx, bx
0x180018b52  or      ecx, 80070000h
0x180018b58  test    ebx, ebx
0x180018b5a  cmovle  ecx, ebx; int
0x180018b5d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180018b63  lea     r8, aConsistencyErr_1; "Consistency error: registry key is of w"...
0x180018b6a  lea     rcx, [rsp+4D0h+var_480]
0x180018b6f  call    ??0SString@@QEAA@W4tagLiteral@0@PEBG@Z; SString::SString(SString::tagLiteral,ushort const *)
0x180018b74  nop
0x180018b75  mov     rdx, rax; struct SString *
0x180018b78  mov     ecx, 8000FFFFh; int
0x180018b7d  call    ?ThrowHR@@YAXJAEBVSString@@@Z; ThrowHR(long,SString const &)
```
