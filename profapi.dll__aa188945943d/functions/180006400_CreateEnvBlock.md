# CreateEnvBlock

- ea: `0x180006400`
- end: `0x1800064a0`
- name: `CreateEnvBlock`
- size: `160`
- prototype: `__int64 __fastcall(PWSTR *Environment, char *, BOOLEAN)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180006400`
- `0x180006de0`
- `0x180007e40`
- `0x1800090f0`

## import_xrefs

- `ntdll!RtlDestroyEnvironment` at `0x18000646b`
- `ntdll!RtlDestroyEnvironment` at `0x18000646b`
- `ntdll!RtlCreateEnvironment` at `0x18000641b`
- `ntdll!RtlCreateEnvironment` at `0x18000641b`
- `ntdll!RtlNtStatusToDosError` at `0x180006423`
- `ntdll!RtlNtStatusToDosError` at `0x180006423`

## pseudocode

```c
__int64 __fastcall CreateEnvBlock(PWSTR *Environment, char *a2, BOOLEAN a3)
{
  NTSTATUS v5; // eax
  signed int v6; // eax
  signed int v7; // ebx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v5 = RtlCreateEnvironment(a3, Environment);
  v6 = RtlNtStatusToDosError(v5);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x279,
      (unsigned int)"minio\\profapi\\env.cpp",
      (const char *)(unsigned int)v7,
      v9);
  }
  else
  {
    _SetMachineEnvironment((void **)Environment);
    if ( (unsigned __int64)(a2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v7 = _SetUserEnvironment((void **)Environment, a2);
      if ( v7 < 0 )
      {
        RtlDestroyEnvironment(*Environment);
        *Environment = 0;
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180006400  mov     [rsp+arg_0], rbx
0x180006405  mov     [rsp+arg_8], rsi
0x18000640a  push    rdi; int
0x18000640b  sub     rsp, 20h
0x18000640f  mov     rdi, rcx
0x180006412  mov     rsi, rdx
0x180006415  mov     rdx, rdi; Environment
0x180006418  mov     cl, r8b; Inherit
0x18000641b  call    cs:__imp_RtlCreateEnvironment
0x180006421  mov     ecx, eax; Status
0x180006423  call    cs:__imp_RtlNtStatusToDosError
0x180006429  mov     ebx, eax
0x18000642b  test    eax, eax
0x18000642d  jg      short loc_18000647A
0x18000642f  test    ebx, ebx
0x180006431  js      short loc_180006485
0x180006433  mov     rcx, rdi; void **
0x180006436  call    ?_SetMachineEnvironment@@YAXPEAPEAX@Z; _SetMachineEnvironment(void * *)
0x18000643b  lea     rax, [rsi-1]
0x18000643f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006443  jbe     short loc_180006457
0x180006445  mov     rsi, [rsp+28h+arg_8]
0x18000644a  mov     eax, ebx
0x18000644c  mov     rbx, [rsp+28h+arg_0]
0x180006451  add     rsp, 20h
0x180006455  pop     rdi
0x180006456  retn
0x180006457  mov     rdx, rsi; TokenHandle
0x18000645a  mov     rcx, rdi; void **
0x18000645d  call    ?_SetUserEnvironment@@YAJPEAPEAXPEAX@Z; _SetUserEnvironment(void * *,void *)
0x180006462  mov     ebx, eax
0x180006464  test    eax, eax
0x180006466  jns     short loc_180006445
0x180006468  mov     rcx, [rdi]; Environment
0x18000646b  call    cs:__imp_RtlDestroyEnvironment
0x180006471  mov     qword ptr [rdi], 0
0x180006478  jmp     short loc_180006445
0x18000647a  movzx   ebx, ax
0x18000647d  or      ebx, 80070000h
0x180006483  jmp     short loc_18000642F
0x180006485  mov     rcx, [rsp+28h]; this
0x18000648a  lea     r8, aMinioProfapiEn; "minio\\profapi\\env.cpp"
0x180006491  mov     r9d, ebx; char *
0x180006494  mov     edx, 279h; void *
0x180006499  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000649e  jmp     short loc_180006445
```
