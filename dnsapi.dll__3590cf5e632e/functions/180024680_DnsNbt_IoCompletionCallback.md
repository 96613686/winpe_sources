# DnsNbt_IoCompletionCallback

- ea: `0x180024680`
- end: `0x1800249b1`
- name: `DnsNbt_IoCompletionCallback`
- size: `817`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG_PTR NumberOfBytesTransferred, PTP_IO Io)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180023fc4`
- `0x180024680`
- `0x1800249b8`
- `0x1800317e0`
- `0x180035ad4`
- `0x1800657e0`
- `0x1800a608c`
- `0x1800ddfa8`
- `0x1800de650`
- `0x1800e4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800246eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800247b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800246eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800247b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800247a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800247eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800247a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800247eb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800247fa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x1800247fa`

## string_xrefs

- `0x180024840`: `DnsNbt_IoCompletionCallback`

## pseudocode

```c
__int64 __fastcall DnsNbt_IoCompletionCallback(__int64 a1, __int64 a2, __int64 a3, unsigned int a4)
{
  void *v6; // rbp
  __int64 v7; // rdi
  __int64 result; // rax
  char v9; // bl
  int v10; // r15d
  unsigned int v11; // r14d
  int v12; // r13d
  signed __int32 *v13; // rbx
  struct _RTL_CRITICAL_SECTION *v14; // r12
  unsigned int v15; // eax
  struct _TP_IO *v17; // rbx
  signed __int32 v18; // eax
  signed __int32 v19; // ett
  void *lpMem; // [rsp+30h] [rbp-58h]
  void *v21; // [rsp+98h] [rbp+10h] BYREF

  v6 = 0;
  v21 = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_q(1035, 30, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids, a2);
  v7 = *(_QWORD *)(a2 + 568);
  _m_prefetchw((const void *)(a2 + 584));
  result = (unsigned int)_InterlockedOr((volatile signed __int32 *)(a2 + 584), 2u);
  v9 = result;
  if ( (result & 2) == 0 )
  {
    v10 = 0;
    v11 = 0;
    v12 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 568));
    lpMem = *(void **)(v7 + 32);
    if ( (v9 & 4) != 0 )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_(1035, 32, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids);
      v13 = (signed __int32 *)(v7 + 4);
      goto LABEL_7;
    }
    v13 = (signed __int32 *)(v7 + 4);
    if ( (*(_BYTE *)(v7 + 4) & 1) != 0 )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_(1035, 33, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids);
      goto LABEL_7;
    }
    v11 = a4;
    if ( a4 )
    {
LABEL_7:
      v14 = (struct _RTL_CRITICAL_SECTION *)(v7 + 568);
LABEL_15:
      if ( (*(_DWORD *)(v7 + 40))-- == 1 )
      {
        _m_prefetchw(v13);
        v18 = *v13;
        do
        {
          v19 = v18;
          v18 = _InterlockedCompareExchange(v13, v18 | 1, v18);
        }
        while ( v19 != v18 );
        if ( (v18 & 1) == 0 )
        {
          v10 = 1;
          if ( *(_QWORD *)(v7 + 32) )
          {
            v12 = 1;
            *(_QWORD *)(v7 + 32) = 0;
          }
        }
      }
      v17 = *(struct _TP_IO **)(a2 + 576);
      *(_QWORD *)(a2 + 576) = 0;
      LeaveCriticalSection(v14);
      CloseThreadpoolIo(v17);
      if ( !v6 && !v11 )
        v11 = 4312;
      if ( v10 && lpMem )
      {
        (*(void (__fastcall **)(void *, _QWORD, void *, _QWORD))(v7 + 608))(lpMem, v11, v6, *(unsigned int *)(a2 + 588));
        v6 = 0;
      }
      if ( v6 )
        DnsFree(v6, DnsFreeRecordList);
      result = DeRefNbtLookupContext((LPVOID)v7);
      if ( v12 )
        return DeRefQueryBlobEx(lpMem);
      return result;
    }
    if ( *(_DWORD *)(v7 + 48) )
    {
      if ( *(_BYTE *)(a2 + 619) )
        goto LABEL_7;
      v15 = DnsNbt_CreateForwardRecords(v7 + 52, a2, &v21);
    }
    else
    {
      if ( !*(_WORD *)(a2 + 682) )
        goto LABEL_7;
      v15 = DnsNbt_CreateReverseRecords(*(unsigned int *)(v7 + 564), a2, &v21);
    }
    v11 = v15;
    v10 = 1;
    _m_prefetchw(v13);
    if ( (_InterlockedOr(v13, 1u) & 1) != 0 )
    {
      v10 = 0;
    }
    else if ( *(_QWORD *)(v7 + 32) )
    {
      v12 = 1;
      *(_QWORD *)(v7 + 32) = 0;
    }
    v14 = (struct _RTL_CRITICAL_SECTION *)(v7 + 568);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 568));
    DnsNbt_Cancel((LPVOID)v7);
    EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 568));
    v6 = v21;
    goto LABEL_15;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    return WPP_SF_(1035, 31, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180024680  mov     rax, rsp
0x180024683  push    rbx
0x180024684  push    rbp
0x180024685  push    rsi
0x180024686  push    rdi
0x180024687  push    r12
0x180024689  push    r13
0x18002468b  push    r14
0x18002468d  push    r15
0x18002468f  sub     rsp, 48h
0x180024693  mov     rsi, rdx
0x180024696  mov     r12d, r9d
0x180024699  xor     edx, edx
0x18002469b  mov     ebp, edx
0x18002469d  mov     [rax+10h], rdx
0x1800246a1  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800246a8  jnz     loc_180024901
0x1800246ae  mov     rdi, [rsi+238h]
0x1800246b5  prefetchw byte ptr [rsi+248h]
0x1800246bc  mov     eax, [rsi+248h]
0x1800246c2  mov     ecx, eax
0x1800246c4  or      ecx, 2
0x1800246c7  lock cmpxchg [rsi+248h], ecx
0x1800246cf  jnz     short loc_1800246C2
0x1800246d1  mov     ebx, eax
0x1800246d3  test    al, 2
0x1800246d5  jnz     loc_1800248D9
0x1800246db  lea     rcx, [rdi+238h]; lpCriticalSection
0x1800246e2  mov     r15d, edx
0x1800246e5  mov     r14d, edx
0x1800246e8  mov     r13d, edx
0x1800246eb  call    cs:__imp_EnterCriticalSection
0x1800246f2  nop     dword ptr [rax+rax+00h]
0x1800246f7  mov     rax, [rdi+20h]
0x1800246fb  mov     r8d, 1
0x180024701  mov     [rsp+88h+lpMem], rax
0x180024706  test    bl, 4
0x180024709  jnz     loc_1800248C7
0x18002470f  lea     rbx, [rdi+4]
0x180024713  test    [rbx], r8b
0x180024716  jnz     loc_180024939
0x18002471c  mov     r14d, r12d
0x18002471f  test    r12d, r12d
0x180024722  jz      short loc_180024730
0x180024724  lea     r12, [rdi+238h]
0x18002472b  jmp     loc_1800247CC
0x180024730  xor     r12d, r12d
0x180024733  cmp     [rdi+30h], r12d
0x180024737  jz      loc_180024961
0x18002473d  cmp     [rsi+26Bh], r12b
0x180024744  jnz     short loc_180024724
0x180024746  lea     rcx, [rdi+34h]
0x18002474a  mov     rdx, rsi
0x18002474d  lea     r8, [rsp+88h+arg_8]
0x180024755  call    DnsNbt_CreateForwardRecords
0x18002475a  mov     r8d, 1
0x180024760  mov     r14d, eax
0x180024763  mov     edx, r8d
0x180024766  mov     r15d, r8d
0x180024769  prefetchw byte ptr [rbx]
0x18002476c  mov     eax, [rbx]
0x18002476e  mov     ecx, eax
0x180024770  or      ecx, r8d
0x180024773  lock cmpxchg [rbx], ecx
0x180024777  jnz     short loc_18002476E
0x180024779  test    r8b, al
0x18002477c  jnz     loc_18002498A
0x180024782  cmp     [rdi+20h], r12
0x180024786  jz      short loc_18002478F
0x180024788  mov     r13d, r8d
0x18002478b  mov     [rdi+20h], r12
0x18002478f  test    edx, edx
0x180024791  jz      loc_180024992
0x180024797  lea     r12, [rdi+238h]
0x18002479e  mov     rcx, r12; lpCriticalSection
0x1800247a1  call    cs:__imp_LeaveCriticalSection
0x1800247a8  nop     dword ptr [rax+rax+00h]
0x1800247ad  mov     rcx, rdi; lpMem
0x1800247b0  call    DnsNbt_Cancel
0x1800247b5  mov     rcx, r12; lpCriticalSection
0x1800247b8  call    cs:__imp_EnterCriticalSection
0x1800247bf  nop     dword ptr [rax+rax+00h]
0x1800247c4  mov     rbp, [rsp+88h+arg_8]
0x1800247cc  add     dword ptr [rdi+28h], 0FFFFFFFFh
0x1800247d0  jz      loc_18002488D
0x1800247d6  mov     rbx, [rsi+240h]
0x1800247dd  mov     rcx, r12; lpCriticalSection
0x1800247e0  mov     qword ptr [rsi+240h], 0
0x1800247eb  call    cs:__imp_LeaveCriticalSection
0x1800247f2  nop     dword ptr [rax+rax+00h]
0x1800247f7  mov     rcx, rbx; pio
0x1800247fa  call    cs:__imp_CloseThreadpoolIo
0x180024801  nop     dword ptr [rax+rax+00h]
0x180024806  xor     r12d, r12d
0x180024809  test    rbp, rbp
0x18002480c  jnz     short loc_18002481A
0x18002480e  test    r14d, r14d
0x180024811  mov     eax, 10D8h
0x180024816  cmovz   r14d, eax
0x18002481a  mov     rbx, [rsp+88h+lpMem]
0x18002481f  test    r15d, r15d
0x180024822  jnz     short loc_180024867
0x180024824  test    rbp, rbp
0x180024827  jnz     loc_18002499F
0x18002482d  mov     rcx, rdi; lpMem
0x180024830  call    DeRefNbtLookupContext
0x180024835  test    r13d, r13d
0x180024838  jz      short loc_180024855
0x18002483a  mov     r9d, 11h
0x180024840  lea     rdx, aDnsnbtIocomple; "DnsNbt_IoCompletionCallback"
0x180024847  mov     r8d, 54Fh
0x18002484d  mov     rcx, rbx; lpMem
0x180024850  call    DeRefQueryBlobEx
0x180024855  add     rsp, 48h
0x180024859  pop     r15
0x18002485b  pop     r14
0x18002485d  pop     r13
0x18002485f  pop     r12
0x180024861  pop     rdi
0x180024862  pop     rsi
0x180024863  pop     rbp
0x180024864  pop     rbx
0x180024865  retn
0x180024867  test    rbx, rbx
0x18002486a  jz      short loc_180024824
0x18002486c  mov     r9d, [rsi+24Ch]
0x180024873  mov     r8, rbp
0x180024876  mov     rax, [rdi+260h]
0x18002487d  mov     edx, r14d
0x180024880  mov     rcx, rbx
0x180024883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024888  mov     rbp, r12
0x18002488b  jmp     short loc_180024824
0x18002488d  prefetchw byte ptr [rbx]
0x180024890  mov     eax, [rbx]
0x180024892  mov     edx, 1
0x180024897  mov     ecx, eax
0x180024899  or      ecx, edx
0x18002489b  lock cmpxchg [rbx], ecx
0x18002489f  jnz     short loc_180024897
0x1800248a1  test    dl, al
0x1800248a3  jnz     loc_1800247D6
0x1800248a9  cmp     qword ptr [rdi+20h], 0
0x1800248ae  mov     r15d, edx
0x1800248b1  jz      loc_1800247D6
0x1800248b7  mov     r13d, edx
0x1800248ba  mov     qword ptr [rdi+20h], 0
0x1800248c2  jmp     loc_1800247D6
0x1800248c7  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800248ce  jnz     short loc_180024921
0x1800248d0  lea     rbx, [rdi+4]
0x1800248d4  jmp     loc_180024724
0x1800248d9  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800248e0  jz      loc_180024855
0x1800248e6  mov     edx, 1Fh
0x1800248eb  lea     r8, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids
0x1800248f2  mov     ecx, 40Bh
0x1800248f7  call    WPP_SF_
0x1800248fc  jmp     loc_180024855
0x180024901  mov     edx, 1Eh
0x180024906  lea     r8, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids
0x18002490d  mov     ecx, 40Bh
0x180024912  mov     r9, rsi
0x180024915  call    WPP_SF_q
0x18002491a  xor     edx, edx
0x18002491c  jmp     loc_1800246AE
0x180024921  mov     edx, 20h ; ' '
0x180024926  lea     r8, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids
0x18002492d  mov     ecx, 40Bh
0x180024932  call    WPP_SF_
0x180024937  jmp     short loc_1800248D0
0x180024939  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180024940  jz      loc_180024724
0x180024946  mov     edx, 21h ; '!'
0x18002494b  lea     r8, WPP_c47320bcde7f3cc74fc8c2adc96bc839_Traceguids
0x180024952  mov     ecx, 40Bh
0x180024957  call    WPP_SF_
0x18002495c  jmp     loc_180024724
0x180024961  cmp     [rsi+2AAh], r12w
0x180024969  jbe     loc_180024724
0x18002496f  mov     ecx, [rdi+234h]
0x180024975  lea     r8, [rsp+88h+arg_8]
0x18002497d  mov     rdx, rsi
0x180024980  call    DnsNbt_CreateReverseRecords
0x180024985  jmp     loc_18002475A
0x18002498a  mov     r15d, r12d
0x18002498d  jmp     loc_18002478F
0x180024992  mov     rbp, [rsp+88h+arg_8]
0x18002499a  jmp     loc_180024724
0x18002499f  mov     edx, 1; FreeType
0x1800249a4  mov     rcx, rbp; pData
0x1800249a7  call    DnsFree
0x1800249ac  jmp     loc_18002482D
```
