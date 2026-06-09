# IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IDCompositionAnimationPartner>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IDCompositionAnimationPartner>>)

- ea: `0x180015a98`
- end: `0x180015aaf`
- name: `??$IID_PPV_ARGS_Helper@V?$ComPtr@UIDCompositionAnimationPartner@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIDCompositionAnimationPartner@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015f90`

## callees

- `0x18001630c`

## pseudocode

```c
__int64 *__fastcall IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IDCompositionAnimationPartner>>(__int64 *a1)
{
  Microsoft::WRL::ComPtr<IDCompositionAnimationTriggerPartner>::InternalRelease(a1);
  return a1;
}

```

## disassembly

```asm
0x180015a98  push    rbx
0x180015a9a  sub     rsp, 20h
0x180015a9e  mov     rbx, rcx
0x180015aa1  call    ?InternalRelease@?$ComPtr@UIDCompositionAnimationTriggerPartner@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionAnimationTriggerPartner>::InternalRelease(void)
0x180015aa6  mov     rax, rbx
0x180015aa9  add     rsp, 20h
0x180015aad  pop     rbx
0x180015aae  retn
```
