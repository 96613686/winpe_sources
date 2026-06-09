# ListViewCompare

- ea: `0x180010f40`
- end: `0x18001101c`
- name: `ListViewCompare`
- size: `220`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180010978`
- `0x180010f40`
- `0x180014aae`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180010fe1`
- `msvcrt!_wcsicmp` at `0x180010fe1`

## pseudocode

```c
int __fastcall ListViewCompare(__int64 a1, __int64 a2)
{
  int FileFromParam; // ebx
  int v5; // eax
  int result; // eax
  wchar_t String2; // [rsp+20h] [rbp-438h] BYREF
  _BYTE v8[526]; // [rsp+22h] [rbp-436h] BYREF
  wchar_t String1; // [rsp+230h] [rbp-228h] BYREF
  _BYTE v10[526]; // [rsp+232h] [rbp-226h] BYREF

  String1 = 0;
  memset_0(v10, 0, 0x208u);
  String2 = 0;
  memset_0(v8, 0, 0x208u);
  FileFromParam = GetFileFromParam(a1, &String1, 261);
  v5 = GetFileFromParam(a2, &String2, 261);
  if ( !FileFromParam || !v5 )
    return 0;
  if ( FileFromParam == v5 )
    return _wcsicmp(&String1, &String2);
  result = 1;
  if ( FileFromParam != 2 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x180010f40  mov     [rsp+arg_10], rbx
0x180010f45  push    rdi
0x180010f46  sub     rsp, 450h
0x180010f4d  mov     rax, cs:__security_cookie
0x180010f54  xor     rax, rsp
0x180010f57  mov     [rsp+458h+var_18], rax
0x180010f5f  mov     rdi, rdx
0x180010f62  mov     rbx, rcx
0x180010f65  xor     eax, eax
0x180010f67  lea     rcx, [rsp+458h+var_226]; void *
0x180010f6f  xor     edx, edx; Val
0x180010f71  mov     [rsp+458h+String1], ax
0x180010f79  mov     r8d, 208h; Size
0x180010f7f  call    memset_0
0x180010f84  xor     eax, eax
0x180010f86  lea     rcx, [rsp+458h+var_436]; void *
0x180010f8b  xor     edx, edx; Val
0x180010f8d  mov     [rsp+458h+String2], ax
0x180010f92  mov     r8d, 208h; Size
0x180010f98  call    memset_0
0x180010f9d  mov     r8d, 105h
0x180010fa3  lea     rdx, [rsp+458h+String1]
0x180010fab  mov     rcx, rbx
0x180010fae  call    GetFileFromParam
0x180010fb3  mov     r8d, 105h
0x180010fb9  lea     rdx, [rsp+458h+String2]
0x180010fbe  mov     rcx, rdi
0x180010fc1  mov     ebx, eax
0x180010fc3  call    GetFileFromParam
0x180010fc8  test    ebx, ebx
0x180010fca  jz      short loc_180010FF9
0x180010fcc  test    eax, eax
0x180010fce  jz      short loc_180010FF9
0x180010fd0  cmp     ebx, eax
0x180010fd2  jnz     short loc_180010FE9
0x180010fd4  lea     rdx, [rsp+458h+String2]; String2
0x180010fd9  lea     rcx, [rsp+458h+String1]; String1
0x180010fe1  call    cs:__imp__wcsicmp
0x180010fe7  jmp     short loc_180010FFB
0x180010fe9  or      ecx, 0FFFFFFFFh
0x180010fec  mov     eax, 1
0x180010ff1  cmp     ebx, 2
0x180010ff4  cmovnz  eax, ecx
0x180010ff7  jmp     short loc_180010FFB
0x180010ff9  xor     eax, eax
0x180010ffb  mov     rcx, [rsp+458h+var_18]
0x180011003  xor     rcx, rsp; StackCookie
0x180011006  call    __security_check_cookie
0x18001100b  mov     rbx, [rsp+458h+arg_10]
0x180011013  add     rsp, 450h
0x18001101a  pop     rdi
0x18001101b  retn
```
