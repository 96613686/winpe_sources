# CreateCodecInstance(IUnknown *,long *)

- ea: `0x180007720`
- end: `0x18000776a`
- name: `?CreateCodecInstance@@YAPEAVCComBase@@PEAUIUnknown@@PEAJ@Z`
- size: `74`
- prototype: `struct CComBase *__fastcall(struct IUnknown *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180007720`
- `0x180007770`
- `0x18000a6dc`

## pseudocode

```c
struct CComBase *__fastcall CreateCodecInstance(struct IUnknown *a1, int *a2)
{
  CWMDeColorConvDMO *v4; // rax

  v4 = (CWMDeColorConvDMO *)operator new(0x518u);
  if ( v4 )
    v4 = CWMDeColorConvDMO::CWMDeColorConvDMO(v4, a1, a2);
  return (struct CComBase *)(((unsigned __int64)v4 + 424) & -(__int64)(v4 != 0));
}

```

## disassembly

```asm
0x180007720  mov     [rsp+arg_0], rbx
0x180007725  push    rdi
0x180007726  sub     rsp, 20h
0x18000772a  mov     rdi, rcx
0x18000772d  mov     rbx, rdx
0x180007730  mov     ecx, 518h; Size
0x180007735  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000773a  test    rax, rax
0x18000773d  jz      short loc_180007768
0x18000773f  mov     r8, rbx; int *
0x180007742  mov     rdx, rdi; struct IUnknown *
0x180007745  mov     rcx, rax; this
0x180007748  call    ??0CWMDeColorConvDMO@@QEAA@PEAUIUnknown@@PEAJ@Z; CWMDeColorConvDMO::CWMDeColorConvDMO(IUnknown *,long *)
0x18000774d  mov     rbx, [rsp+28h+arg_0]
0x180007752  lea     rcx, [rax+1A8h]
0x180007759  neg     rax
0x18000775c  sbb     rax, rax
0x18000775f  and     rax, rcx
0x180007762  add     rsp, 20h
0x180007766  pop     rdi
0x180007767  retn
0x180007768  jmp     short loc_18000774D
```
