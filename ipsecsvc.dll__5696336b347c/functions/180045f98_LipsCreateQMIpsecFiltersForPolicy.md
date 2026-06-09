# LipsCreateQMIpsecFiltersForPolicy

- ea: `0x180045f98`
- end: `0x180046065`
- name: `LipsCreateQMIpsecFiltersForPolicy`
- size: `205`
- prototype: `__int64 __fastcall(__int64, _QWORD *, __int128 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180044da0`

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x180045f98`
- `0x180047e20`

## string_xrefs

- `0x180046046`: `LipsCreateQMIpsecFiltersForPolicy`

## pseudocode

```c
__int64 __fastcall LipsCreateQMIpsecFiltersForPolicy(__int64 a1, _QWORD *a2, __int128 *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // r8
  _QWORD *v8; // rcx
  __int64 v9; // rax
  __int128 v10; // xmm0

  v6 = 0;
  while ( a1 )
  {
    v7 = *(_QWORD *)(a1 + 200);
    v8 = *(_QWORD **)(v7 + 8);
    v9 = *v8 - *a2;
    if ( *v8 == *a2 )
      v9 = v8[1] - a2[1];
    if ( !v9 )
    {
      if ( *(_QWORD *)(v7 + 16) )
      {
        v10 = *a3;
        *(_OWORD *)v8 = *a3;
        *(_OWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 200) + 16LL) + 152LL) = v10;
        v6 = LipsBfeFilterAdd(*(FWPM_FILTER0 **)(*(_QWORD *)(a1 + 200) + 16LL));
        if ( v6 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_3994775e12be339b4b2564b9df2a07e8_Traceguids, v6);
          }
          return LipsReportError(v6, "LipsCreateQMIpsecFiltersForPolicy");
        }
      }
    }
    a1 = *(_QWORD *)(a1 + 208);
  }
  if ( v6 )
    return LipsReportError(v6, "LipsCreateQMIpsecFiltersForPolicy");
  return 0;
}

```

## disassembly

```asm
0x180045f98  push    rbx
0x180045f9a  push    rbp
0x180045f9b  push    rsi
0x180045f9c  push    rdi
0x180045f9d  sub     rsp, 28h
0x180045fa1  mov     rbp, r8
0x180045fa4  mov     rsi, rdx
0x180045fa7  mov     rdi, rcx
0x180045faa  xor     ebx, ebx
0x180045fac  test    rdi, rdi
0x180045faf  jz      loc_18004605D
0x180045fb5  mov     r8, [rdi+0C8h]
0x180045fbc  mov     rcx, [r8+8]
0x180045fc0  mov     rax, [rcx]
0x180045fc3  sub     rax, [rsi]
0x180045fc6  jnz     short loc_180045FD0
0x180045fc8  mov     rax, [rcx+8]
0x180045fcc  sub     rax, [rsi+8]
0x180045fd0  test    rax, rax
0x180045fd3  jnz     short loc_18004600C
0x180045fd5  cmp     [r8+10h], rax
0x180045fd9  jz      short loc_18004600C
0x180045fdb  movups  xmm0, xmmword ptr [rbp+0]
0x180045fdf  movdqu  xmmword ptr [rcx], xmm0
0x180045fe3  mov     rax, [rdi+0C8h]
0x180045fea  mov     rcx, [rax+10h]
0x180045fee  movdqu  xmmword ptr [rcx+98h], xmm0
0x180045ff6  mov     rcx, [rdi+0C8h]
0x180045ffd  mov     rcx, [rcx+10h]; filter
0x180046001  call    LipsBfeFilterAdd
0x180046006  mov     ebx, eax
0x180046008  test    eax, eax
0x18004600a  jnz     short loc_180046015
0x18004600c  mov     rdi, [rdi+0D0h]
0x180046013  jmp     short loc_180045FAC
0x180046015  mov     rcx, cs:WPP_GLOBAL_Control
0x18004601c  lea     rax, WPP_GLOBAL_Control
0x180046023  cmp     rcx, rax
0x180046026  jz      short loc_180046046
0x180046028  test    byte ptr [rcx+1Ch], 10h
0x18004602c  jz      short loc_180046046
0x18004602e  mov     rcx, [rcx+10h]
0x180046032  lea     r8, WPP_3994775e12be339b4b2564b9df2a07e8_Traceguids
0x180046039  mov     edx, 33h ; '3'
0x18004603e  mov     r9d, ebx
0x180046041  call    WPP_SF_d
0x180046046  lea     rdx, aLipscreateqmip; "LipsCreateQMIpsecFiltersForPolicy"
0x18004604d  mov     ecx, ebx
0x18004604f  call    LipsReportError
0x180046054  add     rsp, 28h
0x180046058  pop     rdi
0x180046059  pop     rsi
0x18004605a  pop     rbp
0x18004605b  pop     rbx
0x18004605c  retn
0x18004605d  test    ebx, ebx
0x18004605f  jnz     short loc_180046046
0x180046061  xor     eax, eax
0x180046063  jmp     short loc_180046054
```
