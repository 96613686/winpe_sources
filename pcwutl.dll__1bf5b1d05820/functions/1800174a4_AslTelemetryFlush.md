# AslTelemetryFlush

- ea: `0x1800174a4`
- end: `0x180017ca6`
- name: `AslTelemetryFlush`
- size: `2050`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18001734c`
- `0x180017cac`
- `0x180019850`

## callees

- `0x180001008`
- `0x180008948`
- `0x18000b854`
- `0x18001614c`
- `0x180016378`
- `0x1800174a4`
- `0x180018064`
- `0x1800180f8`
- `0x1800191a2`
- `0x1800191f0`

## import_xrefs

- `msvcrt!sprintf_s` at `0x1800177d4`
- `msvcrt!sprintf_s` at `0x180017818`
- `msvcrt!sprintf_s` at `0x18001791c`
- `msvcrt!sprintf_s` at `0x1800177d4`
- `msvcrt!sprintf_s` at `0x180017818`
- `msvcrt!sprintf_s` at `0x18001791c`
- `KERNEL32!GetProcessHeap` at `0x1800174f2`
- `KERNEL32!GetProcessHeap` at `0x180017521`
- `KERNEL32!GetProcessHeap` at `0x18001754b`
- `KERNEL32!GetProcessHeap` at `0x180017572`
- `KERNEL32!GetProcessHeap` at `0x180017590`
- `KERNEL32!GetProcessHeap` at `0x1800175ae`
- `KERNEL32!GetProcessHeap` at `0x1800175cc`
- `KERNEL32!GetProcessHeap` at `0x1800174f2`
- `KERNEL32!GetProcessHeap` at `0x180017521`
- `KERNEL32!GetProcessHeap` at `0x18001754b`
- `KERNEL32!GetProcessHeap` at `0x180017572`
- `KERNEL32!GetProcessHeap` at `0x180017590`
- `KERNEL32!GetProcessHeap` at `0x1800175ae`
- `KERNEL32!GetProcessHeap` at `0x1800175cc`
- `KERNEL32!HeapFree` at `0x180017be1`
- `KERNEL32!HeapFree` at `0x180017bf6`
- `KERNEL32!HeapFree` at `0x180017c0b`
- `KERNEL32!HeapFree` at `0x180017c23`
- `KERNEL32!HeapFree` at `0x180017c3e`
- `KERNEL32!HeapFree` at `0x180017c59`
- `KERNEL32!HeapFree` at `0x180017c74`
- `KERNEL32!HeapFree` at `0x180017be1`
- `KERNEL32!HeapFree` at `0x180017bf6`
- `KERNEL32!HeapFree` at `0x180017c0b`
- `KERNEL32!HeapFree` at `0x180017c23`
- `KERNEL32!HeapFree` at `0x180017c3e`
- `KERNEL32!HeapFree` at `0x180017c59`
- `KERNEL32!HeapFree` at `0x180017c74`
- `ntdll!RtlLeaveCriticalSection` at `0x180017bc3`
- `ntdll!RtlLeaveCriticalSection` at `0x180017bc3`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1800178a5`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1800178a5`
- `ntdll!RtlEnterCriticalSection` at `0x180017651`
- `ntdll!RtlEnterCriticalSection` at `0x180017651`
- `ntdll!RtlFreeHeap` at `0x180017b33`
- `ntdll!RtlFreeHeap` at `0x180017b50`
- `ntdll!RtlFreeHeap` at `0x180017b33`
- `ntdll!RtlFreeHeap` at `0x180017b50`
- `ntdll!RtlAllocateHeap` at `0x180017612`
- `ntdll!RtlAllocateHeap` at `0x180017636`
- `ntdll!RtlAllocateHeap` at `0x180017612`
- `ntdll!RtlAllocateHeap` at `0x180017636`

## pseudocode

```c
void __fastcall AslTelemetryFlush(__int64 a1)
{
  int v2; // r14d
  PVOID v3; // r15
  PVOID v4; // rcx
  unsigned __int16 *Heap; // r13
  int v6; // edx
  __int64 v7; // r9
  unsigned __int64 v8; // r8
  unsigned int v9; // r12d
  int *v10; // rdi
  __int64 v11; // rax
  unsigned __int64 v12; // rcx
  const char *v13; // r14
  unsigned __int16 *v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // r8d
  unsigned int v17; // edx
  _BYTE *i; // rcx
  unsigned int v19; // r8d
  unsigned int v20; // edx
  _BYTE *j; // rcx
  unsigned __int16 *v22; // rsi
  _BYTE *v23; // rcx
  unsigned int v24; // r8d
  unsigned int k; // edx
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // kr00_8
  unsigned __int64 v28; // rcx
  unsigned int m; // esi
  __int64 v30; // rdi
  __int64 v31; // rax
  unsigned __int64 v32; // rcx
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // kr20_8
  ULONG BytesInUnicodeString; // [rsp+70h] [rbp-90h] BYREF
  const wchar_t *v36; // [rsp+78h] [rbp-88h] BYREF
  __int64 v37; // [rsp+80h] [rbp-80h] BYREF
  char *v38; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v39; // [rsp+90h] [rbp-70h] BYREF
  PVOID P; // [rsp+98h] [rbp-68h] BYREF
  int v41; // [rsp+A0h] [rbp-60h]
  char *v42; // [rsp+A8h] [rbp-58h] BYREF
  char *v43; // [rsp+B0h] [rbp-50h] BYREF
  char *v44; // [rsp+B8h] [rbp-48h] BYREF
  char *v45; // [rsp+C0h] [rbp-40h] BYREF
  char *v46; // [rsp+C8h] [rbp-38h] BYREF
  HANDLE hHeap; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v48; // [rsp+D8h] [rbp-28h]
  __int64 v49; // [rsp+E8h] [rbp-18h]
  LPVOID lpMem[2]; // [rsp+F0h] [rbp-10h]
  HANDLE v51; // [rsp+100h] [rbp+0h] BYREF
  __int128 v52; // [rsp+108h] [rbp+8h]
  __int64 v53; // [rsp+118h] [rbp+18h]
  LPVOID v54[2]; // [rsp+120h] [rbp+20h]
  HANDLE v55; // [rsp+130h] [rbp+30h] BYREF
  __int128 v56; // [rsp+138h] [rbp+38h]
  __int64 v57; // [rsp+148h] [rbp+48h]
  LPVOID v58[2]; // [rsp+150h] [rbp+50h]
  HANDLE v59; // [rsp+160h] [rbp+60h] BYREF
  __int128 v60; // [rsp+168h] [rbp+68h]
  __int64 v61; // [rsp+178h] [rbp+78h]
  LPVOID v62[2]; // [rsp+180h] [rbp+80h]
  HANDLE v63; // [rsp+190h] [rbp+90h] BYREF
  __int128 v64; // [rsp+198h] [rbp+98h]
  __int64 v65; // [rsp+1A8h] [rbp+A8h]
  LPVOID v66[2]; // [rsp+1B0h] [rbp+B0h]
  HANDLE v67; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v68; // [rsp+1C8h] [rbp+C8h]
  __int64 v69; // [rsp+1D8h] [rbp+D8h]
  LPVOID v70[2]; // [rsp+1E0h] [rbp+E0h]
  HANDLE ProcessHeap; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v72; // [rsp+1F8h] [rbp+F8h]
  __int64 v73; // [rsp+208h] [rbp+108h]
  LPVOID v74[2]; // [rsp+210h] [rbp+110h]
  char Buffer[16]; // [rsp+220h] [rbp+120h] BYREF

  if ( a1 )
  {
    v72 = 0;
    *(_OWORD *)v74 = 0;
    ProcessHeap = GetProcessHeap();
    v68 = 0;
    v73 = 4096;
    *(_OWORD *)v70 = 0;
    v69 = 4096;
    v67 = GetProcessHeap();
    v64 = 0;
    *(_OWORD *)v66 = 0;
    v65 = 4096;
    v63 = GetProcessHeap();
    v60 = 0;
    *(_OWORD *)v62 = 0;
    v61 = 4096;
    v59 = GetProcessHeap();
    v56 = 0;
    *(_OWORD *)v58 = 0;
    v57 = 4096;
    v55 = GetProcessHeap();
    v52 = 0;
    *(_OWORD *)v54 = 0;
    v53 = 4096;
    v51 = GetProcessHeap();
    v48 = 0;
    *(_OWORD *)lpMem = 0;
    BytesInUnicodeString = 0;
    v2 = 0;
    v49 = 4096;
    hHeap = GetProcessHeap();
    v3 = 0;
    P = 0;
    v4 = NtCurrentPeb()->ProcessHeap;
    v41 = 0;
    Heap = (unsigned __int16 *)RtlAllocateHeap(v4, 8u, 0x800u);
    if ( Heap )
    {
      v3 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x800u);
      if ( v3 )
      {
        BytesInUnicodeString = 0;
        RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 88));
        v2 = 1;
        v6 = dword_1800268EC;
        LODWORD(v38) = 1;
        ++dword_1800268EC;
        if ( !v6 && *(_QWORD *)(a1 + 144) && (int)PiiFilter::Initialize((PiiFilter *)&P) >= 0 )
        {
          v8 = *(_QWORD *)(a1 + 144);
          if ( v8 )
          {
            v9 = 0;
            while ( 1 )
            {
              v10 = 0;
              if ( v9 < v8 )
              {
                v37 = 0;
                v11 = *(_QWORD *)(a1 + 136) * v9;
                if ( !is_mul_ok(*(_QWORD *)(a1 + 136), v9)
                  || (v12 = *(_QWORD *)(a1 + 168), v10 = (int *)(v12 + v11), v12 + v11 < v12) )
                {
                  v10 = 0;
                }
              }
              v13 = (const char *)&dword_180021794;
              if ( v9 != v8 - 1 )
                v13 = ";";
              v14 = (unsigned __int16 *)&dword_18001D244;
              if ( v9 != v8 - 1 )
                v14 = L";";
              v15 = *v10;
              v39 = v14;
              if ( (int)RtlMemoryStream::WriteStringA((RtlMemoryStream *)&ProcessHeap, off_18001BC30[v15], v13) < 0 )
                break;
              v16 = *((unsigned __int16 *)v10 + 4);
              v17 = 0;
              for ( i = (_BYTE *)*((_QWORD *)v10 + 2); v17 < v16; ++v17 )
              {
                if ( (unsigned __int8)(*i - 32) > 0x5Eu || *i == 59 || *i == 34 )
                  *i = 95;
                ++i;
              }
              if ( (int)RtlMemoryStream::WriteStringA((RtlMemoryStream *)&v51, *((const char **)v10 + 2), v13) < 0 )
                break;
              v19 = *((unsigned __int16 *)v10 + 12);
              v20 = 0;
              for ( j = (_BYTE *)*((_QWORD *)v10 + 4); v20 < v19; ++v20 )
              {
                if ( (unsigned __int8)(*j - 32) > 0x5Eu || *j == 59 || *j == 34 )
                  *j = 95;
                ++j;
              }
              if ( (int)RtlMemoryStream::WriteStringA((RtlMemoryStream *)&v67, *((const char **)v10 + 4), v13) < 0
                || sprintf_s(Buffer, 0x10u, "%d", v10[17]) == -1
                || (int)RtlMemoryStream::WriteStringA((RtlMemoryStream *)&v63, Buffer, v13) < 0
                || sprintf_s(Buffer, 0x10u, "%d", v10[10]) == -1
                || (int)RtlMemoryStream::WriteStringA((RtlMemoryStream *)&v59, Buffer, v13) < 0 )
              {
                break;
              }
              v22 = (unsigned __int16 *)(v10 + 12);
              v23 = (_BYTE *)*((_QWORD *)v10 + 7);
              if ( !v23 )
                goto LABEL_48;
              v24 = *v22;
              for ( k = 0; k < v24; ++k )
              {
                if ( (unsigned __int8)(*v23 - 32) > 0x5Eu || *v23 == 59 || *v23 == 34 )
                  *v23 = 95;
                ++v23;
              }
              if ( (memset_0(v3, 0, 0x800u),
                    RtlMultiByteToUnicodeN((PWCH)v3, 0x800u, &BytesInUnicodeString, *((const CHAR **)v10 + 7), *v22) < 0)
                || BytesInUnicodeString >= 0x800
                || !v41 && (PiiFilter::Initialize((PiiFilter *)&P), !v41)
                || (int)PiiFilterEmbeddedPathsExecute(Heap, 0x400u, (unsigned __int64 *)P, (unsigned __int16 *)v3) < 0 )
              {
LABEL_48:
                *Heap = 0;
              }
              if ( (int)RtlMemoryStream::WriteString((RtlMemoryStream *)&v55, Heap, v39) < 0
                || sprintf_s(Buffer, 0x10u, "%d", v10[16]) == -1
                || (int)RtlMemoryStream::WriteStringA((RtlMemoryStream *)&hHeap, Buffer, v13) < 0 )
              {
                break;
              }
              AslAnsiStringFree(v10 + 2);
              AslAnsiStringFree(v10 + 6);
              AslAnsiStringFree(v10 + 12);
              v8 = *(_QWORD *)(a1 + 144);
              if ( ++v9 >= v8 )
              {
                v2 = (int)v38;
                goto LABEL_54;
              }
            }
            v2 = (int)v38;
          }
          else
          {
LABEL_54:
            if ( (unsigned int)dword_180026100 > 5
              && (qword_180026110 & 0x200000000000LL) != 0
              && (qword_180026118 & 0x200000000000LL) == qword_180026118 )
            {
              v39 = (unsigned __int16 *)lpMem[1];
              v36 = (const wchar_t *)v58[1];
              v38 = (char *)v62[1];
              v42 = (char *)v66[1];
              v43 = (char *)v70[1];
              v44 = (char *)v74[1];
              v45 = (char *)v54[1];
              *(_QWORD *)Buffer = *(_QWORD *)(a1 + 64);
              v46 = (char *)a1;
              v37 = 0x1000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
                qword_180026118,
                (unsigned __int8 *)byte_180022251,
                v8,
                v7,
                (__int64)&v37,
                (__int64)Buffer,
                &v46,
                &v45,
                &v44,
                &v43,
                &v42,
                &v38,
                &v36,
                (char **)&v39);
            }
            v26 = *(_QWORD *)(a1 + 144);
            if ( v26 )
            {
              v27 = *(_QWORD *)(a1 + 136);
              v37 = 0;
              if ( is_mul_ok(v26, v27) )
              {
                memset_0(*(void **)(a1 + 168), (v26 * (unsigned __int128)v27) >> 64, v26 * v27);
                *(_QWORD *)(a1 + 144) = 0;
              }
            }
          }
        }
      }
    }
    v28 = *(_QWORD *)(a1 + 144);
    if ( v28 )
    {
      for ( m = 0; m < v28; ++m )
      {
        v30 = 0;
        if ( m < v28 )
        {
          v31 = *(_QWORD *)(a1 + 136) * m;
          if ( !is_mul_ok(*(_QWORD *)(a1 + 136), m) || (v32 = *(_QWORD *)(a1 + 168), v30 = v32 + v31, v32 + v31 < v32) )
            v30 = 0;
        }
        AslAnsiStringFree(v30 + 8);
        AslAnsiStringFree(v30 + 24);
        AslAnsiStringFree(v30 + 48);
        v28 = *(_QWORD *)(a1 + 144);
      }
    }
    if ( Heap )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    if ( v3 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
    v33 = *(_QWORD *)(a1 + 144);
    if ( v33 )
    {
      v34 = *(_QWORD *)(a1 + 136);
      v37 = 0;
      if ( is_mul_ok(v33, v34) )
      {
        memset_0(*(void **)(a1 + 168), (v33 * (unsigned __int128)v34) >> 64, v33 * v34);
        *(_QWORD *)(a1 + 144) = 0;
      }
    }
    *(_QWORD *)(a1 + 224) = (((unsigned __int64)MEMORY[0x7FFE0004] << 32)
                           * (unsigned __int128)(unsigned __int64)(MEMORY[0x7FFE0320] << 8)) >> 64;
    if ( v2 )
    {
      --dword_1800268EC;
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 88));
    }
    PiiFilterDelete((HANDLE *)P);
    if ( lpMem[1] )
      HeapFree(hHeap, 0, lpMem[1]);
    if ( v54[1] )
      HeapFree(v51, 0, v54[1]);
    if ( v58[1] )
      HeapFree(v55, 0, v58[1]);
    if ( v62[1] )
      HeapFree(v59, 0, v62[1]);
    if ( v66[1] )
      HeapFree(v63, 0, v66[1]);
    if ( v70[1] )
      HeapFree(v67, 0, v70[1]);
    if ( v74[1] )
      HeapFree(ProcessHeap, 0, v74[1]);
  }
}

```

## disassembly

```asm
0x1800174a4  test    rcx, rcx
0x1800174a7  jz      locret_180017C9C
0x1800174ad  push    rbp
0x1800174ae  push    rbx
0x1800174af  push    rsi
0x1800174b0  push    rdi
0x1800174b1  push    r12
0x1800174b3  push    r13
0x1800174b5  push    r14
0x1800174b7  push    r15
0x1800174b9  lea     rbp, [rsp-148h]
0x1800174c1  sub     rsp, 248h
0x1800174c8  mov     rax, cs:__security_cookie
0x1800174cf  xor     rax, rsp
0x1800174d2  mov     [rbp+180h+var_50], rax
0x1800174d9  xorps   xmm0, xmm0
0x1800174dc  xorps   xmm1, xmm1
0x1800174df  movdqu  [rbp+180h+var_88], xmm0
0x1800174e7  mov     rbx, rcx
0x1800174ea  movdqu  xmmword ptr [rbp+180h+var_70], xmm1
0x1800174f2  call    cs:__imp_GetProcessHeap
0x1800174f8  xorps   xmm0, xmm0
0x1800174fb  xorps   xmm1, xmm1
0x1800174fe  mov     edi, 1000h
0x180017503  mov     [rbp+180h+var_90], rax
0x18001750a  movdqu  [rbp+180h+var_B8], xmm0
0x180017512  mov     [rbp+180h+var_78], rdi
0x180017519  movdqu  xmmword ptr [rbp+180h+var_A0], xmm1
0x180017521  call    cs:__imp_GetProcessHeap
0x180017527  xorps   xmm0, xmm0
0x18001752a  mov     [rbp+180h+var_A8], rdi
0x180017531  xorps   xmm1, xmm1
0x180017534  mov     [rbp+180h+var_C0], rax
0x18001753b  movdqu  [rbp+180h+var_E8], xmm0
0x180017543  movdqu  xmmword ptr [rbp+180h+var_D0], xmm1
0x18001754b  call    cs:__imp_GetProcessHeap
0x180017551  xorps   xmm0, xmm0
0x180017554  mov     [rbp+180h+var_D8], rdi
0x18001755b  xorps   xmm1, xmm1
0x18001755e  mov     [rbp+180h+var_F0], rax
0x180017565  movdqu  [rbp+180h+var_118], xmm0
0x18001756a  movdqu  xmmword ptr [rbp+180h+var_100], xmm1
0x180017572  call    cs:__imp_GetProcessHeap
0x180017578  xorps   xmm0, xmm0
0x18001757b  mov     [rbp+180h+var_108], rdi
0x18001757f  xorps   xmm1, xmm1
0x180017582  mov     [rbp+180h+var_120], rax
0x180017586  movdqu  [rbp+180h+var_148], xmm0
0x18001758b  movdqu  xmmword ptr [rbp+180h+var_130], xmm1
0x180017590  call    cs:__imp_GetProcessHeap
0x180017596  xorps   xmm0, xmm0
0x180017599  mov     [rbp+180h+var_138], rdi
0x18001759d  xorps   xmm1, xmm1
0x1800175a0  mov     [rbp+180h+var_150], rax
0x1800175a4  movdqu  [rbp+180h+var_178], xmm0
0x1800175a9  movdqu  xmmword ptr [rbp+180h+var_160], xmm1
0x1800175ae  call    cs:__imp_GetProcessHeap
0x1800175b4  xorps   xmm0, xmm0
0x1800175b7  mov     [rbp+180h+var_168], rdi
0x1800175bb  xorps   xmm1, xmm1
0x1800175be  mov     [rbp+180h+var_180], rax
0x1800175c2  movdqu  [rbp+180h+var_1A8], xmm0
0x1800175c7  movdqu  xmmword ptr [rbp+180h+lpMem], xmm1
0x1800175cc  call    cs:__imp_GetProcessHeap
0x1800175d2  mov     [rsp+280h+BytesInUnicodeString], 0
0x1800175da  xor     r14d, r14d
0x1800175dd  mov     rcx, gs:60h
0x1800175e6  mov     esi, 800h
0x1800175eb  mov     [rbp+180h+var_198], rdi
0x1800175ef  mov     r8d, esi; Size
0x1800175f2  mov     [rbp+180h+hHeap], rax
0x1800175f6  xor     r15d, r15d
0x1800175f9  lea     edi, [r14+8]
0x1800175fd  mov     [rbp+180h+P], 0
0x180017605  mov     rcx, [rcx+30h]; HeapHandle
0x180017609  mov     edx, edi; Flags
0x18001760b  mov     [rbp+180h+var_1E0], 0
0x180017612  call    cs:__imp_RtlAllocateHeap
0x180017618  mov     r13, rax
0x18001761b  test    rax, rax
0x18001761e  jz      loc_180017ABC
0x180017624  mov     rcx, gs:60h
0x18001762d  mov     r8d, esi; Size
0x180017630  mov     edx, edi; Flags
0x180017632  mov     rcx, [rcx+30h]; HeapHandle
0x180017636  call    cs:__imp_RtlAllocateHeap
0x18001763c  mov     r15, rax
0x18001763f  test    rax, rax
0x180017642  jz      loc_180017ABC
0x180017648  lea     rcx, [rbx+58h]; CriticalSection
0x18001764c  mov     [rsp+280h+BytesInUnicodeString], r14d
0x180017651  call    cs:__imp_RtlEnterCriticalSection
0x180017657  mov     ecx, cs:dword_1800268EC
0x18001765d  lea     r14d, [rdi-7]
0x180017661  mov     edx, ecx
0x180017663  mov     dword ptr [rbp+180h+var_1F8], r14d
0x180017667  inc     ecx
0x180017669  mov     cs:dword_1800268EC, ecx
0x18001766f  test    edx, edx
0x180017671  jnz     loc_180017ABC
0x180017677  cmp     qword ptr [rbx+90h], 0
0x18001767f  jz      loc_180017ABC
0x180017685  lea     rcx, [rbp+180h+P]; this
0x180017689  call    ?Initialize@PiiFilter@@QEAAJXZ; PiiFilter::Initialize(void)
0x18001768e  test    eax, eax
0x180017690  js      loc_180017ABC
0x180017696  mov     r8, [rbx+90h]
0x18001769d  test    r8, r8
0x1800176a0  jz      loc_18001797A
0x1800176a6  xor     r12d, r12d
0x1800176a9  mov     r9d, r12d
0x1800176ac  xor     edi, edi
0x1800176ae  cmp     r9, r8
0x1800176b1  jnb     short loc_1800176D8
0x1800176b3  mov     eax, r9d
0x1800176b6  mov     [rbp+180h+var_200], rdi
0x1800176ba  mul     qword ptr [rbx+88h]
0x1800176c1  test    rdx, rdx
0x1800176c4  jnz     short loc_1800176D6
0x1800176c6  mov     rcx, [rbx+0A8h]
0x1800176cd  lea     rdi, [rcx+rax]
0x1800176d1  cmp     rdi, rcx
0x1800176d4  jnb     short loc_1800176D8
0x1800176d6  xor     edi, edi
0x1800176d8  lea     rax, [r8-1]
0x1800176dc  cmp     r9, rax
0x1800176df  lea     rcx, asc_180021798; ";"
0x1800176e6  lea     rdx, asc_18002179C; ";"
0x1800176ed  lea     rax, off_18001BC30; "Simple"
0x1800176f4  lea     r14, dword_180021794
0x1800176fb  cmovnz  r14, rcx
0x1800176ff  lea     rcx, dword_18001D244
0x180017706  cmovnz  rcx, rdx
0x18001770a  mov     r8, r14; char *
0x18001770d  movsxd  rdx, dword ptr [rdi]
0x180017710  mov     [rbp+180h+var_1F0], rcx
0x180017714  lea     rcx, [rbp+180h+var_90]; this
0x18001771b  mov     rdx, [rax+rdx*8]; char *
0x18001771f  call    ?WriteStringA@RtlMemoryStream@@QEAAJPEBD0@Z; RtlMemoryStream::WriteStringA(char const *,char const *)
0x180017724  test    eax, eax
0x180017726  js      loc_180017C9D
0x18001772c  movzx   r8d, word ptr [rdi+8]
0x180017731  xor     edx, edx
0x180017733  mov     rcx, [rdi+10h]
0x180017737  test    r8d, r8d
0x18001773a  jz      short loc_18001775B
0x18001773c  mov     al, [rcx]
0x18001773e  sub     al, 20h ; ' '
0x180017740  cmp     al, 5Eh ; '^'
0x180017742  ja      short loc_18001774E
0x180017744  cmp     byte ptr [rcx], 3Bh ; ';'
0x180017747  jz      short loc_18001774E
0x180017749  cmp     byte ptr [rcx], 22h ; '"'
0x18001774c  jnz     short loc_180017751
0x18001774e  mov     byte ptr [rcx], 5Fh ; '_'
0x180017751  inc     rcx
0x180017754  inc     edx
0x180017756  cmp     edx, r8d
0x180017759  jb      short loc_18001773C
0x18001775b  mov     rdx, [rdi+10h]; char *
0x18001775f  lea     rcx, [rbp+180h+var_180]; this
0x180017763  mov     r8, r14; char *
0x180017766  call    ?WriteStringA@RtlMemoryStream@@QEAAJPEBD0@Z; RtlMemoryStream::WriteStringA(char const *,char const *)
0x18001776b  test    eax, eax
0x18001776d  js      loc_180017C9D
0x180017773  movzx   r8d, word ptr [rdi+18h]
0x180017778  xor     edx, edx
0x18001777a  mov     rcx, [rdi+20h]
0x18001777e  test    r8d, r8d
0x180017781  jz      short loc_1800177A2
0x180017783  mov     al, [rcx]
0x180017785  sub     al, 20h ; ' '
0x180017787  cmp     al, 5Eh ; '^'
0x180017789  ja      short loc_180017795
0x18001778b  cmp     byte ptr [rcx], 3Bh ; ';'
0x18001778e  jz      short loc_180017795
0x180017790  cmp     byte ptr [rcx], 22h ; '"'
0x180017793  jnz     short loc_180017798
0x180017795  mov     byte ptr [rcx], 5Fh ; '_'
0x180017798  inc     rcx
0x18001779b  inc     edx
0x18001779d  cmp     edx, r8d
0x1800177a0  jb      short loc_180017783
0x1800177a2  mov     rdx, [rdi+20h]; char *
0x1800177a6  lea     rcx, [rbp+180h+var_C0]; this
0x1800177ad  mov     r8, r14; char *
0x1800177b0  call    ?WriteStringA@RtlMemoryStream@@QEAAJPEBD0@Z; RtlMemoryStream::WriteStringA(char const *,char const *)
0x1800177b5  test    eax, eax
0x1800177b7  js      loc_180017C9D
0x1800177bd  mov     r9d, [rdi+44h]
0x1800177c1  lea     r8, aD; "%d"
0x1800177c8  mov     edx, 10h; BufferCount
0x1800177cd  lea     rcx, [rbp+180h+Buffer]; Buffer
0x1800177d4  call    cs:__imp_sprintf_s
0x1800177da  cmp     eax, 0FFFFFFFFh
0x1800177dd  jz      loc_180017C9D
0x1800177e3  mov     r8, r14; char *
0x1800177e6  lea     rdx, [rbp+180h+Buffer]; char *
0x1800177ed  lea     rcx, [rbp+180h+var_F0]; this
0x1800177f4  call    ?WriteStringA@RtlMemoryStream@@QEAAJPEBD0@Z; RtlMemoryStream::WriteStringA(char const *,char const *)
0x1800177f9  test    eax, eax
0x1800177fb  js      loc_180017C9D
0x180017801  mov     r9d, [rdi+28h]
0x180017805  lea     r8, aD; "%d"
0x18001780c  mov     edx, 10h; BufferCount
0x180017811  lea     rcx, [rbp+180h+Buffer]; Buffer
0x180017818  call    cs:__imp_sprintf_s
0x18001781e  cmp     eax, 0FFFFFFFFh
0x180017821  jz      loc_180017C9D
0x180017827  mov     r8, r14; char *
0x18001782a  lea     rdx, [rbp+180h+Buffer]; char *
0x180017831  lea     rcx, [rbp+180h+var_120]; this
0x180017835  call    ?WriteStringA@RtlMemoryStream@@QEAAJPEBD0@Z; RtlMemoryStream::WriteStringA(char const *,char const *)
0x18001783a  test    eax, eax
0x18001783c  js      loc_180017C9D
0x180017842  lea     rsi, [rdi+30h]
0x180017846  mov     rcx, [rsi+8]
0x18001784a  test    rcx, rcx
0x18001784d  jz      loc_1800178E6
0x180017853  movzx   r8d, word ptr [rsi]
0x180017857  xor     edx, edx
0x180017859  test    r8d, r8d
0x18001785c  jz      short loc_18001787D
0x18001785e  mov     al, [rcx]
0x180017860  sub     al, 20h ; ' '
0x180017862  cmp     al, 5Eh ; '^'
0x180017864  ja      short loc_180017870
0x180017866  cmp     byte ptr [rcx], 3Bh ; ';'
0x180017869  jz      short loc_180017870
0x18001786b  cmp     byte ptr [rcx], 22h ; '"'
0x18001786e  jnz     short loc_180017873
0x180017870  mov     byte ptr [rcx], 5Fh ; '_'
0x180017873  inc     rcx
0x180017876  inc     edx
0x180017878  cmp     edx, r8d
0x18001787b  jb      short loc_18001785E
0x18001787d  xor     edx, edx; Val
0x18001787f  mov     r8d, 800h; Size
0x180017885  mov     rcx, r15; void *
0x180017888  call    memset_0
0x18001788d  movzx   eax, word ptr [rsi]
0x180017890  lea     r8, [rsp+280h+BytesInUnicodeString]; BytesInUnicodeString
0x180017895  mov     r9, [rdi+38h]; MultiByteString
0x180017899  mov     edx, 800h; MaxBytesInUnicodeString
0x18001789e  mov     rcx, r15; UnicodeString
0x1800178a1  mov     [rsp+280h+BytesInMultiByteString], eax; BytesInMultiByteString
0x1800178a5  call    cs:__imp_RtlMultiByteToUnicodeN
0x1800178ab  test    eax, eax
0x1800178ad  js      short loc_1800178E6
0x1800178af  cmp     [rsp+280h+BytesInUnicodeString], 800h
0x1800178b7  jnb     short loc_1800178E6
0x1800178b9  cmp     [rbp+180h+var_1E0], 0
0x1800178bd  jnz     short loc_1800178CE
0x1800178bf  lea     rcx, [rbp+180h+P]; this
0x1800178c3  call    ?Initialize@PiiFilter@@QEAAJXZ; PiiFilter::Initialize(void)
0x1800178c8  cmp     [rbp+180h+var_1E0], 0
0x1800178cc  jz      short loc_1800178E6
0x1800178ce  mov     r8, [rbp+180h+P]
0x1800178d2  mov     r9, r15
0x1800178d5  mov     edx, 400h; unsigned __int64
0x1800178da  mov     rcx, r13; unsigned __int16 *
0x1800178dd  call    PiiFilterEmbeddedPathsExecute
0x1800178e2  test    eax, eax
0x1800178e4  jns     short loc_1800178ED
0x1800178e6  xor     eax, eax
0x1800178e8  mov     [r13+0], ax
0x1800178ed  mov     r8, [rbp+180h+var_1F0]; unsigned __int16 *
0x1800178f1  lea     rcx, [rbp+180h+var_150]; this
0x1800178f5  mov     rdx, r13; unsigned __int16 *
0x1800178f8  call    ?WriteString@RtlMemoryStream@@QEAAJPEBG0@Z; RtlMemoryStream::WriteString(ushort const *,ushort const *)
0x1800178fd  test    eax, eax
0x1800178ff  js      loc_180017C9D
0x180017905  mov     r9d, [rdi+40h]
0x180017909  lea     r8, aD; "%d"
0x180017910  mov     edx, 10h; BufferCount
0x180017915  lea     rcx, [rbp+180h+Buffer]; Buffer
0x18001791c  call    cs:__imp_sprintf_s
0x180017922  cmp     eax, 0FFFFFFFFh
0x180017925  jz      loc_180017C9D
0x18001792b  mov     r8, r14; char *
0x18001792e  lea     rdx, [rbp+180h+Buffer]; char *
0x180017935  lea     rcx, [rbp+180h+hHeap]; this
0x180017939  call    ?WriteStringA@RtlMemoryStream@@QEAAJPEBD0@Z; RtlMemoryStream::WriteStringA(char const *,char const *)
0x18001793e  test    eax, eax
0x180017940  js      loc_180017C9D
0x180017946  lea     rcx, [rdi+8]
0x18001794a  call    AslAnsiStringFree
0x18001794f  lea     rcx, [rdi+18h]
0x180017953  call    AslAnsiStringFree
0x180017958  mov     rcx, rsi
0x18001795b  call    AslAnsiStringFree
0x180017960  mov     r8, [rbx+90h]
0x180017967  inc     r12d
0x18001796a  mov     eax, r12d
0x18001796d  cmp     rax, r8
0x180017970  jb      loc_1800176A9
0x180017976  mov     r14d, dword ptr [rbp+180h+var_1F8]
0x18001797a  mov     eax, cs:dword_180026100
0x180017980  cmp     eax, 5
0x180017983  jbe     loc_180017A7F
  ... truncated ...
```
