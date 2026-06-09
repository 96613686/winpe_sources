# CScrubJetInstance::SetupInstanceParameters(unsigned __int64 *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x18002dcf8`
- end: `0x18002e15f`
- name: `?SetupInstanceParameters@CScrubJetInstance@@CAJPEA_KPEBG111@Z`
- size: `1127`
- prototype: `__int64 __fastcall(JET_INSTANCE *pinstance, JET_PCWSTR szParam, JET_PCWSTR, JET_PCWSTR, JET_PCWSTR)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18002e168`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x180006584`
- `0x180006688`
- `0x18002dcf8`

## import_xrefs

- `ESENT!JetSetSystemParameterW` at `0x18002ddcd`
- `ESENT!JetSetSystemParameterW` at `0x18002de14`
- `ESENT!JetSetSystemParameterW` at `0x18002de9f`
- `ESENT!JetSetSystemParameterW` at `0x18002df1f`
- `ESENT!JetSetSystemParameterW` at `0x18002df9a`
- `ESENT!JetSetSystemParameterW` at `0x18002e017`
- `ESENT!JetSetSystemParameterW` at `0x18002e065`
- `ESENT!JetSetSystemParameterW` at `0x18002e0b5`
- `ESENT!JetSetSystemParameterW` at `0x18002e103`
- `ESENT!JetSetSystemParameterW` at `0x18002ddcd`
- `ESENT!JetSetSystemParameterW` at `0x18002de14`
- `ESENT!JetSetSystemParameterW` at `0x18002de9f`
- `ESENT!JetSetSystemParameterW` at `0x18002df1f`
- `ESENT!JetSetSystemParameterW` at `0x18002df9a`
- `ESENT!JetSetSystemParameterW` at `0x18002e017`
- `ESENT!JetSetSystemParameterW` at `0x18002e065`
- `ESENT!JetSetSystemParameterW` at `0x18002e0b5`
- `ESENT!JetSetSystemParameterW` at `0x18002e103`

## pseudocode

```c
__int64 __fastcall CScrubJetInstance::SetupInstanceParameters(
        JET_INSTANCE *pinstance,
        JET_PCWSTR szParam,
        JET_PCWSTR a3,
        JET_PCWSTR a4,
        JET_PCWSTR a5)
{
  USHORT Length; // cx
  __int64 v10; // r11
  USHORT v11; // dx
  USHORT v12; // ax
  JET_ERR v13; // edi
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // ebx
  int v17; // eax
  const char *v19; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v20; // [rsp+38h] [rbp-18h]
  USHORT v21; // [rsp+40h] [rbp-10h]
  USHORT v22; // [rsp+42h] [rbp-Eh]
  int v23; // [rsp+44h] [rbp-Ch]
  char *v24; // [rsp+48h] [rbp-8h]

  Length = GlobalIndentString.Length;
  v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v19 = "CScrubJetInstance::SetupInstanceParameters";
  v11 = ++*(_WORD *)(v10 + 8);
  *(_QWORD *)(v10 + 16) = "CScrubJetInstance::SetupInstanceParameters";
  v12 = Length;
  if ( v11 < Length )
  {
    v12 = v11;
    Length = v11;
  }
  v21 = v12;
  v23 = 0;
  v24 = off_180047060;
  v22 = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrubJetInstance::SetupInstanceParameters");
  }
  JetSetSystemParameterW(pinstance, 0, 0x81u, 0, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids, szParam);
  }
  v13 = JetSetSystemParameterW(pinstance, 0, 3u, 0, szParam);
  if ( v13 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v15 = 26;
    goto LABEL_25;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids, a3);
  }
  v13 = JetSetSystemParameterW(pinstance, 0, 2u, 0, a3);
  if ( v13 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v15 = 28;
    goto LABEL_25;
  }
  v13 = JetSetSystemParameterW(pinstance, 0, 0x71u, 0, a3);
  if ( v13 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v15 = 29;
    goto LABEL_25;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids, a4);
  }
  v13 = JetSetSystemParameterW(pinstance, 0, 0, 0, a4);
  if ( v13 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v15 = 31;
    goto LABEL_25;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids, a5);
  }
  v13 = JetSetSystemParameterW(pinstance, 0, 1u, 0, a5);
  if ( v13 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v15 = 33;
    goto LABEL_25;
  }
  v13 = JetSetSystemParameterW(pinstance, 0, 0x64u, 1u, 0);
  if ( v13 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v15 = 34;
    goto LABEL_25;
  }
  v13 = JetSetSystemParameterW(pinstance, 0, 0x88u, 0, 0);
  if ( v13 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_26;
    }
    v15 = 35;
    goto LABEL_25;
  }
  v13 = JetSetSystemParameterW(pinstance, 0, 0x11u, 1u, 0);
  if ( !v13 )
  {
    v20 = 0;
    v16 = 0;
    goto LABEL_71;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = 36;
LABEL_25:
    WPP_SF_d(v14[2], v15, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids, (unsigned int)v13);
  }
LABEL_26:
  if ( v13 == -1011 )
  {
    v16 = -2147024882;
  }
  else
  {
    v17 = -v13;
    if ( v13 > 0 )
      LOWORD(v17) = v13;
    v16 = v13 & 0x8E5E0000 | (unsigned __int16)v17 | 0xE5E0000;
  }
  v20 = v16;
LABEL_71:
  CHResultImp::~CHResultImp((CHResultImp *)&v19);
  return v16;
}

```

## disassembly

```asm
0x18002dcf8  push    rbp
0x18002dcfa  push    rbx
0x18002dcfb  push    rsi
0x18002dcfc  push    rdi
0x18002dcfd  push    r12
0x18002dcff  push    r14
0x18002dd01  push    r15
0x18002dd03  mov     rbp, rsp
0x18002dd06  sub     rsp, 50h
0x18002dd0a  mov     rax, gs:58h
0x18002dd13  mov     rbx, rdx
0x18002dd16  mov     r10d, cs:_tls_index
0x18002dd1d  mov     rsi, rcx
0x18002dd20  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18002dd27  mov     r12d, 1
0x18002dd2d  mov     edx, 8
0x18002dd32  mov     r14, r8
0x18002dd35  lea     r8, aCscrubjetinsta_0; "CScrubJetInstance::SetupInstanceParamet"...
0x18002dd3c  mov     r15, r9
0x18002dd3f  mov     r11, [rax+r10*8]
0x18002dd43  mov     eax, 10h
0x18002dd48  mov     [rbp+var_20], r8
0x18002dd4c  add     [rdx+r11], r12w
0x18002dd51  movzx   edx, word ptr [rdx+r11]
0x18002dd56  mov     [rax+r11], r8
0x18002dd5a  cmp     dx, cx
0x18002dd5d  movzx   eax, cx
0x18002dd60  cmovb   ax, dx
0x18002dd64  cmovb   cx, dx
0x18002dd68  mov     [rbp+var_10], ax
0x18002dd6c  xor     eax, eax
0x18002dd6e  mov     [rbp+var_C], eax
0x18002dd71  mov     rax, cs:off_180047060; "                                       "...
0x18002dd78  mov     [rbp+var_8], rax
0x18002dd7c  mov     [rbp+var_E], cx
0x18002dd80  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dd87  lea     rdi, WPP_GLOBAL_Control
0x18002dd8e  cmp     rcx, rdi
0x18002dd91  jz      short loc_18002DDB6
0x18002dd93  test    [rcx+1Ch], r12b
0x18002dd97  jz      short loc_18002DDB6
0x18002dd99  cmp     byte ptr [rcx+19h], 5
0x18002dd9d  jb      short loc_18002DDB6
0x18002dd9f  mov     rcx, [rcx+10h]; LoggerHandle
0x18002dda3  lea     edx, [r12+0Ch]
0x18002dda8  lea     r9, [rbp+var_10]
0x18002ddac  mov     [rsp+50h+szParam], r8; __int64
0x18002ddb1  call    WPP_SF_aZs
0x18002ddb6  xor     r9d, r9d; lParam
0x18002ddb9  mov     [rsp+50h+szParam], 0; szParam
0x18002ddc2  xor     edx, edx; sesid
0x18002ddc4  mov     r8d, 81h; paramid
0x18002ddca  mov     rcx, rsi; pinstance
0x18002ddcd  call    cs:__imp_JetSetSystemParameterW
0x18002ddd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ddda  cmp     rcx, rdi
0x18002dddd  jz      short loc_18002DE03
0x18002dddf  test    [rcx+1Ch], r12b
0x18002dde3  jz      short loc_18002DE03
0x18002dde5  cmp     byte ptr [rcx+19h], 4
0x18002dde9  jb      short loc_18002DE03
0x18002ddeb  mov     rcx, [rcx+10h]
0x18002ddef  lea     r8, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids
0x18002ddf6  mov     edx, 19h
0x18002ddfb  mov     r9, rbx
0x18002ddfe  call    WPP_SF_S
0x18002de03  xor     r9d, r9d; lParam
0x18002de06  mov     [rsp+50h+szParam], rbx; szParam
0x18002de0b  xor     edx, edx; sesid
0x18002de0d  mov     rcx, rsi; pinstance
0x18002de10  lea     r8d, [r9+3]; paramid
0x18002de14  call    cs:__imp_JetSetSystemParameterW
0x18002de1a  mov     edi, eax
0x18002de1c  test    eax, eax
0x18002de1e  jz      short loc_18002DE54
0x18002de20  mov     rcx, cs:WPP_GLOBAL_Control
0x18002de27  lea     rax, WPP_GLOBAL_Control
0x18002de2e  cmp     rcx, rax
0x18002de31  jz      loc_18002DEDF
0x18002de37  test    [rcx+1Ch], r12b
0x18002de3b  jz      loc_18002DEDF
0x18002de41  mov     ebx, 2
0x18002de46  cmp     [rcx+19h], bl
0x18002de49  jb      loc_18002DEDF
0x18002de4f  lea     edx, [rbx+18h]
0x18002de52  jmp     short loc_18002DECC
0x18002de54  mov     rcx, cs:WPP_GLOBAL_Control
0x18002de5b  lea     rax, WPP_GLOBAL_Control
0x18002de62  cmp     rcx, rax
0x18002de65  jz      short loc_18002DE8B
0x18002de67  test    [rcx+1Ch], r12b
0x18002de6b  jz      short loc_18002DE8B
0x18002de6d  cmp     byte ptr [rcx+19h], 4
0x18002de71  jb      short loc_18002DE8B
0x18002de73  mov     rcx, [rcx+10h]
0x18002de77  lea     r8, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids
0x18002de7e  mov     edx, 1Bh
0x18002de83  mov     r9, r14
0x18002de86  call    WPP_SF_S
0x18002de8b  xor     r9d, r9d; lParam
0x18002de8e  mov     [rsp+50h+szParam], r14; szParam
0x18002de93  xor     edx, edx; sesid
0x18002de95  mov     rcx, rsi; pinstance
0x18002de98  lea     ebx, [r9+2]
0x18002de9c  mov     r8d, ebx; paramid
0x18002de9f  call    cs:__imp_JetSetSystemParameterW
0x18002dea5  mov     edi, eax
0x18002dea7  test    eax, eax
0x18002dea9  jz      short loc_18002DF0E
0x18002deab  mov     rcx, cs:WPP_GLOBAL_Control
0x18002deb2  lea     rax, WPP_GLOBAL_Control
0x18002deb9  cmp     rcx, rax
0x18002debc  jz      short loc_18002DEDF
0x18002debe  test    [rcx+1Ch], r12b
0x18002dec2  jz      short loc_18002DEDF
0x18002dec4  cmp     [rcx+19h], bl
0x18002dec7  jb      short loc_18002DEDF
0x18002dec9  lea     edx, [rbx+1Ah]
0x18002decc  mov     rcx, [rcx+10h]
0x18002ded0  lea     r8, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids
0x18002ded7  mov     r9d, edi
0x18002deda  call    WPP_SF_d
0x18002dedf  cmp     edi, 0FFFFFC0Dh
0x18002dee5  jnz     short loc_18002DEEE
0x18002dee7  mov     ebx, 8007000Eh
0x18002deec  jmp     short loc_18002DF06
0x18002deee  mov     eax, edi
0x18002def0  neg     eax
0x18002def2  cmovs   eax, edi
0x18002def5  and     edi, 8E5E0000h
0x18002defb  movzx   ebx, ax
0x18002defe  or      ebx, edi
0x18002df00  or      ebx, 0E5E0000h
0x18002df06  mov     [rbp+var_18], ebx
0x18002df09  jmp     loc_18002E145
0x18002df0e  xor     r9d, r9d; lParam
0x18002df11  mov     [rsp+50h+szParam], r14; szParam
0x18002df16  xor     edx, edx; sesid
0x18002df18  mov     rcx, rsi; pinstance
0x18002df1b  lea     r8d, [r9+71h]; paramid
0x18002df1f  call    cs:__imp_JetSetSystemParameterW
0x18002df25  mov     edi, eax
0x18002df27  test    eax, eax
0x18002df29  jz      short loc_18002DF53
0x18002df2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df32  lea     rax, WPP_GLOBAL_Control
0x18002df39  cmp     rcx, rax
0x18002df3c  jz      short loc_18002DEDF
0x18002df3e  test    [rcx+1Ch], r12b
0x18002df42  jz      short loc_18002DEDF
0x18002df44  cmp     [rcx+19h], bl
0x18002df47  jb      short loc_18002DEDF
0x18002df49  mov     edx, 1Dh
0x18002df4e  jmp     loc_18002DECC
0x18002df53  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df5a  lea     r14, WPP_GLOBAL_Control
0x18002df61  cmp     rcx, r14
0x18002df64  jz      short loc_18002DF8A
0x18002df66  test    [rcx+1Ch], r12b
0x18002df6a  jz      short loc_18002DF8A
0x18002df6c  cmp     byte ptr [rcx+19h], 4
0x18002df70  jb      short loc_18002DF8A
0x18002df72  mov     rcx, [rcx+10h]
0x18002df76  lea     r8, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids
0x18002df7d  mov     edx, 1Eh
0x18002df82  mov     r9, r15
0x18002df85  call    WPP_SF_S
0x18002df8a  xor     r9d, r9d; lParam
0x18002df8d  mov     [rsp+50h+szParam], r15; szParam
0x18002df92  xor     r8d, r8d; paramid
0x18002df95  xor     edx, edx; sesid
0x18002df97  mov     rcx, rsi; pinstance
0x18002df9a  call    cs:__imp_JetSetSystemParameterW
0x18002dfa0  mov     edi, eax
0x18002dfa2  test    eax, eax
0x18002dfa4  jz      short loc_18002DFD3
0x18002dfa6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dfad  cmp     rcx, r14
0x18002dfb0  jz      loc_18002DEDF
0x18002dfb6  test    [rcx+1Ch], r12b
0x18002dfba  jz      loc_18002DEDF
0x18002dfc0  cmp     [rcx+19h], bl
0x18002dfc3  jb      loc_18002DEDF
0x18002dfc9  mov     edx, 1Fh
0x18002dfce  jmp     loc_18002DECC
0x18002dfd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dfda  mov     rdi, [rbp+arg_20]
0x18002dfde  cmp     rcx, r14
0x18002dfe1  jz      short loc_18002E007
0x18002dfe3  test    [rcx+1Ch], r12b
0x18002dfe7  jz      short loc_18002E007
0x18002dfe9  cmp     byte ptr [rcx+19h], 4
0x18002dfed  jb      short loc_18002E007
0x18002dfef  mov     rcx, [rcx+10h]
0x18002dff3  lea     r8, WPP_beed2d521a61361b55f6693bb3ef5cb4_Traceguids
0x18002dffa  mov     edx, 20h ; ' '
0x18002dfff  mov     r9, rdi
0x18002e002  call    WPP_SF_S
0x18002e007  xor     r9d, r9d; lParam
0x18002e00a  mov     [rsp+50h+szParam], rdi; szParam
0x18002e00f  mov     r8d, r12d; paramid
0x18002e012  xor     edx, edx; sesid
0x18002e014  mov     rcx, rsi; pinstance
0x18002e017  call    cs:__imp_JetSetSystemParameterW
0x18002e01d  mov     edi, eax
0x18002e01f  test    eax, eax
0x18002e021  jz      short loc_18002E050
0x18002e023  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e02a  cmp     rcx, r14
0x18002e02d  jz      loc_18002DEDF
0x18002e033  test    [rcx+1Ch], r12b
0x18002e037  jz      loc_18002DEDF
0x18002e03d  cmp     [rcx+19h], bl
0x18002e040  jb      loc_18002DEDF
0x18002e046  mov     edx, 21h ; '!'
0x18002e04b  jmp     loc_18002DECC
0x18002e050  xor     edx, edx; sesid
0x18002e052  mov     [rsp+50h+szParam], 0; szParam
0x18002e05b  mov     r9, r12; lParam
0x18002e05e  mov     rcx, rsi; pinstance
0x18002e061  lea     r8d, [rdx+64h]; paramid
0x18002e065  call    cs:__imp_JetSetSystemParameterW
0x18002e06b  mov     edi, eax
0x18002e06d  test    eax, eax
0x18002e06f  jz      short loc_18002E09E
0x18002e071  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e078  cmp     rcx, r14
0x18002e07b  jz      loc_18002DEDF
0x18002e081  test    [rcx+1Ch], r12b
0x18002e085  jz      loc_18002DEDF
0x18002e08b  cmp     [rcx+19h], bl
0x18002e08e  jb      loc_18002DEDF
0x18002e094  mov     edx, 22h ; '"'
0x18002e099  jmp     loc_18002DECC
0x18002e09e  xor     r9d, r9d; lParam
0x18002e0a1  mov     [rsp+50h+szParam], 0; szParam
0x18002e0aa  xor     edx, edx; sesid
0x18002e0ac  mov     r8d, 88h; paramid
0x18002e0b2  mov     rcx, rsi; pinstance
0x18002e0b5  call    cs:__imp_JetSetSystemParameterW
0x18002e0bb  mov     edi, eax
0x18002e0bd  test    eax, eax
0x18002e0bf  jz      short loc_18002E0EE
0x18002e0c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e0c8  cmp     rcx, r14
0x18002e0cb  jz      loc_18002DEDF
0x18002e0d1  test    [rcx+1Ch], r12b
0x18002e0d5  jz      loc_18002DEDF
0x18002e0db  cmp     [rcx+19h], bl
0x18002e0de  jb      loc_18002DEDF
0x18002e0e4  mov     edx, 23h ; '#'
0x18002e0e9  jmp     loc_18002DECC
0x18002e0ee  xor     edx, edx; sesid
0x18002e0f0  mov     [rsp+50h+szParam], 0; szParam
0x18002e0f9  mov     r9, r12; lParam
0x18002e0fc  mov     rcx, rsi; pinstance
0x18002e0ff  lea     r8d, [rdx+11h]; paramid
0x18002e103  call    cs:__imp_JetSetSystemParameterW
0x18002e109  mov     edi, eax
0x18002e10b  test    eax, eax
0x18002e10d  jz      short loc_18002E13C
0x18002e10f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e116  cmp     rcx, r14
0x18002e119  jz      loc_18002DEDF
0x18002e11f  test    [rcx+1Ch], r12b
0x18002e123  jz      loc_18002DEDF
0x18002e129  cmp     [rcx+19h], bl
0x18002e12c  jb      loc_18002DEDF
0x18002e132  mov     edx, 24h ; '$'
0x18002e137  jmp     loc_18002DECC
0x18002e13c  mov     [rbp+var_18], 0
0x18002e143  xor     ebx, ebx
0x18002e145  lea     rcx, [rbp+var_20]; this
0x18002e149  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18002e14e  mov     eax, ebx
0x18002e150  add     rsp, 50h
0x18002e154  pop     r15
0x18002e156  pop     r14
0x18002e158  pop     r12
0x18002e15a  pop     rdi
0x18002e15b  pop     rsi
0x18002e15c  pop     rbx
0x18002e15d  pop     rbp
0x18002e15e  retn
```
