# TimerQCancelItem

- ea: `0x1400058c4`
- end: `0x140005913`
- name: `TimerQCancelItem`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400035b8`
- `0x140016534`

## callees

- `0x14000110c`
- `0x140005504`
- `0x1400058c4`

## pseudocode

```c
char __fastcall TimerQCancelItem(__int64 a1, __int64 *a2, int a3)
{
  PDEVICE_OBJECT v4; // rcx

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xCu, (__int64)WPP_9a0567af5d373ab1ea780e14cbd413d9_Traceguids);
  }
  return RemoveTqi((__int64)v4, a2, a3);
}

```

## disassembly

```asm
0x1400058c4  push    rbx
0x1400058c6  sub     rsp, 20h
0x1400058ca  mov     rbx, rdx
0x1400058cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400058d4  lea     rax, WPP_GLOBAL_Control
0x1400058db  cmp     rcx, rax
0x1400058de  jz      short loc_140005904
0x1400058e0  test    dword ptr [rcx+2Ch], 400h
0x1400058e7  jz      short loc_140005904
0x1400058e9  cmp     byte ptr [rcx+29h], 3
0x1400058ed  jb      short loc_140005904
0x1400058ef  mov     rcx, [rcx+18h]
0x1400058f3  lea     r8, WPP_9a0567af5d373ab1ea780e14cbd413d9_Traceguids
0x1400058fa  mov     edx, 0Ch
0x1400058ff  call    WPP_SF_
0x140005904  mov     rdx, rbx
0x140005907  call    RemoveTqi
0x14000590c  add     rsp, 20h
0x140005910  pop     rbx
0x140005911  retn
```
