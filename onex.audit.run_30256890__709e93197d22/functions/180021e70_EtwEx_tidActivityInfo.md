# EtwEx_tidActivityInfo

- ea: `0x180021e70`
- end: `0x180021f53`
- name: `EtwEx_tidActivityInfo`
- size: `227`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013ee0`
- `0x18001c6c0`
- `0x180022384`

## callees

- `0x180020250`
- `0x180021e70`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180021ec2`
- `ntdll!EtwEventActivityIdControl` at `0x180021f2f`
- `ntdll!EtwEventActivityIdControl` at `0x180021ec2`
- `ntdll!EtwEventActivityIdControl` at `0x180021f2f`
- `ntdll!EtwEventWrite` at `0x180021f0d`
- `ntdll!EtwEventWrite` at `0x180021f0d`

## pseudocode

```c
__int64 __fastcall EtwEx_tidActivityInfo(__int64 a1, _WORD *a2, __int128 *a3, __int64 a4, char a5)
{
  __int64 v5; // rdi
  __int128 *v7; // r9
  __int64 v8; // r8
  unsigned int v9; // edi
  __int128 v11; // [rsp+20h] [rbp-30h] BYREF
  char *v12; // [rsp+30h] [rbp-20h]
  __int64 v13; // [rsp+38h] [rbp-18h]

  v5 = Microsoft_Windows_Networking_CorrelationHandle;
  if ( *a2 == 0xEA61 )
  {
    v11 = 0;
    if ( a3 )
      v11 = *a3;
    EtwEventActivityIdControl(2, &v11);
  }
  if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
  {
    *((_QWORD *)&v11 + 1) = 16;
    *(_QWORD *)&v11 = &Microsoft_Windows_Networking_ProviderId;
    v7 = &v11;
    v13 = 4;
    v12 = &a5;
    v8 = 2;
  }
  else
  {
    v7 = 0;
    v8 = 0;
  }
  v9 = EtwEventWrite(v5, a2, v8, v7, v11, *((_QWORD *)&v11 + 1), v12, v13);
  if ( *a2 == 0xEA62 )
  {
    v11 = 0;
    EtwEventActivityIdControl(2, &v11);
  }
  return v9;
}

```

## disassembly

```asm
0x180021e70  mov     [rsp-8+arg_0], rbx
0x180021e75  mov     [rsp-8+arg_18], rdi
0x180021e7a  push    rbp
0x180021e7b  mov     rbp, rsp
0x180021e7e  sub     rsp, 50h
0x180021e82  mov     rax, cs:__security_cookie
0x180021e89  xor     rax, rsp
0x180021e8c  mov     [rbp+var_10], rax
0x180021e90  mov     rdi, cs:Microsoft_Windows_Networking_CorrelationHandle
0x180021e97  mov     eax, 0EA61h
0x180021e9c  mov     rbx, rdx
0x180021e9f  cmp     [rdx], ax
0x180021ea2  jnz     short loc_180021EC8
0x180021ea4  xorps   xmm0, xmm0
0x180021ea7  movups  [rbp+var_30], xmm0
0x180021eab  test    r8, r8
0x180021eae  jz      short loc_180021EB9
0x180021eb0  movups  xmm0, xmmword ptr [r8]
0x180021eb4  movdqu  [rbp+var_30], xmm0
0x180021eb9  lea     rdx, [rbp+var_30]
0x180021ebd  mov     ecx, 2
0x180021ec2  call    cs:__imp_EtwEventActivityIdControl
0x180021ec8  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x180021ece  mov     rdx, rbx
0x180021ed1  mov     rcx, rdi
0x180021ed4  test    eax, eax
0x180021ed6  jz      short loc_180021F07
0x180021ed8  lea     rax, Microsoft_Windows_Networking_ProviderId
0x180021edf  mov     qword ptr [rbp+var_30+8], 10h
0x180021ee7  mov     qword ptr [rbp+var_30], rax
0x180021eeb  lea     r9, [rbp+var_30]
0x180021eef  lea     rax, [rbp+arg_20]
0x180021ef3  mov     [rbp+var_18], 4
0x180021efb  mov     [rbp+var_20], rax
0x180021eff  mov     r8d, 2
0x180021f05  jmp     short loc_180021F0D
0x180021f07  xor     r9d, r9d
0x180021f0a  xor     r8d, r8d
0x180021f0d  call    cs:__imp_EtwEventWrite
0x180021f13  mov     edi, eax
0x180021f15  mov     eax, 0EA62h
0x180021f1a  cmp     [rbx], ax
0x180021f1d  jnz     short loc_180021F35
0x180021f1f  xorps   xmm0, xmm0
0x180021f22  lea     rdx, [rbp+var_30]
0x180021f26  mov     ecx, 2
0x180021f2b  movups  [rbp+var_30], xmm0
0x180021f2f  call    cs:__imp_EtwEventActivityIdControl
0x180021f35  mov     eax, edi
0x180021f37  mov     rcx, [rbp+var_10]
0x180021f3b  xor     rcx, rsp; StackCookie
0x180021f3e  call    __security_check_cookie
0x180021f43  mov     rbx, [rsp+50h+arg_0]
0x180021f48  mov     rdi, [rsp+50h+arg_18]
0x180021f4d  add     rsp, 50h
0x180021f51  pop     rbp
0x180021f52  retn
```
