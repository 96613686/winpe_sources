# ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)

- ea: `0x180003378`
- end: `0x18000347e`
- name: `?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct ATL::_ATL_COM_MODULE70 *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005b40`

## callees

- `0x180003378`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003440`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003440`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003415`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003415`

## pseudocode

```c
__int64 __fastcall ATL::AtlComModuleGetClassObject(
        struct ATL::_ATL_COM_MODULE70 *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v8; // ebx
  __int64 *i; // rcx
  __int64 v10; // rsi
  _DWORD *v11; // rdx
  _QWORD *v12; // rdi

  if ( !ATL::_AtlComModule )
    return 2147549183LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  for ( i = (__int64 *)off_18000B0A0[0]; i < (__int64 *)off_18000B0A8; ++i )
  {
    v10 = *i;
    if ( *i )
    {
      if ( *(_QWORD *)(v10 + 16) )
      {
        v11 = *(_DWORD **)v10;
        if ( a2->Data1 == **(_DWORD **)v10
          && *(_DWORD *)&a2->Data2 == v11[1]
          && *(_DWORD *)a2->Data4 == v11[2]
          && *(_DWORD *)&a2->Data4[4] == v11[3] )
        {
          v12 = (_QWORD *)(v10 + 32);
          if ( !*(_QWORD *)(v10 + 32) )
          {
            EnterCriticalSection(&CriticalSection);
            if ( !*v12 )
              v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v10 + 16))(
                     *(_QWORD *)(v10 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v10 + 32);
            LeaveCriticalSection(&CriticalSection);
          }
          if ( *v12 )
            v8 = (**(__int64 (__fastcall ***)(_QWORD, const struct _GUID *, void **))*v12)(*v12, a3, a4);
          break;
        }
      }
    }
  }
  if ( !*a4 && !v8 )
    return (unsigned int)-2147221231;
  return v8;
}

```

## disassembly

```asm
0x180003378  push    rbx
0x18000337a  push    rbp
0x18000337b  push    rsi
0x18000337c  push    rdi
0x18000337d  push    r14
0x18000337f  sub     rsp, 20h
0x180003383  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18000338a  mov     r14, r9
0x18000338d  mov     r9, rdx
0x180003390  mov     rbp, r8
0x180003393  jnz     short loc_18000339F
0x180003395  mov     eax, 8000FFFFh
0x18000339a  jmp     loc_180003473
0x18000339f  test    r14, r14
0x1800033a2  jnz     short loc_1800033AE
0x1800033a4  mov     eax, 80004003h
0x1800033a9  jmp     loc_180003473
0x1800033ae  mov     qword ptr [r14], 0
0x1800033b5  xor     ebx, ebx
0x1800033b7  mov     rcx, cs:off_18000B0A0
0x1800033be  mov     r8, cs:off_18000B0A8
0x1800033c5  jmp     short loc_1800033FE
0x1800033c7  mov     rsi, [rcx]
0x1800033ca  test    rsi, rsi
0x1800033cd  jz      short loc_1800033FA
0x1800033cf  cmp     [rsi+10h], rbx
0x1800033d3  jz      short loc_1800033FA
0x1800033d5  mov     rdx, [rsi]
0x1800033d8  mov     eax, [rdx]
0x1800033da  cmp     [r9], eax
0x1800033dd  jnz     short loc_1800033FA
0x1800033df  mov     eax, [rdx+4]
0x1800033e2  cmp     [r9+4], eax
0x1800033e6  jnz     short loc_1800033FA
0x1800033e8  mov     eax, [rdx+8]
0x1800033eb  cmp     [r9+8], eax
0x1800033ef  jnz     short loc_1800033FA
0x1800033f1  mov     eax, [rdx+0Ch]
0x1800033f4  cmp     [r9+0Ch], eax
0x1800033f8  jz      short loc_180003405
0x1800033fa  add     rcx, 8
0x1800033fe  cmp     rcx, r8
0x180003401  jb      short loc_1800033C7
0x180003403  jmp     short loc_180003461
0x180003405  lea     rdi, [rsi+20h]
0x180003409  cmp     [rdi], rbx
0x18000340c  jnz     short loc_180003446
0x18000340e  lea     rcx, CriticalSection; lpCriticalSection
0x180003415  call    cs:__imp_EnterCriticalSection
0x18000341b  cmp     [rdi], rbx
0x18000341e  jnz     short loc_180003439
0x180003420  mov     rcx, [rsi+18h]
0x180003424  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18000342b  mov     rax, [rsi+10h]
0x18000342f  mov     r8, rdi
0x180003432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003437  mov     ebx, eax
0x180003439  lea     rcx, CriticalSection; lpCriticalSection
0x180003440  call    cs:__imp_LeaveCriticalSection
0x180003446  mov     rcx, [rdi]
0x180003449  test    rcx, rcx
0x18000344c  jz      short loc_180003461
0x18000344e  mov     rax, [rcx]
0x180003451  mov     r8, r14
0x180003454  mov     rdx, rbp
0x180003457  mov     rax, [rax]
0x18000345a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000345f  mov     ebx, eax
0x180003461  cmp     qword ptr [r14], 0
0x180003465  jnz     short loc_180003471
0x180003467  test    ebx, ebx
0x180003469  mov     eax, 80040111h
0x18000346e  cmovz   ebx, eax
0x180003471  mov     eax, ebx
0x180003473  add     rsp, 20h
0x180003477  pop     r14
0x180003479  pop     rdi
0x18000347a  pop     rsi
0x18000347b  pop     rbp
0x18000347c  pop     rbx
0x18000347d  retn
```
