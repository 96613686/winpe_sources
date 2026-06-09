# ReadClientID

- ea: `0x1800046b0`
- end: `0x1800048c3`
- name: `ReadClientID`
- size: `531`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800048cc`
- `0x18001ade4`

## callees

- `0x1800046b0`
- `0x1800057f0`
- `0x180006440`
- `0x18004b790`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d9e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004701`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004760`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004828`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004701`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004760`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004828`

## pseudocode

```c
__int64 __fastcall ReadClientID(HKEY hKey, _BYTE *a2, DWORD *a3, _QWORD *a4)
{
  unsigned int v8; // edi
  __int64 v10; // rdx
  void *lpData; // rax
  void *v12; // rbx
  unsigned int v13; // eax
  int v14; // r8d
  BYTE v15; // cl
  DWORD v16; // eax
  DWORD cbData; // [rsp+30h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-24h] BYREF
  DWORD Type; // [rsp+38h] [rbp-20h] BYREF
  LPVOID v20; // [rsp+40h] [rbp-18h] BYREF
  __int64 v21; // [rsp+48h] [rbp-10h]

  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"DhcpClientIdentifierType", 0, &Type, Data, &cbData) )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_(1025, 27, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
    *(_DWORD *)Data = 0;
  }
  else if ( Type != 4 || *(_DWORD *)Data > 0xFFu )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_d(1025, 28, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, *(unsigned int *)Data);
    goto LABEL_7;
  }
  cbData = 0;
  if ( RegQueryValueExW(hKey, L"DhcpClientIdentifier", 0, 0, 0, &cbData) || cbData - 1 > 0xFD )
  {
    if ( (xmmword_1800616A0 & 2) == 0 )
    {
LABEL_7:
      v8 = 0;
      *a2 = 0;
      *a3 = 0;
      *a4 = 0;
      return v8;
    }
    v10 = 29;
LABEL_10:
    WPP_SF_(1025, v10, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
    goto LABEL_7;
  }
  lpData = DhcpAlloc(cbData);
  v20 = lpData;
  v12 = lpData;
  if ( !lpData )
  {
    if ( (xmmword_1800616A0 & 2) == 0 )
      goto LABEL_7;
    v10 = 30;
    goto LABEL_10;
  }
  v13 = RegQueryValueExW(hKey, L"DhcpClientIdentifier", 0, 0, (LPBYTE)lpData, &cbData);
  if ( v13 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 31, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v13);
    DhcpPunycodeFree(&v20);
    goto LABEL_7;
  }
  v15 = Data[0];
  v8 = 1;
  v16 = cbData;
  *a2 = Data[0];
  *a3 = v16;
  *a4 = v12;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
  {
    v21 = 0xFFFF;
    v20 = v12;
    if ( v16 <= 0xFFFF )
      LOWORD(v21) = v16;
    WPP_SF_Dd_HEX_((unsigned int)&v20, 0xFFFF, v14, v15, v16, (__int64)&v20);
  }
  return v8;
}

```

## disassembly

```asm
0x1800046b0  push    rbp
0x1800046b2  push    rbx
0x1800046b3  push    rsi
0x1800046b4  push    rdi
0x1800046b5  push    r14
0x1800046b7  push    r15
0x1800046b9  mov     rbp, rsp
0x1800046bc  sub     rsp, 58h
0x1800046c0  lea     rax, [rbp+cbData]
0x1800046c4  mov     [rbp+Type], 0
0x1800046cb  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800046d0  mov     rsi, r9
0x1800046d3  lea     rax, [rbp+Data]
0x1800046d7  mov     dword ptr [rbp+Data], 0
0x1800046de  mov     r14, r8
0x1800046e1  mov     [rsp+58h+lpData], rax; lpData
0x1800046e6  mov     r15, rdx
0x1800046e9  mov     [rbp+cbData], 4
0x1800046f0  lea     r9, [rbp+Type]; lpType
0x1800046f4  xor     r8d, r8d; lpReserved
0x1800046f7  lea     rdx, aDhcpclientiden; "DhcpClientIdentifierType"
0x1800046fe  mov     rdi, rcx
0x180004701  call    cs:__imp_RegQueryValueExW
0x180004707  mov     ebx, 401h
0x18000470c  test    eax, eax
0x18000470e  jz      loc_1800047A2
0x180004714  test    byte ptr cs:xmmword_1800616A0, 2
0x18000471b  jz      short loc_180004730
0x18000471d  mov     edx, 1Bh
0x180004722  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180004729  mov     ecx, ebx
0x18000472b  call    WPP_SF_
0x180004730  mov     dword ptr [rbp+Data], 0
0x180004737  lea     rax, [rbp+cbData]
0x18000473b  mov     [rbp+cbData], 0
0x180004742  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180004747  lea     rdx, aDhcpclientiden_0; "DhcpClientIdentifier"
0x18000474e  xor     r9d, r9d; lpType
0x180004751  mov     [rsp+58h+lpData], 0; lpData
0x18000475a  xor     r8d, r8d; lpReserved
0x18000475d  mov     rcx, rdi; hKey
0x180004760  call    cs:__imp_RegQueryValueExW
0x180004766  test    eax, eax
0x180004768  jz      short loc_1800047D3
0x18000476a  test    byte ptr cs:xmmword_1800616A0, 2
0x180004771  jnz     short loc_18000478D
0x180004773  xor     edi, edi
0x180004775  mov     [r15], dil
0x180004778  mov     [r14], edi
0x18000477b  mov     [rsi], rdi
0x18000477e  mov     eax, edi
0x180004780  add     rsp, 58h
0x180004784  pop     r15
0x180004786  pop     r14
0x180004788  pop     rdi
0x180004789  pop     rsi
0x18000478a  pop     rbx
0x18000478b  pop     rbp
0x18000478c  retn
0x18000478d  mov     edx, 1Dh
0x180004792  mov     ecx, ebx
0x180004794  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x18000479b  call    WPP_SF_
0x1800047a0  jmp     short loc_180004773
0x1800047a2  cmp     [rbp+Type], 4
0x1800047a6  mov     r9d, dword ptr [rbp+Data]
0x1800047aa  jnz     short loc_1800047B5
0x1800047ac  cmp     r9d, 0FFh
0x1800047b3  jbe     short loc_180004737
0x1800047b5  test    byte ptr cs:xmmword_1800616A0, 2
0x1800047bc  jz      short loc_180004773
0x1800047be  mov     edx, 1Ch
0x1800047c3  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x1800047ca  mov     ecx, ebx
0x1800047cc  call    WPP_SF_d
0x1800047d1  jmp     short loc_180004773
0x1800047d3  mov     edx, [rbp+cbData]
0x1800047d6  lea     eax, [rdx-1]
0x1800047d9  cmp     eax, 0FDh
0x1800047de  ja      short loc_18000476A
0x1800047e0  mov     ecx, edx
0x1800047e2  call    DhcpAlloc
0x1800047e7  mov     qword ptr [rbp+var_18], rax
0x1800047eb  mov     rbx, rax
0x1800047ee  test    rax, rax
0x1800047f1  jnz     short loc_18000480A
0x1800047f3  test    byte ptr cs:xmmword_1800616A0, 2
0x1800047fa  jz      loc_180004773
0x180004800  lea     edx, [rax+1Eh]
0x180004803  mov     ecx, 401h
0x180004808  jmp     short loc_180004794
0x18000480a  lea     rax, [rbp+cbData]
0x18000480e  xor     r9d, r9d; lpType
0x180004811  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180004816  lea     rdx, aDhcpclientiden_0; "DhcpClientIdentifier"
0x18000481d  xor     r8d, r8d; lpReserved
0x180004820  mov     [rsp+58h+lpData], rbx; lpData
0x180004825  mov     rcx, rdi; hKey
0x180004828  call    cs:__imp_RegQueryValueExW
0x18000482e  test    eax, eax
0x180004830  jz      short loc_180004862
0x180004832  test    byte ptr cs:xmmword_1800616A0, 2
0x180004839  jz      short loc_180004854
0x18000483b  mov     edx, 1Fh
0x180004840  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180004847  mov     ecx, 401h
0x18000484c  mov     r9d, eax
0x18000484f  call    WPP_SF_D
0x180004854  lea     rcx, [rbp+var_18]
0x180004858  call    DhcpPunycodeFree
0x18000485d  jmp     loc_180004773
0x180004862  mov     ecx, dword ptr [rbp+Data]
0x180004865  mov     edi, 1
0x18000486a  mov     eax, [rbp+cbData]
0x18000486d  mov     [r15], cl
0x180004870  mov     [r14], eax
0x180004873  mov     [rsi], rbx
0x180004876  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000487d  jz      loc_18000477E
0x180004883  mov     edx, 0FFFFh
0x180004888  xorps   xmm0, xmm0
0x18000488b  movups  [rbp+var_18], xmm0
0x18000488f  mov     qword ptr [rbp+var_18], rbx
0x180004893  mov     word ptr [rbp+var_18+8], dx
0x180004897  cmp     eax, edx
0x180004899  ja      short loc_18000489F
0x18000489b  mov     word ptr [rbp+var_18+8], ax
0x18000489f  movaps  xmm0, [rbp+var_18]
0x1800048a3  movzx   r9d, cl
0x1800048a7  lea     rcx, [rbp+var_18]
0x1800048ab  mov     [rsp+58h+lpcbData], rcx
0x1800048b0  mov     dword ptr [rsp+58h+lpData], eax
0x1800048b4  movdqa  [rbp+var_18], xmm0
0x1800048b9  call    WPP_SF_Dd_HEX_
0x1800048be  jmp     loc_18000477E
```
