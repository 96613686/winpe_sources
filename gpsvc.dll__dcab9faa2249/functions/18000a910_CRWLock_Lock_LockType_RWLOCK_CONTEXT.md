# CRWLock::Lock(LockType,_RWLOCK_CONTEXT * *)

- ea: `0x18000a910`
- end: `0x18000ada2`
- name: `?Lock@CRWLock@@QEAAKW4LockType@@PEAPEAU_RWLOCK_CONTEXT@@@Z`
- size: `1170`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000b764`
- `0x18000dec0`

## callees

- `0x18000a4b0`
- `0x18000a504`
- `0x18000a52c`
- `0x18000a910`
- `0x180039148`
- `0x18004dc00`
- `0x180075ec0`
- `0x1800b2738`
- `0x1800b4258`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a942`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a9fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a942`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a9fe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ab1a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000acc9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ab1a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000acc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a9c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aa73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a9c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aa73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aabb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aae1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aabb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aae1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a953`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa0f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa91`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ac79`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a953`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa0f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000aa91`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ac79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a9d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a9d8`

## string_xrefs

- `0x18000ab93`: `Reader has to wait for lock. ReaderID : %d.`
- `0x18000abd6`: `Reader has to wait for lock. ReaderID : %d.`
- `0x18000ac17`: `Writer Lock got immediately.`
- `0x18000ac49`: `Writer Lock got immediately.`
- `0x18000ad4c`: `Writer has to wait for lock. WriterID : %d.`
- `0x18000ad77`: `Writer has to wait for lock. WriterID : %d.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRWLock::Lock(int *a1, int a2, _QWORD *a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  CRWLock *v6; // rcx
  HLOCAL v7; // rdi
  struct _RWLOCK_CONTEXT *v8; // rbx
  int v9; // ecx
  __int64 v10; // rax
  int v11; // eax
  DWORD LastError; // r15d
  CRWLock *v14; // rcx
  HLOCAL v15; // r13
  int v16; // eax
  _QWORD *v17; // r13
  HANDLE EventW; // rax
  HANDLE v19; // rcx
  int v20; // eax
  HLOCAL v21; // rax
  _QWORD *v22; // rdi
  HANDLE v23; // rax
  HANDLE v24; // rcx
  _QWORD *v25; // [rsp+20h] [rbp-28h] BYREF
  struct _RWLOCK_CONTEXT *v26; // [rsp+28h] [rbp-20h] BYREF
  _QWORD *v27; // [rsp+30h] [rbp-18h] BYREF
  __int64 v28; // [rsp+38h] [rbp-10h]
  HANDLE hSourceHandle; // [rsp+A8h] [rbp+60h] BYREF

  v5 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)a1 + 9);
  if ( !a2 )
  {
    v28 = *((_QWORD *)a1 + 9);
    if ( v5 )
      EnterCriticalSection(v5);
    v7 = LocalAlloc(0x40u, 0x18u);
    v8 = (struct _RWLOCK_CONTEXT *)v7;
    v26 = (struct _RWLOCK_CONTEXT *)v7;
    if ( v7 )
    {
      v9 = ++a1[1];
      v10 = *((_QWORD *)a1 + 3);
      if ( (!v10 || !*(_QWORD *)(v10 + 8)) && a1[3] != 2 )
      {
        v11 = *a1;
        if ( !*a1 )
          a1[3] = 1;
        *a1 = v11 + 1;
        *(_DWORD *)v7 = v9;
        *((_QWORD *)v7 + 1) = 0;
LABEL_11:
        *((_DWORD *)v7 + 4) = 0;
        v8 = 0;
        *a3 = v7;
        LastError = 0;
        goto LABEL_12;
      }
      hSourceHandle = 0;
      v17 = LocalAlloc(0x40u, 0x18u);
      v25 = v17;
      if ( v17 )
      {
        EventW = CreateEventW(0, 0, 0, 0);
        XHandle::operator=(&hSourceHandle, EventW);
        v19 = hSourceHandle;
        if ( hSourceHandle )
        {
          v20 = a1[1];
          *(_DWORD *)v17 = v20;
          v17[1] = v19;
          *(_DWORD *)v7 = v20;
          LastError = DuplicateEventHandle(v19, (LPHANDLE)v7 + 1);
          if ( !LastError )
          {
            v27 = v17;
            LastError = STLWrap_List<_RWLOCK_CONTEXT *>::push_back(a1 + 4, &v27);
            if ( !LastError )
            {
              hSourceHandle = 0;
              v25 = 0;
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(4u, L"Reader has to wait for lock. ReaderID : %d.", (unsigned int)a1[1]);
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(4u, L"Reader has to wait for lock. ReaderID : %d.", (unsigned int)a1[1]);
                }
              }
              XHandle::~XHandle(&hSourceHandle);
              XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v25);
              goto LABEL_11;
            }
          }
          XHandle::~XHandle(&hSourceHandle);
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v25);
        }
        else
        {
          LastError = GetLastError();
          XHandle::~XHandle(&hSourceHandle);
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v25);
          if ( !LastError )
          {
LABEL_12:
            if ( v5 )
              LeaveCriticalSection(v5);
            goto LABEL_14;
          }
        }
      }
      else
      {
        LastError = 14;
      }
    }
    else
    {
      LastError = 14;
    }
    CRWLock::FreeLockContext(v6, &v26);
    v8 = v26;
    goto LABEL_12;
  }
  v28 = *((_QWORD *)a1 + 9);
  if ( v5 )
    EnterCriticalSection(v5);
  v15 = LocalAlloc(0x40u, 0x18u);
  v8 = (struct _RWLOCK_CONTEXT *)v15;
  v26 = (struct _RWLOCK_CONTEXT *)v15;
  if ( v15 )
  {
    v16 = ++a1[2];
    if ( !a1[3] )
    {
      a1[3] = 2;
      *(_DWORD *)v15 = v16;
      *((_QWORD *)v15 + 1) = 0;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"Writer Lock got immediately.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"Writer Lock got immediately.");
        }
      }
LABEL_22:
      *((_DWORD *)v15 + 4) = 1;
      v8 = 0;
      *a3 = v15;
      LastError = 0;
      goto LABEL_23;
    }
    v25 = 0;
    hSourceHandle = 0;
    v21 = LocalAlloc(0x40u, 0x18u);
    XPtrLF<_RWLOCK_CONTEXT>::operator=(&v25, v21);
    v22 = v25;
    if ( v25 )
    {
      v23 = CreateEventW(0, 0, 0, 0);
      XHandle::operator=(&hSourceHandle, v23);
      v24 = hSourceHandle;
      if ( !hSourceHandle )
      {
        LastError = GetLastError();
        XHandle::~XHandle(&hSourceHandle);
        XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v25);
        if ( !LastError )
          goto LABEL_23;
        goto LABEL_54;
      }
      *(_DWORD *)v22 = a1[2];
      v22[1] = v24;
      *(_DWORD *)v15 = *(_DWORD *)v22;
      LastError = DuplicateEventHandle(v24, (LPHANDLE)v15 + 1);
      if ( !LastError )
      {
        v27 = v22;
        LastError = STLWrap_List<_RWLOCK_CONTEXT *>::push_back(a1 + 6, &v27);
        if ( !LastError )
        {
          hSourceHandle = 0;
          v25 = 0;
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"Writer has to wait for lock. WriterID : %d.", (unsigned int)a1[2]);
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"Writer has to wait for lock. WriterID : %d.", (unsigned int)a1[2]);
            }
          }
          XHandle::~XHandle(&hSourceHandle);
          XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v25);
          goto LABEL_22;
        }
      }
    }
    else
    {
      LastError = 14;
    }
    XHandle::~XHandle(&hSourceHandle);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v25);
  }
  else
  {
    LastError = 14;
  }
LABEL_54:
  CRWLock::FreeLockContext(v14, &v26);
  v8 = v26;
LABEL_23:
  if ( v5 )
    LeaveCriticalSection(v5);
LABEL_14:
  if ( v8 )
    LocalFree(v8);
  return LastError;
}

```

## disassembly

```asm
0x18000a910  push    rbp
0x18000a912  push    rbx
0x18000a913  push    rsi
0x18000a914  push    rdi
0x18000a915  push    r12
0x18000a917  push    r13
0x18000a919  push    r14
0x18000a91b  push    r15
0x18000a91d  mov     rbp, rsp
0x18000a920  sub     rsp, 48h
0x18000a924  mov     r12, r8
0x18000a927  mov     r14, rcx
0x18000a92a  mov     rsi, [rcx+48h]
0x18000a92e  test    edx, edx
0x18000a930  jnz     loc_18000A9F2
0x18000a936  mov     [rbp+var_10], rsi
0x18000a93a  test    rsi, rsi
0x18000a93d  jz      short loc_18000A949
0x18000a93f  mov     rcx, rsi; lpCriticalSection
0x18000a942  call    cs:__imp_EnterCriticalSection
0x18000a948  nop
0x18000a949  mov     edx, 18h; uBytes
0x18000a94e  mov     ecx, 40h ; '@'; uFlags
0x18000a953  call    cs:__imp_LocalAlloc
0x18000a959  mov     rdi, rax
0x18000a95c  mov     rbx, rax
0x18000a95f  mov     [rbp+var_20], rax
0x18000a963  test    rax, rax
0x18000a966  jz      loc_18000AB08
0x18000a96c  inc     dword ptr [r14+4]
0x18000a970  mov     ecx, [r14+4]
0x18000a974  mov     rax, [r14+18h]
0x18000a978  test    rax, rax
0x18000a97b  jz      short loc_18000A988
0x18000a97d  cmp     qword ptr [rax+8], 0
0x18000a982  jnz     loc_18000AA7F
0x18000a988  cmp     dword ptr [r14+0Ch], 2
0x18000a98d  jz      loc_18000AA7F
0x18000a993  mov     eax, [r14]
0x18000a996  test    eax, eax
0x18000a998  jnz     short loc_18000A9A2
0x18000a99a  mov     dword ptr [r14+0Ch], 1
0x18000a9a2  inc     eax
0x18000a9a4  mov     [r14], eax
0x18000a9a7  mov     [rdi], ecx
0x18000a9a9  mov     qword ptr [rdi+8], 0
0x18000a9b1  mov     dword ptr [rdi+10h], 0
0x18000a9b8  xor     ebx, ebx
0x18000a9ba  mov     [r12], rdi
0x18000a9be  xor     r15d, r15d
0x18000a9c1  test    rsi, rsi
0x18000a9c4  jz      short loc_18000A9D0
0x18000a9c6  mov     rcx, rsi; lpCriticalSection
0x18000a9c9  call    cs:__imp_LeaveCriticalSection
0x18000a9cf  nop
0x18000a9d0  test    rbx, rbx
0x18000a9d3  jz      short loc_18000A9DE
0x18000a9d5  mov     rcx, rbx; hMem
0x18000a9d8  call    cs:__imp_LocalFree
0x18000a9de  mov     eax, r15d
0x18000a9e1  add     rsp, 48h
0x18000a9e5  pop     r15
0x18000a9e7  pop     r14
0x18000a9e9  pop     r13
0x18000a9eb  pop     r12
0x18000a9ed  pop     rdi
0x18000a9ee  pop     rsi
0x18000a9ef  pop     rbx
0x18000a9f0  pop     rbp
0x18000a9f1  retn
0x18000a9f2  mov     [rbp+var_10], rsi
0x18000a9f6  test    rsi, rsi
0x18000a9f9  jz      short loc_18000AA05
0x18000a9fb  mov     rcx, rsi; lpCriticalSection
0x18000a9fe  call    cs:__imp_EnterCriticalSection
0x18000aa04  nop
0x18000aa05  mov     edx, 18h; uBytes
0x18000aa0a  mov     ecx, 40h ; '@'; uFlags
0x18000aa0f  call    cs:__imp_LocalAlloc
0x18000aa15  mov     r13, rax
0x18000aa18  mov     rbx, rax
0x18000aa1b  mov     [rbp+var_20], rax
0x18000aa1f  test    rax, rax
0x18000aa22  jz      loc_18000AC00
0x18000aa28  inc     dword ptr [r14+8]
0x18000aa2c  mov     eax, [r14+8]
0x18000aa30  cmp     dword ptr [r14+0Ch], 0
0x18000aa35  jnz     loc_18000AC5F
0x18000aa3b  mov     dword ptr [r14+0Ch], 2
0x18000aa43  mov     [rbx], eax
0x18000aa45  mov     qword ptr [rbx+8], 0
0x18000aa4d  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18000aa54  jnz     loc_18000AC0B
0x18000aa5a  mov     dword ptr [r13+10h], 1
0x18000aa62  xor     ebx, ebx
0x18000aa64  mov     [r12], r13
0x18000aa68  xor     r15d, r15d
0x18000aa6b  test    rsi, rsi
0x18000aa6e  jz      short loc_18000AA7A
0x18000aa70  mov     rcx, rsi; lpCriticalSection
0x18000aa73  call    cs:__imp_LeaveCriticalSection
0x18000aa79  nop
0x18000aa7a  jmp     loc_18000A9D0
0x18000aa7f  mov     [rbp+hSourceHandle], 0
0x18000aa87  mov     edx, 18h; uBytes
0x18000aa8c  mov     ecx, 40h ; '@'; uFlags
0x18000aa91  call    cs:__imp_LocalAlloc
0x18000aa97  mov     r13, rax
0x18000aa9a  mov     [rbp+var_28], rax
0x18000aa9e  test    rax, rax
0x18000aaa1  jnz     short loc_18000AB10
0x18000aaa3  mov     r15d, 0Eh
0x18000aaa9  lea     rdx, [rbp+var_20]; struct _RWLOCK_CONTEXT **
0x18000aaad  call    ?FreeLockContext@CRWLock@@AEAAXPEAPEAU_RWLOCK_CONTEXT@@@Z; CRWLock::FreeLockContext(_RWLOCK_CONTEXT * *)
0x18000aab2  mov     rbx, [rbp+var_20]
0x18000aab6  jmp     loc_18000A9C1
0x18000aabb  call    cs:__imp_GetLastError
0x18000aac1  mov     r15d, eax
0x18000aac4  lea     rcx, [rbp+hSourceHandle]; this
0x18000aac8  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x18000aacd  nop
0x18000aace  lea     rcx, [rbp+var_28]
0x18000aad2  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18000aad7  test    r15d, r15d
0x18000aada  jz      short loc_18000AA6B
0x18000aadc  jmp     loc_18000ACAD
0x18000aae1  call    cs:__imp_GetLastError
0x18000aae7  mov     r15d, eax
0x18000aaea  lea     rcx, [rbp+hSourceHandle]; this
0x18000aaee  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x18000aaf3  nop
0x18000aaf4  lea     rcx, [rbp+var_28]
0x18000aaf8  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18000aafd  test    r15d, r15d
0x18000ab00  jz      loc_18000A9C1
0x18000ab06  jmp     short loc_18000AAA9
0x18000ab08  mov     r15d, 0Eh
0x18000ab0e  jmp     short loc_18000AAA9
0x18000ab10  xor     r9d, r9d; lpName
0x18000ab13  xor     r8d, r8d; bInitialState
0x18000ab16  xor     edx, edx; bManualReset
0x18000ab18  xor     ecx, ecx; lpEventAttributes
0x18000ab1a  call    cs:__imp_CreateEventW
0x18000ab20  mov     rdx, rax
0x18000ab23  lea     rcx, [rbp+hSourceHandle]
0x18000ab27  call    ??4XHandle@@QEAAXPEAX@Z; XHandle::operator=(void *)
0x18000ab2c  mov     rcx, [rbp+hSourceHandle]; hSourceHandle
0x18000ab30  test    rcx, rcx
0x18000ab33  jz      short loc_18000AAE1
0x18000ab35  mov     eax, [r14+4]
0x18000ab39  mov     [r13+0], eax
0x18000ab3d  mov     [r13+8], rcx
0x18000ab41  mov     [rdi], eax
0x18000ab43  lea     rdx, [rdi+8]; lpTargetHandle
0x18000ab47  call    ?DuplicateEventHandle@@YAKPEAXPEAPEAX@Z; DuplicateEventHandle(void *,void * *)
0x18000ab4c  mov     r15d, eax
0x18000ab4f  test    eax, eax
0x18000ab51  jnz     short loc_18000ABA6
0x18000ab53  mov     [rbp+var_18], r13
0x18000ab57  lea     rcx, [r14+10h]
0x18000ab5b  lea     rdx, [rbp+var_18]
0x18000ab5f  call    ?push_back@?$STLWrap_List@PEAU_RWLOCK_CONTEXT@@@@QEAAKAEBQEAU_RWLOCK_CONTEXT@@@Z; STLWrap_List<_RWLOCK_CONTEXT *>::push_back(_RWLOCK_CONTEXT * const &)
0x18000ab64  mov     r15d, eax
0x18000ab67  test    eax, eax
0x18000ab69  jnz     short loc_18000ABA6
0x18000ab6b  mov     [rbp+hSourceHandle], 0
0x18000ab73  mov     [rbp+var_28], 0
0x18000ab7b  cmp     cs:?g_dwDebugLevel@@3KA, eax; ulong g_dwDebugLevel
0x18000ab81  jz      short loc_18000ABE8
0x18000ab83  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000ab8a  test    rax, rax
0x18000ab8d  jz      short loc_18000ABBE
0x18000ab8f  mov     r8d, [r14+4]
0x18000ab93  lea     rdx, aReaderHasToWai; "Reader has to wait for lock. ReaderID :"...
0x18000ab9a  mov     ecx, 4
0x18000ab9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aba4  jmp     short loc_18000ABE8
0x18000aba6  lea     rcx, [rbp+hSourceHandle]; this
0x18000abaa  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x18000abaf  nop
0x18000abb0  lea     rcx, [rbp+var_28]
0x18000abb4  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18000abb9  jmp     loc_18000AAA9
0x18000abbe  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18000abc6  jz      short loc_18000ABE8
0x18000abc8  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000abd0  jz      short loc_18000ABE8
0x18000abd2  mov     r8d, [r14+4]
0x18000abd6  lea     rdx, aReaderHasToWai; "Reader has to wait for lock. ReaderID :"...
0x18000abdd  mov     ecx, 4; unsigned int
0x18000abe2  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18000abe7  nop
0x18000abe8  lea     rcx, [rbp+hSourceHandle]; this
0x18000abec  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x18000abf1  nop
0x18000abf2  lea     rcx, [rbp+var_28]
0x18000abf6  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18000abfb  jmp     loc_18000A9B1
0x18000ac00  mov     r15d, 0Eh
0x18000ac06  jmp     loc_18000ACAD
0x18000ac0b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000ac12  test    rax, rax
0x18000ac15  jz      short loc_18000AC2D
0x18000ac17  lea     rdx, aWriterLockGotI; "Writer Lock got immediately."
0x18000ac1e  mov     ecx, 4
0x18000ac23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac28  jmp     loc_18000AA5A
0x18000ac2d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18000ac35  jz      loc_18000AA5A
0x18000ac3b  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000ac43  jz      loc_18000AA5A
0x18000ac49  lea     rdx, aWriterLockGotI; "Writer Lock got immediately."
0x18000ac50  mov     ecx, 4; unsigned int
0x18000ac55  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18000ac5a  jmp     loc_18000AA5A
0x18000ac5f  mov     [rbp+var_28], 0
0x18000ac67  mov     [rbp+hSourceHandle], 0
0x18000ac6f  mov     edx, 18h; uBytes
0x18000ac74  mov     ecx, 40h ; '@'; uFlags
0x18000ac79  call    cs:__imp_LocalAlloc
0x18000ac7f  mov     rdx, rax
0x18000ac82  lea     rcx, [rbp+var_28]
0x18000ac86  call    ??4?$XPtrLF@U_RWLOCK_CONTEXT@@@@QEAAPEAU_RWLOCK_CONTEXT@@PEAU1@@Z; XPtrLF<_RWLOCK_CONTEXT>::operator=(_RWLOCK_CONTEXT *)
0x18000ac8b  mov     rdi, [rbp+var_28]
0x18000ac8f  test    rdi, rdi
0x18000ac92  jnz     short loc_18000ACBF
0x18000ac94  mov     r15d, 0Eh
0x18000ac9a  lea     rcx, [rbp+hSourceHandle]; this
0x18000ac9e  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x18000aca3  nop
0x18000aca4  lea     rcx, [rbp+var_28]
0x18000aca8  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18000acad  lea     rdx, [rbp+var_20]; struct _RWLOCK_CONTEXT **
0x18000acb1  call    ?FreeLockContext@CRWLock@@AEAAXPEAPEAU_RWLOCK_CONTEXT@@@Z; CRWLock::FreeLockContext(_RWLOCK_CONTEXT * *)
0x18000acb6  mov     rbx, [rbp+var_20]
0x18000acba  jmp     loc_18000AA6B
0x18000acbf  xor     r9d, r9d; lpName
0x18000acc2  xor     r8d, r8d; bInitialState
0x18000acc5  xor     edx, edx; bManualReset
0x18000acc7  xor     ecx, ecx; lpEventAttributes
0x18000acc9  call    cs:__imp_CreateEventW
0x18000accf  mov     rdx, rax
0x18000acd2  lea     rcx, [rbp+hSourceHandle]
0x18000acd6  call    ??4XHandle@@QEAAXPEAX@Z; XHandle::operator=(void *)
0x18000acdb  mov     rcx, [rbp+hSourceHandle]; hSourceHandle
0x18000acdf  test    rcx, rcx
0x18000ace2  jz      loc_18000AABB
0x18000ace8  mov     eax, [r14+8]
0x18000acec  mov     [rdi], eax
0x18000acee  mov     [rdi+8], rcx
0x18000acf2  mov     eax, [rdi]
0x18000acf4  mov     [r13+0], eax
0x18000acf8  lea     rdx, [r13+8]; lpTargetHandle
0x18000acfc  call    ?DuplicateEventHandle@@YAKPEAXPEAPEAX@Z; DuplicateEventHandle(void *,void * *)
0x18000ad01  mov     r15d, eax
0x18000ad04  test    eax, eax
0x18000ad06  jnz     short loc_18000AC9A
0x18000ad08  mov     [rbp+var_18], rdi
0x18000ad0c  lea     rcx, [r14+18h]
0x18000ad10  lea     rdx, [rbp+var_18]
0x18000ad14  call    ?push_back@?$STLWrap_List@PEAU_RWLOCK_CONTEXT@@@@QEAAKAEBQEAU_RWLOCK_CONTEXT@@@Z; STLWrap_List<_RWLOCK_CONTEXT *>::push_back(_RWLOCK_CONTEXT * const &)
0x18000ad19  mov     r15d, eax
0x18000ad1c  test    eax, eax
0x18000ad1e  jnz     loc_18000AC9A
0x18000ad24  mov     [rbp+hSourceHandle], 0
0x18000ad2c  mov     [rbp+var_28], 0
0x18000ad34  cmp     cs:?g_dwDebugLevel@@3KA, eax; ulong g_dwDebugLevel
0x18000ad3a  jz      short loc_18000AD89
0x18000ad3c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000ad43  test    rax, rax
0x18000ad46  jz      short loc_18000AD5F
0x18000ad48  mov     r8d, [r14+8]
0x18000ad4c  lea     rdx, aWriterHasToWai; "Writer has to wait for lock. WriterID :"...
0x18000ad53  mov     ecx, 4
0x18000ad58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad5d  jmp     short loc_18000AD89
0x18000ad5f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18000ad67  jz      short loc_18000AD89
0x18000ad69  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18000ad71  jz      short loc_18000AD89
0x18000ad73  mov     r8d, [r14+8]
0x18000ad77  lea     rdx, aWriterHasToWai; "Writer has to wait for lock. WriterID :"...
0x18000ad7e  mov     ecx, 4; unsigned int
0x18000ad83  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18000ad88  nop
0x18000ad89  lea     rcx, [rbp+hSourceHandle]; this
0x18000ad8d  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x18000ad92  nop
0x18000ad93  lea     rcx, [rbp+var_28]
0x18000ad97  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18000ad9c  jmp     loc_18000AA5A
```
