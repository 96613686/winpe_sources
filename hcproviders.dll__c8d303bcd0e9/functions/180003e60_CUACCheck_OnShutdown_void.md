# CUACCheck::_OnShutdown(void)

- ea: `0x180003e60`
- end: `0x180003ed7`
- name: `?_OnShutdown@CUACCheck@@MEAAXXZ`
- size: `119`
- prototype: `void __fastcall(CUACCheck *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180003e60`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180003e8c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180003e8c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180003e9b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180003e9b`
- `SHELL32!SHEnableServiceObject` at `0x180003eb0`
- `SHELL32!SHEnableServiceObject` at `0x180003eb0`

## pseudocode

```c
void __fastcall CUACCheck::_OnShutdown(CUACCheck *this)
{
  struct _TP_WAIT *v1; // rdi

  v1 = (struct _TP_WAIT *)*((_QWORD *)this + 29);
  if ( v1 )
  {
    *((_QWORD *)this + 29) = 0;
    WaitForThreadpoolWaitCallbacks(v1, 1);
    CloseThreadpoolWait(v1);
    SHEnableServiceObject(qword_18000D690, 0);
    (*(void (__fastcall **)(CUACCheck *))(*(_QWORD *)this + 16LL))(this);
  }
}

```

## disassembly

```asm
0x180003e60  mov     [rsp+arg_0], rbx
0x180003e65  push    rdi
0x180003e66  sub     rsp, 20h
0x180003e6a  mov     rdi, [rcx+0E8h]
0x180003e71  mov     rbx, rcx
0x180003e74  test    rdi, rdi
0x180003e77  jz      short loc_180003ECB
0x180003e79  mov     qword ptr [rcx+0E8h], 0
0x180003e84  mov     edx, 1; fCancelPendingCallbacks
0x180003e89  mov     rcx, rdi; pwa
0x180003e8c  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180003e93  nop     dword ptr [rax+rax+00h]
0x180003e98  mov     rcx, rdi; pwa
0x180003e9b  call    cs:__imp_CloseThreadpoolWait
0x180003ea2  nop     dword ptr [rax+rax+00h]
0x180003ea7  xor     edx, edx
0x180003ea9  lea     rcx, qword_18000D690
0x180003eb0  call    cs:__imp_SHEnableServiceObject
0x180003eb7  nop     dword ptr [rax+rax+00h]
0x180003ebc  mov     rax, [rbx]
0x180003ebf  mov     rcx, rbx
0x180003ec2  mov     rax, [rax+10h]
0x180003ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ecb  mov     rbx, [rsp+28h+arg_0]
0x180003ed0  add     rsp, 20h
0x180003ed4  pop     rdi
0x180003ed5  retn
```
