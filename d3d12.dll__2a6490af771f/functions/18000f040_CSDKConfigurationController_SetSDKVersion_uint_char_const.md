# CSDKConfigurationController::SetSDKVersion(uint,char const *)

- ea: `0x18000f040`
- end: `0x18000f0df`
- name: `?SetSDKVersion@CSDKConfigurationController@@UEAAJIPEBD@Z`
- size: `159`
- prototype: `int(CSDKConfigurationController *__hidden this, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000ae80`
- `0x18000afcc`
- `0x18000afec`
- `0x18000f040`
- `0x180013750`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CSDKConfigurationController::SetSDKVersion(
        CSDKConfigurationController *this,
        unsigned int a2,
        const char *a3)
{
  __int64 v5; // rcx
  __int64 v6; // r9
  unsigned int v7; // ebx
  int v9; // [rsp+58h] [rbp+20h] BYREF

  Smtx_lock_exclusive(&qword_18001E7F8);
  v9 = 0;
  if ( (int)((__int64 (__fastcall *)(int *))pfnIsDeveloperModeEnabled)(&v9) >= 0 && v9 )
  {
    LODWORD(qword_18001E828) = 1;
    v7 = CModule::SetSDKVersion((CModule *)&g_Module, a2, a3);
  }
  else
  {
    LODWORD(qword_18001E828) = 0;
    CJournal::RecordJournal(
      v5,
      -2005270527,
      "D3D12: SetSDKVersion is only available when developer mode is enabled.",
      v6,
      1);
    v7 = -2005270527;
  }
  Smtx_unlock_exclusive(&qword_18001E7F8);
  return v7;
}

```

## disassembly

```asm
0x18000f040  mov     [rsp+arg_0], rbx
0x18000f045  push    rdi
0x18000f046  sub     rsp, 30h
0x18000f04a  mov     rbx, r8
0x18000f04d  mov     edi, edx
0x18000f04f  lea     rcx, qword_18001E7F8; _Smtx_t *
0x18000f056  call    _Smtx_lock_exclusive
0x18000f05b  mov     [rsp+38h+arg_18], 0
0x18000f063  lea     rcx, [rsp+38h+arg_18]
0x18000f068  mov     rax, cs:?pfnIsDeveloperModeEnabled@@3P6AJPEAH@ZEA; long (*pfnIsDeveloperModeEnabled)(int *)
0x18000f06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f074  test    eax, eax
0x18000f076  js      short loc_18000F09E
0x18000f078  cmp     [rsp+38h+arg_18], 0
0x18000f07d  jz      short loc_18000F09E
0x18000f07f  mov     dword ptr cs:qword_18001E828, 1
0x18000f089  mov     r8, rbx; char *
0x18000f08c  mov     edx, edi; unsigned int
0x18000f08e  lea     rcx, ?g_Module@@3VCModule@@A; this
0x18000f095  call    ?SetSDKVersion@CModule@@QEAAJIPEBD@Z; CModule::SetSDKVersion(uint,char const *)
0x18000f09a  mov     ebx, eax
0x18000f09c  jmp     short loc_18000F0C6
0x18000f09e  mov     dword ptr cs:qword_18001E828, 0
0x18000f0a8  mov     [rsp+38h+var_18], 1
0x18000f0b0  lea     r8, aD3d12Setsdkver; "D3D12: SetSDKVersion is only available "...
0x18000f0b7  mov     edx, 887A0001h
0x18000f0bc  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18000f0c1  mov     ebx, 887A0001h
0x18000f0c6  lea     rcx, qword_18001E7F8; _Smtx_t *
0x18000f0cd  call    _Smtx_unlock_exclusive
0x18000f0d2  mov     eax, ebx
0x18000f0d4  mov     rbx, [rsp+38h+arg_0]
0x18000f0d9  add     rsp, 30h
0x18000f0dd  pop     rdi
0x18000f0de  retn
```
