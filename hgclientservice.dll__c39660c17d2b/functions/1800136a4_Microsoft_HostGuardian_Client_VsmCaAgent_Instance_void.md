# Microsoft::HostGuardian::Client::VsmCaAgent::Instance(void)

- ea: `0x1800136a4`
- end: `0x18001370c`
- name: `?Instance@VsmCaAgent@Client@HostGuardian@Microsoft@@SAAEAV1234@XZ`
- size: `104`
- prototype: `struct Microsoft::HostGuardian::Client::VsmCaAgent *(void)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c574`
- `0x18000d348`
- `0x18000dc5c`
- `0x180012890`

## callees

- `0x180001b88`
- `0x180002c3c`
- `0x180002ca4`
- `0x1800125f4`
- `0x1800136a4`

## pseudocode

```c
struct Microsoft::HostGuardian::Client::VsmCaAgent *Microsoft::HostGuardian::Client::VsmCaAgent::Instance(void)
{
  Microsoft::HostGuardian::Client::VsmCaAgent *v1; // rcx

  if ( dword_180020680 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180020680);
    if ( dword_180020680 == -1 )
    {
      Microsoft::HostGuardian::Client::VsmCaAgent::VsmCaAgent(v1);
      atexit(Microsoft::HostGuardian::Client::VsmCaAgent::Instance_::_2_::_dynamic_atexit_destructor_for__s_instance__);
      Init_thread_footer(&dword_180020680);
    }
  }
  return (struct Microsoft::HostGuardian::Client::VsmCaAgent *)&qword_180020620;
}

```

## disassembly

```asm
0x1800136a4  sub     rsp, 28h
0x1800136a8  mov     ecx, cs:_tls_index
0x1800136ae  mov     rax, gs:58h
0x1800136b7  mov     edx, 4
0x1800136bc  mov     rax, [rax+rcx*8]
0x1800136c0  mov     eax, [rdx+rax]
0x1800136c3  cmp     cs:dword_180020680, eax
0x1800136c9  jg      short loc_1800136D7
0x1800136cb  lea     rax, qword_180020620
0x1800136d2  add     rsp, 28h
0x1800136d6  retn
0x1800136d7  lea     rcx, dword_180020680
0x1800136de  call    _Init_thread_header
0x1800136e3  cmp     cs:dword_180020680, 0FFFFFFFFh
0x1800136ea  jnz     short loc_1800136CB
0x1800136ec  call    ??0VsmCaAgent@Client@HostGuardian@Microsoft@@AEAA@XZ; Microsoft::HostGuardian::Client::VsmCaAgent::VsmCaAgent(void)
0x1800136f1  lea     rcx, _Microsoft__HostGuardian__Client__VsmCaAgent__Instance____2____dynamic_atexit_destructor_for__s_instance__; void (__cdecl *)()
0x1800136f8  call    atexit
0x1800136fd  nop
0x1800136fe  lea     rcx, dword_180020680
0x180013705  call    _Init_thread_footer
0x18001370a  jmp     short loc_1800136CB
```
