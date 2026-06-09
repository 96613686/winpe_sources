# PathIsVolumeGUIDWorker(ushort const *)

- ea: `0x14000fa50`
- end: `0x14000faf4`
- name: `?PathIsVolumeGUIDWorker@@YA_NPEBG@Z`
- size: `164`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f9b4`
- `0x1400105d8`
- `0x140010820`

## callees

- `0x14000fa50`
- `0x1400100b8`

## pseudocode

```c
char __fastcall PathIsVolumeGUIDWorker(const unsigned __int16 *a1)
{
  int v2; // edx
  unsigned __int16 v3; // cx
  _OWORD v5[3]; // [rsp+20h] [rbp-58h]
  _OWORD v6[2]; // [rsp+50h] [rbp-28h]

  if ( StrIsEqualCaseInsensitive(a1, L"\\\\?\\Volume", 10) )
  {
    v2 = 0;
    v5[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
    v5[2] = *(_OWORD *)L"000-0000-000000000000}";
    v5[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
    v6[0] = *(_OWORD *)L"-000000000000}";
    *(_OWORD *)((char *)v6 + 14) = *(_OWORD *)L"000000}";
    while ( 1 )
    {
      v3 = a1[v2 + 10];
      if ( v3 != *((_WORD *)v5 + v2)
        && (*((_WORD *)v5 + v2) != 48
         || (unsigned __int16)(v3 - 48) > 9u && (unsigned __int16)(v3 - 65) > 5u && (unsigned __int16)(v3 - 97) > 5u) )
      {
        break;
      }
      if ( (unsigned int)++v2 >= 0x26 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000fa50  push    rbx
0x14000fa52  sub     rsp, 70h
0x14000fa56  mov     r8d, 0Ah; int
0x14000fa5c  lea     rdx, aVolume; "\\\\?\\Volume"
0x14000fa63  mov     rbx, rcx
0x14000fa66  call    ?StrIsEqualCaseInsensitive@@YA_NPEBG0H@Z; StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)
0x14000fa6b  test    al, al
0x14000fa6d  jz      short loc_14000FAEB
0x14000fa6f  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x14000fa76  xor     edx, edx
0x14000fa78  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x14000fa7f  movaps  [rsp+78h+var_58], xmm0
0x14000fa84  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x14000fa8b  movaps  [rsp+78h+var_38], xmm0
0x14000fa90  movups  xmm0, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x14000fa97  movaps  [rsp+78h+var_48], xmm1
0x14000fa9c  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x14000faa3  movaps  xmmword ptr [rsp+78h+var_28], xmm1
0x14000faa8  movups  xmmword ptr [rsp+78h+var_28+0Eh], xmm0
0x14000faad  movsxd  rax, edx
0x14000fab0  movzx   ecx, word ptr [rbx+rax*2+14h]
0x14000fab5  cmp     cx, word ptr [rsp+rax*2+78h+var_58]
0x14000faba  jz      short loc_14000FAE0
0x14000fabc  cmp     word ptr [rsp+rax*2+78h+var_58], 30h ; '0'
0x14000fac2  jnz     short loc_14000FAEB
0x14000fac4  lea     eax, [rcx-30h]
0x14000fac7  cmp     ax, 9
0x14000facb  jbe     short loc_14000FAE0
0x14000facd  lea     eax, [rcx-41h]
0x14000fad0  cmp     ax, 5
0x14000fad4  jbe     short loc_14000FAE0
0x14000fad6  sub     cx, 61h ; 'a'
0x14000fada  cmp     cx, 5
0x14000fade  ja      short loc_14000FAEB
0x14000fae0  inc     edx
0x14000fae2  cmp     edx, 26h ; '&'
0x14000fae5  jb      short loc_14000FAAD
0x14000fae7  mov     al, 1
0x14000fae9  jmp     short loc_14000FAED
0x14000faeb  xor     al, al
0x14000faed  add     rsp, 70h
0x14000faf1  pop     rbx
0x14000faf2  retn
```
