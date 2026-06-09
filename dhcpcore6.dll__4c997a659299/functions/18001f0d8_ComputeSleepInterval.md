# ComputeSleepInterval

- ea: `0x18001f0d8`
- end: `0x18001f3a6`
- name: `ComputeSleepInterval`
- size: `718`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180014070`
- `0x180014590`
- `0x180020d50`
- `0x180021150`

## callees

- `0x180013028`
- `0x1800190c0`
- `0x180019ad0`
- `0x18001e5c0`
- `0x18001f0d8`
- `0x180020610`
- `0x180020940`
- `0x180028764`
- `0x18003205c`
- `0x180033900`
- `0x180033de4`
- `0x18003431c`

## pseudocode

```c
__int64 __fastcall ComputeSleepInterval(__int64 a1, int a2, int a3)
{
  int v6; // ebx
  unsigned int v7; // eax
  unsigned int v8; // ebx
  int v9; // ecx
  unsigned int v10; // r8d
  int IsMachineInCs; // r14d
  int v12; // eax
  unsigned int InfoRefreshTime; // eax
  __int64 v14; // rcx
  unsigned int v15; // eax
  int v16; // edi
  int v17; // edi
  int v18; // edi
  int v19; // edi
  int v20; // edi
  int v21; // edi
  int v22; // edi
  __int64 v23; // rdx
  unsigned int v25; // [rsp+30h] [rbp-30h] BYREF
  int v26; // [rsp+34h] [rbp-2Ch] BYREF
  int v27; // [rsp+38h] [rbp-28h] BYREF
  int v28; // [rsp+3Ch] [rbp-24h] BYREF
  int v29; // [rsp+40h] [rbp-20h] BYREF
  __int128 v30; // [rsp+48h] [rbp-18h] BYREF

  v25 = 0;
  v30 = 0;
  v29 = 0;
  v28 = 0;
  v26 = 0;
  v27 = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_SdD(a1, a2, a3, *(_QWORD *)(a1 + 56), a2, a3);
  v6 = Dhcpv6CheckDhcpv4Address(a1, &v27, &v26);
  v7 = IsDHCPV6AddrPlumbed(a1, &v30, &v29, &v28);
  if ( v6 && !v7 )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_(1028, 213, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
    v8 = 43200;
    goto LABEL_49;
  }
  IsMachineInCs = Dhcpv6IsMachineInCs(v7);
  switch ( a3 )
  {
    case 65:
      if ( (xmmword_1800423E0 & 0x10) != 0 )
        WPP_SF_(v10, 214, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
      v8 = -1;
      goto LABEL_49;
    case 1223:
      if ( (xmmword_1800423E0 & 0x10) != 0 )
        WPP_SF_(v10, 216, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
      v8 = IsMachineInCs != 0 ? 3600 : 300;
      goto LABEL_49;
    case 5006:
      if ( (xmmword_1800423E0 & 0x10) != 0 )
        WPP_SF_(v10, 215, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
      v8 = IsMachineInCs != 0 ? 3600 : 5;
      goto LABEL_49;
  }
  if ( !v9 )
  {
    v16 = a2 - 1;
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( !v17 )
        goto LABEL_35;
      v18 = v17 - 1;
      if ( !v18 )
        goto LABEL_35;
      v19 = v18 - 1;
      if ( v19 )
      {
        v20 = v19 - 1;
        if ( !v20 )
        {
          DhcpV6ComputeInitRetryInterval(a1, &v25);
          v8 = v25;
          goto LABEL_37;
        }
        v21 = v20 - 1;
        if ( v21 )
        {
          v22 = v21 - 1;
          if ( !v22 )
          {
            if ( (xmmword_1800423E0 & 2) != 0 )
            {
              v23 = 219;
              goto LABEL_32;
            }
LABEL_33:
            v8 = 3600;
LABEL_37:
            if ( IsMachineInCs && (int)v8 <= 3600 )
              v8 = 3600;
            goto LABEL_49;
          }
          if ( v22 == 1 )
          {
            if ( (xmmword_1800423E0 & 2) != 0 )
            {
              v23 = 220;
LABEL_32:
              WPP_SF_(1025, v23, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids);
              goto LABEL_33;
            }
            goto LABEL_33;
          }
        }
LABEL_35:
        v8 = 5;
        goto LABEL_37;
      }
    }
    v8 = -1;
    goto LABEL_37;
  }
  if ( g_fVelocityDhcpv6ContextBitfieldUpdate )
    v12 = *(_DWORD *)(a1 + 8880);
  else
    v12 = (*(_DWORD *)(a1 + 8860) >> 5) & 1;
  if ( v12 )
  {
    InfoRefreshTime = GetInfoRefreshTime(a1, &v25);
    v8 = v25;
    if ( (xmmword_1800423E0 & 0x10) == 0 )
      return v8;
    WPP_SF_Dd(v14, 217, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, InfoRefreshTime, v25);
  }
  else
  {
    v15 = CalculateTimeToSleep(a1);
    v8 = v15;
    if ( (xmmword_1800423E0 & 0x10) == 0 )
      return v8;
    WPP_SF_d(1028, 218, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, v15);
  }
LABEL_49:
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_d(1028, 221, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18001f0d8  mov     [rsp-28h+arg_8], rbx
0x18001f0dd  mov     [rsp-28h+arg_10], rsi
0x18001f0e2  push    rbp
0x18001f0e3  push    rdi
0x18001f0e4  push    r13
0x18001f0e6  push    r14
0x18001f0e8  push    r15
0x18001f0ea  mov     rbp, rsp
0x18001f0ed  sub     rsp, 60h
0x18001f0f1  mov     rax, cs:__security_cookie
0x18001f0f8  xor     rax, rsp
0x18001f0fb  mov     [rbp+var_8], rax
0x18001f0ff  xorps   xmm0, xmm0
0x18001f102  mov     [rbp+var_30], 0
0x18001f109  movups  [rbp+var_18], xmm0
0x18001f10d  mov     r15d, r8d
0x18001f110  mov     [rbp+var_20], 0
0x18001f117  mov     edi, edx
0x18001f119  mov     [rbp+var_24], 0
0x18001f120  mov     rsi, rcx
0x18001f123  mov     [rbp+var_2C], 0
0x18001f12a  mov     [rbp+var_28], 0
0x18001f131  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001f138  jz      short loc_18001F14C
0x18001f13a  mov     r9, [rcx+38h]
0x18001f13e  mov     [rsp+60h+var_38], r8d
0x18001f143  mov     [rsp+60h+var_40], edx
0x18001f147  call    WPP_SF_SdD
0x18001f14c  lea     r8, [rbp+var_2C]
0x18001f150  mov     rcx, rsi
0x18001f153  lea     rdx, [rbp+var_28]
0x18001f157  call    Dhcpv6CheckDhcpv4Address
0x18001f15c  lea     r9, [rbp+var_24]
0x18001f160  mov     rcx, rsi
0x18001f163  lea     r8, [rbp+var_20]
0x18001f167  mov     ebx, eax
0x18001f169  lea     rdx, [rbp+var_18]
0x18001f16d  call    IsDHCPV6AddrPlumbed
0x18001f172  lea     r13, WPP_d400c6d7dc7d3cccc0799e5e1f792179_Traceguids
0x18001f179  mov     ecx, eax
0x18001f17b  mov     r8d, 404h
0x18001f181  test    ebx, ebx
0x18001f183  jz      short loc_18001F1AC
0x18001f185  test    eax, eax
0x18001f187  jnz     short loc_18001F1AC
0x18001f189  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001f190  jz      short loc_18001F1A2
0x18001f192  mov     ecx, r8d
0x18001f195  mov     edx, 0D5h
0x18001f19a  mov     r8, r13
0x18001f19d  call    WPP_SF_
0x18001f1a2  mov     ebx, 0A8C0h
0x18001f1a7  jmp     loc_18001F360
0x18001f1ac  call    Dhcpv6IsMachineInCs
0x18001f1b1  mov     r14d, eax
0x18001f1b4  cmp     r15d, 41h ; 'A'
0x18001f1b8  jz      loc_18001F344
0x18001f1be  cmp     r15d, 4C7h
0x18001f1c5  jz      loc_18001F318
0x18001f1cb  cmp     r15d, 138Eh
0x18001f1d2  jz      loc_18001F2EC
0x18001f1d8  test    ecx, ecx
0x18001f1da  jz      loc_18001F264
0x18001f1e0  cmp     cs:g_fVelocityDhcpv6ContextBitfieldUpdate, 0
0x18001f1e7  jz      short loc_18001F1F1
0x18001f1e9  mov     eax, [rsi+22B0h]
0x18001f1ef  jmp     short loc_18001F1FD
0x18001f1f1  mov     eax, [rsi+229Ch]
0x18001f1f7  shr     eax, 5
0x18001f1fa  and     eax, 1
0x18001f1fd  mov     rcx, rsi
0x18001f200  test    eax, eax
0x18001f202  jz      short loc_18001F236
0x18001f204  lea     rdx, [rbp+var_30]
0x18001f208  call    GetInfoRefreshTime
0x18001f20d  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001f214  mov     ebx, [rbp+var_30]
0x18001f217  jz      loc_18001F37E
0x18001f21d  mov     edx, 0D9h
0x18001f222  mov     [rsp+60h+var_40], ebx
0x18001f226  mov     r9d, eax
0x18001f229  mov     r8, r13
0x18001f22c  call    WPP_SF_Dd
0x18001f231  jmp     loc_18001F360
0x18001f236  call    CalculateTimeToSleep
0x18001f23b  mov     ebx, eax
0x18001f23d  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001f244  jz      loc_18001F37E
0x18001f24a  mov     edx, 0DAh
0x18001f24f  mov     ecx, 404h
0x18001f254  mov     r9d, eax
0x18001f257  mov     r8, r13
0x18001f25a  call    WPP_SF_d
0x18001f25f  jmp     loc_18001F360
0x18001f264  mov     r15d, 0E10h
0x18001f26a  sub     edi, 1
0x18001f26d  jz      short loc_18001F2DA
0x18001f26f  sub     edi, 1
0x18001f272  jz      short loc_18001F2D3
0x18001f274  sub     edi, 1
0x18001f277  jz      short loc_18001F2D3
0x18001f279  sub     edi, 1
0x18001f27c  jz      short loc_18001F2DA
0x18001f27e  sub     edi, 1
0x18001f281  jz      short loc_18001F2C2
0x18001f283  sub     edi, 1
0x18001f286  jz      short loc_18001F2D3
0x18001f288  sub     edi, 1
0x18001f28b  jz      short loc_18001F2A2
0x18001f28d  sub     edi, 1
0x18001f290  jnz     short loc_18001F2D3
0x18001f292  test    byte ptr cs:xmmword_1800423E0, 2
0x18001f299  jz      short loc_18001F2BD
0x18001f29b  mov     edx, 0DCh
0x18001f2a0  jmp     short loc_18001F2B0
0x18001f2a2  test    byte ptr cs:xmmword_1800423E0, 2
0x18001f2a9  jz      short loc_18001F2BD
0x18001f2ab  mov     edx, 0DBh
0x18001f2b0  mov     r8, r13
0x18001f2b3  mov     ecx, 401h
0x18001f2b8  call    WPP_SF_
0x18001f2bd  mov     ebx, r15d
0x18001f2c0  jmp     short loc_18001F2DD
0x18001f2c2  lea     rdx, [rbp+var_30]
0x18001f2c6  mov     rcx, rsi
0x18001f2c9  call    DhcpV6ComputeInitRetryInterval
0x18001f2ce  mov     ebx, [rbp+var_30]
0x18001f2d1  jmp     short loc_18001F2DD
0x18001f2d3  mov     ebx, 5
0x18001f2d8  jmp     short loc_18001F2DD
0x18001f2da  or      ebx, 0FFFFFFFFh
0x18001f2dd  test    r14d, r14d
0x18001f2e0  jz      short loc_18001F360
0x18001f2e2  cmp     ebx, r15d
0x18001f2e5  jg      short loc_18001F360
0x18001f2e7  mov     ebx, r15d
0x18001f2ea  jmp     short loc_18001F360
0x18001f2ec  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001f2f3  jz      short loc_18001F305
0x18001f2f5  mov     ecx, r8d
0x18001f2f8  mov     edx, 0D7h
0x18001f2fd  mov     r8, r13
0x18001f300  call    WPP_SF_
0x18001f305  neg     r14d
0x18001f308  mov     ebx, 5
0x18001f30d  sbb     eax, eax
0x18001f30f  and     eax, 0E0Bh
0x18001f314  add     ebx, eax
0x18001f316  jmp     short loc_18001F360
0x18001f318  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001f31f  jz      short loc_18001F331
0x18001f321  mov     ecx, r8d
0x18001f324  mov     edx, 0D8h
0x18001f329  mov     r8, r13
0x18001f32c  call    WPP_SF_
0x18001f331  neg     r14d
0x18001f334  sbb     ebx, ebx
0x18001f336  and     ebx, 0CE4h
0x18001f33c  add     ebx, 12Ch
0x18001f342  jmp     short loc_18001F360
0x18001f344  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001f34b  jz      short loc_18001F35D
0x18001f34d  mov     ecx, r8d
0x18001f350  mov     edx, 0D6h
0x18001f355  mov     r8, r13
0x18001f358  call    WPP_SF_
0x18001f35d  or      ebx, 0FFFFFFFFh
0x18001f360  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001f367  jz      short loc_18001F37E
0x18001f369  mov     edx, 0DDh
0x18001f36e  mov     ecx, 404h
0x18001f373  mov     r9d, ebx
0x18001f376  mov     r8, r13
0x18001f379  call    WPP_SF_d
0x18001f37e  mov     eax, ebx
0x18001f380  mov     rcx, [rbp+var_8]
0x18001f384  xor     rcx, rsp; StackCookie
0x18001f387  call    __security_check_cookie
0x18001f38c  lea     r11, [rsp+60h+var_s0]
0x18001f391  mov     rbx, [r11+38h]
0x18001f395  mov     rsi, [r11+40h]
0x18001f399  mov     rsp, r11
0x18001f39c  pop     r15
0x18001f39e  pop     r14
0x18001f3a0  pop     r13
0x18001f3a2  pop     rdi
0x18001f3a3  pop     rbp
0x18001f3a4  retn
```
