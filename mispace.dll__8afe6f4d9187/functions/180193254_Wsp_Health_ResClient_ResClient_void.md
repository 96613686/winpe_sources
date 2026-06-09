# Wsp::Health::ResClient::~ResClient(void)

- ea: `0x180193254`
- end: `0x1801933b4`
- name: `??1ResClient@Health@Wsp@@QEAA@XZ`
- size: `352`
- prototype: `void __fastcall(Wsp::Health::ResClient *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801934ec`

## callees

- `0x180024b64`
- `0x180192dc8`
- `0x1801930d4`
- `0x180193254`
- `0x18019494c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180193376`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180193376`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18019338a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18019338a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18019326d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18019326d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1801932ca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1801932ca`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1801932ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1801932ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1801932bd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1801932bd`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1801932fe`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x180193352`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x1801932fe`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x180193352`

## pseudocode

```c
void __fastcall Wsp::Health::ResClient::~ResClient(Wsp::Health::ResClient *this)
{
  RTL_SRWLOCK *v1; // rbx
  PVOID v3[2]; // [rsp+20h] [rbp-38h] BYREF
  char *v4; // [rsp+30h] [rbp-28h]
  PVOID RestartKey[2]; // [rsp+38h] [rbp-20h] BYREF
  char *v6; // [rsp+48h] [rbp-10h]
  wchar_t *v7; // [rsp+80h] [rbp+28h] BYREF

  v1 = (RTL_SRWLOCK *)((char *)this + 328);
  AcquireSRWLockExclusive((PSRWLOCK)this + 41);
  v7 = L"~ResClient::Grabbed the Lock";
  Wsp::Health::ResClient::LogComment((const wchar_t *const *)&v7);
  if ( *((_QWORD *)this + 43) )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 42), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 42), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 42));
    if ( *((_DWORD *)this + 72) )
    {
      v6 = (char *)this + 176;
      *(_OWORD *)RestartKey = 0;
      RestartKey[1] = RtlEnumerateGenericTableWithoutSplayingAvl((PRTL_AVL_TABLE)((char *)this + 184), RestartKey);
      v4 = v6;
      *(_OWORD *)v3 = *(_OWORD *)RestartKey;
      while ( v3[0] && v3[1] )
      {
        Wsp::Health::RefBase::Release(*((Wsp::Health::RefBase **)v3[1] + 1));
        if ( v4 )
        {
          if ( !v3[0] )
            break;
          if ( v3[1] )
          {
            v3[1] = RtlEnumerateGenericTableWithoutSplayingAvl((PRTL_AVL_TABLE)(v4 + 8), v3);
            if ( !v3[1] )
              v3[0] = 0;
          }
        }
      }
      CMapBase<unsigned short const *,_SUEX_SCALEUNIT_OBJECT *>::RemoveAll((char *)this + 176);
    }
    FreeLibrary(*((HMODULE *)this + 43));
    *((_QWORD *)this + 43) = 0;
  }
  ReleaseSRWLockExclusive(v1);
  v7 = L"~ResClient::Released the Lock";
  Wsp::Health::ResClient::LogComment((const wchar_t *const *)&v7);
  CMap<wchar_t *,Wsp::Health::CHealthConnection *>::~CMap<wchar_t *,Wsp::Health::CHealthConnection *>((char *)this + 176);
}

```

## disassembly

```asm
0x180193254  push    rbp
0x180193256  push    rbx
0x180193257  push    rsi
0x180193258  push    rdi
0x180193259  mov     rbp, rsp
0x18019325c  sub     rsp, 58h
0x180193260  lea     rbx, [rcx+148h]
0x180193267  mov     rsi, rcx
0x18019326a  mov     rcx, rbx; SRWLock
0x18019326d  call    cs:__imp_AcquireSRWLockExclusive
0x180193273  lea     rax, aResclientGrabb; "~ResClient::Grabbed the Lock"
0x18019327a  lea     rcx, [rbp+arg_0]; wchar_t **
0x18019327e  mov     [rbp+arg_0], rax
0x180193282  call    ?LogComment@ResClient@Health@Wsp@@SAXAEBQEB_W@Z; Wsp::Health::ResClient::LogComment(wchar_t const * const &)
0x180193287  cmp     qword ptr [rsi+158h], 0
0x18019328f  lea     rdi, [rsi+0B0h]
0x180193296  jz      loc_180193387
0x18019329c  mov     rcx, [rsi+150h]; pti
0x1801932a3  xor     r9d, r9d; msWindowLength
0x1801932a6  xor     r8d, r8d; msPeriod
0x1801932a9  xor     edx, edx; pftDueTime
0x1801932ab  call    cs:__imp_SetThreadpoolTimer
0x1801932b1  mov     rcx, [rsi+150h]; pti
0x1801932b8  mov     edx, 1; fCancelPendingCallbacks
0x1801932bd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1801932c3  mov     rcx, [rsi+150h]; pti
0x1801932ca  call    cs:__imp_CloseThreadpoolTimer
0x1801932d0  cmp     dword ptr [rdi+70h], 0
0x1801932d4  jbe     loc_18019336F
0x1801932da  xorps   xmm0, xmm0
0x1801932dd  mov     [rbp+var_28], 0
0x1801932e5  xorps   xmm1, xmm1
0x1801932e8  mov     [rbp+var_10], rdi
0x1801932ec  lea     rcx, [rdi+8]; Table
0x1801932f0  lea     rdx, [rbp+RestartKey]; RestartKey
0x1801932f4  movdqu  xmmword ptr [rbp+var_38], xmm0
0x1801932f9  movdqu  xmmword ptr [rbp+RestartKey], xmm1
0x1801932fe  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x180193304  movsd   xmm1, [rbp+var_10]
0x180193309  mov     [rbp+RestartKey+8], rax
0x18019330d  movups  xmm0, xmmword ptr [rbp+RestartKey]
0x180193311  movsd   [rbp+var_28], xmm1
0x180193316  movups  xmmword ptr [rbp+var_38], xmm0
0x18019331a  cmp     [rbp+var_38], 0
0x18019331f  jz      short loc_180193367
0x180193321  mov     rcx, [rbp+var_38+8]
0x180193325  test    rcx, rcx
0x180193328  jz      short loc_180193367
0x18019332a  mov     rcx, [rcx+8]; this
0x18019332e  call    ?Release@RefBase@Health@Wsp@@QEAAKXZ; Wsp::Health::RefBase::Release(void)
0x180193333  mov     rcx, [rbp+var_28]
0x180193337  test    rcx, rcx
0x18019333a  jz      short loc_18019331A
0x18019333c  cmp     [rbp+var_38], 0
0x180193341  jz      short loc_180193367
0x180193343  cmp     [rbp+var_38+8], 0
0x180193348  jz      short loc_18019331A
0x18019334a  add     rcx, 8; Table
0x18019334e  lea     rdx, [rbp+var_38]; RestartKey
0x180193352  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x180193358  mov     [rbp+var_38+8], rax
0x18019335c  test    rax, rax
0x18019335f  jnz     short loc_18019331A
0x180193361  mov     [rbp+var_38], rax
0x180193365  jmp     short loc_18019331A
0x180193367  mov     rcx, rdi; TableContext
0x18019336a  call    ?RemoveAll@?$CMapBase@PEBGPEAU_SUEX_SCALEUNIT_OBJECT@@@@QEAAXXZ; CMapBase<ushort const *,_SUEX_SCALEUNIT_OBJECT *>::RemoveAll(void)
0x18019336f  mov     rcx, [rsi+158h]; hLibModule
0x180193376  call    cs:__imp_FreeLibrary
0x18019337c  mov     qword ptr [rsi+158h], 0
0x180193387  mov     rcx, rbx; SRWLock
0x18019338a  call    cs:__imp_ReleaseSRWLockExclusive
0x180193390  lea     rax, aResclientRelea; "~ResClient::Released the Lock"
0x180193397  lea     rcx, [rbp+arg_0]; wchar_t **
0x18019339b  mov     [rbp+arg_0], rax
0x18019339f  call    ?LogComment@ResClient@Health@Wsp@@SAXAEBQEB_W@Z; Wsp::Health::ResClient::LogComment(wchar_t const * const &)
0x1801933a4  mov     rcx, rdi; TableContext
0x1801933a7  add     rsp, 58h
0x1801933ab  pop     rdi
0x1801933ac  pop     rsi
0x1801933ad  pop     rbx
0x1801933ae  pop     rbp
0x1801933af  jmp     ??1?$CMap@PEA_WPEAVCHealthConnection@Health@Wsp@@@@UEAA@XZ; CMap<wchar_t *,Wsp::Health::CHealthConnection *>::~CMap<wchar_t *,Wsp::Health::CHealthConnection *>(void)
```
