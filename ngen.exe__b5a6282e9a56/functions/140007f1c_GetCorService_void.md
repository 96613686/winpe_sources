# GetCorService(void)

- ea: `0x140007f1c`
- end: `0x140008010`
- name: `?GetCorService@@YAPEAUICorSvc@@XZ`
- size: `244`
- prototype: `struct ICorSvc *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140008010`
- `0x1400081f8`

## callees

- `0x140007f1c`
- `0x14000e4f4`
- `0x140013f30`

## import_xrefs

- `mscoree!CorGetSvc` at `0x140007f54`
- `mscoree!CorGetSvc` at `0x140007f54`

## pseudocode

```c
struct ICorSvc *GetCorService(void)
{
  int Svc; // eax
  int v1; // eax
  int v2; // eax
  __int64 v3; // rbx
  __int64 v5; // [rsp+28h] [rbp-28h] BYREF
  int v6; // [rsp+30h] [rbp-20h]
  __int64 v7; // [rsp+38h] [rbp-18h] BYREF
  int v8; // [rsp+40h] [rbp-10h]

  v6 = 0;
  v5 = 0;
  Svc = CorGetSvc(&v5);
  if ( Svc < 0 )
    ThrowHR(Svc);
  v1 = v6;
  if ( v5 )
    v1 = 1;
  v6 = v1;
  v8 = 0;
  v7 = 0;
  v2 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v5)(v5, &IID_ICorSvc, &v7);
  if ( v2 < 0 )
    ThrowHR(v2);
  v3 = v7;
  v8 = 0;
  if ( v6 )
  {
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    v6 = 0;
  }
  return (struct ICorSvc *)v3;
}

```

## disassembly

```asm
0x140007f1c  mov     [rsp-8+arg_8], rbx
0x140007f21  mov     [rsp-8+arg_10], rsi
0x140007f26  push    rbp
0x140007f27  mov     rbp, rsp
0x140007f2a  sub     rsp, 50h
0x140007f2e  and     [rbp+var_30], 0
0x140007f32  and     [rbp+var_28], 0
0x140007f37  and     [rbp+var_20], 0
0x140007f3b  lea     rax, [rbp+var_28]
0x140007f3f  mov     [rbp+arg_0], rax
0x140007f43  and     [rbp+var_28], 0
0x140007f48  mov     esi, 1
0x140007f4d  mov     [rbp+var_30], esi
0x140007f50  lea     rcx, [rbp+var_28]
0x140007f54  call    cs:__imp_CorGetSvc
0x140007f5a  test    eax, eax
0x140007f5c  js      loc_140008008
0x140007f62  mov     ebx, esi
0x140007f64  and     ebx, 0FFFFFFFEh
0x140007f67  mov     [rbp+var_30], ebx
0x140007f6a  mov     eax, [rbp+var_20]
0x140007f6d  cmp     [rbp+var_28], 0
0x140007f72  cmovnz  eax, esi
0x140007f75  mov     [rbp+var_20], eax
0x140007f78  and     [rbp+var_18], 0
0x140007f7d  and     [rbp+var_10], 0
0x140007f81  mov     rcx, [rbp+var_28]
0x140007f85  lea     rax, [rbp+var_18]
0x140007f89  mov     [rbp+arg_0], rax
0x140007f8d  and     [rbp+var_18], 0
0x140007f92  or      ebx, 2
0x140007f95  mov     [rbp+var_30], ebx
0x140007f98  mov     rax, [rcx]
0x140007f9b  lea     r8, [rbp+var_18]
0x140007f9f  lea     rdx, IID_ICorSvc
0x140007fa6  mov     rax, [rax]
0x140007fa9  call    cs:__guard_dispatch_icall_fptr
0x140007faf  test    eax, eax
0x140007fb1  js      short loc_140008000
0x140007fb3  and     ebx, 0FFFFFFFDh
0x140007fb6  mov     [rbp+var_30], ebx
0x140007fb9  mov     eax, [rbp+var_10]
0x140007fbc  mov     rbx, [rbp+var_18]
0x140007fc0  test    rbx, rbx
0x140007fc3  cmovnz  eax, esi
0x140007fc6  mov     [rbp+var_10], eax
0x140007fc9  and     [rbp+var_10], 0
0x140007fcd  cmp     [rbp+var_20], 0
0x140007fd1  jz      short loc_140007FED
0x140007fd3  mov     rcx, [rbp+var_28]
0x140007fd7  test    rcx, rcx
0x140007fda  jz      short loc_140007FE9
0x140007fdc  mov     rdx, [rcx]
0x140007fdf  mov     rax, [rdx+10h]
0x140007fe3  call    cs:__guard_dispatch_icall_fptr
0x140007fe9  and     [rbp+var_20], 0
0x140007fed  mov     rax, rbx
0x140007ff0  mov     rbx, [rsp+50h+arg_8]
0x140007ff5  mov     rsi, [rsp+50h+arg_10]
0x140007ffa  add     rsp, 50h
0x140007ffe  pop     rbp
0x140007fff  retn
0x140008000  mov     ecx, eax; int
0x140008002  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x140008008  mov     ecx, eax; int
0x14000800a  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
