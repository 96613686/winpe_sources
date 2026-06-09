# CAssociationCallback::Create(ushort const *,ushort const *,int,void *,void *,CAssociationCallback * *)

- ea: `0x140017880`
- end: `0x140017a5e`
- name: `?Create@CAssociationCallback@@SAJPEBG0HPEAX1PEAPEAV1@@Z`
- size: `478`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int, void *, void *, struct CAssociationCallback **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x14000afa4`

## callees

- `0x14000190c`
- `0x140009060`
- `0x140009090`
- `0x14000a8ac`
- `0x140017880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140017a16`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140017a16`

## pseudocode

```c
__int64 __fastcall CAssociationCallback::Create(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        int a3,
        void *a4,
        void *a5,
        struct CAssociationCallback **a6)
{
  __int64 v8; // rdx
  const unsigned __int16 *i; // rax
  unsigned int v10; // ebx
  unsigned __int64 v11; // rbx
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // r15
  unsigned __int16 *v14; // r14
  __int64 v15; // rcx
  const unsigned __int16 *v16; // rax
  unsigned __int64 v17; // rbx
  unsigned __int16 *v18; // rax
  char *v19; // rsi
  unsigned __int16 *v21; // [rsp+20h] [rbp-48h]
  unsigned __int16 *v22; // [rsp+28h] [rbp-40h]

  if ( a1 && a6 && a4 )
  {
    *a6 = 0;
    v8 = 0x7FFFFFFF;
    for ( i = a1; *i; ++i )
    {
      if ( !--v8 )
        return (unsigned int)-2147024809;
    }
    v11 = 2 * (0x80000000LL - v8);
    v12 = (unsigned __int16 *)DAF_user_alloc(v11);
    v13 = v12;
    v22 = v12;
    if ( !v12 )
      return (unsigned int)-2147024882;
    v14 = 0;
    v21 = 0;
    v10 = StringCbCopyW(v12, v11, a1);
    if ( v10 )
      goto LABEL_19;
    if ( a2 )
    {
      v15 = 184;
      v16 = a2;
      while ( *v16 )
      {
        ++v16;
        if ( !--v15 )
        {
          v10 = -2147024809;
          goto LABEL_19;
        }
      }
      v17 = 2 * (185 - v15);
      v18 = (unsigned __int16 *)DAF_user_alloc(v17);
      v14 = v18;
      v21 = v18;
      if ( !v18 )
      {
        v10 = -2147024882;
        goto LABEL_19;
      }
      v10 = StringCbCopyW(v18, v17, a2);
      if ( v10 )
      {
LABEL_19:
        MIDL_user_free(v13);
        if ( v14 )
          MIDL_user_free(v14);
        return v10;
      }
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v19 = (char *)operator new(0x98u);
      *(_QWORD *)v19 = &CAssociationCallback::`vftable'{for `IAepAssociationCallback'};
      *((_QWORD *)v19 + 1) = &CAssociationCallback::`vftable'{for `IDafPrivImpersonationToken'};
      *((_QWORD *)v19 + 2) = &CAssociationCallback::`vftable'{for `IServiceProvider'};
      *((_DWORD *)v19 + 6) = 1;
      *((_QWORD *)v19 + 4) = a4;
      *((_QWORD *)v19 + 5) = v13;
      *((_QWORD *)v19 + 6) = v14;
      *((_DWORD *)v19 + 14) = a3;
      *((_QWORD *)v19 + 8) = 0;
      *((_QWORD *)v19 + 9) = 0;
      *((_DWORD *)v19 + 20) = 0;
      *((_QWORD *)v19 + 11) = 0;
      *((_QWORD *)v19 + 12) = a5;
      *((_DWORD *)v19 + 26) = 1;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v19 + 112));
      *a6 = (struct CAssociationCallback *)v19;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v10 = -2147467259;
        v13 = v22;
        v14 = v21;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_140017A22);
        goto LABEL_19;
      }
    }
    return v10;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x140017880  mov     [rsp+arg_18], r9
0x140017885  mov     [rsp+arg_10], r8d
0x14001788a  push    rbx
0x14001788b  push    rsi
0x14001788c  push    rdi
0x14001788d  push    r12
0x14001788f  push    r13
0x140017891  push    r14
0x140017893  push    r15
0x140017895  sub     rsp, 30h
0x140017899  mov     rax, r9
0x14001789c  mov     r13, rdx
0x14001789f  mov     rsi, rcx
0x1400178a2  xor     edi, edi
0x1400178a4  test    rcx, rcx
0x1400178a7  jz      loc_140017A49
0x1400178ad  mov     r12, [rsp+68h+arg_28]
0x1400178b5  test    r12, r12
0x1400178b8  jz      loc_140017A49
0x1400178be  test    rax, rax
0x1400178c1  jz      loc_140017A49
0x1400178c7  mov     [r12], rdi
0x1400178cb  mov     edx, 7FFFFFFFh
0x1400178d0  mov     rax, rcx
0x1400178d3  cmp     [rax], di
0x1400178d6  jz      short loc_1400178EC
0x1400178d8  add     rax, 2
0x1400178dc  sub     rdx, 1
0x1400178e0  jnz     short loc_1400178D3
0x1400178e2  mov     ebx, 80070057h
0x1400178e7  jmp     loc_140017A45
0x1400178ec  mov     ebx, 80000000h
0x1400178f1  sub     rbx, rdx
0x1400178f4  add     rbx, rbx
0x1400178f7  mov     rcx, rbx
0x1400178fa  call    DAF_user_alloc
0x1400178ff  mov     r15, rax
0x140017902  mov     [rsp+68h+var_40], rax
0x140017907  test    rax, rax
0x14001790a  jnz     short loc_140017916
0x14001790c  mov     ebx, 8007000Eh
0x140017911  jmp     loc_140017A45
0x140017916  mov     r14, rdi
0x140017919  mov     [rsp+68h+var_48], rdi
0x14001791e  mov     r8, rsi; unsigned __int16 *
0x140017921  mov     rdx, rbx; unsigned __int64
0x140017924  mov     rcx, r15; unsigned __int16 *
0x140017927  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14001792c  mov     ebx, eax
0x14001792e  test    eax, eax
0x140017930  jnz     loc_140017A30
0x140017936  test    r13, r13
0x140017939  jz      short loc_14001799E
0x14001793b  mov     ecx, 0B8h
0x140017940  mov     rax, r13
0x140017943  cmp     [rax], di
0x140017946  jz      short loc_14001795C
0x140017948  add     rax, 2
0x14001794c  sub     rcx, 1
0x140017950  jnz     short loc_140017943
0x140017952  mov     ebx, 80070057h
0x140017957  jmp     loc_140017A30
0x14001795c  mov     ebx, 0B9h
0x140017961  sub     rbx, rcx
0x140017964  add     rbx, rbx
0x140017967  mov     rcx, rbx
0x14001796a  call    DAF_user_alloc
0x14001796f  mov     r14, rax
0x140017972  mov     [rsp+68h+var_48], rax
0x140017977  test    rax, rax
0x14001797a  jnz     short loc_140017986
0x14001797c  mov     ebx, 8007000Eh
0x140017981  jmp     loc_140017A30
0x140017986  mov     r8, r13; unsigned __int16 *
0x140017989  mov     rdx, rbx; unsigned __int64
0x14001798c  mov     rcx, rax; unsigned __int16 *
0x14001798f  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140017994  mov     ebx, eax
0x140017996  test    eax, eax
0x140017998  jnz     loc_140017A30
0x14001799e  mov     ecx, 98h; Size
0x1400179a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400179a8  mov     rsi, rax
0x1400179ab  lea     rax, ??_7CAssociationCallback@@6BIAepAssociationCallback@@@; const CAssociationCallback::`vftable'{for `IAepAssociationCallback'}
0x1400179b2  mov     [rsi], rax
0x1400179b5  lea     rax, ??_7CAssociationCallback@@6BIDafPrivImpersonationToken@@@; const CAssociationCallback::`vftable'{for `IDafPrivImpersonationToken'}
0x1400179bc  mov     [rsi+8], rax
0x1400179c0  lea     rax, ??_7CAssociationCallback@@6BIServiceProvider@@@; const CAssociationCallback::`vftable'{for `IServiceProvider'}
0x1400179c7  mov     [rsi+10h], rax
0x1400179cb  mov     dword ptr [rsi+18h], 1
0x1400179d2  mov     rax, [rsp+68h+arg_18]
0x1400179da  mov     [rsi+20h], rax
0x1400179de  mov     [rsi+28h], r15
0x1400179e2  mov     [rsi+30h], r14
0x1400179e6  mov     eax, [rsp+68h+arg_10]
0x1400179ed  mov     [rsi+38h], eax
0x1400179f0  mov     [rsi+40h], rdi
0x1400179f4  mov     [rsi+48h], rdi
0x1400179f8  mov     [rsi+50h], edi
0x1400179fb  mov     [rsi+58h], rdi
0x1400179ff  mov     rax, [rsp+68h+arg_20]
0x140017a07  mov     [rsi+60h], rax
0x140017a0b  mov     dword ptr [rsi+68h], 1
0x140017a12  lea     rcx, [rsi+70h]; lpCriticalSection
0x140017a16  call    cs:__imp_InitializeCriticalSection
0x140017a1c  mov     [r12], rsi
0x140017a20  jmp     short loc_140017A45
0x140017a22  mov     ebx, [rsp+68h+arg_0]
0x140017a26  mov     r15, [rsp+68h+var_40]
0x140017a2b  mov     r14, [rsp+68h+var_48]
0x140017a30  mov     rcx, r15; void *
0x140017a33  call    MIDL_user_free
0x140017a38  test    r14, r14
0x140017a3b  jz      short loc_140017A45
0x140017a3d  mov     rcx, r14; void *
0x140017a40  call    MIDL_user_free
0x140017a45  mov     eax, ebx
0x140017a47  jmp     short loc_140017A4E
0x140017a49  mov     eax, 80070057h
0x140017a4e  add     rsp, 30h
0x140017a52  pop     r15
0x140017a54  pop     r14
0x140017a56  pop     r13
0x140017a58  pop     r12
0x140017a5a  pop     rdi
0x140017a5b  pop     rsi
0x140017a5c  pop     rbx
0x140017a5d  retn
```
