# WfpFwpDataTypeToString

- ea: `0x18000f6a8`
- end: `0x18000f7e8`
- name: `WfpFwpDataTypeToString`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f2d8`

## callees

- `0x18000f6a8`

## string_xrefs

- `0x18000f793`: `Security Descriptor`
- `0x18000f78b`: `Token Information`
- `0x18000f783`: `Token Access Information`

## pseudocode

```c
const wchar_t *__fastcall WfpFwpDataTypeToString(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx

  if ( a1 <= 256 )
  {
    if ( a1 == 256 )
      return L"IPv4 Addr & Mask";
    if ( a1 > 9 )
    {
      v9 = a1 - 10;
      if ( !v9 )
        return L"Double";
      v10 = v9 - 1;
      if ( !v10 )
        return L"16-byte Array";
      v11 = v10 - 1;
      if ( !v11 )
        return L"Octet String";
      v12 = v11 - 1;
      if ( !v12 )
        return L"SID";
      v13 = v12 - 1;
      if ( !v13 )
        return L"Security Descriptor";
      v14 = v13 - 1;
      if ( !v14 )
        return L"Token Information";
      v15 = v14 - 1;
      if ( !v15 )
        return L"Token Access Information";
      v16 = v15 - 1;
      if ( !v16 )
        return L"Unicode String";
      if ( v16 == 1 )
        return L"6-byte Array";
    }
    else
    {
      if ( a1 == 9 )
        return L"Float";
      if ( !a1 )
        return L"Empty";
      v1 = a1 - 1;
      if ( !v1 )
        return L"UInt8";
      v2 = v1 - 1;
      if ( !v2 )
        return L"UInt16";
      v3 = v2 - 1;
      if ( !v3 )
        return L"UInt32";
      v4 = v3 - 1;
      if ( !v4 )
        return L"UInt64";
      v5 = v4 - 1;
      if ( !v5 )
        return L"Int8";
      v6 = v5 - 1;
      if ( !v6 )
        return L"Int16";
      v7 = v6 - 1;
      if ( !v7 )
        return L"Int32";
      if ( v7 == 1 )
        return L"Int64";
    }
    return L"<invalid>";
  }
  v17 = a1 - 257;
  if ( !v17 )
    return L"IPv6 Addr & Mask";
  if ( v17 != 1 )
    return L"<invalid>";
  return L"Range";
}

```

## disassembly

```asm
0x18000f6a8  mov     eax, 100h
0x18000f6ad  cmp     ecx, eax
0x18000f6af  jg      loc_18000F7C3
0x18000f6b5  jz      loc_18000F7BB
0x18000f6bb  cmp     ecx, 9
0x18000f6be  jg      loc_18000F746
0x18000f6c4  jz      short loc_18000F73E
0x18000f6c6  test    ecx, ecx
0x18000f6c8  jz      short loc_18000F736
0x18000f6ca  sub     ecx, 1
0x18000f6cd  jz      short loc_18000F72E
0x18000f6cf  sub     ecx, 1
0x18000f6d2  jz      short loc_18000F726
0x18000f6d4  sub     ecx, 1
0x18000f6d7  jz      short loc_18000F71E
0x18000f6d9  sub     ecx, 1
0x18000f6dc  jz      short loc_18000F716
0x18000f6de  sub     ecx, 1
0x18000f6e1  jz      short loc_18000F70E
0x18000f6e3  sub     ecx, 1
0x18000f6e6  jz      short loc_18000F706
0x18000f6e8  sub     ecx, 1
0x18000f6eb  jz      short loc_18000F6FE
0x18000f6ed  cmp     ecx, 1
0x18000f6f0  jnz     loc_18000F7D0
0x18000f6f6  lea     rax, aInt64; "Int64"
0x18000f6fd  retn
0x18000f6fe  lea     rax, aInt32; "Int32"
0x18000f705  retn
0x18000f706  lea     rax, aInt16; "Int16"
0x18000f70d  retn
0x18000f70e  lea     rax, aInt8; "Int8"
0x18000f715  retn
0x18000f716  lea     rax, aUint64; "UInt64"
0x18000f71d  retn
0x18000f71e  lea     rax, aUint32; "UInt32"
0x18000f725  retn
0x18000f726  lea     rax, aUint16; "UInt16"
0x18000f72d  retn
0x18000f72e  lea     rax, aUint8; "UInt8"
0x18000f735  retn
0x18000f736  lea     rax, aEmpty; "Empty"
0x18000f73d  retn
0x18000f73e  lea     rax, aFloat; "Float"
0x18000f745  retn
0x18000f746  sub     ecx, 0Ah
0x18000f749  jz      short loc_18000F7B3
0x18000f74b  sub     ecx, 1
0x18000f74e  jz      short loc_18000F7AB
0x18000f750  sub     ecx, 1
0x18000f753  jz      short loc_18000F7A3
0x18000f755  sub     ecx, 1
0x18000f758  jz      short loc_18000F79B
0x18000f75a  sub     ecx, 1
0x18000f75d  jz      short loc_18000F793
0x18000f75f  sub     ecx, 1
0x18000f762  jz      short loc_18000F78B
0x18000f764  sub     ecx, 1
0x18000f767  jz      short loc_18000F783
0x18000f769  sub     ecx, 1
0x18000f76c  jz      short loc_18000F77B
0x18000f76e  cmp     ecx, 1
0x18000f771  jnz     short loc_18000F7D0
0x18000f773  lea     rax, a6ByteArray; "6-byte Array"
0x18000f77a  retn
0x18000f77b  lea     rax, aUnicodeString; "Unicode String"
0x18000f782  retn
0x18000f783  lea     rax, aTokenAccessInf; "Token Access Information"
0x18000f78a  retn
0x18000f78b  lea     rax, aTokenInformati; "Token Information"
0x18000f792  retn
0x18000f793  lea     rax, aSecurityDescri; "Security Descriptor"
0x18000f79a  retn
0x18000f79b  lea     rax, aSid; "SID"
0x18000f7a2  retn
0x18000f7a3  lea     rax, aOctetString; "Octet String"
0x18000f7aa  retn
0x18000f7ab  lea     rax, a16ByteArray; "16-byte Array"
0x18000f7b2  retn
0x18000f7b3  lea     rax, aDouble; "Double"
0x18000f7ba  retn
0x18000f7bb  lea     rax, aIpv4AddrMask; "IPv4 Addr & Mask"
0x18000f7c2  retn
0x18000f7c3  sub     ecx, 101h
0x18000f7c9  jz      short loc_18000F7E0
0x18000f7cb  cmp     ecx, 1
0x18000f7ce  jz      short loc_18000F7D8
0x18000f7d0  lea     rax, aInvalid; "<invalid>"
0x18000f7d7  retn
0x18000f7d8  lea     rax, aRange; "Range"
0x18000f7df  retn
0x18000f7e0  lea     rax, aIpv6AddrMask; "IPv6 Addr & Mask"
0x18000f7e7  retn
```
