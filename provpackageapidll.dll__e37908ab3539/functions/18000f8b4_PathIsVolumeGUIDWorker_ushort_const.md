# PathIsVolumeGUIDWorker(ushort const *)

- ea: `0x18000f8b4`
- end: `0x18000f957`
- name: `?PathIsVolumeGUIDWorker@@YA_NPEBG@Z`
- size: `163`
- prototype: `char __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f6b0`
- `0x18000f81c`
- `0x18000ff24`

## callees

- `0x18000f8b4`
- `0x18000f960`

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
0x18000f8b4  push    rbx
0x18000f8b6  sub     rsp, 70h
0x18000f8ba  mov     r8d, 0Ah; int
0x18000f8c0  lea     rdx, aVolume; "\\\\?\\Volume"
0x18000f8c7  mov     rbx, rcx
0x18000f8ca  call    ?StrIsEqualCaseInsensitive@@YA_NPEBG0H@Z; StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)
0x18000f8cf  test    al, al
0x18000f8d1  jz      short loc_18000F94F
0x18000f8d3  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x18000f8da  xor     edx, edx
0x18000f8dc  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x18000f8e3  movaps  [rsp+78h+var_58], xmm0
0x18000f8e8  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x18000f8ef  movaps  [rsp+78h+var_38], xmm0
0x18000f8f4  movups  xmm0, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x18000f8fb  movaps  [rsp+78h+var_48], xmm1
0x18000f900  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x18000f907  movaps  xmmword ptr [rsp+78h+var_28], xmm1
0x18000f90c  movups  xmmword ptr [rsp+78h+var_28+0Eh], xmm0
0x18000f911  movsxd  rax, edx
0x18000f914  movzx   ecx, word ptr [rbx+rax*2+14h]
0x18000f919  cmp     cx, word ptr [rsp+rax*2+78h+var_58]
0x18000f91e  jz      short loc_18000F944
0x18000f920  cmp     word ptr [rsp+rax*2+78h+var_58], 30h ; '0'
0x18000f926  jnz     short loc_18000F94F
0x18000f928  lea     eax, [rcx-30h]
0x18000f92b  cmp     ax, 9
0x18000f92f  jbe     short loc_18000F944
0x18000f931  lea     eax, [rcx-41h]
0x18000f934  cmp     ax, 5
0x18000f938  jbe     short loc_18000F944
0x18000f93a  sub     cx, 61h ; 'a'
0x18000f93e  cmp     cx, 5
0x18000f942  ja      short loc_18000F94F
0x18000f944  inc     edx
0x18000f946  cmp     edx, 26h ; '&'
0x18000f949  jb      short loc_18000F911
0x18000f94b  mov     al, 1
0x18000f94d  jmp     short loc_18000F951
0x18000f94f  xor     al, al
0x18000f951  add     rsp, 70h
0x18000f955  pop     rbx
0x18000f956  retn
```
