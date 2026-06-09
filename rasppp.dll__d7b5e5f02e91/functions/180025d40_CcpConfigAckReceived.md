# CcpConfigAckReceived

- ea: `0x180025d40`
- end: `0x180025dff`
- name: `CcpConfigAckReceived`
- size: `191`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x1800115a0`
- `0x180025814`
- `0x180025d40`
- `0x180033a74`

## pseudocode

```c
__int64 __fastcall CcpConfigAckReceived(__int64 a1, unsigned __int8 *a2)
{
  int v2; // edi
  int v3; // ebp
  __int64 v5; // r9
  __int64 result; // rax
  unsigned int v8; // edi
  __int64 PCBPointerFromhPort; // rax
  int v10[4]; // [rsp+20h] [rbp-248h] BYREF
  _BYTE Buf1[512]; // [rsp+30h] [rbp-238h] BYREF

  v2 = a2[2];
  v3 = a2[3];
  v5 = *(unsigned int *)(a1 + 404);
  v10[0] = 500;
  result = CcpBuildOptionList(Buf1, v10, a1 + 404, v5);
  if ( !(_DWORD)result )
  {
    v8 = (v2 << 8) + v3 - 4;
    if ( v8 == v10[0] && !memcmp_0(Buf1, a2 + 4, v8) )
    {
      PCBPointerFromhPort = GetPCBPointerFromhPort(*(_QWORD *)a1);
      if ( PCBPointerFromhPort && (*(_DWORD *)(PCBPointerFromhPort + 56) & 0x100000) != 0 && !v8 )
        *(_DWORD *)(a1 + 464) &= ~1u;
      return 0;
    }
    else
    {
      return 722;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180025d40  push    rbx
0x180025d42  push    rbp
0x180025d43  push    rsi
0x180025d44  push    rdi
0x180025d45  sub     rsp, 248h
0x180025d4c  mov     rax, cs:__security_cookie
0x180025d53  xor     rax, rsp
0x180025d56  mov     [rsp+268h+var_38], rax
0x180025d5e  movzx   edi, byte ptr [rdx+2]
0x180025d62  lea     r8, [rcx+194h]
0x180025d69  movzx   ebp, byte ptr [rdx+3]
0x180025d6d  mov     rsi, rdx
0x180025d70  mov     r9d, [r8]
0x180025d73  lea     rdx, [rsp+268h+var_248]
0x180025d78  mov     rbx, rcx
0x180025d7b  mov     [rsp+268h+var_248], 1F4h
0x180025d83  lea     rcx, [rsp+268h+Buf1]
0x180025d88  call    CcpBuildOptionList
0x180025d8d  test    eax, eax
0x180025d8f  jnz     short loc_180025DE2
0x180025d91  mov     ecx, edi
0x180025d93  mov     edi, ebp
0x180025d95  add     edi, 0FFFFFFFCh
0x180025d98  shl     ecx, 8
0x180025d9b  add     edi, ecx
0x180025d9d  cmp     edi, [rsp+268h+var_248]
0x180025da1  jnz     short loc_180025DDD
0x180025da3  mov     r8d, edi; Size
0x180025da6  lea     rdx, [rsi+4]; Buf2
0x180025daa  lea     rcx, [rsp+268h+Buf1]; Buf1
0x180025daf  call    memcmp_0
0x180025db4  test    eax, eax
0x180025db6  jnz     short loc_180025DDD
0x180025db8  mov     rcx, [rbx]
0x180025dbb  call    GetPCBPointerFromhPort
0x180025dc0  test    rax, rax
0x180025dc3  jz      short loc_180025DD9
0x180025dc5  test    dword ptr [rax+38h], 100000h
0x180025dcc  jz      short loc_180025DD9
0x180025dce  test    edi, edi
0x180025dd0  jnz     short loc_180025DD9
0x180025dd2  and     dword ptr [rbx+1D0h], 0FFFFFFFEh
0x180025dd9  xor     eax, eax
0x180025ddb  jmp     short loc_180025DE2
0x180025ddd  mov     eax, 2D2h
0x180025de2  mov     rcx, [rsp+268h+var_38]
0x180025dea  xor     rcx, rsp; StackCookie
0x180025ded  call    __security_check_cookie
0x180025df2  add     rsp, 248h
0x180025df9  pop     rdi
0x180025dfa  pop     rsi
0x180025dfb  pop     rbp
0x180025dfc  pop     rbx
0x180025dfd  retn
```
