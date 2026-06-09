# PROXYPORT::DocumentEvent(unsigned __int64,void *,HDC__ *,int,ulong,void *,ulong,void *)

- ea: `0x18003f05c`
- end: `0x18003fa58`
- name: `?DocumentEvent@PROXYPORT@@QEAAH_KPEAXPEAUHDC__@@HK1K1@Z`
- size: `2556`
- prototype: `__int64 __usercall@<rax>(PROXYPORT *__hidden this@<rcx>, unsigned __int64@<rdx>, void *@<r8>, HDC@<r9>, int, unsigned int, void *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18003eb04`

## callees

- `0x18003f05c`
- `0x180040ba0`
- `0x180040be4`
- `0x180040c4c`
- `0x180040c74`
- `0x180040cb4`
- `0x18006b8d4`
- `0x1800756cc`
- `0x1800a68d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003f0f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003f0f7`
- `GDI32!GdiGetEntry` at `0x18003f55d`
- `GDI32!GdiGetEntry` at `0x18003f74a`
- `GDI32!GdiGetEntry` at `0x18003f55d`
- `GDI32!GdiGetEntry` at `0x18003f74a`
- `GDI32!gW32PID` at `0x18003f5a3`
- `GDI32!gW32PID` at `0x18003f78d`
- `GDI32!gCookie` at `0x18003f5b5`
- `GDI32!gCookie` at `0x18003f79f`
- `GDI32!gMaxGdiHandleCount` at `0x18003f538`
- `GDI32!gMaxGdiHandleCount` at `0x18003f725`
- `GDI32!GdiSetLastError` at `0x18003fa19`
- `GDI32!GdiSetLastError` at `0x18003fa19`
- `ntdll!RtlFreeHeap` at `0x18003f3e4`
- `ntdll!RtlFreeHeap` at `0x18003f9fc`
- `ntdll!RtlFreeHeap` at `0x18003fa45`
- `ntdll!RtlFreeHeap` at `0x18003f3e4`
- `ntdll!RtlFreeHeap` at `0x18003f9fc`
- `ntdll!RtlFreeHeap` at `0x18003fa45`
- `ntdll!RtlAllocateHeap` at `0x18003f4c7`
- `ntdll!RtlAllocateHeap` at `0x18003f4c7`
- `USER32!GetActiveWindow` at `0x18003f6a1`
- `USER32!GetActiveWindow` at `0x18003f6a1`
- `win32u!NtGdiMakeObjectUnXferable` at `0x18003f6fb`
- `win32u!NtGdiMakeObjectUnXferable` at `0x18003f6fb`
- `win32u!NtGdiMakeObjectXferable` at `0x18003f689`
- `win32u!NtGdiMakeObjectXferable` at `0x18003f689`

## pseudocode

```c
__int64 __fastcall PROXYPORT::DocumentEvent(
        PROXYPORT *this,
        __int64 a2,
        void *a3,
        HDC a4,
        int a5,
        unsigned int a6,
        __int64 *a7,
        unsigned int Size,
        unsigned __int64 *a9)
{
  int v10; // r14d
  unsigned __int8 *v12; // rax
  __int64 *v13; // rcx
  unsigned __int8 *v14; // rsi
  __int64 v15; // rcx
  unsigned __int8 *v16; // r15
  __int64 v17; // r10
  int v18; // r14d
  struct _OffsetPointer *v19; // rdx
  unsigned int v20; // r14d
  unsigned __int8 *v21; // r11
  unsigned __int8 *v22; // r11
  unsigned int v23; // r8d
  __int64 v25; // r14
  unsigned __int8 *v26; // rax
  unsigned __int8 **v27; // r11
  unsigned __int8 *v28; // rax
  struct _OffsetPointer *v29; // rdx
  unsigned __int8 *v30; // r13
  int v31; // eax
  unsigned __int64 Heap; // r13
  unsigned __int8 *v33; // rax
  unsigned __int8 **v34; // r11
  __int64 v35; // rax
  unsigned int v36; // ecx
  __int64 v37; // rdx
  struct _OffsetPointer *v38; // r14
  __int64 v39; // rax
  unsigned __int8 *v40; // rax
  PROXYPORT *v41; // rcx
  unsigned __int8 **v42; // r11
  unsigned __int8 *v43; // rax
  unsigned __int8 *v44; // rax
  unsigned int v45; // eax
  HDC v46; // r11
  _OWORD *v47; // rdx
  int Entry; // eax
  _OWORD *v49; // r8
  _OWORD *v50; // rax
  _OWORD *v51; // rcx
  __int64 v52; // rdx
  int v53; // r14d
  unsigned int v54; // eax
  _OWORD *v55; // r14
  _OWORD *v56; // rdx
  int v57; // eax
  _OWORD *v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rcx
  unsigned __int8 *v61; // rdx
  __int64 v62; // rax
  const void *v63; // rax
  size_t v64; // r9
  unsigned __int8 *v65; // rdx
  unsigned __int8 *v66; // rax
  __int64 v67; // r14
  __int64 v68; // rdx
  unsigned __int8 *v69; // rdx
  _QWORD *v70; // [rsp+30h] [rbp-1F8h]
  int v71; // [rsp+38h] [rbp-1F0h]
  unsigned int v72; // [rsp+3Ch] [rbp-1ECh]
  int ObjectXferable; // [rsp+40h] [rbp-1E8h]
  __int128 v74; // [rsp+48h] [rbp-1E0h] BYREF
  __int64 v75; // [rsp+58h] [rbp-1D0h]
  struct _OffsetPointer *v76; // [rsp+60h] [rbp-1C8h]
  _OWORD *v77; // [rsp+68h] [rbp-1C0h]
  unsigned __int8 *v78; // [rsp+70h] [rbp-1B8h]
  _QWORD *v79; // [rsp+78h] [rbp-1B0h]
  unsigned __int8 *v80; // [rsp+80h] [rbp-1A8h]
  _DWORD *v81; // [rsp+88h] [rbp-1A0h]
  _BYTE v82[368]; // [rsp+90h] [rbp-198h] BYREF

  v10 = (int)a3;
  if ( (*(_BYTE *)(*(_QWORD *)this + 108LL) & 2) == 0 )
    *(_DWORD *)(*(_QWORD *)this + 88LL) = 0;
  v12 = PROXYPORT::HeapAlloc(this, 0x60u);
  v14 = v12;
  v80 = v12;
  if ( !v12 )
    return 0xFFFFFFFFLL;
  v15 = *v13;
  v16 = &v12[-*(_QWORD *)(v15 + 80)];
  if ( v12 == *(unsigned __int8 **)(v15 + 80) )
    return 0xFFFFFFFFLL;
  v78 = PROXYPORT::HeapAlloc(this, 4u);
  if ( !v78 )
    return 0xFFFFFFFFLL;
  *((_DWORD *)v16 + 1) = 109;
  *v16 = 0;
  *((_QWORD *)v16 + 3) = v17;
  *((_DWORD *)v16 + 8) = GetCurrentProcessId();
  *((_DWORD *)v16 + 9) = v10;
  v81 = v16 + 40;
  *((_DWORD *)v16 + 10) = 0;
  *((_QWORD *)v16 + 6) = a4;
  v18 = a5;
  *((_DWORD *)v16 + 14) = a5;
  *((_DWORD *)v16 + 15) = a6;
  v19 = (struct _OffsetPointer *)(v16 + 64);
  v79 = v16 + 64;
  *((_QWORD *)v16 + 8) = 0;
  *((_DWORD *)v16 + 18) = Size;
  v70 = v16 + 80;
  *((_QWORD *)v16 + 10) = 0;
  *((_QWORD *)v16 + 11) = 0;
  if ( !a6 || !a7 )
    goto LABEL_34;
  if ( a5 == 1 )
  {
    v20 = 32;
  }
  else
  {
    v21 = 0;
    if ( (unsigned int)(a5 - 2) <= 3 )
    {
      v20 = 8;
    }
    else
    {
      v20 = 0;
      v19 = (struct _OffsetPointer *)(v16 + 64);
      if ( a5 == 11 )
        v20 = 16;
    }
    if ( !v20 )
      goto LABEL_17;
  }
  v22 = PROXYPORT::HeapAllocOffset(this, v20, v14);
  v19 = (struct _OffsetPointer *)(v16 + 64);
  *((_QWORD *)v16 + 8) = v22;
  if ( !v22 )
    return 0xFFFFFFFFLL;
  *((_DWORD *)v16 + 15) = v20;
  v21 = &v22[(_QWORD)v14 - *(_QWORD *)(*(_QWORD *)this + 80LL)];
LABEL_17:
  v18 = a5;
  switch ( a5 )
  {
    case 1:
      *(_QWORD *)v21 = 0;
      *((_QWORD *)v21 + 1) = a7[1];
      v38 = (struct _OffsetPointer *)(v21 + 16);
      *((_QWORD *)v21 + 2) = a7[2];
      *((_DWORD *)v21 + 6) = *((_DWORD *)a7 + 6);
      v39 = a7[2];
      if ( !v39 )
      {
LABEL_33:
        v18 = a5;
        goto LABEL_34;
      }
      if ( *(unsigned __int16 *)(v39 + 68) + (unsigned int)*(unsigned __int16 *)(v39 + 70) < *(unsigned __int16 *)(v39 + 68)
        || !PROXYPORT::ThunkStr(this, (struct _OffsetPointer *)(v21 + 8), v14) )
      {
        return 0xFFFFFFFFLL;
      }
      v31 = PROXYPORT::ThunkMemBlock(
              this,
              v38,
              *(unsigned __int16 *)(a7[2] + 68) + *(unsigned __int16 *)(a7[2] + 70),
              v14);
LABEL_32:
      if ( !v31 )
        return 0xFFFFFFFFLL;
      goto LABEL_33;
    case 2:
      goto LABEL_43;
    case 3:
      v35 = *a7;
      *(_QWORD *)v21 = *a7;
      if ( !v35 )
        goto LABEL_34;
      v36 = *(unsigned __int16 *)(v35 + 68);
      v23 = v36 + *(unsigned __int16 *)(v35 + 70);
      if ( v23 < v36 )
        return 0xFFFFFFFFLL;
      v19 = (struct _OffsetPointer *)v21;
      goto LABEL_25;
    case 4:
LABEL_43:
      v37 = *a7;
      if ( *a7
        && *(unsigned __int16 *)(v37 + 68) + (unsigned int)*(unsigned __int16 *)(v37 + 70) >= *(unsigned __int16 *)(v37 + 68) )
      {
        *(_QWORD *)v21 = *(_QWORD *)(v37 + 131070);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)*a7);
        *a7 = 0;
      }
      else
      {
        *(_QWORD *)v21 = 0;
      }
      goto LABEL_34;
    case 5:
      v25 = *a7;
      v26 = PROXYPORT::HeapAllocOffset(this, 0x28u, v14);
      if ( !v26 )
        return 0xFFFFFFFFLL;
      *v27 = v26;
      v28 = &v26[-*(_QWORD *)(*(_QWORD *)this + 80LL)];
      *(_DWORD *)&v14[(_QWORD)v28] = *(_DWORD *)v25;
      v29 = (struct _OffsetPointer *)&v28[(_QWORD)v14 + 8];
      *(_QWORD *)v29 = *(_QWORD *)(v25 + 8);
      v30 = &v14[(_QWORD)v28];
      *(_QWORD *)&v14[(_QWORD)v28 + 16] = *(_QWORD *)(v25 + 16);
      v76 = (struct _OffsetPointer *)&v28[(_QWORD)v14 + 24];
      *(_QWORD *)v76 = *(_QWORD *)(v25 + 24);
      *(_DWORD *)&v14[(_QWORD)v28 + 32] = *(_DWORD *)(v25 + 32);
      if ( !PROXYPORT::ThunkStr(this, v29, v14) || !PROXYPORT::ThunkStr(this, (struct _OffsetPointer *)(v30 + 16), v14) )
        return 0xFFFFFFFFLL;
      v31 = PROXYPORT::ThunkStr(this, v76, v14);
      goto LABEL_32;
  }
  if ( a5 != 11 )
  {
    if ( a5 == 13 )
    {
      *(_QWORD *)v19 = a7;
      v23 = 4;
      goto LABEL_25;
    }
    return 0xFFFFFFFFLL;
  }
  *(_DWORD *)v21 = *(_DWORD *)a7;
  *((_DWORD *)v21 + 1) = *((_DWORD *)a7 + 1);
  v19 = (struct _OffsetPointer *)(v21 + 8);
  *((_QWORD *)v21 + 1) = a7[1];
  v23 = *((_DWORD *)a7 + 1);
LABEL_25:
  if ( !PROXYPORT::ThunkMemBlock(this, v19, v23, v14) )
    return 0xFFFFFFFFLL;
LABEL_34:
  Heap = 0;
  v76 = 0;
  if ( Size && a9 )
  {
    if ( ((v18 - 1) & 0xFFFFFFFD) != 0 )
    {
      if ( v18 == 11 )
      {
        v33 = PROXYPORT::HeapAllocOffset(this, Size, v14);
        *v34 = v33;
        if ( !v33 )
          return 0xFFFFFFFFLL;
      }
    }
    else
    {
      v40 = PROXYPORT::HeapAllocOffset(this, 8u, v14);
      *v42 = v40;
      if ( !v40 )
        return 0xFFFFFFFFLL;
      v43 = PROXYPORT::HeapAllocOffset(v41, 0x1FFFEu, v14);
      *((_QWORD *)v16 + 11) = v43;
      if ( !v43 )
        return 0xFFFFFFFFLL;
      Heap = (unsigned __int64)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20006u);
      v76 = (struct _OffsetPointer *)Heap;
      if ( !Heap )
        return 0xFFFFFFFFLL;
      if ( *v70 )
        v44 = &v14[*v70 - *(_QWORD *)(*(_QWORD *)this + 80LL)];
      else
        v44 = 0;
      *(_QWORD *)v44 = 0;
      *((_DWORD *)v16 + 18) = 8;
    }
  }
  v72 = -1;
  ObjectXferable = 0;
  v77 = 0;
  if ( a4 )
  {
    v45 = HANDLE_TO_INDEX(a4);
    v47 = 0;
    if ( v45 < gMaxGdiHandleCount
      && (v74 = 0, v75 = 0, Entry = GdiGetEntry(v45, &v74), v47 = 0, v46 = a4, Entry >= 0)
      && BYTE14(v74) == 1
      && WORD6(v74) == WORD1(a4)
      && (DWORD2(v74) & 0xFFFFFFFE) == gW32PID
      && v75 )
    {
      v49 = (_OWORD *)(gCookie ^ __ROR8__(v75, 64 - (gCookie & 0x3Fu)));
      v77 = v49;
      v47 = v49;
    }
    else
    {
      v49 = 0;
    }
    if ( v47 )
    {
      v50 = v49;
      v51 = v82;
      v52 = 2;
      do
      {
        *v51 = *v50;
        v51[1] = v50[1];
        v51[2] = v50[2];
        v51[3] = v50[3];
        v51[4] = v50[4];
        v51[5] = v50[5];
        v51[6] = v50[6];
        v51[7] = v50[7];
        v51 += 8;
        v50 += 8;
        --v52;
      }
      while ( v52 );
      *v51 = *v50;
      v51[1] = v50[1];
      v51[2] = v50[2];
      v51[3] = v50[3];
      v51[4] = v50[4];
      v51[5] = v50[5];
      v51[6] = v50[6];
      ObjectXferable = NtGdiMakeObjectXferable(v46, *(unsigned int *)(*(_QWORD *)this + 96LL), 128);
    }
  }
  if ( !g_bUMPDLegacyWindowParenting && GetActiveWindow() && (v18 == 5 || v18 == 8) )
    *v16 = 1;
  v53 = PROXYPORT::SendRequest(this, v14, v78, 4u, *v16 != 0);
  v71 = v53;
  if ( ObjectXferable )
  {
    NtGdiMakeObjectUnXferable(a4);
    if ( v77 )
    {
      v54 = HANDLE_TO_INDEX(a4);
      v55 = 0;
      v56 = 0;
      if ( v54 < gMaxGdiHandleCount )
      {
        v74 = 0;
        v75 = 0;
        v57 = GdiGetEntry(v54, &v74);
        v56 = 0;
        if ( v57 >= 0 && BYTE14(v74) == 1 && WORD6(v74) == WORD1(a4) && (DWORD2(v74) & 0xFFFFFFFE) == gW32PID && v75 )
        {
          v55 = (_OWORD *)(gCookie ^ __ROR8__(v75, 64 - (gCookie & 0x3Fu)));
          v56 = v55;
        }
      }
      if ( v56 )
      {
        v58 = v82;
        v59 = 2;
        do
        {
          *v55 = *v58;
          v55[1] = v58[1];
          v55[2] = v58[2];
          v55[3] = v58[3];
          v55[4] = v58[4];
          v55[5] = v58[5];
          v55[6] = v58[6];
          v55[7] = v58[7];
          v55 += 8;
          v58 += 8;
          --v59;
        }
        while ( v59 );
        *v55 = *v58;
        v55[1] = v58[1];
        v55[2] = v58[2];
        v55[3] = v58[3];
        v55[4] = v58[4];
        v55[5] = v58[5];
        v55[6] = v58[6];
      }
      v53 = v71;
    }
  }
  if ( v53 >= 0 )
  {
    v60 = *(_QWORD *)(*(_QWORD *)this + 80LL);
    v72 = *(_DWORD *)&v78[-v60];
    if ( v72 != -1 )
    {
      if ( ((a5 - 1) & 0xFFFFFFFD) != 0 )
      {
        if ( a5 == 11 )
        {
          if ( a6 && a7 )
          {
            if ( *v79 )
              v61 = &v14[*v79 - v60];
            else
              v61 = 0;
            *(_DWORD *)a7 = *(_DWORD *)v61;
            v62 = *((int *)v61 + 1);
            *((_DWORD *)a7 + 1) = v62;
            v63 = (const void *)PROXYPORT::ServerToClientOffsetPtr(this, *((_QWORD *)v61 + 1), v14, v62);
            memcpy_0((void *)a7[1], v63, v64);
          }
          if ( Size && a9 )
          {
            if ( *v70 )
              v65 = &v14[*v70 - *(_QWORD *)(*(_QWORD *)this + 80LL)];
            else
              v65 = 0;
            memcpy_0(a9, v65, Size);
          }
        }
      }
      else
      {
        if ( *v70 )
          v66 = &v14[*v70 - v60];
        else
          v66 = 0;
        v67 = *(_QWORD *)v66;
        *a9 = Heap & -(__int64)(*(_QWORD *)v66 != 0);
        if ( v67 )
        {
          v68 = *((_QWORD *)v16 + 11);
          if ( v68 )
            v69 = &v14[v68 - *(_QWORD *)(*(_QWORD *)this + 80LL)];
          else
            v69 = 0;
          memcpy_0((void *)Heap, v69, 0x1FFFEu);
          *(_QWORD *)(Heap + 131070) = v67;
        }
        else
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)Heap);
          Heap = 0;
        }
      }
    }
    if ( *v81 )
      GdiSetLastError((unsigned int)*v81);
  }
  if ( v72 == -1 )
  {
    if ( Heap )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)Heap);
  }
  return v72;
}

```

## disassembly

```asm
0x18003f05c  mov     rax, rsp
0x18003f05f  mov     [rax+10h], rbx
0x18003f063  mov     [rax+18h], rsi
0x18003f067  mov     [rax+20h], r9
0x18003f06b  mov     [rax+8], rcx
0x18003f06f  push    rdi
0x18003f070  push    r12
0x18003f072  push    r13
0x18003f074  push    r14
0x18003f076  push    r15
0x18003f078  sub     rsp, 200h
0x18003f07f  mov     r12, r9
0x18003f082  mov     r14, r8
0x18003f085  mov     r10, rdx
0x18003f088  mov     rdi, rcx
0x18003f08b  mov     rax, [rcx]
0x18003f08e  mov     r13d, 2
0x18003f094  xor     ebx, ebx
0x18003f096  test    [rax+6Ch], r13b
0x18003f09a  jnz     short loc_18003F09F
0x18003f09c  mov     [rax+58h], ebx
0x18003f09f  mov     edx, 60h ; '`'; unsigned int
0x18003f0a4  call    ?HeapAlloc@PROXYPORT@@QEAAPEAEK@Z; PROXYPORT::HeapAlloc(ulong)
0x18003f0a9  mov     rsi, rax
0x18003f0ac  mov     [rsp+228h+var_1A8], rax
0x18003f0b4  test    rax, rax
0x18003f0b7  jz      loc_18003F237
0x18003f0bd  mov     rcx, [rcx]
0x18003f0c0  mov     r15, rax
0x18003f0c3  sub     r15, [rcx+50h]
0x18003f0c7  jz      loc_18003F237
0x18003f0cd  mov     edx, 4; unsigned int
0x18003f0d2  mov     rcx, rdi; this
0x18003f0d5  call    ?HeapAlloc@PROXYPORT@@QEAAPEAEK@Z; PROXYPORT::HeapAlloc(ulong)
0x18003f0da  mov     [rsp+228h+var_1B8], rax
0x18003f0df  test    rax, rax
0x18003f0e2  jz      loc_18003F237
0x18003f0e8  mov     dword ptr [r15+4], 6Dh ; 'm'
0x18003f0f0  mov     [r15], bl
0x18003f0f3  mov     [r15+18h], r10
0x18003f0f7  call    cs:__imp_GetCurrentProcessId
0x18003f0fe  nop     dword ptr [rax+rax+00h]
0x18003f103  mov     [r15+20h], eax
0x18003f107  mov     [r15+24h], r14d
0x18003f10b  lea     rax, [r15+28h]
0x18003f10f  mov     [rsp+228h+var_1A0], rax
0x18003f117  mov     [rax], ebx
0x18003f119  mov     [r15+30h], r12
0x18003f11d  mov     r14d, [rsp+228h+arg_20]
0x18003f125  mov     [r15+38h], r14d
0x18003f129  mov     ecx, [rsp+228h+arg_28]
0x18003f130  mov     [r15+3Ch], ecx
0x18003f134  lea     rdx, [r15+40h]
0x18003f138  mov     [rsp+228h+var_1B0], rdx
0x18003f13d  mov     [rdx], rbx
0x18003f140  mov     eax, dword ptr [rsp+228h+Size]
0x18003f147  mov     [r15+48h], eax
0x18003f14b  lea     r11, [r15+50h]
0x18003f14f  mov     [rsp+228h+var_1F8], r11
0x18003f154  mov     [r11], rbx
0x18003f157  mov     [r15+58h], rbx
0x18003f15b  mov     r12, [rsp+228h+arg_30]
0x18003f163  test    ecx, ecx
0x18003f165  jz      loc_18003F328
0x18003f16b  test    r12, r12
0x18003f16e  jz      loc_18003F328
0x18003f174  cmp     r14d, 1
0x18003f178  jnz     short loc_18003F182
0x18003f17a  mov     r14d, 20h ; ' '
0x18003f180  jmp     short loc_18003F1B2
0x18003f182  mov     r11, rbx
0x18003f185  lea     eax, [r14-2]
0x18003f189  cmp     eax, 3
0x18003f18c  jbe     short loc_18003F1A7
0x18003f18e  mov     r14d, ebx
0x18003f191  lea     rdx, [r15+40h]
0x18003f195  cmp     [rsp+228h+arg_20], 0Bh
0x18003f19d  jnz     short loc_18003F1AD
0x18003f19f  mov     r14d, 10h
0x18003f1a5  jmp     short loc_18003F1AD
0x18003f1a7  mov     r14d, 8
0x18003f1ad  test    r14d, r14d
0x18003f1b0  jz      short loc_18003F1DD
0x18003f1b2  mov     r8, rsi; unsigned __int8 *
0x18003f1b5  mov     edx, r14d; unsigned int
0x18003f1b8  mov     rcx, rdi; this
0x18003f1bb  call    ?HeapAllocOffset@PROXYPORT@@QEAAPEAEKPEAE@Z; PROXYPORT::HeapAllocOffset(ulong,uchar *)
0x18003f1c0  mov     r11, rax
0x18003f1c3  lea     rdx, [r15+40h]; struct _OffsetPointer *
0x18003f1c7  mov     [rdx], rax
0x18003f1ca  test    rax, rax
0x18003f1cd  jz      short loc_18003F237
0x18003f1cf  mov     [r15+3Ch], r14d
0x18003f1d3  mov     rax, [rdi]
0x18003f1d6  sub     r11, [rax+50h]
0x18003f1da  add     r11, rsi
0x18003f1dd  mov     r14d, [rsp+228h+arg_20]
0x18003f1e5  mov     ecx, r14d
0x18003f1e8  sub     ecx, 1
0x18003f1eb  jz      loc_18003F401
0x18003f1f1  sub     ecx, 1
0x18003f1f4  jz      loc_18003F3B0
0x18003f1fa  sub     ecx, 1
0x18003f1fd  jz      loc_18003F387
0x18003f203  sub     ecx, 1
0x18003f206  jz      loc_18003F3B0
0x18003f20c  sub     ecx, 1
0x18003f20f  jz      short loc_18003F27B
0x18003f211  sub     ecx, 6
0x18003f214  jz      short loc_18003F258
0x18003f216  cmp     ecx, r13d
0x18003f219  jnz     short loc_18003F237
0x18003f21b  mov     [rdx], r12
0x18003f21e  mov     r8d, 4; unsigned int
0x18003f224  mov     r9, rsi; unsigned __int8 *
0x18003f227  mov     rcx, rdi; this
0x18003f22a  call    ?ThunkMemBlock@PROXYPORT@@QEAAHPEAU_OffsetPointer@@KPEAE@Z; PROXYPORT::ThunkMemBlock(_OffsetPointer *,ulong,uchar *)
0x18003f22f  test    eax, eax
0x18003f231  jnz     loc_18003F323
0x18003f237  or      eax, 0FFFFFFFFh
0x18003f23a  lea     r11, [rsp+228h+var_28]
0x18003f242  mov     rbx, [r11+38h]
0x18003f246  mov     rsi, [r11+40h]
0x18003f24a  mov     rsp, r11
0x18003f24d  pop     r15
0x18003f24f  pop     r14
0x18003f251  pop     r13
0x18003f253  pop     r12
0x18003f255  pop     rdi
0x18003f256  retn
0x18003f258  mov     eax, [r12]
0x18003f25c  mov     [r11], eax
0x18003f25f  mov     eax, [r12+4]
0x18003f264  mov     [r11+4], eax
0x18003f268  lea     rdx, [r11+8]
0x18003f26c  mov     rax, [r12+8]
0x18003f271  mov     [rdx], rax
0x18003f274  mov     r8d, [r12+4]
0x18003f279  jmp     short loc_18003F224
0x18003f27b  mov     r14, [r12]
0x18003f27f  mov     r8, rsi; unsigned __int8 *
0x18003f282  mov     edx, 28h ; '('; unsigned int
0x18003f287  mov     rcx, rdi; this
0x18003f28a  call    ?HeapAllocOffset@PROXYPORT@@QEAAPEAEKPEAE@Z; PROXYPORT::HeapAllocOffset(ulong,uchar *)
0x18003f28f  test    rax, rax
0x18003f292  jz      short loc_18003F237
0x18003f294  mov     [r11], rax
0x18003f297  mov     rcx, [rdi]
0x18003f29a  sub     rax, [rcx+50h]
0x18003f29e  mov     ecx, [r14]
0x18003f2a1  mov     [rax+rsi], ecx
0x18003f2a4  lea     rdx, [rax+8]
0x18003f2a8  add     rdx, rsi; struct _OffsetPointer *
0x18003f2ab  mov     rcx, [r14+8]
0x18003f2af  mov     [rdx], rcx
0x18003f2b2  lea     r13, [rax+rsi]
0x18003f2b6  mov     rcx, [r14+10h]
0x18003f2ba  mov     [r13+10h], rcx
0x18003f2be  lea     r8, [rax+18h]
0x18003f2c2  add     r8, rsi
0x18003f2c5  mov     [rsp+228h+var_1C8], r8
0x18003f2ca  mov     rcx, [r14+18h]
0x18003f2ce  mov     [r8], rcx
0x18003f2d1  mov     ecx, [r14+20h]
0x18003f2d5  mov     [rax+rsi+20h], ecx
0x18003f2d9  mov     r8, rsi; unsigned __int8 *
0x18003f2dc  mov     rcx, rdi; this
0x18003f2df  call    ?ThunkStr@PROXYPORT@@QEAAHPEAU_OffsetPointer@@PEAE@Z; PROXYPORT::ThunkStr(_OffsetPointer *,uchar *)
0x18003f2e4  test    eax, eax
0x18003f2e6  jz      loc_18003F237
0x18003f2ec  mov     r8, rsi; unsigned __int8 *
0x18003f2ef  lea     rdx, [r13+10h]; struct _OffsetPointer *
0x18003f2f3  mov     rcx, rdi; this
0x18003f2f6  call    ?ThunkStr@PROXYPORT@@QEAAHPEAU_OffsetPointer@@PEAE@Z; PROXYPORT::ThunkStr(_OffsetPointer *,uchar *)
0x18003f2fb  test    eax, eax
0x18003f2fd  jz      loc_18003F237
0x18003f303  mov     r8, rsi; unsigned __int8 *
0x18003f306  mov     rdx, [rsp+228h+var_1C8]; struct _OffsetPointer *
0x18003f30b  mov     rcx, rdi; this
0x18003f30e  call    ?ThunkStr@PROXYPORT@@QEAAHPEAU_OffsetPointer@@PEAE@Z; PROXYPORT::ThunkStr(_OffsetPointer *,uchar *)
0x18003f313  test    eax, eax
0x18003f315  jz      loc_18003F237
0x18003f31b  mov     r14d, [rsp+228h+arg_20]
0x18003f323  mov     r11, [rsp+228h+var_1F8]
0x18003f328  mov     r13, rbx
0x18003f32b  mov     [rsp+228h+var_1C8], rbx
0x18003f330  mov     r9d, dword ptr [rsp+228h+Size]
0x18003f338  test    r9d, r9d
0x18003f33b  jz      loc_18003F50B
0x18003f341  cmp     [rsp+228h+arg_40], rbx
0x18003f349  jz      loc_18003F50B
0x18003f34f  lea     eax, [r14-1]
0x18003f353  test    eax, 0FFFFFFFDh
0x18003f358  jz      loc_18003F47C
0x18003f35e  cmp     r14d, 0Bh
0x18003f362  jnz     loc_18003F50B
0x18003f368  mov     r8, rsi; unsigned __int8 *
0x18003f36b  mov     edx, r9d; unsigned int
0x18003f36e  mov     rcx, rdi; this
0x18003f371  call    ?HeapAllocOffset@PROXYPORT@@QEAAPEAEKPEAE@Z; PROXYPORT::HeapAllocOffset(ulong,uchar *)
0x18003f376  mov     [r11], rax
0x18003f379  test    rax, rax
0x18003f37c  jz      loc_18003F237
0x18003f382  jmp     loc_18003F50B
0x18003f387  mov     rax, [r12]
0x18003f38b  mov     [r11], rax
0x18003f38e  test    rax, rax
0x18003f391  jz      short loc_18003F323
0x18003f393  movzx   ecx, word ptr [rax+44h]
0x18003f397  movzx   r8d, word ptr [rax+46h]
0x18003f39c  add     r8d, ecx
0x18003f39f  cmp     r8d, ecx
0x18003f3a2  jb      loc_18003F237
0x18003f3a8  mov     rdx, r11
0x18003f3ab  jmp     loc_18003F224
0x18003f3b0  mov     rdx, [r12]
0x18003f3b4  test    rdx, rdx
0x18003f3b7  jz      short loc_18003F3F9
0x18003f3b9  movzx   ecx, word ptr [rdx+44h]
0x18003f3bd  movzx   eax, word ptr [rdx+46h]
0x18003f3c1  add     eax, ecx
0x18003f3c3  cmp     eax, ecx
0x18003f3c5  jb      short loc_18003F3F9
0x18003f3c7  mov     rax, [rdx+1FFFEh]
0x18003f3ce  mov     [r11], rax
0x18003f3d1  mov     rcx, gs:60h
0x18003f3da  mov     r8, [r12]; P
0x18003f3de  xor     edx, edx; Flags
0x18003f3e0  mov     rcx, [rcx+30h]; HeapHandle
0x18003f3e4  call    cs:__imp_RtlFreeHeap
0x18003f3eb  nop     dword ptr [rax+rax+00h]
0x18003f3f0  mov     [r12], rbx
0x18003f3f4  jmp     loc_18003F323
0x18003f3f9  mov     [r11], rbx
0x18003f3fc  jmp     loc_18003F323
0x18003f401  mov     [r11], rbx
0x18003f404  lea     rdx, [r11+8]; struct _OffsetPointer *
0x18003f408  mov     rax, [r12+8]
0x18003f40d  mov     [rdx], rax
0x18003f410  lea     r14, [r11+10h]
0x18003f414  mov     rax, [r12+10h]
0x18003f419  mov     [r14], rax
0x18003f41c  mov     eax, [r12+18h]
0x18003f421  mov     [r11+18h], eax
0x18003f425  mov     rax, [r12+10h]
0x18003f42a  test    rax, rax
0x18003f42d  jz      loc_18003F31B
0x18003f433  movzx   ecx, word ptr [rax+44h]
0x18003f437  movzx   eax, word ptr [rax+46h]
0x18003f43b  add     eax, ecx
0x18003f43d  cmp     eax, ecx
0x18003f43f  jb      loc_18003F237
0x18003f445  mov     r8, rsi; unsigned __int8 *
0x18003f448  mov     rcx, rdi; this
0x18003f44b  call    ?ThunkStr@PROXYPORT@@QEAAHPEAU_OffsetPointer@@PEAE@Z; PROXYPORT::ThunkStr(_OffsetPointer *,uchar *)
0x18003f450  test    eax, eax
0x18003f452  jz      loc_18003F237
0x18003f458  mov     rax, [r12+10h]
0x18003f45d  movzx   r8d, word ptr [rax+46h]
0x18003f462  movzx   eax, word ptr [rax+44h]
0x18003f466  add     r8d, eax; unsigned int
0x18003f469  mov     r9, rsi; unsigned __int8 *
0x18003f46c  mov     rdx, r14; struct _OffsetPointer *
0x18003f46f  mov     rcx, rdi; this
0x18003f472  call    ?ThunkMemBlock@PROXYPORT@@QEAAHPEAU_OffsetPointer@@KPEAE@Z; PROXYPORT::ThunkMemBlock(_OffsetPointer *,ulong,uchar *)
0x18003f477  jmp     loc_18003F313
0x18003f47c  mov     r8, rsi; unsigned __int8 *
0x18003f47f  mov     edx, 8; unsigned int
0x18003f484  mov     rcx, rdi; this
0x18003f487  call    ?HeapAllocOffset@PROXYPORT@@QEAAPEAEKPEAE@Z; PROXYPORT::HeapAllocOffset(ulong,uchar *)
0x18003f48c  mov     [r11], rax
0x18003f48f  test    rax, rax
0x18003f492  jz      loc_18003F237
0x18003f498  mov     r8, rsi; unsigned __int8 *
0x18003f49b  mov     edx, 1FFFEh; unsigned int
0x18003f4a0  call    ?HeapAllocOffset@PROXYPORT@@QEAAPEAEKPEAE@Z; PROXYPORT::HeapAllocOffset(ulong,uchar *)
0x18003f4a5  mov     [r15+58h], rax
0x18003f4a9  test    rax, rax
0x18003f4ac  jz      loc_18003F237
0x18003f4b2  mov     rcx, gs:60h
0x18003f4bb  xor     edx, edx; Flags
0x18003f4bd  mov     r8d, 20006h; Size
0x18003f4c3  mov     rcx, [rcx+30h]; HeapHandle
0x18003f4c7  call    cs:__imp_RtlAllocateHeap
0x18003f4ce  nop     dword ptr [rax+rax+00h]
0x18003f4d3  mov     r13, rax
0x18003f4d6  mov     [rsp+228h+var_1C8], rax
0x18003f4db  test    rax, rax
0x18003f4de  jz      loc_18003F237
0x18003f4e4  mov     rax, [rsp+228h+var_1F8]
0x18003f4e9  mov     rax, [rax]
0x18003f4ec  test    rax, rax
0x18003f4ef  jz      short loc_18003F4FD
0x18003f4f1  mov     rcx, [rdi]
0x18003f4f4  sub     rax, [rcx+50h]
0x18003f4f8  add     rax, rsi
0x18003f4fb  jmp     short loc_18003F500
0x18003f4fd  mov     rax, rbx
0x18003f500  mov     [rax], rbx
0x18003f503  mov     dword ptr [r15+48h], 8
  ... truncated ...
```
