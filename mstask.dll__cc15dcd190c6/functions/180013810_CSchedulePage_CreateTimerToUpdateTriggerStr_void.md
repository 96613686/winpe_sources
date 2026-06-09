# CSchedulePage::_CreateTimerToUpdateTriggerStr(void)

- ea: `0x180013810`
- end: `0x180013847`
- name: `?_CreateTimerToUpdateTriggerStr@CSchedulePage@@AEAAXXZ`
- size: `55`
- prototype: `void __fastcall(CSchedulePage *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180014aa0`
- `0x1800154c0`
- `0x1800159c0`
- `0x180015aa0`

## callees

- `0x180013810`

## import_xrefs

- `USER32!SetTimer` at `0x180013834`
- `USER32!SetTimer` at `0x180013834`

## pseudocode

```c
void __fastcall CSchedulePage::_CreateTimerToUpdateTriggerStr(CSchedulePage *this)
{
  if ( !*((_QWORD *)this + 93) )
    *((_QWORD *)this + 93) = SetTimer(*((HWND *)this + 14), 1u, 0x5DCu, 0);
}

```

## disassembly

```asm
0x180013810  push    rbx
0x180013812  sub     rsp, 20h
0x180013816  cmp     qword ptr [rcx+2E8h], 0
0x18001381e  mov     rbx, rcx
0x180013821  jnz     short loc_180013841
0x180013823  mov     rcx, [rcx+70h]; hWnd
0x180013827  xor     r9d, r9d; lpTimerFunc
0x18001382a  mov     r8d, 5DCh; uElapse
0x180013830  lea     edx, [r9+1]; nIDEvent
0x180013834  call    cs:__imp_SetTimer
0x18001383a  mov     [rbx+2E8h], rax
0x180013841  add     rsp, 20h
0x180013845  pop     rbx
0x180013846  retn
```
