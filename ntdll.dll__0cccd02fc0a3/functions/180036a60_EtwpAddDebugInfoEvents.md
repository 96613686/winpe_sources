# EtwpAddDebugInfoEvents

- ea: `0x180036a60`
- end: `0x180036bab`
- name: `EtwpAddDebugInfoEvents`
- size: `331`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180035a70`
- `0x18007f29c`

## callees

- `0x1800355d8`
- `0x180036a60`
- `0x1800c8180`
- `0x1800ea5b0`
- `0x180162000`

## string_xrefs

- `0x180036ab2`: `\Registry\Machine\SOFTWARE\Microsoft\Windows NT\CurrentVersion`

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
0x180036a60  mov     [rsp+arg_10], rbx
0x180036a65  mov     [rsp+arg_18], rbp
0x180036a6a  push    rsi
0x180036a6b  push    rdi
0x180036a6c  push    r14
0x180036a6e  sub     rsp, 380h
0x180036a75  mov     rax, cs:__security_cookie
0x180036a7c  xor     rax, rsp
0x180036a7f  mov     [rsp+398h+var_28], rax
0x180036a87  mov     ebx, r8d
0x180036a8a  mov     [rsp+398h+var_358], 0
0x180036a92  sub     ebx, [rdx+30h]
0x180036a95  lea     r8, [rsp+398h+var_238]
0x180036a9d  mov     rbp, rdx
0x180036aa0  mov     rsi, rcx
0x180036aa3  mov     edi, 104h
0x180036aa8  lea     rdx, aBuildlabex; "BuildLabEx"
0x180036aaf  mov     r9d, edi
0x180036ab2  lea     rcx, aRegistryMachin_21; "\\Registry\\Machine\\SOFTWARE\\Microsof"...
0x180036ab9  call    EtwpQueryRegString
0x180036abe  test    eax, eax
0x180036ac0  js      short loc_180036B31
0x180036ac2  lea     r9, [rsp+398h+var_238]
0x180036aca  mov     [rsp+398h+var_378], 208h
0x180036ad2  xor     r8d, r8d
0x180036ad5  lea     rcx, [rsp+398h+var_348]
0x180036ada  mov     edx, edi
0x180036adc  call    RtlUnicodeToMultiByteN
0x180036ae1  test    eax, eax
0x180036ae3  js      short loc_180036B31
0x180036ae5  lea     rcx, [rsp+398h+var_348]
0x180036aea  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036aee  inc     rax
0x180036af1  cmp     byte ptr [rcx+rax], 0
0x180036af5  jnz     short loc_180036AEE
0x180036af7  lea     rcx, [rsp+398h+var_358]
0x180036afc  inc     eax
0x180036afe  mov     [rsp+398h+var_368], rcx
0x180036b03  lea     r8, [rbp+58h]
0x180036b07  mov     [rsp+398h+var_370], ebx
0x180036b0b  lea     r9, [rsp+398h+var_348]
0x180036b10  mov     rcx, rbp
0x180036b13  mov     [rsp+398h+var_378], eax
0x180036b17  mov     edx, 42h ; 'B'
0x180036b1c  call    EtwpAddEventToBuffer
0x180036b21  test    eax, eax
0x180036b23  js      short loc_180036B82
0x180036b25  mov     eax, [rsp+398h+var_358]
0x180036b29  add     eax, 7
0x180036b2c  and     eax, 0FFFFFFF8h
0x180036b2f  sub     ebx, eax
0x180036b31  add     rsi, 1C0h
0x180036b38  mov     rdi, [rsi]
0x180036b3b  jmp     short loc_180036B7D
0x180036b3d  mov     eax, [rdi+14h]
0x180036b40  lea     rcx, [rsp+398h+var_358]
0x180036b45  mov     [rsp+398h+var_368], rcx
0x180036b4a  lea     r9, [rdi+1Ch]
0x180036b4e  sub     eax, 4
0x180036b51  mov     [rsp+398h+var_370], ebx
0x180036b55  mov     rcx, rbp
0x180036b58  mov     [rsp+398h+var_378], eax
0x180036b5c  mov     edx, 40h ; '@'
0x180036b61  lea     r8, [rbp+58h]
0x180036b65  call    EtwpAddEventToBuffer
0x180036b6a  test    eax, eax
0x180036b6c  js      short loc_180036B82
0x180036b6e  mov     eax, [rsp+398h+var_358]
0x180036b72  mov     rdi, [rdi]
0x180036b75  add     eax, 7
0x180036b78  and     eax, 0FFFFFFF8h
0x180036b7b  sub     ebx, eax
0x180036b7d  cmp     rdi, rsi
0x180036b80  jnz     short loc_180036B3D
0x180036b82  mov     rcx, [rsp+398h+var_28]
0x180036b8a  xor     rcx, rsp; StackCookie
0x180036b8d  call    __security_check_cookie
0x180036b92  lea     r11, [rsp+398h+var_18]
0x180036b9a  mov     rbx, [r11+30h]
0x180036b9e  mov     rbp, [r11+38h]
0x180036ba2  mov     rsp, r11
0x180036ba5  pop     r14
0x180036ba7  pop     rdi
0x180036ba8  pop     rsi
0x180036ba9  retn
```
