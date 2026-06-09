# CldiStreamDeleteRequest

- ea: `0x140081b4c`
- end: `0x140081c28`
- name: `CldiStreamDeleteRequest`
- size: `220`
- prototype: `void __fastcall(char *Entry)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14003fcb0`
- `0x140040090`
- `0x1400413c4`
- `0x140082ba0`
- `0x140083a94`

## callees

- `0x140081b4c`

## import_xrefs

- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x140081bb9`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x140081bb9`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140081b97`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140081beb`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140081b97`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140081beb`
- `FLTMGR!FltReleaseContext` at `0x140081c0b`
- `FLTMGR!FltReleaseContext` at `0x140081c0b`

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
0x140081b4c  mov     [rsp+arg_0], rbx
0x140081b51  mov     [rsp+arg_8], rsi
0x140081b56  push    rdi
0x140081b57  sub     rsp, 20h
0x140081b5b  mov     edi, [rcx]
0x140081b5d  mov     rbx, rcx
0x140081b60  mov     rsi, [rcx+78h]
0x140081b64  mov     rcx, [rcx+60h]
0x140081b68  movzx   edi, di
0x140081b6b  test    rcx, rcx
0x140081b6e  jz      short loc_140081BA3
0x140081b70  or      eax, 0FFFFFFFFh
0x140081b73  lock xadd [rcx+20h], eax
0x140081b78  cmp     eax, 1
0x140081b7b  jnz     short loc_140081BA3
0x140081b7d  mov     rax, [rbx+60h]
0x140081b81  mov     rcx, [rax]
0x140081b84  mov     qword ptr [rcx+48h], 0
0x140081b8c  lea     rcx, stru_140028880; Lookaside
0x140081b93  mov     rdx, [rbx+60h]; Entry
0x140081b97  call    cs:__imp_ExFreeToPagedLookasideList
0x140081b9e  nop     dword ptr [rax+rax+00h]
0x140081ba3  cmp     edi, 1
0x140081ba6  jnz     short loc_140081BCE
0x140081ba8  cmp     qword ptr [rbx+140h], 0
0x140081bb0  jz      short loc_140081BC5
0x140081bb2  lea     rcx, [rbx+130h]; Mcb
0x140081bb9  call    cs:__imp_FsRtlUninitializeBaseMcb
0x140081bc0  nop     dword ptr [rax+rax+00h]
0x140081bc5  lea     rcx, Lookaside
0x140081bcc  jmp     short loc_140081BE8
0x140081bce  cmp     edi, 2
0x140081bd1  jnz     short loc_140081BDC
0x140081bd3  lea     rcx, stru_140028980
0x140081bda  jmp     short loc_140081BE8
0x140081bdc  cmp     edi, 3
0x140081bdf  jnz     short loc_140081BF7
0x140081be1  lea     rcx, stru_140028A00; Lookaside
0x140081be8  mov     rdx, rbx; Entry
0x140081beb  call    cs:__imp_ExFreeToPagedLookasideList
0x140081bf2  nop     dword ptr [rax+rax+00h]
0x140081bf7  cmp     [rsi+38h], rbx
0x140081bfb  jnz     short loc_140081C05
0x140081bfd  mov     qword ptr [rsi+38h], 0
0x140081c05  mov     rcx, [rsi]
0x140081c08  mov     rcx, [rcx]; Context
0x140081c0b  call    cs:__imp_FltReleaseContext
0x140081c12  nop     dword ptr [rax+rax+00h]
0x140081c17  mov     rbx, [rsp+28h+arg_0]
0x140081c1c  mov     rsi, [rsp+28h+arg_8]
0x140081c21  add     rsp, 20h
0x140081c25  pop     rdi
0x140081c26  retn
```
