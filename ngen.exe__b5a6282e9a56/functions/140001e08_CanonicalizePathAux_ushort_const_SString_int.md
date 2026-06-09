# CanonicalizePathAux(ushort const *,SString &,int)

- ea: `0x140001e08`
- end: `0x140001f26`
- name: `?CanonicalizePathAux@@YAXPEBGAEAVSString@@H@Z`
- size: `286`
- prototype: `void __fastcall(unsigned __int16 *, struct SString *this, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140001f28`
- `0x140002168`

## callees

- `0x1400012c0`
- `0x140001e08`
- `0x14000ad80`
- `0x14000e5e4`
- `0x140013200`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x140001e6e`
- `KERNEL32!GetFileAttributesW` at `0x140001e6e`
- `KERNEL32!GetFullPathNameW` at `0x140001e58`
- `KERNEL32!GetFullPathNameW` at `0x140001e58`

## string_xrefs

- `0x140001ee6`: `Error: The specified file or directory "`

## pseudocode

```c
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
0x140001e08  mov     [rsp-8+arg_10], rbx
0x140001e0d  mov     [rsp-8+arg_18], rsi
0x140001e12  push    rbp
0x140001e13  push    rdi
0x140001e14  push    r14
0x140001e16  lea     rbp, [rsp-370h]
0x140001e1e  sub     rsp, 470h
0x140001e25  mov     rax, cs:__security_cookie
0x140001e2c  xor     rax, rsp
0x140001e2f  mov     [rbp+380h+var_20], rax
0x140001e36  mov     esi, r8d
0x140001e39  mov     rbx, rdx
0x140001e3c  mov     rdi, rcx
0x140001e3f  xor     r14d, r14d
0x140001e42  mov     [rsp+480h+FilePart], r14
0x140001e47  lea     r9, [rsp+480h+FilePart]; lpFilePart
0x140001e4c  lea     r8, [rbp+380h+Buffer]; lpBuffer
0x140001e53  mov     edx, 105h; nBufferLength
0x140001e58  call    cs:__imp_GetFullPathNameW
0x140001e5e  dec     eax
0x140001e60  cmp     eax, 104h
0x140001e65  ja      short loc_140001E82
0x140001e67  lea     rcx, [rbp+380h+Buffer]; lpFileName
0x140001e6e  call    cs:__imp_GetFileAttributesW
0x140001e74  cmp     eax, 0FFFFFFFFh
0x140001e77  jz      short loc_140001E82
0x140001e79  lea     rdx, [rbp+380h+Buffer]
0x140001e80  jmp     short loc_140001E89
0x140001e82  test    esi, esi
0x140001e84  jnz     short loc_140001EB8
0x140001e86  mov     rdx, rdi; unsigned __int16 *
0x140001e89  mov     rcx, rbx; this
0x140001e8c  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x140001e91  mov     rcx, [rbp+380h+var_20]
0x140001e98  xor     rcx, rsp; StackCookie
0x140001e9b  call    __security_check_cookie
0x140001ea0  lea     r11, [rsp+480h+var_10]
0x140001ea8  mov     rbx, [r11+30h]
0x140001eac  mov     rsi, [r11+38h]
0x140001eb0  mov     rsp, r11
0x140001eb3  pop     r14
0x140001eb5  pop     rdi
0x140001eb6  pop     rbp
0x140001eb7  retn
0x140001eb8  mov     qword ptr [rsp+480h+var_450], r14
0x140001ebd  mov     qword ptr [rsp+480h+var_450+4], 200h
0x140001ec6  mov     [rsp+480h+var_440], r14
0x140001ecb  lea     rax, [rsp+480h+var_438]
0x140001ed0  mov     [rsp+480h+var_440], rax
0x140001ed5  mov     [rsp+480h+var_450], 2
0x140001edd  mov     rax, [rsp+480h+var_440]
0x140001ee2  mov     [rax], r14w
0x140001ee6  lea     rdx, aErrorTheSpecif_0; "Error: The specified file or directory "...
0x140001eed  lea     rcx, [rsp+480h+var_450]; this
0x140001ef2  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x140001ef7  nop
0x140001ef8  mov     rdx, rdi; unsigned __int16 *
0x140001efb  lea     rcx, [rsp+480h+var_450]; this
0x140001f00  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x140001f05  lea     rdx, aIsInvalid; "\" is invalid."
0x140001f0c  lea     rcx, [rsp+480h+var_450]; this
0x140001f11  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x140001f16  lea     rdx, [rsp+480h+var_450]; struct SString *
0x140001f1b  mov     ecx, 80070002h; int
0x140001f20  call    ?ThrowHR@@YAXJAEBVSString@@@Z; ThrowHR(long,SString const &)
```
