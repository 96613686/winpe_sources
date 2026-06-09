# COConnectionPoint::Advise(IUnknown *,ulong *)

- ea: `0x18000c6e0`
- end: `0x18000c8be`
- name: `?Advise@COConnectionPoint@@UEAAJPEAUIUnknown@@PEAK@Z`
- size: `478`
- prototype: `__int64 __fastcall(COConnectionPoint *__hidden this, struct IUnknown *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000c6e0`
- `0x18000cc5c`
- `0x18000d5e0`
- `0x180010010`

## import_xrefs

- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c84b`
- `IisRTL!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c84b`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c7ef`
- `IisRTL!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c7ef`

## pseudocode

```c
__int64 __fastcall COConnectionPoint::Advise(COConnectionPoint *this, struct IUnknown *a2, unsigned int *a3)
{
  int Slot; // ebx
  int v7; // eax
  __int64 v8; // r8
  unsigned int v10; // [rsp+30h] [rbp-10h] BYREF
  struct IUnknown *v11; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v12; // [rsp+68h] [rbp+28h] BYREF
  int v13; // [rsp+78h] [rbp+38h] BYREF

  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  if ( a2 && a3 )
  {
    *a3 = 0;
    if ( *((_DWORD *)this + 10) )
    {
      Slot = -2147418113;
    }
    else
    {
      Slot = SetSinkCallbackSecurityBlanket(a2);
      if ( Slot >= 0 )
      {
        v7 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
               a2,
               &IID_IMSAdminBaseSink_W,
               &v11);
        Slot = v7;
        if ( v7 == -2147467262 )
        {
          Slot = -2147220990;
        }
        else if ( v7 >= 0 )
        {
          Slot = SetSinkCallbackSecurityBlanket(v11);
          if ( Slot >= 0 )
          {
            Slot = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown *, GUID *, unsigned int *))(**((_QWORD **)this + 6)
                                                                                                + 24LL))(
                     *((_QWORD *)this + 6),
                     a2,
                     &IID_IUnknown,
                     &v12);
            if ( Slot >= 0 )
            {
              Slot = (*(__int64 (__fastcall **)(_QWORD, struct IUnknown *, GUID *, int *))(**((_QWORD **)this + 6) + 24LL))(
                       *((_QWORD *)this + 6),
                       v11,
                       &IID_IMSAdminBaseSink_W,
                       &v13);
              if ( Slot >= 0 )
              {
                CReaderWriterLock3::WriteLock((COConnectionPoint *)((char *)this + 8));
                if ( *((_DWORD *)this + 10) )
                {
                  Slot = -2147418113;
                }
                else
                {
                  Slot = COConnectionPoint::GetSlot(this, &v10);
                  if ( Slot >= 0 )
                  {
                    v8 = v10;
                    *(_DWORD *)(*((_QWORD *)this + 4) + 8LL * v10) = v12;
                    *(_DWORD *)(*((_QWORD *)this + 4) + 8 * v8 + 4) = v13;
                    *a3 = v12;
                    ++*((_DWORD *)this + 6);
                    v12 = 0;
                    v13 = 0;
                  }
                }
                CReaderWriterLock3::WriteUnlock((COConnectionPoint *)((char *)this + 8));
              }
            }
          }
        }
      }
    }
  }
  else
  {
    Slot = -2147024809;
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 32LL))(*((_QWORD *)this + 6));
    v12 = 0;
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 32LL))(*((_QWORD *)this + 6));
    v13 = 0;
  }
  if ( v11 )
    ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->Release)(v11);
  return (unsigned int)Slot;
}

```

## disassembly

```asm
0x18000c6e0  mov     [rsp-18h+arg_0], rbx
0x18000c6e5  mov     [rsp-18h+arg_10], rsi
0x18000c6ea  push    rbp
0x18000c6eb  push    rdi
0x18000c6ec  push    r14
0x18000c6ee  mov     rbp, rsp
0x18000c6f1  sub     rsp, 40h
0x18000c6f5  mov     [rbp+var_10], 0
0x18000c6fc  mov     r14, r8
0x18000c6ff  mov     [rbp+var_8], 0
0x18000c707  mov     rsi, rdx
0x18000c70a  mov     [rbp+arg_8], 0
0x18000c711  mov     rdi, rcx
0x18000c714  mov     [rbp+arg_18], 0
0x18000c71b  test    rdx, rdx
0x18000c71e  jz      loc_18000C853
0x18000c724  test    r8, r8
0x18000c727  jz      loc_18000C853
0x18000c72d  mov     dword ptr [r8], 0
0x18000c734  mov     eax, [rcx+28h]
0x18000c737  test    eax, eax
0x18000c739  jz      short loc_18000C745
0x18000c73b  mov     ebx, 8000FFFFh
0x18000c740  jmp     loc_18000C858
0x18000c745  mov     rcx, rsi; struct IUnknown *
0x18000c748  call    ?SetSinkCallbackSecurityBlanket@@YAJPEAUIUnknown@@@Z; SetSinkCallbackSecurityBlanket(IUnknown *)
0x18000c74d  mov     ebx, eax
0x18000c74f  test    eax, eax
0x18000c751  js      loc_18000C858
0x18000c757  mov     rax, [rsi]
0x18000c75a  lea     r8, [rbp+var_8]
0x18000c75e  lea     rdx, IID_IMSAdminBaseSink_W
0x18000c765  mov     rcx, rsi
0x18000c768  mov     rax, [rax]
0x18000c76b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c770  mov     ebx, eax
0x18000c772  cmp     eax, 80004002h
0x18000c777  jnz     short loc_18000C783
0x18000c779  mov     ebx, 80040202h
0x18000c77e  jmp     loc_18000C858
0x18000c783  test    eax, eax
0x18000c785  js      loc_18000C858
0x18000c78b  mov     rcx, [rbp+var_8]; struct IUnknown *
0x18000c78f  call    ?SetSinkCallbackSecurityBlanket@@YAJPEAUIUnknown@@@Z; SetSinkCallbackSecurityBlanket(IUnknown *)
0x18000c794  mov     ebx, eax
0x18000c796  test    eax, eax
0x18000c798  js      loc_18000C858
0x18000c79e  mov     rcx, [rdi+30h]
0x18000c7a2  lea     r9, [rbp+arg_8]
0x18000c7a6  lea     r8, IID_IUnknown
0x18000c7ad  mov     rdx, rsi
0x18000c7b0  mov     rax, [rcx]
0x18000c7b3  mov     rax, [rax+18h]
0x18000c7b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7bc  mov     ebx, eax
0x18000c7be  test    eax, eax
0x18000c7c0  js      loc_18000C858
0x18000c7c6  mov     rcx, [rdi+30h]
0x18000c7ca  lea     r9, [rbp+arg_18]
0x18000c7ce  mov     rdx, [rbp+var_8]
0x18000c7d2  lea     r8, IID_IMSAdminBaseSink_W
0x18000c7d9  mov     rax, [rcx]
0x18000c7dc  mov     rax, [rax+18h]
0x18000c7e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7e5  mov     ebx, eax
0x18000c7e7  test    eax, eax
0x18000c7e9  js      short loc_18000C858
0x18000c7eb  lea     rcx, [rdi+8]
0x18000c7ef  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000c7f5  mov     eax, [rdi+28h]
0x18000c7f8  test    eax, eax
0x18000c7fa  jz      short loc_18000C803
0x18000c7fc  mov     ebx, 8000FFFFh
0x18000c801  jmp     short loc_18000C847
0x18000c803  lea     rdx, [rbp+var_10]; unsigned int *
0x18000c807  mov     rcx, rdi; this
0x18000c80a  call    ?GetSlot@COConnectionPoint@@AEAAJPEAI@Z; COConnectionPoint::GetSlot(uint *)
0x18000c80f  mov     ebx, eax
0x18000c811  test    eax, eax
0x18000c813  js      short loc_18000C847
0x18000c815  mov     rdx, [rdi+20h]
0x18000c819  mov     eax, [rbp+arg_8]
0x18000c81c  mov     r8d, [rbp+var_10]
0x18000c820  mov     [rdx+r8*8], eax
0x18000c824  mov     eax, [rbp+arg_18]
0x18000c827  mov     rdx, [rdi+20h]
0x18000c82b  mov     [rdx+r8*8+4], eax
0x18000c830  mov     eax, [rbp+arg_8]
0x18000c833  mov     [r14], eax
0x18000c836  inc     dword ptr [rdi+18h]
0x18000c839  mov     [rbp+arg_8], 0
0x18000c840  mov     [rbp+arg_18], 0
0x18000c847  lea     rcx, [rdi+8]
0x18000c84b  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000c851  jmp     short loc_18000C858
0x18000c853  mov     ebx, 80070057h
0x18000c858  mov     edx, [rbp+arg_8]
0x18000c85b  test    edx, edx
0x18000c85d  jz      short loc_18000C876
0x18000c85f  mov     rcx, [rdi+30h]
0x18000c863  mov     rax, [rcx]
0x18000c866  mov     rax, [rax+20h]
0x18000c86a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c86f  mov     [rbp+arg_8], 0
0x18000c876  mov     edx, [rbp+arg_18]
0x18000c879  test    edx, edx
0x18000c87b  jz      short loc_18000C894
0x18000c87d  mov     rcx, [rdi+30h]
0x18000c881  mov     rax, [rcx]
0x18000c884  mov     rax, [rax+20h]
0x18000c888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c88d  mov     [rbp+arg_18], 0
0x18000c894  mov     rcx, [rbp+var_8]
0x18000c898  test    rcx, rcx
0x18000c89b  jz      short loc_18000C8A9
0x18000c89d  mov     rax, [rcx]
0x18000c8a0  mov     rax, [rax+10h]
0x18000c8a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8a9  mov     rsi, [rsp+40h+arg_10]
0x18000c8ae  mov     eax, ebx
0x18000c8b0  mov     rbx, [rsp+40h+arg_0]
0x18000c8b5  add     rsp, 40h
0x18000c8b9  pop     r14
0x18000c8bb  pop     rdi
0x18000c8bc  pop     rbp
0x18000c8bd  retn
```
