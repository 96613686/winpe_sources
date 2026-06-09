# Configuration::SetConfigPath(NewHolder<Image> &)

- ea: `0x180009c6c`
- end: `0x180009df3`
- name: `?SetConfigPath@Configuration@@QEAAXAEAV?$NewHolder@VImage@@@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x180009ff4`
- `0x18001d780`

## callees

- `0x180009c6c`
- `0x18000b794`
- `0x18000c80c`
- `0x180030568`
- `0x18003dc30`
- `0x18003dc50`
- `0x18003f280`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180009da2`
- `KERNEL32!HeapFree` at `0x180009da2`
- `KERNEL32!GetProcessHeap` at `0x180009d8d`
- `KERNEL32!GetProcessHeap` at `0x180009d8d`

## string_xrefs

- `0x180009cfb`: `Config`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall Configuration::SetConfigPath(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rdi
  void (__fastcall **v5)(_QWORD *, __int64); // rbx
  const unsigned __int16 *v6; // rax
  Image *v7; // rdi
  __int64 v8; // rbx
  void *v9; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD *v11; // [rsp+20h] [rbp-E0h] BYREF
  int v12; // [rsp+28h] [rbp-D8h]
  __int64 v13; // [rsp+30h] [rbp-D0h]
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+44h] [rbp-BCh]
  LPVOID lpMem; // [rsp+50h] [rbp-B0h]
  __int16 v17; // [rsp+58h] [rbp-A8h] BYREF

  v11 = 0;
  v12 = 0;
  Node::GetRegKeyThrowing(a1, &v11);
  v15 = 512;
  lpMem = &v17;
  v14 = 2;
  v17 = 0;
  v4 = v11;
  v5 = (void (__fastcall **)(_QWORD *, __int64))*v11;
  v6 = Image::Serialize(*(Image **)a2, (struct SString *)&v14);
  ((void (__fastcall *)(_QWORD *, const wchar_t *, const unsigned __int16 *))v5[8])(v4, L"Config", v6);
  *(_DWORD *)(a2 + 8) = 0;
  v7 = *(Image **)a2;
  if ( *(_DWORD *)(a1 + 576) )
  {
    v8 = *(_QWORD *)(a1 + 568);
    v13 = v8;
    if ( v8 )
    {
      v13 = v8;
      if ( (*(_BYTE *)(v8 + 8) & 8) != 0 )
        operator delete(*(void **)(v8 + 16));
      operator delete((void *)v8);
    }
    *(_DWORD *)(a1 + 576) = 0;
  }
  *(_QWORD *)(a1 + 568) = v7;
  if ( v7 )
    *(_DWORD *)(a1 + 576) = 1;
  if ( (v15 & 0x800000000LL) != 0 )
  {
    v9 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v9);
    }
  }
  if ( v12 )
  {
    if ( v11 )
      (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
  }
}

```

## disassembly

```asm
0x180009c6c  mov     [rsp-8+arg_10], rbx
0x180009c71  push    rbp
0x180009c72  push    rsi
0x180009c73  push    rdi
0x180009c74  push    r14
0x180009c76  push    r15
0x180009c78  lea     rbp, [rsp-170h]
0x180009c80  sub     rsp, 270h
0x180009c87  mov     rax, cs:__security_cookie
0x180009c8e  xor     rax, rsp
0x180009c91  mov     [rbp+190h+var_30], rax
0x180009c98  mov     rsi, rdx
0x180009c9b  mov     r14, rcx
0x180009c9e  xor     r15d, r15d
0x180009ca1  mov     [rsp+290h+var_270], r15
0x180009ca6  mov     [rsp+290h+var_268], r15d
0x180009cab  lea     rdx, [rsp+290h+var_270]
0x180009cb0  call    ?GetRegKeyThrowing@Node@@QEAAXAEAV?$NewHolder@VKey@IRegWrapper@@@@@Z; Node::GetRegKeyThrowing(NewHolder<IRegWrapper::Key> &)
0x180009cb5  mov     [rsp+290h+var_250], r15
0x180009cba  mov     [rsp+290h+var_250+4], 200h
0x180009cc3  mov     [rsp+290h+lpMem], r15
0x180009cc8  lea     rax, [rsp+290h+var_238]
0x180009ccd  mov     [rsp+290h+lpMem], rax
0x180009cd2  mov     dword ptr [rsp+290h+var_250], 2
0x180009cda  mov     rax, [rsp+290h+lpMem]
0x180009cdf  mov     [rax], r15w
0x180009ce3  mov     rdi, [rsp+290h+var_270]
0x180009ce8  mov     rbx, [rdi]
0x180009ceb  lea     rdx, [rsp+290h+var_250]; struct SString *
0x180009cf0  mov     rcx, [rsi]; this
0x180009cf3  call    ?Serialize@Image@@QEAAPEBGAEAVSString@@@Z; Image::Serialize(SString &)
0x180009cf8  mov     r8, rax
0x180009cfb  lea     rdx, aConfig; "Config"
0x180009d02  mov     rcx, rdi
0x180009d05  mov     rax, [rbx+40h]
0x180009d09  call    cs:__guard_dispatch_icall_fptr
0x180009d0f  mov     [rsi+8], r15d
0x180009d13  mov     rdi, [rsi]
0x180009d16  cmp     [r14+240h], r15d
0x180009d1d  jz      short loc_180009D58
0x180009d1f  mov     rbx, [r14+238h]
0x180009d26  mov     [rsp+290h+var_260], rbx
0x180009d2b  test    rbx, rbx
0x180009d2e  jz      short loc_180009D51
0x180009d30  mov     [rsp+290h+var_260], rbx
0x180009d35  test    byte ptr [rbx+8], 8
0x180009d39  jz      short loc_180009D44
0x180009d3b  mov     rcx, [rbx+10h]; lpMem
0x180009d3f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009d44  mov     edx, 18h; unsigned __int64
0x180009d49  mov     rcx, rbx; void *
0x180009d4c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009d51  mov     [r14+240h], r15d
0x180009d58  mov     [r14+238h], rdi
0x180009d5f  mov     esi, 1
0x180009d64  test    rdi, rdi
0x180009d67  jz      short loc_180009D70
0x180009d69  mov     [r14+240h], esi
0x180009d70  test    [rsp+290h+var_248], 8
0x180009d75  jz      short loc_180009DA9
0x180009d77  mov     rbx, [rsp+290h+lpMem]
0x180009d7c  test    rbx, rbx
0x180009d7f  jz      short loc_180009DA9
0x180009d81  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180009d88  test    rax, rax
0x180009d8b  jnz     short loc_180009D9A
0x180009d8d  call    cs:__imp_GetProcessHeap
0x180009d93  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180009d9a  mov     r8, rbx; lpMem
0x180009d9d  xor     edx, edx; dwFlags
0x180009d9f  mov     rcx, rax; hHeap
0x180009da2  call    cs:__imp_HeapFree
0x180009da8  nop
0x180009da9  cmp     [rsp+290h+var_268], r15d
0x180009dae  jz      short loc_180009DCD
0x180009db0  mov     rcx, [rsp+290h+var_270]
0x180009db5  test    rcx, rcx
0x180009db8  jz      short loc_180009DC8
0x180009dba  mov     rax, [rcx]
0x180009dbd  mov     edx, esi
0x180009dbf  mov     rax, [rax]
0x180009dc2  call    cs:__guard_dispatch_icall_fptr
0x180009dc8  mov     [rsp+290h+var_268], r15d
0x180009dcd  mov     rcx, [rbp+190h+var_30]
0x180009dd4  xor     rcx, rsp; StackCookie
0x180009dd7  call    __security_check_cookie
0x180009ddc  mov     rbx, [rsp+290h+arg_10]
0x180009de4  add     rsp, 270h
0x180009deb  pop     r15
0x180009ded  pop     r14
0x180009def  pop     rdi
0x180009df0  pop     rsi
0x180009df1  pop     rbp
0x180009df2  retn
```
