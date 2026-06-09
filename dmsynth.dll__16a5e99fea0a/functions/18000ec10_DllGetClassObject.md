# DllGetClassObject

- ea: `0x18000ec10`
- end: `0x18000ed1c`
- name: `DllGetClassObject`
- size: `268`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000ec10`
- `0x180015010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000ec43`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000ec84`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000ec43`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18000ec84`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  _DWORD *v5; // rdi
  void **v6; // rax
  HRESULT v7; // ebx
  HRESULT result; // eax

  if ( *(_OWORD *)rclsid == *(_OWORD *)&CLSID_DirectMusicSynth )
  {
    v5 = malloc(0x10u);
    if ( v5 )
    {
      v6 = &CDirectMusicSynthFactory::`vftable';
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
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_DirectMusicSynthSink.Data1
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_DirectMusicSynthSink.Data4 )
  {
    v5 = malloc(0x10u);
    if ( v5 )
    {
      v6 = &CDirectMusicSynthSinkFactory::`vftable';
      goto LABEL_8;
    }
    goto LABEL_9;
  }
  result = -2147221231;
  *ppv = 0;
  return result;
}

```

## disassembly

```asm
0x18000ec10  mov     [rsp+arg_0], rbx
0x18000ec15  mov     [rsp+arg_8], rsi
0x18000ec1a  push    rdi
0x18000ec1b  sub     rsp, 20h
0x18000ec1f  mov     rax, [rcx]
0x18000ec22  mov     rbx, r8
0x18000ec25  cmp     rax, qword ptr cs:CLSID_DirectMusicSynth.Data1
0x18000ec2c  mov     rsi, rdx
0x18000ec2f  jnz     short loc_18000EC5E
0x18000ec31  mov     rax, [rcx+8]
0x18000ec35  cmp     rax, qword ptr cs:CLSID_DirectMusicSynth.Data4
0x18000ec3c  jnz     short loc_18000EC5E
0x18000ec3e  mov     ecx, 10h; Size
0x18000ec43  call    cs:__imp_malloc
0x18000ec49  mov     rdi, rax
0x18000ec4c  test    rax, rax
0x18000ec4f  jz      loc_18000ECE4
0x18000ec55  lea     rax, ??_7CDirectMusicSynthFactory@@6B@; const CDirectMusicSynthFactory::`vftable'
0x18000ec5c  jmp     short loc_18000EC99
0x18000ec5e  mov     rax, [rcx]
0x18000ec61  cmp     rax, qword ptr cs:CLSID_DirectMusicSynthSink.Data1
0x18000ec68  jnz     loc_18000ED00
0x18000ec6e  mov     rax, [rcx+8]
0x18000ec72  cmp     rax, qword ptr cs:CLSID_DirectMusicSynthSink.Data4
0x18000ec79  jnz     loc_18000ED00
0x18000ec7f  mov     ecx, 10h; Size
0x18000ec84  call    cs:__imp_malloc
0x18000ec8a  mov     rdi, rax
0x18000ec8d  test    rax, rax
0x18000ec90  jz      short loc_18000ECE4
0x18000ec92  lea     rax, ??_7CDirectMusicSynthSinkFactory@@6B@; const CDirectMusicSynthSinkFactory::`vftable'
0x18000ec99  mov     [rdi], rax
0x18000ec9c  lea     rax, ?g_cLock@@3JA; long g_cLock
0x18000eca3  mov     dword ptr [rdi+8], 1
0x18000ecaa  lock inc dword ptr [rax]
0x18000ecad  mov     rax, [rdi]
0x18000ecb0  mov     r8, rbx
0x18000ecb3  mov     rdx, rsi
0x18000ecb6  mov     rcx, rdi
0x18000ecb9  mov     rax, [rax]
0x18000ecbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecc1  mov     rdx, [rdi]
0x18000ecc4  mov     ebx, eax
0x18000ecc6  mov     rcx, rdi
0x18000ecc9  mov     rax, [rdx+10h]
0x18000eccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecd2  mov     eax, ebx
0x18000ecd4  mov     rbx, [rsp+28h+arg_0]
0x18000ecd9  mov     rsi, [rsp+28h+arg_8]
0x18000ecde  add     rsp, 20h
0x18000ece2  pop     rdi
0x18000ece3  retn
0x18000ece4  mov     qword ptr [rbx], 0
0x18000eceb  mov     eax, 8007000Eh
0x18000ecf0  mov     rbx, [rsp+28h+arg_0]
0x18000ecf5  mov     rsi, [rsp+28h+arg_8]
0x18000ecfa  add     rsp, 20h
0x18000ecfe  pop     rdi
0x18000ecff  retn
0x18000ed00  mov     rbx, [rsp+28h+arg_0]
0x18000ed05  mov     eax, 80040111h
0x18000ed0a  mov     rsi, [rsp+28h+arg_8]
0x18000ed0f  mov     qword ptr [r8], 0
0x18000ed16  add     rsp, 20h
0x18000ed1a  pop     rdi
0x18000ed1b  retn
```
