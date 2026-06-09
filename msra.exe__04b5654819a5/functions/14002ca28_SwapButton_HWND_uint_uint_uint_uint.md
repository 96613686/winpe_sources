# SwapButton(HWND__ *,uint,uint,uint,uint)

- ea: `0x14002ca28`
- end: `0x14002cb41`
- name: `?SwapButton@@YAJPEAUHWND__@@IIII@Z`
- size: `281`
- prototype: `__int64 __usercall@<rax>(HWND hWnd@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001ba74`
- `0x14001ec30`
- `0x140020e6c`
- `0x140023830`

## callees

- `0x140002463`
- `0x14002ca28`
- `0x140034ce4`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14002ca80`
- `KERNEL32!GetModuleHandleW` at `0x14002ca80`
- `USER32!SendMessageW` at `0x14002cb15`
- `USER32!SendMessageW` at `0x14002cb15`
- `USER32!LoadStringW` at `0x14002ca9c`
- `USER32!LoadStringW` at `0x14002ca9c`

## string_xrefs

- `0x14002cac4`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c

```
