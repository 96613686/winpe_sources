# PAL_System_NonBoundThread_CondWait

- ea: `0x180059644`
- end: `0x180059922`
- name: `PAL_System_NonBoundThread_CondWait`
- size: `734`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, DWORD nCount@<edx>, int, int, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800351f0`

## callees

- `0x1800018a4`
- `0x180004a94`
- `0x180059644`
- `0x180078c20`
- `0x18007969c`
- `0x1801614c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180059698`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180059698`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800596e7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800597fd`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800596e7`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800597fd`

## string_xrefs

- `0x180059732`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x1800598ca`: `onecore\termsrv\rdpplatform\common\pal\wincommon\coresystem\tscoresystempalwincommon.cpp`
- `0x180059717`: `PAL_System_NonBoundThread_CondWait`
- `0x1800598af`: `PAL_System_NonBoundThread_CondWait`
- `0x18005982a`: `Thread: 0x%x got a QUIT`

## pseudocode

```c
__int64 __fastcall PAL_System_NonBoundThread_CondWait(
        const HANDLE *Src,
        DWORD nCount,
        char *a3,
        DWORD a4,
        int a5,
        int a6,
        DWORD *a7)
{
  __int64 v8; // rbx
  int v11; // r8d
  int v12; // r9d
  DWORD CurrentThreadId; // r13d
  DWORD v14; // ecx
  int v15; // r8d
  int v16; // r9d
  unsigned int v17; // ebx
  DWORD v19; // r14d
  DWORD v20; // eax
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  int v22; // [rsp+54h] [rbp-ACh] BYREF
  const char *v23; // [rsp+58h] [rbp-A8h] BYREF
  const char *v24; // [rsp+60h] [rbp-A0h] BYREF
  const char *v25; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Handles[64]; // [rsp+70h] [rbp-90h] BYREF

  v8 = nCount;
  memset_0(Handles, 0, sizeof(Handles));
  CurrentThreadId = GetCurrentThreadId();
  if ( !Src || !a7 || !(_DWORD)v8 )
    return (unsigned int)-2147024809;
  if ( a6 )
  {
    v14 = WaitForMultipleObjectsEx(v8, Src, 0, a4, 0);
LABEL_6:
    if ( v14 > (int)v8 - 1 )
    {
      if ( v14 < 0x80 || v14 > (int)v8 + 127 )
      {
        if ( v14 == 258 )
        {
          *a7 = 0;
          return (unsigned int)-2092629813;
        }
        else
        {
          v17 = -2147467259;
          if ( (unsigned int)CallbackContext > 2 )
          {
            v21 = 1805;
            v23 = "PAL_System_NonBoundThread_CondWait";
            v22 = -2147467259;
            v25 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
            v24 = "Wait Failed with unknown error";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v14,
              (unsigned int)qword_1801B8D20,
              v15,
              v16,
              (__int64)&v24,
              (__int64)&v22,
              (__int64)&v25,
              (__int64)&v21,
              (__int64)&v23);
          }
        }
      }
      else
      {
        v17 = -2092629814;
        *a7 = v14 - 128;
      }
    }
    else
    {
      *a7 = v14;
      return 0;
    }
    return v17;
  }
  if ( (unsigned int)v8 >= 0x3F )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v22 = 1716;
      v24 = "PAL_System_NonBoundThread_CondWait";
      v25 = "onecore\\termsrv\\rdpplatform\\common\\pal\\wincommon\\coresystem\\tscoresystempalwincommon.cpp";
      v23 = "Too many wait objects";
      v21 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)a3 - 1,
        (unsigned int)qword_1801B8F60,
        v11,
        v12,
        (__int64)&v23,
        (__int64)&v21,
        (__int64)&v25,
        (__int64)&v22,
        (__int64)&v24);
    }
    return (unsigned int)-2147024809;
  }
  memcpy_0(Handles, Src, 8 * v8);
  if ( (unsigned __int64)(a3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    Handles[v8] = a3;
  v19 = v8 + 1;
  if ( (unsigned __int64)(a3 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    v19 = v8;
  while ( 1 )
  {
    v20 = WaitForMultipleObjectsEx(v19, Handles, 0, a4, 1);
    v14 = v20;
    if ( (unsigned __int64)(a3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && v20 == (_DWORD)v8 )
      break;
    if ( v20 != 192 )
      goto LABEL_6;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v21 = CurrentThreadId;
    v23 = "Thread: 0x%x got a QUIT";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v20,
      (unsigned int)byte_1801B8CF5,
      v15,
      v16,
      (__int64)&v23,
      (__int64)&v21);
  }
  return (unsigned int)-2092629812;
}

```

## disassembly

```asm
0x180059644  mov     [rsp-8+arg_10], rbx
0x180059649  push    rbp
0x18005964a  push    rsi
0x18005964b  push    rdi
0x18005964c  push    r12
0x18005964e  push    r13
0x180059650  push    r14
0x180059652  push    r15
0x180059654  lea     rbp, [rsp-180h]
0x18005965c  sub     rsp, 280h
0x180059663  mov     rax, cs:__security_cookie
0x18005966a  xor     rax, rsp
0x18005966d  mov     [rbp+1B0h+var_40], rax
0x180059674  mov     rdi, [rbp+1B0h+arg_30]
0x18005967b  mov     r15, r8
0x18005967e  mov     ebx, edx
0x180059680  mov     r14, rcx
0x180059683  xor     edx, edx; Val
0x180059685  lea     rcx, [rsp+2B0h+Handles]; void *
0x18005968a  mov     r8d, 200h; Size
0x180059690  mov     r12d, r9d
0x180059693  call    memset_0
0x180059698  call    cs:__imp_GetCurrentThreadId
0x18005969e  mov     r13d, eax
0x1800596a1  test    r14, r14
0x1800596a4  jz      loc_18005978A
0x1800596aa  test    rdi, rdi
0x1800596ad  jz      loc_18005978A
0x1800596b3  test    ebx, ebx
0x1800596b5  jz      loc_18005978A
0x1800596bb  xor     esi, esi
0x1800596bd  lea     rcx, [r15-1]
0x1800596c1  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800596c5  lea     edx, [rsi+1]
0x1800596c8  cmovbe  esi, edx
0x1800596cb  cmp     [rbp+1B0h+arg_28], 0
0x1800596d2  jz      short loc_180059703
0x1800596d4  mov     r9d, r12d; dwMilliseconds
0x1800596d7  mov     [rsp+2B0h+bAlertable], 0; bAlertable
0x1800596df  xor     r8d, r8d; bWaitAll
0x1800596e2  mov     rdx, r14; lpHandles
0x1800596e5  mov     ecx, ebx; nCount
0x1800596e7  call    cs:__imp_WaitForMultipleObjectsEx
0x1800596ed  mov     ecx, eax
0x1800596ef  lea     eax, [rbx-1]
0x1800596f2  cmp     ecx, eax
0x1800596f4  ja      loc_180059865
0x1800596fa  mov     [rdi], ecx
0x1800596fc  xor     ebx, ebx
0x1800596fe  jmp     loc_18005978F
0x180059703  cmp     ebx, 3Fh ; '?'
0x180059706  jb      loc_1800597BB
0x18005970c  mov     eax, cs:CallbackContext
0x180059712  cmp     eax, 2
0x180059715  jbe     short loc_18005978A
0x180059717  lea     rax, aPalSystemNonbo; "PAL_System_NonBoundThread_CondWait"
0x18005971e  mov     [rsp+2B0h+var_25C], 6B4h
0x180059726  mov     [rsp+2B0h+var_250], rax
0x18005972b  lea     rdx, qword_1801B8F60
0x180059732  lea     rax, aOnecoreTermsrv_12; "onecore\\termsrv\\rdpplatform\\common\\"...
0x180059739  mov     ebx, 80004005h
0x18005973e  mov     [rsp+2B0h+var_248], rax
0x180059743  lea     rax, aTooManyWaitObj; "Too many wait objects"
0x18005974a  mov     [rsp+2B0h+var_258], rax
0x18005974f  lea     rax, [rsp+2B0h+var_250]
0x180059754  mov     [rsp+2B0h+var_270], rax
0x180059759  lea     rax, [rsp+2B0h+var_25C]
0x18005975e  mov     [rsp+2B0h+var_278], rax
0x180059763  lea     rax, [rsp+2B0h+var_248]
0x180059768  mov     [rsp+2B0h+var_280], rax
0x18005976d  lea     rax, [rsp+2B0h+var_260]
0x180059772  mov     [rsp+2B0h+var_288], rax
0x180059777  lea     rax, [rsp+2B0h+var_258]
0x18005977c  mov     qword ptr [rsp+2B0h+bAlertable], rax
0x180059781  mov     [rsp+2B0h+var_260], ebx
0x180059785  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18005978a  mov     ebx, 80070057h
0x18005978f  mov     eax, ebx
0x180059791  mov     rcx, [rbp+1B0h+var_40]
0x180059798  xor     rcx, rsp; StackCookie
0x18005979b  call    __security_check_cookie
0x1800597a0  mov     rbx, [rsp+2B0h+arg_10]
0x1800597a8  add     rsp, 280h
0x1800597af  pop     r15
0x1800597b1  pop     r14
0x1800597b3  pop     r13
0x1800597b5  pop     r12
0x1800597b7  pop     rdi
0x1800597b8  pop     rsi
0x1800597b9  pop     rbp
0x1800597ba  retn
0x1800597bb  test    ebx, ebx
0x1800597bd  jz      short loc_1800597D8
0x1800597bf  mov     r8, rbx
0x1800597c2  lea     rcx, [rsp+2B0h+Handles]; void *
0x1800597c7  shl     r8, 3; Size
0x1800597cb  mov     rdx, r14; Src
0x1800597ce  call    memcpy_0
0x1800597d3  mov     edx, 1
0x1800597d8  test    esi, esi
0x1800597da  jz      short loc_1800597E1
0x1800597dc  mov     [rsp+rbx*8+2B0h+Handles], r15
0x1800597e1  test    esi, esi
0x1800597e3  lea     r14d, [rbx+1]
0x1800597e7  cmovz   r14d, ebx
0x1800597eb  mov     [rsp+2B0h+bAlertable], edx; bAlertable
0x1800597ef  mov     r9d, r12d; dwMilliseconds
0x1800597f2  lea     rdx, [rsp+2B0h+Handles]; lpHandles
0x1800597f7  xor     r8d, r8d; bWaitAll
0x1800597fa  mov     ecx, r14d; nCount
0x1800597fd  call    cs:__imp_WaitForMultipleObjectsEx
0x180059803  mov     ecx, eax
0x180059805  test    esi, esi
0x180059807  jz      short loc_18005980D
0x180059809  cmp     eax, ebx
0x18005980b  jz      short loc_18005981F
0x18005980d  cmp     eax, 0C0h
0x180059812  jnz     loc_1800596EF
0x180059818  mov     edx, 1
0x18005981d  jmp     short loc_1800597EB
0x18005981f  mov     eax, cs:CallbackContext
0x180059825  cmp     eax, 4
0x180059828  jbe     short loc_18005985B
0x18005982a  lea     rax, aThread0xXGotAQ; "Thread: 0x%x got a QUIT"
0x180059831  mov     [rsp+2B0h+var_260], r13d
0x180059836  mov     [rsp+2B0h+var_258], rax
0x18005983b  lea     rdx, byte_1801B8CF5
0x180059842  lea     rax, [rsp+2B0h+var_260]
0x180059847  mov     [rsp+2B0h+var_288], rax
0x18005984c  lea     rax, [rsp+2B0h+var_258]
0x180059851  mov     qword ptr [rsp+2B0h+bAlertable], rax
0x180059856  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005985b  mov     ebx, 834500CCh
0x180059860  jmp     loc_18005978F
0x180059865  cmp     ecx, 80h
0x18005986b  jb      short loc_180059883
0x18005986d  lea     eax, [rbx+7Fh]
0x180059870  cmp     ecx, eax
0x180059872  ja      short loc_180059883
0x180059874  lea     eax, [rcx-80h]
0x180059877  mov     ebx, 834500CAh
0x18005987c  mov     [rdi], eax
0x18005987e  jmp     loc_18005978F
0x180059883  cmp     ecx, 102h
0x180059889  jnz     short loc_18005989B
0x18005988b  mov     dword ptr [rdi], 0
0x180059891  mov     ebx, 834500CBh
0x180059896  jmp     loc_18005978F
0x18005989b  mov     eax, cs:CallbackContext
0x1800598a1  mov     ebx, 80004005h
0x1800598a6  cmp     eax, 2
0x1800598a9  jbe     loc_18005978F
0x1800598af  lea     rax, aPalSystemNonbo; "PAL_System_NonBoundThread_CondWait"
0x1800598b6  mov     [rsp+2B0h+var_260], 70Dh
0x1800598be  mov     [rsp+2B0h+var_258], rax
0x1800598c3  lea     rdx, qword_1801B8D20
0x1800598ca  lea     rax, aOnecoreTermsrv_12; "onecore\\termsrv\\rdpplatform\\common\\"...
0x1800598d1  mov     [rsp+2B0h+var_25C], ebx
0x1800598d5  mov     [rsp+2B0h+var_248], rax
0x1800598da  lea     rax, aWaitFailedWith; "Wait Failed with unknown error"
0x1800598e1  mov     [rsp+2B0h+var_250], rax
0x1800598e6  lea     rax, [rsp+2B0h+var_258]
0x1800598eb  mov     [rsp+2B0h+var_270], rax
0x1800598f0  lea     rax, [rsp+2B0h+var_260]
0x1800598f5  mov     [rsp+2B0h+var_278], rax
0x1800598fa  lea     rax, [rsp+2B0h+var_248]
0x1800598ff  mov     [rsp+2B0h+var_280], rax
0x180059904  lea     rax, [rsp+2B0h+var_25C]
0x180059909  mov     [rsp+2B0h+var_288], rax
0x18005990e  lea     rax, [rsp+2B0h+var_250]
0x180059913  mov     qword ptr [rsp+2B0h+bAlertable], rax
0x180059918  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18005991d  jmp     loc_18005978F
```
