# DeviceThreadProc(void *)

- ea: `0x1800034b0`
- end: `0x1800035fb`
- name: `?DeviceThreadProc@@YAKPEAX@Z`
- size: `331`
- prototype: `__int64 __fastcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003408`
- `0x1800034b0`
- `0x18000415c`
- `0x180004f9c`
- `0x180007010`

## import_xrefs

- `KERNEL32!WaitForMultipleObjects` at `0x1800034f3`
- `KERNEL32!WaitForMultipleObjects` at `0x1800034f3`
- `KERNEL32!SetEvent` at `0x1800035df`
- `KERNEL32!SetEvent` at `0x1800035df`

## pseudocode

```c
__int64 __fastcall DeviceThreadProc(LPVOID lpThreadParameter)
{
  unsigned int v2; // edx
  __int64 v3; // rcx
  int v5; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v6; // [rsp+58h] [rbp+10h] BYREF
  __int64 v7; // [rsp+60h] [rbp+18h] BYREF
  __int64 v8; // [rsp+68h] [rbp+20h] BYREF

  while ( !*((_DWORD *)lpThreadParameter + 63) )
  {
    v5 = 0;
    v8 = 0;
    v7 = 0;
    if ( WaitForMultipleObjects(2u, (const HANDLE *)lpThreadParameter + 34, 0, 0xFFFFFFFF) == 1 )
      return 0;
    if ( (*(int (__fastcall **)(_QWORD, int *, __int64 *, __int64 *, _DWORD))(**((_QWORD **)lpThreadParameter + 20)
                                                                            + 64LL))(
           *((_QWORD *)lpThreadParameter + 20),
           &v5,
           &v8,
           &v7,
           0) >= 0 )
    {
      switch ( v5 )
      {
        case 1:
          if ( !*((_DWORD *)lpThreadParameter + 51) )
          {
            GraphicDelayedNotify(lpThreadParameter, 1);
LABEL_11:
            v3 = *((_QWORD *)lpThreadParameter + 22);
            if ( v3 )
              (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 288LL))(v3, 0);
            DeviceStop((struct _MCIGRAPHIC *)lpThreadParameter, v2);
            SetEvent(*((HANDLE *)lpThreadParameter + 33));
            break;
          }
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)lpThreadParameter + 19) + 64LL))(*((_QWORD *)lpThreadParameter
                                                                                          + 19));
          v6 = *((_DWORD *)lpThreadParameter + 52);
          PutSelection((struct _MCIGRAPHIC *)lpThreadParameter, &v6, 0);
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)lpThreadParameter + 19) + 56LL))(*((_QWORD *)lpThreadParameter
                                                                                          + 19));
          break;
        case 2:
          goto LABEL_11;
        case 3:
          GraphicDelayedNotify(lpThreadParameter, 8);
          break;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800034b0  push    rbx
0x1800034b2  push    rdi
0x1800034b3  sub     rsp, 38h
0x1800034b7  cmp     dword ptr [rcx+0FCh], 0
0x1800034be  mov     rbx, rcx
0x1800034c1  jnz     loc_1800035F2
0x1800034c7  xor     r8d, r8d; bWaitAll
0x1800034ca  mov     [rsp+48h+arg_0], 0
0x1800034d2  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800034d6  mov     [rsp+48h+arg_18], 0
0x1800034df  lea     rdx, [rbx+110h]; lpHandles
0x1800034e6  mov     [rsp+48h+arg_10], 0
0x1800034ef  lea     ecx, [r8+2]; nCount
0x1800034f3  call    cs:__imp_WaitForMultipleObjects
0x1800034f9  cmp     eax, 1
0x1800034fc  jz      loc_1800035F2
0x180003502  mov     rcx, [rbx+0A0h]
0x180003509  lea     r9, [rsp+48h+arg_10]
0x18000350e  lea     r8, [rsp+48h+arg_18]
0x180003513  mov     [rsp+48h+var_28], 0
0x18000351b  lea     rdx, [rsp+48h+arg_0]
0x180003520  mov     rax, [rcx]
0x180003523  mov     rax, [rax+40h]
0x180003527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000352c  test    eax, eax
0x18000352e  js      loc_1800035E5
0x180003534  mov     ecx, [rsp+48h+arg_0]
0x180003538  sub     ecx, 1
0x18000353b  jz      short loc_18000355B
0x18000353d  sub     ecx, 1
0x180003540  jz      short loc_1800035B3
0x180003542  cmp     ecx, 1
0x180003545  jnz     loc_1800035E5
0x18000354b  lea     edx, [rcx+7]
0x18000354e  mov     rcx, rbx
0x180003551  call    GraphicDelayedNotify
0x180003556  jmp     loc_1800035E5
0x18000355b  cmp     dword ptr [rbx+0CCh], 0
0x180003562  jz      short loc_1800035A6
0x180003564  mov     rcx, [rbx+98h]
0x18000356b  mov     rax, [rcx]
0x18000356e  mov     rax, [rax+40h]
0x180003572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003577  mov     eax, [rbx+0D0h]
0x18000357d  lea     rdx, [rsp+48h+arg_8]; unsigned int *
0x180003582  xor     r8d, r8d; unsigned int *
0x180003585  mov     [rsp+48h+arg_8], eax
0x180003589  mov     rcx, rbx; struct _MCIGRAPHIC *
0x18000358c  call    ?PutSelection@@YAJPEAU_MCIGRAPHIC@@PEAK1@Z; PutSelection(_MCIGRAPHIC *,ulong *,ulong *)
0x180003591  mov     rcx, [rbx+98h]
0x180003598  mov     rax, [rcx]
0x18000359b  mov     rax, [rax+38h]
0x18000359f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035a4  jmp     short loc_1800035E5
0x1800035a6  mov     edx, 1
0x1800035ab  mov     rcx, rbx
0x1800035ae  call    GraphicDelayedNotify
0x1800035b3  mov     rcx, [rbx+0B0h]
0x1800035ba  test    rcx, rcx
0x1800035bd  jz      short loc_1800035D0
0x1800035bf  mov     rax, [rcx]
0x1800035c2  xor     edx, edx
0x1800035c4  mov     rax, [rax+120h]
0x1800035cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035d0  mov     rcx, rbx; struct _MCIGRAPHIC *
0x1800035d3  call    ?DeviceStop@@YAKPEAU_MCIGRAPHIC@@K@Z; DeviceStop(_MCIGRAPHIC *,ulong)
0x1800035d8  mov     rcx, [rbx+108h]; hEvent
0x1800035df  call    cs:__imp_SetEvent
0x1800035e5  cmp     dword ptr [rbx+0FCh], 0
0x1800035ec  jz      loc_1800034C7
0x1800035f2  xor     eax, eax
0x1800035f4  add     rsp, 38h
0x1800035f8  pop     rdi
0x1800035f9  pop     rbx
0x1800035fa  retn
```
