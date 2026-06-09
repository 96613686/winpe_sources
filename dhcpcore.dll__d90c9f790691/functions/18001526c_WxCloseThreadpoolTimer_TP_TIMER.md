# WxCloseThreadpoolTimer(_TP_TIMER *)

- ea: `0x18001526c`
- end: `0x18001528f`
- name: `?WxCloseThreadpoolTimer@@YAXPEAU_TP_TIMER@@@Z`
- size: `35`
- prototype: `void __fastcall(struct _TP_TIMER *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180043508`
- `0x180047928`

## callees

- `0x18001526c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015282`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015282`

## pseudocode

```c
void __fastcall WxCloseThreadpoolTimer(struct _TP_TIMER *a1)
{
  if ( a1 )
  {
    if ( !*(_BYTE *)(qword_1800618B0 + 72) )
      CloseThreadpoolTimer(a1);
  }
}

```

## disassembly

```asm
0x18001526c  sub     rsp, 28h
0x180015270  test    rcx, rcx
0x180015273  jz      short loc_18001528A
0x180015275  mov     rax, cs:qword_1800618B0
0x18001527c  cmp     byte ptr [rax+48h], 0
0x180015280  jnz     short loc_18001528A
0x180015282  call    cs:__imp_CloseThreadpoolTimer
0x180015288  jmp     short $+2
0x18001528a  add     rsp, 28h
0x18001528e  retn
0x180047ee6  push    rbp
0x180047ee8  sub     rsp, 20h
0x180047eec  mov     rbp, rdx
0x180047eef  mov     rax, [rcx]
0x180047ef2  xor     ecx, ecx
0x180047ef4  cmp     dword ptr [rax], 0C000000Dh
0x180047efa  setz    cl
0x180047efd  mov     eax, ecx
0x180047eff  add     rsp, 20h
0x180047f03  pop     rbp
0x180047f04  retn
```
