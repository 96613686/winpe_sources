# bDoFontSubset

- ea: `0x1800802e0`
- end: `0x1800805d6`
- name: `bDoFontSubset`
- size: `758`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180094054`

## callees

- `0x180039ae4`
- `0x18006b00c`
- `0x18006caf0`
- `0x18007ac50`
- `0x1800802e0`
- `0x1800805dc`
- `0x1800a5010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008037c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180080450`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008037c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180080450`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080568`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080592`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008059b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080568`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180080592`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18008059b`
- `ntdll!RtlEnterCriticalSection` at `0x180080327`
- `ntdll!RtlEnterCriticalSection` at `0x180080327`
- `ntdll!RtlLeaveCriticalSection` at `0x180080342`
- `ntdll!RtlLeaveCriticalSection` at `0x180080342`
- `ntdll!RtlDecodePointer` at `0x1800804ac`
- `ntdll!RtlDecodePointer` at `0x1800804ac`
- `win32u!NtGdiGetUFIPathname` at `0x1800803ff`
- `win32u!NtGdiGetUFIPathname` at `0x18008048e`
- `win32u!NtGdiGetUFIPathname` at `0x1800803ff`
- `win32u!NtGdiGetUFIPathname` at `0x18008048e`

## pseudocode

```c
__int64 __fastcall bDoFontSubset(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int16 v4; // si
  int inited; // ebx
  unsigned int v7; // esi
  unsigned int v8; // r13d
  HLOCAL v9; // rax
  void *v10; // r14
  unsigned int v11; // r12d
  int v12; // eax
  void *v13; // r15
  unsigned int v14; // eax
  void *v15; // rbx
  HLOCAL v16; // rax
  PVOID v17; // rax
  __int16 v18; // cx
  int v20; // [rsp+28h] [rbp-E8h]
  SIZE_T *p_uBytes; // [rsp+30h] [rbp-E0h]
  HLOCAL v22; // [rsp+38h] [rbp-D8h]
  int *v23; // [rsp+40h] [rbp-D0h]
  int *v24; // [rsp+48h] [rbp-C8h]
  SIZE_T uBytes; // [rsp+90h] [rbp-80h] BYREF
  int v26; // [rsp+98h] [rbp-78h] BYREF
  int v27; // [rsp+9Ch] [rbp-74h] BYREF
  unsigned int v28; // [rsp+A0h] [rbp-70h]
  int v29; // [rsp+A4h] [rbp-6Ch] BYREF
  int v30; // [rsp+A8h] [rbp-68h] BYREF
  __int64 v31; // [rsp+B0h] [rbp-60h]
  __int64 v32; // [rsp+B8h] [rbp-58h]
  __int64 v33; // [rsp+C0h] [rbp-50h]
  unsigned __int16 (__fastcall *v34)(void *, _QWORD, __int64, __int64, __int64, int, SIZE_T *, HLOCAL, int *, int *, __int16, void *, _WORD, __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 (__fastcall *)(), _QWORD); // [rsp+C8h] [rbp-48h]
  void *FileHandle[2]; // [rsp+D0h] [rbp-40h] BYREF
  __int128 v36; // [rsp+E0h] [rbp-30h]
  WCHAR SourceString[784]; // [rsp+F0h] [rbp-20h] BYREF

  v4 = *(_WORD *)(a1 + 16);
  v31 = a4;
  v32 = a3;
  v33 = a2;
  RtlEnterCriticalSection(&semLocal);
  inited = bInitSubsetterFunctionPointer(&gfpCreateFontPackage);
  RtlLeaveCriticalSection(&semLocal);
  if ( inited )
  {
    v7 = v4 & 2;
    v8 = *(_DWORD *)((v7 != 0 ? 4 : 0) + a1 + 36);
    if ( v8 <= 0x7FFFFFFF )
    {
      v9 = LocalAlloc(0x40u, 2LL * v8);
      v10 = v9;
      if ( v9 )
      {
        v11 = 0;
        if ( !(unsigned int)bGetDistGlyphIndices(a1, v9, v7) )
          goto LABEL_23;
        v12 = *(unsigned __int16 *)(a1 + 18);
        v24 = &v27;
        v30 = 0;
        v23 = &v26;
        v22 = 0;
        p_uBytes = &uBytes;
        v29 = 0;
        uBytes = 0;
        v26 = 0;
        v27 = 0;
        if ( !(unsigned int)NtGdiGetUFIPathname(a1, &v30, SourceString, &v29, v12, (char *)&uBytes + 4) )
          goto LABEL_23;
        *(_OWORD *)FileHandle = 0;
        v36 = 0;
        if ( HIDWORD(uBytes) )
        {
          v16 = LocalAlloc(0, (unsigned int)uBytes);
          v15 = v16;
          if ( !v16 )
            goto LABEL_23;
          v24 = 0;
          v23 = 0;
          v22 = v16;
          p_uBytes = 0;
          if ( !(unsigned int)NtGdiGetUFIPathname(a1, 0, 0, 0, *(unsigned __int16 *)(a1 + 18), 0) )
          {
LABEL_22:
            LocalFree(v15);
            goto LABEL_23;
          }
          v14 = uBytes;
          v13 = v15;
        }
        else
        {
          if ( !(unsigned int)bMapFileUNICODEClideSide(SourceString, FileHandle, 1) )
            goto LABEL_23;
          v13 = (void *)v36;
          if ( !(_QWORD)v36 )
            goto LABEL_23;
          v14 = DWORD2(v36);
          v15 = 0;
        }
        v28 = v14;
        v17 = RtlDecodePointer(gfpCreateFontPackage);
        v18 = 13;
        v34 = (unsigned __int16 (__fastcall *)(void *, _QWORD, __int64, __int64, __int64, int, SIZE_T *, HLOCAL, int *, int *, __int16, void *, _WORD, __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 (__fastcall *)(), _QWORD))v17;
        if ( !v26 )
          v18 = 9;
        LOWORD(v24) = 3;
        LOWORD(v23) = 0;
        LOWORD(v22) = (v7 != 0) + 1;
        LOWORD(p_uBytes) = v27;
        LOWORD(v20) = v18;
        if ( !v34(
                v13,
                v28,
                v33,
                v32,
                v31,
                v20,
                p_uBytes,
                v22,
                v23,
                v24,
                -1,
                v10,
                v8,
                AllocCallback,
                ReAllocCallback,
                FreeCallback,
                0) )
        {
          if ( v7 )
          {
            LocalFree(*(HLOCAL *)(a1 + 48));
            *(_QWORD *)(a1 + 48) = 0;
            *(_DWORD *)(a1 + 40) = 0;
          }
          else
          {
            *(_WORD *)(a1 + 16) = 2;
          }
          v11 = 1;
        }
        if ( !HIDWORD(uBytes) )
        {
          vUnmapFileClideSide(FileHandle);
          goto LABEL_23;
        }
        if ( v15 )
          goto LABEL_22;
LABEL_23:
        LocalFree(v10);
        return v11;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800802e0  push    rbp
0x1800802e2  push    rbx
0x1800802e3  push    rsi
0x1800802e4  push    rdi
0x1800802e5  push    r12
0x1800802e7  push    r13
0x1800802e9  push    r14
0x1800802eb  push    r15
0x1800802ed  lea     rbp, [rsp-618h]
0x1800802f5  sub     rsp, 728h
0x1800802fc  mov     rax, cs:__security_cookie
0x180080303  xor     rax, rsp
0x180080306  mov     [rbp+650h+var_50], rax
0x18008030d  movzx   esi, word ptr [rcx+10h]
0x180080311  mov     rdi, rcx
0x180080314  lea     rcx, semLocal; CriticalSection
0x18008031b  mov     [rbp+650h+var_6B0], r9
0x18008031f  mov     [rbp+650h+var_6A8], r8
0x180080323  mov     [rbp+650h+var_6A0], rdx
0x180080327  call    cs:__imp_RtlEnterCriticalSection
0x18008032d  lea     rcx, gfpCreateFontPackage
0x180080334  call    bInitSubsetterFunctionPointer
0x180080339  lea     rcx, semLocal; CriticalSection
0x180080340  mov     ebx, eax
0x180080342  call    cs:__imp_RtlLeaveCriticalSection
0x180080348  xor     r15d, r15d
0x18008034b  test    ebx, ebx
0x18008034d  jz      loc_1800805B1
0x180080353  and     esi, 2
0x180080356  mov     eax, esi
0x180080358  neg     eax
0x18008035a  sbb     rcx, rcx
0x18008035d  and     ecx, 4
0x180080360  mov     r13d, [rcx+rdi+24h]
0x180080365  cmp     r13d, 7FFFFFFFh
0x18008036c  ja      loc_1800805B1
0x180080372  mov     edx, r13d
0x180080375  lea     ecx, [r15+40h]; uFlags
0x180080379  add     rdx, rdx; uBytes
0x18008037c  call    cs:__imp_LocalAlloc
0x180080382  mov     r14, rax
0x180080385  test    rax, rax
0x180080388  jz      loc_1800805B1
0x18008038e  mov     r8d, esi
0x180080391  mov     rdx, rax
0x180080394  mov     rcx, rdi
0x180080397  mov     r12d, r15d
0x18008039a  call    bGetDistGlyphIndices
0x18008039f  test    eax, eax
0x1800803a1  jz      loc_180080598
0x1800803a7  movzx   eax, word ptr [rdi+12h]
0x1800803ab  lea     rcx, [rbp+650h+var_6C4]
0x1800803af  mov     [rsp+760h+var_718], rcx
0x1800803b4  lea     r9, [rbp+650h+var_6BC]
0x1800803b8  lea     rcx, [rbp+650h+var_6C8]
0x1800803bc  mov     [rbp+650h+var_6B8], r15d
0x1800803c0  mov     [rsp+760h+var_720], rcx
0x1800803c5  lea     r8, [rbp+650h+SourceString]
0x1800803c9  mov     [rsp+760h+var_728], r15
0x1800803ce  lea     rcx, [rbp+650h+uBytes]
0x1800803d2  mov     [rsp+760h+var_730], rcx
0x1800803d7  lea     rdx, [rbp+650h+var_6B8]
0x1800803db  lea     rcx, [rbp+650h+uBytes+4]
0x1800803df  mov     [rbp+650h+var_6BC], r15d
0x1800803e3  mov     [rsp+760h+var_738], rcx
0x1800803e8  mov     rcx, rdi
0x1800803eb  mov     dword ptr [rbp+650h+uBytes+4], r15d
0x1800803ef  mov     dword ptr [rbp+650h+uBytes], r15d
0x1800803f3  mov     [rbp+650h+var_6C8], r15d
0x1800803f7  mov     [rbp+650h+var_6C4], r15d
0x1800803fb  mov     dword ptr [rsp+760h+var_740], eax
0x1800803ff  call    cs:__imp_NtGdiGetUFIPathname
0x180080405  test    eax, eax
0x180080407  jz      loc_180080598
0x18008040d  xorps   xmm0, xmm0
0x180080410  movups  xmmword ptr [rbp+650h+FileHandle], xmm0
0x180080414  movups  [rbp+650h+var_680], xmm0
0x180080418  cmp     dword ptr [rbp+650h+uBytes+4], r15d
0x18008041c  jnz     short loc_18008044B
0x18008041e  lea     r8d, [r15+1]
0x180080422  lea     rdx, [rbp+650h+FileHandle]; FileHandle
0x180080426  lea     rcx, [rbp+650h+SourceString]; SourceString
0x18008042a  call    bMapFileUNICODEClideSide
0x18008042f  test    eax, eax
0x180080431  jz      loc_180080598
0x180080437  mov     r15, qword ptr [rbp+650h+var_680]
0x18008043b  test    r15, r15
0x18008043e  jz      loc_180080598
0x180080444  mov     eax, dword ptr [rbp+650h+var_680+8]
0x180080447  xor     ebx, ebx
0x180080449  jmp     short loc_1800804A2
0x18008044b  mov     edx, dword ptr [rbp+650h+uBytes]; uBytes
0x18008044e  xor     ecx, ecx; uFlags
0x180080450  call    cs:__imp_LocalAlloc
0x180080456  mov     rbx, rax
0x180080459  test    rax, rax
0x18008045c  jz      loc_180080598
0x180080462  movzx   ecx, word ptr [rdi+12h]
0x180080466  xor     r9d, r9d
0x180080469  mov     [rsp+760h+var_718], r15
0x18008046e  xor     r8d, r8d
0x180080471  mov     [rsp+760h+var_720], r15
0x180080476  xor     edx, edx
0x180080478  mov     [rsp+760h+var_728], rax
0x18008047d  mov     [rsp+760h+var_730], r15
0x180080482  mov     [rsp+760h+var_738], r15
0x180080487  mov     dword ptr [rsp+760h+var_740], ecx
0x18008048b  mov     rcx, rdi
0x18008048e  call    cs:__imp_NtGdiGetUFIPathname
0x180080494  test    eax, eax
0x180080496  jz      loc_18008058F
0x18008049c  mov     eax, dword ptr [rbp+650h+uBytes]
0x18008049f  mov     r15, rbx
0x1800804a2  mov     rcx, cs:gfpCreateFontPackage; Pointer
0x1800804a9  mov     [rbp+650h+var_6C0], eax
0x1800804ac  call    cs:__imp_RtlDecodePointer
0x1800804b2  mov     ecx, 0Dh
0x1800804b7  mov     [rbp+650h+var_698], rax
0x1800804bb  cmp     [rbp+650h+var_6C8], r12d
0x1800804bf  jnz     short loc_1800804C6
0x1800804c1  mov     ecx, 9
0x1800804c6  mov     r9, [rbp+650h+var_6A8]
0x1800804ca  xor     r11d, r11d
0x1800804cd  mov     r8, [rbp+650h+var_6A0]
0x1800804d1  mov     eax, esi
0x1800804d3  mov     edx, [rbp+650h+var_6C0]
0x1800804d6  neg     eax
0x1800804d8  mov     [rsp+760h+var_6E0], r11
0x1800804e0  lea     rax, FreeCallback
0x1800804e7  mov     [rsp+760h+var_6E8], rax
0x1800804ec  sbb     r10w, r10w
0x1800804f0  lea     rax, ReAllocCallback
0x1800804f7  neg     r10w
0x1800804fb  mov     [rsp+760h+var_6F0], rax
0x180080500  inc     r10w
0x180080504  lea     rax, AllocCallback
0x18008050b  mov     [rsp+760h+var_6F8], rax
0x180080510  movzx   eax, word ptr [rbp+650h+var_6C4]
0x180080514  mov     [rsp+760h+var_700], r13w
0x18008051a  mov     [rsp+760h+var_708], r14
0x18008051f  mov     [rsp+760h+var_710], 0FFFFh
0x180080526  mov     word ptr [rsp+760h+var_718], 3
0x18008052d  mov     word ptr [rsp+760h+var_720], r11w
0x180080533  mov     word ptr [rsp+760h+var_728], r10w
0x180080539  mov     word ptr [rsp+760h+var_730], ax
0x18008053e  mov     rax, [rbp+650h+var_6B0]
0x180080542  mov     word ptr [rsp+760h+var_738], cx
0x180080547  mov     rcx, r15
0x18008054a  mov     [rsp+760h+var_740], rax
0x18008054f  mov     rax, [rbp+650h+var_698]
0x180080553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080558  xor     r15d, r15d
0x18008055b  test    ax, ax
0x18008055e  jnz     short loc_180080584
0x180080560  test    esi, esi
0x180080562  jz      short loc_180080578
0x180080564  mov     rcx, [rdi+30h]; hMem
0x180080568  call    cs:__imp_LocalFree
0x18008056e  mov     [rdi+30h], r15
0x180080572  mov     [rdi+28h], r15d
0x180080576  jmp     short loc_18008057E
0x180080578  mov     word ptr [rdi+10h], 2
0x18008057e  mov     r12d, 1
0x180080584  cmp     dword ptr [rbp+650h+uBytes+4], r15d
0x180080588  jz      short loc_1800805A6
0x18008058a  test    rbx, rbx
0x18008058d  jz      short loc_180080598
0x18008058f  mov     rcx, rbx; hMem
0x180080592  call    cs:__imp_LocalFree
0x180080598  mov     rcx, r14; hMem
0x18008059b  call    cs:__imp_LocalFree
0x1800805a1  mov     eax, r12d
0x1800805a4  jmp     short loc_1800805B3
0x1800805a6  lea     rcx, [rbp+650h+FileHandle]
0x1800805aa  call    vUnmapFileClideSide
0x1800805af  jmp     short loc_180080598
0x1800805b1  xor     eax, eax
0x1800805b3  mov     rcx, [rbp+650h+var_50]
0x1800805ba  xor     rcx, rsp; StackCookie
0x1800805bd  call    __security_check_cookie
0x1800805c2  add     rsp, 728h
0x1800805c9  pop     r15
0x1800805cb  pop     r14
0x1800805cd  pop     r13
0x1800805cf  pop     r12
0x1800805d1  pop     rdi
0x1800805d2  pop     rsi
0x1800805d3  pop     rbx
0x1800805d4  pop     rbp
0x1800805d5  retn
```
