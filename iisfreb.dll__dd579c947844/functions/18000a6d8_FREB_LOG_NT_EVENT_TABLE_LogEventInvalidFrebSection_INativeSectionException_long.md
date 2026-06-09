# FREB_LOG_NT_EVENT_TABLE::LogEventInvalidFrebSection(INativeSectionException *,long)

- ea: `0x18000a6d8`
- end: `0x18000a7da`
- name: `?LogEventInvalidFrebSection@FREB_LOG_NT_EVENT_TABLE@@QEAAXPEAVINativeSectionException@@J@Z`
- size: `258`
- prototype: `void(FREB_LOG_NT_EVENT_TABLE *__hidden this, struct INativeSectionException *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180001f90`
- `0x1800023cc`

## callees

- `0x18000a4dc`
- `0x18000a6d8`
- `0x18000ac90`
- `0x18000b010`

## import_xrefs

- `msvcrt!_ultow` at `0x18000a77e`
- `msvcrt!_ultow` at `0x18000a77e`

## pseudocode

```c
void __fastcall FREB_LOG_NT_EVENT_TABLE::LogEventInvalidFrebSection(
        FREB_LOG_NT_EVENT_TABLE *this,
        struct INativeSectionException *a2,
        unsigned int a3)
{
  __int64 v5; // rax
  unsigned __int16 v6; // dx
  unsigned __int16 **v7; // r8
  unsigned int v8; // ecx
  unsigned int Value; // [rsp+20h] [rbp-59h] BYREF
  __int64 *v10; // [rsp+28h] [rbp-51h] BYREF
  unsigned __int16 *v11[2]; // [rsp+30h] [rbp-49h] BYREF
  _QWORD v12[6]; // [rsp+40h] [rbp-39h] BYREF
  wchar_t Buffer[40]; // [rsp+70h] [rbp-9h] BYREF

  if ( a2 )
  {
    v12[0] = 0;
    v10 = &qword_18000E008;
    v11[0] = (unsigned __int16 *)&qword_18000E008;
    v5 = *(_QWORD *)a2;
    v12[1] = 0;
    Value = 0;
    (*(void (__fastcall **)(struct INativeSectionException *, __int64 **))(v5 + 24))(a2, &v10);
    (*(void (__fastcall **)(struct INativeSectionException *, unsigned __int16 **))(*(_QWORD *)a2 + 40LL))(a2, v11);
    (*(void (__fastcall **)(struct INativeSectionException *, unsigned int *))(*(_QWORD *)a2 + 32LL))(a2, &Value);
    v12[2] = v10;
    v12[3] = v11[0];
    _ultow(Value, Buffer, 10);
    v6 = 5;
    v12[4] = Buffer;
    v7 = (unsigned __int16 **)v12;
    v8 = -2147481361;
  }
  else
  {
    v7 = v11;
    *(_OWORD *)v11 = 0;
    v6 = 2;
    v8 = -2147481360;
  }
  FREB_LOG_NT_EVENT_TABLE::LogEvent(v8, v6, (const unsigned __int16 **const)v7, a3);
}

```

## disassembly

```asm
0x18000a6d8  mov     [rsp-8+arg_0], rbx
0x18000a6dd  mov     [rsp-8+arg_10], rdi
0x18000a6e2  push    rbp
0x18000a6e3  lea     rbp, [rsp-57h]
0x18000a6e8  sub     rsp, 0D0h
0x18000a6ef  mov     rax, cs:__security_cookie
0x18000a6f6  xor     rax, rsp
0x18000a6f9  mov     [rbp+57h+var_10], rax
0x18000a6fd  xor     ecx, ecx
0x18000a6ff  mov     edi, r8d
0x18000a702  mov     rbx, rdx
0x18000a705  test    rdx, rdx
0x18000a708  jz      loc_18000A79C
0x18000a70e  lea     rax, qword_18000E008
0x18000a715  mov     [rbp+57h+var_90], rcx
0x18000a719  mov     [rbp+57h+var_A8], rax
0x18000a71d  mov     [rbp+57h+var_A0], rax
0x18000a721  mov     rax, [rdx]
0x18000a724  lea     rdx, [rbp+57h+var_A8]
0x18000a728  mov     [rbp+57h+var_88], rcx
0x18000a72c  mov     [rbp+57h+Value], ecx
0x18000a72f  mov     rcx, rbx
0x18000a732  mov     rax, [rax+18h]
0x18000a736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a73b  mov     rax, [rbx]
0x18000a73e  lea     rdx, [rbp+57h+var_A0]
0x18000a742  mov     rcx, rbx
0x18000a745  mov     rax, [rax+28h]
0x18000a749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a74e  mov     rax, [rbx]
0x18000a751  lea     rdx, [rbp+57h+Value]
0x18000a755  mov     rcx, rbx
0x18000a758  mov     rax, [rax+20h]
0x18000a75c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a761  mov     rax, [rbp+57h+var_A8]
0x18000a765  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18000a769  mov     ecx, [rbp+57h+Value]; Value
0x18000a76c  mov     r8d, 0Ah; Radix
0x18000a772  mov     [rbp+57h+var_80], rax
0x18000a776  mov     rax, [rbp+57h+var_A0]
0x18000a77a  mov     [rbp+57h+var_78], rax
0x18000a77e  call    cs:__imp__ultow
0x18000a784  lea     rax, [rbp+57h+Buffer]
0x18000a788  mov     edx, 5
0x18000a78d  mov     [rbp+57h+var_70], rax
0x18000a791  lea     r8, [rbp+57h+var_90]
0x18000a795  mov     ecx, 800008EFh
0x18000a79a  jmp     short loc_18000A7B1
0x18000a79c  xorps   xmm0, xmm0
0x18000a79f  lea     r8, [rbp+57h+var_A0]; unsigned __int16 **
0x18000a7a3  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x18000a7a7  mov     edx, 2; unsigned __int16
0x18000a7ac  mov     ecx, 800008F0h; unsigned int
0x18000a7b1  mov     r9d, edi; unsigned int
0x18000a7b4  call    ?LogEvent@FREB_LOG_NT_EVENT_TABLE@@SAXKGQEAPEBGK@Z; FREB_LOG_NT_EVENT_TABLE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000a7b9  mov     rcx, [rbp+57h+var_10]
0x18000a7bd  xor     rcx, rsp; StackCookie
0x18000a7c0  call    __security_check_cookie
0x18000a7c5  lea     r11, [rsp+0D0h+var_s0]
0x18000a7cd  mov     rbx, [r11+10h]
0x18000a7d1  mov     rdi, [r11+20h]
0x18000a7d5  mov     rsp, r11
0x18000a7d8  pop     rbp
0x18000a7d9  retn
```
