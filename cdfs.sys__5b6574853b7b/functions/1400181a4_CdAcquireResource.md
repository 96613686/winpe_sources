# CdAcquireResource

- ea: `0x1400181a4`
- end: `0x140018246`
- name: `CdAcquireResource`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `34`
- callee_count: `2`
- tags: ``

## callers

- `0x1400016b0`
- `0x140001d0c`
- `0x140001fd0`
- `0x1400024e0`
- `0x1400028e0`
- `0x14000b1a4`
- `0x14000bcf8`
- `0x14000c248`
- `0x14000c374`
- `0x14000c8b4`
- `0x14000dc38`
- `0x14000e1d0`
- `0x14000e544`
- `0x140011674`
- `0x140011744`
- `0x140012d24`
- `0x140013140`
- `0x1400135d0`
- `0x140013ac8`
- `0x1400141e0`
- `0x1400142d8`
- `0x140014c38`
- `0x140014e4c`
- `0x140015090`
- `0x140016fe8`
- `0x140017148`
- `0x14001734c`
- `0x1400174c8`
- `0x1400176a8`
- `0x140017ab8`
- `0x14001943c`
- `0x14001a688`
- `0x14001aa78`
- `0x14001af0c`

## callees

- `0x140001114`
- `0x1400181a4`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140018207`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140018207`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400181f6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400181f6`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x1400181e5`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x1400181e5`

## pseudocode

```c
BOOLEAN __fastcall CdAcquireResource(__int64 a1, struct _ERESOURCE *a2, char a3, int a4)
{
  BOOLEAN v6; // dl
  int v8; // r9d
  BOOLEAN result; // al

  v6 = 0;
  if ( !a3 )
    v6 = (*(_BYTE *)(a1 + 32) & 4) != 0;
  if ( !a4 )
  {
    result = ExAcquireResourceExclusiveLite(a2, v6);
LABEL_10:
    if ( result )
      return result;
    goto LABEL_11;
  }
  v8 = a4 - 1;
  if ( !v8 )
  {
    result = ExAcquireResourceSharedLite(a2, v6);
    goto LABEL_10;
  }
  if ( v8 == 1 )
  {
    result = ExAcquireSharedStarveExclusive(a2, v6);
    goto LABEL_10;
  }
  result = 0;
LABEL_11:
  if ( !a3 )
    CdRaiseStatusEx(a1, 3221225688LL, 0, 1572864, 134);
  return result;
}

```

## disassembly

```asm
0x1400181a4  mov     [rsp+arg_0], rbx
0x1400181a9  push    rdi
0x1400181aa  sub     rsp, 30h
0x1400181ae  mov     r10, rdx
0x1400181b1  mov     bl, r8b
0x1400181b4  xor     dl, dl
0x1400181b6  mov     rdi, rcx
0x1400181b9  test    r8b, r8b
0x1400181bc  jnz     short loc_1400181CD
0x1400181be  test    byte ptr [rcx+20h], 4
0x1400181c2  mov     eax, 1
0x1400181c7  movzx   edx, dl
0x1400181ca  cmovnz  edx, eax; Wait
0x1400181cd  test    r9d, r9d
0x1400181d0  jz      short loc_140018204
0x1400181d2  sub     r9d, 1
0x1400181d6  jz      short loc_1400181F3
0x1400181d8  cmp     r9d, 1
0x1400181dc  jz      short loc_1400181E2
0x1400181de  xor     al, al
0x1400181e0  jmp     short loc_140018217
0x1400181e2  mov     rcx, r10; Resource
0x1400181e5  call    cs:__imp_ExAcquireSharedStarveExclusive
0x1400181ec  nop     dword ptr [rax+rax+00h]
0x1400181f1  jmp     short loc_140018213
0x1400181f3  mov     rcx, r10; Resource
0x1400181f6  call    cs:__imp_ExAcquireResourceSharedLite
0x1400181fd  nop     dword ptr [rax+rax+00h]
0x140018202  jmp     short loc_140018213
0x140018204  mov     rcx, r10; Resource
0x140018207  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001820e  nop     dword ptr [rax+rax+00h]
0x140018213  test    al, al
0x140018215  jnz     short loc_14001821B
0x140018217  test    bl, bl
0x140018219  jz      short loc_140018227
0x14001821b  mov     rbx, [rsp+38h+arg_0]
0x140018220  add     rsp, 30h
0x140018224  pop     rdi
0x140018225  retn
0x140018227  mov     r9d, 180000h
0x14001822d  mov     [rsp+38h+var_18], 86h
0x140018235  xor     r8d, r8d
0x140018238  mov     edx, 0C00000D8h
0x14001823d  mov     rcx, rdi
0x140018240  call    CdRaiseStatusEx
```
