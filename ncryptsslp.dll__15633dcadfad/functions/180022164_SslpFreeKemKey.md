# SslpFreeKemKey

- ea: `0x180022164`
- end: `0x1800221f6`
- name: `SslpFreeKemKey`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800022a0`
- `0x180021a74`
- `0x180021b60`
- `0x1800222f0`
- `0x180022420`
- `0x180023234`
- `0x1800234b0`

## callees

- `0x180003ef0`
- `0x18000b654`
- `0x180022164`

## import_xrefs

- `ncrypt!NCryptFreeObject` at `0x1800221a4`
- `ncrypt!NCryptFreeObject` at `0x1800221a4`

## string_xrefs

- `0x18002217b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tlskem.c`

## pseudocode

```c
__int64 __fastcall SslpFreeKemKey(unsigned int *a1)
{
  NCRYPT_HANDLE v4; // rcx
  _BYTE *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  _BYTE *v8; // rcx

  if ( a1 )
  {
    if ( a1[12]-- == 1 )
    {
      v4 = *((_QWORD *)a1 + 3);
      if ( v4 )
        NCryptFreeObject(v4);
      v5 = (_BYTE *)*((_QWORD *)a1 + 4);
      if ( v5 )
      {
        v6 = a1[10];
        if ( a1[10] )
        {
          do
          {
            *v5++ = 0;
            --v6;
          }
          while ( v6 );
        }
        MSCryptFree(*((_QWORD *)a1 + 4));
      }
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
    DebugTraceError(2148073511LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tlskem.c", 40);
    return 2148073511LL;
  }
}

```

## disassembly

```asm
0x180022164  push    rbx
0x180022166  sub     rsp, 20h
0x18002216a  mov     rbx, rcx
0x18002216d  test    rcx, rcx
0x180022170  jnz     short loc_180022195
0x180022172  lea     r9d, [rcx+28h]
0x180022176  mov     ecx, 80090027h
0x18002217b  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180022182  lea     rdx, aStatus_0; "status"
0x180022189  call    DebugTraceError
0x18002218e  mov     eax, 80090027h
0x180022193  jmp     short loc_1800221F0
0x180022195  add     dword ptr [rcx+30h], 0FFFFFFFFh
0x180022199  jnz     short loc_1800221EE
0x18002219b  mov     rcx, [rcx+18h]; hObject
0x18002219f  test    rcx, rcx
0x1800221a2  jz      short loc_1800221AA
0x1800221a4  call    cs:__imp_NCryptFreeObject
0x1800221aa  mov     rax, [rbx+20h]
0x1800221ae  test    rax, rax
0x1800221b1  jz      short loc_1800221D0
0x1800221b3  mov     ecx, [rbx+28h]
0x1800221b6  test    rcx, rcx
0x1800221b9  jz      short loc_1800221C7
0x1800221bb  mov     byte ptr [rax], 0
0x1800221be  inc     rax
0x1800221c1  sub     rcx, 1
0x1800221c5  jnz     short loc_1800221BB
0x1800221c7  mov     rcx, [rbx+20h]
0x1800221cb  call    MSCryptFree
0x1800221d0  mov     eax, [rbx]
0x1800221d2  mov     rcx, rbx
0x1800221d5  test    rax, rax
0x1800221d8  jz      short loc_1800221E6
0x1800221da  mov     byte ptr [rcx], 0
0x1800221dd  inc     rcx
0x1800221e0  sub     rax, 1
0x1800221e4  jnz     short loc_1800221DA
0x1800221e6  mov     rcx, rbx
0x1800221e9  call    MSCryptFree
0x1800221ee  xor     eax, eax
0x1800221f0  add     rsp, 20h
0x1800221f4  pop     rbx
0x1800221f5  retn
```
