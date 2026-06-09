# VidMmFlushCpuCacheWorker

- ea: `0x1400b3544`
- end: `0x1400b3721`
- name: `VidMmFlushCpuCacheWorker`
- size: `477`
- prototype: `__int64 __fastcall(PVOID BaseAddress, ULONG Length)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400b9d90`
- `0x1400be960`

## callees

- `0x140004268`
- `0x1400128c8`
- `0x14002eb80`
- `0x14002f2a8`
- `0x1400b3544`

## import_xrefs

- `ntoskrnl!KeInvalidateAllCaches` at `0x1400b3636`
- `ntoskrnl!KeInvalidateAllCaches` at `0x1400b3636`
- `ntoskrnl!KeInvalidateRangeAllCaches` at `0x1400b365d`
- `ntoskrnl!KeInvalidateRangeAllCaches` at `0x1400b365d`
- `watchdog!WdLogSingleEntry0` at `0x1400b35bb`
- `watchdog!WdLogSingleEntry0` at `0x1400b368a`
- `watchdog!WdLogSingleEntry0` at `0x1400b35bb`
- `watchdog!WdLogSingleEntry0` at `0x1400b368a`

## string_xrefs

- `0x1400b36c4`: `Exception occured while trying to flush allocation from processor cache.\n`

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
  if ( (qword_140087010 & 2) != 0 )
  {
    v15 = 1;
    v13 = 8008;
    if ( (byte_140087202 & 1) != 0 )
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
    if ( v15 && (byte_140087202 & 1) != 0 )
      McTemplateK0q_EtwWriteTransfer(v11, EventProfilerExit, v12, v13);
    return 0;
  }
  else
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 20458;
    DxgkLogInternalTriageEvent(v5, 0x40000, v6, (unsigned int)L"Allocation virtual address is zero", 20458, 0, 0, 0);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v13);
    if ( v15 )
    {
      if ( (byte_140087202 & 1) != 0 )
        McTemplateK0q_EtwWriteTransfer(v7, EventProfilerExit, v8, v13);
    }
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x1400b3544  mov     rax, rsp
0x1400b3547  mov     [rax+18h], rbx
0x1400b354b  mov     [rax+20h], rsi
0x1400b354f  push    r12
0x1400b3551  push    r14
0x1400b3553  push    r15
0x1400b3555  sub     rsp, 70h
0x1400b3559  mov     rsi, rdx
0x1400b355c  mov     r14, rcx
0x1400b355f  xor     r15d, r15d
0x1400b3562  mov     dword ptr [rax-38h], 0FFFFFFFFh
0x1400b3569  mov     [rax-30h], r15
0x1400b356d  test    byte ptr cs:qword_140087010, 2
0x1400b3574  jz      short loc_1400B359E
0x1400b3576  mov     byte ptr [rax-28h], 1
0x1400b357a  mov     dword ptr [rax-38h], 1F48h
0x1400b3581  test    cs:byte_140087202, 1
0x1400b3588  jz      short loc_1400B35A3
0x1400b358a  mov     r9d, 1F48h
0x1400b3590  lea     rdx, EventProfilerEnter
0x1400b3597  call    McTemplateK0q_EtwWriteTransfer
0x1400b359c  jmp     short loc_1400B35A3
0x1400b359e  mov     [rsp+88h+var_28], r15b
0x1400b35a3  mov     edx, 1F48h
0x1400b35a8  lea     rcx, [rsp+88h+var_38]
0x1400b35ad  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1400b35b2  test    r14, r14
0x1400b35b5  jnz     short loc_1400B362C
0x1400b35b7  lea     ecx, [r14+1]
0x1400b35bb  call    cs:__imp_WdLogSingleEntry0
0x1400b35c2  nop     dword ptr [rax+rax+00h]
0x1400b35c7  mov     eax, 4FEAh
0x1400b35cc  mov     cs:WdLogGlobalForLineNumber, eax
0x1400b35d2  mov     [rsp+88h+var_50], r15
0x1400b35d7  mov     [rsp+88h+var_58], r15
0x1400b35dc  mov     [rsp+88h+var_60], r15
0x1400b35e1  mov     [rsp+88h+var_68], rax
0x1400b35e6  lea     r9, aAllocationVirt; "Allocation virtual address is zero"
0x1400b35ed  mov     edx, 40000h
0x1400b35f2  call    DxgkLogInternalTriageEvent
0x1400b35f7  lea     rcx, [rsp+88h+var_38]; this
0x1400b35fc  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1400b3601  cmp     [rsp+88h+var_28], r15b
0x1400b3606  jz      short loc_1400B3622
0x1400b3608  test    cs:byte_140087202, 1
0x1400b360f  jz      short loc_1400B3622
0x1400b3611  mov     r9d, [rsp+88h+var_38]
0x1400b3616  lea     rdx, EventProfilerExit
0x1400b361d  call    McTemplateK0q_EtwWriteTransfer
0x1400b3622  mov     eax, 0C000000Dh
0x1400b3627  jmp     loc_1400B3709
0x1400b362c  mov     eax, 80000000h
0x1400b3631  cmp     rsi, rax
0x1400b3634  jb      short loc_1400B3644
0x1400b3636  call    cs:__imp_KeInvalidateAllCaches
0x1400b363d  nop     dword ptr [rax+rax+00h]
0x1400b3642  jmp     short loc_1400B3683
0x1400b3644  mov     r12d, 0FFFFFFFFh
0x1400b364a  test    rsi, rsi
0x1400b364d  jz      short loc_1400B3683
0x1400b364f  mov     ebx, r12d
0x1400b3652  cmp     rsi, r12
0x1400b3655  cmovb   ebx, esi
0x1400b3658  mov     edx, ebx; Length
0x1400b365a  mov     rcx, r14; BaseAddress
0x1400b365d  call    cs:__imp_KeInvalidateRangeAllCaches
0x1400b3664  nop     dword ptr [rax+rax+00h]
0x1400b3669  mov     eax, ebx
0x1400b366b  sub     rsi, rax
0x1400b366e  mov     [rsp+88h+arg_8], rsi
0x1400b3676  add     r14, rax
0x1400b3679  mov     [rsp+88h+arg_0], r14
0x1400b3681  jmp     short loc_1400B364A
0x1400b3683  jmp     short loc_1400B36DB
0x1400b3685  mov     ecx, 1
0x1400b368a  call    cs:__imp_WdLogSingleEntry0
0x1400b3691  nop     dword ptr [rax+rax+00h]
0x1400b3696  mov     cs:WdLogGlobalForLineNumber, 500Ch
0x1400b36a0  mov     [rsp+88h+var_50], 0
0x1400b36a9  mov     [rsp+88h+var_58], 0
0x1400b36b2  mov     [rsp+88h+var_60], 0
0x1400b36bb  mov     [rsp+88h+var_68], 500Ch
0x1400b36c4  lea     r9, aExceptionOccur_2; "Exception occured while trying to flush"...
0x1400b36cb  mov     edx, 40000h
0x1400b36d0  call    DxgkLogInternalTriageEvent
0x1400b36d5  mov     r15d, 0C000000Dh
0x1400b36db  lea     rcx, [rsp+88h+var_38]; this
0x1400b36e0  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1400b36e5  cmp     [rsp+88h+var_28], 0
0x1400b36ea  jz      short loc_1400B3706
0x1400b36ec  test    cs:byte_140087202, 1
0x1400b36f3  jz      short loc_1400B3706
0x1400b36f5  mov     r9d, [rsp+88h+var_38]
0x1400b36fa  lea     rdx, EventProfilerExit
0x1400b3701  call    McTemplateK0q_EtwWriteTransfer
0x1400b3706  mov     eax, r15d
0x1400b3709  lea     r11, [rsp+88h+var_18]
0x1400b370e  mov     rbx, [r11+30h]
0x1400b3712  mov     rsi, [r11+38h]
0x1400b3716  mov     rsp, r11
0x1400b3719  pop     r15
0x1400b371b  pop     r14
0x1400b371d  pop     r12
0x1400b371f  retn
```
