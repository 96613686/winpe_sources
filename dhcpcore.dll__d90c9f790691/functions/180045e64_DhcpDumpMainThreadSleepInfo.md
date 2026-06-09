# DhcpDumpMainThreadSleepInfo

- ea: `0x180045e64`
- end: `0x180045f8a`
- name: `DhcpDumpMainThreadSleepInfo`
- size: `294`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180042fcc`

## callees

- `0x180045e64`
- `0x18004ce84`
- `0x18004cee4`
- `0x18004d1e0`
- `0x18004d480`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180045ebf`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180045ebf`

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
  v1 = (volatile signed __int32 *)g_pDhcpMainThreadTraceArray;
  v9 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    result = WPP_SF_(1028, 15, WPP_f2df2b91d14732aae1b15bff910fbe97_Traceguids);
  if ( v1 )
  {
    v2 = _InterlockedCompareExchange(v1, 0, 0) + 1;
    GetSystemTimePreciseAsFileTime(&v9);
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_i(v4, 16, v5, v9);
    for ( i = 0; i < 0x80; ++i )
    {
      result = ((_BYTE)v2 + (_BYTE)i) & 0x7F;
      v7 = 7 * result;
      if ( v1[7 * result + 1] || v1[v7 + 2] )
      {
        if ( v1[v7 + 3] )
        {
          if ( (xmmword_1800616A0 & 2) != 0 )
            result = WPP_SF_iddD(v4, v3, v5, *(_QWORD *)&v1[v7 + 1], v1[v7 + 6], v1[v7 + 7], v1[v7 + 7]);
        }
        else if ( (xmmword_1800616A0 & 2) != 0 )
        {
          result = WPP_SF_idd(v4, v3, v5, *(_QWORD *)&v1[v7 + 1], v1[v7 + 5], v1[v7 + 4]);
        }
      }
    }
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    return WPP_SF_(1028, 19, WPP_f2df2b91d14732aae1b15bff910fbe97_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180045e64  mov     rax, rsp
0x180045e67  mov     [rax+10h], rbx
0x180045e6b  mov     [rax+18h], rsi
0x180045e6f  mov     [rax+8], rcx
0x180045e73  push    rdi
0x180045e74  sub     rsp, 40h
0x180045e78  mov     rbx, cs:g_pDhcpMainThreadTraceArray
0x180045e7f  mov     qword ptr [rax+8], 0
0x180045e87  test    byte ptr cs:xmmword_1800616A0, 10h
0x180045e8e  jz      short loc_180045EA6
0x180045e90  mov     edx, 0Fh
0x180045e95  lea     r8, WPP_f2df2b91d14732aae1b15bff910fbe97_Traceguids
0x180045e9c  mov     ecx, 404h
0x180045ea1  call    WPP_SF_
0x180045ea6  test    rbx, rbx
0x180045ea9  jz      loc_180045F5B
0x180045eaf  xor     ecx, ecx
0x180045eb1  xor     eax, eax
0x180045eb3  lock cmpxchg [rbx], ecx
0x180045eb7  lea     rcx, [rsp+48h+arg_0]
0x180045ebc  lea     esi, [rax+1]
0x180045ebf  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180045ec5  test    byte ptr cs:xmmword_1800616A0, 2
0x180045ecc  jz      short loc_180045EDD
0x180045ece  mov     r9, [rsp+48h+arg_0]
0x180045ed3  mov     edx, 10h
0x180045ed8  call    WPP_SF_i
0x180045edd  xor     edi, edi
0x180045edf  lea     eax, [rsi+rdi]
0x180045ee2  and     eax, 7Fh
0x180045ee5  imul    r9, rax, 1Ch
0x180045ee9  cmp     dword ptr [r9+rbx+4], 0
0x180045eef  jnz     short loc_180045EF9
0x180045ef1  cmp     dword ptr [r9+rbx+8], 0
0x180045ef7  jz      short loc_180045F51
0x180045ef9  cmp     dword ptr [r9+rbx+0Ch], 0
0x180045eff  jz      short loc_180045F2C
0x180045f01  test    byte ptr cs:xmmword_1800616A0, 2
0x180045f08  jz      short loc_180045F51
0x180045f0a  mov     eax, [r9+rbx+1Ch]
0x180045f0f  mov     [rsp+48h+var_18], eax
0x180045f13  mov     [rsp+48h+var_20], eax
0x180045f17  mov     eax, [r9+rbx+18h]
0x180045f1c  mov     r9, [r9+rbx+4]
0x180045f21  mov     [rsp+48h+var_28], eax
0x180045f25  call    WPP_SF_iddD
0x180045f2a  jmp     short loc_180045F51
0x180045f2c  test    byte ptr cs:xmmword_1800616A0, 2
0x180045f33  jz      short loc_180045F51
0x180045f35  mov     eax, [r9+rbx+10h]
0x180045f3a  mov     [rsp+48h+var_20], eax
0x180045f3e  mov     eax, [r9+rbx+14h]
0x180045f43  mov     r9, [r9+rbx+4]
0x180045f48  mov     [rsp+48h+var_28], eax
0x180045f4c  call    WPP_SF_idd
0x180045f51  inc     edi
0x180045f53  cmp     edi, 80h
0x180045f59  jb      short loc_180045EDF
0x180045f5b  test    byte ptr cs:xmmword_1800616A0, 10h
0x180045f62  jz      short loc_180045F7A
0x180045f64  mov     edx, 13h
0x180045f69  lea     r8, WPP_f2df2b91d14732aae1b15bff910fbe97_Traceguids
0x180045f70  mov     ecx, 404h
0x180045f75  call    WPP_SF_
0x180045f7a  mov     rbx, [rsp+48h+arg_8]
0x180045f7f  mov     rsi, [rsp+48h+arg_10]
0x180045f84  add     rsp, 40h
0x180045f88  pop     rdi
0x180045f89  retn
```
