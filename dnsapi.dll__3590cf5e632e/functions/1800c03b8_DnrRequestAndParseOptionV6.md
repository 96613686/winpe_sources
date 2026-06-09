# DnrRequestAndParseOptionV6

- ea: `0x1800c03b8`
- end: `0x1800c0536`
- name: `DnrRequestAndParseOptionV6`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800388c0`

## callees

- `0x18008b5f0`
- `0x1800c0000`
- `0x1800c01cc`
- `0x1800c03b8`

## import_xrefs

- `dhcpcsvc6!Dhcpv6RequestCachedParams` at `0x1800c04aa`
- `dhcpcsvc6!Dhcpv6RequestCachedParams` at `0x1800c04aa`
- `dhcpcsvc6!Dhcpv6FreeCachedParamsDataEx` at `0x1800c04ed`
- `dhcpcsvc6!Dhcpv6FreeCachedParamsDataEx` at `0x1800c04ed`
- `dhcpcsvc6!Dhcpv6RequestCachedParamsEx` at `0x1800c0462`
- `dhcpcsvc6!Dhcpv6RequestCachedParamsEx` at `0x1800c0462`
- `dhcpcsvc6!Dhcpv6FreeCachedParamsData` at `0x1800c0508`
- `dhcpcsvc6!Dhcpv6FreeCachedParamsData` at `0x1800c0508`

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
0x1800c03b8  mov     [rsp-8+arg_18], rbx
0x1800c03bd  push    rbp
0x1800c03be  push    rsi
0x1800c03bf  push    rdi
0x1800c03c0  lea     rbp, [rsp-47h]
0x1800c03c5  sub     rsp, 90h
0x1800c03cc  mov     rax, cs:__security_cookie
0x1800c03d3  xor     rax, rsp
0x1800c03d6  mov     [rbp+57h+var_20], rax
0x1800c03da  mov     [rbp+57h+var_60], 0
0x1800c03e2  xorps   xmm1, xmm1
0x1800c03e5  xorps   xmm0, xmm0
0x1800c03e8  mov     rdi, r8
0x1800c03eb  mov     rsi, rdx
0x1800c03ee  movups  [rbp+57h+var_50], xmm0
0x1800c03f2  movups  [rbp+57h+var_40], xmm1
0x1800c03f6  movups  [rbp+57h+var_30], xmm1
0x1800c03fa  test    rdx, rdx
0x1800c03fd  jz      short loc_1800C0405
0x1800c03ff  mov     dword ptr [rdx], 0
0x1800c0405  test    rdi, rdi
0x1800c0408  jz      short loc_1800C0411
0x1800c040a  mov     qword ptr [r8], 0
0x1800c0411  test    rcx, rcx
0x1800c0414  jnz     short loc_1800C0420
0x1800c0416  mov     ebx, 57h ; 'W'
0x1800c041b  jmp     loc_1800C04E0
0x1800c0420  test    rsi, rsi
0x1800c0423  jz      short loc_1800C0416
0x1800c0425  test    rdi, rdi
0x1800c0428  jz      short loc_1800C0416
0x1800c042a  xor     r8d, r8d
0x1800c042d  mov     dword ptr [rbp+57h+var_40+4], 90h
0x1800c0434  cmp     cs:g_fVelocityDhcpv6MultiRecordOptionSupport, r8d
0x1800c043b  lea     rax, [rbp+57h+var_40]
0x1800c043f  mov     r10d, 1
0x1800c0445  mov     qword ptr [rbp+57h+var_50+8], rax
0x1800c0449  mov     dword ptr [rbp+57h+var_50], r10d
0x1800c044d  mov     rdx, rcx
0x1800c0450  jz      short loc_1800C049B
0x1800c0452  lea     rax, [rbp+57h+var_60]
0x1800c0456  mov     ecx, r10d
0x1800c0459  lea     r9, [rbp+57h+var_50]
0x1800c045d  mov     [rsp+0A0h+var_80], rax
0x1800c0462  call    cs:__imp_Dhcpv6RequestCachedParamsEx
0x1800c0469  nop     dword ptr [rax+rax+00h]
0x1800c046e  mov     ebx, eax
0x1800c0470  test    eax, eax
0x1800c0472  jnz     short loc_1800C04E0
0x1800c0474  cmp     [rbp+57h+var_60], 0
0x1800c0479  jz      short loc_1800C04DB
0x1800c047b  mov     rax, [rbp+57h+var_60]
0x1800c047f  mov     rcx, [rax+8]
0x1800c0483  test    rcx, rcx
0x1800c0486  jz      short loc_1800C04DB
0x1800c0488  mov     edx, [rax]
0x1800c048a  test    edx, edx
0x1800c048c  jz      short loc_1800C04DB
0x1800c048e  mov     r9, rdi
0x1800c0491  mov     r8, rsi
0x1800c0494  call    DnrParseOptionV6
0x1800c0499  jmp     short loc_1800C04D7
0x1800c049b  movaps  xmm0, [rbp+57h+var_50]
0x1800c049f  lea     r9, [rbp+57h+var_70]
0x1800c04a3  xor     ecx, ecx
0x1800c04a5  movdqa  [rbp+57h+var_70], xmm0
0x1800c04aa  call    cs:__imp_Dhcpv6RequestCachedParams
0x1800c04b1  nop     dword ptr [rax+rax+00h]
0x1800c04b6  mov     ebx, eax
0x1800c04b8  test    eax, eax
0x1800c04ba  jnz     short loc_1800C04E0
0x1800c04bc  mov     rcx, qword ptr [rbp+57h+var_30]
0x1800c04c0  test    rcx, rcx
0x1800c04c3  jz      short loc_1800C04DB
0x1800c04c5  mov     edx, dword ptr [rbp+57h+var_30+8]
0x1800c04c8  test    edx, edx
0x1800c04ca  jz      short loc_1800C04DB
0x1800c04cc  mov     r9, rdi
0x1800c04cf  mov     r8, rsi
0x1800c04d2  call    DnrParseOptionV6_Old
0x1800c04d7  mov     ebx, eax
0x1800c04d9  jmp     short loc_1800C04E0
0x1800c04db  mov     ebx, 490h
0x1800c04e0  cmp     cs:g_fVelocityDhcpv6MultiRecordOptionSupport, 0
0x1800c04e7  jz      short loc_1800C04FB
0x1800c04e9  mov     rcx, [rbp+57h+var_60]
0x1800c04ed  call    cs:__imp_Dhcpv6FreeCachedParamsDataEx
0x1800c04f4  nop     dword ptr [rax+rax+00h]
0x1800c04f9  jmp     short loc_1800C0514
0x1800c04fb  movaps  xmm0, [rbp+57h+var_50]
0x1800c04ff  lea     rcx, [rbp+57h+var_70]
0x1800c0503  movdqa  [rbp+57h+var_70], xmm0
0x1800c0508  call    cs:__imp_Dhcpv6FreeCachedParamsData
0x1800c050f  nop     dword ptr [rax+rax+00h]
0x1800c0514  mov     eax, ebx
0x1800c0516  mov     rcx, [rbp+57h+var_20]
0x1800c051a  xor     rcx, rsp; StackCookie
0x1800c051d  call    __security_check_cookie
0x1800c0522  mov     rbx, [rsp+0A0h+arg_18]
0x1800c052a  add     rsp, 90h
0x1800c0531  pop     rdi
0x1800c0532  pop     rsi
0x1800c0533  pop     rbp
0x1800c0534  retn
```
