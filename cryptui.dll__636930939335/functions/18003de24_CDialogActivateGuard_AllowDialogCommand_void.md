# CDialogActivateGuard::AllowDialogCommand(void)

- ea: `0x18003de24`
- end: `0x18003de72`
- name: `?AllowDialogCommand@CDialogActivateGuard@@QEAAHXZ`
- size: `78`
- prototype: `__int64 __fastcall(CDialogActivateGuard *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18003c620`
- `0x18003d030`

## callees

- `0x18003de24`
- `0x18003e190`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003de31`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003de31`

## pseudocode

```c
__int64 __fastcall CDialogActivateGuard::AllowDialogCommand(CDialogActivateGuard *this)
{
  ULONGLONG TickCount64; // rdi
  unsigned __int64 ActivationDelay; // rcx
  __int64 result; // rax

  TickCount64 = GetTickCount64();
  ActivationDelay = CDialogActivateGuard::_GetActivationDelay(this);
  if ( !ActivationDelay || *(_QWORD *)this && TickCount64 - *(_QWORD *)this > ActivationDelay )
    return 1;
  result = 0;
  *(_QWORD *)this = TickCount64;
  return result;
}

```

## disassembly

```asm
0x18003de24  mov     [rsp+arg_0], rbx
0x18003de29  push    rdi
0x18003de2a  sub     rsp, 20h
0x18003de2e  mov     rbx, rcx
0x18003de31  call    cs:__imp_GetTickCount64
0x18003de37  mov     rcx, rbx; this
0x18003de3a  mov     rdi, rax
0x18003de3d  call    ?_GetActivationDelay@CDialogActivateGuard@@AEAA_KXZ; CDialogActivateGuard::_GetActivationDelay(void)
0x18003de42  mov     rcx, rax
0x18003de45  test    rax, rax
0x18003de48  jnz     short loc_18003DE51
0x18003de4a  mov     eax, 1
0x18003de4f  jmp     short loc_18003DE67
0x18003de51  cmp     qword ptr [rbx], 0
0x18003de55  jz      short loc_18003DE62
0x18003de57  mov     rax, rdi
0x18003de5a  sub     rax, [rbx]
0x18003de5d  cmp     rax, rcx
0x18003de60  ja      short loc_18003DE4A
0x18003de62  xor     eax, eax
0x18003de64  mov     [rbx], rdi
0x18003de67  mov     rbx, [rsp+28h+arg_0]
0x18003de6c  add     rsp, 20h
0x18003de70  pop     rdi
0x18003de71  retn
```
