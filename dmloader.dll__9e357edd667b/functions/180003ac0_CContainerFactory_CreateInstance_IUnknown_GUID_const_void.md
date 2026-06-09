# CContainerFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003ac0`
- end: `0x180003bbc`
- name: `?CreateInstance@CContainerFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `252`
- prototype: `int(CContainerFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003ac0`
- `0x18000f240`
- `0x18000f640`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003aff`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003aff`

## pseudocode

```c
__int64 __fastcall CContainerFactory::CreateInstance(
        CContainerFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  CContainer *v7; // rax
  CContainer *v8; // rdi
  unsigned int Interface; // ebx

  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return 2147746064LL;
  try
  {
    v7 = (CContainer *)malloc(0x370u);
    v8 = v7;
    if ( v7 )
    {
      *((_QWORD *)v7 + 3) = &IDirectMusicObjectP::`vftable';
      *(_QWORD *)v7 = &CContainer::`vftable'{for `IDirectMusicContainer'};
      *((_QWORD *)v7 + 1) = &CContainer::`vftable'{for `IDirectMusicObject'};
      *((_QWORD *)v7 + 2) = &CContainer::`vftable'{for `IPersistStream'};
      *((_QWORD *)v7 + 3) = &CContainer::`vftable'{for `IDirectMusicObjectP'};
      *((_QWORD *)v7 + 5) = 0;
      _InterlockedIncrement(&g_cLoaderComponent);
      *((_DWORD *)v7 + 12) = 1;
      *((_DWORD *)v7 + 13) = 0;
      *((_DWORD *)v7 + 14) = 0;
      *((_DWORD *)v7 + 15) = 0;
      *((_QWORD *)v7 + 4) = 0;
      *((_BYTE *)v7 + 872) = 0;
    }
    else
    {
      v8 = 0;
    }
  }
  catch ( ... )
  {
    return 2147942414LL;
  }
  if ( !v8 )
    return 2147942414LL;
  Interface = CContainer::QueryInterface(v8, a3, a4);
  CContainer::Release(v8);
  return Interface;
}

```

## disassembly

```asm
0x180003ac0  mov     [rsp+arg_0], rbx
0x180003ac5  mov     [rsp+arg_8], rsi
0x180003aca  push    rdi
0x180003acb  sub     rsp, 30h
0x180003acf  mov     rbx, r9
0x180003ad2  mov     rsi, r8
0x180003ad5  test    r9, r9
0x180003ad8  jnz     short loc_180003AE4
0x180003ada  mov     eax, 80004003h
0x180003adf  jmp     loc_180003BAC
0x180003ae4  mov     qword ptr [r9], 0
0x180003aeb  test    rdx, rdx
0x180003aee  jz      short loc_180003AFA
0x180003af0  mov     eax, 80040110h
0x180003af5  jmp     loc_180003BAC
0x180003afa  mov     ecx, 370h; Size
0x180003aff  call    cs:__imp_malloc
0x180003b05  mov     rdi, rax
0x180003b08  test    rax, rax
0x180003b0b  jz      short loc_180003B7F
0x180003b0d  lea     rax, ??_7IDirectMusicObjectP@@6B@; const IDirectMusicObjectP::`vftable'
0x180003b14  mov     [rdi+18h], rax
0x180003b18  lea     rax, ??_7CContainer@@6BIDirectMusicContainer@@@; const CContainer::`vftable'{for `IDirectMusicContainer'}
0x180003b1f  mov     [rdi], rax
0x180003b22  lea     rax, ??_7CContainer@@6BIDirectMusicObject@@@; const CContainer::`vftable'{for `IDirectMusicObject'}
0x180003b29  mov     [rdi+8], rax
0x180003b2d  lea     rax, ??_7CContainer@@6BIPersistStream@@@; const CContainer::`vftable'{for `IPersistStream'}
0x180003b34  mov     [rdi+10h], rax
0x180003b38  lea     rax, ??_7CContainer@@6BIDirectMusicObjectP@@@; const CContainer::`vftable'{for `IDirectMusicObjectP'}
0x180003b3f  mov     [rdi+18h], rax
0x180003b43  mov     qword ptr [rdi+28h], 0
0x180003b4b  lock inc cs:?g_cLoaderComponent@@3JA; long g_cLoaderComponent
0x180003b52  mov     dword ptr [rdi+30h], 1
0x180003b59  mov     dword ptr [rdi+34h], 0
0x180003b60  mov     dword ptr [rdi+38h], 0
0x180003b67  mov     dword ptr [rdi+3Ch], 0
0x180003b6e  mov     qword ptr [rdi+20h], 0
0x180003b76  mov     byte ptr [rdi+368h], 0
0x180003b7d  jmp     short loc_180003B81
0x180003b7f  xor     edi, edi
0x180003b81  mov     [rsp+38h+var_18], rdi
0x180003b86  test    rdi, rdi
0x180003b89  jz      short loc_180003BA7
0x180003b8b  mov     r8, rbx; void **
0x180003b8e  mov     rdx, rsi; struct _GUID *
0x180003b91  mov     rcx, rdi; this
0x180003b94  call    ?QueryInterface@CContainer@@UEAAJAEBU_GUID@@PEAPEAX@Z; CContainer::QueryInterface(_GUID const &,void * *)
0x180003b99  mov     ebx, eax
0x180003b9b  mov     rcx, rdi; this
0x180003b9e  call    ?Release@CContainer@@UEAAKXZ; CContainer::Release(void)
0x180003ba3  mov     eax, ebx
0x180003ba5  jmp     short loc_180003BAC
0x180003ba7  mov     eax, 8007000Eh
0x180003bac  mov     rbx, [rsp+38h+arg_0]
0x180003bb1  mov     rsi, [rsp+38h+arg_8]
0x180003bb6  add     rsp, 30h
0x180003bba  pop     rdi
0x180003bbb  retn
```
