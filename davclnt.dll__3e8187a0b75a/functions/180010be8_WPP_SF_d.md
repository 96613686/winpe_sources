# WPP_SF_d

- ea: `0x180010be8`
- end: `0x180010c1f`
- name: `WPP_SF_d`
- size: `55`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, int)`
- caller_count: `46`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001010`
- `0x180001310`
- `0x180001600`
- `0x1800028f0`
- `0x180002970`
- `0x1800033f0`
- `0x1800036d0`
- `0x180003b90`
- `0x180004340`
- `0x180004bd0`
- `0x1800051e0`
- `0x1800056e0`
- `0x180005a50`
- `0x180006290`
- `0x180006930`
- `0x180006c50`
- `0x1800071c0`
- `0x180007450`
- `0x180007ad0`
- `0x180009f20`
- `0x18000b494`
- `0x18000b4f0`
- `0x18000b8dc`
- `0x18000ba88`
- `0x18000bcc0`
- `0x18000c170`
- `0x18000c264`
- `0x18000c500`
- `0x18000c7e0`
- `0x18000c980`
- `0x18000cb10`
- `0x18000ceb0`
- `0x18000d0ec`
- `0x18000d5f0`
- `0x18000e494`
- `0x18000ec54`
- `0x18000f154`
- `0x18000f260`
- `0x18000f2d0`
- `0x18000f690`
- `0x18000f7f0`
- `0x18000fd30`
- `0x180010504`
- `0x18001068c`
- `0x180011438`
- `0x180011718`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180010c14`
- `ntdll!EtwTraceMessage` at `0x180010c14`

## pseudocode

```c
__int64 __fastcall WPP_SF_d(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, a3, a2, &v5);
}

```

## disassembly

```asm
0x180010be8  mov     r11, rsp
0x180010beb  mov     [r11+20h], r9d
0x180010bef  sub     rsp, 48h
0x180010bf3  mov     qword ptr [r11-18h], 0
0x180010bfb  lea     rax, [r11+20h]
0x180010bff  movzx   r9d, dx
0x180010c03  mov     edx, 2Bh ; '+'
0x180010c08  mov     qword ptr [r11-20h], 4
0x180010c10  mov     [r11-28h], rax
0x180010c14  call    cs:__imp_EtwTraceMessage
0x180010c1a  add     rsp, 48h
0x180010c1e  retn
```
