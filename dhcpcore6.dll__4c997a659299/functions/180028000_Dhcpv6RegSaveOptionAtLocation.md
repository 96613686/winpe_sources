# Dhcpv6RegSaveOptionAtLocation

- ea: `0x180028000`
- end: `0x180028363`
- name: `Dhcpv6RegSaveOptionAtLocation`
- size: `867`
- prototype: `LSTATUS __fastcall(__int64, const wchar_t *, DWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x18000812c`

## callees

- `0x180006d58`
- `0x1800077e0`
- `0x180007a80`
- `0x180019ad0`
- `0x18001dfb4`
- `0x180028000`
- `0x1800304d4`
- `0x18003098c`
- `0x180033900`
- `0x180033970`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180028055`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180028055`
- `ntdll!RtlInitString` at `0x1800281ff`
- `ntdll!RtlInitString` at `0x1800281ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002808f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002808f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800280b5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800280b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800280c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028309`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800280c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180028309`

## pseudocode

```c
LSTATUS __fastcall Dhcpv6RegSaveOptionAtLocation(__int64 a1, const wchar_t *a2, DWORD a3)
{
  wchar_t *v6; // rax
  const WCHAR *v7; // r15
  LSTATUS result; // eax
  int v9; // ebx
  unsigned int v10; // edx
  DWORD v11; // edi
  __int64 v12; // rdx
  const BYTE *p_Buf2; // rsi
  _BYTE *v14; // rdi
  __int64 v15; // rdx
  __int64 v16; // rbx
  const wchar_t *v17; // rax
  size_t v18; // rdx
  HRESULT v19; // eax
  int v20; // edi
  unsigned __int64 v21; // rcx
  int Buf2; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  size_t pcchLength; // [rsp+40h] [rbp-C0h] BYREF
  struct _STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v26[512]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v27[1008]; // [rsp+260h] [rbp+160h] BYREF

  hKey = 0;
  Buf2 = 0;
  v6 = wcsrchr(a2, 0x5Cu);
  v7 = v6;
  if ( v6 )
  {
    *v6 = 0;
    v7 = v6 + 1;
  }
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0xFu, &hKey);
  v9 = result;
  if ( !result )
  {
    v10 = *(_DWORD *)(a1 + 56);
    if ( !v10 )
    {
      v9 = RegDeleteValueW(hKey, v7);
      RegCloseKey(hKey);
      return v9;
    }
    if ( a3 != 1 && a3 != 7 )
    {
      v11 = 4;
      if ( a3 == 4 )
      {
        if ( v10 != 4 )
        {
          if ( (xmmword_1800423E0 & 2) == 0 )
            goto LABEL_48;
          v12 = 21;
LABEL_39:
          WPP_SF_(1025, v12, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids);
          goto LABEL_48;
        }
        p_Buf2 = (const BYTE *)&Buf2;
        Buf2 = **(_DWORD **)(a1 + 48);
      }
      else
      {
        p_Buf2 = *(const BYTE **)(a1 + 48);
        v11 = *(_DWORD *)(a1 + 56);
      }
      goto LABEL_43;
    }
    if ( *(_WORD *)(a1 + 16) == 39 )
    {
      p_Buf2 = 0;
      v11 = 0;
      if ( v10 > 1 && !(unsigned int)DhcpGetUnicodeNameFromWireName(*(_QWORD *)(a1 + 48) + 1LL, v10 - 1, v27) )
      {
        for ( p_Buf2 = v27; v27 > p_Buf2; p_Buf2 += 2 )
        {
          if ( *(_WORD *)p_Buf2 == 46 )
          {
            p_Buf2 += 2;
            break;
          }
        }
        v11 = 2 * ((v27 - p_Buf2) >> 1);
      }
      goto LABEL_43;
    }
    v14 = *(_BYTE **)(a1 + 48);
    if ( v10 >= 0x1F4 )
      v10 = 499;
    if ( v14[v10 - 1] )
    {
      v16 = v10;
      memcpy_0(v26, v14, v10);
      v26[v16] = 0;
      v14 = v26;
    }
    else if ( !v14 )
    {
      if ( (xmmword_1800423E0 & 2) != 0 )
      {
        v15 = 17;
LABEL_46:
        WPP_SF_(1025, v15, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids);
        goto LABEL_47;
      }
      goto LABEL_47;
    }
    DestinationString = 0;
    RtlInitString(&DestinationString, v14);
    v17 = (const wchar_t *)Dhcpv6OemToUnicodeN(v14);
    p_Buf2 = (const BYTE *)v17;
    if ( v17 )
    {
      pcchLength = 0;
      v19 = StringCchLengthW(v17, v18, &pcchLength);
      if ( v19 >= 0 )
      {
        v20 = pcchLength;
      }
      else
      {
        v20 = 0;
        HIDWORD(pcchLength) = 81;
      }
      v9 = WX_WIN32_FROM_HR((unsigned int)v19);
      if ( v9 )
      {
        if ( (xmmword_1800423E0 & 2) == 0 )
          goto LABEL_48;
        v12 = 19;
        goto LABEL_39;
      }
      v21 = 2LL * (unsigned int)(v20 + 2);
      *(_WORD *)&p_Buf2[v21] = 0;
      if ( v21 <= 0xFFFFFFFF )
      {
        v11 = 2 * (v20 + 2);
        if ( a3 == 1 )
          v11 = v21 - 2;
LABEL_43:
        v9 = Dhcpv6RegSetOptionRegVal(hKey, v7, a3, p_Buf2, v11);
        goto LABEL_48;
      }
      if ( (xmmword_1800423E0 & 2) != 0 )
      {
        v15 = 20;
        goto LABEL_46;
      }
    }
    else if ( (xmmword_1800423E0 & 2) != 0 )
    {
      v15 = 18;
      goto LABEL_46;
    }
LABEL_47:
    v9 = 87;
LABEL_48:
    RegCloseKey(hKey);
    if ( v9 )
    {
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_SD(1025, 22, (unsigned int)WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids, (_DWORD)v7, v9);
    }
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180028000  push    rbp
0x180028002  push    rbx
0x180028003  push    rsi
0x180028004  push    rdi
0x180028005  push    r12
0x180028007  push    r14
0x180028009  push    r15
0x18002800b  lea     rbp, [rsp-560h]
0x180028013  sub     rsp, 660h
0x18002801a  mov     rax, cs:__security_cookie
0x180028021  xor     rax, rsp
0x180028024  mov     [rbp+590h+var_40], rax
0x18002802b  mov     rbx, rdx
0x18002802e  mov     [rsp+690h+hKey], 0
0x180028037  mov     r14, rcx
0x18002803a  mov     [rsp+690h+Buf2], 0
0x180028042  mov     rcx, rbx; Str
0x180028045  mov     [rsp+690h+var_660], 0
0x18002804d  mov     edx, 5Ch ; '\'; Ch
0x180028052  mov     r12d, r8d
0x180028055  call    cs:__imp_wcsrchr
0x18002805c  nop     dword ptr [rax+rax+00h]
0x180028061  mov     r15, rax
0x180028064  test    rax, rax
0x180028067  jz      short loc_180028072
0x180028069  xor     ecx, ecx
0x18002806b  mov     [rax], cx
0x18002806e  add     r15, 2
0x180028072  lea     rax, [rsp+690h+hKey]
0x180028077  mov     r9d, 0Fh; samDesired
0x18002807d  xor     r8d, r8d; ulOptions
0x180028080  mov     [rsp+690h+phkResult], rax; phkResult
0x180028085  mov     rdx, rbx; lpSubKey
0x180028088  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002808f  call    cs:__imp_RegOpenKeyExW
0x180028096  nop     dword ptr [rax+rax+00h]
0x18002809b  mov     ebx, eax
0x18002809d  test    eax, eax
0x18002809f  jnz     loc_180028341
0x1800280a5  mov     edx, [r14+38h]
0x1800280a9  test    edx, edx
0x1800280ab  jnz     short loc_1800280D9
0x1800280ad  mov     rcx, [rsp+690h+hKey]; hKey
0x1800280b2  mov     rdx, r15; lpValueName
0x1800280b5  call    cs:__imp_RegDeleteValueW
0x1800280bc  nop     dword ptr [rax+rax+00h]
0x1800280c1  mov     rcx, [rsp+690h+hKey]; hKey
0x1800280c6  mov     ebx, eax
0x1800280c8  call    cs:__imp_RegCloseKey
0x1800280cf  nop     dword ptr [rax+rax+00h]
0x1800280d4  jmp     loc_18002833F
0x1800280d9  cmp     r12d, 1
0x1800280dd  jz      short loc_180028127
0x1800280df  cmp     r12d, 7
0x1800280e3  jz      short loc_180028127
0x1800280e5  mov     edi, 4
0x1800280ea  cmp     r12d, edi
0x1800280ed  jnz     short loc_18002811C
0x1800280ef  cmp     edx, edi
0x1800280f1  jz      short loc_180028108
0x1800280f3  test    byte ptr cs:xmmword_1800423E0, 2
0x1800280fa  jz      loc_180028304
0x180028100  lea     edx, [rdi+11h]
0x180028103  jmp     loc_180028291
0x180028108  mov     rax, [r14+30h]
0x18002810c  lea     rsi, [rsp+690h+Buf2]
0x180028111  mov     ecx, [rax]
0x180028113  mov     [rsp+690h+Buf2], ecx
0x180028117  jmp     loc_1800282C5
0x18002811c  mov     rsi, [r14+30h]
0x180028120  mov     edi, edx
0x180028122  jmp     loc_1800282C5
0x180028127  mov     eax, 27h ; '''
0x18002812c  cmp     ax, [r14+10h]
0x180028131  jnz     short loc_18002819F
0x180028133  xor     esi, esi
0x180028135  xor     edi, edi
0x180028137  cmp     edx, 1
0x18002813a  jbe     loc_1800282C5
0x180028140  mov     rcx, [r14+30h]
0x180028144  lea     rax, [rsp+690h+var_660]
0x180028149  inc     rcx
0x18002814c  mov     [rsp+690h+phkResult], rax
0x180028151  dec     edx
0x180028153  lea     r8, [rbp+590h+var_430]
0x18002815a  call    DhcpGetUnicodeNameFromWireName
0x18002815f  test    eax, eax
0x180028161  jnz     loc_1800282C5
0x180028167  mov     eax, [rsp+690h+var_660]
0x18002816b  lea     rdi, [rbp+590h+var_430]
0x180028172  lea     rsi, [rbp+590h+var_430]
0x180028179  lea     rdi, [rdi+rax*2]
0x18002817d  cmp     rdi, rsi
0x180028180  jbe     short loc_180028192
0x180028182  cmp     word ptr [rsi], 2Eh ; '.'
0x180028186  jz      short loc_18002818E
0x180028188  add     rsi, 2
0x18002818c  jmp     short loc_18002817D
0x18002818e  add     rsi, 2
0x180028192  sub     rdi, rsi
0x180028195  sar     rdi, 1
0x180028198  add     edi, edi
0x18002819a  jmp     loc_1800282C5
0x18002819f  mov     rdi, [r14+30h]
0x1800281a3  mov     eax, 1F3h
0x1800281a8  lea     esi, [rax+1]
0x1800281ab  cmp     edx, esi
0x1800281ad  cmovnb  edx, eax
0x1800281b0  lea     eax, [rdx-1]
0x1800281b3  cmp     byte ptr [rax+rdi], 0
0x1800281b7  jnz     short loc_1800281D3
0x1800281b9  test    rdi, rdi
0x1800281bc  jnz     short loc_1800281EF
0x1800281be  test    byte ptr cs:xmmword_1800423E0, 2
0x1800281c5  jz      loc_1800282FF
0x1800281cb  lea     edx, [rdi+11h]
0x1800281ce  jmp     loc_1800282EE
0x1800281d3  mov     ebx, edx
0x1800281d5  lea     rcx, [rsp+690h+var_630]; void *
0x1800281da  mov     r8d, edx; Size
0x1800281dd  mov     rdx, rdi; Src
0x1800281e0  call    memcpy_0
0x1800281e5  mov     [rsp+rbx+690h+var_630], 0
0x1800281ea  lea     rdi, [rsp+690h+var_630]
0x1800281ef  xorps   xmm0, xmm0
0x1800281f2  lea     rcx, [rsp+690h+DestinationString]; DestinationString
0x1800281f7  mov     rdx, rdi; SourceString
0x1800281fa  movups  xmmword ptr [rsp+690h+DestinationString.Length], xmm0
0x1800281ff  call    cs:__imp_RtlInitString
0x180028206  nop     dword ptr [rax+rax+00h]
0x18002820b  mov     r8d, esi
0x18002820e  lea     rdx, [rbp+590h+var_430]
0x180028215  mov     rcx, rdi; SourceString
0x180028218  call    Dhcpv6OemToUnicodeN
0x18002821d  mov     rsi, rax
0x180028220  test    rax, rax
0x180028223  jnz     short loc_18002823A
0x180028225  test    byte ptr cs:xmmword_1800423E0, 2
0x18002822c  jz      loc_1800282FF
0x180028232  lea     edx, [rax+12h]
0x180028235  jmp     loc_1800282EE
0x18002823a  mov     dword ptr [rsp+690h+pcchLength+4], 0
0x180028242  lea     r8, [rsp+690h+pcchLength]; pcchLength
0x180028247  mov     rcx, rsi; psz
0x18002824a  mov     [rsp+690h+pcchLength], 0
0x180028253  mov     [rsp+690h+var_660], 0
0x18002825b  call    StringCchLengthW
0x180028260  test    eax, eax
0x180028262  jns     short loc_180028272
0x180028264  mov     edi, [rsp+690h+var_660]
0x180028268  mov     dword ptr [rsp+690h+pcchLength+4], 51h ; 'Q'
0x180028270  jmp     short loc_180028276
0x180028272  mov     edi, dword ptr [rsp+690h+pcchLength]
0x180028276  mov     ecx, eax
0x180028278  call    WX_WIN32_FROM_HR
0x18002827d  mov     ebx, eax
0x18002827f  test    eax, eax
0x180028281  jz      short loc_1800282A4
0x180028283  test    byte ptr cs:xmmword_1800423E0, 2
0x18002828a  jz      short loc_180028304
0x18002828c  mov     edx, 13h
0x180028291  mov     ecx, 401h
0x180028296  lea     r8, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids
0x18002829d  call    WPP_SF_
0x1800282a2  jmp     short loc_180028304
0x1800282a4  xor     eax, eax
0x1800282a6  lea     ecx, [rdi+2]
0x1800282a9  add     rcx, rcx
0x1800282ac  mov     [rcx+rsi], ax
0x1800282b0  mov     eax, 0FFFFFFFFh
0x1800282b5  cmp     rcx, rax
0x1800282b8  ja      short loc_1800282E0
0x1800282ba  mov     edi, ecx
0x1800282bc  cmp     r12d, 1
0x1800282c0  jnz     short loc_1800282C5
0x1800282c2  lea     edi, [rcx-2]
0x1800282c5  mov     rcx, [rsp+690h+hKey]; hkey
0x1800282ca  mov     r9, rsi; Buf2
0x1800282cd  mov     r8d, r12d; dwType
0x1800282d0  mov     dword ptr [rsp+690h+phkResult], edi; DWORD
0x1800282d4  mov     rdx, r15; lpValue
0x1800282d7  call    Dhcpv6RegSetOptionRegVal
0x1800282dc  mov     ebx, eax
0x1800282de  jmp     short loc_180028304
0x1800282e0  test    byte ptr cs:xmmword_1800423E0, 2
0x1800282e7  jz      short loc_1800282FF
0x1800282e9  mov     edx, 14h
0x1800282ee  lea     r8, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids
0x1800282f5  mov     ecx, 401h
0x1800282fa  call    WPP_SF_
0x1800282ff  mov     ebx, 57h ; 'W'
0x180028304  mov     rcx, [rsp+690h+hKey]; hKey
0x180028309  call    cs:__imp_RegCloseKey
0x180028310  nop     dword ptr [rax+rax+00h]
0x180028315  test    ebx, ebx
0x180028317  jz      short loc_18002833F
0x180028319  test    byte ptr cs:xmmword_1800423E0, 2
0x180028320  jz      short loc_18002833F
0x180028322  mov     edx, 16h
0x180028327  mov     dword ptr [rsp+690h+phkResult], ebx
0x18002832b  mov     ecx, 401h
0x180028330  lea     r8, WPP_ec2a5d0085f33850f7877cb54422e2ef_Traceguids
0x180028337  mov     r9, r15
0x18002833a  call    WPP_SF_SD
0x18002833f  mov     eax, ebx
0x180028341  mov     rcx, [rbp+590h+var_40]
0x180028348  xor     rcx, rsp; StackCookie
0x18002834b  call    __security_check_cookie
0x180028350  add     rsp, 660h
0x180028357  pop     r15
0x180028359  pop     r14
0x18002835b  pop     r12
0x18002835d  pop     rdi
0x18002835e  pop     rsi
0x18002835f  pop     rbx
0x180028360  pop     rbp
0x180028361  retn
```
