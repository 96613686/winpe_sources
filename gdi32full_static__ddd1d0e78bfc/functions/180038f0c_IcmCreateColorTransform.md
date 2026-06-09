# IcmCreateColorTransform

- ea: `0x180038f0c`
- end: `0x1800395c8`
- name: `IcmCreateColorTransform`
- size: `1724`
- prototype: ``
- caller_count: `6`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180037e48`
- `0x1800499a4`
- `0x18006efa0`
- `0x180070288`
- `0x18008e7d8`
- `0x18008f324`

## callees

- `0x180038f0c`
- `0x1800395d0`
- `0x180039ea4`
- `0x180039fa0`
- `0x18003a1e4`
- `0x18003aac8`
- `0x18003acb8`
- `0x18003ae00`
- `0x18003b378`
- `0x180045548`
- `0x18007f800`
- `0x180080604`
- `0x18008c3ec`
- `0x18008e010`
- `0x18008e470`
- `0x18008e7bc`
- `0x1800a8010`

## import_xrefs

- `GDI32!ghICM` at `0x180038f5c`
- `ntdll!RtlFreeHeap` at `0x18003908a`
- `ntdll!RtlFreeHeap` at `0x1800390ad`
- `ntdll!RtlFreeHeap` at `0x1800395b5`
- `ntdll!RtlFreeHeap` at `0x18003908a`
- `ntdll!RtlFreeHeap` at `0x1800390ad`
- `ntdll!RtlFreeHeap` at `0x1800395b5`
- `ntdll!RtlAllocateHeap` at `0x1800391ca`
- `ntdll!RtlAllocateHeap` at `0x1800391ca`
- `ntdll!RtlEnterCriticalSection` at `0x1800390e8`
- `ntdll!RtlEnterCriticalSection` at `0x1800391ec`
- `ntdll!RtlEnterCriticalSection` at `0x180039517`
- `ntdll!RtlEnterCriticalSection` at `0x1800390e8`
- `ntdll!RtlEnterCriticalSection` at `0x1800391ec`
- `ntdll!RtlEnterCriticalSection` at `0x180039517`
- `ntdll!RtlLeaveCriticalSection` at `0x180039129`
- `ntdll!RtlLeaveCriticalSection` at `0x1800394c8`
- `ntdll!RtlLeaveCriticalSection` at `0x180039573`
- `ntdll!RtlLeaveCriticalSection` at `0x180039129`
- `ntdll!RtlLeaveCriticalSection` at `0x1800394c8`
- `ntdll!RtlLeaveCriticalSection` at `0x180039573`
- `win32u!NtGdiCreateColorTransform` at `0x1800393e5`
- `win32u!NtGdiCreateColorTransform` at `0x1800393e5`

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
        v18 = (_QWORD *)qword_1800FDF18;
        if ( *(__int64 **)qword_1800FDF18 != &ListCachedColorTransform )
          __fastfail(3u);
        ++cCachedColorTransform;
        *Heap = &ListCachedColorTransform;
        Heap[1] = v18;
        *v18 = Heap;
        qword_1800FDF18 = (__int64)Heap;
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
0x180038f0c  mov     [rsp-8+arg_18], rbx
0x180038f11  push    rbp
0x180038f12  push    rsi
0x180038f13  push    rdi
0x180038f14  push    r12
0x180038f16  push    r13
0x180038f18  push    r14
0x180038f1a  push    r15
0x180038f1c  lea     rbp, [rsp-230h]
0x180038f24  sub     rsp, 330h
0x180038f2b  mov     rax, cs:__security_cookie
0x180038f32  xor     rax, rsp
0x180038f35  mov     [rbp+260h+var_40], rax
0x180038f3c  test    byte ptr [rdx+0F0h], 10h
0x180038f43  mov     r13d, r9d
0x180038f46  mov     rbx, r8
0x180038f49  mov     [rsp+360h+var_320], rdx
0x180038f4e  mov     r15, rdx
0x180038f51  mov     [rsp+360h+var_318], rcx
0x180038f56  jnz     loc_18003901D
0x180038f5c  mov     rax, cs:__imp_ghICM
0x180038f63  cmp     qword ptr [rax], 0
0x180038f67  jz      loc_18003913A
0x180038f6d  mov     r14, [r15+108h]
0x180038f74  test    r14, r14
0x180038f77  jz      loc_180039023
0x180038f7d  xor     edi, edi
0x180038f7f  xor     r12d, r12d
0x180038f82  test    rbx, rbx
0x180038f85  jnz     short loc_180038FF4
0x180038f87  mov     rbx, [r14+28h]
0x180038f8b  test    rbx, rbx
0x180038f8e  jnz     short loc_180038FF4
0x180038f90  xor     edx, edx; Val
0x180038f92  mov     [rbp+260h+P], rbx
0x180038f99  mov     r8d, 24Ch; Size
0x180038f9f  mov     [rbp+260h+var_2D0], rbx
0x180038fa3  lea     rcx, [rbp+260h+var_2C0]; void *
0x180038fa7  call    memset_0
0x180038fac  mov     rcx, [r15+10h]
0x180038fb0  lea     rdx, [rbp+260h+var_2C0]
0x180038fb4  call    IcmGetLogColorSpace
0x180038fb9  test    eax, eax
0x180038fbb  jnz     short loc_180039027
0x180038fbd  mov     [r14+28h], rbx
0x180038fc1  test    rbx, rbx
0x180038fc4  jnz     short loc_180038FF4
0x180038fc6  mov     rax, rdi
0x180038fc9  mov     rcx, [rbp+260h+var_40]
0x180038fd0  xor     rcx, rsp; StackCookie
0x180038fd3  call    __security_check_cookie
0x180038fd8  mov     rbx, [rsp+360h+arg_18]
0x180038fe0  add     rsp, 330h
0x180038fe7  pop     r15
0x180038fe9  pop     r14
0x180038feb  pop     r13
0x180038fed  pop     r12
0x180038fef  pop     rdi
0x180038ff0  pop     rsi
0x180038ff1  pop     rbp
0x180038ff2  retn
0x180038ff4  mov     ecx, [r15+0F0h]
0x180038ffb  xor     esi, esi
0x180038ffd  mov     rax, [r14+30h]
0x180039001  bt      ecx, 0Fh
0x180039005  jb      loc_180039177
0x18003900b  cmp     rbx, rax
0x18003900e  jnz     loc_1800390CC
0x180039014  test    rsi, rsi
0x180039017  jnz     loc_1800390C3
0x18003901d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180039021  jmp     short loc_180038FC9
0x180039023  xor     eax, eax
0x180039025  jmp     short loc_180038FC9
0x180039027  lea     rcx, [rbp+260h+P]
0x18003902e  call    IcmGetDefaultCamp
0x180039033  mov     ecx, [rbp+260h+var_2B0]
0x180039036  lea     rdx, [rbp+260h+var_2D0]
0x18003903a  call    IcmGetDefaultGmmp
0x18003903f  mov     rsi, [rbp+260h+P]
0x180039046  lea     rdx, [rbp+260h+var_2C0]
0x18003904a  mov     r15, [rbp+260h+var_2D0]
0x18003904e  mov     r9, rsi
0x180039051  mov     rcx, [rsp+360h+var_318]
0x180039056  xor     r8d, r8d
0x180039059  mov     [rsp+360h+var_338], ebx
0x18003905d  mov     [rsp+360h+var_340], r15
0x180039062  call    IcmGetColorSpaceByColorSpace
0x180039067  mov     rbx, rax
0x18003906a  test    rax, rax
0x18003906d  jz      loc_18003914C
0x180039073  test    rsi, rsi
0x180039076  jz      short loc_180039096
0x180039078  mov     rcx, gs:60h
0x180039081  mov     r8, rsi; P
0x180039084  xor     edx, edx; Flags
0x180039086  mov     rcx, [rcx+30h]; HeapHandle
0x18003908a  call    cs:__imp_RtlFreeHeap
0x180039091  nop     dword ptr [rax+rax+00h]
0x180039096  test    r15, r15
0x180039099  jz      short loc_1800390B9
0x18003909b  mov     rcx, gs:60h
0x1800390a4  mov     r8, r15; P
0x1800390a7  xor     edx, edx; Flags
0x1800390a9  mov     rcx, [rcx+30h]; HeapHandle
0x1800390ad  call    cs:__imp_RtlFreeHeap
0x1800390b4  nop     dword ptr [rax+rax+00h]
0x1800390b9  mov     r15, [rsp+360h+var_320]
0x1800390be  jmp     loc_180038FBD
0x1800390c3  cmp     rbx, rsi
0x1800390c6  jz      loc_18003901D
0x1800390cc  test    r13b, 2
0x1800390d0  jz      loc_180039180
0x1800390d6  mov     r15, rbx
0x1800390d9  mov     rbx, rax
0x1800390dc  jmp     loc_18003918C
0x1800390e1  lea     rcx, semColorTransformCache; CriticalSection
0x1800390e8  call    cs:__imp_RtlEnterCriticalSection
0x1800390ef  nop     dword ptr [rax+rax+00h]
0x1800390f4  mov     rax, cs:qword_1800FDF18
0x1800390fb  lea     rcx, ListCachedColorTransform
0x180039102  cmp     [rax], rcx
0x180039105  jnz     loc_18003959E
0x18003910b  add     cs:?cCachedColorTransform@@3KA, ebx; ulong cCachedColorTransform
0x180039111  mov     [rdi], rcx
0x180039114  lea     rcx, semColorTransformCache; CriticalSection
0x18003911b  mov     [rdi+8], rax
0x18003911f  mov     [rax], rdi
0x180039122  mov     cs:qword_1800FDF18, rdi
0x180039129  call    cs:__imp_RtlLeaveCriticalSection
0x180039130  nop     dword ptr [rax+rax+00h]
0x180039135  jmp     loc_180038FC6
0x18003913a  call    ?IcmInitialize@@YAHXZ; IcmInitialize(void)
0x18003913f  test    eax, eax
0x180039141  jz      loc_180039023
0x180039147  jmp     loc_180038F6D
0x18003914c  mov     rcx, [rsp+360h+var_318]
0x180039151  lea     rdx, [rbp+260h+var_2C0]
0x180039155  mov     [rsp+360h+var_338], edi
0x180039159  mov     r9, rsi
0x18003915c  xor     r8d, r8d
0x18003915f  mov     [rsp+360h+var_340], r15
0x180039164  call    IcmCreateColorSpaceByColorSpace
0x180039169  mov     rbx, rax
0x18003916c  mov     r12d, 1
0x180039172  jmp     loc_180039073
0x180039177  mov     rsi, [r14+38h]
0x18003917b  jmp     loc_18003900B
0x180039180  test    rax, rax
0x180039183  jz      loc_180038FC6
0x180039189  mov     r15, rax
0x18003918c  mov     r14, [rsp+360h+var_318]
0x180039191  test    r12d, r12d
0x180039194  jnz     short loc_1800391B7
0x180039196  and     ecx, 2
0x180039199  mov     r9, rsi
0x18003919c  mov     dword ptr [rsp+360h+var_340], ecx
0x1800391a0  mov     r8, r15
0x1800391a3  mov     rcx, r14
0x1800391a6  mov     rdx, rbx
0x1800391a9  call    IcmGetColorTransform
0x1800391ae  test    rax, rax
0x1800391b1  jnz     loc_180038FC9
0x1800391b7  mov     rcx, gs:60h
0x1800391c0  xor     edx, edx; Flags
0x1800391c2  mov     rcx, [rcx+30h]; HeapHandle
0x1800391c6  lea     r8d, [rdx+48h]; Size
0x1800391ca  call    cs:__imp_RtlAllocateHeap
0x1800391d1  nop     dword ptr [rax+rax+00h]
0x1800391d6  mov     rdi, rax
0x1800391d9  test    rax, rax
0x1800391dc  jz      loc_180038FC6
0x1800391e2  lea     rcx, semColorSpaceCache; CriticalSection
0x1800391e9  xor     r12d, r12d
0x1800391ec  call    cs:__imp_RtlEnterCriticalSection
0x1800391f3  nop     dword ptr [rax+rax+00h]
0x1800391f8  lea     r13d, [r12+1]
0x1800391fd  mov     rcx, rbx
0x180039200  mov     edx, r13d
0x180039203  call    IcmRealizeColorProfile
0x180039208  test    eax, eax
0x18003920a  jz      loc_1800394A4
0x180039210  mov     edx, r13d
0x180039213  mov     rcx, r15
0x180039216  call    IcmRealizeColorProfile
0x18003921b  test    eax, eax
0x18003921d  jz      loc_1800394A4
0x180039223  mov     edx, r13d
0x180039226  mov     rcx, rsi
0x180039229  call    IcmRealizeColorProfile
0x18003922e  mov     r13, [rsp+360h+var_320]
0x180039233  test    eax, eax
0x180039235  jz      loc_1800394A9
0x18003923b  mov     eax, [r13+0F0h]
0x180039242  lea     ecx, [r12+1]
0x180039247  test    cl, al
0x180039249  jz      loc_18003930F
0x18003924f  mov     rax, [rbx+20h]
0x180039253  xorps   xmm0, xmm0
0x180039256  mov     [rbp+260h+var_60], rax
0x18003925d  mov     edx, ecx
0x18003925f  mov     eax, [rbx+28h]
0x180039262  mov     dword ptr [rbp+260h+P+4], eax
0x180039268  mov     dword ptr [rsp+360h+var_320], ecx
0x18003926c  mov     dword ptr [rbp+260h+P], ecx
0x180039272  movdqu  xmmword ptr [rbp+260h+var_60+8], xmm0
0x18003927a  test    rsi, rsi
0x18003927d  jz      short loc_180039293
0x18003927f  mov     rax, [rsi+20h]
0x180039283  lea     edx, [rcx+1]
0x180039286  mov     [rbp+260h+var_60+8], rax
0x18003928d  mov     [rbp+260h+var_68], ecx
0x180039293  mov     rax, [r15+20h]
0x180039297  lea     r14d, [rdx+1]
0x18003929b  mov     ecx, edx
0x18003929d  lea     r8, [rsp+360h+var_320]
0x1800392a2  mov     edx, r14d
0x1800392a5  mov     [rbp+rcx*8+260h+var_60], rax
0x1800392ad  lea     rcx, [rbp+260h+var_60]
0x1800392b4  call    IcmAreIccProfiles
0x1800392b9  test    eax, eax
0x1800392bb  jz      loc_1800394A9
0x1800392c1  cmp     dword ptr [rsp+360h+var_320], r12d
0x1800392c6  jnz     short loc_1800392DA
0x1800392c8  mov     r9d, 1
0x1800392ce  mov     dword ptr [rbp+260h+P], 0FFFFFFFFh
0x1800392d8  jmp     short loc_1800392DD
0x1800392da  mov     r9d, r14d
0x1800392dd  mov     rax, cs:fpCreateMultiProfileTransform
0x1800392e4  lea     r8, [rbp+260h+P]
0x1800392eb  mov     [rsp+360h+var_338], r12d
0x1800392f0  lea     rcx, [rbp+260h+var_60]
0x1800392f7  mov     edx, r14d
0x1800392fa  mov     dword ptr [rsp+360h+var_340], 10002h
0x180039302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039307  mov     r12, rax
0x18003930a  jmp     loc_1800394A9
0x18003930f  test    al, 2
0x180039311  jz      loc_1800394A9
0x180039317  xorps   xmm0, xmm0
0x18003931a  xorps   xmm1, xmm1
0x18003931d  mov     eax, 61637370h
0x180039322  movups  xmmword ptr [rsp+360h+FileHandle], xmm0
0x180039327  movups  [rbp+260h+var_2E0], xmm0
0x18003932b  movups  xmmword ptr [rsp+360h+var_310], xmm1
0x180039330  movups  [rsp+360h+var_300], xmm1
0x180039335  movups  xmmword ptr [rbp+260h+var_60], xmm0
0x18003933c  movups  [rbp+260h+var_50], xmm0
0x180039343  test    rbx, rbx
0x180039346  jz      short loc_180039354
0x180039348  cmp     [rbx+2A4h], eax
0x18003934e  jnz     loc_1800393F4
0x180039354  cmp     [r15+2A4h], eax
0x18003935b  jnz     loc_1800393F4
0x180039361  test    rsi, rsi
0x180039364  jz      short loc_180039372
0x180039366  cmp     [rsi+2A4h], eax
0x18003936c  jnz     loc_1800393F4
0x180039372  cmp     [rbx+30h], ecx
0x180039375  jnz     loc_180039419
0x18003937b  mov     rcx, [rbx+38h]; SourceString
0x18003937f  lea     rdx, [rsp+360h+FileHandle]; FileHandle
0x180039384  xor     r8d, r8d
0x180039387  call    bMapFileUNICODEClideSide
0x18003938c  test    eax, eax
0x18003938e  jz      short loc_1800393F4
0x180039390  mov     ecx, 1
0x180039395  jmp     loc_18003942D
0x18003939a  mov     rax, [rsi+38h]
0x18003939e  mov     qword ptr [rbp+260h+var_50], rax
0x1800393a5  mov     eax, [rsi+40h]
0x1800393a8  mov     dword ptr [rbp+260h+var_50+8], eax
0x1800393ae  mov     eax, dword ptr [rbp+260h+var_50+8]
0x1800393b4  lea     rdx, [rbx+58h]
0x1800393b8  mov     r9d, dword ptr [rbp+260h+var_2E0+8]
0x1800393bc  mov     rcx, r14
0x1800393bf  mov     r8, qword ptr [rbp+260h+var_2E0]
0x1800393c3  mov     [rsp+360h+var_328], eax
0x1800393c7  mov     rax, qword ptr [rbp+260h+var_50]
0x1800393ce  mov     [rsp+360h+var_330], rax
0x1800393d3  mov     eax, dword ptr [rsp+360h+var_300+8]
0x1800393d7  mov     [rsp+360h+var_338], eax
0x1800393db  mov     rax, qword ptr [rsp+360h+var_300]
0x1800393e0  mov     [rsp+360h+var_340], rax
0x1800393e5  call    cs:__imp_NtGdiCreateColorTransform
0x1800393ec  nop     dword ptr [rax+rax+00h]
0x1800393f1  mov     r12, rax
0x1800393f4  lea     rcx, [rbp+260h+var_60]
0x1800393fb  call    _IcmCreateColorTransform____85___AUTO_CLIENT_SIDE_FILEVIEW___AUTO_CLIENT_SIDE_FILEVIEW
0x180039400  lea     rcx, [rsp+360h+var_310]
0x180039405  call    _IcmCreateColorTransform____85___AUTO_CLIENT_SIDE_FILEVIEW___AUTO_CLIENT_SIDE_FILEVIEW
0x18003940a  lea     rcx, [rsp+360h+FileHandle]
0x18003940f  call    _IcmCreateColorTransform____85___AUTO_CLIENT_SIDE_FILEVIEW___AUTO_CLIENT_SIDE_FILEVIEW
0x180039414  jmp     loc_1800394A9
0x180039419  cmp     dword ptr [rbx+30h], 2
0x18003941d  jnz     short loc_1800393F4
0x18003941f  mov     rax, [rbx+38h]
0x180039423  mov     qword ptr [rbp+260h+var_2E0], rax
0x180039427  mov     eax, [rbx+40h]
0x18003942a  mov     dword ptr [rbp+260h+var_2E0+8], eax
  ... truncated ...
```
