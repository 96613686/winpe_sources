# CUstComputer::_ConstructSchemaBaseString(ushort *,ushort * *)

- ea: `0x18001bc94`
- end: `0x18001bd93`
- name: `?_ConstructSchemaBaseString@CUstComputer@@KAJPEAGPEAPEAG@Z`
- size: `255`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001c50c`

## callees

- `0x180003b80`
- `0x180008e5c`
- `0x180008ea0`
- `0x18000baec`
- `0x18001afa0`
- `0x18001bc94`

## string_xrefs

- `0x18001bcb9`: `CN=ms-DS-Primary-Computer,`
- `0x18001bd5c`: `CN=ms-DS-Primary-Computer,`

## pseudocode

```c
__int64 __fastcall CUstComputer::_ConstructSchemaBaseString(unsigned __int16 *a1, unsigned __int16 **a2)
{
  HRESULT v4; // ebx
  unsigned __int64 v5; // r11
  HRESULT v6; // eax
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // rax
  unsigned __int16 *v9; // rax
  __int64 v10; // r9
  unsigned __int64 v12; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int64 v13; // [rsp+58h] [rbp+20h] BYREF

  v13 = 0;
  v12 = 0;
  v4 = StringCchLengthW(L"CN=ms-DS-Primary-Computer,", 0x7FFFFFFFu, &v13);
  if ( v4 >= 0 )
  {
    v6 = StringCchLengthW(a1, 0x7FFFFFFFu, &v12);
    v5 = v12;
    v4 = v6;
  }
  if ( v4 >= 0 )
  {
    v7 = v5 + v13 + 1;
    v8 = 2 * v7;
    if ( !is_mul_ok(v7, 2u) )
      v8 = -1;
    v9 = (unsigned __int16 *)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
    *a2 = v9;
    if ( v9 )
    {
      v4 = StringCchCopyW(v9, v7, L"CN=ms-DS-Primary-Computer,");
      if ( v4 >= 0 )
        return (unsigned int)StringCchCatW(*a2, v7, a1);
    }
    else
    {
      v4 = -2147024882;
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_ab0185983553356c12180ac14bccd298_Traceguids, v10);
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001bc94  mov     rax, rsp
0x18001bc97  mov     [rax+8], rbx
0x18001bc9b  push    rbp
0x18001bc9c  push    rsi
0x18001bc9d  push    rdi
0x18001bc9e  sub     rsp, 20h
0x18001bca2  mov     rdi, rdx
0x18001bca5  mov     qword ptr [rax+20h], 0
0x18001bcad  mov     rbp, rcx
0x18001bcb0  lea     r8, [rax+20h]; unsigned __int64 *
0x18001bcb4  mov     esi, 7FFFFFFFh
0x18001bcb9  lea     rcx, aCnMsDsPrimaryC; "CN=ms-DS-Primary-Computer,"
0x18001bcc0  xor     r11d, r11d
0x18001bcc3  mov     edx, esi; unsigned __int64
0x18001bcc5  mov     [rax+18h], r11
0x18001bcc9  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001bcce  mov     ebx, eax
0x18001bcd0  test    eax, eax
0x18001bcd2  js      short loc_18001BCEA
0x18001bcd4  lea     r8, [rsp+38h+arg_10]; unsigned __int64 *
0x18001bcd9  mov     edx, esi; unsigned __int64
0x18001bcdb  mov     rcx, rbp; unsigned __int16 *
0x18001bcde  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001bce3  mov     r11, [rsp+38h+arg_10]
0x18001bce8  mov     ebx, eax
0x18001bcea  test    ebx, ebx
0x18001bcec  js      loc_18001BD84
0x18001bcf2  mov     rsi, [rsp+38h+arg_18]
0x18001bcf7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001bcfe  inc     rsi
0x18001bd01  mov     eax, 2
0x18001bd06  add     rsi, r11
0x18001bd09  mul     rsi
0x18001bd0c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001bd13  cmovb   rax, rcx
0x18001bd17  mov     rcx, rax; unsigned __int64
0x18001bd1a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001bd1f  mov     [rdi], rax
0x18001bd22  test    rax, rax
0x18001bd25  jnz     short loc_18001BD5C
0x18001bd27  mov     ebx, 8007000Eh
0x18001bd2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd33  lea     rax, WPP_GLOBAL_Control
0x18001bd3a  cmp     rcx, rax
0x18001bd3d  jz      short loc_18001BD84
0x18001bd3f  test    byte ptr [rcx+1Ch], 1
0x18001bd43  jz      short loc_18001BD84
0x18001bd45  mov     rcx, [rcx+10h]
0x18001bd49  lea     r8, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001bd50  mov     edx, 1Eh
0x18001bd55  call    WPP_SF_
0x18001bd5a  jmp     short loc_18001BD84
0x18001bd5c  lea     r8, aCnMsDsPrimaryC; "CN=ms-DS-Primary-Computer,"
0x18001bd63  mov     rdx, rsi; unsigned __int64
0x18001bd66  mov     rcx, rax; unsigned __int16 *
0x18001bd69  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001bd6e  mov     ebx, eax
0x18001bd70  test    eax, eax
0x18001bd72  js      short loc_18001BD84
0x18001bd74  mov     rcx, [rdi]; unsigned __int16 *
0x18001bd77  mov     r8, rbp; unsigned __int16 *
0x18001bd7a  mov     rdx, rsi; unsigned __int64
0x18001bd7d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001bd82  mov     ebx, eax
0x18001bd84  mov     eax, ebx
0x18001bd86  mov     rbx, [rsp+38h+arg_0]
0x18001bd8b  add     rsp, 20h
0x18001bd8f  pop     rdi
0x18001bd90  pop     rsi
0x18001bd91  pop     rbp
0x18001bd92  retn
```
