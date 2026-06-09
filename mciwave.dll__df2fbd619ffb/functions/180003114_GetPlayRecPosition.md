# GetPlayRecPosition

- ea: `0x180003114`
- end: `0x1800031bd`
- name: `GetPlayRecPosition`
- size: `169`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000492c`
- `0x180004d18`
- `0x1800050b0`
- `0x180005170`

## callees

- `0x180003114`
- `0x1800035d0`
- `0x180005c60`

## import_xrefs

- `WINMM!waveOutGetPosition` at `0x180003165`
- `WINMM!waveOutGetPosition` at `0x180003165`

## pseudocode

```c
MMRESULT __fastcall GetPlayRecPosition(__int64 a1, _DWORD *a2, __int64 a3)
{
  unsigned int v3; // edi
  __int64 v5; // rbx
  HWAVEOUT v6; // rcx
  MMRESULT result; // eax
  int v8; // r9d
  DWORD ms; // edx
  __int64 v10; // rdx
  struct mmtime_tag v11; // [rsp+20h] [rbp-28h] BYREF

  v3 = a3;
  v5 = a1;
  if ( *(_DWORD *)(a1 + 28) != 1 )
  {
    v10 = *(unsigned int *)(a1 + 64);
LABEL_8:
    *a2 = bytes2time(a1, v10, a3);
    return 0;
  }
  v6 = *(HWAVEOUT *)(a1 + 48);
  v11.u = 0;
  v11.wType = 4;
  if ( !v6 || (result = waveOutGetPosition(v6, &v11, 0xCu)) == 0 )
  {
    a1 = v5;
    v8 = *(_DWORD *)(v5 + 68);
    ms = *(_DWORD *)(v5 + 76) - v8;
    if ( v8 + v11.u.ms <= *(_DWORD *)(v5 + 76) )
      ms = v11.u.ms;
    a3 = v3;
    v10 = v8 + ms;
    goto LABEL_8;
  }
  return result;
}

```

## disassembly

```asm
0x180003114  mov     r11, rsp
0x180003117  mov     [r11+18h], rbx
0x18000311b  mov     [r11+20h], rsi
0x18000311f  push    rdi
0x180003120  sub     rsp, 40h
0x180003124  mov     rax, cs:__security_cookie
0x18000312b  xor     rax, rsp
0x18000312e  mov     [rsp+48h+var_18], rax
0x180003133  cmp     dword ptr [rcx+1Ch], 1
0x180003137  mov     edi, r8d
0x18000313a  mov     rsi, rdx
0x18000313d  mov     rbx, rcx
0x180003140  jnz     short loc_180003194
0x180003142  mov     rcx, [rcx+30h]; hwo
0x180003146  mov     qword ptr [r11-24h], 0
0x18000314e  mov     [rsp+48h+var_28], 4
0x180003156  test    rcx, rcx
0x180003159  jz      short loc_18000316F
0x18000315b  mov     r8d, 0Ch; cbmmt
0x180003161  lea     rdx, [r11-28h]; pmmt
0x180003165  call    cs:__imp_waveOutGetPosition
0x18000316b  test    eax, eax
0x18000316d  jnz     short loc_1800031A0
0x18000316f  mov     r8d, [rsp+48h+var_24]
0x180003174  mov     rcx, rbx
0x180003177  mov     r9d, [rbx+44h]
0x18000317b  mov     edx, [rbx+4Ch]
0x18000317e  sub     edx, r9d
0x180003181  lea     eax, [r9+r8]
0x180003185  cmp     eax, [rbx+4Ch]
0x180003188  cmovbe  edx, r8d
0x18000318c  mov     r8d, edi
0x18000318f  add     edx, r9d
0x180003192  jmp     short loc_180003197
0x180003194  mov     edx, [rcx+40h]
0x180003197  call    bytes2time
0x18000319c  mov     [rsi], eax
0x18000319e  xor     eax, eax
0x1800031a0  mov     rcx, [rsp+48h+var_18]
0x1800031a5  xor     rcx, rsp; StackCookie
0x1800031a8  call    __security_check_cookie
0x1800031ad  mov     rbx, [rsp+48h+arg_10]
0x1800031b2  mov     rsi, [rsp+48h+arg_18]
0x1800031b7  add     rsp, 40h
0x1800031bb  pop     rdi
0x1800031bc  retn
```
