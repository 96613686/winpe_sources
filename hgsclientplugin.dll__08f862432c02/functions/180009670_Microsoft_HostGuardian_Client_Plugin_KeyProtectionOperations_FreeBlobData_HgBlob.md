# Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::FreeBlobData(HgBlob &)

- ea: `0x180009670`
- end: `0x1800096bb`
- name: `?FreeBlobData@KeyProtectionOperations@Plugin@Client@HostGuardian@Microsoft@@YAXAEAUHgBlob@@@Z`
- size: `75`
- prototype: `void __fastcall(Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations *__hidden this, struct HgBlob *)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800079f0`
- `0x1800092fc`
- `0x1800096ec`

## callees

- `0x180009670`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000969e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000969e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000968b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000968b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009696`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009696`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations::FreeBlobData(
        Microsoft::HostGuardian::Client::Plugin::KeyProtectionOperations *this,
        struct HgBlob *a2)
{
  void *v2; // rsi
  DWORD LastError; // ebx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    LastError = GetLastError();
    CoTaskMemFree(v2);
    SetLastError(LastError);
  }
  *(_OWORD *)this = 0;
}

```

## disassembly

```asm
0x180009670  mov     [rsp+arg_0], rbx
0x180009675  mov     [rsp+arg_8], rsi
0x18000967a  push    rdi
0x18000967b  sub     rsp, 20h
0x18000967f  mov     rsi, [rcx+8]
0x180009683  mov     rdi, rcx
0x180009686  test    rsi, rsi
0x180009689  jz      short loc_1800096A4
0x18000968b  call    cs:__imp_GetLastError
0x180009691  mov     rcx, rsi; pv
0x180009694  mov     ebx, eax
0x180009696  call    cs:__imp_CoTaskMemFree
0x18000969c  mov     ecx, ebx; dwErrCode
0x18000969e  call    cs:__imp_SetLastError
0x1800096a4  mov     rbx, [rsp+28h+arg_0]
0x1800096a9  xorps   xmm0, xmm0
0x1800096ac  mov     rsi, [rsp+28h+arg_8]
0x1800096b1  movdqu  xmmword ptr [rdi], xmm0
0x1800096b5  add     rsp, 20h
0x1800096b9  pop     rdi
0x1800096ba  retn
```
