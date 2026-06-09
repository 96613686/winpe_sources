# fnEfsLogTrace0

- ea: `0x180003714`
- end: `0x1800037b0`
- name: `fnEfsLogTrace0`
- size: `156`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180002fb0`
- `0x180006bf0`

## callees

- `0x180003714`
- `0x18000d1c0`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18000378b`
- `ntdll!EtwEventWrite` at `0x18000378b`
- `ntdll!EtwEventEnabled` at `0x180003744`
- `ntdll!EtwEventEnabled` at `0x180003744`

## pseudocode

```c
__int64 __fastcall fnEfsLogTrace0(__int64 a1, __int64 a2, int a3, int a4)
{
  __int64 v4; // rdi
  __int64 result; // rax
  _QWORD v7[4]; // [rsp+20h] [rbp-38h] BYREF
  int v8; // [rsp+70h] [rbp+18h] BYREF
  int v9; // [rsp+78h] [rbp+20h] BYREF

  v9 = a4;
  v8 = a3;
  v4 = g_hPublisher;
  result = EtwEventEnabled(g_hPublisher);
  if ( (_BYTE)result )
  {
    v7[1] = 4;
    v7[0] = &v8;
    v7[3] = 4;
    v7[2] = &v9;
    return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD *))EtwEventWrite)(v4, a2, 2, v7);
  }
  return result;
}

```

## disassembly

```asm
0x180003714  mov     [rsp+arg_0], rbx
0x180003719  mov     [rsp+arg_18], r9d
0x18000371e  mov     [rsp+arg_10], r8d
0x180003723  push    rdi
0x180003724  sub     rsp, 50h
0x180003728  mov     rax, cs:__security_cookie
0x18000372f  xor     rax, rsp
0x180003732  mov     [rsp+58h+var_18], rax
0x180003737  mov     rdi, cs:g_hPublisher
0x18000373e  mov     rbx, rdx
0x180003741  mov     rcx, rdi
0x180003744  call    cs:__imp_EtwEventEnabled
0x18000374b  nop     dword ptr [rax+rax+00h]
0x180003750  test    al, al
0x180003752  jz      short loc_180003797
0x180003754  lea     rax, [rsp+58h+arg_10]
0x180003759  mov     [rsp+58h+var_30], 4
0x180003762  mov     [rsp+58h+var_38], rax
0x180003767  lea     r9, [rsp+58h+var_38]
0x18000376c  lea     rax, [rsp+58h+arg_18]
0x180003771  mov     [rsp+58h+var_20], 4
0x18000377a  mov     r8d, 2
0x180003780  mov     [rsp+58h+var_28], rax
0x180003785  mov     rdx, rbx
0x180003788  mov     rcx, rdi
0x18000378b  call    cs:__imp_EtwEventWrite
0x180003792  nop     dword ptr [rax+rax+00h]
0x180003797  mov     rcx, [rsp+58h+var_18]
0x18000379c  xor     rcx, rsp; StackCookie
0x18000379f  call    __security_check_cookie
0x1800037a4  mov     rbx, [rsp+58h+arg_0]
0x1800037a9  add     rsp, 50h
0x1800037ad  pop     rdi
0x1800037ae  retn
```
