# IcmUpdateLocalDCColorSpace

- ea: `0x180032130`
- end: `0x18003256a`
- name: `IcmUpdateLocalDCColorSpace`
- size: `1082`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x180032044`
- `0x180073f20`

## callees

- `0x180032130`
- `0x180032a24`
- `0x180033d30`
- `0x1800346b8`
- `0x1800356cc`
- `0x18003a970`
- `0x180060710`
- `0x18006b93c`
- `0x1800708c0`
- `0x18007ac50`
- `0x1800886e8`
- `0x1800a5010`

## import_xrefs

- `GDI32!pGdiSharedMemory` at `0x1800323c4`
- `ntdll!RtlFreeHeap` at `0x18003246b`
- `ntdll!RtlFreeHeap` at `0x18003246b`
- `ntdll!RtlEnterCriticalSection` at `0x1800321b7`
- `ntdll!RtlEnterCriticalSection` at `0x1800321b7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800321d3`
- `ntdll!RtlLeaveCriticalSection` at `0x1800321d3`
- `win32u!NtGdiDeleteColorSpace` at `0x180032529`
- `win32u!NtGdiDeleteColorSpace` at `0x180032529`
- `win32u!NtGdiSetIcmMode` at `0x18003237a`
- `win32u!NtGdiSetIcmMode` at `0x18003237a`

## pseudocode

```c
__int64 __fastcall IcmUpdateLocalDCColorSpace(HDC hdc, __int64 a2)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // r14
  int v6; // r13d
  __int64 ColorSpaceByName; // rbx
  _BYTE *v8; // rdx
  unsigned int v9; // r10d
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned __int16 near **v12; // rdx
  __int64 v13; // r8
  unsigned __int16 *v14; // r9
  bool v15; // zf
  unsigned __int16 *v16; // rcx
  int DefaultDestinationProfile; // eax
  __int64 v18; // rax
  unsigned __int16 *v19; // rcx
  __int64 v20; // r8
  unsigned __int16 near **v21; // rdx
  __int64 v23; // rax
  unsigned __int16 *v24; // rcx
  __int64 v25; // rdx
  _WORD *v26; // r8
  _WORD *v27; // rcx
  unsigned int v28; // r15d
  PVOID v29; // rbx
  __int64 DefaultDevMode; // rax
  __int64 v31; // rax
  __int64 v32; // rbx
  __int64 ColorSpaceInternalW; // rsi
  unsigned int v34; // [rsp+30h] [rbp-D0h] BYREF
  PVOID P; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v36[264]; // [rsp+40h] [rbp-C0h] BYREF

  v2 = *(_QWORD *)(a2 + 264);
  v3 = *(_QWORD *)(a2 + 144);
  v4 = a2;
  v6 = 0;
  if ( *(_QWORD *)(v2 + 48) && (*(_DWORD *)(a2 + 152) & 0x100000) == 0 )
    goto LABEL_45;
  v36[0] = 0;
  ColorSpaceByName = 0;
  v34 = 0;
  if ( (unsigned int)bDIBSectionSelected(a2) )
  {
    RtlEnterCriticalSection(&semColorSpaceCache);
    v10 = *(_QWORD *)(v4 + 24);
    if ( v10 )
    {
      ++*(_DWORD *)(v10 + 28);
      ColorSpaceByName = v10;
    }
    RtlLeaveCriticalSection(&semColorSpaceCache);
    v9 = 0;
    goto LABEL_35;
  }
  if ( (*v8 & 2) == 0 || (_WORD)PrimaryDisplayProfile == (_WORD)v9 )
  {
    DefaultDestinationProfile = GetDefaultDestinationProfile(hdc, v36, &v34);
    v9 = 0;
    if ( !DefaultDestinationProfile )
      return 0;
    if ( (*(_BYTE *)v4 & 2) == 0 || (_WORD)PrimaryDisplayProfile )
    {
      v23 = 2147483646;
      v24 = v36;
      v25 = 260;
      v26 = (_WORD *)(v2 + 120);
      do
      {
        if ( !v23 )
          break;
        if ( !*v24 )
          break;
        *v26++ = *v24++;
        --v23;
        --v25;
      }
      while ( v25 );
      v27 = v26 - 1;
      if ( v25 )
        v27 = v26;
      *v27 = 0;
      if ( !v25 )
        return 0;
      *(_DWORD *)(v2 + 32) |= 3u;
      goto LABEL_35;
    }
    v18 = 2147483646;
    v19 = v36;
    v20 = 260;
    v21 = &PrimaryDisplayProfile;
    do
    {
      if ( !v18 )
        break;
      if ( !*v19 )
        break;
      *(_WORD *)v21 = *v19++;
      v21 = (unsigned __int16 near **)((char *)v21 + 2);
      --v18;
      --v20;
    }
    while ( v20 );
    v15 = v20 == 0;
    v16 = (unsigned __int16 *)v21 - 1;
    if ( v20 )
      v16 = (unsigned __int16 *)v21;
  }
  else
  {
    v11 = 2147483646;
    v12 = &PrimaryDisplayProfile;
    v13 = 260;
    v14 = v36;
    do
    {
      if ( !v11 )
        break;
      if ( !*(_WORD *)v12 )
        break;
      *v14 = *(_WORD *)v12;
      v12 = (unsigned __int16 near **)((char *)v12 + 2);
      ++v14;
      --v11;
      --v13;
    }
    while ( v13 );
    v15 = v13 == 0;
    v16 = v14 - 1;
    if ( v13 )
      v16 = v14;
  }
  *v16 = v9;
  if ( v15 )
    return 0;
LABEL_35:
  v28 = v9;
  if ( v36[0] == (_WORD)v9 && !ColorSpaceByName )
    return v28;
  if ( !ColorSpaceByName )
  {
    ColorSpaceByName = IcmGetOrCreateColorSpaceByName(hdc, v36, *(unsigned int *)(v2 + 96), v34);
    if ( !ColorSpaceByName )
      return v28;
  }
  if ( ColorSpaceByName == *(_QWORD *)(v2 + 48) )
  {
    IcmReleaseColorSpace(0, ColorSpaceByName, 0);
LABEL_45:
    v28 = 1;
    if ( !v3
      || !*(_QWORD *)(v3 + 48)
      || *(_QWORD *)(v4 + 16) != *(_QWORD *)(pGdiSharedMemory + 1573200LL)
      || *(_QWORD *)(v2 + 88) )
    {
      goto LABEL_65;
    }
    *(_QWORD *)(v2 + 88) = -1;
    v29 = 0;
    v36[0] = 0;
    DefaultDevMode = *(_QWORD *)(v3 + 112);
    P = 0;
    v34 = 0;
    if ( DefaultDevMode
      || (DefaultDevMode = pdmwGetDefaultDevMode(*(_QWORD *)(v3 + 48), a2, &P), v29 = P, DefaultDevMode) )
    {
      if ( (int)IcmAskDriverForColorProfile(v3, 1, DefaultDevMode, v36, &v34) <= 0 )
        v36[0] = 0;
    }
    if ( v29 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v29);
    if ( v36[0] )
      goto LABEL_59;
    if ( *(_DWORD *)(v2 + 96) == 4 )
      goto LABEL_65;
    LODWORD(P) = 260;
    if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, __int64, unsigned __int16 *, PVOID *))fpGetStandardColorSpaceProfileW)(
                         0,
                         1934772034,
                         v36,
                         &P)
      || (int)StringCchCopyW(v36, 0x104u, L"sRGB Color Space Profile.icm") >= 0 )
    {
LABEL_59:
      v31 = IcmGetOrCreateColorSpaceByName(hdc, v36, *(unsigned int *)(v2 + 96), v34);
      v32 = v31;
      if ( !v31 )
        goto LABEL_65;
      ColorSpaceInternalW = CreateColorSpaceInternalW(v31 + 88, 0);
      if ( ColorSpaceInternalW )
      {
        if ( IcmSetSourceColorSpace(hdc) )
        {
          IcmReleaseColorSpace(0, v32, 0);
          *(_DWORD *)(v2 + 32) |= 4u;
          *(_QWORD *)(v2 + 88) = ColorSpaceInternalW;
          goto LABEL_65;
        }
        NtGdiDeleteColorSpace(ColorSpaceInternalW);
      }
      IcmReleaseColorSpace(0, v32, 0);
LABEL_65:
      *(_DWORD *)(v4 + 152) &= ~0x100000u;
      if ( v6 )
        *(_DWORD *)(v4 + 152) |= 0x20000u;
      return v28;
    }
    return 0;
  }
  if ( (unsigned int)NtGdiSetIcmMode(hdc, 4, *(unsigned int *)(ColorSpaceByName + 44)) )
  {
    a2 = *(_QWORD *)(v2 + 48);
    if ( a2 )
      IcmReleaseColorSpace(0, a2, 0);
    *(_QWORD *)(v2 + 48) = ColorSpaceByName;
    v6 = 1;
    goto LABEL_45;
  }
  IcmReleaseColorSpace(0, ColorSpaceByName, 0);
  return v28;
}

```

## disassembly

```asm
0x180032130  mov     [rsp-8+arg_10], rbx
0x180032135  push    rbp
0x180032136  push    rsi
0x180032137  push    rdi
0x180032138  push    r12
0x18003213a  push    r13
0x18003213c  push    r14
0x18003213e  push    r15
0x180032140  lea     rbp, [rsp-160h]
0x180032148  sub     rsp, 260h
0x18003214f  mov     rax, cs:__security_cookie
0x180032156  xor     rax, rsp
0x180032159  mov     [rbp+190h+var_40], rax
0x180032160  mov     rdi, [rdx+108h]
0x180032167  xor     r10d, r10d
0x18003216a  mov     rsi, [rdx+90h]
0x180032171  mov     r14, rdx
0x180032174  mov     r12, rcx
0x180032177  mov     r13d, r10d
0x18003217a  mov     r15d, 104h
0x180032180  cmp     [rdi+30h], r10
0x180032184  jz      short loc_180032196
0x180032186  test    dword ptr [rdx+98h], 100000h
0x180032190  jz      loc_1800323AB
0x180032196  mov     rcx, r14
0x180032199  mov     [rsp+290h+var_250], r10w
0x18003219f  mov     rbx, r10
0x1800321a2  mov     [rsp+290h+var_260], r10d
0x1800321a7  call    bDIBSectionSelected
0x1800321ac  test    eax, eax
0x1800321ae  jz      short loc_1800321E1
0x1800321b0  lea     rcx, semColorSpaceCache; CriticalSection
0x1800321b7  call    cs:__imp_RtlEnterCriticalSection
0x1800321bd  mov     rax, [r14+18h]
0x1800321c1  test    rax, rax
0x1800321c4  jz      short loc_1800321CC
0x1800321c6  inc     dword ptr [rax+1Ch]
0x1800321c9  mov     rbx, rax
0x1800321cc  lea     rcx, semColorSpaceCache; CriticalSection
0x1800321d3  call    cs:__imp_RtlLeaveCriticalSection
0x1800321d9  xor     r10d, r10d
0x1800321dc  jmp     loc_18003231B
0x1800321e1  test    byte ptr [rdx], 2
0x1800321e4  jz      short loc_180032233
0x1800321e6  cmp     cs:?PrimaryDisplayProfile@@3PAGA, r10w; ushort near * PrimaryDisplayProfile
0x1800321ee  jz      short loc_180032233
0x1800321f0  mov     eax, 7FFFFFFEh
0x1800321f5  lea     rdx, ?PrimaryDisplayProfile@@3PAGA; ushort near * PrimaryDisplayProfile
0x1800321fc  mov     r8, r15
0x1800321ff  lea     r9, [rsp+290h+var_250]
0x180032204  test    rax, rax
0x180032207  jz      short loc_180032226
0x180032209  movzx   ecx, word ptr [rdx]
0x18003220c  test    cx, cx
0x18003220f  jz      short loc_180032226
0x180032211  mov     [r9], cx
0x180032215  add     rdx, 2
0x180032219  add     r9, 2
0x18003221d  dec     rax
0x180032220  sub     r8, 1
0x180032224  jnz     short loc_180032204
0x180032226  test    r8, r8
0x180032229  lea     rcx, [r9-2]
0x18003222d  cmovnz  rcx, r9
0x180032231  jmp     short loc_18003229F
0x180032233  lea     r8, [rsp+290h+var_260]
0x180032238  mov     rcx, r12
0x18003223b  lea     rdx, [rsp+290h+var_250]
0x180032240  call    GetDefaultDestinationProfile
0x180032245  xor     r10d, r10d
0x180032248  test    eax, eax
0x18003224a  jz      short loc_1800322A5
0x18003224c  test    byte ptr [r14], 2
0x180032250  jz      short loc_1800322D1
0x180032252  cmp     cs:?PrimaryDisplayProfile@@3PAGA, r10w; ushort near * PrimaryDisplayProfile
0x18003225a  jnz     short loc_1800322D1
0x18003225c  mov     eax, 7FFFFFFEh
0x180032261  lea     rcx, [rsp+290h+var_250]
0x180032266  mov     r8, r15
0x180032269  lea     rdx, ?PrimaryDisplayProfile@@3PAGA; ushort near * PrimaryDisplayProfile
0x180032270  test    rax, rax
0x180032273  jz      short loc_180032294
0x180032275  movzx   r9d, word ptr [rcx]
0x180032279  test    r9w, r9w
0x18003227d  jz      short loc_180032294
0x18003227f  mov     [rdx], r9w
0x180032283  add     rcx, 2
0x180032287  add     rdx, 2
0x18003228b  dec     rax
0x18003228e  sub     r8, 1
0x180032292  jnz     short loc_180032270
0x180032294  test    r8, r8
0x180032297  lea     rcx, [rdx-2]
0x18003229b  cmovnz  rcx, rdx
0x18003229f  mov     [rcx], r10w
0x1800322a3  jnz     short loc_18003231B
0x1800322a5  xor     eax, eax
0x1800322a7  mov     rcx, [rbp+190h+var_40]
0x1800322ae  xor     rcx, rsp; StackCookie
0x1800322b1  call    __security_check_cookie
0x1800322b6  mov     rbx, [rsp+290h+arg_10]
0x1800322be  add     rsp, 260h
0x1800322c5  pop     r15
0x1800322c7  pop     r14
0x1800322c9  pop     r13
0x1800322cb  pop     r12
0x1800322cd  pop     rdi
0x1800322ce  pop     rsi
0x1800322cf  pop     rbp
0x1800322d0  retn
0x1800322d1  mov     eax, 7FFFFFFEh
0x1800322d6  lea     rcx, [rsp+290h+var_250]
0x1800322db  mov     rdx, r15
0x1800322de  lea     r8, [rdi+78h]
0x1800322e2  test    rax, rax
0x1800322e5  jz      short loc_180032306
0x1800322e7  movzx   r9d, word ptr [rcx]
0x1800322eb  test    r9w, r9w
0x1800322ef  jz      short loc_180032306
0x1800322f1  mov     [r8], r9w
0x1800322f5  add     rcx, 2
0x1800322f9  add     r8, 2
0x1800322fd  dec     rax
0x180032300  sub     rdx, 1
0x180032304  jnz     short loc_1800322E2
0x180032306  test    rdx, rdx
0x180032309  lea     rcx, [r8-2]
0x18003230d  cmovnz  rcx, r8
0x180032311  mov     [rcx], r10w
0x180032315  jz      short loc_1800322A5
0x180032317  or      dword ptr [rdi+20h], 3
0x18003231b  mov     r15d, r10d
0x18003231e  cmp     [rsp+290h+var_250], r10w
0x180032324  jnz     short loc_18003232F
0x180032326  test    rbx, rbx
0x180032329  jz      loc_180032562
0x18003232f  test    rbx, rbx
0x180032332  jnz     short loc_180032356
0x180032334  mov     r9d, [rsp+290h+var_260]
0x180032339  lea     rdx, [rsp+290h+var_250]
0x18003233e  mov     r8d, [rdi+60h]
0x180032342  mov     rcx, r12
0x180032345  call    IcmGetOrCreateColorSpaceByName
0x18003234a  mov     rbx, rax
0x18003234d  test    rax, rax
0x180032350  jz      loc_180032562
0x180032356  cmp     rbx, [rdi+30h]
0x18003235a  jnz     short loc_18003236E
0x18003235c  xor     r8d, r8d
0x18003235f  mov     rdx, rbx
0x180032362  xor     ecx, ecx
0x180032364  call    IcmReleaseColorSpace
0x180032369  xor     r10d, r10d
0x18003236c  jmp     short loc_1800323AB
0x18003236e  mov     r8d, [rbx+2Ch]
0x180032372  mov     edx, 4
0x180032377  mov     rcx, r12
0x18003237a  call    cs:__imp_NtGdiSetIcmMode
0x180032380  xor     r10d, r10d
0x180032383  test    eax, eax
0x180032385  jz      loc_180032555
0x18003238b  mov     rdx, [rdi+30h]
0x18003238f  test    rdx, rdx
0x180032392  jz      short loc_1800323A1
0x180032394  xor     r8d, r8d
0x180032397  xor     ecx, ecx
0x180032399  call    IcmReleaseColorSpace
0x18003239e  xor     r10d, r10d
0x1800323a1  mov     [rdi+30h], rbx
0x1800323a5  mov     r13d, 1
0x1800323ab  mov     r15d, 1
0x1800323b1  test    rsi, rsi
0x1800323b4  jz      loc_18003253C
0x1800323ba  cmp     [rsi+30h], r10
0x1800323be  jz      loc_18003253C
0x1800323c4  mov     rax, cs:__imp_pGdiSharedMemory
0x1800323cb  mov     rcx, [rax]
0x1800323ce  mov     rax, [rcx+180150h]
0x1800323d5  cmp     [r14+10h], rax
0x1800323d9  jnz     loc_18003253C
0x1800323df  cmp     [rdi+58h], r10
0x1800323e3  jnz     loc_18003253C
0x1800323e9  mov     qword ptr [rdi+58h], 0FFFFFFFFFFFFFFFFh
0x1800323f1  mov     rbx, r10
0x1800323f4  mov     [rsp+290h+var_250], r10w
0x1800323fa  mov     rax, [rsi+70h]
0x1800323fe  mov     [rsp+290h+P], rbx
0x180032403  mov     [rsp+290h+var_260], r10d
0x180032408  test    rax, rax
0x18003240b  jnz     short loc_180032428
0x18003240d  mov     rcx, [rsi+30h]
0x180032411  lea     r8, [rsp+290h+P]
0x180032416  call    pdmwGetDefaultDevMode
0x18003241b  mov     rbx, [rsp+290h+P]
0x180032420  xor     r10d, r10d
0x180032423  test    rax, rax
0x180032426  jz      short loc_180032454
0x180032428  lea     rcx, [rsp+290h+var_260]
0x18003242d  mov     r8, rax
0x180032430  mov     [rsp+290h+var_270], rcx
0x180032435  lea     r9, [rsp+290h+var_250]
0x18003243a  mov     rcx, rsi
0x18003243d  mov     edx, 1
0x180032442  call    IcmAskDriverForColorProfile
0x180032447  xor     r10d, r10d
0x18003244a  test    eax, eax
0x18003244c  jg      short loc_180032454
0x18003244e  mov     [rsp+290h+var_250], r10w
0x180032454  test    rbx, rbx
0x180032457  jz      short loc_180032474
0x180032459  mov     rcx, gs:60h
0x180032462  mov     r8, rbx; P
0x180032465  xor     edx, edx; Flags
0x180032467  mov     rcx, [rcx+30h]; HeapHandle
0x18003246b  call    cs:__imp_RtlFreeHeap
0x180032471  xor     r10d, r10d
0x180032474  cmp     [rsp+290h+var_250], r10w
0x18003247a  jnz     short loc_1800324CB
0x18003247c  cmp     dword ptr [rdi+60h], 4
0x180032480  jz      loc_18003253C
0x180032486  mov     rax, cs:fpGetStandardColorSpaceProfileW
0x18003248d  lea     r9, [rsp+290h+P]
0x180032492  mov     ebx, 104h
0x180032497  lea     r8, [rsp+290h+var_250]
0x18003249c  mov     edx, 73524742h
0x1800324a1  mov     dword ptr [rsp+290h+P], ebx
0x1800324a5  xor     ecx, ecx
0x1800324a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800324ac  test    eax, eax
0x1800324ae  jnz     short loc_1800324CB
0x1800324b0  lea     r8, aSrgbColorSpace; "sRGB Color Space Profile.icm"
0x1800324b7  mov     edx, ebx; unsigned __int64
0x1800324b9  lea     rcx, [rsp+290h+var_250]; unsigned __int16 *
0x1800324be  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800324c3  test    eax, eax
0x1800324c5  js      loc_1800322A5
0x1800324cb  mov     r9d, [rsp+290h+var_260]
0x1800324d0  lea     rdx, [rsp+290h+var_250]
0x1800324d5  mov     r8d, [rdi+60h]
0x1800324d9  mov     rcx, r12
0x1800324dc  call    IcmGetOrCreateColorSpaceByName
0x1800324e1  mov     rbx, rax
0x1800324e4  test    rax, rax
0x1800324e7  jz      short loc_18003253C
0x1800324e9  lea     rcx, [rax+58h]
0x1800324ed  xor     edx, edx
0x1800324ef  call    CreateColorSpaceInternalW
0x1800324f4  mov     rsi, rax
0x1800324f7  test    rax, rax
0x1800324fa  jz      short loc_18003252F
0x1800324fc  mov     r8, rbx
0x1800324ff  mov     rdx, rax
0x180032502  mov     rcx, r12; hdc
0x180032505  call    IcmSetSourceColorSpace
0x18003250a  test    rax, rax
0x18003250d  jz      short loc_180032526
0x18003250f  xor     r8d, r8d
0x180032512  mov     rdx, rbx
0x180032515  xor     ecx, ecx
0x180032517  call    IcmReleaseColorSpace
0x18003251c  or      dword ptr [rdi+20h], 4
0x180032520  mov     [rdi+58h], rsi
0x180032524  jmp     short loc_18003253C
0x180032526  mov     rcx, rsi
0x180032529  call    cs:__imp_NtGdiDeleteColorSpace
0x18003252f  xor     r8d, r8d
0x180032532  mov     rdx, rbx
0x180032535  xor     ecx, ecx
0x180032537  call    IcmReleaseColorSpace
0x18003253c  btr     dword ptr [r14+98h], 14h
0x180032545  test    r13d, r13d
0x180032548  jz      short loc_180032562
0x18003254a  bts     dword ptr [r14+98h], 11h
0x180032553  jmp     short loc_180032562
0x180032555  xor     r8d, r8d
0x180032558  mov     rdx, rbx
0x18003255b  xor     ecx, ecx
0x18003255d  call    IcmReleaseColorSpace
0x180032562  mov     eax, r15d
0x180032565  jmp     loc_1800322A7
```
