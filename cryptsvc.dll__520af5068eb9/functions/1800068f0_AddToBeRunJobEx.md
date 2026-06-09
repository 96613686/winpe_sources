# AddToBeRunJobEx

- ea: `0x1800068f0`
- end: `0x180006a93`
- name: `AddToBeRunJobEx`
- size: `419`
- prototype: `__int64 __fastcall(FILETIME, int, _QWORD *, int)`
- caller_count: `12`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001ca0`
- `0x180002478`
- `0x180005700`
- `0x1800079d0`
- `0x1800084a0`
- `0x18000a814`
- `0x18000b420`
- `0x18000c8b4`
- `0x18000d62c`
- `0x18000f950`
- `0x18000fbec`
- `0x180010d3c`

## callees

- `0x180001e70`
- `0x180002820`
- `0x1800068f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800069a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006a03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800069a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006a03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006932`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006a1a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006932`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006a1a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006999`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006a34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006a88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006a88`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006a7a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180006a7a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180006962`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180006962`

## pseudocode

```c
__int64 __fastcall AddToBeRunJobEx(FILETIME a1, int a2, _QWORD *a3, int a4)
{
  DWORD LastError; // r14d
  unsigned int v7; // esi
  FILETIME *v8; // rbx
  FILETIME *v10; // rax
  HMODULE hLibModule; // [rsp+40h] [rbp+8h] BYREF

  LastError = 0;
  hLibModule = 0;
  v7 = 1;
  *(_OWORD *)*(_QWORD *)&a1 = 0;
  *(_OWORD *)(*(_QWORD *)&a1 + 16LL) = 0;
  if ( a3 )
    *(_QWORD *)(*(_QWORD *)&a1 + 16LL) = *a3;
  *(_DWORD *)(*(_QWORD *)&a1 + 24LL) = a2;
  EnterCriticalSection(&JobsCriticalSection);
  if ( hToBeRunJobEvent )
    goto LABEL_4;
  if ( !hToBeRunJobModule )
  {
    LeaveCriticalSection(&JobsCriticalSection);
    hLibModule = (HMODULE)DuplicateLibrary();
    EnterCriticalSection(&JobsCriticalSection);
  }
  if ( (unsigned int)CreateToBeRunJobThread(&hLibModule) || (v7 = 0, LastError = GetLastError(), !a4) )
  {
LABEL_4:
    v8 = (FILETIME *)pToBeRunJobHead;
    if ( !pToBeRunJobHead )
    {
      pToBeRunJobHead = (HLOCAL)a1;
LABEL_9:
      if ( hToBeRunJobEvent )
        SetEvent(hToBeRunJobEvent);
      goto LABEL_11;
    }
    while ( CompareFileTime((const FILETIME *)(*(_QWORD *)&a1 + 16LL), v8 + 2) >= 0 )
    {
      if ( !*(_QWORD *)v8 )
      {
        *(_QWORD *)(*(_QWORD *)&a1 + 8LL) = v8;
        *v8 = a1;
        goto LABEL_8;
      }
      v8 = (FILETIME *)*v8;
    }
    **(_QWORD **)&a1 = v8;
    *(FILETIME *)(*(_QWORD *)&a1 + 8LL) = v8[1];
    v10 = (FILETIME *)v8[1];
    if ( v10 )
      *v10 = a1;
    else
      pToBeRunJobHead = (HLOCAL)a1;
    v8[1] = a1;
LABEL_8:
    if ( *(HLOCAL *)&a1 == pToBeRunJobHead )
      goto LABEL_9;
  }
LABEL_11:
  LeaveCriticalSection(&JobsCriticalSection);
  if ( hLibModule )
    FreeLibrary(hLibModule);
  if ( !v7 )
    SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x1800068f0  push    rsi
0x1800068f2  push    r14
0x1800068f4  sub     rsp, 28h
0x1800068f8  xor     r14d, r14d
0x1800068fb  mov     [rsp+38h+arg_8], rbx
0x180006900  mov     [rsp+38h+var_18], rdi
0x180006905  xorps   xmm0, xmm0
0x180006908  mov     [rsp+38h+hLibModule], r14
0x18000690d  mov     ebx, r9d
0x180006910  mov     rdi, rcx
0x180006913  mov     esi, 1
0x180006918  movups  xmmword ptr [rcx], xmm0
0x18000691b  movups  xmmword ptr [rcx+10h], xmm0
0x18000691f  test    r8, r8
0x180006922  jnz     loc_1800069D6
0x180006928  mov     [rcx+18h], edx
0x18000692b  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180006932  call    cs:__imp_EnterCriticalSection
0x180006938  cmp     cs:?hToBeRunJobEvent@@3PEAXEA, r14; void * hToBeRunJobEvent
0x18000693f  jz      loc_1800069F3
0x180006945  mov     rbx, cs:?pToBeRunJobHead@@3PEAU_CUCS_JOB_HEADER@@EA; _CUCS_JOB_HEADER * pToBeRunJobHead
0x18000694c  test    rbx, rbx
0x18000694f  jz      loc_1800069E2
0x180006955  mov     [rsp+38h+arg_10], rbp
0x18000695a  lea     rdx, [rbx+10h]; lpFileTime2
0x18000695e  lea     rcx, [rdi+10h]; lpFileTime1
0x180006962  call    cs:__imp_CompareFileTime
0x180006968  test    eax, eax
0x18000696a  js      loc_180006A4A
0x180006970  mov     rax, [rbx]
0x180006973  test    rax, rax
0x180006976  jnz     short loc_1800069EB
0x180006978  mov     [rdi+8], rbx
0x18000697c  mov     [rbx], rdi
0x18000697f  cmp     rdi, cs:?pToBeRunJobHead@@3PEAU_CUCS_JOB_HEADER@@EA; _CUCS_JOB_HEADER * pToBeRunJobHead
0x180006986  mov     rbp, [rsp+38h+arg_10]
0x18000698b  jnz     short loc_18000699F
0x18000698d  mov     rcx, cs:?hToBeRunJobEvent@@3PEAXEA; hEvent
0x180006994  test    rcx, rcx
0x180006997  jz      short loc_18000699F
0x180006999  call    cs:__imp_SetEvent
0x18000699f  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800069a6  call    cs:__imp_LeaveCriticalSection
0x1800069ac  mov     rcx, [rsp+38h+hLibModule]; hLibModule
0x1800069b1  mov     rdi, [rsp+38h+var_18]
0x1800069b6  mov     rbx, [rsp+38h+arg_8]
0x1800069bb  test    rcx, rcx
0x1800069be  jnz     loc_180006A7A
0x1800069c4  test    esi, esi
0x1800069c6  jz      loc_180006A85
0x1800069cc  mov     eax, esi
0x1800069ce  add     rsp, 28h
0x1800069d2  pop     r14
0x1800069d4  pop     rsi
0x1800069d5  retn
0x1800069d6  mov     rax, [r8]
0x1800069d9  mov     [rcx+10h], rax
0x1800069dd  jmp     loc_180006928
0x1800069e2  mov     cs:?pToBeRunJobHead@@3PEAU_CUCS_JOB_HEADER@@EA, rdi; _CUCS_JOB_HEADER * pToBeRunJobHead
0x1800069e9  jmp     short loc_18000698D
0x1800069eb  mov     rbx, rax
0x1800069ee  jmp     loc_18000695A
0x1800069f3  cmp     cs:?hToBeRunJobModule@@3PEAUHINSTANCE__@@EA, r14; HINSTANCE__ * hToBeRunJobModule
0x1800069fa  jnz     short loc_180006A20
0x1800069fc  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180006a03  call    cs:__imp_LeaveCriticalSection
0x180006a09  call    DuplicateLibrary
0x180006a0e  lea     rcx, ?JobsCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180006a15  mov     [rsp+38h+hLibModule], rax
0x180006a1a  call    cs:__imp_EnterCriticalSection
0x180006a20  lea     rcx, [rsp+38h+hLibModule]; HINSTANCE *
0x180006a25  call    ?CreateToBeRunJobThread@@YAHPEAPEAUHINSTANCE__@@@Z; CreateToBeRunJobThread(HINSTANCE__ * *)
0x180006a2a  test    eax, eax
0x180006a2c  jnz     loc_180006945
0x180006a32  xor     esi, esi
0x180006a34  call    cs:__imp_GetLastError
0x180006a3a  mov     r14d, eax
0x180006a3d  test    ebx, ebx
0x180006a3f  jnz     loc_18000699F
0x180006a45  jmp     loc_180006945
0x180006a4a  mov     [rdi], rbx
0x180006a4d  mov     rax, [rbx+8]
0x180006a51  mov     [rdi+8], rax
0x180006a55  mov     rax, [rbx+8]
0x180006a59  test    rax, rax
0x180006a5c  jnz     short loc_180006A6E
0x180006a5e  mov     cs:?pToBeRunJobHead@@3PEAU_CUCS_JOB_HEADER@@EA, rdi; _CUCS_JOB_HEADER * pToBeRunJobHead
0x180006a65  mov     [rbx+8], rdi
0x180006a69  jmp     loc_18000697F
0x180006a6e  mov     [rax], rdi
0x180006a71  mov     [rbx+8], rdi
0x180006a75  jmp     loc_18000697F
0x180006a7a  call    cs:__imp_FreeLibrary
0x180006a80  jmp     loc_1800069C4
0x180006a85  mov     ecx, r14d; dwErrCode
0x180006a88  call    cs:__imp_SetLastError
0x180006a8e  jmp     loc_1800069CC
```
