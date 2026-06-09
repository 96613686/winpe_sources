# TcpConnectComplete

- ea: `0x140023800`
- end: `0x14002386d`
- name: `TcpConnectComplete`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140006878`
- `0x140023800`
- `0x140030f80`
- `0x140040214`

## pseudocode

```c
__int64 __fastcall TcpConnectComplete(__int64 a1, __int64 a2, IRP *a3)
{
  __int64 v4; // r9
  unsigned int *v5; // rbx
  void (__fastcall *UserApcRoutine)(_QWORD, _QWORD, _QWORD, _QWORD); // rax

  v4 = a2;
  v5 = (unsigned int *)(a2 + 48);
  if ( (BYTE2(xmmword_140038420) & 0x40) != 0 )
    WPP_SF_qD(1046, 16, WPP_fa19288d55e93bdc32b2b8b93e71d639_Traceguids, a2, *v5);
  UserApcRoutine = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))a3->Overlay.AsynchronousParameters.UserApcRoutine;
  if ( UserApcRoutine )
    UserApcRoutine(a3->Overlay.AsynchronousParameters.UserApcContext, *v5, 0, v4);
  NbtFreeIrp(a3);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140023800  mov     [rsp+arg_0], rbx
0x140023805  push    rdi
0x140023806  sub     rsp, 30h
0x14002380a  mov     rdi, r8
0x14002380d  mov     r9, rdx
0x140023810  test    byte ptr cs:xmmword_140038420+2, 40h
0x140023817  lea     rbx, [rdx+30h]
0x14002381b  jnz     short loc_14002384F
0x14002381d  mov     rax, [rdi+58h]
0x140023821  test    rax, rax
0x140023824  jnz     short loc_14002383F
0x140023826  mov     rcx, rdi; Irp
0x140023829  call    NbtFreeIrp
0x14002382e  mov     rbx, [rsp+38h+arg_0]
0x140023833  mov     eax, 0C0000016h
0x140023838  add     rsp, 30h
0x14002383c  pop     rdi
0x14002383d  retn
0x14002383f  mov     edx, [rbx]
0x140023841  xor     r8d, r8d
0x140023844  mov     rcx, [rdi+60h]
0x140023848  call    _guard_dispatch_icall
0x14002384d  jmp     short loc_140023826
0x14002384f  mov     eax, [rbx]
0x140023851  lea     r8, WPP_fa19288d55e93bdc32b2b8b93e71d639_Traceguids
0x140023858  mov     edx, 10h
0x14002385d  mov     [rsp+38h+var_18], eax
0x140023861  mov     ecx, 416h
0x140023866  call    WPP_SF_qD
0x14002386b  jmp     short loc_14002381D
```
