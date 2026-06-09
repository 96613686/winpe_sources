# std::_Ref_count_obj2<FingerprintCollectorTimer>::_Ref_count_obj2<FingerprintCollectorTimer>(unsigned __int64 const &)

- ea: `0x18001f5ac`
- end: `0x18001f733`
- name: `??$?0AEB_K@?$_Ref_count_obj2@VFingerprintCollectorTimer@@@std@@QEAA@AEB_K@Z`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800210ec`

## callees

- `0x18000270c`
- `0x1800179bc`
- `0x18001f5ac`
- `0x18001f798`
- `0x180020f74`
- `0x180033054`
- `0x180033ac4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f66b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f66b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f684`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001f684`

## string_xrefs

- `0x18001f721`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\FingerprintCollectorTimers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Ref_count_obj2<FingerprintCollectorTimer>::_Ref_count_obj2<FingerprintCollectorTimer>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v3; // rdi
  __int64 v4; // rbx
  _QWORD *v5; // rsi
  HANDLE ProcessHeap; // rax
  char *v7; // rax
  char *v8; // rbx
  signed int v9; // edi
  _QWORD v11[6]; // [rsp+20h] [rbp-40h] BYREF
  __int16 v12; // [rsp+50h] [rbp-10h]
  int v13; // [rsp+52h] [rbp-Eh]
  __int16 v14; // [rsp+56h] [rbp-Ah]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  *(_DWORD *)(a1 + 8) = 1;
  *(_DWORD *)(a1 + 12) = 1;
  *(_QWORD *)a1 = &std::_Ref_count_obj2<FingerprintCollectorTimer>::`vftable';
  v3 = a1 + 16;
  v4 = *a2;
  Microsoft::Bluetooth::Foundation::AsyncObjectBase::AsyncObjectBase((Microsoft::Bluetooth::Foundation::AsyncObjectBase *)(a1 + 16));
  *(_DWORD *)(v3 + 24) = 1718641519;
  *(_QWORD *)(v3 + 32) = 0;
  *(_QWORD *)(v3 + 40) = 0;
  *(_QWORD *)(v3 + 48) = 0;
  *(_QWORD *)(v3 + 56) = 0;
  v5 = (_QWORD *)(v3 + 64);
  *(_QWORD *)(v3 + 64) = 0;
  *(_QWORD *)v3 = &FingerprintCollectorTimer::`vftable';
  *(_QWORD *)(v3 + 72) = v4;
  Microsoft::Bluetooth::Foundation::StateMachineTimer::Make();
  *(_QWORD *)(v3 + 96) = 30;
  v13 = 0;
  v14 = 0;
  v11[0] = &FingerprintCollectorStateMachine<FingerprintCollectorTimer>::c_specification;
  v11[1] = v3 + 64;
  v12 = 257;
  memset(&v11[2], 0, 24);
  v11[5] = FingerprintCollectorStateMachine<FingerprintCollectorTimer>::EvtMachineDestroyedThunk;
  ProcessHeap = GetProcessHeap();
  v7 = (char *)HeapAlloc(ProcessHeap, 0, 0x420u);
  v8 = v7;
  if ( v7 )
  {
    memset_0(v7, 0, 0x420u);
    *(_WORD *)(v8 + 965) = 257;
    v8[967] = 2;
    *((_QWORD *)v8 + 129) = 0;
    *((_QWORD *)v8 + 130) = 0;
    *v5 = v8;
    *((_QWORD *)v8 + 131) = v5;
    v9 = SmFx::StateMachineEngine::StateMachineEngineImpl::Initialize(
           (SmFx::StateMachineEngine::StateMachineEngineImpl *)v8,
           (const struct SmFx::STATE_MACHINE_ENGINE_CONFIG *)v11);
    if ( v9 < 0 )
    {
      SmFx::StateMachineEngine::StateMachineEngineImpl::Destroy(
        (SmFx::StateMachineEngine::StateMachineEngineImpl *)v8,
        0);
      *v5 = 0;
    }
    else
    {
      v9 = 0;
    }
  }
  else
  {
    v9 = -1073741670;
  }
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\FingerprintCollectorTimers.h",
      (const char *)(unsigned int)v9,
      v11[0]);
  return a1;
}

```

## disassembly

```asm
0x18001f5ac  mov     [rsp-18h+arg_8], rbx
0x18001f5b1  mov     [rsp-18h+arg_10], rsi
0x18001f5b6  mov     [rsp-18h+arg_18], rdi
0x18001f5bb  push    rbp
0x18001f5bc  push    r14
0x18001f5be  push    r15
0x18001f5c0  mov     rbp, rsp
0x18001f5c3  sub     rsp, 60h
0x18001f5c7  mov     r14, rcx
0x18001f5ca  xor     r15d, r15d
0x18001f5cd  mov     dword ptr [rcx+8], 1
0x18001f5d4  mov     dword ptr [rcx+0Ch], 1
0x18001f5db  lea     rax, ??_7?$_Ref_count_obj2@VFingerprintCollectorTimer@@@std@@6B@; const std::_Ref_count_obj2<FingerprintCollectorTimer>::`vftable'
0x18001f5e2  mov     [rcx], rax
0x18001f5e5  lea     rdi, [rcx+10h]
0x18001f5e9  mov     [rbp+arg_0], rdi
0x18001f5ed  mov     rbx, [rdx]
0x18001f5f0  mov     rcx, rdi; this
0x18001f5f3  call    ??0AsyncObjectBase@Foundation@Bluetooth@Microsoft@@QEAA@XZ; Microsoft::Bluetooth::Foundation::AsyncObjectBase::AsyncObjectBase(void)
0x18001f5f8  mov     dword ptr [rdi+18h], 6670636Fh
0x18001f5ff  mov     [rdi+20h], r15
0x18001f603  mov     [rdi+28h], r15
0x18001f607  mov     [rdi+30h], r15
0x18001f60b  mov     [rdi+38h], r15
0x18001f60f  lea     rsi, [rdi+40h]
0x18001f613  mov     [rsi], r15
0x18001f616  lea     rax, ??_7FingerprintCollectorTimer@@6B@; const FingerprintCollectorTimer::`vftable'
0x18001f61d  mov     [rdi], rax
0x18001f620  mov     [rdi+48h], rbx
0x18001f624  lea     rcx, [rdi+50h]
0x18001f628  call    ?Make@StateMachineTimer@Foundation@Bluetooth@Microsoft@@SA@XZ; Microsoft::Bluetooth::Foundation::StateMachineTimer::Make(void)
0x18001f62d  nop
0x18001f62e  mov     qword ptr [rdi+60h], 1Eh
0x18001f636  mov     [rbp+var_E], r15d
0x18001f63a  mov     [rbp+var_A], r15w
0x18001f63f  lea     rax, ?c_specification@?$FingerprintCollectorStateMachine@VFingerprintCollectorTimer@@@@0USTATE_MACHINE_SPECIFICATION@SmFx@@B; SmFx::STATE_MACHINE_SPECIFICATION const FingerprintCollectorStateMachine<FingerprintCollectorTimer>::c_specification
0x18001f646  mov     [rbp+var_40], rax
0x18001f64a  mov     [rbp+var_38], rsi
0x18001f64e  mov     [rbp+var_10], 101h
0x18001f654  mov     [rbp+var_30], r15
0x18001f658  mov     [rbp+var_28], r15
0x18001f65c  mov     [rbp+var_20], r15
0x18001f660  lea     rax, ?EvtMachineDestroyedThunk@?$FingerprintCollectorStateMachine@VFingerprintCollectorTimer@@@@CAXPEAX@Z; FingerprintCollectorStateMachine<FingerprintCollectorTimer>::EvtMachineDestroyedThunk(void *)
0x18001f667  mov     [rbp+var_18], rax
0x18001f66b  call    cs:__imp_GetProcessHeap
0x18001f672  nop     dword ptr [rax+rax+00h]
0x18001f677  mov     rcx, rax; hHeap
0x18001f67a  mov     edi, 420h
0x18001f67f  mov     r8d, edi; dwBytes
0x18001f682  xor     edx, edx; dwFlags
0x18001f684  call    cs:__imp_HeapAlloc
0x18001f68b  nop     dword ptr [rax+rax+00h]
0x18001f690  mov     rbx, rax
0x18001f693  test    rax, rax
0x18001f696  jnz     short loc_18001F69F
0x18001f698  mov     edi, 0C000009Ah
0x18001f69d  jmp     short loc_18001F6F8
0x18001f69f  mov     r8, rdi; Size
0x18001f6a2  xor     edx, edx; Val
0x18001f6a4  mov     rcx, rbx; void *
0x18001f6a7  call    memset_0
0x18001f6ac  mov     word ptr [rbx+3C5h], 101h
0x18001f6b5  mov     byte ptr [rbx+3C7h], 2
0x18001f6bc  mov     [rbx+408h], r15
0x18001f6c3  mov     [rbx+410h], r15
0x18001f6ca  mov     [rsi], rbx
0x18001f6cd  mov     [rbx+418h], rsi
0x18001f6d4  lea     rdx, [rbp+var_40]; struct SmFx::STATE_MACHINE_ENGINE_CONFIG *
0x18001f6d8  mov     rcx, rbx; this
0x18001f6db  call    ?Initialize@StateMachineEngineImpl@StateMachineEngine@SmFx@@AEAAJAEBUSTATE_MACHINE_ENGINE_CONFIG@3@@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::Initialize(SmFx::STATE_MACHINE_ENGINE_CONFIG const &)
0x18001f6e0  mov     edi, eax
0x18001f6e2  test    eax, eax
0x18001f6e4  js      short loc_18001F6EB
0x18001f6e6  mov     edi, r15d
0x18001f6e9  jmp     short loc_18001F6F8
0x18001f6eb  xor     edx, edx; bool
0x18001f6ed  mov     rcx, rbx; this
0x18001f6f0  call    ?Destroy@StateMachineEngineImpl@StateMachineEngine@SmFx@@QEAAX_N@Z; SmFx::StateMachineEngine::StateMachineEngineImpl::Destroy(bool)
0x18001f6f5  mov     [rsi], r15
0x18001f6f8  mov     rcx, [rbp+18h]; this
0x18001f6fc  test    edi, edi
0x18001f6fe  js      short loc_18001F71E
0x18001f700  mov     rax, r14
0x18001f703  lea     r11, [rsp+60h+var_s0]
0x18001f708  mov     rbx, [r11+28h]
0x18001f70c  mov     rsi, [r11+30h]
0x18001f710  mov     rdi, [r11+38h]
0x18001f714  mov     rsp, r11
0x18001f717  pop     r15
0x18001f719  pop     r14
0x18001f71b  pop     rbp
0x18001f71c  retn
0x18001f71e  mov     r9d, edi; char *
0x18001f721  lea     r8, aOnecoreDrivers; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x18001f728  mov     edx, 19h; void *
0x18001f72d  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
