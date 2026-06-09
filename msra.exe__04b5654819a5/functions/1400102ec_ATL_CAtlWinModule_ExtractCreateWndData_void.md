# ATL::CAtlWinModule::ExtractCreateWndData(void)

- ea: `0x1400102ec`
- end: `0x140010374`
- name: `?ExtractCreateWndData@CAtlWinModule@ATL@@QEAAPEAXXZ`
- size: `136`
- prototype: `void *__fastcall(ATL::CAtlWinModule *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140017d00`
- `0x140017db0`

## callees

- `0x1400102ec`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140010317`
- `KERNEL32!GetCurrentThreadId` at `0x140010317`
- `KERNEL32!LeaveCriticalSection` at `0x140010359`
- `KERNEL32!LeaveCriticalSection` at `0x140010359`
- `KERNEL32!EnterCriticalSection` at `0x1400102fd`
- `KERNEL32!EnterCriticalSection` at `0x1400102fd`

## pseudocode

```c
__int64 __fastcall ATL::CAtlWinModule::ExtractCreateWndData(ATL::CAtlWinModule *this)
{
  __int64 v1; // rbx
  __int64 v2; // rdi
  DWORD CurrentThreadId; // edx
  __int64 v4; // rcx
  __int64 v5; // rax

  EnterCriticalSection(&stru_140063978);
  v1 = qword_1400639A0;
  v2 = 0;
  if ( qword_1400639A0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    v4 = 0;
    while ( 1 )
    {
      v5 = *(_QWORD *)(v1 + 16);
      if ( *(_DWORD *)(v1 + 8) == CurrentThreadId )
        break;
      v4 = v1;
      v1 = *(_QWORD *)(v1 + 16);
      if ( !v5 )
        goto LABEL_10;
    }
    if ( v4 )
      *(_QWORD *)(v4 + 16) = v5;
    else
      qword_1400639A0 = *(_QWORD *)(v1 + 16);
    v2 = *(_QWORD *)v1;
  }
LABEL_10:
  LeaveCriticalSection(&stru_140063978);
  return v2;
}

```

## disassembly

```asm
0x1400102ec  mov     [rsp+arg_0], rbx
0x1400102f1  push    rdi
0x1400102f2  sub     rsp, 20h
0x1400102f6  lea     rcx, stru_140063978; lpCriticalSection
0x1400102fd  call    cs:__imp_EnterCriticalSection
0x140010304  nop     dword ptr [rax+rax+00h]
0x140010309  mov     rbx, cs:qword_1400639A0
0x140010310  xor     edi, edi
0x140010312  test    rbx, rbx
0x140010315  jz      short loc_140010352
0x140010317  call    cs:__imp_GetCurrentThreadId
0x14001031e  nop     dword ptr [rax+rax+00h]
0x140010323  mov     edx, eax
0x140010325  xor     ecx, ecx
0x140010327  mov     rax, [rbx+10h]
0x14001032b  cmp     [rbx+8], edx
0x14001032e  jz      short loc_14001033D
0x140010330  mov     rcx, rbx
0x140010333  mov     rbx, rax
0x140010336  test    rax, rax
0x140010339  jnz     short loc_140010327
0x14001033b  jmp     short loc_140010352
0x14001033d  test    rcx, rcx
0x140010340  jnz     short loc_14001034B
0x140010342  mov     cs:qword_1400639A0, rax
0x140010349  jmp     short loc_14001034F
0x14001034b  mov     [rcx+10h], rax
0x14001034f  mov     rdi, [rbx]
0x140010352  lea     rcx, stru_140063978; lpCriticalSection
0x140010359  call    cs:__imp_LeaveCriticalSection
0x140010360  nop     dword ptr [rax+rax+00h]
0x140010365  mov     rbx, [rsp+28h+arg_0]
0x14001036a  mov     rax, rdi
0x14001036d  add     rsp, 20h
0x140010371  pop     rdi
0x140010372  retn
```
