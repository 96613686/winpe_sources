# CADMCOMSrvFactoryW::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180009dd0`
- end: `0x180009e56`
- name: `?CreateInstance@CADMCOMSrvFactoryW@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `134`
- prototype: `__int64 __fastcall(CADMCOMSrvFactoryW *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001064`
- `0x180001a98`
- `0x1800068d4`
- `0x180009dd0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CADMCOMSrvFactoryW::CreateInstance(
        CADMCOMSrvFactoryW *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  int v6; // ebx
  CADMCOMW *v7; // rax
  CADMCOMW *v8; // rax
  CADMCOMW *v9; // rdi

  *a4 = 0;
  if ( a2 )
  {
    return (unsigned int)-2147221232;
  }
  else
  {
    v7 = (CADMCOMW *)operator new(0x388u);
    if ( v7 && (v8 = CADMCOMW::CADMCOMW(v7), (v9 = v8) != 0) )
    {
      v6 = CADMCOMW::Init(v8);
      if ( v6 >= 0 )
        v6 = (**(__int64 (__fastcall ***)(CADMCOMW *, const struct _GUID *, void **))v9)(v9, a3, a4);
      (*(void (__fastcall **)(CADMCOMW *))(*(_QWORD *)v9 + 16LL))(v9);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009dd0  push    rbx
0x180009dd2  push    rbp
0x180009dd3  push    rsi
0x180009dd4  push    rdi
0x180009dd5  sub     rsp, 28h
0x180009dd9  mov     qword ptr [r9], 0
0x180009de0  mov     rsi, r9
0x180009de3  mov     rbp, r8
0x180009de6  test    rdx, rdx
0x180009de9  jz      short loc_180009DF2
0x180009deb  mov     ebx, 80040110h
0x180009df0  jmp     short loc_180009E4B
0x180009df2  mov     ecx, 388h; Size
0x180009df7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009dfc  test    rax, rax
0x180009dff  jz      short loc_180009E46
0x180009e01  mov     rcx, rax; this
0x180009e04  call    ??0CADMCOMW@@QEAA@XZ; CADMCOMW::CADMCOMW(void)
0x180009e09  mov     rdi, rax
0x180009e0c  test    rax, rax
0x180009e0f  jz      short loc_180009E46
0x180009e11  mov     rcx, rax; this
0x180009e14  call    ?Init@CADMCOMW@@QEAAJXZ; CADMCOMW::Init(void)
0x180009e19  mov     ebx, eax
0x180009e1b  test    eax, eax
0x180009e1d  js      short loc_180009E35
0x180009e1f  mov     rax, [rdi]
0x180009e22  mov     r8, rsi
0x180009e25  mov     rdx, rbp
0x180009e28  mov     rcx, rdi
0x180009e2b  mov     rax, [rax]
0x180009e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e33  mov     ebx, eax
0x180009e35  mov     rax, [rdi]
0x180009e38  mov     rcx, rdi
0x180009e3b  mov     rax, [rax+10h]
0x180009e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e44  jmp     short loc_180009E4B
0x180009e46  mov     ebx, 8007000Eh
0x180009e4b  mov     eax, ebx
0x180009e4d  add     rsp, 28h
0x180009e51  pop     rdi
0x180009e52  pop     rsi
0x180009e53  pop     rbp
0x180009e54  pop     rbx
0x180009e55  retn
```
