# MQGetResourceHandle(void)

- ea: `0x1800016f0`
- end: `0x1800016f8`
- name: `?MQGetResourceHandle@@YAPEAUHINSTANCE__@@XZ`
- size: `8`
- prototype: `HINSTANCE(void)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
HINSTANCE MQGetResourceHandle(void)
{
  return g_hInstance;
}

```

## disassembly

```asm
0x1800016f0  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800016f7  retn
```
