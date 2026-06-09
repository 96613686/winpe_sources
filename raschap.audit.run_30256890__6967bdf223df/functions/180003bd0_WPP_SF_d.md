# WPP_SF_d

- ea: `0x180003bd0`
- end: `0x180003c09`
- name: `WPP_SF_d`
- size: `57`
- prototype: ``
- caller_count: `102`
- callee_count: `0`
- tags: ``

## callers

- `0x180001210`
- `0x180001260`
- `0x180001520`
- `0x1800019b0`
- `0x180001bc0`
- `0x180002040`
- `0x180002530`
- `0x180002954`
- `0x180002f20`
- `0x180003200`
- `0x180003530`
- `0x1800038d0`
- `0x180003ad0`
- `0x180003c10`
- `0x180003fa0`
- `0x1800042f0`
- `0x1800045c0`
- `0x180004ac0`
- `0x180004df0`
- `0x180004f50`
- `0x180005430`
- `0x180005df0`
- `0x180006600`
- `0x180006a50`
- `0x180006c60`
- `0x180007060`
- `0x180007370`
- `0x1800084c0`
- `0x180008938`
- `0x180008cf0`
- `0x180009c08`
- `0x180009dc0`
- `0x18000a4c0`
- `0x18000b1a0`
- `0x18000b460`
- `0x18000b9b4`
- `0x18000cd68`
- `0x18000d670`
- `0x18000d930`
- `0x18000db00`
- `0x18000de60`
- `0x18000e2c8`
- `0x18000e634`
- `0x18000ead0`
- `0x18000ef70`
- `0x18000f158`
- `0x18000f300`
- `0x18000f950`
- `0x180010460`
- `0x1800105a8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180003bfe`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180003bfe`

## pseudocode

```c
ULONG __fastcall WPP_SF_d(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return TraceMessage(a1, 0x2Bu, a3, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x180003bd0  mov     [rsp+arg_18], r9d
0x180003bd5  sub     rsp, 48h
0x180003bd9  mov     [rsp+48h+var_18], 0
0x180003be2  lea     rax, [rsp+48h+arg_18]
0x180003be7  movzx   r9d, dx; MessageNumber
0x180003beb  mov     edx, 2Bh ; '+'; MessageFlags
0x180003bf0  mov     [rsp+48h+var_20], 4
0x180003bf9  mov     [rsp+48h+var_28], rax
0x180003bfe  call    cs:__imp_TraceMessage
0x180003c04  add     rsp, 48h
0x180003c08  retn
```
