# CComponentData::NotifySnapinsResetPending(CLogInfo *)

- ea: `0x180006834`
- end: `0x180006885`
- name: `?NotifySnapinsResetPending@CComponentData@@QEAAXPEAVCLogInfo@@@Z`
- size: `81`
- prototype: `void(CComponentData *__hidden this, struct CLogInfo *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001bfb0`
- `0x18001c1f0`

## callees

- `0x180006834`
- `0x180016af8`

## pseudocode

```c
void __fastcall CComponentData::NotifySnapinsResetPending(CComponentData *this, struct CLogInfo *a2)
{
  __int64 i; // rbx
  CLogInfo *v4; // rcx

  for ( i = *((_QWORD *)this + 8); i; i = (*(_QWORD *)(i + 64) - 56LL) & -(__int64)(*(_QWORD *)(i + 64) != 0) )
  {
    v4 = *(CLogInfo **)(i + 1464);
    if ( v4 )
    {
      if ( (unsigned int)CLogInfo::IsSameLog(v4, a2) )
        *(_WORD *)(i + 80) |= 1u;
    }
  }
}

```

## disassembly

```asm
0x180006834  mov     [rsp+arg_0], rbx
0x180006839  push    rdi
0x18000683a  sub     rsp, 20h
0x18000683e  mov     rbx, [rcx+40h]
0x180006842  mov     rdi, rdx
0x180006845  test    rbx, rbx
0x180006848  jz      short loc_18000687A
0x18000684a  mov     rcx, [rbx+5B8h]; this
0x180006851  test    rcx, rcx
0x180006854  jz      short loc_180006867
0x180006856  mov     rdx, rdi; struct CLogInfo *
0x180006859  call    ?IsSameLog@CLogInfo@@QEBAHPEAV1@@Z; CLogInfo::IsSameLog(CLogInfo *)
0x18000685e  test    eax, eax
0x180006860  jz      short loc_180006867
0x180006862  or      word ptr [rbx+50h], 1
0x180006867  mov     rax, [rbx+40h]
0x18000686b  lea     rcx, [rax-38h]
0x18000686f  neg     rax
0x180006872  sbb     rbx, rbx
0x180006875  and     rbx, rcx
0x180006878  jnz     short loc_18000684A
0x18000687a  mov     rbx, [rsp+28h+arg_0]
0x18000687f  add     rsp, 20h
0x180006883  pop     rdi
0x180006884  retn
```
