# CDirectMusicSynthFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000e6f0`
- end: `0x18000e7ac`
- name: `?CreateInstance@CDirectMusicSynthFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `188`
- prototype: `int(CDirectMusicSynthFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000e5c0`
- `0x18000e6f0`
- `0x180011410`
- `0x180012c90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000e745`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000e745`

## pseudocode

```c
__int64 __fastcall CDirectMusicSynthFactory::CreateInstance(
        CDirectMusicSynthFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  CUserModeSynth *v7; // rax
  CUserModeSynth *v8; // rbx
  int Interface; // edi

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  try
  {
    v7 = (CUserModeSynth *)malloc(0x90u);
    if ( v7 )
      v8 = CUserModeSynth::CUserModeSynth(v7);
    else
      v8 = 0;
  }
  catch ( ... )
  {
    return 2147942414LL;
  }
  if ( !v8 )
    return 2147942414LL;
  Interface = CUserModeSynth::QueryInterface(v8, a3, a4);
  if ( Interface < 0 )
    CUserModeSynth::`scalar deleting destructor'(v8);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x18000e6f0  mov     [rsp+arg_0], rbx
0x18000e6f5  mov     [rsp+arg_8], rsi
0x18000e6fa  push    rdi
0x18000e6fb  sub     rsp, 30h
0x18000e6ff  mov     rdi, r9
0x18000e702  mov     rsi, r8
0x18000e705  test    r9, r9
0x18000e708  jnz     short loc_18000E71F
0x18000e70a  mov     eax, 80004003h
0x18000e70f  mov     rbx, [rsp+38h+arg_0]
0x18000e714  mov     rsi, [rsp+38h+arg_8]
0x18000e719  add     rsp, 30h
0x18000e71d  pop     rdi
0x18000e71e  retn
0x18000e71f  mov     qword ptr [r9], 0
0x18000e726  test    rdx, rdx
0x18000e729  jz      short loc_18000E740
0x18000e72b  mov     eax, 80040110h
0x18000e730  mov     rbx, [rsp+38h+arg_0]
0x18000e735  mov     rsi, [rsp+38h+arg_8]
0x18000e73a  add     rsp, 30h
0x18000e73e  pop     rdi
0x18000e73f  retn
0x18000e740  mov     ecx, 90h; Size
0x18000e745  call    cs:__imp_malloc
0x18000e74b  test    rax, rax
0x18000e74e  jz      short loc_18000E75D
0x18000e750  mov     rcx, rax; this
0x18000e753  call    ??0CUserModeSynth@@QEAA@XZ; CUserModeSynth::CUserModeSynth(void)
0x18000e758  mov     rbx, rax
0x18000e75b  jmp     short loc_18000E75F
0x18000e75d  xor     ebx, ebx
0x18000e75f  mov     [rsp+38h+var_18], rbx
0x18000e764  test    rbx, rbx
0x18000e767  jz      short loc_18000E797
0x18000e769  mov     r8, rdi; void **
0x18000e76c  mov     rdx, rsi; struct _GUID *
0x18000e76f  mov     rcx, rbx; this
0x18000e772  call    ?QueryInterface@CUserModeSynth@@UEAAJAEBU_GUID@@PEAPEAX@Z; CUserModeSynth::QueryInterface(_GUID const &,void * *)
0x18000e777  mov     edi, eax
0x18000e779  test    eax, eax
0x18000e77b  jns     short loc_18000E785
0x18000e77d  mov     rcx, rbx; this
0x18000e780  call    ??_GCUserModeSynth@@QEAAPEAXI@Z; CUserModeSynth::`scalar deleting destructor'(uint)
0x18000e785  mov     eax, edi
0x18000e787  mov     rbx, [rsp+38h+arg_0]
0x18000e78c  mov     rsi, [rsp+38h+arg_8]
0x18000e791  add     rsp, 30h
0x18000e795  pop     rdi
0x18000e796  retn
0x18000e797  mov     eax, 8007000Eh
0x18000e79c  mov     rbx, [rsp+38h+arg_0]
0x18000e7a1  mov     rsi, [rsp+38h+arg_8]
0x18000e7a6  add     rsp, 30h
0x18000e7aa  pop     rdi
0x18000e7ab  retn
```
