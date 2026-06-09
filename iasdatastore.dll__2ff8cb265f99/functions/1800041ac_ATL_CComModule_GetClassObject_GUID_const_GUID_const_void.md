# ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x1800041ac`
- end: `0x1800042a3`
- name: `?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `247`
- prototype: `int(ATL::CComModule *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800061f0`

## callees

- `0x180003008`
- `0x1800041ac`
- `0x180010010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000422e`
- `KERNEL32!EnterCriticalSection` at `0x18000422e`
- `KERNEL32!LeaveCriticalSection` at `0x180004259`
- `KERNEL32!LeaveCriticalSection` at `0x180004259`

## pseudocode

```c
__int64 __fastcall ATL::CComModule::GetClassObject(
        ATL::CComModule *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v8; // edi
  __int64 v9; // rbx
  ATL::CComModule **v10; // r14

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  v9 = qword_180019A58;
  if ( qword_180019A58 )
  {
    while ( *(_QWORD *)v9 )
    {
      if ( *(_QWORD *)(v9 + 16) )
      {
        this = *(ATL::CComModule **)v9;
        if ( a2->Data1 == **(_DWORD **)v9
          && *(_DWORD *)&a2->Data2 == *((_DWORD *)this + 1)
          && *(_DWORD *)a2->Data4 == *((_DWORD *)this + 2)
          && *(_DWORD *)&a2->Data4[4] == *((_DWORD *)this + 3) )
        {
          v10 = (ATL::CComModule **)(v9 + 32);
          if ( !*(_QWORD *)(v9 + 32) )
          {
            EnterCriticalSection(&CriticalSection);
            if ( !*v10 )
              v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v9 + 16))(
                     *(_QWORD *)(v9 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v9 + 32);
            LeaveCriticalSection(&CriticalSection);
          }
          this = *v10;
          if ( *v10 )
            v8 = (**(__int64 (__fastcall ***)(ATL::CComModule *, const struct _GUID *, void **))this)(this, a3, a4);
          break;
        }
      }
      v9 += 72;
    }
  }
  if ( !*a4 && !v8 )
    return (unsigned int)ATL::AtlComModuleGetClassObject(this, a2, a3, a4);
  return v8;
}

```

## disassembly

```asm
0x1800041ac  push    rbx
0x1800041ae  push    rbp
0x1800041af  push    rsi
0x1800041b0  push    rdi
0x1800041b1  push    r14
0x1800041b3  push    r15
0x1800041b5  sub     rsp, 28h
0x1800041b9  mov     rsi, r9
0x1800041bc  mov     r15, r8
0x1800041bf  mov     rbp, rdx
0x1800041c2  test    r9, r9
0x1800041c5  jnz     short loc_1800041D1
0x1800041c7  mov     eax, 80004003h
0x1800041cc  jmp     loc_180004296
0x1800041d1  mov     qword ptr [r9], 0
0x1800041d8  xor     edi, edi
0x1800041da  mov     rbx, cs:qword_180019A58
0x1800041e1  test    rbx, rbx
0x1800041e4  jz      loc_18000427A
0x1800041ea  jmp     short loc_180004217
0x1800041ec  cmp     [rbx+10h], rdi
0x1800041f0  jz      short loc_180004213
0x1800041f2  mov     rcx, [rbx]
0x1800041f5  mov     eax, [rcx]
0x1800041f7  cmp     [rdx], eax
0x1800041f9  jnz     short loc_180004213
0x1800041fb  mov     eax, [rcx+4]
0x1800041fe  cmp     [rdx+4], eax
0x180004201  jnz     short loc_180004213
0x180004203  mov     eax, [rcx+8]
0x180004206  cmp     [rdx+8], eax
0x180004209  jnz     short loc_180004213
0x18000420b  mov     eax, [rcx+0Ch]
0x18000420e  cmp     [rdx+0Ch], eax
0x180004211  jz      short loc_18000421E
0x180004213  add     rbx, 48h ; 'H'
0x180004217  cmp     [rbx], rdi
0x18000421a  jnz     short loc_1800041EC
0x18000421c  jmp     short loc_18000427A
0x18000421e  lea     r14, [rbx+20h]
0x180004222  cmp     [r14], rdi
0x180004225  jnz     short loc_18000425F
0x180004227  lea     rcx, CriticalSection; lpCriticalSection
0x18000422e  call    cs:__imp_EnterCriticalSection
0x180004234  cmp     [r14], rdi
0x180004237  jnz     short loc_180004252
0x180004239  mov     r8, r14
0x18000423c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180004243  mov     rcx, [rbx+18h]
0x180004247  mov     rax, [rbx+10h]
0x18000424b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004250  mov     edi, eax
0x180004252  lea     rcx, CriticalSection; lpCriticalSection
0x180004259  call    cs:__imp_LeaveCriticalSection
0x18000425f  mov     rcx, [r14]
0x180004262  test    rcx, rcx
0x180004265  jz      short loc_18000427A
0x180004267  mov     rax, [rcx]
0x18000426a  mov     r8, rsi
0x18000426d  mov     rdx, r15
0x180004270  mov     rax, [rax]
0x180004273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004278  mov     edi, eax
0x18000427a  cmp     qword ptr [rsi], 0
0x18000427e  jnz     short loc_180004294
0x180004280  test    edi, edi
0x180004282  jnz     short loc_180004294
0x180004284  mov     r9, rsi; void **
0x180004287  mov     r8, r15; struct _GUID *
0x18000428a  mov     rdx, rbp; struct _GUID *
0x18000428d  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x180004292  mov     edi, eax
0x180004294  mov     eax, edi
0x180004296  add     rsp, 28h
0x18000429a  pop     r15
0x18000429c  pop     r14
0x18000429e  pop     rdi
0x18000429f  pop     rsi
0x1800042a0  pop     rbp
0x1800042a1  pop     rbx
0x1800042a2  retn
```
