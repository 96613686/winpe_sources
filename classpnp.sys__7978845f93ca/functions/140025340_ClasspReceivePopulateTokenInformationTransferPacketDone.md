# ClasspReceivePopulateTokenInformationTransferPacketDone

- ea: `0x140025340`
- end: `0x1400259c3`
- name: `ClasspReceivePopulateTokenInformationTransferPacketDone`
- size: `1667`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001008`
- `0x1400084b0`
- `0x14002001c`
- `0x140023d08`
- `0x140025340`
- `0x140026f28`
- `0x140026ffc`
- `0x1400271dc`
- `0x140027760`
- `0x140027870`
- `0x14002c518`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002562f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002562f`

## string_xrefs

- `0x1400255e4`: `Target truncated read. `

## pseudocode

```c
char __fastcall ClasspReceivePopulateTokenInformationTransferPacketDone(_QWORD *P)
{
  struct _DEVICE_OBJECT *v1; // r14
  char *v2; // rax
  __int64 v4; // r13
  int v5; // esi
  unsigned int *DeviceExtension; // r9
  NTSTATUS v7; // ecx
  char v8; // cl
  char v9; // r15
  unsigned __int64 v10; // r13
  __int64 v11; // rcx
  unsigned __int64 v12; // r12
  unsigned int *v13; // r12
  __int64 v14; // rax
  void *v15; // rsi
  __int64 *v16; // rdx
  const wchar_t *v17; // rcx
  bool v18; // zf
  struct _SCSI_REQUEST_BLOCK *v19; // rdx
  char v20; // r11
  __int64 v21; // r10
  __int64 v22; // rcx
  unsigned __int64 v23; // r9
  __int64 v24; // r8
  int v25; // ecx
  int v26; // ecx
  __int64 v27; // r8
  __int64 v28; // rcx
  __int64 v29; // r10
  __int64 v30; // r8
  __int64 v31; // r11
  char **v32; // r9
  unsigned int v33; // edx
  __int64 i; // rcx
  __int64 v35; // rax
  __int64 v36; // rax
  unsigned __int8 v38; // [rsp+40h] [rbp-99h]
  NTSTATUS Status; // [rsp+44h] [rbp-95h] BYREF
  char v40; // [rsp+48h] [rbp-91h]
  unsigned __int64 v41; // [rsp+50h] [rbp-89h]
  __int64 v42; // [rsp+58h] [rbp-81h] BYREF
  int v43; // [rsp+60h] [rbp-79h]
  int v44; // [rsp+64h] [rbp-75h]
  ULONG RetryInterval; // [rsp+68h] [rbp-71h] BYREF
  __int64 v46; // [rsp+70h] [rbp-69h] BYREF
  char *v47; // [rsp+78h] [rbp-61h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v48; // [rsp+80h] [rbp-59h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-39h]
  __int64 v50; // [rsp+A8h] [rbp-31h]
  char **v51; // [rsp+B0h] [rbp-29h]
  __int64 v52; // [rsp+B8h] [rbp-21h]
  __int64 *v53; // [rsp+C0h] [rbp-19h]
  __int64 v54; // [rsp+C8h] [rbp-11h]
  __int64 *v55; // [rsp+D0h] [rbp-9h]
  __int64 v56; // [rsp+D8h] [rbp-1h]

  v1 = (struct _DEVICE_OBJECT *)*P;
  v2 = (char *)P[28];
  v4 = P[1];
  v5 = *((_DWORD *)P + 63);
  Status = 0;
  DeviceExtension = (unsigned int *)v1->DeviceExtension;
  v42 = (__int64)DeviceExtension;
  v43 = v5;
  v46 = v4;
  RetryInterval = 512;
  if ( !v2 )
    v2 = (char *)(P + 2);
  v7 = *((_DWORD *)v2 + 12);
  Status = v7;
  if ( v7 == -1073741764 )
  {
    Status = 0;
  }
  else if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      LODWORD(v2) = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( ((unsigned __int8)v2 & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        LOBYTE(v2) = WPP_SF_qDD(
                       WPP_GLOBAL_Control->AttachedDevice,
                       244,
                       WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
                       v1,
                       v5,
                       Status);
    }
    goto LABEL_84;
  }
  v8 = 0;
  v9 = *((_BYTE *)P + 389) & 0x7F;
  if ( v9 == 1
    || (*((_BYTE *)P + 389) & 0x7F) == 2
    || (*((_BYTE *)P + 389) & 0x7F) == 3
    || (*((_BYTE *)P + 389) & 0x7F) == 0x60 )
  {
    v8 = 1;
  }
  HIBYTE(v41) = *((_BYTE *)P + 400);
  BYTE6(v41) = *((_BYTE *)P + 401);
  BYTE5(v41) = *((_BYTE *)P + 402);
  BYTE4(v41) = *((_BYTE *)P + 403);
  BYTE3(v41) = *((_BYTE *)P + 404);
  BYTE2(v41) = *((_BYTE *)P + 405);
  BYTE1(v41) = *((_BYTE *)P + 406);
  LOBYTE(v41) = *((_BYTE *)P + 407);
  if ( !v8 )
  {
    Status = -1073741823;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      LOBYTE(v2) = WPP_SF_qDD(
                     WPP_GLOBAL_Control->AttachedDevice,
                     250,
                     WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
                     v1,
                     v5,
                     -1073741823);
      goto LABEL_84;
    }
    goto LABEL_85;
  }
  v10 = v41;
  v11 = *((unsigned __int8 *)P + 397);
  v12 = P[33];
  v38 = *((_BYTE *)P + 396);
  v44 = 0;
  v47 = 0;
  if ( v41 > v12 )
    v10 = 0;
  v40 = *((_BYTE *)P + 398);
  if ( ((v9 - 1) & 0xFD) != 0 )
    v10 = 0;
  BYTE3(v41) = *((_BYTE *)P + v11 + 416);
  BYTE2(v41) = *((_BYTE *)P + v11 + 417);
  BYTE1(v41) = *((_BYTE *)P + v11 + 418);
  LOBYTE(v41) = *((_BYTE *)P + v11 + 419);
  if ( !(_DWORD)v41 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qDII(
        WPP_GLOBAL_Control->AttachedDevice,
        WPP_GLOBAL_Control,
        (unsigned int)v41,
        v1,
        v5,
        v10 * DeviceExtension[143],
        v12 * DeviceExtension[143]);
    }
    P[34] = 0;
    goto LABEL_21;
  }
  if ( (_DWORD)v41 == 514 )
  {
    P[34] = v10;
    v44 = 512;
    v47 = (char *)P + v11 + 422;
    if ( v10 < v12 )
      v44 = v10 != 0 ? 0x200 : 0;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      v14 = ClasspBinaryToAscii((char *)P + v11 + 422, 512, &RetryInterval);
      v15 = (void *)v14;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v13 = (unsigned int *)v42;
      }
      else
      {
        v16 = &qword_140043B90;
        v17 = &word_140043310;
        if ( v14 )
          v16 = (__int64 *)v14;
        v18 = v10 == v12;
        v13 = (unsigned int *)v42;
        if ( !v18 )
          v17 = L"Target truncated read. ";
        WPP_SF_qSsDI(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v16,
          (_DWORD)WPP_GLOBAL_Control,
          (_DWORD)v1,
          (__int64)v17,
          (__int64)v16,
          v43,
          *((_BYTE *)P + 272) * *(_DWORD *)(v42 + 572));
      }
      if ( v15 )
        ExFreePoolWithTag(v15, 0);
      v5 = v43;
      goto LABEL_46;
    }
    goto LABEL_21;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 245, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, v1, v41);
LABEL_21:
    v13 = (unsigned int *)v42;
    goto LABEL_46;
  }
  v13 = DeviceExtension;
LABEL_46:
  LOBYTE(v2) = v9 - 2;
  Status = 0;
  if ( (unsigned __int8)(v9 - 2) > 1u && v9 != 96 )
    goto LABEL_73;
  v19 = (struct _SCSI_REQUEST_BLOCK *)(P + 36);
  if ( *((_BYTE *)P + 290) != 40 )
  {
    *((_BYTE *)P + 292) = v38;
    goto LABEL_64;
  }
  if ( *((_DWORD *)P + 77) )
    goto LABEL_64;
  v20 = 0;
  v21 = 0;
  if ( !*((_DWORD *)P + 86) )
    goto LABEL_64;
  while ( 1 )
  {
    v22 = *((unsigned int *)&v19[1].SenseInfoBuffer + v21);
    if ( (unsigned int)v22 >= 0x80 )
    {
      v23 = *((unsigned int *)P + 76);
      if ( (unsigned int)v22 < (unsigned int)v23 )
        break;
    }
LABEL_58:
    v21 = (unsigned int)(v21 + 1);
    if ( (unsigned int)v21 >= *((_DWORD *)P + 86) )
      goto LABEL_64;
  }
  v24 = (unsigned int)v22;
  v25 = *(_DWORD *)((char *)&v19->Length + v22) - 64;
  if ( v25 )
  {
    v26 = v25 - 1;
    if ( !v26 )
    {
      if ( v24 + 56 <= v23 )
      {
        v20 = 1;
        *(&v19->QueueTag + v24) = v38;
      }
LABEL_57:
      if ( v20 )
        goto LABEL_64;
      goto LABEL_58;
    }
    if ( v26 != 1 )
      goto LABEL_57;
  }
  if ( v24 + 40 > v23 )
    goto LABEL_57;
  *(&v19->QueueTag + v24) = v38;
LABEL_64:
  if ( v40 )
  {
    *((_BYTE *)P + 299) = v40;
    P[40] = P + 52;
    RetryInterval = 0;
    *((_WORD *)P + 145) = -31744;
    LOBYTE(v2) = ClassInterpretSenseInfo(v1, v19, 0xFu, 0, 0, &Status, &RetryInterval);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      LODWORD(v2) = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( ((unsigned __int8)v2 & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        LOBYTE(v2) = WPP_SF_qDDI(WPP_GLOBAL_Control->AttachedDevice, 248, v27, v1, Status, v5, v10 * v13[143]);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    LODWORD(v2) = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( ((unsigned __int8)v2 & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      LOBYTE(v2) = WPP_SF_qDDI(WPP_GLOBAL_Control->AttachedDevice, 249, WPP_GLOBAL_Control, v1, v38, v5, v10 * v13[143]);
  }
LABEL_73:
  v4 = v46;
  if ( v44 )
  {
    v28 = *(_QWORD *)(v46 + 24);
    v29 = v13[143];
    v30 = 0;
    v31 = P[34];
    v32 = (char **)(v28 + *(unsigned int *)(v28 + 20));
    v33 = *(_DWORD *)(v28 + 24) >> 4;
    for ( i = 0; (unsigned int)i < v33; v30 += (__int64)v32[2 * v35 + 1] )
    {
      v35 = (unsigned int)i;
      i = (unsigned int)(i + 1);
    }
    P[47] = v47;
    LOBYTE(v2) = dword_14004D060;
    Status = 0;
    if ( (unsigned int)dword_14004D060 > 5 )
    {
      v36 = *((_QWORD *)v13 + 146) + 4LL;
      v50 = 16;
      v49 = v36;
      v47 = *v32;
      v51 = &v47;
      v53 = &v46;
      v55 = &v42;
      v52 = 8;
      v46 = v30;
      v54 = 8;
      v42 = v31 * v29;
      v56 = 8;
      LOBYTE(v2) = tlgWriteTransfer_EtwWriteTransfer(i, (unsigned __int8 *)&byte_140048845, v30, (__int64)v32, 6u, &v48);
    }
  }
  else if ( Status >= 0 )
  {
    Status = -1073741823;
  }
LABEL_84:
  if ( Status != 259 )
LABEL_85:
    LOBYTE(v2) = ClasspCompleteOffloadRead(P);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    LODWORD(v2) = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( ((unsigned __int8)v2 & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      LOBYTE(v2) = WPP_SF_qqD(
                     WPP_GLOBAL_Control->AttachedDevice,
                     251,
                     WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
                     v1,
                     v4,
                     Status);
  }
  return (char)v2;
}

```

## disassembly

```asm
0x140025340  push    rbp
0x140025342  push    rbx
0x140025343  push    rsi
0x140025344  push    rdi
0x140025345  push    r12
0x140025347  push    r13
0x140025349  push    r14
0x14002534b  push    r15
0x14002534d  lea     rbp, [rsp-1Fh]
0x140025352  sub     rsp, 0F8h
0x140025359  mov     rax, cs:__security_cookie
0x140025360  xor     rax, rsp
0x140025363  mov     [rbp+57h+var_50], rax
0x140025367  mov     r14, [rcx]
0x14002536a  mov     r10d, 200h
0x140025370  mov     rax, [rcx+0E0h]
0x140025377  mov     rbx, rcx
0x14002537a  mov     r13, [rcx+8]
0x14002537e  mov     esi, [rcx+0FCh]
0x140025384  mov     [rsp+130h+var_EC], 0
0x14002538c  mov     r9, [r14+40h]
0x140025390  mov     [rsp+130h+var_D8], r9
0x140025395  mov     [rbp+57h+var_D0], esi
0x140025398  mov     [rbp+57h+var_C0], r13
0x14002539c  mov     [rbp+57h+var_C8], r10d
0x1400253a0  test    rax, rax
0x1400253a3  jnz     short loc_1400253A9
0x1400253a5  lea     rax, [rcx+10h]
0x1400253a9  mov     ecx, [rax+30h]
0x1400253ac  lea     r11, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x1400253b3  mov     [rsp+130h+var_EC], ecx
0x1400253b7  cmp     ecx, 0C000003Ch
0x1400253bd  jnz     loc_140025523
0x1400253c3  mov     [rsp+130h+var_EC], 0
0x1400253cb  mov     al, [rbx+185h]
0x1400253d1  xor     cl, cl
0x1400253d3  and     al, 7Fh
0x1400253d5  movzx   r15d, al
0x1400253d9  mov     eax, r15d
0x1400253dc  sub     eax, 1
0x1400253df  jz      short loc_1400253F0
0x1400253e1  sub     eax, 1
0x1400253e4  jz      short loc_1400253F0
0x1400253e6  sub     eax, 1
0x1400253e9  jz      short loc_1400253F0
0x1400253eb  cmp     eax, 5Dh ; ']'
0x1400253ee  jnz     short loc_1400253F2
0x1400253f0  mov     cl, 1
0x1400253f2  mov     al, [rbx+190h]
0x1400253f8  mov     byte ptr [rsp+130h+var_E0+7], al
0x1400253fc  mov     al, [rbx+191h]
0x140025402  mov     byte ptr [rsp+130h+var_E0+6], al
0x140025406  mov     al, [rbx+192h]
0x14002540c  mov     byte ptr [rsp+130h+var_E0+5], al
0x140025410  mov     al, [rbx+193h]
0x140025416  mov     byte ptr [rsp+130h+var_E0+4], al
0x14002541a  mov     al, [rbx+194h]
0x140025420  mov     byte ptr [rsp+130h+var_E0+3], al
0x140025424  mov     al, [rbx+195h]
0x14002542a  mov     byte ptr [rsp+130h+var_E0+2], al
0x14002542e  mov     al, [rbx+196h]
0x140025434  mov     byte ptr [rsp+130h+var_E0+1], al
0x140025438  mov     al, [rbx+197h]
0x14002543e  mov     byte ptr [rsp+130h+var_E0], al
0x140025442  test    cl, cl
0x140025444  jz      loc_140025906
0x14002544a  mov     r13, [rsp+130h+var_E0]
0x14002544f  lea     rdi, WPP_GLOBAL_Control
0x140025456  movzx   ecx, byte ptr [rbx+18Dh]
0x14002545d  xor     edx, edx
0x14002545f  mov     al, [rbx+18Ch]
0x140025465  mov     r12, [rbx+108h]
0x14002546c  mov     [rsp+130h+var_F0], al
0x140025470  xor     eax, eax
0x140025472  cmp     r13, r12
0x140025475  mov     [rbp+57h+var_CC], edx
0x140025478  mov     [rbp+57h+var_B8], rdx
0x14002547c  cmova   r13, rax
0x140025480  lea     eax, [r15-1]
0x140025484  test    al, 0FDh
0x140025486  mov     al, [rbx+18Eh]
0x14002548c  mov     [rsp+130h+var_E8], al
0x140025490  mov     al, [rcx+rbx+1A0h]
0x140025497  cmovnz  r13, rdx
0x14002549b  mov     byte ptr [rsp+130h+var_E0+3], al
0x14002549f  mov     al, [rcx+rbx+1A1h]
0x1400254a6  mov     byte ptr [rsp+130h+var_E0+2], al
0x1400254aa  mov     al, [rcx+rbx+1A2h]
0x1400254b1  mov     byte ptr [rsp+130h+var_E0+1], al
0x1400254b5  mov     al, [rcx+rbx+1A3h]
0x1400254bc  mov     byte ptr [rsp+130h+var_E0], al
0x1400254c0  mov     r8d, dword ptr [rsp+130h+var_E0]
0x1400254c5  test    r8d, r8d
0x1400254c8  jz      loc_140025640
0x1400254ce  cmp     r8d, 202h
0x1400254d5  jz      loc_140025569
0x1400254db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400254e2  cmp     rcx, rdi
0x1400254e5  jz      loc_140025694
0x1400254eb  mov     eax, [rcx+2Ch]
0x1400254ee  test    al, 10h
0x1400254f0  jz      loc_140025694
0x1400254f6  cmp     byte ptr [rcx+29h], 2
0x1400254fa  jb      loc_140025694
0x140025500  mov     rcx, [rcx+18h]
0x140025504  mov     edx, 0F5h
0x140025509  mov     [rsp+130h+RetryCount], r8d
0x14002550e  mov     r9, r14
0x140025511  mov     r8, r11
0x140025514  call    WPP_SF_qD
0x140025519  mov     r12, [rsp+130h+var_D8]
0x14002551e  jmp     loc_140025697
0x140025523  test    ecx, ecx
0x140025525  jns     loc_1400253CB
0x14002552b  mov     rcx, cs:WPP_GLOBAL_Control
0x140025532  lea     rdi, WPP_GLOBAL_Control
0x140025539  cmp     rcx, rdi
0x14002553c  jz      loc_14002594E
0x140025542  mov     eax, [rcx+2Ch]
0x140025545  test    al, 10h
0x140025547  jz      loc_14002594E
0x14002554d  cmp     byte ptr [rcx+29h], 2
0x140025551  jb      loc_14002594E
0x140025557  mov     eax, [rsp+130h+var_EC]
0x14002555b  mov     edx, 0F4h
0x140025560  mov     dword ptr [rsp+130h+Status], eax
0x140025564  jmp     loc_14002593B
0x140025569  lea     r9, [rbx+1A6h]
0x140025570  mov     [rbx+110h], r13
0x140025577  add     r9, rcx
0x14002557a  mov     edx, r10d
0x14002557d  mov     [rbp+57h+var_CC], edx
0x140025580  mov     [rbp+57h+var_B8], r9
0x140025584  cmp     r13, r12
0x140025587  jnb     short loc_140025596
0x140025589  mov     rax, r13
0x14002558c  neg     rax
0x14002558f  sbb     ecx, ecx
0x140025591  and     ecx, edx
0x140025593  mov     [rbp+57h+var_CC], ecx
0x140025596  mov     rax, cs:WPP_GLOBAL_Control
0x14002559d  mov     ecx, [rax+2Ch]
0x1400255a0  test    cl, 10h
0x1400255a3  jz      loc_140025519
0x1400255a9  lea     r8, [rbp+57h+var_C8]
0x1400255ad  mov     rcx, r9
0x1400255b0  call    ClasspBinaryToAscii
0x1400255b5  mov     rsi, rax
0x1400255b8  mov     r8, cs:WPP_GLOBAL_Control
0x1400255bf  cmp     r8, rdi
0x1400255c2  jz      short loc_140025620
0x1400255c4  test    rax, rax
0x1400255c7  lea     rdx, qword_140043B90
0x1400255ce  lea     rcx, word_140043310
0x1400255d5  mov     r9, r14
0x1400255d8  cmovnz  rdx, rax
0x1400255dc  cmp     r13, r12
0x1400255df  mov     r12, [rsp+130h+var_D8]
0x1400255e4  lea     rax, aTargetTruncate_0; "Target truncated read. "
0x1400255eb  cmovnz  rcx, rax
0x1400255ef  mov     eax, [r12+23Ch]
0x1400255f7  imul    rax, [rbx+110h]
0x1400255ff  mov     [rsp+130h+var_F8], rax
0x140025604  mov     eax, [rbp+57h+var_D0]
0x140025607  mov     dword ptr [rsp+130h+RetryInterval], eax
0x14002560b  mov     [rsp+130h+Status], rdx
0x140025610  mov     qword ptr [rsp+130h+RetryCount], rcx
0x140025615  mov     rcx, [r8+18h]
0x140025619  call    WPP_SF_qSsDI
0x14002561e  jmp     short loc_140025625
0x140025620  mov     r12, [rsp+130h+var_D8]
0x140025625  test    rsi, rsi
0x140025628  jz      short loc_14002563B
0x14002562a  xor     edx, edx; Tag
0x14002562c  mov     rcx, rsi; P
0x14002562f  call    cs:__imp_ExFreePoolWithTag
0x140025636  nop     dword ptr [rax+rax+00h]
0x14002563b  mov     esi, [rbp+57h+var_D0]
0x14002563e  jmp     short loc_140025697
0x140025640  mov     rdx, cs:WPP_GLOBAL_Control
0x140025647  cmp     rdx, rdi
0x14002564a  jz      short loc_140025684
0x14002564c  mov     eax, [rdx+2Ch]
0x14002564f  test    al, 10h
0x140025651  jz      short loc_140025684
0x140025653  cmp     byte ptr [rdx+29h], 2
0x140025657  jb      short loc_140025684
0x140025659  mov     ecx, [r9+23Ch]
0x140025660  mov     r9, r14
0x140025663  mov     eax, ecx
0x140025665  imul    rcx, r13
0x140025669  imul    rax, r12
0x14002566d  mov     [rsp+130h+RetryInterval], rax
0x140025672  mov     [rsp+130h+Status], rcx
0x140025677  mov     rcx, [rdx+18h]
0x14002567b  mov     [rsp+130h+RetryCount], esi
0x14002567f  call    WPP_SF_qDII
0x140025684  mov     qword ptr [rbx+110h], 0
0x14002568f  jmp     loc_140025519
0x140025694  mov     r12, r9
0x140025697  lea     eax, [r15-2]
0x14002569b  mov     [rsp+130h+var_EC], 0
0x1400256a3  cmp     al, 1
0x1400256a5  jbe     short loc_1400256B1
0x1400256a7  cmp     r15b, 60h ; '`'
0x1400256ab  jnz     loc_140025811
0x1400256b1  mov     r15b, [rsp+130h+var_F0]
0x1400256b6  lea     rdx, [rbx+120h]; Srb
0x1400256bd  cmp     byte ptr [rdx+2], 28h ; '('
0x1400256c1  jnz     short loc_140025733
0x1400256c3  cmp     dword ptr [rdx+14h], 0
0x1400256c7  jnz     short loc_140025737
0x1400256c9  xor     r11b, r11b
0x1400256cc  xor     r10d, r10d
0x1400256cf  cmp     [rdx+38h], r10d
0x1400256d3  jbe     short loc_140025737
0x1400256d5  mov     ecx, [rdx+r10*4+78h]
0x1400256da  cmp     ecx, 80h
0x1400256e0  jb      short loc_14002570E
0x1400256e2  mov     r9d, [rdx+10h]
0x1400256e6  cmp     ecx, r9d
0x1400256e9  jnb     short loc_14002570E
0x1400256eb  mov     r8d, ecx
0x1400256ee  mov     ecx, [rcx+rdx]
0x1400256f1  sub     ecx, 40h ; '@'
0x1400256f4  jz      short loc_140025700
0x1400256f6  sub     ecx, 1
0x1400256f9  jz      short loc_140025719
0x1400256fb  cmp     ecx, 1
0x1400256fe  jnz     short loc_140025709
0x140025700  lea     rcx, [r8+28h]
0x140025704  cmp     rcx, r9
0x140025707  jbe     short loc_14002572C
0x140025709  test    r11b, r11b
0x14002570c  jnz     short loc_140025737
0x14002570e  inc     r10d
0x140025711  cmp     r10d, [rdx+38h]
0x140025715  jb      short loc_1400256D5
0x140025717  jmp     short loc_140025737
0x140025719  lea     rcx, [r8+38h]
0x14002571d  cmp     rcx, r9
0x140025720  ja      short loc_140025709
0x140025722  mov     r11b, 1
0x140025725  mov     [r8+rdx+8], r15b
0x14002572a  jmp     short loc_140025709
0x14002572c  mov     [r8+rdx+8], r15b
0x140025731  jmp     short loc_140025737
0x140025733  mov     [rdx+4], r15b
0x140025737  mov     cl, [rsp+130h+var_E8]
0x14002573b  test    cl, cl
0x14002573d  jz      loc_1400257C8
0x140025743  lea     rax, [rbx+1A0h]
0x14002574a  mov     [rdx+0Bh], cl
0x14002574d  mov     [rdx+20h], rax
0x140025751  xor     r9d, r9d; IoDeviceCode
0x140025754  lea     rax, [rbp+57h+var_C8]
0x140025758  mov     [rbp+57h+var_C8], 0
0x14002575f  mov     [rsp+130h+RetryInterval], rax; RetryInterval
0x140025764  mov     r8b, 0Fh; MajorFunctionCode
0x140025767  lea     rax, [rsp+130h+var_EC]
0x14002576c  mov     word ptr [rdx+2], 8400h
0x140025772  mov     [rsp+130h+Status], rax; Status
0x140025777  mov     rcx, r14; DeviceObject
0x14002577a  mov     [rsp+130h+RetryCount], 0; RetryCount
0x140025782  call    ClassInterpretSenseInfo
0x140025787  mov     rcx, cs:WPP_GLOBAL_Control
0x14002578e  cmp     rcx, rdi
0x140025791  jz      short loc_140025811
0x140025793  mov     eax, [rcx+2Ch]
0x140025796  test    al, 10h
0x140025798  jz      short loc_140025811
0x14002579a  cmp     byte ptr [rcx+29h], 3
0x14002579e  jb      short loc_140025811
0x1400257a0  mov     eax, [r12+23Ch]
0x1400257a8  mov     edx, 0F8h
0x1400257ad  mov     rcx, [rcx+18h]
0x1400257b1  imul    rax, r13
0x1400257b5  mov     [rsp+130h+RetryInterval], rax
0x1400257ba  mov     eax, [rsp+130h+var_EC]
0x1400257be  mov     dword ptr [rsp+130h+Status], esi
0x1400257c2  mov     [rsp+130h+RetryCount], eax
0x1400257c6  jmp     short loc_140025809
0x1400257c8  mov     r8, cs:WPP_GLOBAL_Control
0x1400257cf  cmp     r8, rdi
0x1400257d2  jz      short loc_140025811
0x1400257d4  mov     eax, [r8+2Ch]
0x1400257d8  test    al, 10h
0x1400257da  jz      short loc_140025811
0x1400257dc  cmp     byte ptr [r8+29h], 3
0x1400257e1  jb      short loc_140025811
0x1400257e3  mov     eax, [r12+23Ch]
0x1400257eb  mov     edx, 0F9h
0x1400257f0  movzx   ecx, r15b
0x1400257f4  imul    rax, r13
0x1400257f8  mov     [rsp+130h+RetryInterval], rax
0x1400257fd  mov     dword ptr [rsp+130h+Status], esi
0x140025801  mov     [rsp+130h+RetryCount], ecx
0x140025805  mov     rcx, [r8+18h]
0x140025809  mov     r9, r14
0x14002580c  call    WPP_SF_qDDI
  ... truncated ...
```
