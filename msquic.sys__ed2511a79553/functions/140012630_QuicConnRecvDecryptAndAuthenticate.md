# QuicConnRecvDecryptAndAuthenticate

- ea: `0x140012630`
- end: `0x140012c76`
- name: `QuicConnRecvDecryptAndAuthenticate`
- size: `1606`
- prototype: `char __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x140012c80`

## callees

- `0x140008944`
- `0x1400123b0`
- `0x1400123c0`
- `0x140012630`
- `0x14001c638`
- `0x14002157c`
- `0x140021e20`
- `0x140026a88`
- `0x1400291f0`
- `0x140029ef0`
- `0x14003455c`
- `0x14003c8e0`
- `0x14003ead8`
- `0x14003ec10`
- `0x140040b80`
- `0x140041de0`
- `0x140042878`
- `0x140046774`
- `0x140048854`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140012847`
- `ntoskrnl!_snprintf_s` at `0x14001288b`
- `ntoskrnl!_snprintf_s` at `0x140012b92`
- `ntoskrnl!_snprintf_s` at `0x140012847`
- `ntoskrnl!_snprintf_s` at `0x14001288b`
- `ntoskrnl!_snprintf_s` at `0x140012b92`

## string_xrefs

- `0x140012b73`: `Updating current read key phase and packet number[%llu]`

## pseudocode

```c
char __fastcall QuicConnRecvDecryptAndAuthenticate(__int64 a1, __int64 a2, __int64 a3)
{
  char v6; // r14
  UCHAR *pbInput; // rsi
  int v8; // r8d
  __int64 v9; // rdx
  _BYTE *v10; // rdx
  __int64 v11; // rcx
  __int64 *v12; // rdx
  __int64 *v13; // rcx
  __int64 v14; // r8
  char v15; // al
  int v16; // r8d
  const char *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // r8
  char v21; // dl
  char v22; // cl
  const char *v23; // r8
  int v24; // ecx
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  int v28; // edx
  int v29; // r8d
  int v30; // edx
  char v31; // dl
  char v32; // cl
  char v33; // dl
  char v34; // dl
  bool v35; // zf
  char v36; // dl
  __int64 v37; // rcx
  int v38; // eax
  __int64 v39; // rsi
  unsigned __int64 v40; // rax
  __int64 v41; // rcx
  int v43; // r8d
  _BYTE v44[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v45[560]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v46; // [rsp+278h] [rbp+178h] BYREF
  char DstBuf[128]; // [rsp+290h] [rbp+190h] BYREF

  v6 = 0;
  pbInput = (UCHAR *)(*(_QWORD *)(a3 + 56) + *(unsigned __int16 *)(a3 + 82));
  if ( (unsigned __int8)QuicConnIsClient(a1) )
  {
    if ( (*(_BYTE *)(a3 + 92) & 4) != 0 )
    {
      v9 = *(unsigned __int16 *)(a3 + 84);
      if ( (unsigned int)(v9 + v8) >= 0x15 )
      {
        v6 = 1;
        v46 = *(_OWORD *)&pbInput[v9 - 16];
      }
    }
  }
  v10 = *(_BYTE **)(a1 + 8LL * *(int *)(a3 + 88) + 2872);
  v45[512] = v10[24];
  v45[513] = v10[25];
  v45[514] = v10[26];
  v45[515] = v10[27];
  v45[516] = *(_BYTE *)(a3 + 47) ^ v10[28];
  v45[517] = *(_BYTE *)(a3 + 46) ^ v10[29];
  v45[518] = *(_BYTE *)(a3 + 45) ^ v10[30];
  v45[519] = *(_BYTE *)(a3 + 44) ^ v10[31];
  v45[520] = *(_BYTE *)(a3 + 43) ^ v10[32];
  v45[521] = *(_BYTE *)(a3 + 42) ^ v10[33];
  v45[522] = *(_BYTE *)(a3 + 41) ^ v10[34];
  v11 = (unsigned __int8)v10[35];
  LOBYTE(v11) = *(_BYTE *)(a3 + 40) ^ v11;
  v35 = (*(_BYTE *)(a3 + 92) & 0x40) == 0;
  v45[523] = v11;
  if ( !v35 )
  {
    if ( (byte_14005C48F & 1) != 0 )
      McTemplateU0p_EtwWriteTransfer(v11, QuicPacketDecrypt);
    if ( (int)CxPlatDecrypt(
                *(BCRYPT_KEY_HANDLE *)(*(_QWORD *)(a1 + 8LL * *(int *)(a3 + 88) + 2872) + 8LL),
                *(_WORD *)(a3 + 84),
                pbInput) < 0 )
    {
      if ( v6 )
      {
        v12 = (__int64 *)(a1 + 1288);
        v13 = *(__int64 **)(a1 + 1288);
        if ( v13 != (__int64 *)(a1 + 1288) )
        {
          v14 = *((_QWORD *)&v46 + 1);
          while ( 1 )
          {
            v15 = *((_BYTE *)v13 + 32);
            if ( (v15 & 0x40) != 0 && (v15 & 0x20) == 0 && *((_OWORD *)v13 + 1) == v46 )
              break;
            v13 = (__int64 *)*v13;
            if ( v13 == v12 )
              goto LABEL_16;
          }
          if ( byte_14005C48E < 0 )
          {
            LOBYTE(v14) = 16;
            v17 = (const char *)QuicCidBufToStr(v45, &v46, v14, v46);
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "[S][RX][-] SR %s", v17);
            McTemplateU0s_EtwWriteTransfer(v18, QuicLogVerbose, DstBuf);
          }
          if ( byte_14005C48B < 0 )
          {
            _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Received stateless reset");
            McTemplateU0ps_EtwWriteTransfer(v19, QuicConnLogInfo, a1, DstBuf);
          }
          QuicConnCloseLocally(a1, 19, -1073741536);
          return 0;
        }
      }
LABEL_16:
      if ( byte_14005C48E < 0 )
      {
        if ( (*(_BYTE *)(a1 + 251) & 2) != 0 )
          v16 = (unsigned __int8)byte_14005C562;
        else
          v16 = 0;
        LOBYTE(v12) = 1;
        QuicPacketLogHeader(
          a1,
          (_DWORD)v12,
          v16,
          *(_QWORD *)(a3 + 40),
          *(_WORD *)(a3 + 82),
          *(_QWORD *)(a3 + 56),
          *(_DWORD *)(a1 + 3636));
      }
      ++*(_QWORD *)(a1 + 3808);
      QuicPacketLogDrop(a1, a3, "Decryption failure");
      _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(a1 + 72) + 2296LL));
      if ( *(_QWORD *)(a1 + 3808) < 0xB504F3u )
        return 0;
      v20 = 15;
LABEL_32:
      QuicConnCloseLocally(a1, 2, v20);
      return 0;
    }
  }
  ++*(_QWORD *)(a1 + 3816);
  v21 = *(_BYTE *)(a3 + 92);
  v22 = **(_BYTE **)(a3 + 56);
  if ( (v21 & 4) != 0 )
  {
    if ( (v22 & 0x18) != 0 )
    {
      v23 = "Invalid SH Reserved bits values";
LABEL_31:
      QuicPacketLogDrop(a1, a3, v23);
      v20 = 10;
      goto LABEL_32;
    }
  }
  else if ( (v22 & 0xC) != 0 )
  {
    v23 = "Invalid LH Reserved bits values";
    goto LABEL_31;
  }
  if ( (v21 & 0x40) != 0 )
    *(_WORD *)(a3 + 84) -= 16;
  v24 = *(_DWORD *)(a3 + 88);
  if ( v24 )
  {
    if ( v24 == 2 )
      v25 = 2768;
    else
      v25 = 2776;
  }
  else
  {
    v25 = 2760;
  }
  v26 = *(_QWORD *)(a3 + 40);
  v27 = *(_QWORD *)(v25 + a1) + 48LL;
  v44[0] = 0;
  if ( !QuicRangeAddRange(v27, v26, 1, v44) || !v44[0] )
  {
    if ( byte_14005C48E < 0 )
    {
      if ( (*(_BYTE *)(a1 + 251) & 2) != 0 )
        v43 = (unsigned __int8)byte_14005C562;
      else
        v43 = 0;
      LOBYTE(v28) = 1;
      QuicPacketLogHeader(
        a1,
        v28,
        v43,
        *(_QWORD *)(a3 + 40),
        *(_WORD *)(a3 + 80),
        *(_QWORD *)(a3 + 56),
        *(_DWORD *)(a1 + 3636));
    }
    QuicPacketLogDrop(a1, a3, "Duplicate packet number");
    ++*(_QWORD *)(a1 + 3800);
    return 0;
  }
  if ( byte_14005C48E < 0 )
  {
    if ( (*(_BYTE *)(a1 + 251) & 2) != 0 )
      v29 = (unsigned __int8)byte_14005C562;
    else
      v29 = 0;
    LOBYTE(v28) = 1;
    QuicPacketLogHeader(
      a1,
      v28,
      v29,
      *(_QWORD *)(a3 + 40),
      *(_WORD *)(a3 + 84) + *(_WORD *)(a3 + 82),
      *(_QWORD *)(a3 + 56),
      *(_DWORD *)(a1 + 3636));
    LOBYTE(v30) = 1;
    QuicFrameLogAll(
      a1,
      v30,
      *(_QWORD *)(a3 + 40),
      (unsigned __int16)(*(_WORD *)(a3 + 84) + *(_WORD *)(a3 + 82)),
      *(_QWORD *)(a3 + 56),
      *(_WORD *)(a3 + 82));
  }
  if ( (byte_14005C48B & 8) != 0 )
  {
    if ( (*(_BYTE *)(a3 + 92) & 4) != 0 )
      v31 = 5;
    else
      v31 = ((**(_BYTE **)(a3 + 56) >> 4) & 3) + 1;
    McTemplateU0pxuh_EtwWriteTransfer(
      (unsigned __int16)(*(_WORD *)(a3 + 82) + *(_WORD *)(a3 + 84)),
      (unsigned int)QuicConnPacketRecv,
      a1,
      *(_QWORD *)(a3 + 40),
      v31,
      *(_BYTE *)(a3 + 82) + *(_BYTE *)(a3 + 84));
  }
  v32 = *(_BYTE *)(a3 + 92);
  if ( (v32 & 4) == 0 )
  {
    v33 = **(_BYTE **)(a3 + 56);
    if ( *(_DWORD *)(a1 + 3636) == -817679509 )
    {
      v34 = v33 & 0x30;
      if ( v34 != 16 )
      {
        v35 = v34 == 32;
        goto LABEL_60;
      }
    }
    else
    {
      v36 = v33 & 0x30;
      if ( v36 )
      {
        v35 = v36 == 16;
LABEL_60:
        if ( v35 )
          *(_BYTE *)(a3 + 92) = v32 | 0x80;
        goto LABEL_65;
      }
    }
    if ( (*(_BYTE *)(a1 + 248) & 8) == 0
      && (unsigned __int8)QuicConnIsClient(a1)
      && !(unsigned __int8)QuicConnUpdateDestCid(v37, a3) )
    {
      return 0;
    }
  }
LABEL_65:
  if ( (*(_BYTE *)(a3 + 92) & 4) != 0 )
  {
    v38 = *(_DWORD *)(a3 + 88);
    v39 = *(_QWORD *)(a1 + 2776);
    if ( v38 == 5 )
    {
      QuicCryptoUpdateKeyPhase(a1, 0);
      v40 = *(_QWORD *)(a3 + 40);
      goto LABEL_71;
    }
    if ( v38 == 3 && ((*(_BYTE *)(v39 + 424) ^ (**(_BYTE **)(a3 + 56) >> 2)) & 1) == 0 )
    {
      v40 = *(_QWORD *)(a3 + 40);
      if ( v40 < *(_QWORD *)(v39 + 408) )
      {
LABEL_71:
        *(_QWORD *)(v39 + 408) = v40;
        if ( (byte_14005C48C & 1) != 0 )
        {
          _snprintf_s(
            DstBuf,
            0x80u,
            0xFFFFFFFFFFFFFFFFuLL,
            "Updating current read key phase and packet number[%llu]",
            *(_QWORD *)(a3 + 40));
          McTemplateU0ps_EtwWriteTransfer(v41, QuicConnLogVerbose, a1, DstBuf);
        }
      }
    }
  }
  if ( *(_DWORD *)(a3 + 88) == 2 && (unsigned __int8)QuicConnIsServer(a1) )
  {
    QuicCryptoDiscardKeys(a1 + 2784, 0);
    QuicPathSetValid(a1, a2, 1);
  }
  return 1;
}

```

## disassembly

```asm
0x140012630  mov     [rsp-8+arg_18], rbx
0x140012635  push    rbp
0x140012636  push    rsi
0x140012637  push    rdi
0x140012638  push    r14
0x14001263a  push    r15
0x14001263c  lea     rbp, [rsp-220h]
0x140012644  sub     rsp, 320h
0x14001264b  mov     rax, cs:__security_cookie
0x140012652  xor     rax, rsp
0x140012655  mov     [rbp+240h+var_30], rax
0x14001265c  mov     rbx, r8
0x14001265f  mov     r15, rdx
0x140012662  movzx   r8d, word ptr [r8+52h]
0x140012667  mov     rdi, rcx
0x14001266a  mov     esi, r8d
0x14001266d  xor     r14b, r14b
0x140012670  add     rsi, [rbx+38h]
0x140012674  call    QuicConnIsClient
0x140012679  test    al, al
0x14001267b  jz      short loc_14001269F
0x14001267d  test    byte ptr [rbx+5Ch], 4
0x140012681  jz      short loc_14001269F
0x140012683  movzx   edx, word ptr [rbx+54h]
0x140012687  lea     ecx, [rdx+r8]
0x14001268b  cmp     ecx, 15h
0x14001268e  jb      short loc_14001269F
0x140012690  movups  xmm0, xmmword ptr [rdx+rsi-10h]
0x140012695  mov     r14b, 1
0x140012698  movups  [rbp+240h+var_C8], xmm0
0x14001269f  movsxd  rax, dword ptr [rbx+58h]
0x1400126a3  mov     rdx, [rdi+rax*8+0B38h]
0x1400126ab  movzx   eax, byte ptr [rdx+18h]
0x1400126af  mov     [rbp+240h+var_F8], al
0x1400126b5  movzx   eax, byte ptr [rdx+19h]
0x1400126b9  mov     [rbp+240h+var_F7], al
0x1400126bf  movzx   eax, byte ptr [rdx+1Ah]
0x1400126c3  mov     [rbp+240h+var_F6], al
0x1400126c9  movzx   eax, byte ptr [rdx+1Bh]
0x1400126cd  mov     [rbp+240h+var_F5], al
0x1400126d3  movzx   ecx, byte ptr [rdx+1Ch]
0x1400126d7  xor     cl, [rbx+2Fh]
0x1400126da  mov     [rbp+240h+var_F4], cl
0x1400126e0  movzx   ecx, byte ptr [rdx+1Dh]
0x1400126e4  xor     cl, [rbx+2Eh]
0x1400126e7  mov     [rbp+240h+var_F3], cl
0x1400126ed  movzx   ecx, byte ptr [rdx+1Eh]
0x1400126f1  xor     cl, [rbx+2Dh]
0x1400126f4  mov     [rbp+240h+var_F2], cl
0x1400126fa  movzx   ecx, byte ptr [rdx+1Fh]
0x1400126fe  xor     cl, [rbx+2Ch]
0x140012701  mov     [rbp+240h+var_F1], cl
0x140012707  movzx   ecx, byte ptr [rdx+20h]
0x14001270b  xor     cl, [rbx+2Bh]
0x14001270e  mov     [rbp+240h+var_F0], cl
0x140012714  movzx   ecx, byte ptr [rdx+21h]
0x140012718  xor     cl, [rbx+2Ah]
0x14001271b  mov     [rbp+240h+var_EF], cl
0x140012721  movzx   ecx, byte ptr [rdx+22h]
0x140012725  xor     cl, [rbx+29h]
0x140012728  mov     [rbp+240h+var_EE], cl
0x14001272e  movzx   ecx, byte ptr [rdx+23h]
0x140012732  xor     cl, [rbx+28h]
0x140012735  test    byte ptr [rbx+5Ch], 40h
0x140012739  mov     [rbp+240h+var_ED], cl
0x14001273f  jz      loc_140012933
0x140012745  test    cs:byte_14005C48F, 1
0x14001274c  jz      short loc_14001275E
0x14001274e  mov     r8, [rbx+20h]
0x140012752  lea     rdx, QuicPacketDecrypt
0x140012759  call    McTemplateU0p_EtwWriteTransfer
0x14001275e  movsxd  rax, dword ptr [rbx+58h]
0x140012762  lea     rdx, [rbp+240h+var_F8]
0x140012769  mov     r9, [rbx+38h]
0x14001276d  movzx   r8d, word ptr [rbx+52h]
0x140012772  mov     [rsp+340h+pbInput], rsi; pbInput
0x140012777  mov     rcx, [rdi+rax*8+0B38h]
0x14001277f  movzx   eax, word ptr [rbx+54h]
0x140012783  mov     [rsp+340h+var_320], ax; __int16
0x140012788  mov     rcx, [rcx+8]; hKey
0x14001278c  call    CxPlatDecrypt
0x140012791  test    eax, eax
0x140012793  jns     loc_140012933
0x140012799  test    r14b, r14b
0x14001279c  jz      short loc_1400127E0
0x14001279e  lea     rdx, [rdi+508h]
0x1400127a5  mov     rcx, [rdx]
0x1400127a8  cmp     rcx, rdx
0x1400127ab  jz      short loc_1400127E0
0x1400127ad  mov     r8, qword ptr [rbp+240h+var_C8+8]
0x1400127b4  mov     r9, qword ptr [rbp+240h+var_C8]
0x1400127bb  nop     dword ptr [rax+rax+00h]
0x1400127c0  movzx   eax, byte ptr [rcx+20h]
0x1400127c4  test    al, 40h
0x1400127c6  jz      short loc_1400127D8
0x1400127c8  test    al, 20h
0x1400127ca  jnz     short loc_1400127D8
0x1400127cc  cmp     [rcx+10h], r9
0x1400127d0  jnz     short loc_1400127D8
0x1400127d2  cmp     [rcx+18h], r8
0x1400127d6  jz      short loc_140012809
0x1400127d8  mov     rcx, [rcx]
0x1400127db  cmp     rcx, rdx
0x1400127de  jnz     short loc_1400127C0
0x1400127e0  movzx   eax, cs:byte_14005C48E
0x1400127e7  test    al, al
0x1400127e9  jns     loc_1400128F5
0x1400127ef  test    byte ptr [rdi+0FBh], 2
0x1400127f6  jz      loc_1400128C8
0x1400127fc  movzx   r8d, cs:byte_14005C562
0x140012804  jmp     loc_1400128CB
0x140012809  movzx   eax, cs:byte_14005C48E
0x140012810  test    al, al
0x140012812  jns     short loc_140012866
0x140012814  mov     r8b, 10h
0x140012817  lea     rdx, [rbp+240h+var_C8]
0x14001281e  lea     rcx, [rsp+340h+var_2F8]
0x140012823  call    QuicCidBufToStr
0x140012828  lea     r9, aSRxSrS; "[S][RX][-] SR %s"
0x14001282f  mov     qword ptr [rsp+340h+var_320], rax
0x140012834  mov     edx, 80h; SizeInBytes
0x140012839  lea     rcx, [rbp+240h+DstBuf]; DstBuf
0x140012840  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140012847  call    cs:__imp__snprintf_s
0x14001284e  nop     dword ptr [rax+rax+00h]
0x140012853  lea     r8, [rbp+240h+DstBuf]
0x14001285a  lea     rdx, QuicLogVerbose
0x140012861  call    McTemplateU0s_EtwWriteTransfer
0x140012866  movzx   eax, cs:byte_14005C48B
0x14001286d  test    al, al
0x14001286f  jns     short loc_1400128AD
0x140012871  lea     r9, aReceivedStatel; "Received stateless reset"
0x140012878  mov     edx, 80h; SizeInBytes
0x14001287d  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140012884  lea     rcx, [rbp+240h+DstBuf]; DstBuf
0x14001288b  call    cs:__imp__snprintf_s
0x140012892  nop     dword ptr [rax+rax+00h]
0x140012897  lea     r9, [rbp+240h+DstBuf]
0x14001289e  mov     r8, rdi
0x1400128a1  lea     rdx, QuicConnLogInfo
0x1400128a8  call    McTemplateU0ps_EtwWriteTransfer
0x1400128ad  xor     r9d, r9d
0x1400128b0  mov     r8, 0FFFFFFFFC0000120h
0x1400128b7  mov     rcx, rdi
0x1400128ba  lea     edx, [r9+13h]
0x1400128be  call    QuicConnCloseLocally
0x1400128c3  jmp     loc_140012C4D
0x1400128c8  xor     r8d, r8d
0x1400128cb  mov     eax, [rdi+0E34h]
0x1400128d1  mov     dl, 1
0x1400128d3  mov     r9, [rbx+28h]
0x1400128d7  mov     rcx, rdi
0x1400128da  mov     [rsp+340h+var_310], eax
0x1400128de  mov     rax, [rbx+38h]
0x1400128e2  mov     [rsp+340h+pbInput], rax
0x1400128e7  movzx   eax, word ptr [rbx+52h]
0x1400128eb  mov     [rsp+340h+var_320], ax
0x1400128f0  call    QuicPacketLogHeader
0x1400128f5  inc     qword ptr [rdi+0EE0h]
0x1400128fc  lea     r8, aDecryptionFail; "Decryption failure"
0x140012903  mov     rdx, rbx
0x140012906  mov     rcx, rdi
0x140012909  call    QuicPacketLogDrop
0x14001290e  mov     rax, [rdi+48h]
0x140012912  lock inc qword ptr [rax+8F8h]
0x14001291a  cmp     qword ptr [rdi+0EE0h], 0B504F3h
0x140012925  jb      loc_140012C4D
0x14001292b  mov     r8d, 0Fh
0x140012931  jmp     short loc_140012967
0x140012933  inc     qword ptr [rdi+0EE8h]
0x14001293a  mov     rax, [rbx+38h]
0x14001293e  movzx   edx, byte ptr [rbx+5Ch]
0x140012942  movzx   ecx, byte ptr [rax]
0x140012945  test    dl, 4
0x140012948  jz      short loc_14001297C
0x14001294a  test    cl, 18h
0x14001294d  jz      short loc_14001298A
0x14001294f  lea     r8, aInvalidShReser; "Invalid SH Reserved bits values"
0x140012956  mov     rdx, rbx
0x140012959  mov     rcx, rdi
0x14001295c  call    QuicPacketLogDrop
0x140012961  mov     r8d, 0Ah
0x140012967  mov     edx, 2
0x14001296c  xor     r9d, r9d
0x14001296f  mov     rcx, rdi
0x140012972  call    QuicConnCloseLocally
0x140012977  jmp     loc_140012C4D
0x14001297c  test    cl, 0Ch
0x14001297f  jz      short loc_14001298A
0x140012981  lea     r8, aInvalidLhReser; "Invalid LH Reserved bits values"
0x140012988  jmp     short loc_140012956
0x14001298a  test    dl, 40h
0x14001298d  jz      short loc_140012998
0x14001298f  mov     eax, 0FFF0h
0x140012994  add     [rbx+54h], ax
0x140012998  mov     ecx, [rbx+58h]
0x14001299b  test    ecx, ecx
0x14001299d  jz      short loc_1400129B7
0x14001299f  sub     ecx, 1
0x1400129a2  jz      short loc_1400129A9
0x1400129a4  cmp     ecx, 1
0x1400129a7  jz      short loc_1400129B0
0x1400129a9  mov     ecx, 0AD8h
0x1400129ae  jmp     short loc_1400129BC
0x1400129b0  mov     ecx, 0AD0h
0x1400129b5  jmp     short loc_1400129BC
0x1400129b7  mov     ecx, 0AC8h
0x1400129bc  mov     rcx, [rcx+rdi]
0x1400129c0  lea     r9, [rsp+340h+var_300]
0x1400129c5  mov     rdx, [rbx+28h]
0x1400129c9  add     rcx, 30h ; '0'
0x1400129cd  mov     r8d, 1
0x1400129d3  mov     [rsp+340h+var_300], 0
0x1400129d8  call    QuicRangeAddRange
0x1400129dd  test    rax, rax
0x1400129e0  jz      loc_140012BE9
0x1400129e6  cmp     [rsp+340h+var_300], 0
0x1400129eb  jz      loc_140012BE9
0x1400129f1  movzx   eax, cs:byte_14005C48E
0x1400129f8  test    al, al
0x1400129fa  jns     short loc_140012A69
0x1400129fc  test    byte ptr [rdi+0FBh], 2
0x140012a03  jz      short loc_140012A0F
0x140012a05  movzx   r8d, cs:byte_14005C562
0x140012a0d  jmp     short loc_140012A12
0x140012a0f  xor     r8d, r8d
0x140012a12  mov     eax, [rdi+0E34h]
0x140012a18  mov     dl, 1
0x140012a1a  movzx   ecx, word ptr [rbx+52h]
0x140012a1e  add     cx, [rbx+54h]
0x140012a22  mov     r9, [rbx+28h]
0x140012a26  mov     [rsp+340h+var_310], eax
0x140012a2a  mov     rax, [rbx+38h]
0x140012a2e  mov     [rsp+340h+pbInput], rax
0x140012a33  mov     [rsp+340h+var_320], cx
0x140012a38  mov     rcx, rdi
0x140012a3b  call    QuicPacketLogHeader
0x140012a40  movzx   eax, word ptr [rbx+52h]
0x140012a44  mov     dl, 1
0x140012a46  mov     r8, [rbx+28h]
0x140012a4a  movzx   r9d, ax
0x140012a4e  add     r9w, [rbx+54h]
0x140012a53  mov     rcx, rdi
0x140012a56  mov     word ptr [rsp+340h+pbInput], ax
0x140012a5b  mov     rax, [rbx+38h]
0x140012a5f  mov     qword ptr [rsp+340h+var_320], rax
0x140012a64  call    QuicFrameLogAll
0x140012a69  test    cs:byte_14005C48B, 8
0x140012a70  jz      short loc_140012AAF
0x140012a72  test    byte ptr [rbx+5Ch], 4
0x140012a76  jz      short loc_140012A7C
0x140012a78  mov     dl, 5
0x140012a7a  jmp     short loc_140012A8B
0x140012a7c  mov     rax, [rbx+38h]
0x140012a80  movzx   edx, byte ptr [rax]
0x140012a83  shr     dl, 4
0x140012a86  and     dl, 3
0x140012a89  inc     dl
0x140012a8b  movzx   ecx, word ptr [rbx+54h]
0x140012a8f  mov     r8, rdi
0x140012a92  add     cx, [rbx+52h]
0x140012a96  mov     r9, [rbx+28h]
0x140012a9a  mov     word ptr [rsp+340h+pbInput], cx
0x140012a9f  mov     byte ptr [rsp+340h+var_320], dl
0x140012aa3  lea     rdx, QuicConnPacketRecv
0x140012aaa  call    McTemplateU0pxuh_EtwWriteTransfer
0x140012aaf  movzx   ecx, byte ptr [rbx+5Ch]
0x140012ab3  test    cl, 4
0x140012ab6  jnz     short loc_140012B0F
0x140012ab8  cmp     dword ptr [rdi+0E34h], 0CF43336Bh
0x140012ac2  mov     rax, [rbx+38h]
0x140012ac6  movzx   edx, byte ptr [rax]
0x140012ac9  jnz     short loc_140012AD8
0x140012acb  and     dl, 30h
0x140012ace  cmp     dl, 10h
0x140012ad1  jz      short loc_140012AEA
0x140012ad3  cmp     dl, 20h ; ' '
0x140012ad6  jmp     short loc_140012AE0
0x140012ad8  and     dl, 30h
0x140012adb  jz      short loc_140012AEA
0x140012add  cmp     dl, 10h
0x140012ae0  jnz     short loc_140012B0F
0x140012ae2  or      cl, 80h
0x140012ae5  mov     [rbx+5Ch], cl
0x140012ae8  jmp     short loc_140012B0F
0x140012aea  test    byte ptr [rdi+0F8h], 8
0x140012af1  jnz     short loc_140012B0F
0x140012af3  mov     rcx, rdi
0x140012af6  call    QuicConnIsClient
0x140012afb  test    al, al
0x140012afd  jz      short loc_140012B0F
0x140012aff  mov     rdx, rbx
0x140012b02  call    QuicConnUpdateDestCid
0x140012b07  test    al, al
0x140012b09  jz      loc_140012C4D
0x140012b0f  test    byte ptr [rbx+5Ch], 4
0x140012b13  jz      loc_140012BB4
0x140012b19  mov     eax, [rbx+58h]
0x140012b1c  mov     rsi, [rdi+0AD8h]
0x140012b23  cmp     eax, 5
  ... truncated ...
```
