# FreeRSNIEContent(DOT11_RSN_IE_INFO *)

- ea: `0x140048cc8`
- end: `0x140048dc0`
- name: `?FreeRSNIEContent@@YAXPEAUDOT11_RSN_IE_INFO@@@Z`
- size: `248`
- prototype: `void __fastcall(struct DOT11_RSN_IE_INFO *)`
- caller_count: `9`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14003a814`
- `0x140040680`
- `0x1400419dc`
- `0x140041bd8`
- `0x14004a904`
- `0x14004b344`
- `0x14004ba84`
- `0x14004cfe8`
- `0x14005351c`

## callees

- `0x140048cc8`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048cfb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048d48`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048d8e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048cfb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048d48`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140048d8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048d0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048d59`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048d9f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048d0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048d59`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048d9f`

## pseudocode

```c
void __fastcall FreeRSNIEContent(struct DOT11_RSN_IE_INFO *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  bool v4; // cc
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx

  if ( a1 )
  {
    if ( *((_WORD *)a1 + 12) > 1u )
    {
      v2 = *((_QWORD *)a1 + 4);
      if ( v2 )
      {
        v3 = v2 - 16;
        if ( *(_QWORD *)v3 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v3, (PVOID)v3);
        else
          ExFreePoolWithTag((PVOID)v3, *(_DWORD *)(v3 + 8));
        *((_QWORD *)a1 + 4) = 0;
      }
    }
    v4 = *((_WORD *)a1 + 4) <= 1u;
    *((_WORD *)a1 + 12) = 0;
    if ( !v4 )
    {
      v5 = *((_QWORD *)a1 + 2);
      if ( v5 )
      {
        v6 = v5 - 16;
        if ( *(_QWORD *)v6 )
          ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v6, (PVOID)v6);
        else
          ExFreePoolWithTag((PVOID)v6, *(_DWORD *)(v6 + 8));
        *((_QWORD *)a1 + 2) = 0;
      }
    }
    v7 = *((_QWORD *)a1 + 6);
    *((_WORD *)a1 + 4) = 0;
    if ( v7 )
    {
      v8 = v7 - 16;
      if ( *(_QWORD *)v8 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v8, (PVOID)v8);
      else
        ExFreePoolWithTag((PVOID)v8, *(_DWORD *)(v8 + 8));
      *((_QWORD *)a1 + 6) = 0;
    }
    *((_WORD *)a1 + 21) = 0;
  }
}

```

## disassembly

```asm
0x140048cc8  test    rcx, rcx
0x140048ccb  jz      locret_140048DBE
0x140048cd1  push    rbx
0x140048cd2  sub     rsp, 20h
0x140048cd6  cmp     word ptr [rcx+18h], 1
0x140048cdb  mov     rbx, rcx
0x140048cde  jbe     short loc_140048D20
0x140048ce0  mov     rcx, [rcx+20h]
0x140048ce4  test    rcx, rcx
0x140048ce7  jz      short loc_140048D20
0x140048ce9  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140048ced  mov     rax, [rcx]
0x140048cf0  test    rax, rax
0x140048cf3  jz      short loc_140048D09
0x140048cf5  mov     rdx, rcx; Entry
0x140048cf8  mov     rcx, rax; Lookaside
0x140048cfb  call    cs:__imp_ExFreeToNPagedLookasideList
0x140048d02  nop     dword ptr [rax+rax+00h]
0x140048d07  jmp     short loc_140048D18
0x140048d09  mov     edx, [rcx+8]; Tag
0x140048d0c  call    cs:__imp_ExFreePoolWithTag
0x140048d13  nop     dword ptr [rax+rax+00h]
0x140048d18  mov     qword ptr [rbx+20h], 0
0x140048d20  xor     eax, eax
0x140048d22  cmp     word ptr [rbx+8], 1
0x140048d27  mov     [rbx+18h], ax
0x140048d2b  jbe     short loc_140048D6D
0x140048d2d  mov     rcx, [rbx+10h]
0x140048d31  test    rcx, rcx
0x140048d34  jz      short loc_140048D6D
0x140048d36  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140048d3a  mov     rax, [rcx]
0x140048d3d  test    rax, rax
0x140048d40  jz      short loc_140048D56
0x140048d42  mov     rdx, rcx; Entry
0x140048d45  mov     rcx, rax; Lookaside
0x140048d48  call    cs:__imp_ExFreeToNPagedLookasideList
0x140048d4f  nop     dword ptr [rax+rax+00h]
0x140048d54  jmp     short loc_140048D65
0x140048d56  mov     edx, [rcx+8]; Tag
0x140048d59  call    cs:__imp_ExFreePoolWithTag
0x140048d60  nop     dword ptr [rax+rax+00h]
0x140048d65  mov     qword ptr [rbx+10h], 0
0x140048d6d  mov     rcx, [rbx+30h]
0x140048d71  xor     eax, eax
0x140048d73  mov     [rbx+8], ax
0x140048d77  test    rcx, rcx
0x140048d7a  jz      short loc_140048DB3
0x140048d7c  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x140048d80  mov     rax, [rcx]
0x140048d83  test    rax, rax
0x140048d86  jz      short loc_140048D9C
0x140048d88  mov     rdx, rcx; Entry
0x140048d8b  mov     rcx, rax; Lookaside
0x140048d8e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140048d95  nop     dword ptr [rax+rax+00h]
0x140048d9a  jmp     short loc_140048DAB
0x140048d9c  mov     edx, [rcx+8]; Tag
0x140048d9f  call    cs:__imp_ExFreePoolWithTag
0x140048da6  nop     dword ptr [rax+rax+00h]
0x140048dab  mov     qword ptr [rbx+30h], 0
0x140048db3  xor     eax, eax
0x140048db5  mov     [rbx+2Ah], ax
0x140048db9  add     rsp, 20h
0x140048dbd  pop     rbx
0x140048dbe  retn
```
