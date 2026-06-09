# DevAuthProxy_HostDisconnect

- ea: `0x1800010e4`
- end: `0x180001184`
- name: `DevAuthProxy_HostDisconnect`
- size: `160`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000118c`
- `0x180001b10`
- `0x180001b9c`

## callees

- `0x1800010e4`
- `0x1800026a0`
- `0x1800067e0`

## pseudocode

```c
__int64 __fastcall DevAuthProxy_HostDisconnect(__int64 a1)
{
  __int64 v2; // rbx
  void *v3; // rcx
  bool v4; // zf
  void *v5; // rcx

  if ( !*(_BYTE *)a1 || *(_BYTE *)a1 == 1 )
  {
    v5 = *(void **)(a1 + 1232);
    if ( !v5 || (unsigned int)DevAuthFinishHash(v5) )
    {
      v4 = *(_BYTE *)(a1 + 8) == 2;
      *(_BYTE *)(a1 + 8) = 4;
      *(_DWORD *)(a1 + 12) = v4;
      return 1;
    }
    return 0;
  }
  if ( *(_BYTE *)a1 != 2 )
    return 0;
  v2 = a1 + 8;
  if ( a1 == -8 )
    return 0;
  v3 = *(void **)(a1 + 1104);
  if ( v3 )
  {
    if ( !(unsigned int)DevAuthFinishHash(v3) )
      return 0;
  }
  v4 = *(_BYTE *)v2 == 2;
  *(_BYTE *)v2 = 4;
  *(_DWORD *)(v2 + 4) = v4;
  return 1;
}

```

## disassembly

```asm
0x1800010e4  push    rbx
0x1800010e6  sub     rsp, 50h
0x1800010ea  mov     rax, cs:__security_cookie
0x1800010f1  xor     rax, rsp
0x1800010f4  mov     [rsp+58h+var_18], rax
0x1800010f9  movzx   edx, byte ptr [rcx]
0x1800010fc  mov     rbx, rcx
0x1800010ff  test    edx, edx
0x180001101  jz      short loc_18000113D
0x180001103  sub     edx, 1
0x180001106  jz      short loc_18000113D
0x180001108  cmp     edx, 1
0x18000110b  jnz     short loc_180001157
0x18000110d  add     rbx, 8
0x180001111  jz      short loc_180001157
0x180001113  mov     rcx, [rbx+448h]; P
0x18000111a  test    rcx, rcx
0x18000111d  jz      short loc_18000112D
0x18000111f  lea     rdx, [rsp+58h+var_38]
0x180001124  call    DevAuthFinishHash
0x180001129  test    eax, eax
0x18000112b  jz      short loc_180001157
0x18000112d  xor     eax, eax
0x18000112f  cmp     byte ptr [rbx], 2
0x180001132  mov     byte ptr [rbx], 4
0x180001135  setz    al
0x180001138  mov     [rbx+4], eax
0x18000113b  jmp     short loc_18000116B
0x18000113d  mov     rcx, [rcx+4D0h]; P
0x180001144  test    rcx, rcx
0x180001147  jz      short loc_18000115B
0x180001149  lea     rdx, [rsp+58h+var_38]
0x18000114e  call    DevAuthFinishHash
0x180001153  test    eax, eax
0x180001155  jnz     short loc_18000115B
0x180001157  xor     eax, eax
0x180001159  jmp     short loc_180001170
0x18000115b  xor     eax, eax
0x18000115d  cmp     byte ptr [rbx+8], 2
0x180001161  mov     byte ptr [rbx+8], 4
0x180001165  setz    al
0x180001168  mov     [rbx+0Ch], eax
0x18000116b  mov     eax, 1
0x180001170  mov     rcx, [rsp+58h+var_18]
0x180001175  xor     rcx, rsp; StackCookie
0x180001178  call    __security_check_cookie
0x18000117d  add     rsp, 50h
0x180001181  pop     rbx
0x180001182  retn
```
