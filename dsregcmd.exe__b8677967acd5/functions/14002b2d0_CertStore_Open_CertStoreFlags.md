# CertStore::Open(CertStoreFlags)

- ea: `0x14002b2d0`
- end: `0x14002b345`
- name: `?Open@CertStore@@QEAAXW4CertStoreFlags@@@Z`
- size: `117`
- prototype: `void __fastcall(CertStore *, DWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140029d48`
- `0x14002aa18`

## callees

- `0x14000c7d8`
- `0x1400234dc`
- `0x14002b198`
- `0x14002b2d0`
- `0x14002c3e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b321`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002b321`
- `CRYPT32!CertOpenStore` at `0x14002b2fb`
- `CRYPT32!CertOpenStore` at `0x14002b2fb`

## string_xrefs

- `0x14002b309`: `Connect: Opened local user certificate store successfully.`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
void __fastcall CertStore::Open(CertStore *a1, DWORD a2)
{
  HCERTSTORE v4; // rax
  DWORD LastError; // eax
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-18h] BYREF

  CertStore::Close(a1);
  v4 = CertOpenStore((LPCSTR)0xA, 0, 0, a2, L"MY");
  *(_QWORD *)a1 = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, LastError);
    throw (Win32Exception *)pExceptionObject;
  }
  Log::Verbose(0, L"Connect: Opened local user certificate store successfully.");
}

```

## disassembly

```asm
0x14002b2d0  mov     [rsp+arg_0], rbx
0x14002b2d5  push    rdi
0x14002b2d6  sub     rsp, 40h
0x14002b2da  mov     ebx, edx
0x14002b2dc  mov     rdi, rcx
0x14002b2df  call    ?Close@CertStore@@QEAAXXZ; CertStore::Close(void)
0x14002b2e4  xor     edx, edx; dwEncodingType
0x14002b2e6  lea     rax, aMy; "MY"
0x14002b2ed  mov     r9d, ebx; dwFlags
0x14002b2f0  mov     [rsp+48h+pvPara], rax; pvPara
0x14002b2f5  xor     r8d, r8d; hCryptProv
0x14002b2f8  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x14002b2fb  call    cs:__imp_CertOpenStore
0x14002b301  mov     [rdi], rax
0x14002b304  test    rax, rax
0x14002b307  jz      short loc_14002B321
0x14002b309  lea     rdx, aConnectOpenedL; "Connect: Opened local user certificate "...
0x14002b310  xor     ecx, ecx; struct ILogContext *
0x14002b312  mov     rbx, [rsp+48h+arg_0]
0x14002b317  add     rsp, 40h
0x14002b31b  pop     rdi
0x14002b31c  jmp     ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x14002b321  call    cs:__imp_GetLastError
0x14002b327  mov     edx, eax; unsigned int
0x14002b329  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14002b32e  call    ??0Win32Exception@@QEAA@K@Z; Win32Exception::Win32Exception(ulong)
0x14002b333  lea     rdx, _TI2?AVWin32Exception@@; pThrowInfo
0x14002b33a  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14002b33f  call    _CxxThrowException_0
```
