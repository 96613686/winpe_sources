# CreateDhcpv6Rebind

- ea: `0x18001f77c`
- end: `0x18001fc51`
- name: `CreateDhcpv6Rebind`
- size: `1237`
- prototype: `__int64 __fastcall(__int64, __int16 *, int *, int, void *)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180020d50`
- `0x180021b58`

## callees

- `0x180001d8c`
- `0x180002cac`
- `0x180002f80`
- `0x180003100`
- `0x180004b30`
- `0x18000e1ec`
- `0x18000ed3c`
- `0x180017ffc`
- `0x180018740`
- `0x180019ad0`
- `0x18001a3ee`
- `0x18001f77c`
- `0x180030920`
- `0x1800337d0`
- `0x1800338c0`
- `0x180033970`

## pseudocode

```c
__int64 __fastcall CreateDhcpv6Rebind(__int64 a1, __int16 *a2, int *a3, int a4, void *a5)
{
  __int64 v9; // rbx
  unsigned int appended; // ebx
  __int16 v11; // ax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int16 v15; // r9
  _QWORD *v16; // r14
  _QWORD *v17; // r8
  _DWORD *v18; // r10
  unsigned int v19; // edx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  void *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // r8
  u_short v27; // r9
  int v29; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v30; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned __int16 v31; // [rsp+78h] [rbp-88h] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v33; // [rsp+88h] [rbp-78h] BYREF
  int Src; // [rsp+8Ch] [rbp-74h] BYREF
  unsigned int v35[4]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v36[208]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v37[272]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v38[208]; // [rsp+280h] [rbp+180h] BYREF
  _WORD v39[2048]; // [rsp+350h] [rbp+250h] BYREF

  v30 = 0;
  v35[0] = 0;
  Src = 0;
  v31 = 259;
  if ( a1 )
  {
    if ( a2 )
    {
      v9 = a1 + 668;
      if ( a1 != -668 )
      {
        if ( a3 )
        {
          if ( (xmmword_1800423E0 & 0x10) != 0 )
            WPP_SF_S(1028, 73, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *(_QWORD *)(a1 + 56));
          if ( a4 && !a5 )
          {
            appended = 87;
            goto LABEL_40;
          }
          memset_0(v36, 0, 0xC8u);
          memset_0(v38, 0, 0xC8u);
          v11 = *a2;
          *(_BYTE *)v9 = 6;
          *(_WORD *)(v9 + 1) = v11;
          *(_BYTE *)(v9 + 3) = *((_BYTE *)a2 + 2);
          v32 = v9 + 4;
          v29 = 4;
          v33 = 0;
          appended = Dhcpv6AppendOption(&Src, 4u, 8u, &v29, &v32, a1 + 4763);
          if ( !appended )
          {
            AddToArray((__int64)v36, v12, &v30, 8);
            appended = Dhcpv6AppendOption((void *)(a1 + 456), 0x10u, 1u, &v29, &v32, a1 + 4763);
            if ( !appended )
            {
              AddToArray((__int64)v36, v13, &v30, 1);
              if ( a4 )
              {
                appended = Dhcpv6AppendOption(a5, 0x30u, 0x19u, &v29, &v32, a1 + 4763);
                if ( appended )
                  goto LABEL_40;
                v15 = 25;
              }
              else
              {
                v16 = *(_QWORD **)(a1 + 104);
                while ( v16 != (_QWORD *)(a1 + 104) )
                {
                  v17 = v16;
                  v18 = v16;
                  v16 = (_QWORD *)*v16;
                  v19 = 0;
                  *(_OWORD *)(v17 + 5) = 0;
                  v17[3] = 0;
                  v17[2] = 0;
                  if ( *((_DWORD *)v17 + 9) )
                  {
                    do
                    {
                      if ( v19 >= 2 )
                        break;
                      v20 = v19++;
                      v17[7 * v20 + 9] = 0;
                    }
                    while ( v19 < v18[9] );
                  }
                  appended = Dhcpv6AppendOption(v18, 0xA8u, 3u, &v29, &v32, a1 + 4763);
                  if ( appended )
                    goto LABEL_40;
                }
                v15 = 3;
              }
              AddToArray((__int64)v36, v14, &v30, v15);
              if ( *(_DWORD *)(a1 + 9032) )
                goto LABEL_31;
              appended = Dhcpv6AppendDefaultVendorClassOption(&v29, (u_short **)&v32, a1 + 4763);
              if ( appended )
                goto LABEL_40;
              AddToArray((__int64)v36, v21, &v30, 16);
              v23 = *(void **)(a1 + 656);
              if ( v23 )
              {
                appended = Dhcpv6AppendUserClassOption(v23, *(unsigned __int8 *)(a1 + 664), v22, &v29, &v32, a1 + 4763);
                if ( appended )
                  goto LABEL_40;
                AddToArray((__int64)v36, v24, &v30, 15);
              }
              memset_0(v37, 0, 0x104u);
              if ( (unsigned int)Dhcpv6DynDnsGetDynDNSOption(v37, &v31, *(_QWORD *)(a1 + 648), *(_QWORD *)(a1 + 56)) )
              {
LABEL_31:
                appended = Dhcpv6AppendSendOptions(
                             a1,
                             (_QWORD **)(a1 + 616),
                             *(_QWORD *)(a1 + 656),
                             *(_DWORD *)(a1 + 664),
                             &v32,
                             &v29,
                             a1 + 4763,
                             (__int64)v36,
                             &v30,
                             (__int64)v38,
                             v35,
                             v39,
                             &v33);
                if ( !appended
                  && (*(_DWORD *)(a1 + 9032)
                   || (unsigned int)IsPresentInArray((__int64)v36, 0, v26, 17)
                   || !v33
                   || v32 + (unsigned __int64)v33 > a1 + 4763
                   || (appended = Dhcpv6AppendOption(v39, v33, v27, &v29, &v32, a1 + 4763)) == 0) )
                {
                  *a3 = v29;
                  return appended;
                }
                goto LABEL_40;
              }
              appended = Dhcpv6AppendOption(v37, v31, 0x27u, &v29, &v32, a1 + 4763);
              if ( !appended )
              {
                AddToArray((__int64)v36, v25, &v30, 39);
                goto LABEL_31;
              }
            }
          }
LABEL_40:
          if ( (xmmword_1800423E0 & 2) != 0 )
            WPP_SF_SD(
              1025,
              74,
              (unsigned int)WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids,
              *(_QWORD *)(a1 + 56),
              appended);
          goto LABEL_42;
        }
      }
    }
  }
  appended = 87;
  if ( (xmmword_1800423E0 & 2) != 0 )
  {
    WPP_SF_D(1025, 72, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, 87);
    goto LABEL_40;
  }
LABEL_42:
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 4) != 0 )
    McTemplateU0qq_EtwEventWriteTransfer(a1, ErrorCreatingPacket, *(unsigned int *)(a1 + 48), appended);
  TraceLogErrorv6(a1, appended, 44);
  return appended;
}

```

## disassembly

```asm
0x18001f77c  mov     [rsp-8+arg_8], rbx
0x18001f781  push    rbp
0x18001f782  push    rsi
0x18001f783  push    rdi
0x18001f784  push    r12
0x18001f786  push    r13
0x18001f788  push    r14
0x18001f78a  push    r15
0x18001f78c  lea     rbp, [rsp-1260h]
0x18001f794  mov     eax, 1360h
0x18001f799  call    _alloca_probe
0x18001f79e  sub     rsp, rax
0x18001f7a1  mov     rax, cs:__security_cookie
0x18001f7a8  xor     rax, rsp
0x18001f7ab  mov     [rbp+1290h+var_40], rax
0x18001f7b2  mov     r15, [rbp+1290h+arg_20]
0x18001f7b9  xor     esi, esi
0x18001f7bb  mov     [rsp+1390h+var_131C], esi
0x18001f7bf  mov     eax, 103h
0x18001f7c4  mov     [rbp+1290h+var_1300], esi
0x18001f7c7  mov     r14d, r9d
0x18001f7ca  mov     [rbp+1290h+Src], esi
0x18001f7cd  mov     r13, r8
0x18001f7d0  mov     [rsp+1390h+var_1318], ax
0x18001f7d5  mov     r12, rdx
0x18001f7d8  mov     rdi, rcx
0x18001f7db  test    rcx, rcx
0x18001f7de  jz      loc_18001FBAC
0x18001f7e4  test    rdx, rdx
0x18001f7e7  jz      loc_18001FBAC
0x18001f7ed  lea     rbx, [rcx+29Ch]
0x18001f7f4  test    rbx, rbx
0x18001f7f7  jz      loc_18001FBAC
0x18001f7fd  test    r8, r8
0x18001f800  jz      loc_18001FBAC
0x18001f806  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001f80d  jz      short loc_18001F827
0x18001f80f  mov     r9, [rdi+38h]
0x18001f813  lea     edx, [rsi+49h]
0x18001f816  mov     ecx, 404h
0x18001f81b  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x18001f822  call    WPP_SF_S
0x18001f827  test    r14d, r14d
0x18001f82a  jz      short loc_18001F83A
0x18001f82c  test    r15, r15
0x18001f82f  jnz     short loc_18001F83A
0x18001f831  lea     ebx, [r15+57h]
0x18001f835  jmp     loc_18001FBD1
0x18001f83a  mov     esi, 0C8h
0x18001f83f  lea     rcx, [rbp+1290h+var_12F0]; void *
0x18001f843  mov     r8d, esi; Size
0x18001f846  xor     edx, edx; Val
0x18001f848  call    memset_0
0x18001f84d  mov     r8d, esi; Size
0x18001f850  lea     rcx, [rbp+1290h+var_1110]; void *
0x18001f857  xor     edx, edx; Val
0x18001f859  call    memset_0
0x18001f85e  movzx   eax, word ptr [r12]
0x18001f863  lea     rsi, [rdi+129Bh]
0x18001f86a  mov     ecx, 4
0x18001f86f  mov     byte ptr [rbx], 6
0x18001f872  mov     [rbx+1], ax
0x18001f876  lea     r9, [rsp+1390h+var_1320]
0x18001f87b  mov     al, [r12+2]
0x18001f880  mov     edx, ecx
0x18001f882  mov     [rbx+3], al
0x18001f885  lea     rax, [rbx+4]
0x18001f889  mov     [rbp+1290h+var_1310], rax
0x18001f88d  lea     r8d, [rcx+4]
0x18001f891  lea     rax, [rbp+1290h+var_1310]
0x18001f895  mov     [rsp+1390h+var_1320], ecx
0x18001f899  mov     [rsp+1390h+var_1368], rsi; __int64
0x18001f89e  lea     rcx, [rbp+1290h+Src]; Src
0x18001f8a2  mov     [rsp+1390h+var_1370], rax; __int64
0x18001f8a7  mov     [rbp+1290h+var_1308], 0
0x18001f8ae  call    Dhcpv6AppendOption
0x18001f8b3  xor     r12d, r12d
0x18001f8b6  mov     ebx, eax
0x18001f8b8  test    eax, eax
0x18001f8ba  jnz     loc_18001FBD1
0x18001f8c0  lea     r9d, [rax+8]
0x18001f8c4  lea     r8, [rsp+1390h+var_131C]
0x18001f8c9  lea     rcx, [rbp+1290h+var_12F0]
0x18001f8cd  call    AddToArray
0x18001f8d2  lea     rax, [rbp+1290h+var_1310]
0x18001f8d6  mov     [rsp+1390h+var_1368], rsi; __int64
0x18001f8db  lea     edx, [rbx+10h]
0x18001f8de  mov     [rsp+1390h+var_1370], rax; __int64
0x18001f8e3  lea     r8d, [rbx+1]
0x18001f8e7  lea     rcx, [rdi+1C8h]; Src
0x18001f8ee  lea     r9, [rsp+1390h+var_1320]
0x18001f8f3  call    Dhcpv6AppendOption
0x18001f8f8  mov     ebx, eax
0x18001f8fa  test    eax, eax
0x18001f8fc  jnz     loc_18001FBD1
0x18001f902  lea     r9d, [r12+1]
0x18001f907  lea     r8, [rsp+1390h+var_131C]
0x18001f90c  lea     rcx, [rbp+1290h+var_12F0]
0x18001f910  call    AddToArray
0x18001f915  test    r14d, r14d
0x18001f918  jz      short loc_18001F94F
0x18001f91a  lea     rax, [rbp+1290h+var_1310]
0x18001f91e  mov     [rsp+1390h+var_1368], rsi; __int64
0x18001f923  lea     r14d, [r12+19h]
0x18001f928  mov     [rsp+1390h+var_1370], rax; __int64
0x18001f92d  mov     r8d, r14d
0x18001f930  lea     edx, [rbx+30h]
0x18001f933  lea     r9, [rsp+1390h+var_1320]
0x18001f938  mov     rcx, r15; Src
0x18001f93b  call    Dhcpv6AppendOption
0x18001f940  mov     ebx, eax
0x18001f942  test    eax, eax
0x18001f944  jnz     loc_18001FBD1
0x18001f94a  mov     r9d, r14d
0x18001f94d  jmp     short loc_18001F9CC
0x18001f94f  lea     r15, [rdi+68h]
0x18001f953  mov     r14, [r15]
0x18001f956  cmp     r14, r15
0x18001f959  jz      short loc_18001F9C6
0x18001f95b  mov     r8, r14
0x18001f95e  mov     r10, r14
0x18001f961  mov     r14, [r14]
0x18001f964  xorps   xmm0, xmm0
0x18001f967  mov     edx, r12d
0x18001f96a  movups  xmmword ptr [r8+28h], xmm0
0x18001f96f  mov     [r8+18h], r12
0x18001f973  mov     [r8+10h], r12
0x18001f977  cmp     [r8+24h], r12d
0x18001f97b  jbe     short loc_18001F995
0x18001f97d  cmp     edx, 2
0x18001f980  jnb     short loc_18001F995
0x18001f982  mov     eax, edx
0x18001f984  inc     edx
0x18001f986  imul    rcx, rax, 38h ; '8'
0x18001f98a  mov     [rcx+r8+48h], r12
0x18001f98f  cmp     edx, [r10+24h]
0x18001f993  jb      short loc_18001F97D
0x18001f995  lea     rax, [rbp+1290h+var_1310]
0x18001f999  mov     [rsp+1390h+var_1368], rsi; __int64
0x18001f99e  mov     edx, 0A8h
0x18001f9a3  mov     [rsp+1390h+var_1370], rax; __int64
0x18001f9a8  mov     r8d, 3
0x18001f9ae  lea     r9, [rsp+1390h+var_1320]
0x18001f9b3  mov     rcx, r10; Src
0x18001f9b6  call    Dhcpv6AppendOption
0x18001f9bb  mov     ebx, eax
0x18001f9bd  test    eax, eax
0x18001f9bf  jz      short loc_18001F956
0x18001f9c1  jmp     loc_18001FBD1
0x18001f9c6  mov     r9d, 3
0x18001f9cc  lea     r8, [rsp+1390h+var_131C]
0x18001f9d1  lea     rcx, [rbp+1290h+var_12F0]
0x18001f9d5  call    AddToArray
0x18001f9da  cmp     [rdi+2348h], r12d
0x18001f9e1  jnz     loc_18001FACC
0x18001f9e7  mov     r8, rsi
0x18001f9ea  lea     rdx, [rbp+1290h+var_1310]
0x18001f9ee  lea     rcx, [rsp+1390h+var_1320]
0x18001f9f3  call    Dhcpv6AppendDefaultVendorClassOption
0x18001f9f8  mov     ebx, eax
0x18001f9fa  test    eax, eax
0x18001f9fc  jnz     loc_18001FBD1
0x18001fa02  lea     r9d, [rax+10h]
0x18001fa06  lea     r8, [rsp+1390h+var_131C]
0x18001fa0b  lea     rcx, [rbp+1290h+var_12F0]
0x18001fa0f  call    AddToArray
0x18001fa14  mov     rcx, [rdi+290h]; Src
0x18001fa1b  test    rcx, rcx
0x18001fa1e  jz      short loc_18001FA5B
0x18001fa20  movzx   edx, byte ptr [rdi+298h]
0x18001fa27  lea     rax, [rbp+1290h+var_1310]
0x18001fa2b  mov     [rsp+1390h+var_1368], rsi; __int64
0x18001fa30  lea     r9, [rsp+1390h+var_1320]
0x18001fa35  mov     [rsp+1390h+var_1370], rax; __int64
0x18001fa3a  call    Dhcpv6AppendUserClassOption
0x18001fa3f  mov     ebx, eax
0x18001fa41  test    eax, eax
0x18001fa43  jnz     loc_18001FBD1
0x18001fa49  lea     r9d, [rax+0Fh]
0x18001fa4d  lea     r8, [rsp+1390h+var_131C]
0x18001fa52  lea     rcx, [rbp+1290h+var_12F0]
0x18001fa56  call    AddToArray
0x18001fa5b  xor     edx, edx; Val
0x18001fa5d  lea     rcx, [rbp+1290h+var_1220]; void *
0x18001fa61  mov     r8d, 104h; Size
0x18001fa67  call    memset_0
0x18001fa6c  mov     r9, [rdi+38h]
0x18001fa70  lea     rdx, [rsp+1390h+var_1318]
0x18001fa75  mov     r8, [rdi+288h]
0x18001fa7c  lea     rcx, [rbp+1290h+var_1220]
0x18001fa80  call    Dhcpv6DynDnsGetDynDNSOption
0x18001fa85  test    eax, eax
0x18001fa87  jnz     short loc_18001FACC
0x18001fa89  movzx   edx, [rsp+1390h+var_1318]
0x18001fa8e  lea     r14d, [rax+27h]
0x18001fa92  lea     rax, [rbp+1290h+var_1310]
0x18001fa96  mov     [rsp+1390h+var_1368], rsi; __int64
0x18001fa9b  mov     r8d, r14d
0x18001fa9e  mov     [rsp+1390h+var_1370], rax; __int64
0x18001faa3  lea     r9, [rsp+1390h+var_1320]
0x18001faa8  lea     rcx, [rbp+1290h+var_1220]; Src
0x18001faac  call    Dhcpv6AppendOption
0x18001fab1  mov     ebx, eax
0x18001fab3  test    eax, eax
0x18001fab5  jnz     loc_18001FBD1
0x18001fabb  mov     r9d, r14d
0x18001fabe  lea     r8, [rsp+1390h+var_131C]
0x18001fac3  lea     rcx, [rbp+1290h+var_12F0]
0x18001fac7  call    AddToArray
0x18001facc  mov     r9d, [rdi+298h]
0x18001fad3  lea     rax, [rbp+1290h+var_1308]
0x18001fad7  mov     r8, [rdi+290h]
0x18001fade  lea     rdx, [rdi+268h]
0x18001fae5  mov     [rsp+1390h+var_1330], rax
0x18001faea  mov     rcx, rdi
0x18001faed  lea     rax, [rbp+1290h+var_1040]
0x18001faf4  mov     [rsp+1390h+var_1338], rax
0x18001faf9  lea     rax, [rbp+1290h+var_1300]
0x18001fafd  mov     [rsp+1390h+var_1340], rax
0x18001fb02  lea     rax, [rbp+1290h+var_1110]
0x18001fb09  mov     [rsp+1390h+var_1348], rax
0x18001fb0e  lea     rax, [rsp+1390h+var_131C]
0x18001fb13  mov     [rsp+1390h+var_1350], rax
0x18001fb18  lea     rax, [rbp+1290h+var_12F0]
0x18001fb1c  mov     [rsp+1390h+var_1358], rax
0x18001fb21  lea     rax, [rsp+1390h+var_1320]
0x18001fb26  mov     [rsp+1390h+var_1360], rsi
0x18001fb2b  mov     [rsp+1390h+var_1368], rax
0x18001fb30  lea     rax, [rbp+1290h+var_1310]
0x18001fb34  mov     [rsp+1390h+var_1370], rax
0x18001fb39  call    Dhcpv6AppendSendOptions
0x18001fb3e  mov     ebx, eax
0x18001fb40  test    eax, eax
0x18001fb42  jnz     loc_18001FBD1
0x18001fb48  cmp     [rdi+2348h], r12d
0x18001fb4f  jnz     short loc_18001FB9E
0x18001fb51  xor     edx, edx
0x18001fb53  lea     r9d, [rax+11h]
0x18001fb57  lea     rcx, [rbp+1290h+var_12F0]
0x18001fb5b  call    IsPresentInArray
0x18001fb60  test    eax, eax
0x18001fb62  jnz     short loc_18001FB9E
0x18001fb64  mov     edx, [rbp+1290h+var_1308]
0x18001fb67  test    edx, edx
0x18001fb69  jz      short loc_18001FB9E
0x18001fb6b  mov     eax, edx
0x18001fb6d  add     rax, [rbp+1290h+var_1310]
0x18001fb71  cmp     rax, rsi
0x18001fb74  ja      short loc_18001FB9E
0x18001fb76  mov     r8d, r9d
0x18001fb79  mov     [rsp+1390h+var_1368], rsi; __int64
0x18001fb7e  lea     rax, [rbp+1290h+var_1310]
0x18001fb82  lea     r9, [rsp+1390h+var_1320]
0x18001fb87  mov     [rsp+1390h+var_1370], rax; __int64
0x18001fb8c  lea     rcx, [rbp+1290h+var_1040]; Src
0x18001fb93  call    Dhcpv6AppendOption
0x18001fb98  mov     ebx, eax
0x18001fb9a  test    eax, eax
0x18001fb9c  jnz     short loc_18001FBD1
0x18001fb9e  mov     eax, [rsp+1390h+var_1320]
0x18001fba2  mov     [r13+0], eax
0x18001fba6  test    ebx, ebx
0x18001fba8  jz      short loc_18001FC24
0x18001fbaa  jmp     short loc_18001FBD1
0x18001fbac  mov     ebx, 57h ; 'W'
0x18001fbb1  test    byte ptr cs:xmmword_1800423E0, 2
0x18001fbb8  jz      short loc_18001FBF8
0x18001fbba  lea     edx, [rbx-0Fh]
0x18001fbbd  mov     ecx, 401h
0x18001fbc2  mov     r9d, ebx
0x18001fbc5  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x18001fbcc  call    WPP_SF_D
0x18001fbd1  test    byte ptr cs:xmmword_1800423E0, 2
0x18001fbd8  jz      short loc_18001FBF8
0x18001fbda  mov     r9, [rdi+38h]
0x18001fbde  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x18001fbe5  mov     edx, 4Ah ; 'J'
0x18001fbea  mov     dword ptr [rsp+1390h+var_1370], ebx
0x18001fbee  mov     ecx, 401h
0x18001fbf3  call    WPP_SF_SD
0x18001fbf8  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 4
0x18001fbff  jz      short loc_18001FC14
0x18001fc01  mov     r8d, [rdi+30h]
0x18001fc05  lea     rdx, ErrorCreatingPacket
0x18001fc0c  mov     r9d, ebx
0x18001fc0f  call    McTemplateU0qq_EtwEventWriteTransfer
0x18001fc14  mov     r8d, 2Ch ; ','
0x18001fc1a  mov     edx, ebx
0x18001fc1c  mov     rcx, rdi
0x18001fc1f  call    TraceLogErrorv6
0x18001fc24  mov     eax, ebx
0x18001fc26  mov     rcx, [rbp+1290h+var_40]
0x18001fc2d  xor     rcx, rsp; StackCookie
0x18001fc30  call    __security_check_cookie
0x18001fc35  mov     rbx, [rsp+1390h+arg_8]
0x18001fc3d  add     rsp, 1360h
0x18001fc44  pop     r15
0x18001fc46  pop     r14
0x18001fc48  pop     r13
0x18001fc4a  pop     r12
  ... truncated ...
```
