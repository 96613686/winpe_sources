# XdrDecodeBool

- ea: `0x14000d99c`
- end: `0x14000d9e9`
- name: `XdrDecodeBool`
- size: `77`
- prototype: ``
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x140004530`
- `0x14000c8d8`
- `0x14000cf04`
- `0x14000d4cc`
- `0x14000da84`
- `0x14000df64`
- `0x14000e4ec`
- `0x14000e940`
- `0x14000f274`
- `0x14000fbc0`
- `0x140010904`
- `0x140011984`
- `0x1400124ec`
- `0x140012c40`
- `0x1400132cc`
- `0x14002372c`
- `0x14002a9e0`

## callees

- `0x14000d99c`
- `0x1400150a4`
- `0x14003896c`

## pseudocode

```c
bool __fastcall XdrDecodeBool(__int64 a1)
{
  __int64 v1; // r9
  __int64 v2; // rcx
  unsigned int *v3; // rax
  unsigned int v4; // eax
  unsigned __int32 v5; // eax

  v1 = a1;
  if ( *(int *)(a1 + 264) < 0 || (unsigned int)OncRpcBufMgrGetCurrentValidLengthRemaining(a1 + 32) < 4 )
  {
    v5 = XdrDecodeIntSlow(v1);
  }
  else
  {
    v2 = *(_QWORD *)(v1 + 72);
    if ( v2 )
      v3 = *(unsigned int **)(v2 + 64);
    else
      v3 = 0;
    v4 = *v3;
    *(_QWORD *)(v2 + 64) += 4LL;
    v5 = _byteswap_ulong(v4);
  }
  return v5 != 0;
}

```

## disassembly

```asm
0x14000d99c  sub     rsp, 28h
0x14000d9a0  cmp     dword ptr [rcx+108h], 0
0x14000d9a7  mov     r9, rcx
0x14000d9aa  jl      short loc_14000D9D6
0x14000d9ac  add     rcx, 20h ; ' '
0x14000d9b0  call    OncRpcBufMgrGetCurrentValidLengthRemaining
0x14000d9b5  cmp     eax, 4
0x14000d9b8  jb      short loc_14000D9D6
0x14000d9ba  mov     rcx, [r9+48h]
0x14000d9be  test    rcx, rcx
0x14000d9c1  jnz     short loc_14000D9C7
0x14000d9c3  xor     eax, eax
0x14000d9c5  jmp     short loc_14000D9CB
0x14000d9c7  mov     rax, [rcx+40h]
0x14000d9cb  mov     eax, [rax]
0x14000d9cd  add     qword ptr [rcx+40h], 4
0x14000d9d2  bswap   eax
0x14000d9d4  jmp     short loc_14000D9DE
0x14000d9d6  mov     rcx, r9
0x14000d9d9  call    XdrDecodeIntSlow
0x14000d9de  test    eax, eax
0x14000d9e0  setnz   al
0x14000d9e3  add     rsp, 28h
0x14000d9e7  retn
```
