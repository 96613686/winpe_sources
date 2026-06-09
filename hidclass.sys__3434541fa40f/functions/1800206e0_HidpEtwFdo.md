# HidpEtwFdo

- ea: `0x1800206e0`
- end: `0x180020c4b`
- name: `HidpEtwFdo`
- size: `1387`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b81c`
- `0x180023b44`

## callees

- `0x180014e80`
- `0x1800206e0`
- `0x180027ba0`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x18002090f`
- `ntoskrnl!EtwWrite` at `0x180020bf3`
- `ntoskrnl!EtwWrite` at `0x180020bf3`
- `ntoskrnl!ExFreePoolWithTag` at `0x180020c14`
- `ntoskrnl!ExFreePoolWithTag` at `0x180020c14`
- `ntoskrnl!ExAllocatePool2` at `0x18002074c`
- `ntoskrnl!ExAllocatePool2` at `0x18002074c`

## pseudocode

```c
void __fastcall HidpEtwFdo(__int64 a1, const GUID *a2, char a3)
{
  unsigned int v4; // edx
  int v7; // esi
  int v8; // edx
  char *Pool2; // rdi
  int v10; // r8d
  bool v11; // r10
  int v12; // ecx
  int *v13; // rax
  int v14; // r9d
  int *v15; // rax
  int v16; // r9d
  int *v17; // rax
  int v18; // r9d
  int *v19; // rax
  int v20; // r9d
  int *v21; // rax
  PVOID v22; // rcx
  int *v23; // r9
  int v24; // eax
  __int64 v25; // rax
  int v26; // ecx
  unsigned int v27; // r9d
  __int64 v28; // rdx
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rcx
  char *v34; // rax
  unsigned int v35; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+64h] [rbp-9Ch] BYREF
  int v37; // [rsp+68h] [rbp-98h] BYREF
  int v38; // [rsp+6Ch] [rbp-94h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+70h] [rbp-90h] BYREF
  __int64 v40; // [rsp+80h] [rbp-80h]
  __int64 v41; // [rsp+88h] [rbp-78h]
  __int64 v42; // [rsp+90h] [rbp-70h]
  __int64 v43; // [rsp+98h] [rbp-68h]
  __int64 v44; // [rsp+A0h] [rbp-60h]
  __int64 v45; // [rsp+A8h] [rbp-58h]
  int *v46; // [rsp+B0h] [rbp-50h]
  int v47; // [rsp+B8h] [rbp-48h]
  int v48; // [rsp+BCh] [rbp-44h]
  int *v49; // [rsp+C0h] [rbp-40h]
  int v50; // [rsp+C8h] [rbp-38h]
  int v51; // [rsp+CCh] [rbp-34h]
  int *v52; // [rsp+D0h] [rbp-30h]
  int v53; // [rsp+D8h] [rbp-28h]
  int v54; // [rsp+DCh] [rbp-24h]
  int *v55; // [rsp+E0h] [rbp-20h]
  int v56; // [rsp+E8h] [rbp-18h]
  int v57; // [rsp+ECh] [rbp-14h]
  int *v58; // [rsp+F0h] [rbp-10h]
  int v59; // [rsp+F8h] [rbp-8h]
  int v60; // [rsp+FCh] [rbp-4h]
  unsigned int *v61; // [rsp+100h] [rbp+0h]
  __int64 v62; // [rsp+108h] [rbp+8h]
  int *v63; // [rsp+110h] [rbp+10h]
  __int64 v64; // [rsp+118h] [rbp+18h]
  void *v65; // [rsp+120h] [rbp+20h]
  int v66; // [rsp+128h] [rbp+28h]
  int v67; // [rsp+12Ch] [rbp+2Ch]
  __int64 v68; // [rsp+130h] [rbp+30h]
  __int64 v69; // [rsp+138h] [rbp+38h]
  int *v70; // [rsp+140h] [rbp+40h]
  __int64 v71; // [rsp+148h] [rbp+48h]
  int *v72; // [rsp+150h] [rbp+50h]
  __int64 v73; // [rsp+158h] [rbp+58h]
  __int64 v74; // [rsp+160h] [rbp+60h]
  __int64 v75; // [rsp+168h] [rbp+68h]
  __int64 v76; // [rsp+170h] [rbp+70h]
  __int64 v77; // [rsp+178h] [rbp+78h]
  __int64 v78; // [rsp+180h] [rbp+80h]
  __int64 v79; // [rsp+188h] [rbp+88h]
  __int64 v80; // [rsp+190h] [rbp+90h]
  __int64 v81; // [rsp+198h] [rbp+98h]
  __int64 v82; // [rsp+1A0h] [rbp+A0h]
  __int64 v83; // [rsp+1A8h] [rbp+A8h]
  __int64 v84; // [rsp+1B0h] [rbp+B0h]
  __int64 v85; // [rsp+1B8h] [rbp+B8h]
  char *v86; // [rsp+1C0h] [rbp+C0h]
  int v87; // [rsp+1C8h] [rbp+C8h]
  int v88; // [rsp+1CCh] [rbp+CCh]

  v4 = *(_DWORD *)(a1 + 168);
  v38 = 0;
  v37 = 0;
  v36 = 0;
  v35 = v4;
  if ( v4 )
  {
    v7 = 68 * v4;
    Pool2 = (char *)ExAllocatePool2(64, 68 * v4, 1130654024);
    if ( !Pool2 )
    {
      v11 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v10 = 4;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          v11 = 1;
      }
      if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = v11;
        LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qLL(
          WPP_GLOBAL_Control->AttachedDevice,
          v8,
          v10,
          *(_QWORD *)(a1 + 680),
          2,
          3,
          76,
          (__int64)WPP_c0d00459c274326499e63e8337aee7d7_Traceguids,
          *(_QWORD *)a1,
          v35,
          v7);
      }
      return;
    }
    v4 = v35;
  }
  else
  {
    Pool2 = 0;
    v7 = 0;
  }
  v12 = 2;
  *(_QWORD *)&UserData.Size = 4;
  v41 = 2;
  UserData.Ptr = a1 + 1856;
  v43 = 2;
  v40 = a1 + 108;
  v42 = a1 + 110;
  v44 = a1 + 112;
  v13 = *(int **)(a1 + 16);
  v45 = 2;
  if ( v13 )
  {
    v14 = *(_DWORD *)(a1 + 24);
  }
  else
  {
    v13 = &dword_18002B11C;
    v14 = 2;
  }
  v46 = v13;
  v15 = *(int **)(a1 + 32);
  v47 = v14;
  v48 = 0;
  if ( v15 )
  {
    v16 = *(_DWORD *)(a1 + 40);
  }
  else
  {
    v15 = &dword_18002B11C;
    v16 = 2;
  }
  v49 = v15;
  v17 = *(int **)(a1 + 48);
  v50 = v16;
  v51 = 0;
  if ( v17 )
  {
    v18 = *(_DWORD *)(a1 + 56);
  }
  else
  {
    v17 = &dword_18002B11C;
    v18 = 2;
  }
  v52 = v17;
  v19 = *(int **)(a1 + 64);
  v53 = v18;
  v54 = 0;
  if ( v19 )
  {
    v20 = *(_DWORD *)(a1 + 72);
  }
  else
  {
    v19 = &dword_18002B11C;
    v20 = 2;
  }
  v55 = v19;
  v21 = *(int **)(a1 + 80);
  v56 = v20;
  v57 = 0;
  if ( v21 )
    v12 = *(_DWORD *)(a1 + 88);
  else
    v21 = &dword_18002B11C;
  v59 = v12;
  v22 = *(PVOID *)(a1 + 136);
  v58 = v21;
  v60 = 0;
  v61 = &v35;
  v62 = 4;
  if ( !v22 || v22 == MmBadPointer || (v23 = (int *)(a1 + 144), (v24 = *(_DWORD *)(a1 + 144)) == 0) )
  {
    v24 = 0;
    v23 = &v38;
    v22 = 0;
  }
  v66 = v24;
  v68 = a1 + 364;
  v25 = *(unsigned int *)(a1 + 1584);
  v63 = v23;
  v64 = 4;
  v65 = v22;
  v67 = 0;
  v69 = 4;
  v26 = *(_DWORD *)(a1 + 4 * v25 + 1556);
  v70 = &v36;
  v37 = *(_DWORD *)(a1 + 248);
  v72 = &v37;
  v74 = a1 + 2104;
  v76 = a1 + 2064;
  v78 = a1 + 2072;
  v80 = a1 + 2080;
  v82 = a1 + 2088;
  v36 = v26;
  v71 = 4;
  v73 = 4;
  v75 = 8;
  v77 = 8;
  v79 = 8;
  v81 = 8;
  v83 = 8;
  v84 = a1 + 2096;
  v85 = 8;
  if ( v4 )
  {
    v27 = 0;
    if ( a3 )
    {
      do
      {
        v31 = *(_QWORD *)(a1 + 152);
        v32 = v27++;
        v33 = 68 * v32;
        *(_DWORD *)&Pool2[v33] = *(_DWORD *)(424 * v32 + v31);
        *(_WORD *)&Pool2[v33 + 4] = *(_WORD *)(424 * v32 + v31 + 8);
        *(_WORD *)&Pool2[v33 + 6] = *(_WORD *)(424 * v32 + v31 + 10);
        *(_DWORD *)&Pool2[v33 + 8] = *(_DWORD *)(424 * v32 + v31 + 352);
        *(_QWORD *)&Pool2[v33 + 12] = *(_QWORD *)(424 * v32 + v31 + 360);
        *(_QWORD *)&Pool2[v33 + 20] = *(_QWORD *)(424 * v32 + v31 + 376);
        *(_QWORD *)&Pool2[v33 + 28] = *(_QWORD *)(424 * v32 + v31 + 384);
        *(_QWORD *)&Pool2[v33 + 36] = *(_QWORD *)(424 * v32 + v31 + 392);
        *(_QWORD *)&Pool2[v33 + 44] = *(_QWORD *)(424 * v32 + v31 + 400);
        *(_QWORD *)&Pool2[v33 + 52] = *(_QWORD *)(424 * v32 + v31 + 408);
        *(_QWORD *)&Pool2[v33 + 60] = *(_QWORD *)(424 * v32 + v31 + 416);
        _InterlockedExchange64((volatile __int64 *)(424 * v32 + v31 + 416), 0);
      }
      while ( v27 < v35 );
    }
    else
    {
      do
      {
        v28 = *(_QWORD *)(a1 + 152);
        v29 = v27++;
        v30 = 68 * v29;
        *(_DWORD *)&Pool2[v30] = *(_DWORD *)(424 * v29 + v28);
        *(_WORD *)&Pool2[v30 + 4] = *(_WORD *)(424 * v29 + v28 + 8);
        *(_WORD *)&Pool2[v30 + 6] = *(_WORD *)(424 * v29 + v28 + 10);
        *(_DWORD *)&Pool2[v30 + 8] = *(_DWORD *)(424 * v29 + v28 + 352);
        *(_QWORD *)&Pool2[v30 + 12] = *(_QWORD *)(424 * v29 + v28 + 360);
        *(_QWORD *)&Pool2[v30 + 20] = *(_QWORD *)(424 * v29 + v28 + 376);
        *(_QWORD *)&Pool2[v30 + 28] = *(_QWORD *)(424 * v29 + v28 + 384);
        *(_QWORD *)&Pool2[v30 + 36] = *(_QWORD *)(424 * v29 + v28 + 392);
        *(_QWORD *)&Pool2[v30 + 44] = *(_QWORD *)(424 * v29 + v28 + 400);
        *(_QWORD *)&Pool2[v30 + 52] = *(_QWORD *)(424 * v29 + v28 + 408);
        *(_QWORD *)&Pool2[v30 + 60] = *(_QWORD *)(424 * v29 + v28 + 416);
      }
      while ( v27 < v35 );
    }
    v34 = Pool2;
  }
  else
  {
    v7 = 0;
    v34 = 0;
  }
  v86 = v34;
  v87 = v7;
  v88 = 0;
  EtwWrite(MS_HIDCLASS_ETW_PROVIDER_Context, &HIDCLASS_ETW_EVENT_DEVICE_INFORMATION_V2, a2, 0x16u, &UserData);
  if ( a3 )
    _InterlockedExchange64((volatile __int64 *)(a1 + 2096), 0);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
}

```

## disassembly

```asm
0x1800206e0  mov     [rsp-8+arg_10], rbx
0x1800206e5  push    rbp
0x1800206e6  push    rsi
0x1800206e7  push    rdi
0x1800206e8  push    r12
0x1800206ea  push    r13
0x1800206ec  push    r14
0x1800206ee  push    r15
0x1800206f0  lea     rbp, [rsp-0E0h]
0x1800206f8  sub     rsp, 1E0h
0x1800206ff  mov     rax, cs:__security_cookie
0x180020706  xor     rax, rsp
0x180020709  mov     [rbp+110h+var_40], rax
0x180020710  xor     r13d, r13d
0x180020713  mov     r12, rdx
0x180020716  mov     edx, [rcx+0A8h]
0x18002071c  mov     r15b, r8b
0x18002071f  mov     [rsp+210h+var_1A4], r13d
0x180020724  mov     rbx, rcx
0x180020727  mov     [rsp+210h+var_1A8], r13d
0x18002072c  mov     [rsp+210h+var_1AC], r13d
0x180020731  mov     [rsp+210h+var_1B0], edx
0x180020735  test    edx, edx
0x180020737  jz      loc_180020807
0x18002073d  imul    esi, edx, 44h ; 'D'
0x180020740  lea     ecx, [r13+40h]
0x180020744  mov     r8d, 43646948h
0x18002074a  mov     edx, esi
0x18002074c  call    cs:__imp_ExAllocatePool2
0x180020753  nop     dword ptr [rax+rax+00h]
0x180020758  mov     rdi, rax
0x18002075b  test    rax, rax
0x18002075e  jnz     loc_180020801
0x180020764  mov     r11, cs:WPP_GLOBAL_Control
0x18002076b  lea     rax, WPP_GLOBAL_Control
0x180020772  lea     ecx, [rdi+2]
0x180020775  cmp     r11, rax
0x180020778  jz      short loc_180020793
0x18002077a  mov     eax, [r11+2Ch]
0x18002077e  lea     r8d, [r13+4]
0x180020782  test    r8b, al
0x180020785  jz      short loc_180020793
0x180020787  cmp     [r11+29h], cl
0x18002078b  jb      short loc_180020793
0x18002078d  lea     r10d, [r13+1]
0x180020791  jmp     short loc_180020796
0x180020793  mov     r10b, r13b
0x180020796  lea     rax, WPP_RECORDER_INITIALIZED
0x18002079d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800207a4  setnz   r8b
0x1800207a8  test    r10b, r10b
0x1800207ab  jnz     short loc_1800207B6
0x1800207ad  test    r8b, r8b
0x1800207b0  jz      loc_180020C20
0x1800207b6  mov     eax, [rsp+210h+var_1B0]
0x1800207ba  mov     dl, r10b
0x1800207bd  mov     r9, [rbx+2A8h]
0x1800207c4  mov     [rsp+210h+var_1C0], esi
0x1800207c8  mov     [rsp+210h+var_1C8], eax
0x1800207cc  mov     rax, [rbx]
0x1800207cf  mov     [rsp+210h+var_1D0], rax
0x1800207d4  lea     rax, WPP_c0d00459c274326499e63e8337aee7d7_Traceguids
0x1800207db  mov     [rsp+210h+var_1D8], rax
0x1800207e0  mov     [rsp+210h+var_1E0], 4Ch ; 'L'
0x1800207e7  mov     [rsp+210h+var_1E8], 3
0x1800207ef  mov     byte ptr [rsp+210h+UserData], cl
0x1800207f3  mov     rcx, [r11+18h]
0x1800207f7  call    WPP_RECORDER_AND_TRACE_SF_qLL
0x1800207fc  jmp     loc_180020C20
0x180020801  mov     edx, [rsp+210h+var_1B0]
0x180020805  jmp     short loc_18002080D
0x180020807  mov     rdi, r13
0x18002080a  mov     esi, r13d
0x18002080d  mov     ecx, 2
0x180020812  mov     qword ptr [rsp+210h+var_1A0.Size], 4
0x18002081b  lea     rax, [rbx+740h]
0x180020822  mov     [rbp+110h+var_188], rcx
0x180020826  mov     [rsp+210h+var_1A0.Ptr], rax
0x18002082b  lea     r10, dword_18002B11C
0x180020832  lea     rax, [rbx+6Ch]
0x180020836  mov     [rbp+110h+var_178], rcx
0x18002083a  mov     [rbp+110h+var_190], rax
0x18002083e  lea     rax, [rbx+6Eh]
0x180020842  mov     [rbp+110h+var_180], rax
0x180020846  lea     rax, [rbx+70h]
0x18002084a  mov     [rbp+110h+var_170], rax
0x18002084e  mov     rax, [rbx+10h]
0x180020852  mov     [rbp+110h+var_168], rcx
0x180020856  test    rax, rax
0x180020859  jz      short loc_180020861
0x18002085b  mov     r9d, [rbx+18h]
0x18002085f  jmp     short loc_180020867
0x180020861  mov     rax, r10
0x180020864  mov     r9d, ecx
0x180020867  mov     [rbp+110h+var_160], rax
0x18002086b  mov     rax, [rbx+20h]
0x18002086f  mov     [rbp+110h+var_158], r9d
0x180020873  mov     [rbp+110h+var_154], r13d
0x180020877  test    rax, rax
0x18002087a  jz      short loc_180020882
0x18002087c  mov     r9d, [rbx+28h]
0x180020880  jmp     short loc_180020888
0x180020882  mov     rax, r10
0x180020885  mov     r9d, ecx
0x180020888  mov     [rbp+110h+var_150], rax
0x18002088c  mov     rax, [rbx+30h]
0x180020890  mov     [rbp+110h+var_148], r9d
0x180020894  mov     [rbp+110h+var_144], r13d
0x180020898  test    rax, rax
0x18002089b  jz      short loc_1800208A3
0x18002089d  mov     r9d, [rbx+38h]
0x1800208a1  jmp     short loc_1800208A9
0x1800208a3  mov     rax, r10
0x1800208a6  mov     r9d, ecx
0x1800208a9  mov     [rbp+110h+var_140], rax
0x1800208ad  mov     rax, [rbx+40h]
0x1800208b1  mov     [rbp+110h+var_138], r9d
0x1800208b5  mov     [rbp+110h+var_134], r13d
0x1800208b9  test    rax, rax
0x1800208bc  jz      short loc_1800208C4
0x1800208be  mov     r9d, [rbx+48h]
0x1800208c2  jmp     short loc_1800208CA
0x1800208c4  mov     rax, r10
0x1800208c7  mov     r9d, ecx
0x1800208ca  mov     [rbp+110h+var_130], rax
0x1800208ce  mov     rax, [rbx+50h]
0x1800208d2  mov     [rbp+110h+var_128], r9d
0x1800208d6  mov     [rbp+110h+var_124], r13d
0x1800208da  test    rax, rax
0x1800208dd  jz      short loc_1800208E4
0x1800208df  mov     ecx, [rbx+58h]
0x1800208e2  jmp     short loc_1800208E7
0x1800208e4  mov     rax, r10
0x1800208e7  mov     [rbp+110h+var_118], ecx
0x1800208ea  mov     rcx, [rbx+88h]
0x1800208f1  mov     [rbp+110h+var_120], rax
0x1800208f5  lea     rax, [rsp+210h+var_1B0]
0x1800208fa  mov     [rbp+110h+var_114], r13d
0x1800208fe  mov     [rbp+110h+var_110], rax
0x180020902  mov     [rbp+110h+var_108], 4
0x18002090a  test    rcx, rcx
0x18002090d  jz      short loc_180020929
0x18002090f  mov     rax, cs:MmBadPointer
0x180020916  cmp     rcx, [rax]
0x180020919  jz      short loc_180020929
0x18002091b  lea     r9, [rbx+90h]
0x180020922  mov     eax, [r9]
0x180020925  test    eax, eax
0x180020927  jnz     short loc_180020934
0x180020929  mov     eax, r13d
0x18002092c  lea     r9, [rsp+210h+var_1A4]
0x180020931  mov     rcx, r13
0x180020934  mov     [rbp+110h+var_E8], eax
0x180020937  lea     rax, [rbx+16Ch]
0x18002093e  mov     [rbp+110h+var_E0], rax
0x180020942  lea     r14, [rbx+830h]
0x180020949  mov     eax, [rbx+630h]
0x18002094f  mov     [rbp+110h+var_100], r9
0x180020953  mov     [rbp+110h+var_F8], 4
0x18002095b  mov     [rbp+110h+var_F0], rcx
0x18002095f  mov     [rbp+110h+var_E4], r13d
0x180020963  mov     [rbp+110h+var_D8], 4
0x18002096b  mov     ecx, [rbx+rax*4+614h]
0x180020972  lea     rax, [rsp+210h+var_1AC]
0x180020977  mov     [rbp+110h+var_D0], rax
0x18002097b  mov     eax, [rbx+0F8h]
0x180020981  mov     [rsp+210h+var_1A8], eax
0x180020985  lea     rax, [rsp+210h+var_1A8]
0x18002098a  mov     [rbp+110h+var_C0], rax
0x18002098e  lea     rax, [rbx+838h]
0x180020995  mov     [rbp+110h+var_B0], rax
0x180020999  lea     rax, [rbx+810h]
0x1800209a0  mov     [rbp+110h+var_A0], rax
0x1800209a4  lea     rax, [rbx+818h]
0x1800209ab  mov     [rbp+110h+var_90], rax
0x1800209b2  lea     rax, [rbx+820h]
0x1800209b9  mov     [rbp+110h+var_80], rax
0x1800209c0  lea     rax, [rbx+828h]
0x1800209c7  mov     [rbp+110h+var_70], rax
0x1800209ce  mov     [rsp+210h+var_1AC], ecx
0x1800209d2  mov     [rbp+110h+var_C8], 4
0x1800209da  mov     [rbp+110h+var_B8], 4
0x1800209e2  mov     [rbp+110h+var_A8], 8
0x1800209ea  mov     [rbp+110h+var_98], 8
0x1800209f2  mov     [rbp+110h+var_88], 8
0x1800209fd  mov     [rbp+110h+var_78], 8
0x180020a08  mov     [rbp+110h+var_68], 8
0x180020a13  mov     [rbp+110h+var_60], r14
0x180020a1a  mov     [rbp+110h+var_58], 8
0x180020a25  test    edx, edx
0x180020a27  jz      loc_180020BB8
0x180020a2d  mov     r9d, r13d
0x180020a30  test    r15b, r15b
0x180020a33  jnz     loc_180020AF3
0x180020a39  test    edx, edx
0x180020a3b  jz      loc_180020BB3
0x180020a41  mov     r10d, 1
0x180020a47  mov     rdx, [rbx+98h]
0x180020a4e  mov     eax, r9d
0x180020a51  add     r9d, r10d
0x180020a54  imul    rcx, rax, 44h ; 'D'
0x180020a58  imul    r8, rax, 1A8h
0x180020a5f  mov     eax, [r8+rdx]
0x180020a63  mov     [rcx+rdi], eax
0x180020a66  movzx   eax, word ptr [r8+rdx+8]
0x180020a6c  mov     [rcx+rdi+4], ax
0x180020a71  movzx   eax, word ptr [r8+rdx+0Ah]
0x180020a77  mov     [rcx+rdi+6], ax
0x180020a7c  mov     eax, [r8+rdx+160h]
0x180020a84  mov     [rcx+rdi+8], eax
0x180020a88  mov     rax, [r8+rdx+168h]
0x180020a90  mov     [rcx+rdi+0Ch], rax
0x180020a95  mov     rax, [r8+rdx+178h]
0x180020a9d  mov     [rcx+rdi+14h], rax
0x180020aa2  mov     rax, [r8+rdx+180h]
0x180020aaa  mov     [rcx+rdi+1Ch], rax
0x180020aaf  mov     rax, [r8+rdx+188h]
0x180020ab7  mov     [rcx+rdi+24h], rax
0x180020abc  mov     rax, [r8+rdx+190h]
0x180020ac4  mov     [rcx+rdi+2Ch], rax
0x180020ac9  mov     rax, [r8+rdx+198h]
0x180020ad1  mov     [rcx+rdi+34h], rax
0x180020ad6  mov     rax, [r8+rdx+1A0h]
0x180020ade  mov     [rcx+rdi+3Ch], rax
0x180020ae3  cmp     r9d, [rsp+210h+var_1B0]
0x180020ae8  jb      loc_180020A47
0x180020aee  jmp     loc_180020BB3
0x180020af3  test    edx, edx
0x180020af5  jz      loc_180020BB3
0x180020afb  mov     r10d, 1
0x180020b01  mov     rdx, [rbx+98h]
0x180020b08  mov     eax, r9d
0x180020b0b  add     r9d, r10d
0x180020b0e  imul    rcx, rax, 44h ; 'D'
0x180020b12  imul    r8, rax, 1A8h
0x180020b19  mov     eax, [r8+rdx]
0x180020b1d  mov     [rcx+rdi], eax
0x180020b20  movzx   eax, word ptr [r8+rdx+8]
0x180020b26  mov     [rcx+rdi+4], ax
0x180020b2b  movzx   eax, word ptr [r8+rdx+0Ah]
0x180020b31  mov     [rcx+rdi+6], ax
0x180020b36  mov     eax, [r8+rdx+160h]
0x180020b3e  mov     [rcx+rdi+8], eax
0x180020b42  mov     rax, [r8+rdx+168h]
0x180020b4a  mov     [rcx+rdi+0Ch], rax
0x180020b4f  mov     rax, [r8+rdx+178h]
0x180020b57  mov     [rcx+rdi+14h], rax
0x180020b5c  mov     rax, [r8+rdx+180h]
0x180020b64  mov     [rcx+rdi+1Ch], rax
0x180020b69  mov     rax, [r8+rdx+188h]
0x180020b71  mov     [rcx+rdi+24h], rax
0x180020b76  mov     rax, [r8+rdx+190h]
0x180020b7e  mov     [rcx+rdi+2Ch], rax
0x180020b83  mov     rax, [r8+rdx+198h]
0x180020b8b  mov     [rcx+rdi+34h], rax
0x180020b90  mov     rax, [r8+rdx+1A0h]
0x180020b98  mov     [rcx+rdi+3Ch], rax
0x180020b9d  mov     rax, r13
0x180020ba0  xchg    rax, [r8+rdx+1A0h]
0x180020ba8  cmp     r9d, [rsp+210h+var_1B0]
0x180020bad  jb      loc_180020B01
0x180020bb3  mov     rax, rdi
0x180020bb6  jmp     short loc_180020BBE
0x180020bb8  mov     esi, r13d
0x180020bbb  mov     rax, r13
0x180020bbe  mov     rcx, cs:MS_HIDCLASS_ETW_PROVIDER_Context; RegHandle
0x180020bc5  lea     rdx, HIDCLASS_ETW_EVENT_DEVICE_INFORMATION_V2; EventDescriptor
0x180020bcc  mov     [rbp+110h+var_50], rax
0x180020bd3  mov     r9d, 16h; UserDataCount
0x180020bd9  lea     rax, [rsp+210h+var_1A0]
0x180020bde  mov     [rbp+110h+var_48], esi
0x180020be4  mov     r8, r12; ActivityId
0x180020be7  mov     [rsp+210h+UserData], rax; UserData
0x180020bec  mov     [rbp+110h+var_44], r13d
0x180020bf3  call    cs:__imp_EtwWrite
0x180020bfa  nop     dword ptr [rax+rax+00h]
0x180020bff  test    r15b, r15b
0x180020c02  jz      short loc_180020C0A
0x180020c04  mov     rax, r13
0x180020c07  xchg    rax, [r14]
0x180020c0a  test    rdi, rdi
0x180020c0d  jz      short loc_180020C20
0x180020c0f  xor     edx, edx; Tag
0x180020c11  mov     rcx, rdi; P
0x180020c14  call    cs:__imp_ExFreePoolWithTag
0x180020c1b  nop     dword ptr [rax+rax+00h]
0x180020c20  mov     rcx, [rbp+110h+var_40]
0x180020c27  xor     rcx, rsp; StackCookie
0x180020c2a  call    __security_check_cookie
0x180020c2f  mov     rbx, [rsp+210h+arg_10]
0x180020c37  add     rsp, 1E0h
0x180020c3e  pop     r15
0x180020c40  pop     r14
0x180020c42  pop     r13
0x180020c44  pop     r12
0x180020c46  pop     rdi
0x180020c47  pop     rsi
0x180020c48  pop     rbp
0x180020c49  retn
```
