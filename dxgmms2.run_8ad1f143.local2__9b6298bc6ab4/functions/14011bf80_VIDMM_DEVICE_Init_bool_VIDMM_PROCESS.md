# VIDMM_DEVICE::Init(bool,VIDMM_PROCESS *)

- ea: `0x14011bf80`
- end: `0x14011c4f9`
- name: `?Init@VIDMM_DEVICE@@QEAAJ_NPEAVVIDMM_PROCESS@@@Z`
- size: `1401`
- prototype: `int(VIDMM_DEVICE *__hidden this, bool, struct VIDMM_PROCESS *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x14003afa0`
- `0x1400ed184`

## callees

- `0x1400037a0`
- `0x1400045ec`
- `0x14002f510`
- `0x1400304b0`
- `0x140031178`
- `0x140035b70`
- `0x1400fa2ac`
- `0x14011bf80`
- `0x14011c500`
- `0x14011f830`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x14011c45b`
- `watchdog!WdLogSingleEntry2` at `0x14011c499`
- `watchdog!WdLogSingleEntry2` at `0x14011c45b`
- `watchdog!WdLogSingleEntry2` at `0x14011c499`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14011bfa6`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14011bfa6`
- `watchdog!WdLogSingleEntry0` at `0x14011c014`
- `watchdog!WdLogSingleEntry0` at `0x14011c082`
- `watchdog!WdLogSingleEntry0` at `0x14011c138`
- `watchdog!WdLogSingleEntry0` at `0x14011c1fb`
- `watchdog!WdLogSingleEntry0` at `0x14011c24b`
- `watchdog!WdLogSingleEntry0` at `0x14011c2cd`
- `watchdog!WdLogSingleEntry0` at `0x14011c33d`
- `watchdog!WdLogSingleEntry0` at `0x14011c3ad`
- `watchdog!WdLogSingleEntry0` at `0x14011c014`
- `watchdog!WdLogSingleEntry0` at `0x14011c082`
- `watchdog!WdLogSingleEntry0` at `0x14011c138`
- `watchdog!WdLogSingleEntry0` at `0x14011c1fb`
- `watchdog!WdLogSingleEntry0` at `0x14011c24b`
- `watchdog!WdLogSingleEntry0` at `0x14011c2cd`
- `watchdog!WdLogSingleEntry0` at `0x14011c33d`
- `watchdog!WdLogSingleEntry0` at `0x14011c3ad`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x14011bf91`

## string_xrefs

- `0x14011c025`: `Trying to open device on a non DX process.`
- `0x14011c093`: `Adapter couldn't be opened for the current process.`

## pseudocode

```c
__int64 __fastcall VIDMM_DEVICE::Init(VIDMM_DEVICE *this, __int64 a2, struct VIDMM_PROCESS *a3)
{
  __int64 v5; // rax
  _QWORD *v6; // rsi
  struct VIDMM_PROCESS *v7; // r8
  __int64 v8; // r8
  int v9; // ecx
  int v10; // r8d
  __int64 result; // rax
  int v12; // ebp
  int v13; // ecx
  int v14; // r8d
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  int v18; // ecx
  int v19; // r8d
  __int64 v20; // rax
  const wchar_t *v21; // r9
  int v22; // edx
  unsigned int i; // ebp
  _QWORD *v24; // rax
  _QWORD *v25; // r8
  __int64 v26; // r9
  VIDMM_PHYSICAL_DEVICE *v27; // rcx
  int v28; // r15d
  int v29; // ecx
  int v30; // r8d
  unsigned __int64 v31; // rbp
  __int64 v32; // rax
  void *v33; // rax
  void *v34; // rsi
  unsigned int v35; // ebp
  __int64 v36; // rax
  void *v37; // rax
  void *v38; // rsi
  unsigned int v39; // ebp
  __int64 v40; // rax
  void *v41; // rax
  void *v42; // rsi
  unsigned int j; // esi
  __int64 v44; // r14
  __int64 v45; // rax
  int v46; // ecx
  int v47; // r8d
  int v48; // ecx
  int v49; // r8d
  __int64 v50; // rbx
  int v51; // [rsp+20h] [rbp-78h]
  int v52; // [rsp+20h] [rbp-78h]

  if ( g_IsInternalReleaseOrDbg )
  {
    v5 = WdLogNewEntry5_WdTrace(this, a2);
    *(_QWORD *)(v5 + 24) = this;
    *(_QWORD *)(v5 + 32) = *(_QWORD *)this;
    WdLogGlobalForLineNumber = 423;
  }
  v6 = (_QWORD *)((char *)this + 24);
  if ( a3 )
  {
    v7 = a3;
  }
  else if ( *v6 )
  {
    if ( DXGPROCESS::GetCurrent() && (v8 = *((_QWORD *)DXGPROCESS::GetCurrent() + 8)) != 0 )
      v7 = *(struct VIDMM_PROCESS **)(v8 + 8);
    else
      v7 = 0;
  }
  else
  {
    v7 = *(struct VIDMM_PROCESS **)(*(_QWORD *)this + 36672LL);
  }
  *((_QWORD *)this + 1) = v7;
  if ( !v7 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 432;
    DxgkLogInternalTriageEvent(
      v9,
      0x40000,
      v10,
      (unsigned int)L"Trying to open device on a non DX process.",
      432,
      0,
      0,
      0);
    return 3221225473LL;
  }
  if ( *v6 )
  {
    v12 = VIDMM_PROCESS::OpenAdapter(v7, *(struct VIDMM_GLOBAL **)this);
    if ( v12 < 0 )
    {
      _InterlockedAdd(&dword_1400866C8, 1u);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 448;
      DxgkLogInternalTriageEvent(
        v13,
        262145,
        v14,
        (unsigned int)L"Adapter couldn't be opened for the current process.",
        448,
        0,
        0,
        0);
      return (unsigned int)v12;
    }
    *((_BYTE *)this + 58) |= 1u;
    v15 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 32LL)
                    + 8LL * *(unsigned int *)(*(_QWORD *)(*(_QWORD *)this + 24LL) + 240LL));
  }
  else
  {
    v15 = *(_QWORD *)(*((_QWORD *)v7 + 4) + 8LL * *(unsigned int *)(*(_QWORD *)(*(_QWORD *)this + 24LL) + 240LL));
  }
  *((_QWORD *)this + 2) = v15;
  v16 = 8LL * *((unsigned int *)this + 15);
  if ( !is_mul_ok(*((unsigned int *)this + 15), 8u) )
    v16 = -1;
  v17 = operator new[](v16, 1630824790, 256);
  *((_QWORD *)this + 5) = v17;
  if ( v17 )
  {
    for ( i = 0; i < *((_DWORD *)this + 15); ++i )
    {
      v24 = (_QWORD *)operator new(24, 1647602006, 256);
      v25 = v24;
      v26 = 8LL * i;
      if ( v24 )
      {
        *v24 = *(_QWORD *)(v26 + *(_QWORD *)(*(_QWORD *)this + 36480LL));
        v24[1] = this;
        v24[2] = 0;
      }
      else
      {
        v25 = 0;
      }
      *(_QWORD *)(v26 + *((_QWORD *)this + 5)) = v25;
      v27 = *(VIDMM_PHYSICAL_DEVICE **)(v26 + *((_QWORD *)this + 5));
      if ( !v27 )
      {
        _InterlockedAdd(&dword_140086870, 1u);
        WdLogSingleEntry0(6);
        v20 = 475;
        v21 = L"Couldn't allocate memory for VIDMM_PHYSICAL_DEVICE.";
        goto LABEL_22;
      }
      v28 = VIDMM_PHYSICAL_DEVICE::Initialize(v27);
      if ( v28 < 0 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 482;
        DxgkLogInternalTriageEvent(
          v29,
          0x40000,
          v30,
          (unsigned int)L"Failed to initialize VIDMM_PHYSICAL_DEVICE",
          482,
          0,
          0,
          0);
        return (unsigned int)v28;
      }
    }
    if ( *v6 || !a3 )
    {
      v31 = *((unsigned int *)this + 15);
      v32 = 32 * v31;
      if ( !is_mul_ok(v31, 0x20u) )
        v32 = -1;
      v33 = (void *)operator new[](v32, 942958934, 256);
      v34 = v33;
      if ( v33 )
        `vector constructor iterator'(
          v33,
          0x20u,
          v31,
          (void *(*)(void *))VIDMM_DEVICE_PAGING_QUEUE::VIDMM_DEVICE_PAGING_QUEUE);
      else
        v34 = 0;
      *((_QWORD *)this + 9) = v34;
      if ( !v34 )
      {
        WdLogSingleEntry0(1);
        v20 = 499;
LABEL_44:
        v21 = L"Failed to allocate memory for VIDMM_DEVICE_PAGING_QUEUE";
        v22 = 0x40000;
        goto LABEL_23;
      }
      v35 = *((_DWORD *)this + 15);
      v36 = 32LL * v35;
      if ( !is_mul_ok(v35, 0x20u) )
        v36 = -1;
      v37 = (void *)operator new[](v36, 942958934, 256);
      v38 = v37;
      if ( v37 )
        `vector constructor iterator'(
          v37,
          0x20u,
          v35,
          (void *(*)(void *))VIDMM_DEVICE_PAGING_QUEUE::VIDMM_DEVICE_PAGING_QUEUE);
      else
        v38 = 0;
      *((_QWORD *)this + 10) = v38;
      if ( !v38 )
      {
        WdLogSingleEntry0(1);
        v20 = 506;
        goto LABEL_44;
      }
      if ( (*(_DWORD *)(*((_QWORD *)this + 1) + 136LL) & 2) != 0 )
      {
        v39 = *((_DWORD *)this + 15);
        v40 = 32LL * v39;
        if ( !is_mul_ok(v39, 0x20u) )
          v40 = -1;
        v41 = (void *)operator new[](v40, 942958934, 256);
        v42 = v41;
        if ( v41 )
          `vector constructor iterator'(
            v41,
            0x20u,
            v39,
            (void *(*)(void *))VIDMM_DEVICE_PAGING_QUEUE::VIDMM_DEVICE_PAGING_QUEUE);
        else
          v42 = 0;
        *((_QWORD *)this + 11) = v42;
        if ( !v42 )
        {
          WdLogSingleEntry0(1);
          v20 = 522;
          goto LABEL_44;
        }
      }
      for ( j = 0; j < *((_DWORD *)this + 15); ++j )
      {
        v44 = 32LL * j;
        LOBYTE(v51) = 0;
        v28 = VIDMM_DEVICE_PAGING_QUEUE::Initialize(v44 + *((_QWORD *)this + 9), this, j, 1, v51);
        if ( v28 < 0 )
        {
          WdLogSingleEntry2(1, this, j);
          WdLogGlobalForLineNumber = 532;
          DxgkLogInternalTriageEvent(
            v48,
            0x40000,
            v49,
            (unsigned int)L"Failed to initialize _pDevicePagingQueue: %p %I64d",
            (__int64)this,
            j,
            0,
            0);
          return (unsigned int)v28;
        }
        LOBYTE(v52) = 0;
        v28 = VIDMM_DEVICE_PAGING_QUEUE::Initialize(v44 + *((_QWORD *)this + 10), this, j, 2, v52);
        if ( v28 < 0 )
        {
          WdLogSingleEntry2(1, this, j);
          WdLogGlobalForLineNumber = 539;
          DxgkLogInternalTriageEvent(
            v46,
            0x40000,
            v47,
            (unsigned int)L"Failed to initialize _pEvictPagingQueue: %p %I64d",
            (__int64)this,
            j,
            0,
            0);
          return (unsigned int)v28;
        }
        v45 = *((_QWORD *)this + 11);
        if ( v45 )
        {
          LOBYTE(v51) = 0;
          result = VIDMM_DEVICE_PAGING_QUEUE::Initialize(v44 + v45, this, j, 3, v51);
          if ( (int)result < 0 )
            return result;
        }
      }
    }
    v50 = qword_140086580;
    *((_QWORD *)this + 28) = v50 + VidMmiQuerySystemTime();
    return 0;
  }
  _InterlockedAdd(&dword_14008686C, 1u);
  WdLogSingleEntry0(6);
  v20 = 465;
  v21 = L"Couldn't allocate memory for VIDMM_PHYSICAL_DEVICE[] array.";
LABEL_22:
  v22 = 262145;
LABEL_23:
  WdLogGlobalForLineNumber = v20;
  DxgkLogInternalTriageEvent(v18, v22, v19, (_DWORD)v21, v20, 0, 0, 0);
  return 3221225495LL;
}

```

## disassembly

```asm
0x14011bf80  push    rbx
0x14011bf82  push    rbp
0x14011bf83  push    rsi
0x14011bf84  push    rdi
0x14011bf85  push    r12
0x14011bf87  push    r13
0x14011bf89  push    r14
0x14011bf8b  push    r15
0x14011bf8d  sub     rsp, 58h
0x14011bf91  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x14011bf98  xor     r12d, r12d
0x14011bf9b  mov     r14, r8
0x14011bf9e  mov     rdi, rcx
0x14011bfa1  cmp     [rax], r12b
0x14011bfa4  jz      short loc_14011BFC7
0x14011bfa6  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14011bfad  nop     dword ptr [rax+rax+00h]
0x14011bfb2  mov     [rax+18h], rdi
0x14011bfb6  mov     rdx, [rdi]
0x14011bfb9  mov     [rax+20h], rdx
0x14011bfbd  mov     cs:WdLogGlobalForLineNumber, 1A7h
0x14011bfc7  lea     rsi, [rdi+18h]
0x14011bfcb  test    r14, r14
0x14011bfce  jz      short loc_14011BFD5
0x14011bfd0  mov     r8, r14
0x14011bfd3  jmp     short loc_14011C007
0x14011bfd5  cmp     [rsi], r12
0x14011bfd8  jz      short loc_14011BFFD
0x14011bfda  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14011bfdf  test    rax, rax
0x14011bfe2  jz      short loc_14011BFF8
0x14011bfe4  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14011bfe9  mov     r8, [rax+40h]
0x14011bfed  test    r8, r8
0x14011bff0  jz      short loc_14011BFF8
0x14011bff2  mov     r8, [r8+8]
0x14011bff6  jmp     short loc_14011C007
0x14011bff8  mov     r8, r12
0x14011bffb  jmp     short loc_14011C007
0x14011bffd  mov     rax, [rdi]
0x14011c000  mov     r8, [rax+8F40h]
0x14011c007  mov     [rdi+8], r8
0x14011c00b  test    r8, r8
0x14011c00e  jnz     short loc_14011C05A
0x14011c010  lea     ecx, [r8+1]
0x14011c014  call    cs:__imp_WdLogSingleEntry0
0x14011c01b  nop     dword ptr [rax+rax+00h]
0x14011c020  mov     [rsp+98h+var_60], r12
0x14011c025  lea     r9, aTryingToOpenDe; "Trying to open device on a non DX proce"...
0x14011c02c  mov     eax, 1B0h
0x14011c031  mov     [rsp+98h+var_68], r12
0x14011c036  mov     [rsp+98h+var_70], r12
0x14011c03b  mov     edx, 40000h
0x14011c040  mov     cs:WdLogGlobalForLineNumber, eax
0x14011c046  mov     [rsp+98h+var_78], rax
0x14011c04b  call    DxgkLogInternalTriageEvent
0x14011c050  mov     eax, 0C0000001h
0x14011c055  jmp     loc_14011C4E7
0x14011c05a  mov     ebx, 1
0x14011c05f  mov     rax, [rdi]
0x14011c062  cmp     [rsi], r12
0x14011c065  jz      short loc_14011C0E3
0x14011c067  mov     rdx, rax; struct VIDMM_GLOBAL *
0x14011c06a  mov     rcx, r8; this
0x14011c06d  call    ?OpenAdapter@VIDMM_PROCESS@@QEAAJPEAVVIDMM_GLOBAL@@@Z; VIDMM_PROCESS::OpenAdapter(VIDMM_GLOBAL *)
0x14011c072  mov     ebp, eax
0x14011c074  test    eax, eax
0x14011c076  jns     short loc_14011C0C5
0x14011c078  lock add cs:dword_1400866C8, ebx
0x14011c07f  lea     ecx, [rbx+5]
0x14011c082  call    cs:__imp_WdLogSingleEntry0
0x14011c089  nop     dword ptr [rax+rax+00h]
0x14011c08e  mov     [rsp+98h+var_60], r12
0x14011c093  lea     r9, aAdapterCouldnT; "Adapter couldn't be opened for the curr"...
0x14011c09a  mov     eax, 1C0h
0x14011c09f  mov     [rsp+98h+var_68], r12
0x14011c0a4  mov     [rsp+98h+var_70], r12
0x14011c0a9  mov     edx, 40001h
0x14011c0ae  mov     cs:WdLogGlobalForLineNumber, eax
0x14011c0b4  mov     [rsp+98h+var_78], rax
0x14011c0b9  call    DxgkLogInternalTriageEvent
0x14011c0be  mov     eax, ebp
0x14011c0c0  jmp     loc_14011C4E7
0x14011c0c5  or      [rdi+3Ah], bl
0x14011c0c8  mov     rax, [rdi]
0x14011c0cb  mov     rcx, [rax+18h]
0x14011c0cf  mov     rax, [rdi+8]
0x14011c0d3  mov     edx, [rcx+0F0h]
0x14011c0d9  mov     rcx, [rax+20h]
0x14011c0dd  mov     rax, [rcx+rdx*8]
0x14011c0e1  jmp     short loc_14011C0F5
0x14011c0e3  mov     rax, [rax+18h]
0x14011c0e7  mov     ecx, [rax+0F0h]
0x14011c0ed  mov     rax, [r8+20h]
0x14011c0f1  mov     rax, [rax+rcx*8]
0x14011c0f5  mov     [rdi+10h], rax
0x14011c0f9  mov     r13, 0FFFFFFFFFFFFFFFFh
0x14011c100  mov     ecx, [rdi+3Ch]
0x14011c103  mov     eax, 8
0x14011c108  mul     rcx
0x14011c10b  mov     r15d, 100h
0x14011c111  mov     edx, 61346956h
0x14011c116  mov     r8d, r15d
0x14011c119  cmovb   rax, r13
0x14011c11d  mov     rcx, rax
0x14011c120  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14011c125  mov     [rdi+28h], rax
0x14011c129  test    rax, rax
0x14011c12c  jnz     short loc_14011C17E
0x14011c12e  lock add cs:dword_14008686C, ebx
0x14011c135  lea     ecx, [rax+6]
0x14011c138  call    cs:__imp_WdLogSingleEntry0
0x14011c13f  nop     dword ptr [rax+rax+00h]
0x14011c144  mov     eax, 1D1h
0x14011c149  lea     r9, aCouldnTAllocat_42; "Couldn't allocate memory for VIDMM_PHYS"...
0x14011c150  mov     edx, 40001h
0x14011c155  mov     [rsp+98h+var_60], r12
0x14011c15a  mov     [rsp+98h+var_68], r12
0x14011c15f  mov     [rsp+98h+var_70], r12
0x14011c164  mov     [rsp+98h+var_78], rax
0x14011c169  mov     cs:WdLogGlobalForLineNumber, eax
0x14011c16f  call    DxgkLogInternalTriageEvent
0x14011c174  mov     eax, 0C0000017h
0x14011c179  jmp     loc_14011C4E7
0x14011c17e  mov     ebp, r12d
0x14011c181  mov     eax, [rdi+3Ch]
0x14011c184  cmp     ebp, eax
0x14011c186  jnb     loc_14011C268
0x14011c18c  mov     r8, r15
0x14011c18f  mov     edx, 62346956h
0x14011c194  mov     ecx, 18h
0x14011c199  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14011c19e  mov     ecx, ebp
0x14011c1a0  mov     r8, rax
0x14011c1a3  lea     r9, ds:0[rcx*8]
0x14011c1ab  test    rax, rax
0x14011c1ae  jz      short loc_14011C1CB
0x14011c1b0  mov     rcx, [rdi]
0x14011c1b3  mov     rdx, [rcx+8E80h]
0x14011c1ba  mov     rcx, [r9+rdx]
0x14011c1be  mov     [rax], rcx
0x14011c1c1  mov     [rax+8], rdi
0x14011c1c5  mov     [rax+10h], r12
0x14011c1c9  jmp     short loc_14011C1CE
0x14011c1cb  mov     r8, r12
0x14011c1ce  mov     rax, [rdi+28h]
0x14011c1d2  mov     [r9+rax], r8
0x14011c1d6  mov     rax, [rdi+28h]
0x14011c1da  mov     rcx, [r9+rax]; this
0x14011c1de  test    rcx, rcx
0x14011c1e1  jz      short loc_14011C23F
0x14011c1e3  call    ?Initialize@VIDMM_PHYSICAL_DEVICE@@QEAAJXZ; VIDMM_PHYSICAL_DEVICE::Initialize(void)
0x14011c1e8  mov     r15d, eax
0x14011c1eb  test    eax, eax
0x14011c1ed  js      short loc_14011C1F9
0x14011c1ef  add     ebp, ebx
0x14011c1f1  mov     r15d, 100h
0x14011c1f7  jmp     short loc_14011C181
0x14011c1f9  mov     ecx, ebx
0x14011c1fb  call    cs:__imp_WdLogSingleEntry0
0x14011c202  nop     dword ptr [rax+rax+00h]
0x14011c207  mov     [rsp+98h+var_60], r12
0x14011c20c  lea     r9, aFailedToInitia_5; "Failed to initialize VIDMM_PHYSICAL_DEV"...
0x14011c213  mov     eax, 1E2h
0x14011c218  mov     [rsp+98h+var_68], r12
0x14011c21d  mov     [rsp+98h+var_70], r12
0x14011c222  mov     cs:WdLogGlobalForLineNumber, eax
0x14011c228  mov     [rsp+98h+var_78], rax
0x14011c22d  mov     edx, 40000h
0x14011c232  call    DxgkLogInternalTriageEvent
0x14011c237  mov     eax, r15d
0x14011c23a  jmp     loc_14011C4E7
0x14011c23f  lock add cs:dword_140086870, ebx
0x14011c246  mov     ecx, 6
0x14011c24b  call    cs:__imp_WdLogSingleEntry0
0x14011c252  nop     dword ptr [rax+rax+00h]
0x14011c257  mov     eax, 1DBh
0x14011c25c  lea     r9, aCouldnTAllocat_47; "Couldn't allocate memory for VIDMM_PHYS"...
0x14011c263  jmp     loc_14011C150
0x14011c268  cmp     [rsi], r12
0x14011c26b  jnz     short loc_14011C276
0x14011c26d  test    r14, r14
0x14011c270  jnz     loc_14011C4CF
0x14011c276  mov     rbp, rax
0x14011c279  mov     r14d, 20h ; ' '
0x14011c27f  mov     eax, r14d
0x14011c282  mov     r8, r15
0x14011c285  mul     rbp
0x14011c288  cmovb   rax, r13
0x14011c28c  mov     r13d, 38346956h
0x14011c292  mov     edx, r13d
0x14011c295  mov     rcx, rax
0x14011c298  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14011c29d  lea     r15, ??0VIDMM_DEVICE_PAGING_QUEUE@@QEAA@XZ; VIDMM_DEVICE_PAGING_QUEUE::VIDMM_DEVICE_PAGING_QUEUE(void)
0x14011c2a4  mov     rsi, rax
0x14011c2a7  test    rax, rax
0x14011c2aa  jz      short loc_14011C2BF
0x14011c2ac  mov     r9, r15; void *(*)(void *)
0x14011c2af  mov     r8, rbp; unsigned __int64
0x14011c2b2  mov     edx, r14d; unsigned __int64
0x14011c2b5  mov     rcx, rax; void *
0x14011c2b8  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x14011c2bd  jmp     short loc_14011C2C2
0x14011c2bf  mov     rsi, r12
0x14011c2c2  mov     [rdi+48h], rsi
0x14011c2c6  test    rsi, rsi
0x14011c2c9  jnz     short loc_14011C2EF
0x14011c2cb  mov     ecx, ebx
0x14011c2cd  call    cs:__imp_WdLogSingleEntry0
0x14011c2d4  nop     dword ptr [rax+rax+00h]
0x14011c2d9  mov     eax, 1F3h
0x14011c2de  lea     r9, aFailedToAlloca_10; "Failed to allocate memory for VIDMM_DEV"...
0x14011c2e5  mov     edx, 40000h
0x14011c2ea  jmp     loc_14011C155
0x14011c2ef  mov     ebp, [rdi+3Ch]
0x14011c2f2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14011c2f9  mov     rax, r14
0x14011c2fc  mov     r8d, 100h
0x14011c302  mul     rbp
0x14011c305  mov     edx, r13d
0x14011c308  cmovb   rax, rcx
0x14011c30c  mov     rcx, rax
0x14011c30f  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14011c314  mov     rsi, rax
0x14011c317  test    rax, rax
0x14011c31a  jz      short loc_14011C32F
0x14011c31c  mov     r9, r15; void *(*)(void *)
0x14011c31f  mov     r8d, ebp; unsigned __int64
0x14011c322  mov     rdx, r14; unsigned __int64
0x14011c325  mov     rcx, rax; void *
0x14011c328  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x14011c32d  jmp     short loc_14011C332
0x14011c32f  mov     rsi, r12
0x14011c332  mov     [rdi+50h], rsi
0x14011c336  test    rsi, rsi
0x14011c339  jnz     short loc_14011C350
0x14011c33b  mov     ecx, ebx
0x14011c33d  call    cs:__imp_WdLogSingleEntry0
0x14011c344  nop     dword ptr [rax+rax+00h]
0x14011c349  mov     eax, 1FAh
0x14011c34e  jmp     short loc_14011C2DE
0x14011c350  mov     rax, [rdi+8]
0x14011c354  mov     ecx, [rax+88h]
0x14011c35a  test    cl, 2
0x14011c35d  jz      short loc_14011C3C3
0x14011c35f  mov     ebp, [rdi+3Ch]
0x14011c362  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14011c369  mov     rax, r14
0x14011c36c  mov     r8d, 100h
0x14011c372  mul     rbp
0x14011c375  mov     edx, r13d
0x14011c378  cmovb   rax, rcx
0x14011c37c  mov     rcx, rax
0x14011c37f  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14011c384  mov     rsi, rax
0x14011c387  test    rax, rax
0x14011c38a  jz      short loc_14011C39F
0x14011c38c  mov     r9, r15; void *(*)(void *)
0x14011c38f  mov     r8d, ebp; unsigned __int64
0x14011c392  mov     rdx, r14; unsigned __int64
0x14011c395  mov     rcx, rax; void *
0x14011c398  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x14011c39d  jmp     short loc_14011C3A2
0x14011c39f  mov     rsi, r12
0x14011c3a2  mov     [rdi+58h], rsi
0x14011c3a6  test    rsi, rsi
0x14011c3a9  jnz     short loc_14011C3C3
0x14011c3ab  mov     ecx, ebx
0x14011c3ad  call    cs:__imp_WdLogSingleEntry0
0x14011c3b4  nop     dword ptr [rax+rax+00h]
0x14011c3b9  mov     eax, 20Ah
0x14011c3be  jmp     loc_14011C2DE
0x14011c3c3  mov     esi, r12d
0x14011c3c6  cmp     esi, [rdi+3Ch]
0x14011c3c9  jnb     loc_14011C4CF
0x14011c3cf  mov     rcx, [rdi+48h]
0x14011c3d3  mov     r9d, ebx
0x14011c3d6  mov     r14d, esi
0x14011c3d9  mov     r8d, esi
0x14011c3dc  shl     r14, 5
0x14011c3e0  mov     rdx, rdi
0x14011c3e3  add     rcx, r14
0x14011c3e6  mov     ebp, esi
0x14011c3e8  mov     byte ptr [rsp+98h+var_78], r12b
0x14011c3ed  call    ?Initialize@VIDMM_DEVICE_PAGING_QUEUE@@QEAAJPEAVVIDMM_DEVICE@@IW4VIDMM_PAGING_QUEUE_TYPE@@_N@Z; VIDMM_DEVICE_PAGING_QUEUE::Initialize(VIDMM_DEVICE *,uint,VIDMM_PAGING_QUEUE_TYPE,bool)
0x14011c3f2  mov     r15d, eax
0x14011c3f5  test    eax, eax
0x14011c3f7  js      loc_14011C491
0x14011c3fd  mov     rcx, [rdi+50h]
0x14011c401  mov     r9d, 2
0x14011c407  add     rcx, r14
0x14011c40a  mov     byte ptr [rsp+98h+var_78], r12b
0x14011c40f  mov     r8d, esi
0x14011c412  mov     rdx, rdi
0x14011c415  call    ?Initialize@VIDMM_DEVICE_PAGING_QUEUE@@QEAAJPEAVVIDMM_DEVICE@@IW4VIDMM_PAGING_QUEUE_TYPE@@_N@Z; VIDMM_DEVICE_PAGING_QUEUE::Initialize(VIDMM_DEVICE *,uint,VIDMM_PAGING_QUEUE_TYPE,bool)
0x14011c41a  mov     r15d, eax
0x14011c41d  test    eax, eax
0x14011c41f  js      short loc_14011C453
0x14011c421  mov     rax, [rdi+58h]
0x14011c425  test    rax, rax
  ... truncated ...
```
