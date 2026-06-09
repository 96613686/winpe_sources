# Helper::IsProcessElevated(void)

- ea: `0x18001478c`
- end: `0x18001485f`
- name: `?IsProcessElevated@Helper@@YAHXZ`
- size: `211`
- prototype: `_BOOL8 __fastcall(Helper *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000f654`

## callees

- `0x18001478c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800147be`
- `KERNEL32!GetLastError` at `0x180014806`
- `KERNEL32!GetLastError` at `0x1800147be`
- `KERNEL32!GetLastError` at `0x180014806`
- `KERNEL32!CloseHandle` at `0x18001483d`
- `KERNEL32!CloseHandle` at `0x18001483d`
- `KERNEL32!GetCurrentProcess` at `0x1800147a3`
- `KERNEL32!GetCurrentProcess` at `0x1800147a3`
- `ADVAPI32!GetTokenInformation` at `0x1800147fc`
- `ADVAPI32!GetTokenInformation` at `0x1800147fc`
- `ADVAPI32!OpenProcessToken` at `0x1800147b4`
- `ADVAPI32!OpenProcessToken` at `0x1800147b4`

## pseudocode

```c
_BOOL8 __fastcall Helper::IsProcessElevated(Helper *this)
{
  signed int v1; // ebx
  int v2; // edi
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v5; // eax
  int TokenInformation; // [rsp+40h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  v1 = 0;
  v2 = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    goto LABEL_6;
  LastError = GetLastError();
  v1 = LastError;
  if ( !LastError )
  {
    v1 = -2147467259;
    goto LABEL_14;
  }
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( v1 >= 0 )
  {
LABEL_6:
    ReturnLength = 4;
    if ( GetTokenInformation(TokenHandle, TokenElevation, &TokenInformation, 4u, &ReturnLength) )
      goto LABEL_13;
    v5 = GetLastError();
    v1 = v5;
    if ( v5 )
    {
      if ( v5 > 0 )
        v1 = (unsigned __int16)v5 | 0x80070000;
    }
    else
    {
      v1 = -2147467259;
    }
    if ( v1 >= 0 )
LABEL_13:
      v2 = TokenInformation;
  }
LABEL_14:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v1 >= 0 && v2;
}

```

## disassembly

```asm
0x18001478c  mov     [rsp+arg_18], rbx
0x180014791  push    rdi
0x180014792  sub     rsp, 30h
0x180014796  xor     ebx, ebx
0x180014798  xor     edi, edi
0x18001479a  mov     [rsp+38h+TokenHandle], rbx
0x18001479f  mov     [rsp+38h+TokenInformation], ebx
0x1800147a3  call    cs:__imp_GetCurrentProcess
0x1800147a9  mov     rcx, rax; ProcessHandle
0x1800147ac  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800147b1  lea     edx, [rbx+8]; DesiredAccess
0x1800147b4  call    cs:__imp_OpenProcessToken
0x1800147ba  test    eax, eax
0x1800147bc  jnz     short loc_1800147D9
0x1800147be  call    cs:__imp_GetLastError
0x1800147c4  mov     ebx, eax
0x1800147c6  test    eax, eax
0x1800147c8  jz      short loc_18001481F
0x1800147ca  jle     short loc_1800147D5
0x1800147cc  movzx   ebx, ax
0x1800147cf  or      ebx, 80070000h
0x1800147d5  test    ebx, ebx
0x1800147d7  js      short loc_180014833
0x1800147d9  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1800147de  lea     rax, [rsp+38h+arg_8]
0x1800147e3  mov     r9d, 4; TokenInformationLength
0x1800147e9  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800147ee  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800147f3  mov     [rsp+38h+arg_8], r9d
0x1800147f8  lea     edx, [r9+10h]; TokenInformationClass
0x1800147fc  call    cs:__imp_GetTokenInformation
0x180014802  test    eax, eax
0x180014804  jnz     short loc_18001482F
0x180014806  call    cs:__imp_GetLastError
0x18001480c  mov     ebx, eax
0x18001480e  test    eax, eax
0x180014810  jz      short loc_180014826
0x180014812  jle     short loc_18001482B
0x180014814  movzx   ebx, ax
0x180014817  or      ebx, 80070000h
0x18001481d  jmp     short loc_18001482B
0x18001481f  mov     ebx, 80004005h
0x180014824  jmp     short loc_180014833
0x180014826  mov     ebx, 80004005h
0x18001482b  test    ebx, ebx
0x18001482d  js      short loc_180014833
0x18001482f  mov     edi, [rsp+38h+TokenInformation]
0x180014833  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180014838  test    rcx, rcx
0x18001483b  jz      short loc_180014843
0x18001483d  call    cs:__imp_CloseHandle
0x180014843  test    ebx, ebx
0x180014845  js      short loc_180014852
0x180014847  test    edi, edi
0x180014849  jz      short loc_180014852
0x18001484b  mov     eax, 1
0x180014850  jmp     short loc_180014854
0x180014852  xor     eax, eax
0x180014854  mov     rbx, [rsp+38h+arg_18]
0x180014859  add     rsp, 30h
0x18001485d  pop     rdi
0x18001485e  retn
```
