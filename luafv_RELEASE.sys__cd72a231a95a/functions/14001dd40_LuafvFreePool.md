# LuafvFreePool

- ea: `0x14001dd40`
- end: `0x14001ddbe`
- name: `LuafvFreePool`
- size: `126`
- prototype: `void __fastcall(__int64)`
- caller_count: `53`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140001f7c`
- `0x140002698`
- `0x140003290`
- `0x1400035f0`
- `0x1400039b8`
- `0x140003b6c`
- `0x140003f60`
- `0x1400041e8`
- `0x1400045f4`
- `0x1400047cc`
- `0x14000488c`
- `0x140005034`
- `0x140005370`
- `0x14000572c`
- `0x140005800`
- `0x14001432c`
- `0x1400157d4`
- `0x1400163b0`
- `0x1400164f0`
- `0x140016670`
- `0x140017140`
- `0x140017360`
- `0x140017850`
- `0x140017b0c`
- `0x140018030`
- `0x14001892c`
- `0x140018c98`
- `0x140018f20`
- `0x140019730`
- `0x140019ac0`
- `0x14001a378`
- `0x14001af3c`
- `0x14001c3d0`
- `0x14001d010`
- `0x14001db3c`
- `0x14001dbd0`
- `0x14001dcb0`
- `0x14001de78`
- `0x14001ded0`
- `0x14001f5d0`
- `0x140020400`
- `0x140021788`
- `0x140021888`
- `0x140021e40`
- `0x140022734`
- `0x140023058`
- `0x140023cc4`
- `0x140025820`
- `0x1400280d4`
- `0x14002814c`

## callees

- `0x14001dd40`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14001ddb0`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14001ddb0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dd8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dd8c`
- `FLTMGR!FltReleasePushLockEx` at `0x14001dd70`
- `FLTMGR!FltReleasePushLockEx` at `0x14001dd70`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001dd53`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001dd53`

## pseudocode

```c
void __fastcall LuafvFreePool(__int64 a1)
{
  _BYTE *v1; // rbx

  v1 = (_BYTE *)(a1 - 8);
  FltAcquirePushLockExclusiveEx(&PoolLock, 0);
  dword_14000ECBC -= *(_DWORD *)v1;
  FltReleasePushLockEx(&PoolLock, 0);
  if ( v1[4] < 7u )
    ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)LookasideLists[(unsigned __int8)v1[4]], v1);
  else
    ExFreePoolWithTag(v1, 0x6661754Cu);
}

```

## disassembly

```asm
0x14001dd40  push    rbx
0x14001dd42  sub     rsp, 20h
0x14001dd46  lea     rbx, [rcx-8]
0x14001dd4a  xor     edx, edx
0x14001dd4c  lea     rcx, PoolLock
0x14001dd53  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001dd5a  nop     dword ptr [rax+rax+00h]
0x14001dd5f  mov     eax, [rbx]
0x14001dd61  lea     rcx, PoolLock
0x14001dd68  sub     cs:dword_14000ECBC, eax
0x14001dd6e  xor     edx, edx
0x14001dd70  call    cs:__imp_FltReleasePushLockEx
0x14001dd77  nop     dword ptr [rax+rax+00h]
0x14001dd7c  movzx   eax, byte ptr [rbx+4]
0x14001dd80  cmp     al, 7
0x14001dd82  jb      short loc_14001DD9F
0x14001dd84  mov     edx, 6661754Ch; Tag
0x14001dd89  mov     rcx, rbx; P
0x14001dd8c  call    cs:__imp_ExFreePoolWithTag
0x14001dd93  nop     dword ptr [rax+rax+00h]
0x14001dd98  add     rsp, 20h
0x14001dd9c  pop     rbx
0x14001dd9d  retn
0x14001dd9f  mov     rcx, rax
0x14001dda2  mov     rdx, rbx; Entry
0x14001dda5  lea     rax, LookasideLists
0x14001ddac  mov     rcx, [rax+rcx*8]; Lookaside
0x14001ddb0  call    cs:__imp_ExFreeToPagedLookasideList
0x14001ddb7  nop     dword ptr [rax+rax+00h]
0x14001ddbc  jmp     short loc_14001DD98
```
