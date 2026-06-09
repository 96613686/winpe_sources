# CComponentDataCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004fb0`
- end: `0x180005041`
- name: `?CreateInstance@CComponentDataCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `145`
- prototype: `__int64 __fastcall(CComponentDataCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002928`
- `0x180004fb0`
- `0x180005168`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall CComponentDataCF::CreateInstance(
        CComponentDataCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v6; // ebx
  CComponentData *v7; // rax
  CComponentData *v8; // rax
  CComponentData *v9; // rdi

  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      v7 = (CComponentData *)operator new(0x4C0u);
      if ( v7 && (v8 = CComponentData::CComponentData(v7), (v9 = v8) != 0) )
      {
        v6 = (**(__int64 (__fastcall ***)(CComponentData *, const struct _GUID *, void **))v8)(v8, a3, a4);
        (*(void (__fastcall **)(CComponentData *))(*(_QWORD *)v9 + 16LL))(v9);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x180004fb0  mov     [rsp+arg_0], rbx
0x180004fb5  mov     [rsp+arg_8], rsi
0x180004fba  push    rdi
0x180004fbb  sub     rsp, 20h
0x180004fbf  mov     rbx, r9
0x180004fc2  mov     rsi, r8
0x180004fc5  test    r9, r9
0x180004fc8  jnz     short loc_180004FD1
0x180004fca  mov     ebx, 80070057h
0x180004fcf  jmp     short loc_18000502F
0x180004fd1  mov     qword ptr [r9], 0
0x180004fd8  test    rdx, rdx
0x180004fdb  jz      short loc_180004FE4
0x180004fdd  mov     ebx, 80040110h
0x180004fe2  jmp     short loc_18000502F
0x180004fe4  mov     ecx, 4C0h; Size
0x180004fe9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004fee  test    rax, rax
0x180004ff1  jz      short loc_18000502A
0x180004ff3  mov     rcx, rax; this
0x180004ff6  call    ??0CComponentData@@QEAA@XZ; CComponentData::CComponentData(void)
0x180004ffb  mov     rdi, rax
0x180004ffe  test    rax, rax
0x180005001  jz      short loc_18000502A
0x180005003  mov     rax, [rax]
0x180005006  mov     r8, rbx
0x180005009  mov     rdx, rsi
0x18000500c  mov     rcx, rdi
0x18000500f  mov     rax, [rax]
0x180005012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005017  mov     rcx, [rdi]
0x18000501a  mov     ebx, eax
0x18000501c  mov     rax, [rcx+10h]
0x180005020  mov     rcx, rdi
0x180005023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005028  jmp     short loc_18000502F
0x18000502a  mov     ebx, 8007000Eh
0x18000502f  mov     rsi, [rsp+28h+arg_8]
0x180005034  mov     eax, ebx
0x180005036  mov     rbx, [rsp+28h+arg_0]
0x18000503b  add     rsp, 20h
0x18000503f  pop     rdi
0x180005040  retn
```
