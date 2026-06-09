# ATL::CComModule::Term(void)

- ea: `0x18000b6fc`
- end: `0x18000b786`
- name: `?Term@CComModule@ATL@@QEAAXXZ`
- size: `138`
- prototype: `void __fastcall(ATL::CComModule *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001160`

## callees

- `0x18000b644`
- `0x18000b6fc`
- `0x18000d010`

## pseudocode

```c
void __fastcall ATL::CComModule::Term(ATL::CComModule *this)
{
  __int64 v1; // rbx
  __int64 v2; // rcx
  __int64 *v3; // rbx
  __int64 *v4; // rax

  v1 = qword_180012928;
  if ( qword_180012928 )
  {
    while ( *(_QWORD *)v1 )
    {
      v2 = *(_QWORD *)(v1 + 32);
      if ( v2 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
      *(_QWORD *)(v1 + 32) = 0;
      (*(void (__fastcall **)(_QWORD))(v1 + 64))(0);
      v1 += 72;
    }
  }
  v3 = (__int64 *)off_1800121B0[0];
  v4 = (__int64 *)off_1800121B8;
  while ( v3 < v4 )
  {
    if ( *v3 )
    {
      (*(void (__fastcall **)(_QWORD))(*v3 + 64))(0);
      v4 = (__int64 *)off_1800121B8;
    }
    ++v3;
  }
  ATL::CAtlModule::Term((ATL::CAtlModule *)&_AtlModule);
}

```

## disassembly

```asm
0x18000b6fc  push    rbx
0x18000b6fe  sub     rsp, 20h
0x18000b702  mov     rbx, cs:qword_180012928
0x18000b709  test    rbx, rbx
0x18000b70c  jz      short loc_18000B742
0x18000b70e  jmp     short loc_18000B73C
0x18000b710  mov     rcx, [rbx+20h]
0x18000b714  test    rcx, rcx
0x18000b717  jz      short loc_18000B725
0x18000b719  mov     rax, [rcx]
0x18000b71c  mov     rax, [rax+10h]
0x18000b720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b725  mov     qword ptr [rbx+20h], 0
0x18000b72d  xor     ecx, ecx
0x18000b72f  mov     rax, [rbx+40h]
0x18000b733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b738  add     rbx, 48h ; 'H'
0x18000b73c  cmp     qword ptr [rbx], 0
0x18000b740  jnz     short loc_18000B710
0x18000b742  mov     rbx, cs:off_1800121B0
0x18000b749  mov     rax, cs:off_1800121B8
0x18000b750  jmp     short loc_18000B770
0x18000b752  mov     rdx, [rbx]
0x18000b755  test    rdx, rdx
0x18000b758  jz      short loc_18000B76C
0x18000b75a  xor     ecx, ecx
0x18000b75c  mov     rax, [rdx+40h]
0x18000b760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b765  mov     rax, cs:off_1800121B8
0x18000b76c  add     rbx, 8
0x18000b770  cmp     rbx, rax
0x18000b773  jb      short loc_18000B752
0x18000b775  lea     rcx, ?_AtlModule@@3VCComModule@ATL@@A; this
0x18000b77c  add     rsp, 20h
0x18000b780  pop     rbx
0x18000b781  jmp     ?Term@CAtlModule@ATL@@QEAAXXZ; ATL::CAtlModule::Term(void)
```
