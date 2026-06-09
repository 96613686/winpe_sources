# HidpPolledReadComplete_TimerDriven

- ea: `0x180009b70`
- end: `0x180009be6`
- name: `HidpPolledReadComplete_TimerDriven`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180009b70`
- `0x18000ac70`
- `0x18000c250`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x180009bc7`
- `ntoskrnl!KeSetTimer` at `0x180009bc7`

## pseudocode

```c
__int64 __fastcall HidpPolledReadComplete_TimerDriven(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  unsigned int Complete; // edi
  __int64 HidclassCollection; // rax

  v3 = *(_QWORD *)(a3 + 64);
  Complete = HidpPolledReadComplete(a1, a2, a3);
  if ( *(_DWORD *)(a3 + 4) == 3 )
  {
    HidclassCollection = GetHidclassCollection(v3 + 32, *(unsigned int *)(a3 + 8));
    if ( HidclassCollection )
      KeSetTimer(
        (PKTIMER)(HidclassCollection + 88),
        (LARGE_INTEGER)((unsigned int)(-10000 * *(_DWORD *)(HidclassCollection + 80)) | 0xFFFFFFFF00000000uLL),
        (PKDPC)(HidclassCollection + 152));
  }
  return Complete;
}

```

## disassembly

```asm
0x180009b70  mov     [rsp+arg_0], rbx
0x180009b75  mov     [rsp+arg_8], rsi
0x180009b7a  push    rdi
0x180009b7b  sub     rsp, 20h
0x180009b7f  mov     rsi, [r8+40h]
0x180009b83  mov     rbx, r8
0x180009b86  call    HidpPolledReadComplete
0x180009b8b  cmp     dword ptr [rbx+4], 3
0x180009b8f  mov     edi, eax
0x180009b91  jnz     short loc_180009BD3
0x180009b93  mov     edx, [rbx+8]
0x180009b96  lea     rcx, [rsi+20h]
0x180009b9a  call    GetHidclassCollection
0x180009b9f  test    rax, rax
0x180009ba2  jz      short loc_180009BD3
0x180009ba4  imul    ecx, [rax+50h], 0FFFFD8F0h
0x180009bab  lea     r8, [rax+98h]; Dpc
0x180009bb2  mov     dword ptr [rsp+28h+DueTime+4], 0FFFFFFFFh
0x180009bba  mov     dword ptr [rsp+28h+DueTime], ecx
0x180009bbe  lea     rcx, [rax+58h]; Timer
0x180009bc2  mov     rdx, qword ptr [rsp+28h+DueTime]; DueTime
0x180009bc7  call    cs:__imp_KeSetTimer
0x180009bce  nop     dword ptr [rax+rax+00h]
0x180009bd3  mov     rbx, [rsp+28h+arg_0]
0x180009bd8  mov     eax, edi
0x180009bda  mov     rsi, [rsp+28h+arg_8]
0x180009bdf  add     rsp, 20h
0x180009be3  pop     rdi
0x180009be4  retn
```
