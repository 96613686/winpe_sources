# std::thread::_Start<void (Rdp::Utils::TP::details::CCompletionPortIo::*)(void),Rdp::Utils::TP::details::CCompletionPortIo *>(void (Rdp::Utils::TP::details::CCompletionPortIo::*&&)(void),Rdp::Utils::TP::details::CCompletionPortIo * &&)

- ea: `0x18000f008`
- end: `0x18000f09d`
- name: `??$_Start@P8CCompletionPortIo@details@TP@Utils@Rdp@@EAAXXZPEAV12345@@thread@std@@AEAAX$$QEAP8CCompletionPortIo@details@TP@Utils@Rdp@@EAAXXZ$$QEAPEAV23456@@Z`
- size: `149`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000deac`
- `0x18000dfdc`
- `0x18000e10c`

## callees

- `0x180003714`
- `0x1800092b0`
- `0x18000f008`
- `0x18000fc6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000f05b`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000f05b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::thread::_Start<void (Rdp::Utils::TP::details::CCompletionPortIo::*)(void),Rdp::Utils::TP::details::CCompletionPortIo *>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *v6; // rax
  __int64 v7; // rax
  _QWORD *v9; // [rsp+40h] [rbp+8h] BYREF

  v6 = operator new(0x10u);
  *v6 = *a3;
  v6[1] = *a2;
  v9 = v6;
  v7 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke<std::tuple<void (Rdp::Utils::TP::details::CCompletionPortIo::*)(void),Rdp::Utils::TP::details::CCompletionPortIo *>,0,1>,
         v6,
         0,
         a1 + 8);
  *(_QWORD *)a1 = v7;
  if ( !v7 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    std::_Throw_Cpp_error(6);
  }
  v9 = 0;
  return std::unique_ptr<std::tuple<void (Rdp::Utils::TP::details::CCompletionPortIo::*)(void),Rdp::Utils::TP::details::CCompletionPortIo *>>::~unique_ptr<std::tuple<void (Rdp::Utils::TP::details::CCompletionPortIo::*)(void),Rdp::Utils::TP::details::CCompletionPortIo *>>(&v9);
}

```

## disassembly

```asm
0x18000f008  mov     [rsp+arg_8], rbx
0x18000f00d  mov     [rsp+arg_10], rsi
0x18000f012  push    rdi
0x18000f013  sub     rsp, 30h
0x18000f017  mov     rbx, r8
0x18000f01a  mov     rdi, rdx
0x18000f01d  mov     rsi, rcx
0x18000f020  mov     ecx, 10h; Size
0x18000f025  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f02a  mov     r8, [rbx]
0x18000f02d  mov     [rax], r8
0x18000f030  mov     rdx, [rdi]
0x18000f033  mov     [rax+8], rdx
0x18000f037  mov     [rsp+38h+arg_0], rax
0x18000f03c  lea     rbx, [rsi+8]
0x18000f040  mov     [rsp+38h+var_10], rbx
0x18000f045  mov     [rsp+38h+var_18], 0
0x18000f04d  mov     r9, rax
0x18000f050  lea     r8, ??$_Invoke@V?$tuple@P8CCompletionPortIo@details@TP@Utils@Rdp@@EAAXXZPEAV12345@@std@@$0A@$00@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<void (Rdp::Utils::TP::details::CCompletionPortIo::*)(void),Rdp::Utils::TP::details::CCompletionPortIo *>,0,1>(void *)
0x18000f057  xor     edx, edx
0x18000f059  xor     ecx, ecx
0x18000f05b  call    cs:__imp__o__beginthreadex
0x18000f061  mov     [rsi], rax
0x18000f064  test    rax, rax
0x18000f067  jz      short loc_18000F08C
0x18000f069  mov     [rsp+38h+arg_0], 0
0x18000f072  lea     rcx, [rsp+38h+arg_0]
0x18000f077  call    ??1?$unique_ptr@V?$tuple@P8CCompletionPortIo@details@TP@Utils@Rdp@@EAAXXZPEAV12345@@std@@U?$default_delete@V?$tuple@P8CCompletionPortIo@details@TP@Utils@Rdp@@EAAXXZPEAV12345@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::tuple<void (Rdp::Utils::TP::details::CCompletionPortIo::*)(void),Rdp::Utils::TP::details::CCompletionPortIo *>>::~unique_ptr<std::tuple<void (Rdp::Utils::TP::details::CCompletionPortIo::*)(void),Rdp::Utils::TP::details::CCompletionPortIo *>>(void)
0x18000f07c  mov     rbx, [rsp+38h+arg_8]
0x18000f081  mov     rsi, [rsp+38h+arg_10]
0x18000f086  add     rsp, 30h
0x18000f08a  pop     rdi
0x18000f08b  retn
0x18000f08c  mov     dword ptr [rbx], 0
0x18000f092  mov     ecx, 6; int
0x18000f097  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
