# COfflinePropSheetExt::_OnSyncConflictRecAddedOrRemoved(ushort const *)

- ea: `0x1800212a4`
- end: `0x1800212f6`
- name: `?_OnSyncConflictRecAddedOrRemoved@COfflinePropSheetExt@@AEAAJPEBG@Z`
- size: `82`
- prototype: `__int64 __fastcall(COfflinePropSheetExt *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800205b0`

## callees

- `0x18000735c`
- `0x1800212a4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800212ce`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800212ce`
- `USER32!PostMessageW` at `0x1800212e8`
- `USER32!PostMessageW` at `0x1800212e8`

## pseudocode

```c
__int64 __fastcall COfflinePropSheetExt::_OnSyncConflictRecAddedOrRemoved(HWND *this, const unsigned __int16 *a2)
{
  const WCHAR *lpString2; // rax
  PCNZWCH v4; // rdx

  lpString2 = CPath::_GetConstBuffer((CPath *)(this + 13));
  if ( CompareStringW(0x7Fu, 1u, v4, -1, lpString2, -1) == 2 )
    PostMessageW(this[5], 0x626u, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x1800212a4  push    rbx
0x1800212a6  sub     rsp, 30h
0x1800212aa  mov     rbx, rcx
0x1800212ad  add     rcx, 68h ; 'h'; this
0x1800212b1  call    ?_GetConstBuffer@CPath@@AEBAPEBGXZ; CPath::_GetConstBuffer(void)
0x1800212b6  or      r9d, 0FFFFFFFFh; cchCount1
0x1800212ba  mov     r8, rdx; lpString1
0x1800212bd  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x1800212c2  mov     [rsp+38h+lpString2], rax; lpString2
0x1800212c7  lea     edx, [r9+2]; dwCmpFlags
0x1800212cb  lea     ecx, [rdx+7Eh]; Locale
0x1800212ce  call    cs:__imp_CompareStringW
0x1800212d4  cmp     eax, 2
0x1800212d7  jnz     short loc_1800212EE
0x1800212d9  mov     rcx, [rbx+28h]; hWnd
0x1800212dd  xor     r9d, r9d; lParam
0x1800212e0  xor     r8d, r8d; wParam
0x1800212e3  mov     edx, 626h; Msg
0x1800212e8  call    cs:__imp_PostMessageW
0x1800212ee  xor     eax, eax
0x1800212f0  add     rsp, 30h
0x1800212f4  pop     rbx
0x1800212f5  retn
```
