# NUMBER_SET::CheckAndRemove(BIG_INT,uchar *)

- ea: `0x180001830`
- end: `0x180001918`
- name: `?CheckAndRemove@NUMBER_SET@@QEAAEVBIG_INT@@PEAE@Z`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180062348`

## callees

- `0x180001830`

## import_xrefs

- `ntdll!RtlInsertElementGenericTableAvl` at `0x180001906`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x180001906`
- `ntdll!RtlDeleteElementGenericTableAvlEx` at `0x1800018a9`
- `ntdll!RtlDeleteElementGenericTableAvlEx` at `0x1800018a9`
- `ntdll!RtlLookupElementGenericTableFullAvl` at `0x18000187f`
- `ntdll!RtlLookupElementGenericTableFullAvl` at `0x18000187f`

## pseudocode

```c
char __fastcall NUMBER_SET::CheckAndRemove(__int64 a1, __int64 a2, _BYTE *a3)
{
  _QWORD *v6; // rax
  __int64 v7; // r8
  __int64 v8; // rdx
  PVOID inserted; // rax
  __int64 v10; // rdx
  _QWORD Buffer[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v13; // [rsp+30h] [rbp-28h]
  __int64 v14; // [rsp+38h] [rbp-20h]
  int v15; // [rsp+60h] [rbp+8h] BYREF
  PVOID v16; // [rsp+68h] [rbp+10h] BYREF

  v13 = a2;
  Buffer[0] = &MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE::`vftable';
  Buffer[1] = NUMBER_EXTENT_cd;
  v14 = a2;
  v16 = 0;
  v15 = 0;
  v6 = RtlLookupElementGenericTableFullAvl((PRTL_AVL_TABLE)(a1 + 16), Buffer, &v16, (TABLE_SEARCH_RESULT *)&v15);
  if ( v15 == 1 )
  {
    v7 = v6[3];
    v8 = v6[2];
    *a3 = 1;
    if ( v8 == v7 )
    {
      RtlDeleteElementGenericTableAvlEx(a1 + 16, v16);
    }
    else if ( v8 == a2 )
    {
      v6[2] = a2 + 1;
    }
    else
    {
      v10 = a2 - 1;
      if ( v7 == a2 )
      {
        v6[3] = v10;
      }
      else
      {
        v13 = a2 + 1;
        v14 = v6[3];
        v6[3] = v10;
        inserted = RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 16), Buffer, 0x20u, 0);
        if ( !inserted )
          return (char)inserted;
      }
    }
    --*(_QWORD *)(a1 + 120);
  }
  else
  {
    *a3 = 0;
  }
  LOBYTE(inserted) = 1;
  return (char)inserted;
}

```

## disassembly

```asm
0x180001830  mov     r11, rsp
0x180001833  mov     [r11+18h], rbx
0x180001837  push    rbp
0x180001838  push    rsi
0x180001839  push    rdi
0x18000183a  sub     rsp, 40h
0x18000183e  lea     rax, ??_7MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE@@6B@; const MEDIA_TRACK_INFORMATION_SORTED_BY_SIZE::`vftable'
0x180001845  mov     [r11-28h], rdx
0x180001849  mov     [r11-38h], rax
0x18000184d  lea     r9, [r11+8]; SearchResult
0x180001851  mov     rax, cs:?NUMBER_EXTENT_cd@@3PEBVCLASS_DESCRIPTOR@@EB; CLASS_DESCRIPTOR const * const NUMBER_EXTENT_cd
0x180001858  mov     rsi, r8
0x18000185b  mov     [r11-30h], rax
0x18000185f  lea     r8, [r11+10h]; NodeOrParent
0x180001863  xor     eax, eax
0x180001865  mov     [r11-20h], rdx
0x180001869  mov     rbx, rdx
0x18000186c  mov     [r11+10h], rax
0x180001870  mov     rdi, rcx
0x180001873  mov     [rsp+58h+arg_0], eax
0x180001877  lea     rdx, [r11-38h]; Buffer
0x18000187b  add     rcx, 10h; Table
0x18000187f  call    cs:__imp_RtlLookupElementGenericTableFullAvl
0x180001885  cmp     [rsp+58h+arg_0], 1
0x18000188a  jnz     loc_180001913
0x180001890  mov     r8, [rax+18h]
0x180001894  mov     rdx, [rax+10h]
0x180001898  mov     byte ptr [rsi], 1
0x18000189b  cmp     rdx, r8
0x18000189e  jnz     short loc_1800018C2
0x1800018a0  mov     rdx, [rsp+58h+arg_8]
0x1800018a5  lea     rcx, [rdi+10h]
0x1800018a9  call    cs:__imp_RtlDeleteElementGenericTableAvlEx
0x1800018af  dec     qword ptr [rdi+78h]
0x1800018b3  mov     al, 1
0x1800018b5  mov     rbx, [rsp+58h+arg_10]
0x1800018ba  add     rsp, 40h
0x1800018be  pop     rdi
0x1800018bf  pop     rsi
0x1800018c0  pop     rbp
0x1800018c1  retn
0x1800018c2  cmp     rdx, rbx
0x1800018c5  jnz     short loc_1800018D0
0x1800018c7  inc     rbx
0x1800018ca  mov     [rax+10h], rbx
0x1800018ce  jmp     short loc_1800018AF
0x1800018d0  lea     rdx, [rbx-1]
0x1800018d4  cmp     r8, rbx
0x1800018d7  jnz     short loc_1800018DF
0x1800018d9  mov     [rax+18h], rdx
0x1800018dd  jmp     short loc_1800018AF
0x1800018df  inc     rbx
0x1800018e2  xor     r9d, r9d; NewElement
0x1800018e5  mov     [rsp+58h+var_28], rbx
0x1800018ea  mov     r8d, 20h ; ' '; BufferSize
0x1800018f0  mov     rcx, [rax+18h]
0x1800018f4  mov     [rsp+58h+var_20], rcx
0x1800018f9  lea     rcx, [rdi+10h]; Table
0x1800018fd  mov     [rax+18h], rdx
0x180001901  lea     rdx, [rsp+58h+Buffer]; Buffer
0x180001906  call    cs:__imp_RtlInsertElementGenericTableAvl
0x18000190c  test    rax, rax
0x18000190f  jnz     short loc_1800018AF
0x180001911  jmp     short loc_1800018B5
0x180001913  mov     byte ptr [rsi], 0
0x180001916  jmp     short loc_1800018B3
```
