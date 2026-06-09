# ProcessPages(tagSPOOL_FILE_HANDLE *,uint)

- ea: `0x18005a260`
- end: `0x18005aa67`
- name: `?ProcessPages@@YAHPEAUtagSPOOL_FILE_HANDLE@@I@Z`
- size: `2055`
- prototype: `__int64 __fastcall(struct tagSPOOL_FILE_HANDLE *, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18005a180`
- `0x180094a80`
- `0x180094af0`

## callees

- `0x18005a260`
- `0x18005af04`
- `0x18007ac50`
- `0x18007ba24`
- `0x18008066c`
- `0x1800a3514`
- `0x1800a5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a2ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a2ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a3a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005a3a5`
- `ntdll!RtlFreeHeap` at `0x18005a375`
- `ntdll!RtlFreeHeap` at `0x18005aa01`
- `ntdll!RtlFreeHeap` at `0x18005aa2a`
- `ntdll!RtlFreeHeap` at `0x18005aa52`
- `ntdll!RtlFreeHeap` at `0x18005a375`
- `ntdll!RtlFreeHeap` at `0x18005aa01`
- `ntdll!RtlFreeHeap` at `0x18005aa2a`
- `ntdll!RtlFreeHeap` at `0x18005aa52`
- `ntdll!RtlAllocateHeap` at `0x18005a32c`
- `ntdll!RtlAllocateHeap` at `0x18005a4ae`
- `ntdll!RtlAllocateHeap` at `0x18005a58b`
- `ntdll!RtlAllocateHeap` at `0x18005a624`
- `ntdll!RtlAllocateHeap` at `0x18005a32c`
- `ntdll!RtlAllocateHeap` at `0x18005a4ae`
- `ntdll!RtlAllocateHeap` at `0x18005a58b`
- `ntdll!RtlAllocateHeap` at `0x18005a624`
- `ntdll!RtlDecodePointer` at `0x18005a2b7`
- `ntdll!RtlDecodePointer` at `0x18005a5c2`
- `ntdll!RtlDecodePointer` at `0x18005a2b7`
- `ntdll!RtlDecodePointer` at `0x18005a5c2`
- `win32u!NtGdiRemoveMergeFont` at `0x18005a8c8`
- `win32u!NtGdiRemoveMergeFont` at `0x18005a8c8`
- `win32u!NtGdiAddRemoteMMInstanceToDC` at `0x18005a85a`
- `win32u!NtGdiAddRemoteMMInstanceToDC` at `0x18005a85a`
- `win32u!NtGdiAddRemoteFontToDC` at `0x18005a740`
- `win32u!NtGdiAddRemoteFontToDC` at `0x18005a915`
- `win32u!NtGdiAddRemoteFontToDC` at `0x18005a740`
- `win32u!NtGdiAddRemoteFontToDC` at `0x18005a915`
- `win32u!NtGdiAddEmbFontToDC` at `0x18005a885`
- `win32u!NtGdiAddEmbFontToDC` at `0x18005a885`

## pseudocode

```c
__int64 __fastcall ProcessPages(struct tagSPOOL_FILE_HANDLE *a1, unsigned int a2)
{
  unsigned int v2; // r13d
  __int64 v3; // r12
  PVOID v5; // rax
  unsigned int (__fastcall *v6)(__int64, __int64, _QWORD, _QWORD, _DWORD); // r14
  unsigned int v7; // esi
  PVOID Heap; // rax
  void *v10; // rsi
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // r15
  __int64 v15; // rcx
  unsigned int v16; // r8d
  unsigned __int8 *v17; // rdi
  unsigned __int8 *v18; // rax
  unsigned __int8 *v19; // rax
  PVOID v20; // r8
  _DWORD *v21; // rax
  __int64 v22; // rax
  unsigned int v23; // r8d
  __int64 v24; // rdx
  __int64 v25; // rax
  int v26; // ecx
  int v27; // eax
  __int64 v28; // rax
  unsigned int v29; // [rsp+40h] [rbp-C0h]
  SIZE_T Size; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v31; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+54h] [rbp-ACh]
  SIZE_T v33; // [rsp+58h] [rbp-A8h] BYREF
  int v34; // [rsp+60h] [rbp-A0h]
  unsigned __int8 v35[8]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v36; // [rsp+70h] [rbp-90h] BYREF
  unsigned int (__fastcall *v37)(_QWORD, __int64, _QWORD, __int64, _DWORD); // [rsp+78h] [rbp-88h]
  PVOID P; // [rsp+80h] [rbp-80h]
  __int64 v39; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 v40[16]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 v41[48]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v42; // [rsp+D0h] [rbp-30h]

  v2 = 0;
  v3 = a2;
  Size = 0;
  v33 = 0;
  v36 = 0;
  v31 = 0;
  v39 = 0;
  *(_QWORD *)v35 = 0;
  v5 = RtlDecodePointer(fpSeekPrinter);
  v6 = (unsigned int (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _DWORD))v5;
  v37 = (unsigned int (__fastcall *)(_QWORD, __int64, _QWORD, __int64, _DWORD))v5;
  if ( *((_DWORD *)a1 + 10) >= (unsigned int)v3 )
  {
    v7 = 1;
    if ( !((unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64, _DWORD))v5)(*((_QWORD *)a1 + 2), 0, 0, 1, 0) )
      return GetLastError() != 63;
    return v7;
  }
  if ( (unsigned int)v3 > *((_DWORD *)a1 + 14) )
  {
    if ( (unsigned int)v3 > 0x4E2000
      || (Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 40 * v3), (v10 = Heap) == 0) )
    {
      SetLastError(8u);
      return 0;
    }
    memset_0(Heap, 0, 40 * v3);
    memcpy_0(v10, *((const void **)a1 + 6), 40LL * *((unsigned int *)a1 + 10));
    *((_DWORD *)a1 + 14) = v3;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *((PVOID *)a1 + 6));
    *((_QWORD *)a1 + 6) = v10;
  }
  v11 = *((_DWORD *)a1 + 10);
  if ( v11 )
  {
    v12 = 5LL * (unsigned int)(v11 - 1);
    v13 = *((_QWORD *)a1 + 6);
    v14 = *(_QWORD *)(v13 + 8 * v12 + 8);
    P = *(PVOID *)(v13 + 8 * v12 + 16);
  }
  else
  {
    v15 = *((_QWORD *)a1 + 2);
    *(_OWORD *)v40 = 0;
    if ( !v6(v15, 0, 0, 0, 0) || !(unsigned int)MyReadPrinter(*((void **)a1 + 2), v40, 0x10u) )
      return 0;
    v14 = *(unsigned int *)&v40[4];
    P = (PVOID)*((_QWORD *)a1 + 3);
  }
  if ( !v6(*((_QWORD *)a1 + 2), v14, 0, 0, 0) )
    return 0;
  v16 = *((_DWORD *)a1 + 10);
  v17 = 0;
  v29 = v16;
  v32 = 0;
  while ( v16 < (unsigned int)v3 && (unsigned int)MyReadPrinter(*((void **)a1 + 2), (unsigned __int8 *)&Size, 8u) )
  {
    v14 += 8;
    v16 = v29;
    if ( HIDWORD(Size) )
    {
      if ( (_DWORD)Size == 5 || (unsigned int)Size <= 1 || (unsigned int)Size >= 9 )
      {
        v34 = 0;
        if ( (unsigned int)(Size - 15) <= 4 || (_DWORD)Size == 21 )
        {
          if ( HIDWORD(Size) < 8
            || !(unsigned int)MyReadPrinter(*((void **)a1 + 2), v35, 8u)
            || *(__int64 *)v35 <= 0
            || !v37(*((_QWORD *)a1 + 2), -16LL - *(_QWORD *)v35, 0, 1, 0)
            || !(unsigned int)MyReadPrinter(*((void **)a1 + 2), (unsigned __int8 *)&v33, 8u) )
          {
            break;
          }
          v19 = (unsigned __int8 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, HIDWORD(v33));
          v17 = v19;
          if ( !v19 )
            goto LABEL_98;
          if ( !(unsigned int)MyReadPrinter(*((void **)a1 + 2), v19, HIDWORD(v33)) )
            goto LABEL_97;
          v2 = HIDWORD(v33);
        }
      }
      else
      {
        v18 = (unsigned __int8 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, HIDWORD(Size));
        v17 = v18;
        if ( !v18 )
          goto LABEL_98;
        if ( !(unsigned int)MyReadPrinter(*((void **)a1 + 2), v18, HIDWORD(Size)) )
          goto LABEL_97;
        v2 = HIDWORD(Size);
        v34 = 1;
      }
      v20 = RtlDecodePointer(fpIsValidDevmodeW);
      if ( (unsigned int)Size > 0xB )
      {
        if ( (unsigned int)Size <= 0x11 )
        {
          switch ( (_DWORD)Size )
          {
            case 0x11:
LABEL_74:
              NtGdiAddRemoteMMInstanceToDC(*((_QWORD *)a1 + 1), v17, v2);
              goto LABEL_85;
            case 0xC:
              goto LABEL_85;
            case 0xD:
            case 0xE:
              if ( HIDWORD(Size) < 8 )
                goto LABEL_96;
              if ( !(unsigned int)MyReadPrinter(*((void **)a1 + 2), v35, 8u) )
                goto LABEL_96;
              if ( *(__int64 *)v35 <= 0 )
                goto LABEL_96;
              if ( !v37(*((_QWORD *)a1 + 2), -16LL - *(_QWORD *)v35, 0, 1, 0) )
                goto LABEL_96;
              if ( !(unsigned int)MyReadPrinter(*((void **)a1 + 2), (unsigned __int8 *)&v33, 8u) )
                goto LABEL_96;
              v23 = v29;
              v25 = *((_QWORD *)a1 + 6);
              v32 = 0;
              *(_QWORD *)(v25 + 40LL * v29 + 16) = P;
              if ( v14 == *(_QWORD *)v35 )
                goto LABEL_96;
              *(_QWORD *)(*((_QWORD *)a1 + 6) + 40LL * v29) = v14 - *(_QWORD *)v35;
              *(_QWORD *)(*((_QWORD *)a1 + 6) + 40LL * v29 + 8) = v14 + HIDWORD(Size);
              *(_DWORD *)(*((_QWORD *)a1 + 6) + 40LL * v29 + 24) = HIDWORD(v33);
              v26 = 10;
              if ( (_DWORD)Size == 13 )
                v26 = 1;
              *(_DWORD *)(*((_QWORD *)a1 + 6) + 40LL * v29 + 28) = v26;
              goto LABEL_54;
          }
          if ( (unsigned int)(Size - 15) > 1 )
            break;
LABEL_61:
          if ( !(unsigned int)NtGdiAddRemoteFontToDC(*((_QWORD *)a1 + 1), v17, v2, 0) )
            break;
          if ( (_DWORD)Size == 4 || (_DWORD)Size == 16 )
            *((_QWORD *)a1 + 4) = 0;
          goto LABEL_85;
        }
        if ( (_DWORD)Size == 18 )
          goto LABEL_82;
        if ( (_DWORD)Size == 19 )
          goto LABEL_80;
        if ( (_DWORD)Size != 20 )
        {
          if ( (_DWORD)Size != 21 )
            break;
          NtGdiAddEmbFontToDC(*((_QWORD *)a1 + 1), v17, v20);
        }
      }
      else
      {
        if ( (_DWORD)Size == 11 )
          goto LABEL_53;
        if ( (unsigned int)Size > 6 )
        {
          if ( (_DWORD)Size == 7 )
          {
LABEL_82:
            v27 = bMergeSubsetFont(
                    *((_QWORD *)a1 + 1),
                    (_DWORD)v17,
                    v2,
                    (unsigned int)&v39,
                    (__int64)&v31,
                    0,
                    (__int64)&v36);
          }
          else
          {
            if ( (_DWORD)Size != 8 )
            {
              if ( (unsigned int)(Size - 9) > 1 )
                break;
LABEL_53:
              v22 = *((_QWORD *)a1 + 6);
              v23 = v29;
              v32 = 0;
              v24 = 5LL * v29;
              *(_QWORD *)(v22 + 8 * v24 + 16) = P;
              *(_QWORD *)(*((_QWORD *)a1 + 6) + 8 * v24) = v14;
              *(_QWORD *)(*((_QWORD *)a1 + 6) + 8 * v24 + 8) = v14 + HIDWORD(Size);
              *(_DWORD *)(*((_QWORD *)a1 + 6) + 8 * v24 + 24) = HIDWORD(Size);
              *(_DWORD *)(*((_QWORD *)a1 + 6) + 8 * v24 + 28) = Size;
LABEL_54:
              ++*((_DWORD *)a1 + 10);
              v29 = v23 + 1;
              goto LABEL_85;
            }
LABEL_80:
            if ( !(unsigned int)bMergeSubsetFont(
                                  *((_QWORD *)a1 + 1),
                                  (_DWORD)v17,
                                  v2,
                                  (unsigned int)&v39,
                                  (__int64)&v31,
                                  1,
                                  (__int64)&v36) )
              goto LABEL_85;
            v27 = NtGdiRemoveMergeFont(*((_QWORD *)a1 + 1), &v36);
          }
          if ( v27 )
            NtGdiAddRemoteFontToDC(*((_QWORD *)a1 + 1), v39, v31, &v36);
          goto LABEL_85;
        }
        switch ( (_DWORD)Size )
        {
          case 6:
            goto LABEL_74;
          case 1:
            goto LABEL_53;
          case 2:
            goto LABEL_61;
          case 3:
            if ( !((unsigned int (__fastcall *)(unsigned __int8 *, _QWORD))v20)(v17, v2) )
              goto LABEL_96;
            P = v17;
            v17 = 0;
            v32 = 1;
            goto LABEL_85;
          case 4:
            goto LABEL_61;
        }
        if ( (_DWORD)Size != 5 )
          break;
        v21 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x18u);
        if ( !v21 )
          break;
        *(_QWORD *)v21 = *(_QWORD *)(*((_QWORD *)a1 + 6) + 40LL * v29 + 32);
        *(_QWORD *)(*((_QWORD *)a1 + 6) + 40LL * v29 + 32) = v21;
        v21[5] = Size;
        v21[4] = HIDWORD(Size);
        *((_QWORD *)v21 + 1) = v14;
      }
LABEL_85:
      if ( (((_DWORD)Size - 1) & 0xFFFFFFF7) != 0 )
      {
        v28 = HIDWORD(Size);
      }
      else
      {
        memset_0(v41, 0, 0x6Cu);
        if ( !v37(*((_QWORD *)a1 + 2), -8, 0, 1, 0)
          || !(unsigned int)MyReadPrinter(*((void **)a1 + 2), v41, 0x6Cu)
          || !v37(*((_QWORD *)a1 + 2), -100, 0, 1, 0)
          || v42 < 8 )
        {
          break;
        }
        v28 = v42 - 8LL;
      }
      v14 += v28;
      if ( !v34 && !v37(*((_QWORD *)a1 + 2), v14, 0, 0, 0) )
        break;
      v16 = v29;
      if ( v17 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
        v16 = v29;
        v17 = 0;
      }
    }
  }
LABEL_96:
  if ( !v17 )
    goto LABEL_98;
LABEL_97:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
LABEL_98:
  if ( P && v32 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  return v29 >= (unsigned int)v3;
}

```

## disassembly

```asm
0x18005a260  mov     [rsp-8+arg_10], rbx
0x18005a265  push    rbp
0x18005a266  push    rsi
0x18005a267  push    rdi
0x18005a268  push    r12
0x18005a26a  push    r13
0x18005a26c  push    r14
0x18005a26e  push    r15
0x18005a270  lea     rbp, [rsp-20h]
0x18005a275  sub     rsp, 120h
0x18005a27c  mov     rax, cs:__security_cookie
0x18005a283  xor     rax, rsp
0x18005a286  mov     [rbp+50h+var_40], rax
0x18005a28a  xor     r13d, r13d
0x18005a28d  mov     r12d, edx
0x18005a290  mov     rbx, rcx
0x18005a293  mov     [rsp+150h+Size], r13
0x18005a298  mov     rcx, cs:fpSeekPrinter; Pointer
0x18005a29f  mov     [rsp+150h+var_F8], r13
0x18005a2a4  mov     [rsp+150h+var_E0], r13
0x18005a2a9  mov     [rsp+150h+var_100], r13d
0x18005a2ae  mov     [rbp+50h+var_C8], r13
0x18005a2b2  mov     qword ptr [rsp+150h+var_E8], r13
0x18005a2b7  call    cs:__imp_RtlDecodePointer
0x18005a2bd  mov     r14, rax
0x18005a2c0  mov     [rsp+150h+var_D8], rax
0x18005a2c5  cmp     [rbx+28h], r12d
0x18005a2c9  jb      short loc_18005A2FF
0x18005a2cb  mov     rcx, [rbx+10h]
0x18005a2cf  lea     esi, [r13+1]
0x18005a2d3  mov     r9d, esi
0x18005a2d6  mov     dword ptr [rsp+150h+var_130], r13d
0x18005a2db  mov     edx, r13d
0x18005a2de  xor     r8d, r8d
0x18005a2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a2e6  test    eax, eax
0x18005a2e8  jnz     short loc_18005A2F8
0x18005a2ea  call    cs:__imp_GetLastError
0x18005a2f0  cmp     eax, 3Fh ; '?'
0x18005a2f3  jnz     short loc_18005A2F8
0x18005a2f5  mov     esi, r13d
0x18005a2f8  mov     eax, esi
0x18005a2fa  jmp     loc_18005A3AD
0x18005a2ff  cmp     r12d, [rbx+38h]
0x18005a303  jbe     short loc_18005A37F
0x18005a305  cmp     r12d, 4E2000h
0x18005a30c  ja      loc_18005A3A0
0x18005a312  mov     rcx, gs:60h
0x18005a31b  lea     rdi, [r12+r12*4]
0x18005a31f  shl     rdi, 3
0x18005a323  xor     edx, edx; Flags
0x18005a325  mov     r8, rdi; Size
0x18005a328  mov     rcx, [rcx+30h]; HeapHandle
0x18005a32c  call    cs:__imp_RtlAllocateHeap
0x18005a332  mov     rsi, rax
0x18005a335  test    rax, rax
0x18005a338  jz      short loc_18005A3A0
0x18005a33a  mov     r8, rdi; Size
0x18005a33d  xor     edx, edx; Val
0x18005a33f  mov     rcx, rax; void *
0x18005a342  call    memset_0
0x18005a347  mov     ecx, [rbx+28h]
0x18005a34a  mov     rdx, [rbx+30h]; Src
0x18005a34e  lea     r8, [rcx+rcx*4]
0x18005a352  mov     rcx, rsi; void *
0x18005a355  shl     r8, 3; Size
0x18005a359  call    memcpy_0
0x18005a35e  mov     [rbx+38h], r12d
0x18005a362  xor     edx, edx; Flags
0x18005a364  mov     rcx, gs:60h
0x18005a36d  mov     r8, [rbx+30h]; P
0x18005a371  mov     rcx, [rcx+30h]; HeapHandle
0x18005a375  call    cs:__imp_RtlFreeHeap
0x18005a37b  mov     [rbx+30h], rsi
0x18005a37f  mov     eax, [rbx+28h]
0x18005a382  test    eax, eax
0x18005a384  jz      short loc_18005A3D4
0x18005a386  dec     eax
0x18005a388  lea     rdx, [rax+rax*4]
0x18005a38c  mov     rax, [rbx+30h]
0x18005a390  mov     rdi, [rax+rdx*8+10h]
0x18005a395  mov     r15, [rax+rdx*8+8]
0x18005a39a  mov     [rbp+50h+P], rdi
0x18005a39e  jmp     short loc_18005A41C
0x18005a3a0  mov     ecx, 8; dwErrCode
0x18005a3a5  call    cs:__imp_SetLastError
0x18005a3ab  xor     eax, eax
0x18005a3ad  mov     rcx, [rbp+50h+var_40]
0x18005a3b1  xor     rcx, rsp; StackCookie
0x18005a3b4  call    __security_check_cookie
0x18005a3b9  mov     rbx, [rsp+150h+arg_10]
0x18005a3c1  add     rsp, 120h
0x18005a3c8  pop     r15
0x18005a3ca  pop     r14
0x18005a3cc  pop     r13
0x18005a3ce  pop     r12
0x18005a3d0  pop     rdi
0x18005a3d1  pop     rsi
0x18005a3d2  pop     rbp
0x18005a3d3  retn
0x18005a3d4  mov     rcx, [rbx+10h]
0x18005a3d8  xorps   xmm0, xmm0
0x18005a3db  mov     rdx, r13
0x18005a3de  mov     dword ptr [rsp+150h+var_130], r13d
0x18005a3e3  xor     r9d, r9d
0x18005a3e6  xor     r8d, r8d
0x18005a3e9  mov     rax, r14
0x18005a3ec  movups  xmmword ptr [rbp+50h+var_C0], xmm0
0x18005a3f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a3f5  test    eax, eax
0x18005a3f7  jz      short loc_18005A3AB
0x18005a3f9  mov     rcx, [rbx+10h]; void *
0x18005a3fd  lea     rdx, [rbp+50h+var_C0]; unsigned __int8 *
0x18005a401  mov     r8d, 10h; unsigned int
0x18005a407  call    ?MyReadPrinter@@YAHPEAXPEAEK@Z; MyReadPrinter(void *,uchar *,ulong)
0x18005a40c  test    eax, eax
0x18005a40e  jz      short loc_18005A3AB
0x18005a410  mov     rax, [rbx+18h]
0x18005a414  mov     r15d, dword ptr [rbp+50h+var_C0+4]
0x18005a418  mov     [rbp+50h+P], rax
0x18005a41c  mov     rcx, [rbx+10h]
0x18005a420  xor     r9d, r9d
0x18005a423  xor     r8d, r8d
0x18005a426  mov     dword ptr [rsp+150h+var_130], r13d
0x18005a42b  mov     rdx, r15
0x18005a42e  mov     rax, r14
0x18005a431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a436  test    eax, eax
0x18005a438  jz      loc_18005A3AB
0x18005a43e  mov     r8d, [rbx+28h]
0x18005a442  mov     esi, 1
0x18005a447  mov     rdi, r13
0x18005a44a  mov     [rsp+150h+var_110], r8d
0x18005a44f  mov     [rsp+150h+var_FC], edi
0x18005a453  lea     r14d, [rsi+7]
0x18005a457  cmp     r8d, r12d
0x18005a45a  jnb     loc_18005AA13
0x18005a460  mov     rcx, [rbx+10h]; void *
0x18005a464  lea     rdx, [rsp+150h+Size]; unsigned __int8 *
0x18005a469  mov     r8d, r14d; unsigned int
0x18005a46c  call    ?MyReadPrinter@@YAHPEAXPEAEK@Z; MyReadPrinter(void *,uchar *,ulong)
0x18005a471  test    eax, eax
0x18005a473  jz      loc_18005AA13
0x18005a479  mov     edx, dword ptr [rsp+150h+Size+4]
0x18005a47d  add     r15, r14
0x18005a480  mov     r8d, [rsp+150h+var_110]
0x18005a485  test    edx, edx
0x18005a487  jz      short loc_18005A457
0x18005a489  mov     rax, [rsp+150h+Size]
0x18005a48e  cmp     eax, 5
0x18005a491  jz      short loc_18005A4E7
0x18005a493  cmp     eax, esi
0x18005a495  jbe     short loc_18005A4E7
0x18005a497  cmp     eax, 9
0x18005a49a  jnb     short loc_18005A4E7
0x18005a49c  mov     rcx, gs:60h
0x18005a4a5  mov     r8d, edx; Size
0x18005a4a8  xor     edx, edx; Flags
0x18005a4aa  mov     rcx, [rcx+30h]; HeapHandle
0x18005a4ae  call    cs:__imp_RtlAllocateHeap
0x18005a4b4  mov     rdi, rax
0x18005a4b7  test    rax, rax
0x18005a4ba  jz      loc_18005AA30
0x18005a4c0  mov     r8d, dword ptr [rsp+150h+Size+4]; unsigned int
0x18005a4c5  mov     rdx, rax; unsigned __int8 *
0x18005a4c8  mov     rcx, [rbx+10h]; void *
0x18005a4cc  call    ?MyReadPrinter@@YAHPEAXPEAEK@Z; MyReadPrinter(void *,uchar *,ulong)
0x18005a4d1  test    eax, eax
0x18005a4d3  jz      loc_18005AA18
0x18005a4d9  mov     r13d, dword ptr [rsp+150h+Size+4]
0x18005a4de  mov     [rsp+150h+var_F0], esi
0x18005a4e2  jmp     loc_18005A5BB
0x18005a4e7  lea     ecx, [rax-0Fh]
0x18005a4ea  mov     [rsp+150h+var_F0], 0
0x18005a4f2  cmp     ecx, 4
0x18005a4f5  jbe     short loc_18005A500
0x18005a4f7  cmp     eax, 15h
0x18005a4fa  jnz     loc_18005A5BB
0x18005a500  cmp     edx, r14d
0x18005a503  jb      loc_18005AA13
0x18005a509  mov     rcx, [rbx+10h]; void *
0x18005a50d  lea     rdx, [rsp+150h+var_E8]; unsigned __int8 *
0x18005a512  mov     r8d, r14d; unsigned int
0x18005a515  call    ?MyReadPrinter@@YAHPEAXPEAEK@Z; MyReadPrinter(void *,uchar *,ulong)
0x18005a51a  test    eax, eax
0x18005a51c  jz      loc_18005AA13
0x18005a522  mov     rax, qword ptr [rsp+150h+var_E8]
0x18005a527  test    rax, rax
0x18005a52a  jle     loc_18005AA13
0x18005a530  mov     rcx, [rbx+10h]
0x18005a534  mov     rdx, 0FFFFFFFFFFFFFFF0h
0x18005a53b  sub     rdx, rax
0x18005a53e  mov     dword ptr [rsp+150h+var_130], 0
0x18005a546  mov     rax, [rsp+150h+var_D8]
0x18005a54b  mov     r9d, esi
0x18005a54e  xor     r8d, r8d
0x18005a551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a556  test    eax, eax
0x18005a558  jz      loc_18005AA13
0x18005a55e  mov     rcx, [rbx+10h]; void *
0x18005a562  lea     rdx, [rsp+150h+var_F8]; unsigned __int8 *
0x18005a567  mov     r8d, r14d; unsigned int
0x18005a56a  call    ?MyReadPrinter@@YAHPEAXPEAEK@Z; MyReadPrinter(void *,uchar *,ulong)
0x18005a56f  test    eax, eax
0x18005a571  jz      loc_18005AA13
0x18005a577  mov     rcx, gs:60h
0x18005a580  xor     edx, edx; Flags
0x18005a582  mov     r8d, dword ptr [rsp+150h+var_F8+4]; Size
0x18005a587  mov     rcx, [rcx+30h]; HeapHandle
0x18005a58b  call    cs:__imp_RtlAllocateHeap
0x18005a591  mov     rdi, rax
0x18005a594  test    rax, rax
0x18005a597  jz      loc_18005AA30
0x18005a59d  mov     r8d, dword ptr [rsp+150h+var_F8+4]; unsigned int
0x18005a5a2  mov     rdx, rax; unsigned __int8 *
0x18005a5a5  mov     rcx, [rbx+10h]; void *
0x18005a5a9  call    ?MyReadPrinter@@YAHPEAXPEAEK@Z; MyReadPrinter(void *,uchar *,ulong)
0x18005a5ae  test    eax, eax
0x18005a5b0  jz      loc_18005AA18
0x18005a5b6  mov     r13d, dword ptr [rsp+150h+var_F8+4]
0x18005a5bb  mov     rcx, cs:fpIsValidDevmodeW; Pointer
0x18005a5c2  call    cs:__imp_RtlDecodePointer
0x18005a5c8  mov     r8, rax
0x18005a5cb  mov     eax, dword ptr [rsp+150h+Size]
0x18005a5cf  cmp     eax, 0Bh
0x18005a5d2  ja      loc_18005A707
0x18005a5d8  jz      loc_18005A6A9
0x18005a5de  cmp     eax, 6
0x18005a5e1  ja      loc_18005A68C
0x18005a5e7  jz      loc_18005A850
0x18005a5ed  sub     eax, esi
0x18005a5ef  jz      loc_18005A6A9
0x18005a5f5  sub     eax, esi
0x18005a5f7  jz      loc_18005A733
0x18005a5fd  sub     eax, esi
0x18005a5ff  jz      short loc_18005A667
0x18005a601  sub     eax, esi
0x18005a603  jz      loc_18005A733
0x18005a609  cmp     eax, esi
0x18005a60b  jnz     loc_18005AA13
0x18005a611  mov     rcx, gs:60h
0x18005a61a  xor     edx, edx; Flags
0x18005a61c  mov     rcx, [rcx+30h]; HeapHandle
0x18005a620  lea     r8d, [rdx+18h]; Size
0x18005a624  call    cs:__imp_RtlAllocateHeap
0x18005a62a  test    rax, rax
0x18005a62d  jz      loc_18005AA13
0x18005a633  mov     ecx, [rsp+150h+var_110]
0x18005a637  lea     r8, [rcx+rcx*4]
0x18005a63b  mov     rcx, [rbx+30h]
0x18005a63f  mov     rdx, [rcx+r8*8+20h]
0x18005a644  mov     [rax], rdx
0x18005a647  mov     rcx, [rbx+30h]
0x18005a64b  mov     [rcx+r8*8+20h], rax
0x18005a650  mov     ecx, dword ptr [rsp+150h+Size]
0x18005a654  mov     [rax+14h], ecx
0x18005a657  mov     ecx, dword ptr [rsp+150h+Size+4]
0x18005a65b  mov     [rax+10h], ecx
0x18005a65e  mov     [rax+8], r15
0x18005a662  jmp     loc_18005A91B
0x18005a667  mov     edx, r13d
0x18005a66a  mov     rcx, rdi
0x18005a66d  mov     rax, r8
0x18005a670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a675  test    eax, eax
0x18005a677  jz      loc_18005AA13
0x18005a67d  mov     [rbp+50h+P], rdi
0x18005a681  xor     edi, edi
0x18005a683  mov     [rsp+150h+var_FC], esi
0x18005a687  jmp     loc_18005A91B
0x18005a68c  sub     eax, 7
0x18005a68f  jz      loc_18005A8D0
0x18005a695  sub     eax, esi
0x18005a697  jz      loc_18005A890
0x18005a69d  sub     eax, esi
0x18005a69f  jz      short loc_18005A6A9
0x18005a6a1  cmp     eax, esi
0x18005a6a3  jnz     loc_18005AA13
0x18005a6a9  mov     rax, [rbx+30h]
0x18005a6ad  mov     rcx, [rbp+50h+P]
0x18005a6b1  mov     r8d, [rsp+150h+var_110]
0x18005a6b6  mov     [rsp+150h+var_FC], 0
0x18005a6be  lea     rdx, [r8+r8*4]
0x18005a6c2  mov     [rax+rdx*8+10h], rcx
0x18005a6c7  mov     rax, [rbx+30h]
0x18005a6cb  mov     [rax+rdx*8], r15
0x18005a6cf  mov     rax, [rbx+30h]
0x18005a6d3  mov     ecx, dword ptr [rsp+150h+Size+4]
0x18005a6d7  add     rcx, r15
0x18005a6da  mov     [rax+rdx*8+8], rcx
0x18005a6df  mov     rcx, [rbx+30h]
0x18005a6e3  mov     eax, dword ptr [rsp+150h+Size+4]
0x18005a6e7  mov     [rcx+rdx*8+18h], eax
0x18005a6eb  mov     rcx, [rbx+30h]
0x18005a6ef  mov     eax, dword ptr [rsp+150h+Size]
0x18005a6f3  mov     [rcx+rdx*8+1Ch], eax
0x18005a6f7  add     [rbx+28h], esi
0x18005a6fa  add     r8d, esi
0x18005a6fd  mov     [rsp+150h+var_110], r8d
0x18005a702  jmp     loc_18005A91B
  ... truncated ...
```
