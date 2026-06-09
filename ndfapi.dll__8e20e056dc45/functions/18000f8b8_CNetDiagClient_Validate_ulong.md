# CNetDiagClient::Validate(ulong)

- ea: `0x18000f8b8`
- end: `0x18000fa39`
- name: `?Validate@CNetDiagClient@@QEAAJK@Z`
- size: `385`
- prototype: `__int64 __fastcall(CNetDiagClient *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180015900`
- `0x18001a6b4`

## callees

- `0x18000cd4c`
- `0x18000eb28`
- `0x18000f8b8`
- `0x18001f646`
- `0x18001f690`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000f98b`
- `KERNEL32!GetLastError` at `0x18000f98b`
- `wdi!WdiGetResult` at `0x18000f971`
- `wdi!WdiGetResult` at `0x18000f971`
- `wdi!WdiAddParameter` at `0x18000f918`
- `wdi!WdiAddParameter` at `0x18000f918`
- `wdi!WdiResolve` at `0x18000f92f`
- `wdi!WdiResolve` at `0x18000f92f`

## string_xrefs

- `0x18000f90d`: `ValidateRepair`

## pseudocode

```c
signed int __fastcall CNetDiagClient::Validate(CNetDiagClient *this, DWORD a2)
{
  __int64 v4; // rcx
  signed int result; // eax
  __int64 v6; // rcx
  __int64 v7; // r8
  DWORD v8; // eax
  bool v9; // sf
  int v10; // [rsp+30h] [rbp-30h] BYREF
  unsigned int v11; // [rsp+34h] [rbp-2Ch] BYREF
  int v12; // [rsp+38h] [rbp-28h] BYREF
  __int128 Buf2; // [rsp+40h] [rbp-20h] BYREF

  v10 = 0;
  v11 = 0;
  v4 = *((_QWORD *)this + 16);
  v12 = 1;
  Buf2 = 0;
  result = WdiAddParameter(v4, 0, L"ValidateRepair", 4, &v12);
  if ( result < 0 )
    goto LABEL_24;
  result = WdiResolve(*((_QWORD *)this + 16), 0);
  if ( result < 0 )
    goto LABEL_24;
  v8 = NetDiagClientWaitForObjects(v6, (void *const *)this + 388, v7, a2);
  if ( !v8 )
  {
    if ( !*((_DWORD *)this + 819) )
    {
      result = WdiGetResult(*((_QWORD *)this + 16), &Buf2, &v10, &v11);
      goto LABEL_10;
    }
    goto LABEL_23;
  }
  if ( v8 == 128 )
  {
LABEL_23:
    result = -2147467260;
    goto LABEL_24;
  }
  if ( v8 != 258 )
  {
    result = GetLastError();
    v9 = result < 0;
    if ( result <= 0 )
      goto LABEL_11;
    result = (unsigned __int16)result | 0x80070000;
LABEL_10:
    v9 = result < 0;
LABEL_11:
    if ( v9 )
      goto LABEL_24;
    if ( !memcmp_0(NetDiagModuleId, &Buf2, 0x10u) && v11 >= 2 )
    {
      if ( v11 == 2 )
      {
        if ( v10 >= 0 )
          CNetDiagClient::GetCallResult(this, &v10);
LABEL_21:
        result = v10;
        goto LABEL_24;
      }
      if ( v11 == 4 )
      {
        if ( v10 == -2147023673 )
          return -2147467260;
        goto LABEL_21;
      }
    }
    result = -2147467259;
    goto LABEL_24;
  }
  result = -2147024638;
LABEL_24:
  if ( v10 == -2146895610 )
    return -2146895610;
  return result;
}

```

## disassembly

```asm
0x18000f8b8  mov     [rsp-8+arg_10], rbx
0x18000f8bd  mov     [rsp-8+arg_18], rdi
0x18000f8c2  push    rbp
0x18000f8c3  mov     rbp, rsp
0x18000f8c6  sub     rsp, 60h
0x18000f8ca  mov     rax, cs:__security_cookie
0x18000f8d1  xor     rax, rsp
0x18000f8d4  mov     [rbp+var_10], rax
0x18000f8d8  mov     edi, edx
0x18000f8da  mov     [rbp+var_30], 0
0x18000f8e1  mov     rbx, rcx
0x18000f8e4  mov     [rbp+var_2C], 0
0x18000f8eb  mov     rcx, [rcx+80h]
0x18000f8f2  lea     rax, [rbp+var_28]
0x18000f8f6  xorps   xmm0, xmm0
0x18000f8f9  mov     [rsp+60h+var_40], rax
0x18000f8fe  xor     edx, edx
0x18000f900  mov     [rbp+var_28], 1
0x18000f907  mov     r9d, 4
0x18000f90d  lea     r8, aValidaterepair; "ValidateRepair"
0x18000f914  movups  [rbp+Buf2], xmm0
0x18000f918  call    cs:__imp_WdiAddParameter
0x18000f91e  test    eax, eax
0x18000f920  js      loc_18000FA10
0x18000f926  mov     rcx, [rbx+80h]
0x18000f92d  xor     edx, edx
0x18000f92f  call    cs:__imp_WdiResolve
0x18000f935  test    eax, eax
0x18000f937  js      loc_18000FA10
0x18000f93d  lea     rdx, [rbx+0C20h]; void **
0x18000f944  mov     r9d, edi; unsigned int
0x18000f947  call    ?NetDiagClientWaitForObjects@@YAKKPEBQEAXHK@Z; NetDiagClientWaitForObjects(ulong,void * const *,int,ulong)
0x18000f94c  test    eax, eax
0x18000f94e  jnz     short loc_18000F979
0x18000f950  mov     eax, [rbx+0CCCh]
0x18000f956  test    eax, eax
0x18000f958  jnz     loc_18000FA0B
0x18000f95e  mov     rcx, [rbx+80h]
0x18000f965  lea     r9, [rbp+var_2C]
0x18000f969  lea     r8, [rbp+var_30]
0x18000f96d  lea     rdx, [rbp+Buf2]
0x18000f971  call    cs:__imp_WdiGetResult
0x18000f977  jmp     short loc_18000F99D
0x18000f979  cmp     eax, 80h
0x18000f97e  jz      loc_18000FA0B
0x18000f984  cmp     eax, 102h
0x18000f989  jz      short loc_18000FA04
0x18000f98b  call    cs:__imp_GetLastError
0x18000f991  test    eax, eax
0x18000f993  jle     short loc_18000F99F
0x18000f995  movzx   eax, ax
0x18000f998  or      eax, 80070000h
0x18000f99d  test    eax, eax
0x18000f99f  js      short loc_18000FA10
0x18000f9a1  mov     r8d, 10h; Size
0x18000f9a7  lea     rdx, [rbp+Buf2]; Buf2
0x18000f9ab  lea     rcx, NetDiagModuleId; Buf1
0x18000f9b2  call    memcmp_0
0x18000f9b7  test    eax, eax
0x18000f9b9  jz      short loc_18000F9C2
0x18000f9bb  mov     eax, 80004005h
0x18000f9c0  jmp     short loc_18000FA10
0x18000f9c2  mov     ecx, [rbp+var_2C]
0x18000f9c5  test    ecx, ecx
0x18000f9c7  jz      short loc_18000F9BB
0x18000f9c9  sub     ecx, 1
0x18000f9cc  jz      short loc_18000F9BB
0x18000f9ce  sub     ecx, 1
0x18000f9d1  jz      short loc_18000F9ED
0x18000f9d3  sub     ecx, 1
0x18000f9d6  jz      short loc_18000F9BB
0x18000f9d8  cmp     ecx, 1
0x18000f9db  jnz     short loc_18000F9BB
0x18000f9dd  cmp     [rbp+var_30], 800704C7h
0x18000f9e4  jnz     short loc_18000F9FF
0x18000f9e6  mov     eax, 80004004h
0x18000f9eb  jmp     short loc_18000FA1B
0x18000f9ed  cmp     [rbp+var_30], 0
0x18000f9f1  jl      short loc_18000F9FF
0x18000f9f3  lea     rdx, [rbp+var_30]; void *
0x18000f9f7  mov     rcx, rbx; this
0x18000f9fa  call    ?GetCallResult@CNetDiagClient@@QEAAJPEAJ@Z; CNetDiagClient::GetCallResult(long *)
0x18000f9ff  mov     eax, [rbp+var_30]
0x18000fa02  jmp     short loc_18000FA10
0x18000fa04  mov     eax, 80070102h
0x18000fa09  jmp     short loc_18000FA10
0x18000fa0b  mov     eax, 80004004h
0x18000fa10  mov     ecx, 8008F906h
0x18000fa15  cmp     [rbp+var_30], ecx
0x18000fa18  cmovz   eax, ecx
0x18000fa1b  mov     rcx, [rbp+var_10]
0x18000fa1f  xor     rcx, rsp; StackCookie
0x18000fa22  call    __security_check_cookie
0x18000fa27  lea     r11, [rsp+60h+var_s0]
0x18000fa2c  mov     rbx, [r11+20h]
0x18000fa30  mov     rdi, [r11+28h]
0x18000fa34  mov     rsp, r11
0x18000fa37  pop     rbp
0x18000fa38  retn
```
