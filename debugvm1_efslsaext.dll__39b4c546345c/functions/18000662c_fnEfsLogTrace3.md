# fnEfsLogTrace3

- ea: `0x18000662c`
- end: `0x180006701`
- name: `fnEfsLogTrace3`
- size: `213`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008e54`
- `0x180009b2c`

## callees

- `0x18000662c`
- `0x180012040`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18000666d`
- `ntdll!EtwEventEnabled` at `0x18000666d`
- `ntdll!EtwEventWrite` at `0x1800066db`
- `ntdll!EtwEventWrite` at `0x1800066db`

## pseudocode

```c
__int64 __fastcall fnEfsLogTrace3(__int64 a1, __int64 a2, unsigned int a3, int a4, char a5, int a6, char a7)
{
  __int64 v7; // rbx
  _QWORD v9[2]; // [rsp+28h] [rbp-31h] BYREF
  _QWORD v10[10]; // [rsp+38h] [rbp-21h] BYREF
  unsigned int v11; // [rsp+B8h] [rbp+5Fh] BYREF
  int v12; // [rsp+C0h] [rbp+67h] BYREF

  v12 = a4;
  v11 = a3;
  v7 = g_hPublisher;
  LODWORD(v9[0]) = 11;
  if ( (unsigned __int8)EtwEventEnabled(g_hPublisher) )
  {
    v10[1] = 4;
    v10[0] = v9;
    v10[3] = 4;
    v10[2] = &a7;
    v10[5] = 4;
    v10[4] = &v11;
    v10[7] = 4;
    v10[6] = &v12;
    v10[9] = 4;
    v10[8] = &a5;
    ((void (__fastcall *)(__int64, __int64 *, __int64, _QWORD *, _QWORD, _QWORD))EtwEventWrite)(
      v7,
      EFS_API_ERROR_2,
      5,
      v10,
      v9[0],
      v9[1]);
  }
  return v11;
}

```

## disassembly

```asm
0x18000662c  mov     rax, rsp
0x18000662f  mov     [rax+8], rbx
0x180006633  mov     [rax+20h], r9d
0x180006637  mov     [rax+18h], r8d
0x18000663b  push    rbp
0x18000663c  lea     rbp, [rax-47h]
0x180006640  sub     rsp, 90h
0x180006647  mov     rax, cs:__security_cookie
0x18000664e  xor     rax, rsp
0x180006651  mov     [rbp+3Fh+var_10], rax
0x180006655  mov     rbx, cs:g_hPublisher
0x18000665c  lea     rdx, EFS_API_ERROR_2
0x180006663  mov     rcx, rbx
0x180006666  mov     [rbp+3Fh+var_70], 0Bh
0x18000666d  call    cs:__imp_EtwEventEnabled
0x180006673  test    al, al
0x180006675  jz      short loc_1800066E1
0x180006677  lea     rax, [rbp+3Fh+var_70]
0x18000667b  mov     [rbp+3Fh+var_58], 4
0x180006683  mov     [rbp+3Fh+var_60], rax
0x180006687  lea     r9, [rbp+3Fh+var_60]
0x18000668b  lea     rax, [rbp+3Fh+arg_30]
0x18000668f  mov     [rbp+3Fh+var_48], 4
0x180006697  mov     [rbp+3Fh+var_50], rax
0x18000669b  lea     rdx, EFS_API_ERROR_2
0x1800066a2  lea     rax, [rbp+3Fh+arg_10]
0x1800066a6  mov     [rbp+3Fh+var_38], 4
0x1800066ae  mov     [rbp+3Fh+var_40], rax
0x1800066b2  mov     r8d, 5
0x1800066b8  lea     rax, [rbp+3Fh+arg_18]
0x1800066bc  mov     [rbp+3Fh+var_28], 4
0x1800066c4  mov     [rbp+3Fh+var_30], rax
0x1800066c8  mov     rcx, rbx
0x1800066cb  lea     rax, [rbp+3Fh+arg_20]
0x1800066cf  mov     [rbp+3Fh+var_18], 4
0x1800066d7  mov     [rbp+3Fh+var_20], rax
0x1800066db  call    cs:__imp_EtwEventWrite
0x1800066e1  mov     eax, [rbp+3Fh+arg_10]
0x1800066e4  mov     rcx, [rbp+3Fh+var_10]
0x1800066e8  xor     rcx, rsp; StackCookie
0x1800066eb  call    __security_check_cookie
0x1800066f0  mov     rbx, [rsp+90h+arg_0]
0x1800066f8  add     rsp, 90h
0x1800066ff  pop     rbp
0x180006700  retn
```
