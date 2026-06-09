# ReConfigureParams

- ea: `0x180008a70`
- end: `0x180008d67`
- name: `ReConfigureParams`
- size: `759`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013580`
- `0x180013840`
- `0x180029104`

## callees

- `0x180001ca4`
- `0x1800062e8`
- `0x180007cc8`
- `0x180008440`
- `0x180008a70`
- `0x180008d70`
- `0x18000bdd4`
- `0x18000e7dc`
- `0x18000edbc`
- `0x180010fd4`
- `0x180013b6c`
- `0x180016db0`
- `0x18001a3ee`
- `0x1800206ac`
- `0x180020940`
- `0x180022b80`
- `0x1800337d0`
- `0x1800338c0`
- `0x180033900`

## pseudocode

```c
__int64 __fastcall ReConfigureParams(__int64 a1)
{
  int v2; // esi
  __int64 v3; // rcx
  unsigned int Reply; // edi
  unsigned int v5; // edx
  int InfoRefreshTime; // eax
  __int64 v7; // rdx
  __int64 (__fastcall *v8)(_QWORD); // r8
  unsigned int v9; // eax
  _QWORD v11[2]; // [rsp+30h] [rbp-118h] BYREF
  _BYTE v12[264]; // [rsp+40h] [rbp-108h] BYREF
  __int16 v13; // [rsp+150h] [rbp+8h] BYREF
  char v14; // [rsp+152h] [rbp+Ah]
  unsigned int v15; // [rsp+158h] [rbp+10h] BYREF
  int v16; // [rsp+160h] [rbp+18h] BYREF
  __int64 v17; // [rsp+168h] [rbp+20h] BYREF

  v15 = 0;
  v13 = 0;
  v14 = 0;
  memset_0(v12, 0, 0xD4u);
  v2 = 0;
  v17 = 0;
  v16 = 0;
  v11[0] = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    WPP_SF_S(1028, 202, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *(_QWORD *)(a1 + 56));
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_(1028, 203, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
  }
  Reply = DhcpV6ActivateNetwork(v11, &v17, a1, 12);
  if ( !Reply )
  {
    v2 = 1;
    if ( *(_DWORD *)(a1 + 496) )
    {
      if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
        McTemplateU0q_EtwEventWriteTransfer(v3, IRTExpired, *(unsigned int *)(a1 + 48));
      *(_DWORD *)(a1 + 496) = 0;
    }
    *(_DWORD *)(a1 + 592) = 1;
    CreateDhcpv6TransactionId(&v13);
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_(1028, 204, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
    Reply = CreateDhcpv6InfoRequest((char *)a1, &v13, (int *)&v15);
    if ( !Reply )
    {
      v5 = v15;
      *(_WORD *)(a1 + 676) = 0;
      Reply = SendDhcpv6InfoRequestAndGetReply(a1, v5, (unsigned __int8 *)&v13, (__int64)v12);
      if ( !Reply )
      {
        if ( **(_DWORD **)&pDhcpv6GlobalIsShuttingDown )
        {
          if ( (xmmword_1800423E0 & 2) != 0 )
            WPP_SF_D(1025, 205, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, 0);
          Reply = 65;
        }
        else
        {
          Dhcpv6RegSaveOptions(
            (_QWORD **)(a1 + 632),
            *(_QWORD *)(a1 + 56),
            *(HKEY *)(a1 + 648),
            *(_QWORD *)(a1 + 656),
            *(_DWORD *)(a1 + 664));
          Dhcpv6SaveNetworkHint(a1);
          *(_DWORD *)(a1 + 8920) = ((unsigned int)Dhcpv6RegisterWithDns(a1, 0) != 0) + 2;
        }
      }
    }
  }
  CleanupDhcpOptions((__int64)v12);
  if ( v2 )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_(1028, 206, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
    DhcpV6DeactivateNetwork(v11, &v17, a1, 12);
  }
  *(_DWORD *)(a1 + 592) = 0;
  InfoRefreshTime = GetInfoRefreshTime(a1, &v16);
  v7 = v16;
  if ( InfoRefreshTime || v16 == -1 )
  {
    *(_QWORD *)(a1 + 8968) = 0;
    v8 = 0;
  }
  else
  {
    *(_DWORD *)(a1 + 496) = 1;
    v8 = ReConfigureParams;
    *(_QWORD *)(a1 + 8968) = v7;
  }
  ScheduleDhcpv6Renewal(a1, v7, v8);
  if ( !Reply )
  {
    if ( *(_DWORD *)&Dhcpv6GlobalUseNetworkHint )
    {
      if ( *(_QWORD *)(a1 + 8952) )
      {
        v9 = DhcpCacheScavanger(a1, 0);
        Reply = v9;
        if ( v9 )
        {
          if ( (xmmword_1800423E0 & 0x10) != 0 )
            WPP_SF_D(1028, 207, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, v9);
          Reply = 0;
        }
      }
    }
    Dhcpv6SaveInfoTime(a1);
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 208, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, Reply);
  return Reply;
}

```

## disassembly

```asm
0x180008a70  mov     r11, rsp
0x180008a73  push    rbx
0x180008a74  push    rsi
0x180008a75  push    rdi
0x180008a76  push    r13
0x180008a78  push    r15
0x180008a7a  sub     rsp, 120h
0x180008a81  xor     eax, eax
0x180008a83  mov     dword ptr [r11+10h], 0
0x180008a8b  mov     rbx, rcx
0x180008a8e  mov     [r11+8], ax
0x180008a93  lea     rcx, [rsp+148h+var_108]; void *
0x180008a98  mov     [r11+0Ah], al
0x180008a9c  xor     edx, edx; Val
0x180008a9e  mov     r8d, 0D4h; Size
0x180008aa4  call    memset_0
0x180008aa9  xor     esi, esi
0x180008aab  mov     [rsp+148h+arg_18], 0
0x180008ab7  mov     [rsp+148h+arg_10], esi
0x180008abe  mov     [rsp+148h+var_118], 0
0x180008ac7  mov     al, byte ptr cs:xmmword_1800423E0
0x180008acd  lea     r15, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180008ad4  mov     r13d, 404h
0x180008ada  test    al, 10h
0x180008adc  jz      short loc_180008B0C
0x180008ade  mov     r9, [rbx+38h]
0x180008ae2  mov     edx, 0CAh
0x180008ae7  mov     ecx, r13d
0x180008aea  mov     r8, r15
0x180008aed  call    WPP_SF_S
0x180008af2  mov     al, byte ptr cs:xmmword_1800423E0
0x180008af8  test    al, 10h
0x180008afa  jz      short loc_180008B0C
0x180008afc  mov     edx, 0CBh
0x180008b01  mov     ecx, r13d
0x180008b04  mov     r8, r15
0x180008b07  call    WPP_SF_
0x180008b0c  mov     r9d, 0Ch
0x180008b12  lea     rdx, [rsp+148h+arg_18]
0x180008b1a  mov     r8, rbx
0x180008b1d  lea     rcx, [rsp+148h+var_118]
0x180008b22  call    DhcpV6ActivateNetwork
0x180008b27  mov     edi, eax
0x180008b29  test    eax, eax
0x180008b2b  jnz     loc_180008C50
0x180008b31  lea     esi, [rax+1]
0x180008b34  cmp     [rbx+1F0h], eax
0x180008b3a  jz      short loc_180008B5F
0x180008b3c  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, sil
0x180008b43  jz      short loc_180008B55
0x180008b45  mov     r8d, [rbx+30h]
0x180008b49  lea     rdx, IRTExpired
0x180008b50  call    McTemplateU0q_EtwEventWriteTransfer
0x180008b55  mov     dword ptr [rbx+1F0h], 0
0x180008b5f  lea     rcx, [rsp+148h+arg_0]
0x180008b67  mov     [rbx+250h], esi
0x180008b6d  call    CreateDhcpv6TransactionId
0x180008b72  test    byte ptr cs:xmmword_1800423E0, 10h
0x180008b79  jz      short loc_180008B8B
0x180008b7b  mov     edx, 0CCh
0x180008b80  mov     ecx, r13d
0x180008b83  mov     r8, r15
0x180008b86  call    WPP_SF_
0x180008b8b  lea     r8, [rsp+148h+arg_8]
0x180008b93  mov     rcx, rbx
0x180008b96  lea     rdx, [rsp+148h+arg_0]
0x180008b9e  call    CreateDhcpv6InfoRequest
0x180008ba3  mov     edi, eax
0x180008ba5  test    eax, eax
0x180008ba7  jnz     loc_180008C50
0x180008bad  mov     edx, [rsp+148h+arg_8]
0x180008bb4  lea     r9, [rsp+148h+var_108]
0x180008bb9  lea     r8, [rsp+148h+arg_0]
0x180008bc1  mov     [rbx+2A4h], ax
0x180008bc8  mov     rcx, rbx
0x180008bcb  call    SendDhcpv6InfoRequestAndGetReply
0x180008bd0  mov     edi, eax
0x180008bd2  test    eax, eax
0x180008bd4  jnz     short loc_180008C50
0x180008bd6  mov     rax, cs:pDhcpv6GlobalIsShuttingDown
0x180008bdd  cmp     [rax], edi
0x180008bdf  jz      short loc_180008C06
0x180008be1  test    byte ptr cs:xmmword_1800423E0, 2
0x180008be8  jz      short loc_180008BFF
0x180008bea  mov     edx, 0CDh
0x180008bef  mov     ecx, 401h
0x180008bf4  xor     r9d, r9d
0x180008bf7  mov     r8, r15
0x180008bfa  call    WPP_SF_D
0x180008bff  mov     edi, 41h ; 'A'
0x180008c04  jmp     short loc_180008C50
0x180008c06  mov     eax, [rbx+298h]
0x180008c0c  lea     rcx, [rbx+278h]
0x180008c13  mov     r9, [rbx+290h]
0x180008c1a  mov     r8, [rbx+288h]
0x180008c21  mov     rdx, [rbx+38h]
0x180008c25  mov     [rsp+148h+var_128], eax
0x180008c29  call    Dhcpv6RegSaveOptions
0x180008c2e  mov     rcx, rbx
0x180008c31  call    Dhcpv6SaveNetworkHint
0x180008c36  xor     edx, edx
0x180008c38  mov     rcx, rbx
0x180008c3b  call    Dhcpv6RegisterWithDns
0x180008c40  xor     ecx, ecx
0x180008c42  test    eax, eax
0x180008c44  setnz   cl
0x180008c47  add     ecx, 2
0x180008c4a  mov     [rbx+22D8h], ecx
0x180008c50  lea     rcx, [rsp+148h+var_108]
0x180008c55  call    CleanupDhcpOptions
0x180008c5a  test    esi, esi
0x180008c5c  jz      short loc_180008C92
0x180008c5e  test    byte ptr cs:xmmword_1800423E0, 10h
0x180008c65  jz      short loc_180008C77
0x180008c67  mov     edx, 0CEh
0x180008c6c  mov     ecx, r13d
0x180008c6f  mov     r8, r15
0x180008c72  call    WPP_SF_
0x180008c77  mov     r9d, 0Ch
0x180008c7d  lea     rdx, [rsp+148h+arg_18]
0x180008c85  mov     r8, rbx
0x180008c88  lea     rcx, [rsp+148h+var_118]
0x180008c8d  call    DhcpV6DeactivateNetwork
0x180008c92  lea     rdx, [rsp+148h+arg_10]
0x180008c9a  mov     dword ptr [rbx+250h], 0
0x180008ca4  mov     rcx, rbx
0x180008ca7  call    GetInfoRefreshTime
0x180008cac  movsxd  rdx, [rsp+148h+arg_10]
0x180008cb4  test    eax, eax
0x180008cb6  jnz     short loc_180008CD7
0x180008cb8  cmp     edx, 0FFFFFFFFh
0x180008cbb  jnb     short loc_180008CD7
0x180008cbd  mov     dword ptr [rbx+1F0h], 1
0x180008cc7  lea     r8, ReConfigureParams
0x180008cce  mov     [rbx+2308h], rdx
0x180008cd5  jmp     short loc_180008CE5
0x180008cd7  mov     qword ptr [rbx+2308h], 0
0x180008ce2  xor     r8d, r8d
0x180008ce5  mov     rcx, rbx
0x180008ce8  call    ScheduleDhcpv6Renewal
0x180008ced  test    edi, edi
0x180008cef  jnz     short loc_180008D39
0x180008cf1  cmp     cs:Dhcpv6GlobalUseNetworkHint, edi
0x180008cf7  jz      short loc_180008D31
0x180008cf9  cmp     qword ptr [rbx+22F8h], 0
0x180008d01  jz      short loc_180008D31
0x180008d03  xor     edx, edx
0x180008d05  mov     rcx, rbx
0x180008d08  call    DhcpCacheScavanger
0x180008d0d  mov     edi, eax
0x180008d0f  test    eax, eax
0x180008d11  jz      short loc_180008D31
0x180008d13  test    byte ptr cs:xmmword_1800423E0, 10h
0x180008d1a  jz      short loc_180008D2F
0x180008d1c  mov     edx, 0CFh
0x180008d21  mov     ecx, r13d
0x180008d24  mov     r9d, eax
0x180008d27  mov     r8, r15
0x180008d2a  call    WPP_SF_D
0x180008d2f  xor     edi, edi
0x180008d31  mov     rcx, rbx
0x180008d34  call    Dhcpv6SaveInfoTime
0x180008d39  test    byte ptr cs:xmmword_1800423E0, 10h
0x180008d40  jz      short loc_180008D55
0x180008d42  mov     edx, 0D0h
0x180008d47  mov     ecx, r13d
0x180008d4a  mov     r9d, edi
0x180008d4d  mov     r8, r15
0x180008d50  call    WPP_SF_D
0x180008d55  mov     eax, edi
0x180008d57  add     rsp, 120h
0x180008d5e  pop     r15
0x180008d60  pop     r13
0x180008d62  pop     rdi
0x180008d63  pop     rsi
0x180008d64  pop     rbx
0x180008d65  retn
```
