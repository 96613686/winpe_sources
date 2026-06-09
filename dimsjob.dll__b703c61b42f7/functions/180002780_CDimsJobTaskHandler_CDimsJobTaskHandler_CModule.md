# CDimsJobTaskHandler::CDimsJobTaskHandler(CModule &)

- ea: `0x180002780`
- end: `0x180002857`
- name: `??0CDimsJobTaskHandler@@IEAA@AEAVCModule@@@Z`
- size: `215`
- prototype: `CDimsJobTaskHandler *__fastcall(CDimsJobTaskHandler *__hidden this, struct CModule *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180002670`

## callees

- `0x180002780`
- `0x18000a338`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800027d2`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800027d2`
- `ntdll!RtlInitializeSRWLock` at `0x180002807`
- `ntdll!RtlInitializeSRWLock` at `0x180002807`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800027bb`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800027bb`

## pseudocode

```c
CDimsJobTaskHandler *__fastcall CDimsJobTaskHandler::CDimsJobTaskHandler(CDimsJobTaskHandler *this, struct CModule *a2)
{
  char *v3; // rdi

  *((_QWORD *)this + 1) = &hModule;
  v3 = (char *)&off_180011028 + SLODWORD((*off_180011028)[1]);
  RtlAcquireSRWLockShared(&v3[*(int *)(*(_QWORD *)v3 + 4LL)]);
  _InterlockedIncrement(&dword_180011020);
  RtlReleaseSRWLockShared(&v3[*(int *)(*(_QWORD *)v3 + 4LL)]);
  *(_QWORD *)this = &CDimsJobTaskHandler::`vftable';
  *((_QWORD *)this + 2) = _CRwlock::`vbtable'{for `_CRwlock'};
  *((_QWORD *)this + 4) = &_CRwlock::`vbtable'{for `_CReader'};
  *((_QWORD *)this + 5) = &_CRwlock::`vbtable'{for `_CWriter'};
  RtlInitializeSRWLock((char *)this + 24);
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 15) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids);
  return this;
}

```

## disassembly

```asm
0x180002780  mov     [rsp+arg_0], rbx
0x180002785  mov     [rsp+arg_10], rsi
0x18000278a  push    rdi
0x18000278b  sub     rsp, 20h
0x18000278f  mov     rbx, rcx
0x180002792  lea     rdx, hModule
0x180002799  mov     [rcx+8], rdx
0x18000279d  lea     rdi, [rdx+10h]
0x1800027a1  mov     rax, cs:off_180011028
0x1800027a8  xor     esi, esi
0x1800027aa  movsxd  rcx, dword ptr [rax+8]
0x1800027ae  add     rdi, rcx
0x1800027b1  mov     rax, [rdi]
0x1800027b4  movsxd  rcx, dword ptr [rax+4]
0x1800027b8  add     rcx, rdi
0x1800027bb  call    cs:__imp_RtlAcquireSRWLockShared
0x1800027c1  lock inc cs:dword_180011020
0x1800027c8  mov     rax, [rdi]
0x1800027cb  movsxd  rcx, dword ptr [rax+4]
0x1800027cf  add     rcx, rdi
0x1800027d2  call    cs:__imp_RtlReleaseSRWLockShared
0x1800027d8  lea     rax, ??_7CDimsJobTaskHandler@@6B@; const CDimsJobTaskHandler::`vftable'
0x1800027df  mov     [rbx], rax
0x1800027e2  lea     rcx, [rbx+18h]
0x1800027e6  lea     rax, ??_8_CRwlock@@7B0@@; const _CRwlock::`vbtable'{for `_CRwlock'}
0x1800027ed  mov     [rbx+10h], rax
0x1800027f1  lea     rax, ??_8_CRwlock@@7B_CReader@@@; const _CRwlock::`vbtable'{for `_CReader'}
0x1800027f8  mov     [rbx+20h], rax
0x1800027fc  lea     rax, ??_8_CRwlock@@7B_CWriter@@@; const _CRwlock::`vbtable'{for `_CWriter'}
0x180002803  mov     [rbx+28h], rax
0x180002807  call    cs:__imp_RtlInitializeSRWLock
0x18000280d  mov     [rbx+30h], rsi
0x180002811  mov     [rbx+3Ch], esi
0x180002814  mov     rcx, cs:WPP_GLOBAL_Control
0x18000281b  lea     rax, WPP_GLOBAL_Control
0x180002822  cmp     rcx, rax
0x180002825  jz      short loc_18000282D
0x180002827  test    byte ptr [rcx+1Ch], 10h
0x18000282b  jnz     short loc_180002840
0x18000282d  mov     rsi, [rsp+28h+arg_10]
0x180002832  mov     rax, rbx
0x180002835  mov     rbx, [rsp+28h+arg_0]
0x18000283a  add     rsp, 20h
0x18000283e  pop     rdi
0x18000283f  retn
0x180002840  mov     rcx, [rcx+10h]
0x180002844  lea     r8, WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids
0x18000284b  mov     edx, 0Ah
0x180002850  call    WPP_SF_
0x180002855  jmp     short loc_18000282D
```
