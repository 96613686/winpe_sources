# CASFOutput::GetCreateVideoAcceleratorData(_GUID const *,ulong *,void * *)

- ea: `0x1800098f0`
- end: `0x180009983`
- name: `?GetCreateVideoAcceleratorData@CASFOutput@@UEAAJPEBU_GUID@@PEAKPEAPEAX@Z`
- size: `147`
- prototype: `__int64 __fastcall(CASFOutput *__hidden this, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001460`
- `0x180009838`
- `0x1800098f0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFOutput::GetCreateVideoAcceleratorData(
        CASFOutput *this,
        const struct _GUID *a2,
        unsigned int *a3,
        void **a4)
{
  unsigned int CodecInterface; // ebx
  void *v9; // [rsp+30h] [rbp-38h] BYREF

  v9 = 0;
  CodecInterface = CASFOutput::GetCodecInterface(
                     (CASFOutput *)((char *)this - 232),
                     &IID_IAMVideoAcceleratorNotify,
                     &v9);
  if ( v9 )
  {
    CodecInterface = (*(__int64 (__fastcall **)(void *, const struct _GUID *, unsigned int *, void **))(*(_QWORD *)v9 + 40LL))(
                       v9,
                       a2,
                       a3,
                       a4);
    if ( v9 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return CodecInterface;
}

```

## disassembly

```asm
0x1800098f0  push    rbx
0x1800098f2  push    rbp
0x1800098f3  push    rsi
0x1800098f4  push    rdi
0x1800098f5  sub     rsp, 48h
0x1800098f9  mov     rax, cs:__security_cookie
0x180009900  xor     rax, rsp
0x180009903  mov     [rsp+68h+var_30], rax
0x180009908  mov     rsi, r8
0x18000990b  mov     [rsp+68h+var_38], 0
0x180009914  mov     rdi, rdx
0x180009917  lea     r8, [rsp+68h+var_38]; void **
0x18000991c  lea     rdx, IID_IAMVideoAcceleratorNotify; struct _GUID *
0x180009923  add     rcx, 0FFFFFFFFFFFFFF18h; this
0x18000992a  mov     rbp, r9
0x18000992d  call    ?GetCodecInterface@CASFOutput@@QEAAJAEBU_GUID@@PEAPEAX@Z; CASFOutput::GetCodecInterface(_GUID const &,void * *)
0x180009932  mov     rcx, [rsp+68h+var_38]
0x180009937  mov     ebx, eax
0x180009939  test    rcx, rcx
0x18000993c  jz      short loc_18000996B
0x18000993e  mov     rax, [rcx]
0x180009941  mov     r9, rbp
0x180009944  mov     r8, rsi
0x180009947  mov     rdx, rdi
0x18000994a  mov     rax, [rax+28h]
0x18000994e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009953  mov     rcx, [rsp+68h+var_38]
0x180009958  mov     ebx, eax
0x18000995a  test    rcx, rcx
0x18000995d  jz      short loc_18000996B
0x18000995f  mov     rax, [rcx]
0x180009962  mov     rax, [rax+10h]
0x180009966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000996b  mov     eax, ebx
0x18000996d  mov     rcx, [rsp+68h+var_30]
0x180009972  xor     rcx, rsp; StackCookie
0x180009975  call    __security_check_cookie
0x18000997a  add     rsp, 48h
0x18000997e  pop     rdi
0x18000997f  pop     rsi
0x180009980  pop     rbp
0x180009981  pop     rbx
0x180009982  retn
```
