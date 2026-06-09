# CldiStreamDeleteRequest

- ea: `0x1400819ac`
- end: `0x140081a88`
- name: `CldiStreamDeleteRequest`
- size: `220`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14003fc70`
- `0x140040090`
- `0x1400413b4`
- `0x1400829e0`
- `0x140083898`

## callees

- `0x1400819ac`

## import_xrefs

- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x140081a19`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x140081a19`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400819f7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140081a4b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400819f7`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140081a4b`
- `FLTMGR!FltReleaseContext` at `0x140081a6b`
- `FLTMGR!FltReleaseContext` at `0x140081a6b`

## pseudocode

```c
void __fastcall CldiStreamDeleteRequest(char *Entry)
{
  int v1; // edi
  __int64 v3; // rsi
  __int64 v4; // rcx
  struct _PAGED_LOOKASIDE_LIST *v5; // rcx

  v1 = *(_DWORD *)Entry;
  v3 = *((_QWORD *)Entry + 15);
  v4 = *((_QWORD *)Entry + 12);
  if ( v4 && _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 32), 0xFFFFFFFF) == 1 )
  {
    *(_QWORD *)(**((_QWORD **)Entry + 12) + 72LL) = 0;
    ExFreeToPagedLookasideList(&stru_140028880, *((PVOID *)Entry + 12));
  }
  switch ( (unsigned __int16)v1 )
  {
    case 1u:
      if ( *((_QWORD *)Entry + 40) )
        FsRtlUninitializeBaseMcb((PBASE_MCB)(Entry + 304));
      v5 = &Lookaside;
      break;
    case 2u:
      v5 = &stru_140028980;
      break;
    case 3u:
      v5 = &stru_140028A00;
      break;
    default:
      goto LABEL_13;
  }
  ExFreeToPagedLookasideList(v5, Entry);
LABEL_13:
  if ( *(char **)(v3 + 56) == Entry )
    *(_QWORD *)(v3 + 56) = 0;
  FltReleaseContext(**(PFLT_CONTEXT **)v3);
}

```

## disassembly

```asm
0x1400819ac  mov     [rsp+arg_0], rbx
0x1400819b1  mov     [rsp+arg_8], rsi
0x1400819b6  push    rdi
0x1400819b7  sub     rsp, 20h
0x1400819bb  mov     edi, [rcx]
0x1400819bd  mov     rbx, rcx
0x1400819c0  mov     rsi, [rcx+78h]
0x1400819c4  mov     rcx, [rcx+60h]
0x1400819c8  movzx   edi, di
0x1400819cb  test    rcx, rcx
0x1400819ce  jz      short loc_140081A03
0x1400819d0  or      eax, 0FFFFFFFFh
0x1400819d3  lock xadd [rcx+20h], eax
0x1400819d8  cmp     eax, 1
0x1400819db  jnz     short loc_140081A03
0x1400819dd  mov     rax, [rbx+60h]
0x1400819e1  mov     rcx, [rax]
0x1400819e4  mov     qword ptr [rcx+48h], 0
0x1400819ec  lea     rcx, stru_140028880; Lookaside
0x1400819f3  mov     rdx, [rbx+60h]; Entry
0x1400819f7  call    cs:__imp_ExFreeToPagedLookasideList
0x1400819fe  nop     dword ptr [rax+rax+00h]
0x140081a03  cmp     edi, 1
0x140081a06  jnz     short loc_140081A2E
0x140081a08  cmp     qword ptr [rbx+140h], 0
0x140081a10  jz      short loc_140081A25
0x140081a12  lea     rcx, [rbx+130h]; Mcb
0x140081a19  call    cs:__imp_FsRtlUninitializeBaseMcb
0x140081a20  nop     dword ptr [rax+rax+00h]
0x140081a25  lea     rcx, Lookaside
0x140081a2c  jmp     short loc_140081A48
0x140081a2e  cmp     edi, 2
0x140081a31  jnz     short loc_140081A3C
0x140081a33  lea     rcx, stru_140028980
0x140081a3a  jmp     short loc_140081A48
0x140081a3c  cmp     edi, 3
0x140081a3f  jnz     short loc_140081A57
0x140081a41  lea     rcx, stru_140028A00; Lookaside
0x140081a48  mov     rdx, rbx; Entry
0x140081a4b  call    cs:__imp_ExFreeToPagedLookasideList
0x140081a52  nop     dword ptr [rax+rax+00h]
0x140081a57  cmp     [rsi+38h], rbx
0x140081a5b  jnz     short loc_140081A65
0x140081a5d  mov     qword ptr [rsi+38h], 0
0x140081a65  mov     rcx, [rsi]
0x140081a68  mov     rcx, [rcx]; Context
0x140081a6b  call    cs:__imp_FltReleaseContext
0x140081a72  nop     dword ptr [rax+rax+00h]
0x140081a77  mov     rbx, [rsp+28h+arg_0]
0x140081a7c  mov     rsi, [rsp+28h+arg_8]
0x140081a81  add     rsp, 20h
0x140081a85  pop     rdi
0x140081a86  retn
```
