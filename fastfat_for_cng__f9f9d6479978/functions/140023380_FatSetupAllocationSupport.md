# FatSetupAllocationSupport

- ea: `0x140023380`
- end: `0x140023935`
- name: `FatSetupAllocationSupport`
- size: `1461`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x140040674`
- `0x140042ec8`

## callees

- `0x14000170c`
- `0x140001858`
- `0x14000c230`
- `0x14000c680`
- `0x1400216f4`
- `0x140021fa8`
- `0x140023380`
- `0x140023a5c`

## import_xrefs

- `ntoskrnl!RtlFindClearBits` at `0x1400238d5`
- `ntoskrnl!RtlFindClearBits` at `0x1400238d5`
- `ntoskrnl!RtlInitializeBitMap` at `0x14002381f`
- `ntoskrnl!RtlInitializeBitMap` at `0x14002381f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400237df`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400237df`
- `ntoskrnl!CcSetFileSizes` at `0x14002376f`
- `ntoskrnl!CcSetFileSizes` at `0x14002376f`
- `ntoskrnl!ExRaiseStatus` at `0x140023426`
- `ntoskrnl!ExRaiseStatus` at `0x1400237aa`
- `ntoskrnl!ExRaiseStatus` at `0x140023928`
- `ntoskrnl!ExRaiseStatus` at `0x140023426`
- `ntoskrnl!ExRaiseStatus` at `0x1400237aa`
- `ntoskrnl!ExRaiseStatus` at `0x140023928`

## pseudocode

```c
ULONG __fastcall FatSetupAllocationSupport(__int64 a1, __int64 a2)
{
  unsigned int v4; // r11d
  unsigned int v5; // r8d
  int v6; // r10d
  __int64 v7; // rcx
  unsigned __int16 v8; // si
  unsigned __int8 v9; // di
  unsigned __int64 v10; // rax
  unsigned int v11; // edx
  unsigned int v12; // r9d
  unsigned int v13; // ecx
  unsigned int v14; // edx
  unsigned int v15; // r14d
  int v16; // ecx
  int v17; // eax
  int v18; // r8d
  int v19; // r9d
  int v20; // edx
  unsigned int v21; // r15d
  unsigned int v22; // eax
  unsigned __int8 *v23; // rdi
  unsigned __int64 v24; // rax
  __int64 v25; // rsi
  int v26; // r12d
  unsigned int v27; // edx
  char v28; // al
  unsigned int v29; // r10d
  __int64 v30; // r9
  unsigned __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r8
  unsigned __int64 v34; // rcx
  int v35; // ecx
  unsigned int v36; // eax
  unsigned int v37; // edx
  struct _FILE_OBJECT *v38; // rcx
  unsigned int v39; // ecx
  __int64 v40; // rax
  size_t v41; // rsi
  PVOID PoolWithTag; // rax
  PVOID v43; // r14
  _DWORD *v44; // rax
  ULONG result; // eax
  int v46; // ecx
  int v47; // [rsp+40h] [rbp-68h]
  int v48; // [rsp+44h] [rbp-64h]
  unsigned __int64 v49; // [rsp+48h] [rbp-60h]
  unsigned int v50; // [rsp+50h] [rbp-58h]
  _CC_FILE_SIZES FileSizes; // [rsp+60h] [rbp-48h] BYREF

  v4 = *(unsigned __int16 *)(a2 + 298);
  v5 = v4;
  if ( !(_WORD)v4 )
    v5 = *(_DWORD *)(a2 + 312);
  v6 = *(unsigned __int16 *)(a2 + 302);
  if ( (_WORD)v6 )
  {
    v9 = *(_BYTE *)(a2 + 294);
    v12 = *(unsigned __int16 *)(a2 + 292);
    v13 = v12 + v6 * v9;
    if ( v13 < v12
      || (v8 = *(_WORD *)(a2 + 288), v14 = 32 * (unsigned int)*(unsigned __int16 *)(a2 + 296) / v8 + v13, v14 < v13)
      || v5 < v14 )
    {
LABEL_8:
      *(_DWORD *)(a1 + 72) = -1073741566;
      ExRaiseStatus(-1073741566);
    }
    LOWORD(v11) = v12;
  }
  else
  {
    v7 = *(unsigned int *)(a2 + 316);
    v8 = *(_WORD *)(a2 + 288);
    if ( v7 * (unsigned __int64)v8 > 0xFFFFFFFF )
      goto LABEL_8;
    v9 = *(_BYTE *)(a2 + 294);
    v10 = v7 * v9;
    if ( v10 > 0xFFFFFFFF )
      goto LABEL_8;
    v11 = *(unsigned __int16 *)(a2 + 292);
    if ( (unsigned int)v10 + v11 < v11 || v5 < (unsigned int)v10 + v11 )
      goto LABEL_8;
  }
  v15 = v8;
  v16 = v8 * v6;
  if ( (_WORD)v6 )
    v17 = v8 * v6;
  else
    v17 = *(_DWORD *)(a2 + 316) * v8;
  v18 = v9;
  v19 = (unsigned __int16)v11;
  v48 = (unsigned __int16)v11;
  v20 = v8 * (unsigned __int16)v11;
  *(_QWORD *)(a2 + 344) = v20 + (unsigned int)v9 * v17;
  v47 = *(unsigned __int16 *)(a2 + 296);
  *(_DWORD *)(a2 + 360) = 32 * v47;
  if ( !(_WORD)v6 )
    v16 = *(_DWORD *)(a2 + 316) * v8;
  *(_QWORD *)(a2 + 352) = v20 + (unsigned int)v9 * v16 + 32 * v47;
  v21 = v4;
  if ( (_WORD)v6 )
  {
    v27 = v4;
    if ( !(_WORD)v4 )
      v27 = *(_DWORD *)(a2 + 312);
    v23 = (unsigned __int8 *)(a2 + 290);
    v49 = v8;
    v25 = (unsigned __int16)v47;
    v26 = v18 * v6;
    v24 = (v27 - (unsigned __int64)(unsigned int)(v18 * v6 + v48) - 32 * (unsigned __int64)(unsigned __int16)v47 / v49)
        / *(unsigned __int8 *)(a2 + 290);
    LOBYTE(v50) = *(_BYTE *)(a2 + 290);
    v19 = v48;
  }
  else
  {
    v22 = v4;
    if ( !(_WORD)v4 )
      v22 = *(_DWORD *)(a2 + 312);
    v23 = (unsigned __int8 *)(a2 + 290);
    v50 = *(unsigned __int8 *)(a2 + 290);
    LODWORD(v24) = (v22 - *(_DWORD *)(a2 + 316) * v18 - v19) / v50;
    v49 = v8;
    v25 = (unsigned __int16)v47;
    v26 = v18 * v6;
  }
  *(_DWORD *)(a2 + 364) = v24;
  if ( (_WORD)v6 )
  {
    if ( !(_WORD)v4 )
      v21 = *(_DWORD *)(a2 + 312);
    if ( (v21 - (unsigned __int64)(unsigned int)(v26 + v19) - 32 * v25 / v49) / (unsigned __int8)v50 >= 0xFF7 )
    {
      v28 = 16;
    }
    else
    {
      v28 = 12;
      v23 = (unsigned __int8 *)(a2 + 290);
    }
  }
  else
  {
    v28 = 32;
  }
  *(_BYTE *)(a2 + 376) = v28;
  *(_BYTE *)(a2 + 377) = FatLogOf(v15);
  *(_BYTE *)(a2 + 378) = FatLogOf(*(unsigned __int16 *)(a2 + 288) * (unsigned int)*v23);
  *(_DWORD *)(a2 + 368) = 0;
  *(_DWORD *)(a2 + 372) = 4096;
  if ( *(_BYTE *)(a2 + 376) == 32 )
    v29 = *(_DWORD *)(a2 + 316);
  else
    v29 = *(unsigned __int16 *)(a2 + 302);
  v30 = *(unsigned __int16 *)(a2 + 302);
  if ( (_WORD)v30 )
  {
    if ( *(_WORD *)(a2 + 298) )
      v32 = *(unsigned __int16 *)(a2 + 298);
    else
      v32 = *(unsigned int *)(a2 + 312);
    v31 = (-(__int64)((v32
                     - 32 * (unsigned __int64)*(unsigned __int16 *)(a2 + 296) / *(unsigned __int16 *)(a2 + 288)
                     - *(unsigned __int8 *)(a2 + 294) * v30
                     - *(unsigned __int16 *)(a2 + 292))
                    / *v23 < 0xFF7)
         & 0xFFFFFFFFFFFFFFFCuLL)
        + 16;
  }
  else
  {
    v31 = 32;
  }
  v33 = *(unsigned __int16 *)(a2 + 288);
  v34 = 8 * v33 * (unsigned __int64)v29 / v31 - 2;
  if ( *(unsigned int *)(a2 + 364) > v34 )
    *(_DWORD *)(a2 + 364) = v34;
  FileSizes.FileSize.QuadPart = 0;
  if ( (_WORD)v30 )
    v35 = v33 * v30;
  else
    v35 = *(_DWORD *)(a2 + 316) * v33;
  v36 = v33 * *(unsigned __int16 *)(a2 + 292);
  v37 = v36 + v35;
  if ( v36 + v35 < v36 )
  {
    *(_DWORD *)(a1 + 72) = -1073741566;
    ExRaiseStatus(-1073741566);
  }
  FileSizes.FileSize.QuadPart = v37;
  FileSizes.AllocationSize.QuadPart = v37;
  FileSizes.ValidDataLength.QuadPart = FatMaxLarge;
  v38 = *(struct _FILE_OBJECT **)(a2 + 728);
  if ( v38->PrivateCacheMap )
    CcSetFileSizes(v38, &FileSizes);
  else
    FatInitializeCacheMap(v38, &FileSizes, 1u, (struct _CACHE_MANAGER_CALLBACKS *)&qword_140017DB0, (PVOID)a2);
  if ( *(_BYTE *)(a2 + 376) == 32 && (v39 = *(_DWORD *)(a2 + 364), v39 > 0x10000) )
  {
    if ( v39 + 0xFFFF < v39 )
    {
      *(_DWORD *)(a1 + 72) = -1073741566;
      ExRaiseStatus(-1073741566);
    }
    v40 = (v39 + 0xFFFF) >> 16;
    *(_DWORD *)(a2 + 216) = v40;
  }
  else
  {
    *(_DWORD *)(a2 + 216) = 1;
    v40 = 1;
  }
  v41 = 12 * v40;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1041, 12 * v40, 0x57746146u);
  v43 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, v41);
  *(_QWORD *)(a2 + 224) = v43;
  RtlInitializeBitMap((PRTL_BITMAP)(a2 + 448), 0, 0);
  if ( *(_DWORD *)(a2 + 216) <= 1u )
  {
    v44 = *(_DWORD **)(a2 + 224);
    *(_QWORD *)(a2 + 232) = v44;
    *v44 = 2;
    *(_DWORD *)(*(_QWORD *)(a2 + 232) + 4LL) = *(_DWORD *)(a2 + 364) + 1;
  }
  else
  {
    FatExamineFatEntries(a1, a2, 2, *(_DWORD *)(a2 + 364) + 1, 1, 0, 0);
    *(_QWORD *)(a2 + 232) = *(_QWORD *)(a2 + 224) + 12LL * (unsigned int)FatSelectBestWindow(a2);
  }
  FatExamineFatEntries(a1, a2, 0, 0, 0, *(_QWORD *)(a2 + 232), 0);
  result = RtlFindClearBits((PRTL_BITMAP)(a2 + 448), 1u, 0);
  v46 = result + 2;
  if ( result == -1 )
    v46 = 2;
  *(_DWORD *)(a2 + 760) = v46;
  return result;
}

```

## disassembly

```asm
0x140023380  mov     [rsp+arg_10], rbx
0x140023385  mov     [rsp+arg_18], rsi
0x14002338a  push    rdi
0x14002338b  push    r12
0x14002338d  push    r13
0x14002338f  push    r14
0x140023391  push    r15
0x140023393  sub     rsp, 80h
0x14002339a  mov     rax, cs:__security_cookie
0x1400233a1  xor     rax, rsp
0x1400233a4  mov     [rsp+0A8h+var_30], rax
0x1400233a9  mov     rbx, rdx
0x1400233ac  mov     r13, rcx
0x1400233af  mov     [rsp+0A8h+var_50], rdx
0x1400233b4  movzx   r11d, word ptr [rdx+12Ah]
0x1400233bc  test    r11w, r11w
0x1400233c0  mov     r8d, r11d
0x1400233c3  jnz     short loc_1400233CC
0x1400233c5  mov     r8d, [rdx+138h]
0x1400233cc  movzx   r10d, word ptr [rdx+12Eh]
0x1400233d4  test    r10w, r10w
0x1400233d8  jnz     short loc_140023433
0x1400233da  mov     ecx, [rdx+13Ch]
0x1400233e0  movzx   esi, word ptr [rdx+120h]
0x1400233e7  mov     eax, esi
0x1400233e9  imul    rax, rcx
0x1400233ed  mov     r9d, 0FFFFFFFFh
0x1400233f3  cmp     rax, r9
0x1400233f6  ja      short loc_14002341D
0x1400233f8  movzx   edi, byte ptr [rdx+126h]
0x1400233ff  mov     eax, edi
0x140023401  imul    rax, rcx
0x140023405  cmp     rax, r9
0x140023408  ja      short loc_14002341D
0x14002340a  movzx   edx, word ptr [rdx+124h]
0x140023411  lea     ecx, [rax+rdx]
0x140023414  cmp     ecx, edx
0x140023416  jb      short loc_14002341D
0x140023418  cmp     r8d, ecx
0x14002341b  jnb     short loc_140023475
0x14002341d  mov     ecx, 0C0000102h; Status
0x140023422  mov     [r13+48h], ecx
0x140023426  call    cs:__imp_ExRaiseStatus
0x140023433  movzx   edi, byte ptr [rdx+126h]
0x14002343a  movzx   r9d, word ptr [rdx+124h]
0x140023442  mov     ecx, edi
0x140023444  imul    ecx, r10d
0x140023448  add     ecx, r9d
0x14002344b  cmp     ecx, r9d
0x14002344e  jb      short loc_14002341D
0x140023450  movzx   esi, word ptr [rdx+120h]
0x140023457  movzx   eax, word ptr [rdx+128h]
0x14002345e  shl     eax, 5
0x140023461  xor     edx, edx
0x140023463  div     esi
0x140023465  lea     edx, [rax+rcx]
0x140023468  cmp     edx, ecx
0x14002346a  jb      short loc_14002341D
0x14002346c  cmp     r8d, edx
0x14002346f  jb      short loc_14002341D
0x140023471  movzx   edx, r9w
0x140023475  mov     r12d, r10d
0x140023478  movzx   r14d, si
0x14002347c  mov     ecx, r10d
0x14002347f  imul    ecx, r14d
0x140023483  test    r10w, r10w
0x140023487  jnz     short loc_140023495
0x140023489  mov     eax, r14d
0x14002348c  imul    eax, [rbx+13Ch]
0x140023493  jmp     short loc_140023497
0x140023495  mov     eax, ecx
0x140023497  movzx   r8d, dil
0x14002349b  movzx   r9d, dx
0x14002349f  mov     [rsp+0A8h+var_64], r9d
0x1400234a4  mov     edx, r9d
0x1400234a7  imul    edx, r14d
0x1400234ab  imul    eax, r8d
0x1400234af  add     eax, edx
0x1400234b1  mov     [rbx+158h], rax
0x1400234b8  movzx   eax, word ptr [rbx+128h]
0x1400234bf  mov     [rsp+0A8h+var_68], eax
0x1400234c3  shl     eax, 5
0x1400234c6  mov     [rbx+168h], eax
0x1400234cc  test    r10w, r10w
0x1400234d0  jnz     short loc_1400234DC
0x1400234d2  mov     ecx, r14d
0x1400234d5  imul    ecx, [rbx+13Ch]
0x1400234dc  imul    ecx, r8d
0x1400234e0  add     eax, ecx
0x1400234e2  add     eax, edx
0x1400234e4  mov     [rbx+160h], rax
0x1400234eb  mov     r15d, r11d
0x1400234ee  test    r10w, r10w
0x1400234f2  jnz     short loc_14002353A
0x1400234f4  test    r11w, r11w
0x1400234f8  mov     eax, r11d
0x1400234fb  jnz     short loc_140023503
0x1400234fd  mov     eax, [rbx+138h]
0x140023503  lea     rdi, [rbx+122h]
0x14002350a  movzx   ecx, byte ptr [rdi]
0x14002350d  mov     [rsp+0A8h+var_58], rcx
0x140023512  mov     ecx, r8d
0x140023515  imul    ecx, [rbx+13Ch]
0x14002351c  sub     eax, ecx
0x14002351e  sub     eax, r9d
0x140023521  xor     edx, edx
0x140023523  div     dword ptr [rsp+0A8h+var_58]
0x140023527  movzx   ecx, si
0x14002352a  mov     [rsp+0A8h+var_60], rcx
0x14002352f  movzx   esi, word ptr [rsp+0A8h+var_68]
0x140023534  imul    r12d, r8d
0x140023538  jmp     short loc_140023594
0x14002353a  test    r11w, r11w
0x14002353e  mov     edx, r11d
0x140023541  jnz     short loc_140023549
0x140023543  mov     edx, [rbx+138h]
0x140023549  lea     rdi, [rbx+122h]
0x140023550  movzx   r9d, byte ptr [rdi]
0x140023554  movzx   eax, si
0x140023557  mov     [rsp+0A8h+var_60], rax
0x14002355c  movzx   esi, word ptr [rsp+0A8h+var_68]
0x140023561  imul    r12d, r8d
0x140023565  mov     ecx, [rsp+0A8h+var_64]
0x140023569  add     ecx, r12d
0x14002356c  mov     r8d, edx
0x14002356f  sub     r8, rcx
0x140023572  mov     eax, esi
0x140023574  shl     rax, 5
0x140023578  xor     edx, edx
0x14002357a  div     [rsp+0A8h+var_60]
0x14002357f  sub     r8, rax
0x140023582  xor     edx, edx
0x140023584  mov     rax, r8
0x140023587  div     r9
0x14002358a  mov     byte ptr [rsp+0A8h+var_58], r9b
0x14002358f  mov     r9d, [rsp+0A8h+var_64]
0x140023594  mov     [rbx+16Ch], eax
0x14002359a  test    r10w, r10w
0x14002359e  jnz     short loc_1400235A4
0x1400235a0  mov     al, 20h ; ' '
0x1400235a2  jmp     short loc_1400235F1
0x1400235a4  test    r11w, r11w
0x1400235a8  jnz     short loc_1400235B1
0x1400235aa  mov     r15d, [rbx+138h]
0x1400235b1  lea     edx, [r12+r9]
0x1400235b5  mov     r8d, r15d
0x1400235b8  sub     r8, rdx
0x1400235bb  shl     rsi, 5
0x1400235bf  xor     edx, edx
0x1400235c1  mov     rax, rsi
0x1400235c4  div     [rsp+0A8h+var_60]
0x1400235c9  sub     r8, rax
0x1400235cc  mov     rcx, [rsp+0A8h+var_58]
0x1400235d1  movzx   ecx, cl
0x1400235d4  xor     edx, edx
0x1400235d6  mov     rax, r8
0x1400235d9  div     rcx
0x1400235dc  cmp     rax, 0FF7h
0x1400235e2  jnb     short loc_1400235EF
0x1400235e4  mov     al, 0Ch
0x1400235e6  lea     rdi, [rbx+122h]
0x1400235ed  jmp     short loc_1400235F1
0x1400235ef  mov     al, 10h
0x1400235f1  mov     [rbx+178h], al
0x1400235f7  mov     ecx, r14d; BugCheckParameter2
0x1400235fa  call    FatLogOf
0x1400235ff  mov     [rbx+179h], al
0x140023605  movzx   ecx, byte ptr [rdi]
0x140023608  movzx   eax, word ptr [rbx+120h]
0x14002360f  imul    ecx, eax; BugCheckParameter2
0x140023612  call    FatLogOf
0x140023617  mov     [rbx+17Ah], al
0x14002361d  xor     r15d, r15d
0x140023620  mov     [rbx+170h], r15d
0x140023627  mov     dword ptr [rbx+174h], 1000h
0x140023631  cmp     byte ptr [rbx+178h], 20h ; ' '
0x140023638  jnz     short loc_140023643
0x14002363a  mov     r10d, [rbx+13Ch]
0x140023641  jmp     short loc_14002364B
0x140023643  movzx   r10d, word ptr [rbx+12Eh]
0x14002364b  movzx   r9d, word ptr [rbx+12Eh]
0x140023653  test    r9w, r9w
0x140023657  jnz     short loc_140023660
0x140023659  mov     ecx, 20h ; ' '
0x14002365e  jmp     short loc_1400236C9
0x140023660  movzx   eax, word ptr [rbx+12Ah]
0x140023667  test    ax, ax
0x14002366a  jz      short loc_140023671
0x14002366c  mov     r8d, eax
0x14002366f  jmp     short loc_140023678
0x140023671  mov     r8d, [rbx+138h]
0x140023678  movzx   eax, word ptr [rbx+128h]
0x14002367f  shl     rax, 5
0x140023683  movzx   ecx, word ptr [rbx+120h]
0x14002368a  xor     edx, edx
0x14002368c  div     rcx
0x14002368f  sub     r8, rax
0x140023692  mov     rdx, r9
0x140023695  movzx   ecx, byte ptr [rbx+126h]
0x14002369c  imul    rdx, rcx
0x1400236a0  sub     r8, rdx
0x1400236a3  movzx   ecx, word ptr [rbx+124h]
0x1400236aa  sub     r8, rcx
0x1400236ad  movzx   ecx, byte ptr [rdi]
0x1400236b0  xor     edx, edx
0x1400236b2  mov     rax, r8
0x1400236b5  div     rcx
0x1400236b8  cmp     rax, 0FF7h
0x1400236be  sbb     rcx, rcx
0x1400236c1  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1400236c5  add     rcx, 10h
0x1400236c9  movzx   r8d, word ptr [rbx+120h]
0x1400236d1  mov     eax, r10d
0x1400236d4  imul    rax, r8
0x1400236d8  shl     rax, 3
0x1400236dc  xor     edx, edx
0x1400236de  div     rcx
0x1400236e1  lea     rcx, [rax-2]
0x1400236e5  mov     eax, [rbx+16Ch]
0x1400236eb  cmp     rax, rcx
0x1400236ee  jbe     short loc_1400236F6
0x1400236f0  mov     [rbx+16Ch], ecx
0x1400236f6  mov     qword ptr [rsp+0A8h+FileSizes.FileSize], r15
0x1400236fb  mov     edx, r8d
0x1400236fe  test    r9w, r9w
0x140023702  jnz     short loc_14002370F
0x140023704  mov     ecx, edx
0x140023706  imul    ecx, [rbx+13Ch]
0x14002370d  jmp     short loc_140023715
0x14002370f  mov     ecx, r9d
0x140023712  imul    ecx, edx
0x140023715  movzx   eax, word ptr [rbx+124h]
0x14002371c  imul    eax, edx
0x14002371f  lea     edx, [rax+rcx]
0x140023722  cmp     edx, eax
0x140023724  jb      loc_14002391F
0x14002372a  mov     eax, edx
0x14002372c  mov     qword ptr [rsp+0A8h+FileSizes.FileSize], rax
0x140023731  mov     qword ptr [rsp+0A8h+FileSizes.AllocationSize], rax
0x140023736  mov     rax, cs:FatMaxLarge
0x14002373d  mov     qword ptr [rsp+0A8h+FileSizes.ValidDataLength], rax
0x140023742  mov     rcx, [rbx+2D8h]; int
0x140023749  lea     rdx, [rsp+0A8h+FileSizes]; int
0x14002374e  cmp     [rcx+30h], r15
0x140023752  jnz     short loc_14002376F
0x140023754  mov     [rsp+0A8h+var_88], rbx; PVOID
0x140023759  lea     r9, qword_140017DB0; int
0x140023760  mov     edi, 1
0x140023765  mov     r8b, dil; int
0x140023768  call    FatInitializeCacheMap
0x14002376d  jmp     short loc_140023780
0x14002376f  call    cs:__imp_CcSetFileSizes
0x140023776  nop     dword ptr [rax+rax+00h]
0x14002377b  mov     edi, 1
0x140023780  cmp     byte ptr [rbx+178h], 20h ; ' '
0x140023787  jnz     short loc_1400237C1
0x140023789  mov     ecx, [rbx+16Ch]
0x14002378f  cmp     ecx, 10000h
0x140023795  jbe     short loc_1400237C1
0x140023797  lea     eax, [rcx+0FFFFh]
0x14002379d  cmp     eax, ecx
0x14002379f  jnb     short loc_1400237B6
0x1400237a1  mov     ecx, 0C0000102h; Status
0x1400237a6  mov     [r13+48h], ecx
0x1400237aa  call    cs:__imp_ExRaiseStatus
0x1400237b6  shr     eax, 10h
0x1400237b9  mov     [rbx+0D8h], eax
0x1400237bf  jmp     short loc_1400237C9
0x1400237c1  mov     [rbx+0D8h], edi
0x1400237c7  mov     eax, edi
0x1400237c9  lea     rsi, [rax+rax*2]
0x1400237cd  shl     rsi, 2
0x1400237d1  mov     r8d, 57746146h; Tag
0x1400237d7  mov     rdx, rsi; NumberOfBytes
0x1400237da  mov     ecx, 411h; PoolType
0x1400237df  call    cs:__imp_ExAllocatePoolWithTag
0x1400237e6  nop     dword ptr [rax+rax+00h]
0x1400237eb  mov     r14, rax
0x1400237ee  cmp     cs:ExPoolZeroingNativelySupported, r15b
0x1400237f5  jnz     short loc_140023809
0x1400237f7  test    rax, rax
0x1400237fa  jz      short loc_140023809
0x1400237fc  mov     r8, rsi; Size
0x1400237ff  xor     edx, edx; Val
0x140023801  mov     rcx, rax; void *
0x140023804  call    memset
0x140023809  mov     [rbx+0E0h], r14
0x140023810  lea     r14, [rbx+1C0h]
0x140023817  xor     r8d, r8d; SizeOfBitMap
0x14002381a  xor     edx, edx; BitMapBuffer
0x14002381c  mov     rcx, r14; BitMapHeader
0x14002381f  call    cs:__imp_RtlInitializeBitMap
0x140023826  nop     dword ptr [rax+rax+00h]
0x14002382b  mov     esi, 2
0x140023830  cmp     [rbx+0D8h], edi
0x140023836  jbe     short loc_140023881
0x140023838  mov     r9d, [rbx+16Ch]
0x14002383f  add     r9d, edi; int
0x140023842  mov     [rsp+0A8h+BitMapBuffer], r15; BitMapBuffer
0x140023847  mov     [rsp+0A8h+var_80], r15; __int64
  ... truncated ...
```
