# NUMBER_SET::Add(BIG_INT,BIG_INT)

- ea: `0x180001670`
- end: `0x180001825`
- name: `?Add@NUMBER_SET@@QEAAEVBIG_INT@@0@Z`
- size: `437`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180063d3c`
- `0x18006821c`
- `0x180068628`
- `0x18006a43c`
- `0x18006f1ec`
- `0x18006f3f4`
- `0x180073e8c`
- `0x180075364`

## callees

- `0x180001670`

## import_xrefs

- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x180001814`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x180001814`
- `ntdll!RtlInsertElementGenericTableFullAvl` at `0x180001804`
- `ntdll!RtlInsertElementGenericTableFullAvl` at `0x180001804`
- `ntdll!RtlLookupElementGenericTableFullAvl` at `0x180001795`
- `ntdll!RtlLookupElementGenericTableFullAvl` at `0x180001795`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800017c9`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1800017c9`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x180001718`
- `ntdll!RtlEnumerateGenericTableWithoutSplayingAvl` at `0x180001718`
- `ntdll!RtlLookupFirstMatchingElementGenericTableAvl` at `0x1800016f3`
- `ntdll!RtlLookupFirstMatchingElementGenericTableAvl` at `0x1800016f3`

## pseudocode

```c
__int64 __fastcall NUMBER_SET::Add(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 v4; // rbx
  unsigned __int8 v6; // r15
  _QWORD *v7; // rsi
  _QWORD *v8; // rax
  __int64 v9; // r12
  _QWORD *v11; // rax
  _QWORD Buffer[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v13; // [rsp+40h] [rbp-48h]
  __int64 v14; // [rsp+48h] [rbp-40h]
  TABLE_SEARCH_RESULT SearchResult; // [rsp+98h] [rbp+10h] BYREF
  PVOID RestartKey; // [rsp+A0h] [rbp+18h] BYREF
  PVOID NodeOrParent; // [rsp+A8h] [rbp+20h] BYREF

  v3 = a2 + a3;
  v4 = a2;
LABEL_2:
  v6 = 1;
  while ( v4 < v3 )
  {
    Buffer[0] = &MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE::`vftable';
    Buffer[1] = NUMBER_EXTENT_cd;
    SearchResult = TableEmptyTree;
    NodeOrParent = 0;
    RestartKey = 0;
    v13 = v4 - 1;
    v14 = v4;
    v7 = RtlLookupFirstMatchingElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 16), Buffer, &RestartKey);
    if ( !v7 )
    {
      v13 = v4 + 1;
      v14 = v4 + 1;
      v11 = RtlLookupElementGenericTableFullAvl((PRTL_AVL_TABLE)(a1 + 16), Buffer, &NodeOrParent, &SearchResult);
      if ( SearchResult == TableFoundNode )
      {
        v11[2] = v4;
      }
      else
      {
        v13 = v4;
        v14 = v4;
        if ( !RtlInsertElementGenericTableFullAvl(
                (PRTL_AVL_TABLE)(a1 + 16),
                Buffer,
                0x20u,
                0,
                NodeOrParent,
                SearchResult) )
        {
          RtlSetLastWin32ErrorAndNtStatusFromNtStatus(-1073741801);
          ++v4;
          goto LABEL_21;
        }
      }
      ++v4;
      goto LABEL_9;
    }
    if ( v7[3] == v13 )
    {
      v8 = RtlEnumerateGenericTableWithoutSplayingAvl((PRTL_AVL_TABLE)(a1 + 16), &RestartKey);
      if ( v8 && v8[2] == v4 + 1 )
      {
        v9 = v8[3];
        RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 16), v8);
        ++v4;
      }
      else
      {
        v9 = v4++;
      }
      v7[3] = v9;
LABEL_9:
      ++*(_QWORD *)(a1 + 120);
      goto LABEL_10;
    }
    ++v4;
LABEL_10:
    if ( v6 )
      goto LABEL_2;
LABEL_21:
    v6 = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180001670  mov     rax, rsp
0x180001673  push    rbx
0x180001674  push    rdi
0x180001675  push    r14
0x180001677  push    r15
0x180001679  sub     rsp, 68h
0x18000167d  mov     [rax+8], rbp
0x180001681  lea     rdi, [rdx+r8]
0x180001685  mov     [rax-28h], rsi
0x180001689  mov     rbx, rdx
0x18000168c  mov     [rax-30h], r12
0x180001690  mov     r14, rcx
0x180001693  mov     [rax-38h], r13
0x180001697  mov     r15b, 1
0x18000169a  xor     ecx, ecx
0x18000169c  lea     rax, ??_7MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE@@6B@; const MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE::`vftable'
0x1800016a3  cmp     rbx, rdi
0x1800016a6  jge     loc_180001743
0x1800016ac  mov     [rsp+88h+Buffer], rax
0x1800016b1  lea     r8, [rsp+88h+RestartKey]; RestartKey
0x1800016b9  mov     rax, cs:?NUMBER_EXTENT_cd@@3PEBVCLASS_DESCRIPTOR@@EB; CLASS_DESCRIPTOR const * const NUMBER_EXTENT_cd
0x1800016c0  lea     rdx, [rsp+88h+Buffer]; Buffer
0x1800016c5  mov     [rsp+88h+var_50], rax
0x1800016ca  lea     rax, [rbx-1]
0x1800016ce  mov     [rsp+88h+SearchResult], ecx
0x1800016d5  mov     [rsp+88h+NodeOrParent], rcx
0x1800016dd  mov     [rsp+88h+RestartKey], rcx
0x1800016e5  lea     rcx, [r14+10h]; Table
0x1800016e9  mov     [rsp+88h+var_48], rax
0x1800016ee  mov     [rsp+88h+var_40], rbx
0x1800016f3  call    cs:__imp_RtlLookupFirstMatchingElementGenericTableAvl
0x1800016f9  mov     rsi, rax
0x1800016fc  test    rax, rax
0x1800016ff  jz      short loc_18000176E
0x180001701  mov     rax, [rsp+88h+var_48]
0x180001706  cmp     [rsi+18h], rax
0x18000170a  jnz     short loc_180001769
0x18000170c  lea     rdx, [rsp+88h+RestartKey]; RestartKey
0x180001714  lea     rcx, [r14+10h]; Table
0x180001718  call    cs:__imp_RtlEnumerateGenericTableWithoutSplayingAvl
0x18000171e  test    rax, rax
0x180001721  jnz     loc_1800017B0
0x180001727  mov     r12, rbx
0x18000172a  inc     rbx
0x18000172d  mov     [rsi+18h], r12
0x180001731  inc     qword ptr [r14+78h]
0x180001735  test    r15b, r15b
0x180001738  jnz     loc_180001697
0x18000173e  jmp     loc_18000181D
0x180001743  mov     r13, [rsp+88h+var_38]
0x180001748  movzx   eax, r15b
0x18000174c  mov     r12, [rsp+88h+var_30]
0x180001751  mov     rsi, [rsp+88h+var_28]
0x180001756  mov     rbp, [rsp+88h+arg_0]
0x18000175e  add     rsp, 68h
0x180001762  pop     r15
0x180001764  pop     r14
0x180001766  pop     rdi
0x180001767  pop     rbx
0x180001768  retn
0x180001769  inc     rbx
0x18000176c  jmp     short loc_180001735
0x18000176e  lea     rsi, [rbx+1]
0x180001772  lea     r9, [rsp+88h+SearchResult]; SearchResult
0x18000177a  mov     [rsp+88h+var_48], rsi
0x18000177f  lea     r8, [rsp+88h+NodeOrParent]; NodeOrParent
0x180001787  mov     [rsp+88h+var_40], rsi
0x18000178c  lea     rdx, [rsp+88h+Buffer]; Buffer
0x180001791  lea     rcx, [r14+10h]; Table
0x180001795  call    cs:__imp_RtlLookupElementGenericTableFullAvl
0x18000179b  mov     ecx, [rsp+88h+SearchResult]
0x1800017a2  cmp     ecx, 1
0x1800017a5  jnz     short loc_1800017D7
0x1800017a7  mov     [rax+10h], rbx
0x1800017ab  mov     rbx, rsi
0x1800017ae  jmp     short loc_180001731
0x1800017b0  lea     r13, [rbx+1]
0x1800017b4  cmp     [rax+10h], r13
0x1800017b8  jnz     loc_180001727
0x1800017be  mov     r12, [rax+18h]
0x1800017c2  lea     rcx, [r14+10h]; Table
0x1800017c6  mov     rdx, rax; Buffer
0x1800017c9  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1800017cf  mov     rbx, r13
0x1800017d2  jmp     loc_18000172D
0x1800017d7  mov     rax, [rsp+88h+NodeOrParent]
0x1800017df  lea     rdx, [rsp+88h+Buffer]; Buffer
0x1800017e4  mov     [rsp+88h+var_60], ecx; SearchResult
0x1800017e8  xor     r9d, r9d; NewElement
0x1800017eb  lea     rcx, [r14+10h]; Table
0x1800017ef  mov     [rsp+88h+var_68], rax; NodeOrParent
0x1800017f4  mov     r8d, 20h ; ' '; BufferSize
0x1800017fa  mov     [rsp+88h+var_48], rbx
0x1800017ff  mov     [rsp+88h+var_40], rbx
0x180001804  call    cs:__imp_RtlInsertElementGenericTableFullAvl
0x18000180a  test    rax, rax
0x18000180d  jnz     short loc_1800017AB
0x18000180f  mov     ecx, 0C0000017h; Status
0x180001814  call    cs:__imp_RtlSetLastWin32ErrorAndNtStatusFromNtStatus
0x18000181a  mov     rbx, rsi
0x18000181d  xor     r15b, r15b
0x180001820  jmp     loc_18000169A
```
