# ClfsAdvanceLogBaseInternal

- ea: `0x140078270`
- end: `0x1400784de`
- name: `ClfsAdvanceLogBaseInternal`
- size: `622`
- prototype: `__int64 __fastcall(struct _FILE_OBJECT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140034a38`

## callees

- `0x14000c2f0`
- `0x14000ed64`
- `0x140017f20`
- `0x140058670`
- `0x140059e80`
- `0x140078270`
- `0x1400784e4`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400782a7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400782a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140078472`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007cbf2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140078472`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007cbf2`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007834a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14007834a`

## pseudocode

```c
__int64 __fastcall ClfsAdvanceLogBaseInternal(struct _FILE_OBJECT *a1, __int64 a2, union _CLS_LSN *a3)
{
  CClfsRequest *v5; // rdi
  struct CClfsLogFcbCommon *v6; // rsi
  CClfsLogCcb *FsContext2; // r13
  int v8; // ebx
  CClfsRequest *v9; // rax
  CClfsRequest *v10; // rbx
  __int64 v12; // [rsp+30h] [rbp-58h]
  CClfsRequest *v13; // [rsp+38h] [rbp-50h]

  if ( a1 && (v5 = 0, a3) )
  {
    KeEnterCriticalRegion();
    v6 = (struct CClfsLogFcbCommon *)*((_QWORD *)a1->FsContext + 15);
    FsContext2 = (CClfsLogCcb *)a1->FsContext2;
    (*(void (__fastcall **)(struct CClfsLogFcbCommon *))(*(_QWORD *)v6 + 64LL))(v6);
    CClfsLogCcb::AddRef(FsContext2);
    v8 = 0;
    if ( !*(_BYTE *)(*((_QWORD *)FsContext2 + 9) + 75LL) )
      v8 = -1073741790;
    HIDWORD(v12) = v8;
    LODWORD(v12) = v8;
    if ( v8 >= 0 )
    {
      v9 = (CClfsRequest *)ExAllocateFromNPagedLookasideList(&CClfsRequest::m_laList);
      if ( v9 )
        v10 = CClfsRequest::CClfsRequest(v9, a1, v6, FsContext2);
      else
        v10 = 0;
      if ( v10 )
      {
        v5 = v10;
        v13 = v10;
        (**(void (__fastcall ***)(CClfsRequest *))v10)(v10);
        v8 = CClfsRequest::AdvanceLogBase(v10, a3);
        LODWORD(v12) = v8;
        if ( v8 < 0
          && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
        {
          WPP_SF_slD(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            205,
            (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
            (unsigned int)"ClfsAdvanceLogBaseInternal",
            78,
            v8,
            v12,
            v13);
        }
      }
      else
      {
        v8 = -1073741670;
        LODWORD(v12) = -1073741670;
        if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
        {
          WPP_SF_slD(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            204,
            (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
            (unsigned int)"ClfsAdvanceLogBaseInternal",
            50,
            -1073741670,
            v12,
            0);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        203,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsAdvanceLogBaseInternal",
        32,
        v8,
        v12,
        0);
    }
    if ( v5 )
      (*(void (__fastcall **)(CClfsRequest *))(*(_QWORD *)v5 + 8LL))(v5);
    CClfsLogCcb::Release((volatile signed __int32 *)FsContext2);
    (*(void (__fastcall **)(struct CClfsLogFcbCommon *))(*(_QWORD *)v6 + 72LL))(v6);
    KeLeaveCriticalRegion();
    return (unsigned int)v8;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        202,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsAdvanceLogBaseInternal",
        250,
        -1073741811);
    }
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x140078270  push    rbx
0x140078272  push    rsi
0x140078273  push    rdi
0x140078274  push    r13
0x140078276  push    r14
0x140078278  push    r15
0x14007827a  sub     rsp, 58h
0x14007827e  mov     r15, r8
0x140078281  mov     r14, rcx
0x140078284  test    rcx, rcx
0x140078287  jz      loc_140078482
0x14007828d  xor     edi, edi
0x14007828f  mov     [rsp+88h+var_50], rdi
0x140078294  mov     [rsp+88h+var_40], rdi
0x140078299  mov     [rsp+88h+var_48], rdi
0x14007829e  test    r8, r8
0x1400782a1  jz      loc_140078482
0x1400782a7  call    cs:__imp_KeEnterCriticalRegion
0x1400782ae  nop     dword ptr [rax+rax+00h]
0x1400782b3  mov     rax, [r14+18h]
0x1400782b7  mov     rsi, [rax+78h]
0x1400782bb  mov     [rsp+88h+arg_0], rsi
0x1400782c3  mov     [rsp+88h+var_40], rsi
0x1400782c8  mov     r13, [r14+20h]
0x1400782cc  mov     [rsp+88h+var_48], r13
0x1400782d1  mov     rax, [rsi]
0x1400782d4  mov     rax, [rax+40h]
0x1400782d8  mov     rcx, rsi
0x1400782db  call    _guard_dispatch_icall
0x1400782e0  mov     rcx, r13; this
0x1400782e3  call    ?AddRef@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::AddRef(void)
0x1400782e8  mov     [rsp+88h+var_54], edi
0x1400782ec  mov     rax, [r13+48h]
0x1400782f0  xor     ebx, ebx
0x1400782f2  mov     ecx, 0C0000022h
0x1400782f7  cmp     [rax+4Bh], bl
0x1400782fa  cmovz   ebx, ecx
0x1400782fd  mov     [rsp+88h+var_54], ebx
0x140078301  mov     [rsp+88h+var_58], ebx
0x140078305  test    ebx, ebx
0x140078307  jns     short loc_140078343
0x140078309  lea     rax, WPP_GLOBAL_Control
0x140078310  mov     rcx, cs:WPP_GLOBAL_Control
0x140078317  cmp     rcx, rax
0x14007831a  jz      loc_140078447
0x140078320  mov     eax, [rcx+2Ch]
0x140078323  bt      eax, 1Ah
0x140078327  jnb     loc_140078447
0x14007832d  mov     edx, 0CBh
0x140078332  mov     [rsp+88h+var_60], ebx
0x140078336  mov     [rsp+88h+var_68], 1820h
0x14007833e  jmp     loc_14007842F
0x140078343  lea     rcx, ?m_laList@CClfsRequest@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x14007834a  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140078351  nop     dword ptr [rax+rax+00h]
0x140078356  test    rax, rax
0x140078359  jz      short loc_140078371
0x14007835b  mov     r9, r13; struct CClfsLogCcb *
0x14007835e  mov     r8, rsi; struct CClfsLogFcbCommon *
0x140078361  mov     rdx, r14; struct _FILE_OBJECT *
0x140078364  mov     rcx, rax; this
0x140078367  call    ??0CClfsRequest@@QEAA@PEAU_FILE_OBJECT@@PEAVCClfsLogFcbCommon@@PEAVCClfsLogCcb@@@Z; CClfsRequest::CClfsRequest(_FILE_OBJECT *,CClfsLogFcbCommon *,CClfsLogCcb *)
0x14007836c  mov     rbx, rax
0x14007836f  jmp     short loc_140078373
0x140078371  xor     ebx, ebx
0x140078373  test    rbx, rbx
0x140078376  jnz     short loc_1400783BC
0x140078378  mov     ebx, 0C000009Ah
0x14007837d  mov     [rsp+88h+var_58], ebx
0x140078381  lea     rax, WPP_GLOBAL_Control
0x140078388  mov     rcx, cs:WPP_GLOBAL_Control
0x14007838f  cmp     rcx, rax
0x140078392  jz      loc_140078447
0x140078398  mov     eax, [rcx+2Ch]
0x14007839b  bt      eax, 1Ah
0x14007839f  jnb     loc_140078447
0x1400783a5  mov     edx, 0CCh
0x1400783aa  mov     [rsp+88h+var_60], 0C000009Ah
0x1400783b2  mov     [rsp+88h+var_68], 1832h
0x1400783ba  jmp     short loc_14007842F
0x1400783bc  mov     rdi, rbx
0x1400783bf  mov     [rsp+88h+var_50], rbx
0x1400783c4  mov     rax, [rbx]
0x1400783c7  mov     rax, [rax]
0x1400783ca  mov     rcx, rbx
0x1400783cd  call    _guard_dispatch_icall
0x1400783d2  nop
0x1400783d3  mov     rdx, r15; union _CLS_LSN *
0x1400783d6  mov     rcx, rbx; this
0x1400783d9  call    ?AdvanceLogBase@CClfsRequest@@QEAAJAEAT_CLS_LSN@@@Z; CClfsRequest::AdvanceLogBase(_CLS_LSN &)
0x1400783de  mov     ebx, eax
0x1400783e0  mov     [rsp+88h+var_58], eax
0x1400783e4  jmp     short loc_1400783FE
0x1400783e6  mov     ebx, eax
0x1400783e8  mov     [rsp+88h+var_58], eax
0x1400783ec  mov     rdi, [rsp+88h+var_50]
0x1400783f1  mov     r13, [rsp+88h+var_48]
0x1400783f6  mov     rsi, [rsp+88h+arg_0]
0x1400783fe  test    ebx, ebx
0x140078400  jns     short loc_140078447
0x140078402  lea     rax, WPP_GLOBAL_Control
0x140078409  mov     rcx, cs:WPP_GLOBAL_Control
0x140078410  cmp     rcx, rax
0x140078413  jz      short loc_140078447
0x140078415  mov     eax, [rcx+2Ch]
0x140078418  bt      eax, 1Ah
0x14007841c  jnb     short loc_140078447
0x14007841e  mov     edx, 0CDh
0x140078423  mov     [rsp+88h+var_60], ebx
0x140078427  mov     [rsp+88h+var_68], 184Eh
0x14007842f  lea     r9, aClfsadvancelog; "ClfsAdvanceLogBaseInternal"
0x140078436  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14007843d  mov     rcx, [rcx+18h]
0x140078441  call    WPP_SF_slD
0x140078446  nop
0x140078447  test    rdi, rdi
0x14007844a  jz      short loc_14007845B
0x14007844c  mov     rax, [rdi]
0x14007844f  mov     rax, [rax+8]
0x140078453  mov     rcx, rdi
0x140078456  call    _guard_dispatch_icall
0x14007845b  mov     rcx, r13; Entry
0x14007845e  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x140078463  mov     rax, [rsi]
0x140078466  mov     rax, [rax+48h]
0x14007846a  mov     rcx, rsi
0x14007846d  call    _guard_dispatch_icall
0x140078472  call    cs:__imp_KeLeaveCriticalRegion
0x140078479  nop     dword ptr [rax+rax+00h]
0x14007847e  mov     eax, ebx
0x140078480  jmp     short loc_1400784CF
0x140078482  lea     rax, WPP_GLOBAL_Control
0x140078489  mov     rcx, cs:WPP_GLOBAL_Control
0x140078490  cmp     rcx, rax
0x140078493  jz      short loc_1400784CA
0x140078495  test    dword ptr [rcx+2Ch], 4000000h
0x14007849c  jz      short loc_1400784CA
0x14007849e  mov     edx, 0CAh
0x1400784a3  mov     [rsp+88h+var_60], 0C000000Dh
0x1400784ab  mov     [rsp+88h+var_68], 17FAh
0x1400784b3  lea     r9, aClfsadvancelog; "ClfsAdvanceLogBaseInternal"
0x1400784ba  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x1400784c1  mov     rcx, [rcx+18h]
0x1400784c5  call    WPP_SF_slD
0x1400784ca  mov     eax, 0C000000Dh
0x1400784cf  add     rsp, 58h
0x1400784d3  pop     r15
0x1400784d5  pop     r14
0x1400784d7  pop     r13
0x1400784d9  pop     rdi
0x1400784da  pop     rsi
0x1400784db  pop     rbx
0x1400784dc  retn
0x14007cb99  push    rbp
0x14007cb9b  sub     rsp, 30h
0x14007cb9f  mov     rbp, rdx
0x14007cba2  mov     rcx, [rbp+38h]
0x14007cba6  test    rcx, rcx
0x14007cba9  jz      short loc_14007CBBF
0x14007cbab  mov     rax, [rcx]
0x14007cbae  mov     rax, [rax+8]
0x14007cbb2  call    _guard_dispatch_icall
0x14007cbb7  mov     qword ptr [rbp+38h], 0
0x14007cbbf  mov     rcx, [rbp+40h]; Entry
0x14007cbc3  test    rcx, rcx
0x14007cbc6  jz      short loc_14007CBD5
0x14007cbc8  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x14007cbcd  mov     qword ptr [rbp+40h], 0
0x14007cbd5  mov     rcx, [rbp+48h]
0x14007cbd9  test    rcx, rcx
0x14007cbdc  jz      short loc_14007CBF2
0x14007cbde  mov     rax, [rcx]
0x14007cbe1  mov     rax, [rax+48h]
0x14007cbe5  call    _guard_dispatch_icall
0x14007cbea  mov     qword ptr [rbp+48h], 0
0x14007cbf2  call    cs:__imp_KeLeaveCriticalRegion
0x14007cbf9  nop     dword ptr [rax+rax+00h]
0x14007cbfe  nop
0x14007cbff  add     rsp, 30h
0x14007cc03  pop     rbp
0x14007cc04  retn
```
