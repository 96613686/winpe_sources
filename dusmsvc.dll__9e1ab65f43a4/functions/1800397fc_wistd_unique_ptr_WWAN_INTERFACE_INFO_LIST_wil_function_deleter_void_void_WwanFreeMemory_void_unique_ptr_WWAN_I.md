# wistd::unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>::~unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>(void)

- ea: `0x1800397fc`
- end: `0x18003981d`
- name: `??1?$unique_ptr@UWWAN_INTERFACE_INFO_LIST@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18004990b`
- `0x18004991d`
- `0x18004992f`
- `0x180049953`
- `0x180049c23`
- `0x180049c47`
- `0x180049c6b`
- `0x180049cb3`
- `0x180049d0d`
- `0x180049d31`

## callees

- `0x1800397fc`

## import_xrefs

- `wwapi!WwanFreeMemory` at `0x180039812`
- `wwapi!WwanFreeMemory` at `0x180039812`

## pseudocode

```c
__int64 __fastcall wistd::unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>::~unique_ptr<WWAN_INTERFACE_INFO_LIST,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>(
        __int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  *a1 = 0;
  if ( result )
    return WwanFreeMemory(result);
  return result;
}

```

## disassembly

```asm
0x1800397fc  sub     rsp, 28h
0x180039800  mov     rax, [rcx]
0x180039803  mov     qword ptr [rcx], 0
0x18003980a  test    rax, rax
0x18003980d  jz      short loc_180039818
0x18003980f  mov     rcx, rax
0x180039812  call    cs:__imp_WwanFreeMemory
0x180039818  add     rsp, 28h
0x18003981c  retn
```
