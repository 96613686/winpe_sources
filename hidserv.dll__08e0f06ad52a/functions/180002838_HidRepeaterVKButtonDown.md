# HidRepeaterVKButtonDown

- ea: `0x180002838`
- end: `0x18000290a`
- name: `HidRepeaterVKButtonDown`
- size: `210`
- prototype: `BOOL __fastcall(UINT_PTR uIDEvent, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003594`

## callees

- `0x180002838`
- `0x180004920`
- `0x18000534c`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x180002886`
- `KERNEL32!WaitForSingleObject` at `0x180002886`
- `KERNEL32!ReleaseMutex` at `0x180002903`
- `USER32!KillTimer` at `0x1800028dc`
- `USER32!KillTimer` at `0x1800028dc`
- `USER32!SetTimer` at `0x1800028c6`
- `USER32!SetTimer` at `0x1800028c6`

## pseudocode

```c
BOOL __fastcall HidRepeaterVKButtonDown(UINT_PTR uIDEvent, __int64 a2, __int64 a3)
{
  char v3; // bp
  __int16 v4; // si
  UINT_PTR v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rcx

  v3 = a3;
  v4 = a2;
  v5 = (unsigned int)uIDEvent;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (unsigned int)(__int16)a2, uIDEvent);
  }
  WaitForSingleObject(hMutexOOC, 0xFFFFFFFF);
  v7 = (unsigned int)(v5 - 3);
  if ( v4 )
  {
    if ( !OOC_State[(unsigned int)(v5 - 3)] )
    {
      LOBYTE(v6) = v3;
      SendVK(v6, 1);
      OOC_State[v7] = SetTimer(hWndHidServ, v5, INITIAL_WAIT, 0);
    }
  }
  else
  {
    KillTimer(hWndHidServ, v5);
    OOC_State[v7] = 0;
    LOBYTE(v8) = v3;
    SendVK(v8, 0);
  }
  return ReleaseMutex(hMutexOOC);
}

```

## disassembly

```asm
0x180002838  push    rbx
0x18000283a  push    rbp
0x18000283b  push    rsi
0x18000283c  push    rdi
0x18000283d  push    r14
0x18000283f  push    r15
0x180002841  sub     rsp, 38h
0x180002845  mov     bpl, r8b
0x180002848  movsx   esi, dx
0x18000284b  mov     ebx, ecx
0x18000284d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002854  lea     rax, WPP_GLOBAL_Control
0x18000285b  cmp     rcx, rax
0x18000285e  jz      short loc_18000287C
0x180002860  test    byte ptr [rcx+1Ch], 10h
0x180002864  jz      short loc_18000287C
0x180002866  cmp     byte ptr [rcx+19h], 4
0x18000286a  jb      short loc_18000287C
0x18000286c  mov     rcx, [rcx+10h]
0x180002870  mov     r9d, esi
0x180002873  mov     [rsp+68h+var_48], ebx
0x180002877  call    WPP_SF_dd
0x18000287c  mov     rcx, cs:hMutexOOC; hHandle
0x180002883  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002886  call    cs:__imp_WaitForSingleObject
0x18000288c  xor     r14d, r14d
0x18000288f  lea     eax, [rbx-3]
0x180002892  mov     edi, eax
0x180002894  lea     r15, OOC_State
0x18000289b  test    si, si
0x18000289e  jz      short loc_1800028D2
0x1800028a0  cmp     [r15+rax*8], r14
0x1800028a4  jnz     short loc_1800028F0
0x1800028a6  lea     edx, [r14+1]
0x1800028aa  mov     cl, bpl
0x1800028ad  call    SendVK
0x1800028b2  mov     r8d, cs:INITIAL_WAIT; uElapse
0x1800028b9  mov     rdx, rbx; nIDEvent
0x1800028bc  mov     rcx, cs:hWndHidServ; hWnd
0x1800028c3  xor     r9d, r9d; lpTimerFunc
0x1800028c6  call    cs:__imp_SetTimer
0x1800028cc  mov     [r15+rdi*8], rax
0x1800028d0  jmp     short loc_1800028F0
0x1800028d2  mov     rcx, cs:hWndHidServ; hWnd
0x1800028d9  mov     rdx, rbx; uIDEvent
0x1800028dc  call    cs:__imp_KillTimer
0x1800028e2  xor     edx, edx
0x1800028e4  mov     [r15+rdi*8], r14
0x1800028e8  mov     cl, bpl
0x1800028eb  call    SendVK
0x1800028f0  mov     rcx, cs:hMutexOOC
0x1800028f7  add     rsp, 38h
0x1800028fb  pop     r15
0x1800028fd  pop     r14
0x1800028ff  pop     rdi
0x180002900  pop     rsi
0x180002901  pop     rbp
0x180002902  pop     rbx
0x180002903  jmp     cs:__imp_ReleaseMutex
```
