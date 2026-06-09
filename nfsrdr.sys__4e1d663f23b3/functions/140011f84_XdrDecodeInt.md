# XdrDecodeInt

- ea: `0x140011f84`
- end: `0x140011fcc`
- name: `XdrDecodeInt`
- size: `72`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `34`
- callee_count: `3`
- tags: ``

## callers

- `0x1400029d0`
- `0x140004530`
- `0x14000adb0`
- `0x14000c818`
- `0x14000c8d8`
- `0x14000cdb8`
- `0x14000ce48`
- `0x14000cf04`
- `0x14000d3e4`
- `0x14000d4cc`
- `0x14000da84`
- `0x14000df64`
- `0x14000e4ec`
- `0x14000e940`
- `0x14000f274`
- `0x14000fbc0`
- `0x140010904`
- `0x140011298`
- `0x140011984`
- `0x1400124ec`
- `0x1400132cc`
- `0x140014c64`
- `0x14001ea54`
- `0x14001f178`
- `0x140020fa8`
- `0x1400219e8`
- `0x14002372c`
- `0x140023dd0`
- `0x14002a5f0`
- `0x14002a9e0`
- `0x14002b138`
- `0x140038aec`
- `0x140038c94`
- `0x140038d28`

## callees

- `0x140011f84`
- `0x1400150a4`
- `0x14003896c`

## pseudocode

```c
__int64 __fastcall XdrDecodeInt(__int64 a1)
{
  __int64 v1; // r9
  __int64 v2; // rcx
  unsigned int *v3; // rax
  unsigned int v4; // eax

  v1 = a1;
  if ( *(int *)(a1 + 264) < 0 || (unsigned int)OncRpcBufMgrGetCurrentValidLengthRemaining(a1 + 32) < 4 )
    return XdrDecodeIntSlow(v1);
  v2 = *(_QWORD *)(v1 + 72);
  if ( v2 )
    v3 = *(unsigned int **)(v2 + 64);
  else
    v3 = 0;
  v4 = *v3;
  *(_QWORD *)(v2 + 64) += 4LL;
  return _byteswap_ulong(v4);
}

```

## disassembly

```asm
0x140011f84  sub     rsp, 28h
0x140011f88  cmp     dword ptr [rcx+108h], 0
0x140011f8f  mov     r9, rcx
0x140011f92  jl      short loc_140011FBE
0x140011f94  add     rcx, 20h ; ' '
0x140011f98  call    OncRpcBufMgrGetCurrentValidLengthRemaining
0x140011f9d  cmp     eax, 4
0x140011fa0  jb      short loc_140011FBE
0x140011fa2  mov     rcx, [r9+48h]
0x140011fa6  test    rcx, rcx
0x140011fa9  jnz     short loc_140011FAF
0x140011fab  xor     eax, eax
0x140011fad  jmp     short loc_140011FB3
0x140011faf  mov     rax, [rcx+40h]
0x140011fb3  mov     eax, [rax]
0x140011fb5  add     qword ptr [rcx+40h], 4
0x140011fba  bswap   eax
0x140011fbc  jmp     short loc_140011FC6
0x140011fbe  mov     rcx, r9
0x140011fc1  call    XdrDecodeIntSlow
0x140011fc6  add     rsp, 28h
0x140011fca  retn
```
