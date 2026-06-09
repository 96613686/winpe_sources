# WppCleanupUm

- ea: `0x1800065a8`
- end: `0x1800065ff`
- name: `WppCleanupUm`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005510`
- `0x180005b10`

## callees

- `0x1800065a8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1800065d0`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1800065d0`

## pseudocode

```c
ULONG WppCleanupUm()
{
  _QWORD *v0; // rbx
  TRACEHANDLE v1; // rcx
  ULONG result; // eax

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    while ( v0 )
    {
      v1 = v0[1];
      if ( v1 )
      {
        result = UnregisterTraceGuids(v1);
        v0[1] = 0;
      }
      v0 = (_QWORD *)*v0;
    }
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
  }
  return result;
}

```

## disassembly

```asm
0x1800065a8  mov     [rsp+arg_0], rbx
0x1800065ad  push    rdi
0x1800065ae  sub     rsp, 20h
0x1800065b2  mov     rbx, cs:WPP_GLOBAL_Control
0x1800065b9  lea     rdi, WPP_GLOBAL_Control
0x1800065c0  cmp     rbx, rdi
0x1800065c3  jz      short loc_1800065F3
0x1800065c5  jmp     short loc_1800065E7
0x1800065c7  mov     rcx, [rbx+8]; RegistrationHandle
0x1800065cb  test    rcx, rcx
0x1800065ce  jz      short loc_1800065E4
0x1800065d0  call    cs:__imp_UnregisterTraceGuids
0x1800065d7  nop     dword ptr [rax+rax+00h]
0x1800065dc  mov     qword ptr [rbx+8], 0
0x1800065e4  mov     rbx, [rbx]
0x1800065e7  test    rbx, rbx
0x1800065ea  jnz     short loc_1800065C7
0x1800065ec  mov     cs:WPP_GLOBAL_Control, rdi
0x1800065f3  mov     rbx, [rsp+28h+arg_0]
0x1800065f8  add     rsp, 20h
0x1800065fc  pop     rdi
0x1800065fd  retn
```
