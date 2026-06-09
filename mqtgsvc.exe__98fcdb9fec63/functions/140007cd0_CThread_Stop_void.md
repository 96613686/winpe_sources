# CThread::Stop(void)

- ea: `0x140007cd0`
- end: `0x140007d18`
- name: `?Stop@CThread@@QEAA_NXZ`
- size: `72`
- prototype: `bool __fastcall(CThread *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b5a0`
- `0x14000c0e0`
- `0x14000c850`

## callees

- `0x140007554`
- `0x140007cd0`

## pseudocode

```c
bool __fastcall CThread::Stop(CThread *this)
{
  bool result; // al

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids);
  result = *((_BYTE *)this + 72);
  *((_BYTE *)this + 72) = 0;
  return result;
}

```

## disassembly

```asm
0x140007cd0  push    rbx
0x140007cd2  sub     rsp, 20h
0x140007cd6  mov     rbx, rcx
0x140007cd9  mov     rcx, cs:WPP_GLOBAL_Control
0x140007ce0  lea     rax, WPP_GLOBAL_Control
0x140007ce7  cmp     rcx, rax
0x140007cea  jz      short loc_140007D0B
0x140007cec  test    byte ptr [rcx+1Ch], 4
0x140007cf0  jz      short loc_140007D0B
0x140007cf2  mov     r9d, [rbx+18h]
0x140007cf6  lea     r8, WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids
0x140007cfd  mov     rcx, [rcx+10h]
0x140007d01  mov     edx, 15h
0x140007d06  call    WPP_SF_d
0x140007d0b  mov     al, [rbx+48h]
0x140007d0e  mov     byte ptr [rbx+48h], 0
0x140007d12  add     rsp, 20h
0x140007d16  pop     rbx
0x140007d17  retn
```
