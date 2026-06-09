# ReadClientDUID

- ea: `0x180016658`
- end: `0x180016908`
- name: `ReadClientDUID`
- size: `688`
- prototype: `__int64 __fastcall(__int64, DWORD *, BYTE **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18001564c`

## callees

- `0x180007564`
- `0x18000c740`
- `0x180016658`
- `0x18002a454`
- `0x18002a8ec`
- `0x18002dce8`
- `0x180032ab8`
- `0x1800338c0`
- `0x180033900`
- `0x180034500`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016756`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800167be`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016756`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800167be`

## pseudocode

```c
__int64 __fastcall ReadClientDUID(__int64 a1, DWORD *a2, BYTE **a3)
{
  HKEY v3; // rsi
  unsigned int v6; // eax
  int v7; // edx
  int v8; // ecx
  int v9; // r8d
  BYTE *v10; // rbx
  DWORD v11; // r9d
  unsigned int v12; // edi
  BYTE *lpData; // rax
  __int64 v14; // rdx
  unsigned int v15; // eax
  unsigned int BooleanDwordValue; // eax
  __int128 v18; // [rsp+40h] [rbp-20h] BYREF
  __int128 v19; // [rsp+50h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+30h] BYREF
  int v21; // [rsp+94h] [rbp+34h]
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF

  v21 = HIDWORD(a1);
  v3 = Dhcpv6GlobalTcpipParametersKey;
  cbData = 0;
  Type = 0;
  *(_QWORD *)&v18 = 0;
  v6 = ReadDUIDOverride(&v18, &cbData);
  if ( !v6 )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_(1028, 16, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids);
    v10 = (BYTE *)v18;
    goto LABEL_5;
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 17, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, v6);
  cbData = 0;
  if ( RegQueryValueExW(v3, L"Dhcpv6DUID", 0, &Type, 0, &cbData) || cbData - 1 > 0x7F )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
    {
      v14 = 18;
      goto LABEL_32;
    }
LABEL_33:
    v12 = 0;
    *a2 = 0;
    *a3 = 0;
    return v12;
  }
  lpData = (BYTE *)DhcpAlloc(cbData);
  *(_QWORD *)&v18 = lpData;
  v10 = lpData;
  if ( !lpData )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
    {
      v14 = 19;
LABEL_32:
      WPP_SF_(1025, v14, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids);
      goto LABEL_33;
    }
    goto LABEL_33;
  }
  v15 = RegQueryValueExW(v3, L"Dhcpv6DUID", 0, &Type, lpData, &cbData);
  if ( v15 )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_D(1025, 20, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, v15);
LABEL_26:
    DhcpFree(&v18);
    goto LABEL_33;
  }
  BooleanDwordValue = DhcpRegQueryBooleanDwordValue(v3, L"Dhcpv6EnableDUIDUUID");
  if ( (BooleanDwordValue & 0xFFFFFFFD) != 0 )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_D(1025, 21, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, BooleanDwordValue);
    goto LABEL_33;
  }
  if ( (unsigned int)Dhcpv6MatchDUIDTypes(v10, cbData, 4) )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
    {
      *((_QWORD *)&v19 + 1) = 0xFFFF;
      *(_QWORD *)&v19 = v10;
      if ( cbData <= 0xFFFF )
        WORD4(v19) = cbData;
      WPP_SF__HEX_(1025, 22, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, &v19);
    }
    goto LABEL_26;
  }
LABEL_5:
  v11 = cbData;
  v12 = 1;
  *a2 = cbData;
  *a3 = v10;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    v18 = (unsigned __int64)v10;
    if ( v10 )
    {
      WORD4(v18) = -1;
      if ( v11 <= 0xFFFF )
        WORD4(v18) = v11;
    }
    else
    {
      WORD4(v18) = 0;
    }
    v19 = v18;
    WPP_SF_d_HEX_(v8, v7, v9, v11, (__int64)&v19);
  }
  return v12;
}

```

## disassembly

```asm
0x180016658  mov     [rsp-28h+arg_8], rbx
0x18001665d  mov     qword ptr [rsp-28h+cbData], rcx
0x180016662  push    rbp
0x180016663  push    rsi
0x180016664  push    rdi
0x180016665  push    r14
0x180016667  push    r15
0x180016669  mov     rbp, rsp
0x18001666c  sub     rsp, 60h
0x180016670  mov     rsi, cs:Dhcpv6GlobalTcpipParametersKey
0x180016677  lea     rcx, [rbp+var_20]
0x18001667b  mov     r15, rdx
0x18001667e  mov     [rbp+cbData], 0
0x180016685  lea     rdx, [rbp+cbData]
0x180016689  mov     [rbp+Type], 0
0x180016690  mov     r14, r8
0x180016693  mov     [rbp+var_30], 0
0x18001669a  mov     qword ptr [rbp+var_20], 0
0x1800166a2  call    ReadDUIDOverride
0x1800166a7  test    eax, eax
0x1800166a9  jnz     short loc_180016707
0x1800166ab  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800166b2  jz      short loc_1800166C8
0x1800166b4  lea     edx, [rax+10h]
0x1800166b7  mov     ecx, 404h
0x1800166bc  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x1800166c3  call    WPP_SF_
0x1800166c8  mov     rbx, qword ptr [rbp+var_20]
0x1800166cc  mov     r9d, [rbp+cbData]
0x1800166d0  mov     edi, 1
0x1800166d5  mov     [r15], r9d
0x1800166d8  mov     [r14], rbx
0x1800166db  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800166e2  jz      loc_1800168F1
0x1800166e8  xorps   xmm0, xmm0
0x1800166eb  movups  [rbp+var_20], xmm0
0x1800166ef  mov     qword ptr [rbp+var_20], rbx
0x1800166f3  test    rbx, rbx
0x1800166f6  jnz     loc_1800168A2
0x1800166fc  xor     eax, eax
0x1800166fe  mov     word ptr [rbp+var_20+8], ax
0x180016702  jmp     loc_1800168B5
0x180016707  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001670e  lea     rdi, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x180016715  jz      short loc_18001672C
0x180016717  mov     edx, 11h
0x18001671c  mov     ecx, 404h
0x180016721  mov     r9d, eax
0x180016724  mov     r8, rdi
0x180016727  call    WPP_SF_D
0x18001672c  lea     rax, [rbp+cbData]
0x180016730  mov     [rbp+cbData], 0
0x180016737  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18001673c  lea     r9, [rbp+Type]; lpType
0x180016740  xor     r8d, r8d; lpReserved
0x180016743  mov     [rsp+60h+lpData], 0; lpData
0x18001674c  lea     rdx, aDhcpv6duid; "Dhcpv6DUID"
0x180016753  mov     rcx, rsi; hKey
0x180016756  call    cs:__imp_RegQueryValueExW
0x18001675d  nop     dword ptr [rax+rax+00h]
0x180016762  test    eax, eax
0x180016764  jnz     loc_1800168CE
0x18001676a  mov     ecx, [rbp+cbData]
0x18001676d  lea     eax, [rcx-1]
0x180016770  cmp     eax, 7Fh
0x180016773  ja      loc_1800168CE
0x180016779  call    DhcpAlloc
0x18001677e  mov     qword ptr [rbp+var_20], rax
0x180016782  mov     rbx, rax
0x180016785  test    rax, rax
0x180016788  jnz     short loc_18001679F
0x18001678a  test    byte ptr cs:xmmword_1800423E0, 2
0x180016791  jz      loc_1800168E9
0x180016797  lea     edx, [rax+13h]
0x18001679a  jmp     loc_1800168DC
0x18001679f  lea     rax, [rbp+cbData]
0x1800167a3  xor     r8d, r8d; lpReserved
0x1800167a6  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1800167ab  lea     r9, [rbp+Type]; lpType
0x1800167af  lea     rdx, aDhcpv6duid; "Dhcpv6DUID"
0x1800167b6  mov     [rsp+60h+lpData], rbx; lpData
0x1800167bb  mov     rcx, rsi; hKey
0x1800167be  call    cs:__imp_RegQueryValueExW
0x1800167c5  nop     dword ptr [rax+rax+00h]
0x1800167ca  test    eax, eax
0x1800167cc  jz      short loc_1800167F5
0x1800167ce  test    byte ptr cs:xmmword_1800423E0, 2
0x1800167d5  jz      loc_180016897
0x1800167db  mov     edx, 14h
0x1800167e0  mov     ecx, 401h
0x1800167e5  mov     r9d, eax
0x1800167e8  mov     r8, rdi
0x1800167eb  call    WPP_SF_D
0x1800167f0  jmp     loc_180016897
0x1800167f5  lea     r8, [rbp+var_30]
0x1800167f9  mov     rcx, rsi; hKey
0x1800167fc  lea     rdx, aDhcpv6enabledu; "Dhcpv6EnableDUIDUUID"
0x180016803  call    DhcpRegQueryBooleanDwordValue
0x180016808  test    eax, 0FFFFFFFDh
0x18001680d  jz      short loc_180016836
0x18001680f  test    byte ptr cs:xmmword_1800423E0, 2
0x180016816  jz      loc_1800168E9
0x18001681c  mov     edx, 15h
0x180016821  mov     ecx, 401h
0x180016826  mov     r9d, eax
0x180016829  mov     r8, rdi
0x18001682c  call    WPP_SF_D
0x180016831  jmp     loc_1800168E9
0x180016836  mov     edx, [rbp+cbData]
0x180016839  mov     r8d, 4
0x18001683f  mov     rcx, rbx
0x180016842  call    Dhcpv6MatchDUIDTypes
0x180016847  cmp     [rbp+var_30], eax
0x18001684a  jz      loc_1800166CC
0x180016850  test    byte ptr cs:xmmword_1800423E0, 2
0x180016857  jz      short loc_180016897
0x180016859  mov     ecx, [rbp+cbData]
0x18001685c  mov     eax, 0FFFFh
0x180016861  xorps   xmm0, xmm0
0x180016864  movups  [rbp+var_10], xmm0
0x180016868  mov     qword ptr [rbp+var_10], rbx
0x18001686c  mov     word ptr [rbp+var_10+8], ax
0x180016870  cmp     ecx, eax
0x180016872  ja      short loc_180016878
0x180016874  mov     word ptr [rbp+var_10+8], cx
0x180016878  movaps  xmm0, [rbp+var_10]
0x18001687c  lea     r9, [rbp+var_10]
0x180016880  mov     edx, 16h
0x180016885  movdqa  [rbp+var_10], xmm0
0x18001688a  mov     ecx, 401h
0x18001688f  mov     r8, rdi
0x180016892  call    WPP_SF__HEX_
0x180016897  lea     rcx, [rbp+var_20]
0x18001689b  call    DhcpFree
0x1800168a0  jmp     short loc_1800168E9
0x1800168a2  mov     eax, 0FFFFh
0x1800168a7  mov     word ptr [rbp+var_20+8], ax
0x1800168ab  cmp     r9d, eax
0x1800168ae  ja      short loc_1800168B5
0x1800168b0  mov     word ptr [rbp+var_20+8], r9w
0x1800168b5  movaps  xmm0, [rbp+var_20]
0x1800168b9  lea     rax, [rbp+var_10]
0x1800168bd  movdqa  [rbp+var_10], xmm0
0x1800168c2  mov     [rsp+60h+lpData], rax
0x1800168c7  call    WPP_SF_d_HEX_
0x1800168cc  jmp     short loc_1800168F1
0x1800168ce  test    byte ptr cs:xmmword_1800423E0, 2
0x1800168d5  jz      short loc_1800168E9
0x1800168d7  mov     edx, 12h
0x1800168dc  mov     r8, rdi
0x1800168df  mov     ecx, 401h
0x1800168e4  call    WPP_SF_
0x1800168e9  xor     edi, edi
0x1800168eb  mov     [r15], edi
0x1800168ee  mov     [r14], rdi
0x1800168f1  mov     rbx, [rsp+60h+arg_8]
0x1800168f9  mov     eax, edi
0x1800168fb  add     rsp, 60h
0x1800168ff  pop     r15
0x180016901  pop     r14
0x180016903  pop     rdi
0x180016904  pop     rsi
0x180016905  pop     rbp
0x180016906  retn
```
