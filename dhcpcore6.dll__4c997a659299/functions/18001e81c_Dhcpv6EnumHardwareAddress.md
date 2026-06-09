# Dhcpv6EnumHardwareAddress

- ea: `0x18001e81c`
- end: `0x18001eaba`
- name: `Dhcpv6EnumHardwareAddress`
- size: `670`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800128dc`

## callees

- `0x180001ca4`
- `0x180004b30`
- `0x18001a3ee`
- `0x18001e81c`
- `0x1800338c0`
- `0x180033900`

## import_xrefs

- `NSI!NsiFreeTable` at `0x18001ea25`
- `NSI!NsiFreeTable` at `0x18001ea25`
- `NSI!NsiAllocateAndGetTable` at `0x18001e8f3`
- `NSI!NsiAllocateAndGetTable` at `0x18001e8f3`

## pseudocode

```c
__int64 __fastcall Dhcpv6EnumHardwareAddress(char *a1, char *a2)
{
  unsigned int Table; // ebx
  unsigned int v5; // eax
  __int64 v6; // r8
  _OWORD *v7; // rax
  __int64 v8; // rcx
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int64 v18; // rax
  __int64 v19; // rax
  __int128 v20; // xmm1
  __int64 v21; // rcx
  unsigned int v23; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v24; // [rsp+A8h] [rbp+38h] BYREF
  __int64 v25; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v26; // [rsp+B8h] [rbp+48h] BYREF

  v26 = 0;
  v24 = 0;
  v25 = 0;
  v23 = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_(1028, 16, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids);
  if ( a1 )
    memset_0(a1, 0, 0x238u);
  if ( a2 )
    memset_0(a2, 0, 0x290u);
  if ( a1 && a2 )
  {
    Table = NsiAllocateAndGetTable(1, &NPI_MS_NDIS_MODULEID, 1, &v26, 8, 0, 0, &v24, 656, &v25, 568, &v23, 0);
    if ( !Table )
    {
      v5 = 0;
      if ( v23 )
      {
        while ( 1 )
        {
          v6 = v24 + 656LL * v5;
          if ( *(_WORD *)(v6 + 548) )
            break;
          if ( ++v5 >= v23 )
            goto LABEL_20;
        }
        v7 = (_OWORD *)(568LL * v5 + v25);
        v8 = 4;
        do
        {
          v9 = v7[1];
          *(_OWORD *)a1 = *v7;
          v10 = v7[2];
          *((_OWORD *)a1 + 1) = v9;
          v11 = v7[3];
          *((_OWORD *)a1 + 2) = v10;
          v12 = v7[4];
          *((_OWORD *)a1 + 3) = v11;
          v13 = v7[5];
          *((_OWORD *)a1 + 4) = v12;
          v14 = v7[6];
          *((_OWORD *)a1 + 5) = v13;
          v15 = v7[7];
          v7 += 8;
          *((_OWORD *)a1 + 6) = v14;
          *((_OWORD *)a1 + 7) = v15;
          a1 += 128;
          --v8;
        }
        while ( v8 );
        v16 = v7[1];
        *(_OWORD *)a1 = *v7;
        v17 = v7[2];
        v18 = *((_QWORD *)v7 + 6);
        *((_OWORD *)a1 + 1) = v16;
        *((_OWORD *)a1 + 2) = v17;
        *((_QWORD *)a1 + 6) = v18;
        v19 = 5;
        do
        {
          *(_OWORD *)a2 = *(_OWORD *)v6;
          *((_OWORD *)a2 + 1) = *(_OWORD *)(v6 + 16);
          *((_OWORD *)a2 + 2) = *(_OWORD *)(v6 + 32);
          *((_OWORD *)a2 + 3) = *(_OWORD *)(v6 + 48);
          *((_OWORD *)a2 + 4) = *(_OWORD *)(v6 + 64);
          *((_OWORD *)a2 + 5) = *(_OWORD *)(v6 + 80);
          *((_OWORD *)a2 + 6) = *(_OWORD *)(v6 + 96);
          v20 = *(_OWORD *)(v6 + 112);
          v6 += 128;
          *((_OWORD *)a2 + 7) = v20;
          a2 += 128;
          --v19;
        }
        while ( v19 );
        *(_OWORD *)a2 = *(_OWORD *)v6;
      }
    }
  }
  else
  {
    Table = 87;
  }
LABEL_20:
  NsiFreeTable(v26, 0, v24, v25);
  v26 = 0;
  v24 = 0;
  v25 = 0;
  if ( Table )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_D(1025, 17, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids, Table);
    if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v21, (__int64)ErrorEnumeratingHardwareAddress, Table);
    TraceLogErrorv6(0, Table, 28);
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 18, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids, Table);
  return Table;
}

```

## disassembly

```asm
0x18001e81c  push    rbp
0x18001e81e  push    rbx
0x18001e81f  push    rsi
0x18001e820  push    rdi
0x18001e821  push    r14
0x18001e823  mov     rbp, rsp
0x18001e826  sub     rsp, 70h
0x18001e82a  xor     r14d, r14d
0x18001e82d  mov     rdi, rdx
0x18001e830  mov     [rbp+arg_18], r14
0x18001e834  mov     rsi, rcx
0x18001e837  mov     [rbp+arg_8], r14
0x18001e83b  mov     [rbp+arg_10], r14
0x18001e83f  mov     [rbp+arg_0], r14d
0x18001e843  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001e84a  jz      short loc_18001E861
0x18001e84c  lea     edx, [r14+10h]
0x18001e850  mov     ecx, 404h
0x18001e855  lea     r8, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids
0x18001e85c  call    WPP_SF_
0x18001e861  test    rsi, rsi
0x18001e864  jz      short loc_18001E876
0x18001e866  xor     edx, edx; Val
0x18001e868  mov     r8d, 238h; Size
0x18001e86e  mov     rcx, rsi; void *
0x18001e871  call    memset_0
0x18001e876  mov     ebx, 290h
0x18001e87b  test    rdi, rdi
0x18001e87e  jz      short loc_18001E88D
0x18001e880  mov     r8d, ebx; Size
0x18001e883  xor     edx, edx; Val
0x18001e885  mov     rcx, rdi; void *
0x18001e888  call    memset_0
0x18001e88d  test    rsi, rsi
0x18001e890  jnz     short loc_18001E89C
0x18001e892  mov     ebx, 57h ; 'W'
0x18001e897  jmp     loc_18001EA17
0x18001e89c  test    rdi, rdi
0x18001e89f  jz      short loc_18001E892
0x18001e8a1  mov     [rsp+70h+var_10], r14b
0x18001e8a6  lea     rax, [rbp+arg_0]
0x18001e8aa  mov     [rsp+70h+var_18], rax
0x18001e8af  lea     r9, [rbp+arg_18]
0x18001e8b3  mov     [rsp+70h+var_20], 238h
0x18001e8bb  lea     rax, [rbp+arg_10]
0x18001e8bf  mov     [rsp+70h+var_28], rax
0x18001e8c4  lea     rdx, NPI_MS_NDIS_MODULEID
0x18001e8cb  mov     [rsp+70h+var_30], ebx
0x18001e8cf  lea     rax, [rbp+arg_8]
0x18001e8d3  mov     [rsp+70h+var_38], rax
0x18001e8d8  mov     r8d, 1
0x18001e8de  mov     [rsp+70h+var_40], r14d
0x18001e8e3  mov     ecx, r8d
0x18001e8e6  mov     [rsp+70h+var_48], r14
0x18001e8eb  mov     [rsp+70h+var_50], 8
0x18001e8f3  call    cs:__imp_NsiAllocateAndGetTable
0x18001e8fa  nop     dword ptr [rax+rax+00h]
0x18001e8ff  mov     ebx, eax
0x18001e901  test    eax, eax
0x18001e903  jnz     loc_18001EA17
0x18001e909  mov     r9d, [rbp+arg_0]
0x18001e90d  mov     eax, r14d
0x18001e910  test    r9d, r9d
0x18001e913  jz      loc_18001EA17
0x18001e919  mov     r10d, eax
0x18001e91c  imul    r8, r10, 290h
0x18001e923  add     r8, [rbp+arg_8]
0x18001e927  cmp     [r8+224h], r14w
0x18001e92f  ja      short loc_18001E93D
0x18001e931  inc     eax
0x18001e933  cmp     eax, r9d
0x18001e936  jb      short loc_18001E919
0x18001e938  jmp     loc_18001EA17
0x18001e93d  mov     rax, [rbp+arg_10]
0x18001e941  imul    rcx, r10, 238h
0x18001e948  add     rax, rcx
0x18001e94b  mov     ecx, 4
0x18001e950  lea     edx, [rcx+7Ch]
0x18001e953  movups  xmm0, xmmword ptr [rax]
0x18001e956  movups  xmm1, xmmword ptr [rax+10h]
0x18001e95a  movups  xmmword ptr [rsi], xmm0
0x18001e95d  movups  xmm0, xmmword ptr [rax+20h]
0x18001e961  movups  xmmword ptr [rsi+10h], xmm1
0x18001e965  movups  xmm1, xmmword ptr [rax+30h]
0x18001e969  movups  xmmword ptr [rsi+20h], xmm0
0x18001e96d  movups  xmm0, xmmword ptr [rax+40h]
0x18001e971  movups  xmmword ptr [rsi+30h], xmm1
0x18001e975  movups  xmm1, xmmword ptr [rax+50h]
0x18001e979  movups  xmmword ptr [rsi+40h], xmm0
0x18001e97d  movups  xmm0, xmmword ptr [rax+60h]
0x18001e981  movups  xmmword ptr [rsi+50h], xmm1
0x18001e985  movups  xmm1, xmmword ptr [rax+70h]
0x18001e989  add     rax, rdx
0x18001e98c  movups  xmmword ptr [rsi+60h], xmm0
0x18001e990  movups  xmmword ptr [rsi+70h], xmm1
0x18001e994  add     rsi, rdx
0x18001e997  sub     rcx, 1
0x18001e99b  jnz     short loc_18001E953
0x18001e99d  movups  xmm0, xmmword ptr [rax]
0x18001e9a0  movups  xmm1, xmmword ptr [rax+10h]
0x18001e9a4  movups  xmmword ptr [rsi], xmm0
0x18001e9a7  movups  xmm0, xmmword ptr [rax+20h]
0x18001e9ab  mov     rax, [rax+30h]
0x18001e9af  movups  xmmword ptr [rsi+10h], xmm1
0x18001e9b3  movups  xmmword ptr [rsi+20h], xmm0
0x18001e9b7  mov     [rsi+30h], rax
0x18001e9bb  lea     eax, [rcx+5]
0x18001e9be  movups  xmm0, xmmword ptr [r8]
0x18001e9c2  movups  xmmword ptr [rdi], xmm0
0x18001e9c5  movups  xmm1, xmmword ptr [r8+10h]
0x18001e9ca  movups  xmmword ptr [rdi+10h], xmm1
0x18001e9ce  movups  xmm0, xmmword ptr [r8+20h]
0x18001e9d3  movups  xmmword ptr [rdi+20h], xmm0
0x18001e9d7  movups  xmm1, xmmword ptr [r8+30h]
0x18001e9dc  movups  xmmword ptr [rdi+30h], xmm1
0x18001e9e0  movups  xmm0, xmmword ptr [r8+40h]
0x18001e9e5  movups  xmmword ptr [rdi+40h], xmm0
0x18001e9e9  movups  xmm1, xmmword ptr [r8+50h]
0x18001e9ee  movups  xmmword ptr [rdi+50h], xmm1
0x18001e9f2  movups  xmm0, xmmword ptr [r8+60h]
0x18001e9f7  movups  xmmword ptr [rdi+60h], xmm0
0x18001e9fb  movups  xmm1, xmmword ptr [r8+70h]
0x18001ea00  add     r8, rdx
0x18001ea03  movups  xmmword ptr [rdi+70h], xmm1
0x18001ea07  add     rdi, rdx
0x18001ea0a  sub     rax, 1
0x18001ea0e  jnz     short loc_18001E9BE
0x18001ea10  movups  xmm0, xmmword ptr [r8]
0x18001ea14  movups  xmmword ptr [rdi], xmm0
0x18001ea17  mov     r9, [rbp+arg_10]
0x18001ea1b  xor     edx, edx
0x18001ea1d  mov     r8, [rbp+arg_8]
0x18001ea21  mov     rcx, [rbp+arg_18]
0x18001ea25  call    cs:__imp_NsiFreeTable
0x18001ea2c  nop     dword ptr [rax+rax+00h]
0x18001ea31  mov     [rbp+arg_18], r14
0x18001ea35  mov     [rbp+arg_8], r14
0x18001ea39  mov     [rbp+arg_10], r14
0x18001ea3d  test    ebx, ebx
0x18001ea3f  jz      short loc_18001EA8A
0x18001ea41  test    byte ptr cs:xmmword_1800423E0, 2
0x18001ea48  jz      short loc_18001EA63
0x18001ea4a  mov     edx, 11h
0x18001ea4f  lea     r8, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids
0x18001ea56  mov     ecx, 401h
0x18001ea5b  mov     r9d, ebx
0x18001ea5e  call    WPP_SF_D
0x18001ea63  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x18001ea6a  jz      short loc_18001EA7B
0x18001ea6c  mov     r8d, ebx
0x18001ea6f  lea     rdx, ErrorEnumeratingHardwareAddress
0x18001ea76  call    McTemplateU0q_EtwEventWriteTransfer
0x18001ea7b  mov     r8d, 1Ch
0x18001ea81  mov     edx, ebx
0x18001ea83  xor     ecx, ecx
0x18001ea85  call    TraceLogErrorv6
0x18001ea8a  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001ea91  jz      short loc_18001EAAC
0x18001ea93  mov     edx, 12h
0x18001ea98  lea     r8, WPP_642d1a2b547f3a6a91393fb9cb453e87_Traceguids
0x18001ea9f  mov     ecx, 404h
0x18001eaa4  mov     r9d, ebx
0x18001eaa7  call    WPP_SF_D
0x18001eaac  mov     eax, ebx
0x18001eaae  add     rsp, 70h
0x18001eab2  pop     r14
0x18001eab4  pop     rdi
0x18001eab5  pop     rsi
0x18001eab6  pop     rbx
0x18001eab7  pop     rbp
0x18001eab8  retn
```
