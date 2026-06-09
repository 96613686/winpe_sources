# CWrapperOutputPin::GetCreateVideoAcceleratorData(_GUID const *,ulong *,void * *)

- ea: `0x180019540`
- end: `0x1800195ed`
- name: `?GetCreateVideoAcceleratorData@CWrapperOutputPin@@UEAAJPEBU_GUID@@PEAKPEAPEAX@Z`
- size: `173`
- prototype: `__int64 __fastcall(CWrapperOutputPin *__hidden this, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001460`
- `0x180019540`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWrapperOutputPin::GetCreateVideoAcceleratorData(
        CWrapperOutputPin *this,
        const struct _GUID *a2,
        unsigned int *a3,
        void **a4)
{
  __int64 v4; // rax
  int v8; // ebx
  void (*v9)(void); // rax
  __int64 v11; // [rsp+30h] [rbp-38h] BYREF

  v4 = *((_QWORD *)this - 20);
  v11 = 0;
  v8 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(v4 + 160))(
         *(_QWORD *)(v4 + 160),
         &IID_IAMVideoAcceleratorNotify,
         &v11);
  if ( v8 < 0 )
  {
    if ( v11 )
    {
      v9 = *(void (**)(void))(*(_QWORD *)v11 + 16LL);
      goto LABEL_6;
    }
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, unsigned int *, void **))(*(_QWORD *)v11 + 40LL))(
           v11,
           a2,
           a3,
           a4);
    if ( v11 )
    {
      v9 = *(void (**)(void))(*(_QWORD *)v11 + 16LL);
LABEL_6:
      v9();
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180019540  push    rbx
0x180019542  push    rbp
0x180019543  push    rsi
0x180019544  push    rdi
0x180019545  sub     rsp, 48h
0x180019549  mov     rax, cs:__security_cookie
0x180019550  xor     rax, rsp
0x180019553  mov     [rsp+68h+var_30], rax
0x180019558  mov     rax, [rcx-0A0h]
0x18001955f  mov     rsi, r8
0x180019562  mov     [rsp+68h+var_38], 0
0x18001956b  lea     r8, [rsp+68h+var_38]
0x180019570  mov     rdi, rdx
0x180019573  mov     rbp, r9
0x180019576  lea     rdx, IID_IAMVideoAcceleratorNotify
0x18001957d  mov     rcx, [rax+0A0h]
0x180019584  mov     rax, [rcx]
0x180019587  mov     rax, [rax]
0x18001958a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001958f  mov     rcx, [rsp+68h+var_38]
0x180019594  mov     ebx, eax
0x180019596  test    eax, eax
0x180019598  js      short loc_1800195C4
0x18001959a  mov     rax, [rcx]
0x18001959d  mov     r9, rbp
0x1800195a0  mov     r8, rsi
0x1800195a3  mov     rdx, rdi
0x1800195a6  mov     rax, [rax+28h]
0x1800195aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195af  mov     rcx, [rsp+68h+var_38]
0x1800195b4  mov     ebx, eax
0x1800195b6  test    rcx, rcx
0x1800195b9  jz      short loc_1800195D5
0x1800195bb  mov     rdx, [rcx]
0x1800195be  mov     rax, [rdx+10h]
0x1800195c2  jmp     short loc_1800195D0
0x1800195c4  test    rcx, rcx
0x1800195c7  jz      short loc_1800195D5
0x1800195c9  mov     rax, [rcx]
0x1800195cc  mov     rax, [rax+10h]
0x1800195d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195d5  mov     eax, ebx
0x1800195d7  mov     rcx, [rsp+68h+var_30]
0x1800195dc  xor     rcx, rsp; StackCookie
0x1800195df  call    __security_check_cookie
0x1800195e4  add     rsp, 48h
0x1800195e8  pop     rdi
0x1800195e9  pop     rsi
0x1800195ea  pop     rbp
0x1800195eb  pop     rbx
0x1800195ec  retn
```
