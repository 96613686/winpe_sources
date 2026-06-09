# CIEAdminBrokerClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140003a10`
- end: `0x140003af0`
- name: `?CreateInstance@CIEAdminBrokerClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `224`
- prototype: `__int64 __fastcall(CIEAdminBrokerClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140003978`
- `0x140003a10`
- `0x140004108`
- `0x140011010`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerClassFactory::CreateInstance(
        CIEAdminBrokerClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  unsigned int v9; // esi

  if ( a2 )
  {
    *a4 = 0;
    return 2147746064LL;
  }
  else
  {
    v7 = operator new(0x30u);
    v8 = v7;
    if ( v7 )
    {
      *v7 = &CIEAdminBrokerObject::`vftable'{for `IeAxiAdminInstaller'};
      v7[1] = &CIEAdminBrokerObject::`vftable'{for `IeAxiSystemInstaller'};
      v7[2] = &CIEAdminBrokerObject::`vftable'{for `IeAxiInstaller2'};
      _InterlockedAdd(&g_ObjectCount, 1u);
      *((_DWORD *)v7 + 6) = 1;
      v7[4] = 0;
      v7[5] = 0;
      if ( _InterlockedExchangeAdd(&g_LockCount, 1u) == -1 )
      {
        _InterlockedAdd(&g_LockCount, 1u);
        RegisterClassFactory();
      }
      v9 = (*(__int64 (__fastcall **)(_QWORD *, const struct _GUID *, void **))*v8)(v8, a3, a4);
      (*(void (__fastcall **)(_QWORD *))(*v8 + 16LL))(v8);
    }
    else
    {
      v9 = -2147024882;
      *a4 = 0;
    }
    return v9;
  }
}

```

## disassembly

```asm
0x140003a10  mov     [rsp+arg_0], rbx
0x140003a15  mov     [rsp+arg_8], rsi
0x140003a1a  push    rdi
0x140003a1b  sub     rsp, 20h
0x140003a1f  mov     rdi, r9
0x140003a22  mov     rsi, r8
0x140003a25  test    rdx, rdx
0x140003a28  jz      short loc_140003A3B
0x140003a2a  mov     qword ptr [r9], 0
0x140003a31  mov     eax, 80040110h
0x140003a36  jmp     loc_140003ADF
0x140003a3b  mov     ecx, 30h ; '0'; dwBytes
0x140003a40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140003a45  mov     rbx, rax
0x140003a48  test    rax, rax
0x140003a4b  jz      loc_140003AD1
0x140003a51  lea     rax, ??_7CIEAdminBrokerObject@@6BIeAxiAdminInstaller@@@; const CIEAdminBrokerObject::`vftable'{for `IeAxiAdminInstaller'}
0x140003a58  mov     ecx, 1
0x140003a5d  mov     [rbx], rax
0x140003a60  lea     rax, ??_7CIEAdminBrokerObject@@6BIeAxiSystemInstaller@@@; const CIEAdminBrokerObject::`vftable'{for `IeAxiSystemInstaller'}
0x140003a67  mov     [rbx+8], rax
0x140003a6b  lea     rax, ??_7CIEAdminBrokerObject@@6BIeAxiInstaller2@@@; const CIEAdminBrokerObject::`vftable'{for `IeAxiInstaller2'}
0x140003a72  mov     [rbx+10h], rax
0x140003a76  lock add cs:?g_ObjectCount@@3JA, ecx; long g_ObjectCount
0x140003a7d  mov     [rbx+18h], ecx
0x140003a80  mov     eax, ecx
0x140003a82  mov     qword ptr [rbx+20h], 0
0x140003a8a  mov     qword ptr [rbx+28h], 0
0x140003a92  lock xadd cs:?g_LockCount@@3JA, eax; long g_LockCount
0x140003a9a  add     eax, ecx
0x140003a9c  jnz     short loc_140003AAA
0x140003a9e  lock add cs:?g_LockCount@@3JA, ecx; long g_LockCount
0x140003aa5  call    ?RegisterClassFactory@@YAJXZ; RegisterClassFactory(void)
0x140003aaa  mov     rax, [rbx]
0x140003aad  mov     r8, rdi
0x140003ab0  mov     rdx, rsi
0x140003ab3  mov     rcx, rbx
0x140003ab6  mov     rax, [rax]
0x140003ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003abe  mov     rcx, [rbx]
0x140003ac1  mov     esi, eax
0x140003ac3  mov     rax, [rcx+10h]
0x140003ac7  mov     rcx, rbx
0x140003aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003acf  jmp     short loc_140003ADD
0x140003ad1  mov     esi, 8007000Eh
0x140003ad6  mov     qword ptr [rdi], 0
0x140003add  mov     eax, esi
0x140003adf  mov     rbx, [rsp+28h+arg_0]
0x140003ae4  mov     rsi, [rsp+28h+arg_8]
0x140003ae9  add     rsp, 20h
0x140003aed  pop     rdi
0x140003aee  retn
```
