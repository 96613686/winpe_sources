# fnEfsLogTrace0

- ea: `0x18000645c`
- end: `0x1800064ee`
- name: `fnEfsLogTrace0`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800068c8`

## callees

- `0x18000645c`
- `0x180012040`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18000648f`
- `ntdll!EtwEventEnabled` at `0x18000648f`
- `ntdll!EtwEventWrite` at `0x1800064d0`
- `ntdll!EtwEventWrite` at `0x1800064d0`

## pseudocode

```c
__int64 __fastcall fnEfsLogTrace0(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v4; // rdi
  __int64 result; // rax
  __int64 v7; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v8[4]; // [rsp+28h] [rbp-30h] BYREF
  int v9; // [rsp+78h] [rbp+20h] BYREF

  v9 = a4;
  v4 = g_hPublisher;
  LODWORD(v7) = 28;
  result = EtwEventEnabled(g_hPublisher);
  if ( (_BYTE)result )
  {
    v8[1] = 4;
    v8[0] = &v7;
    v8[3] = 4;
    v8[2] = &v9;
    return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD *, __int64))EtwEventWrite)(v4, a2, 2, v8, v7);
  }
  return result;
}

```

## disassembly

```asm
0x18000645c  mov     [rsp+arg_0], rbx
0x180006461  mov     [rsp+arg_18], r9d
0x180006466  push    rdi
0x180006467  sub     rsp, 50h
0x18000646b  mov     rax, cs:__security_cookie
0x180006472  xor     rax, rsp
0x180006475  mov     [rsp+58h+var_10], rax
0x18000647a  mov     rdi, cs:g_hPublisher
0x180006481  mov     rbx, rdx
0x180006484  mov     rcx, rdi
0x180006487  mov     dword ptr [rsp+58h+var_38], 1Ch
0x18000648f  call    cs:__imp_EtwEventEnabled
0x180006495  test    al, al
0x180006497  jz      short loc_1800064D6
0x180006499  lea     rax, [rsp+58h+var_38]
0x18000649e  mov     [rsp+58h+var_28], 4
0x1800064a7  mov     [rsp+58h+var_30], rax
0x1800064ac  lea     r9, [rsp+58h+var_30]
0x1800064b1  lea     rax, [rsp+58h+arg_18]
0x1800064b6  mov     [rsp+58h+var_18], 4
0x1800064bf  mov     r8d, 2
0x1800064c5  mov     [rsp+58h+var_20], rax
0x1800064ca  mov     rdx, rbx
0x1800064cd  mov     rcx, rdi
0x1800064d0  call    cs:__imp_EtwEventWrite
0x1800064d6  mov     rcx, [rsp+58h+var_10]
0x1800064db  xor     rcx, rsp; StackCookie
0x1800064de  call    __security_check_cookie
0x1800064e3  mov     rbx, [rsp+58h+arg_0]
0x1800064e8  add     rsp, 50h
0x1800064ec  pop     rdi
0x1800064ed  retn
```
