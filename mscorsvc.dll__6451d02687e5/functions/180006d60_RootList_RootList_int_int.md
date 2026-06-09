# RootList::RootList(int,int *)

- ea: `0x180006d60`
- end: `0x18000704f`
- name: `??0RootList@@QEAA@HPEAH@Z`
- size: `751`
- prototype: `RootList *__fastcall(RootList *this, int, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180006a2c`

## callees

- `0x180001e8c`
- `0x180006d60`
- `0x1800198dc`
- `0x180030ab8`
- `0x180030d84`
- `0x18003691c`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180006efa`
- `KERNEL32!HeapFree` at `0x18000701b`
- `KERNEL32!HeapFree` at `0x180006efa`
- `KERNEL32!HeapFree` at `0x18000701b`
- `KERNEL32!GetProcessHeap` at `0x180006ee5`
- `KERNEL32!GetProcessHeap` at `0x180007006`
- `KERNEL32!GetProcessHeap` at `0x180006ee5`
- `KERNEL32!GetProcessHeap` at `0x180007006`

## string_xrefs

- `0x180006e69`: `NGenService`

## pseudocode

```c
RootList *__fastcall RootList::RootList(RootList *this, int a2, int *a3)
{
  int v6; // r15d
  char *v7; // rsi
  char *v8; // rcx
  struct IRegWrapper *SimpleRegWrapper; // r14
  char v10; // di
  unsigned __int16 *v11; // r14
  HANDLE ProcessHeap; // rax
  void *v13; // rdi
  HANDLE v14; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-E0h] BYREF
  char *v17; // [rsp+28h] [rbp-D8h]
  int v18; // [rsp+30h] [rbp-D0h]
  RootList *v19; // [rsp+38h] [rbp-C8h]
  char *v20; // [rsp+40h] [rbp-C0h]
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+54h] [rbp-ACh]
  LPVOID v23; // [rsp+60h] [rbp-A0h]
  __int16 v24; // [rsp+68h] [rbp-98h] BYREF

  v19 = this;
  *(_QWORD *)this = &Node::`vftable';
  v6 = 0;
  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &RootList::`vftable';
  v7 = (char *)this + 24;
  lpMem = (char *)this + 24;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 8) = 0;
  v8 = (char *)this + 40;
  v20 = v8;
  *(_DWORD *)v8 = 0;
  *(_QWORD *)(v8 + 4) = 512;
  *((_QWORD *)v8 + 2) = v8 + 24;
  v17 = (char *)this + 576;
  *((_QWORD *)this + 72) = 0;
  *((_DWORD *)this + 146) = 0;
  *((_BYTE *)this + 597) = 0;
  *a3 = 0;
  SimpleRegWrapper = CreateSimpleRegWrapper(a2);
  v10 = 1;
  if ( *((_DWORD *)v7 + 2) )
  {
    if ( *(_QWORD *)v7 )
      (***(void (__fastcall ****)(_QWORD, __int64))v7)(*(_QWORD *)v7, 1);
    *((_DWORD *)v7 + 2) = 0;
  }
  *(_QWORD *)v7 = SimpleRegWrapper;
  if ( SimpleRegWrapper )
    *((_DWORD *)v7 + 2) = 1;
  v22 = 512;
  v23 = &v24;
  v21 = 2;
  v24 = 0;
  SString::Set((SString *)&v21, L"NGenService");
  lpMem = 0;
  CLRConfig::GetConfigValue(
    (const struct CLRConfig::ConfigStringInfo *)&CLRConfig::EXTERNAL_ZapSet,
    (unsigned __int16 **)&lpMem);
  v11 = (unsigned __int16 *)lpMem;
  v17 = (char *)lpMem;
  v18 = 0;
  if ( lpMem )
    v6 = 1;
  v18 = v6;
  if ( lpMem )
  {
    SString::Append((SString *)&v21, L"\\");
    SString::Append((SString *)&v21, v11);
  }
  if ( v6 )
  {
    if ( v11 )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v11);
    }
    v18 = 0;
  }
  SString::Append((SString *)&v21, L"\\");
  SString::Append((SString *)&v21, L"Roots");
  SString::ConvertToUnicode((SString *)&v21);
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, LPVOID, char *))(**(_QWORD **)(*(_QWORD *)v7 + 8LL) + 8LL))(
          *(_QWORD *)(*(_QWORD *)v7 + 8LL),
          v23,
          (char *)this + 576) )
  {
    if ( a2 )
    {
      *a3 = 1;
    }
    else
    {
      SString::ConvertToUnicode((SString *)&v21);
      (*(void (__fastcall **)(_QWORD, LPVOID, char *))(**(_QWORD **)(*(_QWORD *)v7 + 8LL) + 16LL))(
        *(_QWORD *)(*(_QWORD *)v7 + 8LL),
        v23,
        (char *)this + 576);
    }
  }
  *((_DWORD *)this + 148) = 0;
  *((_BYTE *)this + 596) = a2 != 0;
  if ( !a2 && !*a3 )
  {
    LODWORD(lpMem) = 0;
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, const wchar_t *, LPVOID *))(**((_QWORD **)this + 72) + 48LL))(
            *((_QWORD *)this + 72),
            L"WorkPending",
            &lpMem)
      || !(_DWORD)lpMem )
    {
      v10 = 0;
    }
    *((_BYTE *)this + 599) = v10;
    *((_BYTE *)this + 598) = v10;
  }
  if ( (v22 & 0x800000000LL) != 0 )
  {
    v13 = v23;
    if ( v23 )
    {
      v14 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v14 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v14;
      }
      HeapFree(v14, 0, v13);
    }
  }
  return this;
}

```

## disassembly

```asm
0x180006d60  mov     [rsp-8+arg_18], rbx
0x180006d65  push    rbp
0x180006d66  push    rsi
0x180006d67  push    rdi
0x180006d68  push    r12
0x180006d6a  push    r13
0x180006d6c  push    r14
0x180006d6e  push    r15
0x180006d70  lea     rbp, [rsp-180h]
0x180006d78  sub     rsp, 280h
0x180006d7f  mov     rax, cs:__security_cookie
0x180006d86  xor     rax, rsp
0x180006d89  mov     [rbp+1B0h+var_40], rax
0x180006d90  mov     r13, r8
0x180006d93  mov     r12d, edx
0x180006d96  mov     rbx, rcx
0x180006d99  mov     [rsp+2B0h+var_278], rcx
0x180006d9e  lea     rax, ??_7Node@@6B@; const Node::`vftable'
0x180006da5  mov     [rcx], rax
0x180006da8  xor     r15d, r15d
0x180006dab  mov     [rcx+8], r15
0x180006daf  lea     rax, ??_7RootList@@6B@; const RootList::`vftable'
0x180006db6  mov     [rcx], rax
0x180006db9  lea     rsi, [rcx+18h]
0x180006dbd  mov     [rsp+2B0h+lpMem], rsi
0x180006dc2  mov     [rsi], r15
0x180006dc5  mov     [rsi+8], r15d
0x180006dc9  add     rcx, 28h ; '('
0x180006dcd  mov     [rsp+2B0h+var_270], rcx
0x180006dd2  mov     [rcx], r15d
0x180006dd5  mov     qword ptr [rcx+4], 200h
0x180006ddd  lea     rax, [rcx+18h]
0x180006de1  mov     [rcx+10h], rax
0x180006de5  lea     rax, [rbx+240h]
0x180006dec  mov     [rsp+2B0h+var_288], rax
0x180006df1  mov     [rax], r15
0x180006df4  mov     [rax+8], r15d
0x180006df8  mov     [rbx+255h], r15b
0x180006dff  mov     [r8], r15d
0x180006e02  mov     ecx, edx; int
0x180006e04  call    ?CreateSimpleRegWrapper@@YAPEAVIRegWrapper@@H@Z; CreateSimpleRegWrapper(int)
0x180006e09  mov     r14, rax
0x180006e0c  lea     edi, [r15+1]
0x180006e10  cmp     [rsi+8], r15d
0x180006e14  jz      short loc_180006E30
0x180006e16  mov     rcx, [rsi]
0x180006e19  test    rcx, rcx
0x180006e1c  jz      short loc_180006E2C
0x180006e1e  mov     rax, [rcx]
0x180006e21  mov     edx, edi
0x180006e23  mov     rax, [rax]
0x180006e26  call    cs:__guard_dispatch_icall_fptr
0x180006e2c  mov     [rsi+8], r15d
0x180006e30  mov     [rsi], r14
0x180006e33  test    r14, r14
0x180006e36  jz      short loc_180006E3B
0x180006e38  mov     [rsi+8], edi
0x180006e3b  mov     [rsp+2B0h+var_260], r15
0x180006e40  mov     [rsp+2B0h+var_260+4], 200h
0x180006e49  mov     [rsp+2B0h+var_250], r15
0x180006e4e  lea     rax, [rsp+2B0h+var_248]
0x180006e53  mov     [rsp+2B0h+var_250], rax
0x180006e58  mov     dword ptr [rsp+2B0h+var_260], 2
0x180006e60  mov     rax, [rsp+2B0h+var_250]
0x180006e65  mov     [rax], r15w
0x180006e69  lea     rdx, aNgenservice; "NGenService"
0x180006e70  lea     rcx, [rsp+2B0h+var_260]; this
0x180006e75  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x180006e7a  mov     [rsp+2B0h+lpMem], r15
0x180006e7f  lea     rdx, [rsp+2B0h+lpMem]; unsigned __int16 **
0x180006e84  lea     rcx, ?EXTERNAL_ZapSet@CLRConfig@@2UConfigStringInfo@1@B; struct CLRConfig::ConfigStringInfo *
0x180006e8b  call    ?GetConfigValue@CLRConfig@@SAJAEBUConfigStringInfo@1@PEAPEAG@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigStringInfo const &,ushort * *)
0x180006e90  mov     r14, [rsp+2B0h+lpMem]
0x180006e95  mov     [rsp+2B0h+var_288], r14
0x180006e9a  mov     [rsp+2B0h+var_280], r15d
0x180006e9f  test    r14, r14
0x180006ea2  cmovnz  r15d, edi
0x180006ea6  mov     [rsp+2B0h+var_280], r15d
0x180006eab  jz      short loc_180006ECC
0x180006ead  lea     rdx, asc_180049544; "\\"
0x180006eb4  lea     rcx, [rsp+2B0h+var_260]; this
0x180006eb9  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180006ebe  mov     rdx, r14; unsigned __int16 *
0x180006ec1  lea     rcx, [rsp+2B0h+var_260]; this
0x180006ec6  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180006ecb  nop
0x180006ecc  test    r15d, r15d
0x180006ecf  jz      short loc_180006F07
0x180006ed1  xor     r15d, r15d
0x180006ed4  test    r14, r14
0x180006ed7  jz      short loc_180006F00
0x180006ed9  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180006ee0  test    rax, rax
0x180006ee3  jnz     short loc_180006EF2
0x180006ee5  call    cs:__imp_GetProcessHeap
0x180006eeb  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180006ef2  mov     r8, r14; lpMem
0x180006ef5  xor     edx, edx; dwFlags
0x180006ef7  mov     rcx, rax; hHeap
0x180006efa  call    cs:__imp_HeapFree
0x180006f00  mov     [rsp+2B0h+var_280], r15d
0x180006f05  jmp     short loc_180006F0A
0x180006f07  xor     r15d, r15d
0x180006f0a  lea     rdx, asc_180049544; "\\"
0x180006f11  lea     rcx, [rsp+2B0h+var_260]; this
0x180006f16  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180006f1b  lea     rdx, aRoots; "Roots"
0x180006f22  lea     rcx, [rsp+2B0h+var_260]; this
0x180006f27  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180006f2c  lea     rcx, [rsp+2B0h+var_260]; this
0x180006f31  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180006f36  mov     rax, [rsi]
0x180006f39  mov     rcx, [rax+8]
0x180006f3d  mov     rax, [rcx]
0x180006f40  lea     r14, [rbx+240h]
0x180006f47  mov     r8, r14
0x180006f4a  mov     rdx, [rsp+2B0h+var_250]
0x180006f4f  mov     rax, [rax+8]
0x180006f53  call    cs:__guard_dispatch_icall_fptr
0x180006f59  test    al, al
0x180006f5b  jnz     short loc_180006F8E
0x180006f5d  test    r12d, r12d
0x180006f60  jnz     short loc_180006F8A
0x180006f62  lea     rcx, [rsp+2B0h+var_260]; this
0x180006f67  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180006f6c  mov     rax, [rsi]
0x180006f6f  mov     rcx, [rax+8]
0x180006f73  mov     rax, [rcx]
0x180006f76  mov     r8, r14
0x180006f79  mov     rdx, [rsp+2B0h+var_250]
0x180006f7e  mov     rax, [rax+10h]
0x180006f82  call    cs:__guard_dispatch_icall_fptr
0x180006f88  jmp     short loc_180006F8E
0x180006f8a  mov     [r13+0], edi
0x180006f8e  mov     [rbx+250h], r15d
0x180006f95  test    r12d, r12d
0x180006f98  setnz   al
0x180006f9b  mov     [rbx+254h], al
0x180006fa1  test    r12d, r12d
0x180006fa4  jnz     short loc_180006FE9
0x180006fa6  cmp     [r13+0], r15d
0x180006faa  jnz     short loc_180006FE9
0x180006fac  mov     dword ptr [rsp+2B0h+lpMem], r15d
0x180006fb1  mov     rcx, [r14]
0x180006fb4  mov     rax, [rcx]
0x180006fb7  lea     r8, [rsp+2B0h+lpMem]
0x180006fbc  lea     rdx, aWorkpending; "WorkPending"
0x180006fc3  mov     rax, [rax+30h]
0x180006fc7  call    cs:__guard_dispatch_icall_fptr
0x180006fcd  test    al, al
0x180006fcf  jz      short loc_180006FD8
0x180006fd1  cmp     dword ptr [rsp+2B0h+lpMem], r15d
0x180006fd6  jnz     short loc_180006FDB
0x180006fd8  mov     dil, r15b
0x180006fdb  mov     [rbx+257h], dil
0x180006fe2  mov     [rbx+256h], dil
0x180006fe9  test    [rsp+2B0h+var_258], 8
0x180006fee  jz      short loc_180007022
0x180006ff0  mov     rdi, [rsp+2B0h+var_250]
0x180006ff5  test    rdi, rdi
0x180006ff8  jz      short loc_180007022
0x180006ffa  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180007001  test    rax, rax
0x180007004  jnz     short loc_180007013
0x180007006  call    cs:__imp_GetProcessHeap
0x18000700c  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180007013  mov     r8, rdi; lpMem
0x180007016  xor     edx, edx; dwFlags
0x180007018  mov     rcx, rax; hHeap
0x18000701b  call    cs:__imp_HeapFree
0x180007021  nop
0x180007022  mov     rax, rbx
0x180007025  mov     rcx, [rbp+1B0h+var_40]
0x18000702c  xor     rcx, rsp; StackCookie
0x18000702f  call    __security_check_cookie
0x180007034  mov     rbx, [rsp+2B0h+arg_18]
0x18000703c  add     rsp, 280h
0x180007043  pop     r15
0x180007045  pop     r14
0x180007047  pop     r13
0x180007049  pop     r12
0x18000704b  pop     rdi
0x18000704c  pop     rsi
0x18000704d  pop     rbp
0x18000704e  retn
```
