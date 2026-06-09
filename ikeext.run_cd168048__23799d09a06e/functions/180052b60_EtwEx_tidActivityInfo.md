# EtwEx_tidActivityInfo

- ea: `0x180052b60`
- end: `0x180052c4a`
- name: `EtwEx_tidActivityInfo`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004cbf0`
- `0x18004cff4`

## callees

- `0x180050850`
- `0x180052b60`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180052c04`
- `ntdll!EtwEventWrite` at `0x180052c04`
- `ntdll!EtwEventActivityIdControl` at `0x180052bb9`
- `ntdll!EtwEventActivityIdControl` at `0x180052c26`
- `ntdll!EtwEventActivityIdControl` at `0x180052bb9`
- `ntdll!EtwEventActivityIdControl` at `0x180052c26`

## pseudocode

```c
__int64 __fastcall EtwEx_tidActivityInfo(__int64 a1, _WORD *a2, __int128 *a3)
{
  __int64 v3; // rdi
  __int128 *v5; // r9
  __int64 v6; // r8
  unsigned int v7; // edi
  int v9; // [rsp+20h] [rbp-30h] BYREF
  __int128 v10; // [rsp+28h] [rbp-28h] BYREF
  int *v11; // [rsp+38h] [rbp-18h]
  __int64 v12; // [rsp+40h] [rbp-10h]

  v3 = Microsoft_Windows_Networking_CorrelationHandle;
  v9 = 0;
  if ( *a2 == 0xEA61 )
  {
    v10 = 0;
    if ( a3 )
      v10 = *a3;
    EtwEventActivityIdControl(2, &v10);
  }
  if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
  {
    *((_QWORD *)&v10 + 1) = 16;
    *(_QWORD *)&v10 = &Microsoft_Windows_Networking_ProviderId;
    v5 = &v10;
    v12 = 4;
    v11 = &v9;
    v6 = 2;
  }
  else
  {
    v5 = 0;
    v6 = 0;
  }
  v7 = EtwEventWrite(v3, a2, v6, v5);
  if ( *a2 == 0xEA62 )
  {
    v10 = 0;
    EtwEventActivityIdControl(2, &v10);
  }
  return v7;
}

```

## disassembly

```asm
0x180052b60  mov     [rsp-8+arg_0], rbx
0x180052b65  mov     [rsp-8+arg_18], rdi
0x180052b6a  push    rbp
0x180052b6b  mov     rbp, rsp
0x180052b6e  sub     rsp, 50h
0x180052b72  mov     rax, cs:__security_cookie
0x180052b79  xor     rax, rsp
0x180052b7c  mov     [rbp+var_8], rax
0x180052b80  mov     rdi, cs:Microsoft_Windows_Networking_CorrelationHandle
0x180052b87  mov     eax, 0EA61h
0x180052b8c  mov     rbx, rdx
0x180052b8f  mov     [rbp+var_30], 0
0x180052b96  cmp     [rdx], ax
0x180052b99  jnz     short loc_180052BBF
0x180052b9b  xorps   xmm0, xmm0
0x180052b9e  movups  [rbp+var_28], xmm0
0x180052ba2  test    r8, r8
0x180052ba5  jz      short loc_180052BB0
0x180052ba7  movups  xmm0, xmmword ptr [r8]
0x180052bab  movdqu  [rbp+var_28], xmm0
0x180052bb0  lea     rdx, [rbp+var_28]
0x180052bb4  mov     ecx, 2
0x180052bb9  call    cs:__imp_EtwEventActivityIdControl
0x180052bbf  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x180052bc5  mov     rdx, rbx
0x180052bc8  mov     rcx, rdi
0x180052bcb  test    eax, eax
0x180052bcd  jz      short loc_180052BFE
0x180052bcf  lea     rax, Microsoft_Windows_Networking_ProviderId
0x180052bd6  mov     qword ptr [rbp+var_28+8], 10h
0x180052bde  mov     qword ptr [rbp+var_28], rax
0x180052be2  lea     r9, [rbp+var_28]
0x180052be6  lea     rax, [rbp+var_30]
0x180052bea  mov     [rbp+var_10], 4
0x180052bf2  mov     [rbp+var_18], rax
0x180052bf6  mov     r8d, 2
0x180052bfc  jmp     short loc_180052C04
0x180052bfe  xor     r9d, r9d
0x180052c01  xor     r8d, r8d
0x180052c04  call    cs:__imp_EtwEventWrite
0x180052c0a  mov     edi, eax
0x180052c0c  mov     eax, 0EA62h
0x180052c11  cmp     [rbx], ax
0x180052c14  jnz     short loc_180052C2C
0x180052c16  xorps   xmm0, xmm0
0x180052c19  lea     rdx, [rbp+var_28]
0x180052c1d  mov     ecx, 2
0x180052c22  movups  [rbp+var_28], xmm0
0x180052c26  call    cs:__imp_EtwEventActivityIdControl
0x180052c2c  mov     eax, edi
0x180052c2e  mov     rcx, [rbp+var_8]
0x180052c32  xor     rcx, rsp; StackCookie
0x180052c35  call    __security_check_cookie
0x180052c3a  mov     rbx, [rsp+50h+arg_0]
0x180052c3f  mov     rdi, [rsp+50h+arg_18]
0x180052c44  add     rsp, 50h
0x180052c48  pop     rbp
0x180052c49  retn
```
