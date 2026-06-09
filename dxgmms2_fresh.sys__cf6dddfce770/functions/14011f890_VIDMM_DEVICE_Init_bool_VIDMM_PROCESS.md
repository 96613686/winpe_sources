# VIDMM_DEVICE::Init(bool,VIDMM_PROCESS *)

- ea: `0x14011f890`
- end: `0x14011fe09`
- name: `?Init@VIDMM_DEVICE@@QEAAJ_NPEAVVIDMM_PROCESS@@@Z`
- size: `1401`
- prototype: `int(VIDMM_DEVICE *__hidden this, bool, struct VIDMM_PROCESS *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140039cb0`
- `0x140102cf4`

## callees

- `0x140003490`
- `0x140004268`
- `0x14002c5d0`
- `0x14002e1f0`
- `0x14002ed58`
- `0x140034920`
- `0x1401168a8`
- `0x14011f890`
- `0x14011fe10`
- `0x140123010`

## import_xrefs

- `watchdog!WdLogSingleEntry2` at `0x14011fd6b`
- `watchdog!WdLogSingleEntry2` at `0x14011fda9`
- `watchdog!WdLogSingleEntry2` at `0x14011fd6b`
- `watchdog!WdLogSingleEntry2` at `0x14011fda9`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14011f8b6`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x14011f8b6`
- `watchdog!WdLogSingleEntry0` at `0x14011f924`
- `watchdog!WdLogSingleEntry0` at `0x14011f992`
- `watchdog!WdLogSingleEntry0` at `0x14011fa48`
- `watchdog!WdLogSingleEntry0` at `0x14011fb0b`
- `watchdog!WdLogSingleEntry0` at `0x14011fb5b`
- `watchdog!WdLogSingleEntry0` at `0x14011fbdd`
- `watchdog!WdLogSingleEntry0` at `0x14011fc4d`
- `watchdog!WdLogSingleEntry0` at `0x14011fcbd`
- `watchdog!WdLogSingleEntry0` at `0x14011f924`
- `watchdog!WdLogSingleEntry0` at `0x14011f992`
- `watchdog!WdLogSingleEntry0` at `0x14011fa48`
- `watchdog!WdLogSingleEntry0` at `0x14011fb0b`
- `watchdog!WdLogSingleEntry0` at `0x14011fb5b`
- `watchdog!WdLogSingleEntry0` at `0x14011fbdd`
- `watchdog!WdLogSingleEntry0` at `0x14011fc4d`
- `watchdog!WdLogSingleEntry0` at `0x14011fcbd`
- `dxgkrnl!g_IsInternalReleaseOrDbg` at `0x14011f8a1`

## string_xrefs

- `0x14011f935`: `Trying to open device on a non DX process.`
- `0x14011f9a3`: `Adapter couldn't be opened for the current process.`

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
    WdLogGlobalForLineNumber = 441;
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
    WdLogGlobalForLineNumber = 450;
    DxgkLogInternalTriageEvent(
      v9,
      0x40000,
      v10,
      (unsigned int)L"Trying to open device on a non DX process.",
      450,
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
      _InterlockedAdd(&dword_1400876A8, 1u);
      WdLogSingleEntry0(6);
      WdLogGlobalForLineNumber = 466;
      DxgkLogInternalTriageEvent(
        v13,
        262145,
        v14,
        (unsigned int)L"Adapter couldn't be opened for the current process.",
        466,
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
        _InterlockedAdd(&dword_140087850, 1u);
        WdLogSingleEntry0(6);
        v20 = 493;
        v21 = L"Couldn't allocate memory for VIDMM_PHYSICAL_DEVICE.";
        goto LABEL_22;
      }
      v28 = VIDMM_PHYSICAL_DEVICE::Initialize(v27);
      if ( v28 < 0 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 500;
        DxgkLogInternalTriageEvent(
          v29,
          0x40000,
          v30,
          (unsigned int)L"Failed to initialize VIDMM_PHYSICAL_DEVICE",
          500,
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
        v20 = 517;
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
        v20 = 524;
        goto LABEL_44;
      }
      if ( (*(_DWORD *)(*((_QWORD *)this + 1) + 144LL) & 2) != 0 )
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
          v20 = 540;
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
          WdLogGlobalForLineNumber = 550;
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
          WdLogGlobalForLineNumber = 557;
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
    v50 = qword_140087550;
    *((_QWORD *)this + 28) = v50 + VidMmiQuerySystemTime();
    return 0;
  }
  _InterlockedAdd(&dword_14008784C, 1u);
  WdLogSingleEntry0(6);
  v20 = 483;
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
0x14011f890  push    rbx
0x14011f892  push    rbp
0x14011f893  push    rsi
0x14011f894  push    rdi
0x14011f895  push    r12
0x14011f897  push    r13
0x14011f899  push    r14
0x14011f89b  push    r15
0x14011f89d  sub     rsp, 58h
0x14011f8a1  mov     rax, cs:?g_IsInternalReleaseOrDbg@@3EA; uchar g_IsInternalReleaseOrDbg
0x14011f8a8  xor     r12d, r12d
0x14011f8ab  mov     r14, r8
0x14011f8ae  mov     rdi, rcx
0x14011f8b1  cmp     [rax], r12b
0x14011f8b4  jz      short loc_14011F8D7
0x14011f8b6  call    cs:__imp_WdLogNewEntry5_WdTrace
0x14011f8bd  nop     dword ptr [rax+rax+00h]
0x14011f8c2  mov     [rax+18h], rdi
0x14011f8c6  mov     rdx, [rdi]
0x14011f8c9  mov     [rax+20h], rdx
0x14011f8cd  mov     cs:WdLogGlobalForLineNumber, 1B9h
0x14011f8d7  lea     rsi, [rdi+18h]
0x14011f8db  test    r14, r14
0x14011f8de  jz      short loc_14011F8E5
0x14011f8e0  mov     r8, r14
0x14011f8e3  jmp     short loc_14011F917
0x14011f8e5  cmp     [rsi], r12
0x14011f8e8  jz      short loc_14011F90D
0x14011f8ea  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14011f8ef  test    rax, rax
0x14011f8f2  jz      short loc_14011F908
0x14011f8f4  call    ?GetCurrent@DXGPROCESS@@SAPEAV1@XZ; DXGPROCESS::GetCurrent(void)
0x14011f8f9  mov     r8, [rax+40h]
0x14011f8fd  test    r8, r8
0x14011f900  jz      short loc_14011F908
0x14011f902  mov     r8, [r8+8]
0x14011f906  jmp     short loc_14011F917
0x14011f908  mov     r8, r12
0x14011f90b  jmp     short loc_14011F917
0x14011f90d  mov     rax, [rdi]
0x14011f910  mov     r8, [rax+8F40h]
0x14011f917  mov     [rdi+8], r8
0x14011f91b  test    r8, r8
0x14011f91e  jnz     short loc_14011F96A
0x14011f920  lea     ecx, [r8+1]
0x14011f924  call    cs:__imp_WdLogSingleEntry0
0x14011f92b  nop     dword ptr [rax+rax+00h]
0x14011f930  mov     [rsp+98h+var_60], r12
0x14011f935  lea     r9, aTryingToOpenDe; "Trying to open device on a non DX proce"...
0x14011f93c  mov     eax, 1C2h
0x14011f941  mov     [rsp+98h+var_68], r12
0x14011f946  mov     [rsp+98h+var_70], r12
0x14011f94b  mov     edx, 40000h
0x14011f950  mov     cs:WdLogGlobalForLineNumber, eax
0x14011f956  mov     [rsp+98h+var_78], rax
0x14011f95b  call    DxgkLogInternalTriageEvent
0x14011f960  mov     eax, 0C0000001h
0x14011f965  jmp     loc_14011FDF7
0x14011f96a  mov     ebx, 1
0x14011f96f  mov     rax, [rdi]
0x14011f972  cmp     [rsi], r12
0x14011f975  jz      short loc_14011F9F3
0x14011f977  mov     rdx, rax; struct VIDMM_GLOBAL *
0x14011f97a  mov     rcx, r8; this
0x14011f97d  call    ?OpenAdapter@VIDMM_PROCESS@@QEAAJPEAVVIDMM_GLOBAL@@@Z; VIDMM_PROCESS::OpenAdapter(VIDMM_GLOBAL *)
0x14011f982  mov     ebp, eax
0x14011f984  test    eax, eax
0x14011f986  jns     short loc_14011F9D5
0x14011f988  lock add cs:dword_1400876A8, ebx
0x14011f98f  lea     ecx, [rbx+5]
0x14011f992  call    cs:__imp_WdLogSingleEntry0
0x14011f999  nop     dword ptr [rax+rax+00h]
0x14011f99e  mov     [rsp+98h+var_60], r12
0x14011f9a3  lea     r9, aAdapterCouldnT; "Adapter couldn't be opened for the curr"...
0x14011f9aa  mov     eax, 1D2h
0x14011f9af  mov     [rsp+98h+var_68], r12
0x14011f9b4  mov     [rsp+98h+var_70], r12
0x14011f9b9  mov     edx, 40001h
0x14011f9be  mov     cs:WdLogGlobalForLineNumber, eax
0x14011f9c4  mov     [rsp+98h+var_78], rax
0x14011f9c9  call    DxgkLogInternalTriageEvent
0x14011f9ce  mov     eax, ebp
0x14011f9d0  jmp     loc_14011FDF7
0x14011f9d5  or      [rdi+3Ah], bl
0x14011f9d8  mov     rax, [rdi]
0x14011f9db  mov     rcx, [rax+18h]
0x14011f9df  mov     rax, [rdi+8]
0x14011f9e3  mov     edx, [rcx+0F0h]
0x14011f9e9  mov     rcx, [rax+20h]
0x14011f9ed  mov     rax, [rcx+rdx*8]
0x14011f9f1  jmp     short loc_14011FA05
0x14011f9f3  mov     rax, [rax+18h]
0x14011f9f7  mov     ecx, [rax+0F0h]
0x14011f9fd  mov     rax, [r8+20h]
0x14011fa01  mov     rax, [rax+rcx*8]
0x14011fa05  mov     [rdi+10h], rax
0x14011fa09  mov     r13, 0FFFFFFFFFFFFFFFFh
0x14011fa10  mov     ecx, [rdi+3Ch]
0x14011fa13  mov     eax, 8
0x14011fa18  mul     rcx
0x14011fa1b  mov     r15d, 100h
0x14011fa21  mov     edx, 61346956h
0x14011fa26  mov     r8d, r15d
0x14011fa29  cmovb   rax, r13
0x14011fa2d  mov     rcx, rax
0x14011fa30  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14011fa35  mov     [rdi+28h], rax
0x14011fa39  test    rax, rax
0x14011fa3c  jnz     short loc_14011FA8E
0x14011fa3e  lock add cs:dword_14008784C, ebx
0x14011fa45  lea     ecx, [rax+6]
0x14011fa48  call    cs:__imp_WdLogSingleEntry0
0x14011fa4f  nop     dword ptr [rax+rax+00h]
0x14011fa54  mov     eax, 1E3h
0x14011fa59  lea     r9, aCouldnTAllocat_46; "Couldn't allocate memory for VIDMM_PHYS"...
0x14011fa60  mov     edx, 40001h
0x14011fa65  mov     [rsp+98h+var_60], r12
0x14011fa6a  mov     [rsp+98h+var_68], r12
0x14011fa6f  mov     [rsp+98h+var_70], r12
0x14011fa74  mov     [rsp+98h+var_78], rax
0x14011fa79  mov     cs:WdLogGlobalForLineNumber, eax
0x14011fa7f  call    DxgkLogInternalTriageEvent
0x14011fa84  mov     eax, 0C0000017h
0x14011fa89  jmp     loc_14011FDF7
0x14011fa8e  mov     ebp, r12d
0x14011fa91  mov     eax, [rdi+3Ch]
0x14011fa94  cmp     ebp, eax
0x14011fa96  jnb     loc_14011FB78
0x14011fa9c  mov     r8, r15
0x14011fa9f  mov     edx, 62346956h
0x14011faa4  mov     ecx, 18h
0x14011faa9  call    ??2@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new(unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14011faae  mov     ecx, ebp
0x14011fab0  mov     r8, rax
0x14011fab3  lea     r9, ds:0[rcx*8]
0x14011fabb  test    rax, rax
0x14011fabe  jz      short loc_14011FADB
0x14011fac0  mov     rcx, [rdi]
0x14011fac3  mov     rdx, [rcx+8E80h]
0x14011faca  mov     rcx, [r9+rdx]
0x14011face  mov     [rax], rcx
0x14011fad1  mov     [rax+8], rdi
0x14011fad5  mov     [rax+10h], r12
0x14011fad9  jmp     short loc_14011FADE
0x14011fadb  mov     r8, r12
0x14011fade  mov     rax, [rdi+28h]
0x14011fae2  mov     [r9+rax], r8
0x14011fae6  mov     rax, [rdi+28h]
0x14011faea  mov     rcx, [r9+rax]; this
0x14011faee  test    rcx, rcx
0x14011faf1  jz      short loc_14011FB4F
0x14011faf3  call    ?Initialize@VIDMM_PHYSICAL_DEVICE@@QEAAJXZ; VIDMM_PHYSICAL_DEVICE::Initialize(void)
0x14011faf8  mov     r15d, eax
0x14011fafb  test    eax, eax
0x14011fafd  js      short loc_14011FB09
0x14011faff  add     ebp, ebx
0x14011fb01  mov     r15d, 100h
0x14011fb07  jmp     short loc_14011FA91
0x14011fb09  mov     ecx, ebx
0x14011fb0b  call    cs:__imp_WdLogSingleEntry0
0x14011fb12  nop     dword ptr [rax+rax+00h]
0x14011fb17  mov     [rsp+98h+var_60], r12
0x14011fb1c  lea     r9, aFailedToInitia_7; "Failed to initialize VIDMM_PHYSICAL_DEV"...
0x14011fb23  mov     eax, 1F4h
0x14011fb28  mov     [rsp+98h+var_68], r12
0x14011fb2d  mov     [rsp+98h+var_70], r12
0x14011fb32  mov     cs:WdLogGlobalForLineNumber, eax
0x14011fb38  mov     [rsp+98h+var_78], rax
0x14011fb3d  mov     edx, 40000h
0x14011fb42  call    DxgkLogInternalTriageEvent
0x14011fb47  mov     eax, r15d
0x14011fb4a  jmp     loc_14011FDF7
0x14011fb4f  lock add cs:dword_140087850, ebx
0x14011fb56  mov     ecx, 6
0x14011fb5b  call    cs:__imp_WdLogSingleEntry0
0x14011fb62  nop     dword ptr [rax+rax+00h]
0x14011fb67  mov     eax, 1EDh
0x14011fb6c  lea     r9, aCouldnTAllocat_51; "Couldn't allocate memory for VIDMM_PHYS"...
0x14011fb73  jmp     loc_14011FA60
0x14011fb78  cmp     [rsi], r12
0x14011fb7b  jnz     short loc_14011FB86
0x14011fb7d  test    r14, r14
0x14011fb80  jnz     loc_14011FDDF
0x14011fb86  mov     rbp, rax
0x14011fb89  mov     r14d, 20h ; ' '
0x14011fb8f  mov     eax, r14d
0x14011fb92  mov     r8, r15
0x14011fb95  mul     rbp
0x14011fb98  cmovb   rax, r13
0x14011fb9c  mov     r13d, 38346956h
0x14011fba2  mov     edx, r13d
0x14011fba5  mov     rcx, rax
0x14011fba8  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14011fbad  lea     r15, ??0VIDMM_DEVICE_PAGING_QUEUE@@QEAA@XZ; VIDMM_DEVICE_PAGING_QUEUE::VIDMM_DEVICE_PAGING_QUEUE(void)
0x14011fbb4  mov     rsi, rax
0x14011fbb7  test    rax, rax
0x14011fbba  jz      short loc_14011FBCF
0x14011fbbc  mov     r9, r15; void *(*)(void *)
0x14011fbbf  mov     r8, rbp; unsigned __int64
0x14011fbc2  mov     edx, r14d; unsigned __int64
0x14011fbc5  mov     rcx, rax; void *
0x14011fbc8  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x14011fbcd  jmp     short loc_14011FBD2
0x14011fbcf  mov     rsi, r12
0x14011fbd2  mov     [rdi+48h], rsi
0x14011fbd6  test    rsi, rsi
0x14011fbd9  jnz     short loc_14011FBFF
0x14011fbdb  mov     ecx, ebx
0x14011fbdd  call    cs:__imp_WdLogSingleEntry0
0x14011fbe4  nop     dword ptr [rax+rax+00h]
0x14011fbe9  mov     eax, 205h
0x14011fbee  lea     r9, aFailedToAlloca_12; "Failed to allocate memory for VIDMM_DEV"...
0x14011fbf5  mov     edx, 40000h
0x14011fbfa  jmp     loc_14011FA65
0x14011fbff  mov     ebp, [rdi+3Ch]
0x14011fc02  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14011fc09  mov     rax, r14
0x14011fc0c  mov     r8d, 100h
0x14011fc12  mul     rbp
0x14011fc15  mov     edx, r13d
0x14011fc18  cmovb   rax, rcx
0x14011fc1c  mov     rcx, rax
0x14011fc1f  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14011fc24  mov     rsi, rax
0x14011fc27  test    rax, rax
0x14011fc2a  jz      short loc_14011FC3F
0x14011fc2c  mov     r9, r15; void *(*)(void *)
0x14011fc2f  mov     r8d, ebp; unsigned __int64
0x14011fc32  mov     rdx, r14; unsigned __int64
0x14011fc35  mov     rcx, rax; void *
0x14011fc38  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x14011fc3d  jmp     short loc_14011FC42
0x14011fc3f  mov     rsi, r12
0x14011fc42  mov     [rdi+50h], rsi
0x14011fc46  test    rsi, rsi
0x14011fc49  jnz     short loc_14011FC60
0x14011fc4b  mov     ecx, ebx
0x14011fc4d  call    cs:__imp_WdLogSingleEntry0
0x14011fc54  nop     dword ptr [rax+rax+00h]
0x14011fc59  mov     eax, 20Ch
0x14011fc5e  jmp     short loc_14011FBEE
0x14011fc60  mov     rax, [rdi+8]
0x14011fc64  mov     ecx, [rax+90h]
0x14011fc6a  test    cl, 2
0x14011fc6d  jz      short loc_14011FCD3
0x14011fc6f  mov     ebp, [rdi+3Ch]
0x14011fc72  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14011fc79  mov     rax, r14
0x14011fc7c  mov     r8d, 100h
0x14011fc82  mul     rbp
0x14011fc85  mov     edx, r13d
0x14011fc88  cmovb   rax, rcx
0x14011fc8c  mov     rcx, rax
0x14011fc8f  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14011fc94  mov     rsi, rax
0x14011fc97  test    rax, rax
0x14011fc9a  jz      short loc_14011FCAF
0x14011fc9c  mov     r9, r15; void *(*)(void *)
0x14011fc9f  mov     r8d, ebp; unsigned __int64
0x14011fca2  mov     rdx, r14; unsigned __int64
0x14011fca5  mov     rcx, rax; void *
0x14011fca8  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x14011fcad  jmp     short loc_14011FCB2
0x14011fcaf  mov     rsi, r12
0x14011fcb2  mov     [rdi+58h], rsi
0x14011fcb6  test    rsi, rsi
0x14011fcb9  jnz     short loc_14011FCD3
0x14011fcbb  mov     ecx, ebx
0x14011fcbd  call    cs:__imp_WdLogSingleEntry0
0x14011fcc4  nop     dword ptr [rax+rax+00h]
0x14011fcc9  mov     eax, 21Ch
0x14011fcce  jmp     loc_14011FBEE
0x14011fcd3  mov     esi, r12d
0x14011fcd6  cmp     esi, [rdi+3Ch]
0x14011fcd9  jnb     loc_14011FDDF
0x14011fcdf  mov     rcx, [rdi+48h]
0x14011fce3  mov     r9d, ebx
0x14011fce6  mov     r14d, esi
0x14011fce9  mov     r8d, esi
0x14011fcec  shl     r14, 5
0x14011fcf0  mov     rdx, rdi
0x14011fcf3  add     rcx, r14
0x14011fcf6  mov     ebp, esi
0x14011fcf8  mov     byte ptr [rsp+98h+var_78], r12b
0x14011fcfd  call    ?Initialize@VIDMM_DEVICE_PAGING_QUEUE@@QEAAJPEAVVIDMM_DEVICE@@IW4VIDMM_PAGING_QUEUE_TYPE@@_N@Z; VIDMM_DEVICE_PAGING_QUEUE::Initialize(VIDMM_DEVICE *,uint,VIDMM_PAGING_QUEUE_TYPE,bool)
0x14011fd02  mov     r15d, eax
0x14011fd05  test    eax, eax
0x14011fd07  js      loc_14011FDA1
0x14011fd0d  mov     rcx, [rdi+50h]
0x14011fd11  mov     r9d, 2
0x14011fd17  add     rcx, r14
0x14011fd1a  mov     byte ptr [rsp+98h+var_78], r12b
0x14011fd1f  mov     r8d, esi
0x14011fd22  mov     rdx, rdi
0x14011fd25  call    ?Initialize@VIDMM_DEVICE_PAGING_QUEUE@@QEAAJPEAVVIDMM_DEVICE@@IW4VIDMM_PAGING_QUEUE_TYPE@@_N@Z; VIDMM_DEVICE_PAGING_QUEUE::Initialize(VIDMM_DEVICE *,uint,VIDMM_PAGING_QUEUE_TYPE,bool)
0x14011fd2a  mov     r15d, eax
0x14011fd2d  test    eax, eax
0x14011fd2f  js      short loc_14011FD63
0x14011fd31  mov     rax, [rdi+58h]
0x14011fd35  test    rax, rax
  ... truncated ...
```
