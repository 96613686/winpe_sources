# Faz_ValidateSingleLabelZone

- ea: `0x180086a64`
- end: `0x180086bf1`
- name: `Faz_ValidateSingleLabelZone`
- size: `397`
- prototype: `__int64 __fastcall(PCNZWCH lpString2)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006cd4c`

## callees

- `0x180005870`
- `0x18000702c`
- `0x18002b050`
- `0x180086a64`
- `0x18008b5f0`
- `0x1800dbadc`
- `0x1800dbfe0`
- `0x1800ddec0`

## import_xrefs

- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x180086b2c`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x180086b2c`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x180086b9b`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupClose` at `0x180086b9b`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180086b86`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x180086b86`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x180086b11`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x180086b11`

## pseudocode

```c
__int64 __fastcall Faz_ValidateSingleLabelZone(PCNZWCH lpString2, __int64 a2)
{
  unsigned int v4; // ebx
  PCNZWCH lpString1; // [rsp+30h] [rbp-50h] BYREF
  PVOID DomainInfo; // [rsp+38h] [rbp-48h] BYREF
  PVOID PolicyHandle; // [rsp+40h] [rbp-40h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-38h] BYREF

  lpString1 = 0;
  PolicyHandle = 0;
  DomainInfo = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_S(1035, 13, WPP_899061fd388939665cddd0f8129d3785_Traceguids, lpString2);
  if ( (unsigned int)Reg_ReadPrimaryDomainName(0, a2, &lpString1) )
    return 0;
  v4 = 0;
  if ( (unsigned int)Dns_NameCompare_W(lpString1, lpString2) )
  {
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    if ( !LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle)
      && !LsaLookupGetDomainInfo(PolicyHandle, DnsDomainInformation, &DomainInfo) )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_Sq(
          1035,
          14,
          (unsigned int)WPP_899061fd388939665cddd0f8129d3785_Traceguids,
          (_DWORD)lpString2,
          *((_QWORD *)DomainInfo + 8));
      LOBYTE(v4) = *((_QWORD *)DomainInfo + 8) != 0;
    }
  }
  DnsApiFree((LPVOID)lpString1);
  if ( DomainInfo )
    LsaLookupFreeMemory(DomainInfo);
  if ( PolicyHandle )
    LsaLookupClose(PolicyHandle);
  if ( (BYTE1(xmmword_1801119E0) & 0x20) != 0 )
    WPP_SF_Sd(1037, 15, (unsigned int)WPP_899061fd388939665cddd0f8129d3785_Traceguids, (_DWORD)lpString2, v4);
  return v4;
}

```

## disassembly

```asm
0x180086a64  mov     [rsp-8+arg_8], rbx
0x180086a69  mov     [rsp-8+arg_10], rdi
0x180086a6e  push    rbp
0x180086a6f  mov     rbp, rsp
0x180086a72  sub     rsp, 80h
0x180086a79  mov     rax, cs:__security_cookie
0x180086a80  xor     rax, rsp
0x180086a83  mov     [rbp+var_8], rax
0x180086a87  xorps   xmm0, xmm0
0x180086a8a  mov     [rbp+lpString1], 0
0x180086a92  xor     eax, eax
0x180086a94  mov     [rbp+PolicyHandle], 0
0x180086a9c  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180086aa0  mov     rdi, rcx
0x180086aa3  mov     [rbp+DomainInfo], rax
0x180086aa7  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180086aab  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180086aaf  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180086ab6  jz      short loc_180086ACF
0x180086ab8  lea     edx, [rax+0Dh]
0x180086abb  mov     ecx, 40Bh
0x180086ac0  mov     r9, rdi
0x180086ac3  lea     r8, WPP_899061fd388939665cddd0f8129d3785_Traceguids
0x180086aca  call    WPP_SF_S
0x180086acf  lea     r8, [rbp+lpString1]
0x180086ad3  xor     ecx, ecx
0x180086ad5  call    Reg_ReadPrimaryDomainName
0x180086ada  test    eax, eax
0x180086adc  jz      short loc_180086AE5
0x180086ade  xor     eax, eax
0x180086ae0  jmp     loc_180086BCF
0x180086ae5  mov     rcx, [rbp+lpString1]; lpString1
0x180086ae9  mov     rdx, rdi; lpString2
0x180086aec  xor     ebx, ebx
0x180086aee  call    Dns_NameCompare_W
0x180086af3  test    eax, eax
0x180086af5  jz      short loc_180086B74
0x180086af7  xorps   xmm0, xmm0
0x180086afa  lea     r8, [rbp+PolicyHandle]; PolicyHandle
0x180086afe  lea     edx, [rbx+1]; AccessMask
0x180086b01  lea     rcx, [rbp+ObjectAttributes]; ObjectAttributes
0x180086b05  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180086b09  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180086b0d  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180086b11  call    cs:__imp_LsaLookupOpenLocalPolicy
0x180086b18  nop     dword ptr [rax+rax+00h]
0x180086b1d  test    eax, eax
0x180086b1f  jnz     short loc_180086B74
0x180086b21  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180086b25  lea     r8, [rbp+DomainInfo]; DomainInfo
0x180086b29  lea     edx, [rbx+0Ch]; DomainInfoClass
0x180086b2c  call    cs:__imp_LsaLookupGetDomainInfo
0x180086b33  nop     dword ptr [rax+rax+00h]
0x180086b38  test    eax, eax
0x180086b3a  jnz     short loc_180086B74
0x180086b3c  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180086b43  jz      short loc_180086B69
0x180086b45  mov     rax, [rbp+DomainInfo]
0x180086b49  lea     edx, [rbx+0Eh]
0x180086b4c  mov     ecx, 40Bh
0x180086b51  mov     r9, rdi
0x180086b54  mov     r8, [rax+40h]
0x180086b58  mov     [rsp+80h+var_60], r8
0x180086b5d  lea     r8, WPP_899061fd388939665cddd0f8129d3785_Traceguids
0x180086b64  call    WPP_SF_Sq
0x180086b69  mov     rax, [rbp+DomainInfo]
0x180086b6d  cmp     [rax+40h], rbx
0x180086b71  setnz   bl
0x180086b74  mov     rcx, [rbp+lpString1]; lpMem
0x180086b78  call    DnsApiFree
0x180086b7d  mov     rcx, [rbp+DomainInfo]; Buffer
0x180086b81  test    rcx, rcx
0x180086b84  jz      short loc_180086B92
0x180086b86  call    cs:__imp_LsaLookupFreeMemory
0x180086b8d  nop     dword ptr [rax+rax+00h]
0x180086b92  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180086b96  test    rcx, rcx
0x180086b99  jz      short loc_180086BA7
0x180086b9b  call    cs:__imp_LsaLookupClose
0x180086ba2  nop     dword ptr [rax+rax+00h]
0x180086ba7  test    byte ptr cs:xmmword_1801119E0+1, 20h
0x180086bae  jz      short loc_180086BCD
0x180086bb0  mov     edx, 0Fh
0x180086bb5  mov     dword ptr [rsp+80h+var_60], ebx
0x180086bb9  mov     ecx, 40Dh
0x180086bbe  lea     r8, WPP_899061fd388939665cddd0f8129d3785_Traceguids
0x180086bc5  mov     r9, rdi
0x180086bc8  call    WPP_SF_Sd
0x180086bcd  mov     eax, ebx
0x180086bcf  mov     rcx, [rbp+var_8]
0x180086bd3  xor     rcx, rsp; StackCookie
0x180086bd6  call    __security_check_cookie
0x180086bdb  lea     r11, [rsp+80h+var_s0]
0x180086be3  mov     rbx, [r11+18h]
0x180086be7  mov     rdi, [r11+20h]
0x180086beb  mov     rsp, r11
0x180086bee  pop     rbp
0x180086bef  retn
```
