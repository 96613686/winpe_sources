# CGPApplicationService::UnLockPolicySection(void *)

- ea: `0x180006f70`
- end: `0x18000734a`
- name: `?UnLockPolicySection@CGPApplicationService@@UEAAKPEAX@Z`
- size: `986`
- prototype: `unsigned int(CGPApplicationService *__hidden this, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180006f70`
- `0x180007350`
- `0x180007e00`
- `0x18000a504`
- `0x180075ec0`
- `0x18007d304`
- `0x18007d6f0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006fcf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006fcf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006fa6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006fa6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800070db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800070db`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800071e8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007229`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800071e8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007229`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007000`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007000`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800070d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800070d1`

## string_xrefs

- `0x180007250`: `WaitForServiceInitialization: Event is null.`
- `0x18000727e`: `WaitForServiceInitialization: Event is null.`
- `0x1800072aa`: `CPolicyCriticalSectionCollection: Deleting critical section for UserSid <%ws>`
- `0x1800072db`: `CPolicyCriticalSectionCollection: Deleting critical section for UserSid <%ws>`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CGPApplicationService::UnLockPolicySection(CGPApplicationService *this, _QWORD *a2)
{
  void *v4; // rcx
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  WCHAR *lpString2; // rsi
  __int64 v7; // rbx
  unsigned __int64 v8; // rbx
  WCHAR *v9; // rax
  __int64 v10; // rcx
  WCHAR *v11; // rdx
  WCHAR v12; // r8
  WCHAR *v13; // rcx
  __int64 **v14; // rbx
  __int64 *v15; // rbx
  __int64 **v16; // rax
  __int64 *v17; // rax
  const WCHAR *v18; // r8
  bool v19; // zf
  __int64 v20; // rbp
  unsigned int v21; // ebx
  void **v23; // rbx
  _QWORD *v24; // rbx
  void **v25; // rax
  _QWORD *v26; // rax
  const WCHAR *v27; // r8
  bool v28; // zf
  void *v29; // rbp
  __int64 v30; // rdx
  WCHAR *v31; // [rsp+70h] [rbp+8h] BYREF
  __int64 v32; // [rsp+78h] [rbp+10h]

  v4 = (void *)*((_QWORD *)this + 44);
  if ( v4 )
  {
    WaitForSingleObject(v4, 0xFFFFFFFF);
  }
  else if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"WaitForServiceInitialization: Event is null.");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"WaitForServiceInitialization: Event is null.");
    }
  }
  if ( (*((_BYTE *)a2 + 12) & 0x20) != 0 )
    return AccountPolicyCriticalSection::UnLock(*((AccountPolicyCriticalSection **)this + 35), a2);
  v5 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 24);
  if ( !v5 )
    return 87;
  v32 = *((_QWORD *)this + 24);
  EnterCriticalSection(v5);
  lpString2 = 0;
  v31 = 0;
  if ( *a2 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(*a2 + 2 * v7) );
    v8 = v7 + 1;
    v9 = (WCHAR *)LocalAlloc(0x40u, 2 * v8);
    lpString2 = v9;
    v31 = v9;
    if ( !v9 )
    {
      v21 = 14;
      goto LABEL_30;
    }
    if ( v8 )
    {
      if ( v8 > 0x7FFFFFFF )
      {
        *v9 = 0;
      }
      else
      {
        v10 = 2147483646;
        v11 = (WCHAR *)*a2;
        do
        {
          if ( !v10 )
            break;
          v12 = *v11;
          if ( !*v11 )
            break;
          ++v11;
          *v9++ = v12;
          --v10;
          --v8;
        }
        while ( v8 );
        v13 = v9 - 1;
        if ( v8 )
          v13 = v9;
        *v13 = 0;
      }
    }
  }
  v14 = (__int64 **)*((_QWORD *)this + 25);
  if ( !v14 )
  {
LABEL_69:
    v21 = 0;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CPolicyCriticalSectionCollection: Did not find the critical section");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CPolicyCriticalSectionCollection: Did not find the critical section");
      }
    }
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v31);
    goto LABEL_30;
  }
  v15 = *v14;
  while ( 1 )
  {
    v15 = (__int64 *)*v15;
    v16 = (__int64 **)*((_QWORD *)this + 25);
    if ( v16 )
      v17 = *v16;
    else
      v17 = 0;
    if ( v15 == v17 )
      goto LABEL_69;
    v18 = *(const WCHAR **)v15[2];
    if ( !lpString2 )
    {
      v19 = v18 == 0;
      goto LABEL_25;
    }
    if ( v18 )
    {
      v19 = CompareStringW(0x7Fu, 1u, v18, -1, lpString2, -1) == 2;
LABEL_25:
      if ( v19 )
        break;
    }
  }
  v20 = v15[2];
  if ( !v20 )
    goto LABEL_69;
  v21 = AccountPolicyCriticalSection::UnLock((AccountPolicyCriticalSection *)v15[2], a2);
  if ( !v21 && !*(_DWORD *)(v20 + 24) && !*(_DWORD *)(v20 + 120) )
  {
    v23 = (void **)*((_QWORD *)this + 25);
    if ( v23 )
    {
      v24 = *v23;
      while ( 1 )
      {
        while ( 1 )
        {
          v24 = (_QWORD *)*v24;
          v25 = (void **)*((_QWORD *)this + 25);
          if ( v25 )
            v26 = *v25;
          else
            v26 = 0;
          if ( v24 == v26 )
            goto LABEL_40;
          v27 = *(const WCHAR **)v24[2];
          if ( lpString2 )
            break;
          v28 = v27 == 0;
LABEL_44:
          if ( v28 )
          {
            if ( *(_DWORD *)&g_dwDebugLevel )
            {
              if ( g_lpDebugMsg )
              {
                g_lpDebugMsg(
                  4u,
                  L"CPolicyCriticalSectionCollection: Deleting critical section for UserSid <%ws>",
                  lpString2);
              }
              else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
              {
                RedirectDebugMsg(
                  4u,
                  L"CPolicyCriticalSectionCollection: Deleting critical section for UserSid <%ws>",
                  lpString2);
              }
            }
            v29 = (void *)v24[2];
            if ( v29 )
            {
              AccountPolicyCriticalSection::~AccountPolicyCriticalSection((AccountPolicyCriticalSection *)v24[2]);
              operator delete(v29);
            }
            v30 = *((_QWORD *)this + 25);
            if ( v30 )
            {
              *(_QWORD *)v24[1] = *v24;
              *(_QWORD *)(*v24 + 8LL) = v24[1];
              --*(_QWORD *)(v30 + 8);
              operator delete(v24);
            }
            goto LABEL_40;
          }
        }
        if ( v27 )
        {
          v28 = CompareStringW(0x7Fu, 1u, v27, -1, lpString2, -1) == 2;
          goto LABEL_44;
        }
      }
    }
LABEL_40:
    v21 = 0;
  }
  if ( lpString2 )
    LocalFree(lpString2);
LABEL_30:
  LeaveCriticalSection(v5);
  return v21;
}

```

## disassembly

```asm
0x180006f70  mov     [rsp+arg_10], rbx
0x180006f75  push    rbp
0x180006f76  push    rsi
0x180006f77  push    rdi
0x180006f78  push    r12
0x180006f7a  push    r13
0x180006f7c  push    r14
0x180006f7e  push    r15
0x180006f80  sub     rsp, 30h
0x180006f84  mov     r15, rdx
0x180006f87  mov     r14, rcx
0x180006f8a  mov     rcx, [rcx+160h]; hHandle
0x180006f91  mov     r13d, 4
0x180006f97  xor     r12d, r12d
0x180006f9a  test    rcx, rcx
0x180006f9d  jz      loc_180007237
0x180006fa3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006fa6  call    cs:__imp_WaitForSingleObject
0x180006fac  test    byte ptr [r15+0Ch], 20h
0x180006fb1  jnz     loc_1800070FB
0x180006fb7  mov     rdi, [r14+0C0h]
0x180006fbe  test    rdi, rdi
0x180006fc1  jz      loc_1800071FE
0x180006fc7  mov     [rsp+68h+arg_8], rdi
0x180006fcc  mov     rcx, rdi; lpCriticalSection
0x180006fcf  call    cs:__imp_EnterCriticalSection
0x180006fd5  nop
0x180006fd6  mov     rsi, r12
0x180006fd9  mov     [rsp+68h+arg_0], r12
0x180006fde  mov     rax, [r15]
0x180006fe1  test    rax, rax
0x180006fe4  jz      short loc_180007064
0x180006fe6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006fea  inc     rbx
0x180006fed  cmp     [rax+rbx*2], r12w
0x180006ff2  jnz     short loc_180006FEA
0x180006ff4  inc     rbx
0x180006ff7  lea     rdx, [rbx+rbx]; uBytes
0x180006ffb  mov     ecx, 40h ; '@'; uFlags
0x180007000  call    cs:__imp_LocalAlloc
0x180007006  mov     rsi, rax
0x180007009  mov     [rsp+68h+arg_0], rax
0x18000700e  test    rax, rax
0x180007011  jz      loc_180007149
0x180007017  test    rbx, rbx
0x18000701a  jz      short loc_180007064
0x18000701c  cmp     rbx, 7FFFFFFFh
0x180007023  ja      loc_180007292
0x180007029  mov     ecx, 7FFFFFFEh
0x18000702e  mov     rdx, [r15]
0x180007031  test    rcx, rcx
0x180007034  jz      short loc_180007055
0x180007036  movzx   r8d, word ptr [rdx]
0x18000703a  test    r8w, r8w
0x18000703e  jz      short loc_180007055
0x180007040  add     rdx, 2
0x180007044  mov     [rax], r8w
0x180007048  add     rax, 2
0x18000704c  dec     rcx
0x18000704f  sub     rbx, 1
0x180007053  jnz     short loc_180007031
0x180007055  lea     rcx, [rax-2]
0x180007059  test    rbx, rbx
0x18000705c  cmovnz  rcx, rax
0x180007060  mov     [rcx], r12w
0x180007064  mov     rbx, [r14+0C8h]
0x18000706b  test    rbx, rbx
0x18000706e  jz      loc_1800072EF
0x180007074  mov     rbx, [rbx]
0x180007077  mov     rbx, [rbx]
0x18000707a  mov     rax, [r14+0C8h]
0x180007081  test    rax, rax
0x180007084  jz      loc_1800071BF
0x18000708a  mov     rax, [rax]
0x18000708d  cmp     rbx, rax
0x180007090  jz      loc_1800072EF
0x180007096  mov     rax, [rbx+10h]
0x18000709a  mov     r8, [rax]; lpString1
0x18000709d  test    rsi, rsi
0x1800070a0  jnz     loc_1800071C7
0x1800070a6  test    r8, r8
0x1800070a9  jnz     short loc_180007077
0x1800070ab  mov     rbp, [rbx+10h]
0x1800070af  test    rbp, rbp
0x1800070b2  jz      loc_1800072EF
0x1800070b8  mov     rdx, r15; void *
0x1800070bb  mov     rcx, rbp; this
0x1800070be  call    ?UnLock@AccountPolicyCriticalSection@@QEAAKPEAX@Z; AccountPolicyCriticalSection::UnLock(void *)
0x1800070c3  mov     ebx, eax
0x1800070c5  test    eax, eax
0x1800070c7  jz      short loc_18000710E
0x1800070c9  test    rsi, rsi
0x1800070cc  jz      short loc_1800070D8
0x1800070ce  mov     rcx, rsi; hMem
0x1800070d1  call    cs:__imp_LocalFree
0x1800070d7  nop
0x1800070d8  mov     rcx, rdi; lpCriticalSection
0x1800070db  call    cs:__imp_LeaveCriticalSection
0x1800070e1  mov     eax, ebx
0x1800070e3  mov     rbx, [rsp+68h+arg_10]
0x1800070eb  add     rsp, 30h
0x1800070ef  pop     r15
0x1800070f1  pop     r14
0x1800070f3  pop     r13
0x1800070f5  pop     r12
0x1800070f7  pop     rdi
0x1800070f8  pop     rsi
0x1800070f9  pop     rbp
0x1800070fa  retn
0x1800070fb  mov     rdx, r15; void *
0x1800070fe  mov     rcx, [r14+118h]; this
0x180007105  call    ?UnLock@AccountPolicyCriticalSection@@QEAAKPEAX@Z; AccountPolicyCriticalSection::UnLock(void *)
0x18000710a  mov     ebx, eax
0x18000710c  jmp     short loc_1800070E1
0x18000710e  cmp     [rbp+18h], r12d
0x180007112  jnz     short loc_1800070C9
0x180007114  cmp     [rbp+78h], r12d
0x180007118  jnz     short loc_1800070C9
0x18000711a  mov     rbx, [r14+0C8h]
0x180007121  test    rbx, rbx
0x180007124  jz      short loc_180007144
0x180007126  mov     rbx, [rbx]
0x180007129  mov     rbx, [rbx]
0x18000712c  mov     rax, [r14+0C8h]
0x180007133  test    rax, rax
0x180007136  jz      loc_1800071F6
0x18000713c  mov     rax, [rax]
0x18000713f  cmp     rbx, rax
0x180007142  jnz     short loc_180007150
0x180007144  mov     ebx, r12d
0x180007147  jmp     short loc_1800070C9
0x180007149  mov     ebx, 0Eh
0x18000714e  jmp     short loc_1800070D8
0x180007150  mov     rax, [rbx+10h]
0x180007154  mov     r8, [rax]; lpString1
0x180007157  test    rsi, rsi
0x18000715a  jnz     loc_180007208
0x180007160  test    r8, r8
0x180007163  jnz     short loc_180007129
0x180007165  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18000716c  jnz     loc_18000729B
0x180007172  mov     rbp, [rbx+10h]
0x180007176  test    rbp, rbp
0x180007179  jz      short loc_180007190
0x18000717b  mov     rcx, rbp; this
0x18000717e  call    ??1AccountPolicyCriticalSection@@QEAA@XZ; AccountPolicyCriticalSection::~AccountPolicyCriticalSection(void)
0x180007183  mov     edx, 0D0h
0x180007188  mov     rcx, rbp; Block
0x18000718b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007190  mov     rdx, [r14+0C8h]
0x180007197  test    rdx, rdx
0x18000719a  jz      short loc_180007144
0x18000719c  mov     rcx, [rbx+8]
0x1800071a0  mov     rax, [rbx]
0x1800071a3  mov     [rcx], rax
0x1800071a6  mov     rcx, [rbx]
0x1800071a9  mov     rax, [rbx+8]
0x1800071ad  mov     [rcx+8], rax
0x1800071b1  dec     qword ptr [rdx+8]
0x1800071b5  mov     rcx, rbx; Block
0x1800071b8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800071bd  jmp     short loc_180007144
0x1800071bf  mov     rax, r12
0x1800071c2  jmp     loc_18000708D
0x1800071c7  test    r8, r8
0x1800071ca  jz      loc_180007077
0x1800071d0  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800071d8  mov     [rsp+68h+lpString2], rsi; lpString2
0x1800071dd  or      r9d, 0FFFFFFFFh; cchCount1
0x1800071e1  lea     edx, [r9+2]; dwCmpFlags
0x1800071e5  lea     ecx, [rdx+7Eh]; Locale
0x1800071e8  call    cs:__imp_CompareStringW
0x1800071ee  cmp     eax, 2
0x1800071f1  jmp     loc_1800070A9
0x1800071f6  mov     rax, r12
0x1800071f9  jmp     loc_18000713F
0x1800071fe  mov     ebx, 57h ; 'W'
0x180007203  jmp     loc_1800070E1
0x180007208  test    r8, r8
0x18000720b  jz      loc_180007129
0x180007211  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x180007219  mov     [rsp+68h+lpString2], rsi; lpString2
0x18000721e  or      r9d, 0FFFFFFFFh; cchCount1
0x180007222  lea     edx, [r9+2]; dwCmpFlags
0x180007226  lea     ecx, [rdx+7Eh]; Locale
0x180007229  call    cs:__imp_CompareStringW
0x18000722f  cmp     eax, 2
0x180007232  jmp     loc_180007163
0x180007237  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x18000723e  jz      loc_180006FAC
0x180007244  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18000724b  test    rax, rax
0x18000724e  jz      short loc_180007264
0x180007250  lea     rdx, aWaitforservice; "WaitForServiceInitialization: Event is "...
0x180007257  mov     ecx, r13d
0x18000725a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000725f  jmp     loc_180006FAC
0x180007264  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18000726b  jz      loc_180006FAC
0x180007271  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180007278  jz      loc_180006FAC
0x18000727e  lea     rdx, aWaitforservice; "WaitForServiceInitialization: Event is "...
0x180007285  mov     ecx, r13d; unsigned int
0x180007288  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18000728d  jmp     loc_180006FAC
0x180007292  mov     [rax], r12w
0x180007296  jmp     loc_180007064
0x18000729b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800072a2  test    rax, rax
0x1800072a5  jz      short loc_1800072BE
0x1800072a7  mov     r8, rsi
0x1800072aa  lea     rdx, aCpolicycritica_1; "CPolicyCriticalSectionCollection: Delet"...
0x1800072b1  mov     ecx, r13d
0x1800072b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072b9  jmp     loc_180007172
0x1800072be  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800072c5  jz      loc_180007172
0x1800072cb  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800072d2  jz      loc_180007172
0x1800072d8  mov     r8, rsi
0x1800072db  lea     rdx, aCpolicycritica_1; "CPolicyCriticalSectionCollection: Delet"...
0x1800072e2  mov     ecx, r13d; unsigned int
0x1800072e5  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800072ea  jmp     loc_180007172
0x1800072ef  mov     ebx, r12d
0x1800072f2  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x1800072f9  jz      short loc_18000733A
0x1800072fb  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180007302  test    rax, rax
0x180007305  jz      short loc_180007318
0x180007307  lea     rdx, aCpolicycritica; "CPolicyCriticalSectionCollection: Did n"...
0x18000730e  mov     ecx, r13d
0x180007311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007316  jmp     short loc_18000733A
0x180007318  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18000731f  jz      short loc_18000733A
0x180007321  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180007328  jz      short loc_18000733A
0x18000732a  lea     rdx, aCpolicycritica; "CPolicyCriticalSectionCollection: Did n"...
0x180007331  mov     ecx, r13d; unsigned int
0x180007334  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180007339  nop
0x18000733a  lea     rcx, [rsp+68h+arg_0]
0x18000733f  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x180007344  jmp     loc_1800070D8
```
