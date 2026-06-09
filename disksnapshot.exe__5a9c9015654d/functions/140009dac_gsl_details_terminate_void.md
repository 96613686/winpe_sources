# gsl::details::terminate(void)

- ea: `0x140009dac`
- end: `0x140009db7`
- name: `?terminate@details@gsl@@YAXXZ`
- size: `11`
- prototype: `void __fastcall __noreturn(gsl::details *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140007c84`
- `0x140008a38`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x140009db0`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x140009db0`

## pseudocode

```c
void __fastcall __noreturn gsl::details::terminate(gsl::details *this)
{
  _o_terminate(this);
  JUMPOUT(0x140009DB6LL);
}

```

## disassembly

```asm
0x140009dac  sub     rsp, 28h
0x140009db0  call    cs:__imp__o_terminate
```
