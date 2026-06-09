# wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath

- ea: `0x180008bcc`
- end: `0x180008c18`
- name: `wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005dc4`

## callees

- `0x180008bcc`

## pseudocode

```c
void __fastcall wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(unsigned __int8 a1, int a2, __int64 a3)
{
  int v4; // edx
  unsigned int v5; // r9d
  volatile signed __int32 *v6; // r8
  signed __int32 v7; // eax
  signed __int32 v8; // ett

  v4 = a2 - 3;
  if ( v4 )
  {
    if ( v4 != 1 )
      return;
    v5 = 32;
  }
  else
  {
    v5 = 16;
  }
  v6 = *(volatile signed __int32 **)a3;
  if ( *(_BYTE *)(a3 + 30) || *(_BYTE *)(a3 + 29) )
  {
    _InterlockedOr(v6, v5);
  }
  else
  {
    v7 = *v6;
    do
    {
      if ( (v7 & 2) == 0 )
        break;
      if ( ((a1 ^ (unsigned __int8)v7) & 1) != 0 )
        break;
      v8 = v7;
      v7 = _InterlockedCompareExchange(v6, v7 | v5, v7);
    }
    while ( v8 != v7 );
  }
}

```

## disassembly

```asm
0x180008bcc  mov     r10, r8
0x180008bcf  sub     edx, 3
0x180008bd2  jz      short loc_180008BDF
0x180008bd4  cmp     edx, 1
0x180008bd7  jnz     short locret_180008C17
0x180008bd9  lea     r9d, [rdx+1Fh]
0x180008bdd  jmp     short loc_180008BE5
0x180008bdf  mov     r9d, 10h
0x180008be5  cmp     byte ptr [r10+1Eh], 0
0x180008bea  mov     r8, [r8]
0x180008bed  jnz     short loc_180008C13
0x180008bef  cmp     byte ptr [r10+1Dh], 0
0x180008bf4  jnz     short loc_180008C13
0x180008bf6  mov     eax, [r8]
0x180008bf9  test    al, 2
0x180008bfb  jz      short locret_180008C17
0x180008bfd  mov     edx, eax
0x180008bff  xor     edx, ecx
0x180008c01  test    dl, 1
0x180008c04  jnz     short locret_180008C17
0x180008c06  mov     edx, r9d
0x180008c09  or      edx, eax
0x180008c0b  lock cmpxchg [r8], edx
0x180008c10  jnz     short loc_180008BF9
0x180008c12  retn
0x180008c13  lock or [r8], r9d
0x180008c17  retn
```
