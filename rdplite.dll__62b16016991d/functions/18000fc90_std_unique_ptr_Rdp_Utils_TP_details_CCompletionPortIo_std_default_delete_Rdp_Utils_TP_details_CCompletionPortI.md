# std::unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo,std::default_delete<Rdp::Utils::TP::details::CCompletionPortIo>>::~unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo,std::default_delete<Rdp::Utils::TP::details::CCompletionPortIo>>(void)

- ea: `0x18000fc90`
- end: `0x18000fca6`
- name: `??1?$unique_ptr@VCCompletionPortIo@details@TP@Utils@Rdp@@U?$default_delete@VCCompletionPortIo@details@TP@Utils@Rdp@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e45c`
- `0x18000e5fc`
- `0x18000e794`
- `0x18000fb68`
- `0x180028c0b`

## callees

- `0x18000fc90`
- `0x1800100d4`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>::~unique_ptr<Rdp::Utils::TP::details::CCompletionPortIo>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<Rdp::Utils::TP::details::CCompletionPortIo>::operator()();
  return result;
}

```

## disassembly

```asm
0x18000fc90  sub     rsp, 28h
0x18000fc94  mov     rdx, [rcx]
0x18000fc97  test    rdx, rdx
0x18000fc9a  jz      short loc_18000FCA1
0x18000fc9c  call    ??R?$default_delete@VCCompletionPortIo@details@TP@Utils@Rdp@@@std@@QEBAXPEAVCCompletionPortIo@details@TP@Utils@Rdp@@@Z; std::default_delete<Rdp::Utils::TP::details::CCompletionPortIo>::operator()(Rdp::Utils::TP::details::CCompletionPortIo *)
0x18000fca1  add     rsp, 28h
0x18000fca5  retn
```
