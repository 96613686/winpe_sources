# HPerformanceCounterDataCollector::AddCounter(ushort *)

- ea: `0x18008e6f4`
- end: `0x18008e989`
- name: `?AddCounter@HPerformanceCounterDataCollector@@IEAAJPEAG@Z`
- size: `661`
- prototype: `__int64 __fastcall(HPerformanceCounterDataCollector *this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800fe570`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x18008e6f4`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008e7c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008e7c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008e760`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008e7ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008e760`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008e7ad`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18008e76e`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x18008e76e`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18008e7d1`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18008e7d1`
- `pdh!PdhAddCounterW` at `0x18008e833`
- `pdh!PdhAddCounterW` at `0x18008e876`
- `pdh!PdhAddCounterW` at `0x18008e833`
- `pdh!PdhAddCounterW` at `0x18008e876`
- `pdh!PdhExpandWildCardPathW` at `0x18008e790`
- `pdh!PdhExpandWildCardPathW` at `0x18008e790`

## pseudocode

```c
__int64 __fastcall HPerformanceCounterDataCollector::AddCounter(
        HPerformanceCounterDataCollector *this,
        unsigned __int16 *a2)
{
  DWORD dwFlags; // r14d
  const void *v5; // rbx
  DWORD v6; // eax
  HANDLE ProcessHeap; // rax
  WCHAR *v8; // r8
  PDH_STATUS v9; // eax
  int v10; // ebx
  void *v11; // rsi
  SIZE_T v12; // rbx
  HANDLE v13; // rax
  LPVOID v14; // rax
  const WCHAR *v15; // rsi
  __int64 v16; // rax
  PDH_STATUS v17; // eax
  int v18; // eax
  __int64 v19; // r14
  DWORD pcchPathListLength; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+78h] [rbp-88h] BYREF
  int v23; // [rsp+80h] [rbp-80h] BYREF
  PDH_HCOUNTER phCounter; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v25[64]; // [rsp+90h] [rbp-70h] BYREF

  phCounter = 0;
  pcchPathListLength = 0;
  if ( *((_DWORD *)this + 56) )
  {
    dwFlags = 2;
    v5 = (const void *)*((_QWORD *)this + 31);
    if ( *((_DWORD *)this + 64) != 7 )
      dwFlags = 0;
    if ( v5 )
    {
      ProcessHeap = GetProcessHeap();
      v6 = HeapSize(ProcessHeap, 0, v5);
    }
    else
    {
      v6 = 0;
    }
    while ( 1 )
    {
      v8 = (WCHAR *)*((_QWORD *)this + 31);
      pcchPathListLength = v6 >> 1;
      v9 = PdhExpandWildCardPathW(0, a2, v8, &pcchPathListLength, dwFlags);
      v10 = v9;
      if ( v9 != -2147481646 )
        break;
      v11 = (void *)*((_QWORD *)this + 31);
      v12 = 2LL * pcchPathListLength;
      v13 = GetProcessHeap();
      if ( v11 )
        v14 = HeapReAlloc(v13, 8u, v11, v12);
      else
        v14 = HeapAlloc(v13, 8u, v12);
      *((_QWORD *)this + 31) = v14;
      if ( !v14 )
      {
        v10 = -1073738821;
        *((_QWORD *)this + 31) = v11;
        return (unsigned int)v10;
      }
      v6 = 2 * pcchPathListLength;
    }
    if ( !v9 )
    {
      v15 = (const WCHAR *)*((_QWORD *)this + 31);
      if ( v15 )
      {
        while ( *v15 )
        {
          v10 = PdhAddCounterW(*((PDH_HQUERY *)this + 29), v15, 0, &phCounter);
          v16 = -1;
          do
            ++v16;
          while ( v15[v16] );
          v15 += v16 + 1;
          if ( v10 > 0 )
            v10 = (unsigned __int16)v10 | 0x80070000;
        }
      }
    }
  }
  else
  {
    v17 = PdhAddCounterW(*((PDH_HQUERY *)this + 29), a2, 0, &phCounter);
    v18 = PlaiHResultFromWin32(v17);
    v10 = v18;
    if ( v18 < 0 )
    {
      v22 = 0;
      v23 = v18;
      if ( (_DWORD)xmmword_180169738 )
      {
        if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v25, 0x4000000000000800uLL);
          v19 = -1;
          do
            ++v19;
          while ( v25[v19] );
          EventingWriteEvent(
            &g_Eventing,
            PLA_EVENT_ERROR,
            5,
            &v23,
            4,
            qword_180147320,
            1,
            &v22,
            4,
            "HPerformanceCounterDataCollector::AddCounter",
            45);
        }
      }
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18008e6f4  mov     [rsp-8+arg_10], rbx
0x18008e6f9  mov     [rsp-8+arg_18], rsi
0x18008e6fe  push    rbp
0x18008e6ff  push    rdi
0x18008e700  push    r12
0x18008e702  push    r14
0x18008e704  push    r15
0x18008e706  lea     rbp, [rsp-20h]
0x18008e70b  sub     rsp, 120h
0x18008e712  mov     rax, cs:__security_cookie
0x18008e719  xor     rax, rsp
0x18008e71c  mov     [rbp+40h+var_30], rax
0x18008e720  xor     r12d, r12d
0x18008e723  mov     r15, rdx
0x18008e726  mov     rdi, rcx
0x18008e729  mov     [rbp+40h+phCounter], r12
0x18008e72d  mov     [rsp+140h+pcchPathListLength], r12d
0x18008e732  cmp     [rcx+0E0h], r12d
0x18008e739  jz      loc_18008E868
0x18008e73f  cmp     dword ptr [rcx+100h], 7
0x18008e746  lea     r14d, [r12+2]
0x18008e74b  mov     rbx, [rcx+0F8h]
0x18008e752  cmovnz  r14d, r12d
0x18008e756  test    rbx, rbx
0x18008e759  jnz     short loc_18008E760
0x18008e75b  mov     eax, r12d
0x18008e75e  jmp     short loc_18008E774
0x18008e760  call    cs:__imp_GetProcessHeap
0x18008e766  mov     r8, rbx; lpMem
0x18008e769  xor     edx, edx; dwFlags
0x18008e76b  mov     rcx, rax; hHeap
0x18008e76e  call    cs:__imp_HeapSize
0x18008e774  mov     r8, [rdi+0F8h]; mszExpandedPathList
0x18008e77b  lea     r9, [rsp+140h+pcchPathListLength]; pcchPathListLength
0x18008e780  shr     eax, 1
0x18008e782  mov     rdx, r15; szWildCardPath
0x18008e785  xor     ecx, ecx; szDataSource
0x18008e787  mov     [rsp+140h+pcchPathListLength], eax
0x18008e78b  mov     [rsp+140h+dwFlags], r14d; dwFlags
0x18008e790  call    cs:__imp_PdhExpandWildCardPathW
0x18008e796  mov     ebx, eax
0x18008e798  cmp     eax, 800007D2h
0x18008e79d  jnz     short loc_18008E7FC
0x18008e79f  mov     ebx, [rsp+140h+pcchPathListLength]
0x18008e7a3  mov     rsi, [rdi+0F8h]
0x18008e7aa  add     rbx, rbx
0x18008e7ad  call    cs:__imp_GetProcessHeap
0x18008e7b3  mov     edx, 8; dwFlags
0x18008e7b8  mov     rcx, rax; hHeap
0x18008e7bb  test    rsi, rsi
0x18008e7be  jnz     short loc_18008E7CB
0x18008e7c0  mov     r8, rbx; dwBytes
0x18008e7c3  call    cs:__imp_HeapAlloc
0x18008e7c9  jmp     short loc_18008E7D7
0x18008e7cb  mov     r9, rbx; dwBytes
0x18008e7ce  mov     r8, rsi; lpMem
0x18008e7d1  call    cs:__imp_HeapReAlloc
0x18008e7d7  mov     [rdi+0F8h], rax
0x18008e7de  test    rax, rax
0x18008e7e1  jz      short loc_18008E7EB
0x18008e7e3  mov     eax, [rsp+140h+pcchPathListLength]
0x18008e7e7  add     eax, eax
0x18008e7e9  jmp     short loc_18008E774
0x18008e7eb  mov     ebx, 0C0000BBBh
0x18008e7f0  mov     [rdi+0F8h], rsi
0x18008e7f7  jmp     loc_18008E95F
0x18008e7fc  test    eax, eax
0x18008e7fe  jnz     loc_18008E95F
0x18008e804  mov     rsi, [rdi+0F8h]
0x18008e80b  test    rsi, rsi
0x18008e80e  jz      loc_18008E95F
0x18008e814  cmp     [rsi], r12w
0x18008e818  jz      loc_18008E95F
0x18008e81e  or      r14, 0FFFFFFFFFFFFFFFFh
0x18008e822  mov     rcx, [rdi+0E8h]; hQuery
0x18008e829  lea     r9, [rbp+40h+phCounter]; phCounter
0x18008e82d  xor     r8d, r8d; dwUserData
0x18008e830  mov     rdx, rsi; szFullCounterPath
0x18008e833  call    cs:__imp_PdhAddCounterW
0x18008e839  mov     ebx, eax
0x18008e83b  mov     rax, r14
0x18008e83e  inc     rax
0x18008e841  cmp     [rsi+rax*2], r12w
0x18008e846  jnz     short loc_18008E83E
0x18008e848  lea     rsi, [rsi+rax*2]
0x18008e84c  add     rsi, 2
0x18008e850  test    ebx, ebx
0x18008e852  jle     short loc_18008E85D
0x18008e854  movzx   ebx, bx
0x18008e857  or      ebx, 80070000h
0x18008e85d  cmp     [rsi], r12w
0x18008e861  jnz     short loc_18008E822
0x18008e863  jmp     loc_18008E95F
0x18008e868  mov     rcx, [rcx+0E8h]; hQuery
0x18008e86f  lea     r9, [rbp+40h+phCounter]; phCounter
0x18008e873  xor     r8d, r8d; dwUserData
0x18008e876  call    cs:__imp_PdhAddCounterW
0x18008e87c  mov     ecx, eax; unsigned int
0x18008e87e  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18008e883  mov     ebx, eax
0x18008e885  test    eax, eax
0x18008e887  jns     loc_18008E95F
0x18008e88d  cmp     dword ptr cs:xmmword_180169738, r12d
0x18008e894  mov     [rsp+140h+var_C8], r12d
0x18008e899  mov     [rbp+40h+var_C0], eax
0x18008e89c  jz      loc_18008E95F
0x18008e8a2  mov     rdx, 4000000000000800h; unsigned __int64
0x18008e8ac  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008e8b3  jz      loc_18008E95F
0x18008e8b9  mov     rax, cs:qword_180169748
0x18008e8c0  and     rax, rdx
0x18008e8c3  cmp     cs:qword_180169748, rax
0x18008e8ca  jnz     loc_18008E95F
0x18008e8d0  lea     rcx, [rbp+40h+var_B0]; unsigned __int16 *
0x18008e8d4  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008e8d9  lea     rax, [rbp+40h+var_B0]
0x18008e8dd  or      r14, 0FFFFFFFFFFFFFFFFh
0x18008e8e1  inc     r14
0x18008e8e4  cmp     [rax+r14*2], r12w
0x18008e8e9  jnz     short loc_18008E8E1
0x18008e8eb  lea     rax, [rbp+40h+var_B0]
0x18008e8ef  lea     ecx, [r14+r14]
0x18008e8f3  add     rcx, 2
0x18008e8f7  lea     r9, [rbp+40h+var_C0]
0x18008e8fb  mov     [rsp+140h+var_E0], rcx
0x18008e900  lea     rdx, PLA_EVENT_ERROR
0x18008e907  mov     [rsp+140h+var_E8], rax
0x18008e90c  mov     ecx, 4
0x18008e911  mov     [rsp+140h+var_F0], 2Dh ; '-'
0x18008e91a  lea     rax, aHperformanceco_1; "HPerformanceCounterDataCollector::AddCo"...
0x18008e921  mov     [rsp+140h+var_F8], rax
0x18008e926  lea     rax, [rsp+140h+var_C8]
0x18008e92b  mov     [rsp+140h+var_100], rcx
0x18008e930  mov     [rsp+140h+var_108], rax
0x18008e935  lea     r8d, [rcx+1]
0x18008e939  lea     rax, qword_180147320
0x18008e940  mov     [rsp+140h+var_110], 1
0x18008e949  mov     [rsp+140h+var_118], rax
0x18008e94e  mov     qword ptr [rsp+140h+dwFlags], rcx
0x18008e953  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18008e95a  call    EventingWriteEvent
0x18008e95f  mov     eax, ebx
0x18008e961  mov     rcx, [rbp+40h+var_30]
0x18008e965  xor     rcx, rsp; StackCookie
0x18008e968  call    __security_check_cookie
0x18008e96d  lea     r11, [rsp+140h+var_20]
0x18008e975  mov     rbx, [r11+40h]
0x18008e979  mov     rsi, [r11+48h]
0x18008e97d  mov     rsp, r11
0x18008e980  pop     r15
0x18008e982  pop     r14
0x18008e984  pop     r12
0x18008e986  pop     rdi
0x18008e987  pop     rbp
0x18008e988  retn
```
