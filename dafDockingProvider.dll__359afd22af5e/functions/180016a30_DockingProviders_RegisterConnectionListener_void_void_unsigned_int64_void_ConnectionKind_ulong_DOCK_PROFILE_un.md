# DockingProviders::RegisterConnectionListener(void *,void (*)(unsigned __int64,void *,_ConnectionKind,ulong,_DOCK_PROFILE *),unsigned __int64 *)

- ea: `0x180016a30`
- end: `0x180016dab`
- name: `?RegisterConnectionListener@DockingProviders@@QEAAJPEAXP6AX_K0W4_ConnectionKind@@KPEAU_DOCK_PROFILE@@@ZPEA_K@Z`
- size: `891`
- prototype: `__int64 __fastcall(DockingProviders *__hidden this, void *, void (__high *)(unsigned __int64, void *, enum _ConnectionKind, unsigned int, struct _DOCK_PROFILE *), unsigned __int64 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18000ccdc`
- `0x18001be10`

## callees

- `0x1800014d0`
- `0x180001ef4`
- `0x180001f28`
- `0x18000c308`
- `0x18000c348`
- `0x1800102ec`
- `0x180013c80`
- `0x180016a30`
- `0x180016ff4`
- `0x180017854`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180016a79`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180016a79`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016d1e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016d1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016aff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016c52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016cc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016aff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016c52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016cc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016b1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016c75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016cd5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016b1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016c75`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016cd5`

## pseudocode

```c
__int64 __fastcall DockingProviders::RegisterConnectionListener(
        DockingProviders *this,
        void *a2,
        void (__high *a3)(unsigned __int64, void *, enum _ConnectionKind, unsigned int, struct _DOCK_PROFILE *),
        unsigned __int64 *a4)
{
  struct _RTL_CRITICAL_SECTION *v7; // rax
  unsigned __int64 v8; // rsi
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // rax
  ListenerRegistration::RegistrationPair *v11; // rax
  ListenerRegistration::RegistrationPair *v12; // rdi
  ListenerRegistration::RegistrationPair *v13; // rbp
  char v14; // bl
  int v15; // r13d
  __int64 v16; // r12
  int v17; // ebx
  _QWORD *v18; // r10
  __int64 v19; // rdi
  signed int v20; // eax
  __int64 v21; // r8
  signed int v22; // edi
  ListenerRegistration::RegistrationPair *v23; // rcx
  bool v24; // sf
  ListenerRegistration::RegistrationPair *v25; // rdi
  __int64 v26; // rcx
  __int64 v27; // rax
  int v28; // ebx
  __int64 result; // rax
  ListenerRegistration::RegistrationPair *v30; // [rsp+30h] [rbp-48h] BYREF
  struct _RTL_CRITICAL_SECTION *v31; // [rsp+38h] [rbp-40h]
  int v32; // [rsp+44h] [rbp-34h]

  v7 = (struct _RTL_CRITICAL_SECTION *)operator new(0x48u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = (unsigned __int64)v7;
  v31 = v7;
  if ( v7 )
  {
    v9 = *((unsigned int *)this + 4);
    InitializeCriticalSection(v7);
    *(_QWORD *)(v8 + 40) = a2;
    *(_QWORD *)(v8 + 48) = a3;
    *(_QWORD *)(v8 + 56) = (unsigned int)v9;
    *(_QWORD *)(v8 + 64) = 0;
    if ( (_DWORD)v9 )
    {
      v10 = 16 * v9;
      if ( !is_mul_ok(v9, 0x10u) )
        v10 = -1;
      v11 = (ListenerRegistration::RegistrationPair *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
      v12 = v11;
      v30 = v11;
      if ( v11 )
      {
        v13 = v11;
        do
        {
          ListenerRegistration::RegistrationPair::RegistrationPair(v13);
          v13 = (ListenerRegistration::RegistrationPair *)((char *)v13 + 16);
          --v9;
        }
        while ( v9 );
      }
      else
      {
        v12 = 0;
      }
      *(_QWORD *)(v8 + 64) = v12;
    }
  }
  else
  {
    v8 = 0;
  }
  if ( v8
    && ((EnterCriticalSection((LPCRITICAL_SECTION)v8), !*(_DWORD *)(v8 + 56)) || *(_QWORD *)(v8 + 64)
      ? (v14 = 1)
      : (v14 = 0),
        LeaveCriticalSection((LPCRITICAL_SECTION)v8),
        v14) )
  {
    v15 = 0;
    v16 = 0;
    if ( *((_DWORD *)this + 4) )
    {
      v17 = v32;
      v18 = WPP_GLOBAL_Control;
      do
      {
        v30 = 0;
        v19 = *(_QWORD *)(*((_QWORD *)this + 3) + 8 * v16);
        v31 = (struct _RTL_CRITICAL_SECTION *)v19;
        if ( v18 != &WPP_GLOBAL_Control && *((_BYTE *)v18 + 25) >= 4u && (*((_BYTE *)v18 + 28) & 1) != 0 )
          WPP_SF_q(v18[2], 46, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, v19);
        v20 = (*(__int64 (__fastcall **)(unsigned __int64, __int64 (__fastcall *)(int, int, int, int, __int64), ListenerRegistration::RegistrationPair **))(v19 + 144))(
                v8,
                ListenerCallbackAdapter,
                &v30);
        v22 = v20;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v23 = 0;
          if ( !v20 )
            v23 = v30;
          WPP_SF_qDq(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, v21, v31, v20, v23);
          v18 = WPP_GLOBAL_Control;
        }
        v24 = v22 < 0;
        if ( v22 > 0 )
        {
          v22 = (unsigned __int16)v22 | 0x80070000;
          v24 = v22 < 0;
        }
        if ( v24 )
        {
          if ( v15 >= 0 )
            v15 = v22;
          if ( v18 == &WPP_GLOBAL_Control || !*((_BYTE *)v18 + 25) || (*((_BYTE *)v18 + 28) & 1) == 0 )
            goto LABEL_45;
          WPP_SF_qDd(v18[2], 122, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, this, v16, v22, v30, (_DWORD)v31);
        }
        else
        {
          v25 = v30;
          EnterCriticalSection((LPCRITICAL_SECTION)v8);
          v26 = 2LL * *(unsigned int *)(v8 + 60);
          v27 = *(_QWORD *)(v8 + 64);
          *(_QWORD *)(v27 + 8 * v26) = v25;
          *(_DWORD *)(v27 + 8 * v26 + 8) = v16;
          *(_DWORD *)(v27 + 8 * v26 + 12) = v17;
          ++*(_DWORD *)(v8 + 60);
          LeaveCriticalSection((LPCRITICAL_SECTION)v8);
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_45;
          }
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            123,
            &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids,
            this,
            v16);
        }
        v18 = WPP_GLOBAL_Control;
LABEL_45:
        v16 = (unsigned int)(v16 + 1);
      }
      while ( (unsigned int)v16 < *((_DWORD *)this + 4) );
    }
    EnterCriticalSection((LPCRITICAL_SECTION)v8);
    v28 = *(_DWORD *)(v8 + 60);
    LeaveCriticalSection((LPCRITICAL_SECTION)v8);
    if ( v28 )
    {
      if ( a4 )
      {
        result = ListenerRegistration::TrackRegistration(v8);
        if ( (int)result >= 0 )
          *a4 = v8;
      }
      else
      {
        return 2147500035LL;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, this, v15);
      }
      operator delete(*(void **)(v8 + 64));
      DeleteCriticalSection((LPCRITICAL_SECTION)v8);
      operator delete((void *)v8);
      return (unsigned int)v15;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, this);
    }
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x180016a30  mov     [rsp+arg_0], rbx
0x180016a35  mov     [rsp+arg_8], rbp
0x180016a3a  mov     [rsp+arg_18], r9
0x180016a3f  push    rsi
0x180016a40  push    rdi
0x180016a41  push    r12
0x180016a43  push    r13
0x180016a45  push    r14
0x180016a47  sub     rsp, 50h
0x180016a4b  mov     rdi, r8
0x180016a4e  mov     rbp, rdx
0x180016a51  mov     r14, rcx
0x180016a54  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016a5b  mov     ecx, 48h ; 'H'; unsigned __int64
0x180016a60  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180016a65  mov     rsi, rax
0x180016a68  mov     [rsp+78h+var_40], rax
0x180016a6d  test    rax, rax
0x180016a70  jz      short loc_180016AF1
0x180016a72  mov     ebx, [r14+10h]
0x180016a76  mov     rcx, rax; lpCriticalSection
0x180016a79  call    cs:__imp_InitializeCriticalSection
0x180016a7f  nop
0x180016a80  mov     [rsi+28h], rbp
0x180016a84  mov     [rsi+30h], rdi
0x180016a88  mov     [rsi+38h], ebx
0x180016a8b  mov     dword ptr [rsi+3Ch], 0
0x180016a92  mov     qword ptr [rsi+40h], 0
0x180016a9a  test    ebx, ebx
0x180016a9c  jz      short loc_180016AEF
0x180016a9e  mov     eax, 10h
0x180016aa3  mul     rbx
0x180016aa6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180016aad  cmovb   rax, rcx
0x180016ab1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180016ab8  mov     rcx, rax; unsigned __int64
0x180016abb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180016ac0  mov     rdi, rax
0x180016ac3  mov     [rsp+78h+var_48], rax
0x180016ac8  test    rax, rax
0x180016acb  jz      short loc_180016AE9
0x180016acd  mov     rbp, rax
0x180016ad0  test    rbx, rbx
0x180016ad3  jz      short loc_180016AEB
0x180016ad5  mov     rcx, rbp; this
0x180016ad8  call    ??0RegistrationPair@ListenerRegistration@@QEAA@XZ; ListenerRegistration::RegistrationPair::RegistrationPair(void)
0x180016add  add     rbp, 10h
0x180016ae1  sub     rbx, 1
0x180016ae5  jnz     short loc_180016AD5
0x180016ae7  jmp     short loc_180016AEB
0x180016ae9  xor     edi, edi
0x180016aeb  mov     [rsi+40h], rdi
0x180016aef  jmp     short loc_180016AF3
0x180016af1  xor     esi, esi
0x180016af3  test    rsi, rsi
0x180016af6  jz      loc_180016D56
0x180016afc  mov     rcx, rsi; lpCriticalSection
0x180016aff  call    cs:__imp_EnterCriticalSection
0x180016b05  cmp     dword ptr [rsi+38h], 0
0x180016b09  jz      short loc_180016B16
0x180016b0b  cmp     qword ptr [rsi+40h], 0
0x180016b10  jnz     short loc_180016B16
0x180016b12  xor     bl, bl
0x180016b14  jmp     short loc_180016B18
0x180016b16  mov     bl, 1
0x180016b18  mov     rcx, rsi; lpCriticalSection
0x180016b1b  call    cs:__imp_LeaveCriticalSection
0x180016b21  test    bl, bl
0x180016b23  jz      loc_180016D56
0x180016b29  xor     r13d, r13d
0x180016b2c  xor     r12d, r12d
0x180016b2f  lea     rbp, WPP_GLOBAL_Control
0x180016b36  cmp     [r14+10h], r12d
0x180016b3a  jbe     loc_180016CC6
0x180016b40  mov     ebx, [rsp+78h+var_34]
0x180016b44  mov     r10, cs:WPP_GLOBAL_Control
0x180016b4b  mov     [rsp+78h+var_48], 0
0x180016b54  mov     rax, [r14+18h]
0x180016b58  mov     rdi, [rax+r12*8]
0x180016b5c  mov     [rsp+78h+var_40], rdi
0x180016b61  cmp     r10, rbp
0x180016b64  jz      short loc_180016B8C
0x180016b66  cmp     byte ptr [r10+19h], 4
0x180016b6b  jb      short loc_180016B8C
0x180016b6d  test    byte ptr [r10+1Ch], 1
0x180016b72  jz      short loc_180016B8C
0x180016b74  mov     edx, 2Eh ; '.'
0x180016b79  mov     r9, rdi
0x180016b7c  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180016b83  mov     rcx, [r10+10h]
0x180016b87  call    WPP_SF_q
0x180016b8c  lea     r8, [rsp+78h+var_48]
0x180016b91  lea     rdx, ListenerCallbackAdapter
0x180016b98  mov     rcx, rsi
0x180016b9b  mov     rax, [rdi+90h]
0x180016ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ba7  mov     edi, eax
0x180016ba9  mov     r10, cs:WPP_GLOBAL_Control
0x180016bb0  cmp     r10, rbp
0x180016bb3  jz      short loc_180016BF0
0x180016bb5  cmp     byte ptr [r10+19h], 4
0x180016bba  jb      short loc_180016BF0
0x180016bbc  test    byte ptr [r10+1Ch], 1
0x180016bc1  jz      short loc_180016BF0
0x180016bc3  xor     ecx, ecx
0x180016bc5  test    eax, eax
0x180016bc7  cmovz   rcx, [rsp+78h+var_48]
0x180016bcd  mov     edx, 2Fh ; '/'
0x180016bd2  mov     [rsp+78h+var_50], rcx
0x180016bd7  mov     [rsp+78h+var_58], eax
0x180016bdb  mov     r9, [rsp+78h+var_40]
0x180016be0  mov     rcx, [r10+10h]
0x180016be4  call    WPP_SF_qDq
0x180016be9  mov     r10, cs:WPP_GLOBAL_Control
0x180016bf0  test    edi, edi
0x180016bf2  jle     short loc_180016BFF
0x180016bf4  movzx   edi, di
0x180016bf7  or      edi, 80070000h
0x180016bfd  test    edi, edi
0x180016bff  jns     short loc_180016C4A
0x180016c01  test    r13d, r13d
0x180016c04  cmovns  r13d, edi
0x180016c08  cmp     r10, rbp
0x180016c0b  jz      loc_180016CB9
0x180016c11  cmp     byte ptr [r10+19h], 1
0x180016c16  jb      loc_180016CB9
0x180016c1c  test    byte ptr [r10+1Ch], 1
0x180016c21  jz      loc_180016CB9
0x180016c27  mov     edx, 7Ah ; 'z'
0x180016c2c  mov     dword ptr [rsp+78h+var_50], edi
0x180016c30  mov     [rsp+78h+var_58], r12d
0x180016c35  mov     r9, r14
0x180016c38  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180016c3f  mov     rcx, [r10+10h]
0x180016c43  call    WPP_SF_qDd
0x180016c48  jmp     short loc_180016CB2
0x180016c4a  mov     rdi, [rsp+78h+var_48]
0x180016c4f  mov     rcx, rsi; lpCriticalSection
0x180016c52  call    cs:__imp_EnterCriticalSection
0x180016c58  mov     ecx, [rsi+3Ch]
0x180016c5b  add     rcx, rcx
0x180016c5e  mov     rax, [rsi+40h]
0x180016c62  mov     [rax+rcx*8], rdi
0x180016c66  mov     [rax+rcx*8+8], r12d
0x180016c6b  mov     [rax+rcx*8+0Ch], ebx
0x180016c6f  inc     dword ptr [rsi+3Ch]
0x180016c72  mov     rcx, rsi; lpCriticalSection
0x180016c75  call    cs:__imp_LeaveCriticalSection
0x180016c7b  mov     r10, cs:WPP_GLOBAL_Control
0x180016c82  cmp     r10, rbp
0x180016c85  jz      short loc_180016CB9
0x180016c87  cmp     byte ptr [r10+19h], 4
0x180016c8c  jb      short loc_180016CB9
0x180016c8e  test    byte ptr [r10+1Ch], 1
0x180016c93  jz      short loc_180016CB9
0x180016c95  mov     edx, 7Bh ; '{'
0x180016c9a  mov     [rsp+78h+var_58], r12d
0x180016c9f  mov     r9, r14
0x180016ca2  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180016ca9  mov     rcx, [r10+10h]
0x180016cad  call    WPP_SF_qD
0x180016cb2  mov     r10, cs:WPP_GLOBAL_Control
0x180016cb9  inc     r12d
0x180016cbc  cmp     r12d, [r14+10h]
0x180016cc0  jb      loc_180016B4B
0x180016cc6  mov     rcx, rsi; lpCriticalSection
0x180016cc9  call    cs:__imp_EnterCriticalSection
0x180016ccf  mov     ebx, [rsi+3Ch]
0x180016cd2  mov     rcx, rsi; lpCriticalSection
0x180016cd5  call    cs:__imp_LeaveCriticalSection
0x180016cdb  test    ebx, ebx
0x180016cdd  jnz     short loc_180016D31
0x180016cdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180016ce6  cmp     rcx, rbp
0x180016ce9  jz      short loc_180016D12
0x180016ceb  cmp     byte ptr [rcx+19h], 1
0x180016cef  jb      short loc_180016D12
0x180016cf1  test    byte ptr [rcx+1Ch], 1
0x180016cf5  jz      short loc_180016D12
0x180016cf7  lea     edx, [rbx+7Ch]
0x180016cfa  mov     [rsp+78h+var_58], r13d
0x180016cff  mov     r9, r14
0x180016d02  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180016d09  mov     rcx, [rcx+10h]
0x180016d0d  call    WPP_SF_qD
0x180016d12  mov     rcx, [rsi+40h]; Block
0x180016d16  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016d1b  mov     rcx, rsi; lpCriticalSection
0x180016d1e  call    cs:__imp_DeleteCriticalSection
0x180016d24  mov     rcx, rsi; Block
0x180016d27  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016d2c  mov     eax, r13d
0x180016d2f  jmp     short loc_180016D92
0x180016d31  mov     rbx, [rsp+78h+arg_18]
0x180016d39  test    rbx, rbx
0x180016d3c  jnz     short loc_180016D45
0x180016d3e  mov     eax, 80004003h
0x180016d43  jmp     short loc_180016D92
0x180016d45  mov     rcx, rsi; unsigned __int64
0x180016d48  call    ?TrackRegistration@ListenerRegistration@@SAJ_K@Z; ListenerRegistration::TrackRegistration(unsigned __int64)
0x180016d4d  test    eax, eax
0x180016d4f  js      short loc_180016D92
0x180016d51  mov     [rbx], rsi
0x180016d54  jmp     short loc_180016D92
0x180016d56  lea     rbp, WPP_GLOBAL_Control
0x180016d5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d64  cmp     rcx, rbp
0x180016d67  jz      short loc_180016D8D
0x180016d69  cmp     byte ptr [rcx+19h], 1
0x180016d6d  jb      short loc_180016D8D
0x180016d6f  test    byte ptr [rcx+1Ch], 1
0x180016d73  jz      short loc_180016D8D
0x180016d75  mov     edx, 79h ; 'y'
0x180016d7a  mov     r9, r14
0x180016d7d  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180016d84  mov     rcx, [rcx+10h]
0x180016d88  call    WPP_SF_q
0x180016d8d  mov     eax, 8007000Eh
0x180016d92  lea     r11, [rsp+78h+var_28]
0x180016d97  mov     rbx, [r11+30h]
0x180016d9b  mov     rbp, [r11+38h]
0x180016d9f  mov     rsp, r11
0x180016da2  pop     r14
0x180016da4  pop     r13
0x180016da6  pop     r12
0x180016da8  pop     rdi
0x180016da9  pop     rsi
0x180016daa  retn
```
