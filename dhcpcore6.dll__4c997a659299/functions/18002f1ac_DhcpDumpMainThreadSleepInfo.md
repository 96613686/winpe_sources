# DhcpDumpMainThreadSleepInfo

- ea: `0x18002f1ac`
- end: `0x18002f2e5`
- name: `DhcpDumpMainThreadSleepInfo`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002b4b0`

## callees

- `0x18002f1ac`
- `0x180031008`
- `0x1800334f8`
- `0x180033558`
- `0x180033900`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18002f207`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18002f207`

## pseudocode

```c
__int64 DhcpDumpMainThreadSleepInfo()
{
  __int64 result; // rax
  volatile signed __int32 *v1; // rbx
  signed __int32 v2; // esi
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  unsigned int i; // edi
  __int64 v7; // r9
  _UNKNOWN *retaddr; // [rsp+48h] [rbp+0h] BYREF
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  result = (__int64)&retaddr;
  v1 = (volatile signed __int32 *)g_pDhcpv6MainThreadTraceArray;
  v9 = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    result = WPP_SF_(1028, 15, WPP_f2df2b91d14732aae1b15bff910fbe97_Traceguids);
  if ( v1 )
  {
    v2 = _InterlockedCompareExchange(v1, 0, 0) + 1;
    GetSystemTimePreciseAsFileTime(&v9);
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_J(1025, 16, WPP_f2df2b91d14732aae1b15bff910fbe97_Traceguids, v9);
    for ( i = 0; i < 0x80; ++i )
    {
      result = ((_BYTE)v2 + (_BYTE)i) & 0x7F;
      v7 = 7 * result;
      if ( v1[7 * result + 1] || v1[v7 + 2] )
      {
        if ( v1[v7 + 3] )
        {
          if ( (xmmword_1800423E0 & 2) != 0 )
            result = WPP_SF_iddD(v4, v3, v5, *(_QWORD *)&v1[v7 + 1], v1[v7 + 6], v1[v7 + 7], v1[v7 + 7]);
        }
        else if ( (xmmword_1800423E0 & 2) != 0 )
        {
          result = WPP_SF_idd(v4, v3, v5, *(_QWORD *)&v1[v7 + 1], v1[v7 + 5], v1[v7 + 4]);
        }
      }
    }
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    return WPP_SF_(1028, 19, WPP_f2df2b91d14732aae1b15bff910fbe97_Traceguids);
  return result;
}

```

## disassembly

```asm
0x18002f1ac  mov     rax, rsp
0x18002f1af  mov     [rax+10h], rbx
0x18002f1b3  mov     [rax+18h], rsi
0x18002f1b7  mov     [rax+8], rcx
0x18002f1bb  push    rdi
0x18002f1bc  sub     rsp, 40h
0x18002f1c0  mov     rbx, cs:g_pDhcpv6MainThreadTraceArray
0x18002f1c7  mov     qword ptr [rax+8], 0
0x18002f1cf  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002f1d6  jz      short loc_18002F1EE
0x18002f1d8  mov     edx, 0Fh
0x18002f1dd  lea     r8, WPP_f2df2b91d14732aae1b15bff910fbe97_Traceguids
0x18002f1e4  mov     ecx, 404h
0x18002f1e9  call    WPP_SF_
0x18002f1ee  test    rbx, rbx
0x18002f1f1  jz      loc_18002F2B5
0x18002f1f7  xor     ecx, ecx
0x18002f1f9  xor     eax, eax
0x18002f1fb  lock cmpxchg [rbx], ecx
0x18002f1ff  lea     rcx, [rsp+48h+arg_0]
0x18002f204  lea     esi, [rax+1]
0x18002f207  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x18002f20e  nop     dword ptr [rax+rax+00h]
0x18002f213  test    byte ptr cs:xmmword_1800423E0, 2
0x18002f21a  jz      short loc_18002F237
0x18002f21c  mov     r9, [rsp+48h+arg_0]
0x18002f221  lea     r8, WPP_f2df2b91d14732aae1b15bff910fbe97_Traceguids
0x18002f228  mov     edx, 10h
0x18002f22d  mov     ecx, 401h
0x18002f232  call    WPP_SF_J
0x18002f237  xor     edi, edi
0x18002f239  lea     eax, [rsi+rdi]
0x18002f23c  and     eax, 7Fh
0x18002f23f  imul    r9, rax, 1Ch
0x18002f243  cmp     dword ptr [r9+rbx+4], 0
0x18002f249  jnz     short loc_18002F253
0x18002f24b  cmp     dword ptr [r9+rbx+8], 0
0x18002f251  jz      short loc_18002F2AB
0x18002f253  cmp     dword ptr [r9+rbx+0Ch], 0
0x18002f259  jz      short loc_18002F286
0x18002f25b  test    byte ptr cs:xmmword_1800423E0, 2
0x18002f262  jz      short loc_18002F2AB
0x18002f264  mov     eax, [r9+rbx+1Ch]
0x18002f269  mov     [rsp+48h+var_18], eax
0x18002f26d  mov     [rsp+48h+var_20], eax
0x18002f271  mov     eax, [r9+rbx+18h]
0x18002f276  mov     r9, [r9+rbx+4]
0x18002f27b  mov     [rsp+48h+var_28], eax
0x18002f27f  call    WPP_SF_iddD
0x18002f284  jmp     short loc_18002F2AB
0x18002f286  test    byte ptr cs:xmmword_1800423E0, 2
0x18002f28d  jz      short loc_18002F2AB
0x18002f28f  mov     eax, [r9+rbx+10h]
0x18002f294  mov     [rsp+48h+var_20], eax
0x18002f298  mov     eax, [r9+rbx+14h]
0x18002f29d  mov     r9, [r9+rbx+4]
0x18002f2a2  mov     [rsp+48h+var_28], eax
0x18002f2a6  call    WPP_SF_idd
0x18002f2ab  inc     edi
0x18002f2ad  cmp     edi, 80h
0x18002f2b3  jb      short loc_18002F239
0x18002f2b5  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002f2bc  jz      short loc_18002F2D4
0x18002f2be  mov     edx, 13h
0x18002f2c3  lea     r8, WPP_f2df2b91d14732aae1b15bff910fbe97_Traceguids
0x18002f2ca  mov     ecx, 404h
0x18002f2cf  call    WPP_SF_
0x18002f2d4  mov     rbx, [rsp+48h+arg_8]
0x18002f2d9  mov     rsi, [rsp+48h+arg_10]
0x18002f2de  add     rsp, 40h
0x18002f2e2  pop     rdi
0x18002f2e3  retn
```
