# CreateOrSetIpForwardEntry

- ea: `0x18002d9fc`
- end: `0x18002db21`
- name: `CreateOrSetIpForwardEntry`
- size: `293`
- prototype: `int __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180033304`
- `0x180033724`

## callees

- `0x180001460`
- `0x18002d9fc`
- `0x18002dbc0`
- `0x18002dda0`

## import_xrefs

- `IPHLPAPI!ConvertIpv4MaskToLength` at `0x18002da44`
- `IPHLPAPI!ConvertIpv4MaskToLength` at `0x18002da44`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x18002da5f`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x18002da5f`

## pseudocode

```c
int __fastcall CreateOrSetIpForwardEntry(_DWORD *a1)
{
  ULONG v2; // ecx
  int result; // eax
  int v4; // edx
  int v5; // r8d
  int v6; // ecx
  __int32 v7; // eax
  __m128i v8; // [rsp+58h] [rbp-1h] BYREF
  __m128i si128; // [rsp+68h] [rbp+Fh]
  __int128 v10; // [rsp+78h] [rbp+1Fh] BYREF
  NET_LUID InterfaceLuid[2]; // [rsp+88h] [rbp+2Fh] BYREF
  __int128 v12; // [rsp+98h] [rbp+3Fh]

  v2 = a1[1];
  v10 = 0;
  *(_OWORD *)&InterfaceLuid[0].Value = 0;
  v12 = 0;
  v8 = 0;
  si128 = 0;
  result = ConvertIpv4MaskToLength(v2, (PUINT8)&v10 + 8);
  if ( !result )
  {
    result = ConvertInterfaceIndexToLuid(a1[4], &InterfaceLuid[1]);
    *(NET_LUID *)&v12 = InterfaceLuid[1];
    if ( !result )
    {
      result = GetParameter(InterfaceLuid[1].Value, v4, v5, (unsigned int)&InterfaceLuid[1]);
      if ( !result )
      {
        DWORD1(v10) = *a1;
        DWORD2(v12) = a1[3];
        LODWORD(v10) = 1;
        v7 = a1[9];
        si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
        v8 = si128;
        v8.m128i_i32[3] = v7;
        si128.m128i_i32[0] = a1[6];
        v8.m128i_i8[0] = 0;
        si128.m128i_i8[4] = 0;
        si128.m128i_i16[3] = 256;
        return SetAllParameters(
                 v6,
                 (unsigned int)&NPI_MS_IPV4_MODULEID,
                 16,
                 (unsigned int)&v10,
                 48,
                 (__int64)&v8,
                 32,
                 2);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002d9fc  mov     [rsp-8+arg_8], rbx
0x18002da01  push    rbp
0x18002da02  lea     rbp, [rsp-57h]
0x18002da07  sub     rsp, 0B0h
0x18002da0e  mov     rax, cs:__security_cookie
0x18002da15  xor     rax, rsp
0x18002da18  mov     [rbp+57h+var_8], rax
0x18002da1c  xorps   xmm0, xmm0
0x18002da1f  mov     [rbp+57h+var_60], 1
0x18002da26  mov     rbx, rcx
0x18002da29  lea     rdx, [rbp+57h+MaskLength]; MaskLength
0x18002da2d  mov     ecx, [rcx+4]; Mask
0x18002da30  movups  xmmword ptr [rbp+1Fh], xmm0
0x18002da34  movups  xmmword ptr [rbp+57h+InterfaceLuid], xmm0
0x18002da38  movups  [rbp+57h+var_18], xmm0
0x18002da3c  movups  [rbp+57h+var_58], xmm0
0x18002da40  movups  [rbp+57h+var_48], xmm0
0x18002da44  call    cs:__imp_ConvertIpv4MaskToLength
0x18002da4b  nop     dword ptr [rax+rax+00h]
0x18002da50  test    eax, eax
0x18002da52  jnz     loc_18002DB03
0x18002da58  mov     ecx, [rbx+10h]; InterfaceIndex
0x18002da5b  lea     rdx, [rbp+57h+InterfaceLuid+8]; InterfaceLuid
0x18002da5f  call    cs:__imp_ConvertInterfaceIndexToLuid
0x18002da66  nop     dword ptr [rax+rax+00h]
0x18002da6b  mov     rcx, qword ptr [rbp+57h+InterfaceLuid+8]
0x18002da6f  mov     qword ptr [rbp+57h+var_18], rcx
0x18002da73  test    eax, eax
0x18002da75  jnz     loc_18002DB03
0x18002da7b  lea     rax, [rbp+57h+var_60]
0x18002da7f  lea     r9, [rbp+57h+InterfaceLuid+8]
0x18002da83  mov     [rsp+0B0h+var_80], rax
0x18002da88  call    GetParameter
0x18002da8d  test    eax, eax
0x18002da8f  jnz     short loc_18002DB03
0x18002da91  mov     eax, [rbx]
0x18002da93  lea     r9, [rbp+57h+var_38]
0x18002da97  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18002da9f  lea     rdx, NPI_MS_IPV4_MODULEID
0x18002daa6  mov     [rbp+57h+var_34], eax
0x18002daa9  mov     r8d, 10h
0x18002daaf  mov     eax, [rbx+0Ch]
0x18002dab2  mov     dword ptr [rbp+57h+var_18+8], eax
0x18002dab5  mov     eax, [rbp+57h+var_60]
0x18002dab8  mov     [rbp+57h+var_38], eax
0x18002dabb  mov     eax, [rbx+24h]
0x18002dabe  movups  [rbp+57h+var_48], xmm0
0x18002dac2  mov     [rsp+0B0h+var_78], 2
0x18002daca  movups  [rbp+57h+var_58], xmm0
0x18002dace  mov     dword ptr [rbp+57h+var_58+0Ch], eax
0x18002dad1  mov     eax, [rbx+18h]
0x18002dad4  mov     dword ptr [rbp+57h+var_48], eax
0x18002dad7  lea     rax, [rbp+57h+var_58]
0x18002dadb  mov     dword ptr [rsp+0B0h+var_80], 20h ; ' '
0x18002dae3  mov     [rsp+0B0h+var_88], rax
0x18002dae8  mov     [rsp+0B0h+var_90], 30h ; '0'
0x18002daf0  mov     byte ptr [rbp+57h+var_58], 0
0x18002daf4  mov     byte ptr [rbp+57h+var_48+4], 0
0x18002daf8  mov     word ptr [rbp+57h+var_48+6], 100h
0x18002dafe  call    SetAllParameters
0x18002db03  mov     rcx, [rbp+57h+var_8]
0x18002db07  xor     rcx, rsp; StackCookie
0x18002db0a  call    __security_check_cookie
0x18002db0f  mov     rbx, [rsp+0B0h+arg_8]
0x18002db17  add     rsp, 0B0h
0x18002db1e  pop     rbp
0x18002db1f  retn
```
