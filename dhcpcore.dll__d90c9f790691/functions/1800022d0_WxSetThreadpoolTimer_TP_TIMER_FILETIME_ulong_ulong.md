# WxSetThreadpoolTimer(_TP_TIMER *,_FILETIME *,ulong,ulong)

- ea: `0x1800022d0`
- end: `0x1800022f6`
- name: `?WxSetThreadpoolTimer@@YAXPEAU_TP_TIMER@@PEAU_FILETIME@@KK@Z`
- size: `38`
- prototype: `void __fastcall(struct _TP_TIMER *, struct _FILETIME *, __int64, DWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800020d0`
- `0x1800021c0`
- `0x18001c46c`
- `0x180043508`

## callees

- `0x1800022d0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800022e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800022e9`

## pseudocode

```c
void __fastcall WxSetThreadpoolTimer(struct _TP_TIMER *a1, struct _FILETIME *a2, __int64 a3, DWORD a4)
{
  if ( a1 )
  {
    if ( !*(_BYTE *)(qword_1800618B0 + 72) )
      SetThreadpoolTimer(a1, a2, 0, a4);
  }
}

```

## disassembly

```asm
0x1800022d0  sub     rsp, 28h
0x1800022d4  test    rcx, rcx
0x1800022d7  jz      short loc_1800022F1
0x1800022d9  mov     rax, cs:qword_1800618B0
0x1800022e0  cmp     byte ptr [rax+48h], 0
0x1800022e4  jnz     short loc_1800022F1
0x1800022e6  xor     r8d, r8d; msPeriod
0x1800022e9  call    cs:__imp_SetThreadpoolTimer
0x1800022ef  jmp     short $+2
0x1800022f1  add     rsp, 28h
0x1800022f5  retn
0x180047ec0  push    rbp
0x180047ec2  sub     rsp, 20h
0x180047ec6  mov     rbp, rdx
0x180047ec9  mov     rax, [rcx]
0x180047ecc  xor     ecx, ecx
0x180047ece  cmp     dword ptr [rax], 0C000000Dh
0x180047ed4  setz    cl
0x180047ed7  mov     eax, ecx
0x180047ed9  add     rsp, 20h
0x180047edd  pop     rbp
0x180047ede  retn
```
