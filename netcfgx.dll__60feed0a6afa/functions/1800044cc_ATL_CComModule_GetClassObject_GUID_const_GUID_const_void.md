# ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)

- ea: `0x1800044cc`
- end: `0x1800045c0`
- name: `?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `244`
- prototype: `int(ATL::CComModule *__hidden this, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006480`

## callees

- `0x180003d68`
- `0x1800044cc`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004576`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004576`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000454b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000454b`

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
  ATL::CComModule **v10; // rsi

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  v8 = 0;
  v9 = *((_QWORD *)this + 9);
  if ( v9 )
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
            EnterCriticalSection(&stru_18001A200);
            if ( !*v10 )
              v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(v9 + 16))(
                     *(_QWORD *)(v9 + 24),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     v9 + 32);
            LeaveCriticalSection(&stru_18001A200);
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
0x1800044cc  push    rbx
0x1800044ce  push    rbp
0x1800044cf  push    rsi
0x1800044d0  push    rdi
0x1800044d1  push    r14
0x1800044d3  push    r15
0x1800044d5  sub     rsp, 28h
0x1800044d9  mov     r14, r9
0x1800044dc  mov     r15, r8
0x1800044df  mov     rbp, rdx
0x1800044e2  test    r9, r9
0x1800044e5  jnz     short loc_1800044F1
0x1800044e7  mov     eax, 80004003h
0x1800044ec  jmp     loc_1800045B3
0x1800044f1  mov     qword ptr [r9], 0
0x1800044f8  xor     edi, edi
0x1800044fa  mov     rbx, [rcx+48h]
0x1800044fe  test    rbx, rbx
0x180004501  jz      loc_180004597
0x180004507  jmp     short loc_180004534
0x180004509  cmp     [rbx+10h], rdi
0x18000450d  jz      short loc_180004530
0x18000450f  mov     rcx, [rbx]
0x180004512  mov     eax, [rcx]
0x180004514  cmp     [rdx], eax
0x180004516  jnz     short loc_180004530
0x180004518  mov     eax, [rcx+4]
0x18000451b  cmp     [rdx+4], eax
0x18000451e  jnz     short loc_180004530
0x180004520  mov     eax, [rcx+8]
0x180004523  cmp     [rdx+8], eax
0x180004526  jnz     short loc_180004530
0x180004528  mov     eax, [rcx+0Ch]
0x18000452b  cmp     [rdx+0Ch], eax
0x18000452e  jz      short loc_18000453B
0x180004530  add     rbx, 48h ; 'H'
0x180004534  cmp     [rbx], rdi
0x180004537  jnz     short loc_180004509
0x180004539  jmp     short loc_180004597
0x18000453b  lea     rsi, [rbx+20h]
0x18000453f  cmp     [rsi], rdi
0x180004542  jnz     short loc_18000457C
0x180004544  lea     rcx, stru_18001A200; lpCriticalSection
0x18000454b  call    cs:__imp_EnterCriticalSection
0x180004551  cmp     [rsi], rdi
0x180004554  jnz     short loc_18000456F
0x180004556  mov     r8, rsi
0x180004559  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180004560  mov     rcx, [rbx+18h]
0x180004564  mov     rax, [rbx+10h]
0x180004568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000456d  mov     edi, eax
0x18000456f  lea     rcx, stru_18001A200; lpCriticalSection
0x180004576  call    cs:__imp_LeaveCriticalSection
0x18000457c  mov     rcx, [rsi]
0x18000457f  test    rcx, rcx
0x180004582  jz      short loc_180004597
0x180004584  mov     rax, [rcx]
0x180004587  mov     r8, r14
0x18000458a  mov     rdx, r15
0x18000458d  mov     rax, [rax]
0x180004590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004595  mov     edi, eax
0x180004597  cmp     qword ptr [r14], 0
0x18000459b  jnz     short loc_1800045B1
0x18000459d  test    edi, edi
0x18000459f  jnz     short loc_1800045B1
0x1800045a1  mov     r9, r14; void **
0x1800045a4  mov     r8, r15; struct _GUID *
0x1800045a7  mov     rdx, rbp; struct _GUID *
0x1800045aa  call    ?AtlComModuleGetClassObject@ATL@@YAJPEAU_ATL_COM_MODULE70@1@AEBU_GUID@@1PEAPEAX@Z; ATL::AtlComModuleGetClassObject(ATL::_ATL_COM_MODULE70 *,_GUID const &,_GUID const &,void * *)
0x1800045af  mov     edi, eax
0x1800045b1  mov     eax, edi
0x1800045b3  add     rsp, 28h
0x1800045b7  pop     r15
0x1800045b9  pop     r14
0x1800045bb  pop     rdi
0x1800045bc  pop     rsi
0x1800045bd  pop     rbp
0x1800045be  pop     rbx
0x1800045bf  retn
```
