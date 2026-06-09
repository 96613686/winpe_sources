# CWiGigDAFProviderAssociation::StartWriteCeremonyData(ulong,uchar const *,IAepAssociationWriteCallback *)

- ea: `0x18000b660`
- end: `0x18000bb1e`
- name: `?StartWriteCeremonyData@CWiGigDAFProviderAssociation@@UEAAJKPEBEPEAUIAepAssociationWriteCallback@@@Z`
- size: `1214`
- prototype: `__int64 __fastcall(CWiGigDAFProviderAssociation *this, int, const wchar_t *, struct IAepAssociationWriteCallback *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x180001ef4`
- `0x180009040`
- `0x18000b660`
- `0x18000c308`
- `0x18000c348`
- `0x180016f0c`
- `0x180017f94`
- `0x18001ca32`
- `0x18001f010`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18000b884`
- `msvcrt!wcsnlen` at `0x18000b9c2`
- `msvcrt!wcsnlen` at `0x18000b884`
- `msvcrt!wcsnlen` at `0x18000b9c2`

## pseudocode

```c
__int64 __fastcall CWiGigDAFProviderAssociation::StartWriteCeremonyData(
        CWiGigDAFProviderAssociation *this,
        int a2,
        const wchar_t *a3,
        struct IAepAssociationWriteCallback *a4)
{
  _BYTE *v8; // rcx
  int v10; // eax
  unsigned int v11; // edi
  _BYTE *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rdx
  size_t v15; // rax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  RTL_SRWLOCK *v18; // rdi
  struct Work *v19; // rax
  struct Work *v20; // rbx
  size_t v21; // rax

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a3 || !a4 )
  {
    if ( v8 == (_BYTE *)&WPP_GLOBAL_Control || v8[25] < 4u || (v8[28] & 1) == 0 )
      return 2147942487LL;
    v14 = 77;
    goto LABEL_83;
  }
  if ( !*((_BYTE *)this + 3288) )
  {
    v10 = ManualResetEvent::Wait((CWiGigDAFProviderAssociation *)((char *)this + 64), 0xEA60u);
    v11 = v10;
    if ( v10 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v11;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, v10);
        v12 = WPP_GLOBAL_Control;
      }
      if ( v12 == (_BYTE *)&WPP_GLOBAL_Control || v12[25] < 4u || (v12[28] & 1) == 0 )
        return v11;
      v13 = 81;
      goto LABEL_26;
    }
    if ( *((_BYTE *)this + 3288) )
    {
      v11 = -2147023673;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v11;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
        v12 = WPP_GLOBAL_Control;
      }
      if ( v12 == (_BYTE *)&WPP_GLOBAL_Control || v12[25] < 4u || (v12[28] & 1) == 0 )
        return v11;
      v13 = 83;
      goto LABEL_26;
    }
    if ( *(_OWORD *)((char *)this + 76) == DAF_Ceremony_PinEntry )
    {
      if ( a2 != 536 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          return 2147942487LL;
        }
        v14 = 84;
LABEL_83:
        WPP_SF_qD(*((_QWORD *)v8 + 2), v14, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, -2147024809);
        return 2147942487LL;
      }
      v15 = 2 * wcsnlen(a3 + 8, 0x104u);
      if ( v15 > 0xFF )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          return 2147942511LL;
        }
        v17 = 85;
LABEL_67:
        WPP_SF_qD(v16[2], v17, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, -2147024785);
        return 2147942511LL;
      }
      *((_DWORD *)this + 23) = v15;
      memcpy_0((char *)this + 96, a3 + 8, (unsigned int)v15);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
      }
      v18 = (RTL_SRWLOCK *)*((_QWORD *)this + 334);
      v19 = (struct Work *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      v20 = v19;
      if ( !v19 )
      {
        v20 = 0;
        return DockingProviders::SubmitWork(v18, v20);
      }
    }
    else
    {
      if ( *(_OWORD *)((char *)this + 76) != DAF_Ceremony_PassphraseEntry )
      {
        v11 = -2147019873;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          return v11;
        }
        v13 = 90;
LABEL_26:
        WPP_SF_qD(*((_QWORD *)v12 + 2), v13, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this, v11);
        return v11;
      }
      if ( a2 != 536 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          return 2147942487LL;
        }
        v14 = 87;
        goto LABEL_83;
      }
      v21 = 2 * wcsnlen(a3 + 8, 0x104u);
      if ( v21 > 0xFF )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          return 2147942511LL;
        }
        v17 = 88;
        goto LABEL_67;
      }
      *((_DWORD *)this + 23) = v21;
      memcpy_0((char *)this + 96, a3 + 8, (unsigned int)v21);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
      }
      v18 = (RTL_SRWLOCK *)*((_QWORD *)this + 334);
      v19 = (struct Work *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      v20 = v19;
      if ( !v19 )
      {
        v20 = 0;
        return DockingProviders::SubmitWork(v18, v20);
      }
    }
    *(_QWORD *)v19 = &WriteCeremonyDataWork::`vftable';
    *((_QWORD *)v19 + 1) = a4;
    (*(void (__fastcall **)(struct IAepAssociationWriteCallback *))(*(_QWORD *)a4 + 8LL))(a4);
    return DockingProviders::SubmitWork(v18, v20);
  }
  if ( v8 != (_BYTE *)&WPP_GLOBAL_Control )
  {
    if ( v8[25] >= 3u && (v8[28] & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)v8 + 2), 78, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
      v8 = WPP_GLOBAL_Control;
    }
    if ( v8 != (_BYTE *)&WPP_GLOBAL_Control && v8[25] >= 4u && (v8[28] & 1) != 0 )
      WPP_SF_q(*((_QWORD *)v8 + 2), 79, &WPP_c2da2149000737c368804296c411cd66_Traceguids, this);
  }
  return CWiGigDAFProviderAssociation::CancelCleanup(this);
}

```

## disassembly

```asm
0x18000b660  push    rbx
0x18000b662  push    rbp
0x18000b663  push    rsi
0x18000b664  push    rdi
0x18000b665  push    r12
0x18000b667  push    r13
0x18000b669  push    r14
0x18000b66b  push    r15
0x18000b66d  sub     rsp, 38h
0x18000b671  mov     rsi, r9
0x18000b674  mov     r14, r8
0x18000b677  mov     ebp, edx
0x18000b679  mov     rbx, rcx
0x18000b67c  lea     r12, WPP_GLOBAL_Control
0x18000b683  mov     r15b, 1
0x18000b686  lea     rdi, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000b68d  mov     r13b, 4
0x18000b690  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b697  cmp     rcx, r12
0x18000b69a  jz      short loc_18000B6C3
0x18000b69c  cmp     [rcx+19h], r13b
0x18000b6a0  jb      short loc_18000B6C3
0x18000b6a2  test    [rcx+1Ch], r15b
0x18000b6a6  jz      short loc_18000B6C3
0x18000b6a8  mov     edx, 4Ch ; 'L'
0x18000b6ad  mov     r9, rbx
0x18000b6b0  mov     r8, rdi
0x18000b6b3  mov     rcx, [rcx+10h]
0x18000b6b7  call    WPP_SF_q
0x18000b6bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b6c3  test    r14, r14
0x18000b6c6  jz      loc_18000BADB
0x18000b6cc  test    rsi, rsi
0x18000b6cf  jz      loc_18000BADB
0x18000b6d5  cmp     byte ptr [rbx+0CD8h], 0
0x18000b6dc  jz      short loc_18000B73C
0x18000b6de  cmp     rcx, r12
0x18000b6e1  jz      short loc_18000B72F
0x18000b6e3  cmp     byte ptr [rcx+19h], 3
0x18000b6e7  jb      short loc_18000B70A
0x18000b6e9  test    [rcx+1Ch], r15b
0x18000b6ed  jz      short loc_18000B70A
0x18000b6ef  mov     edx, 4Eh ; 'N'
0x18000b6f4  mov     r9, rbx
0x18000b6f7  mov     r8, rdi
0x18000b6fa  mov     rcx, [rcx+10h]
0x18000b6fe  call    WPP_SF_q
0x18000b703  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b70a  cmp     rcx, r12
0x18000b70d  jz      short loc_18000B72F
0x18000b70f  cmp     [rcx+19h], r13b
0x18000b713  jb      short loc_18000B72F
0x18000b715  test    [rcx+1Ch], r15b
0x18000b719  jz      short loc_18000B72F
0x18000b71b  mov     edx, 4Fh ; 'O'
0x18000b720  mov     r9, rbx
0x18000b723  mov     r8, rdi
0x18000b726  mov     rcx, [rcx+10h]
0x18000b72a  call    WPP_SF_q
0x18000b72f  mov     rcx, rbx; this
0x18000b732  call    ?CancelCleanup@CWiGigDAFProviderAssociation@@AEAAJXZ; CWiGigDAFProviderAssociation::CancelCleanup(void)
0x18000b737  jmp     loc_18000BB0D
0x18000b73c  lea     rcx, [rbx+40h]; this
0x18000b740  mov     edx, 0EA60h; unsigned int
0x18000b745  call    ?Wait@ManualResetEvent@@QEAAJK@Z; ManualResetEvent::Wait(ulong)
0x18000b74a  mov     edi, eax
0x18000b74c  test    eax, eax
0x18000b74e  jns     short loc_18000B7BF
0x18000b750  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b757  cmp     rcx, r12
0x18000b75a  jz      short loc_18000B7B8
0x18000b75c  cmp     [rcx+19h], r15b
0x18000b760  jb      short loc_18000B78B
0x18000b762  test    [rcx+1Ch], r15b
0x18000b766  jz      short loc_18000B78B
0x18000b768  mov     edx, 50h ; 'P'
0x18000b76d  mov     [rsp+78h+var_58], eax
0x18000b771  mov     r9, rbx
0x18000b774  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000b77b  mov     rcx, [rcx+10h]
0x18000b77f  call    WPP_SF_qD
0x18000b784  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b78b  cmp     rcx, r12
0x18000b78e  jz      short loc_18000B7B8
0x18000b790  cmp     [rcx+19h], r13b
0x18000b794  jb      short loc_18000B7B8
0x18000b796  test    [rcx+1Ch], r15b
0x18000b79a  jz      short loc_18000B7B8
0x18000b79c  mov     edx, 51h ; 'Q'
0x18000b7a1  mov     [rsp+78h+var_58], edi
0x18000b7a5  mov     r9, rbx
0x18000b7a8  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000b7af  mov     rcx, [rcx+10h]
0x18000b7b3  call    WPP_SF_qD
0x18000b7b8  mov     eax, edi
0x18000b7ba  jmp     loc_18000BB0D
0x18000b7bf  cmp     byte ptr [rbx+0CD8h], 0
0x18000b7c6  jz      short loc_18000B81C
0x18000b7c8  mov     edi, 800704C7h
0x18000b7cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b7d4  cmp     rcx, r12
0x18000b7d7  jz      short loc_18000B7B8
0x18000b7d9  cmp     byte ptr [rcx+19h], 3
0x18000b7dd  jb      short loc_18000B804
0x18000b7df  test    [rcx+1Ch], r15b
0x18000b7e3  jz      short loc_18000B804
0x18000b7e5  mov     edx, 52h ; 'R'
0x18000b7ea  mov     r9, rbx
0x18000b7ed  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000b7f4  mov     rcx, [rcx+10h]
0x18000b7f8  call    WPP_SF_q
0x18000b7fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b804  cmp     rcx, r12
0x18000b807  jz      short loc_18000B7B8
0x18000b809  cmp     [rcx+19h], r13b
0x18000b80d  jb      short loc_18000B7B8
0x18000b80f  test    [rcx+1Ch], r15b
0x18000b813  jz      short loc_18000B7B8
0x18000b815  mov     edx, 53h ; 'S'
0x18000b81a  jmp     short loc_18000B7A1
0x18000b81c  mov     rax, [rbx+4Ch]
0x18000b820  cmp     rax, qword ptr cs:DAF_Ceremony_PinEntry
0x18000b827  jnz     loc_18000B961
0x18000b82d  mov     rax, [rbx+54h]
0x18000b831  cmp     rax, qword ptr cs:DAF_Ceremony_PinEntry+8
0x18000b838  jnz     loc_18000B961
0x18000b83e  cmp     ebp, 218h
0x18000b844  jz      short loc_18000B87B
0x18000b846  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b84d  cmp     rcx, r12
0x18000b850  jz      loc_18000BB08
0x18000b856  cmp     [rcx+19h], r13b
0x18000b85a  jb      loc_18000BB08
0x18000b860  test    [rcx+1Ch], r15b
0x18000b864  jz      loc_18000BB08
0x18000b86a  mov     edx, 54h ; 'T'
0x18000b86f  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000b876  jmp     loc_18000BAF4
0x18000b87b  mov     edx, 104h; MaxCount
0x18000b880  lea     rcx, [r14+10h]; Source
0x18000b884  call    cs:__imp_wcsnlen
0x18000b88a  add     rax, rax
0x18000b88d  cmp     rax, 0FFh
0x18000b893  jbe     short loc_18000B8C3
0x18000b895  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b89c  cmp     rcx, r12
0x18000b89f  jz      loc_18000BA0B
0x18000b8a5  cmp     [rcx+19h], r13b
0x18000b8a9  jb      loc_18000BA0B
0x18000b8af  test    [rcx+1Ch], r15b
0x18000b8b3  jz      loc_18000BA0B
0x18000b8b9  mov     edx, 55h ; 'U'
0x18000b8be  jmp     loc_18000B9F0
0x18000b8c3  mov     r8d, eax; Size
0x18000b8c6  mov     [rbx+5Ch], r8d
0x18000b8ca  lea     rcx, [rbx+60h]; void *
0x18000b8ce  lea     rdx, [r14+10h]; Src
0x18000b8d2  call    memcpy_0
0x18000b8d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8de  cmp     rcx, r12
0x18000b8e1  jz      short loc_18000B907
0x18000b8e3  cmp     [rcx+19h], r13b
0x18000b8e7  jb      short loc_18000B907
0x18000b8e9  test    [rcx+1Ch], r15b
0x18000b8ed  jz      short loc_18000B907
0x18000b8ef  mov     edx, 56h ; 'V'
0x18000b8f4  mov     r9, rbx
0x18000b8f7  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000b8fe  mov     rcx, [rcx+10h]
0x18000b902  call    WPP_SF_q
0x18000b907  mov     rdi, [rbx+0A70h]
0x18000b90e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b915  mov     ecx, 10h; unsigned __int64
0x18000b91a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b91f  mov     rbx, rax
0x18000b922  mov     [rsp+78h+arg_10], rax
0x18000b92a  test    rax, rax
0x18000b92d  jz      short loc_18000B94F
0x18000b92f  lea     rax, ??_7WriteCeremonyDataWork@@6B@; const WriteCeremonyDataWork::`vftable'
0x18000b936  mov     [rbx], rax
0x18000b939  mov     [rbx+8], rsi
0x18000b93d  mov     rax, [rsi]
0x18000b940  mov     rcx, rsi
0x18000b943  mov     rax, [rax+8]
0x18000b947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b94c  nop
0x18000b94d  jmp     short loc_18000B951
0x18000b94f  xor     ebx, ebx
0x18000b951  mov     rdx, rbx; struct Work *
0x18000b954  mov     rcx, rdi; SRWLock
0x18000b957  call    ?SubmitWork@DockingProviders@@QEAAJPEAVWork@@@Z; DockingProviders::SubmitWork(Work *)
0x18000b95c  jmp     loc_18000BB0D
0x18000b961  mov     rax, [rbx+4Ch]
0x18000b965  cmp     rax, qword ptr cs:DAF_Ceremony_PassphraseEntry
0x18000b96c  jnz     loc_18000BAA8
0x18000b972  mov     rax, [rbx+54h]
0x18000b976  cmp     rax, qword ptr cs:DAF_Ceremony_PassphraseEntry+8
0x18000b97d  jnz     loc_18000BAA8
0x18000b983  cmp     ebp, 218h
0x18000b989  jz      short loc_18000B9B9
0x18000b98b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b992  cmp     rcx, r12
0x18000b995  jz      loc_18000BB08
0x18000b99b  cmp     [rcx+19h], r13b
0x18000b99f  jb      loc_18000BB08
0x18000b9a5  test    [rcx+1Ch], r15b
0x18000b9a9  jz      loc_18000BB08
0x18000b9af  mov     edx, 57h ; 'W'
0x18000b9b4  jmp     loc_18000B86F
0x18000b9b9  mov     edx, 104h; MaxCount
0x18000b9be  lea     rcx, [r14+10h]; Source
0x18000b9c2  call    cs:__imp_wcsnlen
0x18000b9c8  add     rax, rax
0x18000b9cb  cmp     rax, 0FFh
0x18000b9d1  jbe     short loc_18000BA15
0x18000b9d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b9da  cmp     rcx, r12
0x18000b9dd  jz      short loc_18000BA0B
0x18000b9df  cmp     [rcx+19h], r13b
0x18000b9e3  jb      short loc_18000BA0B
0x18000b9e5  test    [rcx+1Ch], r15b
0x18000b9e9  jz      short loc_18000BA0B
0x18000b9eb  mov     edx, 58h ; 'X'
0x18000b9f0  mov     [rsp+78h+var_58], 8007006Fh
0x18000b9f8  mov     r9, rbx
0x18000b9fb  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000ba02  mov     rcx, [rcx+10h]
0x18000ba06  call    WPP_SF_qD
0x18000ba0b  mov     eax, 8007006Fh
0x18000ba10  jmp     loc_18000BB0D
0x18000ba15  mov     r8d, eax; Size
0x18000ba18  mov     [rbx+5Ch], r8d
0x18000ba1c  lea     rcx, [rbx+60h]; void *
0x18000ba20  lea     rdx, [r14+10h]; Src
0x18000ba24  call    memcpy_0
0x18000ba29  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ba30  cmp     rcx, r12
0x18000ba33  jz      short loc_18000BA59
0x18000ba35  cmp     [rcx+19h], r13b
0x18000ba39  jb      short loc_18000BA59
0x18000ba3b  test    [rcx+1Ch], r15b
0x18000ba3f  jz      short loc_18000BA59
0x18000ba41  mov     edx, 59h ; 'Y'
0x18000ba46  mov     r9, rbx
0x18000ba49  lea     r8, WPP_c2da2149000737c368804296c411cd66_Traceguids
0x18000ba50  mov     rcx, [rcx+10h]
0x18000ba54  call    WPP_SF_q
0x18000ba59  mov     rdi, [rbx+0A70h]
0x18000ba60  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ba67  mov     ecx, 10h; unsigned __int64
0x18000ba6c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ba71  mov     rbx, rax
0x18000ba74  mov     [rsp+78h+arg_10], rax
0x18000ba7c  test    rax, rax
0x18000ba7f  jz      short loc_18000BAA1
0x18000ba81  lea     rax, ??_7WriteCeremonyDataWork@@6B@; const WriteCeremonyDataWork::`vftable'
0x18000ba88  mov     [rbx], rax
0x18000ba8b  mov     [rbx+8], rsi
0x18000ba8f  mov     rax, [rsi]
0x18000ba92  mov     rcx, rsi
0x18000ba95  mov     rax, [rax+8]
0x18000ba99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba9e  nop
0x18000ba9f  jmp     short loc_18000BAA3
0x18000baa1  xor     ebx, ebx
0x18000baa3  jmp     loc_18000B951
0x18000baa8  mov     edi, 8007139Fh
0x18000baad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bab4  cmp     rcx, r12
0x18000bab7  jz      loc_18000B7B8
0x18000babd  cmp     [rcx+19h], r13b
0x18000bac1  jb      loc_18000B7B8
0x18000bac7  test    [rcx+1Ch], r15b
0x18000bacb  jz      loc_18000B7B8
0x18000bad1  mov     edx, 5Ah ; 'Z'
0x18000bad6  jmp     loc_18000B7A1
0x18000badb  cmp     rcx, r12
0x18000bade  jz      short loc_18000BB08
0x18000bae0  cmp     [rcx+19h], r13b
0x18000bae4  jb      short loc_18000BB08
0x18000bae6  test    [rcx+1Ch], r15b
0x18000baea  jz      short loc_18000BB08
0x18000baec  mov     edx, 4Dh ; 'M'
0x18000baf1  mov     r8, rdi
0x18000baf4  mov     [rsp+78h+var_58], 80070057h
0x18000bafc  mov     r9, rbx
0x18000baff  mov     rcx, [rcx+10h]
0x18000bb03  call    WPP_SF_qD
0x18000bb08  mov     eax, 80070057h
0x18000bb0d  add     rsp, 38h
0x18000bb11  pop     r15
0x18000bb13  pop     r14
0x18000bb15  pop     r13
0x18000bb17  pop     r12
0x18000bb19  pop     rdi
0x18000bb1a  pop     rsi
0x18000bb1b  pop     rbp
0x18000bb1c  pop     rbx
0x18000bb1d  retn
```
