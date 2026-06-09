# QosTbcFlowUpdate

- ea: `0x14001554c`
- end: `0x1400158cc`
- name: `QosTbcFlowUpdate`
- size: `896`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140014434`

## callees

- `0x140009368`
- `0x1400097c8`
- `0x1400097f8`
- `0x14000a168`
- `0x1400147b8`
- `0x14001554c`
- `0x140015e90`
- `0x140015f9c`
- `0x140016004`

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
0x14001554c  mov     [rsp-8+arg_0], rbx
0x140015551  mov     [rsp-8+arg_8], rsi
0x140015556  push    rbp
0x140015557  push    rdi
0x140015558  push    r12
0x14001555a  push    r14
0x14001555c  push    r15
0x14001555e  lea     rbp, [rsp-17h]
0x140015563  sub     rsp, 0A0h
0x14001556a  mov     r12d, edx
0x14001556d  mov     [rbp+37h+arg_20], 0
0x140015575  lea     rax, [rbp+37h+var_68]
0x140015579  mov     [rbp+37h+var_70], 0
0x140015581  mov     [rbp+37h+var_60], rax
0x140015585  mov     rdi, r8
0x140015588  lea     rax, [rbp+37h+var_68]
0x14001558c  mov     [rbp+37h+arg_18], 0
0x140015593  mov     [rbp+37h+var_68], rax
0x140015597  mov     rbx, rcx
0x14001559a  xor     eax, eax
0x14001559c  xorps   xmm0, xmm0
0x14001559f  xorps   xmm1, xmm1
0x1400155a2  mov     [rbp+37h+var_48], rax
0x1400155a6  mov     ecx, r12d
0x1400155a9  mov     [rbp+37h+var_30], rax
0x1400155ad  mov     r15, r9
0x1400155b0  lea     esi, [rax+1]
0x1400155b3  mov     r8b, sil
0x1400155b6  mov     dl, sil
0x1400155b9  movups  [rbp+37h+var_58], xmm0
0x1400155bd  movups  [rbp+37h+var_40], xmm1
0x1400155c1  call    QosTimerGetCurrentTime
0x1400155c6  mov     r14, rax
0x1400155c9  test    r15, r15
0x1400155cc  jz      loc_14001568F
0x1400155d2  mov     rdx, [rbx+68h]
0x1400155d6  lea     r10, [rbx+60h]
0x1400155da  cmp     rdx, r10
0x1400155dd  jz      short loc_140015637
0x1400155df  mov     ecx, [r15]
0x1400155e2  cmp     [rdx+10h], ecx
0x1400155e5  jnz     short loc_140015637
0x1400155e7  mov     rax, [rdx]
0x1400155ea  cmp     [rax+8], rdx
0x1400155ee  jnz     loc_140015889
0x1400155f4  lea     r9, [rdx+8]
0x1400155f8  mov     rcx, [r9]
0x1400155fb  cmp     [rcx], rdx
0x1400155fe  jnz     loc_140015889
0x140015604  mov     [rcx], rax
0x140015607  mov     [rax+8], rcx
0x14001560b  lea     rax, [rbp+37h+var_68]
0x14001560f  mov     r8, [rbp+37h+var_68]
0x140015613  cmp     [r8+8], rax
0x140015617  jnz     loc_140015889
0x14001561d  mov     rax, rdx
0x140015620  mov     rdx, rcx
0x140015623  lea     rcx, [rbp+37h+var_68]
0x140015627  mov     [r9], rcx
0x14001562a  mov     [rax], r8
0x14001562d  mov     [r8+8], rax
0x140015631  mov     [rbp+37h+var_68], rax
0x140015635  jmp     short loc_1400155DA
0x140015637  mov     rcx, [rbp+37h+var_68]
0x14001563b  lea     rax, [rbp+37h+var_68]
0x14001563f  cmp     rcx, rax
0x140015642  jz      short loc_14001568F
0x140015644  mov     eax, [rcx+20h]
0x140015647  mov     [rbx+80h], eax
0x14001564d  mov     rax, [rcx+28h]
0x140015651  mov     [rbx+70h], rax
0x140015655  mov     rax, [rcx+30h]
0x140015659  mov     [rbx+78h], rax
0x14001565d  mov     rax, [rcx+38h]
0x140015661  mov     [rbx+88h], rax
0x140015668  mov     rax, [rcx+18h]
0x14001566c  mov     [rbx+0E0h], rax
0x140015673  mov     rax, cs:QosgEtwDispatchTable
0x14001567a  mov     rcx, [rax]
0x14001567d  cmp     [rcx], esi
0x14001567f  jnz     short loc_14001568F
0x140015681  xor     r8d, r8d
0x140015684  mov     rdx, r14
0x140015687  mov     rcx, rbx
0x14001568a  call    QosTraceFlowConformance
0x14001568f  mov     eax, [rdi+24h]
0x140015692  mov     [rbx+58h], eax
0x140015695  mov     rax, [rbx+70h]
0x140015699  cmp     rax, r14
0x14001569c  jnb     short loc_1400156D8
0x14001569e  mov     rdx, r14
0x1400156a1  lea     rcx, [rbx+88h]
0x1400156a8  sub     rdx, rax
0x1400156ab  call    QosUtilComputeTokenSpec
0x1400156b0  mov     ecx, [rcx]
0x1400156b2  mov     rax, cs:QosgEtwDispatchTable
0x1400156b9  mov     [rbx+80h], ecx
0x1400156bf  mov     [rbx+70h], r14
0x1400156c3  mov     rcx, [rax]
0x1400156c6  cmp     [rcx], esi
0x1400156c8  jnz     short loc_1400156D8
0x1400156ca  mov     r8d, esi
0x1400156cd  mov     rdx, r14
0x1400156d0  mov     rcx, rbx
0x1400156d3  call    QosTraceFlowConformance
0x1400156d8  lea     rcx, [rbx+88h]
0x1400156df  mov     rdx, rdi
0x1400156e2  cmp     qword ptr [rcx+8], 0
0x1400156e7  setz    r8b
0x1400156eb  call    QosUtilSetTokenSpec
0x1400156f0  mov     rcx, cs:QosgEtwDispatchTable
0x1400156f7  mov     r15d, 2
0x1400156fd  mov     rax, [rcx]
0x140015700  cmp     [rax], esi
0x140015702  jnz     short loc_140015712
0x140015704  mov     r8d, r15d
0x140015707  mov     rdx, r14
0x14001570a  mov     rcx, rbx
0x14001570d  call    QosTraceFlowConformance
0x140015712  mov     rax, [rdi+10h]
0x140015716  or      r8d, 0FFFFFFFFh
0x14001571a  mov     [rbx+0A0h], rax
0x140015721  xor     eax, eax
0x140015723  mov     ecx, [rdi+20h]
0x140015726  cmp     ecx, r8d
0x140015729  cmovnz  eax, ecx
0x14001572c  mov     [rbx+0A8h], eax
0x140015732  mov     eax, [rbx+58h]
0x140015735  cmp     eax, 3
0x140015738  jz      short loc_140015748
0x14001573a  cmp     qword ptr [rbx+98h], 0FFFFFFFFFFFFFFFFh
0x140015742  jz      short loc_140015748
0x140015744  xor     cl, cl
0x140015746  jmp     short loc_14001574B
0x140015748  mov     cl, sil
0x14001574b  mov     [rbx+5Dh], cl
0x14001574e  cmp     eax, esi
0x140015750  jz      short loc_140015761
0x140015752  cmp     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x140015757  jz      short loc_14001575E
0x140015759  cmp     eax, 3
0x14001575c  jnz     short loc_140015761
0x14001575e  xor     sil, sil
0x140015761  mov     [rbx+5Ch], sil
0x140015765  mov     eax, [rdi+28h]
0x140015768  mov     [rbx+0D4h], eax
0x14001576e  mov     eax, [rdi+2Ch]
0x140015771  mov     [rbx+0D8h], eax
0x140015777  mov     rax, [rdi+18h]
0x14001577b  test    rax, rax
0x14001577e  jz      short loc_140015787
0x140015780  mov     [rbx+0F0h], rax
0x140015787  mov     edx, [rdi+38h]
0x14001578a  cmp     edx, r8d
0x14001578d  jz      short loc_1400157C8
0x14001578f  mov     ecx, [rbx+144h]
0x140015795  mov     eax, edx
0x140015797  cmp     edx, ecx
0x140015799  mov     [rbx+140h], edx
0x14001579f  mov     [rbx+14Ch], r15d
0x1400157a6  cmovbe  eax, ecx
0x1400157a9  mov     rcx, rbx
0x1400157ac  mov     [rbx+144h], eax
0x1400157b2  mov     eax, [rbx+148h]
0x1400157b8  cmp     edx, eax
0x1400157ba  cmovbe  edx, eax
0x1400157bd  mov     [rbx+148h], edx
0x1400157c3  call    QosTbcTuneParameters
0x1400157c8  mov     r10, [rbp+37h+var_68]
0x1400157cc  lea     rax, [rbp+37h+var_68]
0x1400157d0  cmp     r10, rax
0x1400157d3  jz      loc_140015890
0x1400157d9  lea     rax, [rbp+37h+var_68]
0x1400157dd  mov     [rbp+37h+arg_20], 0
0x1400157e5  mov     [rbp+37h+var_70], 0
0x1400157ed  cmp     [r10+8], rax
0x1400157f1  jnz     loc_140015889
0x1400157f7  mov     rax, [r10]
0x1400157fa  cmp     [rax+8], r10
0x1400157fe  jnz     loc_140015889
0x140015804  mov     [rbp+37h+var_68], rax
0x140015808  lea     rcx, [rbp+37h+var_68]
0x14001580c  mov     [rax+8], rcx
0x140015810  lea     rdx, [rbp+37h+arg_18]
0x140015814  mov     r9, [r10-18h]
0x140015818  mov     rcx, r9
0x14001581b  call    QosGetNetBufferCount
0x140015820  mov     r8, [r10-10h]
0x140015824  lea     rcx, [rbp+37h+var_70]
0x140015828  mov     [rsp+0C0h+var_80], rcx
0x14001582d  mov     edx, r12d
0x140015830  lea     rcx, [rbp+37h+arg_20]
0x140015834  mov     [rsp+0C0h+var_88], rcx
0x140015839  mov     ecx, [rbp+37h+arg_18]
0x14001583c  mov     [rsp+0C0h+var_90], 0
0x140015844  mov     [rsp+0C0h+var_98], ecx
0x140015848  mov     rcx, rbx
0x14001584b  mov     [rsp+0C0h+var_A0], eax
0x14001584f  call    QosTbcSendNetBufferList
0x140015854  mov     r8, [rbp+37h+arg_20]
0x140015858  test    r8, r8
0x14001585b  jz      short loc_14001586A
0x14001585d  mov     rdx, qword ptr [rbp+37h+var_58+8]
0x140015861  lea     rcx, [rbp+37h+var_58]
0x140015865  call    QosNblChainInsert
0x14001586a  mov     r8, [rbp+37h+var_70]
0x14001586e  test    r8, r8
0x140015871  jz      loc_1400157C8
0x140015877  mov     rdx, qword ptr [rbp+37h+var_40+8]
0x14001587b  lea     rcx, [rbp+37h+var_40]
0x14001587f  call    QosNblChainInsert
0x140015884  jmp     loc_1400157C8
0x140015889  mov     ecx, 3
0x14001588e  int     29h; Win8: RtlFailFast(ecx)
0x140015890  mov     rcx, [rbp+37h+arg_30]
0x140015894  lea     r11, [rsp+0C0h+var_20]
0x14001589c  mov     rax, qword ptr [rbp+37h+var_58]
0x1400158a0  mov     rbx, [r11+30h]
0x1400158a4  mov     rsi, [r11+38h]
0x1400158a8  mov     [rcx], rax
0x1400158ab  mov     rcx, [rbp+37h+arg_38]
0x1400158af  mov     rax, qword ptr [rbp+37h+var_40]
0x1400158b3  mov     [rcx], rax
0x1400158b6  mov     rcx, [rbp+37h+arg_28]
0x1400158ba  mov     eax, dword ptr [rbp+37h+var_48]
0x1400158bd  mov     [rcx], eax
0x1400158bf  mov     rsp, r11
0x1400158c2  pop     r15
0x1400158c4  pop     r14
0x1400158c6  pop     r12
0x1400158c8  pop     rdi
0x1400158c9  pop     rbp
0x1400158ca  retn
```
