# CThread::Resume(void)

- ea: `0x140007c78`
- end: `0x140007cc9`
- name: `?Resume@CThread@@QEAA_NXZ`
- size: `81`
- prototype: `bool __fastcall(HANDLE *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b43c`
- `0x14000e768`

## callees

- `0x140007554`
- `0x140007c78`

## import_xrefs

- `KERNEL32!ResumeThread` at `0x140007cb7`
- `KERNEL32!ResumeThread` at `0x140007cb7`

## pseudocode

```c
bool __fastcall CThread::Resume(HANDLE *this)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids);
  return ResumeThread(this[4]) != -1;
}

```

## disassembly

```asm
0x140007c78  push    rbx
0x140007c7a  sub     rsp, 20h
0x140007c7e  mov     rbx, rcx
0x140007c81  mov     rcx, cs:WPP_GLOBAL_Control
0x140007c88  lea     rax, WPP_GLOBAL_Control
0x140007c8f  cmp     rcx, rax
0x140007c92  jz      short loc_140007CB3
0x140007c94  test    byte ptr [rcx+1Ch], 4
0x140007c98  jz      short loc_140007CB3
0x140007c9a  mov     r9d, [rbx+18h]
0x140007c9e  lea     r8, WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids
0x140007ca5  mov     rcx, [rcx+10h]
0x140007ca9  mov     edx, 0Eh
0x140007cae  call    WPP_SF_d
0x140007cb3  mov     rcx, [rbx+20h]; hThread
0x140007cb7  call    cs:__imp_ResumeThread
0x140007cbd  cmp     eax, 0FFFFFFFFh
0x140007cc0  setnz   al
0x140007cc3  add     rsp, 20h
0x140007cc7  pop     rbx
0x140007cc8  retn
```
