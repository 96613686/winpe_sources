# PoWdiLogResumeEvent

- ea: `0x180002e50`
- end: `0x1800032b9`
- name: `PoWdiLogResumeEvent`
- size: `1129`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800032c0`

## callees

- `0x18000113c`
- `0x180002e50`
- `0x180004902`
- `0x180004930`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000309b`
- `ntdll!EtwEventWrite` at `0x18000309b`
- `ntdll!NtPowerInformation` at `0x1800030d2`
- `ntdll!NtPowerInformation` at `0x1800030d2`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x1800030de`
- `api-ms-win-power-base-l1-1-0!GetPwrCapabilities` at `0x1800030de`

## pseudocode

```c
char __fastcall PoWdiLogResumeEvent(__int64 a1)
{
  __int16 v2; // ax
  __int16 v3; // dx
  __int16 v4; // cx
  unsigned int v5; // r8d
  __int64 v6; // rdx
  __int64 v7; // rcx
  NTSTATUS v8; // edi
  __int64 v9; // r9
  __int16 v11; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v12; // [rsp+34h] [rbp-CCh] BYREF
  __int16 v13; // [rsp+38h] [rbp-C8h] BYREF
  int v14; // [rsp+3Ch] [rbp-C4h] BYREF
  BOOL v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+44h] [rbp-BCh] BYREF
  int v17; // [rsp+48h] [rbp-B8h] BYREF
  int v18; // [rsp+4Ch] [rbp-B4h] BYREF
  int v19; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD OutputBuffer[2]; // [rsp+58h] [rbp-A8h] BYREF
  _SYSTEM_POWER_CAPABILITIES spc; // [rsp+80h] [rbp-80h] BYREF
  __int64 v22; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v23[28]; // [rsp+D8h] [rbp-28h]
  int v24; // [rsp+1B8h] [rbp+B8h]
  int v25; // [rsp+1BCh] [rbp+BCh]
  __int16 *v26; // [rsp+1C0h] [rbp+C0h]
  __int64 v27; // [rsp+1C8h] [rbp+C8h]
  __int16 *v28; // [rsp+1D0h] [rbp+D0h]
  __int64 v29; // [rsp+1D8h] [rbp+D8h]
  __int64 v30; // [rsp+1E0h] [rbp+E0h]
  __int64 v31; // [rsp+1E8h] [rbp+E8h]
  __int64 v32; // [rsp+1F0h] [rbp+F0h]
  int v33; // [rsp+1F8h] [rbp+F8h]
  int v34; // [rsp+1FCh] [rbp+FCh]
  __int64 v35; // [rsp+200h] [rbp+100h]
  int v36; // [rsp+208h] [rbp+108h]
  int v37; // [rsp+20Ch] [rbp+10Ch]
  _BYTE v38[32]; // [rsp+220h] [rbp+120h] BYREF
  _DWORD *v39; // [rsp+240h] [rbp+140h]
  __int64 v40; // [rsp+248h] [rbp+148h]
  __int64 v41; // [rsp+250h] [rbp+150h]
  _DWORD v42[2]; // [rsp+258h] [rbp+158h] BYREF
  _DWORD *v43; // [rsp+260h] [rbp+160h]
  __int64 v44; // [rsp+268h] [rbp+168h]
  __int64 v45; // [rsp+270h] [rbp+170h]
  _DWORD v46[2]; // [rsp+278h] [rbp+178h] BYREF
  _DWORD *v47; // [rsp+280h] [rbp+180h]
  __int64 v48; // [rsp+288h] [rbp+188h]
  __int64 v49; // [rsp+290h] [rbp+190h]
  _DWORD v50[2]; // [rsp+298h] [rbp+198h] BYREF
  int *v51; // [rsp+2A0h] [rbp+1A0h]
  __int64 v52; // [rsp+2A8h] [rbp+1A8h]
  BOOL *v53; // [rsp+2B0h] [rbp+1B0h]
  __int64 v54; // [rsp+2B8h] [rbp+1B8h]
  int *v55; // [rsp+2C0h] [rbp+1C0h]
  __int64 v56; // [rsp+2C8h] [rbp+1C8h]
  int *v57; // [rsp+2D0h] [rbp+1D0h]
  __int64 v58; // [rsp+2D8h] [rbp+1D8h]
  int *v59; // [rsp+2E0h] [rbp+1E0h]
  __int64 v60; // [rsp+2E8h] [rbp+1E8h]
  int *v61; // [rsp+2F0h] [rbp+1F0h]
  __int64 v62; // [rsp+2F8h] [rbp+1F8h]

  memset(OutputBuffer, 0, sizeof(OutputBuffer));
  memset_0(&spc, 0, sizeof(spc));
  v2 = *(_WORD *)(a1 + 72) >> 1;
  v3 = *(_WORD *)(a1 + 88) >> 1;
  v4 = *(_WORD *)(a1 + 104) >> 1;
  v13 = v2;
  v11 = v3;
  v12 = v4;
  if ( PoWdiProvHandle )
  {
    v23[0] = 8;
    v22 = a1 + 120;
    v23[1] = a1 + 128;
    v23[3] = a1 + 20;
    v23[5] = a1 + 24;
    v23[7] = a1 + 28;
    v23[9] = a1 + 48;
    v23[11] = a1 + 32;
    v23[13] = a1 + 36;
    v23[15] = a1 + 40;
    v23[17] = a1 + 4;
    v23[19] = a1 + 12;
    v23[21] = a1 + 16;
    v23[23] = a1 + 68;
    v23[25] = &v13;
    v5 = 18;
    v23[27] = *(_QWORD *)(a1 + 80);
    v24 = *(unsigned __int16 *)(a1 + 72);
    v26 = &v11;
    v28 = &v12;
    v30 = a1 + 192;
    v23[2] = 8;
    v23[4] = 4;
    v23[6] = 4;
    v23[8] = 4;
    v23[10] = 4;
    v23[12] = 4;
    v23[14] = 4;
    v23[16] = 4;
    v23[18] = 4;
    v23[20] = 4;
    v23[22] = 4;
    v23[24] = 4;
    v23[26] = 2;
    v25 = 0;
    v27 = 2;
    v29 = 2;
    v31 = 4;
    if ( v3 )
    {
      v5 = 19;
      v32 = *(_QWORD *)(a1 + 96);
      v33 = *(unsigned __int16 *)(a1 + 88);
      v34 = 0;
      if ( v4 )
      {
        v5 = 20;
        v35 = *(_QWORD *)(a1 + 112);
        v36 = *(unsigned __int16 *)(a1 + 104);
        v37 = 0;
      }
    }
    v6 = 2LL * v5;
    v7 = PoWdiProvHandle;
    v23[v6 - 1] = a1 + 52;
    v23[v6] = 4;
    LOBYTE(v2) = EtwEventWrite(v7, &POP_TS_ETW_EVENT_SYSTEMRESUME, v5 + 1, &v22);
    v3 = v11;
    v4 = v12;
  }
  if ( v3 )
  {
    if ( v4 )
    {
      v8 = NtPowerInformation(ProcessorPowerPolicyDc|0x40, 0, 0, OutputBuffer, 0x20u);
      LOBYTE(v2) = GetPwrCapabilities(&spc);
      if ( (unsigned int)dword_1800091A8 > 5 && (qword_1800091B8 & 0x400000000000LL) != 0 )
      {
        LOBYTE(v2) = 0;
        if ( (qword_1800091C0 & 0x400000000000LL) == qword_1800091C0 )
        {
          v40 = 2;
          v39 = v42;
          v41 = *(_QWORD *)(a1 + 80);
          v42[0] = *(unsigned __int16 *)(a1 + 72);
          v43 = v46;
          v45 = *(_QWORD *)(a1 + 96);
          v46[0] = *(unsigned __int16 *)(a1 + 88);
          v47 = v50;
          v49 = *(_QWORD *)(a1 + 112);
          v50[0] = *(unsigned __int16 *)(a1 + 104);
          v14 = *(_DWORD *)(a1 + 12);
          v51 = &v14;
          v53 = &v15;
          v16 = LOBYTE(OutputBuffer[0]);
          v55 = &v16;
          v17 = HIDWORD(OutputBuffer[0]);
          v57 = &v17;
          v18 = DWORD2(OutputBuffer[0]);
          v59 = &v18;
          v19 = spc.spare2[1];
          v61 = &v19;
          v42[1] = 0;
          v44 = 2;
          v46[1] = 0;
          v48 = 2;
          v50[1] = 0;
          v52 = 4;
          v15 = v8 >= 0;
          v54 = 4;
          v56 = 4;
          v58 = 4;
          v60 = 4;
          v62 = 4;
          LOBYTE(v2) = tlgWriteTransfer_EtwEventWriteTransfer(
                         qword_1800091B8,
                         byte_180006D86,
                         0x400000000000LL,
                         v9,
                         14,
                         (__int64)v38);
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180002e50  push    rbp
0x180002e52  push    rbx
0x180002e53  push    rsi
0x180002e54  push    rdi
0x180002e55  push    r14
0x180002e57  push    r15
0x180002e59  lea     rbp, [rsp-218h]
0x180002e61  sub     rsp, 318h
0x180002e68  mov     rax, cs:__security_cookie
0x180002e6f  xor     rax, rsp
0x180002e72  mov     [rbp+240h+var_40], rax
0x180002e79  xorps   xmm0, xmm0
0x180002e7c  xor     edx, edx; Val
0x180002e7e  mov     rbx, rcx
0x180002e81  lea     rcx, [rbp+240h+spc]; void *
0x180002e85  movups  [rsp+340h+OutputBuffer], xmm0
0x180002e8a  lea     r8d, [rdx+4Ch]; Size
0x180002e8e  movups  [rsp+340h+var_2D8], xmm0
0x180002e93  call    memset_0
0x180002e98  movzx   eax, word ptr [rbx+48h]
0x180002e9c  xor     esi, esi
0x180002e9e  movzx   edx, word ptr [rbx+58h]
0x180002ea2  movzx   ecx, word ptr [rbx+68h]
0x180002ea6  mov     r10, cs:PoWdiProvHandle
0x180002ead  shr     ax, 1
0x180002eb0  shr     dx, 1
0x180002eb3  shr     cx, 1
0x180002eb6  mov     [rsp+340h+var_308], ax
0x180002ebb  mov     [rsp+340h+var_310], dx
0x180002ec0  mov     [rsp+340h+var_30C], cx
0x180002ec5  test    r10, r10
0x180002ec8  jz      loc_1800030AB
0x180002ece  mov     [rbp+240h+var_268], 8
0x180002ed6  lea     rax, [rbx+78h]
0x180002eda  mov     [rbp+240h+var_270], rax
0x180002ede  lea     rax, [rbx+80h]
0x180002ee5  mov     [rbp+240h+var_260], rax
0x180002ee9  lea     rax, [rbx+14h]
0x180002eed  mov     [rbp+240h+var_250], rax
0x180002ef1  lea     rax, [rbx+18h]
0x180002ef5  mov     [rbp+240h+var_240], rax
0x180002ef9  lea     rax, [rbx+1Ch]
0x180002efd  mov     [rbp+240h+var_230], rax
0x180002f01  lea     rax, [rbx+30h]
0x180002f05  mov     [rbp+240h+var_220], rax
0x180002f09  lea     rax, [rbx+20h]
0x180002f0d  mov     [rbp+240h+var_210], rax
0x180002f11  lea     rax, [rbx+24h]
0x180002f15  mov     [rbp+240h+var_200], rax
0x180002f19  lea     rax, [rbx+28h]
0x180002f1d  mov     [rbp+240h+var_1F0], rax
0x180002f21  lea     rax, [rbx+4]
0x180002f25  mov     [rbp+240h+var_1E0], rax
0x180002f29  lea     rax, [rbx+0Ch]
0x180002f2d  mov     [rbp+240h+var_1D0], rax
0x180002f31  lea     rax, [rbx+10h]
0x180002f35  mov     [rbp+240h+var_1C0], rax
0x180002f3c  lea     rax, [rbx+44h]
0x180002f40  mov     [rbp+240h+var_1B0], rax
0x180002f47  lea     rax, [rsp+340h+var_308]
0x180002f4c  mov     [rbp+240h+var_1A0], rax
0x180002f53  lea     r8d, [rsi+12h]
0x180002f57  mov     rax, [rbx+50h]
0x180002f5b  mov     [rbp+240h+var_190], rax
0x180002f62  movzx   eax, word ptr [rbx+48h]
0x180002f66  mov     [rbp+240h+var_188], eax
0x180002f6c  lea     rax, [rsp+340h+var_310]
0x180002f71  mov     [rbp+240h+var_180], rax
0x180002f78  lea     rax, [rsp+340h+var_30C]
0x180002f7d  mov     [rbp+240h+var_170], rax
0x180002f84  lea     rax, [rbx+0C0h]
0x180002f8b  mov     [rbp+240h+var_160], rax
0x180002f92  mov     [rbp+240h+var_258], 8
0x180002f9a  mov     [rbp+240h+var_248], 4
0x180002fa2  mov     [rbp+240h+var_238], 4
0x180002faa  mov     [rbp+240h+var_228], 4
0x180002fb2  mov     [rbp+240h+var_218], 4
0x180002fba  mov     [rbp+240h+var_208], 4
0x180002fc2  mov     [rbp+240h+var_1F8], 4
0x180002fca  mov     [rbp+240h+var_1E8], 4
0x180002fd2  mov     [rbp+240h+var_1D8], 4
0x180002fda  mov     [rbp+240h+var_1C8], 4
0x180002fe2  mov     [rbp+240h+var_1B8], 4
0x180002fed  mov     [rbp+240h+var_1A8], 4
0x180002ff8  mov     [rbp+240h+var_198], 2
0x180003003  mov     [rbp+240h+var_184], esi
0x180003009  mov     [rbp+240h+var_178], 2
0x180003014  mov     [rbp+240h+var_168], 2
0x18000301f  mov     [rbp+240h+var_158], 4
0x18000302a  test    dx, dx
0x18000302d  jz      short loc_180003072
0x18000302f  mov     rax, [rbx+60h]
0x180003033  lea     r8d, [rsi+13h]
0x180003037  mov     [rbp+240h+var_150], rax
0x18000303e  movzx   eax, word ptr [rbx+58h]
0x180003042  mov     [rbp+240h+var_148], eax
0x180003048  mov     [rbp+240h+var_144], esi
0x18000304e  test    cx, cx
0x180003051  jz      short loc_180003072
0x180003053  mov     rax, [rbx+70h]
0x180003057  lea     r8d, [rsi+14h]
0x18000305b  mov     [rbp+240h+var_140], rax
0x180003062  movzx   eax, word ptr [rbx+68h]
0x180003066  mov     [rbp+240h+var_138], eax
0x18000306c  mov     [rbp+240h+var_134], esi
0x180003072  mov     edx, r8d
0x180003075  lea     rax, [rbx+34h]
0x180003079  add     rdx, rdx
0x18000307c  lea     r9, [rbp+240h+var_270]
0x180003080  inc     r8d
0x180003083  mov     rcx, r10
0x180003086  mov     [rbp+rdx*8+240h+var_270], rax
0x18000308b  mov     [rbp+rdx*8+240h+var_268], 4
0x180003094  lea     rdx, POP_TS_ETW_EVENT_SYSTEMRESUME
0x18000309b  call    cs:__imp_EtwEventWrite
0x1800030a1  movzx   edx, [rsp+340h+var_310]
0x1800030a6  movzx   ecx, [rsp+340h+var_30C]
0x1800030ab  test    dx, dx
0x1800030ae  jz      loc_18000329A
0x1800030b4  test    cx, cx
0x1800030b7  jz      loc_18000329A
0x1800030bd  xor     edx, edx; InputBuffer
0x1800030bf  mov     [rsp+340h+OutputBufferLength], 20h ; ' '; OutputBufferLength
0x1800030c7  lea     r9, [rsp+340h+OutputBuffer]; OutputBuffer
0x1800030cc  xor     r8d, r8d; InputBufferLength
0x1800030cf  lea     ecx, [rdx+53h]; PowerInformationLevel
0x1800030d2  call    cs:__imp_NtPowerInformation
0x1800030d8  lea     rcx, [rbp+240h+spc]; lpspc
0x1800030dc  mov     edi, eax
0x1800030de  call    cs:__imp_GetPwrCapabilities
0x1800030e4  mov     ecx, cs:dword_1800091A8
0x1800030ea  cmp     ecx, 5
0x1800030ed  jbe     loc_18000329A
0x1800030f3  mov     rdx, cs:qword_1800091C0
0x1800030fa  mov     r8, 400000000000h
0x180003104  mov     rcx, cs:qword_1800091B8
0x18000310b  test    r8, rcx
0x18000310e  jz      loc_18000329A
0x180003114  mov     rax, rdx
0x180003117  and     rax, r8
0x18000311a  cmp     rax, rdx
0x18000311d  jnz     loc_18000329A
0x180003123  lea     rax, [rbp+240h+var_E8]
0x18000312a  mov     [rbp+240h+var_F8], 2
0x180003135  mov     [rbp+240h+var_100], rax
0x18000313c  lea     rdx, byte_180006D86
0x180003143  mov     rax, [rbx+50h]
0x180003147  not     edi
0x180003149  mov     [rbp+240h+var_F0], rax
0x180003150  movzx   eax, word ptr [rbx+48h]
0x180003154  mov     [rbp+240h+var_E8], eax
0x18000315a  lea     rax, [rbp+240h+var_C8]
0x180003161  mov     [rbp+240h+var_E0], rax
0x180003168  mov     rax, [rbx+60h]
0x18000316c  mov     [rbp+240h+var_D0], rax
0x180003173  movzx   eax, word ptr [rbx+58h]
0x180003177  mov     [rbp+240h+var_C8], eax
0x18000317d  lea     rax, [rbp+240h+var_A8]
0x180003184  mov     [rbp+240h+var_C0], rax
0x18000318b  mov     rax, [rbx+70h]
0x18000318f  mov     [rbp+240h+var_B0], rax
0x180003196  movzx   eax, word ptr [rbx+68h]
0x18000319a  mov     [rbp+240h+var_A8], eax
0x1800031a0  mov     eax, [rbx+0Ch]
0x1800031a3  mov     [rsp+340h+var_304], eax
0x1800031a7  lea     rax, [rsp+340h+var_304]
0x1800031ac  mov     [rbp+240h+var_A0], rax
0x1800031b3  lea     rax, [rsp+340h+var_300]
0x1800031b8  mov     [rbp+240h+var_90], rax
0x1800031bf  movzx   eax, byte ptr [rsp+340h+OutputBuffer]
0x1800031c4  mov     [rsp+340h+var_2FC], eax
0x1800031c8  lea     rax, [rsp+340h+var_2FC]
0x1800031cd  mov     [rbp+240h+var_80], rax
0x1800031d4  mov     eax, dword ptr [rsp+340h+OutputBuffer+0Ch]
0x1800031d8  mov     [rsp+340h+var_2F8], eax
0x1800031dc  lea     rax, [rsp+340h+var_2F8]
0x1800031e1  mov     [rbp+240h+var_70], rax
0x1800031e8  mov     eax, dword ptr [rsp+340h+OutputBuffer+8]
0x1800031ec  mov     [rsp+340h+var_2F4], eax
0x1800031f0  lea     rax, [rsp+340h+var_2F4]
0x1800031f5  mov     [rbp+240h+var_60], rax
0x1800031fc  movzx   eax, [rbp+240h+spc.spare2+1]
0x180003200  mov     [rsp+340h+var_2F0], eax
0x180003204  lea     rax, [rsp+340h+var_2F0]
0x180003209  mov     [rbp+240h+var_50], rax
0x180003210  lea     rax, [rbp+240h+var_120]
0x180003217  shr     edi, 1Fh
0x18000321a  mov     [rsp+340h+var_318], rax
0x18000321f  mov     [rsp+340h+OutputBufferLength], 0Eh
0x180003227  mov     [rbp+240h+var_E4], esi
0x18000322d  mov     [rbp+240h+var_D8], 2
0x180003238  mov     [rbp+240h+var_C4], esi
0x18000323e  mov     [rbp+240h+var_B8], 2
0x180003249  mov     [rbp+240h+var_A4], esi
0x18000324f  mov     [rbp+240h+var_98], 4
0x18000325a  mov     [rsp+340h+var_300], edi
0x18000325e  mov     [rbp+240h+var_88], 4
0x180003269  mov     [rbp+240h+var_78], 4
0x180003274  mov     [rbp+240h+var_68], 4
0x18000327f  mov     [rbp+240h+var_58], 4
0x18000328a  mov     [rbp+240h+var_48], 4
0x180003295  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18000329a  mov     rcx, [rbp+240h+var_40]
0x1800032a1  xor     rcx, rsp; StackCookie
0x1800032a4  call    __security_check_cookie
0x1800032a9  add     rsp, 318h
0x1800032b0  pop     r15
0x1800032b2  pop     r14
0x1800032b4  pop     rdi
0x1800032b5  pop     rsi
0x1800032b6  pop     rbx
0x1800032b7  pop     rbp
0x1800032b8  retn
```
