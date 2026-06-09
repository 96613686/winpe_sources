# CMutex::~CMutex(void)

- ea: `0x1000ba90`
- end: `0x1000ba9e`
- name: `??1CMutex@@QAE@XZ`
- size: `14`
- prototype: `void __thiscall(CMutex *__hidden this)`
- caller_count: `75`
- callee_count: `1`
- tags: ``

## callers

- `0x1000c0d0`
- `0x1000c750`
- `0x1000ce70`
- `0x1000cff0`
- `0x1000d150`
- `0x1000d5b0`
- `0x1000d8e0`
- `0x1000ddb0`
- `0x1000e140`
- `0x1000eab0`
- `0x1000f260`
- `0x1000fc70`
- `0x1000fcf0`
- `0x10010b50`
- `0x10011380`
- `0x10011530`
- `0x100118b0`
- `0x10011d40`
- `0x100132e0`
- `0x10013890`
- `0x10014d90`
- `0x100153e0`
- `0x10016040`
- `0x10016f60`
- `0x10017160`
- `0x10017b50`
- `0x10018750`
- `0x1001a540`
- `0x1001a700`
- `0x1001a970`
- `0x1001b4a0`
- `0x1001b930`
- `0x1001d4b0`
- `0x1001d7f0`
- `0x1001df20`
- `0x1001e350`
- `0x1001ebc0`
- `0x10024630`
- `0x10024750`
- `0x10024c90`
- `0x10025180`
- `0x10026110`
- `0x10026470`
- `0x10026890`
- `0x10026d80`
- `0x10027660`
- `0x1002dca0`
- `0x1002e200`
- `0x1002e3e0`
- `0x1002ef90`

## callees

- `0x1000ba90`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1000ba97`
- `KERNEL32!LeaveCriticalSection` at `0x1000ba97`

## pseudocode

```c
void __thiscall CMutex::~CMutex(LPCRITICAL_SECTION *this)
{
  if ( *this )
    LeaveCriticalSection(*this);
}

```

## disassembly

```asm
0x1000ba90  mov     eax, [ecx]
0x1000ba92  test    eax, eax
0x1000ba94  jz      short locret_1000BA9D
0x1000ba96  push    eax; lpCriticalSection
0x1000ba97  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x1000ba9d  retn
```
