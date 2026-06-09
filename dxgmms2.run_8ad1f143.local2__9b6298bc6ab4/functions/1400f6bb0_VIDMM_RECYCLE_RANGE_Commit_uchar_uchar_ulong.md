# VIDMM_RECYCLE_RANGE::Commit(uchar,uchar *,ulong)

- ea: `0x1400f6bb0`
- end: `0x1400f6f9e`
- name: `?Commit@VIDMM_RECYCLE_RANGE@@QEAAJEPEAEK@Z`
- size: `1006`
- prototype: `__int64 __fastcall(VIDMM_RECYCLE_RANGE *__hidden this, unsigned __int8, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400f68d8`

## callees

- `0x1400045ec`
- `0x140013434`
- `0x1400f1edc`
- `0x1400f3438`
- `0x1400f6bb0`
- `0x1400f6fa4`
- `0x1400f70b4`

## import_xrefs

- `watchdog!WdLogSingleEntry5` at `0x1400f6c3a`
- `watchdog!WdLogSingleEntry5` at `0x1400f6d14`
- `watchdog!WdLogSingleEntry5` at `0x1400f6d85`
- `watchdog!WdLogSingleEntry5` at `0x1400f6e64`
- `watchdog!WdLogSingleEntry5` at `0x1400f6f1d`
- `watchdog!WdLogSingleEntry5` at `0x1400f6f7a`
- `watchdog!WdLogSingleEntry5` at `0x1400f6c3a`
- `watchdog!WdLogSingleEntry5` at `0x1400f6d14`
- `watchdog!WdLogSingleEntry5` at `0x1400f6d85`
- `watchdog!WdLogSingleEntry5` at `0x1400f6e64`
- `watchdog!WdLogSingleEntry5` at `0x1400f6f1d`
- `watchdog!WdLogSingleEntry5` at `0x1400f6f7a`
- `watchdog!WdLogSingleEntry1` at `0x1400f6e9d`
- `watchdog!WdLogSingleEntry1` at `0x1400f6e9d`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f6c17`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f6cef`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f6d60`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f6e3f`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f6ef8`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x1400f6f55`
- `dxgkrnl!g_IsInternalRelease` at `0x1400f6c0b`
- `dxgkrnl!g_IsInternalRelease` at `0x1400f6ce3`
- `dxgkrnl!g_IsInternalRelease` at `0x1400f6d50`
- `dxgkrnl!g_IsInternalRelease` at `0x1400f6ee8`
- `dxgkrnl!g_IsInternalRelease` at `0x1400f6f45`

## string_xrefs

- `0x1400f6eae`: `Couldn't commit virtual memory. Status = 0x%I64x\n`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 __fastcall VIDMM_RECYCLE_RANGE::Commit(
        VIDMM_RECYCLE_RANGE *this,
        __int64 a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  unsigned int v5; // r10d
  int v7; // ecx
  void *v8; // r8
  int v9; // edx
  VIDMM_RECYCLE_HEAP_MGR *v10; // rcx
  __int64 v11; // rdx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  unsigned int v16; // r9d
  int v17; // eax
  __int64 v18; // rsi
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // rdx
  int v22; // ecx
  int v23; // r8d
  void *v24; // [rsp+50h] [rbp-38h] BYREF
  unsigned __int64 v25; // [rsp+90h] [rbp+8h] BYREF

  v5 = a4;
  v7 = *((_DWORD *)this + 16);
  if ( !v7 )
  {
    v8 = (void *)*((_QWORD *)this + 4);
    v25 = *((_QWORD *)this + 5) - (_QWORD)v8;
    v9 = **(_DWORD **)(*((_QWORD *)this + 9) + 32LL);
    if ( (unsigned int)(v9 - 9) > 1 )
    {
      if ( (unsigned int)(v9 - 3) <= 3 )
      {
        if ( dword_140086500 && !*((_DWORD *)this + 20) && g_IsInternalRelease )
        {
          g_DxgMmsBugcheckExportIndex = 1;
          WdLogSingleEntry5(0, 270, 9);
          WdLogGlobalForLineNumber = 222;
          goto LABEL_48;
        }
        goto LABEL_12;
      }
      goto LABEL_29;
    }
    if ( !dword_140086500 || *((_DWORD *)this + 20) || !g_IsInternalRelease )
      goto LABEL_12;
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 9);
    WdLogGlobalForLineNumber = 222;
  }
  v10 = (VIDMM_RECYCLE_HEAP_MGR *)(unsigned int)(v7 - 4);
  if ( !(_DWORD)v10 )
  {
    VIDMM_RECYCLE_HEAP_MGR::UpdateUnlockAgingOnTransition(
      *(VIDMM_RECYCLE_HEAP_MGR **)(*(_QWORD *)(*((_QWORD *)this + 9) + 32LL) + 8LL),
      this);
    if ( !dword_140086500 || *((_DWORD *)this + 20) > 1u || !g_IsInternalRelease )
    {
      v11 = 3;
      goto LABEL_13;
    }
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 9);
    WdLogGlobalForLineNumber = 222;
  }
  if ( (_DWORD)v10 != 1 )
  {
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 270, 52);
    WdLogGlobalForLineNumber = 222;
    goto LABEL_38;
  }
  VIDMM_RECYCLE_HEAP_MGR::RemoveFromDebounce(v10, this);
  if ( !dword_140086500 || *((_DWORD *)this + 20) || !g_IsInternalRelease )
    goto LABEL_12;
  g_DxgMmsBugcheckExportIndex = 1;
  WdLogSingleEntry5(0, 270, 9);
  WdLogGlobalForLineNumber = 222;
LABEL_29:
  if ( v9 == 2 )
  {
LABEL_30:
    v16 = 4;
    goto LABEL_31;
  }
LABEL_38:
  v16 = 1028;
  if ( v9 == 8 )
    goto LABEL_30;
LABEL_31:
  v24 = v8;
  v17 = VidMmAllocateVirtualMemory(&v24, &v25, 0x1000u, v16, v5);
  v18 = v17;
  if ( v17 >= 0 )
  {
    if ( dword_140086500 && *((_DWORD *)this + 20) && g_IsInternalRelease )
    {
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 270, 9);
      WdLogGlobalForLineNumber = 222;
    }
    else
    {
      if ( (byte_140086201 & 0x10) == 0 )
      {
LABEL_12:
        v11 = 1;
LABEL_13:
        VIDMM_RECYCLE_RANGE::Transition(this, v11);
        v12 = *((_DWORD *)this + 20);
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( !v14 )
            {
              *((_DWORD *)this + 20) = 3;
LABEL_17:
              *((_BYTE *)this + 84) = *a3;
              return 0;
            }
LABEL_48:
            if ( v14 != 1 )
              return 0;
            goto LABEL_17;
          }
        }
        else
        {
          *((_DWORD *)this + 20) = 1;
        }
        *((_BYTE *)this + 84) = 0;
        return 0;
      }
      v19 = *((_QWORD *)this + 9);
      v20 = *(_QWORD *)(v19 + 32);
      if ( (unsigned int)(*(_DWORD *)v20 - 3) <= 3 )
      {
        v21 = *(_QWORD *)(v19 + 56);
LABEL_36:
        McTemplateK0qxxx_EtwWriteTransfer(
          v19,
          (unsigned int)EventCreateProcessAllocationDetails,
          v20,
          *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v20 + 8) + 8LL) + 24LL),
          (char)this,
          v25,
          v21);
        goto LABEL_12;
      }
    }
    v21 = *((_QWORD *)this + 4);
    goto LABEL_36;
  }
  _InterlockedIncrement(&dword_1400867A8);
  WdLogSingleEntry1(6, v17);
  WdLogGlobalForLineNumber = 1226;
  DxgkLogInternalTriageEvent(
    v22,
    262145,
    v23,
    (unsigned int)L"Couldn't commit virtual memory. Status = 0x%I64x\n",
    v18,
    0,
    0,
    0);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1400f6bb0  mov     r11, rsp
0x1400f6bb3  push    rbx
0x1400f6bb4  push    rbp
0x1400f6bb5  push    rsi
0x1400f6bb6  push    r14
0x1400f6bb8  sub     rsp, 68h
0x1400f6bbc  movsxd  rdx, dword ptr [rcx+40h]
0x1400f6bc0  xor     ebp, ebp
0x1400f6bc2  mov     rbx, rcx
0x1400f6bc5  mov     r10d, r9d
0x1400f6bc8  mov     r14, r8
0x1400f6bcb  mov     ecx, edx
0x1400f6bcd  test    edx, edx
0x1400f6bcf  jnz     short loc_1400F6C50
0x1400f6bd1  mov     r8, [rbx+20h]
0x1400f6bd5  mov     rax, [rbx+28h]
0x1400f6bd9  sub     rax, r8
0x1400f6bdc  mov     [r11+8], rax
0x1400f6be0  mov     rax, [rbx+48h]
0x1400f6be4  mov     rcx, [rax+20h]
0x1400f6be8  mov     edx, [rcx]
0x1400f6bea  lea     eax, [rdx-9]
0x1400f6bed  cmp     eax, 1
0x1400f6bf0  ja      loc_1400F6C7C
0x1400f6bf6  cmp     cs:dword_140086500, ebp
0x1400f6bfc  jz      loc_1400F6C94
0x1400f6c02  cmp     [rbx+50h], ebp
0x1400f6c05  jnz     loc_1400F6C94
0x1400f6c0b  mov     rax, cs:__imp_?g_IsInternalRelease@@3EA; uchar g_IsInternalRelease
0x1400f6c12  cmp     [rax], bpl
0x1400f6c15  jz      short loc_1400F6C94
0x1400f6c17  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400f6c1e  mov     dword ptr [rax], 1
0x1400f6c24  mov     [r11-60h], rbp
0x1400f6c28  lea     r8d, [rbp+9]
0x1400f6c2c  xor     r9d, r9d
0x1400f6c2f  mov     [r11-68h], rbp
0x1400f6c33  mov     edx, 10Eh
0x1400f6c38  xor     ecx, ecx
0x1400f6c3a  call    cs:__imp_WdLogSingleEntry5
0x1400f6c41  nop     dword ptr [rax+rax+00h]
0x1400f6c46  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400f6c50  sub     ecx, 4
0x1400f6c53  jnz     loc_1400F6D2A
0x1400f6c59  mov     rax, [rbx+48h]
0x1400f6c5d  mov     rdx, rbx; struct VIDMM_RECYCLE_RANGE *
0x1400f6c60  mov     rcx, [rax+20h]
0x1400f6c64  mov     rcx, [rcx+8]; this
0x1400f6c68  call    ?UpdateUnlockAgingOnTransition@VIDMM_RECYCLE_HEAP_MGR@@QEAAXPEAVVIDMM_RECYCLE_RANGE@@@Z; VIDMM_RECYCLE_HEAP_MGR::UpdateUnlockAgingOnTransition(VIDMM_RECYCLE_RANGE *)
0x1400f6c6d  cmp     cs:dword_140086500, ebp
0x1400f6c73  jnz     short loc_1400F6CDD
0x1400f6c75  mov     edx, 3
0x1400f6c7a  jmp     short loc_1400F6C99
0x1400f6c7c  lea     eax, [rdx-3]
0x1400f6c7f  cmp     eax, 3
0x1400f6c82  ja      loc_1400F6D9B
0x1400f6c88  cmp     cs:dword_140086500, ebp
0x1400f6c8e  jnz     loc_1400F6F3C
0x1400f6c94  mov     edx, 1
0x1400f6c99  mov     rcx, rbx
0x1400f6c9c  call    ?Transition@VIDMM_RECYCLE_RANGE@@QEAAXW4VIDMM_RECYCLE_RANGE_STATE@@@Z; VIDMM_RECYCLE_RANGE::Transition(VIDMM_RECYCLE_RANGE_STATE)
0x1400f6ca1  mov     ecx, [rbx+50h]
0x1400f6ca4  test    ecx, ecx
0x1400f6ca6  jz      short loc_1400F6CD0
0x1400f6ca8  sub     ecx, 1
0x1400f6cab  jz      short loc_1400F6CD7
0x1400f6cad  sub     ecx, 1
0x1400f6cb0  jnz     loc_1400F6F90
0x1400f6cb6  mov     dword ptr [rbx+50h], 3
0x1400f6cbd  mov     al, [r14]
0x1400f6cc0  mov     [rbx+54h], al
0x1400f6cc3  xor     eax, eax
0x1400f6cc5  add     rsp, 68h
0x1400f6cc9  pop     r14
0x1400f6ccb  pop     rsi
0x1400f6ccc  pop     rbp
0x1400f6ccd  pop     rbx
0x1400f6cce  retn
0x1400f6cd0  mov     dword ptr [rbx+50h], 1
0x1400f6cd7  mov     [rbx+54h], bpl
0x1400f6cdb  jmp     short loc_1400F6CC3
0x1400f6cdd  cmp     dword ptr [rbx+50h], 1
0x1400f6ce1  ja      short loc_1400F6C75
0x1400f6ce3  mov     rax, cs:__imp_?g_IsInternalRelease@@3EA; uchar g_IsInternalRelease
0x1400f6cea  cmp     [rax], bpl
0x1400f6ced  jz      short loc_1400F6C75
0x1400f6cef  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400f6cf6  mov     dword ptr [rax], 1
0x1400f6cfc  xor     r9d, r9d
0x1400f6cff  mov     [rsp+88h+var_60], rbp
0x1400f6d04  mov     edx, 10Eh
0x1400f6d09  mov     qword ptr [rsp+88h+var_68], rbp
0x1400f6d0e  xor     ecx, ecx
0x1400f6d10  lea     r8d, [r9+9]
0x1400f6d14  call    cs:__imp_WdLogSingleEntry5
0x1400f6d1b  nop     dword ptr [rax+rax+00h]
0x1400f6d20  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400f6d2a  cmp     ecx, 1
0x1400f6d2d  jnz     loc_1400F6E3F
0x1400f6d33  mov     rdx, rbx; struct VIDMM_RECYCLE_RANGE *
0x1400f6d36  call    ?RemoveFromDebounce@VIDMM_RECYCLE_HEAP_MGR@@QEAAXPEAVVIDMM_RECYCLE_RANGE@@@Z; VIDMM_RECYCLE_HEAP_MGR::RemoveFromDebounce(VIDMM_RECYCLE_RANGE *)
0x1400f6d3b  cmp     cs:dword_140086500, ebp
0x1400f6d41  jz      loc_1400F6C94
0x1400f6d47  cmp     [rbx+50h], ebp
0x1400f6d4a  jnz     loc_1400F6C94
0x1400f6d50  mov     rax, cs:__imp_?g_IsInternalRelease@@3EA; uchar g_IsInternalRelease
0x1400f6d57  cmp     [rax], bpl
0x1400f6d5a  jz      loc_1400F6C94
0x1400f6d60  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400f6d67  mov     dword ptr [rax], 1
0x1400f6d6d  xor     r9d, r9d
0x1400f6d70  mov     [rsp+88h+var_60], rbp
0x1400f6d75  mov     edx, 10Eh
0x1400f6d7a  mov     qword ptr [rsp+88h+var_68], rbp
0x1400f6d7f  xor     ecx, ecx
0x1400f6d81  lea     r8d, [r9+9]
0x1400f6d85  call    cs:__imp_WdLogSingleEntry5
0x1400f6d8c  nop     dword ptr [rax+rax+00h]
0x1400f6d91  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400f6d9b  cmp     edx, 2
0x1400f6d9e  jnz     loc_1400F6E7A
0x1400f6da4  mov     r9d, 4; unsigned int
0x1400f6daa  mov     [rsp+88h+var_38], r8
0x1400f6daf  lea     rdx, [rsp+88h+arg_0]; unsigned __int64 *
0x1400f6db7  mov     r8d, 1000h; unsigned int
0x1400f6dbd  mov     [rsp+88h+var_68], r10d; unsigned int
0x1400f6dc2  lea     rcx, [rsp+88h+var_38]; void **
0x1400f6dc7  call    ?VidMmAllocateVirtualMemory@@YAJPEAPEAXPEA_KKKK@Z; VidMmAllocateVirtualMemory(void * *,unsigned __int64 *,ulong,ulong,ulong)
0x1400f6dcc  movsxd  rsi, eax
0x1400f6dcf  test    eax, eax
0x1400f6dd1  js      loc_1400F6E8E
0x1400f6dd7  cmp     cs:dword_140086500, ebp
0x1400f6ddd  jnz     loc_1400F6EDF
0x1400f6de3  test    cs:byte_140086201, 10h
0x1400f6dea  jz      loc_1400F6C94
0x1400f6df0  mov     rcx, [rbx+48h]
0x1400f6df4  mov     r8, [rcx+20h]
0x1400f6df8  mov     eax, [r8]
0x1400f6dfb  sub     eax, 3
0x1400f6dfe  cmp     eax, 3
0x1400f6e01  ja      loc_1400F6F33
0x1400f6e07  mov     rdx, [rcx+38h]
0x1400f6e0b  mov     rax, [r8+8]
0x1400f6e0f  mov     [rsp+88h+var_58], rdx
0x1400f6e14  lea     rdx, EventCreateProcessAllocationDetails
0x1400f6e1b  mov     r9, [rax+8]
0x1400f6e1f  mov     rax, [rsp+88h+arg_0]
0x1400f6e27  mov     [rsp+88h+var_60], rax
0x1400f6e2c  mov     qword ptr [rsp+88h+var_68], rbx
0x1400f6e31  mov     r9d, [r9+18h]
0x1400f6e35  call    McTemplateK0qxxx_EtwWriteTransfer
0x1400f6e3a  jmp     loc_1400F6C94
0x1400f6e3f  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400f6e46  mov     dword ptr [rax], 1
0x1400f6e4c  xor     r9d, r9d
0x1400f6e4f  mov     [rsp+88h+var_60], rbp
0x1400f6e54  mov     qword ptr [rsp+88h+var_68], rdx
0x1400f6e59  xor     ecx, ecx
0x1400f6e5b  mov     edx, 10Eh
0x1400f6e60  lea     r8d, [r9+34h]
0x1400f6e64  call    cs:__imp_WdLogSingleEntry5
0x1400f6e6b  nop     dword ptr [rax+rax+00h]
0x1400f6e70  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400f6e7a  mov     r9d, 404h
0x1400f6e80  cmp     edx, 8
0x1400f6e83  jnz     loc_1400F6DAA
0x1400f6e89  jmp     loc_1400F6DA4
0x1400f6e8e  lock inc cs:dword_1400867A8
0x1400f6e95  mov     rdx, rsi
0x1400f6e98  mov     ecx, 6
0x1400f6e9d  call    cs:__imp_WdLogSingleEntry1
0x1400f6ea4  nop     dword ptr [rax+rax+00h]
0x1400f6ea9  mov     [rsp+88h+var_50], rbp
0x1400f6eae  lea     r9, aCouldnTCommitV_0; "Couldn't commit virtual memory. Status "...
0x1400f6eb5  mov     [rsp+88h+var_58], rbp
0x1400f6eba  mov     edx, 40001h
0x1400f6ebf  mov     [rsp+88h+var_60], rbp
0x1400f6ec4  mov     qword ptr [rsp+88h+var_68], rsi
0x1400f6ec9  mov     cs:WdLogGlobalForLineNumber, 4CAh
0x1400f6ed3  call    DxgkLogInternalTriageEvent
0x1400f6ed8  mov     eax, esi
0x1400f6eda  jmp     loc_1400F6CC5
0x1400f6edf  cmp     [rbx+50h], ebp
0x1400f6ee2  jz      loc_1400F6DE3
0x1400f6ee8  mov     rax, cs:__imp_?g_IsInternalRelease@@3EA; uchar g_IsInternalRelease
0x1400f6eef  cmp     [rax], bpl
0x1400f6ef2  jz      loc_1400F6DE3
0x1400f6ef8  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400f6eff  mov     dword ptr [rax], 1
0x1400f6f05  xor     r9d, r9d
0x1400f6f08  mov     [rsp+88h+var_60], rbp
0x1400f6f0d  mov     edx, 10Eh
0x1400f6f12  mov     qword ptr [rsp+88h+var_68], rbp
0x1400f6f17  xor     ecx, ecx
0x1400f6f19  lea     r8d, [r9+9]
0x1400f6f1d  call    cs:__imp_WdLogSingleEntry5
0x1400f6f24  nop     dword ptr [rax+rax+00h]
0x1400f6f29  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400f6f33  mov     rdx, [rbx+20h]
0x1400f6f37  jmp     loc_1400F6E0B
0x1400f6f3c  cmp     [rbx+50h], ebp
0x1400f6f3f  jnz     loc_1400F6C94
0x1400f6f45  mov     rax, cs:__imp_?g_IsInternalRelease@@3EA; uchar g_IsInternalRelease
0x1400f6f4c  cmp     [rax], bpl
0x1400f6f4f  jz      loc_1400F6C94
0x1400f6f55  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x1400f6f5c  mov     dword ptr [rax], 1
0x1400f6f62  xor     r9d, r9d
0x1400f6f65  mov     [rsp+88h+var_60], rbp
0x1400f6f6a  mov     edx, 10Eh
0x1400f6f6f  mov     qword ptr [rsp+88h+var_68], rbp
0x1400f6f74  xor     ecx, ecx
0x1400f6f76  lea     r8d, [r9+9]
0x1400f6f7a  call    cs:__imp_WdLogSingleEntry5
0x1400f6f81  nop     dword ptr [rax+rax+00h]
0x1400f6f86  mov     cs:WdLogGlobalForLineNumber, 0DEh
0x1400f6f90  cmp     ecx, 1
0x1400f6f93  jnz     loc_1400F6CC3
0x1400f6f99  jmp     loc_1400F6CBD
```
