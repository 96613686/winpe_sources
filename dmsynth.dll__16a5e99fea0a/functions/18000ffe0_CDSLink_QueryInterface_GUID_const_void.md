# CDSLink::QueryInterface(_GUID const &,void * *)

- ea: `0x18000ffe0`
- end: `0x180010081`
- name: `?QueryInterface@CDSLink@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `161`
- prototype: `__int64 __fastcall(CDSLink *__hidden this, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e7c0`
- `0x180010090`

## callees

- `0x18000ffe0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CDSLink::QueryInterface(CDSLink *this, const struct _GUID *a2, void **a3)
{
  CDSLink *v3; // r9

  v3 = this;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( !a2 )
    return 2147500035LL;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IUnknown.Data1 && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IUnknown.Data4
    || *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IDirectMusicSynthSink.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IDirectMusicSynthSink.Data4 )
  {
    goto LABEL_11;
  }
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IKsControl.Data1
    && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IKsControl.Data4 )
  {
    this = (CDSLink *)((char *)this + 8);
    if ( !v3 )
      this = 0;
LABEL_11:
    *a3 = this;
    (*(void (__fastcall **)(CDSLink *))(*(_QWORD *)v3 + 8LL))(v3);
    return 0;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x18000ffe0  sub     rsp, 28h
0x18000ffe4  mov     r9, rcx
0x18000ffe7  test    r8, r8
0x18000ffea  jz      loc_180010077
0x18000fff0  mov     qword ptr [r8], 0
0x18000fff7  test    rdx, rdx
0x18000fffa  jz      short loc_180010077
0x18000fffc  mov     rax, [rdx]
0x18000ffff  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x180010006  jnz     short loc_180010015
0x180010008  mov     rax, [rdx+8]
0x18001000c  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x180010013  jz      short loc_180010054
0x180010015  mov     rax, [rdx]
0x180010018  cmp     rax, qword ptr cs:IID_IDirectMusicSynthSink.Data1
0x18001001f  jnz     short loc_18001002E
0x180010021  mov     rax, [rdx+8]
0x180010025  cmp     rax, qword ptr cs:IID_IDirectMusicSynthSink.Data4
0x18001002c  jz      short loc_180010054
0x18001002e  mov     rax, [rdx]
0x180010031  cmp     rax, qword ptr cs:IID_IKsControl.Data1
0x180010038  jnz     short loc_18001006D
0x18001003a  mov     rax, [rdx+8]
0x18001003e  cmp     rax, qword ptr cs:IID_IKsControl.Data4
0x180010045  jnz     short loc_18001006D
0x180010047  add     rcx, 8
0x18001004b  xor     eax, eax
0x18001004d  test    r9, r9
0x180010050  cmovz   rcx, rax
0x180010054  mov     [r8], rcx
0x180010057  mov     rcx, r9
0x18001005a  mov     rax, [r9]
0x18001005d  mov     rax, [rax+8]
0x180010061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010066  xor     eax, eax
0x180010068  add     rsp, 28h
0x18001006c  retn
0x18001006d  mov     eax, 80004002h
0x180010072  add     rsp, 28h
0x180010076  retn
0x180010077  mov     eax, 80004003h
0x18001007c  add     rsp, 28h
0x180010080  retn
```
