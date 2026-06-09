# DXGADAPTER::CheckMcdmDdiSubmission(void)

- ea: `0x140077c4c`
- end: `0x140078729`
- name: `?CheckMcdmDdiSubmission@DXGADAPTER@@AEAAJXZ`
- size: `2781`
- prototype: `__int64 __fastcall(DXGADAPTER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1401fa52c`

## callees

- `0x14001b890`
- `0x140033bb0`
- `0x140077c4c`

## import_xrefs

- `watchdog!WdLogSingleEntry0` at `0x140077d4b`
- `watchdog!WdLogSingleEntry0` at `0x140077d9e`
- `watchdog!WdLogSingleEntry0` at `0x140077df4`
- `watchdog!WdLogSingleEntry0` at `0x140077e46`
- `watchdog!WdLogSingleEntry0` at `0x140077e95`
- `watchdog!WdLogSingleEntry0` at `0x140077eea`
- `watchdog!WdLogSingleEntry0` at `0x140077f47`
- `watchdog!WdLogSingleEntry0` at `0x140077f98`
- `watchdog!WdLogSingleEntry0` at `0x140077fe9`
- `watchdog!WdLogSingleEntry0` at `0x14007803a`
- `watchdog!WdLogSingleEntry0` at `0x14007808f`
- `watchdog!WdLogSingleEntry0` at `0x1400780e4`
- `watchdog!WdLogSingleEntry0` at `0x140078132`
- `watchdog!WdLogSingleEntry0` at `0x140078180`
- `watchdog!WdLogSingleEntry0` at `0x1400781ce`
- `watchdog!WdLogSingleEntry0` at `0x14007821c`
- `watchdog!WdLogSingleEntry0` at `0x14007826a`
- `watchdog!WdLogSingleEntry0` at `0x1400782b8`
- `watchdog!WdLogSingleEntry0` at `0x14007830f`
- `watchdog!WdLogSingleEntry0` at `0x140078360`
- `watchdog!WdLogSingleEntry0` at `0x1400783ba`
- `watchdog!WdLogSingleEntry0` at `0x140078408`
- `watchdog!WdLogSingleEntry0` at `0x140078456`
- `watchdog!WdLogSingleEntry0` at `0x1400784a4`
- `watchdog!WdLogSingleEntry0` at `0x1400784f2`
- `watchdog!WdLogSingleEntry0` at `0x140078540`
- `watchdog!WdLogSingleEntry0` at `0x14007858e`
- `watchdog!WdLogSingleEntry0` at `0x1400785dc`
- `watchdog!WdLogSingleEntry0` at `0x14007862a`
- `watchdog!WdLogSingleEntry0` at `0x140078678`
- `watchdog!WdLogSingleEntry0` at `0x1400786c6`
- `watchdog!WdLogSingleEntry0` at `0x140077d4b`
- `watchdog!WdLogSingleEntry0` at `0x140077d9e`
- `watchdog!WdLogSingleEntry0` at `0x140077df4`
- `watchdog!WdLogSingleEntry0` at `0x140077e46`
- `watchdog!WdLogSingleEntry0` at `0x140077e95`
- `watchdog!WdLogSingleEntry0` at `0x140077eea`
- `watchdog!WdLogSingleEntry0` at `0x140077f47`
- `watchdog!WdLogSingleEntry0` at `0x140077f98`
- `watchdog!WdLogSingleEntry0` at `0x140077fe9`
- `watchdog!WdLogSingleEntry0` at `0x14007803a`
- `watchdog!WdLogSingleEntry0` at `0x14007808f`
- `watchdog!WdLogSingleEntry0` at `0x1400780e4`
- `watchdog!WdLogSingleEntry0` at `0x140078132`
- `watchdog!WdLogSingleEntry0` at `0x140078180`
- `watchdog!WdLogSingleEntry0` at `0x1400781ce`
- `watchdog!WdLogSingleEntry0` at `0x14007821c`
- `watchdog!WdLogSingleEntry0` at `0x14007826a`
- `watchdog!WdLogSingleEntry0` at `0x1400782b8`
- `watchdog!WdLogSingleEntry0` at `0x14007830f`
- `watchdog!WdLogSingleEntry0` at `0x140078360`
- `watchdog!WdLogSingleEntry0` at `0x1400783ba`
- `watchdog!WdLogSingleEntry0` at `0x140078408`
- `watchdog!WdLogSingleEntry0` at `0x140078456`
- `watchdog!WdLogSingleEntry0` at `0x1400784a4`
- `watchdog!WdLogSingleEntry0` at `0x1400784f2`
- `watchdog!WdLogSingleEntry0` at `0x140078540`
- `watchdog!WdLogSingleEntry0` at `0x14007858e`
- `watchdog!WdLogSingleEntry0` at `0x1400785dc`
- `watchdog!WdLogSingleEntry0` at `0x14007862a`
- `watchdog!WdLogSingleEntry0` at `0x140078678`
- `watchdog!WdLogSingleEntry0` at `0x1400786c6`

## string_xrefs

- `0x140077e02`: `DxgkDdiSubmitCommand is required.`
- `0x140077ef8`: `DxgkDdiSubmitCommand is not used.`
- `0x140077f58`: `DxgkDdiCreateProcess is required.`
- `0x1400780f5`: `DxgkDdiCreateProcess is not used.`
- `0x1400780a0`: `DxgkDdiSubmitCommandVirtual is required.`
- `0x14007822d`: `DxgkDdiSubmitCommandVirtual is not used.`
- `0x140078371`: `DxgkDdiEndExclusiveAccess is required.`
- `0x140078320`: `DxgkDdiBeginExclusiveAccess is required.`
- `0x1400783cb`: `DxgkDdiCreateHwQueue is not used.`
- `0x140078689`: `DxgkDdiSubmitCommandToHwQueue is not used.`

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

  if ( (*((_DWORD *)this + 772) & 8) == 0 )
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
    v10 = *(_QWORD *)(v7 + 3104);
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
0x140077c4c  push    rbx
0x140077c4e  push    rbp
0x140077c4f  push    rsi
0x140077c50  push    rdi
0x140077c51  push    r12
0x140077c53  push    r13
0x140077c55  push    r14
0x140077c57  push    r15
0x140077c59  sub     rsp, 58h
0x140077c5d  mov     eax, [rcx+0C10h]
0x140077c63  mov     rbx, rcx
0x140077c66  shr     eax, 3
0x140077c69  test    al, 1
0x140077c6b  jz      loc_140078715
0x140077c71  mov     eax, [rcx+1BCh]
0x140077c77  test    al, 8
0x140077c79  jnz     loc_140078715
0x140077c7f  bt      eax, 0Eh
0x140077c83  jb      loc_140078715
0x140077c89  xor     r14d, r14d
0x140077c8c  xor     r10b, r10b
0x140077c8f  xor     r15b, r15b
0x140077c92  xor     r12b, r12b
0x140077c95  xor     r13b, r13b
0x140077c98  call    ?GetNumDifferentPhysicalAdapters@DXGADAPTER@@QEBAIXZ; DXGADAPTER::GetNumDifferentPhysicalAdapters(void)
0x140077c9d  mov     ebp, eax
0x140077c9f  test    eax, eax
0x140077ca1  jz      loc_140077D27
0x140077ca7  mov     rdi, [rcx+0C20h]
0x140077cae  xor     edx, edx
0x140077cb0  lea     r14d, [rdx+1]
0x140077cb4  mov     ecx, edx
0x140077cb6  imul    r11, rcx, 160h
0x140077cbd  mov     r8, [r11+rdi+20h]
0x140077cc2  test    r8, r8
0x140077cc5  jnz     short loc_140077CCC
0x140077cc7  mov     r10b, r14b
0x140077cca  jmp     short loc_140077D1D
0x140077ccc  movzx   esi, word ptr [r11+rdi]
0x140077cd1  test    esi, esi
0x140077cd3  jz      short loc_140077D1D
0x140077cd5  xor     ecx, ecx
0x140077cd7  mov     eax, ecx
0x140077cd9  imul    r9, rax, 4Ah ; 'J'
0x140077cdd  cmp     byte ptr [r9+r8+48h], 0
0x140077ce3  jnz     short loc_140077CFB
0x140077ce5  cmp     byte ptr [r9+r8+49h], 0
0x140077ceb  jnz     short loc_140077CFB
0x140077ced  mov     eax, [r11+rdi+10h]
0x140077cf2  test    al, 0C0h
0x140077cf4  jnz     short loc_140077CFB
0x140077cf6  mov     r10b, r14b
0x140077cf9  jmp     short loc_140077D16
0x140077cfb  test    [r9+r8+44h], r14b
0x140077d00  mov     r15b, r14b
0x140077d03  movzx   r12d, r12b
0x140077d07  cmovnz  r12d, r14d
0x140077d0b  cmp     byte ptr [r9+r8+49h], 0
0x140077d11  jz      short loc_140077D16
0x140077d13  mov     r13b, r14b
0x140077d16  add     ecx, r14d
0x140077d19  cmp     ecx, esi
0x140077d1b  jb      short loc_140077CD7
0x140077d1d  add     edx, r14d
0x140077d20  cmp     edx, ebp
0x140077d22  jb      short loc_140077CB4
0x140077d24  xor     r14d, r14d
0x140077d27  mov     rax, [rbx+208h]
0x140077d2e  or      esi, 0FFFFFFFFh
0x140077d31  mov     edi, 2
0x140077d36  mov     ebp, 40000h
0x140077d3b  test    r10b, r10b
0x140077d3e  jz      loc_140077E3F
0x140077d44  test    rax, rax
0x140077d47  jnz     short loc_140077D92
0x140077d49  mov     ecx, edi
0x140077d4b  call    cs:__imp_WdLogSingleEntry0
0x140077d52  nop     dword ptr [rax+rax+00h]
0x140077d57  xor     ecx, ecx
0x140077d59  lea     r9, aDxgkddipatchIs_0; "DxgkDdiPatch is required."
0x140077d60  mov     [rsp+98h+var_58], rcx
0x140077d65  mov     eax, 10Dh
0x140077d6a  mov     [rsp+98h+var_60], rcx
0x140077d6f  mov     r8d, esi
0x140077d72  mov     [rsp+98h+var_68], rcx
0x140077d77  mov     edx, ebp
0x140077d79  mov     [rsp+98h+var_70], rcx
0x140077d7e  mov     [rsp+98h+var_78], rax
0x140077d83  mov     cs:WdLogGlobalForLineNumber, eax
0x140077d89  call    DxgkLogInternalTriageEvent
0x140077d8e  lea     r14d, [rdi-1]
0x140077d92  cmp     qword ptr [rbx+2E0h], 0
0x140077d9a  jnz     short loc_140077DE4
0x140077d9c  mov     ecx, edi
0x140077d9e  call    cs:__imp_WdLogSingleEntry0
0x140077da5  nop     dword ptr [rax+rax+00h]
0x140077daa  xor     ecx, ecx
0x140077dac  lea     r9, aDxgkddirenderI; "DxgkDdiRender is required."
0x140077db3  mov     [rsp+98h+var_58], rcx
0x140077db8  mov     eax, 10Eh
0x140077dbd  mov     [rsp+98h+var_60], rcx
0x140077dc2  mov     r8d, esi
0x140077dc5  mov     [rsp+98h+var_68], rcx
0x140077dca  mov     edx, ebp
0x140077dcc  mov     [rsp+98h+var_70], rcx
0x140077dd1  mov     [rsp+98h+var_78], rax
0x140077dd6  mov     cs:WdLogGlobalForLineNumber, eax
0x140077ddc  call    DxgkLogInternalTriageEvent
0x140077de1  inc     r14d
0x140077de4  cmp     qword ptr [rbx+210h], 0
0x140077dec  jnz     loc_140077F2D
0x140077df2  mov     ecx, edi
0x140077df4  call    cs:__imp_WdLogSingleEntry0
0x140077dfb  nop     dword ptr [rax+rax+00h]
0x140077e00  xor     ecx, ecx
0x140077e02  lea     r9, aDxgkddisubmitc_0; "DxgkDdiSubmitCommand is required."
0x140077e09  mov     [rsp+98h+var_58], rcx
0x140077e0e  mov     eax, 10Fh
0x140077e13  mov     [rsp+98h+var_60], rcx
0x140077e18  mov     r8d, esi
0x140077e1b  mov     [rsp+98h+var_68], rcx
0x140077e20  mov     edx, ebp
0x140077e22  mov     [rsp+98h+var_70], rcx
0x140077e27  mov     [rsp+98h+var_78], rax
0x140077e2c  mov     cs:WdLogGlobalForLineNumber, eax
0x140077e32  call    DxgkLogInternalTriageEvent
0x140077e37  inc     r14d
0x140077e3a  jmp     loc_140077F2D
0x140077e3f  test    rax, rax
0x140077e42  jz      short loc_140077E89
0x140077e44  mov     ecx, edi
0x140077e46  call    cs:__imp_WdLogSingleEntry0
0x140077e4d  nop     dword ptr [rax+rax+00h]
0x140077e52  xor     ecx, ecx
0x140077e54  lea     r9, aDxgkddipatchIs; "DxgkDdiPatch is not used."
0x140077e5b  mov     [rsp+98h+var_58], rcx
0x140077e60  mov     eax, 113h
0x140077e65  mov     [rsp+98h+var_60], rcx
0x140077e6a  mov     r8d, esi
0x140077e6d  mov     [rsp+98h+var_68], rcx
0x140077e72  mov     edx, ebp
0x140077e74  mov     [rsp+98h+var_70], rcx
0x140077e79  mov     [rsp+98h+var_78], rax
0x140077e7e  mov     cs:WdLogGlobalForLineNumber, eax
0x140077e84  call    DxgkLogInternalTriageEvent
0x140077e89  cmp     qword ptr [rbx+2E0h], 0
0x140077e91  jz      short loc_140077ED8
0x140077e93  mov     ecx, edi
0x140077e95  call    cs:__imp_WdLogSingleEntry0
0x140077e9c  nop     dword ptr [rax+rax+00h]
0x140077ea1  xor     ecx, ecx
0x140077ea3  lea     r9, aDxgkddirenderI_0; "DxgkDdiRender is not used."
0x140077eaa  mov     [rsp+98h+var_58], rcx
0x140077eaf  mov     eax, 114h
0x140077eb4  mov     [rsp+98h+var_60], rcx
0x140077eb9  mov     r8d, esi
0x140077ebc  mov     [rsp+98h+var_68], rcx
0x140077ec1  mov     edx, ebp
0x140077ec3  mov     [rsp+98h+var_70], rcx
0x140077ec8  mov     [rsp+98h+var_78], rax
0x140077ecd  mov     cs:WdLogGlobalForLineNumber, eax
0x140077ed3  call    DxgkLogInternalTriageEvent
0x140077ed8  lea     rax, ?DefaultDdiSubmitCommand@DXGADAPTER@@CAJQEAXPEBU_DXGKARG_SUBMITCOMMAND@@@Z; DXGADAPTER::DefaultDdiSubmitCommand(void * const,_DXGKARG_SUBMITCOMMAND const *)
0x140077edf  cmp     [rbx+210h], rax
0x140077ee6  jz      short loc_140077F2D
0x140077ee8  mov     ecx, edi
0x140077eea  call    cs:__imp_WdLogSingleEntry0
0x140077ef1  nop     dword ptr [rax+rax+00h]
0x140077ef6  xor     ecx, ecx
0x140077ef8  lea     r9, aDxgkddisubmitc_2; "DxgkDdiSubmitCommand is not used."
0x140077eff  mov     [rsp+98h+var_58], rcx
0x140077f04  mov     eax, 115h
0x140077f09  mov     [rsp+98h+var_60], rcx
0x140077f0e  mov     r8d, esi
0x140077f11  mov     [rsp+98h+var_68], rcx
0x140077f16  mov     edx, ebp
0x140077f18  mov     [rsp+98h+var_70], rcx
0x140077f1d  mov     [rsp+98h+var_78], rax
0x140077f22  mov     cs:WdLogGlobalForLineNumber, eax
0x140077f28  call    DxgkLogInternalTriageEvent
0x140077f2d  mov     rax, [rbx+3D0h]
0x140077f34  test    r15b, r15b
0x140077f37  jz      loc_1400780DA
0x140077f3d  xor     r15d, r15d
0x140077f40  test    rax, rax
0x140077f43  jnz     short loc_140077F8D
0x140077f45  mov     ecx, edi
0x140077f47  call    cs:__imp_WdLogSingleEntry0
0x140077f4e  nop     dword ptr [rax+rax+00h]
0x140077f53  mov     [rsp+98h+var_58], r15
0x140077f58  lea     r9, aDxgkddicreatep_1; "DxgkDdiCreateProcess is required."
0x140077f5f  mov     [rsp+98h+var_60], r15
0x140077f64  mov     eax, 11Ah
0x140077f69  mov     [rsp+98h+var_68], r15
0x140077f6e  mov     r8d, esi
0x140077f71  mov     [rsp+98h+var_70], r15
0x140077f76  mov     edx, ebp
0x140077f78  xor     ecx, ecx
0x140077f7a  mov     [rsp+98h+var_78], rax
0x140077f7f  mov     cs:WdLogGlobalForLineNumber, eax
0x140077f85  call    DxgkLogInternalTriageEvent
0x140077f8a  inc     r14d
0x140077f8d  cmp     [rbx+3D8h], r15
0x140077f94  jnz     short loc_140077FDE
0x140077f96  mov     ecx, edi
0x140077f98  call    cs:__imp_WdLogSingleEntry0
0x140077f9f  nop     dword ptr [rax+rax+00h]
0x140077fa4  mov     [rsp+98h+var_58], r15
0x140077fa9  lea     r9, aDxgkddidestroy_1; "DxgkDdiDestroyProcess is required."
0x140077fb0  mov     [rsp+98h+var_60], r15
0x140077fb5  mov     eax, 11Bh
0x140077fba  mov     [rsp+98h+var_68], r15
0x140077fbf  mov     r8d, esi
0x140077fc2  mov     [rsp+98h+var_70], r15
0x140077fc7  mov     edx, ebp
0x140077fc9  xor     ecx, ecx
0x140077fcb  mov     [rsp+98h+var_78], rax
0x140077fd0  mov     cs:WdLogGlobalForLineNumber, eax
0x140077fd6  call    DxgkLogInternalTriageEvent
0x140077fdb  inc     r14d
0x140077fde  cmp     [rbx+3B8h], r15
0x140077fe5  jnz     short loc_14007802F
0x140077fe7  mov     ecx, edi
0x140077fe9  call    cs:__imp_WdLogSingleEntry0
0x140077ff0  nop     dword ptr [rax+rax+00h]
0x140077ff5  mov     [rsp+98h+var_58], r15
0x140077ffa  lea     r9, aDxgkddigetroot; "DxgkDdiGetRootPageTableSize is required"...
0x140078001  mov     [rsp+98h+var_60], r15
0x140078006  mov     eax, 11Ch
0x14007800b  mov     [rsp+98h+var_68], r15
0x140078010  mov     r8d, esi
0x140078013  mov     [rsp+98h+var_70], r15
0x140078018  mov     edx, ebp
0x14007801a  xor     ecx, ecx
0x14007801c  mov     [rsp+98h+var_78], rax
0x140078021  mov     cs:WdLogGlobalForLineNumber, eax
0x140078027  call    DxgkLogInternalTriageEvent
0x14007802c  inc     r14d
0x14007802f  cmp     [rbx+3B0h], r15
0x140078036  jnz     short loc_140078080
0x140078038  mov     ecx, edi
0x14007803a  call    cs:__imp_WdLogSingleEntry0
0x140078041  nop     dword ptr [rax+rax+00h]
0x140078046  mov     [rsp+98h+var_58], r15
0x14007804b  lea     r9, aDxgkddisetroot; "DxgkDdiSetRootPageTable is required."
0x140078052  mov     [rsp+98h+var_60], r15
0x140078057  mov     eax, 11Dh
0x14007805c  mov     [rsp+98h+var_68], r15
0x140078061  mov     r8d, esi
0x140078064  mov     [rsp+98h+var_70], r15
0x140078069  mov     edx, ebp
0x14007806b  xor     ecx, ecx
0x14007806d  mov     [rsp+98h+var_78], rax
0x140078072  mov     cs:WdLogGlobalForLineNumber, eax
0x140078078  call    DxgkLogInternalTriageEvent
0x14007807d  inc     r14d
0x140078080  cmp     [rbx+3A8h], r15
0x140078087  jnz     loc_1400782FB
0x14007808d  mov     ecx, edi
0x14007808f  call    cs:__imp_WdLogSingleEntry0
0x140078096  nop     dword ptr [rax+rax+00h]
0x14007809b  mov     [rsp+98h+var_58], r15
0x1400780a0  lea     r9, aDxgkddisubmitc; "DxgkDdiSubmitCommandVirtual is required"...
0x1400780a7  mov     [rsp+98h+var_60], r15
0x1400780ac  mov     eax, 11Eh
0x1400780b1  mov     [rsp+98h+var_68], r15
0x1400780b6  mov     r8d, esi
0x1400780b9  mov     [rsp+98h+var_70], r15
0x1400780be  mov     edx, ebp
0x1400780c0  xor     ecx, ecx
0x1400780c2  mov     [rsp+98h+var_78], rax
0x1400780c7  mov     cs:WdLogGlobalForLineNumber, eax
0x1400780cd  call    DxgkLogInternalTriageEvent
0x1400780d2  inc     r14d
0x1400780d5  jmp     loc_1400782FB
0x1400780da  xor     r15d, r15d
0x1400780dd  test    rax, rax
0x1400780e0  jz      short loc_140078127
0x1400780e2  mov     ecx, edi
0x1400780e4  call    cs:__imp_WdLogSingleEntry0
0x1400780eb  nop     dword ptr [rax+rax+00h]
0x1400780f0  mov     [rsp+98h+var_58], r15
0x1400780f5  lea     r9, aDxgkddicreatep; "DxgkDdiCreateProcess is not used."
0x1400780fc  mov     [rsp+98h+var_60], r15
0x140078101  mov     eax, 124h
0x140078106  mov     [rsp+98h+var_68], r15
0x14007810b  mov     r8d, esi
0x14007810e  mov     [rsp+98h+var_70], r15
0x140078113  mov     edx, ebp
0x140078115  xor     ecx, ecx
0x140078117  mov     [rsp+98h+var_78], rax
0x14007811c  mov     cs:WdLogGlobalForLineNumber, eax
0x140078122  call    DxgkLogInternalTriageEvent
0x140078127  cmp     [rbx+3D8h], r15
0x14007812e  jz      short loc_140078175
0x140078130  mov     ecx, edi
0x140078132  call    cs:__imp_WdLogSingleEntry0
0x140078139  nop     dword ptr [rax+rax+00h]
0x14007813e  mov     [rsp+98h+var_58], r15
0x140078143  lea     r9, aDxgkddidestroy_2; "DxgkDdiDestroyProcess is not used."
  ... truncated ...
```
