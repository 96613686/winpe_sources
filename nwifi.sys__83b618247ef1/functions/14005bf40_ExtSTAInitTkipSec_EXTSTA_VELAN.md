# ExtSTAInitTkipSec(EXTSTA_VELAN *)

- ea: `0x14005bf40`
- end: `0x14005c058`
- name: `?ExtSTAInitTkipSec@@YAHPEAUEXTSTA_VELAN@@@Z`
- size: `280`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140063f00`

## callees

- `0x14005bc58`
- `0x14005bf40`
- `0x14009a7c0`
- `0x1400b9f38`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005bf77`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005bf77`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005c028`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005c028`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c03c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c03c`

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
0x14005bf40  push    rbx
0x14005bf42  push    rbp
0x14005bf43  push    rsi
0x14005bf44  push    rdi
0x14005bf45  push    r14
0x14005bf47  push    r15
0x14005bf49  sub     rsp, 38h
0x14005bf4d  mov     rdi, rcx
0x14005bf50  mov     qword ptr [rcx+338h], 0
0x14005bf5b  mov     dword ptr [rcx+5F0h], 0
0x14005bf65  lea     rsi, Lookaside
0x14005bf6c  mov     rcx, rsi; Lookaside
0x14005bf6f  mov     [rsp+68h+arg_0], 0
0x14005bf77  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14005bf7e  nop     dword ptr [rax+rax+00h]
0x14005bf83  mov     rbx, rax
0x14005bf86  test    rax, rax
0x14005bf89  jz      loc_14005C048
0x14005bf8f  lea     r14, [rax+10h]
0x14005bf93  mov     [rax], rsi
0x14005bf96  mov     dword ptr [rax+8], 38617473h
0x14005bf9d  test    r14, r14
0x14005bfa0  jz      loc_14005C048
0x14005bfa6  xor     edx, edx; Val
0x14005bfa8  mov     r8d, 140h; Size
0x14005bfae  mov     rcx, r14; void *
0x14005bfb1  call    memset
0x14005bfb6  mov     rcx, [rdi+0A38h]
0x14005bfbd  lea     rax, [rsp+68h+arg_0]
0x14005bfc2  mov     r9, r14
0x14005bfc5  mov     [rsp+68h+var_48], rax
0x14005bfca  mov     rcx, [rcx+1310h]
0x14005bfd1  call    Dot11ReadBLOB
0x14005bfd6  mov     ecx, [rsp+68h+arg_0]
0x14005bfda  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14005bfe4  mul     rcx
0x14005bfe7  mov     r15, 0FFFFF78000000014h
0x14005bff1  xor     esi, esi
0x14005bff3  mov     rbp, rdx
0x14005bff6  shr     rbp, 5
0x14005bffa  mov     r15, [r15]
0x14005bffd  test    ebp, ebp
0x14005bfff  jz      short loc_14005C01D
0x14005c001  lea     rcx, [rsi+rsi*4]
0x14005c005  lea     rdx, [r14+rcx*8]; struct EXTSTA_TKIP_COUNTERMEASURE_ENTRY *
0x14005c009  cmp     r15, [rdx+18h]
0x14005c00d  jnb     short loc_14005C017
0x14005c00f  mov     rcx, rdi; struct EXTSTA_VELAN *
0x14005c012  call    ?ExtSTAAddTkipCounterMeasure@@YAHPEAUEXTSTA_VELAN@@PEBUEXTSTA_TKIP_COUNTERMEASURE_ENTRY@@@Z; ExtSTAAddTkipCounterMeasure(EXTSTA_VELAN *,EXTSTA_TKIP_COUNTERMEASURE_ENTRY const *)
0x14005c017  inc     esi
0x14005c019  cmp     esi, ebp
0x14005c01b  jb      short loc_14005C001
0x14005c01d  mov     rcx, [rbx]; Lookaside
0x14005c020  test    rcx, rcx
0x14005c023  jz      short loc_14005C036
0x14005c025  mov     rdx, rbx; Entry
0x14005c028  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005c02f  nop     dword ptr [rax+rax+00h]
0x14005c034  jmp     short loc_14005C048
0x14005c036  mov     edx, [rbx+8]; Tag
0x14005c039  mov     rcx, rbx; P
0x14005c03c  call    cs:__imp_ExFreePoolWithTag
0x14005c043  nop     dword ptr [rax+rax+00h]
0x14005c048  xor     eax, eax
0x14005c04a  add     rsp, 38h
0x14005c04e  pop     r15
0x14005c050  pop     r14
0x14005c052  pop     rdi
0x14005c053  pop     rsi
0x14005c054  pop     rbp
0x14005c055  pop     rbx
0x14005c056  retn
```
