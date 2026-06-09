# TOKEN_KEY::GetLogonMethod(void)

- ea: `0x18000de40`
- end: `0x18000de44`
- name: `?GetLogonMethod@TOKEN_KEY@@UEBAKXZ`
- size: `4`
- prototype: `unsigned int __fastcall(TOKEN_KEY *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall TOKEN_KEY::GetLogonMethod(TOKEN_KEY *this)
{
  return *((unsigned int *)this + 30);
}

```

## disassembly

```asm
0x18000de40  mov     eax, [rcx+78h]
0x18000de43  retn
```
