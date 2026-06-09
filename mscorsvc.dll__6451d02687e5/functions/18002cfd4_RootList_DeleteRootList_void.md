# RootList::DeleteRootList(void)

- ea: `0x18002cfd4`
- end: `0x18002d208`
- name: `?DeleteRootList@RootList@@SAXXZ`
- size: `564`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18001dcb0`
- `0x18001eed0`

## callees

- `0x1800198dc`
- `0x18002cfd4`
- `0x180034fd4`
- `0x1800351e8`
- `0x18003691c`
- `0x18003f280`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18002d1b9`
- `KERNEL32!HeapFree` at `0x18002d1b9`
- `KERNEL32!GetProcessHeap` at `0x18002d1a4`
- `KERNEL32!GetProcessHeap` at `0x18002d1a4`

## string_xrefs

- `0x18002d066`: `NGenService`
- `0x18002d113`: `NGenService\Roots`
- `0x18002d154`: `NGenService\Roots`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void RootList::DeleteRootList(void)
{
  struct IRegWrapper *SimpleRegWrapper; // rdi
  void *v1; // rbx
  BOOL v2; // esi
  __int64 v3; // r8
  __int64 v4; // r8
  HANDLE ProcessHeap; // rax
  void (__fastcall ***v6)(_QWORD, __int64); // [rsp+20h] [rbp-50h] BYREF
  int v7; // [rsp+28h] [rbp-48h]
  __int64 v8; // [rsp+30h] [rbp-40h] BYREF
  int v9; // [rsp+38h] [rbp-38h]
  void (__fastcall ***v10)(_QWORD, __int64); // [rsp+40h] [rbp-30h] BYREF
  int v11; // [rsp+48h] [rbp-28h]
  struct IRegWrapper *v12; // [rsp+50h] [rbp-20h]
  BOOL v13; // [rsp+58h] [rbp-18h]
  LPVOID v14; // [rsp+60h] [rbp-10h]
  BOOL v15; // [rsp+68h] [rbp-8h]
  LPVOID lpMem; // [rsp+A0h] [rbp+30h] BYREF

  SimpleRegWrapper = CreateSimpleRegWrapper(0);
  v12 = SimpleRegWrapper;
  v13 = SimpleRegWrapper != 0;
  lpMem = 0;
  CLRConfig::GetConfigValue(
    (const struct CLRConfig::ConfigStringInfo *)&CLRConfig::EXTERNAL_ZapSet,
    (unsigned __int16 **)&lpMem);
  v1 = lpMem;
  v14 = lpMem;
  v2 = lpMem != 0;
  v15 = v2;
  if ( lpMem )
  {
    v8 = 0;
    v9 = 0;
    v10 = 0;
    v11 = 0;
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, const unsigned __int16 *, __int64 *))(**((_QWORD **)SimpleRegWrapper
                                                                                            + 1)
                                                                                         + 8LL))(
            *((_QWORD *)SimpleRegWrapper + 1),
            L"NGenService",
            &v8) )
      ThrowHR(-2147467259);
    if ( (*(unsigned __int8 (__fastcall **)(__int64, void *, void (__fastcall ****)(_QWORD, __int64)))(*(_QWORD *)v8 + 8LL))(
           v8,
           v1,
           &v10) )
    {
      LOBYTE(v3) = 1;
      (*(void (__fastcall **)(__int64, void *, __int64))(*(_QWORD *)v8 + 24LL))(v8, v1, v3);
    }
    if ( v11 )
    {
      if ( v10 )
        (**v10)(v10, 1);
      v11 = 0;
    }
    if ( v9 )
    {
      if ( v8 )
        (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
      v9 = 0;
    }
  }
  else
  {
    v6 = 0;
    v7 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD, const wchar_t *, void (__fastcall ****)(_QWORD, __int64)))(**((_QWORD **)SimpleRegWrapper + 1) + 8LL))(
           *((_QWORD *)SimpleRegWrapper + 1),
           L"NGenService\\Roots",
           &v6) )
    {
      if ( v7 )
      {
        if ( v6 )
          (**v6)(v6, 1);
        v7 = 0;
      }
      LOBYTE(v4) = 1;
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, const wchar_t *, __int64))(**((_QWORD **)SimpleRegWrapper + 1)
                                                                                + 24LL))(
              *((_QWORD *)SimpleRegWrapper + 1),
              L"NGenService\\Roots",
              v4) )
        ThrowLastError();
    }
    if ( v7 )
    {
      if ( v6 )
        (**v6)(v6, 1);
      v7 = 0;
    }
  }
  if ( v2 )
  {
    if ( v1 )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v1);
    }
    v15 = 0;
  }
  if ( SimpleRegWrapper )
  {
    (**(void (__fastcall ***)(struct IRegWrapper *, __int64))SimpleRegWrapper)(SimpleRegWrapper, 1);
    v13 = 0;
  }
}

```

## disassembly

```asm
0x18002cfd4  mov     [rsp-28h+arg_8], rbx
0x18002cfd9  mov     [rsp-28h+arg_10], rsi
0x18002cfde  push    rbp
0x18002cfdf  push    rdi
0x18002cfe0  push    r12
0x18002cfe2  push    r14
0x18002cfe4  push    r15
0x18002cfe6  mov     rbp, rsp
0x18002cfe9  sub     rsp, 70h
0x18002cfed  xor     r15d, r15d
0x18002cff0  mov     [rbp+var_20], r15
0x18002cff4  mov     [rbp+var_18], r15d
0x18002cff8  xor     ecx, ecx; int
0x18002cffa  call    ?CreateSimpleRegWrapper@@YAPEAVIRegWrapper@@H@Z; CreateSimpleRegWrapper(int)
0x18002cfff  mov     rdi, rax
0x18002d002  mov     [rbp+var_20], rax
0x18002d006  mov     r14d, r15d
0x18002d009  lea     r12d, [r15+1]
0x18002d00d  test    rax, rax
0x18002d010  cmovnz  r14d, r12d
0x18002d014  mov     [rbp+var_18], r14d
0x18002d018  mov     [rbp+lpMem], r15
0x18002d01c  lea     rdx, [rbp+lpMem]; unsigned __int16 **
0x18002d020  lea     rcx, ?EXTERNAL_ZapSet@CLRConfig@@2UConfigStringInfo@1@B; struct CLRConfig::ConfigStringInfo *
0x18002d027  call    ?GetConfigValue@CLRConfig@@SAJAEBUConfigStringInfo@1@PEAPEAG@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &,ushort * *)
0x18002d02c  mov     rbx, [rbp+lpMem]
0x18002d030  mov     [rbp+var_10], rbx
0x18002d034  mov     [rbp+var_8], r15d
0x18002d038  mov     esi, r15d
0x18002d03b  test    rbx, rbx
0x18002d03e  cmovnz  esi, r12d
0x18002d042  mov     [rbp+var_8], esi
0x18002d045  jz      loc_18002D100
0x18002d04b  mov     [rbp+var_40], r15
0x18002d04f  mov     [rbp+var_38], r15d
0x18002d053  mov     [rbp+var_30], r15
0x18002d057  mov     [rbp+var_28], r15d
0x18002d05b  mov     rcx, [rdi+8]
0x18002d05f  mov     rax, [rcx]
0x18002d062  lea     r8, [rbp+var_40]
0x18002d066  lea     rdx, aNgenservice; "NGenService"
0x18002d06d  mov     rax, [rax+8]
0x18002d071  call    cs:__guard_dispatch_icall_fptr
0x18002d077  test    al, al
0x18002d079  jz      loc_18002D1FD
0x18002d07f  mov     rcx, [rbp+var_40]
0x18002d083  mov     rax, [rcx]
0x18002d086  lea     r8, [rbp+var_30]
0x18002d08a  mov     rdx, rbx
0x18002d08d  mov     rax, [rax+8]
0x18002d091  call    cs:__guard_dispatch_icall_fptr
0x18002d097  test    al, al
0x18002d099  jz      short loc_18002D0B3
0x18002d09b  mov     rcx, [rbp+var_40]
0x18002d09f  mov     rax, [rcx]
0x18002d0a2  mov     r8b, r12b
0x18002d0a5  mov     rdx, rbx
0x18002d0a8  mov     rax, [rax+18h]
0x18002d0ac  call    cs:__guard_dispatch_icall_fptr
0x18002d0b2  nop
0x18002d0b3  cmp     [rbp+var_28], r15d
0x18002d0b7  jz      short loc_18002D0D5
0x18002d0b9  mov     rcx, [rbp+var_30]
0x18002d0bd  test    rcx, rcx
0x18002d0c0  jz      short loc_18002D0D1
0x18002d0c2  mov     rax, [rcx]
0x18002d0c5  mov     edx, r12d
0x18002d0c8  mov     rax, [rax]
0x18002d0cb  call    cs:__guard_dispatch_icall_fptr
0x18002d0d1  mov     [rbp+var_28], r15d
0x18002d0d5  cmp     [rbp+var_38], r15d
0x18002d0d9  jz      loc_18002D18F
0x18002d0df  mov     rcx, [rbp+var_40]
0x18002d0e3  test    rcx, rcx
0x18002d0e6  jz      short loc_18002D0F7
0x18002d0e8  mov     rax, [rcx]
0x18002d0eb  mov     edx, r12d
0x18002d0ee  mov     rax, [rax]
0x18002d0f1  call    cs:__guard_dispatch_icall_fptr
0x18002d0f7  mov     [rbp+var_38], r15d
0x18002d0fb  jmp     loc_18002D18F
0x18002d100  mov     [rbp+var_50], r15
0x18002d104  mov     [rbp+var_48], r15d
0x18002d108  mov     rcx, [rdi+8]
0x18002d10c  mov     rax, [rcx]
0x18002d10f  lea     r8, [rbp+var_50]
0x18002d113  lea     rdx, aNgenserviceRoo; "NGenService\\Roots"
0x18002d11a  mov     rax, [rax+8]
0x18002d11e  call    cs:__guard_dispatch_icall_fptr
0x18002d124  test    al, al
0x18002d126  jz      short loc_18002D16D
0x18002d128  cmp     [rbp+var_48], r15d
0x18002d12c  jz      short loc_18002D14A
0x18002d12e  mov     rcx, [rbp+var_50]
0x18002d132  test    rcx, rcx
0x18002d135  jz      short loc_18002D146
0x18002d137  mov     rax, [rcx]
0x18002d13a  mov     edx, r12d
0x18002d13d  mov     rax, [rax]
0x18002d140  call    cs:__guard_dispatch_icall_fptr
0x18002d146  mov     [rbp+var_48], r15d
0x18002d14a  mov     rcx, [rdi+8]
0x18002d14e  mov     rax, [rcx]
0x18002d151  mov     r8b, r12b
0x18002d154  lea     rdx, aNgenserviceRoo; "NGenService\\Roots"
0x18002d15b  mov     rax, [rax+18h]
0x18002d15f  call    cs:__guard_dispatch_icall_fptr
0x18002d165  test    al, al
0x18002d167  jz      loc_18002D1F7
0x18002d16d  cmp     [rbp+var_48], r15d
0x18002d171  jz      short loc_18002D18F
0x18002d173  mov     rcx, [rbp+var_50]
0x18002d177  test    rcx, rcx
0x18002d17a  jz      short loc_18002D18B
0x18002d17c  mov     rax, [rcx]
0x18002d17f  mov     edx, r12d
0x18002d182  mov     rax, [rax]
0x18002d185  call    cs:__guard_dispatch_icall_fptr
0x18002d18b  mov     [rbp+var_48], r15d
0x18002d18f  test    esi, esi
0x18002d191  jz      short loc_18002D1C3
0x18002d193  test    rbx, rbx
0x18002d196  jz      short loc_18002D1BF
0x18002d198  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18002d19f  test    rax, rax
0x18002d1a2  jnz     short loc_18002D1B1
0x18002d1a4  call    cs:__imp_GetProcessHeap
0x18002d1aa  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18002d1b1  mov     r8, rbx; lpMem
0x18002d1b4  xor     edx, edx; dwFlags
0x18002d1b6  mov     rcx, rax; hHeap
0x18002d1b9  call    cs:__imp_HeapFree
0x18002d1bf  mov     [rbp+var_8], r15d
0x18002d1c3  test    r14d, r14d
0x18002d1c6  jz      short loc_18002D1DE
0x18002d1c8  mov     rax, [rdi]
0x18002d1cb  mov     edx, r12d
0x18002d1ce  mov     rcx, rdi
0x18002d1d1  mov     rax, [rax]
0x18002d1d4  call    cs:__guard_dispatch_icall_fptr
0x18002d1da  mov     [rbp+var_18], r15d
0x18002d1de  lea     r11, [rsp+70h+var_s0]
0x18002d1e3  mov     rbx, [r11+38h]
0x18002d1e7  mov     rsi, [r11+40h]
0x18002d1eb  mov     rsp, r11
0x18002d1ee  pop     r15
0x18002d1f0  pop     r14
0x18002d1f2  pop     r12
0x18002d1f4  pop     rdi
0x18002d1f5  pop     rbp
0x18002d1f6  retn
0x18002d1f7  call    ?ThrowLastError@@YAXXZ; ThrowLastError(void)
0x18002d1fd  mov     ecx, 80004005h; int
0x18002d202  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
