# AddActiveAssociation(ushort const *,ushort const *,int,CAssociationContext *)

- ea: `0x1800620c4`
- end: `0x180062303`
- name: `?AddActiveAssociation@@YAJPEBG0HPEAVCAssociationContext@@@Z`
- size: `575`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, struct CAssociationContext *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002eee0`
- `0x180030960`

## callees

- `0x1800119b0`
- `0x18001b0fc`
- `0x1800620c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800620f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800620f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062295`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180062295`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062181`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800621dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062230`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800622ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800622ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800622de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062181`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800621dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180062230`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800622ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800622ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800622de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800622bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800622d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800622ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800622bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800622d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800622ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180062190`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800621ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006223f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180062190`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800621ec`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006223f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062164`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062164`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180062121`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180062146`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180062121`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180062146`

## pseudocode

```c
__int64 __fastcall AddActiveAssociation(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        int a3,
        struct CAssociationContext *a4)
{
  _QWORD *v4; // rdi
  LPCWCH *i; // rbx
  int v10; // eax
  signed int v11; // ebx
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  _QWORD *v14; // rax
  unsigned __int64 v15; // rbx
  HANDLE v16; // rax
  unsigned __int16 *v17; // rax
  unsigned __int64 v18; // rbx
  HANDLE v19; // rax
  unsigned __int16 *v20; // rax
  _QWORD *v21; // rax
  void *v22; // rsi
  HANDLE v23; // rax
  void *v24; // rsi
  HANDLE v25; // rax
  HANDLE v26; // rax
  unsigned __int64 v28; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int64 v29[8]; // [rsp+38h] [rbp-40h] BYREF

  v4 = 0;
  v28 = 0;
  v29[0] = 0;
  EnterCriticalSection(&ActiveAssociationsList);
  for ( i = (LPCWCH *)qword_1800A46A0; ; i = (LPCWCH *)*i )
  {
    if ( i == (LPCWCH *)&qword_1800A46A0 )
      goto LABEL_12;
    v10 = CompareStringOrdinal(a1, -1, i[3], -1, 1);
    if ( v10 == 2 )
    {
      if ( !a3 || (v10 = CompareStringOrdinal(a2, -1, i[4], -1, 1), v10 == 2) )
      {
        v11 = -2140930030;
        goto LABEL_23;
      }
    }
    if ( !v10 )
      break;
  }
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  if ( !v11 )
  {
LABEL_12:
    ProcessHeap = GetProcessHeap();
    v14 = HeapAlloc(ProcessHeap, 0, 0x30u);
    v4 = v14;
    if ( !v14 )
    {
LABEL_13:
      v11 = -2147024882;
      goto LABEL_23;
    }
    *(_OWORD *)v14 = 0;
    *((_OWORD *)v14 + 1) = 0;
    *((_OWORD *)v14 + 2) = 0;
    *((_DWORD *)v14 + 10) = a3;
    v11 = StringCchLengthW(a1, 0x300u, &v28);
    if ( v11 >= 0 )
    {
      v15 = v28 + 1;
      v16 = GetProcessHeap();
      v17 = (unsigned __int16 *)HeapAlloc(v16, 0, 2 * v15);
      v4[3] = v17;
      if ( !v17 )
        goto LABEL_13;
      v11 = StringCchCopyW(v17, v15, a1);
      if ( !a2 )
        goto LABEL_20;
      v11 = StringCchLengthW(a2, 0xB8u, v29);
      if ( v11 >= 0 )
      {
        v18 = v29[0] + 1;
        v19 = GetProcessHeap();
        v20 = (unsigned __int16 *)HeapAlloc(v19, 0, 2 * v18);
        v4[4] = v20;
        if ( !v20 )
          goto LABEL_13;
        v11 = StringCchCopyW(v20, v18, a2);
        if ( v11 >= 0 )
        {
LABEL_20:
          v4[2] = a4;
          v21 = (_QWORD *)qword_1800A46A8;
          if ( *(LPVOID **)qword_1800A46A8 != &qword_1800A46A0 )
            __fastfail(3u);
          *v4 = &qword_1800A46A0;
          v4[1] = v21;
          *v21 = v4;
          qword_1800A46A8 = (__int64)v4;
        }
      }
    }
  }
LABEL_23:
  LeaveCriticalSection(&ActiveAssociationsList);
  if ( v11 && v4 )
  {
    v22 = (void *)v4[3];
    if ( v22 )
    {
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v22);
    }
    v24 = (void *)v4[4];
    if ( v24 )
    {
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v24);
    }
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v4);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800620c4  push    rbx
0x1800620c6  push    rbp
0x1800620c7  push    rsi
0x1800620c8  push    rdi
0x1800620c9  push    r13
0x1800620cb  push    r14
0x1800620cd  push    r15
0x1800620cf  sub     rsp, 40h
0x1800620d3  xor     edi, edi
0x1800620d5  mov     r14, rcx
0x1800620d8  lea     rcx, ?ActiveAssociationsList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x1800620df  mov     [rsp+78h+var_48], rdi
0x1800620e4  mov     [rsp+78h+var_40], rdi
0x1800620e9  mov     r15, r9
0x1800620ec  mov     ebp, r8d
0x1800620ef  mov     rsi, rdx
0x1800620f2  call    cs:__imp_EnterCriticalSection
0x1800620f8  mov     rbx, cs:qword_1800A46A0
0x1800620ff  lea     r13, qword_1800A46A0
0x180062106  cmp     rbx, r13
0x180062109  jz      short loc_180062181
0x18006210b  mov     r8, [rbx+18h]; lpString2
0x18006210f  or      r9d, 0FFFFFFFFh; cchCount2
0x180062113  or      edx, r9d; cchCount1
0x180062116  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x18006211e  mov     rcx, r14; lpString1
0x180062121  call    cs:__imp_CompareStringOrdinal
0x180062127  cmp     eax, 2
0x18006212a  jnz     short loc_180062151
0x18006212c  test    ebp, ebp
0x18006212e  jz      short loc_18006215A
0x180062130  mov     r8, [rbx+20h]; lpString2
0x180062134  or      r9d, 0FFFFFFFFh; cchCount2
0x180062138  or      edx, r9d; cchCount1
0x18006213b  mov     [rsp+78h+bIgnoreCase], 1; bIgnoreCase
0x180062143  mov     rcx, rsi; lpString1
0x180062146  call    cs:__imp_CompareStringOrdinal
0x18006214c  cmp     eax, 2
0x18006214f  jz      short loc_18006215A
0x180062151  test    eax, eax
0x180062153  jz      short loc_180062164
0x180062155  mov     rbx, [rbx]
0x180062158  jmp     short loc_180062106
0x18006215a  mov     ebx, 80640012h
0x18006215f  jmp     loc_18006228E
0x180062164  call    cs:__imp_GetLastError
0x18006216a  mov     ebx, eax
0x18006216c  test    eax, eax
0x18006216e  jle     short loc_180062179
0x180062170  movzx   ebx, ax
0x180062173  or      ebx, 80070000h
0x180062179  test    ebx, ebx
0x18006217b  jnz     loc_18006228E
0x180062181  call    cs:__imp_GetProcessHeap
0x180062187  xor     edx, edx; dwFlags
0x180062189  mov     rcx, rax; hHeap
0x18006218c  lea     r8d, [rdx+30h]; dwBytes
0x180062190  call    cs:__imp_HeapAlloc
0x180062196  mov     rdi, rax
0x180062199  test    rax, rax
0x18006219c  jnz     short loc_1800621A8
0x18006219e  mov     ebx, 8007000Eh
0x1800621a3  jmp     loc_18006228E
0x1800621a8  xorps   xmm0, xmm0
0x1800621ab  lea     r8, [rsp+78h+var_48]; unsigned __int64 *
0x1800621b0  movups  xmmword ptr [rax], xmm0
0x1800621b3  mov     edx, 300h; unsigned __int64
0x1800621b8  mov     rcx, r14; unsigned __int16 *
0x1800621bb  movups  xmmword ptr [rax+10h], xmm0
0x1800621bf  movups  xmmword ptr [rax+20h], xmm0
0x1800621c3  mov     [rax+28h], ebp
0x1800621c6  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800621cb  mov     ebx, eax
0x1800621cd  test    eax, eax
0x1800621cf  js      loc_18006228E
0x1800621d5  mov     rbx, [rsp+78h+var_48]
0x1800621da  inc     rbx
0x1800621dd  call    cs:__imp_GetProcessHeap
0x1800621e3  lea     r8, [rbx+rbx]; dwBytes
0x1800621e7  xor     edx, edx; dwFlags
0x1800621e9  mov     rcx, rax; hHeap
0x1800621ec  call    cs:__imp_HeapAlloc
0x1800621f2  mov     [rdi+18h], rax
0x1800621f6  test    rax, rax
0x1800621f9  jz      short loc_18006219E
0x1800621fb  mov     r8, r14; unsigned __int16 *
0x1800621fe  mov     rdx, rbx; unsigned __int64
0x180062201  mov     rcx, rax; unsigned __int16 *
0x180062204  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180062209  mov     ebx, eax
0x18006220b  test    rsi, rsi
0x18006220e  jz      short loc_180062266
0x180062210  lea     r8, [rsp+78h+var_40]; unsigned __int64 *
0x180062215  mov     edx, 0B8h; unsigned __int64
0x18006221a  mov     rcx, rsi; unsigned __int16 *
0x18006221d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180062222  mov     ebx, eax
0x180062224  test    eax, eax
0x180062226  js      short loc_18006228E
0x180062228  mov     rbx, [rsp+78h+var_40]
0x18006222d  inc     rbx
0x180062230  call    cs:__imp_GetProcessHeap
0x180062236  lea     r8, [rbx+rbx]; dwBytes
0x18006223a  xor     edx, edx; dwFlags
0x18006223c  mov     rcx, rax; hHeap
0x18006223f  call    cs:__imp_HeapAlloc
0x180062245  mov     [rdi+20h], rax
0x180062249  test    rax, rax
0x18006224c  jz      loc_18006219E
0x180062252  mov     r8, rsi; unsigned __int16 *
0x180062255  mov     rdx, rbx; unsigned __int64
0x180062258  mov     rcx, rax; unsigned __int16 *
0x18006225b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180062260  mov     ebx, eax
0x180062262  test    eax, eax
0x180062264  js      short loc_18006228E
0x180062266  mov     [rdi+10h], r15
0x18006226a  mov     rax, cs:qword_1800A46A8
0x180062271  cmp     [rax], r13
0x180062274  jz      short loc_18006227D
0x180062276  mov     ecx, 3
0x18006227b  int     29h; Win8: RtlFailFast(ecx)
0x18006227d  mov     [rdi], r13
0x180062280  mov     [rdi+8], rax
0x180062284  mov     [rax], rdi
0x180062287  mov     cs:qword_1800A46A8, rdi
0x18006228e  lea     rcx, ?ActiveAssociationsList@@3U_DAS_LOCKED_LIST@@A; lpCriticalSection
0x180062295  call    cs:__imp_LeaveCriticalSection
0x18006229b  test    ebx, ebx
0x18006229d  jz      short loc_1800622F2
0x18006229f  test    rdi, rdi
0x1800622a2  jz      short loc_1800622F2
0x1800622a4  mov     rsi, [rdi+18h]
0x1800622a8  test    rsi, rsi
0x1800622ab  jz      short loc_1800622C1
0x1800622ad  call    cs:__imp_GetProcessHeap
0x1800622b3  mov     r8, rsi; lpMem
0x1800622b6  xor     edx, edx; dwFlags
0x1800622b8  mov     rcx, rax; hHeap
0x1800622bb  call    cs:__imp_HeapFree
0x1800622c1  mov     rsi, [rdi+20h]
0x1800622c5  test    rsi, rsi
0x1800622c8  jz      short loc_1800622DE
0x1800622ca  call    cs:__imp_GetProcessHeap
0x1800622d0  mov     r8, rsi; lpMem
0x1800622d3  xor     edx, edx; dwFlags
0x1800622d5  mov     rcx, rax; hHeap
0x1800622d8  call    cs:__imp_HeapFree
0x1800622de  call    cs:__imp_GetProcessHeap
0x1800622e4  mov     r8, rdi; lpMem
0x1800622e7  xor     edx, edx; dwFlags
0x1800622e9  mov     rcx, rax; hHeap
0x1800622ec  call    cs:__imp_HeapFree
0x1800622f2  mov     eax, ebx
0x1800622f4  add     rsp, 40h
0x1800622f8  pop     r15
0x1800622fa  pop     r14
0x1800622fc  pop     r13
0x1800622fe  pop     rdi
0x1800622ff  pop     rsi
0x180062300  pop     rbp
0x180062301  pop     rbx
0x180062302  retn
```
