# ExtSTAInitTkipSec(EXTSTA_VELAN *)

- ea: `0x14005d760`
- end: `0x14005d878`
- name: `?ExtSTAInitTkipSec@@YAHPEAUEXTSTA_VELAN@@@Z`
- size: `280`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140065730`

## callees

- `0x14005d478`
- `0x14005d760`
- `0x14009bfc0`
- `0x1400bcee8`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005d797`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005d797`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005d848`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005d848`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d85c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d85c`

## pseudocode

```c
__int64 __fastcall ExtSTAInitTkipSec(struct EXTSTA_VELAN *a1)
{
  _DWORD *v2; // rax
  PNPAGED_LOOKASIDE_LIST *v3; // rbx
  char *v4; // r14
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rsi
  unsigned int v8; // ebp
  unsigned __int64 i; // r15
  char *v10; // rdx
  unsigned int v12; // [rsp+70h] [rbp+8h] BYREF

  *(_QWORD *)&a1->TkipSec.uNumPeersInTkipMicFailure = 0;
  a1->TkipSec.bExcludeMacListInProgress = 0;
  v12 = 0;
  v2 = ExAllocateFromNPagedLookasideList(&Lookaside);
  v3 = (PNPAGED_LOOKASIDE_LIST *)v2;
  if ( v2 )
  {
    v4 = (char *)(v2 + 4);
    *(_QWORD *)v2 = &Lookaside;
    v2[2] = 945910899;
    if ( v2 != (_DWORD *)-16LL )
    {
      memset(v2 + 4, 0, 0x140u);
      Dot11ReadBLOB(a1->pGenVElan->hMibKey, v5, v6, v4, &v12);
      v7 = 0;
      v8 = v12 / 0x28;
      for ( i = MEMORY[0xFFFFF78000000014]; (unsigned int)v7 < v8; v7 = (unsigned int)(v7 + 1) )
      {
        v10 = &v4[40 * v7];
        if ( i < *((_QWORD *)v10 + 3) )
          ExtSTAAddTkipCounterMeasure(a1, (const struct EXTSTA_TKIP_COUNTERMEASURE_ENTRY *)v10);
      }
      if ( *v3 )
        ExFreeToNPagedLookasideList(*v3, v3);
      else
        ExFreePoolWithTag(v3, *((_DWORD *)v3 + 2));
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14005d760  push    rbx
0x14005d762  push    rbp
0x14005d763  push    rsi
0x14005d764  push    rdi
0x14005d765  push    r14
0x14005d767  push    r15
0x14005d769  sub     rsp, 38h
0x14005d76d  mov     rdi, rcx
0x14005d770  mov     qword ptr [rcx+338h], 0
0x14005d77b  mov     dword ptr [rcx+5F0h], 0
0x14005d785  lea     rsi, Lookaside
0x14005d78c  mov     rcx, rsi; Lookaside
0x14005d78f  mov     [rsp+68h+arg_0], 0
0x14005d797  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14005d79e  nop     dword ptr [rax+rax+00h]
0x14005d7a3  mov     rbx, rax
0x14005d7a6  test    rax, rax
0x14005d7a9  jz      loc_14005D868
0x14005d7af  lea     r14, [rax+10h]
0x14005d7b3  mov     [rax], rsi
0x14005d7b6  mov     dword ptr [rax+8], 38617473h
0x14005d7bd  test    r14, r14
0x14005d7c0  jz      loc_14005D868
0x14005d7c6  xor     edx, edx; Val
0x14005d7c8  mov     r8d, 140h; Size
0x14005d7ce  mov     rcx, r14; void *
0x14005d7d1  call    memset
0x14005d7d6  mov     rcx, [rdi+0A38h]
0x14005d7dd  lea     rax, [rsp+68h+arg_0]
0x14005d7e2  mov     r9, r14
0x14005d7e5  mov     [rsp+68h+var_48], rax
0x14005d7ea  mov     rcx, [rcx+1310h]
0x14005d7f1  call    Dot11ReadBLOB
0x14005d7f6  mov     ecx, [rsp+68h+arg_0]
0x14005d7fa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14005d804  mul     rcx
0x14005d807  mov     r15, 0FFFFF78000000014h
0x14005d811  xor     esi, esi
0x14005d813  mov     rbp, rdx
0x14005d816  shr     rbp, 5
0x14005d81a  mov     r15, [r15]
0x14005d81d  test    ebp, ebp
0x14005d81f  jz      short loc_14005D83D
0x14005d821  lea     rcx, [rsi+rsi*4]
0x14005d825  lea     rdx, [r14+rcx*8]; struct EXTSTA_TKIP_COUNTERMEASURE_ENTRY *
0x14005d829  cmp     r15, [rdx+18h]
0x14005d82d  jnb     short loc_14005D837
0x14005d82f  mov     rcx, rdi; struct EXTSTA_VELAN *
0x14005d832  call    ?ExtSTAAddTkipCounterMeasure@@YAHPEAUEXTSTA_VELAN@@PEBUEXTSTA_TKIP_COUNTERMEASURE_ENTRY@@@Z; ExtSTAAddTkipCounterMeasure(EXTSTA_VELAN *,EXTSTA_TKIP_COUNTERMEASURE_ENTRY const *)
0x14005d837  inc     esi
0x14005d839  cmp     esi, ebp
0x14005d83b  jb      short loc_14005D821
0x14005d83d  mov     rcx, [rbx]; Lookaside
0x14005d840  test    rcx, rcx
0x14005d843  jz      short loc_14005D856
0x14005d845  mov     rdx, rbx; Entry
0x14005d848  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005d84f  nop     dword ptr [rax+rax+00h]
0x14005d854  jmp     short loc_14005D868
0x14005d856  mov     edx, [rbx+8]; Tag
0x14005d859  mov     rcx, rbx; P
0x14005d85c  call    cs:__imp_ExFreePoolWithTag
0x14005d863  nop     dword ptr [rax+rax+00h]
0x14005d868  xor     eax, eax
0x14005d86a  add     rsp, 38h
0x14005d86e  pop     r15
0x14005d870  pop     r14
0x14005d872  pop     rdi
0x14005d873  pop     rsi
0x14005d874  pop     rbp
0x14005d875  pop     rbx
0x14005d876  retn
```
