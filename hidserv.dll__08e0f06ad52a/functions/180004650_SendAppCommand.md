# SendAppCommand

- ea: `0x180004650`
- end: `0x18000478c`
- name: `SendAppCommand`
- size: `316`
- prototype: `_UNKNOWN **__fastcall(unsigned __int16)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003594`
- `0x180004a50`

## callees

- `0x180004650`
- `0x180005308`
- `0x180009010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18000470c`
- `KERNEL32!WaitForSingleObject` at `0x18000470c`
- `KERNEL32!SetEvent` at `0x1800046fc`
- `KERNEL32!SetEvent` at `0x1800046fc`

## pseudocode

```c
_UNKNOWN **__fastcall SendAppCommand(unsigned __int16 a1)
{
  __int64 v1; // r8
  unsigned int v2; // ebx
  _UNKNOWN **result; // rax
  int v4; // [rsp+60h] [rbp+8h] BYREF

  v1 = 0;
  v2 = a1;
  if ( a1 <= 0x13u )
  {
    if ( a1 != 19 && a1 != 8 && a1 != 9 && a1 != 10 && a1 != 11 && a1 != 12 && (unsigned int)a1 - 13 >= 2 )
      goto LABEL_17;
LABEL_16:
    v1 = 1;
    goto LABEL_17;
  }
  if ( a1 == 20 || a1 == 21 || a1 == 22 || a1 == 23 || a1 == 24 || (unsigned int)a1 - 25 <= 1 )
    goto LABEL_16;
LABEL_17:
  if ( InputThreadEnabled && (!IsSessionLocked || (_DWORD)v1) )
  {
    if ( SessionId )
    {
      if ( WinStaProc )
      {
        v4 = 0;
        WinStaProc(0, (unsigned int)SessionId, 5, (unsigned int)hWndHidServ, 793, a1, 0, &v4);
      }
    }
    else
    {
      InputAppCommand = a1;
      InputType = 0;
      SetEvent(hInputEvent);
      WaitForSingleObject(hInputDoneEvent, 0xFFFFFFFF);
    }
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      return (_UNKNOWN **)WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, v1, v2);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004650  push    rbx
0x180004652  sub     rsp, 50h
0x180004656  movzx   r9d, cx
0x18000465a  xor     r10d, r10d
0x18000465d  mov     r8d, r10d
0x180004660  mov     ebx, r9d
0x180004663  cmp     r9d, 13h
0x180004667  ja      short loc_180004692
0x180004669  jz      short loc_1800046B7
0x18000466b  mov     edx, ebx
0x18000466d  sub     edx, 8
0x180004670  jz      short loc_1800046B7
0x180004672  sub     edx, 1
0x180004675  jz      short loc_1800046B7
0x180004677  sub     edx, 1
0x18000467a  jz      short loc_1800046B7
0x18000467c  sub     edx, 1
0x18000467f  jz      short loc_1800046B7
0x180004681  sub     edx, 1
0x180004684  jz      short loc_1800046B7
0x180004686  sub     edx, 1
0x180004689  jz      short loc_1800046B7
0x18000468b  cmp     edx, 1
0x18000468e  jz      short loc_1800046B7
0x180004690  jmp     short loc_1800046BD
0x180004692  mov     ecx, ebx
0x180004694  sub     ecx, 14h
0x180004697  jz      short loc_1800046B7
0x180004699  sub     ecx, 1
0x18000469c  jz      short loc_1800046B7
0x18000469e  sub     ecx, 1
0x1800046a1  jz      short loc_1800046B7
0x1800046a3  sub     ecx, 1
0x1800046a6  jz      short loc_1800046B7
0x1800046a8  sub     ecx, 1
0x1800046ab  jz      short loc_1800046B7
0x1800046ad  sub     ecx, 1
0x1800046b0  jz      short loc_1800046B7
0x1800046b2  cmp     ecx, 1
0x1800046b5  jnz     short loc_1800046BD
0x1800046b7  mov     r8d, 1
0x1800046bd  cmp     cs:InputThreadEnabled, r10d
0x1800046c4  jz      loc_180004786
0x1800046ca  cmp     cs:IsSessionLocked, r10d
0x1800046d1  jz      short loc_1800046DC
0x1800046d3  test    r8d, r8d
0x1800046d6  jz      loc_180004786
0x1800046dc  mov     edx, cs:SessionId
0x1800046e2  test    edx, edx
0x1800046e4  jnz     short loc_180004714
0x1800046e6  mov     rcx, cs:hInputEvent; hEvent
0x1800046ed  mov     cs:InputAppCommand, r9w
0x1800046f5  mov     cs:InputType, r10d
0x1800046fc  call    cs:__imp_SetEvent
0x180004702  mov     rcx, cs:hInputDoneEvent; hHandle
0x180004709  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000470c  call    cs:__imp_WaitForSingleObject
0x180004712  jmp     short loc_180004756
0x180004714  mov     rax, cs:WinStaProc
0x18000471b  test    rax, rax
0x18000471e  jz      short loc_180004756
0x180004720  mov     rcx, r9
0x180004723  mov     [rsp+58h+arg_0], r10d
0x180004728  mov     r9d, dword ptr cs:hWndHidServ
0x18000472f  lea     r8, [rsp+58h+arg_0]
0x180004734  mov     [rsp+58h+var_20], r8
0x180004739  mov     [rsp+58h+var_28], r10
0x18000473e  mov     [rsp+58h+var_30], rcx
0x180004743  xor     ecx, ecx
0x180004745  mov     [rsp+58h+var_38], 319h
0x18000474d  lea     r8d, [rcx+5]
0x180004751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004756  mov     rcx, cs:WPP_GLOBAL_Control
0x18000475d  lea     rax, WPP_GLOBAL_Control
0x180004764  cmp     rcx, rax
0x180004767  jz      short loc_180004786
0x180004769  test    byte ptr [rcx+1Ch], 10h
0x18000476d  jz      short loc_180004786
0x18000476f  cmp     byte ptr [rcx+19h], 4
0x180004773  jb      short loc_180004786
0x180004775  mov     rcx, [rcx+10h]
0x180004779  mov     edx, 26h ; '&'
0x18000477e  mov     r9d, ebx
0x180004781  call    WPP_SF_d
0x180004786  add     rsp, 50h
0x18000478a  pop     rbx
0x18000478b  retn
```
