# CFileStream::Create(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x180005600`
- end: `0x1800056b3`
- name: `?Create@CFileStream@@UEAAJPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `179`
- prototype: `int(CFileStream *__hidden this, const wchar_t *, unsigned int, unsigned int, struct _SECURITY_ATTRIBUTES *, unsigned int, unsigned int, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180004890`
- `0x180005600`
- `0x1800056bc`
- `0x1800056f4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000565c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000565c`

## string_xrefs

- `0x180005682`: `onecoreuap\base\appmodel\search\common\pkmutill\filestream.cxx`

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
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
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
0x180005600  mov     [rsp+arg_0], rbx
0x180005605  mov     [rsp+arg_8], rsi
0x18000560a  push    rdi
0x18000560b  sub     rsp, 40h
0x18000560f  mov     [rcx+0C0h], r8d
0x180005616  mov     r11d, r9d
0x180005619  mov     r10d, r8d
0x18000561c  mov     rdi, rdx
0x18000561f  mov     rsi, rcx
0x180005622  test    rdx, rdx
0x180005625  jnz     short loc_18000562E
0x180005627  mov     eax, 80004003h
0x18000562c  jmp     short loc_1800056A3
0x18000562e  mov     rax, [rsp+48h+arg_38]
0x180005636  mov     r8d, r11d; dwShareMode
0x180005639  mov     r9, [rsp+48h+lpSecurityAttributes]; lpSecurityAttributes
0x18000563e  mov     edx, r10d; dwDesiredAccess
0x180005641  mov     [rsp+48h+hTemplateFile], rax; hTemplateFile
0x180005646  mov     rcx, rdi; lpFileName
0x180005649  mov     eax, [rsp+48h+arg_30]
0x180005650  mov     [rsp+48h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180005654  mov     eax, [rsp+48h+arg_28]
0x180005658  mov     [rsp+48h+dwCreationDisposition], eax; dwCreationDisposition
0x18000565c  call    cs:__imp_CreateFileW
0x180005662  mov     rdx, rax
0x180005665  lea     rcx, [rsi+18h]
0x180005669  call    ?reset@?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000566e  mov     rax, [rsi+18h]
0x180005672  inc     rax
0x180005675  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000567b  jnz     short loc_180005695
0x18000567d  mov     rcx, [rsp+48h]; this
0x180005682  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\search\\com"...
0x180005689  mov     edx, 47h ; 'G'; void *
0x18000568e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005693  jmp     short loc_1800056A3
0x180005695  lea     rcx, [rsi+20h]
0x180005699  mov     rdx, rdi
0x18000569c  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x1800056a1  xor     eax, eax
0x1800056a3  mov     rbx, [rsp+48h+arg_0]
0x1800056a8  mov     rsi, [rsp+48h+arg_8]
0x1800056ad  add     rsp, 40h
0x1800056b1  pop     rdi
0x1800056b2  retn
```
