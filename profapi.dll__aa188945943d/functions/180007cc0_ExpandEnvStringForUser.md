# ExpandEnvStringForUser

- ea: `0x180007cc0`
- end: `0x180007e2d`
- name: `ExpandEnvStringForUser`
- size: `365`
- prototype: `__int64 __fastcall(char *TokenHandle, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180005b60`
- `0x180006de0`
- `0x180007cc0`
- `0x180007e40`
- `0x1800090f0`

## import_xrefs

- `ntdll!RtlDestroyEnvironment` at `0x180007d76`
- `ntdll!RtlDestroyEnvironment` at `0x180007da7`
- `ntdll!RtlDestroyEnvironment` at `0x180007dd2`
- `ntdll!RtlDestroyEnvironment` at `0x180007e18`
- `ntdll!RtlDestroyEnvironment` at `0x180007d76`
- `ntdll!RtlDestroyEnvironment` at `0x180007da7`
- `ntdll!RtlDestroyEnvironment` at `0x180007dd2`
- `ntdll!RtlDestroyEnvironment` at `0x180007e18`
- `ntdll!RtlCreateEnvironment` at `0x180007ce8`
- `ntdll!RtlCreateEnvironment` at `0x180007ce8`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180007d54`
- `ntdll!RtlExpandEnvironmentStrings` at `0x180007d54`
- `ntdll!RtlNtStatusToDosError` at `0x180007cf0`
- `ntdll!RtlNtStatusToDosError` at `0x180007d5c`
- `ntdll!RtlNtStatusToDosError` at `0x180007cf0`
- `ntdll!RtlNtStatusToDosError` at `0x180007d5c`

## pseudocode

```c
__int64 __fastcall ExpandEnvStringForUser(char *TokenHandle, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v5; // rbp
  NTSTATUS v8; // eax
  signed int v9; // eax
  signed int v10; // edi
  __int64 v11; // r8
  NTSTATUS v12; // eax
  signed int v13; // eax
  signed int v14; // ebx
  int v16; // [rsp+20h] [rbp-58h]
  PWSTR Environment; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v18[8]; // [rsp+38h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v5 = a4;
  Environment = 0;
  v8 = RtlCreateEnvironment(0, &Environment);
  v9 = RtlNtStatusToDosError(v8);
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x279,
      (unsigned int)"minio\\profapi\\env.cpp",
      (const char *)(unsigned int)v10,
      v16);
    goto LABEL_19;
  }
  _SetMachineEnvironment((void **)&Environment);
  if ( (unsigned __int64)(TokenHandle - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v10 = _SetUserEnvironment((void **)&Environment, TokenHandle);
    if ( v10 < 0 )
    {
      RtlDestroyEnvironment(Environment);
      Environment = 0;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x29F,
        (unsigned int)"minio\\profapi\\env.cpp",
        (const char *)(unsigned int)v10,
        v16);
      if ( Environment )
        RtlDestroyEnvironment(Environment);
      return (unsigned int)v10;
    }
  }
  v18[0] = 0;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(a2 + 2 * v11) );
  v12 = RtlExpandEnvironmentStrings(Environment, a2, v11, a3, v5, v18);
  v13 = RtlNtStatusToDosError(v12);
  v14 = v13;
  if ( v13 > 0 )
    v14 = (unsigned __int16)v13 | 0x80070000;
  if ( v14 >= 0 )
  {
    if ( Environment )
      RtlDestroyEnvironment(Environment);
    return 0;
  }
  else
  {
    if ( Environment )
      RtlDestroyEnvironment(Environment);
    return (unsigned int)v14;
  }
}

```

## disassembly

```asm
0x180007cc0  push    rbx
0x180007cc2  push    rbp
0x180007cc3  push    rsi
0x180007cc4  push    rdi
0x180007cc5  push    r14
0x180007cc7  push    r15
0x180007cc9  sub     rsp, 48h
0x180007ccd  mov     rbx, rdx
0x180007cd0  mov     ebp, r9d
0x180007cd3  mov     rsi, rcx
0x180007cd6  lea     rdx, [rsp+78h+Environment]; Environment
0x180007cdb  xor     r15d, r15d
0x180007cde  xor     ecx, ecx; Inherit
0x180007ce0  mov     [rsp+78h+Environment], r15
0x180007ce5  mov     r14, r8
0x180007ce8  call    cs:__imp_RtlCreateEnvironment
0x180007cee  mov     ecx, eax; Status
0x180007cf0  call    cs:__imp_RtlNtStatusToDosError
0x180007cf6  mov     edi, eax
0x180007cf8  test    eax, eax
0x180007cfa  jg      loc_180007DB4
0x180007d00  test    edi, edi
0x180007d02  js      loc_180007DDC
0x180007d08  lea     rcx, [rsp+78h+Environment]; void **
0x180007d0d  call    ?_SetMachineEnvironment@@YAXPEAPEAX@Z; _SetMachineEnvironment(void * *)
0x180007d12  lea     rax, [rsi-1]
0x180007d16  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007d1a  jbe     short loc_180007D8B
0x180007d1c  mov     [rsp+78h+var_40], r15
0x180007d21  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180007d28  nop     dword ptr [rax+rax+00000000h]
0x180007d30  inc     r8
0x180007d33  cmp     [rbx+r8*2], r15w
0x180007d38  jnz     short loc_180007D30
0x180007d3a  lea     rcx, [rsp+78h+var_40]
0x180007d3f  mov     r9, r14
0x180007d42  mov     [rsp+78h+var_50], rcx
0x180007d47  mov     rdx, rbx
0x180007d4a  mov     rcx, [rsp+78h+Environment]
0x180007d4f  mov     [rsp+78h+var_58], rbp
0x180007d54  call    cs:__imp_RtlExpandEnvironmentStrings
0x180007d5a  mov     ecx, eax; Status
0x180007d5c  call    cs:__imp_RtlNtStatusToDosError
0x180007d62  mov     ebx, eax
0x180007d64  test    eax, eax
0x180007d66  jg      short loc_180007DC2
0x180007d68  mov     rcx, [rsp+78h+Environment]; Environment
0x180007d6d  test    ebx, ebx
0x180007d6f  jns     short loc_180007DCD
0x180007d71  test    rcx, rcx
0x180007d74  jz      short loc_180007D7C
0x180007d76  call    cs:__imp_RtlDestroyEnvironment
0x180007d7c  mov     eax, ebx
0x180007d7e  add     rsp, 48h
0x180007d82  pop     r15
0x180007d84  pop     r14
0x180007d86  pop     rdi
0x180007d87  pop     rsi
0x180007d88  pop     rbp
0x180007d89  pop     rbx
0x180007d8a  retn
0x180007d8b  mov     rdx, rsi; TokenHandle
0x180007d8e  lea     rcx, [rsp+78h+Environment]; void **
0x180007d93  call    ?_SetUserEnvironment@@YAJPEAPEAXPEAX@Z; _SetUserEnvironment(void * *,void *)
0x180007d98  mov     edi, eax
0x180007d9a  test    eax, eax
0x180007d9c  jns     loc_180007D1C
0x180007da2  mov     rcx, [rsp+78h+Environment]; Environment
0x180007da7  call    cs:__imp_RtlDestroyEnvironment
0x180007dad  mov     [rsp+78h+Environment], r15
0x180007db2  jmp     short loc_180007DF5
0x180007db4  movzx   edi, ax
0x180007db7  or      edi, 80070000h
0x180007dbd  jmp     loc_180007D00
0x180007dc2  movzx   ebx, ax
0x180007dc5  or      ebx, 80070000h
0x180007dcb  jmp     short loc_180007D68
0x180007dcd  test    rcx, rcx
0x180007dd0  jz      short loc_180007DD8
0x180007dd2  call    cs:__imp_RtlDestroyEnvironment
0x180007dd8  xor     eax, eax
0x180007dda  jmp     short loc_180007D7E
0x180007ddc  mov     rcx, [rsp+78h]; this
0x180007de1  lea     r8, aMinioProfapiEn; "minio\\profapi\\env.cpp"
0x180007de8  mov     r9d, edi; char *
0x180007deb  mov     edx, 279h; void *
0x180007df0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007df5  mov     rcx, [rsp+78h]; this
0x180007dfa  lea     r8, aMinioProfapiEn; "minio\\profapi\\env.cpp"
0x180007e01  mov     r9d, edi; char *
0x180007e04  mov     edx, 29Fh; void *
0x180007e09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007e0e  mov     rcx, [rsp+78h+Environment]; Environment
0x180007e13  test    rcx, rcx
0x180007e16  jz      short loc_180007E1E
0x180007e18  call    cs:__imp_RtlDestroyEnvironment
0x180007e1e  mov     eax, edi
0x180007e20  add     rsp, 48h
0x180007e24  pop     r15
0x180007e26  pop     r14
0x180007e28  pop     rdi
0x180007e29  pop     rsi
0x180007e2a  pop     rbp
0x180007e2b  pop     rbx
0x180007e2c  retn
```
