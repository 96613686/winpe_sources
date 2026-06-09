# CreateOrSetIpForwardEntry

- ea: `0x18002c8dc`
- end: `0x18002c9f4`
- name: `CreateOrSetIpForwardEntry`
- size: `280`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180031d0c`
- `0x180032110`

## callees

- `0x180001460`
- `0x18002c8dc`
- `0x18002ca8c`
- `0x18002cc50`

## import_xrefs

- `IPHLPAPI!ConvertIpv4MaskToLength` at `0x18002c924`
- `IPHLPAPI!ConvertIpv4MaskToLength` at `0x18002c924`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x18002c939`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x18002c939`

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
0x18002c8dc  mov     [rsp-8+arg_8], rbx
0x18002c8e1  push    rbp
0x18002c8e2  lea     rbp, [rsp-57h]
0x18002c8e7  sub     rsp, 0B0h
0x18002c8ee  mov     rax, cs:__security_cookie
0x18002c8f5  xor     rax, rsp
0x18002c8f8  mov     [rbp+57h+var_8], rax
0x18002c8fc  xorps   xmm0, xmm0
0x18002c8ff  mov     [rbp+57h+var_60], 1
0x18002c906  mov     rbx, rcx
0x18002c909  lea     rdx, [rbp+57h+MaskLength]; MaskLength
0x18002c90d  mov     ecx, [rcx+4]; Mask
0x18002c910  movups  xmmword ptr [rbp+1Fh], xmm0
0x18002c914  movups  xmmword ptr [rbp+57h+InterfaceLuid], xmm0
0x18002c918  movups  [rbp+57h+var_18], xmm0
0x18002c91c  movups  [rbp+57h+var_58], xmm0
0x18002c920  movups  [rbp+57h+var_48], xmm0
0x18002c924  call    cs:__imp_ConvertIpv4MaskToLength
0x18002c92a  test    eax, eax
0x18002c92c  jnz     loc_18002C9D7
0x18002c932  mov     ecx, [rbx+10h]; InterfaceIndex
0x18002c935  lea     rdx, [rbp+57h+InterfaceLuid+8]; InterfaceLuid
0x18002c939  call    cs:__imp_ConvertInterfaceIndexToLuid
0x18002c93f  mov     rcx, qword ptr [rbp+57h+InterfaceLuid+8]
0x18002c943  mov     qword ptr [rbp+57h+var_18], rcx
0x18002c947  test    eax, eax
0x18002c949  jnz     loc_18002C9D7
0x18002c94f  lea     rax, [rbp+57h+var_60]
0x18002c953  lea     r9, [rbp+57h+InterfaceLuid+8]
0x18002c957  mov     [rsp+0B0h+var_80], rax
0x18002c95c  call    GetParameter
0x18002c961  test    eax, eax
0x18002c963  jnz     short loc_18002C9D7
0x18002c965  mov     eax, [rbx]
0x18002c967  lea     r9, [rbp+57h+var_38]
0x18002c96b  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x18002c973  lea     rdx, NPI_MS_IPV4_MODULEID
0x18002c97a  mov     [rbp+57h+var_34], eax
0x18002c97d  mov     r8d, 10h
0x18002c983  mov     eax, [rbx+0Ch]
0x18002c986  mov     dword ptr [rbp+57h+var_18+8], eax
0x18002c989  mov     eax, [rbp+57h+var_60]
0x18002c98c  mov     [rbp+57h+var_38], eax
0x18002c98f  mov     eax, [rbx+24h]
0x18002c992  movups  [rbp+57h+var_48], xmm0
0x18002c996  mov     [rsp+0B0h+var_78], 2
0x18002c99e  movups  [rbp+57h+var_58], xmm0
0x18002c9a2  mov     dword ptr [rbp+57h+var_58+0Ch], eax
0x18002c9a5  mov     eax, [rbx+18h]
0x18002c9a8  mov     dword ptr [rbp+57h+var_48], eax
0x18002c9ab  lea     rax, [rbp+57h+var_58]
0x18002c9af  mov     dword ptr [rsp+0B0h+var_80], 20h ; ' '
0x18002c9b7  mov     [rsp+0B0h+var_88], rax
0x18002c9bc  mov     [rsp+0B0h+var_90], 30h ; '0'
0x18002c9c4  mov     byte ptr [rbp+57h+var_58], 0
0x18002c9c8  mov     byte ptr [rbp+57h+var_48+4], 0
0x18002c9cc  mov     word ptr [rbp+57h+var_48+6], 100h
0x18002c9d2  call    SetAllParameters
0x18002c9d7  mov     rcx, [rbp+57h+var_8]
0x18002c9db  xor     rcx, rsp; StackCookie
0x18002c9de  call    __security_check_cookie
0x18002c9e3  mov     rbx, [rsp+0B0h+arg_8]
0x18002c9eb  add     rsp, 0B0h
0x18002c9f2  pop     rbp
0x18002c9f3  retn
```
