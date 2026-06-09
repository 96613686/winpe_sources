# VidMmFlushCpuCacheWorker

- ea: `0x1400b1f94`
- end: `0x1400b2171`
- name: `VidMmFlushCpuCacheWorker`
- size: `477`
- prototype: `__int64 __fastcall(PVOID BaseAddress, ULONG Length)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400b63b8`
- `0x1400baec0`

## callees

- `0x1400045ec`
- `0x140012e28`
- `0x140030fa0`
- `0x14003142c`
- `0x1400b1f94`

## import_xrefs

- `ntoskrnl!KeInvalidateAllCaches` at `0x1400b2086`
- `ntoskrnl!KeInvalidateAllCaches` at `0x1400b2086`
- `ntoskrnl!KeInvalidateRangeAllCaches` at `0x1400b20ad`
- `ntoskrnl!KeInvalidateRangeAllCaches` at `0x1400b20ad`
- `watchdog!WdLogSingleEntry0` at `0x1400b200b`
- `watchdog!WdLogSingleEntry0` at `0x1400b20da`
- `watchdog!WdLogSingleEntry0` at `0x1400b200b`
- `watchdog!WdLogSingleEntry0` at `0x1400b20da`

## string_xrefs

- `0x1400b2114`: `Exception occured while trying to flush allocation from processor cache.\n`

## pseudocode

```c
__int64 __fastcall VidMmFlushCpuCacheWorker(char *BaseAddress, unsigned __int64 Length, __int64 a3)
{
  char *v4; // r14
  int v5; // ecx
  int v6; // r8d
  __int64 v7; // rcx
  __int64 v8; // r8
  ULONG v10; // ebx
  __int64 v11; // rcx
  __int64 v12; // r8
  unsigned int v13; // [rsp+50h] [rbp-38h] BYREF
  __int64 v14; // [rsp+58h] [rbp-30h]
  char v15; // [rsp+60h] [rbp-28h]

  v4 = BaseAddress;
  v13 = -1;
  v14 = 0;
  if ( (qword_140086010 & 2) != 0 )
  {
    v15 = 1;
    v13 = 8008;
    if ( (byte_140086202 & 1) != 0 )
      McTemplateK0q_EtwWriteTransfer(BaseAddress, EventProfilerEnter, a3, 8008);
  }
  else
  {
    v15 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v13, 8008);
  if ( v4 )
  {
    if ( Length < 0x80000000 )
    {
      while ( Length )
      {
        v10 = -1;
        if ( Length < 0xFFFFFFFF )
          v10 = Length;
        KeInvalidateRangeAllCaches(v4, v10);
        Length -= v10;
        v4 += v10;
      }
    }
    else
    {
      KeInvalidateAllCaches();
    }
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v13);
    if ( v15 && (byte_140086202 & 1) != 0 )
      McTemplateK0q_EtwWriteTransfer(v11, EventProfilerExit, v12, v13);
    return 0;
  }
  else
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 20287;
    DxgkLogInternalTriageEvent(v5, 0x40000, v6, (unsigned int)L"Allocation virtual address is zero", 20287, 0, 0, 0);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v13);
    if ( v15 )
    {
      if ( (byte_140086202 & 1) != 0 )
        McTemplateK0q_EtwWriteTransfer(v7, EventProfilerExit, v8, v13);
    }
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x1400b1f94  mov     rax, rsp
0x1400b1f97  mov     [rax+18h], rbx
0x1400b1f9b  mov     [rax+20h], rsi
0x1400b1f9f  push    r12
0x1400b1fa1  push    r14
0x1400b1fa3  push    r15
0x1400b1fa5  sub     rsp, 70h
0x1400b1fa9  mov     rsi, rdx
0x1400b1fac  mov     r14, rcx
0x1400b1faf  xor     r15d, r15d
0x1400b1fb2  mov     dword ptr [rax-38h], 0FFFFFFFFh
0x1400b1fb9  mov     [rax-30h], r15
0x1400b1fbd  test    byte ptr cs:qword_140086010, 2
0x1400b1fc4  jz      short loc_1400B1FEE
0x1400b1fc6  mov     byte ptr [rax-28h], 1
0x1400b1fca  mov     dword ptr [rax-38h], 1F48h
0x1400b1fd1  test    cs:byte_140086202, 1
0x1400b1fd8  jz      short loc_1400B1FF3
0x1400b1fda  mov     r9d, 1F48h
0x1400b1fe0  lea     rdx, EventProfilerEnter
0x1400b1fe7  call    McTemplateK0q_EtwWriteTransfer
0x1400b1fec  jmp     short loc_1400B1FF3
0x1400b1fee  mov     [rsp+88h+var_28], r15b
0x1400b1ff3  mov     edx, 1F48h
0x1400b1ff8  lea     rcx, [rsp+88h+var_38]
0x1400b1ffd  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1400b2002  test    r14, r14
0x1400b2005  jnz     short loc_1400B207C
0x1400b2007  lea     ecx, [r14+1]
0x1400b200b  call    cs:__imp_WdLogSingleEntry0
0x1400b2012  nop     dword ptr [rax+rax+00h]
0x1400b2017  mov     eax, 4F3Fh
0x1400b201c  mov     cs:WdLogGlobalForLineNumber, eax
0x1400b2022  mov     [rsp+88h+var_50], r15
0x1400b2027  mov     [rsp+88h+var_58], r15
0x1400b202c  mov     [rsp+88h+var_60], r15
0x1400b2031  mov     [rsp+88h+var_68], rax
0x1400b2036  lea     r9, aAllocationVirt; "Allocation virtual address is zero"
0x1400b203d  mov     edx, 40000h
0x1400b2042  call    DxgkLogInternalTriageEvent
0x1400b2047  lea     rcx, [rsp+88h+var_38]; this
0x1400b204c  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1400b2051  cmp     [rsp+88h+var_28], r15b
0x1400b2056  jz      short loc_1400B2072
0x1400b2058  test    cs:byte_140086202, 1
0x1400b205f  jz      short loc_1400B2072
0x1400b2061  mov     r9d, [rsp+88h+var_38]
0x1400b2066  lea     rdx, EventProfilerExit
0x1400b206d  call    McTemplateK0q_EtwWriteTransfer
0x1400b2072  mov     eax, 0C000000Dh
0x1400b2077  jmp     loc_1400B2159
0x1400b207c  mov     eax, 80000000h
0x1400b2081  cmp     rsi, rax
0x1400b2084  jb      short loc_1400B2094
0x1400b2086  call    cs:__imp_KeInvalidateAllCaches
0x1400b208d  nop     dword ptr [rax+rax+00h]
0x1400b2092  jmp     short loc_1400B20D3
0x1400b2094  mov     r12d, 0FFFFFFFFh
0x1400b209a  test    rsi, rsi
0x1400b209d  jz      short loc_1400B20D3
0x1400b209f  mov     ebx, r12d
0x1400b20a2  cmp     rsi, r12
0x1400b20a5  cmovb   ebx, esi
0x1400b20a8  mov     edx, ebx; Length
0x1400b20aa  mov     rcx, r14; BaseAddress
0x1400b20ad  call    cs:__imp_KeInvalidateRangeAllCaches
0x1400b20b4  nop     dword ptr [rax+rax+00h]
0x1400b20b9  mov     eax, ebx
0x1400b20bb  sub     rsi, rax
0x1400b20be  mov     [rsp+88h+arg_8], rsi
0x1400b20c6  add     r14, rax
0x1400b20c9  mov     [rsp+88h+arg_0], r14
0x1400b20d1  jmp     short loc_1400B209A
0x1400b20d3  jmp     short loc_1400B212B
0x1400b20d5  mov     ecx, 1
0x1400b20da  call    cs:__imp_WdLogSingleEntry0
0x1400b20e1  nop     dword ptr [rax+rax+00h]
0x1400b20e6  mov     cs:WdLogGlobalForLineNumber, 4F61h
0x1400b20f0  mov     [rsp+88h+var_50], 0
0x1400b20f9  mov     [rsp+88h+var_58], 0
0x1400b2102  mov     [rsp+88h+var_60], 0
0x1400b210b  mov     [rsp+88h+var_68], 4F61h
0x1400b2114  lea     r9, aExceptionOccur_2; "Exception occured while trying to flush"...
0x1400b211b  mov     edx, 40000h
0x1400b2120  call    DxgkLogInternalTriageEvent
0x1400b2125  mov     r15d, 0C000000Dh
0x1400b212b  lea     rcx, [rsp+88h+var_38]; this
0x1400b2130  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1400b2135  cmp     [rsp+88h+var_28], 0
0x1400b213a  jz      short loc_1400B2156
0x1400b213c  test    cs:byte_140086202, 1
0x1400b2143  jz      short loc_1400B2156
0x1400b2145  mov     r9d, [rsp+88h+var_38]
0x1400b214a  lea     rdx, EventProfilerExit
0x1400b2151  call    McTemplateK0q_EtwWriteTransfer
0x1400b2156  mov     eax, r15d
0x1400b2159  lea     r11, [rsp+88h+var_18]
0x1400b215e  mov     rbx, [r11+30h]
0x1400b2162  mov     rsi, [r11+38h]
0x1400b2166  mov     rsp, r11
0x1400b2169  pop     r15
0x1400b216b  pop     r14
0x1400b216d  pop     r12
0x1400b216f  retn
```
