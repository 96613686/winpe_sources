# WxSetThreadpoolTimer(_TP_TIMER *,_FILETIME *,ulong,ulong)

- ea: `0x18000b310`
- end: `0x18000b33d`
- name: `?WxSetThreadpoolTimer@@YAXPEAU_TP_TIMER@@PEAU_FILETIME@@KK@Z`
- size: `45`
- prototype: `void __fastcall(struct _TP_TIMER *, struct _FILETIME *, unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a4c0`
- `0x18000a5c0`
- `0x18000aaa0`
- `0x18000b1e0`
- `0x18000ff14`
- `0x1800193a0`

## callees

- `0x18000b310`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b329`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b329`

## pseudocode

```c
void __fastcall WxSetThreadpoolTimer(struct _TP_TIMER *a1, struct _FILETIME *a2, __int64 a3, DWORD a4)
{
  if ( a1 )
  {
    if ( !*(_BYTE *)(qword_1800426A0 + 72) )
      SetThreadpoolTimer(a1, a2, 0, a4);
  }
}

```

## disassembly

```asm
0x18000b310  sub     rsp, 28h
0x18000b314  test    rcx, rcx
0x18000b317  jz      short loc_18000B337
0x18000b319  mov     rax, cs:qword_1800426A0
0x18000b320  cmp     byte ptr [rax+48h], 0
0x18000b324  jnz     short loc_18000B337
0x18000b326  xor     r8d, r8d; msPeriod
0x18000b329  call    cs:__imp_SetThreadpoolTimer
0x18000b330  nop     dword ptr [rax+rax+00h]
0x18000b335  jmp     short $+2
0x18000b337  add     rsp, 28h
0x18000b33b  retn
0x180030a10  push    rbp
0x180030a12  sub     rsp, 20h
0x180030a16  mov     rbp, rdx
0x180030a19  mov     rax, [rcx]
0x180030a1c  xor     ecx, ecx
0x180030a1e  cmp     dword ptr [rax], 0C000000Dh
0x180030a24  setz    cl
0x180030a27  mov     eax, ecx
0x180030a29  add     rsp, 20h
0x180030a2d  pop     rbp
0x180030a2e  retn
```
