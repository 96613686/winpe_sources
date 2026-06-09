# DeviceStop(_MCIGRAPHIC *,ulong)

- ea: `0x180003408`
- end: `0x18000349f`
- name: `?DeviceStop@@YAKPEAU_MCIGRAPHIC@@K@Z`
- size: `151`
- prototype: `unsigned int __fastcall(struct _MCIGRAPHIC *, unsigned int)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180003074`
- `0x1800034b0`
- `0x180003d40`
- `0x18000485c`
- `0x180006088`

## callees

- `0x180001e7c`
- `0x180003408`
- `0x180004314`
- `0x180004f9c`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall DeviceStop(struct _MCIGRAPHIC *a1, int a2)
{
  bool v2; // zf
  int v5; // eax
  int v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = a2;
  v2 = *((_QWORD *)a1 + 16) == 0;
  v6 = 0;
  if ( v2 )
    return 277;
  GraphicDelayedNotify(a1, 4);
  v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(**((_QWORD **)a1 + 16) + 56LL))(*((_QWORD *)a1 + 16), 0, &v6);
  if ( v5 >= 0 )
  {
    if ( v6 )
    {
      if ( *((_DWORD *)a1 + 72) == 528 )
        v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)a1 + 19) + 72LL))(*((_QWORD *)a1 + 19));
      else
        v5 = StopAndSavePosition(a1);
    }
    *((_DWORD *)a1 + 72) = 525;
  }
  return CheckResult(v5);
}

```

## disassembly

```asm
0x180003408  mov     [rsp+arg_8], edx
0x18000340c  push    rbx
0x18000340d  sub     rsp, 20h
0x180003411  cmp     qword ptr [rcx+80h], 0
0x180003419  mov     rbx, rcx
0x18000341c  mov     [rsp+28h+arg_8], 0
0x180003424  jnz     short loc_180003431
0x180003426  mov     eax, 115h
0x18000342b  add     rsp, 20h
0x18000342f  pop     rbx
0x180003430  retn
0x180003431  mov     edx, 4
0x180003436  call    GraphicDelayedNotify
0x18000343b  mov     rcx, [rbx+80h]
0x180003442  lea     r8, [rsp+28h+arg_8]
0x180003447  xor     edx, edx
0x180003449  mov     rax, [rcx]
0x18000344c  mov     rax, [rax+38h]
0x180003450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003455  test    eax, eax
0x180003457  js      short loc_180003493
0x180003459  cmp     [rsp+28h+arg_8], 0
0x18000345e  jz      short loc_180003489
0x180003460  cmp     dword ptr [rbx+120h], 210h
0x18000346a  jz      short loc_180003476
0x18000346c  mov     rcx, rbx; struct _MCIGRAPHIC *
0x18000346f  call    ?StopAndSavePosition@@YAJPEAU_MCIGRAPHIC@@@Z; StopAndSavePosition(_MCIGRAPHIC *)
0x180003474  jmp     short loc_180003489
0x180003476  mov     rcx, [rbx+98h]
0x18000347d  mov     rax, [rcx]
0x180003480  mov     rax, [rax+48h]
0x180003484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003489  mov     dword ptr [rbx+120h], 20Dh
0x180003493  mov     ecx, eax; int
0x180003495  add     rsp, 20h
0x180003499  pop     rbx
0x18000349a  jmp     ?CheckResult@@YAKJ@Z; CheckResult(long)
```
