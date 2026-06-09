# system

- ea: `0x18001b4c0`
- end: `0x18001b5fd`
- name: `system`
- size: `317`
- prototype: `int __cdecl(const char *Command)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180007f00`
- `0x1800080a0`
- `0x180019810`
- `0x180019b70`
- `0x18001b4c0`
- `0x18001d300`
- `0x18002f05c`
- `0x1800328b0`
- `0x180079760`

## string_xrefs

- `0x18001b4ee`: `COMSPEC`

## pseudocode

```c
int __cdecl system(const char *Command)
{
  int v2; // edi
  char *Buffer; // [rsp+30h] [rbp-30h] BYREF
  char *FileName[2]; // [rsp+38h] [rbp-28h] BYREF
  __int128 v6; // [rsp+48h] [rbp-18h]

  Buffer = 0;
  *(_OWORD *)FileName = 0;
  v6 = 0;
  if ( dupenv_s(&Buffer, 0, "COMSPEC") == 22 )
    invoke_watson(0, 0, 0, 0, 0);
  FileName[0] = Buffer;
  if ( !Command )
  {
    if ( Buffer )
      LOBYTE(Command) = access_s(Buffer, 0) == 0;
    goto LABEL_13;
  }
  v6 = (unsigned __int64)Command;
  FileName[1] = "/c";
  if ( !Buffer )
  {
LABEL_12:
    FileName[0] = "cmd.exe";
    LODWORD(Command) = spawnvpe(0, "cmd.exe", (const char *const *)FileName, 0);
    goto LABEL_13;
  }
  v2 = *errno();
  *errno() = 0;
  LODWORD(Command) = spawnve(0, FileName[0], (const char *const *)FileName, 0);
  if ( (_DWORD)Command != -1 )
  {
    *errno() = v2;
    goto LABEL_13;
  }
  if ( *errno() == 2 || *errno() == 13 )
  {
    *errno() = v2;
    goto LABEL_12;
  }
LABEL_13:
  free(Buffer);
  return (int)Command;
}

```

## disassembly

```asm
0x18001b4c0  mov     [rsp-8+arg_0], rbx
0x18001b4c5  mov     [rsp-8+arg_8], rdi
0x18001b4ca  push    rbp
0x18001b4cb  mov     rbp, rsp
0x18001b4ce  sub     rsp, 60h
0x18001b4d2  mov     rax, cs:__security_cookie
0x18001b4d9  xor     rax, rsp
0x18001b4dc  mov     [rbp+var_8], rax
0x18001b4e0  xorps   xmm0, xmm0
0x18001b4e3  mov     [rbp+Buffer], 0
0x18001b4eb  mov     rbx, rcx
0x18001b4ee  lea     r8, aComspec_0; "COMSPEC"
0x18001b4f5  lea     rcx, [rbp+Buffer]; Buffer
0x18001b4f9  xor     edx, edx; BufferCount
0x18001b4fb  movups  xmmword ptr [rbp+FileName], xmm0
0x18001b4ff  movups  [rbp+var_18], xmm0
0x18001b503  call    _dupenv_s
0x18001b508  cmp     eax, 16h
0x18001b50b  jnz     short loc_18001B525
0x18001b50d  xor     r9d, r9d; LineNo
0x18001b510  mov     [rsp+60h+Reserved], 0; Reserved
0x18001b519  xor     r8d, r8d; FileName
0x18001b51c  xor     edx, edx; FunctionName
0x18001b51e  xor     ecx, ecx; Expression
0x18001b520  call    _invoke_watson
0x18001b525  mov     rax, [rbp+Buffer]
0x18001b529  mov     [rbp+FileName], rax
0x18001b52d  test    rbx, rbx
0x18001b530  jnz     short loc_18001B54F
0x18001b532  test    rax, rax
0x18001b535  jz      loc_18001B5D6
0x18001b53b  xor     edx, edx; AccessMode
0x18001b53d  mov     rcx, rax; FileName
0x18001b540  call    _access_s
0x18001b545  test    eax, eax
0x18001b547  setz    bl
0x18001b54a  jmp     loc_18001B5D6
0x18001b54f  mov     qword ptr [rbp+var_18], rbx
0x18001b553  lea     rcx, aC; "/c"
0x18001b55a  mov     [rbp+FileName+8], rcx
0x18001b55e  mov     qword ptr [rbp+var_18+8], 0
0x18001b566  test    rax, rax
0x18001b569  jz      short loc_18001B5BB
0x18001b56b  call    _errno
0x18001b570  mov     edi, [rax]
0x18001b572  call    _errno
0x18001b577  xor     r9d, r9d; Environment
0x18001b57a  lea     r8, [rbp+FileName]; Arguments
0x18001b57e  xor     ecx, ecx; Mode
0x18001b580  mov     dword ptr [rax], 0
0x18001b586  mov     rdx, [rbp+FileName]; FileName
0x18001b58a  call    _spawnve
0x18001b58f  mov     rbx, rax
0x18001b592  cmp     eax, 0FFFFFFFFh
0x18001b595  jz      short loc_18001B5A0
0x18001b597  call    _errno
0x18001b59c  mov     [rax], edi
0x18001b59e  jmp     short loc_18001B5D6
0x18001b5a0  call    _errno
0x18001b5a5  cmp     dword ptr [rax], 2
0x18001b5a8  jz      short loc_18001B5B4
0x18001b5aa  call    _errno
0x18001b5af  cmp     dword ptr [rax], 0Dh
0x18001b5b2  jnz     short loc_18001B5D6
0x18001b5b4  call    _errno
0x18001b5b9  mov     [rax], edi
0x18001b5bb  lea     rdx, aCmdExe; "cmd.exe"
0x18001b5c2  xor     r9d, r9d; Environment
0x18001b5c5  lea     r8, [rbp+FileName]; Arguments
0x18001b5c9  mov     [rbp+FileName], rdx
0x18001b5cd  xor     ecx, ecx; Mode
0x18001b5cf  call    _spawnvpe
0x18001b5d4  mov     ebx, eax
0x18001b5d6  mov     rcx, [rbp+Buffer]; Block
0x18001b5da  call    free
0x18001b5df  mov     eax, ebx
0x18001b5e1  mov     rcx, [rbp+var_8]
0x18001b5e5  xor     rcx, rsp; StackCookie
0x18001b5e8  call    __security_check_cookie
0x18001b5ed  mov     rbx, [rsp+60h+arg_0]
0x18001b5f2  mov     rdi, [rsp+60h+arg_8]
0x18001b5f7  add     rsp, 60h
0x18001b5fb  pop     rbp
0x18001b5fc  retn
```
