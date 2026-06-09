# Microsoft::HostGuardian::Client::HgRegistryConfiguration::`vector deleting destructor'(uint)

- ea: `0x180008280`
- end: `0x1800082e1`
- name: `??_EHgRegistryConfiguration@Client@HostGuardian@Microsoft@@UEAAPEAXI@Z`
- size: `97`
- prototype: `Microsoft::HostGuardian::Client::HgRegistryConfiguration *__fastcall(Microsoft::HostGuardian::Client::HgRegistryConfiguration *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001bb4`
- `0x180008280`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800082ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800082ac`

## pseudocode

```c
Microsoft::HostGuardian::Client::HgRegistryConfiguration *__fastcall Microsoft::HostGuardian::Client::HgRegistryConfiguration::`vector deleting destructor'(
        Microsoft::HostGuardian::Client::HgRegistryConfiguration *this,
        char a2)
{
  HKEY v4; // rsi
  DWORD LastError; // ebx

  *(_QWORD *)this = &Microsoft::HostGuardian::Client::HgRegistryConfiguration::`vftable';
  v4 = (HKEY)*((_QWORD *)this + 1);
  if ( v4 )
  {
    LastError = GetLastError();
    RegCloseKey(v4);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 1) = 0;
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180008280  push    rbx
0x180008282  push    rbp
0x180008283  push    rsi
0x180008284  push    rdi
0x180008285  sub     rsp, 28h
0x180008289  lea     rax, ??_7HgRegistryConfiguration@Client@HostGuardian@Microsoft@@6B@; const Microsoft::HostGuardian::Client::HgRegistryConfiguration::`vftable'
0x180008290  mov     ebp, edx
0x180008292  mov     [rcx], rax
0x180008295  mov     rdi, rcx
0x180008298  mov     rsi, [rcx+8]
0x18000829c  test    rsi, rsi
0x18000829f  jz      short loc_1800082BA
0x1800082a1  call    cs:__imp_GetLastError
0x1800082a7  mov     rcx, rsi; hKey
0x1800082aa  mov     ebx, eax
0x1800082ac  call    cs:__imp_RegCloseKey
0x1800082b2  mov     ecx, ebx; dwErrCode
0x1800082b4  call    cs:__imp_SetLastError
0x1800082ba  mov     qword ptr [rdi+8], 0
0x1800082c2  test    bpl, 1
0x1800082c6  jz      short loc_1800082D5
0x1800082c8  mov     edx, 10h
0x1800082cd  mov     rcx, rdi; Block
0x1800082d0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800082d5  mov     rax, rdi
0x1800082d8  add     rsp, 28h
0x1800082dc  pop     rdi
0x1800082dd  pop     rsi
0x1800082de  pop     rbp
0x1800082df  pop     rbx
0x1800082e0  retn
```
