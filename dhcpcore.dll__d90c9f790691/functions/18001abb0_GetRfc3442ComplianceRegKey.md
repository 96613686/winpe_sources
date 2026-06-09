# GetRfc3442ComplianceRegKey

- ea: `0x18001abb0`
- end: `0x18001ac76`
- name: `GetRfc3442ComplianceRegKey`
- size: `198`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003da30`

## callees

- `0x1800069d0`
- `0x18001abb0`
- `0x180036684`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004dd28`

## string_xrefs

- `0x18001abfa`: `OSDATA\Networking\Dhcp\Client4\Configurations`
- `0x18001abf3`: `System\CurrentControlSet\Services\Dhcp\Configurations`

## pseudocode

```c
__int64 __fastcall GetRfc3442ComplianceRegKey(_DWORD *a1)
{
  int v2; // ebx
  unsigned int v3; // ebp
  BOOL IsWCOSSystem; // eax
  __int64 v5; // r8
  const WCHAR *v6; // rcx
  unsigned int DWORD; // eax
  unsigned int v8; // edi
  int v10; // [rsp+60h] [rbp+8h] BYREF

  v10 = 0;
  v2 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 50, WPP_c340248efe383a4e03597a9397b959ee_Traceguids);
  if ( a1 )
  {
    *a1 = 0;
    v3 = 0;
    IsWCOSSystem = DhcpIsWCOSSystem();
    v6 = L"OSDATA\\Networking\\Dhcp\\Client4\\Configurations";
    if ( !IsWCOSSystem )
      v6 = L"System\\CurrentControlSet\\Services\\Dhcp\\Configurations";
    DWORD = DhcpRegReadDWORD(
              v6,
              (__int64)L"System\\CurrentControlSet\\Services\\Dhcp\\Configurations",
              v5,
              (__int64)&v10);
    v8 = DWORD;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_D(1028, 51, WPP_c340248efe383a4e03597a9397b959ee_Traceguids, DWORD);
    if ( !v8 )
    {
      LOBYTE(v2) = v10 != 0;
      *a1 = v2;
    }
  }
  else
  {
    v8 = 0;
    v3 = 87;
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_Dd(1028, 52, WPP_c340248efe383a4e03597a9397b959ee_Traceguids, v8, v2);
  return v3;
}

```

## disassembly

```asm
0x18001abb0  push    rbx
0x18001abb2  push    rbp
0x18001abb3  push    rsi
0x18001abb4  push    rdi
0x18001abb5  sub     rsp, 38h
0x18001abb9  mov     rsi, rcx
0x18001abbc  mov     [rsp+58h+arg_0], 0
0x18001abc4  xor     ebx, ebx
0x18001abc6  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001abcd  jz      short loc_18001ABE3
0x18001abcf  lea     edx, [rbx+32h]
0x18001abd2  mov     ecx, 404h
0x18001abd7  lea     r8, WPP_c340248efe383a4e03597a9397b959ee_Traceguids
0x18001abde  call    WPP_SF_
0x18001abe3  test    rsi, rsi
0x18001abe6  jz      short loc_18001AC40
0x18001abe8  mov     [rsi], ebx
0x18001abea  xor     ebp, ebp
0x18001abec  call    DhcpIsWCOSSystem
0x18001abf1  test    eax, eax
0x18001abf3  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Dh"...
0x18001abfa  lea     rcx, aOsdataNetworki_4; "OSDATA\\Networking\\Dhcp\\Client4\\Conf"...
0x18001ac01  cmovz   rcx, rdx; lpSubKey
0x18001ac05  lea     r9, [rsp+58h+arg_0]
0x18001ac0a  call    DhcpRegReadDWORD
0x18001ac0f  mov     edi, eax
0x18001ac11  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001ac18  jz      short loc_18001AC31
0x18001ac1a  lea     edx, [rbp+33h]
0x18001ac1d  mov     ecx, 404h
0x18001ac22  mov     r9d, eax
0x18001ac25  lea     r8, WPP_c340248efe383a4e03597a9397b959ee_Traceguids
0x18001ac2c  call    WPP_SF_D
0x18001ac31  test    edi, edi
0x18001ac33  jnz     short loc_18001AC45
0x18001ac35  cmp     [rsp+58h+arg_0], ebx
0x18001ac39  setnz   bl
0x18001ac3c  mov     [rsi], ebx
0x18001ac3e  jmp     short loc_18001AC45
0x18001ac40  xor     edi, edi
0x18001ac42  lea     ebp, [rdi+57h]
0x18001ac45  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001ac4c  jz      short loc_18001AC6B
0x18001ac4e  mov     edx, 34h ; '4'
0x18001ac53  mov     [rsp+58h+var_38], ebx
0x18001ac57  mov     ecx, 404h
0x18001ac5c  lea     r8, WPP_c340248efe383a4e03597a9397b959ee_Traceguids
0x18001ac63  mov     r9d, edi
0x18001ac66  call    WPP_SF_Dd
0x18001ac6b  mov     eax, ebp
0x18001ac6d  add     rsp, 38h
0x18001ac71  pop     rdi
0x18001ac72  pop     rsi
0x18001ac73  pop     rbp
0x18001ac74  pop     rbx
0x18001ac75  retn
```
