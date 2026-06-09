# PROXYPORT::DocumentEvent(unsigned __int64,void *,HDC__ *,int,ulong,void *,ulong,void *)

- ea: `0x180045248`
- end: `0x180045c01`
- name: `?DocumentEvent@PROXYPORT@@QEAAH_KPEAXPEAUHDC__@@HK1K1@Z`
- size: `2489`
- prototype: `__int64 __usercall@<rax>(PROXYPORT *__hidden this@<rcx>, unsigned __int64@<rdx>, void *@<r8>, HDC@<r9>, int, unsigned int, void *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180044d48`

## callees

- `0x180045248`
- `0x180046c44`
- `0x180046c84`
- `0x180046cec`
- `0x180046d10`
- `0x180046d4c`
- `0x1800676e4`
- `0x1800710c4`
- `0x1800a3514`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800452e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800452e3`
- `GDI32!GdiGetEntry` at `0x180045736`
- `GDI32!GdiGetEntry` at `0x18004590b`
- `GDI32!GdiGetEntry` at `0x180045736`
- `GDI32!GdiGetEntry` at `0x18004590b`
- `GDI32!gW32PID` at `0x180045776`
- `GDI32!gW32PID` at `0x180045948`
- `GDI32!gCookie` at `0x180045788`
- `GDI32!gCookie` at `0x18004595a`
- `GDI32!gMaxGdiHandleCount` at `0x180045711`
- `GDI32!gMaxGdiHandleCount` at `0x1800458e6`
- `GDI32!GdiSetLastError` at `0x180045bce`
- `GDI32!GdiSetLastError` at `0x180045bce`
- `ntdll!RtlFreeHeap` at `0x1800455c9`
- `ntdll!RtlFreeHeap` at `0x180045bb7`
- `ntdll!RtlFreeHeap` at `0x180045bf4`
- `ntdll!RtlFreeHeap` at `0x1800455c9`
- `ntdll!RtlFreeHeap` at `0x180045bb7`
- `ntdll!RtlFreeHeap` at `0x180045bf4`
- `ntdll!RtlAllocateHeap` at `0x1800456a6`
- `ntdll!RtlAllocateHeap` at `0x1800456a6`
- `USER32!GetActiveWindow` at `0x18004586e`
- `USER32!GetActiveWindow` at `0x18004586e`
- `win32u!NtGdiMakeObjectUnXferable` at `0x1800458c2`
- `win32u!NtGdiMakeObjectUnXferable` at `0x1800458c2`
- `win32u!NtGdiMakeObjectXferable` at `0x18004585c`
- `win32u!NtGdiMakeObjectXferable` at `0x18004585c`

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
0x180045248  mov     rax, rsp
0x18004524b  mov     [rax+10h], rbx
0x18004524f  mov     [rax+18h], rsi
0x180045253  mov     [rax+20h], r9
0x180045257  mov     [rax+8], rcx
0x18004525b  push    rdi
0x18004525c  push    r12
0x18004525e  push    r13
0x180045260  push    r14
0x180045262  push    r15
0x180045264  sub     rsp, 200h
0x18004526b  mov     r12, r9
0x18004526e  mov     r14, r8
0x180045271  mov     r10, rdx
0x180045274  mov     rdi, rcx
0x180045277  mov     rax, [rcx]
0x18004527a  mov     r13d, 2
0x180045280  xor     ebx, ebx
0x180045282  test    [rax+6Ch], r13b
0x180045286  jnz     short loc_18004528B
0x180045288  mov     [rax+58h], ebx
0x18004528b  mov     edx, 60h ; '`'; unsigned int
0x180045290  call    ?HeapAlloc@PROXYPORT@@QEAAPEAEK@Z; PROXYPORT::HeapAlloc(ulong)
0x180045295  mov     rsi, rax
0x180045298  mov     [rsp+228h+var_1A8], rax
0x1800452a0  test    rax, rax
0x1800452a3  jz      loc_18004541D
0x1800452a9  mov     rcx, [rcx]
0x1800452ac  mov     r15, rax
0x1800452af  sub     r15, [rcx+50h]
0x1800452b3  jz      loc_18004541D
0x1800452b9  mov     edx, 4; unsigned int
0x1800452be  mov     rcx, rdi; this
0x1800452c1  call    ?HeapAlloc@PROXYPORT@@QEAAPEAEK@Z; PROXYPORT::HeapAlloc(ulong)
0x1800452c6  mov     [rsp+228h+var_1B8], rax
0x1800452cb  test    rax, rax
0x1800452ce  jz      loc_18004541D
0x1800452d4  mov     dword ptr [r15+4], 6Dh ; 'm'
0x1800452dc  mov     [r15], bl
0x1800452df  mov     [r15+18h], r10
0x1800452e3  call    cs:__imp_GetCurrentProcessId
0x1800452e9  mov     [r15+20h], eax
0x1800452ed  mov     [r15+24h], r14d
0x1800452f1  lea     rax, [r15+28h]
0x1800452f5  mov     [rsp+228h+var_1A0], rax
0x1800452fd  mov     [rax], ebx
0x1800452ff  mov     [r15+30h], r12
0x180045303  mov     r14d, [rsp+228h+arg_20]
0x18004530b  mov     [r15+38h], r14d
0x18004530f  mov     ecx, [rsp+228h+arg_28]
0x180045316  mov     [r15+3Ch], ecx
0x18004531a  lea     rdx, [r15+40h]
0x18004531e  mov     [rsp+228h+var_1B0], rdx
0x180045323  mov     [rdx], rbx
0x180045326  mov     eax, dword ptr [rsp+228h+Size]
0x18004532d  mov     [r15+48h], eax
0x180045331  lea     r11, [r15+50h]
0x180045335  mov     [rsp+228h+var_1F8], r11
0x18004533a  mov     [r11], rbx
0x18004533d  mov     [r15+58h], rbx
0x180045341  mov     r12, [rsp+228h+arg_30]
0x180045349  test    ecx, ecx
0x18004534b  jz      loc_18004550D
0x180045351  test    r12, r12
0x180045354  jz      loc_18004550D
0x18004535a  cmp     r14d, 1
0x18004535e  jnz     short loc_180045368
0x180045360  mov     r14d, 20h ; ' '
0x180045366  jmp     short loc_180045398
0x180045368  mov     r11, rbx
0x18004536b  lea     eax, [r14-2]
0x18004536f  cmp     eax, 3
0x180045372  jbe     short loc_18004538D
0x180045374  mov     r14d, ebx
0x180045377  lea     rdx, [r15+40h]
0x18004537b  cmp     [rsp+228h+arg_20], 0Bh
0x180045383  jnz     short loc_180045393
0x180045385  mov     r14d, 10h
0x18004538b  jmp     short loc_180045393
0x18004538d  mov     r14d, 8
0x180045393  test    r14d, r14d
0x180045396  jz      short loc_1800453C3
0x180045398  mov     r8, rsi; unsigned __int8 *
0x18004539b  mov     edx, r14d; unsigned int
0x18004539e  mov     rcx, rdi; this
0x1800453a1  call    ?HeapAllocOffset@PROXYPORT@@QEAAPEAEKPEAE@Z; PROXYPORT::HeapAllocOffset(ulong,uchar *)
0x1800453a6  mov     r11, rax
0x1800453a9  lea     rdx, [r15+40h]; struct _OffsetPointer *
0x1800453ad  mov     [rdx], rax
0x1800453b0  test    rax, rax
0x1800453b3  jz      short loc_18004541D
0x1800453b5  mov     [r15+3Ch], r14d
0x1800453b9  mov     rax, [rdi]
0x1800453bc  sub     r11, [rax+50h]
0x1800453c0  add     r11, rsi
0x1800453c3  mov     r14d, [rsp+228h+arg_20]
0x1800453cb  mov     ecx, r14d
0x1800453ce  sub     ecx, 1
0x1800453d1  jz      loc_1800455E0
0x1800453d7  sub     ecx, 1
0x1800453da  jz      loc_180045595
0x1800453e0  sub     ecx, 1
0x1800453e3  jz      loc_18004556C
0x1800453e9  sub     ecx, 1
0x1800453ec  jz      loc_180045595
0x1800453f2  sub     ecx, 1
0x1800453f5  jz      short loc_180045460
0x1800453f7  sub     ecx, 6
0x1800453fa  jz      short loc_18004543D
0x1800453fc  cmp     ecx, r13d
0x1800453ff  jnz     short loc_18004541D
0x180045401  mov     [rdx], r12
0x180045404  mov     r8d, 4; unsigned int
0x18004540a  mov     r9, rsi; unsigned __int8 *
0x18004540d  mov     rcx, rdi; this
0x180045410  call    ?ThunkMemBlock@PROXYPORT@@QEAAHPEAU_OffsetPointer@@KPEAE@Z; PROXYPORT::ThunkMemBlock(_OffsetPointer *,ulong,uchar *)
0x180045415  test    eax, eax
0x180045417  jnz     loc_180045508
0x18004541d  or      eax, 0FFFFFFFFh
0x180045420  lea     r11, [rsp+228h+var_28]
0x180045428  mov     rbx, [r11+38h]
0x18004542c  mov     rsi, [r11+40h]
0x180045430  mov     rsp, r11
0x180045433  pop     r15
0x180045435  pop     r14
0x180045437  pop     r13
0x180045439  pop     r12
0x18004543b  pop     rdi
0x18004543c  retn
0x18004543d  mov     eax, [r12]
0x180045441  mov     [r11], eax
0x180045444  mov     eax, [r12+4]
0x180045449  mov     [r11+4], eax
0x18004544d  lea     rdx, [r11+8]
0x180045451  mov     rax, [r12+8]
0x180045456  mov     [rdx], rax
0x180045459  mov     r8d, [r12+4]
0x18004545e  jmp     short loc_18004540A
0x180045460  mov     r14, [r12]
0x180045464  mov     r8, rsi; unsigned __int8 *
0x180045467  mov     edx, 28h ; '('; unsigned int
0x18004546c  mov     rcx, rdi; this
0x18004546f  call    ?HeapAllocOffset@PROXYPORT@@QEAAPEAEKPEAE@Z; PROXYPORT::HeapAllocOffset(ulong,uchar *)
0x180045474  test    rax, rax
0x180045477  jz      short loc_18004541D
0x180045479  mov     [r11], rax
0x18004547c  mov     rcx, [rdi]
0x18004547f  sub     rax, [rcx+50h]
0x180045483  mov     ecx, [r14]
0x180045486  mov     [rax+rsi], ecx
0x180045489  lea     rdx, [rax+8]
0x18004548d  add     rdx, rsi; struct _OffsetPointer *
0x180045490  mov     rcx, [r14+8]
0x180045494  mov     [rdx], rcx
0x180045497  lea     r13, [rax+rsi]
0x18004549b  mov     rcx, [r14+10h]
0x18004549f  mov     [r13+10h], rcx
0x1800454a3  lea     r8, [rax+18h]
0x1800454a7  add     r8, rsi
0x1800454aa  mov     [rsp+228h+var_1C8], r8
0x1800454af  mov     rcx, [r14+18h]
0x1800454b3  mov     [r8], rcx
0x1800454b6  mov     ecx, [r14+20h]
0x1800454ba  mov     [rax+rsi+20h], ecx
0x1800454be  mov     r8, rsi; unsigned __int8 *
0x1800454c1  mov     rcx, rdi; this
0x1800454c4  call    ?ThunkStr@PROXYPORT@@QEAAHPEAU_OffsetPointer@@PEAE@Z; PROXYPORT::ThunkStr(_OffsetPointer *,uchar *)
0x1800454c9  test    eax, eax
0x1800454cb  jz      loc_18004541D
0x1800454d1  mov     r8, rsi; unsigned __int8 *
0x1800454d4  lea     rdx, [r13+10h]; struct _OffsetPointer *
0x1800454d8  mov     rcx, rdi; this
0x1800454db  call    ?ThunkStr@PROXYPORT@@QEAAHPEAU_OffsetPointer@@PEAE@Z; PROXYPORT::ThunkStr(_OffsetPointer *,uchar *)
0x1800454e0  test    eax, eax
0x1800454e2  jz      loc_18004541D
0x1800454e8  mov     r8, rsi; unsigned __int8 *
0x1800454eb  mov     rdx, [rsp+228h+var_1C8]; struct _OffsetPointer *
0x1800454f0  mov     rcx, rdi; this
0x1800454f3  call    ?ThunkStr@PROXYPORT@@QEAAHPEAU_OffsetPointer@@PEAE@Z; PROXYPORT::ThunkStr(_OffsetPointer *,uchar *)
0x1800454f8  test    eax, eax
0x1800454fa  jz      loc_18004541D
0x180045500  mov     r14d, [rsp+228h+arg_20]
0x180045508  mov     r11, [rsp+228h+var_1F8]
0x18004550d  mov     r13, rbx
0x180045510  mov     [rsp+228h+var_1C8], rbx
0x180045515  mov     r9d, dword ptr [rsp+228h+Size]
0x18004551d  test    r9d, r9d
0x180045520  jz      loc_1800456E4
0x180045526  cmp     [rsp+228h+arg_40], rbx
0x18004552e  jz      loc_1800456E4
0x180045534  lea     eax, [r14-1]
0x180045538  test    eax, 0FFFFFFFDh
0x18004553d  jz      loc_18004565B
0x180045543  cmp     r14d, 0Bh
0x180045547  jnz     loc_1800456E4
0x18004554d  mov     r8, rsi; unsigned __int8 *
0x180045550  mov     edx, r9d; unsigned int
0x180045553  mov     rcx, rdi; this
0x180045556  call    ?HeapAllocOffset@PROXYPORT@@QEAAPEAEKPEAE@Z; PROXYPORT::HeapAllocOffset(ulong,uchar *)
0x18004555b  mov     [r11], rax
0x18004555e  test    rax, rax
0x180045561  jz      loc_18004541D
0x180045567  jmp     loc_1800456E4
0x18004556c  mov     rax, [r12]
0x180045570  mov     [r11], rax
0x180045573  test    rax, rax
0x180045576  jz      short loc_180045508
0x180045578  movzx   ecx, word ptr [rax+44h]
0x18004557c  movzx   r8d, word ptr [rax+46h]
0x180045581  add     r8d, ecx
0x180045584  cmp     r8d, ecx
0x180045587  jb      loc_18004541D
0x18004558d  mov     rdx, r11
0x180045590  jmp     loc_18004540A
0x180045595  mov     rdx, [r12]
0x180045599  test    rdx, rdx
0x18004559c  jz      short loc_1800455D8
0x18004559e  movzx   ecx, word ptr [rdx+44h]
0x1800455a2  movzx   eax, word ptr [rdx+46h]
0x1800455a6  add     eax, ecx
0x1800455a8  cmp     eax, ecx
0x1800455aa  jb      short loc_1800455D8
0x1800455ac  mov     rax, [rdx+1FFFEh]
0x1800455b3  mov     [r11], rax
0x1800455b6  mov     rcx, gs:60h
0x1800455bf  mov     r8, [r12]; P
0x1800455c3  xor     edx, edx; Flags
0x1800455c5  mov     rcx, [rcx+30h]; HeapHandle
0x1800455c9  call    cs:__imp_RtlFreeHeap
0x1800455cf  mov     [r12], rbx
0x1800455d3  jmp     loc_180045508
0x1800455d8  mov     [r11], rbx
0x1800455db  jmp     loc_180045508
0x1800455e0  mov     [r11], rbx
0x1800455e3  lea     rdx, [r11+8]; struct _OffsetPointer *
0x1800455e7  mov     rax, [r12+8]
0x1800455ec  mov     [rdx], rax
0x1800455ef  lea     r14, [r11+10h]
0x1800455f3  mov     rax, [r12+10h]
0x1800455f8  mov     [r14], rax
0x1800455fb  mov     eax, [r12+18h]
0x180045600  mov     [r11+18h], eax
0x180045604  mov     rax, [r12+10h]
0x180045609  test    rax, rax
0x18004560c  jz      loc_180045500
0x180045612  movzx   ecx, word ptr [rax+44h]
0x180045616  movzx   eax, word ptr [rax+46h]
0x18004561a  add     eax, ecx
0x18004561c  cmp     eax, ecx
0x18004561e  jb      loc_18004541D
0x180045624  mov     r8, rsi; unsigned __int8 *
0x180045627  mov     rcx, rdi; this
0x18004562a  call    ?ThunkStr@PROXYPORT@@QEAAHPEAU_OffsetPointer@@PEAE@Z; PROXYPORT::ThunkStr(_OffsetPointer *,uchar *)
0x18004562f  test    eax, eax
0x180045631  jz      loc_18004541D
0x180045637  mov     rax, [r12+10h]
0x18004563c  movzx   r8d, word ptr [rax+46h]
0x180045641  movzx   eax, word ptr [rax+44h]
0x180045645  add     r8d, eax; unsigned int
0x180045648  mov     r9, rsi; unsigned __int8 *
0x18004564b  mov     rdx, r14; struct _OffsetPointer *
0x18004564e  mov     rcx, rdi; this
0x180045651  call    ?ThunkMemBlock@PROXYPORT@@QEAAHPEAU_OffsetPointer@@KPEAE@Z; PROXYPORT::ThunkMemBlock(_OffsetPointer *,ulong,uchar *)
0x180045656  jmp     loc_1800454F8
0x18004565b  mov     r8, rsi; unsigned __int8 *
0x18004565e  mov     edx, 8; unsigned int
0x180045663  mov     rcx, rdi; this
0x180045666  call    ?HeapAllocOffset@PROXYPORT@@QEAAPEAEKPEAE@Z; PROXYPORT::HeapAllocOffset(ulong,uchar *)
0x18004566b  mov     [r11], rax
0x18004566e  test    rax, rax
0x180045671  jz      loc_18004541D
0x180045677  mov     r8, rsi; unsigned __int8 *
0x18004567a  mov     edx, 1FFFEh; unsigned int
0x18004567f  call    ?HeapAllocOffset@PROXYPORT@@QEAAPEAEKPEAE@Z; PROXYPORT::HeapAllocOffset(ulong,uchar *)
0x180045684  mov     [r15+58h], rax
0x180045688  test    rax, rax
0x18004568b  jz      loc_18004541D
0x180045691  mov     rcx, gs:60h
0x18004569a  xor     edx, edx; Flags
0x18004569c  mov     r8d, 20006h; Size
0x1800456a2  mov     rcx, [rcx+30h]; HeapHandle
0x1800456a6  call    cs:__imp_RtlAllocateHeap
0x1800456ac  mov     r13, rax
0x1800456af  mov     [rsp+228h+var_1C8], rax
0x1800456b4  test    rax, rax
0x1800456b7  jz      loc_18004541D
0x1800456bd  mov     rax, [rsp+228h+var_1F8]
0x1800456c2  mov     rax, [rax]
0x1800456c5  test    rax, rax
0x1800456c8  jz      short loc_1800456D6
0x1800456ca  mov     rcx, [rdi]
0x1800456cd  sub     rax, [rcx+50h]
0x1800456d1  add     rax, rsi
0x1800456d4  jmp     short loc_1800456D9
0x1800456d6  mov     rax, rbx
0x1800456d9  mov     [rax], rbx
0x1800456dc  mov     dword ptr [r15+48h], 8
0x1800456e4  mov     [rsp+228h+var_1EC], 0FFFFFFFFh
0x1800456ec  mov     [rsp+228h+var_1E8], ebx
0x1800456f0  mov     [rsp+228h+var_1C0], rbx
  ... truncated ...
```
