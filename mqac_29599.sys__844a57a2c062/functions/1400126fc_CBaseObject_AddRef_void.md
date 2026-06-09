# CBaseObject::AddRef(void)

- ea: `0x1400126fc`
- end: `0x14001274d`
- name: `?AddRef@CBaseObject@@QEAAKXZ`
- size: `81`
- prototype: `unsigned int __fastcall(CBaseObject *__hidden this)`
- caller_count: `32`
- callee_count: `2`
- tags: ``

## callers

- `0x140004314`
- `0x140007a88`
- `0x140007cb8`
- `0x14000c914`
- `0x14000caf8`
- `0x14000d96c`
- `0x140012368`
- `0x140014a58`
- `0x140014ef8`
- `0x1400152d0`
- `0x140015490`
- `0x14001569c`
- `0x140017884`
- `0x140017b04`
- `0x140017b90`
- `0x140017ca4`
- `0x140018150`
- `0x14001837c`
- `0x140018644`
- `0x140018b58`
- `0x140018c5c`
- `0x140018dc8`
- `0x140019348`
- `0x140019454`
- `0x1400194ec`
- `0x1400195ac`
- `0x14001a220`
- `0x14001dd80`
- `0x14001dfb4`
- `0x14001f3dc`
- `0x14001f4e0`
- `0x14001f8d4`

## callees

- `0x140001010`
- `0x1400126fc`

## pseudocode

```c
__int64 __fastcall CBaseObject::AddRef(CBaseObject *this)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_qD(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      10,
      &WPP_f1f0d3063e6d32506fe08e0fee4801bb_Traceguids,
      this,
      *((_DWORD *)this + 2) + 1);
  }
  return (unsigned int)++*((_DWORD *)this + 2);
}

```

## disassembly

```asm
0x1400126fc  push    rbx
0x1400126fe  sub     rsp, 30h
0x140012702  mov     rbx, rcx
0x140012705  mov     rcx, cs:WPP_GLOBAL_Control
0x14001270c  lea     rax, WPP_GLOBAL_Control
0x140012713  cmp     rcx, rax
0x140012716  jz      short loc_140012740
0x140012718  mov     eax, [rcx+6Ch]
0x14001271b  test    al, 4
0x14001271d  jz      short loc_140012740
0x14001271f  mov     eax, [rbx+8]
0x140012722  lea     r8, WPP_f1f0d3063e6d32506fe08e0fee4801bb_Traceguids
0x140012729  mov     rcx, [rcx+58h]
0x14001272d  inc     eax
0x14001272f  mov     edx, 0Ah
0x140012734  mov     [rsp+38h+var_18], eax
0x140012738  mov     r9, rbx
0x14001273b  call    WPP_SF_qD
0x140012740  inc     dword ptr [rbx+8]
0x140012743  mov     eax, [rbx+8]
0x140012746  add     rsp, 30h
0x14001274a  pop     rbx
0x14001274b  retn
```
