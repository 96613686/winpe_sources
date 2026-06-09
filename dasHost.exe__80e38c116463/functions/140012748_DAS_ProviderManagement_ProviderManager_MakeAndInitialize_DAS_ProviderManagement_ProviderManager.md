# DAS::ProviderManagement::ProviderManager::MakeAndInitialize(DAS::ProviderManagement::ProviderManager * *)

- ea: `0x140012748`
- end: `0x140012897`
- name: `?MakeAndInitialize@ProviderManager@ProviderManagement@DAS@@SAJPEAPEAV123@@Z`
- size: `335`
- prototype: `__int64 __fastcall(struct DAS::ProviderManagement::ProviderManager **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x140010928`

## callees

- `0x1400018d4`
- `0x14000190c`
- `0x1400020d0`
- `0x14000217c`
- `0x1400021f0`
- `0x140006cc4`
- `0x140006ce4`
- `0x1400107b0`
- `0x140012748`
- `0x140012c08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140012801`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140012801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012817`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012817`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001282a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001282a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012822`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140012822`

## pseudocode

```c
__int64 __fastcall DAS::ProviderManagement::ProviderManager::MakeAndInitialize(
        struct DAS::ProviderManagement::ProviderManager **a1)
{
  char *v2; // rax
  char *v3; // rdi
  _QWORD *v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  HANDLE EventW; // rsi
  const char *v8; // r9
  void *v9; // rbp
  DWORD LastError; // ebx
  int v12; // [rsp+20h] [rbp-48h]
  int v13; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = (char *)operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( v2 )
  {
    memset_0(v2, 0, 0x80u);
    v3[16] = 1;
    v4 = operator new(0x50u);
    *v4 = v4;
    v4[1] = v4;
    v4[2] = v4;
    *((_WORD *)v4 + 12) = 257;
    *((_QWORD *)v3 + 4) = v4;
    `eh vector constructor iterator'(
      v3 + 48,
      0x28u,
      2u,
      (void (*)(void *))DAS::ProviderManagement::ProviderManager::_REG_CHANGE_CONTEXT::_REG_CHANGE_CONTEXT,
      (void (*)(void *))DAS::ProviderManagement::ProviderManager::_REG_CHANGE_CONTEXT::~_REG_CHANGE_CONTEXT);
    v5 = DAS::ProviderManagement::ProviderManager::ProcessRegChange((DAS::ProviderManagement::ProviderManager *)v3);
    v6 = v5;
    if ( v5 >= 0 )
    {
      EventW = CreateEventW(0, 1, 0, 0);
      v9 = *(void **)v3;
      if ( (unsigned __int64)(*(_QWORD *)v3 - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        CloseHandle(v9);
        SetLastError(LastError);
      }
      *(_QWORD *)v3 = EventW;
      if ( EventW )
      {
        *a1 = (struct DAS::ProviderManagement::ProviderManager *)v3;
        return 0;
      }
      v6 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x35,
             (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
             v8);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
        (const char *)(unsigned int)v5,
        v13);
    }
    DAS::ProviderManagement::ProviderManager::~ProviderManager((DAS::ProviderManagement::ProviderManager *)v3);
    operator delete(v3);
  }
  else
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
      (const char *)0x8007000ELL,
      v12);
  }
  return v6;
}

```

## disassembly

```asm
0x140012748  push    rbx
0x14001274a  push    rbp
0x14001274b  push    rsi
0x14001274c  push    rdi
0x14001274d  push    r14
0x14001274f  push    r15
0x140012751  sub     rsp, 38h
0x140012755  mov     r14, rcx
0x140012758  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001275f  mov     r15d, 80h
0x140012765  mov     ecx, r15d; unsigned __int64
0x140012768  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001276d  mov     rdi, rax
0x140012770  test    rax, rax
0x140012773  jz      loc_14001286A
0x140012779  mov     r8d, r15d; Size
0x14001277c  xor     edx, edx; Val
0x14001277e  mov     rcx, rax; void *
0x140012781  call    memset_0
0x140012786  mov     byte ptr [rdi+10h], 1
0x14001278a  lea     ecx, [r15-30h]; Size
0x14001278e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140012793  mov     [rax], rax
0x140012796  mov     [rax+8], rax
0x14001279a  mov     [rax+10h], rax
0x14001279e  mov     word ptr [rax+18h], 101h
0x1400127a4  mov     [rdi+20h], rax
0x1400127a8  lea     rcx, [rdi+30h]; void *
0x1400127ac  lea     rax, ??1_REG_CHANGE_CONTEXT@ProviderManager@ProviderManagement@DAS@@QEAA@XZ; DAS::ProviderManagement::ProviderManager::_REG_CHANGE_CONTEXT::~_REG_CHANGE_CONTEXT(void)
0x1400127b3  mov     qword ptr [rsp+68h+var_48], rax; int
0x1400127b8  lea     r9, ??0_REG_CHANGE_CONTEXT@ProviderManager@ProviderManagement@DAS@@QEAA@XZ; void (*)(void *)
0x1400127bf  lea     edx, [r15-58h]; unsigned __int64
0x1400127c3  lea     r8d, [r15-7Eh]; unsigned __int64
0x1400127c7  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1400127cc  nop
0x1400127cd  mov     rcx, rdi; this
0x1400127d0  call    ?ProcessRegChange@ProviderManager@ProviderManagement@DAS@@QEAAJXZ; DAS::ProviderManagement::ProviderManager::ProcessRegChange(void)
0x1400127d5  mov     ebx, eax
0x1400127d7  test    eax, eax
0x1400127d9  jns     short loc_1400127F5
0x1400127db  mov     rcx, [rsp+68h]; this
0x1400127e0  mov     r9d, eax; char *
0x1400127e3  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x1400127ea  lea     edx, [r15-57h]; void *
0x1400127ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400127f3  jmp     short loc_14001284E
0x1400127f5  xor     r9d, r9d; lpName
0x1400127f8  xor     r8d, r8d; bInitialState
0x1400127fb  lea     edx, [r9+1]; bManualReset
0x1400127ff  xor     ecx, ecx; lpEventAttributes
0x140012801  call    cs:__imp_CreateEventW
0x140012807  mov     rsi, rax
0x14001280a  mov     rbp, [rdi]
0x14001280d  lea     rdx, [rbp-1]
0x140012811  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140012815  ja      short loc_140012830
0x140012817  call    cs:__imp_GetLastError
0x14001281d  mov     ebx, eax
0x14001281f  mov     rcx, rbp; hObject
0x140012822  call    cs:__imp_CloseHandle
0x140012828  mov     ecx, ebx; dwErrCode
0x14001282a  call    cs:__imp_SetLastError
0x140012830  mov     [rdi], rsi
0x140012833  test    rsi, rsi
0x140012836  jnz     short loc_140012863
0x140012838  mov     rcx, [rsp+68h]; this
0x14001283d  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x140012844  lea     edx, [rsi+35h]; void *
0x140012847  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001284c  mov     ebx, eax
0x14001284e  mov     rcx, rdi; this
0x140012851  call    ??1ProviderManager@ProviderManagement@DAS@@QEAA@XZ; DAS::ProviderManagement::ProviderManager::~ProviderManager(void)
0x140012856  mov     rdx, r15; unsigned __int64
0x140012859  mov     rcx, rdi; void *
0x14001285c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140012861  jmp     short loc_140012888
0x140012863  mov     [r14], rdi
0x140012866  xor     eax, eax
0x140012868  jmp     short loc_14001288A
0x14001286a  mov     rcx, [rsp+68h]; this
0x14001286f  mov     ebx, 8007000Eh
0x140012874  mov     r9d, ebx; char *
0x140012877  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x14001287e  mov     edx, 26h ; '&'; void *
0x140012883  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140012888  mov     eax, ebx
0x14001288a  add     rsp, 38h
0x14001288e  pop     r15
0x140012890  pop     r14
0x140012892  pop     rdi
0x140012893  pop     rsi
0x140012894  pop     rbp
0x140012895  pop     rbx
0x140012896  retn
```
