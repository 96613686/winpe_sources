# msOpenStream

- ea: `0x180002eac`
- end: `0x1800033cf`
- name: `msOpenStream`
- size: `1315`
- prototype: `__int64 __fastcall(DWORD_PTR *, WCHAR *, MMIOPROC *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x18000160c`

## callees

- `0x18000128c`
- `0x1800012fc`
- `0x180001344`
- `0x18000240c`
- `0x180002d90`
- `0x180002eac`
- `0x180003bb8`
- `0x180005270`
- `0x180005e7c`
- `0x180005fd5`
- `0x180005ff0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800031e3`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800031e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800030aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003238`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800030aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003238`
- `WINMM!mmioRead` at `0x1800030d4`
- `WINMM!mmioRead` at `0x1800032bd`
- `WINMM!mmioRead` at `0x1800030d4`
- `WINMM!mmioRead` at `0x1800032bd`
- `WINMM!mmioOpenW` at `0x180002f94`
- `WINMM!mmioOpenW` at `0x180002f94`
- `WINMM!mmTaskCreate` at `0x180003342`
- `WINMM!mmTaskCreate` at `0x180003342`
- `WINMM!mmioClose` at `0x180003320`
- `WINMM!mmioClose` at `0x18000337d`
- `WINMM!mmioClose` at `0x180003320`
- `WINMM!mmioClose` at `0x18000337d`
- `WINMM!mmioAscend` at `0x180003188`
- `WINMM!mmioAscend` at `0x1800032ee`
- `WINMM!mmioAscend` at `0x180003188`
- `WINMM!mmioAscend` at `0x1800032ee`
- `WINMM!mmioDescend` at `0x180002fd9`
- `WINMM!mmioDescend` at `0x180003251`
- `WINMM!mmioDescend` at `0x180002fd9`
- `WINMM!mmioDescend` at `0x180003251`
- `WINMM!mmioSeek` at `0x18000319e`
- `WINMM!mmioSeek` at `0x1800032aa`
- `WINMM!mmioSeek` at `0x18000330a`
- `WINMM!mmioSeek` at `0x18000319e`
- `WINMM!mmioSeek` at `0x1800032aa`
- `WINMM!mmioSeek` at `0x18000330a`

## pseudocode

```c
__int64 __fastcall msOpenStream(DWORD_PTR *a1, WCHAR *a2, MMIOPROC *a3)
{
  __int16 v3; // r12
  __int64 v5; // r15
  WCHAR *v6; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  WCHAR *v11; // rcx
  unsigned int v12; // ebx
  LONG cksize; // r14d
  HMMIO v14; // rax
  HMMIO v15; // rsi
  DWORD_PTR v16; // rdi
  _QWORD *v17; // rax
  __int64 v18; // r8
  WCHAR *v19; // rcx
  __int64 v20; // rdx
  _WORD *v21; // rax
  _WORD *v22; // rcx
  unsigned int v23; // edx
  unsigned int v24; // ebx
  int Sequence; // eax
  int v26; // ecx
  int v27; // eax
  DWORD *v28; // rax
  DWORD *v29; // r14
  __int64 v30; // r15
  _QWORD *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rax
  DWORD dwDataOffset; // ecx
  DWORD v36; // edx
  __int64 result; // rax
  _QWORD v38[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v39; // [rsp+40h] [rbp-C0h]
  struct _MMCKINFO pmmcki; // [rsp+48h] [rbp-B8h] BYREF
  MMCKINFO pmmckiParent; // [rsp+60h] [rbp-A0h] BYREF
  struct _MMIOINFO pmmioinfo; // [rsp+80h] [rbp-80h] BYREF
  char pch; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int8 v44; // [rsp+F1h] [rbp-Fh]
  unsigned __int8 v45; // [rsp+F2h] [rbp-Eh]
  unsigned __int8 v46; // [rsp+F3h] [rbp-Dh]
  WCHAR pszFileName[264]; // [rsp+1F0h] [rbp+F0h] BYREF

  v3 = 0;
  v39 = 0;
  v5 = 2147483646;
  v6 = pszFileName;
  v9 = 260;
  memset(&pmmckiParent, 0, sizeof(pmmckiParent));
  v10 = 2147483646;
  memset(&pmmcki, 0, sizeof(pmmcki));
  do
  {
    if ( !v10 )
      break;
    if ( !*a2 )
      break;
    *v6++ = *a2++;
    --v10;
    --v9;
  }
  while ( v9 );
  v11 = v6 - 1;
  if ( v9 )
    v11 = v6;
  *v11 = 0;
  if ( !v9 )
    return 275;
  memset_0(&pmmioinfo, 0, sizeof(pmmioinfo));
  if ( a3 )
    pmmioinfo.pIOProc = a3;
  else
    pmmioinfo.fccIOProc = 542330692;
  cksize = 256;
  if ( !mmioOpenW(pszFileName, &pmmioinfo, 0x100u) )
    return 275;
  v14 = msOpenFile(pszFileName, &pmmckiParent, a3);
  v15 = v14;
  if ( !v14 )
    return 275;
  pmmcki.ckid = 1684558925;
  v16 = 0;
  if ( mmioDescend(v14, &pmmcki, &pmmckiParent, 0x10u) )
    goto LABEL_15;
  pmmcki.cksize = HIBYTE(pmmcki.cksize)
                + (BYTE2(pmmcki.cksize) << 8)
                + ((BYTE1(pmmcki.cksize) + (LOBYTE(pmmcki.cksize) << 8)) << 16);
  if ( pmmcki.cksize < 6 )
    goto LABEL_15;
  v17 = List_Allocate(SeqStreamListHandle);
  v16 = (DWORD_PTR)v17;
  if ( !v17 )
    goto LABEL_54;
  List_Attach_Tail(SeqStreamListHandle, (__int64)v17);
  v19 = pszFileName;
  *(_DWORD *)(v16 + 296) = -1;
  v20 = 128;
  *(_QWORD *)(v16 + 264) = v15;
  v21 = (_WORD *)v16;
  *(_QWORD *)(v16 + 272) = a3;
  do
  {
    if ( !v5 )
      break;
    v18 = *v19;
    if ( !(_WORD)v18 )
      break;
    *v21 = v18;
    ++v19;
    ++v21;
    --v5;
    --v20;
  }
  while ( v20 );
  v22 = v21 - 1;
  if ( v20 )
    v22 = v21;
  *v22 = 0;
  if ( !v20 )
    goto LABEL_15;
  LeaveSeq(v22, v20, v18);
  EnterCriticalSection(&SeqCritSec);
  *(_DWORD *)(v16 + 292) = pmmckiParent.cksize;
  if ( pmmcki.cksize < 0x100 )
    cksize = pmmcki.cksize;
  if ( (LODWORD(v39) = cksize,
        mmioRead(v15, &pch, cksize),
        v23 = v44 + ((unsigned __int8)pch << 8),
        v24 = v46 + (v45 << 8),
        !v23)
    && v24 > 1
    || v23 > 1 )
  {
LABEL_15:
    v12 = 296;
    goto LABEL_55;
  }
  v38[1] = v16;
  v38[3] = &pch;
  v38[2] = v16;
  v38[0] = mciSeqCallback;
  *(_DWORD *)(v16 + 288) = -1;
  Sequence = CreateSequence((__int64)v38, (__int64 *)(v16 + 256));
  if ( Sequence )
  {
    v26 = 264;
    if ( Sequence != 100 )
      v26 = 296;
    v12 = v26;
LABEL_55:
    mmioClose(v15, 0);
    if ( !v16 )
      return v12;
    goto LABEL_52;
  }
  v27 = List_Create(32);
  *(_DWORD *)(v16 + 296) = v27;
  if ( v27 == -1 )
  {
LABEL_54:
    v12 = 264;
    goto LABEL_55;
  }
  mmioAscend(v15, &pmmcki, 0);
  if ( (pmmcki.cksize & 1) != 0 )
    mmioSeek(v15, -1, 1);
  pmmcki.ckid = 1802654797;
LABEL_49:
  if ( v24 )
  {
    v28 = (DWORD *)List_Allocate(*(_DWORD *)(v16 + 296));
    v29 = v28;
    if ( v28 )
    {
      List_Attach_Tail(*(_DWORD *)(v16 + 296), (__int64)v28);
      v30 = 0;
      while ( 1 )
      {
        v31 = GlobalAlloc(0x40u, 0x220u);
        *(_QWORD *)&v29[2 * v30 + 4] = v31;
        if ( !v31 )
          break;
        *v31 = v31 + 4;
        *(_WORD *)(*(_QWORD *)&v29[2 * v30 + 4] + 14LL) = v3;
        *(_QWORD *)(*(_QWORD *)&v29[2 * v30 + 4] + 16LL) = 0;
        v34 = *(_QWORD *)&v29[2 * v30 + 4];
        v30 = (unsigned int)(v30 + 1);
        *(_WORD *)(v34 + 12) = 1;
        if ( (int)v30 >= 2 )
        {
          LeaveSeq(1, v32, v33);
          EnterCriticalSection(&SeqCritSec);
          if ( mmioDescend(v15, &pmmcki, &pmmckiParent, 0x10u) )
            goto LABEL_15;
          pmmcki.cksize = HIBYTE(pmmcki.cksize)
                        + (BYTE2(pmmcki.cksize) << 8)
                        + ((BYTE1(pmmcki.cksize) + (LOBYTE(pmmcki.cksize) << 8)) << 16);
          *v29 = pmmcki.dwDataOffset;
          dwDataOffset = pmmcki.dwDataOffset;
          v29[2] = pmmcki.dwDataOffset;
          v36 = dwDataOffset - 1 + pmmcki.cksize;
          v29[1] = v36;
          mmioSeek(v15, v36 - 2, 0);
          mmioRead(v15, &pch, 3);
          if ( pch != -1 || v44 != 47 || v45 )
            goto LABEL_15;
          --v24;
          mmioAscend(v15, &pmmcki, 0);
          if ( (pmmcki.cksize & 1) != 0 )
            mmioSeek(v15, -1, 1);
          ++v3;
          goto LABEL_49;
        }
      }
    }
    goto LABEL_54;
  }
  mmioClose(v15, 0);
  *(_QWORD *)(v16 + 300) = 1;
  if ( mmTaskCreate((LPTASKCALLBACK)mciStreamCycle, (HANDLE *)(v16 + 312), v16) )
  {
    v12 = 264;
LABEL_52:
    midiSeqMessage(*(_QWORD *)(v16 + 256), 0xDu, 0, 0);
    EndFileStream(v16);
    return v12;
  }
  *(_DWORD *)(v16 + 348) = 0;
  result = 0;
  *(_QWORD *)(v16 + 320) = 0;
  *a1 = v16;
  return result;
}

```

## disassembly

```asm
0x180002eac  mov     [rsp-8+arg_8], rbx
0x180002eb1  push    rbp
0x180002eb2  push    rsi
0x180002eb3  push    rdi
0x180002eb4  push    r12
0x180002eb6  push    r13
0x180002eb8  push    r14
0x180002eba  push    r15
0x180002ebc  lea     rbp, [rsp-310h]
0x180002ec4  sub     rsp, 410h
0x180002ecb  mov     rax, cs:__security_cookie
0x180002ed2  xor     rax, rsp
0x180002ed5  mov     [rbp+340h+var_40], rax
0x180002edc  xor     r12d, r12d
0x180002edf  mov     rbx, r8
0x180002ee2  xor     eax, eax
0x180002ee4  mov     [rsp+440h+var_400], r12
0x180002ee9  xorps   xmm0, xmm0
0x180002eec  mov     [rsp+440h+pmmckiParent.dwFlags], eax
0x180002ef0  xorps   xmm1, xmm1
0x180002ef3  mov     [rsp+440h+pmmcki.dwFlags], eax
0x180002ef7  mov     r15d, 7FFFFFFEh
0x180002efd  lea     rax, [rbp+340h+pszFileName]
0x180002f04  mov     r8, rdx
0x180002f07  lea     r10d, [r12+1]
0x180002f0c  mov     r13, rcx
0x180002f0f  mov     edx, 104h
0x180002f14  movups  xmmword ptr [rsp+440h+pmmckiParent.ckid], xmm0
0x180002f19  mov     ecx, r15d
0x180002f1c  movups  xmmword ptr [rsp+440h+pmmcki.ckid], xmm1
0x180002f21  test    rcx, rcx
0x180002f24  jz      short loc_180002F44
0x180002f26  movzx   r9d, word ptr [r8]
0x180002f2a  test    r9w, r9w
0x180002f2e  jz      short loc_180002F44
0x180002f30  mov     [rax], r9w
0x180002f34  add     r8, 2
0x180002f38  add     rax, 2
0x180002f3c  sub     rcx, r10
0x180002f3f  sub     rdx, r10
0x180002f42  jnz     short loc_180002F21
0x180002f44  test    rdx, rdx
0x180002f47  lea     rcx, [rax-2]
0x180002f4b  cmovnz  rcx, rax
0x180002f4f  mov     [rcx], r12w
0x180002f53  jnz     short loc_180002F5F
0x180002f55  mov     ebx, 113h
0x180002f5a  jmp     loc_18000336F
0x180002f5f  xor     edx, edx; Val
0x180002f61  lea     rcx, [rbp+340h+pmmioinfo]; void *
0x180002f65  lea     r8d, [rdx+64h]; Size
0x180002f69  call    memset_0
0x180002f6e  test    rbx, rbx
0x180002f71  jz      short loc_180002F79
0x180002f73  mov     [rbp+340h+pmmioinfo.pIOProc], rbx
0x180002f77  jmp     short loc_180002F80
0x180002f79  mov     [rbp+340h+pmmioinfo.fccIOProc], 20534F44h
0x180002f80  mov     r14d, 100h
0x180002f86  lea     rdx, [rbp+340h+pmmioinfo]; pmmioinfo
0x180002f8a  mov     r8d, r14d; fdwOpen
0x180002f8d  lea     rcx, [rbp+340h+pszFileName]; pszFileName
0x180002f94  call    cs:__imp_mmioOpenW
0x180002f9a  test    rax, rax
0x180002f9d  jz      short loc_180002F55
0x180002f9f  mov     r8, rbx
0x180002fa2  lea     rdx, [rsp+440h+pmmckiParent]; pmmcki
0x180002fa7  lea     rcx, [rbp+340h+pszFileName]; pszFileName
0x180002fae  call    msOpenFile
0x180002fb3  mov     rsi, rax
0x180002fb6  test    rax, rax
0x180002fb9  jz      short loc_180002F55
0x180002fbb  mov     r9d, 10h; fuDescend
0x180002fc1  mov     [rsp+440h+pmmcki.ckid], 6468544Dh
0x180002fc9  lea     r8, [rsp+440h+pmmckiParent]; pmmckiParent
0x180002fce  mov     rcx, rax; hmmio
0x180002fd1  lea     rdx, [rsp+440h+pmmcki]; pmmcki
0x180002fd6  mov     rdi, r12
0x180002fd9  call    cs:__imp_mmioDescend
0x180002fdf  test    eax, eax
0x180002fe1  jz      short loc_180002FED
0x180002fe3  mov     ebx, 128h
0x180002fe8  jmp     loc_180003378
0x180002fed  movzx   eax, byte ptr [rsp+440h+pmmcki.cksize+1]
0x180002ff2  movzx   ecx, byte ptr [rsp+440h+pmmcki.cksize]
0x180002ff7  shl     ecx, 8
0x180002ffa  add     ecx, eax
0x180002ffc  movzx   eax, byte ptr [rsp+440h+pmmcki.cksize+2]
0x180003001  shl     eax, 8
0x180003004  shl     ecx, 10h
0x180003007  add     ecx, eax
0x180003009  movzx   eax, byte ptr [rsp+440h+pmmcki.cksize+3]
0x18000300e  add     ecx, eax
0x180003010  mov     [rsp+440h+pmmcki.cksize], ecx
0x180003014  cmp     ecx, 6
0x180003017  jb      short loc_180002FE3
0x180003019  mov     ecx, cs:SeqStreamListHandle
0x18000301f  call    List_Allocate
0x180003024  mov     rdi, rax
0x180003027  test    rax, rax
0x18000302a  jz      loc_180003373
0x180003030  mov     ecx, cs:SeqStreamListHandle
0x180003036  mov     rdx, rax
0x180003039  call    List_Attach_Tail
0x18000303e  lea     rcx, [rbp+340h+pszFileName]
0x180003045  mov     dword ptr [rdi+128h], 0FFFFFFFFh
0x18000304f  mov     edx, 80h
0x180003054  mov     [rdi+108h], rsi
0x18000305b  mov     rax, rdi
0x18000305e  mov     [rdi+110h], rbx
0x180003065  test    r15, r15
0x180003068  jz      short loc_180003089
0x18000306a  movzx   r8d, word ptr [rcx]
0x18000306e  test    r8w, r8w
0x180003072  jz      short loc_180003089
0x180003074  mov     [rax], r8w
0x180003078  add     rcx, 2
0x18000307c  add     rax, 2
0x180003080  dec     r15
0x180003083  sub     rdx, 1
0x180003087  jnz     short loc_180003065
0x180003089  test    rdx, rdx
0x18000308c  lea     rcx, [rax-2]
0x180003090  cmovnz  rcx, rax
0x180003094  mov     [rcx], r12w
0x180003098  jz      loc_180002FE3
0x18000309e  call    LeaveSeq
0x1800030a3  lea     rcx, SeqCritSec; lpCriticalSection
0x1800030aa  call    cs:__imp_EnterCriticalSection
0x1800030b0  mov     eax, [rsp+440h+pmmckiParent.cksize]
0x1800030b4  lea     rdx, [rbp+340h+pch]; pch
0x1800030b8  mov     [rdi+124h], eax
0x1800030be  mov     rcx, rsi; hmmio
0x1800030c1  cmp     [rsp+440h+pmmcki.cksize], r14d
0x1800030c6  cmovb   r14d, [rsp+440h+pmmcki.cksize]
0x1800030cc  mov     r8d, r14d; cch
0x1800030cf  mov     dword ptr [rsp+440h+var_400], r14d
0x1800030d4  call    cs:__imp_mmioRead
0x1800030da  movzx   eax, [rbp+340h+var_34F]
0x1800030de  mov     r14d, 1
0x1800030e4  movzx   edx, [rbp+340h+pch]
0x1800030e8  movzx   ebx, [rbp+340h+var_34E]
0x1800030ec  shl     edx, 8
0x1800030ef  add     edx, eax
0x1800030f1  shl     ebx, 8
0x1800030f4  movzx   eax, [rbp+340h+var_34D]
0x1800030f8  add     ebx, eax
0x1800030fa  test    edx, edx
0x1800030fc  jnz     short loc_180003107
0x1800030fe  cmp     ebx, r14d
0x180003101  ja      loc_180002FE3
0x180003107  cmp     edx, r14d
0x18000310a  ja      loc_180002FE3
0x180003110  lea     rax, [rbp+340h+pch]
0x180003114  mov     [rsp+440h+var_418], rdi
0x180003119  mov     [rsp+440h+var_408], rax
0x18000311e  lea     rdx, [rdi+100h]
0x180003125  lea     rax, mciSeqCallback
0x18000312c  mov     [rsp+440h+var_410], rdi
0x180003131  or      r15d, 0FFFFFFFFh
0x180003135  mov     [rsp+440h+var_420], rax
0x18000313a  lea     rcx, [rsp+440h+var_420]
0x18000313f  mov     [rdi+120h], r15d
0x180003146  call    CreateSequence
0x18000314b  test    eax, eax
0x18000314d  jz      short loc_180003164
0x18000314f  mov     ecx, 108h
0x180003154  cmp     eax, 64h ; 'd'
0x180003157  lea     ebx, [rcx+20h]
0x18000315a  cmovnz  ecx, ebx
0x18000315d  mov     ebx, ecx
0x18000315f  jmp     loc_180003378
0x180003164  mov     ecx, 20h ; ' '
0x180003169  call    List_Create
0x18000316e  mov     [rdi+128h], eax
0x180003174  cmp     eax, r15d
0x180003177  jz      loc_180003373
0x18000317d  xor     r8d, r8d; fuAscend
0x180003180  lea     rdx, [rsp+440h+pmmcki]; pmmcki
0x180003185  mov     rcx, rsi; hmmio
0x180003188  call    cs:__imp_mmioAscend
0x18000318e  test    byte ptr [rsp+440h+pmmcki.cksize], r14b
0x180003193  jz      short loc_1800031A4
0x180003195  mov     r8d, r14d; iOrigin
0x180003198  or      edx, 0FFFFFFFFh; lOffset
0x18000319b  mov     rcx, rsi; hmmio
0x18000319e  call    cs:__imp_mmioSeek
0x1800031a4  mov     [rsp+440h+pmmcki.ckid], 6B72544Dh
0x1800031ac  jmp     loc_180003313
0x1800031b1  mov     ecx, [rdi+128h]
0x1800031b7  call    List_Allocate
0x1800031bc  mov     r14, rax
0x1800031bf  test    rax, rax
0x1800031c2  jz      loc_180003373
0x1800031c8  mov     ecx, [rdi+128h]
0x1800031ce  mov     rdx, rax
0x1800031d1  call    List_Attach_Tail
0x1800031d6  xor     r15d, r15d
0x1800031d9  mov     edx, 220h; dwBytes
0x1800031de  mov     ecx, 40h ; '@'; uFlags
0x1800031e3  call    cs:__imp_GlobalAlloc
0x1800031e9  mov     [r14+r15*8+10h], rax
0x1800031ee  test    rax, rax
0x1800031f1  jz      loc_180003373
0x1800031f7  lea     rcx, [rax+20h]
0x1800031fb  mov     [rax], rcx
0x1800031fe  mov     ecx, 1
0x180003203  mov     rax, [r14+r15*8+10h]
0x180003208  mov     [rax+0Eh], r12w
0x18000320d  mov     rax, [r14+r15*8+10h]
0x180003212  mov     qword ptr [rax+10h], 0
0x18000321a  mov     rax, [r14+r15*8+10h]
0x18000321f  add     r15d, ecx
0x180003222  mov     [rax+0Ch], cx
0x180003226  cmp     r15d, 2
0x18000322a  jl      short loc_1800031D9
0x18000322c  call    LeaveSeq
0x180003231  lea     rcx, SeqCritSec; lpCriticalSection
0x180003238  call    cs:__imp_EnterCriticalSection
0x18000323e  mov     r9d, 10h; fuDescend
0x180003244  lea     r8, [rsp+440h+pmmckiParent]; pmmckiParent
0x180003249  lea     rdx, [rsp+440h+pmmcki]; pmmcki
0x18000324e  mov     rcx, rsi; hmmio
0x180003251  call    cs:__imp_mmioDescend
0x180003257  test    eax, eax
0x180003259  jnz     loc_180002FE3
0x18000325f  movzx   ecx, byte ptr [rsp+440h+pmmcki.cksize]
0x180003264  xor     r8d, r8d; iOrigin
0x180003267  movzx   eax, byte ptr [rsp+440h+pmmcki.cksize+1]
0x18000326c  shl     ecx, 8
0x18000326f  add     ecx, eax
0x180003271  movzx   eax, byte ptr [rsp+440h+pmmcki.cksize+2]
0x180003276  shl     ecx, 10h
0x180003279  shl     eax, 8
0x18000327c  add     ecx, eax
0x18000327e  movzx   eax, byte ptr [rsp+440h+pmmcki.cksize+3]
0x180003283  add     ecx, eax
0x180003285  mov     eax, [rsp+440h+pmmcki.dwDataOffset]
0x180003289  mov     [rsp+440h+pmmcki.cksize], ecx
0x18000328d  mov     [r14], eax
0x180003290  mov     ecx, [rsp+440h+pmmcki.dwDataOffset]
0x180003294  mov     [r14+8], ecx
0x180003298  dec     ecx
0x18000329a  mov     edx, [rsp+440h+pmmcki.cksize]
0x18000329e  add     edx, ecx
0x1800032a0  mov     rcx, rsi; hmmio
0x1800032a3  mov     [r14+4], edx
0x1800032a7  add     edx, 0FFFFFFFEh; lOffset
0x1800032aa  call    cs:__imp_mmioSeek
0x1800032b0  mov     r8d, 3; cch
0x1800032b6  lea     rdx, [rbp+340h+pch]; pch
0x1800032ba  mov     rcx, rsi; hmmio
0x1800032bd  call    cs:__imp_mmioRead
0x1800032c3  cmp     [rbp+340h+pch], 0FFh
0x1800032c7  jnz     loc_180002FE3
0x1800032cd  cmp     [rbp+340h+var_34F], 2Fh ; '/'
0x1800032d1  jnz     loc_180002FE3
0x1800032d7  cmp     [rbp+340h+var_34E], 0
0x1800032db  jnz     loc_180002FE3
0x1800032e1  xor     r8d, r8d; fuAscend
0x1800032e4  lea     rdx, [rsp+440h+pmmcki]; pmmcki
0x1800032e9  mov     rcx, rsi; hmmio
0x1800032ec  dec     ebx
0x1800032ee  call    cs:__imp_mmioAscend
0x1800032f4  mov     r14d, 1
0x1800032fa  test    byte ptr [rsp+440h+pmmcki.cksize], r14b
0x1800032ff  jz      short loc_180003310
0x180003301  mov     r8d, r14d; iOrigin
0x180003304  or      edx, 0FFFFFFFFh; lOffset
0x180003307  mov     rcx, rsi; hmmio
0x18000330a  call    cs:__imp_mmioSeek
0x180003310  add     r12d, r14d
0x180003313  test    ebx, ebx
0x180003315  jnz     loc_1800031B1
0x18000331b  xor     edx, edx; fuClose
0x18000331d  mov     rcx, rsi; hmmio
0x180003320  call    cs:__imp_mmioClose
0x180003326  lea     rdx, [rdi+138h]; lph
0x18000332d  mov     qword ptr [rdi+12Ch], 1
0x180003338  mov     r8, rdi; dwInst
0x18000333b  lea     rcx, mciStreamCycle; lpfn
0x180003342  call    cs:__imp_mmTaskCreate
0x180003348  test    eax, eax
0x18000334a  jz      short loc_18000338A
0x18000334c  mov     ebx, 108h
0x180003351  mov     rcx, [rdi+100h]; dwUser
0x180003358  xor     r9d, r9d
0x18000335b  xor     r8d, r8d
0x18000335e  lea     edx, [r9+0Dh]
0x180003362  call    midiSeqMessage
0x180003367  mov     rcx, rdi
0x18000336a  call    EndFileStream
0x18000336f  mov     eax, ebx
0x180003371  jmp     short loc_1800033A5
0x180003373  mov     ebx, 108h
0x180003378  xor     edx, edx; fuClose
0x18000337a  mov     rcx, rsi; hmmio
0x18000337d  call    cs:__imp_mmioClose
0x180003383  test    rdi, rdi
0x180003386  jz      short loc_18000336F
0x180003388  jmp     short loc_180003351
  ... truncated ...
```
