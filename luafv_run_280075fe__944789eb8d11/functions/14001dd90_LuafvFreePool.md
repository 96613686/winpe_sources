# LuafvFreePool

- ea: `0x14001dd90`
- end: `0x14001de0e`
- name: `LuafvFreePool`
- size: `126`
- prototype: ``
- caller_count: `55`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140001e98`
- `0x140002408`
- `0x140003060`
- `0x1400033c0`
- `0x140003788`
- `0x14000393c`
- `0x140003d30`
- `0x140003fb8`
- `0x1400043c4`
- `0x14000459c`
- `0x1400046c4`
- `0x140004e6c`
- `0x1400054e8`
- `0x140005798`
- `0x1400058cc`
- `0x140005a2c`
- `0x140005b84`
- `0x14001432c`
- `0x1400157d4`
- `0x1400163b0`
- `0x1400164f0`
- `0x140016670`
- `0x140017190`
- `0x1400173b0`
- `0x1400178a0`
- `0x140017b5c`
- `0x140018080`
- `0x14001897c`
- `0x140018ce8`
- `0x140018f70`
- `0x140019780`
- `0x140019b10`
- `0x14001a3c8`
- `0x14001af8c`
- `0x14001c420`
- `0x14001d060`
- `0x14001db8c`
- `0x14001dc20`
- `0x14001dd00`
- `0x14001dec8`
- `0x14001df20`
- `0x14001f620`
- `0x140020450`
- `0x1400217d8`
- `0x1400218d8`
- `0x140021e90`
- `0x140022784`
- `0x1400230a8`
- `0x140023d14`
- `0x1400258a0`

## callees

- `0x14001dd90`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14001de00`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14001de00`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dddc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dddc`
- `FLTMGR!FltReleasePushLockEx` at `0x14001ddc0`
- `FLTMGR!FltReleasePushLockEx` at `0x14001ddc0`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001dda3`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001dda3`

## pseudocode

```c
void __fastcall LuafvFreePool(__int64 a1)
{
  _BYTE *v1; // rbx

  v1 = (_BYTE *)(a1 - 8);
  FltAcquirePushLockExclusiveEx(&PoolLock, 0);
  dword_14000F2FC -= *(_DWORD *)v1;
  FltReleasePushLockEx(&PoolLock, 0);
  if ( v1[4] < 7u )
    ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)LookasideLists[(unsigned __int8)v1[4]], v1);
  else
    ExFreePoolWithTag(v1, 0x6661754Cu);
}

```

## disassembly

```asm
0x14001dd90  push    rbx
0x14001dd92  sub     rsp, 20h
0x14001dd96  lea     rbx, [rcx-8]
0x14001dd9a  xor     edx, edx
0x14001dd9c  lea     rcx, PoolLock
0x14001dda3  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001ddaa  nop     dword ptr [rax+rax+00h]
0x14001ddaf  mov     eax, [rbx]
0x14001ddb1  lea     rcx, PoolLock
0x14001ddb8  sub     cs:dword_14000F2FC, eax
0x14001ddbe  xor     edx, edx
0x14001ddc0  call    cs:__imp_FltReleasePushLockEx
0x14001ddc7  nop     dword ptr [rax+rax+00h]
0x14001ddcc  movzx   eax, byte ptr [rbx+4]
0x14001ddd0  cmp     al, 7
0x14001ddd2  jb      short loc_14001DDEF
0x14001ddd4  mov     edx, 6661754Ch; Tag
0x14001ddd9  mov     rcx, rbx; P
0x14001dddc  call    cs:__imp_ExFreePoolWithTag
0x14001dde3  nop     dword ptr [rax+rax+00h]
0x14001dde8  add     rsp, 20h
0x14001ddec  pop     rbx
0x14001dded  retn
0x14001ddef  mov     rcx, rax
0x14001ddf2  mov     rdx, rbx; Entry
0x14001ddf5  lea     rax, LookasideLists
0x14001ddfc  mov     rcx, [rax+rcx*8]; Lookaside
0x14001de00  call    cs:__imp_ExFreeToPagedLookasideList
0x14001de07  nop     dword ptr [rax+rax+00h]
0x14001de0c  jmp     short loc_14001DDE8
```
