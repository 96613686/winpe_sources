# EEDBTrimGuidBracket(ushort const *,ushort *)

- ea: `0x18000deb0`
- end: `0x18000df45`
- name: `?EEDBTrimGuidBracket@@YAJPEBGPEAG@Z`
- size: `149`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ddd0`
- `0x18000df4c`
- `0x18000eb50`
- `0x18000eccc`
- `0x18000f860`
- `0x18000faf0`
- `0x18000ffa0`

## callees

- `0x1800040a4`
- `0x18000b534`
- `0x18000deb0`

## pseudocode

```c
__int64 __fastcall EEDBTrimGuidBracket(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  int v3; // ecx
  unsigned __int16 *v4; // r11
  unsigned __int64 v5; // rdx
  const unsigned __int16 *v6; // r11
  __int64 v7; // r11
  unsigned __int64 v9; // [rsp+30h] [rbp+8h] BYREF

  v9 = 0;
  if ( a1 && a2 )
  {
    v3 = StringCchLengthW(a1, (unsigned __int64)a2, &v9);
    if ( v3 >= 0 )
    {
      if ( v9 - 2 > 0x24 )
        return (unsigned int)-2147418113;
      v3 = StringCchCopyW(v4, 0x27u, a1 + 1);
      if ( v3 >= 0 )
      {
        v3 = StringCchLengthW(v6, v5, &v9);
        if ( v3 >= 0 )
        {
          if ( v9 - 2 <= 0x24 )
          {
            *(_WORD *)(v7 + 2 * v9 - 2) = 0;
            return (unsigned int)v3;
          }
          return (unsigned int)-2147418113;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000deb0  push    rbx
0x18000deb2  sub     rsp, 20h
0x18000deb6  mov     [rsp+28h+arg_0], 0
0x18000debf  mov     r11, rdx
0x18000dec2  mov     rbx, rcx
0x18000dec5  test    rcx, rcx
0x18000dec8  jnz     short loc_18000DED1
0x18000deca  mov     ecx, 80070057h; unsigned __int16 *
0x18000decf  jmp     short loc_18000DF3D
0x18000ded1  test    r11, r11
0x18000ded4  jz      short loc_18000DECA
0x18000ded6  lea     r8, [rsp+28h+arg_0]; unsigned __int64 *
0x18000dedb  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000dee0  mov     ecx, eax
0x18000dee2  test    eax, eax
0x18000dee4  js      short loc_18000DF3D
0x18000dee6  mov     rax, [rsp+28h+arg_0]
0x18000deeb  add     rax, 0FFFFFFFFFFFFFFFEh
0x18000deef  cmp     rax, 24h ; '$'
0x18000def3  ja      short loc_18000DF38
0x18000def5  lea     r8, [rbx+2]; unsigned __int16 *
0x18000def9  mov     edx, 27h ; '''; unsigned __int64
0x18000defe  mov     rcx, r11; unsigned __int16 *
0x18000df01  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000df06  mov     ecx, eax
0x18000df08  test    eax, eax
0x18000df0a  js      short loc_18000DF3D
0x18000df0c  lea     r8, [rsp+28h+arg_0]; unsigned __int64 *
0x18000df11  mov     rcx, r11; unsigned __int16 *
0x18000df14  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000df19  mov     ecx, eax
0x18000df1b  test    eax, eax
0x18000df1d  js      short loc_18000DF3D
0x18000df1f  mov     rdx, [rsp+28h+arg_0]
0x18000df24  lea     rax, [rdx-2]
0x18000df28  cmp     rax, 24h ; '$'
0x18000df2c  ja      short loc_18000DF38
0x18000df2e  xor     eax, eax
0x18000df30  mov     [r11+rdx*2-2], ax
0x18000df36  jmp     short loc_18000DF3D
0x18000df38  mov     ecx, 8000FFFFh
0x18000df3d  mov     eax, ecx
0x18000df3f  add     rsp, 20h
0x18000df43  pop     rbx
0x18000df44  retn
```
