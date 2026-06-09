# CContext::ETWWriteNULLCommandList(void)

- ea: `0x1800a2098`
- end: `0x1800a2105`
- name: `?ETWWriteNULLCommandList@CContext@@QEAAXXZ`
- size: `109`
- prototype: `void __fastcall(CContext *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180115d10`
- `0x180165b70`
- `0x180166770`
- `0x1801675f0`
- `0x1801bada0`

## callees

- `0x1800a9d20`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800a20ed`
- `ntdll!EtwEventWrite` at `0x1800a20ed`

## pseudocode

```c
void __fastcall CContext::ETWWriteNULLCommandList(CContext *this)
{
  __int64 v1; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v2[4]; // [rsp+28h] [rbp-30h] BYREF

  v2[1] = 8;
  v2[0] = (char *)this + 168;
  v1 = 0;
  v2[2] = &v1;
  v2[3] = 8;
  EtwEventWrite(Direct3D11EtwProviderGuid_Context, &EventD3D11CreateCommandList, 2, v2);
}

```

## disassembly

```asm
0x1800a2098  mov     r11, rsp
0x1800a209b  sub     rsp, 58h
0x1800a209f  mov     rax, cs:__security_cookie
0x1800a20a6  xor     rax, rsp
0x1800a20a9  mov     [rsp+58h+var_10], rax
0x1800a20ae  lea     rax, [rcx+0A8h]
0x1800a20b5  mov     qword ptr [r11-28h], 8
0x1800a20bd  xor     ecx, ecx
0x1800a20bf  mov     [r11-30h], rax
0x1800a20c3  mov     [r11-38h], rcx
0x1800a20c7  lea     rax, [r11-38h]
0x1800a20cb  lea     r9, [r11-30h]
0x1800a20cf  mov     [r11-20h], rax
0x1800a20d3  lea     rdx, EventD3D11CreateCommandList
0x1800a20da  mov     qword ptr [r11-18h], 8
0x1800a20e2  lea     r8d, [rcx+2]
0x1800a20e6  mov     rcx, cs:Direct3D11EtwProviderGuid_Context
0x1800a20ed  call    cs:__imp_EtwEventWrite
0x1800a20f3  mov     rcx, [rsp+58h+var_10]
0x1800a20f8  xor     rcx, rsp; StackCookie
0x1800a20fb  call    __security_check_cookie
0x1800a2100  add     rsp, 58h
0x1800a2104  retn
```
