# IsCommandSwitchPresent(ushort *,ushort *)

- ea: `0x140005710`
- end: `0x140005778`
- name: `?IsCommandSwitchPresent@@YA_NPEAG0@Z`
- size: `104`
- prototype: `bool __fastcall(unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400014e4`
- `0x140004128`

## callees

- `0x14000566c`
- `0x140005710`
- `0x1400057a8`
- `0x1400057cc`

## pseudocode

```c
char __fastcall IsCommandSwitchPresent(unsigned __int16 *a1, unsigned __int16 *a2)
{
  __int64 v4; // rcx
  int v5; // eax
  void *v6; // rdx
  __int64 v7; // r8
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v11; // [rsp+40h] [rbp+18h] BYREF

  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  v11 = 0;
  v5 = ULongLongToULong(v4 + 1, &v11);
  if ( v5 < 0 )
    wil::details::in1diag3::_FailFast_Hr(retaddr, v6, v7, (const char *)(unsigned int)v5, v9);
  return FindOrRemoveCommandSwitch(a1, v11, a2, 0);
}

```

## disassembly

```asm
0x140005710  mov     [rsp+arg_0], rbx
0x140005715  mov     [rsp+arg_8], rsi
0x14000571a  push    rdi; int
0x14000571b  sub     rsp, 20h
0x14000571f  mov     rbx, rcx
0x140005722  mov     rdi, rdx
0x140005725  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140005729  xor     esi, esi
0x14000572b  inc     rcx
0x14000572e  cmp     [rbx+rcx*2], si
0x140005732  jnz     short loc_14000572B
0x140005734  inc     rcx; unsigned __int64
0x140005737  mov     [rsp+28h+arg_10], esi
0x14000573b  lea     rdx, [rsp+28h+arg_10]; unsigned int *
0x140005740  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x140005745  test    eax, eax
0x140005747  jns     short loc_140005757
0x140005749  mov     rcx, [rsp+28h]; this
0x14000574e  mov     r9d, eax; char *
0x140005751  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x140005757  mov     edx, [rsp+28h+arg_10]; unsigned int
0x14000575b  xor     r9d, r9d; bool
0x14000575e  mov     r8, rdi; unsigned __int16 *
0x140005761  mov     rcx, rbx; unsigned __int16 *
0x140005764  mov     rbx, [rsp+28h+arg_0]
0x140005769  mov     rsi, [rsp+28h+arg_8]
0x14000576e  add     rsp, 20h
0x140005772  pop     rdi
0x140005773  jmp     ?FindOrRemoveCommandSwitch@@YA_NPEAGKPEBG_N@Z; FindOrRemoveCommandSwitch(ushort *,ulong,ushort const *,bool)
```
