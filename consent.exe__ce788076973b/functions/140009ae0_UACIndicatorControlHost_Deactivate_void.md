# UACIndicatorControlHost::Deactivate(void)

- ea: `0x140009ae0`
- end: `0x140009b23`
- name: `?Deactivate@UACIndicatorControlHost@@QEAAXXZ`
- size: `67`
- prototype: `void __fastcall(UACIndicatorControlHost *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001e940`

## callees

- `0x140009ae0`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x140009b04`
- `USER32!PostThreadMessageW` at `0x140009b04`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140009b13`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140009b13`

## pseudocode

```c
void __fastcall UACIndicatorControlHost::Deactivate(UACIndicatorControlHost *this)
{
  if ( *((_QWORD *)this + 1) )
  {
    PostThreadMessageW(*((_DWORD *)this + 4), 0x12u, 0, 0);
    WaitForSingleObject(*((HANDLE *)this + 1), 0x1388u);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x140009ae0  push    rbx
0x140009ae2  sub     rsp, 20h
0x140009ae6  cmp     qword ptr [rcx+8], 0
0x140009aeb  mov     rbx, rcx
0x140009aee  jnz     short loc_140009AF6
0x140009af0  add     rsp, 20h
0x140009af4  pop     rbx
0x140009af5  retn
0x140009af6  mov     ecx, [rcx+10h]; idThread
0x140009af9  xor     r9d, r9d; lParam
0x140009afc  xor     r8d, r8d; wParam
0x140009aff  mov     edx, 12h; Msg
0x140009b04  call    cs:__imp_PostThreadMessageW
0x140009b0a  mov     rcx, [rbx+8]; hHandle
0x140009b0e  mov     edx, 1388h; dwMilliseconds
0x140009b13  call    cs:__imp_WaitForSingleObject
0x140009b19  mov     qword ptr [rbx+8], 0
0x140009b21  jmp     short loc_140009AF0
```
