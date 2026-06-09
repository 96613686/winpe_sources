# homedir

- ea: `0x18019a9f0`
- end: `0x18019ab09`
- name: `homedir`
- size: `281`
- prototype: `__int64 __fastcall(int, int, int, int, PCSTR)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000aeec`
- `0x18019a460`
- `0x18019a9f0`
- `0x1801a6630`
- `0x1801a8240`
- `0x1801d6350`
- `0x180205010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019aaea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019aaea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019aac5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019aac5`

## string_xrefs

- `0x18019aa48`: `Home directory is %s\n`
- `0x18019aaf3`: `error 0x%x setting home directory to  %s\n`

## pseudocode

```c
void __fastcall homedir(__int64 a1, __int64 a2, __int64 a3, __int64 a4, PCSTR a5)
{
  void (*lpOutputRoutine)(const char *, ...); // rbx
  DWORD LastError; // eax
  void *hp; // [rsp+20h] [rbp-138h] BYREF
  CHAR dir[272]; // [rsp+30h] [rbp-128h] BYREF

  hp = 0;
  if ( !*a5 )
    goto LABEL_13;
  GetCurrentProcessHandle(&hp);
  if ( !hp )
  {
    ExtensionApis.lpOutputRoutine("couldn't get process handle\n");
    return;
  }
  if ( !FindProcessEntry(hp) )
  {
    ExtensionApis.lpOutputRoutine("Couldn't find process 0x%x\n", hp);
    SetLastError(6u);
    return;
  }
  if ( SymSetHomeDirectory(hp, a5) )
  {
LABEL_13:
    if ( SymGetHomeDirectory(0, dir, 0x105u) )
      ExtensionApis.lpOutputRoutine("Home directory is %s\n", dir);
  }
  else
  {
    lpOutputRoutine = ExtensionApis.lpOutputRoutine;
    LastError = GetLastError();
    lpOutputRoutine("error 0x%x setting home directory to  %s\n", LastError, a5);
  }
}

```

## disassembly

```asm
0x18019a9f0  mov     [rsp+arg_0], rbx
0x18019a9f5  push    rdi
0x18019a9f6  sub     rsp, 150h
0x18019a9fd  mov     rax, cs:__security_cookie
0x18019aa04  xor     rax, rsp
0x18019aa07  mov     [rsp+158h+var_18], rax
0x18019aa0f  mov     rdi, [rsp+158h+arg_20]
0x18019aa17  mov     [rsp+158h+hp], 0
0x18019aa20  cmp     byte ptr [rdi], 0
0x18019aa23  jnz     short loc_18019AA75
0x18019aa25  mov     r8d, 105h; size
0x18019aa2b  lea     rdx, [rsp+158h+dir]; dir
0x18019aa30  xor     ecx, ecx; type
0x18019aa32  call    SymGetHomeDirectory
0x18019aa37  test    rax, rax
0x18019aa3a  jz      short loc_18019AA54
0x18019aa3c  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019aa43  lea     rdx, [rsp+158h+dir]
0x18019aa48  lea     rcx, aHomeDirectoryI; "Home directory is %s\n"
0x18019aa4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019aa54  mov     rcx, [rsp+158h+var_18]
0x18019aa5c  xor     rcx, rsp; StackCookie
0x18019aa5f  call    __security_check_cookie
0x18019aa64  mov     rbx, [rsp+158h+arg_0]
0x18019aa6c  add     rsp, 150h
0x18019aa73  pop     rdi
0x18019aa74  retn
0x18019aa75  lea     rcx, [rsp+158h+hp]; hp
0x18019aa7a  call    GetCurrentProcessHandle
0x18019aa7f  mov     rcx, [rsp+158h+hp]; void *
0x18019aa84  test    rcx, rcx
0x18019aa87  jnz     short loc_18019AA9E
0x18019aa89  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019aa90  lea     rcx, aCouldnTGetProc_0; "couldn't get process handle\n"
0x18019aa97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019aa9c  jmp     short loc_18019AA54
0x18019aa9e  call    ?FindProcessEntry@@YAPEAU_PROCESS_ENTRY@@PEAX@Z; FindProcessEntry(void *)
0x18019aaa3  test    rax, rax
0x18019aaa6  jnz     short loc_18019AACD
0x18019aaa8  mov     rdx, [rsp+158h+hp]
0x18019aaad  lea     rcx, aCouldnTFindPro; "Couldn't find process 0x%x\n"
0x18019aab4  mov     rax, cs:ExtensionApis.lpOutputRoutine
0x18019aabb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019aac0  mov     ecx, 6; dwErrCode
0x18019aac5  call    cs:__imp_SetLastError
0x18019aacb  jmp     short loc_18019AA54
0x18019aacd  mov     rcx, [rsp+158h+hp]; hProcess
0x18019aad2  mov     rdx, rdi; dir
0x18019aad5  call    SymSetHomeDirectory
0x18019aada  test    rax, rax
0x18019aadd  jnz     loc_18019AA25
0x18019aae3  mov     rbx, cs:ExtensionApis.lpOutputRoutine
0x18019aaea  call    cs:__imp_GetLastError
0x18019aaf0  mov     r8, rdi
0x18019aaf3  lea     rcx, aError0xXSettin; "error 0x%x setting home directory to  %"...
0x18019aafa  mov     edx, eax
0x18019aafc  mov     rax, rbx
0x18019aaff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019ab04  jmp     loc_18019AA54
```
