# SslpFreeEphemeralKey

- ea: `0x180013e6c`
- end: `0x180013f01`
- name: `SslpFreeEphemeralKey`
- size: `149`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800022a0`
- `0x180013950`
- `0x180013b80`
- `0x180021778`
- `0x180023234`
- `0x1800234b0`

## callees

- `0x180003ef0`
- `0x18000b594`
- `0x180013e6c`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x180013ed5`
- `ncrypt!NCryptFreeObject` at `0x180013ed5`

## string_xrefs

- `0x180013e97`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlsephemeral.c`

## pseudocode

```c
__int64 __fastcall SslpFreeEphemeralKey(unsigned int *a1, int a2, int a3)
{
  NCRYPT_HANDLE v6; // rcx
  __int64 v7; // rax
  _BYTE *v8; // rcx

  if ( a1 )
  {
    if ( a1[9]-- == 1 )
    {
      v6 = *((_QWORD *)a1 + 3);
      if ( v6 )
        NCryptFreeObject(v6);
      v7 = *a1;
      v8 = a1;
      if ( *a1 )
      {
        do
        {
          *v8++ = 0;
          --v7;
        }
        while ( v7 );
      }
      MSCryptFree(a1);
    }
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlsephemeral.c",
        42);
    return 2148073511LL;
  }
}

```

## disassembly

```asm
0x180013e6c  push    rbx
0x180013e6e  sub     rsp, 40h
0x180013e72  mov     rbx, rcx
0x180013e75  test    rcx, rcx
0x180013e78  jnz     short loc_180013EC6
0x180013e7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e81  lea     rax, WPP_GLOBAL_Control
0x180013e88  cmp     rcx, rax
0x180013e8b  jz      short loc_180013EBF
0x180013e8d  test    byte ptr [rcx+1Ch], 1
0x180013e91  jz      short loc_180013EBF
0x180013e93  mov     rcx, [rcx+10h]
0x180013e97  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013e9e  mov     [rsp+48h+var_18], 2Ah ; '*'
0x180013ea6  lea     r9, aStatus_0; "status"
0x180013ead  mov     [rsp+48h+var_20], rax
0x180013eb2  mov     [rsp+48h+var_28], 80090027h
0x180013eba  call    WPP_SF_sDsd
0x180013ebf  mov     eax, 80090027h
0x180013ec4  jmp     short loc_180013EFB
0x180013ec6  add     dword ptr [rcx+24h], 0FFFFFFFFh
0x180013eca  jnz     short loc_180013EF9
0x180013ecc  mov     rcx, [rcx+18h]; hObject
0x180013ed0  test    rcx, rcx
0x180013ed3  jz      short loc_180013EDB
0x180013ed5  call    cs:__imp_NCryptFreeObject
0x180013edb  mov     eax, [rbx]
0x180013edd  mov     rcx, rbx
0x180013ee0  test    rax, rax
0x180013ee3  jz      short loc_180013EF1
0x180013ee5  mov     byte ptr [rcx], 0
0x180013ee8  inc     rcx
0x180013eeb  sub     rax, 1
0x180013eef  jnz     short loc_180013EE5
0x180013ef1  mov     rcx, rbx
0x180013ef4  call    MSCryptFree
0x180013ef9  xor     eax, eax
0x180013efb  add     rsp, 40h
0x180013eff  pop     rbx
0x180013f00  retn
```
