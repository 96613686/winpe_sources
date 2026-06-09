# WSTReferenceUserModeContextByLsaHandle(unsigned __int64,uchar,_NEGOEXTS_UMODE_CONTEXT * *)

- ea: `0x18000c700`
- end: `0x18000c7bc`
- name: `?WSTReferenceUserModeContextByLsaHandle@@YAJ_KEPEAPEAU_NEGOEXTS_UMODE_CONTEXT@@@Z`
- size: `188`
- prototype: `int(unsigned __int64, unsigned __int8, struct _NEGOEXTS_UMODE_CONTEXT **)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000c5a4`
- `0x18000c5f0`
- `0x180018f28`
- `0x180019124`
- `0x180019840`
- `0x180019950`
- `0x180019a70`
- `0x180019bf0`

## callees

- `0x18000c700`
- `0x18001e1e0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000c78d`
- `ntdll!RtlLeaveCriticalSection` at `0x18000c78d`
- `ntdll!RtlEnterCriticalSection` at `0x18000c75e`
- `ntdll!RtlEnterCriticalSection` at `0x18000c75e`

## pseudocode

```c
__int64 __fastcall WSTReferenceUserModeContextByLsaHandle(__int64 a1, char a2, struct _NEGOEXTS_UMODE_CONTEXT **a3)
{
  struct basessp::_WST_LIST near *v4; // rsi
  char v5; // di
  struct basessp::_WST_LIST near **v8; // r14
  struct basessp::_WST_LIST_ENTRY *v9; // r8
  unsigned __int8 v10; // r9
  struct basessp::_WST_LIST near *i; // rdx
  struct _NEGOEXTS_UMODE_CONTEXT *v12; // rax

  v4 = 0;
  v5 = 0;
  v8 = &NegoExtsGlobalUserModeContextList
     + 7
     * (unsigned __int8)(BYTE2(a1)
                       + BYTE3(a1)
                       + a1
                       + BYTE1(a1)
                       + ((unsigned int)a1 >> 4)
                       + ((WORD1(a1) + BYTE3(a1) + (_DWORD)a1 + ((unsigned int)a1 >> 8) + ((unsigned int)a1 >> 4)) >> 4));
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v8 + 2));
  for ( i = *v8; i != (struct basessp::_WST_LIST near *)v8; i = *(struct basessp::_WST_LIST near **)i )
  {
    v4 = i;
    if ( a1 == *((_QWORD *)i + 4) )
    {
      LOBYTE(v9) = a2;
      basessp::WSTReferenceListEntry((basessp *)v8, i, v9, v10);
      v5 = 1;
      break;
    }
  }
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v8 + 2));
  v12 = (struct _NEGOEXTS_UMODE_CONTEXT *)((unsigned __int64)v4 & -(__int64)(v5 != 0));
  *a3 = v12;
  return v12 == 0 ? 0x80090301 : 0;
}

```

## disassembly

```asm
0x18000c700  push    rbx
0x18000c702  push    rbp
0x18000c703  push    rsi
0x18000c704  push    rdi
0x18000c705  push    r12
0x18000c707  push    r13
0x18000c709  push    r14
0x18000c70b  push    r15
0x18000c70d  sub     rsp, 28h
0x18000c711  mov     eax, ecx
0x18000c713  lea     r13, ?NegoExtsGlobalUserModeContextList@@3PAU_WST_LIST@basessp@@A; basessp::_WST_LIST near * NegoExtsGlobalUserModeContextList
0x18000c71a  shr     eax, 10h
0x18000c71d  mov     r10d, ecx
0x18000c720  mov     r9d, ecx
0x18000c723  shr     r10d, 18h
0x18000c727  add     r10d, eax
0x18000c72a  shr     r9d, 8
0x18000c72e  add     r9d, ecx
0x18000c731  mov     rbp, rcx
0x18000c734  shr     ecx, 4
0x18000c737  add     r9d, r10d
0x18000c73a  add     ecx, r9d
0x18000c73d  xor     esi, esi
0x18000c73f  mov     eax, ecx
0x18000c741  xor     dil, dil
0x18000c744  shr     eax, 4
0x18000c747  mov     r15, r8
0x18000c74a  add     eax, ecx
0x18000c74c  mov     r12b, dl
0x18000c74f  movzx   eax, al
0x18000c752  imul    rbx, rax, 38h ; '8'
0x18000c756  lea     r14, [rbx+r13]
0x18000c75a  lea     rcx, [r14+10h]; CriticalSection
0x18000c75e  call    cs:__imp_RtlEnterCriticalSection
0x18000c764  lea     rcx, [rbx+r13]; this
0x18000c768  mov     rdx, [rcx]; struct basessp::_WST_LIST *
0x18000c76b  cmp     rdx, rcx
0x18000c76e  jz      short loc_18000C789
0x18000c770  mov     rsi, rdx
0x18000c773  cmp     rbp, [rdx+20h]
0x18000c777  jz      short loc_18000C77E
0x18000c779  mov     rdx, [rdx]
0x18000c77c  jmp     short loc_18000C76B
0x18000c77e  mov     r8b, r12b; struct basessp::_WST_LIST_ENTRY *
0x18000c781  call    ?WSTReferenceListEntry@basessp@@YAXPEAU_WST_LIST@1@PEAU_WST_LIST_ENTRY@1@E@Z; basessp::WSTReferenceListEntry(basessp::_WST_LIST *,basessp::_WST_LIST_ENTRY *,uchar)
0x18000c786  mov     dil, 1
0x18000c789  lea     rcx, [r14+10h]; CriticalSection
0x18000c78d  call    cs:__imp_RtlLeaveCriticalSection
0x18000c793  neg     dil
0x18000c796  sbb     rax, rax
0x18000c799  and     rax, rsi
0x18000c79c  mov     [r15], rax
0x18000c79f  neg     rax
0x18000c7a2  sbb     eax, eax
0x18000c7a4  not     eax
0x18000c7a6  and     eax, 80090301h
0x18000c7ab  add     rsp, 28h
0x18000c7af  pop     r15
0x18000c7b1  pop     r14
0x18000c7b3  pop     r13
0x18000c7b5  pop     r12
0x18000c7b7  pop     rdi
0x18000c7b8  pop     rsi
0x18000c7b9  pop     rbp
0x18000c7ba  pop     rbx
0x18000c7bb  retn
```
