# IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_CREATE_APP_CONTEXT_DATA const *,Windows::Isolation::Rtl::_CREATE_APPLICATION_CONTEXT_DATA * &)

- ea: `0x180030b70`
- end: `0x180030f88`
- name: `?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_CREATE_APP_CONTEXT_DATA@@AEAPEAU_CREATE_APPLICATION_CONTEXT_DATA@Rtl@Isolation@Windows@@@Z`
- size: `1048`
- prototype: `__int64 __fastcall(IsolationImplementation::Com *__hidden this, struct _RTL_ALLOCATION_LIST *, const struct _CREATE_APP_CONTEXT_DATA *, struct Windows::Isolation::Rtl::_CREATE_APPLICATION_CONTEXT_DATA **)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180012dd0`

## callees

- `0x180012910`
- `0x180012acc`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x18002dde4`
- `0x18002decc`
- `0x180030b70`
- `0x180031118`
- `0x1800312c4`
- `0x180031454`
- `0x18003194c`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180030bfc`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180030e56`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180030e91`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180030ebf`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180030efa`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180030bfc`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180030e56`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180030e91`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180030ebf`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180030efa`

## string_xrefs

- `0x180030b98`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`
- `0x180030c8c`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`
- `0x180030e62`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::ConvertIn(
        IsolationImplementation::Com *this,
        struct _RTL_ALLOCATION_LIST *a2,
        const struct _CREATE_APP_CONTEXT_DATA *a3,
        struct Windows::Isolation::Rtl::_CREATE_APPLICATION_CONTEXT_DATA **a4)
{
  char *v5; // rdx
  _BYTE *v7; // r13
  int v8; // eax
  struct Windows::Isolation::Rtl::_CREATE_APPLICATION_CONTEXT_DATA_CUSTOM_STORE_LIST **v9; // r9
  unsigned int v10; // ebx
  __int64 v11; // r8
  int v12; // edx
  unsigned int v13; // ebx
  _OWORD *v14; // rsi
  struct _RTL_ALLOCATION_LIST **v15; // r12
  struct _RTL_ALLOCATION_LIST *v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  char *v19; // r14
  struct _RTL_ALLOCATION_LIST *v20; // rdx
  char *v21; // r12
  struct _RTL_ALLOCATION_LIST *v22; // rdx
  char *v23; // rcx
  struct _RTL_ALLOCATION_LIST **v24; // rdx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int AllocationListArray; // eax
  _OWORD *v30; // r8
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rdx
  unsigned int v35; // [rsp+20h] [rbp-40h]
  __int64 v36; // [rsp+30h] [rbp-30h] BYREF
  __int64 v37; // [rsp+38h] [rbp-28h] BYREF
  const char *v38; // [rsp+40h] [rbp-20h] BYREF
  int v39; // [rsp+48h] [rbp-18h]
  unsigned int v40; // [rsp+50h] [rbp-10h]
  _OWORD *v41; // [rsp+A8h] [rbp+48h] BYREF
  const struct _CREATE_APP_CONTEXT_DATA *v42; // [rsp+B0h] [rbp+50h]
  __int64 v43; // [rsp+B8h] [rbp+58h] BYREF

  v42 = a3;
  v40 = -2147023537;
  v5 = (char *)a2 + *(unsigned int *)a2;
  v38 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp";
  v41 = 0;
  v7 = (char *)a2 + 4;
  if ( (char *)a2 + 4 > v5 )
  {
    v39 = 782;
LABEL_39:
    Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v38);
    return v40;
  }
  if ( (char *)a2 + 8 > v5 )
  {
    v39 = 783;
    goto LABEL_39;
  }
  v8 = RtlAllocateAllocationListMemory(this, 56, 0, &v41);
  v10 = v8;
  if ( v8 >= 0 )
  {
    v14 = v41;
    *v41 = 0;
    v14[1] = 0;
    v14[2] = 0;
    *((_QWORD *)v14 + 6) = 0;
    *(_QWORD *)v14 = 56;
    v15 = (struct _RTL_ALLOCATION_LIST **)((char *)a2 + 16);
    *((_DWORD *)v14 + 2) = 0;
    if ( (*v7 & 1) != 0 )
    {
      if ( v15 > (struct _RTL_ALLOCATION_LIST **)((char *)a2 + *(unsigned int *)a2) )
      {
        v39 = 797;
        goto LABEL_39;
      }
      v16 = (struct _RTL_ALLOCATION_LIST *)*((_QWORD *)a2 + 1);
      v41 = 0;
      v17 = IsolationImplementation::Com::ConvertIn(
              this,
              v16,
              (const struct _CREATE_APP_CONTEXT_DATA_CUSTOM_STORE_LIST *)&v41,
              v9);
      v13 = v17;
      if ( v17 < 0 )
      {
        v18 = 805;
LABEL_15:
        Windows::ErrorHandling::COM::ReportErrorPropagation(
          (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp",
          (const char *)v18,
          v17,
          (int)v9);
        return v13;
      }
      v19 = (char *)a2 + 4;
      *((_QWORD *)v14 + 2) = v41;
      *((_DWORD *)v14 + 2) |= 1u;
    }
    else
    {
      v19 = (char *)a2 + 4;
    }
    if ( (*v7 & 2) != 0 )
    {
      if ( (char *)a2 + 24 > (char *)a2 + *(unsigned int *)a2 )
      {
        v39 = 813;
        goto LABEL_39;
      }
      v20 = *v15;
      v41 = 0;
      v17 = IsolationImplementation::Com::ConvertIn(this, v20, (const struct _CULTURE_FALLBACK_LIST *)&v41, v9);
      v13 = v17;
      if ( v17 < 0 )
      {
        v18 = 821;
        goto LABEL_15;
      }
      v21 = (char *)a2 + 4;
      *((_QWORD *)v14 + 3) = v41;
      *((_DWORD *)v14 + 2) |= 2u;
    }
    else
    {
      v21 = v19;
    }
    if ( (*v19 & 4) != 0 )
    {
      if ( (char *)a2 + 32 > (char *)a2 + *(unsigned int *)a2 )
      {
        v39 = 829;
        goto LABEL_39;
      }
      v22 = (struct _RTL_ALLOCATION_LIST *)*((_QWORD *)a2 + 3);
      v41 = 0;
      v17 = IsolationImplementation::Com::ConvertIn(
              this,
              v22,
              (const struct _CREATE_APP_CONTEXT_DATA_PROCESSOR_ARCHITECTURE_FALLBACK_LIST *)&v41,
              v9);
      v13 = v17;
      if ( v17 < 0 )
      {
        v18 = 837;
        goto LABEL_15;
      }
      v19 = v21;
      *((_QWORD *)v14 + 4) = v41;
      *((_DWORD *)v14 + 2) |= 4u;
    }
    if ( (*v19 & 8) != 0 )
    {
      if ( (char *)a2 + 42 > (char *)a2 + *(unsigned int *)a2 )
      {
        v39 = 845;
        goto LABEL_39;
      }
      v23 = (char *)a2 + 40;
      *((_WORD *)v14 + 24) = *((_WORD *)a2 + 20);
      *((_DWORD *)v14 + 2) |= 8u;
    }
    else
    {
      v23 = (char *)a2 + 40;
    }
    if ( (*v7 & 0x10) != 0 )
    {
      if ( v23 > (char *)a2 + *(unsigned int *)a2 )
      {
        v39 = 853;
        goto LABEL_39;
      }
      v24 = (struct _RTL_ALLOCATION_LIST **)*((_QWORD *)a2 + 4);
      v41 = 0;
      v17 = IsolationImplementation::Com::ConvertIn(this, v24, (const struct _CREATE_APP_CONTEXT_DATA_SOURCE *)&v41, v9);
      v13 = v17;
      if ( v17 < 0 )
      {
        v18 = 861;
        goto LABEL_15;
      }
      *((_QWORD *)v14 + 5) = v41;
      v25 = *((_DWORD *)v14 + 2) | 0x10;
      *((_DWORD *)v14 + 2) = v25;
      if ( (v25 & 1) == 0 )
      {
        v41 = 0;
        v43 = 0;
        v36 = 0;
        v37 = 0;
        if ( *((_QWORD *)v14 + 2) )
        {
          v39 = 877;
          Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(
            &v38,
            &v38);
          return v40;
        }
        v26 = RtlAllocateAllocationListMemory(this, 32, 0, &v41);
        v10 = v26;
        if ( v26 < 0 )
        {
          if ( v26 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          v11 = 879;
          goto LABEL_9;
        }
        v27 = RtlAllocateAllocationListMemory(this, 24, 0, &v36);
        v10 = v27;
        if ( v27 < 0 )
        {
          if ( v27 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          v11 = 880;
          goto LABEL_9;
        }
        v28 = RtlAllocateAllocationListMemory(this, 24, 0, &v37);
        v10 = v28;
        if ( v28 < 0 )
        {
          if ( v28 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          v11 = 881;
          goto LABEL_9;
        }
        AllocationListArray = RtlAllocateAllocationListArray((_DWORD)this, 2, 8, 0, (__int64)&v43);
        v10 = AllocationListArray;
        if ( AllocationListArray < 0 )
        {
          if ( AllocationListArray == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          v11 = 882;
          goto LABEL_9;
        }
        v30 = v41;
        v31 = v36;
        v32 = v37;
        v33 = v43;
        *(_QWORD *)v41 = 32;
        *((_DWORD *)v30 + 2) = 0;
        *((_QWORD *)v30 + 2) = 0;
        *((_QWORD *)v30 + 3) = v33;
        *(_QWORD *)v31 = 24;
        *(_DWORD *)(v31 + 8) = 0;
        *(_DWORD *)(v31 + 12) = 2;
        *(_QWORD *)(v31 + 16) = 0;
        *(_QWORD *)v32 = 24;
        *(_DWORD *)(v32 + 8) = 0;
        *(_DWORD *)(v32 + 12) = 1;
        *(_QWORD *)(v32 + 16) = 0;
        *(_QWORD *)(v33 + 8LL * (*((_QWORD *)v30 + 2))++) = v31;
        *((_DWORD *)v14 + 2) |= 1u;
        *((_QWORD *)v14 + 2) = v30;
      }
    }
    v13 = 0;
    *(_QWORD *)v42 = v14;
    return v13;
  }
  if ( v8 == g_NTSTATUS_to_break_on_propagate )
    DebugBreak();
  v11 = 788;
LABEL_9:
  Windows::ErrorHandling::COM::ReportError(
    (Windows::ErrorHandling::COM *)"Status propagated",
    "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp",
    (const char *)v11,
    v10,
    v35);
  return (unsigned int)Windows::ErrorHandling::COM::ConvertNtStatusToHResult((Windows::ErrorHandling::COM *)v10, v12);
}

```

## disassembly

```asm
0x180030b70  mov     [rsp-38h+arg_0], rbx
0x180030b75  mov     [rsp-38h+arg_10], r8
0x180030b7a  push    rbp
0x180030b7b  push    rsi
0x180030b7c  push    rdi
0x180030b7d  push    r12
0x180030b7f  push    r13
0x180030b81  push    r14
0x180030b83  push    r15
0x180030b85  mov     rbp, rsp
0x180030b88  sub     rsp, 60h
0x180030b8c  mov     rdi, rdx
0x180030b8f  mov     [rbp+var_10], 8007054Fh
0x180030b96  mov     edx, [rdx]
0x180030b98  lea     rsi, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180030b9f  add     rdx, rdi
0x180030ba2  mov     [rbp+var_20], rsi
0x180030ba6  mov     r15, rcx
0x180030ba9  mov     [rbp+arg_8], 0
0x180030bb1  lea     r13, [rdi+4]
0x180030bb5  cmp     r13, rdx
0x180030bb8  jbe     short loc_180030BC6
0x180030bba  mov     [rbp+var_18], 30Eh
0x180030bc1  jmp     loc_180030DB5
0x180030bc6  lea     r14, [rdi+8]
0x180030bca  cmp     r14, rdx
0x180030bcd  jbe     short loc_180030BDB
0x180030bcf  mov     [rbp+var_18], 30Fh
0x180030bd6  jmp     loc_180030DB5
0x180030bdb  xor     r8d, r8d
0x180030bde  lea     r9, [rbp+arg_8]
0x180030be2  lea     r12d, [r8+38h]
0x180030be6  mov     edx, r12d
0x180030be9  call    RtlAllocateAllocationListMemory
0x180030bee  mov     ebx, eax
0x180030bf0  test    eax, eax
0x180030bf2  jns     short loc_180030C28
0x180030bf4  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180030bfa  jnz     short loc_180030C02
0x180030bfc  call    cs:__imp_DebugBreak
0x180030c02  mov     r8d, 314h; char *
0x180030c08  mov     rdx, rsi; char *
0x180030c0b  mov     r9d, ebx; int
0x180030c0e  lea     rcx, aStatusPropagat; "Status propagated"
0x180030c15  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180030c1a  mov     ecx, ebx; this
0x180030c1c  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x180030c21  mov     ebx, eax
0x180030c23  jmp     loc_180030F6E
0x180030c28  mov     rsi, [rbp+arg_8]
0x180030c2c  xorps   xmm0, xmm0
0x180030c2f  xor     eax, eax
0x180030c31  movups  xmmword ptr [rsi], xmm0
0x180030c34  movups  xmmword ptr [rsi+10h], xmm0
0x180030c38  movups  xmmword ptr [rsi+20h], xmm0
0x180030c3c  mov     [rsi+30h], rax
0x180030c40  mov     [rsi], r12
0x180030c43  lea     r12, [rdi+10h]
0x180030c47  mov     [rsi+8], eax
0x180030c4a  test    byte ptr [r13+0], 1
0x180030c4f  jz      short loc_180030CAF
0x180030c51  mov     eax, [rdi]
0x180030c53  add     rax, rdi
0x180030c56  cmp     r12, rax
0x180030c59  jbe     short loc_180030C67
0x180030c5b  mov     [rbp+var_18], 31Dh
0x180030c62  jmp     loc_180030DB5
0x180030c67  mov     rdx, [r14]; struct _RTL_ALLOCATION_LIST *
0x180030c6a  lea     r8, [rbp+arg_8]; struct _CREATE_APP_CONTEXT_DATA_CUSTOM_STORE_LIST *
0x180030c6e  mov     rcx, r15; this
0x180030c71  mov     [rbp+arg_8], 0
0x180030c79  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_CREATE_APP_CONTEXT_DATA_CUSTOM_STORE_LIST@@AEAPEAU_CREATE_APPLICATION_CONTEXT_DATA_CUSTOM_STORE_LIST@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_CREATE_APP_CONTEXT_DATA_CUSTOM_STORE_LIST const *,Windows::Isolation::Rtl::_CREATE_APPLICATION_CONTEXT_DATA_CUSTOM_STORE_LIST * &)
0x180030c7e  mov     ebx, eax
0x180030c80  test    eax, eax
0x180030c82  jns     short loc_180030C9D
0x180030c84  mov     edx, 325h; char *
0x180030c89  mov     r8d, eax; int
0x180030c8c  lea     rcx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180030c93  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180030c98  jmp     loc_180030F6E
0x180030c9d  mov     rax, [rbp+arg_8]
0x180030ca1  lea     r14, [rdi+4]
0x180030ca5  mov     [rsi+10h], rax
0x180030ca9  or      dword ptr [rsi+8], 1
0x180030cad  jmp     short loc_180030CB2
0x180030caf  mov     r14, r13
0x180030cb2  test    byte ptr [r13+0], 2
0x180030cb7  jz      short loc_180030D0A
0x180030cb9  mov     eax, [rdi]
0x180030cbb  lea     rcx, [rdi+18h]
0x180030cbf  add     rax, rdi
0x180030cc2  cmp     rcx, rax
0x180030cc5  jbe     short loc_180030CD3
0x180030cc7  mov     [rbp+var_18], 32Dh
0x180030cce  jmp     loc_180030DB5
0x180030cd3  mov     rdx, [r12]; struct _RTL_ALLOCATION_LIST *
0x180030cd7  lea     r8, [rbp+arg_8]; struct _CULTURE_FALLBACK_LIST *
0x180030cdb  mov     rcx, r15; this
0x180030cde  mov     [rbp+arg_8], 0
0x180030ce6  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_CULTURE_FALLBACK_LIST@@AEAPEAU_RTL_CULTURE_FALLBACK_LIST@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_CULTURE_FALLBACK_LIST const *,Windows::Isolation::Rtl::_RTL_CULTURE_FALLBACK_LIST * &)
0x180030ceb  mov     ebx, eax
0x180030ced  test    eax, eax
0x180030cef  jns     short loc_180030CF8
0x180030cf1  mov     edx, 335h
0x180030cf6  jmp     short loc_180030C89
0x180030cf8  mov     rax, [rbp+arg_8]
0x180030cfc  lea     r12, [rdi+4]
0x180030d00  mov     [rsi+18h], rax
0x180030d04  or      dword ptr [rsi+8], 2
0x180030d08  jmp     short loc_180030D0D
0x180030d0a  mov     r12, r14
0x180030d0d  test    byte ptr [r14], 4
0x180030d11  lea     rdx, [rdi+18h]
0x180030d15  jz      short loc_180030D67
0x180030d17  mov     ecx, [rdi]
0x180030d19  lea     rax, [rdi+20h]
0x180030d1d  add     rcx, rdi
0x180030d20  cmp     rax, rcx
0x180030d23  jbe     short loc_180030D31
0x180030d25  mov     [rbp+var_18], 33Dh
0x180030d2c  jmp     loc_180030DB5
0x180030d31  mov     rdx, [rdx]; struct _RTL_ALLOCATION_LIST *
0x180030d34  lea     r8, [rbp+arg_8]; struct _CREATE_APP_CONTEXT_DATA_PROCESSOR_ARCHITECTURE_FALLBACK_LIST *
0x180030d38  mov     rcx, r15; this
0x180030d3b  mov     [rbp+arg_8], 0
0x180030d43  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_CREATE_APP_CONTEXT_DATA_PROCESSOR_ARCHITECTURE_FALLBACK_LIST@@AEAPEAU_CREATE_APPLICATION_CONTEXT_DATA_PROCESSOR_ARCHITECTURE_FALLBACK_LIST@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_CREATE_APP_CONTEXT_DATA_PROCESSOR_ARCHITECTURE_FALLBACK_LIST const *,Windows::Isolation::Rtl::_CREATE_APPLICATION_CONTEXT_DATA_PROCESSOR_ARCHITECTURE_FALLBACK_LIST * &)
0x180030d48  mov     ebx, eax
0x180030d4a  test    eax, eax
0x180030d4c  jns     short loc_180030D58
0x180030d4e  mov     edx, 345h
0x180030d53  jmp     loc_180030C89
0x180030d58  mov     rax, [rbp+arg_8]
0x180030d5c  mov     r14, r12
0x180030d5f  mov     [rsi+20h], rax
0x180030d63  or      dword ptr [rsi+8], 4
0x180030d67  test    byte ptr [r14], 8
0x180030d6b  jz      short loc_180030D95
0x180030d6d  mov     ecx, [rdi]
0x180030d6f  lea     rax, [rdi+2Ah]
0x180030d73  add     rcx, rdi
0x180030d76  cmp     rax, rcx
0x180030d79  jbe     short loc_180030D84
0x180030d7b  mov     [rbp+var_18], 34Dh
0x180030d82  jmp     short loc_180030DB5
0x180030d84  lea     rcx, [rdi+28h]
0x180030d88  movzx   eax, word ptr [rcx]
0x180030d8b  mov     [rsi+30h], ax
0x180030d8f  or      dword ptr [rsi+8], 8
0x180030d93  jmp     short loc_180030D99
0x180030d95  lea     rcx, [rdi+28h]
0x180030d99  test    byte ptr [r13+0], 10h
0x180030d9e  jz      loc_180030F61
0x180030da4  mov     eax, [rdi]
0x180030da6  add     rax, rdi
0x180030da9  cmp     rcx, rax
0x180030dac  jbe     short loc_180030DC0
0x180030dae  mov     [rbp+var_18], 355h
0x180030db5  lea     rcx, [rbp+var_20]
0x180030db9  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x180030dbe  jmp     short loc_180030E2A
0x180030dc0  mov     rdx, [rdi+20h]; struct _RTL_ALLOCATION_LIST *
0x180030dc4  lea     r8, [rbp+arg_8]; struct _CREATE_APP_CONTEXT_DATA_SOURCE *
0x180030dc8  xor     r14d, r14d
0x180030dcb  mov     rcx, r15; this
0x180030dce  mov     [rbp+arg_8], r14
0x180030dd2  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_CREATE_APP_CONTEXT_DATA_SOURCE@@AEAPEAU_CREATE_APPLICATION_CONTEXT_DATA_SOURCE@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_CREATE_APP_CONTEXT_DATA_SOURCE const *,Windows::Isolation::Rtl::_CREATE_APPLICATION_CONTEXT_DATA_SOURCE * &)
0x180030dd7  mov     ebx, eax
0x180030dd9  test    eax, eax
0x180030ddb  jns     short loc_180030DE7
0x180030ddd  mov     edx, 35Dh
0x180030de2  jmp     loc_180030C89
0x180030de7  mov     rax, [rbp+arg_8]
0x180030deb  mov     [rsi+28h], rax
0x180030def  mov     eax, [rsi+8]
0x180030df2  or      eax, 10h
0x180030df5  mov     [rsi+8], eax
0x180030df8  test    al, 1
0x180030dfa  jnz     loc_180030F64
0x180030e00  mov     [rbp+arg_8], r14
0x180030e04  mov     [rbp+arg_18], r14
0x180030e08  mov     [rbp+var_30], r14
0x180030e0c  mov     [rbp+var_28], r14
0x180030e10  cmp     [rsi+10h], r14
0x180030e14  jz      short loc_180030E32
0x180030e16  mov     [rbp+var_18], 36Dh
0x180030e1d  lea     rdx, [rbp+var_20]
0x180030e21  lea     rcx, [rbp+var_20]
0x180030e25  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180030e2a  mov     ebx, [rbp+var_10]
0x180030e2d  jmp     loc_180030F6E
0x180030e32  xor     r8d, r8d
0x180030e35  lea     r9, [rbp+arg_8]
0x180030e39  mov     rcx, r15
0x180030e3c  lea     r12d, [r8+20h]
0x180030e40  mov     edx, r12d
0x180030e43  call    RtlAllocateAllocationListMemory
0x180030e48  mov     ebx, eax
0x180030e4a  test    eax, eax
0x180030e4c  jns     short loc_180030E6E
0x180030e4e  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180030e54  jnz     short loc_180030E5C
0x180030e56  call    cs:__imp_DebugBreak
0x180030e5c  mov     r8d, 36Fh
0x180030e62  lea     rdx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180030e69  jmp     loc_180030C0B
0x180030e6e  xor     r8d, r8d
0x180030e71  lea     r9, [rbp+var_30]
0x180030e75  mov     rcx, r15
0x180030e78  lea     edi, [r8+18h]
0x180030e7c  mov     edx, edi
0x180030e7e  call    RtlAllocateAllocationListMemory
0x180030e83  mov     ebx, eax
0x180030e85  test    eax, eax
0x180030e87  jns     short loc_180030E9F
0x180030e89  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180030e8f  jnz     short loc_180030E97
0x180030e91  call    cs:__imp_DebugBreak
0x180030e97  mov     r8d, 370h
0x180030e9d  jmp     short loc_180030E62
0x180030e9f  lea     r9, [rbp+var_28]
0x180030ea3  xor     r8d, r8d
0x180030ea6  mov     rdx, rdi
0x180030ea9  mov     rcx, r15
0x180030eac  call    RtlAllocateAllocationListMemory
0x180030eb1  mov     ebx, eax
0x180030eb3  test    eax, eax
0x180030eb5  jns     short loc_180030ECD
0x180030eb7  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180030ebd  jnz     short loc_180030EC5
0x180030ebf  call    cs:__imp_DebugBreak
0x180030ec5  mov     r8d, 371h
0x180030ecb  jmp     short loc_180030E62
0x180030ecd  xor     r9d, r9d
0x180030ed0  lea     rax, [rbp+arg_18]
0x180030ed4  mov     rcx, r15
0x180030ed7  mov     qword ptr [rsp+60h+var_40], rax
0x180030edc  lea     r13d, [r9+2]
0x180030ee0  mov     edx, r13d
0x180030ee3  lea     r8d, [r9+8]
0x180030ee7  call    RtlAllocateAllocationListArray
0x180030eec  mov     ebx, eax
0x180030eee  test    eax, eax
0x180030ef0  jns     short loc_180030F0B
0x180030ef2  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180030ef8  jnz     short loc_180030F00
0x180030efa  call    cs:__imp_DebugBreak
0x180030f00  mov     r8d, 372h
0x180030f06  jmp     loc_180030E62
0x180030f0b  mov     r8, [rbp+arg_8]
0x180030f0f  mov     rcx, [rbp+var_30]
0x180030f13  mov     rax, [rbp+var_28]
0x180030f17  mov     rdx, [rbp+arg_18]
0x180030f1b  mov     [r8], r12
0x180030f1e  mov     [r8+8], r14d
0x180030f22  mov     [r8+10h], r14
0x180030f26  mov     [r8+18h], rdx
0x180030f2a  mov     [rcx], rdi
0x180030f2d  mov     [rcx+8], r14d
0x180030f31  mov     [rcx+0Ch], r13d
0x180030f35  mov     [rcx+10h], r14
0x180030f39  mov     [rax], rdi
0x180030f3c  mov     [rax+8], r14d
0x180030f40  mov     dword ptr [rax+0Ch], 1
0x180030f47  mov     [rax+10h], r14
0x180030f4b  mov     rax, [r8+10h]
0x180030f4f  mov     [rdx+rax*8], rcx
0x180030f53  inc     qword ptr [r8+10h]
0x180030f57  or      dword ptr [rsi+8], 1
0x180030f5b  mov     [rsi+10h], r8
0x180030f5f  jmp     short loc_180030F64
0x180030f61  xor     r14d, r14d
0x180030f64  mov     rax, [rbp+arg_10]
0x180030f68  mov     ebx, r14d
0x180030f6b  mov     [rax], rsi
0x180030f6e  mov     eax, ebx
0x180030f70  mov     rbx, [rsp+60h+arg_0]
0x180030f78  add     rsp, 60h
0x180030f7c  pop     r15
0x180030f7e  pop     r14
0x180030f80  pop     r13
0x180030f82  pop     r12
0x180030f84  pop     rdi
0x180030f85  pop     rsi
0x180030f86  pop     rbp
0x180030f87  retn
```
