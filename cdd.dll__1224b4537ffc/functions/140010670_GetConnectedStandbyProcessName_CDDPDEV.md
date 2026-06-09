# GetConnectedStandbyProcessName(CDDPDEV *)

- ea: `0x140010670`
- end: `0x1400106e3`
- name: `?GetConnectedStandbyProcessName@@YAXPEAUCDDPDEV@@@Z`
- size: `115`
- prototype: `void __fastcall(struct CDDPDEV *)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x14000919c`
- `0x14000cec4`
- `0x14000cf80`
- `0x14000ef80`
- `0x14000fbb4`
- `0x1400101a0`
- `0x1400130d0`
- `0x140018a80`
- `0x140020af0`
- `0x1400210c0`
- `0x1400212b0`
- `0x1400226b0`
- `0x14002b270`
- `0x14002b5f0`
- `0x14002ee20`

## callees

- `0x140010670`
- `0x1400372d0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400106ac`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400106ac`

## pseudocode

```c
void __fastcall GetConnectedStandbyProcessName(struct CDDPDEV *a1, __int64 a2, __int64 a3)
{
  bool v3; // zf
  char *v5; // rsi
  int (__fastcall *v6)(__int64, char *, __int64); // rdi
  __int64 CurrentProcess; // rax

  v3 = *((_BYTE *)a1 + 2719) == 0;
  *((_QWORD *)a1 + 452) = 0;
  if ( !v3 )
  {
    v5 = (char *)a1 + 3624;
    v6 = (int (__fastcall *)(__int64, char *, __int64))*((_QWORD *)a1 + 54);
    CurrentProcess = PsGetCurrentProcess(a1, a2, a3);
    if ( v6(CurrentProcess, v5, 17) >= 0 )
      *((_QWORD *)a1 + 452) = v5;
  }
}

```

## disassembly

```asm
0x140010670  push    rbx
0x140010672  sub     rsp, 20h
0x140010676  cmp     byte ptr [rcx+0A9Fh], 0
0x14001067d  mov     rbx, rcx
0x140010680  mov     qword ptr [rcx+0E20h], 0
0x14001068b  jnz     short loc_140010694
0x14001068d  add     rsp, 20h
0x140010691  pop     rbx
0x140010692  retn
0x140010694  mov     [rsp+28h+arg_0], rsi
0x140010699  lea     rsi, [rcx+0E28h]
0x1400106a0  mov     [rsp+28h+arg_8], rdi
0x1400106a5  mov     rdi, [rcx+1B0h]
0x1400106ac  call    cs:__imp_PsGetCurrentProcess
0x1400106b3  nop     dword ptr [rax+rax+00h]
0x1400106b8  mov     r8d, 11h
0x1400106be  mov     rdx, rsi
0x1400106c1  mov     rcx, rax
0x1400106c4  mov     rax, rdi
0x1400106c7  call    _guard_dispatch_icall
0x1400106cc  mov     rdi, [rsp+28h+arg_8]
0x1400106d1  test    eax, eax
0x1400106d3  js      short loc_1400106DC
0x1400106d5  mov     [rbx+0E20h], rsi
0x1400106dc  mov     rsi, [rsp+28h+arg_0]
0x1400106e1  jmp     short loc_14001068D
```
