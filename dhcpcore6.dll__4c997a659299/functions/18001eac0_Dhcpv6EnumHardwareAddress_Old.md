# Dhcpv6EnumHardwareAddress_Old

- ea: `0x18001eac0`
- end: `0x18001ed7e`
- name: `Dhcpv6EnumHardwareAddress_Old`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800128dc`

## callees

- `0x180001ca4`
- `0x180004b30`
- `0x18001eac0`
- `0x1800338c0`
- `0x180033900`

## import_xrefs

- `NSI!NsiFreeTable` at `0x18001ed3b`
- `NSI!NsiFreeTable` at `0x18001ed3b`
- `NSI!NsiAllocateAndGetTable` at `0x18001eb71`
- `NSI!NsiAllocateAndGetTable` at `0x18001eb71`

## pseudocode

```c
__int64 __fastcall Dhcpv6EnumHardwareAddress_Old(_OWORD *a1, _OWORD *a2)
{
  unsigned int Table; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  char v7; // dl
  unsigned int v9; // r8d
  __int64 v10; // r11
  __int64 v11; // r10
  __int64 v12; // rcx
  __int64 v13; // rdx
  _OWORD *v14; // rax
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int64 v24; // rax
  __int64 v25; // rax
  __int128 v26; // xmm1
  __int64 v27; // [rsp+70h] [rbp-28h] BYREF
  __int64 v28; // [rsp+78h] [rbp-20h] BYREF
  unsigned int v29; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v30; // [rsp+B8h] [rbp+20h] BYREF

  v28 = 0;
  v30 = 0;
  v27 = 0;
  v29 = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_(1028, 11, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids);
  Table = NsiAllocateAndGetTable(1, &NPI_MS_NDIS_MODULEID, 1, &v28, 8, 0, 0, &v30, 656, &v27, 568, &v29, 0);
  v6 = Table;
  v7 = xmmword_1800423E0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    WPP_SF_D(1028, 12, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids, Table);
    v7 = xmmword_1800423E0;
  }
  if ( v6 )
  {
    if ( (v7 & 2) != 0 )
      WPP_SF_D(1025, 13, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids, v6);
    if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v5, (__int64)ErrorEnumeratingHardwareAddress, v6);
    TraceLogErrorv6(0, v6, 28);
    return v6;
  }
  else
  {
    v9 = 0;
    v10 = v30;
    v11 = v27;
    if ( v29 )
    {
      while ( 1 )
      {
        v12 = v30 + 656LL * v9;
        if ( *(_WORD *)(v12 + 548) )
          break;
        if ( ++v9 >= v29 )
          goto LABEL_20;
      }
      v13 = 4;
      v14 = (_OWORD *)(v27 + 568LL * v9);
      do
      {
        v15 = v14[1];
        *a1 = *v14;
        v16 = v14[2];
        a1[1] = v15;
        v17 = v14[3];
        a1[2] = v16;
        v18 = v14[4];
        a1[3] = v17;
        v19 = v14[5];
        a1[4] = v18;
        v20 = v14[6];
        a1[5] = v19;
        v21 = v14[7];
        v14 += 8;
        a1[6] = v20;
        a1[7] = v21;
        a1 += 8;
        --v13;
      }
      while ( v13 );
      v22 = v14[1];
      *a1 = *v14;
      v23 = v14[2];
      v24 = *((_QWORD *)v14 + 6);
      a1[1] = v22;
      a1[2] = v23;
      *((_QWORD *)a1 + 6) = v24;
      v25 = 5;
      do
      {
        *a2 = *(_OWORD *)v12;
        a2[1] = *(_OWORD *)(v12 + 16);
        a2[2] = *(_OWORD *)(v12 + 32);
        a2[3] = *(_OWORD *)(v12 + 48);
        a2[4] = *(_OWORD *)(v12 + 64);
        a2[5] = *(_OWORD *)(v12 + 80);
        a2[6] = *(_OWORD *)(v12 + 96);
        v26 = *(_OWORD *)(v12 + 112);
        v12 += 128;
        a2[7] = v26;
        a2 += 8;
        --v25;
      }
      while ( v25 );
      *a2 = *(_OWORD *)v12;
      v7 = xmmword_1800423E0;
    }
LABEL_20:
    if ( (v7 & 0x10) != 0 )
    {
      WPP_SF_(1028, 14, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids);
      v10 = v30;
      v11 = v27;
    }
    NsiFreeTable(v28, 0, v10, v11);
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_(1028, 15, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids);
    return 0;
  }
}

```

## disassembly

```asm
0x18001eac0  mov     rax, rsp
0x18001eac3  mov     [rax+8], rbx
0x18001eac7  mov     [rax+10h], rsi
0x18001eacb  push    rdi
0x18001eacc  push    r14
0x18001eace  push    r15
0x18001ead0  sub     rsp, 80h
0x18001ead7  xor     r14d, r14d
0x18001eada  mov     rdi, rdx
0x18001eadd  mov     [rax-20h], r14
0x18001eae1  mov     rsi, rcx
0x18001eae4  mov     [rax+20h], r14
0x18001eae8  mov     [rax-28h], r14
0x18001eaec  mov     [rax+18h], r14d
0x18001eaf0  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001eaf7  lea     r15, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids
0x18001eafe  jz      short loc_18001EB11
0x18001eb00  lea     edx, [r14+0Bh]
0x18001eb04  mov     ecx, 404h
0x18001eb09  mov     r8, r15
0x18001eb0c  call    WPP_SF_
0x18001eb11  mov     [rsp+98h+var_38], r14b
0x18001eb16  lea     rax, [rsp+98h+arg_10]
0x18001eb1e  mov     [rsp+98h+var_40], rax
0x18001eb23  lea     r9, [rsp+98h+var_20]
0x18001eb28  mov     [rsp+98h+var_48], 238h
0x18001eb30  lea     rax, [rsp+98h+var_28]
0x18001eb35  mov     [rsp+98h+var_50], rax
0x18001eb3a  lea     rdx, NPI_MS_NDIS_MODULEID
0x18001eb41  mov     [rsp+98h+var_58], 290h
0x18001eb49  lea     rax, [rsp+98h+arg_18]
0x18001eb51  mov     [rsp+98h+var_60], rax
0x18001eb56  mov     r8d, 1
0x18001eb5c  mov     [rsp+98h+var_68], r14d
0x18001eb61  mov     ecx, r8d
0x18001eb64  mov     [rsp+98h+var_70], r14
0x18001eb69  mov     [rsp+98h+var_78], 8
0x18001eb71  call    cs:__imp_NsiAllocateAndGetTable
0x18001eb78  nop     dword ptr [rax+rax+00h]
0x18001eb7d  mov     ebx, eax
0x18001eb7f  mov     dl, byte ptr cs:xmmword_1800423E0
0x18001eb85  test    dl, 10h
0x18001eb88  jz      short loc_18001EBA5
0x18001eb8a  mov     edx, 0Ch
0x18001eb8f  mov     ecx, 404h
0x18001eb94  mov     r9d, eax
0x18001eb97  mov     r8, r15
0x18001eb9a  call    WPP_SF_D
0x18001eb9f  mov     dl, byte ptr cs:xmmword_1800423E0
0x18001eba5  test    ebx, ebx
0x18001eba7  jz      short loc_18001EBF1
0x18001eba9  test    dl, 2
0x18001ebac  jz      short loc_18001EBC3
0x18001ebae  mov     edx, 0Dh
0x18001ebb3  mov     ecx, 401h
0x18001ebb8  mov     r9d, ebx
0x18001ebbb  mov     r8, r15
0x18001ebbe  call    WPP_SF_D
0x18001ebc3  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x18001ebca  jz      short loc_18001EBDB
0x18001ebcc  mov     r8d, ebx
0x18001ebcf  lea     rdx, ErrorEnumeratingHardwareAddress
0x18001ebd6  call    McTemplateU0q_EtwEventWriteTransfer
0x18001ebdb  mov     r8d, 1Ch
0x18001ebe1  mov     edx, ebx
0x18001ebe3  xor     ecx, ecx
0x18001ebe5  call    TraceLogErrorv6
0x18001ebea  mov     eax, ebx
0x18001ebec  jmp     loc_18001ED64
0x18001ebf1  mov     r9d, [rsp+98h+arg_10]
0x18001ebf9  mov     r8d, r14d
0x18001ebfc  mov     r11, [rsp+98h+arg_18]
0x18001ec04  mov     r10, [rsp+98h+var_28]
0x18001ec09  test    r9d, r9d
0x18001ec0c  jz      loc_18001ED0A
0x18001ec12  mov     ebx, r8d
0x18001ec15  imul    rcx, rbx, 290h
0x18001ec1c  add     rcx, r11
0x18001ec1f  cmp     [rcx+224h], r14w
0x18001ec27  ja      short loc_18001EC36
0x18001ec29  inc     r8d
0x18001ec2c  cmp     r8d, r9d
0x18001ec2f  jb      short loc_18001EC12
0x18001ec31  jmp     loc_18001ED0A
0x18001ec36  imul    rax, rbx, 238h
0x18001ec3d  mov     edx, 4
0x18001ec42  add     rax, r10
0x18001ec45  lea     r8d, [rdx+7Ch]
0x18001ec49  movups  xmm0, xmmword ptr [rax]
0x18001ec4c  movups  xmm1, xmmword ptr [rax+10h]
0x18001ec50  movups  xmmword ptr [rsi], xmm0
0x18001ec53  movups  xmm0, xmmword ptr [rax+20h]
0x18001ec57  movups  xmmword ptr [rsi+10h], xmm1
0x18001ec5b  movups  xmm1, xmmword ptr [rax+30h]
0x18001ec5f  movups  xmmword ptr [rsi+20h], xmm0
0x18001ec63  movups  xmm0, xmmword ptr [rax+40h]
0x18001ec67  movups  xmmword ptr [rsi+30h], xmm1
0x18001ec6b  movups  xmm1, xmmword ptr [rax+50h]
0x18001ec6f  movups  xmmword ptr [rsi+40h], xmm0
0x18001ec73  movups  xmm0, xmmword ptr [rax+60h]
0x18001ec77  movups  xmmword ptr [rsi+50h], xmm1
0x18001ec7b  movups  xmm1, xmmword ptr [rax+70h]
0x18001ec7f  add     rax, r8
0x18001ec82  movups  xmmword ptr [rsi+60h], xmm0
0x18001ec86  movups  xmmword ptr [rsi+70h], xmm1
0x18001ec8a  add     rsi, r8
0x18001ec8d  sub     rdx, 1
0x18001ec91  jnz     short loc_18001EC49
0x18001ec93  movups  xmm0, xmmword ptr [rax]
0x18001ec96  movups  xmm1, xmmword ptr [rax+10h]
0x18001ec9a  movups  xmmword ptr [rsi], xmm0
0x18001ec9d  movups  xmm0, xmmword ptr [rax+20h]
0x18001eca1  mov     rax, [rax+30h]
0x18001eca5  movups  xmmword ptr [rsi+10h], xmm1
0x18001eca9  movups  xmmword ptr [rsi+20h], xmm0
0x18001ecad  mov     [rsi+30h], rax
0x18001ecb1  lea     eax, [rdx+5]
0x18001ecb4  movups  xmm0, xmmword ptr [rcx]
0x18001ecb7  movups  xmmword ptr [rdi], xmm0
0x18001ecba  movups  xmm1, xmmword ptr [rcx+10h]
0x18001ecbe  movups  xmmword ptr [rdi+10h], xmm1
0x18001ecc2  movups  xmm0, xmmword ptr [rcx+20h]
0x18001ecc6  movups  xmmword ptr [rdi+20h], xmm0
0x18001ecca  movups  xmm1, xmmword ptr [rcx+30h]
0x18001ecce  movups  xmmword ptr [rdi+30h], xmm1
0x18001ecd2  movups  xmm0, xmmword ptr [rcx+40h]
0x18001ecd6  movups  xmmword ptr [rdi+40h], xmm0
0x18001ecda  movups  xmm1, xmmword ptr [rcx+50h]
0x18001ecde  movups  xmmword ptr [rdi+50h], xmm1
0x18001ece2  movups  xmm0, xmmword ptr [rcx+60h]
0x18001ece6  movups  xmmword ptr [rdi+60h], xmm0
0x18001ecea  movups  xmm1, xmmword ptr [rcx+70h]
0x18001ecee  add     rcx, r8
0x18001ecf1  movups  xmmword ptr [rdi+70h], xmm1
0x18001ecf5  add     rdi, r8
0x18001ecf8  sub     rax, 1
0x18001ecfc  jnz     short loc_18001ECB4
0x18001ecfe  movups  xmm0, xmmword ptr [rcx]
0x18001ed01  movups  xmmword ptr [rdi], xmm0
0x18001ed04  mov     dl, byte ptr cs:xmmword_1800423E0
0x18001ed0a  test    dl, 10h
0x18001ed0d  jz      short loc_18001ED2E
0x18001ed0f  mov     edx, 0Eh
0x18001ed14  mov     ecx, 404h
0x18001ed19  mov     r8, r15
0x18001ed1c  call    WPP_SF_
0x18001ed21  mov     r11, [rsp+98h+arg_18]
0x18001ed29  mov     r10, [rsp+98h+var_28]
0x18001ed2e  mov     rcx, [rsp+98h+var_20]
0x18001ed33  mov     r9, r10
0x18001ed36  mov     r8, r11
0x18001ed39  xor     edx, edx
0x18001ed3b  call    cs:__imp_NsiFreeTable
0x18001ed42  nop     dword ptr [rax+rax+00h]
0x18001ed47  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001ed4e  jz      short loc_18001ED62
0x18001ed50  mov     edx, 0Fh
0x18001ed55  mov     ecx, 404h
0x18001ed5a  mov     r8, r15
0x18001ed5d  call    WPP_SF_
0x18001ed62  xor     eax, eax
0x18001ed64  lea     r11, [rsp+98h+var_18]
0x18001ed6c  mov     rbx, [r11+20h]
0x18001ed70  mov     rsi, [r11+28h]
0x18001ed74  mov     rsp, r11
0x18001ed77  pop     r15
0x18001ed79  pop     r14
0x18001ed7b  pop     rdi
0x18001ed7c  retn
```
