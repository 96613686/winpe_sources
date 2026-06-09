# _lambda_280cd5b56449d64c91a1408b409a836e_::operator()(winrt::Windows::Graphics::Capture::Server::ICaptureServerAccessStatics const &)

- ea: `0x180014570`
- end: `0x180014590`
- name: `??R_lambda_280cd5b56449d64c91a1408b409a836e_@@QEBA@AEBUICaptureServerAccessStatics@Server@Capture@Graphics@Windows@winrt@@@Z`
- size: `32`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800137e0`
- `0x180014dd8`
- `0x18001b44c`
- `0x18001be68`

## callees

- `0x180014d74`

## pseudocode

```c
__int64 __fastcall _lambda_280cd5b56449d64c91a1408b409a836e_::operator()(_QWORD *a1, __int64 a2, __int64 a3)
{
  winrt::impl::consume_Windows_Graphics_Capture_Server_ICapturableItemStatics<winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::PickAsync(
    a3,
    a2,
    *a1);
  return a2;
}

```

## disassembly

```asm
0x180014570  push    rbx
0x180014572  sub     rsp, 30h
0x180014576  mov     rax, r8
0x180014579  mov     rbx, rdx
0x18001457c  mov     r8, [rcx]
0x18001457f  mov     rcx, rax
0x180014582  call    ?PickAsync@?$consume_Windows_Graphics_Capture_Server_ICapturableItemStatics@UICapturableItemStatics@Server@Capture@Graphics@Windows@winrt@@@impl@winrt@@QEBA@AEBUWindowId@WindowManagement@ApplicationModel@Internal@Windows@3@@Z; winrt::impl::consume_Windows_Graphics_Capture_Server_ICapturableItemStatics<winrt::Windows::Graphics::Capture::Server::ICapturableItemStatics>::PickAsync(winrt::Windows::Internal::ApplicationModel::WindowManagement::WindowId const &)
0x180014587  mov     rax, rbx
0x18001458a  add     rsp, 30h
0x18001458e  pop     rbx
0x18001458f  retn
```
