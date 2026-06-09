# PushRouter::SubmitPush(tagSrcPushMsg *)

- ea: `0x1800174e4`
- end: `0x1800176e1`
- name: `?SubmitPush@PushRouter@@QEAAJPEAUtagSrcPushMsg@@@Z`
- size: `509`
- prototype: `__int64 __fastcall(PushRouter *this, struct tagSrcPushMsg *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fac0`

## callees

- `0x180006090`
- `0x180014f80`
- `0x1800174e4`
- `0x18001974c`
- `0x18001a458`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017551`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001768a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017551`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001768a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017545`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001765b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017545`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001765b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001769b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001769b`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180017528`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800175e5`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180017528`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800175e5`

## pseudocode

```c
__int64 __fastcall PushRouter::SubmitPush(PushRouter *this, struct tagSrcPushMsg *a2)
{
  PushRouter *v3; // rsi
  unsigned int *v4; // rdi
  unsigned int v5; // ebx
  int v6; // ebx
  _WORD *v7; // rax
  __int64 v8; // r8
  unsigned int v9; // r8d
  unsigned int v10; // r14d
  unsigned int *v11; // rdi
  PersistObject *v12; // rax
  PushMessage *v13; // rdi

  v3 = g_pPushRouter;
  v4 = (unsigned int *)((char *)g_pPushRouter + 276);
  if ( OmaDmRegistryGetDWORD(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\PushRouter\\Settings",
         L"MaxUnauthenticatedMessages",
         (unsigned int *)g_pPushRouter + 69) )
  {
    *v4 = 20;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 136));
  v5 = *((_DWORD *)v3 + 28);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 136));
  if ( v5 < *v4 )
  {
    v7 = (_WORD *)*((_QWORD *)a2 + 1);
    if ( v7 )
    {
      v8 = 0x7FFFFFFF;
      do
      {
        if ( !*v7 )
          break;
        ++v7;
        --v8;
      }
      while ( v8 );
      v6 = -2147024809;
      if ( v8 )
      {
        v9 = v8 != 0 ? -2 - 2 * v8 : 0;
        v10 = v9 + *((_DWORD *)a2 + 6);
        if ( v10 < v9 )
        {
          return (unsigned int)-2147024362;
        }
        else
        {
          v11 = (unsigned int *)((char *)v3 + 272);
          if ( OmaDmRegistryGetDWORD(
                 HKEY_LOCAL_MACHINE,
                 L"Software\\Microsoft\\PushRouter\\Settings",
                 L"MaxMessageSize",
                 (unsigned int *)v3 + 68) )
          {
            *v11 = 0x10000;
          }
          if ( v10 <= *v11 )
          {
            v12 = (PersistObject *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
            v13 = v12;
            if ( v12 )
            {
              PersistObject::PersistObject(v12);
              *(_QWORD *)v13 = &PushMessage::`vftable';
            }
            else
            {
              v13 = 0;
            }
            if ( v13 )
            {
              v6 = PushMessage::Initialize(v13, a2);
              if ( v6 < 0
                || ((EnterCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 136)), *((_DWORD *)v3 + 31))
                  ? (v6 = PersistList::InternalAddTail((PushRouter *)((char *)v3 + 96), v13, 1))
                  : (v6 = -2102788096),
                    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 136)),
                    v6 < 0) )
              {
                (**(void (__fastcall ***)(PushMessage *, __int64))v13)(v13, 1);
              }
              else
              {
                SetEvent(*((HANDLE *)v3 + 22));
              }
            }
            else
            {
              return (unsigned int)-2147024882;
            }
          }
        }
      }
      else
      {
        return (unsigned int)-2147024809;
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  else
  {
    return (unsigned int)-2142040063;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800174e4  mov     [rsp+arg_8], rbx
0x1800174e9  mov     [rsp+arg_10], rbp
0x1800174ee  mov     [rsp+arg_0], rcx
0x1800174f3  push    rsi
0x1800174f4  push    rdi
0x1800174f5  push    r12
0x1800174f7  push    r14
0x1800174f9  push    r15
0x1800174fb  sub     rsp, 30h
0x1800174ff  mov     r15, rdx
0x180017502  mov     rsi, cs:?g_pPushRouter@@3PEAVPushRouter@@EA; PushRouter * g_pPushRouter
0x180017509  lea     rdi, [rsi+114h]
0x180017510  mov     r9, rdi
0x180017513  lea     r8, ?c_szMaxUnauthenticatedMessagesValueName@@3QBGB; "MaxUnauthenticatedMessages"
0x18001751a  lea     rdx, ?c_szPushRouterSettingsKey@@3QBGB; "Software\\Microsoft\\PushRouter\\Settin"...
0x180017521  mov     rcx, 0FFFFFFFF80000002h
0x180017528  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001752e  xor     r12d, r12d
0x180017531  test    eax, eax
0x180017533  jz      short loc_18001753B
0x180017535  mov     dword ptr [rdi], 14h
0x18001753b  lea     rbp, [rsi+88h]
0x180017542  mov     rcx, rbp; lpCriticalSection
0x180017545  call    cs:__imp_EnterCriticalSection
0x18001754b  mov     ebx, [rsi+70h]
0x18001754e  mov     rcx, rbp; lpCriticalSection
0x180017551  call    cs:__imp_LeaveCriticalSection
0x180017557  cmp     ebx, [rdi]
0x180017559  jb      short loc_180017565
0x18001755b  mov     ebx, 80531001h
0x180017560  jmp     loc_1800176C8
0x180017565  mov     rax, [r15+8]
0x180017569  test    rax, rax
0x18001756c  jz      loc_1800176C3
0x180017572  mov     r8d, 7FFFFFFFh
0x180017578  cmp     [rax], r12w
0x18001757c  jz      short loc_180017588
0x18001757e  add     rax, 2
0x180017582  sub     r8, 1
0x180017586  jnz     short loc_180017578
0x180017588  mov     rax, r8
0x18001758b  neg     rax
0x18001758e  sbb     ecx, ecx
0x180017590  not     ecx
0x180017592  mov     ebx, 80070057h
0x180017597  and     ecx, ebx
0x180017599  test    r8, r8
0x18001759c  jz      loc_1800176BF
0x1800175a2  lea     eax, [r8+r8]
0x1800175a6  mov     ecx, 0FFFFFFFEh
0x1800175ab  sub     ecx, eax
0x1800175ad  neg     r8
0x1800175b0  sbb     r8d, r8d
0x1800175b3  and     r8d, ecx
0x1800175b6  mov     r14d, [r15+18h]
0x1800175ba  add     r14d, r8d
0x1800175bd  cmp     r14d, r8d
0x1800175c0  jb      loc_1800176B8
0x1800175c6  lea     rdi, [rsi+110h]
0x1800175cd  mov     r9, rdi
0x1800175d0  lea     r8, ?c_szMaxMessageSizeValueName@@3QBGB; "MaxMessageSize"
0x1800175d7  lea     rdx, ?c_szPushRouterSettingsKey@@3QBGB; "Software\\Microsoft\\PushRouter\\Settin"...
0x1800175de  mov     rcx, 0FFFFFFFF80000002h
0x1800175e5  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800175eb  test    eax, eax
0x1800175ed  jz      short loc_1800175F5
0x1800175ef  mov     dword ptr [rdi], 10000h
0x1800175f5  cmp     r14d, [rdi]
0x1800175f8  ja      loc_1800176C8
0x1800175fe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017605  mov     ecx, 60h ; '`'; unsigned __int64
0x18001760a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001760f  mov     rdi, rax
0x180017612  mov     [rsp+58h+arg_0], rax
0x180017617  test    rax, rax
0x18001761a  jz      short loc_180017630
0x18001761c  mov     rcx, rax; this
0x18001761f  call    ??0PersistObject@@QEAA@XZ; PersistObject::PersistObject(void)
0x180017624  lea     rax, ??_7PushMessage@@6B@; const PushMessage::`vftable'
0x18001762b  mov     [rdi], rax
0x18001762e  jmp     short loc_180017633
0x180017630  mov     rdi, r12
0x180017633  test    rdi, rdi
0x180017636  jnz     short loc_180017642
0x180017638  mov     ebx, 8007000Eh
0x18001763d  jmp     loc_1800176C8
0x180017642  mov     rdx, r15; struct tagSrcPushMsg *
0x180017645  mov     rcx, rdi; this
0x180017648  call    ?Initialize@PushMessage@@QEAAJPEAUtagSrcPushMsg@@@Z; PushMessage::Initialize(tagSrcPushMsg *)
0x18001764d  mov     ebx, eax
0x18001764f  test    eax, eax
0x180017651  js      short loc_1800176A3
0x180017653  mov     [rsp+58h+var_38], rbp
0x180017658  mov     rcx, rbp; lpCriticalSection
0x18001765b  call    cs:__imp_EnterCriticalSection
0x180017661  mov     [rsp+58h+var_30], 1
0x180017666  lea     rcx, [rsi+60h]; this
0x18001766a  cmp     [rcx+1Ch], r12d
0x18001766e  jnz     short loc_180017677
0x180017670  mov     ebx, 82AA0000h
0x180017675  jmp     short loc_180017687
0x180017677  mov     r8d, 1; int
0x18001767d  mov     rdx, rdi; struct PersistObject *
0x180017680  call    ?InternalAddTail@PersistList@@AEAAJPEAVPersistObject@@H@Z; PersistList::InternalAddTail(PersistObject *,int)
0x180017685  mov     ebx, eax
0x180017687  mov     rcx, rbp; lpCriticalSection
0x18001768a  call    cs:__imp_LeaveCriticalSection
0x180017690  test    ebx, ebx
0x180017692  js      short loc_1800176A3
0x180017694  mov     rcx, [rsi+0B0h]; hEvent
0x18001769b  call    cs:__imp_SetEvent
0x1800176a1  jmp     short loc_1800176C8
0x1800176a3  mov     rax, [rdi]
0x1800176a6  mov     edx, 1
0x1800176ab  mov     rcx, rdi
0x1800176ae  mov     rax, [rax]
0x1800176b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176b6  jmp     short loc_1800176C8
0x1800176b8  mov     ebx, 80070216h
0x1800176bd  jmp     short loc_1800176C8
0x1800176bf  mov     ebx, ecx
0x1800176c1  jmp     short loc_1800176C8
0x1800176c3  mov     ebx, 80070057h
0x1800176c8  mov     eax, ebx
0x1800176ca  mov     rbx, [rsp+58h+arg_8]
0x1800176cf  mov     rbp, [rsp+58h+arg_10]
0x1800176d4  add     rsp, 30h
0x1800176d8  pop     r15
0x1800176da  pop     r14
0x1800176dc  pop     r12
0x1800176de  pop     rdi
0x1800176df  pop     rsi
0x1800176e0  retn
```
