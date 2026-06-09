# QosTbcFlowUpdate

- ea: `0x140004c58`
- end: `0x140004fd8`
- name: `QosTbcFlowUpdate`
- size: `896`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140003ab0`

## callees

- `0x140004c58`
- `0x140004fe0`
- `0x14000516c`
- `0x140007260`
- `0x140007ef0`
- `0x140007f60`
- `0x140009b50`
- `0x14000b404`
- `0x140012ec4`

## pseudocode

```c
__int64 __fastcall QosTbcFlowUpdate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        __int64 a5,
        _DWORD *a6,
        _QWORD *a7,
        _QWORD *a8)
{
  int v8; // r12d
  __int64 v9; // rdi
  __int64 v11; // rcx
  char v13; // si
  __int64 v14; // r8
  unsigned __int64 CurrentTime; // r14
  _QWORD *v16; // rdx
  __int64 v17; // rax
  _QWORD *v18; // r9
  _QWORD *v19; // rcx
  _QWORD *v20; // rax
  _QWORD *v21; // rcx
  unsigned __int64 v22; // rax
  _DWORD *v23; // rcx
  _DWORD **v24; // rax
  int v25; // eax
  int v26; // eax
  bool v27; // cl
  __int64 v28; // rax
  unsigned int v29; // edx
  unsigned int v30; // ecx
  unsigned int v31; // eax
  __int64 v32; // r10
  __int64 v33; // rax
  int NetBufferCount; // eax
  __int64 v35; // r10
  int v36; // r9d
  __int64 result; // rax
  __int64 v38; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v39[2]; // [rsp+58h] [rbp-31h] BYREF
  __int128 v40; // [rsp+68h] [rbp-21h] BYREF
  __int64 v41; // [rsp+78h] [rbp-11h]
  __int128 v42; // [rsp+80h] [rbp-9h] BYREF
  __int64 v43; // [rsp+90h] [rbp+7h]
  int v44; // [rsp+E8h] [rbp+5Fh] BYREF

  v8 = a2;
  a5 = 0;
  v38 = 0;
  v39[1] = v39;
  v9 = a3;
  v44 = 0;
  v39[0] = v39;
  v41 = 0;
  v11 = (unsigned int)a2;
  v43 = 0;
  v13 = 1;
  LOBYTE(a3) = 1;
  LOBYTE(a2) = 1;
  v40 = 0;
  v42 = 0;
  CurrentTime = QosTimerGetCurrentTime(v11, a2, a3);
  if ( a4 )
  {
    v16 = *(_QWORD **)(a1 + 104);
    while ( v16 != (_QWORD *)(a1 + 96) && *((_DWORD *)v16 + 4) == *a4 )
    {
      v17 = *v16;
      if ( *(_QWORD **)(*v16 + 8LL) != v16
        || (v18 = v16 + 1, v19 = (_QWORD *)v16[1], (_QWORD *)*v19 != v16)
        || (*v19 = v17, *(_QWORD *)(v17 + 8) = v19, v14 = v39[0], *(_QWORD **)(v39[0] + 8LL) != v39) )
      {
LABEL_42:
        __fastfail(3u);
      }
      v20 = v16;
      v16 = v19;
      *v18 = v39;
      *v20 = v14;
      *(_QWORD *)(v14 + 8) = v20;
      v39[0] = v20;
    }
    v21 = (_QWORD *)v39[0];
    if ( (_QWORD *)v39[0] != v39 )
    {
      *(_DWORD *)(a1 + 128) = *(_DWORD *)(v39[0] + 32LL);
      *(_QWORD *)(a1 + 112) = v21[5];
      *(_QWORD *)(a1 + 120) = v21[6];
      *(_QWORD *)(a1 + 136) = v21[7];
      *(_QWORD *)(a1 + 224) = v21[3];
      if ( **(_DWORD **)QosgEtwDispatchTable == 1 )
        QosTraceFlowConformance(a1, CurrentTime, 0);
    }
  }
  *(_DWORD *)(a1 + 88) = *(_DWORD *)(v9 + 36);
  v22 = *(_QWORD *)(a1 + 112);
  if ( v22 < CurrentTime )
  {
    QosUtilComputeTokenSpec(a1 + 136, CurrentTime - v22);
    v24 = (_DWORD **)QosgEtwDispatchTable;
    *(_DWORD *)(a1 + 128) = *v23;
    *(_QWORD *)(a1 + 112) = CurrentTime;
    if ( **v24 == 1 )
      QosTraceFlowConformance(a1, CurrentTime, 1);
  }
  LOBYTE(v14) = *(_QWORD *)(a1 + 144) == 0;
  QosUtilSetTokenSpec(a1 + 136, v9, v14);
  if ( **(_DWORD **)QosgEtwDispatchTable == 1 )
    QosTraceFlowConformance(a1, CurrentTime, 2);
  *(_QWORD *)(a1 + 160) = *(_QWORD *)(v9 + 16);
  v25 = 0;
  if ( *(_DWORD *)(v9 + 32) != -1 )
    v25 = *(_DWORD *)(v9 + 32);
  *(_DWORD *)(a1 + 168) = v25;
  v26 = *(_DWORD *)(a1 + 88);
  v27 = v26 == 3 || *(_QWORD *)(a1 + 152) == -1;
  *(_BYTE *)(a1 + 93) = v27;
  if ( v26 != 1 && (*(_QWORD *)(v9 + 16) == -1 || v26 == 3) )
    v13 = 0;
  *(_BYTE *)(a1 + 92) = v13;
  *(_DWORD *)(a1 + 212) = *(_DWORD *)(v9 + 40);
  *(_DWORD *)(a1 + 216) = *(_DWORD *)(v9 + 44);
  v28 = *(_QWORD *)(v9 + 24);
  if ( v28 )
    *(_QWORD *)(a1 + 240) = v28;
  v29 = *(_DWORD *)(v9 + 56);
  if ( v29 != -1 )
  {
    v30 = *(_DWORD *)(a1 + 324);
    v31 = *(_DWORD *)(v9 + 56);
    *(_DWORD *)(a1 + 320) = v29;
    *(_DWORD *)(a1 + 332) = 2;
    if ( v29 <= v30 )
      v31 = v30;
    *(_DWORD *)(a1 + 324) = v31;
    if ( v29 <= *(_DWORD *)(a1 + 328) )
      v29 = *(_DWORD *)(a1 + 328);
    *(_DWORD *)(a1 + 328) = v29;
    QosTbcTuneParameters(a1);
  }
  while ( 1 )
  {
    v32 = v39[0];
    if ( (_QWORD *)v39[0] == v39 )
      break;
    a5 = 0;
    v38 = 0;
    if ( *(_QWORD **)(v39[0] + 8LL) != v39 )
      goto LABEL_42;
    v33 = *(_QWORD *)v39[0];
    if ( *(_QWORD *)(*(_QWORD *)v39[0] + 8LL) != v39[0] )
      goto LABEL_42;
    v39[0] = *(_QWORD *)v39[0];
    *(_QWORD *)(v33 + 8) = v39;
    NetBufferCount = QosGetNetBufferCount(*(_QWORD *)(v32 - 24), &v44);
    QosTbcSendNetBufferList(a1, v8, *(_QWORD *)(v35 - 16), v36, NetBufferCount, v44, 0, (__int64)&a5, (__int64)&v38);
    if ( a5 )
      QosNblChainInsert(&v40, *((_QWORD *)&v40 + 1), a5);
    if ( v38 )
      QosNblChainInsert(&v42, *((_QWORD *)&v42 + 1), v38);
  }
  *a7 = v40;
  *a8 = v42;
  result = (unsigned int)v41;
  *a6 = v41;
  return result;
}

```

## disassembly

```asm
0x140004c58  mov     [rsp-8+arg_0], rbx
0x140004c5d  mov     [rsp-8+arg_8], rsi
0x140004c62  push    rbp
0x140004c63  push    rdi
0x140004c64  push    r12
0x140004c66  push    r14
0x140004c68  push    r15
0x140004c6a  lea     rbp, [rsp-17h]
0x140004c6f  sub     rsp, 0A0h
0x140004c76  mov     r12d, edx
0x140004c79  mov     [rbp+37h+arg_20], 0
0x140004c81  lea     rax, [rbp+37h+var_68]
0x140004c85  mov     [rbp+37h+var_70], 0
0x140004c8d  mov     [rbp+37h+var_60], rax
0x140004c91  mov     rdi, r8
0x140004c94  lea     rax, [rbp+37h+var_68]
0x140004c98  mov     [rbp+37h+arg_18], 0
0x140004c9f  mov     [rbp+37h+var_68], rax
0x140004ca3  mov     rbx, rcx
0x140004ca6  xor     eax, eax
0x140004ca8  xorps   xmm0, xmm0
0x140004cab  xorps   xmm1, xmm1
0x140004cae  mov     [rbp+37h+var_48], rax
0x140004cb2  mov     ecx, r12d
0x140004cb5  mov     [rbp+37h+var_30], rax
0x140004cb9  mov     r15, r9
0x140004cbc  lea     esi, [rax+1]
0x140004cbf  mov     r8b, sil
0x140004cc2  mov     dl, sil
0x140004cc5  movups  [rbp+37h+var_58], xmm0
0x140004cc9  movups  [rbp+37h+var_40], xmm1
0x140004ccd  call    QosTimerGetCurrentTime
0x140004cd2  mov     r14, rax
0x140004cd5  test    r15, r15
0x140004cd8  jz      loc_140004D9B
0x140004cde  mov     rdx, [rbx+68h]
0x140004ce2  lea     r10, [rbx+60h]
0x140004ce6  cmp     rdx, r10
0x140004ce9  jz      short loc_140004D43
0x140004ceb  mov     ecx, [r15]
0x140004cee  cmp     [rdx+10h], ecx
0x140004cf1  jnz     short loc_140004D43
0x140004cf3  mov     rax, [rdx]
0x140004cf6  cmp     [rax+8], rdx
0x140004cfa  jnz     loc_140004F95
0x140004d00  lea     r9, [rdx+8]
0x140004d04  mov     rcx, [r9]
0x140004d07  cmp     [rcx], rdx
0x140004d0a  jnz     loc_140004F95
0x140004d10  mov     [rcx], rax
0x140004d13  mov     [rax+8], rcx
0x140004d17  lea     rax, [rbp+37h+var_68]
0x140004d1b  mov     r8, [rbp+37h+var_68]
0x140004d1f  cmp     [r8+8], rax
0x140004d23  jnz     loc_140004F95
0x140004d29  mov     rax, rdx
0x140004d2c  mov     rdx, rcx
0x140004d2f  lea     rcx, [rbp+37h+var_68]
0x140004d33  mov     [r9], rcx
0x140004d36  mov     [rax], r8
0x140004d39  mov     [r8+8], rax
0x140004d3d  mov     [rbp+37h+var_68], rax
0x140004d41  jmp     short loc_140004CE6
0x140004d43  mov     rcx, [rbp+37h+var_68]
0x140004d47  lea     rax, [rbp+37h+var_68]
0x140004d4b  cmp     rcx, rax
0x140004d4e  jz      short loc_140004D9B
0x140004d50  mov     eax, [rcx+20h]
0x140004d53  mov     [rbx+80h], eax
0x140004d59  mov     rax, [rcx+28h]
0x140004d5d  mov     [rbx+70h], rax
0x140004d61  mov     rax, [rcx+30h]
0x140004d65  mov     [rbx+78h], rax
0x140004d69  mov     rax, [rcx+38h]
0x140004d6d  mov     [rbx+88h], rax
0x140004d74  mov     rax, [rcx+18h]
0x140004d78  mov     [rbx+0E0h], rax
0x140004d7f  mov     rax, cs:QosgEtwDispatchTable
0x140004d86  mov     rcx, [rax]
0x140004d89  cmp     [rcx], esi
0x140004d8b  jnz     short loc_140004D9B
0x140004d8d  xor     r8d, r8d
0x140004d90  mov     rdx, r14
0x140004d93  mov     rcx, rbx
0x140004d96  call    QosTraceFlowConformance
0x140004d9b  mov     eax, [rdi+24h]
0x140004d9e  mov     [rbx+58h], eax
0x140004da1  mov     rax, [rbx+70h]
0x140004da5  cmp     rax, r14
0x140004da8  jnb     short loc_140004DE4
0x140004daa  mov     rdx, r14
0x140004dad  lea     rcx, [rbx+88h]
0x140004db4  sub     rdx, rax
0x140004db7  call    QosUtilComputeTokenSpec
0x140004dbc  mov     ecx, [rcx]
0x140004dbe  mov     rax, cs:QosgEtwDispatchTable
0x140004dc5  mov     [rbx+80h], ecx
0x140004dcb  mov     [rbx+70h], r14
0x140004dcf  mov     rcx, [rax]
0x140004dd2  cmp     [rcx], esi
0x140004dd4  jnz     short loc_140004DE4
0x140004dd6  mov     r8d, esi
0x140004dd9  mov     rdx, r14
0x140004ddc  mov     rcx, rbx
0x140004ddf  call    QosTraceFlowConformance
0x140004de4  lea     rcx, [rbx+88h]
0x140004deb  mov     rdx, rdi
0x140004dee  cmp     qword ptr [rcx+8], 0
0x140004df3  setz    r8b
0x140004df7  call    QosUtilSetTokenSpec
0x140004dfc  mov     rcx, cs:QosgEtwDispatchTable
0x140004e03  mov     r15d, 2
0x140004e09  mov     rax, [rcx]
0x140004e0c  cmp     [rax], esi
0x140004e0e  jnz     short loc_140004E1E
0x140004e10  mov     r8d, r15d
0x140004e13  mov     rdx, r14
0x140004e16  mov     rcx, rbx
0x140004e19  call    QosTraceFlowConformance
0x140004e1e  mov     rax, [rdi+10h]
0x140004e22  or      r8d, 0FFFFFFFFh
0x140004e26  mov     [rbx+0A0h], rax
0x140004e2d  xor     eax, eax
0x140004e2f  mov     ecx, [rdi+20h]
0x140004e32  cmp     ecx, r8d
0x140004e35  cmovnz  eax, ecx
0x140004e38  mov     [rbx+0A8h], eax
0x140004e3e  mov     eax, [rbx+58h]
0x140004e41  cmp     eax, 3
0x140004e44  jz      short loc_140004E54
0x140004e46  cmp     qword ptr [rbx+98h], 0FFFFFFFFFFFFFFFFh
0x140004e4e  jz      short loc_140004E54
0x140004e50  xor     cl, cl
0x140004e52  jmp     short loc_140004E57
0x140004e54  mov     cl, sil
0x140004e57  mov     [rbx+5Dh], cl
0x140004e5a  cmp     eax, esi
0x140004e5c  jz      short loc_140004E6D
0x140004e5e  cmp     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x140004e63  jz      short loc_140004E6A
0x140004e65  cmp     eax, 3
0x140004e68  jnz     short loc_140004E6D
0x140004e6a  xor     sil, sil
0x140004e6d  mov     [rbx+5Ch], sil
0x140004e71  mov     eax, [rdi+28h]
0x140004e74  mov     [rbx+0D4h], eax
0x140004e7a  mov     eax, [rdi+2Ch]
0x140004e7d  mov     [rbx+0D8h], eax
0x140004e83  mov     rax, [rdi+18h]
0x140004e87  test    rax, rax
0x140004e8a  jz      short loc_140004E93
0x140004e8c  mov     [rbx+0F0h], rax
0x140004e93  mov     edx, [rdi+38h]
0x140004e96  cmp     edx, r8d
0x140004e99  jz      short loc_140004ED4
0x140004e9b  mov     ecx, [rbx+144h]
0x140004ea1  mov     eax, edx
0x140004ea3  cmp     edx, ecx
0x140004ea5  mov     [rbx+140h], edx
0x140004eab  mov     [rbx+14Ch], r15d
0x140004eb2  cmovbe  eax, ecx
0x140004eb5  mov     rcx, rbx
0x140004eb8  mov     [rbx+144h], eax
0x140004ebe  mov     eax, [rbx+148h]
0x140004ec4  cmp     edx, eax
0x140004ec6  cmovbe  edx, eax
0x140004ec9  mov     [rbx+148h], edx
0x140004ecf  call    QosTbcTuneParameters
0x140004ed4  mov     r10, [rbp+37h+var_68]
0x140004ed8  lea     rax, [rbp+37h+var_68]
0x140004edc  cmp     r10, rax
0x140004edf  jz      loc_140004F9C
0x140004ee5  lea     rax, [rbp+37h+var_68]
0x140004ee9  mov     [rbp+37h+arg_20], 0
0x140004ef1  mov     [rbp+37h+var_70], 0
0x140004ef9  cmp     [r10+8], rax
0x140004efd  jnz     loc_140004F95
0x140004f03  mov     rax, [r10]
0x140004f06  cmp     [rax+8], r10
0x140004f0a  jnz     loc_140004F95
0x140004f10  mov     [rbp+37h+var_68], rax
0x140004f14  lea     rcx, [rbp+37h+var_68]
0x140004f18  mov     [rax+8], rcx
0x140004f1c  lea     rdx, [rbp+37h+arg_18]
0x140004f20  mov     r9, [r10-18h]
0x140004f24  mov     rcx, r9
0x140004f27  call    QosGetNetBufferCount
0x140004f2c  mov     r8, [r10-10h]
0x140004f30  lea     rcx, [rbp+37h+var_70]
0x140004f34  mov     [rsp+0C0h+var_80], rcx
0x140004f39  mov     edx, r12d
0x140004f3c  lea     rcx, [rbp+37h+arg_20]
0x140004f40  mov     [rsp+0C0h+var_88], rcx
0x140004f45  mov     ecx, [rbp+37h+arg_18]
0x140004f48  mov     [rsp+0C0h+var_90], 0
0x140004f50  mov     [rsp+0C0h+var_98], ecx
0x140004f54  mov     rcx, rbx
0x140004f57  mov     [rsp+0C0h+var_A0], eax
0x140004f5b  call    QosTbcSendNetBufferList
0x140004f60  mov     r8, [rbp+37h+arg_20]
0x140004f64  test    r8, r8
0x140004f67  jz      short loc_140004F76
0x140004f69  mov     rdx, qword ptr [rbp+37h+var_58+8]
0x140004f6d  lea     rcx, [rbp+37h+var_58]
0x140004f71  call    QosNblChainInsert
0x140004f76  mov     r8, [rbp+37h+var_70]
0x140004f7a  test    r8, r8
0x140004f7d  jz      loc_140004ED4
0x140004f83  mov     rdx, qword ptr [rbp+37h+var_40+8]
0x140004f87  lea     rcx, [rbp+37h+var_40]
0x140004f8b  call    QosNblChainInsert
0x140004f90  jmp     loc_140004ED4
0x140004f95  mov     ecx, 3
0x140004f9a  int     29h; Win8: RtlFailFast(ecx)
0x140004f9c  mov     rcx, [rbp+37h+arg_30]
0x140004fa0  lea     r11, [rsp+0C0h+var_20]
0x140004fa8  mov     rax, qword ptr [rbp+37h+var_58]
0x140004fac  mov     rbx, [r11+30h]
0x140004fb0  mov     rsi, [r11+38h]
0x140004fb4  mov     [rcx], rax
0x140004fb7  mov     rcx, [rbp+37h+arg_38]
0x140004fbb  mov     rax, qword ptr [rbp+37h+var_40]
0x140004fbf  mov     [rcx], rax
0x140004fc2  mov     rcx, [rbp+37h+arg_28]
0x140004fc6  mov     eax, dword ptr [rbp+37h+var_48]
0x140004fc9  mov     [rcx], eax
0x140004fcb  mov     rsp, r11
0x140004fce  pop     r15
0x140004fd0  pop     r14
0x140004fd2  pop     r12
0x140004fd4  pop     rdi
0x140004fd5  pop     rbp
0x140004fd6  retn
```
