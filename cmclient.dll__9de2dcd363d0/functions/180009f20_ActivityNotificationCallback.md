# ActivityNotificationCallback

- ea: `0x180009f20`
- end: `0x180009f58`
- name: `ActivityNotificationCallback`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000700c`
- `0x180009f20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009f32`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009f32`

## string_xrefs

- `0x180009f46`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall ActivityNotificationCallback(_DWORD *a1, __int64 a2)
{
  int v2; // eax
  void *v3; // rcx
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !*a1 )
  {
    v2 = a1[1];
    v3 = *(void **)(a2 + 8);
    *(_DWORD *)a2 = v2;
    if ( !SetEvent(v3) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
  }
}

```

## disassembly

```asm
0x180009f20  sub     rsp, 28h
0x180009f24  cmp     dword ptr [rcx], 0
0x180009f27  jnz     short loc_180009F3C
0x180009f29  mov     eax, [rcx+4]
0x180009f2c  mov     rcx, [rdx+8]; hEvent
0x180009f30  mov     [rdx], eax
0x180009f32  call    cs:__imp_SetEvent
0x180009f38  test    eax, eax
0x180009f3a  jz      short loc_180009F41
0x180009f3c  add     rsp, 28h
0x180009f40  retn
0x180009f41  mov     rcx, [rsp+28h]; this
0x180009f46  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009f4d  mov     edx, 0A01h; void *
0x180009f52  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
