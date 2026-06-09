# CreateDhcpv6Decline

- ea: `0x1800170cc`
- end: `0x180017360`
- name: `CreateDhcpv6Decline`
- size: `660`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180016f8c`

## callees

- `0x180001d8c`
- `0x180002cac`
- `0x180004b30`
- `0x18000ed3c`
- `0x1800170cc`
- `0x180019ad0`
- `0x1800337d0`
- `0x1800338c0`
- `0x180033970`

## pseudocode

```c
__int64 __fastcall CreateDhcpv6Decline(__int64 a1, __int16 *a2, int *a3)
{
  __int64 v6; // rbx
  __int16 v7; // ax
  __int64 v8; // rdx
  unsigned int appended; // ebx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  _QWORD *v13; // rsi
  void *v14; // rcx
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD Src[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[208]; // [rsp+50h] [rbp-B0h] BYREF

  v17 = 0;
  Src[0] = 0;
  if ( !a1 || !a2 || (v6 = a1 + 668, a1 == -668) || !a3 )
  {
    appended = 87;
    if ( (xmmword_1800423E0 & 2) == 0 )
    {
LABEL_19:
      if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 4) != 0 )
        McTemplateU0qq_EtwEventWriteTransfer(a1, (__int64)ErrorCreatingPacket, *(unsigned int *)(a1 + 48), appended);
      TraceLogErrorv6(a1, appended, 24);
      return appended;
    }
    WPP_SF_D(1025, 81, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, 87);
LABEL_17:
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_SD(1025, 83, (unsigned int)WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *(_QWORD *)(a1 + 56), appended);
    goto LABEL_19;
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_S(1028, 82, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, *(_QWORD *)(a1 + 56));
  v7 = *a2;
  *(_BYTE *)v6 = 9;
  *(_WORD *)(v6 + 1) = v7;
  *(_BYTE *)(v6 + 3) = *((_BYTE *)a2 + 2);
  v18 = v6 + 4;
  v16 = 4;
  appended = Dhcpv6AppendOption(Src, 4u, 8u, &v16, &v18, a1 + 4763);
  if ( appended )
    goto LABEL_17;
  AddToArray((__int64)v20, v8, &v17, 8);
  appended = Dhcpv6AppendOption((void *)(a1 + 456), 0x10u, 1u, &v16, &v18, a1 + 4763);
  if ( appended )
    goto LABEL_17;
  AddToArray((__int64)v20, v10, &v17, 1);
  appended = Dhcpv6AppendOption((void *)(a1 + 480), 0x10u, 2u, &v16, &v18, a1 + 4763);
  if ( appended )
    goto LABEL_17;
  AddToArray((__int64)v20, v11, &v17, 2);
  v13 = *(_QWORD **)(a1 + 176);
  while ( v13 != (_QWORD *)(a1 + 176) )
  {
    v14 = v13;
    v13 = (_QWORD *)*v13;
    appended = Dhcpv6AppendOption(v14, 0xA8u, 3u, &v16, &v18, a1 + 4763);
    if ( appended )
      goto LABEL_17;
  }
  AddToArray((__int64)v20, v12, &v17, 3);
  *a3 = v16;
  return appended;
}

```

## disassembly

```asm
0x1800170cc  mov     [rsp-8+arg_8], rbx
0x1800170d1  mov     [rsp-8+arg_18], rsi
0x1800170d6  push    rbp
0x1800170d7  push    rdi
0x1800170d8  push    r12
0x1800170da  push    r14
0x1800170dc  push    r15
0x1800170de  lea     rbp, [rsp-30h]
0x1800170e3  sub     rsp, 130h
0x1800170ea  mov     rax, cs:__security_cookie
0x1800170f1  xor     rax, rsp
0x1800170f4  mov     [rbp+50h+var_30], rax
0x1800170f8  mov     [rsp+150h+var_11C], 0
0x180017100  mov     r15, r8
0x180017103  mov     [rsp+150h+Src], 0
0x18001710b  mov     rsi, rdx
0x18001710e  mov     rdi, rcx
0x180017111  test    rcx, rcx
0x180017114  jz      loc_1800172BD
0x18001711a  test    rdx, rdx
0x18001711d  jz      loc_1800172BD
0x180017123  lea     rbx, [rcx+29Ch]
0x18001712a  test    rbx, rbx
0x18001712d  jz      loc_1800172BD
0x180017133  test    r8, r8
0x180017136  jz      loc_1800172BD
0x18001713c  mov     r14d, 10h
0x180017142  test    byte ptr cs:xmmword_1800423E0, r14b
0x180017149  jz      short loc_180017164
0x18001714b  mov     r9, [rdi+38h]
0x18001714f  lea     edx, [r14+42h]
0x180017153  mov     ecx, 404h
0x180017158  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x18001715f  call    WPP_SF_S
0x180017164  movzx   eax, word ptr [rsi]
0x180017167  lea     r12, [rdi+129Bh]
0x18001716e  mov     byte ptr [rbx], 9
0x180017171  lea     r9, [rsp+150h+var_120]
0x180017176  mov     [rbx+1], ax
0x18001717a  lea     rcx, [rsp+150h+Src]; Src
0x18001717f  mov     al, [rsi+2]
0x180017182  mov     esi, 8
0x180017187  mov     [rbx+3], al
0x18001718a  mov     r8d, esi
0x18001718d  lea     rax, [rbx+4]
0x180017191  mov     [rsp+150h+var_128], r12; __int64
0x180017196  mov     [rsp+150h+var_118], rax
0x18001719b  lea     rax, [rsp+150h+var_118]
0x1800171a0  lea     edx, [rsi-4]
0x1800171a3  mov     [rsp+150h+var_130], rax; __int64
0x1800171a8  mov     [rsp+150h+var_120], 4
0x1800171b0  call    Dhcpv6AppendOption
0x1800171b5  mov     ebx, eax
0x1800171b7  test    eax, eax
0x1800171b9  jnz     loc_1800172E2
0x1800171bf  mov     r9d, esi
0x1800171c2  lea     r8, [rsp+150h+var_11C]
0x1800171c7  lea     rcx, [rsp+150h+var_100]
0x1800171cc  call    AddToArray
0x1800171d1  lea     rax, [rsp+150h+var_118]
0x1800171d6  mov     [rsp+150h+var_128], r12; __int64
0x1800171db  lea     esi, [rbx+1]
0x1800171de  mov     [rsp+150h+var_130], rax; __int64
0x1800171e3  mov     r8d, esi
0x1800171e6  lea     rcx, [rdi+1C8h]; Src
0x1800171ed  mov     edx, r14d
0x1800171f0  lea     r9, [rsp+150h+var_120]
0x1800171f5  call    Dhcpv6AppendOption
0x1800171fa  mov     ebx, eax
0x1800171fc  test    eax, eax
0x1800171fe  jnz     loc_1800172E2
0x180017204  mov     r9d, esi
0x180017207  lea     r8, [rsp+150h+var_11C]
0x18001720c  lea     rcx, [rsp+150h+var_100]
0x180017211  call    AddToArray
0x180017216  lea     rax, [rsp+150h+var_118]
0x18001721b  mov     [rsp+150h+var_128], r12; __int64
0x180017220  lea     r8d, [rsi+1]
0x180017224  mov     [rsp+150h+var_130], rax; __int64
0x180017229  mov     edx, r14d
0x18001722c  lea     rcx, [rdi+1E0h]; Src
0x180017233  lea     r9, [rsp+150h+var_120]
0x180017238  call    Dhcpv6AppendOption
0x18001723d  mov     ebx, eax
0x18001723f  test    eax, eax
0x180017241  jnz     loc_1800172E2
0x180017247  lea     r9d, [rsi+1]
0x18001724b  lea     r8, [rsp+150h+var_11C]
0x180017250  lea     rcx, [rsp+150h+var_100]
0x180017255  call    AddToArray
0x18001725a  lea     r14, [rdi+0B0h]
0x180017261  mov     rsi, [r14]
0x180017264  cmp     rsi, r14
0x180017267  jz      short loc_18001729B
0x180017269  lea     rax, [rsp+150h+var_118]
0x18001726e  mov     [rsp+150h+var_128], r12; __int64
0x180017273  mov     rcx, rsi; Src
0x180017276  mov     [rsp+150h+var_130], rax; __int64
0x18001727b  mov     rsi, [rsi]
0x18001727e  lea     r9, [rsp+150h+var_120]
0x180017283  mov     edx, 0A8h
0x180017288  mov     r8d, 3
0x18001728e  call    Dhcpv6AppendOption
0x180017293  mov     ebx, eax
0x180017295  test    eax, eax
0x180017297  jz      short loc_180017264
0x180017299  jmp     short loc_1800172E2
0x18001729b  mov     r9d, 3
0x1800172a1  lea     r8, [rsp+150h+var_11C]
0x1800172a6  lea     rcx, [rsp+150h+var_100]
0x1800172ab  call    AddToArray
0x1800172b0  mov     ecx, [rsp+150h+var_120]
0x1800172b4  mov     [r15], ecx
0x1800172b7  test    ebx, ebx
0x1800172b9  jnz     short loc_1800172E2
0x1800172bb  jmp     short loc_180017335
0x1800172bd  mov     ebx, 57h ; 'W'
0x1800172c2  test    byte ptr cs:xmmword_1800423E0, 2
0x1800172c9  jz      short loc_180017309
0x1800172cb  lea     edx, [rbx-6]
0x1800172ce  mov     ecx, 401h
0x1800172d3  mov     r9d, ebx
0x1800172d6  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x1800172dd  call    WPP_SF_D
0x1800172e2  test    byte ptr cs:xmmword_1800423E0, 2
0x1800172e9  jz      short loc_180017309
0x1800172eb  mov     r9, [rdi+38h]
0x1800172ef  lea     r8, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x1800172f6  mov     edx, 53h ; 'S'
0x1800172fb  mov     dword ptr [rsp+150h+var_130], ebx
0x1800172ff  mov     ecx, 401h
0x180017304  call    WPP_SF_SD
0x180017309  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 4
0x180017310  jz      short loc_180017325
0x180017312  mov     r8d, [rdi+30h]
0x180017316  lea     rdx, ErrorCreatingPacket
0x18001731d  mov     r9d, ebx
0x180017320  call    McTemplateU0qq_EtwEventWriteTransfer
0x180017325  mov     r8d, 18h
0x18001732b  mov     edx, ebx
0x18001732d  mov     rcx, rdi
0x180017330  call    TraceLogErrorv6
0x180017335  mov     eax, ebx
0x180017337  mov     rcx, [rbp+50h+var_30]
0x18001733b  xor     rcx, rsp; StackCookie
0x18001733e  call    __security_check_cookie
0x180017343  lea     r11, [rsp+150h+var_20]
0x18001734b  mov     rbx, [r11+38h]
0x18001734f  mov     rsi, [r11+48h]
0x180017353  mov     rsp, r11
0x180017356  pop     r15
0x180017358  pop     r14
0x18001735a  pop     r12
0x18001735c  pop     rdi
0x18001735d  pop     rbp
0x18001735e  retn
```
