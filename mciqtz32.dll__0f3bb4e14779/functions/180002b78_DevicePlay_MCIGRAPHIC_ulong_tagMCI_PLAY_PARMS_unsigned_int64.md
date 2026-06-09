# DevicePlay(_MCIGRAPHIC *,ulong,tagMCI_PLAY_PARMS *,unsigned __int64)

- ea: `0x180002b78`
- end: `0x180002d17`
- name: `?DevicePlay@@YAKPEAU_MCIGRAPHIC@@KPEAUtagMCI_PLAY_PARMS@@_K@Z`
- size: `415`
- prototype: `unsigned int __fastcall(struct _MCIGRAPHIC *, unsigned int, struct tagMCI_PLAY_PARMS *, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000485c`

## callees

- `0x180001e7c`
- `0x180002b78`
- `0x180003b5c`
- `0x18000415c`
- `0x18000423c`
- `0x180004314`
- `0x180004f9c`
- `0x180007010`

## import_xrefs

- `USER32!SetForegroundWindow` at `0x180002ced`
- `USER32!SetForegroundWindow` at `0x180002ced`
- `USER32!IsWindowVisible` at `0x180002cc4`
- `USER32!IsWindowVisible` at `0x180002cc4`
- `USER32!ShowWindow` at `0x180002ce0`
- `USER32!ShowWindow` at `0x180002ce0`

## pseudocode

```c
__int64 __fastcall DevicePlay(struct _MCIGRAPHIC *a1, unsigned int a2, struct tagMCI_PLAY_PARMS *a3, __int64 a4)
{
  bool v9; // zf
  DWORD dwTo; // eax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  unsigned int v15; // [rsp+48h] [rbp+10h] BYREF

  if ( (a2 & 0x20000) != 0 )
    return 274;
  *((_DWORD *)a1 + 72) = 526;
  v9 = *((_QWORD *)a1 + 18) == 0;
  *((_DWORD *)a1 + 51) = HIWORD(a2) & 1;
  if ( !v9 )
  {
    if ( (a2 & 4) != 0 )
    {
      GraphicDelayedNotify(a1, 4);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 19) + 72LL))(*((_QWORD *)a1 + 19));
    }
    else
    {
      *((_DWORD *)a1 + 52) = 0;
    }
    if ( (a2 & 8) != 0 )
      dwTo = a3->dwTo;
    else
      dwTo = Duration(a1);
    v15 = dwTo;
    if ( dwTo != *((_DWORD *)a1 + 50) )
      StopAndSavePosition(a1);
    PutSelection(a1, (unsigned int *)((unsigned __int64)&a3->dwFrom & -(__int64)((a2 & 4) != 0)), &v15);
  }
  v11 = a2 & 0x7000000;
  if ( (a2 & 0x7000000) == 0 || v11 == 0x1000000 )
  {
    v12 = *((_QWORD *)a1 + 22);
    if ( v12 )
    {
      v13 = 0;
      goto LABEL_21;
    }
  }
  else
  {
    if ( ((v11 - 0x2000000) & 0xFDFFFFFF) != 0 )
      return 284;
    v12 = *((_QWORD *)a1 + 22);
    if ( v12 )
    {
      v13 = 0xFFFFFFFFLL;
LABEL_21:
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 288LL))(v12, v13);
    }
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 19) + 64LL))(*((_QWORD *)a1 + 19));
  *((_DWORD *)a1 + 72) = 526;
  if ( (a2 & 1) != 0 )
  {
    GraphicDelayedNotify(a1, 2);
    *(_QWORD *)a1 = a4;
  }
  if ( !IsWindowVisible(*((HWND *)a1 + 37)) && (a2 & 0x6000000) == 0 )
  {
    ShowWindow(*((HWND *)a1 + 37), 5);
    SetForegroundWindow(*((HWND *)a1 + 37));
  }
  v14 = RunAndWait(a1, a2);
  return CheckResult(v14);
}

```

## disassembly

```asm
0x180002b78  mov     [rsp+arg_0], rbx
0x180002b7d  mov     [rsp+arg_10], rbp
0x180002b82  push    rsi
0x180002b83  push    rdi
0x180002b84  push    r14
0x180002b86  sub     rsp, 20h
0x180002b8a  mov     r14, r9
0x180002b8d  mov     rbp, r8
0x180002b90  mov     edi, edx
0x180002b92  mov     rbx, rcx
0x180002b95  bt      edx, 11h
0x180002b99  jnb     short loc_180002BA5
0x180002b9b  mov     eax, 112h
0x180002ba0  jmp     loc_180002D04
0x180002ba5  mov     eax, edi
0x180002ba7  mov     dword ptr [rcx+120h], 20Eh
0x180002bb1  shr     eax, 10h
0x180002bb4  and     eax, 1
0x180002bb7  cmp     qword ptr [rcx+90h], 0
0x180002bbf  mov     [rcx+0CCh], eax
0x180002bc5  jz      short loc_180002C36
0x180002bc7  mov     esi, edi
0x180002bc9  mov     edx, 4
0x180002bce  and     esi, edx
0x180002bd0  jz      short loc_180002BEC
0x180002bd2  call    GraphicDelayedNotify
0x180002bd7  mov     rcx, [rbx+98h]
0x180002bde  mov     rax, [rcx]
0x180002be1  mov     rax, [rax+48h]
0x180002be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bea  jmp     short loc_180002BF6
0x180002bec  mov     dword ptr [rcx+0D0h], 0
0x180002bf6  test    dil, 8
0x180002bfa  jz      short loc_180002C01
0x180002bfc  mov     eax, [rbp+0Ch]
0x180002bff  jmp     short loc_180002C09
0x180002c01  mov     rcx, rbx; struct _MCIGRAPHIC *
0x180002c04  call    ?Duration@@YAKPEAU_MCIGRAPHIC@@@Z; Duration(_MCIGRAPHIC *)
0x180002c09  mov     [rsp+38h+arg_8], eax
0x180002c0d  cmp     eax, [rbx+0C8h]
0x180002c13  jz      short loc_180002C1D
0x180002c15  mov     rcx, rbx; struct _MCIGRAPHIC *
0x180002c18  call    ?StopAndSavePosition@@YAJPEAU_MCIGRAPHIC@@@Z; StopAndSavePosition(_MCIGRAPHIC *)
0x180002c1d  neg     esi
0x180002c1f  lea     rax, [rbp+8]
0x180002c23  lea     r8, [rsp+38h+arg_8]; unsigned int *
0x180002c28  mov     rcx, rbx; struct _MCIGRAPHIC *
0x180002c2b  sbb     rdx, rdx
0x180002c2e  and     rdx, rax; unsigned int *
0x180002c31  call    ?PutSelection@@YAJPEAU_MCIGRAPHIC@@PEAK1@Z; PutSelection(_MCIGRAPHIC *,ulong *,ulong *)
0x180002c36  mov     eax, edi
0x180002c38  and     eax, 7000000h
0x180002c3d  jz      short loc_180002C6D
0x180002c3f  cmp     eax, 1000000h
0x180002c44  jz      short loc_180002C6D
0x180002c46  add     eax, 0FE000000h
0x180002c4b  test    eax, 0FDFFFFFFh
0x180002c50  jz      short loc_180002C5C
0x180002c52  mov     eax, 11Ch
0x180002c57  jmp     loc_180002D04
0x180002c5c  mov     rcx, [rbx+0B0h]
0x180002c63  test    rcx, rcx
0x180002c66  jz      short loc_180002C8A
0x180002c68  or      edx, 0FFFFFFFFh
0x180002c6b  jmp     short loc_180002C7B
0x180002c6d  mov     rcx, [rbx+0B0h]
0x180002c74  test    rcx, rcx
0x180002c77  jz      short loc_180002C8A
0x180002c79  xor     edx, edx
0x180002c7b  mov     rax, [rcx]
0x180002c7e  mov     rax, [rax+120h]
0x180002c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c8a  mov     rcx, [rbx+98h]
0x180002c91  mov     rax, [rcx]
0x180002c94  mov     rax, [rax+40h]
0x180002c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c9d  mov     dword ptr [rbx+120h], 20Eh
0x180002ca7  test    dil, 1
0x180002cab  jz      short loc_180002CBD
0x180002cad  mov     edx, 2
0x180002cb2  mov     rcx, rbx
0x180002cb5  call    GraphicDelayedNotify
0x180002cba  mov     [rbx], r14
0x180002cbd  mov     rcx, [rbx+128h]; hWnd
0x180002cc4  call    cs:__imp_IsWindowVisible
0x180002cca  test    eax, eax
0x180002ccc  jnz     short loc_180002CF3
0x180002cce  test    edi, 6000000h
0x180002cd4  jnz     short loc_180002CF3
0x180002cd6  mov     rcx, [rbx+128h]; hWnd
0x180002cdd  lea     edx, [rax+5]; nCmdShow
0x180002ce0  call    cs:__imp_ShowWindow
0x180002ce6  mov     rcx, [rbx+128h]; hWnd
0x180002ced  call    cs:__imp_SetForegroundWindow
0x180002cf3  mov     edx, edi; unsigned int
0x180002cf5  mov     rcx, rbx; struct _MCIGRAPHIC *
0x180002cf8  call    ?RunAndWait@@YAJPEAU_MCIGRAPHIC@@K@Z; RunAndWait(_MCIGRAPHIC *,ulong)
0x180002cfd  mov     ecx, eax; int
0x180002cff  call    ?CheckResult@@YAKJ@Z; CheckResult(long)
0x180002d04  mov     rbx, [rsp+38h+arg_0]
0x180002d09  mov     rbp, [rsp+38h+arg_10]
0x180002d0e  add     rsp, 20h
0x180002d12  pop     r14
0x180002d14  pop     rdi
0x180002d15  pop     rsi
0x180002d16  retn
```
