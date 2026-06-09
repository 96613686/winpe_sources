# CreateDhcpv6Confirm

- ea: `0x180001ed4`
- end: `0x180002322`
- name: `CreateDhcpv6Confirm`
- size: `1102`
- prototype: `__int64 __fastcall(__int64, __int16 *, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180014070`

## callees

- `0x180001d8c`
- `0x180001ed4`
- `0x180002cac`
- `0x180002f80`
- `0x180004b30`
- `0x18000ed3c`
- `0x180017ffc`
- `0x180018740`
- `0x180019ad0`
- `0x18001a3ee`
- `0x180030920`
- `0x1800337d0`
- `0x1800338c0`
- `0x180033970`

## pseudocode

```c
__int64 __fastcall CreateDhcpv6Confirm(__int64 a1, __int16 *a2, int *a3)
{
  __int64 v6; // rbx
  __int16 v7; // ax
  unsigned int appended; // ebx
  _QWORD *v9; // r14
  _QWORD *v10; // rax
  unsigned __int32 v11; // edx
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // r8
  void *v24; // rcx
  __int64 v25; // rdx
  int v27; // [rsp+70h] [rbp-90h] BYREF
  __int64 v28; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v29; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v30; // [rsp+84h] [rbp-7Ch] BYREF
  int Src; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v32; // [rsp+8Ch] [rbp-74h] BYREF
  __int16 v33; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v34[206]; // [rsp+92h] [rbp-6Eh] BYREF
  _BYTE v35[208]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v36; // [rsp+230h] [rbp+130h] BYREF
  __int128 v37; // [rsp+240h] [rbp+140h]
  __m256i v38; // [rsp+250h] [rbp+150h]
  _OWORD v39[6]; // [rsp+270h] [rbp+170h]
  __int64 v40; // [rsp+2D0h] [rbp+1D0h]

  v29 = 0;
  v32 = 0;
  Src = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v6 = a1 + 668;
      if ( a1 != -668 )
      {
        if ( a3 )
        {
          if ( (xmmword_1800423E0 & 0x10) != 0 )
            WPP_SF_S(1028, 76, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *(_QWORD *)(a1 + 56));
          memset_0(v34, 0, 0xC6u);
          memset_0(v35, 0, 0xC8u);
          v7 = *a2;
          *(_BYTE *)v6 = 4;
          *(_WORD *)(v6 + 1) = v7;
          *(_BYTE *)(v6 + 3) = *((_BYTE *)a2 + 2);
          v27 = 4;
          v28 = v6 + 4;
          v30 = 0;
          appended = Dhcpv6AppendOption(&Src, 4u, 8u, &v27, &v28, a1 + 4763);
          if ( !appended )
          {
            appended = Dhcpv6AppendOption((void *)(a1 + 456), 0x10u, 1u, &v27, &v28, a1 + 4763);
            if ( !appended )
            {
              v33 = 1;
              v9 = *(_QWORD **)(a1 + 104);
              while ( v9 != (_QWORD *)(a1 + 104) )
              {
                v10 = v9;
                v11 = 0;
                v9 = (_QWORD *)*v9;
                v12 = *((_OWORD *)v10 + 1);
                v36 = *(_OWORD *)v10;
                v13 = *((_OWORD *)v10 + 2);
                v37 = (unsigned __int64)v12;
                v14 = *((_OWORD *)v10 + 3);
                *(_QWORD *)&v37 = 0;
                *(_OWORD *)v38.m256i_i8 = v13;
                v15 = *((_OWORD *)v10 + 4);
                *(_OWORD *)&v38.m256i_u64[2] = v14;
                v16 = *((_OWORD *)v10 + 5);
                v39[0] = v15;
                v17 = *((_OWORD *)v10 + 6);
                v39[1] = v16;
                v18 = *((_OWORD *)v10 + 7);
                v39[2] = v17;
                v19 = *((_OWORD *)v10 + 8);
                v39[3] = v18;
                v20 = *((_OWORD *)v10 + 9);
                v21 = v10[20];
                v39[4] = v19;
                v40 = v21;
                *(_OWORD *)&v38.m256i_u64[1] = 0;
                for ( v39[5] = v20; v11 < v38.m256i_i32[1]; *((_QWORD *)v39 + 7 * v22 + 1) = 0 )
                {
                  if ( v11 >= 2 )
                    break;
                  v22 = v11++;
                }
                appended = Dhcpv6AppendOption(&v36, 0xA8u, 3u, &v27, &v28, a1 + 4763);
                if ( appended )
                  goto LABEL_27;
              }
              appended = Dhcpv6AppendDefaultVendorClassOption(&v27, (u_short **)&v28, a1 + 4763);
              if ( !appended )
              {
                v24 = *(void **)(a1 + 656);
                v33 = 16;
                if ( !v24 )
                {
LABEL_20:
                  appended = Dhcpv6AppendSendOptions(
                               a1,
                               (_QWORD **)(a1 + 616),
                               *(_QWORD *)(a1 + 656),
                               *(_DWORD *)(a1 + 664),
                               &v28,
                               &v27,
                               a1 + 4763,
                               (__int64)&v33,
                               &v29,
                               (__int64)v35,
                               &v32,
                               &v36,
                               &v30);
                  if ( !appended
                    && (!v30
                     || v28 + (unsigned __int64)v30 > a1 + 4763
                     || (appended = Dhcpv6AppendOption(&v36, v30, 0x11u, &v27, &v28, a1 + 4763)) == 0) )
                  {
                    *a3 = v27;
                    return appended;
                  }
                  goto LABEL_27;
                }
                appended = Dhcpv6AppendUserClassOption(v24, *(unsigned __int8 *)(a1 + 664), v23, &v27, &v28, a1 + 4763);
                if ( !appended )
                {
                  AddToArray((__int64)&v33, v25, &v29, 15);
                  goto LABEL_20;
                }
              }
            }
          }
LABEL_27:
          if ( (xmmword_1800423E0 & 2) != 0 )
            WPP_SF_SD(
              1025,
              77,
              (unsigned int)WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids,
              *(_QWORD *)(a1 + 56),
              appended);
          goto LABEL_29;
        }
      }
    }
  }
  appended = 87;
  if ( (xmmword_1800423E0 & 2) != 0 )
  {
    WPP_SF_D(1025, 75, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, 87);
    goto LABEL_27;
  }
LABEL_29:
  if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 4) != 0 )
    McTemplateU0qq_EtwEventWriteTransfer(a1, ErrorCreatingPacket, *(unsigned int *)(a1 + 48), appended);
  TraceLogErrorv6(a1, appended, 22);
  return appended;
}

```

## disassembly

```asm
0x180001ed4  mov     [rsp-8+arg_8], rbx
0x180001ed9  mov     [rsp-8+arg_18], rsi
0x180001ede  push    rbp
0x180001edf  push    rdi
0x180001ee0  push    r12
0x180001ee2  push    r14
0x180001ee4  push    r15
0x180001ee6  lea     rbp, [rsp-1140h]
0x180001eee  mov     eax, 1240h
0x180001ef3  call    _alloca_probe
0x180001ef8  sub     rsp, rax
0x180001efb  mov     rax, cs:__security_cookie
0x180001f02  xor     rax, rsp
0x180001f05  mov     [rbp+1160h+var_30], rax
0x180001f0c  mov     [rbp+1160h+var_11E0], 0
0x180001f13  mov     r12, r8
0x180001f16  mov     [rbp+1160h+var_11D4], 0
0x180001f1d  mov     r14, rdx
0x180001f20  mov     [rbp+1160h+Src], 0
0x180001f27  mov     rdi, rcx
0x180001f2a  test    rcx, rcx
0x180001f2d  jz      loc_18000227C
0x180001f33  test    rdx, rdx
0x180001f36  jz      loc_18000227C
0x180001f3c  lea     rbx, [rcx+29Ch]
0x180001f43  test    rbx, rbx
0x180001f46  jz      loc_18000227C
0x180001f4c  test    r8, r8
0x180001f4f  jz      loc_18000227C
0x180001f55  mov     r15d, 10h
0x180001f5b  test    byte ptr cs:xmmword_1800423E0, r15b
0x180001f62  jz      short loc_180001F7D
0x180001f64  mov     r9, [rdi+38h]
0x180001f68  lea     edx, [r15+3Ch]
0x180001f6c  mov     ecx, 404h
0x180001f71  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x180001f78  call    WPP_SF_S
0x180001f7d  xor     edx, edx; Val
0x180001f7f  lea     rcx, [rbp+1160h+var_11CE]; void *
0x180001f83  mov     r8d, 0C6h; Size
0x180001f89  call    memset_0
0x180001f8e  xor     edx, edx; Val
0x180001f90  lea     rcx, [rbp+1160h+var_1100]; void *
0x180001f94  mov     r8d, 0C8h; Size
0x180001f9a  call    memset_0
0x180001f9f  movzx   eax, word ptr [r14]
0x180001fa3  lea     rsi, [rdi+129Bh]
0x180001faa  mov     ecx, 4
0x180001faf  mov     [rsp+1260h+var_1238], rsi; __int64
0x180001fb4  mov     [rbx], cl
0x180001fb6  lea     r9, [rsp+1260h+var_11F0]
0x180001fbb  mov     [rbx+1], ax
0x180001fbf  mov     edx, ecx
0x180001fc1  mov     al, [r14+2]
0x180001fc5  mov     [rbx+3], al
0x180001fc8  lea     r8d, [rcx+4]
0x180001fcc  lea     rax, [rbx+4]
0x180001fd0  mov     [rsp+1260h+var_11F0], ecx
0x180001fd4  mov     [rsp+1260h+var_11E8], rax
0x180001fd9  lea     rcx, [rbp+1160h+Src]; Src
0x180001fdd  lea     rax, [rsp+1260h+var_11E8]
0x180001fe2  mov     [rbp+1160h+var_11DC], 0
0x180001fe9  mov     [rsp+1260h+var_1240], rax; __int64
0x180001fee  call    Dhcpv6AppendOption
0x180001ff3  mov     ebx, eax
0x180001ff5  test    eax, eax
0x180001ff7  jnz     loc_1800022A1
0x180001ffd  lea     r14d, [rax+1]
0x180002001  mov     [rsp+1260h+var_1238], rsi; __int64
0x180002006  lea     rax, [rsp+1260h+var_11E8]
0x18000200b  mov     r8d, r14d
0x18000200e  mov     edx, r15d
0x180002011  mov     [rsp+1260h+var_1240], rax; __int64
0x180002016  lea     rcx, [rdi+1C8h]; Src
0x18000201d  lea     r9, [rsp+1260h+var_11F0]
0x180002022  call    Dhcpv6AppendOption
0x180002027  mov     ebx, eax
0x180002029  test    eax, eax
0x18000202b  jnz     loc_1800022A1
0x180002031  lea     r15, [rdi+68h]
0x180002035  mov     [rbp+1160h+var_11D0], r14w
0x18000203a  mov     r14, [r15]
0x18000203d  cmp     r14, r15
0x180002040  jz      loc_180002152
0x180002046  mov     rax, r14
0x180002049  xor     edx, edx
0x18000204b  mov     r14, [r14]
0x18000204e  movups  xmm0, xmmword ptr [rax]
0x180002051  movups  xmm1, xmmword ptr [rax+10h]
0x180002055  movups  [rbp+1160h+var_1030], xmm0
0x18000205c  movups  xmm0, xmmword ptr [rax+20h]
0x180002060  movups  [rbp+1160h+var_1020], xmm1
0x180002067  mov     qword ptr [rbp+1160h+var_1020+8], 0
0x180002072  movups  xmm1, xmmword ptr [rax+30h]
0x180002076  mov     qword ptr [rbp+1160h+var_1020], 0
0x180002081  movups  [rbp+1160h+var_1010], xmm0
0x180002088  movups  xmm0, xmmword ptr [rax+40h]
0x18000208c  movups  [rbp+1160h+var_1000], xmm1
0x180002093  movups  xmm1, xmmword ptr [rax+50h]
0x180002097  movups  [rbp+1160h+var_FF0], xmm0
0x18000209e  movups  xmm0, xmmword ptr [rax+60h]
0x1800020a2  movups  [rbp+1160h+var_FE0], xmm1
0x1800020a9  movups  xmm1, xmmword ptr [rax+70h]
0x1800020ad  movups  [rbp+1160h+var_FD0], xmm0
0x1800020b4  movups  xmm0, xmmword ptr [rax+80h]
0x1800020bb  movups  [rbp+1160h+var_FC0], xmm1
0x1800020c2  movups  xmm1, xmmword ptr [rax+90h]
0x1800020c9  mov     rax, [rax+0A0h]
0x1800020d0  movups  [rbp+1160h+var_FB0], xmm0
0x1800020d7  mov     [rbp+1160h+var_F90], rax
0x1800020de  xorps   xmm0, xmm0
0x1800020e1  movups  [rbp+1160h+var_1010+8], xmm0
0x1800020e8  movups  [rbp+1160h+var_FA0], xmm1
0x1800020ef  cmp     dword ptr [rbp+1160h+var_1010+4], edx
0x1800020f5  jbe     short loc_180002118
0x1800020f7  cmp     edx, 2
0x1800020fa  jnb     short loc_180002118
0x1800020fc  mov     eax, edx
0x1800020fe  inc     edx
0x180002100  imul    rcx, rax, 38h ; '8'
0x180002104  mov     qword ptr [rbp+rcx+1160h+var_FF0+8], 0
0x180002110  cmp     edx, dword ptr [rbp+1160h+var_1010+4]
0x180002116  jb      short loc_1800020F7
0x180002118  lea     rax, [rsp+1260h+var_11E8]
0x18000211d  mov     [rsp+1260h+var_1238], rsi; __int64
0x180002122  mov     edx, 0A8h
0x180002127  mov     [rsp+1260h+var_1240], rax; __int64
0x18000212c  mov     r8d, 3
0x180002132  lea     r9, [rsp+1260h+var_11F0]
0x180002137  lea     rcx, [rbp+1160h+var_1030]; Src
0x18000213e  call    Dhcpv6AppendOption
0x180002143  mov     ebx, eax
0x180002145  test    eax, eax
0x180002147  jz      loc_18000203D
0x18000214d  jmp     loc_1800022A1
0x180002152  mov     r8, rsi
0x180002155  lea     rdx, [rsp+1260h+var_11E8]
0x18000215a  lea     rcx, [rsp+1260h+var_11F0]
0x18000215f  call    Dhcpv6AppendDefaultVendorClassOption
0x180002164  mov     ebx, eax
0x180002166  test    eax, eax
0x180002168  jnz     loc_1800022A1
0x18000216e  mov     rcx, [rdi+290h]; Src
0x180002175  lea     eax, [rbx+10h]
0x180002178  mov     [rbp+1160h+var_11D0], ax
0x18000217c  test    rcx, rcx
0x18000217f  jz      short loc_1800021BC
0x180002181  movzx   edx, byte ptr [rdi+298h]
0x180002188  lea     rax, [rsp+1260h+var_11E8]
0x18000218d  mov     [rsp+1260h+var_1238], rsi; __int64
0x180002192  lea     r9, [rsp+1260h+var_11F0]
0x180002197  mov     [rsp+1260h+var_1240], rax; __int64
0x18000219c  call    Dhcpv6AppendUserClassOption
0x1800021a1  mov     ebx, eax
0x1800021a3  test    eax, eax
0x1800021a5  jnz     loc_1800022A1
0x1800021ab  lea     r9d, [rax+0Fh]
0x1800021af  lea     r8, [rbp+1160h+var_11E0]
0x1800021b3  lea     rcx, [rbp+1160h+var_11D0]
0x1800021b7  call    AddToArray
0x1800021bc  mov     r9d, [rdi+298h]
0x1800021c3  lea     rax, [rbp+1160h+var_11DC]
0x1800021c7  mov     r8, [rdi+290h]
0x1800021ce  lea     rdx, [rdi+268h]
0x1800021d5  mov     [rsp+1260h+var_1200], rax
0x1800021da  mov     rcx, rdi
0x1800021dd  lea     rax, [rbp+1160h+var_1030]
0x1800021e4  mov     [rsp+1260h+var_1208], rax
0x1800021e9  lea     rax, [rbp+1160h+var_11D4]
0x1800021ed  mov     [rsp+1260h+var_1210], rax
0x1800021f2  lea     rax, [rbp+1160h+var_1100]
0x1800021f6  mov     [rsp+1260h+var_1218], rax
0x1800021fb  lea     rax, [rbp+1160h+var_11E0]
0x1800021ff  mov     [rsp+1260h+var_1220], rax
0x180002204  lea     rax, [rbp+1160h+var_11D0]
0x180002208  mov     [rsp+1260h+var_1228], rax
0x18000220d  lea     rax, [rsp+1260h+var_11F0]
0x180002212  mov     [rsp+1260h+var_1230], rsi
0x180002217  mov     [rsp+1260h+var_1238], rax
0x18000221c  lea     rax, [rsp+1260h+var_11E8]
0x180002221  mov     [rsp+1260h+var_1240], rax
0x180002226  call    Dhcpv6AppendSendOptions
0x18000222b  mov     ebx, eax
0x18000222d  test    eax, eax
0x18000222f  jnz     short loc_1800022A1
0x180002231  mov     edx, [rbp+1160h+var_11DC]
0x180002234  test    edx, edx
0x180002236  jz      short loc_18000226E
0x180002238  mov     eax, edx
0x18000223a  add     rax, [rsp+1260h+var_11E8]
0x18000223f  cmp     rax, rsi
0x180002242  ja      short loc_18000226E
0x180002244  lea     rax, [rsp+1260h+var_11E8]
0x180002249  mov     [rsp+1260h+var_1238], rsi; __int64
0x18000224e  lea     r8d, [rbx+11h]
0x180002252  mov     [rsp+1260h+var_1240], rax; __int64
0x180002257  lea     r9, [rsp+1260h+var_11F0]
0x18000225c  lea     rcx, [rbp+1160h+var_1030]; Src
0x180002263  call    Dhcpv6AppendOption
0x180002268  mov     ebx, eax
0x18000226a  test    eax, eax
0x18000226c  jnz     short loc_1800022A1
0x18000226e  mov     eax, [rsp+1260h+var_11F0]
0x180002272  mov     [r12], eax
0x180002276  test    ebx, ebx
0x180002278  jnz     short loc_1800022A1
0x18000227a  jmp     short loc_1800022F4
0x18000227c  mov     ebx, 57h ; 'W'
0x180002281  test    byte ptr cs:xmmword_1800423E0, 2
0x180002288  jz      short loc_1800022C8
0x18000228a  lea     edx, [rbx-0Ch]
0x18000228d  mov     ecx, 401h
0x180002292  mov     r9d, ebx
0x180002295  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x18000229c  call    WPP_SF_D
0x1800022a1  test    byte ptr cs:xmmword_1800423E0, 2
0x1800022a8  jz      short loc_1800022C8
0x1800022aa  mov     r9, [rdi+38h]
0x1800022ae  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x1800022b5  mov     edx, 4Dh ; 'M'
0x1800022ba  mov     dword ptr [rsp+1260h+var_1240], ebx
0x1800022be  mov     ecx, 401h
0x1800022c3  call    WPP_SF_SD
0x1800022c8  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 4
0x1800022cf  jz      short loc_1800022E4
0x1800022d1  mov     r8d, [rdi+30h]
0x1800022d5  lea     rdx, ErrorCreatingPacket
0x1800022dc  mov     r9d, ebx
0x1800022df  call    McTemplateU0qq_EtwEventWriteTransfer
0x1800022e4  mov     r8d, 16h
0x1800022ea  mov     edx, ebx
0x1800022ec  mov     rcx, rdi
0x1800022ef  call    TraceLogErrorv6
0x1800022f4  mov     eax, ebx
0x1800022f6  mov     rcx, [rbp+1160h+var_30]
0x1800022fd  xor     rcx, rsp; StackCookie
0x180002300  call    __security_check_cookie
0x180002305  lea     r11, [rsp+1260h+var_20]
0x18000230d  mov     rbx, [r11+38h]
0x180002311  mov     rsi, [r11+48h]
0x180002315  mov     rsp, r11
0x180002318  pop     r15
0x18000231a  pop     r14
0x18000231c  pop     r12
0x18000231e  pop     rdi
0x18000231f  pop     rbp
0x180002320  retn
```
