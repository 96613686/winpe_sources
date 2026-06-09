# NUMBER_SET::CheckAndAdd(BIG_INT,uchar *)

- ea: `0x180001510`
- end: `0x180001668`
- name: `?CheckAndAdd@NUMBER_SET@@QEAAEVBIG_INT@@PEAE@Z`
- size: `344`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001b20`
- `0x18001f4b4`
- `0x18005f2e8`
- `0x18005f480`
- `0x18005f568`
- `0x180062348`

## callees

- `0x180001510`

## import_xrefs

- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x18000165b`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x18000165b`
- `ntdll!RtlInsertElementGenericTableFullAvl` at `0x180001647`
- `ntdll!RtlInsertElementGenericTableFullAvl` at `0x180001647`
- `ntdll!RtlLookupElementGenericTableFullAvl` at `0x1800015e2`
- `ntdll!RtlLookupElementGenericTableFullAvl` at `0x1800015e2`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000160f`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000160f`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18000158a`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x18000158a`
- `ntdll!RtlLookupFirstMatchingElementGenericTableAvl` at `0x180001565`
- `ntdll!RtlLookupFirstMatchingElementGenericTableAvl` at `0x180001565`

## pseudocode

```c
char __fastcall NUMBER_SET::CheckAndAdd(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v4; // rdi
  _QWORD *v6; // rax
  _QWORD *v7; // rsi
  _QWORD *v8; // rax
  _QWORD *v10; // rax
  _QWORD Buffer[2]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v12; // [rsp+40h] [rbp-38h]
  __int64 v13; // [rsp+48h] [rbp-30h]
  TABLE_SEARCH_RESULT SearchResult; // [rsp+80h] [rbp+8h] BYREF
  PVOID RestartKey; // [rsp+88h] [rbp+10h] BYREF
  PVOID NodeOrParent; // [rsp+90h] [rbp+18h] BYREF

  v13 = a2;
  Buffer[0] = &MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE::`vftable';
  v4 = a2;
  Buffer[1] = NUMBER_EXTENT_cd;
  *a3 = 0;
  SearchResult = TableEmptyTree;
  NodeOrParent = 0;
  RestartKey = 0;
  v12 = a2 - 1;
  v6 = RtlLookupFirstMatchingElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 16), Buffer, &RestartKey);
  v7 = v6;
  if ( !v6 )
  {
    v12 = v4 + 1;
    v13 = v4 + 1;
    v10 = RtlLookupElementGenericTableFullAvl((PRTL_AVL_TABLE)(a1 + 16), Buffer, &NodeOrParent, &SearchResult);
    if ( SearchResult == TableFoundNode )
    {
      v10[2] = v4;
    }
    else
    {
      v12 = v4;
      v13 = v4;
      if ( !RtlInsertElementGenericTableFullAvl((PRTL_AVL_TABLE)(a1 + 16), Buffer, 0x20u, 0, NodeOrParent, SearchResult) )
      {
        RtlSetLastWin32ErrorAndNtStatusFromNtStatus(-1073741801);
        return 0;
      }
    }
LABEL_5:
    ++*(_QWORD *)(a1 + 120);
    return 1;
  }
  if ( v6[3] == v12 )
  {
    v8 = RtlEnumerateGenericTableWithoutSplayingAvl((PRTL_AVL_TABLE)(a1 + 16), &RestartKey);
    if ( v8 )
    {
      if ( v8[2] == v4 + 1 )
      {
        v4 = v8[3];
        RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 16), v8);
      }
    }
    v7[3] = v4;
    goto LABEL_5;
  }
  *a3 = 1;
  return 1;
}

```

## disassembly

```asm
0x180001510  mov     r11, rsp
0x180001513  push    rbx
0x180001514  push    rbp
0x180001515  push    rsi
0x180001516  push    rdi
0x180001517  push    r14
0x180001519  sub     rsp, 50h
0x18000151d  lea     rax, ??_7MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE@@6B@; const MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE::`vftable'
0x180001524  mov     [r11-30h], rdx
0x180001528  mov     [r11-48h], rax
0x18000152c  mov     r14, r8
0x18000152f  mov     rax, cs:?NUMBER_EXTENT_cd@@3PEBVCLASS_DESCRIPTOR@@EB; CLASS_DESCRIPTOR const * const NUMBER_EXTENT_cd
0x180001536  mov     rdi, rdx
0x180001539  mov     [r11-40h], rax
0x18000153d  mov     rbx, rcx
0x180001540  xor     eax, eax
0x180001542  add     rcx, 10h; Table
0x180001546  mov     [r8], al
0x180001549  lea     r8, [r11+10h]; RestartKey
0x18000154d  mov     [r11+8], eax
0x180001551  mov     [r11+18h], rax
0x180001555  mov     [r11+10h], rax
0x180001559  lea     rax, [rdx-1]
0x18000155d  lea     rdx, [r11-48h]; Buffer
0x180001561  mov     [r11-38h], rax
0x180001565  call    cs:__imp_RtlLookupFirstMatchingElementGenericTableAvl
0x18000156b  mov     rsi, rax
0x18000156e  test    rax, rax
0x180001571  jz      short loc_1800015BB
0x180001573  mov     rcx, [rsp+78h+var_38]
0x180001578  cmp     [rax+18h], rcx
0x18000157c  jnz     short loc_1800015AA
0x18000157e  lea     rdx, [rsp+78h+RestartKey]; RestartKey
0x180001586  lea     rcx, [rbx+10h]; Table
0x18000158a  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x180001590  test    rax, rax
0x180001593  jnz     short loc_1800015FA
0x180001595  mov     [rsi+18h], rdi
0x180001599  inc     qword ptr [rbx+78h]
0x18000159d  mov     al, 1
0x18000159f  add     rsp, 50h
0x1800015a3  pop     r14
0x1800015a5  pop     rdi
0x1800015a6  pop     rsi
0x1800015a7  pop     rbp
0x1800015a8  pop     rbx
0x1800015a9  retn
0x1800015aa  mov     byte ptr [r14], 1
0x1800015ae  mov     al, 1
0x1800015b0  add     rsp, 50h
0x1800015b4  pop     r14
0x1800015b6  pop     rdi
0x1800015b7  pop     rsi
0x1800015b8  pop     rbp
0x1800015b9  pop     rbx
0x1800015ba  retn
0x1800015bb  lea     rax, [rdi+1]
0x1800015bf  lea     r9, [rsp+78h+SearchResult]; SearchResult
0x1800015c7  mov     [rsp+78h+var_38], rax
0x1800015cc  lea     r8, [rsp+78h+NodeOrParent]; NodeOrParent
0x1800015d4  mov     [rsp+78h+var_30], rax
0x1800015d9  lea     rdx, [rsp+78h+Buffer]; Buffer
0x1800015de  lea     rcx, [rbx+10h]; Table
0x1800015e2  call    cs:__imp_RtlLookupElementGenericTableFullAvl
0x1800015e8  mov     ecx, [rsp+78h+SearchResult]
0x1800015ef  cmp     ecx, 1
0x1800015f2  jnz     short loc_18000161A
0x1800015f4  mov     [rax+10h], rdi
0x1800015f8  jmp     short loc_180001599
0x1800015fa  lea     rdx, [rdi+1]
0x1800015fe  cmp     [rax+10h], rdx
0x180001602  jnz     short loc_180001595
0x180001604  mov     rdi, [rax+18h]
0x180001608  lea     rcx, [rbx+10h]; Table
0x18000160c  mov     rdx, rax; Buffer
0x18000160f  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x180001615  jmp     loc_180001595
0x18000161a  mov     rax, [rsp+78h+NodeOrParent]
0x180001622  lea     rdx, [rsp+78h+Buffer]; Buffer
0x180001627  mov     [rsp+78h+var_50], ecx; SearchResult
0x18000162b  xor     r9d, r9d; NewElement
0x18000162e  lea     rcx, [rbx+10h]; Table
0x180001632  mov     [rsp+78h+var_58], rax; NodeOrParent
0x180001637  mov     r8d, 20h ; ' '; BufferSize
0x18000163d  mov     [rsp+78h+var_38], rdi
0x180001642  mov     [rsp+78h+var_30], rdi
0x180001647  call    cs:__imp_RtlInsertElementGenericTableFullAvl
0x18000164d  test    rax, rax
0x180001650  jnz     loc_180001599
0x180001656  mov     ecx, 0C0000017h; Status
0x18000165b  call    cs:__imp_RtlSetLastWin32ErrorAndNtStatusFromNtStatus
0x180001661  xor     al, al
0x180001663  jmp     loc_18000159F
```
