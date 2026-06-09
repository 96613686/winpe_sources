# DllGetClassObject

- ea: `0x18000d470`
- end: `0x18000d551`
- name: `DllGetClassObject`
- size: `225`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000d470`
- `0x180022010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d4a3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d4d8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d4a3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000d4d8`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  _DWORD *v5; // rdi
  void **v6; // rax
  HRESULT v7; // ebx

  if ( *(_OWORD *)rclsid == *(_OWORD *)&CLSID_DirectMusic )
  {
    v5 = malloc(0x10u);
    if ( v5 )
    {
      v6 = &CDirectMusicFactory::`vftable';
LABEL_8:
      *(_QWORD *)v5 = v6;
      v5[2] = 1;
      _InterlockedIncrement(&g_cLock);
      v7 = (**(__int64 (__fastcall ***)(_DWORD *, const IID *const, LPVOID *))v5)(v5, riid, ppv);
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
      return v7;
    }
LABEL_9:
    *ppv = 0;
    return -2147024882;
  }
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_DirectMusicCollection.Data1
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_DirectMusicCollection.Data4 )
  {
    v5 = malloc(0x10u);
    if ( v5 )
    {
      v6 = &CDirectMusicCollectionFactory::`vftable';
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
0x18000d470  mov     [rsp+arg_0], rbx
0x18000d475  mov     [rsp+arg_8], rsi
0x18000d47a  push    rdi
0x18000d47b  sub     rsp, 20h
0x18000d47f  mov     rax, [rcx]
0x18000d482  mov     rbx, r8
0x18000d485  cmp     rax, qword ptr cs:CLSID_DirectMusic.Data1
0x18000d48c  mov     rsi, rdx
0x18000d48f  jnz     short loc_18000D4BA
0x18000d491  mov     rax, [rcx+8]
0x18000d495  cmp     rax, qword ptr cs:CLSID_DirectMusic.Data4
0x18000d49c  jnz     short loc_18000D4BA
0x18000d49e  mov     ecx, 10h; Size
0x18000d4a3  call    cs:__imp_malloc
0x18000d4a9  mov     rdi, rax
0x18000d4ac  test    rax, rax
0x18000d4af  jz      short loc_18000D527
0x18000d4b1  lea     rax, ??_7CDirectMusicFactory@@6B@; const CDirectMusicFactory::`vftable'
0x18000d4b8  jmp     short loc_18000D4ED
0x18000d4ba  mov     rax, [rcx]
0x18000d4bd  cmp     rax, qword ptr cs:CLSID_DirectMusicCollection.Data1
0x18000d4c4  jnz     short loc_18000D535
0x18000d4c6  mov     rax, [rcx+8]
0x18000d4ca  cmp     rax, qword ptr cs:CLSID_DirectMusicCollection.Data4
0x18000d4d1  jnz     short loc_18000D535
0x18000d4d3  mov     ecx, 10h; Size
0x18000d4d8  call    cs:__imp_malloc
0x18000d4de  mov     rdi, rax
0x18000d4e1  test    rax, rax
0x18000d4e4  jz      short loc_18000D527
0x18000d4e6  lea     rax, ??_7CDirectMusicCollectionFactory@@6B@; const CDirectMusicCollectionFactory::`vftable'
0x18000d4ed  mov     [rdi], rax
0x18000d4f0  mov     dword ptr [rdi+8], 1
0x18000d4f7  lock inc cs:?g_cLock@@3JA; long g_cLock
0x18000d4fe  mov     rax, [rdi]
0x18000d501  mov     r8, rbx
0x18000d504  mov     rdx, rsi
0x18000d507  mov     rcx, rdi
0x18000d50a  mov     rax, [rax]
0x18000d50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d512  mov     rdx, [rdi]
0x18000d515  mov     ebx, eax
0x18000d517  mov     rcx, rdi
0x18000d51a  mov     rax, [rdx+10h]
0x18000d51e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d523  mov     eax, ebx
0x18000d525  jmp     short loc_18000D541
0x18000d527  mov     qword ptr [rbx], 0
0x18000d52e  mov     eax, 8007000Eh
0x18000d533  jmp     short loc_18000D541
0x18000d535  mov     qword ptr [r8], 0
0x18000d53c  mov     eax, 80040111h
0x18000d541  mov     rbx, [rsp+28h+arg_0]
0x18000d546  mov     rsi, [rsp+28h+arg_8]
0x18000d54b  add     rsp, 20h
0x18000d54f  pop     rdi
0x18000d550  retn
```
