# CanonicalizePathAux(ushort const *,SString &,int)

- ea: `0x18000d84c`
- end: `0x18000d96a`
- name: `?CanonicalizePathAux@@YAXPEBGAEAVSString@@H@Z`
- size: `286`
- prototype: `void __fastcall(unsigned __int16 *, struct SString *this, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000d96c`
- `0x18000dbac`

## callees

- `0x180001e8c`
- `0x18000d84c`
- `0x180030ab8`
- `0x1800350c4`
- `0x18003dc30`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x18000d89c`
- `KERNEL32!GetFullPathNameW` at `0x18000d89c`
- `KERNEL32!GetFileAttributesW` at `0x18000d8b2`
- `KERNEL32!GetFileAttributesW` at `0x18000d8b2`

## string_xrefs

- `0x18000d92a`: `Error: The specified file or directory "`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall CanonicalizePathAux(unsigned __int16 *a1, struct SString *this, int a3)
{
  WCHAR *v6; // rdx
  LPWSTR FilePart; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD v8[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 *v9; // [rsp+40h] [rbp-C0h]
  __int16 v10; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp+150h] BYREF

  FilePart = 0;
  if ( GetFullPathNameW(a1, 0x105u, Buffer, &FilePart) - 1 > 0x104 || GetFileAttributesW(Buffer) == -1 )
  {
    if ( a3 )
    {
      *(_QWORD *)&v8[1] = 512;
      v9 = &v10;
      v8[0] = 2;
      v10 = 0;
      SString::Set((SString *)v8, L"Error: The specified file or directory \"");
      SString::Append((SString *)v8, a1);
      SString::Append((SString *)v8, L"\" is invalid.");
      ThrowHR(-2147024894, (const struct SString *)v8);
    }
    v6 = a1;
  }
  else
  {
    v6 = Buffer;
  }
  SString::Set(this, v6);
}

```

## disassembly

```asm
0x18000d84c  mov     [rsp-8+arg_10], rbx
0x18000d851  mov     [rsp-8+arg_18], rsi
0x18000d856  push    rbp
0x18000d857  push    rdi
0x18000d858  push    r14
0x18000d85a  lea     rbp, [rsp-370h]
0x18000d862  sub     rsp, 470h
0x18000d869  mov     rax, cs:__security_cookie
0x18000d870  xor     rax, rsp
0x18000d873  mov     [rbp+380h+var_20], rax
0x18000d87a  mov     esi, r8d
0x18000d87d  mov     rbx, rdx
0x18000d880  mov     rdi, rcx
0x18000d883  xor     r14d, r14d
0x18000d886  mov     [rsp+480h+FilePart], r14
0x18000d88b  lea     r9, [rsp+480h+FilePart]; lpFilePart
0x18000d890  lea     r8, [rbp+380h+Buffer]; lpBuffer
0x18000d897  mov     edx, 105h; nBufferLength
0x18000d89c  call    cs:__imp_GetFullPathNameW
0x18000d8a2  dec     eax
0x18000d8a4  cmp     eax, 104h
0x18000d8a9  ja      short loc_18000D8C6
0x18000d8ab  lea     rcx, [rbp+380h+Buffer]; lpFileName
0x18000d8b2  call    cs:__imp_GetFileAttributesW
0x18000d8b8  cmp     eax, 0FFFFFFFFh
0x18000d8bb  jz      short loc_18000D8C6
0x18000d8bd  lea     rdx, [rbp+380h+Buffer]
0x18000d8c4  jmp     short loc_18000D8CD
0x18000d8c6  test    esi, esi
0x18000d8c8  jnz     short loc_18000D8FC
0x18000d8ca  mov     rdx, rdi; unsigned __int16 *
0x18000d8cd  mov     rcx, rbx; this
0x18000d8d0  call    ?Set@SString@@QEAAXPEBG@Z
0x18000d8d5  mov     rcx, [rbp+380h+var_20]
0x18000d8dc  xor     rcx, rsp; StackCookie
0x18000d8df  call    __security_check_cookie
0x18000d8e4  lea     r11, [rsp+480h+var_10]
0x18000d8ec  mov     rbx, [r11+30h]
0x18000d8f0  mov     rsi, [r11+38h]
0x18000d8f4  mov     rsp, r11
0x18000d8f7  pop     r14
0x18000d8f9  pop     rdi
0x18000d8fa  pop     rbp
0x18000d8fb  retn
0x18000d8fc  mov     qword ptr [rsp+480h+var_450], r14
0x18000d901  mov     qword ptr [rsp+480h+var_450+4], 200h
0x18000d90a  mov     [rsp+480h+var_440], r14
0x18000d90f  lea     rax, [rsp+480h+var_438]
0x18000d914  mov     [rsp+480h+var_440], rax
0x18000d919  mov     [rsp+480h+var_450], 2
0x18000d921  mov     rax, [rsp+480h+var_440]
0x18000d926  mov     [rax], r14w
0x18000d92a  lea     rdx, aErrorTheSpecif_0
0x18000d931  lea     rcx, [rsp+480h+var_450]; this
0x18000d936  call    ?Set@SString@@QEAAXPEBG@Z
0x18000d93b  nop
0x18000d93c  mov     rdx, rdi; unsigned __int16 *
0x18000d93f  lea     rcx, [rsp+480h+var_450]; this
0x18000d944  call    ?Append@SString@@QEAAXPEBG@Z
0x18000d949  lea     rdx, aIsInvalid
0x18000d950  lea     rcx, [rsp+480h+var_450]; this
0x18000d955  call    ?Append@SString@@QEAAXPEBG@Z
0x18000d95a  lea     rdx, [rsp+480h+var_450]; struct SString *
0x18000d95f  mov     ecx, 80070002h; int
0x18000d964  call    ?ThrowHR@@YAXJAEBVSString@@@Z
```
