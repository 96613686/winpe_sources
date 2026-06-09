# ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong)

- ea: `0x180010044`
- end: `0x180010095`
- name: `?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WK@Z`
- size: `81`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, HKEY hKey, LPCWSTR lpSubKey, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010328`
- `0x18001075c`

## callees

- `0x18000fc14`
- `0x180010044`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001006f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001006f`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::Open(ATL::CRegKey *this, HKEY hKey, LPCWSTR lpSubKey, REGSAM a4)
{
  unsigned int v5; // edx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF

  phkResult = 0;
  v5 = RegOpenKeyExW(hKey, lpSubKey, 0, a4, &phkResult);
  if ( !v5 )
  {
    v5 = ATL::CRegKey::Close(this);
    *(_QWORD *)this = phkResult;
  }
  return v5;
}

```

## disassembly

```asm
0x180010044  push    rbx
0x180010046  sub     rsp, 40h
0x18001004a  mov     rbx, rcx
0x18001004d  mov     [rsp+48h+var_18], 0
0x180010056  mov     rax, r8
0x180010059  lea     rcx, [rsp+48h+var_18]
0x18001005e  mov     r10, rdx
0x180010061  mov     [rsp+48h+phkResult], rcx; phkResult
0x180010066  mov     rcx, r10; hKey
0x180010069  xor     r8d, r8d; ulOptions
0x18001006c  mov     rdx, rax; lpSubKey
0x18001006f  call    cs:__imp_RegOpenKeyExW
0x180010075  mov     edx, eax
0x180010077  test    eax, eax
0x180010079  jnz     short loc_18001008D
0x18001007b  mov     rcx, rbx; this
0x18001007e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180010083  mov     edx, eax
0x180010085  mov     rax, [rsp+48h+var_18]
0x18001008a  mov     [rbx], rax
0x18001008d  mov     eax, edx
0x18001008f  add     rsp, 40h
0x180010093  pop     rbx
0x180010094  retn
```
