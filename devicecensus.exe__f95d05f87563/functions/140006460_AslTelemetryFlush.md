# AslTelemetryFlush

- ea: `0x140006460`
- end: `0x140006cab`
- name: `AslTelemetryFlush`
- size: `2123`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x140006308`
- `0x140006cb4`
- `0x1400119a0`

## callees

- `0x140001008`
- `0x14000233f`
- `0x140005b3c`
- `0x140005c70`
- `0x140005e9c`
- `0x140006460`
- `0x1400085f4`
- `0x140008f48`
- `0x140009648`
- `0x1400115f0`

## import_xrefs

- `msvcrt!sprintf_s` at `0x1400067a3`
- `msvcrt!sprintf_s` at `0x1400067e7`
- `msvcrt!sprintf_s` at `0x1400068ee`
- `msvcrt!sprintf_s` at `0x1400067a3`
- `msvcrt!sprintf_s` at `0x1400067e7`
- `msvcrt!sprintf_s` at `0x1400068ee`
- `ntdll!RtlMultiByteToUnicodeN` at `0x140006875`
- `ntdll!RtlMultiByteToUnicodeN` at `0x140006875`
- `ntdll!RtlLeaveCriticalSection` at `0x140006b9a`
- `ntdll!RtlLeaveCriticalSection` at `0x140006b9a`
- `ntdll!RtlFreeHeap` at `0x140006b0a`
- `ntdll!RtlFreeHeap` at `0x140006b27`
- `ntdll!RtlFreeHeap` at `0x140006bcc`
- `ntdll!RtlFreeHeap` at `0x140006be1`
- `ntdll!RtlFreeHeap` at `0x140006bf6`
- `ntdll!RtlFreeHeap` at `0x140006c0b`
- `ntdll!RtlFreeHeap` at `0x140006c23`
- `ntdll!RtlFreeHeap` at `0x140006c3e`
- `ntdll!RtlFreeHeap` at `0x140006c59`
- `ntdll!RtlFreeHeap` at `0x140006c74`
- `ntdll!RtlFreeHeap` at `0x140006b0a`
- `ntdll!RtlFreeHeap` at `0x140006b27`
- `ntdll!RtlFreeHeap` at `0x140006bcc`
- `ntdll!RtlFreeHeap` at `0x140006be1`
- `ntdll!RtlFreeHeap` at `0x140006bf6`
- `ntdll!RtlFreeHeap` at `0x140006c0b`
- `ntdll!RtlFreeHeap` at `0x140006c23`
- `ntdll!RtlFreeHeap` at `0x140006c3e`
- `ntdll!RtlFreeHeap` at `0x140006c59`
- `ntdll!RtlFreeHeap` at `0x140006c74`
- `ntdll!RtlEnterCriticalSection` at `0x140006620`
- `ntdll!RtlEnterCriticalSection` at `0x140006620`
- `ntdll!RtlAllocateHeap` at `0x1400065dc`
- `ntdll!RtlAllocateHeap` at `0x140006605`
- `ntdll!RtlAllocateHeap` at `0x1400065dc`
- `ntdll!RtlAllocateHeap` at `0x140006605`

## pseudocode

```c
void __fastcall AslTelemetryFlush(__int64 a1)
{
  int v2; // r12d
  PVOID v3; // r15
  PVOID v4; // rcx
  unsigned __int16 *v5; // r14
  int v6; // edx
  __int64 v7; // r9
  unsigned __int64 v8; // r8
  unsigned int v9; // r12d
  int *v10; // rdi
  __int64 v11; // rax
  unsigned __int64 v12; // rcx
  const char *v13; // rsi
  unsigned __int16 *v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // r8d
  unsigned int v17; // edx
  _BYTE *i; // rcx
  unsigned int v19; // r8d
  unsigned int v20; // edx
  _BYTE *j; // rcx
  unsigned __int16 *v22; // r14
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
  char *v35; // rbx
  ULONG BytesInUnicodeString; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *Heap; // [rsp+78h] [rbp-88h] BYREF
  __int64 v38; // [rsp+80h] [rbp-80h] BYREF
  PVOID v39; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v40; // [rsp+90h] [rbp-70h] BYREF
  PVOID P; // [rsp+98h] [rbp-68h] BYREF
  int v42; // [rsp+A0h] [rbp-60h]
  PVOID v43; // [rsp+A8h] [rbp-58h] BYREF
  PVOID v44; // [rsp+B0h] [rbp-50h] BYREF
  PVOID v45; // [rsp+B8h] [rbp-48h] BYREF
  PVOID v46; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v47; // [rsp+C8h] [rbp-38h] BYREF
  HANDLE HeapHandle; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v49; // [rsp+D8h] [rbp-28h]
  __int64 v50; // [rsp+E8h] [rbp-18h]
  PVOID v51[2]; // [rsp+F0h] [rbp-10h]
  HANDLE v52; // [rsp+100h] [rbp+0h] BYREF
  __int128 v53; // [rsp+108h] [rbp+8h]
  __int64 v54; // [rsp+118h] [rbp+18h]
  PVOID v55[2]; // [rsp+120h] [rbp+20h]
  HANDLE v56; // [rsp+130h] [rbp+30h] BYREF
  __int128 v57; // [rsp+138h] [rbp+38h]
  __int64 v58; // [rsp+148h] [rbp+48h]
  PVOID v59[2]; // [rsp+150h] [rbp+50h]
  HANDLE v60; // [rsp+160h] [rbp+60h] BYREF
  __int128 v61; // [rsp+168h] [rbp+68h]
  __int64 v62; // [rsp+178h] [rbp+78h]
  PVOID v63[2]; // [rsp+180h] [rbp+80h]
  HANDLE v64; // [rsp+190h] [rbp+90h] BYREF
  __int128 v65; // [rsp+198h] [rbp+98h]
  __int64 v66; // [rsp+1A8h] [rbp+A8h]
  PVOID v67[2]; // [rsp+1B0h] [rbp+B0h]
  HANDLE v68; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v69; // [rsp+1C8h] [rbp+C8h]
  __int64 v70; // [rsp+1D8h] [rbp+D8h]
  PVOID v71[2]; // [rsp+1E0h] [rbp+E0h]
  HANDLE ProcessHeap; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v73; // [rsp+1F8h] [rbp+F8h]
  __int64 v74; // [rsp+208h] [rbp+108h]
  PVOID v75[2]; // [rsp+210h] [rbp+110h]
  char Buffer[16]; // [rsp+220h] [rbp+120h] BYREF

  if ( a1 )
  {
    P = 0;
    v74 = 4096;
    v70 = 4096;
    v2 = 0;
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
    v66 = 4096;
    v3 = 0;
    v62 = 4096;
    v68 = NtCurrentPeb()->ProcessHeap;
    v58 = 4096;
    v54 = 4096;
    v64 = NtCurrentPeb()->ProcessHeap;
    v50 = 4096;
    v73 = 0;
    v60 = NtCurrentPeb()->ProcessHeap;
    *(_OWORD *)v75 = 0;
    v42 = 0;
    v56 = NtCurrentPeb()->ProcessHeap;
    v69 = 0;
    v52 = NtCurrentPeb()->ProcessHeap;
    *(_OWORD *)v71 = 0;
    HeapHandle = NtCurrentPeb()->ProcessHeap;
    BytesInUnicodeString = 0;
    v65 = 0;
    *(_OWORD *)v67 = 0;
    v4 = NtCurrentPeb()->ProcessHeap;
    v61 = 0;
    *(_OWORD *)v63 = 0;
    v57 = 0;
    *(_OWORD *)v59 = 0;
    v53 = 0;
    *(_OWORD *)v55 = 0;
    v49 = 0;
    *(_OWORD *)v51 = 0;
    Heap = (unsigned __int16 *)RtlAllocateHeap(v4, 8u, 0x800u);
    v5 = Heap;
    if ( Heap )
    {
      v3 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x800u);
      if ( v3 )
      {
        BytesInUnicodeString = 0;
        RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 88));
        v2 = 1;
        v6 = dword_14001C90C;
        LODWORD(v39) = 1;
        ++dword_14001C90C;
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
                v38 = 0;
                v11 = *(_QWORD *)(a1 + 136) * v9;
                if ( !is_mul_ok(*(_QWORD *)(a1 + 136), v9)
                  || (v12 = *(_QWORD *)(a1 + 168), v10 = (int *)(v12 + v11), v12 + v11 < v12) )
                {
                  v10 = 0;
                }
              }
              v13 = (const char *)&dword_140015D74;
              if ( v9 != v8 - 1 )
                v13 = ";";
              v14 = (unsigned __int16 *)&dword_140015D7C;
              if ( v9 != v8 - 1 )
                v14 = L";";
              v15 = *v10;
              v40 = v14;
              if ( (int)RtlMemoryStream::WriteStringA((RtlMemoryStream *)&ProcessHeap, off_140013AF0[v15], v13) < 0 )
                break;
              v16 = *((unsigned __int16 *)v10 + 4);
              v17 = 0;
              for ( i = (_BYTE *)*((_QWORD *)v10 + 2); v17 < v16; ++v17 )
              {
                if ( (unsigned __int8)(*i - 32) > 0x5Eu || *i == 59 || *i == 34 )
                  *i = 95;
                ++i;
              }
              if ( (int)RtlMemoryStream::WriteStringA((RtlMemoryStream *)&v52, *((const char **)v10 + 2), v13) < 0 )
                break;
              v19 = *((unsigned __int16 *)v10 + 12);
              v20 = 0;
              for ( j = (_BYTE *)*((_QWORD *)v10 + 4); v20 < v19; ++v20 )
              {
                if ( (unsigned __int8)(*j - 32) > 0x5Eu || *j == 59 || *j == 34 )
                  *j = 95;
                ++j;
              }
              if ( (int)RtlMemoryStream::WriteStringA((RtlMemoryStream *)&v68, *((const char **)v10 + 4), v13) < 0
                || sprintf_s(Buffer, 0x10u, "%d", v10[17]) == -1
                || (int)RtlMemoryStream::WriteStringA((RtlMemoryStream *)&v64, Buffer, v13) < 0
                || sprintf_s(Buffer, 0x10u, "%d", v10[10]) == -1
                || (int)RtlMemoryStream::WriteStringA((RtlMemoryStream *)&v60, Buffer, v13) < 0 )
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
                || !v42 && (PiiFilter::Initialize((PiiFilter *)&P), !v42)
                || (int)PiiFilterEmbeddedPathsExecute(Heap) < 0 )
              {
LABEL_48:
                *Heap = 0;
              }
              if ( (int)RtlMemoryStream::WriteString((RtlMemoryStream *)&v56, Heap, v40) < 0
                || sprintf_s(Buffer, 0x10u, "%d", v10[16]) == -1
                || (int)RtlMemoryStream::WriteStringA((RtlMemoryStream *)&HeapHandle, Buffer, v13) < 0 )
              {
                break;
              }
              AslAnsiStringFree((__int64)(v10 + 2));
              AslAnsiStringFree((__int64)(v10 + 6));
              AslAnsiStringFree((__int64)(v10 + 12));
              v8 = *(_QWORD *)(a1 + 144);
              if ( ++v9 >= v8 )
              {
                v5 = Heap;
                v2 = (int)v39;
                goto LABEL_54;
              }
            }
            v5 = Heap;
            v2 = (int)v39;
          }
          else
          {
LABEL_54:
            if ( (unsigned int)dword_14001C000 > 5
              && (qword_14001C010 & 0x200000000000LL) != 0
              && (qword_14001C018 & 0x200000000000LL) == qword_14001C018 )
            {
              v40 = (unsigned __int16 *)v51[1];
              Heap = (unsigned __int16 *)v59[1];
              v39 = v63[1];
              v43 = v67[1];
              v44 = v71[1];
              v45 = v75[1];
              v46 = v55[1];
              *(_QWORD *)Buffer = *(_QWORD *)(a1 + 64);
              v47 = a1;
              v38 = 0x1000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
                qword_14001C018,
                (__int64)byte_140018DC9,
                v8,
                v7,
                (__int64)&v38,
                (__int64)Buffer,
                &v47,
                &v46,
                &v45,
                &v44,
                &v43,
                &v39,
                &Heap,
                &v40);
            }
            v26 = *(_QWORD *)(a1 + 144);
            if ( v26 )
            {
              v27 = *(_QWORD *)(a1 + 136);
              v38 = 0;
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
    if ( v5 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
    if ( v3 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
    v33 = *(_QWORD *)(a1 + 144);
    if ( v33 )
    {
      v34 = *(_QWORD *)(a1 + 136);
      v38 = 0;
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
      --dword_14001C90C;
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 88));
    }
    v35 = (char *)P;
    if ( P )
    {
      RtlNameValueArray::Free((RtlNameValueArray *)P);
      RtlNameValueArray::Free((RtlNameValueArray *)(v35 + 48));
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v35);
    }
    if ( v51[1] )
      RtlFreeHeap(HeapHandle, 0, v51[1]);
    if ( v55[1] )
      RtlFreeHeap(v52, 0, v55[1]);
    if ( v59[1] )
      RtlFreeHeap(v56, 0, v59[1]);
    if ( v63[1] )
      RtlFreeHeap(v60, 0, v63[1]);
    if ( v67[1] )
      RtlFreeHeap(v64, 0, v67[1]);
    if ( v71[1] )
      RtlFreeHeap(v68, 0, v71[1]);
    if ( v75[1] )
      RtlFreeHeap(ProcessHeap, 0, v75[1]);
  }
}

```

## disassembly

```asm
0x140006460  test    rcx, rcx
0x140006463  jz      locret_140006C9C
0x140006469  push    rbp
0x14000646a  push    rbx
0x14000646b  push    rsi
0x14000646c  push    rdi
0x14000646d  push    r12
0x14000646f  push    r13
0x140006471  push    r14
0x140006473  push    r15
0x140006475  lea     rbp, [rsp-148h]
0x14000647d  sub     rsp, 248h
0x140006484  mov     rax, cs:__security_cookie
0x14000648b  xor     rax, rsp
0x14000648e  mov     [rbp+180h+var_50], rax
0x140006495  mov     rax, gs:60h
0x14000649e  mov     rbx, rcx
0x1400064a1  mov     edx, 1000h
0x1400064a6  mov     [rbp+180h+P], 0
0x1400064ae  xorps   xmm0, xmm0
0x1400064b1  mov     [rbp+180h+var_78], rdx
0x1400064b8  xorps   xmm1, xmm1
0x1400064bb  mov     [rbp+180h+var_A8], rdx
0x1400064c2  mov     rcx, [rax+30h]
0x1400064c6  xor     r12d, r12d
0x1400064c9  mov     rax, gs:60h
0x1400064d2  mov     esi, 800h
0x1400064d7  mov     [rbp+180h+var_90], rcx
0x1400064de  mov     r8d, esi; Size
0x1400064e1  mov     [rbp+180h+var_D8], rdx
0x1400064e8  xor     r15d, r15d
0x1400064eb  mov     [rbp+180h+var_108], rdx
0x1400064ef  lea     edi, [r12+8]
0x1400064f4  mov     rcx, [rax+30h]
0x1400064f8  mov     rax, gs:60h
0x140006501  mov     [rbp+180h+var_C0], rcx
0x140006508  mov     [rbp+180h+var_138], rdx
0x14000650c  mov     [rbp+180h+var_168], rdx
0x140006510  mov     rcx, [rax+30h]
0x140006514  mov     rax, gs:60h
0x14000651d  mov     [rbp+180h+var_F0], rcx
0x140006524  mov     [rbp+180h+var_198], rdx
0x140006528  mov     edx, edi; Flags
0x14000652a  movdqu  [rbp+180h+var_88], xmm0
0x140006532  mov     rcx, [rax+30h]
0x140006536  mov     rax, gs:60h
0x14000653f  mov     [rbp+180h+var_120], rcx
0x140006543  movdqu  xmmword ptr [rbp+180h+var_70], xmm1
0x14000654b  mov     [rbp+180h+var_1E0], 0
0x140006552  mov     rcx, [rax+30h]
0x140006556  mov     rax, gs:60h
0x14000655f  mov     [rbp+180h+var_150], rcx
0x140006563  movdqu  [rbp+180h+var_B8], xmm0
0x14000656b  mov     rcx, [rax+30h]
0x14000656f  mov     rax, gs:60h
0x140006578  mov     [rbp+180h+var_180], rcx
0x14000657c  movdqu  xmmword ptr [rbp+180h+var_A0], xmm1
0x140006584  mov     rcx, [rax+30h]
0x140006588  mov     [rbp+180h+HeapHandle], rcx
0x14000658c  mov     [rsp+280h+BytesInUnicodeString], 0
0x140006594  mov     rcx, gs:60h
0x14000659d  movdqu  [rbp+180h+var_E8], xmm0
0x1400065a5  movdqu  xmmword ptr [rbp+180h+var_D0], xmm1
0x1400065ad  mov     rcx, [rcx+30h]; HeapHandle
0x1400065b1  movdqu  [rbp+180h+var_118], xmm0
0x1400065b6  movdqu  xmmword ptr [rbp+180h+var_100], xmm1
0x1400065be  movdqu  [rbp+180h+var_148], xmm0
0x1400065c3  movdqu  xmmword ptr [rbp+180h+var_130], xmm1
0x1400065c8  movdqu  [rbp+180h+var_178], xmm0
0x1400065cd  movdqu  xmmword ptr [rbp+180h+var_160], xmm1
0x1400065d2  movdqu  [rbp+180h+var_1A8], xmm0
0x1400065d7  movdqu  xmmword ptr [rbp+180h+var_190], xmm1
0x1400065dc  call    cs:__imp_RtlAllocateHeap
0x1400065e2  mov     [rsp+280h+var_208], rax
0x1400065e7  mov     r14, rax
0x1400065ea  test    rax, rax
0x1400065ed  jz      loc_140006A93
0x1400065f3  mov     rcx, gs:60h
0x1400065fc  mov     r8d, esi; Size
0x1400065ff  mov     edx, edi; Flags
0x140006601  mov     rcx, [rcx+30h]; HeapHandle
0x140006605  call    cs:__imp_RtlAllocateHeap
0x14000660b  mov     r15, rax
0x14000660e  test    rax, rax
0x140006611  jz      loc_140006A93
0x140006617  lea     rcx, [rbx+58h]; CriticalSection
0x14000661b  mov     [rsp+280h+BytesInUnicodeString], r12d
0x140006620  call    cs:__imp_RtlEnterCriticalSection
0x140006626  mov     ecx, cs:dword_14001C90C
0x14000662c  lea     r12d, [rdi-7]
0x140006630  mov     edx, ecx
0x140006632  mov     dword ptr [rbp+180h+var_1F8], r12d
0x140006636  inc     ecx
0x140006638  mov     cs:dword_14001C90C, ecx
0x14000663e  test    edx, edx
0x140006640  jnz     loc_140006A93
0x140006646  cmp     qword ptr [rbx+90h], 0
0x14000664e  jz      loc_140006A93
0x140006654  lea     rcx, [rbp+180h+P]; this
0x140006658  call    ?Initialize@PiiFilter@@QEAAJXZ; PiiFilter::Initialize(void)
0x14000665d  test    eax, eax
0x14000665f  js      loc_140006A93
0x140006665  mov     r8, [rbx+90h]
0x14000666c  test    r8, r8
0x14000666f  jz      loc_140006951
0x140006675  xor     r12d, r12d
0x140006678  mov     r9d, r12d
0x14000667b  xor     edi, edi
0x14000667d  cmp     r9, r8
0x140006680  jnb     short loc_1400066A7
0x140006682  mov     eax, r9d
0x140006685  mov     [rbp+180h+var_200], rdi
0x140006689  mul     qword ptr [rbx+88h]
0x140006690  test    rdx, rdx
0x140006693  jnz     short loc_1400066A5
0x140006695  mov     rcx, [rbx+0A8h]
0x14000669c  lea     rdi, [rcx+rax]
0x1400066a0  cmp     rdi, rcx
0x1400066a3  jnb     short loc_1400066A7
0x1400066a5  xor     edi, edi
0x1400066a7  lea     rax, [r8-1]
0x1400066ab  cmp     r9, rax
0x1400066ae  lea     rcx, asc_140015D78; ";"
0x1400066b5  lea     rdx, Delimiter; ";"
0x1400066bc  lea     rax, off_140013AF0; "Simple"
0x1400066c3  lea     rsi, dword_140015D74
0x1400066ca  cmovnz  rsi, rcx
0x1400066ce  lea     rcx, dword_140015D7C
0x1400066d5  cmovnz  rcx, rdx
0x1400066d9  mov     r8, rsi; char *
0x1400066dc  movsxd  rdx, dword ptr [rdi]
0x1400066df  mov     [rbp+180h+var_1F0], rcx
0x1400066e3  lea     rcx, [rbp+180h+var_90]; this
0x1400066ea  mov     rdx, [rax+rdx*8]; char *
0x1400066ee  call    ?WriteStringA@RtlMemoryStream@@QEAAJPEBD0@Z; RtlMemoryStream::WriteStringA(char const *,char const *)
0x1400066f3  test    eax, eax
0x1400066f5  js      loc_140006C9D
0x1400066fb  movzx   r8d, word ptr [rdi+8]
0x140006700  xor     edx, edx
0x140006702  mov     rcx, [rdi+10h]
0x140006706  test    r8d, r8d
0x140006709  jz      short loc_14000672A
0x14000670b  mov     al, [rcx]
0x14000670d  sub     al, 20h ; ' '
0x14000670f  cmp     al, 5Eh ; '^'
0x140006711  ja      short loc_14000671D
0x140006713  cmp     byte ptr [rcx], 3Bh ; ';'
0x140006716  jz      short loc_14000671D
0x140006718  cmp     byte ptr [rcx], 22h ; '"'
0x14000671b  jnz     short loc_140006720
0x14000671d  mov     byte ptr [rcx], 5Fh ; '_'
0x140006720  inc     rcx
0x140006723  inc     edx
0x140006725  cmp     edx, r8d
0x140006728  jb      short loc_14000670B
0x14000672a  mov     rdx, [rdi+10h]; char *
0x14000672e  lea     rcx, [rbp+180h+var_180]; this
0x140006732  mov     r8, rsi; char *
0x140006735  call    ?WriteStringA@RtlMemoryStream@@QEAAJPEBD0@Z; RtlMemoryStream::WriteStringA(char const *,char const *)
0x14000673a  test    eax, eax
0x14000673c  js      loc_140006C9D
0x140006742  movzx   r8d, word ptr [rdi+18h]
0x140006747  xor     edx, edx
0x140006749  mov     rcx, [rdi+20h]
0x14000674d  test    r8d, r8d
0x140006750  jz      short loc_140006771
0x140006752  mov     al, [rcx]
0x140006754  sub     al, 20h ; ' '
0x140006756  cmp     al, 5Eh ; '^'
0x140006758  ja      short loc_140006764
0x14000675a  cmp     byte ptr [rcx], 3Bh ; ';'
0x14000675d  jz      short loc_140006764
0x14000675f  cmp     byte ptr [rcx], 22h ; '"'
0x140006762  jnz     short loc_140006767
0x140006764  mov     byte ptr [rcx], 5Fh ; '_'
0x140006767  inc     rcx
0x14000676a  inc     edx
0x14000676c  cmp     edx, r8d
0x14000676f  jb      short loc_140006752
0x140006771  mov     rdx, [rdi+20h]; char *
0x140006775  lea     rcx, [rbp+180h+var_C0]; this
0x14000677c  mov     r8, rsi; char *
0x14000677f  call    ?WriteStringA@RtlMemoryStream@@QEAAJPEBD0@Z; RtlMemoryStream::WriteStringA(char const *,char const *)
0x140006784  test    eax, eax
0x140006786  js      loc_140006C9D
0x14000678c  mov     r9d, [rdi+44h]
0x140006790  lea     r8, aD; "%d"
0x140006797  mov     edx, 10h; BufferCount
0x14000679c  lea     rcx, [rbp+180h+Buffer]; Buffer
0x1400067a3  call    cs:__imp_sprintf_s
0x1400067a9  cmp     eax, 0FFFFFFFFh
0x1400067ac  jz      loc_140006C9D
0x1400067b2  mov     r8, rsi; char *
0x1400067b5  lea     rdx, [rbp+180h+Buffer]; char *
0x1400067bc  lea     rcx, [rbp+180h+var_F0]; this
0x1400067c3  call    ?WriteStringA@RtlMemoryStream@@QEAAJPEBD0@Z; RtlMemoryStream::WriteStringA(char const *,char const *)
0x1400067c8  test    eax, eax
0x1400067ca  js      loc_140006C9D
0x1400067d0  mov     r9d, [rdi+28h]
0x1400067d4  lea     r8, aD; "%d"
0x1400067db  mov     edx, 10h; BufferCount
0x1400067e0  lea     rcx, [rbp+180h+Buffer]; Buffer
0x1400067e7  call    cs:__imp_sprintf_s
0x1400067ed  cmp     eax, 0FFFFFFFFh
0x1400067f0  jz      loc_140006C9D
0x1400067f6  mov     r8, rsi; char *
0x1400067f9  lea     rdx, [rbp+180h+Buffer]; char *
0x140006800  lea     rcx, [rbp+180h+var_120]; this
0x140006804  call    ?WriteStringA@RtlMemoryStream@@QEAAJPEBD0@Z; RtlMemoryStream::WriteStringA(char const *,char const *)
0x140006809  test    eax, eax
0x14000680b  js      loc_140006C9D
0x140006811  lea     r14, [rdi+30h]
0x140006815  mov     rcx, [r14+8]
0x140006819  test    rcx, rcx
0x14000681c  jz      loc_1400068B3
0x140006822  movzx   r8d, word ptr [r14]
0x140006826  xor     edx, edx
0x140006828  test    r8d, r8d
0x14000682b  jz      short loc_14000684C
0x14000682d  mov     al, [rcx]
0x14000682f  sub     al, 20h ; ' '
0x140006831  cmp     al, 5Eh ; '^'
0x140006833  ja      short loc_14000683F
0x140006835  cmp     byte ptr [rcx], 3Bh ; ';'
0x140006838  jz      short loc_14000683F
0x14000683a  cmp     byte ptr [rcx], 22h ; '"'
0x14000683d  jnz     short loc_140006842
0x14000683f  mov     byte ptr [rcx], 5Fh ; '_'
0x140006842  inc     rcx
0x140006845  inc     edx
0x140006847  cmp     edx, r8d
0x14000684a  jb      short loc_14000682D
0x14000684c  xor     edx, edx; Val
0x14000684e  mov     r8d, 800h; Size
0x140006854  mov     rcx, r15; void *
0x140006857  call    memset_0
0x14000685c  movzx   eax, word ptr [r14]
0x140006860  lea     r8, [rsp+280h+BytesInUnicodeString]; BytesInUnicodeString
0x140006865  mov     r9, [rdi+38h]; MultiByteString
0x140006869  mov     edx, 800h; MaxBytesInUnicodeString
0x14000686e  mov     rcx, r15; UnicodeString
0x140006871  mov     [rsp+280h+BytesInMultiByteString], eax; BytesInMultiByteString
0x140006875  call    cs:__imp_RtlMultiByteToUnicodeN
0x14000687b  test    eax, eax
0x14000687d  js      short loc_1400068B3
0x14000687f  cmp     [rsp+280h+BytesInUnicodeString], 800h
0x140006887  jnb     short loc_1400068B3
0x140006889  cmp     [rbp+180h+var_1E0], 0
0x14000688d  jnz     short loc_14000689E
0x14000688f  lea     rcx, [rbp+180h+P]; this
0x140006893  call    ?Initialize@PiiFilter@@QEAAJXZ; PiiFilter::Initialize(void)
0x140006898  cmp     [rbp+180h+var_1E0], 0
0x14000689c  jz      short loc_1400068B3
0x14000689e  mov     r8, [rbp+180h+P]
0x1400068a2  mov     r9, r15
0x1400068a5  mov     rcx, [rsp+280h+var_208]; unsigned __int16 *
0x1400068aa  call    PiiFilterEmbeddedPathsExecute
0x1400068af  test    eax, eax
0x1400068b1  jns     short loc_1400068BD
0x1400068b3  mov     rcx, [rsp+280h+var_208]
0x1400068b8  xor     eax, eax
0x1400068ba  mov     [rcx], ax
0x1400068bd  mov     r8, [rbp+180h+var_1F0]; unsigned __int16 *
0x1400068c1  lea     rcx, [rbp+180h+var_150]; this
0x1400068c5  mov     rdx, [rsp+280h+var_208]; unsigned __int16 *
0x1400068ca  call    ?WriteString@RtlMemoryStream@@QEAAJPEBG0@Z; RtlMemoryStream::WriteString(ushort const *,ushort const *)
0x1400068cf  test    eax, eax
0x1400068d1  js      loc_140006C9D
0x1400068d7  mov     r9d, [rdi+40h]
0x1400068db  lea     r8, aD; "%d"
0x1400068e2  mov     edx, 10h; BufferCount
0x1400068e7  lea     rcx, [rbp+180h+Buffer]; Buffer
0x1400068ee  call    cs:__imp_sprintf_s
0x1400068f4  cmp     eax, 0FFFFFFFFh
0x1400068f7  jz      loc_140006C9D
0x1400068fd  mov     r8, rsi; char *
0x140006900  lea     rdx, [rbp+180h+Buffer]; char *
0x140006907  lea     rcx, [rbp+180h+HeapHandle]; this
0x14000690b  call    ?WriteStringA@RtlMemoryStream@@QEAAJPEBD0@Z; RtlMemoryStream::WriteStringA(char const *,char const *)
0x140006910  test    eax, eax
0x140006912  js      loc_140006C9D
0x140006918  lea     rcx, [rdi+8]
0x14000691c  call    AslAnsiStringFree
0x140006921  lea     rcx, [rdi+18h]
0x140006925  call    AslAnsiStringFree
0x14000692a  mov     rcx, r14
0x14000692d  call    AslAnsiStringFree
0x140006932  mov     r8, [rbx+90h]
0x140006939  inc     r12d
0x14000693c  mov     eax, r12d
0x14000693f  cmp     rax, r8
0x140006942  jb      loc_140006678
0x140006948  mov     r14, [rsp+280h+var_208]
0x14000694d  mov     r12d, dword ptr [rbp+180h+var_1F8]
0x140006951  mov     eax, cs:dword_14001C000
0x140006957  cmp     eax, 5
0x14000695a  jbe     loc_140006A56
0x140006960  mov     rcx, cs:qword_14001C018
0x140006967  mov     rdx, 200000000000h
0x140006971  mov     rax, cs:qword_14001C010
  ... truncated ...
```
