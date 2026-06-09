# CStr::Empty(void)

- ea: `0x18000931c`
- end: `0x18000938b`
- name: `?Empty@CStr@@QEAAXXZ`
- size: `111`
- prototype: `void __fastcall(CStr *__hidden this)`
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x180003b30`
- `0x180003c40`
- `0x180004240`
- `0x180005aa0`
- `0x180005c00`
- `0x180005dbc`
- `0x180008b70`
- `0x180008f5c`
- `0x180009054`
- `0x180009148`
- `0x18000afc0`

## callees

- `0x180007dec`
- `0x18000931c`
- `0x180009e74`

## pseudocode

```c
void __fastcall CStr::Empty(CStr *this)
{
  unsigned __int16 near **v2; // rdx

  if ( *((_DWORD *)this + 6) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_46616a5bce583dfc538f214383f522c0_Traceguids);
    }
  }
  else
  {
    v2 = (unsigned __int16 near **)*((_QWORD *)this + 1);
    if ( v2 != &CStr::s_rgwchEmptyStringBuffer )
    {
      CHeapFactory::Free(this, v2);
      *((_QWORD *)this + 1) = &CStr::s_rgwchEmptyStringBuffer;
    }
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x18000931c  mov     [rsp+arg_0], rbx
0x180009321  push    rsi
0x180009322  sub     rsp, 20h
0x180009326  cmp     dword ptr [rcx+18h], 0
0x18000932a  mov     rbx, rcx
0x18000932d  jz      short loc_18000935F
0x18000932f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009336  lea     rax, WPP_GLOBAL_Control
0x18000933d  cmp     rcx, rax
0x180009340  jz      short loc_180009380
0x180009342  cmp     byte ptr [rcx+19h], 1
0x180009346  jb      short loc_180009380
0x180009348  mov     rcx, [rcx+10h]
0x18000934c  lea     r8, WPP_46616a5bce583dfc538f214383f522c0_Traceguids
0x180009353  mov     edx, 17h
0x180009358  call    WPP_SF_
0x18000935d  jmp     short loc_180009380
0x18000935f  mov     rdx, [rcx+8]; void *
0x180009363  lea     rsi, ?s_rgwchEmptyStringBuffer@CStr@@0PAGA; ushort near * CStr::s_rgwchEmptyStringBuffer
0x18000936a  cmp     rdx, rsi
0x18000936d  jz      short loc_180009378
0x18000936f  call    ?Free@CHeapFactory@@QEAAHPEAX@Z; CHeapFactory::Free(void *)
0x180009374  mov     [rbx+8], rsi
0x180009378  mov     qword ptr [rbx+10h], 0
0x180009380  mov     rbx, [rsp+28h+arg_0]
0x180009385  add     rsp, 20h
0x180009389  pop     rsi
0x18000938a  retn
```
