# bDoFontSubset

- ea: `0x180085150`
- end: `0x180085483`
- name: `bDoFontSubset`
- size: `819`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180099e04`

## callees

- `0x180045548`
- `0x180046018`
- `0x180071594`
- `0x18007f800`
- `0x180085150`
- `0x18008548c`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800851f8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800852d8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800851f8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800852d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085402`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085432`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085441`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085402`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085432`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085441`
- `ntdll!RtlEnterCriticalSection` at `0x180085197`
- `ntdll!RtlEnterCriticalSection` at `0x180085197`
- `ntdll!RtlLeaveCriticalSection` at `0x1800851b8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800851b8`
- `ntdll!RtlDecodePointer` at `0x180085340`
- `ntdll!RtlDecodePointer` at `0x180085340`
- `win32u!NtGdiGetUFIPathname` at `0x180085281`
- `win32u!NtGdiGetUFIPathname` at `0x18008531c`
- `win32u!NtGdiGetUFIPathname` at `0x180085281`
- `win32u!NtGdiGetUFIPathname` at `0x18008531c`

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
0x180085150  push    rbp
0x180085152  push    rbx
0x180085153  push    rsi
0x180085154  push    rdi
0x180085155  push    r12
0x180085157  push    r13
0x180085159  push    r14
0x18008515b  push    r15
0x18008515d  lea     rbp, [rsp-618h]
0x180085165  sub     rsp, 728h
0x18008516c  mov     rax, cs:__security_cookie
0x180085173  xor     rax, rsp
0x180085176  mov     [rbp+650h+var_50], rax
0x18008517d  movzx   esi, word ptr [rcx+10h]
0x180085181  mov     rdi, rcx
0x180085184  lea     rcx, semLocal; CriticalSection
0x18008518b  mov     [rbp+650h+var_6B0], r9
0x18008518f  mov     [rbp+650h+var_6A8], r8
0x180085193  mov     [rbp+650h+var_6A0], rdx
0x180085197  call    cs:__imp_RtlEnterCriticalSection
0x18008519e  nop     dword ptr [rax+rax+00h]
0x1800851a3  lea     rcx, gfpCreateFontPackage
0x1800851aa  call    bInitSubsetterFunctionPointer
0x1800851af  lea     rcx, semLocal; CriticalSection
0x1800851b6  mov     ebx, eax
0x1800851b8  call    cs:__imp_RtlLeaveCriticalSection
0x1800851bf  nop     dword ptr [rax+rax+00h]
0x1800851c4  xor     r15d, r15d
0x1800851c7  test    ebx, ebx
0x1800851c9  jz      loc_18008545D
0x1800851cf  and     esi, 2
0x1800851d2  mov     eax, esi
0x1800851d4  neg     eax
0x1800851d6  sbb     rcx, rcx
0x1800851d9  and     ecx, 4
0x1800851dc  mov     r13d, [rcx+rdi+24h]
0x1800851e1  cmp     r13d, 7FFFFFFFh
0x1800851e8  ja      loc_18008545D
0x1800851ee  mov     edx, r13d
0x1800851f1  lea     ecx, [r15+40h]; uFlags
0x1800851f5  add     rdx, rdx; uBytes
0x1800851f8  call    cs:__imp_LocalAlloc
0x1800851ff  nop     dword ptr [rax+rax+00h]
0x180085204  mov     r14, rax
0x180085207  test    rax, rax
0x18008520a  jz      loc_18008545D
0x180085210  mov     r8d, esi
0x180085213  mov     rdx, rax
0x180085216  mov     rcx, rdi
0x180085219  mov     r12d, r15d
0x18008521c  call    bGetDistGlyphIndices
0x180085221  test    eax, eax
0x180085223  jz      loc_18008543E
0x180085229  movzx   eax, word ptr [rdi+12h]
0x18008522d  lea     rcx, [rbp+650h+var_6C4]
0x180085231  mov     [rsp+760h+var_718], rcx
0x180085236  lea     r9, [rbp+650h+var_6BC]
0x18008523a  lea     rcx, [rbp+650h+var_6C8]
0x18008523e  mov     [rbp+650h+var_6B8], r15d
0x180085242  mov     [rsp+760h+var_720], rcx
0x180085247  lea     r8, [rbp+650h+SourceString]
0x18008524b  mov     [rsp+760h+var_728], r15
0x180085250  lea     rcx, [rbp+650h+uBytes]
0x180085254  mov     [rsp+760h+var_730], rcx
0x180085259  lea     rdx, [rbp+650h+var_6B8]
0x18008525d  lea     rcx, [rbp+650h+uBytes+4]
0x180085261  mov     [rbp+650h+var_6BC], r15d
0x180085265  mov     [rsp+760h+var_738], rcx
0x18008526a  mov     rcx, rdi
0x18008526d  mov     dword ptr [rbp+650h+uBytes+4], r15d
0x180085271  mov     dword ptr [rbp+650h+uBytes], r15d
0x180085275  mov     [rbp+650h+var_6C8], r15d
0x180085279  mov     [rbp+650h+var_6C4], r15d
0x18008527d  mov     dword ptr [rsp+760h+var_740], eax
0x180085281  call    cs:__imp_NtGdiGetUFIPathname
0x180085288  nop     dword ptr [rax+rax+00h]
0x18008528d  test    eax, eax
0x18008528f  jz      loc_18008543E
0x180085295  xorps   xmm0, xmm0
0x180085298  movups  xmmword ptr [rbp+650h+FileHandle], xmm0
0x18008529c  movups  [rbp+650h+var_680], xmm0
0x1800852a0  cmp     dword ptr [rbp+650h+uBytes+4], r15d
0x1800852a4  jnz     short loc_1800852D3
0x1800852a6  lea     r8d, [r15+1]
0x1800852aa  lea     rdx, [rbp+650h+FileHandle]; FileHandle
0x1800852ae  lea     rcx, [rbp+650h+SourceString]; SourceString
0x1800852b2  call    bMapFileUNICODEClideSide
0x1800852b7  test    eax, eax
0x1800852b9  jz      loc_18008543E
0x1800852bf  mov     r15, qword ptr [rbp+650h+var_680]
0x1800852c3  test    r15, r15
0x1800852c6  jz      loc_18008543E
0x1800852cc  mov     eax, dword ptr [rbp+650h+var_680+8]
0x1800852cf  xor     ebx, ebx
0x1800852d1  jmp     short loc_180085336
0x1800852d3  mov     edx, dword ptr [rbp+650h+uBytes]; uBytes
0x1800852d6  xor     ecx, ecx; uFlags
0x1800852d8  call    cs:__imp_LocalAlloc
0x1800852df  nop     dword ptr [rax+rax+00h]
0x1800852e4  mov     rbx, rax
0x1800852e7  test    rax, rax
0x1800852ea  jz      loc_18008543E
0x1800852f0  movzx   ecx, word ptr [rdi+12h]
0x1800852f4  xor     r9d, r9d
0x1800852f7  mov     [rsp+760h+var_718], r15
0x1800852fc  xor     r8d, r8d
0x1800852ff  mov     [rsp+760h+var_720], r15
0x180085304  xor     edx, edx
0x180085306  mov     [rsp+760h+var_728], rax
0x18008530b  mov     [rsp+760h+var_730], r15
0x180085310  mov     [rsp+760h+var_738], r15
0x180085315  mov     dword ptr [rsp+760h+var_740], ecx
0x180085319  mov     rcx, rdi
0x18008531c  call    cs:__imp_NtGdiGetUFIPathname
0x180085323  nop     dword ptr [rax+rax+00h]
0x180085328  test    eax, eax
0x18008532a  jz      loc_18008542F
0x180085330  mov     eax, dword ptr [rbp+650h+uBytes]
0x180085333  mov     r15, rbx
0x180085336  mov     rcx, cs:gfpCreateFontPackage; Pointer
0x18008533d  mov     [rbp+650h+var_6C0], eax
0x180085340  call    cs:__imp_RtlDecodePointer
0x180085347  nop     dword ptr [rax+rax+00h]
0x18008534c  mov     ecx, 0Dh
0x180085351  mov     [rbp+650h+var_698], rax
0x180085355  cmp     [rbp+650h+var_6C8], r12d
0x180085359  jnz     short loc_180085360
0x18008535b  mov     ecx, 9
0x180085360  mov     r9, [rbp+650h+var_6A8]
0x180085364  xor     r11d, r11d
0x180085367  mov     r8, [rbp+650h+var_6A0]
0x18008536b  mov     eax, esi
0x18008536d  mov     edx, [rbp+650h+var_6C0]
0x180085370  neg     eax
0x180085372  mov     [rsp+760h+var_6E0], r11
0x18008537a  lea     rax, FreeCallback
0x180085381  mov     [rsp+760h+var_6E8], rax
0x180085386  sbb     r10w, r10w
0x18008538a  lea     rax, ReAllocCallback
0x180085391  neg     r10w
0x180085395  mov     [rsp+760h+var_6F0], rax
0x18008539a  inc     r10w
0x18008539e  lea     rax, AllocCallback
0x1800853a5  mov     [rsp+760h+var_6F8], rax
0x1800853aa  movzx   eax, word ptr [rbp+650h+var_6C4]
0x1800853ae  mov     [rsp+760h+var_700], r13w
0x1800853b4  mov     [rsp+760h+var_708], r14
0x1800853b9  mov     [rsp+760h+var_710], 0FFFFh
0x1800853c0  mov     word ptr [rsp+760h+var_718], 3
0x1800853c7  mov     word ptr [rsp+760h+var_720], r11w
0x1800853cd  mov     word ptr [rsp+760h+var_728], r10w
0x1800853d3  mov     word ptr [rsp+760h+var_730], ax
0x1800853d8  mov     rax, [rbp+650h+var_6B0]
0x1800853dc  mov     word ptr [rsp+760h+var_738], cx
0x1800853e1  mov     rcx, r15
0x1800853e4  mov     [rsp+760h+var_740], rax
0x1800853e9  mov     rax, [rbp+650h+var_698]
0x1800853ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800853f2  xor     r15d, r15d
0x1800853f5  test    ax, ax
0x1800853f8  jnz     short loc_180085424
0x1800853fa  test    esi, esi
0x1800853fc  jz      short loc_180085418
0x1800853fe  mov     rcx, [rdi+30h]; hMem
0x180085402  call    cs:__imp_LocalFree
0x180085409  nop     dword ptr [rax+rax+00h]
0x18008540e  mov     [rdi+30h], r15
0x180085412  mov     [rdi+28h], r15d
0x180085416  jmp     short loc_18008541E
0x180085418  mov     word ptr [rdi+10h], 2
0x18008541e  mov     r12d, 1
0x180085424  cmp     dword ptr [rbp+650h+uBytes+4], r15d
0x180085428  jz      short loc_180085452
0x18008542a  test    rbx, rbx
0x18008542d  jz      short loc_18008543E
0x18008542f  mov     rcx, rbx; hMem
0x180085432  call    cs:__imp_LocalFree
0x180085439  nop     dword ptr [rax+rax+00h]
0x18008543e  mov     rcx, r14; hMem
0x180085441  call    cs:__imp_LocalFree
0x180085448  nop     dword ptr [rax+rax+00h]
0x18008544d  mov     eax, r12d
0x180085450  jmp     short loc_18008545F
0x180085452  lea     rcx, [rbp+650h+FileHandle]
0x180085456  call    vUnmapFileClideSide
0x18008545b  jmp     short loc_18008543E
0x18008545d  xor     eax, eax
0x18008545f  mov     rcx, [rbp+650h+var_50]
0x180085466  xor     rcx, rsp; StackCookie
0x180085469  call    __security_check_cookie
0x18008546e  add     rsp, 728h
0x180085475  pop     r15
0x180085477  pop     r14
0x180085479  pop     r13
0x18008547b  pop     r12
0x18008547d  pop     rdi
0x18008547e  pop     rsi
0x18008547f  pop     rbx
0x180085480  pop     rbp
0x180085481  retn
```
