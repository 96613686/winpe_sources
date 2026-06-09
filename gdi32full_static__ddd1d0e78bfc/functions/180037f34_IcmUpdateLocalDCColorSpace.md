# IcmUpdateLocalDCColorSpace

- ea: `0x180037f34`
- end: `0x180038391`
- name: `IcmUpdateLocalDCColorSpace`
- size: `1117`
- prototype: `__int64 __fastcall(HDC hdc)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x180037e48`
- `0x180078770`

## callees

- `0x180037f34`
- `0x18003888c`
- `0x180039d00`
- `0x18003a6f8`
- `0x18003b834`
- `0x1800446d0`
- `0x180064f9c`
- `0x180070288`
- `0x180074e68`
- `0x18007f800`
- `0x18008dc14`
- `0x1800a8010`

## import_xrefs

- `GDI32!pGdiSharedMemory` at `0x1800381df`
- `ntdll!RtlFreeHeap` at `0x180038286`
- `ntdll!RtlFreeHeap` at `0x180038286`
- `ntdll!RtlEnterCriticalSection` at `0x180037fbb`
- `ntdll!RtlEnterCriticalSection` at `0x180037fbb`
- `ntdll!RtlLeaveCriticalSection` at `0x180037fdd`
- `ntdll!RtlLeaveCriticalSection` at `0x180037fdd`
- `win32u!NtGdiDeleteColorSpace` at `0x18003834a`
- `win32u!NtGdiDeleteColorSpace` at `0x18003834a`
- `win32u!NtGdiSetIcmMode` at `0x18003818f`
- `win32u!NtGdiSetIcmMode` at `0x18003818f`

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
0x180037f34  mov     [rsp-8+arg_10], rbx
0x180037f39  push    rbp
0x180037f3a  push    rsi
0x180037f3b  push    rdi
0x180037f3c  push    r12
0x180037f3e  push    r13
0x180037f40  push    r14
0x180037f42  push    r15
0x180037f44  lea     rbp, [rsp-160h]
0x180037f4c  sub     rsp, 260h
0x180037f53  mov     rax, cs:__security_cookie
0x180037f5a  xor     rax, rsp
0x180037f5d  mov     [rbp+190h+var_40], rax
0x180037f64  mov     rdi, [rdx+108h]
0x180037f6b  xor     r10d, r10d
0x180037f6e  mov     rsi, [rdx+90h]
0x180037f75  mov     r14, rdx
0x180037f78  mov     r12, rcx
0x180037f7b  mov     r13d, r10d
0x180037f7e  mov     r15d, 104h
0x180037f84  cmp     [rdi+30h], r10
0x180037f88  jz      short loc_180037F9A
0x180037f8a  test    dword ptr [rdx+98h], 100000h
0x180037f94  jz      loc_1800381C6
0x180037f9a  mov     rcx, r14
0x180037f9d  mov     [rsp+290h+var_250], r10w
0x180037fa3  mov     rbx, r10
0x180037fa6  mov     [rsp+290h+var_260], r10d
0x180037fab  call    bDIBSectionSelected
0x180037fb0  test    eax, eax
0x180037fb2  jz      short loc_180037FF1
0x180037fb4  lea     rcx, semColorSpaceCache; CriticalSection
0x180037fbb  call    cs:__imp_RtlEnterCriticalSection
0x180037fc2  nop     dword ptr [rax+rax+00h]
0x180037fc7  mov     rax, [r14+18h]
0x180037fcb  test    rax, rax
0x180037fce  jz      short loc_180037FD6
0x180037fd0  inc     dword ptr [rax+1Ch]
0x180037fd3  mov     rbx, rax
0x180037fd6  lea     rcx, semColorSpaceCache; CriticalSection
0x180037fdd  call    cs:__imp_RtlLeaveCriticalSection
0x180037fe4  nop     dword ptr [rax+rax+00h]
0x180037fe9  xor     r10d, r10d
0x180037fec  jmp     loc_180038130
0x180037ff1  test    byte ptr [rdx], 2
0x180037ff4  jz      short loc_180038043
0x180037ff6  cmp     cs:?PrimaryDisplayProfile@@3PAGA, r10w; ushort near * PrimaryDisplayProfile
0x180037ffe  jz      short loc_180038043
0x180038000  mov     eax, 7FFFFFFEh
0x180038005  lea     rdx, ?PrimaryDisplayProfile@@3PAGA; ushort near * PrimaryDisplayProfile
0x18003800c  mov     r8, r15
0x18003800f  lea     r9, [rsp+290h+var_250]
0x180038014  test    rax, rax
0x180038017  jz      short loc_180038036
0x180038019  movzx   ecx, word ptr [rdx]
0x18003801c  test    cx, cx
0x18003801f  jz      short loc_180038036
0x180038021  mov     [r9], cx
0x180038025  add     rdx, 2
0x180038029  add     r9, 2
0x18003802d  dec     rax
0x180038030  sub     r8, 1
0x180038034  jnz     short loc_180038014
0x180038036  test    r8, r8
0x180038039  lea     rcx, [r9-2]
0x18003803d  cmovnz  rcx, r9
0x180038041  jmp     short loc_1800380B3
0x180038043  lea     r8, [rsp+290h+var_260]
0x180038048  mov     rcx, r12
0x18003804b  lea     rdx, [rsp+290h+var_250]
0x180038050  call    GetDefaultDestinationProfile
0x180038055  xor     r10d, r10d
0x180038058  test    eax, eax
0x18003805a  jz      short loc_1800380B9
0x18003805c  test    byte ptr [r14], 2
0x180038060  jz      loc_1800380E6
0x180038066  cmp     cs:?PrimaryDisplayProfile@@3PAGA, r10w; ushort near * PrimaryDisplayProfile
0x18003806e  jnz     short loc_1800380E6
0x180038070  mov     eax, 7FFFFFFEh
0x180038075  lea     rcx, [rsp+290h+var_250]
0x18003807a  mov     r8, r15
0x18003807d  lea     rdx, ?PrimaryDisplayProfile@@3PAGA; ushort near * PrimaryDisplayProfile
0x180038084  test    rax, rax
0x180038087  jz      short loc_1800380A8
0x180038089  movzx   r9d, word ptr [rcx]
0x18003808d  test    r9w, r9w
0x180038091  jz      short loc_1800380A8
0x180038093  mov     [rdx], r9w
0x180038097  add     rcx, 2
0x18003809b  add     rdx, 2
0x18003809f  dec     rax
0x1800380a2  sub     r8, 1
0x1800380a6  jnz     short loc_180038084
0x1800380a8  test    r8, r8
0x1800380ab  lea     rcx, [rdx-2]
0x1800380af  cmovnz  rcx, rdx
0x1800380b3  mov     [rcx], r10w
0x1800380b7  jnz     short loc_180038130
0x1800380b9  xor     eax, eax
0x1800380bb  mov     rcx, [rbp+190h+var_40]
0x1800380c2  xor     rcx, rsp; StackCookie
0x1800380c5  call    __security_check_cookie
0x1800380ca  mov     rbx, [rsp+290h+arg_10]
0x1800380d2  add     rsp, 260h
0x1800380d9  pop     r15
0x1800380db  pop     r14
0x1800380dd  pop     r13
0x1800380df  pop     r12
0x1800380e1  pop     rdi
0x1800380e2  pop     rsi
0x1800380e3  pop     rbp
0x1800380e4  retn
0x1800380e6  mov     eax, 7FFFFFFEh
0x1800380eb  lea     rcx, [rsp+290h+var_250]
0x1800380f0  mov     rdx, r15
0x1800380f3  lea     r8, [rdi+78h]
0x1800380f7  test    rax, rax
0x1800380fa  jz      short loc_18003811B
0x1800380fc  movzx   r9d, word ptr [rcx]
0x180038100  test    r9w, r9w
0x180038104  jz      short loc_18003811B
0x180038106  mov     [r8], r9w
0x18003810a  add     rcx, 2
0x18003810e  add     r8, 2
0x180038112  dec     rax
0x180038115  sub     rdx, 1
0x180038119  jnz     short loc_1800380F7
0x18003811b  test    rdx, rdx
0x18003811e  lea     rcx, [r8-2]
0x180038122  cmovnz  rcx, r8
0x180038126  mov     [rcx], r10w
0x18003812a  jz      short loc_1800380B9
0x18003812c  or      dword ptr [rdi+20h], 3
0x180038130  mov     r15d, r10d
0x180038133  cmp     [rsp+290h+var_250], r10w
0x180038139  jnz     short loc_180038144
0x18003813b  test    rbx, rbx
0x18003813e  jz      loc_180038389
0x180038144  test    rbx, rbx
0x180038147  jnz     short loc_18003816B
0x180038149  mov     r9d, [rsp+290h+var_260]
0x18003814e  lea     rdx, [rsp+290h+var_250]
0x180038153  mov     r8d, [rdi+60h]
0x180038157  mov     rcx, r12
0x18003815a  call    IcmGetOrCreateColorSpaceByName
0x18003815f  mov     rbx, rax
0x180038162  test    rax, rax
0x180038165  jz      loc_180038389
0x18003816b  cmp     rbx, [rdi+30h]
0x18003816f  jnz     short loc_180038183
0x180038171  xor     r8d, r8d
0x180038174  mov     rdx, rbx
0x180038177  xor     ecx, ecx
0x180038179  call    IcmReleaseColorSpace
0x18003817e  xor     r10d, r10d
0x180038181  jmp     short loc_1800381C6
0x180038183  mov     r8d, [rbx+2Ch]
0x180038187  mov     edx, 4
0x18003818c  mov     rcx, r12
0x18003818f  call    cs:__imp_NtGdiSetIcmMode
0x180038196  nop     dword ptr [rax+rax+00h]
0x18003819b  xor     r10d, r10d
0x18003819e  test    eax, eax
0x1800381a0  jz      loc_18003837C
0x1800381a6  mov     rdx, [rdi+30h]
0x1800381aa  test    rdx, rdx
0x1800381ad  jz      short loc_1800381BC
0x1800381af  xor     r8d, r8d
0x1800381b2  xor     ecx, ecx
0x1800381b4  call    IcmReleaseColorSpace
0x1800381b9  xor     r10d, r10d
0x1800381bc  mov     [rdi+30h], rbx
0x1800381c0  mov     r13d, 1
0x1800381c6  mov     r15d, 1
0x1800381cc  test    rsi, rsi
0x1800381cf  jz      loc_180038363
0x1800381d5  cmp     [rsi+30h], r10
0x1800381d9  jz      loc_180038363
0x1800381df  mov     rax, cs:__imp_pGdiSharedMemory
0x1800381e6  mov     rcx, [rax]
0x1800381e9  mov     rax, [rcx+180150h]
0x1800381f0  cmp     [r14+10h], rax
0x1800381f4  jnz     loc_180038363
0x1800381fa  cmp     [rdi+58h], r10
0x1800381fe  jnz     loc_180038363
0x180038204  mov     qword ptr [rdi+58h], 0FFFFFFFFFFFFFFFFh
0x18003820c  mov     rbx, r10
0x18003820f  mov     [rsp+290h+var_250], r10w
0x180038215  mov     rax, [rsi+70h]
0x180038219  mov     [rsp+290h+P], rbx
0x18003821e  mov     [rsp+290h+var_260], r10d
0x180038223  test    rax, rax
0x180038226  jnz     short loc_180038243
0x180038228  mov     rcx, [rsi+30h]
0x18003822c  lea     r8, [rsp+290h+P]
0x180038231  call    pdmwGetDefaultDevMode
0x180038236  mov     rbx, [rsp+290h+P]
0x18003823b  xor     r10d, r10d
0x18003823e  test    rax, rax
0x180038241  jz      short loc_18003826F
0x180038243  lea     rcx, [rsp+290h+var_260]
0x180038248  mov     r8, rax
0x18003824b  mov     [rsp+290h+var_270], rcx
0x180038250  lea     r9, [rsp+290h+var_250]
0x180038255  mov     rcx, rsi
0x180038258  mov     edx, 1
0x18003825d  call    IcmAskDriverForColorProfile
0x180038262  xor     r10d, r10d
0x180038265  test    eax, eax
0x180038267  jg      short loc_18003826F
0x180038269  mov     [rsp+290h+var_250], r10w
0x18003826f  test    rbx, rbx
0x180038272  jz      short loc_180038295
0x180038274  mov     rcx, gs:60h
0x18003827d  mov     r8, rbx; P
0x180038280  xor     edx, edx; Flags
0x180038282  mov     rcx, [rcx+30h]; HeapHandle
0x180038286  call    cs:__imp_RtlFreeHeap
0x18003828d  nop     dword ptr [rax+rax+00h]
0x180038292  xor     r10d, r10d
0x180038295  cmp     [rsp+290h+var_250], r10w
0x18003829b  jnz     short loc_1800382EC
0x18003829d  cmp     dword ptr [rdi+60h], 4
0x1800382a1  jz      loc_180038363
0x1800382a7  mov     rax, cs:fpGetStandardColorSpaceProfileW
0x1800382ae  lea     r9, [rsp+290h+P]
0x1800382b3  mov     ebx, 104h
0x1800382b8  lea     r8, [rsp+290h+var_250]
0x1800382bd  mov     edx, 73524742h
0x1800382c2  mov     dword ptr [rsp+290h+P], ebx
0x1800382c6  xor     ecx, ecx
0x1800382c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382cd  test    eax, eax
0x1800382cf  jnz     short loc_1800382EC
0x1800382d1  lea     r8, aSrgbColorSpace; "sRGB Color Space Profile.icm"
0x1800382d8  mov     edx, ebx; unsigned __int64
0x1800382da  lea     rcx, [rsp+290h+var_250]; unsigned __int16 *
0x1800382df  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800382e4  test    eax, eax
0x1800382e6  js      loc_1800380B9
0x1800382ec  mov     r9d, [rsp+290h+var_260]
0x1800382f1  lea     rdx, [rsp+290h+var_250]
0x1800382f6  mov     r8d, [rdi+60h]
0x1800382fa  mov     rcx, r12
0x1800382fd  call    IcmGetOrCreateColorSpaceByName
0x180038302  mov     rbx, rax
0x180038305  test    rax, rax
0x180038308  jz      short loc_180038363
0x18003830a  lea     rcx, [rax+58h]
0x18003830e  xor     edx, edx
0x180038310  call    CreateColorSpaceInternalW
0x180038315  mov     rsi, rax
0x180038318  test    rax, rax
0x18003831b  jz      short loc_180038356
0x18003831d  mov     r8, rbx
0x180038320  mov     rdx, rax
0x180038323  mov     rcx, r12; hdc
0x180038326  call    IcmSetSourceColorSpace
0x18003832b  test    rax, rax
0x18003832e  jz      short loc_180038347
0x180038330  xor     r8d, r8d
0x180038333  mov     rdx, rbx
0x180038336  xor     ecx, ecx
0x180038338  call    IcmReleaseColorSpace
0x18003833d  or      dword ptr [rdi+20h], 4
0x180038341  mov     [rdi+58h], rsi
0x180038345  jmp     short loc_180038363
0x180038347  mov     rcx, rsi
0x18003834a  call    cs:__imp_NtGdiDeleteColorSpace
0x180038351  nop     dword ptr [rax+rax+00h]
0x180038356  xor     r8d, r8d
0x180038359  mov     rdx, rbx
0x18003835c  xor     ecx, ecx
0x18003835e  call    IcmReleaseColorSpace
0x180038363  btr     dword ptr [r14+98h], 14h
0x18003836c  test    r13d, r13d
0x18003836f  jz      short loc_180038389
0x180038371  bts     dword ptr [r14+98h], 11h
0x18003837a  jmp     short loc_180038389
0x18003837c  xor     r8d, r8d
0x18003837f  mov     rdx, rbx
0x180038382  xor     ecx, ecx
0x180038384  call    IcmReleaseColorSpace
0x180038389  mov     eax, r15d
0x18003838c  jmp     loc_1800380BB
```
