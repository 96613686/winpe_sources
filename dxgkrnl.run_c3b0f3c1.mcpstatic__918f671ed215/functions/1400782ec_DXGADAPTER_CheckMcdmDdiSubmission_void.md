# DXGADAPTER::CheckMcdmDdiSubmission(void)

- ea: `0x1400782ec`
- end: `0x140078dc9`
- name: `?CheckMcdmDdiSubmission@DXGADAPTER@@AEAAJXZ`
- size: `2781`
- prototype: `__int64 __fastcall(DXGADAPTER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1401fc90c`

## callees

- `0x14001b9c0`
- `0x140033d80`
- `0x1400782ec`

## import_xrefs

- `watchdog!WdLogSingleEntry0` at `0x1400783eb`
- `watchdog!WdLogSingleEntry0` at `0x14007843e`
- `watchdog!WdLogSingleEntry0` at `0x140078494`
- `watchdog!WdLogSingleEntry0` at `0x1400784e6`
- `watchdog!WdLogSingleEntry0` at `0x140078535`
- `watchdog!WdLogSingleEntry0` at `0x14007858a`
- `watchdog!WdLogSingleEntry0` at `0x1400785e7`
- `watchdog!WdLogSingleEntry0` at `0x140078638`
- `watchdog!WdLogSingleEntry0` at `0x140078689`
- `watchdog!WdLogSingleEntry0` at `0x1400786da`
- `watchdog!WdLogSingleEntry0` at `0x14007872f`
- `watchdog!WdLogSingleEntry0` at `0x140078784`
- `watchdog!WdLogSingleEntry0` at `0x1400787d2`
- `watchdog!WdLogSingleEntry0` at `0x140078820`
- `watchdog!WdLogSingleEntry0` at `0x14007886e`
- `watchdog!WdLogSingleEntry0` at `0x1400788bc`
- `watchdog!WdLogSingleEntry0` at `0x14007890a`
- `watchdog!WdLogSingleEntry0` at `0x140078958`
- `watchdog!WdLogSingleEntry0` at `0x1400789af`
- `watchdog!WdLogSingleEntry0` at `0x140078a00`
- `watchdog!WdLogSingleEntry0` at `0x140078a5a`
- `watchdog!WdLogSingleEntry0` at `0x140078aa8`
- `watchdog!WdLogSingleEntry0` at `0x140078af6`
- `watchdog!WdLogSingleEntry0` at `0x140078b44`
- `watchdog!WdLogSingleEntry0` at `0x140078b92`
- `watchdog!WdLogSingleEntry0` at `0x140078be0`
- `watchdog!WdLogSingleEntry0` at `0x140078c2e`
- `watchdog!WdLogSingleEntry0` at `0x140078c7c`
- `watchdog!WdLogSingleEntry0` at `0x140078cca`
- `watchdog!WdLogSingleEntry0` at `0x140078d18`
- `watchdog!WdLogSingleEntry0` at `0x140078d66`
- `watchdog!WdLogSingleEntry0` at `0x1400783eb`
- `watchdog!WdLogSingleEntry0` at `0x14007843e`
- `watchdog!WdLogSingleEntry0` at `0x140078494`
- `watchdog!WdLogSingleEntry0` at `0x1400784e6`
- `watchdog!WdLogSingleEntry0` at `0x140078535`
- `watchdog!WdLogSingleEntry0` at `0x14007858a`
- `watchdog!WdLogSingleEntry0` at `0x1400785e7`
- `watchdog!WdLogSingleEntry0` at `0x140078638`
- `watchdog!WdLogSingleEntry0` at `0x140078689`
- `watchdog!WdLogSingleEntry0` at `0x1400786da`
- `watchdog!WdLogSingleEntry0` at `0x14007872f`
- `watchdog!WdLogSingleEntry0` at `0x140078784`
- `watchdog!WdLogSingleEntry0` at `0x1400787d2`
- `watchdog!WdLogSingleEntry0` at `0x140078820`
- `watchdog!WdLogSingleEntry0` at `0x14007886e`
- `watchdog!WdLogSingleEntry0` at `0x1400788bc`
- `watchdog!WdLogSingleEntry0` at `0x14007890a`
- `watchdog!WdLogSingleEntry0` at `0x140078958`
- `watchdog!WdLogSingleEntry0` at `0x1400789af`
- `watchdog!WdLogSingleEntry0` at `0x140078a00`
- `watchdog!WdLogSingleEntry0` at `0x140078a5a`
- `watchdog!WdLogSingleEntry0` at `0x140078aa8`
- `watchdog!WdLogSingleEntry0` at `0x140078af6`
- `watchdog!WdLogSingleEntry0` at `0x140078b44`
- `watchdog!WdLogSingleEntry0` at `0x140078b92`
- `watchdog!WdLogSingleEntry0` at `0x140078be0`
- `watchdog!WdLogSingleEntry0` at `0x140078c2e`
- `watchdog!WdLogSingleEntry0` at `0x140078c7c`
- `watchdog!WdLogSingleEntry0` at `0x140078cca`
- `watchdog!WdLogSingleEntry0` at `0x140078d18`
- `watchdog!WdLogSingleEntry0` at `0x140078d66`

## string_xrefs

- `0x1400784a2`: `DxgkDdiSubmitCommand is required.`
- `0x1400785f8`: `DxgkDdiCreateProcess is required.`
- `0x140078598`: `DxgkDdiSubmitCommand is not used.`
- `0x140078740`: `DxgkDdiSubmitCommandVirtual is required.`
- `0x140078795`: `DxgkDdiCreateProcess is not used.`
- `0x1400788cd`: `DxgkDdiSubmitCommandVirtual is not used.`
- `0x1400789c0`: `DxgkDdiBeginExclusiveAccess is required.`
- `0x140078a6b`: `DxgkDdiCreateHwQueue is not used.`
- `0x140078a11`: `DxgkDdiEndExclusiveAccess is required.`
- `0x140078d29`: `DxgkDdiSubmitCommandToHwQueue is not used.`

## pseudocode

```c
__int64 __fastcall DXGADAPTER::CheckMcdmDdiSubmission(DXGADAPTER *this)
{
  int v2; // eax
  int v3; // r14d
  char v4; // r15
  char v5; // r12
  char v6; // r13
  __int64 v7; // rcx
  unsigned int NumDifferentPhysicalAdapters; // ebp
  char v9; // r10
  __int64 v10; // rdi
  unsigned int i; // edx
  __int64 v12; // r11
  __int64 v13; // r8
  unsigned int v14; // ecx
  __int64 v15; // r9
  __int64 v16; // rax
  __int64 v17; // rax

  if ( (*((_DWORD *)this + 776) & 8) == 0 )
    return 0;
  v2 = *((_DWORD *)this + 111);
  if ( (v2 & 8) != 0 || (v2 & 0x4000) != 0 )
    return 0;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  NumDifferentPhysicalAdapters = DXGADAPTER::GetNumDifferentPhysicalAdapters(this);
  if ( NumDifferentPhysicalAdapters )
  {
    v10 = *(_QWORD *)(v7 + 3120);
    for ( i = 0; i < NumDifferentPhysicalAdapters; ++i )
    {
      v12 = 352LL * i;
      v13 = *(_QWORD *)(v12 + v10 + 32);
      if ( v13 )
      {
        if ( *(_WORD *)(v12 + v10) )
        {
          v14 = 0;
          do
          {
            v15 = 74LL * v14;
            if ( *(_BYTE *)(v15 + v13 + 72) || *(_BYTE *)(v15 + v13 + 73) || (*(_DWORD *)(v12 + v10 + 16) & 0xC0) != 0 )
            {
              v4 = 1;
              if ( (*(_BYTE *)(v15 + v13 + 68) & 1) != 0 )
                v5 = 1;
              if ( *(_BYTE *)(v15 + v13 + 73) )
                v6 = 1;
            }
            else
            {
              v9 = 1;
            }
            ++v14;
          }
          while ( v14 < *(unsigned __int16 *)(v12 + v10) );
        }
      }
      else
      {
        v9 = 1;
      }
    }
    v3 = 0;
  }
  v16 = *((_QWORD *)this + 65);
  if ( v9 )
  {
    if ( !v16 )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 269;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"DxgkDdiPatch is required.", 269, 0, 0, 0, 0);
      v3 = 1;
    }
    if ( !*((_QWORD *)this + 92) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 270;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"DxgkDdiRender is required.", 270, 0, 0, 0, 0);
      ++v3;
    }
    if ( !*((_QWORD *)this + 66) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 271;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"DxgkDdiSubmitCommand is required.", 271, 0, 0, 0, 0);
      ++v3;
    }
  }
  else
  {
    if ( v16 )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 275;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"DxgkDdiPatch is not used.", 275, 0, 0, 0, 0);
    }
    if ( *((_QWORD *)this + 92) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 276;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"DxgkDdiRender is not used.", 276, 0, 0, 0, 0);
    }
    if ( *((__int64 (__fastcall **)(void *const, const struct _DXGKARG_SUBMITCOMMAND *))this + 66) != DXGADAPTER::DefaultDdiSubmitCommand )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 277;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"DxgkDdiSubmitCommand is not used.", 277, 0, 0, 0, 0);
    }
  }
  v17 = *((_QWORD *)this + 122);
  if ( v4 )
  {
    if ( !v17 )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 282;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"DxgkDdiCreateProcess is required.", 282, 0, 0, 0, 0);
      ++v3;
    }
    if ( !*((_QWORD *)this + 123) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 283;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"DxgkDdiDestroyProcess is required.", 283, 0, 0, 0, 0);
      ++v3;
    }
    if ( !*((_QWORD *)this + 119) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 284;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"DxgkDdiGetRootPageTableSize is required.",
        284,
        0,
        0,
        0,
        0);
      ++v3;
    }
    if ( !*((_QWORD *)this + 118) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 285;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"DxgkDdiSetRootPageTable is required.", 285, 0, 0, 0, 0);
      ++v3;
    }
    if ( !*((_QWORD *)this + 117) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 286;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"DxgkDdiSubmitCommandVirtual is required.",
        286,
        0,
        0,
        0,
        0);
      ++v3;
    }
  }
  else
  {
    if ( v17 )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 292;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"DxgkDdiCreateProcess is not used.", 292, 0, 0, 0, 0);
    }
    if ( *((_QWORD *)this + 123) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 293;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"DxgkDdiDestroyProcess is not used.", 293, 0, 0, 0, 0);
    }
    if ( *((_QWORD *)this + 119) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 294;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"DxgkDdiGetRootPageTableSize is not used.",
        294,
        0,
        0,
        0,
        0);
    }
    if ( *((_QWORD *)this + 118) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 295;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"DxgkDdiSetRootPageTable is not used.", 295, 0, 0, 0, 0);
    }
    if ( *((_QWORD *)this + 117) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 296;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"DxgkDdiSubmitCommandVirtual is not used.",
        296,
        0,
        0,
        0,
        0);
    }
    if ( *((_QWORD *)this + 120) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 297;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"DxgkDdiMapCpuHostAperture is not used.",
        297,
        0,
        0,
        0,
        0);
    }
    if ( *((_QWORD *)this + 121) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 298;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"DxgkDdiUnmapCpuHostAperture is not used.",
        298,
        0,
        0,
        0,
        0);
    }
  }
  if ( v6 )
  {
    if ( !*((_QWORD *)this + 164) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 303;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"DxgkDdiBeginExclusiveAccess is required.",
        303,
        0,
        0,
        0,
        0);
      ++v3;
    }
    if ( !*((_QWORD *)this + 165) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 304;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"DxgkDdiEndExclusiveAccess is required.",
        304,
        0,
        0,
        0,
        0);
      ++v3;
    }
  }
  if ( !v5 )
  {
    if ( *((_QWORD *)this + 138) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 309;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"DxgkDdiCreateHwQueue is not used.", 309, 0, 0, 0, 0);
    }
    if ( *((_QWORD *)this + 139) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 310;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"DxgkDdiDestroyHwQueue is not used.", 310, 0, 0, 0, 0);
    }
    if ( *((_QWORD *)this + 141) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 311;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"DxgkDdiResetHwEngine is not used.", 311, 0, 0, 0, 0);
    }
    if ( *((_QWORD *)this + 162) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 312;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"DxgkDdiResumeContext is not used.", 312, 0, 0, 0, 0);
    }
    if ( *((_QWORD *)this + 142) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 313;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"DxgkDdiResumeHwEngine is not used.", 313, 0, 0, 0, 0);
    }
    if ( *((_QWORD *)this + 160) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 314;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"DxgkDdiSetContextSchedulingProperties is not used.",
        314,
        0,
        0,
        0,
        0);
    }
    if ( *((_QWORD *)this + 157) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 315;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"DxgkDdiSetSchedulingLogBuffer is not used.",
        315,
        0,
        0,
        0,
        0);
    }
    if ( *((_QWORD *)this + 158) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 316;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"DxgkDdiSetupPriorityBands is not used.",
        316,
        0,
        0,
        0,
        0);
    }
    if ( *((_QWORD *)this + 168) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 317;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"DxgkDdiSignalMonitoredFence is not used.",
        317,
        0,
        0,
        0,
        0);
    }
    if ( *((_QWORD *)this + 140) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 318;
      DxgkLogInternalTriageEvent(
        0,
        0x40000,
        -1,
        (unsigned int)L"DxgkDdiSubmitCommandToHwQueue is not used.",
        318,
        0,
        0,
        0,
        0);
    }
    if ( *((_QWORD *)this + 161) )
    {
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 319;
      DxgkLogInternalTriageEvent(0, 0x40000, -1, (unsigned int)L"DxgkDdiSuspendContext is not used.", 319, 0, 0, 0, 0);
    }
  }
  if ( !v3 )
    return 0;
  else
    return 3221225561LL;
}

```

## disassembly

```asm
0x1400782ec  push    rbx
0x1400782ee  push    rbp
0x1400782ef  push    rsi
0x1400782f0  push    rdi
0x1400782f1  push    r12
0x1400782f3  push    r13
0x1400782f5  push    r14
0x1400782f7  push    r15
0x1400782f9  sub     rsp, 58h
0x1400782fd  mov     eax, [rcx+0C20h]
0x140078303  mov     rbx, rcx
0x140078306  shr     eax, 3
0x140078309  test    al, 1
0x14007830b  jz      loc_140078DB5
0x140078311  mov     eax, [rcx+1BCh]
0x140078317  test    al, 8
0x140078319  jnz     loc_140078DB5
0x14007831f  bt      eax, 0Eh
0x140078323  jb      loc_140078DB5
0x140078329  xor     r14d, r14d
0x14007832c  xor     r10b, r10b
0x14007832f  xor     r15b, r15b
0x140078332  xor     r12b, r12b
0x140078335  xor     r13b, r13b
0x140078338  call    ?GetNumDifferentPhysicalAdapters@DXGADAPTER@@QEBAIXZ; DXGADAPTER::GetNumDifferentPhysicalAdapters(void)
0x14007833d  mov     ebp, eax
0x14007833f  test    eax, eax
0x140078341  jz      loc_1400783C7
0x140078347  mov     rdi, [rcx+0C30h]
0x14007834e  xor     edx, edx
0x140078350  lea     r14d, [rdx+1]
0x140078354  mov     ecx, edx
0x140078356  imul    r11, rcx, 160h
0x14007835d  mov     r8, [r11+rdi+20h]
0x140078362  test    r8, r8
0x140078365  jnz     short loc_14007836C
0x140078367  mov     r10b, r14b
0x14007836a  jmp     short loc_1400783BD
0x14007836c  movzx   esi, word ptr [r11+rdi]
0x140078371  test    esi, esi
0x140078373  jz      short loc_1400783BD
0x140078375  xor     ecx, ecx
0x140078377  mov     eax, ecx
0x140078379  imul    r9, rax, 4Ah ; 'J'
0x14007837d  cmp     byte ptr [r9+r8+48h], 0
0x140078383  jnz     short loc_14007839B
0x140078385  cmp     byte ptr [r9+r8+49h], 0
0x14007838b  jnz     short loc_14007839B
0x14007838d  mov     eax, [r11+rdi+10h]
0x140078392  test    al, 0C0h
0x140078394  jnz     short loc_14007839B
0x140078396  mov     r10b, r14b
0x140078399  jmp     short loc_1400783B6
0x14007839b  test    [r9+r8+44h], r14b
0x1400783a0  mov     r15b, r14b
0x1400783a3  movzx   r12d, r12b
0x1400783a7  cmovnz  r12d, r14d
0x1400783ab  cmp     byte ptr [r9+r8+49h], 0
0x1400783b1  jz      short loc_1400783B6
0x1400783b3  mov     r13b, r14b
0x1400783b6  add     ecx, r14d
0x1400783b9  cmp     ecx, esi
0x1400783bb  jb      short loc_140078377
0x1400783bd  add     edx, r14d
0x1400783c0  cmp     edx, ebp
0x1400783c2  jb      short loc_140078354
0x1400783c4  xor     r14d, r14d
0x1400783c7  mov     rax, [rbx+208h]
0x1400783ce  or      esi, 0FFFFFFFFh
0x1400783d1  mov     edi, 2
0x1400783d6  mov     ebp, 40000h
0x1400783db  test    r10b, r10b
0x1400783de  jz      loc_1400784DF
0x1400783e4  test    rax, rax
0x1400783e7  jnz     short loc_140078432
0x1400783e9  mov     ecx, edi
0x1400783eb  call    cs:__imp_WdLogSingleEntry0
0x1400783f2  nop     dword ptr [rax+rax+00h]
0x1400783f7  xor     ecx, ecx
0x1400783f9  lea     r9, aDxgkddipatchIs_0; "DxgkDdiPatch is required."
0x140078400  mov     [rsp+98h+var_58], rcx
0x140078405  mov     eax, 10Dh
0x14007840a  mov     [rsp+98h+var_60], rcx
0x14007840f  mov     r8d, esi
0x140078412  mov     [rsp+98h+var_68], rcx
0x140078417  mov     edx, ebp
0x140078419  mov     [rsp+98h+var_70], rcx
0x14007841e  mov     [rsp+98h+var_78], rax
0x140078423  mov     cs:WdLogGlobalForLineNumber, eax
0x140078429  call    DxgkLogInternalTriageEvent
0x14007842e  lea     r14d, [rdi-1]
0x140078432  cmp     qword ptr [rbx+2E0h], 0
0x14007843a  jnz     short loc_140078484
0x14007843c  mov     ecx, edi
0x14007843e  call    cs:__imp_WdLogSingleEntry0
0x140078445  nop     dword ptr [rax+rax+00h]
0x14007844a  xor     ecx, ecx
0x14007844c  lea     r9, aDxgkddirenderI; "DxgkDdiRender is required."
0x140078453  mov     [rsp+98h+var_58], rcx
0x140078458  mov     eax, 10Eh
0x14007845d  mov     [rsp+98h+var_60], rcx
0x140078462  mov     r8d, esi
0x140078465  mov     [rsp+98h+var_68], rcx
0x14007846a  mov     edx, ebp
0x14007846c  mov     [rsp+98h+var_70], rcx
0x140078471  mov     [rsp+98h+var_78], rax
0x140078476  mov     cs:WdLogGlobalForLineNumber, eax
0x14007847c  call    DxgkLogInternalTriageEvent
0x140078481  inc     r14d
0x140078484  cmp     qword ptr [rbx+210h], 0
0x14007848c  jnz     loc_1400785CD
0x140078492  mov     ecx, edi
0x140078494  call    cs:__imp_WdLogSingleEntry0
0x14007849b  nop     dword ptr [rax+rax+00h]
0x1400784a0  xor     ecx, ecx
0x1400784a2  lea     r9, aDxgkddisubmitc_0; "DxgkDdiSubmitCommand is required."
0x1400784a9  mov     [rsp+98h+var_58], rcx
0x1400784ae  mov     eax, 10Fh
0x1400784b3  mov     [rsp+98h+var_60], rcx
0x1400784b8  mov     r8d, esi
0x1400784bb  mov     [rsp+98h+var_68], rcx
0x1400784c0  mov     edx, ebp
0x1400784c2  mov     [rsp+98h+var_70], rcx
0x1400784c7  mov     [rsp+98h+var_78], rax
0x1400784cc  mov     cs:WdLogGlobalForLineNumber, eax
0x1400784d2  call    DxgkLogInternalTriageEvent
0x1400784d7  inc     r14d
0x1400784da  jmp     loc_1400785CD
0x1400784df  test    rax, rax
0x1400784e2  jz      short loc_140078529
0x1400784e4  mov     ecx, edi
0x1400784e6  call    cs:__imp_WdLogSingleEntry0
0x1400784ed  nop     dword ptr [rax+rax+00h]
0x1400784f2  xor     ecx, ecx
0x1400784f4  lea     r9, aDxgkddipatchIs; "DxgkDdiPatch is not used."
0x1400784fb  mov     [rsp+98h+var_58], rcx
0x140078500  mov     eax, 113h
0x140078505  mov     [rsp+98h+var_60], rcx
0x14007850a  mov     r8d, esi
0x14007850d  mov     [rsp+98h+var_68], rcx
0x140078512  mov     edx, ebp
0x140078514  mov     [rsp+98h+var_70], rcx
0x140078519  mov     [rsp+98h+var_78], rax
0x14007851e  mov     cs:WdLogGlobalForLineNumber, eax
0x140078524  call    DxgkLogInternalTriageEvent
0x140078529  cmp     qword ptr [rbx+2E0h], 0
0x140078531  jz      short loc_140078578
0x140078533  mov     ecx, edi
0x140078535  call    cs:__imp_WdLogSingleEntry0
0x14007853c  nop     dword ptr [rax+rax+00h]
0x140078541  xor     ecx, ecx
0x140078543  lea     r9, aDxgkddirenderI_0; "DxgkDdiRender is not used."
0x14007854a  mov     [rsp+98h+var_58], rcx
0x14007854f  mov     eax, 114h
0x140078554  mov     [rsp+98h+var_60], rcx
0x140078559  mov     r8d, esi
0x14007855c  mov     [rsp+98h+var_68], rcx
0x140078561  mov     edx, ebp
0x140078563  mov     [rsp+98h+var_70], rcx
0x140078568  mov     [rsp+98h+var_78], rax
0x14007856d  mov     cs:WdLogGlobalForLineNumber, eax
0x140078573  call    DxgkLogInternalTriageEvent
0x140078578  lea     rax, ?DefaultDdiSubmitCommand@DXGADAPTER@@CAJQEAXPEBU_DXGKARG_SUBMITCOMMAND@@@Z; DXGADAPTER::DefaultDdiSubmitCommand(void * const,_DXGKARG_SUBMITCOMMAND const *)
0x14007857f  cmp     [rbx+210h], rax
0x140078586  jz      short loc_1400785CD
0x140078588  mov     ecx, edi
0x14007858a  call    cs:__imp_WdLogSingleEntry0
0x140078591  nop     dword ptr [rax+rax+00h]
0x140078596  xor     ecx, ecx
0x140078598  lea     r9, aDxgkddisubmitc_2; "DxgkDdiSubmitCommand is not used."
0x14007859f  mov     [rsp+98h+var_58], rcx
0x1400785a4  mov     eax, 115h
0x1400785a9  mov     [rsp+98h+var_60], rcx
0x1400785ae  mov     r8d, esi
0x1400785b1  mov     [rsp+98h+var_68], rcx
0x1400785b6  mov     edx, ebp
0x1400785b8  mov     [rsp+98h+var_70], rcx
0x1400785bd  mov     [rsp+98h+var_78], rax
0x1400785c2  mov     cs:WdLogGlobalForLineNumber, eax
0x1400785c8  call    DxgkLogInternalTriageEvent
0x1400785cd  mov     rax, [rbx+3D0h]
0x1400785d4  test    r15b, r15b
0x1400785d7  jz      loc_14007877A
0x1400785dd  xor     r15d, r15d
0x1400785e0  test    rax, rax
0x1400785e3  jnz     short loc_14007862D
0x1400785e5  mov     ecx, edi
0x1400785e7  call    cs:__imp_WdLogSingleEntry0
0x1400785ee  nop     dword ptr [rax+rax+00h]
0x1400785f3  mov     [rsp+98h+var_58], r15
0x1400785f8  lea     r9, aDxgkddicreatep_1; "DxgkDdiCreateProcess is required."
0x1400785ff  mov     [rsp+98h+var_60], r15
0x140078604  mov     eax, 11Ah
0x140078609  mov     [rsp+98h+var_68], r15
0x14007860e  mov     r8d, esi
0x140078611  mov     [rsp+98h+var_70], r15
0x140078616  mov     edx, ebp
0x140078618  xor     ecx, ecx
0x14007861a  mov     [rsp+98h+var_78], rax
0x14007861f  mov     cs:WdLogGlobalForLineNumber, eax
0x140078625  call    DxgkLogInternalTriageEvent
0x14007862a  inc     r14d
0x14007862d  cmp     [rbx+3D8h], r15
0x140078634  jnz     short loc_14007867E
0x140078636  mov     ecx, edi
0x140078638  call    cs:__imp_WdLogSingleEntry0
0x14007863f  nop     dword ptr [rax+rax+00h]
0x140078644  mov     [rsp+98h+var_58], r15
0x140078649  lea     r9, aDxgkddidestroy_1; "DxgkDdiDestroyProcess is required."
0x140078650  mov     [rsp+98h+var_60], r15
0x140078655  mov     eax, 11Bh
0x14007865a  mov     [rsp+98h+var_68], r15
0x14007865f  mov     r8d, esi
0x140078662  mov     [rsp+98h+var_70], r15
0x140078667  mov     edx, ebp
0x140078669  xor     ecx, ecx
0x14007866b  mov     [rsp+98h+var_78], rax
0x140078670  mov     cs:WdLogGlobalForLineNumber, eax
0x140078676  call    DxgkLogInternalTriageEvent
0x14007867b  inc     r14d
0x14007867e  cmp     [rbx+3B8h], r15
0x140078685  jnz     short loc_1400786CF
0x140078687  mov     ecx, edi
0x140078689  call    cs:__imp_WdLogSingleEntry0
0x140078690  nop     dword ptr [rax+rax+00h]
0x140078695  mov     [rsp+98h+var_58], r15
0x14007869a  lea     r9, aDxgkddigetroot; "DxgkDdiGetRootPageTableSize is required"...
0x1400786a1  mov     [rsp+98h+var_60], r15
0x1400786a6  mov     eax, 11Ch
0x1400786ab  mov     [rsp+98h+var_68], r15
0x1400786b0  mov     r8d, esi
0x1400786b3  mov     [rsp+98h+var_70], r15
0x1400786b8  mov     edx, ebp
0x1400786ba  xor     ecx, ecx
0x1400786bc  mov     [rsp+98h+var_78], rax
0x1400786c1  mov     cs:WdLogGlobalForLineNumber, eax
0x1400786c7  call    DxgkLogInternalTriageEvent
0x1400786cc  inc     r14d
0x1400786cf  cmp     [rbx+3B0h], r15
0x1400786d6  jnz     short loc_140078720
0x1400786d8  mov     ecx, edi
0x1400786da  call    cs:__imp_WdLogSingleEntry0
0x1400786e1  nop     dword ptr [rax+rax+00h]
0x1400786e6  mov     [rsp+98h+var_58], r15
0x1400786eb  lea     r9, aDxgkddisetroot; "DxgkDdiSetRootPageTable is required."
0x1400786f2  mov     [rsp+98h+var_60], r15
0x1400786f7  mov     eax, 11Dh
0x1400786fc  mov     [rsp+98h+var_68], r15
0x140078701  mov     r8d, esi
0x140078704  mov     [rsp+98h+var_70], r15
0x140078709  mov     edx, ebp
0x14007870b  xor     ecx, ecx
0x14007870d  mov     [rsp+98h+var_78], rax
0x140078712  mov     cs:WdLogGlobalForLineNumber, eax
0x140078718  call    DxgkLogInternalTriageEvent
0x14007871d  inc     r14d
0x140078720  cmp     [rbx+3A8h], r15
0x140078727  jnz     loc_14007899B
0x14007872d  mov     ecx, edi
0x14007872f  call    cs:__imp_WdLogSingleEntry0
0x140078736  nop     dword ptr [rax+rax+00h]
0x14007873b  mov     [rsp+98h+var_58], r15
0x140078740  lea     r9, aDxgkddisubmitc; "DxgkDdiSubmitCommandVirtual is required"...
0x140078747  mov     [rsp+98h+var_60], r15
0x14007874c  mov     eax, 11Eh
0x140078751  mov     [rsp+98h+var_68], r15
0x140078756  mov     r8d, esi
0x140078759  mov     [rsp+98h+var_70], r15
0x14007875e  mov     edx, ebp
0x140078760  xor     ecx, ecx
0x140078762  mov     [rsp+98h+var_78], rax
0x140078767  mov     cs:WdLogGlobalForLineNumber, eax
0x14007876d  call    DxgkLogInternalTriageEvent
0x140078772  inc     r14d
0x140078775  jmp     loc_14007899B
0x14007877a  xor     r15d, r15d
0x14007877d  test    rax, rax
0x140078780  jz      short loc_1400787C7
0x140078782  mov     ecx, edi
0x140078784  call    cs:__imp_WdLogSingleEntry0
0x14007878b  nop     dword ptr [rax+rax+00h]
0x140078790  mov     [rsp+98h+var_58], r15
0x140078795  lea     r9, aDxgkddicreatep; "DxgkDdiCreateProcess is not used."
0x14007879c  mov     [rsp+98h+var_60], r15
0x1400787a1  mov     eax, 124h
0x1400787a6  mov     [rsp+98h+var_68], r15
0x1400787ab  mov     r8d, esi
0x1400787ae  mov     [rsp+98h+var_70], r15
0x1400787b3  mov     edx, ebp
0x1400787b5  xor     ecx, ecx
0x1400787b7  mov     [rsp+98h+var_78], rax
0x1400787bc  mov     cs:WdLogGlobalForLineNumber, eax
0x1400787c2  call    DxgkLogInternalTriageEvent
0x1400787c7  cmp     [rbx+3D8h], r15
0x1400787ce  jz      short loc_140078815
0x1400787d0  mov     ecx, edi
0x1400787d2  call    cs:__imp_WdLogSingleEntry0
0x1400787d9  nop     dword ptr [rax+rax+00h]
0x1400787de  mov     [rsp+98h+var_58], r15
0x1400787e3  lea     r9, aDxgkddidestroy_2; "DxgkDdiDestroyProcess is not used."
  ... truncated ...
```
