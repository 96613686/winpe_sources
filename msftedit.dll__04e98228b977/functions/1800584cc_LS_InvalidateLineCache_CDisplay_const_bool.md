# LS::InvalidateLineCache(CDisplay const *,bool)

- ea: `0x1800584cc`
- end: `0x1800586c7`
- name: `?InvalidateLineCache@LS@@YAXPEBVCDisplay@@_N@Z`
- size: `507`
- prototype: `void __fastcall(LS *__hidden this, const struct CDisplay *, bool)`
- caller_count: `17`
- callee_count: `9`
- tags: ``

## callers

- `0x1800205e0`
- `0x180036ec4`
- `0x18003b04c`
- `0x18008ab1c`
- `0x180096704`
- `0x18009b294`
- `0x18009c09c`
- `0x1800a9cf0`
- `0x1800b2828`
- `0x1800b6598`
- `0x1800c1110`
- `0x1800dfcc0`
- `0x1800e2e30`
- `0x180101520`
- `0x180118fb0`
- `0x18011ba20`
- `0x18014de40`

## callees

- `0x180057560`
- `0x1800584cc`
- `0x18005912c`
- `0x1800591c8`
- `0x18005921c`
- `0x18005a524`
- `0x18005a5f8`
- `0x18005a710`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005862e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005862e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800584f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005863a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800584f2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005863a`

## pseudocode

```c
void __fastcall LS::InvalidateLineCache(LS *this, const struct CDisplay *a2)
{
  int v2; // ebx
  _DWORD *LockTelemetry; // rax
  int v5; // ecx
  __int64 v6; // rbx
  Ptls6::ols *v7; // r9
  Ptls6::ols *v8; // rbx
  __int16 v9; // ax
  __int64 v10; // rdx
  _DWORD *v11; // rax
  __int16 v12; // dx
  RTL_SRWLOCK *Lock; // rax
  __int64 v14; // rax
  int v15; // [rsp+30h] [rbp+8h] BYREF
  char v16; // [rsp+34h] [rbp+Ch]

  v2 = (int)CLockSharedData::LockOwner;
  v15 = 0;
  if ( (_DWORD)CLockSharedData::LockOwner && v2 == GetCurrentThreadId() )
  {
    LockTelemetry = (_DWORD *)CLock::GetLockTelemetry(0);
    ++*LockTelemetry;
  }
  else
  {
    Lock = (RTL_SRWLOCK *)CLockSharedOS::GetLock(0);
    AcquireSRWLockExclusive(Lock);
    LODWORD(CLockSharedData::LockOwner) = GetCurrentThreadId();
    v14 = CLock::GetLockTelemetry(0);
    ++*(_DWORD *)(v14 + 4);
  }
  v5 = CLSLock::_cOLSBusy + 1;
  v16 = 1;
  ++CLSLock::_cOLSBusy;
  if ( this && (v6 = *((_QWORD *)this + 2)) != 0 )
  {
    v7 = CLSLock::_pols;
    if ( (*(_DWORD *)(v6 + 184) & 0x40000000) != 0 )
      v8 = *(Ptls6::ols **)(v6 + 616);
    else
      v8 = CLSLock::_pols;
    if ( v8 )
    {
      v9 = *((_WORD *)v8 + 526);
      if ( v5 > 1 )
      {
        *((_WORD *)v8 + 526) = v9 | 0x10;
      }
      else
      {
        *((_WORD *)v8 + 526) = v9 & 0xFFEF;
        if ( this == *((LS **)v8 + 4) )
        {
          v10 = *((_QWORD *)v8 + 6);
          if ( v10 )
          {
            v11 = (_DWORD *)*((_QWORD *)v8 + 5);
            if ( v11 && *v11 == 977490764 && *(_DWORD **)(v10 + 8) == v11 )
            {
              Ptls6::CLsLine::Destroy(*((Ptls6::CLsLine **)v8 + 6));
              v5 = CLSLock::_cOLSBusy;
            }
            *((_QWORD *)v8 + 6) = 0;
          }
          v12 = *((_WORD *)v8 + 406);
          *((_WORD *)v8 + 92) = -1;
          if ( v12 >= 0 )
          {
            if ( qword_1802E45A8 )
            {
              (*(void (__fastcall **)(CCharFormatArray *))(*(_QWORD *)qword_1802E45A8 + 8LL))(qword_1802E45A8);
              v5 = CLSLock::_cOLSBusy;
            }
            *((_WORD *)v8 + 406) = -1;
          }
          if ( (*((_BYTE *)v8 + 1052) & 0x20) == 0 )
          {
            Ptls6::ols::ClearRunCache(v8);
            v5 = CLSLock::_cOLSBusy;
          }
        }
      }
      v7 = CLSLock::_pols;
    }
    CLSLock::_cOLSBusy = v5 - 1;
    if ( v5 == 1 && v7 && (*((_BYTE *)v7 + 1052) & 0x10) != 0 )
      Ptls6::ols::DestroyLine(v7, *((const struct CDisplay **)v7 + 4), 1);
    CWriteLock::~CWriteLock((CWriteLock *)&v15);
  }
  else
  {
    CLSLock::~CLSLock((CLSLock *)&v15);
  }
}

```

## disassembly

```asm
0x1800584cc  mov     [rsp+arg_10], rbx
0x1800584d1  mov     [rsp+arg_18], rsi
0x1800584d6  push    rdi
0x1800584d7  sub     rsp, 20h
0x1800584db  mov     ebx, dword ptr cs:?LockOwner@CLockSharedData@@2PAIA; uint near * CLockSharedData::LockOwner
0x1800584e1  xor     esi, esi
0x1800584e3  mov     [rsp+28h+arg_0], esi
0x1800584e7  mov     rdi, rcx
0x1800584ea  test    ebx, ebx
0x1800584ec  jz      loc_180058624
0x1800584f2  call    cs:__imp_GetCurrentThreadId
0x1800584f9  nop     dword ptr [rax+rax+00h]
0x1800584fe  cmp     ebx, eax
0x180058500  jnz     loc_180058624
0x180058506  xor     ecx, ecx
0x180058508  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x18005850d  inc     dword ptr [rax]
0x18005850f  mov     ecx, cs:?_cOLSBusy@CLSLock@@1HA; int CLSLock::_cOLSBusy
0x180058515  inc     ecx
0x180058517  mov     [rsp+28h+arg_4], 1
0x18005851c  mov     cs:?_cOLSBusy@CLSLock@@1HA, ecx; int CLSLock::_cOLSBusy
0x180058522  test    rdi, rdi
0x180058525  jz      loc_18005865B
0x18005852b  mov     rbx, [rdi+10h]
0x18005852f  test    rbx, rbx
0x180058532  jz      loc_18005865B
0x180058538  mov     eax, [rbx+0B8h]
0x18005853e  mov     r9, cs:?_pols@CLSLock@@1PEAUols@Ptls6@@EA; Ptls6::ols * CLSLock::_pols
0x180058545  shr     eax, 1Eh
0x180058548  test    al, 1
0x18005854a  jnz     loc_180058694
0x180058550  mov     rbx, r9
0x180058553  test    rbx, rbx
0x180058556  jz      loc_1800585EB
0x18005855c  movzx   eax, word ptr [rbx+41Ch]
0x180058563  cmp     ecx, 1
0x180058566  jg      loc_1800586A0
0x18005856c  mov     edx, 0FFEFh
0x180058571  and     ax, dx
0x180058574  mov     [rbx+41Ch], ax
0x18005857b  cmp     rdi, [rbx+20h]
0x18005857f  jnz     short loc_1800585E4
0x180058581  mov     rdx, [rbx+30h]
0x180058585  test    rdx, rdx
0x180058588  jz      short loc_1800585B3
0x18005858a  mov     rax, [rbx+28h]
0x18005858e  test    rax, rax
0x180058591  jz      short loc_1800585AF
0x180058593  cmp     dword ptr [rax], 3A43534Ch
0x180058599  jnz     short loc_1800585AF
0x18005859b  cmp     [rdx+8], rax
0x18005859f  jnz     short loc_1800585AF
0x1800585a1  mov     rcx, rdx; this
0x1800585a4  call    ?Destroy@CLsLine@Ptls6@@UEAAXXZ; Ptls6::CLsLine::Destroy(void)
0x1800585a9  mov     ecx, cs:?_cOLSBusy@CLSLock@@1HA; int CLSLock::_cOLSBusy
0x1800585af  mov     [rbx+30h], rsi
0x1800585b3  movzx   edx, word ptr [rbx+32Ch]
0x1800585ba  or      edi, 0FFFFFFFFh
0x1800585bd  mov     [rbx+0B8h], di
0x1800585c4  test    dx, dx
0x1800585c7  jns     loc_180058667
0x1800585cd  test    byte ptr [rbx+41Ch], 20h
0x1800585d4  jnz     short loc_1800585E4
0x1800585d6  mov     rcx, rbx; this
0x1800585d9  call    ?ClearRunCache@ols@Ptls6@@QEAAXXZ; Ptls6::ols::ClearRunCache(void)
0x1800585de  mov     ecx, cs:?_cOLSBusy@CLSLock@@1HA; int CLSLock::_cOLSBusy
0x1800585e4  mov     r9, cs:?_pols@CLSLock@@1PEAUols@Ptls6@@EA; Ptls6::ols * CLSLock::_pols
0x1800585eb  sub     ecx, 1
0x1800585ee  mov     cs:?_cOLSBusy@CLSLock@@1HA, ecx; int CLSLock::_cOLSBusy
0x1800585f4  jnz     short loc_180058609
0x1800585f6  test    r9, r9
0x1800585f9  jz      short loc_180058609
0x1800585fb  test    byte ptr [r9+41Ch], 10h
0x180058603  jnz     loc_1800586B0
0x180058609  lea     rcx, [rsp+28h+arg_0]; this
0x18005860e  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x180058613  mov     rbx, [rsp+28h+arg_10]
0x180058618  mov     rsi, [rsp+28h+arg_18]
0x18005861d  add     rsp, 20h
0x180058621  pop     rdi
0x180058622  retn
0x180058624  xor     ecx, ecx
0x180058626  call    ?GetLock@CLockSharedOS@@SAAEAVCOSLock@1@W4LOCK_TYPE@@@Z; CLockSharedOS::GetLock(LOCK_TYPE)
0x18005862b  mov     rcx, rax; SRWLock
0x18005862e  call    cs:__imp_AcquireSRWLockExclusive
0x180058635  nop     dword ptr [rax+rax+00h]
0x18005863a  call    cs:__imp_GetCurrentThreadId
0x180058641  nop     dword ptr [rax+rax+00h]
0x180058646  xor     ecx, ecx
0x180058648  mov     dword ptr cs:?LockOwner@CLockSharedData@@2PAIA, eax; uint near * CLockSharedData::LockOwner
0x18005864e  call    ?GetLockTelemetry@CLock@@SAPEAULOCK_TELEMETRY@@W4LOCK_TYPE@@@Z; CLock::GetLockTelemetry(LOCK_TYPE)
0x180058653  inc     dword ptr [rax+4]
0x180058656  jmp     loc_18005850F
0x18005865b  lea     rcx, [rsp+28h+arg_0]; this
0x180058660  call    ??1CLSLock@@QEAA@XZ; CLSLock::~CLSLock(void)
0x180058665  jmp     short loc_180058613
0x180058667  mov     r8, cs:qword_1802E45A8
0x18005866e  test    r8, r8
0x180058671  jz      short loc_180058688
0x180058673  mov     rax, [r8]
0x180058676  mov     rcx, r8
0x180058679  mov     rax, [rax+8]
0x18005867d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058682  mov     ecx, cs:?_cOLSBusy@CLSLock@@1HA; int CLSLock::_cOLSBusy
0x180058688  mov     [rbx+32Ch], di
0x18005868f  jmp     loc_1800585CD
0x180058694  mov     rbx, [rbx+268h]
0x18005869b  jmp     loc_180058553
0x1800586a0  or      ax, 10h
0x1800586a4  mov     [rbx+41Ch], ax
0x1800586ab  jmp     loc_1800585E4
0x1800586b0  mov     rdx, [r9+20h]; struct CDisplay *
0x1800586b4  mov     r8d, 1; int
0x1800586ba  mov     rcx, r9; this
0x1800586bd  call    ?DestroyLine@ols@Ptls6@@QEAAXPEBVCDisplay@@H@Z; Ptls6::ols::DestroyLine(CDisplay const *,int)
0x1800586c2  jmp     loc_180058609
```
