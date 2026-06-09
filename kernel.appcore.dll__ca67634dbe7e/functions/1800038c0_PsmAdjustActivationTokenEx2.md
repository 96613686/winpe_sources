# PsmAdjustActivationTokenEx2

- ea: `0x1800038c0`
- end: `0x1800038c5`
- name: `PsmAdjustActivationTokenEx2`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800038d0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall PsmAdjustActivationTokenEx2(
        void *a1,
        int a2,
        int a3,
        WCHAR *a4,
        wchar_t *Str,
        PackageOrigin origin,
        UUID *a7,
        __int64 *a8,
        const WCHAR *a9,
        HANDLE *a10)
{
  return PsmpAdjustActivationToken(a1, a2, a3, a4, Str, origin, a7, a8, a9, a10);
}

```

## disassembly

```asm
0x1800038c0  jmp     PsmpAdjustActivationToken
```
