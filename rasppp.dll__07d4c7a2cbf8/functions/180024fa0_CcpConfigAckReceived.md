# CcpConfigAckReceived

- ea: `0x180024fa0`
- end: `0x18002505e`
- name: `CcpConfigAckReceived`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001460`
- `0x180011038`
- `0x180024a6c`
- `0x180024fa0`
- `0x180032454`

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
0x180024fa0  push    rbx
0x180024fa2  push    rbp
0x180024fa3  push    rsi
0x180024fa4  push    rdi
0x180024fa5  sub     rsp, 248h
0x180024fac  mov     rax, cs:__security_cookie
0x180024fb3  xor     rax, rsp
0x180024fb6  mov     [rsp+268h+var_38], rax
0x180024fbe  movzx   edi, byte ptr [rdx+2]
0x180024fc2  lea     r8, [rcx+194h]
0x180024fc9  movzx   ebp, byte ptr [rdx+3]
0x180024fcd  mov     rsi, rdx
0x180024fd0  mov     r9d, [r8]
0x180024fd3  lea     rdx, [rsp+268h+var_248]
0x180024fd8  mov     rbx, rcx
0x180024fdb  mov     [rsp+268h+var_248], 1F4h
0x180024fe3  lea     rcx, [rsp+268h+Buf1]
0x180024fe8  call    CcpBuildOptionList
0x180024fed  test    eax, eax
0x180024fef  jnz     short loc_180025042
0x180024ff1  mov     ecx, edi
0x180024ff3  mov     edi, ebp
0x180024ff5  add     edi, 0FFFFFFFCh
0x180024ff8  shl     ecx, 8
0x180024ffb  add     edi, ecx
0x180024ffd  cmp     edi, [rsp+268h+var_248]
0x180025001  jnz     short loc_18002503D
0x180025003  mov     r8d, edi; Size
0x180025006  lea     rdx, [rsi+4]; Buf2
0x18002500a  lea     rcx, [rsp+268h+Buf1]; Buf1
0x18002500f  call    memcmp_0
0x180025014  test    eax, eax
0x180025016  jnz     short loc_18002503D
0x180025018  mov     rcx, [rbx]
0x18002501b  call    GetPCBPointerFromhPort
0x180025020  test    rax, rax
0x180025023  jz      short loc_180025039
0x180025025  test    dword ptr [rax+38h], 100000h
0x18002502c  jz      short loc_180025039
0x18002502e  test    edi, edi
0x180025030  jnz     short loc_180025039
0x180025032  and     dword ptr [rbx+1D0h], 0FFFFFFFEh
0x180025039  xor     eax, eax
0x18002503b  jmp     short loc_180025042
0x18002503d  mov     eax, 2D2h
0x180025042  mov     rcx, [rsp+268h+var_38]
0x18002504a  xor     rcx, rsp; StackCookie
0x18002504d  call    __security_check_cookie
0x180025052  add     rsp, 248h
0x180025059  pop     rdi
0x18002505a  pop     rsi
0x18002505b  pop     rbp
0x18002505c  pop     rbx
0x18002505d  retn
```
