# Recycler::WaitForConcurrentThread(ulong)

- ea: `0x180006784`
- end: `0x180006814`
- name: `?WaitForConcurrentThread@Recycler@@AEAAHK@Z`
- size: `144`
- prototype: `__int64 __fastcall(Recycler *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004d94`
- `0x1800062c0`
- `0x180006660`

## callees

- `0x180006784`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x1800067d5`
- `KERNEL32!SetThreadPriority` at `0x1800067fd`
- `KERNEL32!SetThreadPriority` at `0x1800067d5`
- `KERNEL32!SetThreadPriority` at `0x1800067fd`
- `KERNEL32!WaitForSingleObject` at `0x1800067b1`
- `KERNEL32!WaitForSingleObject` at `0x1800067b1`

## pseudocode

```c
_BOOL8 __fastcall Recycler::WaitForConcurrentThread(Recycler *this, DWORD a2)
{
  void *v3; // rcx
  DWORD v4; // eax
  void *v5; // rcx
  DWORD v6; // edi

  v3 = (void *)*((_QWORD *)this + 1619);
  if ( v3 )
    SetThreadPriority(v3, 0);
  v4 = WaitForSingleObject(*((HANDLE *)this + 1618), a2);
  v5 = (void *)*((_QWORD *)this + 1619);
  v6 = v4;
  if ( v5 )
  {
    if ( v4 == 258 )
    {
      *((_BYTE *)this + 12910) = 1;
    }
    else
    {
      SetThreadPriority(v5, -1);
      *((_BYTE *)this + 12910) = 0;
    }
  }
  return v6 == 0;
}

```

## disassembly

```asm
0x180006784  mov     rax, rsp
0x180006787  mov     [rax+18h], rbx
0x18000678b  mov     [rax+10h], edx
0x18000678e  mov     [rax+8], rcx
0x180006792  push    rdi
0x180006793  sub     rsp, 20h
0x180006797  mov     rbx, rcx
0x18000679a  mov     rcx, [rcx+3298h]; hThread
0x1800067a1  test    rcx, rcx
0x1800067a4  jnz     short loc_1800067FB
0x1800067a6  mov     edx, [rsp+28h+dwMilliseconds]; dwMilliseconds
0x1800067aa  mov     rcx, [rbx+3290h]; hHandle
0x1800067b1  call    cs:__imp_WaitForSingleObject
0x1800067b8  nop     dword ptr [rax+rax+00h]
0x1800067bd  mov     rcx, [rbx+3298h]; hThread
0x1800067c4  mov     edi, eax
0x1800067c6  test    rcx, rcx
0x1800067c9  jz      short loc_1800067E8
0x1800067cb  cmp     eax, 102h
0x1800067d0  jz      short loc_18000680B
0x1800067d2  or      edx, 0FFFFFFFFh; nPriority
0x1800067d5  call    cs:__imp_SetThreadPriority
0x1800067dc  nop     dword ptr [rax+rax+00h]
0x1800067e1  mov     byte ptr [rbx+326Eh], 0
0x1800067e8  mov     rbx, [rsp+28h+arg_10]
0x1800067ed  xor     eax, eax
0x1800067ef  test    edi, edi
0x1800067f1  setz    al
0x1800067f4  add     rsp, 20h
0x1800067f8  pop     rdi
0x1800067f9  retn
0x1800067fb  xor     edx, edx; nPriority
0x1800067fd  call    cs:__imp_SetThreadPriority
0x180006804  nop     dword ptr [rax+rax+00h]
0x180006809  jmp     short loc_1800067A6
0x18000680b  mov     byte ptr [rbx+326Eh], 1
0x180006812  jmp     short loc_1800067E8
```
