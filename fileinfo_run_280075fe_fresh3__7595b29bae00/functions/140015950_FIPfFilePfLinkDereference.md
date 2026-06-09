# FIPfFilePfLinkDereference

- ea: `0x140015950`
- end: `0x1400159ed`
- name: `FIPfFilePfLinkDereference`
- size: `157`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140015460`
- `0x14001606c`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x140002d64`
- `0x140015950`
- `0x1400165f4`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x1400159b9`
- `FLTMGR!FltReleaseContext` at `0x1400159b9`

## pseudocode

```c
void __fastcall FIPfFilePfLinkDereference(__int64 *a1)
{
  _QWORD *v1; // rdi
  __int64 v3; // rsi
  bool v4; // zf
  __int64 *v5; // rax
  __int64 **v6; // rcx

  v1 = (_QWORD *)a1[7];
  v3 = v1[3];
  FILockExclusiveAcquire(v3 + 136);
  v4 = (*((_DWORD *)a1 + 4))-- == 1;
  if ( v4 )
  {
    v5 = (__int64 *)*a1;
    if ( *(__int64 **)(*a1 + 8) != a1 || (v6 = (__int64 **)a1[1], *v6 != a1) )
      __fastfail(3u);
    *v6 = v5;
    v5[1] = (__int64)v6;
    a1[1] = (__int64)a1;
    *a1 = (__int64)a1;
    v4 = (*(_DWORD *)(v3 + 208))-- == 1;
    if ( v4 && *(_DWORD *)(v3 + 220) )
      FIPfBlockersRelease(v3 + 192);
  }
  FILockExclusiveRelease(v3 + 136);
  FIPfFilePfContextDereference(a1, v1);
  FltReleaseContext(v1);
}

```

## disassembly

```asm
0x140015950  push    rbx
0x140015952  push    rbp
0x140015953  push    rsi
0x140015954  push    rdi
0x140015955  sub     rsp, 28h
0x140015959  mov     rdi, [rcx+38h]
0x14001595d  mov     rbx, rcx
0x140015960  mov     rsi, [rdi+18h]
0x140015964  lea     rcx, [rsi+88h]
0x14001596b  call    FILockExclusiveAcquire
0x140015970  add     dword ptr [rbx+10h], 0FFFFFFFFh
0x140015974  jnz     short loc_14001599F
0x140015976  mov     rax, [rbx]
0x140015979  cmp     [rax+8], rbx
0x14001597d  jnz     short loc_1400159CF
0x14001597f  mov     rcx, [rbx+8]
0x140015983  cmp     [rcx], rbx
0x140015986  jnz     short loc_1400159CF
0x140015988  mov     [rcx], rax
0x14001598b  mov     [rax+8], rcx
0x14001598f  mov     [rbx+8], rbx
0x140015993  mov     [rbx], rbx
0x140015996  add     dword ptr [rsi+0D0h], 0FFFFFFFFh
0x14001599d  jz      short loc_1400159D6
0x14001599f  lea     rcx, [rsi+88h]
0x1400159a6  call    FILockExclusiveRelease
0x1400159ab  mov     rdx, rdi
0x1400159ae  mov     rcx, rbx
0x1400159b1  call    FIPfFilePfContextDereference
0x1400159b6  mov     rcx, rdi; Context
0x1400159b9  call    cs:__imp_FltReleaseContext
0x1400159c0  nop     dword ptr [rax+rax+00h]
0x1400159c5  add     rsp, 28h
0x1400159c9  pop     rdi
0x1400159ca  pop     rsi
0x1400159cb  pop     rbp
0x1400159cc  pop     rbx
0x1400159cd  retn
0x1400159cf  mov     ecx, 3
0x1400159d4  int     29h; Win8: RtlFailFast(ecx)
0x1400159d6  cmp     dword ptr [rsi+0DCh], 0
0x1400159dd  jz      short loc_14001599F
0x1400159df  lea     rcx, [rsi+0C0h]
0x1400159e6  call    FIPfBlockersRelease
0x1400159eb  jmp     short loc_14001599F
```
