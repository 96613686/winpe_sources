# RtlTrimNtPathSegment

- ea: `0x140026b2c`
- end: `0x140026c00`
- name: `RtlTrimNtPathSegment`
- size: `212`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x140026784`

## callees

- `0x140002360`
- `0x140026548`
- `0x140026664`
- `0x140026b2c`

## string_xrefs

- `0x140026b5e`: `onecore\base\lstring\path.cpp`
- `0x140026b78`: `RtlTrimNtPathSegment`

## pseudocode

```c
__int64 __fastcall RtlTrimNtPathSegment(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v4; // rcx
  __int64 v5; // r8
  _QWORD *v6; // r11
  __int64 result; // rax
  __int16 *v8; // r10
  __int64 v9; // r9
  __int16 *v10; // rdx
  __int16 *v11; // rcx
  __int16 v12; // ax
  _QWORD v13[4]; // [rsp+20h] [rbp-38h] BYREF
  unsigned int v14; // [rsp+40h] [rbp-18h] BYREF

  *a2 = 0;
  v14 = 0;
  *a3 = 0;
  if ( (unsigned __int8)RtlIsLUnicodeStringValid() )
  {
    v8 = (__int16 *)v4[2];
    v9 = v5;
    v10 = v8;
    v11 = (__int16 *)((char *)v8 + *v4);
    if ( v8 < v11 )
    {
      do
      {
        v12 = *v10++;
        if ( v12 != 92 )
          break;
        v9 += 2;
      }
      while ( v10 < v11 );
      if ( v10 < v11 )
      {
        do
        {
          if ( *--v11 != 92 )
            break;
          v5 += 2;
        }
        while ( v11 > v8 );
      }
    }
    *v6 = v9;
    result = 0;
    *a3 = v5;
  }
  else
  {
    v13[2] = 548;
    v13[0] = "onecore\\base\\lstring\\path.cpp";
    v13[1] = "RtlTrimNtPathSegment";
    v13[3] = "RtlIsLUnicodeStringValid(Segment)";
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v14,
             (__int64)v13,
             0xC000000D);
  }
  return result;
}

```

## disassembly

```asm
0x140026b2c  push    rbx
0x140026b2e  sub     rsp, 50h
0x140026b32  mov     rax, cs:__security_cookie
0x140026b39  xor     rax, rsp
0x140026b3c  mov     [rsp+58h+var_10], rax
0x140026b41  mov     rbx, r8
0x140026b44  mov     r11, rdx
0x140026b47  xor     r8d, r8d
0x140026b4a  mov     [rdx], r8
0x140026b4d  mov     [rsp+58h+var_18], r8d
0x140026b52  mov     [rbx], r8
0x140026b55  call    RtlIsLUnicodeStringValid
0x140026b5a  test    al, al
0x140026b5c  jnz     short loc_140026BA2
0x140026b5e  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x140026b65  mov     [rsp+58h+var_28], 224h
0x140026b6e  mov     [rsp+58h+var_38], rax
0x140026b73  lea     rdx, [rsp+58h+var_38]
0x140026b78  lea     rax, aRtltrimntpaths; "RtlTrimNtPathSegment"
0x140026b7f  mov     r8d, 0C000000Dh
0x140026b85  mov     [rsp+58h+var_30], rax
0x140026b8a  lea     rcx, [rsp+58h+var_18]
0x140026b8f  lea     rax, aRtlislunicodes; "RtlIsLUnicodeStringValid(Segment)"
0x140026b96  mov     [rsp+58h+var_20], rax
0x140026b9b  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140026ba0  jmp     short loc_140026BED
0x140026ba2  mov     r10, [rcx+10h]
0x140026ba6  mov     r9, r8
0x140026ba9  mov     rcx, [rcx]
0x140026bac  mov     rdx, r10
0x140026baf  add     rcx, r10
0x140026bb2  cmp     r10, rcx
0x140026bb5  jnb     short loc_140026BE5
0x140026bb7  movzx   eax, word ptr [rdx]
0x140026bba  add     rdx, 2
0x140026bbe  cmp     ax, 5Ch ; '\'
0x140026bc2  jnz     short loc_140026BCD
0x140026bc4  add     r9, 2
0x140026bc8  cmp     rdx, rcx
0x140026bcb  jb      short loc_140026BB7
0x140026bcd  cmp     rdx, rcx
0x140026bd0  jnb     short loc_140026BE5
0x140026bd2  sub     rcx, 2
0x140026bd6  cmp     word ptr [rcx], 5Ch ; '\'
0x140026bda  jnz     short loc_140026BE5
0x140026bdc  add     r8, 2
0x140026be0  cmp     rcx, r10
0x140026be3  ja      short loc_140026BD2
0x140026be5  mov     [r11], r9
0x140026be8  xor     eax, eax
0x140026bea  mov     [rbx], r8
0x140026bed  mov     rcx, [rsp+58h+var_10]
0x140026bf2  xor     rcx, rsp; StackCookie
0x140026bf5  call    __security_check_cookie
0x140026bfa  add     rsp, 50h
0x140026bfe  pop     rbx
0x140026bff  retn
```
