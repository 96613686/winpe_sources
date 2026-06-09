# SPSslEnumEccCurves

- ea: `0x18001eb90`
- end: `0x18001ebfb`
- name: `SPSslEnumEccCurves`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800068e0`
- `0x18000b654`
- `0x18001e014`
- `0x18001eb90`

## string_xrefs

- `0x18001ebb0`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslEnumEccCurves(__int64 a1)
{
  int *v1; // rdx
  __int64 v2; // rcx
  _QWORD *v3; // r8
  int v4; // r9d
  unsigned int v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rcx
  int v8; // eax

  if ( SslpValidateProvHandle(a1) )
  {
    if ( v4 )
    {
      v5 = -2146893815;
      v6 = 2141;
      v7 = 2148073481LL;
    }
    else
    {
      v8 = SslpEnumEccCurves(v2, v1, v3);
      v5 = v8;
      if ( v8 >= 0 )
        return 0;
      v6 = 2154;
      v7 = (unsigned int)v8;
    }
  }
  else
  {
    v5 = -2146893786;
    v6 = 2134;
    v7 = 2148073510LL;
  }
  DebugTraceError(v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v6);
  return v5;
}

```

## disassembly

```asm
0x18001eb90  push    rbx
0x18001eb92  sub     rsp, 20h
0x18001eb96  call    SslpValidateProvHandle
0x18001eb9b  test    rax, rax
0x18001eb9e  jnz     short loc_18001EBC5
0x18001eba0  mov     ebx, 80090026h
0x18001eba5  mov     r9d, 856h
0x18001ebab  mov     ecx, 80090026h
0x18001ebb0  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ebb7  lea     rdx, aStatus; "Status"
0x18001ebbe  call    DebugTraceError
0x18001ebc3  jmp     short loc_18001EBF3
0x18001ebc5  test    r9d, r9d
0x18001ebc8  jz      short loc_18001EBDC
0x18001ebca  mov     ebx, 80090009h
0x18001ebcf  mov     r9d, 85Dh
0x18001ebd5  mov     ecx, 80090009h
0x18001ebda  jmp     short loc_18001EBB0
0x18001ebdc  call    SslpEnumEccCurves
0x18001ebe1  mov     ebx, eax
0x18001ebe3  test    eax, eax
0x18001ebe5  jns     short loc_18001EBF1
0x18001ebe7  mov     r9d, 86Ah
0x18001ebed  mov     ecx, eax
0x18001ebef  jmp     short loc_18001EBB0
0x18001ebf1  xor     ebx, ebx
0x18001ebf3  mov     eax, ebx
0x18001ebf5  add     rsp, 20h
0x18001ebf9  pop     rbx
0x18001ebfa  retn
```
