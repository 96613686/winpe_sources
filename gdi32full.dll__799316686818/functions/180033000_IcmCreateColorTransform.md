# IcmCreateColorTransform

- ea: `0x180033000`
- end: `0x180033675`
- name: `IcmCreateColorTransform`
- size: `1653`
- prototype: ``
- caller_count: `6`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180032044`
- `0x18003e184`
- `0x18006a7c4`
- `0x18006b93c`
- `0x1800891e4`
- `0x180089c9c`

## callees

- `0x180033000`
- `0x18003367c`
- `0x180033ec8`
- `0x180033fb4`
- `0x1800341ec`
- `0x180034a60`
- `0x180034c50`
- `0x180034d98`
- `0x1800352b4`
- `0x180039ae4`
- `0x18007ac50`
- `0x18007ba24`
- `0x180086fe8`
- `0x180088aa0`
- `0x180088eb0`
- `0x1800891c8`
- `0x1800a5010`

## import_xrefs

- `GDI32!ghICM` at `0x180033050`
- `ntdll!RtlFreeHeap` at `0x18003317d`
- `ntdll!RtlFreeHeap` at `0x18003319a`
- `ntdll!RtlFreeHeap` at `0x180033668`
- `ntdll!RtlFreeHeap` at `0x18003317d`
- `ntdll!RtlFreeHeap` at `0x18003319a`
- `ntdll!RtlFreeHeap` at `0x180033668`
- `ntdll!RtlAllocateHeap` at `0x1800332a5`
- `ntdll!RtlAllocateHeap` at `0x1800332a5`
- `ntdll!RtlEnterCriticalSection` at `0x1800331cf`
- `ntdll!RtlEnterCriticalSection` at `0x1800332c1`
- `ntdll!RtlEnterCriticalSection` at `0x1800335d6`
- `ntdll!RtlEnterCriticalSection` at `0x1800331cf`
- `ntdll!RtlEnterCriticalSection` at `0x1800332c1`
- `ntdll!RtlEnterCriticalSection` at `0x1800335d6`
- `ntdll!RtlLeaveCriticalSection` at `0x18003320a`
- `ntdll!RtlLeaveCriticalSection` at `0x18003358d`
- `ntdll!RtlLeaveCriticalSection` at `0x18003362c`
- `ntdll!RtlLeaveCriticalSection` at `0x18003320a`
- `ntdll!RtlLeaveCriticalSection` at `0x18003358d`
- `ntdll!RtlLeaveCriticalSection` at `0x18003362c`
- `win32u!NtGdiCreateColorTransform` at `0x1800334b0`
- `win32u!NtGdiCreateColorTransform` at `0x1800334b0`

## pseudocode

```c
__int64 __fastcall IcmCreateColorTransform(void *a1, __int64 a2, PVOID *ColorSpaceByColorSpace, char a4)
{
  bool v4; // zf
  __int64 v7; // r15
  _QWORD *v8; // r14
  _QWORD *Heap; // rdi
  int v10; // r12d
  __int64 result; // rax
  int v12; // ecx
  __int64 v13; // rsi
  PVOID *v14; // rax
  PVOID v15; // rsi
  PVOID v16; // r15
  PVOID *v17; // r15
  _QWORD *v18; // rax
  __int64 ColorTransform; // r12
  __int64 v20; // r13
  int v21; // eax
  int v22; // edx
  unsigned int v23; // r14d
  __int64 v24; // r9
  int v25; // r14d
  __int64 v26; // [rsp+40h] [rbp-C0h] BYREF
  PVOID v27; // [rsp+48h] [rbp-B8h]
  void *v28[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v29; // [rsp+60h] [rbp-A0h]
  void *FileHandle[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v31; // [rsp+80h] [rbp-80h]
  PVOID v32[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v33[16]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v34; // [rsp+B0h] [rbp-50h]
  PVOID P; // [rsp+2F0h] [rbp+1F0h] BYREF
  int v36; // [rsp+2F8h] [rbp+1F8h]
  void *v37[4]; // [rsp+300h] [rbp+200h] BYREF

  v4 = (*(_BYTE *)(a2 + 240) & 0x10) == 0;
  v26 = a2;
  v7 = a2;
  v27 = a1;
  if ( !v4 )
    return -1;
  if ( !ghICM && !(unsigned int)IcmInitialize() )
    return 0;
  v8 = *(_QWORD **)(v7 + 264);
  if ( !v8 )
    return 0;
  Heap = 0;
  v10 = 0;
  if ( !ColorSpaceByColorSpace )
  {
    ColorSpaceByColorSpace = (PVOID *)v8[5];
    if ( !ColorSpaceByColorSpace )
    {
      P = 0;
      v32[0] = 0;
      memset_0(v33, 0, 0x24Cu);
      if ( (unsigned int)IcmGetLogColorSpace(*(_QWORD *)(v7 + 16), v33) )
      {
        IcmGetDefaultCamp(&P);
        IcmGetDefaultGmmp(v34, v32);
        v15 = P;
        v16 = v32[0];
        ColorSpaceByColorSpace = IcmGetColorSpaceByColorSpace(v27, (__int64)v33, 0, (__int64)P, (__int64)v32[0], 0);
        if ( !ColorSpaceByColorSpace )
        {
          ColorSpaceByColorSpace = (PVOID *)IcmCreateColorSpaceByColorSpace(v27, v33, 0, v15, v16, 0);
          v10 = 1;
        }
        if ( v15 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
        if ( v16 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
        v7 = v26;
      }
      v8[5] = ColorSpaceByColorSpace;
      if ( !ColorSpaceByColorSpace )
        return (__int64)Heap;
    }
  }
  v12 = *(_DWORD *)(v7 + 240);
  v13 = 0;
  v14 = (PVOID *)v8[6];
  if ( (v12 & 0x8000) != 0 )
    v13 = v8[7];
  if ( ColorSpaceByColorSpace == v14 && (!v13 || ColorSpaceByColorSpace == (PVOID *)v13) )
    return -1;
  if ( (a4 & 2) != 0 )
  {
    v17 = ColorSpaceByColorSpace;
    ColorSpaceByColorSpace = (PVOID *)v8[6];
  }
  else
  {
    if ( !v14 )
      return (__int64)Heap;
    v17 = (PVOID *)v8[6];
  }
  if ( v10
    || (result = IcmGetColorTransform((_DWORD)v27, (_DWORD)ColorSpaceByColorSpace, (_DWORD)v17, v13, v12 & 2)) == 0 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x48u);
    if ( Heap )
    {
      ColorTransform = 0;
      RtlEnterCriticalSection(&semColorSpaceCache);
      if ( (unsigned int)IcmRealizeColorProfile(ColorSpaceByColorSpace, 1)
        && (unsigned int)IcmRealizeColorProfile(v17, 1) )
      {
        v20 = v26;
        if ( (unsigned int)IcmRealizeColorProfile(v13, 1) )
        {
          v21 = *(_DWORD *)(v26 + 240);
          if ( (v21 & 1) != 0 )
          {
            v37[0] = ColorSpaceByColorSpace[4];
            v22 = 1;
            HIDWORD(P) = *((_DWORD *)ColorSpaceByColorSpace + 10);
            LODWORD(v26) = 1;
            LODWORD(P) = 1;
            *(_OWORD *)&v37[1] = 0;
            if ( v13 )
            {
              v22 = 2;
              v37[1] = *(void **)(v13 + 32);
              v36 = 1;
            }
            v23 = v22 + 1;
            v37[v22] = v17[4];
            if ( (unsigned int)IcmAreIccProfiles(v37, (unsigned int)(v22 + 1), &v26) )
            {
              if ( (_DWORD)v26 )
              {
                v24 = v23;
              }
              else
              {
                v24 = 1;
                LODWORD(P) = -1;
              }
              ColorTransform = ((__int64 (__fastcall *)(void **, _QWORD, PVOID *, __int64, int, _DWORD))fpCreateMultiProfileTransform)(
                                 v37,
                                 v23,
                                 &P,
                                 v24,
                                 65538,
                                 0);
            }
            goto LABEL_71;
          }
          if ( (v21 & 2) != 0 )
          {
            *(_OWORD *)FileHandle = 0;
            v31 = 0;
            *(_OWORD *)v28 = 0;
            v29 = 0;
            memset(v37, 0, sizeof(v37));
            if ( ColorSpaceByColorSpace && *((_DWORD *)ColorSpaceByColorSpace + 169) != 1633907568
              || *((_DWORD *)v17 + 169) != 1633907568
              || v13 && *(_DWORD *)(v13 + 676) != 1633907568 )
            {
              goto LABEL_56;
            }
            if ( *((_DWORD *)ColorSpaceByColorSpace + 12) == 1 )
            {
              if ( !(unsigned int)bMapFileUNICODEClideSide((PCWSTR)ColorSpaceByColorSpace[7], FileHandle, 0) )
                goto LABEL_56;
            }
            else
            {
              if ( *((_DWORD *)ColorSpaceByColorSpace + 12) != 2 )
                goto LABEL_56;
              *(_QWORD *)&v31 = ColorSpaceByColorSpace[7];
              DWORD2(v31) = *((_DWORD *)ColorSpaceByColorSpace + 16);
            }
            if ( *((_DWORD *)v17 + 12) == 1 )
            {
              if ( !(unsigned int)bMapFileUNICODEClideSide((PCWSTR)v17[7], v28, 0) )
                goto LABEL_56;
            }
            else
            {
              if ( *((_DWORD *)v17 + 12) != 2 )
                goto LABEL_56;
              *(_QWORD *)&v29 = v17[7];
              DWORD2(v29) = *((_DWORD *)v17 + 16);
            }
            if ( v13 )
            {
              if ( *(_DWORD *)(v13 + 48) == 1 )
              {
                if ( !(unsigned int)bMapFileUNICODEClideSide(*(PCWSTR *)(v13 + 56), v37, 0) )
                  goto LABEL_56;
              }
              else
              {
                if ( *(_DWORD *)(v13 + 48) != 2 )
                  goto LABEL_56;
                v37[2] = *(void **)(v13 + 56);
                LODWORD(v37[3]) = *(_DWORD *)(v13 + 64);
              }
            }
            ColorTransform = NtGdiCreateColorTransform(
                               v27,
                               ColorSpaceByColorSpace + 11,
                               v31,
                               DWORD2(v31),
                               v29,
                               DWORD2(v29),
                               v37[2],
                               v37[3]);
LABEL_56:
            IcmCreateColorTransform_::_85_::AUTO_CLIENT_SIDE_FILEVIEW::_AUTO_CLIENT_SIDE_FILEVIEW(v37);
            IcmCreateColorTransform_::_85_::AUTO_CLIENT_SIDE_FILEVIEW::_AUTO_CLIENT_SIDE_FILEVIEW(v28);
            IcmCreateColorTransform_::_85_::AUTO_CLIENT_SIDE_FILEVIEW::_AUTO_CLIENT_SIDE_FILEVIEW(FileHandle);
          }
        }
      }
      else
      {
        v20 = v26;
      }
LABEL_71:
      IcmUnrealizeColorProfile(ColorSpaceByColorSpace);
      IcmUnrealizeColorProfile(v17);
      IcmUnrealizeColorProfile(v13);
      RtlLeaveCriticalSection(&semColorSpaceCache);
      if ( ColorTransform )
      {
        v25 = 1;
        memset_0(Heap, 0, 0x48u);
        Heap[5] = ColorTransform;
        Heap[6] = ColorSpaceByColorSpace;
        Heap[7] = v17;
        Heap[8] = v13;
        if ( (*(_BYTE *)(v20 + 240) & 2) != 0 )
        {
          *((_DWORD *)Heap + 4) |= 4u;
          v25 = 0;
        }
        RtlEnterCriticalSection(&semColorSpaceCache);
        if ( ColorSpaceByColorSpace )
        {
          ++*((_DWORD *)ColorSpaceByColorSpace + 7);
          if ( v25 )
            v25 &= IcmIsCacheable(ColorSpaceByColorSpace);
        }
        ++*((_DWORD *)v17 + 7);
        if ( v25 )
          v25 &= IcmIsCacheable(v17);
        if ( v13 )
        {
          ++*(_DWORD *)(v13 + 28);
          if ( v25 )
            v25 &= IcmIsCacheable(v13);
        }
        RtlLeaveCriticalSection(&semColorSpaceCache);
        *((_DWORD *)Heap + 8) = 1;
        if ( v25 )
          *((_DWORD *)Heap + 4) |= 0x10u;
        else
          Heap[3] = v27;
        RtlEnterCriticalSection(&semColorTransformCache);
        v18 = (_QWORD *)qword_1800FAE28;
        if ( *(__int64 **)qword_1800FAE28 != &ListCachedColorTransform )
          __fastfail(3u);
        ++cCachedColorTransform;
        *Heap = &ListCachedColorTransform;
        Heap[1] = v18;
        *v18 = Heap;
        qword_1800FAE28 = (__int64)Heap;
        RtlLeaveCriticalSection(&semColorTransformCache);
      }
      else
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        return 0;
      }
    }
    return (__int64)Heap;
  }
  return result;
}

```

## disassembly

```asm
0x180033000  mov     [rsp-8+arg_18], rbx
0x180033005  push    rbp
0x180033006  push    rsi
0x180033007  push    rdi
0x180033008  push    r12
0x18003300a  push    r13
0x18003300c  push    r14
0x18003300e  push    r15
0x180033010  lea     rbp, [rsp-230h]
0x180033018  sub     rsp, 330h
0x18003301f  mov     rax, cs:__security_cookie
0x180033026  xor     rax, rsp
0x180033029  mov     [rbp+260h+var_40], rax
0x180033030  test    byte ptr [rdx+0F0h], 10h
0x180033037  mov     r13d, r9d
0x18003303a  mov     rbx, r8
0x18003303d  mov     [rsp+360h+var_320], rdx
0x180033042  mov     r15, rdx
0x180033045  mov     [rsp+360h+var_318], rcx
0x18003304a  jnz     loc_180033110
0x180033050  mov     rax, cs:__imp_ghICM
0x180033057  cmp     qword ptr [rax], 0
0x18003305b  jz      loc_180033215
0x180033061  mov     r14, [r15+108h]
0x180033068  test    r14, r14
0x18003306b  jz      loc_180033116
0x180033071  xor     edi, edi
0x180033073  xor     r12d, r12d
0x180033076  test    rbx, rbx
0x180033079  jnz     short loc_1800330E7
0x18003307b  mov     rbx, [r14+28h]
0x18003307f  test    rbx, rbx
0x180033082  jnz     short loc_1800330E7
0x180033084  xor     edx, edx; Val
0x180033086  mov     [rbp+260h+P], rbx
0x18003308d  mov     r8d, 24Ch; Size
0x180033093  mov     [rbp+260h+var_2D0], rbx
0x180033097  lea     rcx, [rbp+260h+var_2C0]; void *
0x18003309b  call    memset_0
0x1800330a0  mov     rcx, [r15+10h]
0x1800330a4  lea     rdx, [rbp+260h+var_2C0]
0x1800330a8  call    IcmGetLogColorSpace
0x1800330ad  test    eax, eax
0x1800330af  jnz     short loc_18003311A
0x1800330b1  mov     [r14+28h], rbx
0x1800330b5  test    rbx, rbx
0x1800330b8  jnz     short loc_1800330E7
0x1800330ba  mov     rax, rdi
0x1800330bd  mov     rcx, [rbp+260h+var_40]
0x1800330c4  xor     rcx, rsp; StackCookie
0x1800330c7  call    __security_check_cookie
0x1800330cc  mov     rbx, [rsp+360h+arg_18]
0x1800330d4  add     rsp, 330h
0x1800330db  pop     r15
0x1800330dd  pop     r14
0x1800330df  pop     r13
0x1800330e1  pop     r12
0x1800330e3  pop     rdi
0x1800330e4  pop     rsi
0x1800330e5  pop     rbp
0x1800330e6  retn
0x1800330e7  mov     ecx, [r15+0F0h]
0x1800330ee  xor     esi, esi
0x1800330f0  mov     rax, [r14+30h]
0x1800330f4  bt      ecx, 0Fh
0x1800330f8  jb      loc_180033252
0x1800330fe  cmp     rbx, rax
0x180033101  jnz     loc_1800331B3
0x180033107  test    rsi, rsi
0x18003310a  jnz     loc_1800331AA
0x180033110  or      rax, 0FFFFFFFFFFFFFFFFh
0x180033114  jmp     short loc_1800330BD
0x180033116  xor     eax, eax
0x180033118  jmp     short loc_1800330BD
0x18003311a  lea     rcx, [rbp+260h+P]
0x180033121  call    IcmGetDefaultCamp
0x180033126  mov     ecx, [rbp+260h+var_2B0]
0x180033129  lea     rdx, [rbp+260h+var_2D0]
0x18003312d  call    IcmGetDefaultGmmp
0x180033132  mov     rsi, [rbp+260h+P]
0x180033139  lea     rdx, [rbp+260h+var_2C0]
0x18003313d  mov     r15, [rbp+260h+var_2D0]
0x180033141  mov     r9, rsi
0x180033144  mov     rcx, [rsp+360h+var_318]
0x180033149  xor     r8d, r8d
0x18003314c  mov     [rsp+360h+var_338], ebx
0x180033150  mov     [rsp+360h+var_340], r15
0x180033155  call    IcmGetColorSpaceByColorSpace
0x18003315a  mov     rbx, rax
0x18003315d  test    rax, rax
0x180033160  jz      loc_180033227
0x180033166  test    rsi, rsi
0x180033169  jz      short loc_180033183
0x18003316b  mov     rcx, gs:60h
0x180033174  mov     r8, rsi; P
0x180033177  xor     edx, edx; Flags
0x180033179  mov     rcx, [rcx+30h]; HeapHandle
0x18003317d  call    cs:__imp_RtlFreeHeap
0x180033183  test    r15, r15
0x180033186  jz      short loc_1800331A0
0x180033188  mov     rcx, gs:60h
0x180033191  mov     r8, r15; P
0x180033194  xor     edx, edx; Flags
0x180033196  mov     rcx, [rcx+30h]; HeapHandle
0x18003319a  call    cs:__imp_RtlFreeHeap
0x1800331a0  mov     r15, [rsp+360h+var_320]
0x1800331a5  jmp     loc_1800330B1
0x1800331aa  cmp     rbx, rsi
0x1800331ad  jz      loc_180033110
0x1800331b3  test    r13b, 2
0x1800331b7  jz      loc_18003325B
0x1800331bd  mov     r15, rbx
0x1800331c0  mov     rbx, rax
0x1800331c3  jmp     loc_180033267
0x1800331c8  lea     rcx, semColorTransformCache; CriticalSection
0x1800331cf  call    cs:__imp_RtlEnterCriticalSection
0x1800331d5  mov     rax, cs:qword_1800FAE28
0x1800331dc  lea     rcx, ListCachedColorTransform
0x1800331e3  cmp     [rax], rcx
0x1800331e6  jnz     loc_180033651
0x1800331ec  add     cs:?cCachedColorTransform@@3KA, ebx; ulong cCachedColorTransform
0x1800331f2  mov     [rdi], rcx
0x1800331f5  lea     rcx, semColorTransformCache; CriticalSection
0x1800331fc  mov     [rdi+8], rax
0x180033200  mov     [rax], rdi
0x180033203  mov     cs:qword_1800FAE28, rdi
0x18003320a  call    cs:__imp_RtlLeaveCriticalSection
0x180033210  jmp     loc_1800330BA
0x180033215  call    ?IcmInitialize@@YAHXZ; IcmInitialize(void)
0x18003321a  test    eax, eax
0x18003321c  jz      loc_180033116
0x180033222  jmp     loc_180033061
0x180033227  mov     rcx, [rsp+360h+var_318]
0x18003322c  lea     rdx, [rbp+260h+var_2C0]
0x180033230  mov     [rsp+360h+var_338], edi
0x180033234  mov     r9, rsi
0x180033237  xor     r8d, r8d
0x18003323a  mov     [rsp+360h+var_340], r15
0x18003323f  call    IcmCreateColorSpaceByColorSpace
0x180033244  mov     rbx, rax
0x180033247  mov     r12d, 1
0x18003324d  jmp     loc_180033166
0x180033252  mov     rsi, [r14+38h]
0x180033256  jmp     loc_1800330FE
0x18003325b  test    rax, rax
0x18003325e  jz      loc_1800330BA
0x180033264  mov     r15, rax
0x180033267  mov     r14, [rsp+360h+var_318]
0x18003326c  test    r12d, r12d
0x18003326f  jnz     short loc_180033292
0x180033271  and     ecx, 2
0x180033274  mov     r9, rsi
0x180033277  mov     dword ptr [rsp+360h+var_340], ecx
0x18003327b  mov     r8, r15
0x18003327e  mov     rcx, r14
0x180033281  mov     rdx, rbx
0x180033284  call    IcmGetColorTransform
0x180033289  test    rax, rax
0x18003328c  jnz     loc_1800330BD
0x180033292  mov     rcx, gs:60h
0x18003329b  xor     edx, edx; Flags
0x18003329d  mov     rcx, [rcx+30h]; HeapHandle
0x1800332a1  lea     r8d, [rdx+48h]; Size
0x1800332a5  call    cs:__imp_RtlAllocateHeap
0x1800332ab  mov     rdi, rax
0x1800332ae  test    rax, rax
0x1800332b1  jz      loc_1800330BA
0x1800332b7  lea     rcx, semColorSpaceCache; CriticalSection
0x1800332be  xor     r12d, r12d
0x1800332c1  call    cs:__imp_RtlEnterCriticalSection
0x1800332c7  lea     r13d, [r12+1]
0x1800332cc  mov     rcx, rbx
0x1800332cf  mov     edx, r13d
0x1800332d2  call    IcmRealizeColorProfile
0x1800332d7  test    eax, eax
0x1800332d9  jz      loc_180033569
0x1800332df  mov     edx, r13d
0x1800332e2  mov     rcx, r15
0x1800332e5  call    IcmRealizeColorProfile
0x1800332ea  test    eax, eax
0x1800332ec  jz      loc_180033569
0x1800332f2  mov     edx, r13d
0x1800332f5  mov     rcx, rsi
0x1800332f8  call    IcmRealizeColorProfile
0x1800332fd  mov     r13, [rsp+360h+var_320]
0x180033302  test    eax, eax
0x180033304  jz      loc_18003356E
0x18003330a  mov     eax, [r13+0F0h]
0x180033311  lea     ecx, [r12+1]
0x180033316  test    cl, al
0x180033318  jz      loc_1800333DE
0x18003331e  mov     rax, [rbx+20h]
0x180033322  xorps   xmm0, xmm0
0x180033325  mov     [rbp+260h+var_60], rax
0x18003332c  mov     edx, ecx
0x18003332e  mov     eax, [rbx+28h]
0x180033331  mov     dword ptr [rbp+260h+P+4], eax
0x180033337  mov     dword ptr [rsp+360h+var_320], ecx
0x18003333b  mov     dword ptr [rbp+260h+P], ecx
0x180033341  movdqu  xmmword ptr [rbp+260h+var_60+8], xmm0
0x180033349  test    rsi, rsi
0x18003334c  jz      short loc_180033362
0x18003334e  mov     rax, [rsi+20h]
0x180033352  lea     edx, [rcx+1]
0x180033355  mov     [rbp+260h+var_60+8], rax
0x18003335c  mov     [rbp+260h+var_68], ecx
0x180033362  mov     rax, [r15+20h]
0x180033366  lea     r14d, [rdx+1]
0x18003336a  mov     ecx, edx
0x18003336c  lea     r8, [rsp+360h+var_320]
0x180033371  mov     edx, r14d
0x180033374  mov     [rbp+rcx*8+260h+var_60], rax
0x18003337c  lea     rcx, [rbp+260h+var_60]
0x180033383  call    IcmAreIccProfiles
0x180033388  test    eax, eax
0x18003338a  jz      loc_18003356E
0x180033390  cmp     dword ptr [rsp+360h+var_320], r12d
0x180033395  jnz     short loc_1800333A9
0x180033397  mov     r9d, 1
0x18003339d  mov     dword ptr [rbp+260h+P], 0FFFFFFFFh
0x1800333a7  jmp     short loc_1800333AC
0x1800333a9  mov     r9d, r14d
0x1800333ac  mov     rax, cs:fpCreateMultiProfileTransform
0x1800333b3  lea     r8, [rbp+260h+P]
0x1800333ba  mov     [rsp+360h+var_338], r12d
0x1800333bf  lea     rcx, [rbp+260h+var_60]
0x1800333c6  mov     edx, r14d
0x1800333c9  mov     dword ptr [rsp+360h+var_340], 10002h
0x1800333d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333d6  mov     r12, rax
0x1800333d9  jmp     loc_18003356E
0x1800333de  test    al, 2
0x1800333e0  jz      loc_18003356E
0x1800333e6  xorps   xmm0, xmm0
0x1800333e9  xorps   xmm1, xmm1
0x1800333ec  mov     eax, 61637370h
0x1800333f1  movups  xmmword ptr [rsp+360h+FileHandle], xmm0
0x1800333f6  movups  [rbp+260h+var_2E0], xmm0
0x1800333fa  movups  xmmword ptr [rsp+360h+var_310], xmm1
0x1800333ff  movups  [rsp+360h+var_300], xmm1
0x180033404  movups  xmmword ptr [rbp+260h+var_60], xmm0
0x18003340b  movups  [rbp+260h+var_50], xmm0
0x180033412  test    rbx, rbx
0x180033415  jz      short loc_180033423
0x180033417  cmp     [rbx+2A4h], eax
0x18003341d  jnz     loc_1800334B9
0x180033423  cmp     [r15+2A4h], eax
0x18003342a  jnz     loc_1800334B9
0x180033430  test    rsi, rsi
0x180033433  jz      short loc_18003343D
0x180033435  cmp     [rsi+2A4h], eax
0x18003343b  jnz     short loc_1800334B9
0x18003343d  cmp     [rbx+30h], ecx
0x180033440  jnz     loc_1800334DE
0x180033446  mov     rcx, [rbx+38h]; SourceString
0x18003344a  lea     rdx, [rsp+360h+FileHandle]; FileHandle
0x18003344f  xor     r8d, r8d
0x180033452  call    bMapFileUNICODEClideSide
0x180033457  test    eax, eax
0x180033459  jz      short loc_1800334B9
0x18003345b  mov     ecx, 1
0x180033460  jmp     loc_1800334F2
0x180033465  mov     rax, [rsi+38h]
0x180033469  mov     qword ptr [rbp+260h+var_50], rax
0x180033470  mov     eax, [rsi+40h]
0x180033473  mov     dword ptr [rbp+260h+var_50+8], eax
0x180033479  mov     eax, dword ptr [rbp+260h+var_50+8]
0x18003347f  lea     rdx, [rbx+58h]
0x180033483  mov     r9d, dword ptr [rbp+260h+var_2E0+8]
0x180033487  mov     rcx, r14
0x18003348a  mov     r8, qword ptr [rbp+260h+var_2E0]
0x18003348e  mov     [rsp+360h+var_328], eax
0x180033492  mov     rax, qword ptr [rbp+260h+var_50]
0x180033499  mov     [rsp+360h+var_330], rax
0x18003349e  mov     eax, dword ptr [rsp+360h+var_300+8]
0x1800334a2  mov     [rsp+360h+var_338], eax
0x1800334a6  mov     rax, qword ptr [rsp+360h+var_300]
0x1800334ab  mov     [rsp+360h+var_340], rax
0x1800334b0  call    cs:__imp_NtGdiCreateColorTransform
0x1800334b6  mov     r12, rax
0x1800334b9  lea     rcx, [rbp+260h+var_60]
0x1800334c0  call    _IcmCreateColorTransform____85___AUTO_CLIENT_SIDE_FILEVIEW___AUTO_CLIENT_SIDE_FILEVIEW
0x1800334c5  lea     rcx, [rsp+360h+var_310]
0x1800334ca  call    _IcmCreateColorTransform____85___AUTO_CLIENT_SIDE_FILEVIEW___AUTO_CLIENT_SIDE_FILEVIEW
0x1800334cf  lea     rcx, [rsp+360h+FileHandle]
0x1800334d4  call    _IcmCreateColorTransform____85___AUTO_CLIENT_SIDE_FILEVIEW___AUTO_CLIENT_SIDE_FILEVIEW
0x1800334d9  jmp     loc_18003356E
0x1800334de  cmp     dword ptr [rbx+30h], 2
0x1800334e2  jnz     short loc_1800334B9
0x1800334e4  mov     rax, [rbx+38h]
0x1800334e8  mov     qword ptr [rbp+260h+var_2E0], rax
0x1800334ec  mov     eax, [rbx+40h]
0x1800334ef  mov     dword ptr [rbp+260h+var_2E0+8], eax
0x1800334f2  cmp     [r15+30h], ecx
0x1800334f6  jnz     short loc_180033514
0x1800334f8  mov     rcx, [r15+38h]; SourceString
0x1800334fc  lea     rdx, [rsp+360h+var_310]; FileHandle
0x180033501  xor     r8d, r8d
0x180033504  call    bMapFileUNICODEClideSide
0x180033509  test    eax, eax
  ... truncated ...
```
