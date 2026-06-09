# CFileStream::Create(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x18000f100`
- end: `0x18000f1b3`
- name: `?Create@CFileStream@@UEAAJPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `179`
- prototype: `__int64 __fastcall(CFileStream *this, const wchar_t *, DWORD, DWORD, struct _SECURITY_ATTRIBUTES *lpSecurityAttributes, DWORD dwCreationDisposition, DWORD dwFlagsAndAttributes, HANDLE hTemplateFile)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180004e60`
- `0x180006430`
- `0x18000f100`
- `0x18000f1bc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f15c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f15c`

## string_xrefs

- `0x18000f182`: `onecoreuap\base\appmodel\search\common\pkmutill\filestream.cxx`

## pseudocode

```c
__int64 __fastcall CFileStream::Create(
        CFileStream *this,
        const wchar_t *a2,
        DWORD a3,
        DWORD a4,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes,
        HANDLE hTemplateFile)
{
  HANDLE FileW; // rax
  const char *v12; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *((_DWORD *)this + 48) = a3;
  if ( !a2 )
    return 2147500035LL;
  FileW = CreateFileW(a2, a3, a4, lpSecurityAttributes, dwCreationDisposition, dwFlagsAndAttributes, hTemplateFile);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 24,
    FileW);
  if ( ((*((_QWORD *)this + 3) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x47,
             (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutill\\filestream.cxx",
             v12);
  CLMString::operator=((char *)this + 32, a2);
  return 0;
}

```

## disassembly

```asm
0x18000f100  mov     [rsp+arg_0], rbx
0x18000f105  mov     [rsp+arg_8], rsi
0x18000f10a  push    rdi
0x18000f10b  sub     rsp, 40h
0x18000f10f  mov     [rcx+0C0h], r8d
0x18000f116  mov     r11d, r9d
0x18000f119  mov     r10d, r8d
0x18000f11c  mov     rdi, rdx
0x18000f11f  mov     rsi, rcx
0x18000f122  test    rdx, rdx
0x18000f125  jnz     short loc_18000F12E
0x18000f127  mov     eax, 80004003h
0x18000f12c  jmp     short loc_18000F1A3
0x18000f12e  mov     rax, [rsp+48h+arg_38]
0x18000f136  mov     r8d, r11d; dwShareMode
0x18000f139  mov     r9, [rsp+48h+lpSecurityAttributes]; lpSecurityAttributes
0x18000f13e  mov     edx, r10d; dwDesiredAccess
0x18000f141  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x18000f146  mov     rcx, rdi; lpFileName
0x18000f149  mov     eax, [rsp+48h+arg_30]
0x18000f150  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x18000f154  mov     eax, [rsp+48h+arg_28]
0x18000f158  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x18000f15c  call    cs:__imp_CreateFileW
0x18000f162  mov     rdx, rax
0x18000f165  lea     rcx, [rsi+18h]
0x18000f169  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000f16e  mov     rax, [rsi+18h]
0x18000f172  inc     rax
0x18000f175  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000f17b  jnz     short loc_18000F195
0x18000f17d  mov     rcx, [rsp+48h]; this
0x18000f182  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\search\\com"...
0x18000f189  mov     edx, 47h ; 'G'; void *
0x18000f18e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f193  jmp     short loc_18000F1A3
0x18000f195  lea     rcx, [rsi+20h]
0x18000f199  mov     rdx, rdi
0x18000f19c  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x18000f1a1  xor     eax, eax
0x18000f1a3  mov     rbx, [rsp+48h+arg_0]
0x18000f1a8  mov     rsi, [rsp+48h+arg_8]
0x18000f1ad  add     rsp, 40h
0x18000f1b1  pop     rdi
0x18000f1b2  retn
```
