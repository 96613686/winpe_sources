# CShareEventContext::SetStringProperty(ushort *,ushort *)

- ea: `0x18000d880`
- end: `0x18000d8f9`
- name: `?SetStringProperty@CShareEventContext@@UEAAXPEAG0@Z`
- size: `121`
- prototype: `void(CShareEventContext *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000bf48`
- `0x18000bfb8`
- `0x18000d880`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000d8ab`
- `msvcrt!_wcsicmp` at `0x18000d8d0`
- `msvcrt!_wcsicmp` at `0x18000d8ab`
- `msvcrt!_wcsicmp` at `0x18000d8d0`

## string_xrefs

- `0x18000d8a1`: `SharePath`

## pseudocode

```c
void __fastcall CShareEventContext::SetStringProperty(
        CShareEventContext *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  if ( *((_DWORD *)this + 76) != -1 )
  {
    if ( _wcsicmp(a2, L"SharePath") )
    {
      if ( !_wcsicmp(a2, L"Alias") )
        MSFT_NfsMappedIdentity_Set_AccountName((char *)this + 128, a3);
    }
    else
    {
      MSFT_NfsShare_Set_Path((char *)this + 128, a3);
    }
  }
}

```

## disassembly

```asm
0x18000d880  mov     [rsp+arg_0], rbx
0x18000d885  mov     [rsp+arg_8], rsi
0x18000d88a  push    rdi
0x18000d88b  sub     rsp, 20h
0x18000d88f  cmp     dword ptr [rcx+130h], 0FFFFFFFFh
0x18000d896  mov     rdi, r8
0x18000d899  mov     rsi, rdx
0x18000d89c  mov     rbx, rcx
0x18000d89f  jz      short loc_18000D8E9
0x18000d8a1  lea     rdx, aSharepath; "SharePath"
0x18000d8a8  mov     rcx, rsi; String1
0x18000d8ab  call    cs:__imp__wcsicmp
0x18000d8b1  test    eax, eax
0x18000d8b3  jnz     short loc_18000D8C6
0x18000d8b5  lea     rcx, [rbx+80h]
0x18000d8bc  mov     rdx, rdi
0x18000d8bf  call    MSFT_NfsShare_Set_Path
0x18000d8c4  jmp     short loc_18000D8E9
0x18000d8c6  lea     rdx, aAlias; "Alias"
0x18000d8cd  mov     rcx, rsi; String1
0x18000d8d0  call    cs:__imp__wcsicmp
0x18000d8d6  test    eax, eax
0x18000d8d8  jnz     short loc_18000D8E9
0x18000d8da  lea     rcx, [rbx+80h]
0x18000d8e1  mov     rdx, rdi
0x18000d8e4  call    MSFT_NfsMappedIdentity_Set_AccountName
0x18000d8e9  mov     rbx, [rsp+28h+arg_0]
0x18000d8ee  mov     rsi, [rsp+28h+arg_8]
0x18000d8f3  add     rsp, 20h
0x18000d8f7  pop     rdi
0x18000d8f8  retn
```
