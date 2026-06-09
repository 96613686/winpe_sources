# SrvCryptOpenStorageProvider

- ea: `0x180004550`
- end: `0x1800048e1`
- name: `SrvCryptOpenStorageProvider`
- size: `913`
- prototype: `__int64 __fastcall(__int64, _QWORD *, const WCHAR *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x180004550`
- `0x1800048f0`
- `0x180004b70`
- `0x180006a70`
- `0x180006e60`
- `0x18000a6cc`
- `0x18000a798`
- `0x18000d0ac`
- `0x180019010`

## import_xrefs

- `bcrypt!BCryptResolveProviders` at `0x1800045b6`
- `bcrypt!BCryptResolveProviders` at `0x1800045b6`
- `bcrypt!BCryptFreeBuffer` at `0x180004727`
- `bcrypt!BCryptFreeBuffer` at `0x180004727`
- `ntdll!RtlAllocateHeap` at `0x1800045db`
- `ntdll!RtlAllocateHeap` at `0x1800045db`
- `ntdll!RtlEnterCriticalSection` at `0x1800046d1`
- `ntdll!RtlEnterCriticalSection` at `0x1800046d1`
- `ntdll!RtlLeaveCriticalSection` at `0x180004715`
- `ntdll!RtlLeaveCriticalSection` at `0x180004715`
- `ntdll!RtlInitializeCriticalSection` at `0x18000468e`
- `ntdll!RtlInitializeCriticalSection` at `0x18000468e`

## string_xrefs

- `0x180004772`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x1800047c9`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000481b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000485b`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x18000487a`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`
- `0x1800048aa`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvapi.c`

## pseudocode

```c
__int64 __fastcall SrvCryptOpenStorageProvider(__int64 a1, _QWORD *a2, const WCHAR *a3, unsigned int a4)
{
  int v8; // edx
  NTSTATUS v9; // ebx
  char *Heap; // rax
  int v11; // edx
  char *v12; // rdi
  int v13; // r8d
  int Provider; // eax
  int v15; // edx
  struct _RTL_CRITICAL_SECTION *v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rcx
  _QWORD *v19; // rsi
  __int64 v21; // r9
  PVOID pvBuffer; // [rsp+40h] [rbp-58h] BYREF
  ULONG v23; // [rsp+A8h] [rbp+10h] BYREF

  pvBuffer = 0;
  v23 = 0;
  if ( a2 )
  {
    if ( !a1 )
    {
      v9 = -2146893786;
      DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c", 2368);
      goto LABEL_12;
    }
    v9 = BCryptResolveProviders(0, 0x10001u, L"KEY_STORAGE", a3, 1u, 0, &v23, (PCRYPT_PROVIDER_REFS *)&pvBuffer);
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v8,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          (unsigned int)"Status",
          v9,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          84);
    }
    else
    {
      Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x178u);
      v12 = Heap;
      if ( Heap )
      {
        memset_0(Heap, 0, 0x178u);
        Provider = LoadProviderEx(**((_QWORD **)pvBuffer + 1), (int)v12 + 40, v13, (int)v12 + 32, (__int64)(v12 + 40));
        v9 = Provider;
        if ( Provider < 0 )
        {
          v21 = 2429;
        }
        else
        {
          v9 = (*((__int64 (__fastcall **)(char *, const WCHAR *, _QWORD))v12 + 6))(v12 + 296, a3, a4);
          if ( v9 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v15,
                (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
                (unsigned int)"Status",
                v9,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
                141);
            goto LABEL_34;
          }
          Provider = (*((__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64, __int64, _DWORD))v12 + 11))(
                       *((_QWORD *)v12 + 37),
                       L"MSSP/Client Process ID",
                       a1 + 16,
                       4,
                       0);
          v9 = Provider;
          if ( !Provider )
          {
            *(_QWORD *)v12 = 1145324614;
            *((_QWORD *)v12 + 1) = 1;
            RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(v12 + 304));
            *((_QWORD *)v12 + 44) = v12 + 344;
            *((_QWORD *)v12 + 43) = v12 + 344;
            if ( (unsigned int)Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline() )
            {
              *((_QWORD *)v12 + 46) = *(_QWORD *)(a1 + 296);
              IncrementKeyIsoPerfCounter(*(PPERF_COUNTERSET_INSTANCE *)(a1 + 296), 1u);
            }
            v16 = (struct _RTL_CRITICAL_SECTION *)(a1 + 40);
            RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 40));
            v17 = ++*(_QWORD *)(a1 + 96);
            *((_QWORD *)v12 + 45) = v17;
            *a2 = v17;
            _InterlockedIncrement64((volatile signed __int64 *)v12 + 1);
            v18 = *(_QWORD *)(a1 + 80);
            v19 = (_QWORD *)(a1 + 80);
            if ( *(_QWORD **)(v18 + 8) != v19 )
              __fastfail(3u);
            *((_QWORD *)v12 + 2) = v18;
            *((_QWORD *)v12 + 3) = v19;
            *(_QWORD *)(v18 + 8) = v12 + 16;
            *v19 = v12 + 16;
            RtlLeaveCriticalSection(v16);
            v9 = 0;
            goto LABEL_12;
          }
          v21 = 2462;
        }
        DebugTraceError(
          (unsigned int)Provider,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          v21);
LABEL_34:
        if ( *((_QWORD *)v12 + 4) )
          UnloadProvider();
        SrvCryptLocalFree(v12);
        goto LABEL_12;
      }
      v9 = -2146893810;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          (unsigned int)"Status",
          14,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
          101);
    }
  }
  else
  {
    v9 = -2146893785;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)NormalizeNteStatus((unsigned int)v9);
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
      (unsigned int)"Status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvapi.c",
      51);
  }
LABEL_12:
  if ( pvBuffer )
    BCryptFreeBuffer(pvBuffer);
  if ( v9 )
    return (unsigned int)NormalizeNteStatus((unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180004550  mov     r11, rsp
0x180004553  push    rbx
0x180004554  push    rbp
0x180004555  push    rsi
0x180004556  push    rdi
0x180004557  push    r12
0x180004559  push    r13
0x18000455b  push    r14
0x18000455d  push    r15
0x18000455f  sub     rsp, 58h
0x180004563  mov     rsi, rcx
0x180004566  mov     r13d, r9d
0x180004569  xor     ecx, ecx; pszContext
0x18000456b  mov     rbp, r8
0x18000456e  mov     [r11-58h], rcx
0x180004572  mov     r14, rdx
0x180004575  mov     [r11+10h], ecx
0x180004579  test    rdx, rdx
0x18000457c  jz      loc_18000482D
0x180004582  test    rsi, rsi
0x180004585  jz      loc_180004874
0x18000458b  lea     rax, [r11-58h]
0x18000458f  mov     r9, r8; pszProvider
0x180004592  mov     [r11-60h], rax
0x180004596  lea     r8, pszFunction; "KEY_STORAGE"
0x18000459d  lea     rax, [r11+10h]
0x1800045a1  mov     edx, 10001h; dwInterface
0x1800045a6  mov     [r11-68h], rax
0x1800045aa  mov     [rsp+98h+dwFlags], ecx; dwFlags
0x1800045ae  mov     [rsp+98h+dwMode], 1; dwMode
0x1800045b6  call    cs:__imp_BCryptResolveProviders
0x1800045bc  mov     ebx, eax
0x1800045be  test    eax, eax
0x1800045c0  js      loc_1800047F2
0x1800045c6  mov     rcx, gs:60h
0x1800045cf  xor     edx, edx; Flags
0x1800045d1  mov     r8d, 178h; Size
0x1800045d7  mov     rcx, [rcx+30h]; HeapHandle
0x1800045db  call    cs:__imp_RtlAllocateHeap
0x1800045e1  mov     rdi, rax
0x1800045e4  test    rax, rax
0x1800045e7  jz      loc_18000479B
0x1800045ed  xor     edx, edx; Val
0x1800045ef  mov     r8d, 178h; Size
0x1800045f5  mov     rcx, rax; void *
0x1800045f8  call    memset_0
0x1800045fd  mov     rax, [rsp+98h+pvBuffer]
0x180004602  lea     rdx, [rdi+28h]
0x180004606  lea     r9, [rdi+20h]
0x18000460a  mov     qword ptr [rsp+98h+dwMode], rdx
0x18000460f  mov     rcx, [rax+8]
0x180004613  mov     rcx, [rcx]
0x180004616  call    LoadProviderEx
0x18000461b  mov     ebx, eax
0x18000461d  test    eax, eax
0x18000461f  js      loc_18000489C
0x180004625  mov     rax, [rdi+30h]
0x180004629  lea     rcx, [rdi+128h]
0x180004630  mov     r8d, r13d
0x180004633  mov     rdx, rbp
0x180004636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000463b  mov     ebx, eax
0x18000463d  test    eax, eax
0x18000463f  js      loc_18000474D
0x180004645  mov     rcx, [rdi+128h]
0x18000464c  lea     r8, [rsi+10h]
0x180004650  mov     rax, [rdi+58h]
0x180004654  lea     rdx, aMsspClientProc; "MSSP/Client Process ID"
0x18000465b  mov     r9d, 4
0x180004661  mov     [rsp+98h+dwMode], 0
0x180004669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000466e  mov     ebx, eax
0x180004670  test    eax, eax
0x180004672  jnz     loc_1800048A4
0x180004678  lea     rcx, [rdi+130h]; CriticalSection
0x18000467f  mov     qword ptr [rdi], 44444446h
0x180004686  mov     qword ptr [rdi+8], 1
0x18000468e  call    cs:__imp_RtlInitializeCriticalSection
0x180004694  lea     rax, [rdi+158h]
0x18000469b  mov     [rax+8], rax
0x18000469f  mov     [rax], rax
0x1800046a2  call    Feature_CNG_KEYISO_TRACK_OPEN_HANDLE_COUNT__private_IsEnabledDeviceUsageNoInline
0x1800046a7  test    eax, eax
0x1800046a9  jz      short loc_1800046CA
0x1800046ab  mov     rax, [rsi+128h]
0x1800046b2  mov     edx, 1; CounterId
0x1800046b7  mov     [rdi+170h], rax
0x1800046be  mov     rcx, [rsi+128h]; Instance
0x1800046c5  call    IncrementKeyIsoPerfCounter
0x1800046ca  lea     rbx, [rsi+28h]
0x1800046ce  mov     rcx, rbx; CriticalSection
0x1800046d1  call    cs:__imp_RtlEnterCriticalSection
0x1800046d7  inc     qword ptr [rsi+60h]
0x1800046db  mov     rax, [rsi+60h]
0x1800046df  mov     [rdi+168h], rax
0x1800046e6  mov     [r14], rax
0x1800046e9  lock inc qword ptr [rdi+8]
0x1800046ee  mov     rcx, [rsi+50h]
0x1800046f2  add     rsi, 50h ; 'P'
0x1800046f6  cmp     [rcx+8], rsi
0x1800046fa  jnz     loc_1800048DA
0x180004700  lea     rax, [rdi+10h]
0x180004704  mov     [rax], rcx
0x180004707  mov     [rax+8], rsi
0x18000470b  mov     [rcx+8], rax
0x18000470f  mov     rcx, rbx; CriticalSection
0x180004712  mov     [rsi], rax
0x180004715  call    cs:__imp_RtlLeaveCriticalSection
0x18000471b  xor     ebx, ebx
0x18000471d  mov     rcx, [rsp+98h+pvBuffer]; pvBuffer
0x180004722  test    rcx, rcx
0x180004725  jz      short loc_18000472D
0x180004727  call    cs:__imp_BCryptFreeBuffer
0x18000472d  test    ebx, ebx
0x18000472f  jz      short loc_18000473A
0x180004731  mov     ecx, ebx
0x180004733  call    NormalizeNteStatus
0x180004738  mov     ebx, eax
0x18000473a  mov     eax, ebx
0x18000473c  add     rsp, 58h
0x180004740  pop     r15
0x180004742  pop     r14
0x180004744  pop     r13
0x180004746  pop     r12
0x180004748  pop     rdi
0x180004749  pop     rsi
0x18000474a  pop     rbp
0x18000474b  pop     rbx
0x18000474c  retn
0x18000474d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004754  lea     rax, WPP_GLOBAL_Control
0x18000475b  cmp     rcx, rax
0x18000475e  jz      loc_1800048BF
0x180004764  test    byte ptr [rcx+1Ch], 1
0x180004768  jz      loc_1800048BF
0x18000476e  mov     rcx, [rcx+10h]
0x180004772  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004779  mov     [rsp+98h+var_68], 98Dh
0x180004781  lea     r9, aStatus; "Status"
0x180004788  mov     qword ptr [rsp+98h+dwFlags], r8
0x18000478d  mov     [rsp+98h+dwMode], ebx
0x180004791  call    WPP_SF_sDsd
0x180004796  jmp     loc_1800048BF
0x18000479b  mov     ebx, 8009000Eh
0x1800047a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047a7  lea     rax, WPP_GLOBAL_Control
0x1800047ae  cmp     rcx, rax
0x1800047b1  jz      loc_18000471D
0x1800047b7  test    byte ptr [rcx+1Ch], 1
0x1800047bb  jz      loc_18000471D
0x1800047c1  mov     [rsp+98h+var_68], 965h
0x1800047c9  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800047d0  mov     qword ptr [rsp+98h+dwFlags], r8
0x1800047d5  mov     [rsp+98h+dwMode], 8009000Eh
0x1800047dd  mov     rcx, [rcx+10h]
0x1800047e1  lea     r9, aStatus; "Status"
0x1800047e8  call    WPP_SF_sDsd
0x1800047ed  jmp     loc_18000471D
0x1800047f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047f9  lea     rax, WPP_GLOBAL_Control
0x180004800  cmp     rcx, rax
0x180004803  jz      loc_18000471D
0x180004809  test    byte ptr [rcx+1Ch], 1
0x18000480d  jz      loc_18000471D
0x180004813  mov     [rsp+98h+var_68], 954h
0x18000481b  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004822  mov     qword ptr [rsp+98h+dwFlags], r8
0x180004827  mov     [rsp+98h+dwMode], ebx
0x18000482b  jmp     short loc_1800047DD
0x18000482d  mov     ebx, 80090027h
0x180004832  mov     rcx, cs:WPP_GLOBAL_Control
0x180004839  lea     rax, WPP_GLOBAL_Control
0x180004840  cmp     rcx, rax
0x180004843  jz      loc_180004731
0x180004849  test    byte ptr [rcx+1Ch], 1
0x18000484d  jz      loc_180004731
0x180004853  mov     [rsp+98h+var_68], 933h
0x18000485b  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004862  mov     qword ptr [rsp+98h+dwFlags], r8
0x180004867  mov     [rsp+98h+dwMode], 80090027h
0x18000486f  jmp     loc_1800047DD
0x180004874  mov     r9d, 940h
0x18000487a  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180004881  lea     rdx, aStatus; "Status"
0x180004888  mov     ecx, 80090026h
0x18000488d  mov     ebx, 80090026h
0x180004892  call    DebugTraceError
0x180004897  jmp     loc_18000471D
0x18000489c  mov     r9d, 97Dh
0x1800048a2  jmp     short loc_1800048AA
0x1800048a4  mov     r9d, 99Eh
0x1800048aa  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800048b1  mov     ecx, eax
0x1800048b3  lea     rdx, aStatus; "Status"
0x1800048ba  call    DebugTraceError
0x1800048bf  mov     rcx, [rdi+20h]
0x1800048c3  test    rcx, rcx
0x1800048c6  jz      short loc_1800048CD
0x1800048c8  call    UnloadProvider
0x1800048cd  mov     rcx, rdi; P
0x1800048d0  call    SrvCryptLocalFree
0x1800048d5  jmp     loc_18000471D
0x1800048da  mov     ecx, 3
0x1800048df  int     29h; Win8: RtlFailFast(ecx)
```
