# ACCreateRemoteCursor

- ea: `0x1400057f4`
- end: `0x1400058f5`
- name: `ACCreateRemoteCursor`
- size: `257`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, CProxy *this, volatile void *Address)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000a3b0`

## callees

- `0x140001c34`
- `0x140003994`
- `0x1400057f4`
- `0x14000b5d8`
- `0x14001a564`
- `0x14001b9e0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140005815`
- `ntoskrnl!ProbeForRead` at `0x140005815`

## pseudocode

```c
__int64 __fastcall ACCreateRemoteCursor(struct _DEVICE_OBJECT *a1, CProxy *this, int *Address)
{
  int v6; // eax
  unsigned int v7; // ebx

  ProbeForRead(Address, 8u, 1u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_DD(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      92,
      &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
      (unsigned int)Address[1],
      *Address);
  }
  v6 = CQueueBase::Validate(this);
  v7 = v6;
  if ( v6 >= 0 )
    return CProxy::CreateRemoteCursor((CProxy ***)this, a1, Address[1], *Address);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_Dq(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      93,
      &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
      (unsigned int)v6,
      this);
  }
  return v7;
}

```

## disassembly

```asm
0x1400057f4  push    rbx
0x1400057f6  push    rsi
0x1400057f7  push    rdi
0x1400057f8  push    r14
0x1400057fa  push    r15
0x1400057fc  sub     rsp, 30h
0x140005800  mov     rdi, r8
0x140005803  mov     rsi, rdx
0x140005806  mov     r14, rcx
0x140005809  mov     edx, 8; Length
0x14000580e  lea     r8d, [rdx-7]; Alignment
0x140005812  mov     rcx, rdi; Address
0x140005815  call    cs:__imp_ProbeForRead
0x14000581c  nop     dword ptr [rax+rax+00h]
0x140005821  lea     r15, WPP_GLOBAL_Control
0x140005828  mov     rcx, cs:WPP_GLOBAL_Control
0x14000582f  cmp     rcx, r15
0x140005832  jz      short loc_14000585A
0x140005834  mov     eax, [rcx+6Ch]
0x140005837  test    al, 4
0x140005839  jz      short loc_14000585A
0x14000583b  mov     edx, 5Ch ; '\'
0x140005840  mov     eax, [rdi]
0x140005842  mov     dword ptr [rsp+58h+var_38], eax
0x140005846  mov     r9d, [rdi+4]
0x14000584a  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005851  mov     rcx, [rcx+58h]
0x140005855  call    WPP_SF_DD
0x14000585a  mov     rcx, rsi; struct CQueueBase *
0x14000585d  call    ?Validate@CQueueBase@@SAJPEBV1@@Z; CQueueBase::Validate(CQueueBase const *)
0x140005862  mov     ebx, eax
0x140005864  test    eax, eax
0x140005866  jns     short loc_14000589D
0x140005868  mov     rcx, cs:WPP_GLOBAL_Control
0x14000586f  cmp     rcx, r15
0x140005872  jz      short loc_140005899
0x140005874  mov     edx, [rcx+6Ch]
0x140005877  test    dl, 1
0x14000587a  jz      short loc_140005899
0x14000587c  mov     edx, 5Dh ; ']'
0x140005881  mov     [rsp+58h+var_38], rsi
0x140005886  mov     r9d, eax
0x140005889  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005890  mov     rcx, [rcx+58h]
0x140005894  call    WPP_SF_Dq
0x140005899  mov     eax, ebx
0x14000589b  jmp     short loc_1400058E8
0x14000589d  mov     r9d, [rdi]; unsigned int
0x1400058a0  mov     r8d, [rdi+4]; unsigned int
0x1400058a4  mov     rdx, r14; struct _DEVICE_OBJECT *
0x1400058a7  mov     rcx, rsi; this
0x1400058aa  call    ?CreateRemoteCursor@CProxy@@UEAAJPEAU_DEVICE_OBJECT@@KK@Z; CProxy::CreateRemoteCursor(_DEVICE_OBJECT *,ulong,ulong)
0x1400058af  jmp     short loc_1400058E8
0x1400058b1  mov     ebx, eax
0x1400058b3  lea     rax, WPP_GLOBAL_Control
0x1400058ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400058c1  cmp     rcx, rax
0x1400058c4  jz      short loc_1400058E6
0x1400058c6  mov     edx, [rcx+6Ch]
0x1400058c9  test    dl, 1
0x1400058cc  jz      short loc_1400058E6
0x1400058ce  mov     edx, 5Eh ; '^'
0x1400058d3  mov     r9d, ebx
0x1400058d6  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400058dd  mov     rcx, [rcx+58h]
0x1400058e1  call    WPP_SF_d
0x1400058e6  mov     eax, ebx
0x1400058e8  add     rsp, 30h
0x1400058ec  pop     r15
0x1400058ee  pop     r14
0x1400058f0  pop     rdi
0x1400058f1  pop     rsi
0x1400058f2  pop     rbx
0x1400058f3  retn
```
