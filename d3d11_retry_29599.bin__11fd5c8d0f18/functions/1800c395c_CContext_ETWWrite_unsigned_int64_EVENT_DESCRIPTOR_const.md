# CContext::ETWWrite(unsigned __int64,_EVENT_DESCRIPTOR const *)

- ea: `0x1800c395c`
- end: `0x1800c3a21`
- name: `?ETWWrite@CContext@@QEAAX_KPEBU_EVENT_DESCRIPTOR@@@Z`
- size: `197`
- prototype: `void __fastcall(CContext *__hidden this, unsigned __int64, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18005e4f0`
- `0x180081150`
- `0x1800a3aa4`
- `0x1800c38b8`

## callees

- `0x1800a22f0`
- `0x1800a9d20`
- `0x1800c395c`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800c39fa`
- `ntdll!EtwEventWrite` at `0x1800c39fa`

## pseudocode

```c
void __fastcall CContext::ETWWrite(RTL_SRWLOCK *this, __int64 a2, const struct _EVENT_DESCRIPTOR *a3)
{
  __int64 *v3; // rsi
  int v5; // edi
  _QWORD v7[8]; // [rsp+20h] [rbp-50h] BYREF

  v3 = (__int64 *)&this[21];
  v5 = a2;
  if ( (a2 & 2) != 0 )
    CPrivateDataImpl<ID3D11DeviceChild>::ETWReportName(this, a2, *v3);
  if ( (*(_QWORD *)&v5 & 0x40000LL) != 0 )
  {
    v7[0] = (char *)this[20].Ptr + 1240;
    v7[1] = 8;
    v7[4] = this + 464;
    v7[2] = v3;
    v7[6] = (char *)this + 3716;
    v7[3] = 8;
    v7[5] = 4;
    v7[7] = 4;
    EtwEventWrite(Direct3D11EtwProviderGuid_Context, a3, 4, v7);
  }
}

```

## disassembly

```asm
0x1800c395c  mov     [rsp-18h+arg_8], rbx
0x1800c3961  mov     [rsp-18h+arg_18], rsi
0x1800c3966  push    rbp
0x1800c3967  push    rdi
0x1800c3968  push    r14
0x1800c396a  mov     rbp, rsp
0x1800c396d  sub     rsp, 70h
0x1800c3971  mov     rax, cs:__security_cookie
0x1800c3978  xor     rax, rsp
0x1800c397b  mov     [rbp+var_10], rax
0x1800c397f  lea     rsi, [rcx+0A8h]
0x1800c3986  mov     r14, r8
0x1800c3989  mov     rdi, rdx
0x1800c398c  mov     rbx, rcx
0x1800c398f  test    dl, 2
0x1800c3992  jz      short loc_1800C399C
0x1800c3994  mov     r8, [rsi]
0x1800c3997  call    ?ETWReportName@?$CPrivateDataImpl@UID3D11DeviceChild@@@@QEAAXPEBU_EVENT_DESCRIPTOR@@PEBX@Z; CPrivateDataImpl<ID3D11DeviceChild>::ETWReportName(_EVENT_DESCRIPTOR const *,void const *)
0x1800c399c  bt      rdi, 12h
0x1800c39a1  jnb     short loc_1800C3A00
0x1800c39a3  mov     rax, [rbx+0A0h]
0x1800c39aa  lea     r9, [rbp+var_50]
0x1800c39ae  mov     rcx, cs:Direct3D11EtwProviderGuid_Context
0x1800c39b5  add     rax, 4D8h
0x1800c39bb  mov     [rbp+var_50], rax
0x1800c39bf  mov     r8d, 4
0x1800c39c5  lea     rax, [rbx+0E80h]
0x1800c39cc  mov     [rbp+var_48], 8
0x1800c39d4  mov     [rbp+var_30], rax
0x1800c39d8  mov     rdx, r14
0x1800c39db  lea     rax, [rbx+0E84h]
0x1800c39e2  mov     [rbp+var_40], rsi
0x1800c39e6  mov     [rbp+var_20], rax
0x1800c39ea  mov     [rbp+var_38], 8
0x1800c39f2  mov     [rbp+var_28], r8
0x1800c39f6  mov     [rbp+var_18], r8
0x1800c39fa  call    cs:__imp_EtwEventWrite
0x1800c3a00  mov     rcx, [rbp+var_10]
0x1800c3a04  xor     rcx, rsp; StackCookie
0x1800c3a07  call    __security_check_cookie
0x1800c3a0c  lea     r11, [rsp+70h+var_s0]
0x1800c3a11  mov     rbx, [r11+28h]
0x1800c3a15  mov     rsi, [r11+38h]
0x1800c3a19  mov     rsp, r11
0x1800c3a1c  pop     r14
0x1800c3a1e  pop     rdi
0x1800c3a1f  pop     rbp
0x1800c3a20  retn
```
