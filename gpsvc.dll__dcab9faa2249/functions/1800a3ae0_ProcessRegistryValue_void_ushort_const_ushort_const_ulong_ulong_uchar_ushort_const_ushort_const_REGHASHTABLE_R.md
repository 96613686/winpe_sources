# ProcessRegistryValue(void *,ushort const *,ushort const *,ulong,ulong,uchar *,ushort const *,ushort const *,_REGHASHTABLE *,_REGHASHTABLE *)

- ea: `0x1800a3ae0`
- end: `0x1800a3e37`
- name: `?ProcessRegistryValue@@YAHPEAXPEBG1KKPEAE11PEAU_REGHASHTABLE@@3@Z`
- size: `855`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned __int8 *, const unsigned __int16 *, const unsigned __int16 *, struct _REGHASHTABLE *, struct _REGHASHTABLE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180045844`
- `0x18007d320`
- `0x18009f958`
- `0x1800a3ae0`
- `0x1800bb8e0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800a3b63`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800a3bbc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800a3bf7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800a3ca4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800a3d54`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800a3d99`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800a3dbe`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800a3b63`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800a3bbc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800a3bf7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800a3ca4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800a3d54`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800a3d99`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800a3dbe`

## string_xrefs

- `0x1800a3c8c`: `**DeleteKeys`
- `0x1800a3bdf`: `**DeleteValues`
- `0x1800a3daf`: `**Comment:`

## pseudocode

```c
__int64 __fastcall ProcessRegistryValue(
        void *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *lpString2,
        unsigned int a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        struct _REGHASHTABLE *a9)
{
  unsigned __int8 *v9; // r14
  struct _REGHASHTABLE *v11; // rdi
  unsigned __int16 *v12; // r12
  unsigned __int16 *v14; // r13
  unsigned int v16; // edx
  const WCHAR *v17; // r9
  unsigned int v19; // edi
  int v20; // eax
  int v21; // eax
  const WCHAR *v22; // r9
  unsigned int v23; // edx
  struct _REGHASHTABLE *v24; // rcx
  unsigned __int16 *v26; // [rsp+48h] [rbp-B8h]
  unsigned __int8 *v27; // [rsp+60h] [rbp-A0h] BYREF
  struct _REGHASHTABLE *v28; // [rsp+68h] [rbp-98h]
  WCHAR v29[2048]; // [rsp+70h] [rbp-90h] BYREF

  v9 = a6;
  v11 = a9;
  v12 = a7;
  v14 = a8;
  v27 = a6;
  v28 = a9;
  if ( CompareStringW(0x7Fu, 1u, L"**del.", 6, lpString2, 6) == 2 )
  {
    v16 = 0;
    v17 = lpString2 + 6;
    return (unsigned int)AddRegHashEntry(v11, v16, a2, v17, 0, 0, 0, v12, v14, lpString2, 1);
  }
  if ( CompareStringW(0x7Fu, 1u, L"**delvals.", 10, lpString2, 10) == 2 )
  {
    v17 = 0;
    v16 = 1;
    return (unsigned int)AddRegHashEntry(v11, v16, a2, v17, 0, 0, 0, v12, v14, lpString2, 1);
  }
  if ( CompareStringW(0x7Fu, 1u, L"**DeleteValues", 14, lpString2, 14) == 2 )
  {
    v19 = 1;
    if ( v9 )
    {
      while ( *v9 )
      {
        if ( !(unsigned int)ExtractKeyOrValueName(&v27, &a5, v29, 512) )
          return 0;
        v20 = AddRegHashEntry(v28, 0, a2, v29, 0, 0, 0, v12, v14, lpString2, 1);
        v9 = v27;
        v19 &= -(v20 != 0);
      }
    }
  }
  else
  {
    if ( CompareStringW(0x7Fu, 1u, L"**DeleteKeys", 12, lpString2, 12) != 2 )
    {
      if ( CompareStringW(0x7Fu, 1u, L"**soft.", 7, lpString2, 7) == 2 )
      {
        v22 = lpString2 + 7;
        v26 = lpString2;
        v23 = 4;
        v24 = v11;
      }
      else
      {
        v19 = 1;
        if ( CompareStringW(0x7Fu, 1u, L"**SecureKey", 11, lpString2, 11) == 2
          || CompareStringW(0x7Fu, 1u, L"**Comment:", 10, lpString2, 10) == 2 )
        {
          return v19;
        }
        v24 = v28;
        v23 = 3;
        v26 = (unsigned __int16 *)&DomainName;
        v22 = lpString2;
      }
      return (unsigned int)AddRegHashEntry(v24, v23, a2, v22, a4, a5, (__int64)v9, v12, v14, v26, 1);
    }
    v19 = 1;
    if ( v9 )
    {
      while ( *v9 )
      {
        if ( !(unsigned int)ExtractKeyOrValueName(&v27, &a5, v29, 2048) )
          return 0;
        v21 = AddRegHashEntry(v28, 2u, a2, 0, 0, 0, 0, v12, v14, lpString2, 1);
        v9 = v27;
        v19 &= -(v21 != 0);
      }
    }
  }
  return v19;
}

```

## disassembly

```asm
0x1800a3ae0  mov     [rsp-8+arg_0], rbx
0x1800a3ae5  push    rbp
0x1800a3ae6  push    rsi
0x1800a3ae7  push    rdi
0x1800a3ae8  push    r12
0x1800a3aea  push    r13
0x1800a3aec  push    r14
0x1800a3aee  push    r15
0x1800a3af0  lea     rbp, [rsp-0F80h]
0x1800a3af8  mov     eax, 1080h
0x1800a3afd  call    _alloca_probe
0x1800a3b02  sub     rsp, rax
0x1800a3b05  mov     rax, cs:__security_cookie
0x1800a3b0c  xor     rax, rsp
0x1800a3b0f  mov     [rbp+0FB0h+var_40], rax
0x1800a3b16  mov     r14, [rbp+0FB0h+arg_28]
0x1800a3b1d  mov     ebx, r9d
0x1800a3b20  mov     rdi, [rbp+0FB0h+arg_40]
0x1800a3b27  mov     r9d, 6; cchCount1
0x1800a3b2d  mov     r12, [rbp+0FB0h+arg_30]
0x1800a3b34  mov     r15, rdx
0x1800a3b37  mov     r13, [rbp+0FB0h+arg_38]
0x1800a3b3e  mov     rsi, r8
0x1800a3b41  mov     [rsp+10B0h+cchCount2], r9d; cchCount2
0x1800a3b46  lea     edx, [r9-5]; dwCmpFlags
0x1800a3b4a  mov     [rsp+10B0h+lpString2], r8; lpString2
0x1800a3b4f  lea     ecx, [rdx+7Eh]; Locale
0x1800a3b52  mov     [rsp+10B0h+var_1050], r14
0x1800a3b57  lea     r8, aDel; "**del."
0x1800a3b5e  mov     [rsp+10B0h+var_1048], rdi
0x1800a3b63  call    cs:__imp_CompareStringW
0x1800a3b69  cmp     eax, 2
0x1800a3b6c  jnz     short loc_1800A3B9E
0x1800a3b6e  xor     ebx, ebx
0x1800a3b70  mov     [rsp+10B0h+var_1060], 1
0x1800a3b78  xor     edx, edx
0x1800a3b7a  lea     r9, [rsi+0Ch]
0x1800a3b7e  mov     [rsp+10B0h+var_1068], rsi
0x1800a3b83  mov     rcx, rdi
0x1800a3b86  mov     [rsp+10B0h+var_1070], r13
0x1800a3b8b  mov     [rsp+10B0h+var_1078], r12
0x1800a3b90  mov     [rsp+10B0h+var_1080], rbx
0x1800a3b95  mov     [rsp+10B0h+cchCount2], ebx
0x1800a3b99  jmp     loc_1800A3DFD
0x1800a3b9e  mov     eax, 0Ah
0x1800a3ba3  lea     r8, aDelvals; "**delvals."
0x1800a3baa  mov     [rsp+10B0h+cchCount2], eax; cchCount2
0x1800a3bae  mov     r9d, eax; cchCount1
0x1800a3bb1  mov     [rsp+10B0h+lpString2], rsi; lpString2
0x1800a3bb6  lea     edx, [rax-9]; dwCmpFlags
0x1800a3bb9  lea     ecx, [rax+75h]; Locale
0x1800a3bbc  call    cs:__imp_CompareStringW
0x1800a3bc2  cmp     eax, 2
0x1800a3bc5  jnz     short loc_1800A3BD9
0x1800a3bc7  mov     eax, 1
0x1800a3bcc  xor     ebx, ebx
0x1800a3bce  mov     [rsp+10B0h+var_1060], eax
0x1800a3bd2  xor     r9d, r9d
0x1800a3bd5  mov     edx, eax
0x1800a3bd7  jmp     short loc_1800A3B7E
0x1800a3bd9  mov     r9d, 0Eh; cchCount1
0x1800a3bdf  lea     r8, aDeletevalues; "**DeleteValues"
0x1800a3be6  mov     [rsp+10B0h+cchCount2], r9d; cchCount2
0x1800a3beb  mov     [rsp+10B0h+lpString2], rsi; lpString2
0x1800a3bf0  lea     edx, [r9-0Dh]; dwCmpFlags
0x1800a3bf4  lea     ecx, [rdx+7Eh]; Locale
0x1800a3bf7  call    cs:__imp_CompareStringW
0x1800a3bfd  cmp     eax, 2
0x1800a3c00  jnz     loc_1800A3C86
0x1800a3c06  xor     ebx, ebx
0x1800a3c08  lea     edi, [rax-1]
0x1800a3c0b  test    r14, r14
0x1800a3c0e  jz      loc_1800A3E0B
0x1800a3c14  cmp     [r14], bl
0x1800a3c17  jz      loc_1800A3E0B
0x1800a3c1d  mov     r9d, 200h
0x1800a3c23  lea     r8, [rsp+10B0h+var_1040]
0x1800a3c28  lea     rdx, [rbp+0FB0h+arg_20]
0x1800a3c2f  lea     rcx, [rsp+10B0h+var_1050]
0x1800a3c34  call    ExtractKeyOrValueName
0x1800a3c39  test    eax, eax
0x1800a3c3b  jz      loc_1800A3D2F
0x1800a3c41  mov     rcx, [rsp+10B0h+var_1048]
0x1800a3c46  lea     r9, [rsp+10B0h+var_1040]
0x1800a3c4b  mov     [rsp+10B0h+var_1060], 1
0x1800a3c53  mov     r8, r15
0x1800a3c56  mov     [rsp+10B0h+var_1068], rsi
0x1800a3c5b  xor     edx, edx
0x1800a3c5d  mov     [rsp+10B0h+var_1070], r13
0x1800a3c62  mov     [rsp+10B0h+var_1078], r12
0x1800a3c67  mov     [rsp+10B0h+var_1080], rbx
0x1800a3c6c  mov     [rsp+10B0h+cchCount2], ebx
0x1800a3c70  mov     dword ptr [rsp+10B0h+lpString2], ebx
0x1800a3c74  call    ?AddRegHashEntry@@YAHPEAU_REGHASHTABLE@@W4_REGOPERATION@@PEBG2KKPEAE222H@Z; AddRegHashEntry(_REGHASHTABLE *,_REGOPERATION,ushort const *,ushort const *,ulong,ulong,uchar *,ushort const *,ushort const *,ushort const *,int)
0x1800a3c79  mov     r14, [rsp+10B0h+var_1050]
0x1800a3c7e  neg     eax
0x1800a3c80  sbb     ecx, ecx
0x1800a3c82  and     edi, ecx
0x1800a3c84  jmp     short loc_1800A3C14
0x1800a3c86  mov     r9d, 0Ch; cchCount1
0x1800a3c8c  lea     r8, aDeletekeys; "**DeleteKeys"
0x1800a3c93  mov     [rsp+10B0h+cchCount2], r9d; cchCount2
0x1800a3c98  mov     [rsp+10B0h+lpString2], rsi; lpString2
0x1800a3c9d  lea     edx, [r9-0Bh]; dwCmpFlags
0x1800a3ca1  lea     ecx, [rdx+7Eh]; Locale
0x1800a3ca4  call    cs:__imp_CompareStringW
0x1800a3caa  cmp     eax, 2
0x1800a3cad  jnz     loc_1800A3D36
0x1800a3cb3  xor     ebx, ebx
0x1800a3cb5  lea     edi, [rax-1]
0x1800a3cb8  test    r14, r14
0x1800a3cbb  jz      loc_1800A3E0B
0x1800a3cc1  cmp     [r14], bl
0x1800a3cc4  jz      loc_1800A3E0B
0x1800a3cca  mov     r9d, 800h
0x1800a3cd0  lea     r8, [rsp+10B0h+var_1040]
0x1800a3cd5  lea     rdx, [rbp+0FB0h+arg_20]
0x1800a3cdc  lea     rcx, [rsp+10B0h+var_1050]
0x1800a3ce1  call    ExtractKeyOrValueName
0x1800a3ce6  test    eax, eax
0x1800a3ce8  jz      short loc_1800A3D2F
0x1800a3cea  mov     rcx, [rsp+10B0h+var_1048]
0x1800a3cef  xor     r9d, r9d
0x1800a3cf2  mov     [rsp+10B0h+var_1060], 1
0x1800a3cfa  mov     r8, r15
0x1800a3cfd  mov     [rsp+10B0h+var_1068], rsi
0x1800a3d02  mov     [rsp+10B0h+var_1070], r13
0x1800a3d07  mov     [rsp+10B0h+var_1078], r12
0x1800a3d0c  lea     edx, [r9+2]
0x1800a3d10  mov     [rsp+10B0h+var_1080], rbx
0x1800a3d15  mov     [rsp+10B0h+cchCount2], ebx
0x1800a3d19  mov     dword ptr [rsp+10B0h+lpString2], ebx
0x1800a3d1d  call    ?AddRegHashEntry@@YAHPEAU_REGHASHTABLE@@W4_REGOPERATION@@PEBG2KKPEAE222H@Z; AddRegHashEntry(_REGHASHTABLE *,_REGOPERATION,ushort const *,ushort const *,ulong,ulong,uchar *,ushort const *,ushort const *,ushort const *,int)
0x1800a3d22  mov     r14, [rsp+10B0h+var_1050]
0x1800a3d27  neg     eax
0x1800a3d29  sbb     ecx, ecx
0x1800a3d2b  and     edi, ecx
0x1800a3d2d  jmp     short loc_1800A3CC1
0x1800a3d2f  mov     edi, ebx
0x1800a3d31  jmp     loc_1800A3E0B
0x1800a3d36  mov     r9d, 7; cchCount1
0x1800a3d3c  lea     r8, aSoft; "**soft."
0x1800a3d43  mov     [rsp+10B0h+cchCount2], r9d; cchCount2
0x1800a3d48  mov     [rsp+10B0h+lpString2], rsi; lpString2
0x1800a3d4d  lea     edx, [r9-6]; dwCmpFlags
0x1800a3d51  lea     ecx, [rdx+7Eh]; Locale
0x1800a3d54  call    cs:__imp_CompareStringW
0x1800a3d5a  cmp     eax, 2
0x1800a3d5d  jnz     short loc_1800A3D78
0x1800a3d5f  mov     [rsp+10B0h+var_1060], 1
0x1800a3d67  lea     r9, [rsi+0Eh]
0x1800a3d6b  mov     [rsp+10B0h+var_1068], rsi
0x1800a3d70  lea     edx, [rax+2]
0x1800a3d73  mov     rcx, rdi
0x1800a3d76  jmp     short loc_1800A3DE4
0x1800a3d78  mov     eax, 1
0x1800a3d7d  lea     r8, aSecurekey; "**SecureKey"
0x1800a3d84  mov     edx, eax; dwCmpFlags
0x1800a3d86  mov     edi, eax
0x1800a3d88  lea     r9d, [rax+0Ah]; cchCount1
0x1800a3d8c  mov     [rsp+10B0h+cchCount2], r9d; cchCount2
0x1800a3d91  lea     ecx, [rax+7Eh]; Locale
0x1800a3d94  mov     [rsp+10B0h+lpString2], rsi; lpString2
0x1800a3d99  call    cs:__imp_CompareStringW
0x1800a3d9f  cmp     eax, 2
0x1800a3da2  jz      short loc_1800A3E0B
0x1800a3da4  lea     r9d, [rdi+9]; cchCount1
0x1800a3da8  mov     edx, edi; dwCmpFlags
0x1800a3daa  mov     [rsp+10B0h+cchCount2], r9d; cchCount2
0x1800a3daf  lea     r8, aComment; "**Comment:"
0x1800a3db6  lea     ecx, [rdi+7Eh]; Locale
0x1800a3db9  mov     [rsp+10B0h+lpString2], rsi; lpString2
0x1800a3dbe  call    cs:__imp_CompareStringW
0x1800a3dc4  cmp     eax, 2
0x1800a3dc7  jz      short loc_1800A3E0B
0x1800a3dc9  mov     rcx, [rsp+10B0h+var_1048]
0x1800a3dce  lea     rax, DomainName
0x1800a3dd5  mov     [rsp+10B0h+var_1060], edi
0x1800a3dd9  lea     edx, [rdi+2]
0x1800a3ddc  mov     [rsp+10B0h+var_1068], rax
0x1800a3de1  mov     r9, rsi
0x1800a3de4  mov     eax, [rbp+0FB0h+arg_20]
0x1800a3dea  mov     [rsp+10B0h+var_1070], r13
0x1800a3def  mov     [rsp+10B0h+var_1078], r12
0x1800a3df4  mov     [rsp+10B0h+var_1080], r14
0x1800a3df9  mov     [rsp+10B0h+cchCount2], eax
0x1800a3dfd  mov     r8, r15
0x1800a3e00  mov     dword ptr [rsp+10B0h+lpString2], ebx
0x1800a3e04  call    ?AddRegHashEntry@@YAHPEAU_REGHASHTABLE@@W4_REGOPERATION@@PEBG2KKPEAE222H@Z; AddRegHashEntry(_REGHASHTABLE *,_REGOPERATION,ushort const *,ushort const *,ulong,ulong,uchar *,ushort const *,ushort const *,ushort const *,int)
0x1800a3e09  mov     edi, eax
0x1800a3e0b  mov     eax, edi
0x1800a3e0d  mov     rcx, [rbp+0FB0h+var_40]
0x1800a3e14  xor     rcx, rsp; StackCookie
0x1800a3e17  call    __security_check_cookie
0x1800a3e1c  mov     rbx, [rsp+10B0h+arg_0]
0x1800a3e24  add     rsp, 1080h
0x1800a3e2b  pop     r15
0x1800a3e2d  pop     r14
0x1800a3e2f  pop     r13
0x1800a3e31  pop     r12
0x1800a3e33  pop     rdi
0x1800a3e34  pop     rsi
0x1800a3e35  pop     rbp
0x1800a3e36  retn
```
