# CWMIContext::GetResourceModule(void)

- ea: `0x18000b4ec`
- end: `0x18000b61a`
- name: `?GetResourceModule@CWMIContext@@QEAAPEAUHINSTANCE__@@XZ`
- size: `302`
- prototype: `HINSTANCE __fastcall(CWMIContext *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b328`

## callees

- `0x18000b4ec`
- `0x180035b02`
- `0x180035b40`

## import_xrefs

- `msvcrt!swprintf_s` at `0x18000b5be`
- `msvcrt!swprintf_s` at `0x18000b5be`
- `KERNEL32!GetLastError` at `0x18000b5dd`
- `KERNEL32!GetLastError` at `0x18000b5dd`
- `KERNEL32!GetEnvironmentVariableW` at `0x18000b545`
- `KERNEL32!GetEnvironmentVariableW` at `0x18000b545`
- `KERNEL32!LoadLibraryW` at `0x18000b5cf`
- `KERNEL32!LoadLibraryW` at `0x18000b5cf`

## string_xrefs

- `0x18000b5a1`: `nfscimprov.dll`
- `0x18000b5ab`: `system32`

## pseudocode

```c
HINSTANCE __fastcall CWMIContext::GetResourceModule(CWMIContext *this)
{
  HMODULE LibraryW; // rsi
  DWORD EnvironmentVariableW; // eax
  __int64 v4; // rdx
  DWORD LastError; // ebx
  WCHAR Buffer[784]; // [rsp+30h] [rbp-638h] BYREF

  if ( *((_BYTE *)this + 16) )
    return (HINSTANCE)*((_QWORD *)this + 1);
  LibraryW = 0;
  memset_0(Buffer, 0, 0x61Au);
  EnvironmentVariableW = GetEnvironmentVariableW(L"SystemRoot", Buffer, 0x30Cu);
  v4 = EnvironmentVariableW;
  if ( !EnvironmentVariableW )
  {
    LastError = 203;
    goto LABEL_13;
  }
  if ( EnvironmentVariableW > 0x30D )
    goto LABEL_5;
  if ( EnvironmentVariableW != 781 )
  {
    if ( Buffer[EnvironmentVariableW - 1] == 92
      || (Buffer[EnvironmentVariableW] = 92, v4 = EnvironmentVariableW + 1, (unsigned int)v4 <= 0x30C) )
    {
      if ( swprintf_s(&Buffer[v4], 781LL - (unsigned int)v4, L"%s\\%s", L"system32", L"nfscimprov.dll") >= 0 )
      {
        LastError = 0;
        LibraryW = LoadLibraryW(Buffer);
        if ( !LibraryW )
          LastError = GetLastError();
        goto LABEL_13;
      }
    }
LABEL_5:
    LastError = 122;
    goto LABEL_13;
  }
  LastError = 13;
LABEL_13:
  *((_QWORD *)this + 1) = LibraryW;
  if ( !LastError )
    *((_BYTE *)this + 16) = 1;
  return (HINSTANCE)*((_QWORD *)this + 1);
}

```

## disassembly

```asm
0x18000b4ec  mov     [rsp+arg_8], rbx
0x18000b4f1  mov     [rsp+arg_10], rsi
0x18000b4f6  push    rdi
0x18000b4f7  sub     rsp, 660h
0x18000b4fe  mov     rax, cs:__security_cookie
0x18000b505  xor     rax, rsp
0x18000b508  mov     [rsp+668h+var_18], rax
0x18000b510  cmp     byte ptr [rcx+10h], 0
0x18000b514  mov     rdi, rcx
0x18000b517  jnz     loc_18000B5F1
0x18000b51d  xor     edx, edx; Val
0x18000b51f  lea     rcx, [rsp+668h+Buffer]; void *
0x18000b524  mov     r8d, 61Ah; Size
0x18000b52a  xor     esi, esi
0x18000b52c  call    memset_0
0x18000b531  mov     ebx, 30Ch
0x18000b536  lea     rdx, [rsp+668h+Buffer]; lpBuffer
0x18000b53b  mov     r8d, ebx; nSize
0x18000b53e  lea     rcx, Name; "SystemRoot"
0x18000b545  call    cs:__imp_GetEnvironmentVariableW
0x18000b54b  mov     edx, eax
0x18000b54d  test    eax, eax
0x18000b54f  jnz     short loc_18000B55B
0x18000b551  mov     ebx, 0CBh
0x18000b556  jmp     loc_18000B5E5
0x18000b55b  mov     r10d, 30Dh
0x18000b561  cmp     edx, r10d
0x18000b564  jbe     short loc_18000B56D
0x18000b566  mov     ebx, 7Ah ; 'z'
0x18000b56b  jmp     short loc_18000B5E5
0x18000b56d  jnz     short loc_18000B576
0x18000b56f  mov     ebx, 0Dh
0x18000b574  jmp     short loc_18000B5E5
0x18000b576  lea     eax, [rdx-1]
0x18000b579  mov     r8d, 5Ch ; '\'
0x18000b57f  cmp     [rsp+rax*2+668h+Buffer], r8w
0x18000b585  jz      short loc_18000B593
0x18000b587  mov     [rsp+rdx*2+668h+Buffer], r8w
0x18000b58d  inc     edx
0x18000b58f  cmp     edx, ebx
0x18000b591  ja      short loc_18000B566
0x18000b593  mov     eax, edx
0x18000b595  lea     rcx, [rsp+668h+Buffer]
0x18000b59a  sub     r10, rax
0x18000b59d  lea     rcx, [rcx+rdx*2]; Buffer
0x18000b5a1  lea     rax, aNfscimprovDll_0; "nfscimprov.dll"
0x18000b5a8  mov     rdx, r10; BufferCount
0x18000b5ab  lea     r9, aSystem32; "system32"
0x18000b5b2  mov     [rsp+668h+var_648], rax
0x18000b5b7  lea     r8, aSS; "%s\\%s"
0x18000b5be  call    cs:__imp_swprintf_s
0x18000b5c4  test    eax, eax
0x18000b5c6  js      short loc_18000B566
0x18000b5c8  lea     rcx, [rsp+668h+Buffer]; lpLibFileName
0x18000b5cd  xor     ebx, ebx
0x18000b5cf  call    cs:__imp_LoadLibraryW
0x18000b5d5  mov     rsi, rax
0x18000b5d8  test    rax, rax
0x18000b5db  jnz     short loc_18000B5E5
0x18000b5dd  call    cs:__imp_GetLastError
0x18000b5e3  mov     ebx, eax
0x18000b5e5  mov     [rdi+8], rsi
0x18000b5e9  test    ebx, ebx
0x18000b5eb  jnz     short loc_18000B5F1
0x18000b5ed  mov     byte ptr [rdi+10h], 1
0x18000b5f1  mov     rax, [rdi+8]
0x18000b5f5  mov     rcx, [rsp+668h+var_18]
0x18000b5fd  xor     rcx, rsp; StackCookie
0x18000b600  call    __security_check_cookie
0x18000b605  lea     r11, [rsp+668h+var_8]
0x18000b60d  mov     rbx, [r11+18h]
0x18000b611  mov     rsi, [r11+20h]
0x18000b615  mov     rsp, r11
0x18000b618  pop     rdi
0x18000b619  retn
```
