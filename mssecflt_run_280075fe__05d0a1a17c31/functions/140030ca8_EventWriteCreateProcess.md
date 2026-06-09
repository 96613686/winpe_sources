# EventWriteCreateProcess

- ea: `0x140030ca8`
- end: `0x1400312fe`
- name: `EventWriteCreateProcess`
- size: `1622`
- prototype: `__int64 __fastcall(int, int, int, int, PSID Sid, char, char, char, __int64, __int64, wchar_t *Str, __int64, __int64, __int64, char, char, char, char, char, char, char, char, char, char, char, __int64, char, char, char, char, char, wchar_t *, char, __int64, wchar_t *, char, char, char, char, char, char, char, char, wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14003205c`

## callees

- `0x140007520`
- `0x140008714`
- `0x14000876c`
- `0x140009b80`
- `0x14001008c`
- `0x140011650`
- `0x140030ca8`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x1400312b6`
- `ntoskrnl!EtwWrite` at `0x1400312b6`
- `ntoskrnl!RtlLengthSid` at `0x140030d6a`
- `ntoskrnl!RtlLengthSid` at `0x140030d6a`

## pseudocode

```c
__int64 __fastcall EventWriteCreateProcess(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        PSID Sid,
        char a6,
        char a7,
        char a8,
        __int64 a9,
        __int64 a10,
        wchar_t *Str,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        char a15,
        char a16,
        char a17,
        char a18,
        char a19,
        char a20,
        char a21,
        char a22,
        char a23,
        char a24,
        char a25,
        __int64 a26,
        char a27,
        char a28,
        char a29,
        char a30,
        char a31,
        wchar_t *a32,
        char a33,
        __int64 a34,
        wchar_t *a35,
        char a36,
        char a37,
        char a38,
        char a39,
        char a40,
        char a41,
        char a42,
        char a43,
        wchar_t *a44)
{
  PSID v44; // rdi
  __int64 v45; // r12
  __int64 v46; // r13
  const wchar_t *v47; // rsi
  _QWORD *EtwDescriptorBuffer; // rax
  _QWORD *UserData; // rbx
  ULONG v51; // eax
  unsigned __int8 v52; // al
  int v53; // ecx
  int v54; // edi
  wchar_t *v55; // r15
  int v56; // eax
  int v57; // eax
  const WCHAR *v58; // r14
  const WCHAR *v59; // rax
  const WCHAR *v60; // rax
  const WCHAR *v61; // rax
  const wchar_t *v62; // rsi
  int v63; // ecx
  __int64 v64; // rcx
  const WCHAR *v65; // rax
  const wchar_t *v66; // rsi
  int v67; // ecx
  const WCHAR *v68; // rax
  const wchar_t *v69; // rsi
  bool v70; // zf
  int v71; // eax
  unsigned int v72; // edi
  PVOID P; // [rsp+40h] [rbp-38h] BYREF
  int v74; // [rsp+48h] [rbp-30h] BYREF
  int v75; // [rsp+4Ch] [rbp-2Ch] BYREF
  int v76; // [rsp+50h] [rbp-28h] BYREF
  int v77; // [rsp+54h] [rbp-24h] BYREF
  int v78; // [rsp+58h] [rbp-20h] BYREF
  __int64 v79; // [rsp+C0h] [rbp+48h] BYREF
  int v80; // [rsp+C8h] [rbp+50h] BYREF
  __int64 v81; // [rsp+D0h] [rbp+58h] BYREF
  int v82; // [rsp+D8h] [rbp+60h] BYREF

  v82 = a4;
  v81 = a3;
  v80 = a2;
  v79 = a1;
  v44 = Sid;
  v45 = a9;
  v46 = a10;
  v47 = Str;
  EtwDescriptorBuffer = (_QWORD *)SecGetEtwDescriptorBuffer(49);
  UserData = EtwDescriptorBuffer;
  v75 = 0;
  v76 = 0;
  v74 = 0;
  P = 0;
  if ( !EtwDescriptorBuffer )
    return 3221225626LL;
  EtwDescriptorBuffer[1] = 8;
  *EtwDescriptorBuffer = &v79;
  EtwDescriptorBuffer[2] = &v80;
  EtwDescriptorBuffer[4] = &v81;
  EtwDescriptorBuffer[6] = &v82;
  EtwDescriptorBuffer[3] = 4;
  EtwDescriptorBuffer[5] = 8;
  EtwDescriptorBuffer[7] = 4;
  if ( v44 )
    v51 = RtlLengthSid(v44);
  else
    v51 = 0;
  *((_DWORD *)UserData + 18) = v51;
  UserData[8] = v44;
  UserData[10] = &a6;
  *((_DWORD *)UserData + 19) = 0;
  UserData[12] = &a7;
  UserData[11] = 4;
  UserData[14] = &a8;
  UserData[13] = 4;
  UserData[15] = 8;
  v52 = SecTruncateCommandLine(v45, v46, v47, &v75, &v76, &v74, &P);
  v53 = v74;
  v54 = 2;
  v55 = (wchar_t *)P;
  v78 = v52;
  v77 = v74;
  if ( v52 )
  {
    if ( v47 )
    {
      v57 = wcslen_0(v47);
      v53 = v74;
      v56 = 2 * v57 + 2;
    }
    else
    {
      v56 = 2;
    }
    v77 = v56;
    v47 = v55;
  }
  *((_DWORD *)UserData + 42) = v53;
  v58 = &SourceString;
  UserData[23] = 32;
  v59 = &SourceString;
  UserData[25] = 20;
  if ( v45 )
    v59 = (const WCHAR *)v45;
  UserData[27] = 16;
  UserData[16] = v59;
  *((_DWORD *)UserData + 34) = v75;
  v60 = &SourceString;
  if ( v46 )
    v60 = (const WCHAR *)v46;
  *((_DWORD *)UserData + 35) = 0;
  UserData[18] = v60;
  *((_DWORD *)UserData + 38) = v76;
  v61 = &SourceString;
  if ( v47 )
    v61 = v47;
  *((_DWORD *)UserData + 39) = 0;
  UserData[20] = v61;
  UserData[22] = a12;
  UserData[24] = a13;
  UserData[26] = a14;
  UserData[28] = &a15;
  UserData[30] = &a16;
  UserData[32] = &a17;
  UserData[34] = &a18;
  UserData[36] = &a19;
  UserData[38] = &a20;
  UserData[40] = &a21;
  UserData[42] = &a22;
  UserData[44] = &a23;
  UserData[46] = &a24;
  UserData[48] = &a25;
  UserData[50] = &v78;
  UserData[52] = &v77;
  UserData[54] = a26;
  UserData[56] = &a27;
  UserData[58] = &a28;
  UserData[60] = &a29;
  *((_DWORD *)UserData + 43) = 0;
  UserData[29] = 4;
  UserData[31] = 4;
  UserData[33] = 4;
  UserData[35] = 4;
  UserData[37] = 4;
  UserData[39] = 4;
  UserData[41] = 4;
  UserData[43] = 4;
  UserData[45] = 8;
  UserData[47] = 8;
  UserData[49] = 8;
  UserData[51] = 4;
  UserData[53] = 4;
  UserData[55] = 64;
  UserData[57] = 8;
  UserData[59] = 1;
  v62 = a32;
  UserData[62] = &a30;
  UserData[64] = &a31;
  UserData[61] = 4;
  UserData[63] = 4;
  UserData[65] = 8;
  if ( v62 )
    v63 = 2 * wcslen_0(v62) + 2;
  else
    v63 = 2;
  *((_DWORD *)UserData + 134) = v63;
  v64 = a34;
  v65 = &SourceString;
  if ( v62 )
    v65 = v62;
  *((_DWORD *)UserData + 135) = 0;
  v66 = a35;
  UserData[66] = v65;
  UserData[68] = &a33;
  UserData[70] = v64 + 4;
  UserData[72] = v64 + 8;
  UserData[74] = v64 + 12;
  UserData[76] = v64 + 16;
  UserData[69] = 8;
  UserData[71] = 4;
  UserData[73] = 4;
  UserData[75] = 4;
  UserData[77] = 1;
  if ( v66 )
    v67 = 2 * wcslen_0(v66) + 2;
  else
    v67 = 2;
  *((_DWORD *)UserData + 158) = v67;
  v68 = &SourceString;
  *((_DWORD *)UserData + 159) = 0;
  if ( v66 )
    v68 = v66;
  UserData[81] = 8;
  v69 = a44;
  UserData[78] = v68;
  UserData[80] = &a36;
  UserData[82] = &a37;
  UserData[84] = &a38;
  UserData[86] = &a39;
  UserData[88] = &a40;
  UserData[90] = &a41;
  UserData[92] = &a42;
  UserData[94] = &a43;
  UserData[83] = 4;
  UserData[85] = 8;
  UserData[87] = 4;
  UserData[89] = 4;
  UserData[91] = 4;
  UserData[93] = 4;
  UserData[95] = 4;
  v70 = v69 == 0;
  if ( v69 )
  {
    v71 = wcslen_0(v69);
    v70 = v69 == 0;
    v54 = 2 * v71 + 2;
  }
  if ( !v70 )
    v58 = v69;
  *((_DWORD *)UserData + 194) = v54;
  UserData[96] = v58;
  *((_DWORD *)UserData + 195) = 0;
  v72 = EtwWrite(Microsoft_Windows_SECHandle, &Event1, 0, 0x31u, (PEVENT_DATA_DESCRIPTOR)UserData);
  if ( v55 )
    SecFreePool(v55, 0x74736353u);
  SecReleaseEtwDescriptorBuffer((PSLIST_ENTRY)UserData);
  return v72;
}

```

## disassembly

```asm
0x140030ca8  mov     rax, rsp
0x140030cab  mov     [rax+20h], r9d
0x140030caf  mov     [rax+18h], r8
0x140030cb3  mov     [rax+10h], edx
0x140030cb6  mov     [rax+8], rcx
0x140030cba  push    rbp
0x140030cbb  push    rbx
0x140030cbc  push    rsi
0x140030cbd  push    rdi
0x140030cbe  push    r12
0x140030cc0  push    r13
0x140030cc2  push    r14
0x140030cc4  push    r15
0x140030cc6  mov     rbp, rsp
0x140030cc9  sub     rsp, 78h
0x140030ccd  mov     rax, cs:__security_cookie
0x140030cd4  xor     rax, rsp
0x140030cd7  mov     [rbp+var_18], rax
0x140030cdb  mov     rdi, [rbp+Sid]
0x140030cdf  mov     ecx, 31h ; '1'
0x140030ce4  mov     r12, [rbp+arg_40]
0x140030ceb  mov     r13, [rbp+arg_48]
0x140030cf2  mov     rsi, [rbp+Str]
0x140030cf9  call    SecGetEtwDescriptorBuffer
0x140030cfe  xor     r14d, r14d
0x140030d01  mov     rbx, rax
0x140030d04  mov     [rbp+var_2C], r14d
0x140030d08  mov     [rbp+var_28], r14d
0x140030d0c  mov     [rbp+var_30], r14d
0x140030d10  mov     [rbp+P], r14
0x140030d14  test    rax, rax
0x140030d17  jnz     short loc_140030D23
0x140030d19  mov     eax, 0C000009Ah
0x140030d1e  jmp     loc_1400312E0
0x140030d23  mov     qword ptr [rbx+8], 8
0x140030d2b  lea     rax, [rbp+arg_0]
0x140030d2f  mov     [rbx], rax
0x140030d32  lea     rax, [rbp+arg_8]
0x140030d36  mov     [rbx+10h], rax
0x140030d3a  lea     rax, [rbp+arg_10]
0x140030d3e  mov     [rbx+20h], rax
0x140030d42  lea     rax, [rbp+arg_18]
0x140030d46  mov     [rbx+30h], rax
0x140030d4a  mov     qword ptr [rbx+18h], 4
0x140030d52  mov     qword ptr [rbx+28h], 8
0x140030d5a  mov     qword ptr [rbx+38h], 4
0x140030d62  test    rdi, rdi
0x140030d65  jz      short loc_140030D78
0x140030d67  mov     rcx, rdi; Sid
0x140030d6a  call    cs:__imp_RtlLengthSid
0x140030d71  nop     dword ptr [rax+rax+00h]
0x140030d76  jmp     short loc_140030D7B
0x140030d78  mov     eax, r14d
0x140030d7b  mov     [rbx+48h], eax
0x140030d7e  lea     r9, [rbp+var_2C]
0x140030d82  lea     rax, [rbp+arg_28]
0x140030d86  mov     [rbx+40h], rdi
0x140030d8a  mov     [rbx+50h], rax
0x140030d8e  mov     r8, rsi
0x140030d91  lea     rax, [rbp+arg_30]
0x140030d95  mov     [rbx+4Ch], r14d
0x140030d99  mov     [rbx+60h], rax
0x140030d9d  mov     rdx, r13
0x140030da0  lea     rax, [rbp+arg_38]
0x140030da7  mov     qword ptr [rbx+58h], 4
0x140030daf  mov     [rbx+70h], rax
0x140030db3  mov     rcx, r12
0x140030db6  lea     rax, [rbp+P]
0x140030dba  mov     qword ptr [rbx+68h], 4
0x140030dc2  mov     [rsp+78h+var_48], rax
0x140030dc7  lea     rax, [rbp+var_30]
0x140030dcb  mov     [rsp+78h+var_50], rax
0x140030dd0  lea     rax, [rbp+var_28]
0x140030dd4  mov     [rsp+78h+UserData], rax
0x140030dd9  mov     qword ptr [rbx+78h], 8
0x140030de1  call    SecTruncateCommandLine
0x140030de6  mov     ecx, [rbp+var_30]
0x140030de9  mov     edi, 2
0x140030dee  mov     r15, [rbp+P]
0x140030df2  movzx   eax, al
0x140030df5  mov     [rbp+var_20], eax
0x140030df8  mov     [rbp+var_24], ecx
0x140030dfb  test    eax, eax
0x140030dfd  jz      short loc_140030E20
0x140030dff  test    rsi, rsi
0x140030e02  jnz     short loc_140030E08
0x140030e04  mov     eax, edi
0x140030e06  jmp     short loc_140030E1A
0x140030e08  mov     rcx, rsi; Str
0x140030e0b  call    wcslen_0
0x140030e10  mov     ecx, [rbp+var_30]
0x140030e13  lea     eax, ds:2[rax*2]
0x140030e1a  mov     [rbp+var_24], eax
0x140030e1d  mov     rsi, r15
0x140030e20  test    r12, r12
0x140030e23  mov     [rbx+0A8h], ecx
0x140030e29  lea     r14, SourceString
0x140030e30  mov     qword ptr [rbx+0B8h], 20h ; ' '
0x140030e3b  mov     rax, r14
0x140030e3e  mov     qword ptr [rbx+0C8h], 14h
0x140030e49  cmovnz  rax, r12
0x140030e4d  mov     qword ptr [rbx+0D8h], 10h
0x140030e58  mov     [rbx+80h], rax
0x140030e5f  xor     r12d, r12d
0x140030e62  mov     eax, [rbp+var_2C]
0x140030e65  test    r13, r13
0x140030e68  mov     [rbx+88h], eax
0x140030e6e  mov     rax, r14
0x140030e71  cmovnz  rax, r13
0x140030e75  mov     [rbx+8Ch], r12d
0x140030e7c  mov     [rbx+90h], rax
0x140030e83  test    rsi, rsi
0x140030e86  mov     eax, [rbp+var_28]
0x140030e89  mov     [rbx+98h], eax
0x140030e8f  mov     rax, r14
0x140030e92  cmovnz  rax, rsi
0x140030e96  mov     [rbx+9Ch], r12d
0x140030e9d  mov     [rbx+0A0h], rax
0x140030ea4  mov     rax, [rbp+arg_58]
0x140030eab  mov     [rbx+0B0h], rax
0x140030eb2  mov     rax, [rbp+arg_60]
0x140030eb9  mov     [rbx+0C0h], rax
0x140030ec0  mov     rax, [rbp+arg_68]
0x140030ec7  mov     [rbx+0D0h], rax
0x140030ece  lea     rax, [rbp+arg_70]
0x140030ed5  mov     [rbx+0E0h], rax
0x140030edc  lea     rax, [rbp+arg_78]
0x140030ee3  mov     [rbx+0F0h], rax
0x140030eea  lea     rax, [rbp+arg_80]
0x140030ef1  mov     [rbx+100h], rax
0x140030ef8  lea     rax, [rbp+arg_88]
0x140030eff  mov     [rbx+110h], rax
0x140030f06  lea     rax, [rbp+arg_90]
0x140030f0d  mov     [rbx+120h], rax
0x140030f14  lea     rax, [rbp+arg_98]
0x140030f1b  mov     [rbx+130h], rax
0x140030f22  lea     rax, [rbp+arg_A0]
0x140030f29  mov     [rbx+140h], rax
0x140030f30  lea     rax, [rbp+arg_A8]
0x140030f37  mov     [rbx+150h], rax
0x140030f3e  lea     rax, [rbp+arg_B0]
0x140030f45  mov     [rbx+160h], rax
0x140030f4c  lea     rax, [rbp+arg_B8]
0x140030f53  mov     [rbx+170h], rax
0x140030f5a  lea     rax, [rbp+arg_C0]
0x140030f61  mov     [rbx+180h], rax
0x140030f68  lea     rax, [rbp+var_20]
0x140030f6c  mov     [rbx+190h], rax
0x140030f73  lea     rax, [rbp+var_24]
0x140030f77  mov     [rbx+1A0h], rax
0x140030f7e  mov     rax, [rbp+arg_C8]
0x140030f85  mov     [rbx+1B0h], rax
0x140030f8c  lea     rax, [rbp+arg_D0]
0x140030f93  mov     [rbx+1C0h], rax
0x140030f9a  lea     rax, [rbp+arg_D8]
0x140030fa1  mov     [rbx+1D0h], rax
0x140030fa8  lea     rax, [rbp+arg_E0]
0x140030faf  mov     [rbx+1E0h], rax
0x140030fb6  mov     [rbx+0ACh], r12d
0x140030fbd  mov     qword ptr [rbx+0E8h], 4
0x140030fc8  mov     qword ptr [rbx+0F8h], 4
0x140030fd3  mov     qword ptr [rbx+108h], 4
0x140030fde  mov     qword ptr [rbx+118h], 4
0x140030fe9  mov     qword ptr [rbx+128h], 4
0x140030ff4  mov     qword ptr [rbx+138h], 4
0x140030fff  mov     qword ptr [rbx+148h], 4
0x14003100a  mov     qword ptr [rbx+158h], 4
0x140031015  mov     qword ptr [rbx+168h], 8
0x140031020  mov     qword ptr [rbx+178h], 8
0x14003102b  mov     qword ptr [rbx+188h], 8
0x140031036  mov     qword ptr [rbx+198h], 4
0x140031041  mov     qword ptr [rbx+1A8h], 4
0x14003104c  mov     qword ptr [rbx+1B8h], 40h ; '@'
0x140031057  mov     qword ptr [rbx+1C8h], 8
0x140031062  mov     qword ptr [rbx+1D8h], 1
0x14003106d  mov     rsi, [rbp+arg_F8]
0x140031074  lea     rax, [rbp+arg_E8]
0x14003107b  mov     [rbx+1F0h], rax
0x140031082  lea     rax, [rbp+arg_F0]
0x140031089  mov     [rbx+200h], rax
0x140031090  mov     qword ptr [rbx+1E8h], 4
0x14003109b  mov     qword ptr [rbx+1F8h], 4
0x1400310a6  mov     qword ptr [rbx+208h], 8
0x1400310b1  test    rsi, rsi
0x1400310b4  jz      short loc_1400310C7
0x1400310b6  mov     rcx, rsi; Str
0x1400310b9  call    wcslen_0
0x1400310be  lea     ecx, ds:2[rax*2]
0x1400310c5  jmp     short loc_1400310C9
0x1400310c7  mov     ecx, edi
0x1400310c9  test    rsi, rsi
0x1400310cc  mov     [rbx+218h], ecx
0x1400310d2  mov     rcx, [rbp+arg_108]
0x1400310d9  mov     rax, r14
0x1400310dc  cmovnz  rax, rsi
0x1400310e0  mov     [rbx+21Ch], r12d
0x1400310e7  mov     rsi, [rbp+arg_110]
0x1400310ee  mov     [rbx+210h], rax
0x1400310f5  lea     rax, [rbp+arg_100]
0x1400310fc  mov     [rbx+220h], rax
0x140031103  lea     rax, [rcx+4]
0x140031107  mov     [rbx+230h], rax
0x14003110e  lea     rax, [rcx+8]
0x140031112  mov     [rbx+240h], rax
0x140031119  lea     rax, [rcx+0Ch]
0x14003111d  mov     [rbx+250h], rax
0x140031124  lea     rax, [rcx+10h]
0x140031128  mov     [rbx+260h], rax
0x14003112f  mov     qword ptr [rbx+228h], 8
0x14003113a  mov     qword ptr [rbx+238h], 4
0x140031145  mov     qword ptr [rbx+248h], 4
0x140031150  mov     qword ptr [rbx+258h], 4
0x14003115b  mov     qword ptr [rbx+268h], 1
0x140031166  test    rsi, rsi
0x140031169  jz      short loc_14003117C
0x14003116b  mov     rcx, rsi; Str
0x14003116e  call    wcslen_0
0x140031173  lea     ecx, ds:2[rax*2]
0x14003117a  jmp     short loc_14003117E
0x14003117c  mov     ecx, edi
0x14003117e  test    rsi, rsi
0x140031181  mov     [rbx+278h], ecx
0x140031187  mov     rax, r14
0x14003118a  mov     [rbx+27Ch], r12d
0x140031191  cmovnz  rax, rsi
0x140031195  mov     qword ptr [rbx+288h], 8
0x1400311a0  mov     rsi, [rbp+arg_158]
0x1400311a7  mov     [rbx+270h], rax
0x1400311ae  lea     rax, [rbp+arg_118]
0x1400311b5  mov     [rbx+280h], rax
0x1400311bc  lea     rax, [rbp+arg_120]
0x1400311c3  mov     [rbx+290h], rax
0x1400311ca  lea     rax, [rbp+arg_128]
0x1400311d1  mov     [rbx+2A0h], rax
0x1400311d8  lea     rax, [rbp+arg_130]
0x1400311df  mov     [rbx+2B0h], rax
0x1400311e6  lea     rax, [rbp+arg_138]
0x1400311ed  mov     [rbx+2C0h], rax
0x1400311f4  lea     rax, [rbp+arg_140]
0x1400311fb  mov     [rbx+2D0h], rax
0x140031202  lea     rax, [rbp+arg_148]
0x140031209  mov     [rbx+2E0h], rax
0x140031210  lea     rax, [rbp+arg_150]
0x140031217  mov     [rbx+2F0h], rax
0x14003121e  mov     qword ptr [rbx+298h], 4
0x140031229  mov     qword ptr [rbx+2A8h], 8
0x140031234  mov     qword ptr [rbx+2B8h], 4
0x14003123f  mov     qword ptr [rbx+2C8h], 4
0x14003124a  mov     qword ptr [rbx+2D8h], 4
0x140031255  mov     qword ptr [rbx+2E8h], 4
0x140031260  mov     qword ptr [rbx+2F8h], 4
0x14003126b  test    rsi, rsi
0x14003126e  jz      short loc_140031282
0x140031270  mov     rcx, rsi; Str
0x140031273  call    wcslen_0
0x140031278  test    rsi, rsi
0x14003127b  lea     edi, ds:2[rax*2]
0x140031282  cmovnz  r14, rsi
0x140031286  mov     [rbx+308h], edi
0x14003128c  mov     [rbx+300h], r14
0x140031293  lea     rdx, Event1; EventDescriptor
0x14003129a  mov     [rbx+30Ch], r12d
0x1400312a1  mov     r9d, 31h ; '1'; UserDataCount
0x1400312a7  mov     rcx, cs:Microsoft_Windows_SECHandle; RegHandle
0x1400312ae  xor     r8d, r8d; ActivityId
0x1400312b1  mov     [rsp+78h+UserData], rbx; UserData
0x1400312b6  call    cs:__imp_EtwWrite
0x1400312bd  nop     dword ptr [rax+rax+00h]
0x1400312c2  mov     edi, eax
0x1400312c4  test    r15, r15
0x1400312c7  jz      short loc_1400312D6
0x1400312c9  mov     edx, 74736353h; Tag
0x1400312ce  mov     rcx, r15; P
0x1400312d1  call    SecFreePool
0x1400312d6  mov     rcx, rbx; ListEntry
0x1400312d9  call    SecReleaseEtwDescriptorBuffer
0x1400312de  mov     eax, edi
0x1400312e0  mov     rcx, [rbp+var_18]
0x1400312e4  xor     rcx, rsp; StackCookie
0x1400312e7  call    __security_check_cookie
0x1400312ec  add     rsp, 78h
0x1400312f0  pop     r15
0x1400312f2  pop     r14
0x1400312f4  pop     r13
0x1400312f6  pop     r12
0x1400312f8  pop     rdi
0x1400312f9  pop     rsi
0x1400312fa  pop     rbx
0x1400312fb  pop     rbp
0x1400312fc  retn
```
