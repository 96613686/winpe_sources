# MRxSmbFsCtlUserTransact

- ea: `0x14002f968`
- end: `0x14002ff6a`
- name: `MRxSmbFsCtlUserTransact`
- size: `1538`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14002f640`

## callees

- `0x14000a340`
- `0x14000b210`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000f5a4`
- `0x1400169c0`
- `0x14002f968`
- `0x140053c10`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x14002f9f8`
- `ntoskrnl!IoIs32bitProcess` at `0x14002fe86`
- `ntoskrnl!IoIs32bitProcess` at `0x14002f9f8`
- `ntoskrnl!IoIs32bitProcess` at `0x14002fe86`
- `ntoskrnl!ProbeForWrite` at `0x14002fd89`
- `ntoskrnl!ProbeForWrite` at `0x14002fdc0`
- `ntoskrnl!ProbeForWrite` at `0x14002fdf3`
- `ntoskrnl!ProbeForWrite` at `0x14002fd89`
- `ntoskrnl!ProbeForWrite` at `0x14002fdc0`
- `ntoskrnl!ProbeForWrite` at `0x14002fdf3`

## pseudocode

```c
void __fastcall MRxSmbFsCtlUserTransact(__int64 a1)
{
  __int128 *v2; // rax
  unsigned int v3; // edi
  unsigned int v4; // r15d
  int *v5; // rax
  int v6; // r13d
  unsigned int v7; // esi
  unsigned int v8; // r14d
  unsigned int v9; // r12d
  unsigned int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rsi
  int v15; // edx
  int v16; // r8d
  volatile void *v17; // rdi
  __int64 v18; // rax
  int v19; // edi
  BOOLEAN v20; // al
  _DWORD *v21; // rdx
  int v22; // [rsp+80h] [rbp-178h]
  unsigned int v23; // [rsp+84h] [rbp-174h]
  int v24; // [rsp+88h] [rbp-170h]
  int v25; // [rsp+8Ch] [rbp-16Ch]
  int v26; // [rsp+90h] [rbp-168h]
  __int64 v27; // [rsp+98h] [rbp-160h]
  __int64 Address; // [rsp+A0h] [rbp-158h]
  __int64 v29; // [rsp+A8h] [rbp-150h]
  __int128 v30; // [rsp+B0h] [rbp-148h] BYREF
  __int64 v31; // [rsp+C0h] [rbp-138h]
  __int128 v32; // [rsp+C8h] [rbp-130h] BYREF
  __int128 v33; // [rsp+E0h] [rbp-118h]
  __int128 v34; // [rsp+F0h] [rbp-108h]
  __int128 v35; // [rsp+100h] [rbp-F8h]
  __int128 v36; // [rsp+110h] [rbp-E8h]
  __int128 v37; // [rsp+120h] [rbp-D8h]
  __int64 v38; // [rsp+130h] [rbp-C8h]
  __int64 v39; // [rsp+140h] [rbp-B8h]
  volatile void *v40; // [rsp+148h] [rbp-B0h]
  _DWORD v41[42]; // [rsp+150h] [rbp-A8h] BYREF
  char v42; // [rsp+200h] [rbp+8h]
  unsigned int Length; // [rsp+208h] [rbp+10h]
  unsigned int v44; // [rsp+210h] [rbp+18h]
  unsigned int v45; // [rsp+218h] [rbp+20h]

  v32 = 0;
  v2 = *(__int128 **)(a1 + 552);
  if ( v2 )
  {
    v39 = *(_QWORD *)(a1 + 64);
    v3 = *(_DWORD *)(a1 + 568);
    v33 = *v2;
    v34 = v2[1];
    v35 = v2[2];
    v36 = v2[3];
    v37 = v2[4];
    v38 = *((_QWORD *)v2 + 10);
    if ( IoIs32bitProcess(*(PIRP *)(a1 + 40)) )
    {
      v4 = 68;
      if ( v3 < 0x44 )
        return;
      v5 = *(int **)(a1 + 552);
      v6 = *v5;
      v22 = v5[2];
      v7 = v5[3];
      HIDWORD(v33) = v7;
      v23 = v5[4];
      v42 = *((_BYTE *)v5 + 20);
      v24 = v5[6];
      v8 = v5[7];
      HIDWORD(v34) = v8;
      v9 = v5[8];
      Length = v5[9];
      v26 = v5[10];
      Address = v5[11];
      v44 = v5[12];
      v25 = v5[13];
      v29 = v5[14];
      v45 = v5[15];
      v27 = v5[16];
    }
    else
    {
      v4 = 88;
      v27 = v38;
      v45 = DWORD2(v37);
      v29 = v37;
      v25 = HIDWORD(v36);
      v44 = DWORD2(v36);
      Address = v36;
      v26 = DWORD2(v35);
      Length = DWORD1(v35);
      v9 = v35;
      v8 = HIDWORD(v34);
      v24 = DWORD2(v34);
      v42 = BYTE4(v34);
      v23 = v34;
      v7 = HIDWORD(v33);
      v22 = DWORD2(v33);
      v6 = v33;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids);
    if ( v3 >= v4 && v3 - v4 >= v7 && v6 == 3 && v22 == 2 )
    {
      v10 = v7;
      if ( v23 > v7 )
        v10 = v23;
      if ( v7 + v23 >= v10 && v7 + v23 <= v3 )
      {
        v11 = v8;
        if ( v9 > v8 )
          v11 = v9;
        if ( v9 + v8 >= v11 && v9 + v8 <= v3 )
        {
          if ( !v39 )
            goto LABEL_25;
          v12 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL);
          if ( *(_WORD *)v12 != 0xEB12 )
            v12 = *(_QWORD *)(*(_QWORD *)(v39 + 32) + 40LL);
          SmbCeReconnect(*(PVOID *)(v12 + 40));
          if ( !v13 )
          {
LABEL_25:
            WORD1(v32) = WORD6(v33);
            LOWORD(v32) = WORD6(v33);
            v14 = *(_QWORD *)(a1 + 552) + v23;
            *((_QWORD *)&v32 + 1) = v14;
            v30 = RxDefaultTransactionOptions;
            v31 = qword_14001F6B0;
            memset(v41, 0, 0x68u);
            v17 = 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
            {
              WPP_SF_Sl(WPP_GLOBAL_Control->AttachedDevice, v15, v16, v14, SBYTE12(v33));
            }
            LODWORD(v30) = 0x40000000;
            *((_QWORD *)&v30 + 1) = &v32;
            if ( !v42 )
              WORD1(v30) = 16386;
            LODWORD(v31) = v24;
            SmbCeInitializeTransactionResumptionContext(v41);
            if ( v9 )
            {
              v17 = (volatile void *)(*(_QWORD *)(a1 + 552) + v9);
              v40 = v17;
            }
            if ( v17 )
              ProbeForWrite(v17, Length, 1u);
            if ( Address )
              ProbeForWrite((volatile void *)Address, v44, 1u);
            v18 = v27;
            if ( v27 )
            {
              ProbeForWrite((volatile void *)v27, v45, 1u);
              v18 = v27;
            }
            v19 = SmbCeTransact(
                    a1,
                    (unsigned int)&v30,
                    (_DWORD)v17,
                    WORD6(v34),
                    (__int64)v17,
                    Length,
                    Address,
                    v26,
                    Address,
                    v44,
                    v29,
                    v25,
                    v18,
                    v45,
                    (__int64)v41);
            if ( v19 >= 0 )
            {
              v20 = IoIs32bitProcess(*(PIRP *)(a1 + 40));
              v21 = *(_DWORD **)(a1 + 552);
              if ( v20 )
              {
                v21[12] = v41[16];
                v21[15] = v41[15];
              }
              else
              {
                v21[14] = v41[16];
                v21[18] = v41[15];
              }
              v21[9] = v41[14];
              *(_QWORD *)(a1 + 184) = v4 + v21[7];
            }
            if ( v19 < 0
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                24,
                WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids,
                (unsigned int)v19);
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                25,
                WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids,
                (unsigned int)v19);
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14002f968  push    rbx
0x14002f96a  push    rsi
0x14002f96b  push    rdi
0x14002f96c  push    r12
0x14002f96e  push    r13
0x14002f970  push    r14
0x14002f972  push    r15
0x14002f974  sub     rsp, 1C0h
0x14002f97b  mov     rbx, rcx
0x14002f97e  xorps   xmm0, xmm0
0x14002f981  movups  [rsp+1F8h+var_130], xmm0
0x14002f989  mov     rax, [rcx+228h]
0x14002f990  test    rax, rax
0x14002f993  jz      loc_14002FF51
0x14002f999  mov     rcx, [rcx+40h]
0x14002f99d  mov     [rsp+1F8h+var_B8], rcx
0x14002f9a5  mov     edi, [rbx+238h]
0x14002f9ab  movups  xmm0, xmmword ptr [rax]
0x14002f9ae  movaps  [rsp+1F8h+var_118], xmm0
0x14002f9b6  movups  xmm1, xmmword ptr [rax+10h]
0x14002f9ba  movaps  [rsp+1F8h+var_108], xmm1
0x14002f9c2  movups  xmm0, xmmword ptr [rax+20h]
0x14002f9c6  movaps  [rsp+1F8h+var_F8], xmm0
0x14002f9ce  movups  xmm1, xmmword ptr [rax+30h]
0x14002f9d2  movaps  [rsp+1F8h+var_E8], xmm1
0x14002f9da  movups  xmm0, xmmword ptr [rax+40h]
0x14002f9de  movaps  [rsp+1F8h+var_D8], xmm0
0x14002f9e6  movsd   xmm1, qword ptr [rax+50h]
0x14002f9eb  movsd   [rsp+1F8h+var_C8], xmm1
0x14002f9f4  mov     rcx, [rbx+28h]; Irp
0x14002f9f8  call    cs:__imp_IoIs32bitProcess
0x14002f9ff  nop     dword ptr [rax+rax+00h]
0x14002fa04  test    al, al
0x14002fa06  jz      loc_14002FAC6
0x14002fa0c  mov     r15d, 44h ; 'D'
0x14002fa12  cmp     edi, r15d
0x14002fa15  jb      loc_14002FF51
0x14002fa1b  mov     rax, [rbx+228h]
0x14002fa22  mov     r13d, [rax]
0x14002fa25  mov     edx, [rax+8]
0x14002fa28  mov     [rsp+1F8h+var_178], edx
0x14002fa2f  mov     esi, [rax+0Ch]
0x14002fa32  mov     dword ptr [rsp+1F8h+var_118+0Ch], esi
0x14002fa39  mov     ecx, [rax+10h]
0x14002fa3c  mov     [rsp+1F8h+var_174], ecx
0x14002fa43  mov     dl, [rax+14h]
0x14002fa46  mov     [rsp+1F8h+arg_0], dl
0x14002fa4d  mov     edx, [rax+18h]
0x14002fa50  mov     [rsp+1F8h+var_170], edx
0x14002fa57  mov     r14d, [rax+1Ch]
0x14002fa5b  mov     dword ptr [rsp+1F8h+var_108+0Ch], r14d
0x14002fa63  mov     r12d, [rax+20h]
0x14002fa67  mov     edx, [rax+24h]
0x14002fa6a  mov     dword ptr [rsp+1F8h+Length], edx
0x14002fa71  mov     r8d, [rax+28h]
0x14002fa75  mov     [rsp+1F8h+var_168], r8d
0x14002fa7d  movsxd  rcx, dword ptr [rax+2Ch]
0x14002fa81  mov     [rsp+1F8h+Address], rcx
0x14002fa89  mov     edx, [rax+30h]
0x14002fa8c  mov     dword ptr [rsp+1F8h+arg_10], edx
0x14002fa93  mov     r8d, [rax+34h]
0x14002fa97  mov     [rsp+1F8h+var_16C], r8d
0x14002fa9f  movsxd  r8, dword ptr [rax+38h]
0x14002faa3  mov     [rsp+1F8h+var_150], r8
0x14002faab  mov     edx, [rax+3Ch]
0x14002faae  mov     dword ptr [rsp+1F8h+arg_18], edx
0x14002fab5  movsxd  rcx, dword ptr [rax+40h]
0x14002fab9  mov     [rsp+1F8h+var_160], rcx
0x14002fac1  jmp     loc_14002FB99
0x14002fac6  mov     r15d, 58h ; 'X'
0x14002facc  mov     rcx, [rsp+1F8h+var_C8]
0x14002fad4  mov     [rsp+1F8h+var_160], rcx
0x14002fadc  mov     eax, dword ptr [rsp+1F8h+var_D8+8]
0x14002fae3  mov     dword ptr [rsp+1F8h+arg_18], eax
0x14002faea  mov     rax, qword ptr [rsp+1F8h+var_D8]
0x14002faf2  mov     [rsp+1F8h+var_150], rax
0x14002fafa  mov     eax, dword ptr [rsp+1F8h+var_E8+0Ch]
0x14002fb01  mov     [rsp+1F8h+var_16C], eax
0x14002fb08  mov     eax, dword ptr [rsp+1F8h+var_E8+8]
0x14002fb0f  mov     dword ptr [rsp+1F8h+arg_10], eax
0x14002fb16  mov     rcx, qword ptr [rsp+1F8h+var_E8]
0x14002fb1e  mov     [rsp+1F8h+Address], rcx
0x14002fb26  mov     eax, dword ptr [rsp+1F8h+var_F8+8]
0x14002fb2d  mov     [rsp+1F8h+var_168], eax
0x14002fb34  mov     eax, dword ptr [rsp+1F8h+var_F8+4]
0x14002fb3b  mov     dword ptr [rsp+1F8h+Length], eax
0x14002fb42  mov     r12d, dword ptr [rsp+1F8h+var_F8]
0x14002fb4a  mov     r14d, dword ptr [rsp+1F8h+var_108+0Ch]
0x14002fb52  mov     eax, dword ptr [rsp+1F8h+var_108+8]
0x14002fb59  mov     [rsp+1F8h+var_170], eax
0x14002fb60  mov     al, byte ptr [rsp+1F8h+var_108+4]
0x14002fb67  mov     [rsp+1F8h+arg_0], al
0x14002fb6e  mov     ecx, dword ptr [rsp+1F8h+var_108]
0x14002fb75  mov     [rsp+1F8h+var_174], ecx
0x14002fb7c  mov     esi, dword ptr [rsp+1F8h+var_118+0Ch]
0x14002fb83  mov     eax, dword ptr [rsp+1F8h+var_118+8]
0x14002fb8a  mov     [rsp+1F8h+var_178], eax
0x14002fb91  mov     r13d, dword ptr [rsp+1F8h+var_118]
0x14002fb99  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x14002fba0  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fba7  cmp     rcx, rax
0x14002fbaa  jz      short loc_14002FBCA
0x14002fbac  test    dword ptr [rcx+2Ch], 400h
0x14002fbb3  jz      short loc_14002FBCA
0x14002fbb5  mov     edx, 16h
0x14002fbba  lea     r8, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids
0x14002fbc1  mov     rcx, [rcx+18h]
0x14002fbc5  call    WPP_SF_
0x14002fbca  cmp     edi, r15d
0x14002fbcd  jb      loc_14002FF51
0x14002fbd3  mov     eax, edi
0x14002fbd5  sub     eax, r15d
0x14002fbd8  cmp     eax, esi
0x14002fbda  jnb     short loc_14002FBE6
0x14002fbdc  mov     eax, 0C0000023h
0x14002fbe1  jmp     loc_14002FF56
0x14002fbe6  cmp     r13d, 3
0x14002fbea  jnz     loc_14002FF51
0x14002fbf0  cmp     [rsp+1F8h+var_178], 2
0x14002fbf8  jnz     loc_14002FF51
0x14002fbfe  mov     eax, esi
0x14002fc00  mov     r13d, [rsp+1F8h+var_174]
0x14002fc08  cmp     r13d, esi
0x14002fc0b  cmova   eax, r13d
0x14002fc0f  lea     ecx, [rsi+r13]
0x14002fc13  cmp     ecx, eax
0x14002fc15  jb      loc_14002FF51
0x14002fc1b  cmp     ecx, edi
0x14002fc1d  ja      loc_14002FF51
0x14002fc23  mov     eax, r14d
0x14002fc26  cmp     r12d, r14d
0x14002fc29  cmova   eax, r12d
0x14002fc2d  lea     ecx, [r12+r14]
0x14002fc31  cmp     ecx, eax
0x14002fc33  jb      loc_14002FF51
0x14002fc39  cmp     ecx, edi
0x14002fc3b  ja      loc_14002FF51
0x14002fc41  mov     rdx, [rsp+1F8h+var_B8]
0x14002fc49  test    rdx, rdx
0x14002fc4c  jz      short loc_14002FC79
0x14002fc4e  mov     rax, [rbx+48h]
0x14002fc52  mov     rcx, [rax+28h]
0x14002fc56  mov     eax, 0EB12h
0x14002fc5b  cmp     [rcx], ax
0x14002fc5e  jz      short loc_14002FC68
0x14002fc60  mov     rax, [rdx+20h]
0x14002fc64  mov     rcx, [rax+28h]
0x14002fc68  mov     rcx, [rcx+28h]; Context
0x14002fc6c  call    SmbCeReconnect
0x14002fc71  test    eax, eax
0x14002fc73  jnz     loc_14002FF56
0x14002fc79  movzx   r14d, word ptr [rsp+1F8h+var_118+0Ch]
0x14002fc82  mov     word ptr [rsp+1F8h+var_130+2], r14w
0x14002fc8b  mov     word ptr [rsp+1F8h+var_130], r14w
0x14002fc94  mov     rsi, r13
0x14002fc97  add     rsi, [rbx+228h]
0x14002fc9e  mov     qword ptr [rsp+1F8h+var_130+8], rsi
0x14002fca6  movups  xmm0, cs:RxDefaultTransactionOptions
0x14002fcad  movups  [rsp+1F8h+var_148], xmm0
0x14002fcb5  movsd   xmm1, cs:qword_14001F6B0
0x14002fcbd  movsd   [rsp+1F8h+var_138], xmm1
0x14002fcc6  xor     edx, edx; Val
0x14002fcc8  lea     r8d, [rdx+68h]; Size
0x14002fccc  lea     rcx, [rsp+1F8h+var_A8]; void *
0x14002fcd4  call    memset
0x14002fcd9  xor     edi, edi
0x14002fcdb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002fce2  lea     rax, WPP_GLOBAL_Control
0x14002fce9  mov     r13d, 400h
0x14002fcef  cmp     rcx, rax
0x14002fcf2  jz      short loc_14002FD0B
0x14002fcf4  test    [rcx+2Ch], r13d
0x14002fcf8  jz      short loc_14002FD0B
0x14002fcfa  mov     dword ptr [rsp+1F8h+var_1D8], r14d
0x14002fcff  mov     r9, rsi
0x14002fd02  mov     rcx, [rcx+18h]
0x14002fd06  call    WPP_SF_Sl
0x14002fd0b  mov     dword ptr [rsp+1F8h+var_148], 40000000h
0x14002fd16  lea     rax, [rsp+1F8h+var_130]
0x14002fd1e  mov     qword ptr [rsp+1F8h+var_148+8], rax
0x14002fd26  cmp     [rsp+1F8h+arg_0], dil
0x14002fd2e  jnz     short loc_14002FD3D
0x14002fd30  mov     eax, 4002h
0x14002fd35  mov     word ptr [rsp+1F8h+var_148+2], ax
0x14002fd3d  mov     eax, [rsp+1F8h+var_170]
0x14002fd44  mov     dword ptr [rsp+1F8h+var_138], eax
0x14002fd4b  lea     rcx, [rsp+1F8h+var_A8]
0x14002fd53  call    SmbCeInitializeTransactionResumptionContext
0x14002fd58  nop
0x14002fd59  test    r12d, r12d
0x14002fd5c  jz      short loc_14002FD70
0x14002fd5e  mov     edi, r12d
0x14002fd61  add     rdi, [rbx+228h]
0x14002fd68  mov     [rsp+1F8h+var_B0], rdi
0x14002fd70  test    rdi, rdi
0x14002fd73  jz      short loc_14002FD97
0x14002fd75  mov     r14d, dword ptr [rsp+1F8h+Length]
0x14002fd7d  mov     edx, r14d; Length
0x14002fd80  mov     r8d, 1; Alignment
0x14002fd86  mov     rcx, rdi; Address
0x14002fd89  call    cs:__imp_ProbeForWrite
0x14002fd90  nop     dword ptr [rax+rax+00h]
0x14002fd95  jmp     short loc_14002FD9F
0x14002fd97  mov     r14d, dword ptr [rsp+1F8h+Length]
0x14002fd9f  mov     rsi, [rsp+1F8h+Address]
0x14002fda7  test    rsi, rsi
0x14002fdaa  jz      short loc_14002FDCE
0x14002fdac  mov     r12d, dword ptr [rsp+1F8h+arg_10]
0x14002fdb4  mov     edx, r12d; Length
0x14002fdb7  mov     r8d, 1; Alignment
0x14002fdbd  mov     rcx, rsi; Address
0x14002fdc0  call    cs:__imp_ProbeForWrite
0x14002fdc7  nop     dword ptr [rax+rax+00h]
0x14002fdcc  jmp     short loc_14002FDD6
0x14002fdce  mov     r12d, dword ptr [rsp+1F8h+arg_10]
0x14002fdd6  mov     rax, [rsp+1F8h+var_160]
0x14002fdde  test    rax, rax
0x14002fde1  jz      short loc_14002FE07
0x14002fde3  mov     edx, dword ptr [rsp+1F8h+arg_18]; Length
0x14002fdea  mov     r8d, 1; Alignment
0x14002fdf0  mov     rcx, rax; Address
0x14002fdf3  call    cs:__imp_ProbeForWrite
0x14002fdfa  nop     dword ptr [rax+rax+00h]
0x14002fdff  mov     rax, [rsp+1F8h+var_160]
0x14002fe07  movzx   r9d, word ptr [rsp+1F8h+var_108+0Ch]
0x14002fe10  lea     rcx, [rsp+1F8h+var_A8]
0x14002fe18  mov     [rsp+1F8h+var_188], rcx
0x14002fe1d  mov     ecx, dword ptr [rsp+1F8h+arg_18]
0x14002fe24  mov     [rsp+1F8h+var_190], ecx
0x14002fe28  mov     [rsp+1F8h+var_198], rax
0x14002fe2d  mov     eax, [rsp+1F8h+var_16C]
0x14002fe34  mov     [rsp+1F8h+var_1A0], eax
0x14002fe38  mov     rax, [rsp+1F8h+var_150]
0x14002fe40  mov     [rsp+1F8h+var_1A8], rax
0x14002fe45  mov     [rsp+1F8h+var_1B0], r12d
0x14002fe4a  mov     [rsp+1F8h+var_1B8], rsi
0x14002fe4f  mov     eax, [rsp+1F8h+var_168]
0x14002fe56  mov     [rsp+1F8h+var_1C0], eax
0x14002fe5a  mov     [rsp+1F8h+var_1C8], rsi
0x14002fe5f  mov     [rsp+1F8h+var_1D0], r14d
0x14002fe64  mov     [rsp+1F8h+var_1D8], rdi
0x14002fe69  mov     r8, rdi
0x14002fe6c  lea     rdx, [rsp+1F8h+var_148]
0x14002fe74  mov     rcx, rbx
0x14002fe77  call    SmbCeTransact
0x14002fe7c  mov     edi, eax
0x14002fe7e  test    eax, eax
0x14002fe80  js      short loc_14002FEDE
0x14002fe82  mov     rcx, [rbx+28h]; Irp
0x14002fe86  call    cs:__imp_IoIs32bitProcess
0x14002fe8d  nop     dword ptr [rax+rax+00h]
0x14002fe92  mov     rdx, [rbx+228h]
0x14002fe99  test    al, al
0x14002fe9b  jz      short loc_14002FEB3
0x14002fe9d  mov     ecx, [rsp+1F8h+var_68]
0x14002fea4  mov     [rdx+30h], ecx
0x14002fea7  mov     eax, [rsp+1F8h+var_6C]
0x14002feae  mov     [rdx+3Ch], eax
0x14002feb1  jmp     short loc_14002FEC7
0x14002feb3  mov     eax, [rsp+1F8h+var_68]
0x14002feba  mov     [rdx+38h], eax
0x14002febd  mov     eax, [rsp+1F8h+var_6C]
0x14002fec4  mov     [rdx+48h], eax
0x14002fec7  mov     eax, [rsp+1F8h+var_70]
0x14002fece  mov     [rdx+24h], eax
0x14002fed1  mov     eax, [rdx+1Ch]
0x14002fed4  add     eax, r15d
0x14002fed7  mov     [rbx+0B8h], rax
0x14002fede  test    edi, edi
0x14002fee0  jns     short loc_14002FF15
0x14002fee2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002fee9  lea     rbx, WPP_GLOBAL_Control
0x14002fef0  cmp     rcx, rbx
0x14002fef3  jz      short loc_14002FF1C
0x14002fef5  test    [rcx+2Ch], r13d
0x14002fef9  jz      short loc_14002FF1C
0x14002fefb  mov     edx, 18h
0x14002ff00  mov     r9d, edi
0x14002ff03  lea     r8, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids
0x14002ff0a  mov     rcx, [rcx+18h]
0x14002ff0e  call    WPP_SF_d
0x14002ff13  jmp     short loc_14002FF1C
0x14002ff15  lea     rbx, WPP_GLOBAL_Control
0x14002ff1c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002ff23  cmp     rcx, rbx
0x14002ff26  jz      short loc_14002FF46
0x14002ff28  test    [rcx+2Ch], r13d
0x14002ff2c  jz      short loc_14002FF46
0x14002ff2e  mov     edx, 19h
0x14002ff33  mov     r9d, edi
0x14002ff36  lea     r8, WPP_55e04b1f402d3c12c0337189f1358c73_Traceguids
0x14002ff3d  mov     rcx, [rcx+18h]
0x14002ff41  call    WPP_SF_d
0x14002ff46  mov     eax, edi
0x14002ff48  jmp     short loc_14002FF56
0x14002ff4a  mov     eax, 0C000000Dh
0x14002ff4f  jmp     short loc_14002FF56
0x14002ff51  mov     eax, 0C000000Dh
0x14002ff56  add     rsp, 1C0h
0x14002ff5d  pop     r15
  ... truncated ...
```
