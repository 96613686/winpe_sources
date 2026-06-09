# CSslUserContext::GetPostHandshakeAuthExtensionReceived(void)

- ea: `0x14000af40`
- end: `0x14000af47`
- name: `?GetPostHandshakeAuthExtensionReceived@CSslUserContext@@UEAAEXZ`
- size: `7`
- prototype: `unsigned __int8 __fastcall(CSslUserContext *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
unsigned __int8 __fastcall CSslUserContext::GetPostHandshakeAuthExtensionReceived(CSslUserContext *this)
{
  return *((_BYTE *)this + 504);
}

```

## disassembly

```asm
0x14000af40  mov     al, [rcx+1F8h]
0x14000af46  retn
```
