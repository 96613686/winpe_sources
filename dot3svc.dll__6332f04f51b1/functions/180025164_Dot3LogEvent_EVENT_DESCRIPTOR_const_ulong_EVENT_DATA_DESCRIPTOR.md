# Dot3LogEvent(_EVENT_DESCRIPTOR const *,ulong,_EVENT_DATA_DESCRIPTOR *)

- ea: `0x180025164`
- end: `0x1800251bc`
- name: `?Dot3LogEvent@@YAKPEBU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@Z`
- size: `88`
- prototype: `__int64 __fastcall(const struct _EVENT_DESCRIPTOR *, unsigned int, struct _EVENT_DATA_DESCRIPTOR *)`
- caller_count: `12`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000aac0`
- `0x18000b5e0`
- `0x180017a68`
- `0x180024e2c`
- `0x180024efc`
- `0x180024fb0`
- `0x1800250cc`
- `0x1800251c4`
- `0x180025244`
- `0x1800252b0`
- `0x180025410`
- `0x180025480`

## callees

- `0x180025164`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180025185`
- `ntdll!EtwEventEnabled` at `0x180025185`
- `ntdll!EtwEventWrite` at `0x18002519f`
- `ntdll!EtwEventWrite` at `0x18002519f`

## pseudocode

```c
__int64 __fastcall Dot3LogEvent(const struct _EVENT_DESCRIPTOR *a1, unsigned int a2, struct _EVENT_DATA_DESCRIPTOR *a3)
{
  if ( (unsigned __int8)EtwEventEnabled(DOT3SVC_EVT_GUID_Context, a1) )
    return EtwEventWrite(DOT3SVC_EVT_GUID_Context, a1, a2, a3);
  else
    return 5023;
}

```

## disassembly

```asm
0x180025164  mov     [rsp+arg_0], rbx
0x180025169  mov     [rsp+arg_8], rsi
0x18002516e  push    rdi
0x18002516f  sub     rsp, 20h
0x180025173  mov     esi, edx
0x180025175  mov     rbx, rcx
0x180025178  mov     rdx, rcx
0x18002517b  mov     rdi, r8
0x18002517e  mov     rcx, cs:DOT3SVC_EVT_GUID_Context
0x180025185  call    cs:__imp_EtwEventEnabled
0x18002518b  test    al, al
0x18002518d  jz      short loc_1800251A7
0x18002518f  mov     rcx, cs:DOT3SVC_EVT_GUID_Context
0x180025196  mov     r9, rdi
0x180025199  mov     r8d, esi
0x18002519c  mov     rdx, rbx
0x18002519f  call    cs:__imp_EtwEventWrite
0x1800251a5  jmp     short loc_1800251AC
0x1800251a7  mov     eax, 139Fh
0x1800251ac  mov     rbx, [rsp+28h+arg_0]
0x1800251b1  mov     rsi, [rsp+28h+arg_8]
0x1800251b6  add     rsp, 20h
0x1800251ba  pop     rdi
0x1800251bb  retn
```
