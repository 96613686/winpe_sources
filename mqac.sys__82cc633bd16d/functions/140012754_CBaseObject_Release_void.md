# CBaseObject::Release(void)

- ea: `0x140012754`
- end: `0x1400127bd`
- name: `?Release@CBaseObject@@QEAAKXZ`
- size: `105`
- prototype: `unsigned int __fastcall(CBaseObject *__hidden this)`
- caller_count: `64`
- callee_count: `3`
- tags: ``

## callers

- `0x140003b20`
- `0x140003f74`
- `0x1400041ac`
- `0x1400058fc`
- `0x1400061fc`
- `0x140007a88`
- `0x140007cb8`
- `0x14000a2b8`
- `0x14000b28c`
- `0x14000c6c8`
- `0x14000c6e4`
- `0x14000c87c`
- `0x14000c914`
- `0x14000caf8`
- `0x14000d728`
- `0x14000d748`
- `0x14000d848`
- `0x14000da8c`
- `0x14000dc20`
- `0x14000df60`
- `0x140010524`
- `0x14001206c`
- `0x140012368`
- `0x140012c14`
- `0x140014850`
- `0x140014ef8`
- `0x140015084`
- `0x14001569c`
- `0x140015ac4`
- `0x140017884`
- `0x140017b04`
- `0x140017b90`
- `0x140017ca4`
- `0x14001821c`
- `0x14001837c`
- `0x1400183c4`
- `0x140018644`
- `0x140018a04`
- `0x140018b58`
- `0x140018b9c`
- `0x140018dc8`
- `0x140019454`
- `0x1400194ec`
- `0x1400195ac`
- `0x140019f04`
- `0x14001a460`
- `0x14001aa04`
- `0x14001c230`
- `0x14001c788`
- `0x14001c8c0`

## callees

- `0x140001010`
- `0x140012754`
- `0x140024bf0`

## pseudocode

```c
__int64 __fastcall CBaseObject::Release(CBaseObject *this)
{
  bool v2; // zf
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      11,
      WPP_f1f0d3063e6d32506fe08e0fee4801bb_Traceguids,
      this,
      *((_DWORD *)this + 2) - 1);
  }
  v2 = (*((_DWORD *)this + 2))-- == 1;
  result = *((unsigned int *)this + 2);
  if ( v2 )
  {
    (**(void (__fastcall ***)(CBaseObject *, __int64))this)(this, 1);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140012754  push    rbx
0x140012756  sub     rsp, 30h
0x14001275a  mov     rbx, rcx
0x14001275d  mov     rcx, cs:WPP_GLOBAL_Control
0x140012764  lea     rax, WPP_GLOBAL_Control
0x14001276b  cmp     rcx, rax
0x14001276e  jz      short loc_140012798
0x140012770  mov     eax, [rcx+6Ch]
0x140012773  test    al, 4
0x140012775  jz      short loc_140012798
0x140012777  mov     eax, [rbx+8]
0x14001277a  lea     r8, WPP_f1f0d3063e6d32506fe08e0fee4801bb_Traceguids
0x140012781  mov     rcx, [rcx+58h]
0x140012785  dec     eax
0x140012787  mov     edx, 0Bh
0x14001278c  mov     [rsp+38h+var_18], eax
0x140012790  mov     r9, rbx
0x140012793  call    WPP_SF_qD
0x140012798  add     dword ptr [rbx+8], 0FFFFFFFFh
0x14001279c  mov     eax, [rbx+8]
0x14001279f  jnz     short loc_1400127B6
0x1400127a1  mov     rax, [rbx]
0x1400127a4  mov     edx, 1
0x1400127a9  mov     rcx, rbx
0x1400127ac  mov     rax, [rax]
0x1400127af  call    _guard_dispatch_icall
0x1400127b4  xor     eax, eax
0x1400127b6  add     rsp, 30h
0x1400127ba  pop     rbx
0x1400127bb  retn
```
