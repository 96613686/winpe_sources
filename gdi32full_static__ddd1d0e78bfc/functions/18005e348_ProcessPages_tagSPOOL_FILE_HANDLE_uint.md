# ProcessPages(tagSPOOL_FILE_HANDLE *,uint)

- ea: `0x18005e348`
- end: `0x18005ebbd`
- name: `?ProcessPages@@YAHPEAUtagSPOOL_FILE_HANDLE@@I@Z`
- size: `2165`
- prototype: `__int64 __fastcall(struct tagSPOOL_FILE_HANDLE *, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18005e260`
- `0x18009a8f0`
- `0x18009a960`

## callees

- `0x18005e348`
- `0x18005f0b4`
- `0x18007f800`
- `0x180080604`
- `0x180085538`
- `0x1800a68d4`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e3d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e3d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e4ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e4ac`
- `ntdll!RtlFreeHeap` at `0x18005e473`
- `ntdll!RtlFreeHeap` at `0x18005eb45`
- `ntdll!RtlFreeHeap` at `0x18005eb74`
- `ntdll!RtlFreeHeap` at `0x18005eba2`
- `ntdll!RtlFreeHeap` at `0x18005e473`
- `ntdll!RtlFreeHeap` at `0x18005eb45`
- `ntdll!RtlFreeHeap` at `0x18005eb74`
- `ntdll!RtlFreeHeap` at `0x18005eba2`
- `ntdll!RtlAllocateHeap` at `0x18005e424`
- `ntdll!RtlAllocateHeap` at `0x18005e5bc`
- `ntdll!RtlAllocateHeap` at `0x18005e69f`
- `ntdll!RtlAllocateHeap` at `0x18005e744`
- `ntdll!RtlAllocateHeap` at `0x18005e424`
- `ntdll!RtlAllocateHeap` at `0x18005e5bc`
- `ntdll!RtlAllocateHeap` at `0x18005e69f`
- `ntdll!RtlAllocateHeap` at `0x18005e744`
- `ntdll!RtlDecodePointer` at `0x18005e39f`
- `ntdll!RtlDecodePointer` at `0x18005e6dc`
- `ntdll!RtlDecodePointer` at `0x18005e39f`
- `ntdll!RtlDecodePointer` at `0x18005e6dc`
- `win32u!NtGdiRemoveMergeFont` at `0x18005ea00`
- `win32u!NtGdiRemoveMergeFont` at `0x18005ea00`
- `win32u!NtGdiAddRemoteMMInstanceToDC` at `0x18005e986`
- `win32u!NtGdiAddRemoteMMInstanceToDC` at `0x18005e986`
- `win32u!NtGdiAddRemoteFontToDC` at `0x18005e866`
- `win32u!NtGdiAddRemoteFontToDC` at `0x18005ea53`
- `win32u!NtGdiAddRemoteFontToDC` at `0x18005e866`
- `win32u!NtGdiAddRemoteFontToDC` at `0x18005ea53`
- `win32u!NtGdiAddEmbFontToDC` at `0x18005e9b7`
- `win32u!NtGdiAddEmbFontToDC` at `0x18005e9b7`

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
0x18005e348  mov     [rsp-8+arg_10], rbx
0x18005e34d  push    rbp
0x18005e34e  push    rsi
0x18005e34f  push    rdi
0x18005e350  push    r12
0x18005e352  push    r13
0x18005e354  push    r14
0x18005e356  push    r15
0x18005e358  lea     rbp, [rsp-20h]
0x18005e35d  sub     rsp, 120h
0x18005e364  mov     rax, cs:__security_cookie
0x18005e36b  xor     rax, rsp
0x18005e36e  mov     [rbp+50h+var_40], rax
0x18005e372  xor     r13d, r13d
0x18005e375  mov     r12d, edx
0x18005e378  mov     rbx, rcx
0x18005e37b  mov     [rsp+150h+Size], r13
0x18005e380  mov     rcx, cs:fpSeekPrinter; Pointer
0x18005e387  mov     [rsp+150h+var_F8], r13
0x18005e38c  mov     [rsp+150h+var_E0], r13
0x18005e391  mov     [rsp+150h+var_100], r13d
0x18005e396  mov     [rbp+50h+var_C8], r13
0x18005e39a  mov     qword ptr [rsp+150h+var_E8], r13
0x18005e39f  call    cs:__imp_RtlDecodePointer
0x18005e3a6  nop     dword ptr [rax+rax+00h]
0x18005e3ab  mov     r14, rax
0x18005e3ae  mov     [rsp+150h+var_D8], rax
0x18005e3b3  cmp     [rbx+28h], r12d
0x18005e3b7  jb      short loc_18005E3F3
0x18005e3b9  mov     rcx, [rbx+10h]
0x18005e3bd  lea     esi, [r13+1]
0x18005e3c1  mov     r9d, esi
0x18005e3c4  mov     dword ptr [rsp+150h+var_130], r13d
0x18005e3c9  mov     edx, r13d
0x18005e3cc  xor     r8d, r8d
0x18005e3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e3d4  test    eax, eax
0x18005e3d6  jnz     short loc_18005E3EC
0x18005e3d8  call    cs:__imp_GetLastError
0x18005e3df  nop     dword ptr [rax+rax+00h]
0x18005e3e4  cmp     eax, 3Fh ; '?'
0x18005e3e7  jnz     short loc_18005E3EC
0x18005e3e9  mov     esi, r13d
0x18005e3ec  mov     eax, esi
0x18005e3ee  jmp     loc_18005E4BA
0x18005e3f3  cmp     r12d, [rbx+38h]
0x18005e3f7  jbe     loc_18005E483
0x18005e3fd  cmp     r12d, 4E2000h
0x18005e404  ja      loc_18005E4A7
0x18005e40a  mov     rcx, gs:60h
0x18005e413  lea     rdi, [r12+r12*4]
0x18005e417  shl     rdi, 3
0x18005e41b  xor     edx, edx; Flags
0x18005e41d  mov     r8, rdi; Size
0x18005e420  mov     rcx, [rcx+30h]; HeapHandle
0x18005e424  call    cs:__imp_RtlAllocateHeap
0x18005e42b  nop     dword ptr [rax+rax+00h]
0x18005e430  mov     rsi, rax
0x18005e433  test    rax, rax
0x18005e436  jz      short loc_18005E4A7
0x18005e438  mov     r8, rdi; Size
0x18005e43b  xor     edx, edx; Val
0x18005e43d  mov     rcx, rax; void *
0x18005e440  call    memset_0
0x18005e445  mov     ecx, [rbx+28h]
0x18005e448  mov     rdx, [rbx+30h]; Src
0x18005e44c  lea     r8, [rcx+rcx*4]
0x18005e450  mov     rcx, rsi; void *
0x18005e453  shl     r8, 3; Size
0x18005e457  call    memcpy_0
0x18005e45c  mov     [rbx+38h], r12d
0x18005e460  xor     edx, edx; Flags
0x18005e462  mov     rcx, gs:60h
0x18005e46b  mov     r8, [rbx+30h]; P
0x18005e46f  mov     rcx, [rcx+30h]; HeapHandle
0x18005e473  call    cs:__imp_RtlFreeHeap
0x18005e47a  nop     dword ptr [rax+rax+00h]
0x18005e47f  mov     [rbx+30h], rsi
0x18005e483  mov     eax, [rbx+28h]
0x18005e486  test    eax, eax
0x18005e488  jz      short loc_18005E4E2
0x18005e48a  dec     eax
0x18005e48c  lea     rdx, [rax+rax*4]
0x18005e490  mov     rax, [rbx+30h]
0x18005e494  mov     rdi, [rax+rdx*8+10h]
0x18005e499  mov     r15, [rax+rdx*8+8]
0x18005e49e  mov     [rbp+50h+P], rdi
0x18005e4a2  jmp     loc_18005E52A
0x18005e4a7  mov     ecx, 8; dwErrCode
0x18005e4ac  call    cs:__imp_SetLastError
0x18005e4b3  nop     dword ptr [rax+rax+00h]
0x18005e4b8  xor     eax, eax
0x18005e4ba  mov     rcx, [rbp+50h+var_40]
0x18005e4be  xor     rcx, rsp; StackCookie
0x18005e4c1  call    __security_check_cookie
0x18005e4c6  mov     rbx, [rsp+150h+arg_10]
0x18005e4ce  add     rsp, 120h
0x18005e4d5  pop     r15
0x18005e4d7  pop     r14
0x18005e4d9  pop     r13
0x18005e4db  pop     r12
0x18005e4dd  pop     rdi
0x18005e4de  pop     rsi
0x18005e4df  pop     rbp
0x18005e4e0  retn
0x18005e4e2  mov     rcx, [rbx+10h]
0x18005e4e6  xorps   xmm0, xmm0
0x18005e4e9  mov     rdx, r13
0x18005e4ec  mov     dword ptr [rsp+150h+var_130], r13d
0x18005e4f1  xor     r9d, r9d
0x18005e4f4  xor     r8d, r8d
0x18005e4f7  mov     rax, r14
0x18005e4fa  movups  xmmword ptr [rbp+50h+var_C0], xmm0
0x18005e4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e503  test    eax, eax
0x18005e505  jz      short loc_18005E4B8
0x18005e507  mov     rcx, [rbx+10h]; void *
0x18005e50b  lea     rdx, [rbp+50h+var_C0]; unsigned __int8 *
0x18005e50f  mov     r8d, 10h; unsigned int
0x18005e515  call    ?MyReadPrinter@@YAHPEAXPEAEK@Z; MyReadPrinter(void *,uchar *,ulong)
0x18005e51a  test    eax, eax
0x18005e51c  jz      short loc_18005E4B8
0x18005e51e  mov     rax, [rbx+18h]
0x18005e522  mov     r15d, dword ptr [rbp+50h+var_C0+4]
0x18005e526  mov     [rbp+50h+P], rax
0x18005e52a  mov     rcx, [rbx+10h]
0x18005e52e  xor     r9d, r9d
0x18005e531  xor     r8d, r8d
0x18005e534  mov     dword ptr [rsp+150h+var_130], r13d
0x18005e539  mov     rdx, r15
0x18005e53c  mov     rax, r14
0x18005e53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e544  test    eax, eax
0x18005e546  jz      loc_18005E4B8
0x18005e54c  mov     r8d, [rbx+28h]
0x18005e550  mov     esi, 1
0x18005e555  mov     rdi, r13
0x18005e558  mov     [rsp+150h+var_110], r8d
0x18005e55d  mov     [rsp+150h+var_FC], edi
0x18005e561  lea     r14d, [rsi+7]
0x18005e565  cmp     r8d, r12d
0x18005e568  jnb     loc_18005EB5D
0x18005e56e  mov     rcx, [rbx+10h]; void *
0x18005e572  lea     rdx, [rsp+150h+Size]; unsigned __int8 *
0x18005e577  mov     r8d, r14d; unsigned int
0x18005e57a  call    ?MyReadPrinter@@YAHPEAXPEAEK@Z; MyReadPrinter(void *,uchar *,ulong)
0x18005e57f  test    eax, eax
0x18005e581  jz      loc_18005EB5D
0x18005e587  mov     edx, dword ptr [rsp+150h+Size+4]
0x18005e58b  add     r15, r14
0x18005e58e  mov     r8d, [rsp+150h+var_110]
0x18005e593  test    edx, edx
0x18005e595  jz      short loc_18005E565
0x18005e597  mov     rax, [rsp+150h+Size]
0x18005e59c  cmp     eax, 5
0x18005e59f  jz      short loc_18005E5FB
0x18005e5a1  cmp     eax, esi
0x18005e5a3  jbe     short loc_18005E5FB
0x18005e5a5  cmp     eax, 9
0x18005e5a8  jnb     short loc_18005E5FB
0x18005e5aa  mov     rcx, gs:60h
0x18005e5b3  mov     r8d, edx; Size
0x18005e5b6  xor     edx, edx; Flags
0x18005e5b8  mov     rcx, [rcx+30h]; HeapHandle
0x18005e5bc  call    cs:__imp_RtlAllocateHeap
0x18005e5c3  nop     dword ptr [rax+rax+00h]
0x18005e5c8  mov     rdi, rax
0x18005e5cb  test    rax, rax
0x18005e5ce  jz      loc_18005EB80
0x18005e5d4  mov     r8d, dword ptr [rsp+150h+Size+4]; unsigned int
0x18005e5d9  mov     rdx, rax; unsigned __int8 *
0x18005e5dc  mov     rcx, [rbx+10h]; void *
0x18005e5e0  call    ?MyReadPrinter@@YAHPEAXPEAEK@Z; MyReadPrinter(void *,uchar *,ulong)
0x18005e5e5  test    eax, eax
0x18005e5e7  jz      loc_18005EB62
0x18005e5ed  mov     r13d, dword ptr [rsp+150h+Size+4]
0x18005e5f2  mov     [rsp+150h+var_F0], esi
0x18005e5f6  jmp     loc_18005E6D5
0x18005e5fb  lea     ecx, [rax-0Fh]
0x18005e5fe  mov     [rsp+150h+var_F0], 0
0x18005e606  cmp     ecx, 4
0x18005e609  jbe     short loc_18005E614
0x18005e60b  cmp     eax, 15h
0x18005e60e  jnz     loc_18005E6D5
0x18005e614  cmp     edx, r14d
0x18005e617  jb      loc_18005EB5D
0x18005e61d  mov     rcx, [rbx+10h]; void *
0x18005e621  lea     rdx, [rsp+150h+var_E8]; unsigned __int8 *
0x18005e626  mov     r8d, r14d; unsigned int
0x18005e629  call    ?MyReadPrinter@@YAHPEAXPEAEK@Z; MyReadPrinter(void *,uchar *,ulong)
0x18005e62e  test    eax, eax
0x18005e630  jz      loc_18005EB5D
0x18005e636  mov     rax, qword ptr [rsp+150h+var_E8]
0x18005e63b  test    rax, rax
0x18005e63e  jle     loc_18005EB5D
0x18005e644  mov     rcx, [rbx+10h]
0x18005e648  mov     rdx, 0FFFFFFFFFFFFFFF0h
0x18005e64f  sub     rdx, rax
0x18005e652  mov     dword ptr [rsp+150h+var_130], 0
0x18005e65a  mov     rax, [rsp+150h+var_D8]
0x18005e65f  mov     r9d, esi
0x18005e662  xor     r8d, r8d
0x18005e665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e66a  test    eax, eax
0x18005e66c  jz      loc_18005EB5D
0x18005e672  mov     rcx, [rbx+10h]; void *
0x18005e676  lea     rdx, [rsp+150h+var_F8]; unsigned __int8 *
0x18005e67b  mov     r8d, r14d; unsigned int
0x18005e67e  call    ?MyReadPrinter@@YAHPEAXPEAEK@Z; MyReadPrinter(void *,uchar *,ulong)
0x18005e683  test    eax, eax
0x18005e685  jz      loc_18005EB5D
0x18005e68b  mov     rcx, gs:60h
0x18005e694  xor     edx, edx; Flags
0x18005e696  mov     r8d, dword ptr [rsp+150h+var_F8+4]; Size
0x18005e69b  mov     rcx, [rcx+30h]; HeapHandle
0x18005e69f  call    cs:__imp_RtlAllocateHeap
0x18005e6a6  nop     dword ptr [rax+rax+00h]
0x18005e6ab  mov     rdi, rax
0x18005e6ae  test    rax, rax
0x18005e6b1  jz      loc_18005EB80
0x18005e6b7  mov     r8d, dword ptr [rsp+150h+var_F8+4]; unsigned int
0x18005e6bc  mov     rdx, rax; unsigned __int8 *
0x18005e6bf  mov     rcx, [rbx+10h]; void *
0x18005e6c3  call    ?MyReadPrinter@@YAHPEAXPEAEK@Z; MyReadPrinter(void *,uchar *,ulong)
0x18005e6c8  test    eax, eax
0x18005e6ca  jz      loc_18005EB62
0x18005e6d0  mov     r13d, dword ptr [rsp+150h+var_F8+4]
0x18005e6d5  mov     rcx, cs:fpIsValidDevmodeW; Pointer
0x18005e6dc  call    cs:__imp_RtlDecodePointer
0x18005e6e3  nop     dword ptr [rax+rax+00h]
0x18005e6e8  mov     r8, rax
0x18005e6eb  mov     eax, dword ptr [rsp+150h+Size]
0x18005e6ef  cmp     eax, 0Bh
0x18005e6f2  ja      loc_18005E82D
0x18005e6f8  jz      loc_18005E7CF
0x18005e6fe  cmp     eax, 6
0x18005e701  ja      loc_18005E7B2
0x18005e707  jz      loc_18005E97C
0x18005e70d  sub     eax, esi
0x18005e70f  jz      loc_18005E7CF
0x18005e715  sub     eax, esi
0x18005e717  jz      loc_18005E859
0x18005e71d  sub     eax, esi
0x18005e71f  jz      short loc_18005E78D
0x18005e721  sub     eax, esi
0x18005e723  jz      loc_18005E859
0x18005e729  cmp     eax, esi
0x18005e72b  jnz     loc_18005EB5D
0x18005e731  mov     rcx, gs:60h
0x18005e73a  xor     edx, edx; Flags
0x18005e73c  mov     rcx, [rcx+30h]; HeapHandle
0x18005e740  lea     r8d, [rdx+18h]; Size
0x18005e744  call    cs:__imp_RtlAllocateHeap
0x18005e74b  nop     dword ptr [rax+rax+00h]
0x18005e750  test    rax, rax
0x18005e753  jz      loc_18005EB5D
0x18005e759  mov     ecx, [rsp+150h+var_110]
0x18005e75d  lea     r8, [rcx+rcx*4]
0x18005e761  mov     rcx, [rbx+30h]
0x18005e765  mov     rdx, [rcx+r8*8+20h]
0x18005e76a  mov     [rax], rdx
0x18005e76d  mov     rcx, [rbx+30h]
0x18005e771  mov     [rcx+r8*8+20h], rax
0x18005e776  mov     ecx, dword ptr [rsp+150h+Size]
0x18005e77a  mov     [rax+14h], ecx
0x18005e77d  mov     ecx, dword ptr [rsp+150h+Size+4]
0x18005e781  mov     [rax+10h], ecx
0x18005e784  mov     [rax+8], r15
0x18005e788  jmp     loc_18005EA5F
0x18005e78d  mov     edx, r13d
0x18005e790  mov     rcx, rdi
0x18005e793  mov     rax, r8
0x18005e796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e79b  test    eax, eax
0x18005e79d  jz      loc_18005EB5D
0x18005e7a3  mov     [rbp+50h+P], rdi
0x18005e7a7  xor     edi, edi
0x18005e7a9  mov     [rsp+150h+var_FC], esi
0x18005e7ad  jmp     loc_18005EA5F
0x18005e7b2  sub     eax, 7
0x18005e7b5  jz      loc_18005EA0E
0x18005e7bb  sub     eax, esi
0x18005e7bd  jz      loc_18005E9C8
0x18005e7c3  sub     eax, esi
0x18005e7c5  jz      short loc_18005E7CF
0x18005e7c7  cmp     eax, esi
0x18005e7c9  jnz     loc_18005EB5D
0x18005e7cf  mov     rax, [rbx+30h]
0x18005e7d3  mov     rcx, [rbp+50h+P]
0x18005e7d7  mov     r8d, [rsp+150h+var_110]
0x18005e7dc  mov     [rsp+150h+var_FC], 0
0x18005e7e4  lea     rdx, [r8+r8*4]
0x18005e7e8  mov     [rax+rdx*8+10h], rcx
0x18005e7ed  mov     rax, [rbx+30h]
0x18005e7f1  mov     [rax+rdx*8], r15
0x18005e7f5  mov     rax, [rbx+30h]
0x18005e7f9  mov     ecx, dword ptr [rsp+150h+Size+4]
0x18005e7fd  add     rcx, r15
0x18005e800  mov     [rax+rdx*8+8], rcx
0x18005e805  mov     rcx, [rbx+30h]
  ... truncated ...
```
