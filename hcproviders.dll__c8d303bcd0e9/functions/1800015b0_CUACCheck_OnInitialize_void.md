# CUACCheck::_OnInitialize(void)

- ea: `0x1800015b0`
- end: `0x180001664`
- name: `?_OnInitialize@CUACCheck@@MEAAJXZ`
- size: `180`
- prototype: `__int64 __fastcall(CUACCheck *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800015b0`
- `0x180001670`
- `0x1800019f0`
- `0x180004a4c`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800015fa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800015fa`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180001620`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180001620`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000162f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000162f`

## pseudocode

```c
__int64 __fastcall CUACCheck::_OnInitialize(CUACCheck *this)
{
  int UACState; // eax
  __int64 result; // rax
  unsigned int v4; // ebx
  struct _TP_WORK *ThreadpoolWork; // rsi

  UACState = CUACCheck::s_GetUACState();
  result = CCheckBase::_SetState(this, (const struct HCSTATE *)(&CUACCheck::c_rgStates + 10 * UACState), 0);
  v4 = result;
  if ( (int)result >= 0 )
  {
    ThreadpoolWork = CreateThreadpoolWork((PTP_WORK_CALLBACK)CUACCheck::s_InitalizeWorkCallback, this, 0);
    if ( ThreadpoolWork )
    {
      (*(void (__fastcall **)(CUACCheck *))(*(_QWORD *)this + 8LL))(this);
      SubmitThreadpoolWork(ThreadpoolWork);
      CloseThreadpoolWork(ThreadpoolWork);
      return v4;
    }
    else
    {
      return ResultFromKnownLastError();
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800015b0  mov     [rsp+arg_8], rbx
0x1800015b5  push    rdi
0x1800015b6  sub     rsp, 20h
0x1800015ba  mov     rdi, rcx
0x1800015bd  call    ?s_GetUACState@CUACCheck@@CA?AW4UACSTATE@1@XZ; CUACCheck::s_GetUACState(void)
0x1800015c2  movsxd  rdx, eax
0x1800015c5  xor     r8d, r8d; bool
0x1800015c8  lea     rax, ?c_rgStates@CUACCheck@@0QBUHCSTATE@@B; HCSTATE const near * const CUACCheck::c_rgStates
0x1800015cf  mov     rcx, rdi; this
0x1800015d2  lea     rdx, [rdx+rdx*4]
0x1800015d6  shl     rdx, 4
0x1800015da  add     rdx, rax; struct HCSTATE *
0x1800015dd  call    ?_SetState@CCheckBase@@IEAAJPEBUHCSTATE@@_N@Z; CCheckBase::_SetState(HCSTATE const *,bool)
0x1800015e2  mov     ebx, eax
0x1800015e4  test    eax, eax
0x1800015e6  js      short loc_180001658
0x1800015e8  xor     r8d, r8d; pcbe
0x1800015eb  mov     [rsp+28h+arg_0], rsi
0x1800015f0  mov     rdx, rdi; pv
0x1800015f3  lea     rcx, ?s_InitalizeWorkCallback@CUACCheck@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800015fa  call    cs:__imp_CreateThreadpoolWork
0x180001601  nop     dword ptr [rax+rax+00h]
0x180001606  mov     rsi, rax
0x180001609  test    rax, rax
0x18000160c  jz      short loc_18000164E
0x18000160e  mov     rcx, [rdi]
0x180001611  mov     rax, [rcx+8]
0x180001615  mov     rcx, rdi
0x180001618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000161d  mov     rcx, rsi; pwk
0x180001620  call    cs:__imp_SubmitThreadpoolWork
0x180001627  nop     dword ptr [rax+rax+00h]
0x18000162c  mov     rcx, rsi; pwk
0x18000162f  call    cs:__imp_CloseThreadpoolWork
0x180001636  nop     dword ptr [rax+rax+00h]
0x18000163b  mov     rsi, [rsp+28h+arg_0]
0x180001640  mov     eax, ebx
0x180001642  mov     rbx, [rsp+28h+arg_8]
0x180001647  add     rsp, 20h
0x18000164b  pop     rdi
0x18000164c  retn
0x18000164e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180001653  mov     rsi, [rsp+28h+arg_0]
0x180001658  mov     rbx, [rsp+28h+arg_8]
0x18000165d  add     rsp, 20h
0x180001661  pop     rdi
0x180001662  retn
```
