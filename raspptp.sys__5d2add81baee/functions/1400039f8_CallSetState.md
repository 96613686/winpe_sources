# CallSetState

- ea: `0x1400039f8`
- end: `0x140003a9f`
- name: `CallSetState`
- size: `167`
- prototype: ``
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x1400051f0`
- `0x140005730`
- `0x140005ee0`
- `0x14000f224`
- `0x14000f344`
- `0x14000f3fc`
- `0x14000f588`
- `0x14000f8d8`
- `0x14000fbac`
- `0x140010250`
- `0x1400102fc`
- `0x140010ef0`
- `0x140010f80`
- `0x140011050`
- `0x1400114c8`
- `0x1400133d0`
- `0x140015a40`
- `0x1400162f0`
- `0x140016980`

## callees

- `0x1400039f8`
- `0x140004138`
- `0x140004784`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140003a87`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003a87`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003a14`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003a14`

## pseudocode

```c
void __fastcall CallSetState(__int64 a1, unsigned int a2, __int64 a3, char a4)
{
  unsigned int v7; // r9d
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8

  if ( !a4 )
    *(_BYTE *)(a1 + 104) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
  if ( a2 != *(_DWORD *)(a1 + 112)
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    szCallState(a2);
    v8 = szCallState(v7);
    WPP_SF_dss(*(_QWORD *)(v9 + 24), v9, v10, *(_DWORD *)(a1 + 200), v8, v10);
  }
  *(_DWORD *)(a1 + 112) = a2;
  if ( !a4 )
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), *(_BYTE *)(a1 + 104));
}

```

## disassembly

```asm
0x1400039f8  push    rbx
0x1400039fa  push    rbp
0x1400039fb  push    rsi
0x1400039fc  push    rdi
0x1400039fd  push    r14
0x1400039ff  sub     rsp, 30h
0x140003a03  mov     r14b, r9b
0x140003a06  mov     ebp, edx
0x140003a08  mov     rsi, rcx
0x140003a0b  test    r9b, r9b
0x140003a0e  jnz     short loc_140003A23
0x140003a10  add     rcx, 60h ; '`'; SpinLock
0x140003a14  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003a1b  nop     dword ptr [rax+rax+00h]
0x140003a20  mov     [rsi+68h], al
0x140003a23  mov     r9d, [rsi+70h]
0x140003a27  cmp     ebp, r9d
0x140003a2a  jz      short loc_140003A78
0x140003a2c  mov     rdx, cs:WPP_GLOBAL_Control
0x140003a33  lea     rax, WPP_GLOBAL_Control
0x140003a3a  cmp     rdx, rax
0x140003a3d  jz      short loc_140003A78
0x140003a3f  mov     eax, [rdx+2Ch]
0x140003a42  test    al, 10h
0x140003a44  jz      short loc_140003A78
0x140003a46  cmp     byte ptr [rdx+29h], 2
0x140003a4a  jb      short loc_140003A78
0x140003a4c  mov     ecx, ebp
0x140003a4e  call    szCallState
0x140003a53  mov     ecx, r9d
0x140003a56  mov     r8, rax
0x140003a59  call    szCallState
0x140003a5e  mov     rcx, [rdx+18h]
0x140003a62  mov     r9d, [rsi+0C8h]
0x140003a69  mov     [rsp+58h+var_30], r8
0x140003a6e  mov     [rsp+58h+var_38], rax
0x140003a73  call    WPP_SF_dss
0x140003a78  mov     [rsi+70h], ebp
0x140003a7b  test    r14b, r14b
0x140003a7e  jnz     short loc_140003A93
0x140003a80  mov     dl, [rsi+68h]; NewIrql
0x140003a83  lea     rcx, [rsi+60h]; SpinLock
0x140003a87  call    cs:__imp_KeReleaseSpinLock
0x140003a8e  nop     dword ptr [rax+rax+00h]
0x140003a93  add     rsp, 30h
0x140003a97  pop     r14
0x140003a99  pop     rdi
0x140003a9a  pop     rsi
0x140003a9b  pop     rbp
0x140003a9c  pop     rbx
0x140003a9d  retn
```
