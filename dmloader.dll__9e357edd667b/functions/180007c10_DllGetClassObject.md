# DllGetClassObject

- ea: `0x180007c10`
- end: `0x180007cf1`
- name: `DllGetClassObject`
- size: `225`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180007c10`
- `0x180010010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007c43`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007c78`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007c43`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180007c78`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  _DWORD *v5; // rdi
  void **v6; // rax
  HRESULT v7; // ebx

  if ( *(_OWORD *)rclsid == *(_OWORD *)&CLSID_DirectMusicLoader )
  {
    v5 = malloc(0x10u);
    if ( v5 )
    {
      v6 = &CLoaderFactory::`vftable';
LABEL_8:
      *(_QWORD *)v5 = v6;
      v5[2] = 1;
      _InterlockedIncrement(&g_cLoaderLock);
      v7 = (**(__int64 (__fastcall ***)(_DWORD *, const IID *const, LPVOID *))v5)(v5, riid, ppv);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
      return v7;
    }
LABEL_9:
    *ppv = 0;
    return -2147024882;
  }
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_DirectMusicContainer.Data1
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_DirectMusicContainer.Data4 )
  {
    v5 = malloc(0x10u);
    if ( v5 )
    {
      v6 = &CContainerFactory::`vftable';
      goto LABEL_8;
    }
    goto LABEL_9;
  }
  *ppv = 0;
  return -2147221231;
}

```

## disassembly

```asm
0x180007c10  mov     [rsp+arg_0], rbx
0x180007c15  mov     [rsp+arg_8], rsi
0x180007c1a  push    rdi
0x180007c1b  sub     rsp, 20h
0x180007c1f  mov     rax, [rcx]
0x180007c22  mov     rbx, r8
0x180007c25  cmp     rax, qword ptr cs:CLSID_DirectMusicLoader.Data1
0x180007c2c  mov     rsi, rdx
0x180007c2f  jnz     short loc_180007C5A
0x180007c31  mov     rax, [rcx+8]
0x180007c35  cmp     rax, qword ptr cs:CLSID_DirectMusicLoader.Data4
0x180007c3c  jnz     short loc_180007C5A
0x180007c3e  mov     ecx, 10h; Size
0x180007c43  call    cs:__imp_malloc
0x180007c49  mov     rdi, rax
0x180007c4c  test    rax, rax
0x180007c4f  jz      short loc_180007CC7
0x180007c51  lea     rax, ??_7CLoaderFactory@@6B@; const CLoaderFactory::`vftable'
0x180007c58  jmp     short loc_180007C8D
0x180007c5a  mov     rax, [rcx]
0x180007c5d  cmp     rax, qword ptr cs:CLSID_DirectMusicContainer.Data1
0x180007c64  jnz     short loc_180007CD5
0x180007c66  mov     rax, [rcx+8]
0x180007c6a  cmp     rax, qword ptr cs:CLSID_DirectMusicContainer.Data4
0x180007c71  jnz     short loc_180007CD5
0x180007c73  mov     ecx, 10h; Size
0x180007c78  call    cs:__imp_malloc
0x180007c7e  mov     rdi, rax
0x180007c81  test    rax, rax
0x180007c84  jz      short loc_180007CC7
0x180007c86  lea     rax, ??_7CContainerFactory@@6B@; const CContainerFactory::`vftable'
0x180007c8d  mov     [rdi], rax
0x180007c90  mov     dword ptr [rdi+8], 1
0x180007c97  lock inc cs:?g_cLoaderLock@@3JA; long g_cLoaderLock
0x180007c9e  mov     rax, [rdi]
0x180007ca1  mov     r8, rbx
0x180007ca4  mov     rdx, rsi
0x180007ca7  mov     rcx, rdi
0x180007caa  mov     rax, [rax]
0x180007cad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cb2  mov     rdx, [rdi]
0x180007cb5  mov     ebx, eax
0x180007cb7  mov     rcx, rdi
0x180007cba  mov     rax, [rdx+10h]
0x180007cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cc3  mov     eax, ebx
0x180007cc5  jmp     short loc_180007CE1
0x180007cc7  mov     qword ptr [rbx], 0
0x180007cce  mov     eax, 8007000Eh
0x180007cd3  jmp     short loc_180007CE1
0x180007cd5  mov     qword ptr [r8], 0
0x180007cdc  mov     eax, 80040111h
0x180007ce1  mov     rbx, [rsp+28h+arg_0]
0x180007ce6  mov     rsi, [rsp+28h+arg_8]
0x180007ceb  add     rsp, 20h
0x180007cef  pop     rdi
0x180007cf0  retn
```
