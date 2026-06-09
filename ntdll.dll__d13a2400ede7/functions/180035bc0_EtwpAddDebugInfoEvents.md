# EtwpAddDebugInfoEvents

- ea: `0x180035bc0`
- end: `0x180035d0b`
- name: `EtwpAddDebugInfoEvents`
- size: `331`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034bd0`
- `0x18003803c`

## callees

- `0x180035bc0`
- `0x1800362dc`
- `0x1800cbc30`
- `0x1800eac10`
- `0x180162810`

## string_xrefs

- `0x180035c12`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion`

## pseudocode

```c
__int64 __fastcall EtwpAddDebugInfoEvents(__int64 a1, __int64 a2, int a3)
{
  int v3; // ebx
  __int64 result; // rax
  __int64 v7; // rax
  __int64 **v8; // rsi
  __int64 *v9; // rdi
  _DWORD v10[4]; // [rsp+40h] [rbp-358h] BYREF
  _BYTE v11[272]; // [rsp+50h] [rbp-348h] BYREF
  _BYTE v12[528]; // [rsp+160h] [rbp-238h] BYREF

  v10[0] = 0;
  v3 = a3 - *(_DWORD *)(a2 + 48);
  result = EtwpQueryRegString(
             L"\\Registry\\Machine\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion",
             L"BuildLabEx",
             v12,
             260);
  if ( (int)result >= 0 )
  {
    result = RtlUnicodeToMultiByteN((unsigned int)v11, 260, 0, (unsigned int)v12, 520);
    if ( (int)result >= 0 )
    {
      v7 = -1;
      do
        ++v7;
      while ( v11[v7] );
      result = EtwpAddEventToBuffer(a2, 66, a2 + 88, v11, (int)v7 + 1, v3, v10);
      if ( (int)result < 0 )
        return result;
      result = (v10[0] + 7) & 0xFFFFFFF8;
      v3 -= result;
    }
  }
  v8 = (__int64 **)(a1 + 448);
  v9 = *v8;
  while ( v9 != (__int64 *)v8 )
  {
    result = EtwpAddEventToBuffer(a2, 64, a2 + 88, (char *)v9 + 28, *((_DWORD *)v9 + 5) - 4, v3, v10);
    if ( (int)result < 0 )
      break;
    v9 = (__int64 *)*v9;
    result = (v10[0] + 7) & 0xFFFFFFF8;
    v3 -= result;
  }
  return result;
}

```

## disassembly

```asm
0x180035bc0  mov     [rsp+arg_10], rbx
0x180035bc5  mov     [rsp+arg_18], rbp
0x180035bca  push    rsi
0x180035bcb  push    rdi
0x180035bcc  push    r14
0x180035bce  sub     rsp, 380h
0x180035bd5  mov     rax, cs:__security_cookie
0x180035bdc  xor     rax, rsp
0x180035bdf  mov     [rsp+398h+var_28], rax
0x180035be7  mov     ebx, r8d
0x180035bea  mov     [rsp+398h+var_358], 0
0x180035bf2  sub     ebx, [rdx+30h]
0x180035bf5  lea     r8, [rsp+398h+var_238]
0x180035bfd  mov     rbp, rdx
0x180035c00  mov     rsi, rcx
0x180035c03  mov     edi, 104h
0x180035c08  lea     rdx, aBuildlabex; "BuildLabEx"
0x180035c0f  mov     r9d, edi
0x180035c12  lea     rcx, aRegistryMachin_21; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180035c19  call    EtwpQueryRegString
0x180035c1e  test    eax, eax
0x180035c20  js      short loc_180035C91
0x180035c22  lea     r9, [rsp+398h+var_238]
0x180035c2a  mov     [rsp+398h+var_378], 208h
0x180035c32  xor     r8d, r8d
0x180035c35  lea     rcx, [rsp+398h+var_348]
0x180035c3a  mov     edx, edi
0x180035c3c  call    RtlUnicodeToMultiByteN
0x180035c41  test    eax, eax
0x180035c43  js      short loc_180035C91
0x180035c45  lea     rcx, [rsp+398h+var_348]
0x180035c4a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035c4e  inc     rax
0x180035c51  cmp     byte ptr [rcx+rax], 0
0x180035c55  jnz     short loc_180035C4E
0x180035c57  lea     rcx, [rsp+398h+var_358]
0x180035c5c  inc     eax
0x180035c5e  mov     [rsp+398h+var_368], rcx
0x180035c63  lea     r8, [rbp+58h]
0x180035c67  mov     [rsp+398h+var_370], ebx
0x180035c6b  lea     r9, [rsp+398h+var_348]
0x180035c70  mov     rcx, rbp
0x180035c73  mov     [rsp+398h+var_378], eax
0x180035c77  mov     edx, 42h ; 'B'
0x180035c7c  call    EtwpAddEventToBuffer
0x180035c81  test    eax, eax
0x180035c83  js      short loc_180035CE2
0x180035c85  mov     eax, [rsp+398h+var_358]
0x180035c89  add     eax, 7
0x180035c8c  and     eax, 0FFFFFFF8h
0x180035c8f  sub     ebx, eax
0x180035c91  add     rsi, 1C0h
0x180035c98  mov     rdi, [rsi]
0x180035c9b  jmp     short loc_180035CDD
0x180035c9d  mov     eax, [rdi+14h]
0x180035ca0  lea     rcx, [rsp+398h+var_358]
0x180035ca5  mov     [rsp+398h+var_368], rcx
0x180035caa  lea     r9, [rdi+1Ch]
0x180035cae  sub     eax, 4
0x180035cb1  mov     [rsp+398h+var_370], ebx
0x180035cb5  mov     rcx, rbp
0x180035cb8  mov     [rsp+398h+var_378], eax
0x180035cbc  mov     edx, 40h ; '@'
0x180035cc1  lea     r8, [rbp+58h]
0x180035cc5  call    EtwpAddEventToBuffer
0x180035cca  test    eax, eax
0x180035ccc  js      short loc_180035CE2
0x180035cce  mov     eax, [rsp+398h+var_358]
0x180035cd2  mov     rdi, [rdi]
0x180035cd5  add     eax, 7
0x180035cd8  and     eax, 0FFFFFFF8h
0x180035cdb  sub     ebx, eax
0x180035cdd  cmp     rdi, rsi
0x180035ce0  jnz     short loc_180035C9D
0x180035ce2  mov     rcx, [rsp+398h+var_28]
0x180035cea  xor     rcx, rsp; StackCookie
0x180035ced  call    __security_check_cookie
0x180035cf2  lea     r11, [rsp+398h+var_18]
0x180035cfa  mov     rbx, [r11+30h]
0x180035cfe  mov     rbp, [r11+38h]
0x180035d02  mov     rsp, r11
0x180035d05  pop     r14
0x180035d07  pop     rdi
0x180035d08  pop     rsi
0x180035d09  retn
```
