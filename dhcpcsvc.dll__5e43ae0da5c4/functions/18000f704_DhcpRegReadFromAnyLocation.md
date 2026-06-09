# DhcpRegReadFromAnyLocation

- ea: `0x18000f704`
- end: `0x18000f7cd`
- name: `DhcpRegReadFromAnyLocation`
- size: `201`
- prototype: `__int64 __fastcall(int, int, int, int, LPDWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800088d0`

## callees

- `0x18000f704`
- `0x18000f7d4`
- `0x1800127f0`
- `0x180012a00`

## string_xrefs

- `0x18000f71d`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces\?\DhcpRequestOptions`

## pseudocode

```c
__int64 __fastcall DhcpRegReadFromAnyLocation(__int64 a1, void *a2, BYTE **a3, DWORD *a4, LPDWORD a5)
{
  const wchar_t *v5; // rsi
  unsigned int v9; // edi
  __int64 v10; // rbx

  v5 = L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces\\?\\DhcpRequestOptions";
  *a4 = 0;
  *a3 = 0;
  *a5 = 0;
  v9 = 2;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_S(1028, 18, WPP_94d5010c5674399d06148e3a91870046_Traceguids, a2);
  while ( 1 )
  {
    v10 = -1;
    do
      ++v10;
    while ( v5[v10] );
    if ( !v10 )
      break;
    if ( !(unsigned int)DhcpRegReadFromLocation(v5, a2, a3, a4, a5) )
    {
      v9 = 0;
      break;
    }
    v5 += v10 + 1;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 19, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18000f704  push    rbx
0x18000f706  push    rbp
0x18000f707  push    rsi
0x18000f708  push    rdi
0x18000f709  push    r12
0x18000f70b  push    r13
0x18000f70d  push    r14
0x18000f70f  push    r15
0x18000f711  sub     rsp, 38h
0x18000f715  mov     r12, [rsp+78h+arg_20]
0x18000f71d  lea     rsi, Src; "System\\CurrentControlSet\\Services\\Tc"...
0x18000f724  xor     r13d, r13d
0x18000f727  mov     r14, r9
0x18000f72a  mov     [r9], r13d
0x18000f72d  mov     r15, r8
0x18000f730  mov     rbp, rdx
0x18000f733  mov     [r8], r13
0x18000f736  mov     [r12], r13d
0x18000f73a  mov     edi, 2
0x18000f73f  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000f746  jz      short loc_18000F75F
0x18000f748  lea     edx, [rdi+10h]
0x18000f74b  mov     ecx, 404h
0x18000f750  mov     r9, rbp
0x18000f753  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000f75a  call    WPP_SF_S
0x18000f75f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000f763  inc     rbx
0x18000f766  cmp     [rsi+rbx*2], r13w
0x18000f76b  jnz     short loc_18000F763
0x18000f76d  test    rbx, rbx
0x18000f770  jz      short loc_18000F798
0x18000f772  mov     r9, r14
0x18000f775  mov     [rsp+78h+var_58], r12; LPDWORD
0x18000f77a  mov     r8, r15
0x18000f77d  mov     rdx, rbp
0x18000f780  mov     rcx, rsi; Src
0x18000f783  call    DhcpRegReadFromLocation
0x18000f788  test    eax, eax
0x18000f78a  jz      short loc_18000F795
0x18000f78c  lea     rsi, [rsi+rbx*2]
0x18000f790  add     rsi, rdi
0x18000f793  jmp     short loc_18000F75F
0x18000f795  mov     edi, r13d
0x18000f798  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000f79f  jz      short loc_18000F7BA
0x18000f7a1  mov     edx, 13h
0x18000f7a6  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000f7ad  mov     ecx, 404h
0x18000f7b2  mov     r9d, edi
0x18000f7b5  call    WPP_SF_d
0x18000f7ba  mov     eax, edi
0x18000f7bc  add     rsp, 38h
0x18000f7c0  pop     r15
0x18000f7c2  pop     r14
0x18000f7c4  pop     r13
0x18000f7c6  pop     r12
0x18000f7c8  pop     rdi
0x18000f7c9  pop     rsi
0x18000f7ca  pop     rbp
0x18000f7cb  pop     rbx
0x18000f7cc  retn
```
