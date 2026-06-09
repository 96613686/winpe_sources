# StopAndSavePosition(_MCIGRAPHIC *)

- ea: `0x180004314`
- end: `0x1800043c9`
- name: `?StopAndSavePosition@@YAJPEAU_MCIGRAPHIC@@@Z`
- size: `181`
- prototype: `__int64 __fastcall(struct _MCIGRAPHIC *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180002b78`
- `0x180003408`

## callees

- `0x180001ef4`
- `0x18000415c`
- `0x180004314`
- `0x1800043d0`
- `0x180004f9c`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall StopAndSavePosition(struct _MCIGRAPHIC *a1)
{
  __int64 result; // rax
  unsigned int v3; // edi
  unsigned int v4; // eax
  unsigned int v5; // ebx
  int v6; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v7; // [rsp+38h] [rbp+10h] BYREF

  v6 = 0;
  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(**((_QWORD **)a1 + 16) + 56LL))(
             *((_QWORD *)a1 + 16),
             0,
             &v6);
  if ( (int)result >= 0 )
  {
    if ( v6 )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 19) + 64LL))(*((_QWORD *)a1 + 19));
      v3 = CurrentPosition(a1);
      v4 = StopPosition(a1);
      if ( v3 > v4 )
        v3 = v4;
      v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 19) + 72LL))(*((_QWORD *)a1 + 19));
      GraphicDelayedNotify(a1, 4);
      v7 = v3;
      PutSelection(a1, &v7, 0);
      return v5;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004314  mov     [rsp+arg_10], rbx
0x180004319  mov     [rsp+arg_18], rsi
0x18000431e  push    rdi
0x18000431f  sub     rsp, 20h
0x180004323  mov     rsi, rcx
0x180004326  mov     [rsp+28h+arg_0], 0
0x18000432e  mov     rcx, [rcx+80h]
0x180004335  lea     r8, [rsp+28h+arg_0]
0x18000433a  xor     edx, edx
0x18000433c  mov     rax, [rcx]
0x18000433f  mov     rax, [rax+38h]
0x180004343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004348  test    eax, eax
0x18000434a  js      short loc_1800043B9
0x18000434c  cmp     [rsp+28h+arg_0], 0
0x180004351  jnz     short loc_180004357
0x180004353  xor     eax, eax
0x180004355  jmp     short loc_1800043B9
0x180004357  mov     rcx, [rsi+98h]
0x18000435e  mov     rax, [rcx]
0x180004361  mov     rax, [rax+40h]
0x180004365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000436a  mov     rcx, rsi; struct _MCIGRAPHIC *
0x18000436d  call    ?CurrentPosition@@YAKPEAU_MCIGRAPHIC@@@Z; CurrentPosition(_MCIGRAPHIC *)
0x180004372  mov     rcx, rsi; struct _MCIGRAPHIC *
0x180004375  mov     edi, eax
0x180004377  call    ?StopPosition@@YAKPEAU_MCIGRAPHIC@@@Z; StopPosition(_MCIGRAPHIC *)
0x18000437c  mov     rcx, [rsi+98h]
0x180004383  cmp     edi, eax
0x180004385  cmova   edi, eax
0x180004388  mov     rdx, [rcx]
0x18000438b  mov     rax, [rdx+48h]
0x18000438f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004394  mov     edx, 4
0x180004399  mov     rcx, rsi
0x18000439c  mov     ebx, eax
0x18000439e  call    GraphicDelayedNotify
0x1800043a3  xor     r8d, r8d; unsigned int *
0x1800043a6  mov     [rsp+28h+arg_8], edi
0x1800043aa  lea     rdx, [rsp+28h+arg_8]; unsigned int *
0x1800043af  mov     rcx, rsi; struct _MCIGRAPHIC *
0x1800043b2  call    ?PutSelection@@YAJPEAU_MCIGRAPHIC@@PEAK1@Z; PutSelection(_MCIGRAPHIC *,ulong *,ulong *)
0x1800043b7  mov     eax, ebx
0x1800043b9  mov     rbx, [rsp+28h+arg_10]
0x1800043be  mov     rsi, [rsp+28h+arg_18]
0x1800043c3  add     rsp, 20h
0x1800043c7  pop     rdi
0x1800043c8  retn
```
