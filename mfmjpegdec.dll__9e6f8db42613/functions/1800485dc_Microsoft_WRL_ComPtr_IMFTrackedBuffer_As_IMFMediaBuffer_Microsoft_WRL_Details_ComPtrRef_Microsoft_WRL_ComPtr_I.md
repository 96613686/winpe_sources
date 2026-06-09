# Microsoft::WRL::ComPtr<IMFTrackedBuffer>::As<IMFMediaBuffer>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IMFMediaBuffer>>)

- ea: `0x1800485dc`
- end: `0x180048625`
- name: `??$As@UIMFMediaBuffer@@@?$ComPtr@UIMFTrackedBuffer@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIMFMediaBuffer@@@WRL@Microsoft@@@Details@12@@Z`
- size: `73`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800483f8`
- `0x1800492f0`
- `0x18004e4ec`
- `0x18004f9d0`
- `0x180052d30`

## callees

- `0x180020598`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<IMFTrackedBuffer>::As<IMFMediaBuffer>(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64 *),
        __int64 *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64 *); // rdi

  v3 = *a1;
  v4 = ***a1;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
  return v4(v3, &GUID_045fa593_8799_42b8_bc8d_8968c6453507, a2);
}

```

## disassembly

```asm
0x1800485dc  mov     [rsp+arg_0], rbx
0x1800485e1  mov     [rsp+arg_8], rsi
0x1800485e6  push    rdi
0x1800485e7  sub     rsp, 20h
0x1800485eb  mov     rbx, rdx
0x1800485ee  mov     rsi, [rcx]
0x1800485f1  mov     rax, [rsi]
0x1800485f4  mov     rdi, [rax]
0x1800485f7  mov     rcx, rdx
0x1800485fa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800485ff  mov     r8, rbx
0x180048602  lea     rdx, _GUID_045fa593_8799_42b8_bc8d_8968c6453507
0x180048609  mov     rcx, rsi
0x18004860c  mov     rax, rdi
0x18004860f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048614  nop
0x180048615  mov     rbx, [rsp+28h+arg_0]
0x18004861a  mov     rsi, [rsp+28h+arg_8]
0x18004861f  add     rsp, 20h
0x180048623  pop     rdi
0x180048624  retn
```
