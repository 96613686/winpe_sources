# DnrRequestAndParseOptionV6Old

- ea: `0x18006c418`
- end: `0x18006c57e`
- name: `DnrRequestAndParseOptionV6Old`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800217f0`

## callees

- `0x180046ec0`
- `0x18006c170`
- `0x18006c334`
- `0x18006c418`

## import_xrefs

- `dhcpcsvc6!Dhcpv6RequestCachedParamsEx` at `0x18006c4c3`
- `dhcpcsvc6!Dhcpv6RequestCachedParamsEx` at `0x18006c4c3`
- `dhcpcsvc6!Dhcpv6FreeCachedParamsData` at `0x18006c557`
- `dhcpcsvc6!Dhcpv6FreeCachedParamsData` at `0x18006c557`
- `dhcpcsvc6!Dhcpv6FreeCachedParamsDataEx` at `0x18006c542`
- `dhcpcsvc6!Dhcpv6FreeCachedParamsDataEx` at `0x18006c542`
- `dhcpcsvc6!Dhcpv6RequestCachedParams` at `0x18006c505`
- `dhcpcsvc6!Dhcpv6RequestCachedParams` at `0x18006c505`

## pseudocode

```c
__int64 __fastcall DnrRequestAndParseOptionV6Old(__int64 a1, _DWORD *a2, _QWORD *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  unsigned int v9; // eax
  __int128 v11; // [rsp+30h] [rbp-19h] BYREF
  unsigned int *v12; // [rsp+40h] [rbp-9h] BYREF
  __int128 v13; // [rsp+50h] [rbp+7h] BYREF
  __int128 v14; // [rsp+60h] [rbp+17h] BYREF
  __int128 v15; // [rsp+70h] [rbp+27h]

  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a1 || !a2 || !a3 )
  {
    v5 = 87;
    goto LABEL_21;
  }
  DWORD1(v14) = 144;
  *((_QWORD *)&v13 + 1) = &v14;
  LODWORD(v13) = 1;
  v6 = a1 + 104;
  if ( g_fVelocityDhcpv6MultiRecordOptionSupport )
  {
    v5 = Dhcpv6RequestCachedParamsEx(1, v6, 0, &v13, &v12);
    if ( v5 )
      goto LABEL_21;
    if ( v12 )
    {
      v7 = *((_QWORD *)v12 + 1);
      if ( v7 )
      {
        v8 = *v12;
        if ( (_DWORD)v8 )
        {
          v9 = DnrParseOptionV6(v7, v8, a2, a3);
LABEL_19:
          v5 = v9;
          goto LABEL_21;
        }
      }
    }
  }
  else
  {
    v11 = v13;
    v5 = Dhcpv6RequestCachedParams(0, v6, 0, &v11);
    if ( v5 )
      goto LABEL_21;
    if ( (_QWORD)v15 && DWORD2(v15) )
    {
      v9 = DnrParseOptionV6_Old(v15, DWORD2(v15), a2, a3);
      goto LABEL_19;
    }
  }
  v5 = 1168;
LABEL_21:
  if ( g_fVelocityDhcpv6MultiRecordOptionSupport )
  {
    Dhcpv6FreeCachedParamsDataEx(v12);
  }
  else
  {
    v11 = v13;
    Dhcpv6FreeCachedParamsData(&v11);
  }
  return v5;
}

```

## disassembly

```asm
0x18006c418  mov     [rsp-8+arg_18], rbx
0x18006c41d  push    rbp
0x18006c41e  push    rsi
0x18006c41f  push    rdi
0x18006c420  lea     rbp, [rsp-47h]
0x18006c425  sub     rsp, 90h
0x18006c42c  mov     rax, cs:__security_cookie
0x18006c433  xor     rax, rsp
0x18006c436  mov     [rbp+57h+var_20], rax
0x18006c43a  mov     [rbp+57h+var_60], 0
0x18006c442  xorps   xmm1, xmm1
0x18006c445  xorps   xmm0, xmm0
0x18006c448  mov     rdi, r8
0x18006c44b  mov     rsi, rdx
0x18006c44e  movups  [rbp+57h+var_50], xmm0
0x18006c452  movups  [rbp+57h+var_40], xmm1
0x18006c456  movups  [rbp+57h+var_30], xmm1
0x18006c45a  test    rdx, rdx
0x18006c45d  jz      short loc_18006C465
0x18006c45f  mov     dword ptr [rdx], 0
0x18006c465  test    rdi, rdi
0x18006c468  jz      short loc_18006C471
0x18006c46a  mov     qword ptr [r8], 0
0x18006c471  test    rcx, rcx
0x18006c474  jnz     short loc_18006C480
0x18006c476  mov     ebx, 57h ; 'W'
0x18006c47b  jmp     loc_18006C535
0x18006c480  test    rsi, rsi
0x18006c483  jz      short loc_18006C476
0x18006c485  test    rdi, rdi
0x18006c488  jz      short loc_18006C476
0x18006c48a  xor     r8d, r8d
0x18006c48d  mov     dword ptr [rbp+57h+var_40+4], 90h
0x18006c494  cmp     cs:g_fVelocityDhcpv6MultiRecordOptionSupport, r8d
0x18006c49b  lea     rax, [rbp+57h+var_40]
0x18006c49f  mov     r10d, 1
0x18006c4a5  mov     qword ptr [rbp+57h+var_50+8], rax
0x18006c4a9  mov     dword ptr [rbp+57h+var_50], r10d
0x18006c4ad  lea     rdx, [rcx+68h]
0x18006c4b1  jz      short loc_18006C4F6
0x18006c4b3  lea     rax, [rbp+57h+var_60]
0x18006c4b7  mov     ecx, r10d
0x18006c4ba  lea     r9, [rbp+57h+var_50]
0x18006c4be  mov     [rsp+0A0h+var_80], rax
0x18006c4c3  call    cs:__imp_Dhcpv6RequestCachedParamsEx
0x18006c4c9  mov     ebx, eax
0x18006c4cb  test    eax, eax
0x18006c4cd  jnz     short loc_18006C535
0x18006c4cf  cmp     [rbp+57h+var_60], 0
0x18006c4d4  jz      short loc_18006C530
0x18006c4d6  mov     rax, [rbp+57h+var_60]
0x18006c4da  mov     rcx, [rax+8]
0x18006c4de  test    rcx, rcx
0x18006c4e1  jz      short loc_18006C530
0x18006c4e3  mov     edx, [rax]
0x18006c4e5  test    edx, edx
0x18006c4e7  jz      short loc_18006C530
0x18006c4e9  mov     r9, rdi
0x18006c4ec  mov     r8, rsi
0x18006c4ef  call    DnrParseOptionV6
0x18006c4f4  jmp     short loc_18006C52C
0x18006c4f6  movaps  xmm0, [rbp+57h+var_50]
0x18006c4fa  lea     r9, [rbp+57h+var_70]
0x18006c4fe  xor     ecx, ecx
0x18006c500  movdqa  [rbp+57h+var_70], xmm0
0x18006c505  call    cs:__imp_Dhcpv6RequestCachedParams
0x18006c50b  mov     ebx, eax
0x18006c50d  test    eax, eax
0x18006c50f  jnz     short loc_18006C535
0x18006c511  mov     rcx, qword ptr [rbp+57h+var_30]
0x18006c515  test    rcx, rcx
0x18006c518  jz      short loc_18006C530
0x18006c51a  mov     edx, dword ptr [rbp+57h+var_30+8]
0x18006c51d  test    edx, edx
0x18006c51f  jz      short loc_18006C530
0x18006c521  mov     r9, rdi
0x18006c524  mov     r8, rsi
0x18006c527  call    DnrParseOptionV6_Old
0x18006c52c  mov     ebx, eax
0x18006c52e  jmp     short loc_18006C535
0x18006c530  mov     ebx, 490h
0x18006c535  cmp     cs:g_fVelocityDhcpv6MultiRecordOptionSupport, 0
0x18006c53c  jz      short loc_18006C54A
0x18006c53e  mov     rcx, [rbp+57h+var_60]
0x18006c542  call    cs:__imp_Dhcpv6FreeCachedParamsDataEx
0x18006c548  jmp     short loc_18006C55D
0x18006c54a  movaps  xmm0, [rbp+57h+var_50]
0x18006c54e  lea     rcx, [rbp+57h+var_70]
0x18006c552  movdqa  [rbp+57h+var_70], xmm0
0x18006c557  call    cs:__imp_Dhcpv6FreeCachedParamsData
0x18006c55d  mov     eax, ebx
0x18006c55f  mov     rcx, [rbp+57h+var_20]
0x18006c563  xor     rcx, rsp; StackCookie
0x18006c566  call    __security_check_cookie
0x18006c56b  mov     rbx, [rsp+0A0h+arg_18]
0x18006c573  add     rsp, 90h
0x18006c57a  pop     rdi
0x18006c57b  pop     rsi
0x18006c57c  pop     rbp
0x18006c57d  retn
```
