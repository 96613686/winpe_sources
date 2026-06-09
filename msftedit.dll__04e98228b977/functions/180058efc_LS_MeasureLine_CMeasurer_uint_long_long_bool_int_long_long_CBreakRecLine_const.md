# LS::MeasureLine(CMeasurer &,uint,long *,long,bool,int &,long *,long *,CBreakRecLine const *)

- ea: `0x180058efc`
- end: `0x180059124`
- name: `?MeasureLine@LS@@YAHAEAVCMeasurer@@IPEAJJ_NAEAH11PEBUCBreakRecLine@@@Z`
- size: `552`
- prototype: `__int64 __fastcall(LS *__hidden this, struct CMeasurer *, unsigned int, int *, int, bool, int *, int *, int *, const struct CBreakRecLine *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003b04c`

## callees

- `0x180012270`
- `0x180057560`
- `0x180058efc`
- `0x18005912c`
- `0x180059150`
- `0x18005a5f8`
- `0x18005abb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005909a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005909a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058fb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800590a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058fb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800590a6`

## pseudocode

```c
__int64 __fastcall LS::MeasureLine(
        LS *this,
        struct CMeasurer *a2,
        int *a3,
        int *a4,
        int a5,
        _DWORD *a6,
        int *a7,
        int *a8,
        struct CBreakRecLine *a9)
{
  __int64 v9; // r11
  int v10; // r14d
  unsigned int v12; // r12d
  __int64 v13; // rax
  unsigned int v14; // ebx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 *v21; // rax
  __int64 v22; // rsi
  int v23; // edi
  _DWORD *LockTelemetry; // rax
  struct Ptls6::ols *Pols; // rax
  Ptls6::ols *v26; // rdi
  __int16 v27; // ax
  int v28; // eax
  RTL_SRWLOCK *Lock; // rax
  __int64 v31; // rax
  _QWORD v32[2]; // [rsp+50h] [rbp-49h] BYREF
  bool v33; // [rsp+60h] [rbp-39h]
  char v34; // [rsp+61h] [rbp-38h]
  int v35; // [rsp+68h] [rbp-31h]
  char v36; // [rsp+6Ch] [rbp-2Dh]
  BOOL v37; // [rsp+70h] [rbp-29h]
  __int64 v38; // [rsp+78h] [rbp-21h]
  __int128 v39; // [rsp+80h] [rbp-19h]
  __int16 v40; // [rsp+90h] [rbp-9h]

  v9 = *((_QWORD *)this + 2);
  v10 = (int)a4;
  v12 = (unsigned int)a2;
  if ( v9 )
    v13 = *(_QWORD *)(v9 + 40);
  else
    v13 = 0;
  v14 = 1;
  if ( (*(_BYTE *)(v13 + 358) & 1) == 0 )
    return 0;
  v32[0] = this;
  if ( v9 )
    v15 = *(_QWORD *)(v9 + 40);
  else
    v15 = 0;
  v16 = *(_QWORD *)(v15 + 256);
  v33 = 0;
  if ( v16 && (v17 = *(__int64 **)(v16 + 80)) != 0 )
  {
    v33 = (v17[2] & 4) != 0;
    v18 = *v17;
  }
  else
  {
    v18 = 0;
  }
  v32[1] = v18;
  v34 = 0;
  if ( v9 )
    v19 = *(_QWORD *)(v9 + 40);
  else
    v19 = 0;
  v20 = *(_QWORD *)(v19 + 256);
  if ( v20 && (v21 = *(__int64 **)(v20 + 80)) != 0 )
    v22 = *v21;
  else
    v22 = 0;
  v23 = (int)CLockSharedData::LockOwner;
  v35 = 0;
  if ( (_DWORD)CLockSharedData::LockOwner && v23 == GetCurrentThreadId() )
  {
    LockTelemetry = (_DWORD *)CLock::GetLockTelemetry(0);
    ++*LockTelemetry;
  }
  else
  {
    Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
    AcquireSRWLockExclusive(Lock);
    LODWORD(CLockSharedData::LockOwner) = GetCurrentThreadId();
    v31 = CLock::GetLockTelemetry(0);
    ++*(_DWORD *)(v31 + 4);
  }
  ++CLSLock::_cOLSBusy;
  v36 = 1;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  g_cFCLock += v22 == 0;
  v37 = v22 == 0;
  Pols = CMeasurerLS::GetPols((CMeasurerLS *)v32);
  v26 = Pols;
  if ( !Pols )
    goto LABEL_24;
  v27 = *((_WORD *)Pols + 526);
  if ( (v27 & 0x20) != 0 && !a9 )
  {
    *((_WORD *)v26 + 526) = v27 & 0xFFDF;
    Ptls6::ols::ClearRunCache(v26);
  }
  v28 = Ptls6::ols::MeasureLine(v26, v12, a3, v10, 1, 0, 0, a7, a8, a9);
  if ( v28 >= 0 )
    *a6 = v28 != 1;
  else
LABEL_24:
    v14 = 0;
  CMeasurerLS::~CMeasurerLS((CMeasurerLS *)v32);
  return v14;
}

```

## disassembly

```asm
0x180058efc  push    rbp
0x180058efe  push    rbx
0x180058eff  push    rsi
0x180058f00  push    rdi
0x180058f01  push    r12
0x180058f03  push    r14
0x180058f05  push    r15
0x180058f07  lea     rbp, [rsp-7]
0x180058f0c  sub     rsp, 0A0h
0x180058f13  mov     r11, [rcx+10h]
0x180058f17  mov     r14d, r9d
0x180058f1a  mov     r15, r8
0x180058f1d  mov     r12d, edx
0x180058f20  test    r11, r11
0x180058f23  jz      loc_1800590CF
0x180058f29  mov     rax, [r11+28h]
0x180058f2d  mov     ebx, 1
0x180058f32  test    [rax+166h], bl
0x180058f38  jz      loc_1800590C7
0x180058f3e  mov     [rbp+37h+var_80], rcx
0x180058f42  test    r11, r11
0x180058f45  jz      loc_1800590D6
0x180058f4b  mov     rax, [r11+28h]
0x180058f4f  mov     rcx, [rax+100h]
0x180058f56  mov     [rbp+37h+var_70], 0
0x180058f5a  test    rcx, rcx
0x180058f5d  jz      short loc_180058F6C
0x180058f5f  mov     rcx, [rcx+50h]
0x180058f63  test    rcx, rcx
0x180058f66  jnz     loc_1800590E4
0x180058f6c  xor     eax, eax
0x180058f6e  mov     [rbp+37h+var_78], rax
0x180058f72  mov     [rbp+37h+var_6F], 0
0x180058f76  test    r11, r11
0x180058f79  jz      loc_1800590DD
0x180058f7f  mov     rax, [r11+28h]
0x180058f83  mov     rcx, [rax+100h]
0x180058f8a  test    rcx, rcx
0x180058f8d  jz      short loc_180058F9C
0x180058f8f  mov     rax, [rcx+50h]
0x180058f93  test    rax, rax
0x180058f96  jnz     loc_1800590F7
0x180058f9c  xor     esi, esi
0x180058f9e  mov     edi, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x180058fa4  mov     [rbp+37h+var_68], 0
0x180058fab  test    edi, edi
0x180058fad  jz      loc_180059090
0x180058fb3  call    cs:__imp_GetCurrentThreadId
0x180058fba  nop     dword ptr [rax+rax+00h]
0x180058fbf  cmp     edi, eax
0x180058fc1  jnz     loc_180059090
0x180058fc7  xor     ecx, ecx
0x180058fc9  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180058fce  add     [rax], ebx
0x180058fd0  add     cs:?_cOLSBusy@CLSLock@@1HA, ebx; int CLSLock::_cOLSBusy
0x180058fd6  lea     rcx, [rbp+37h+var_80]; this
0x180058fda  xor     eax, eax
0x180058fdc  mov     [rbp+37h+var_64], bl
0x180058fdf  xorps   xmm0, xmm0
0x180058fe2  mov     [rbp+37h+var_58], 0
0x180058fea  test    rsi, rsi
0x180058fed  movdqa  [rbp+37h+var_50], xmm0
0x180058ff2  mov     [rbp+37h+var_40], 0
0x180058ff8  setz    al
0x180058ffb  add     cs:?g_cFCLock@@3JA, eax; long g_cFCLock
0x180059001  mov     [rbp+37h+var_60], eax
0x180059004  call    ?GetPols@CMeasurerLS@@QEAAPEAUols@Ptls6@@XZ; CMeasurerLS::GetPols(void)
0x180059009  mov     rdi, rax
0x18005900c  test    rax, rax
0x18005900f  jz      loc_1800590CB
0x180059015  movzx   eax, word ptr [rax+41Ch]
0x18005901c  mov     rsi, [rbp+37h+arg_40]
0x180059023  test    al, 20h
0x180059025  jnz     loc_1800590FF
0x18005902b  mov     rax, [rbp+37h+arg_38]
0x18005902f  mov     r9d, r14d; int
0x180059032  mov     [rsp+0D0h+var_88], rsi; struct CBreakRecLine *
0x180059037  mov     r8, r15; int *
0x18005903a  mov     [rsp+0D0h+var_90], rax; int *
0x18005903f  mov     edx, r12d; unsigned int
0x180059042  mov     rax, [rbp+37h+arg_30]
0x180059046  mov     rcx, rdi; this
0x180059049  mov     [rsp+0D0h+var_98], rax; int *
0x18005904e  mov     [rsp+0D0h+var_A0], 0; bool
0x180059053  mov     [rsp+0D0h+var_A8], 0; bool
0x180059058  mov     [rsp+0D0h+var_B0], bl; bool
0x18005905c  call    ?MeasureLine@ols@Ptls6@@QEAAJIPEAJJ_N1100PEBUCBreakRecLine@@@Z; Ptls6::ols::MeasureLine(uint,long *,long,bool,bool,bool,long *,long *,CBreakRecLine const *)
0x180059061  test    eax, eax
0x180059063  js      short loc_1800590CB
0x180059065  xor     ecx, ecx
0x180059067  cmp     eax, ebx
0x180059069  mov     rax, [rbp+37h+arg_28]
0x18005906d  setnz   cl
0x180059070  mov     [rax], ecx
0x180059072  lea     rcx, [rbp+37h+var_80]; this
0x180059076  call    ??1CMeasurerLS@@QEAA@XZ; CMeasurerLS::~CMeasurerLS(void)
0x18005907b  mov     eax, ebx
0x18005907d  add     rsp, 0A0h
0x180059084  pop     r15
0x180059086  pop     r14
0x180059088  pop     r12
0x18005908a  pop     rdi
0x18005908b  pop     rsi
0x18005908c  pop     rbx
0x18005908d  pop     rbp
0x18005908e  retn
0x180059090  xor     ecx, ecx
0x180059092  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x180059097  mov     rcx, rax; SRWLock
0x18005909a  call    cs:__imp_AcquireSRWLockExclusive
0x1800590a1  nop     dword ptr [rax+rax+00h]
0x1800590a6  call    cs:__imp_GetCurrentThreadId
0x1800590ad  nop     dword ptr [rax+rax+00h]
0x1800590b2  xor     ecx, ecx
0x1800590b4  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x1800590ba  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x1800590bf  add     [rax+4], ebx
0x1800590c2  jmp     loc_180058FD0
0x1800590c7  xor     eax, eax
0x1800590c9  jmp     short loc_18005907D
0x1800590cb  xor     ebx, ebx
0x1800590cd  jmp     short loc_180059072
0x1800590cf  xor     eax, eax
0x1800590d1  jmp     loc_180058F2D
0x1800590d6  xor     eax, eax
0x1800590d8  jmp     loc_180058F4F
0x1800590dd  xor     eax, eax
0x1800590df  jmp     loc_180058F83
0x1800590e4  mov     eax, [rcx+10h]
0x1800590e7  shr     eax, 2
0x1800590ea  and     al, bl
0x1800590ec  mov     [rbp+37h+var_70], al
0x1800590ef  mov     rax, [rcx]
0x1800590f2  jmp     loc_180058F6E
0x1800590f7  mov     rsi, [rax]
0x1800590fa  jmp     loc_180058F9E
0x1800590ff  test    rsi, rsi
0x180059102  jnz     loc_18005902B
0x180059108  mov     ecx, 0FFDFh
0x18005910d  and     ax, cx
0x180059110  mov     rcx, rdi; this
0x180059113  mov     [rdi+41Ch], ax
0x18005911a  call    ?ClearRunCache@ols@Ptls6@@QEAAXXZ; Ptls6::ols::ClearRunCache(void)
0x18005911f  jmp     loc_18005902B
```
