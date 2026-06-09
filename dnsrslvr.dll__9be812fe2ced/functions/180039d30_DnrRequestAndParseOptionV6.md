# DnrRequestAndParseOptionV6

- ea: `0x180039d30`
- end: `0x180039e95`
- name: `DnrRequestAndParseOptionV6`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180022a18`

## callees

- `0x180039d30`
- `0x180046ec0`
- `0x18006c170`
- `0x18006c334`

## import_xrefs

- `dhcpcsvc6!Dhcpv6RequestCachedParamsEx` at `0x180039dda`
- `dhcpcsvc6!Dhcpv6RequestCachedParamsEx` at `0x180039dda`
- `dhcpcsvc6!Dhcpv6FreeCachedParamsData` at `0x180039e6e`
- `dhcpcsvc6!Dhcpv6FreeCachedParamsData` at `0x180039e6e`
- `dhcpcsvc6!Dhcpv6FreeCachedParamsDataEx` at `0x180039e59`
- `dhcpcsvc6!Dhcpv6FreeCachedParamsDataEx` at `0x180039e59`
- `dhcpcsvc6!Dhcpv6RequestCachedParams` at `0x180039e1c`
- `dhcpcsvc6!Dhcpv6RequestCachedParams` at `0x180039e1c`

## pseudocode

```c
__int64 __fastcall DnrRequestAndParseOptionV6(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rdx
  unsigned int v8; // eax
  __int128 v10; // [rsp+30h] [rbp-19h] BYREF
  unsigned int *v11; // [rsp+40h] [rbp-9h] BYREF
  __int128 v12; // [rsp+50h] [rbp+7h] BYREF
  __int128 v13; // [rsp+60h] [rbp+17h] BYREF
  __int128 v14; // [rsp+70h] [rbp+27h]

  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a1 || !a2 || !a3 )
  {
    v5 = 87;
    goto LABEL_21;
  }
  DWORD1(v13) = 144;
  *((_QWORD *)&v12 + 1) = &v13;
  LODWORD(v12) = 1;
  if ( g_fVelocityDhcpv6MultiRecordOptionSupport )
  {
    v5 = Dhcpv6RequestCachedParamsEx(1, a1, 0, &v12, &v11);
    if ( v5 )
      goto LABEL_21;
    if ( v11 )
    {
      v6 = *((_QWORD *)v11 + 1);
      if ( v6 )
      {
        v7 = *v11;
        if ( (_DWORD)v7 )
        {
          v8 = DnrParseOptionV6(v6, v7, a2, a3);
LABEL_19:
          v5 = v8;
          goto LABEL_21;
        }
      }
    }
  }
  else
  {
    v10 = v12;
    v5 = Dhcpv6RequestCachedParams(0, a1, 0, &v10);
    if ( v5 )
      goto LABEL_21;
    if ( (_QWORD)v14 && DWORD2(v14) )
    {
      v8 = DnrParseOptionV6_Old(v14, DWORD2(v14), a2, a3);
      goto LABEL_19;
    }
  }
  v5 = 1168;
LABEL_21:
  if ( g_fVelocityDhcpv6MultiRecordOptionSupport )
  {
    Dhcpv6FreeCachedParamsDataEx(v11);
  }
  else
  {
    v10 = v12;
    Dhcpv6FreeCachedParamsData(&v10);
  }
  return v5;
}

```

## disassembly

```asm
0x180039d30  mov     [rsp-8+arg_18], rbx
0x180039d35  push    rbp
0x180039d36  push    rsi
0x180039d37  push    rdi
0x180039d38  lea     rbp, [rsp-47h]
0x180039d3d  sub     rsp, 90h
0x180039d44  mov     rax, cs:__security_cookie
0x180039d4b  xor     rax, rsp
0x180039d4e  mov     [rbp+57h+var_20], rax
0x180039d52  mov     [rbp+57h+var_60], 0
0x180039d5a  xorps   xmm1, xmm1
0x180039d5d  xorps   xmm0, xmm0
0x180039d60  mov     rdi, r8
0x180039d63  mov     rsi, rdx
0x180039d66  movups  [rbp+57h+var_50], xmm0
0x180039d6a  movups  [rbp+57h+var_40], xmm1
0x180039d6e  movups  [rbp+57h+var_30], xmm1
0x180039d72  test    rdx, rdx
0x180039d75  jz      short loc_180039D7D
0x180039d77  mov     dword ptr [rdx], 0
0x180039d7d  test    rdi, rdi
0x180039d80  jz      short loc_180039D89
0x180039d82  mov     qword ptr [r8], 0
0x180039d89  test    rcx, rcx
0x180039d8c  jnz     short loc_180039D98
0x180039d8e  mov     ebx, 57h ; 'W'
0x180039d93  jmp     loc_180039E4C
0x180039d98  test    rsi, rsi
0x180039d9b  jz      short loc_180039D8E
0x180039d9d  test    rdi, rdi
0x180039da0  jz      short loc_180039D8E
0x180039da2  xor     r8d, r8d
0x180039da5  mov     dword ptr [rbp+57h+var_40+4], 90h
0x180039dac  cmp     cs:g_fVelocityDhcpv6MultiRecordOptionSupport, r8d
0x180039db3  lea     rax, [rbp+57h+var_40]
0x180039db7  mov     r10d, 1
0x180039dbd  mov     qword ptr [rbp+57h+var_50+8], rax
0x180039dc1  mov     dword ptr [rbp+57h+var_50], r10d
0x180039dc5  mov     rdx, rcx
0x180039dc8  jz      short loc_180039E0D
0x180039dca  lea     rax, [rbp+57h+var_60]
0x180039dce  mov     ecx, r10d
0x180039dd1  lea     r9, [rbp+57h+var_50]
0x180039dd5  mov     [rsp+0A0h+var_80], rax
0x180039dda  call    cs:__imp_Dhcpv6RequestCachedParamsEx
0x180039de0  mov     ebx, eax
0x180039de2  test    eax, eax
0x180039de4  jnz     short loc_180039E4C
0x180039de6  cmp     [rbp+57h+var_60], 0
0x180039deb  jz      short loc_180039E47
0x180039ded  mov     rax, [rbp+57h+var_60]
0x180039df1  mov     rcx, [rax+8]
0x180039df5  test    rcx, rcx
0x180039df8  jz      short loc_180039E47
0x180039dfa  mov     edx, [rax]
0x180039dfc  test    edx, edx
0x180039dfe  jz      short loc_180039E47
0x180039e00  mov     r9, rdi
0x180039e03  mov     r8, rsi
0x180039e06  call    DnrParseOptionV6
0x180039e0b  jmp     short loc_180039E43
0x180039e0d  movaps  xmm0, [rbp+57h+var_50]
0x180039e11  lea     r9, [rbp+57h+var_70]
0x180039e15  xor     ecx, ecx
0x180039e17  movdqa  [rbp+57h+var_70], xmm0
0x180039e1c  call    cs:__imp_Dhcpv6RequestCachedParams
0x180039e22  mov     ebx, eax
0x180039e24  test    eax, eax
0x180039e26  jnz     short loc_180039E4C
0x180039e28  mov     rcx, qword ptr [rbp+57h+var_30]
0x180039e2c  test    rcx, rcx
0x180039e2f  jz      short loc_180039E47
0x180039e31  mov     edx, dword ptr [rbp+57h+var_30+8]
0x180039e34  test    edx, edx
0x180039e36  jz      short loc_180039E47
0x180039e38  mov     r9, rdi
0x180039e3b  mov     r8, rsi
0x180039e3e  call    DnrParseOptionV6_Old
0x180039e43  mov     ebx, eax
0x180039e45  jmp     short loc_180039E4C
0x180039e47  mov     ebx, 490h
0x180039e4c  cmp     cs:g_fVelocityDhcpv6MultiRecordOptionSupport, 0
0x180039e53  jz      short loc_180039E61
0x180039e55  mov     rcx, [rbp+57h+var_60]
0x180039e59  call    cs:__imp_Dhcpv6FreeCachedParamsDataEx
0x180039e5f  jmp     short loc_180039E74
0x180039e61  movaps  xmm0, [rbp+57h+var_50]
0x180039e65  lea     rcx, [rbp+57h+var_70]
0x180039e69  movdqa  [rbp+57h+var_70], xmm0
0x180039e6e  call    cs:__imp_Dhcpv6FreeCachedParamsData
0x180039e74  mov     eax, ebx
0x180039e76  mov     rcx, [rbp+57h+var_20]
0x180039e7a  xor     rcx, rsp; StackCookie
0x180039e7d  call    __security_check_cookie
0x180039e82  mov     rbx, [rsp+0A0h+arg_18]
0x180039e8a  add     rsp, 90h
0x180039e91  pop     rdi
0x180039e92  pop     rsi
0x180039e93  pop     rbp
0x180039e94  retn
```
