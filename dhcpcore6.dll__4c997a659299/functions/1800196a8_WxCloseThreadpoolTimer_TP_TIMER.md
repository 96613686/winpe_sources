# WxCloseThreadpoolTimer(_TP_TIMER *)

- ea: `0x1800196a8`
- end: `0x1800196d2`
- name: `?WxCloseThreadpoolTimer@@YAXPEAU_TP_TIMER@@@Z`
- size: `42`
- prototype: `void __fastcall(struct _TP_TIMER *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ff14`
- `0x1800195a8`

## callees

- `0x1800196a8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800196be`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800196be`

## pseudocode

```c
void __fastcall WxCloseThreadpoolTimer(struct _TP_TIMER *a1)
{
  if ( a1 )
  {
    if ( !*(_BYTE *)(qword_1800426A0 + 72) )
      CloseThreadpoolTimer(a1);
  }
}

```

## disassembly

```asm
0x1800196a8  sub     rsp, 28h
0x1800196ac  test    rcx, rcx
0x1800196af  jz      short loc_1800196CC
0x1800196b1  mov     rax, cs:qword_1800426A0
0x1800196b8  cmp     byte ptr [rax+48h], 0
0x1800196bc  jnz     short loc_1800196CC
0x1800196be  call    cs:__imp_CloseThreadpoolTimer
0x1800196c5  nop     dword ptr [rax+rax+00h]
0x1800196ca  jmp     short $+2
0x1800196cc  add     rsp, 28h
0x1800196d0  retn
0x180030a36  push    rbp
0x180030a38  sub     rsp, 20h
0x180030a3c  mov     rbp, rdx
0x180030a3f  mov     rax, [rcx]
0x180030a42  xor     ecx, ecx
0x180030a44  cmp     dword ptr [rax], 0C000000Dh
0x180030a4a  setz    cl
0x180030a4d  mov     eax, ecx
0x180030a4f  add     rsp, 20h
0x180030a53  pop     rbp
0x180030a54  retn
```
