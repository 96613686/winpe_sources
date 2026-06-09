# CProvisioningCommandsNode::DeleteChild(IConfigManager2URI *)

- ea: `0x1800093e0`
- end: `0x180009493`
- name: `?DeleteChild@CProvisioningCommandsNode@@UEAAJPEAUIConfigManager2URI@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(CProvisioningCommandsNode *__hidden this, struct IConfigManager2URI *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001090`
- `0x1800093e0`
- `0x18000ccc0`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::DeleteChild(
        CProvisioningCommandsNode *this,
        struct IConfigManager2URI *a2)
{
  int *v2; // rbx
  unsigned int v4; // edx
  int v6; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+38h] [rbp-40h] BYREF
  int *v8; // [rsp+58h] [rbp-20h]
  __int64 v9; // [rsp+60h] [rbp-18h]

  v2 = (int *)((char *)this + 44);
  if ( (unsigned int)dword_180014230 > 4 )
  {
    v6 = *v2;
    v9 = 4;
    v8 = &v6;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180014230, (unsigned __int8 *)byte_1800109D9, 0, 0, 3u, &v7);
  }
  if ( a2 )
  {
    v4 = 0;
    if ( *v2 != 1 && *v2 != 2 && (unsigned int)(*v2 - 5) >= 2 )
      return (unsigned int)-2046820335;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x1800093e0  mov     r11, rsp
0x1800093e3  mov     [r11+8], rbx
0x1800093e7  push    rdi
0x1800093e8  sub     rsp, 70h
0x1800093ec  mov     rax, cs:__security_cookie
0x1800093f3  xor     rax, rsp
0x1800093f6  mov     [rsp+78h+var_10], rax
0x1800093fb  mov     eax, cs:dword_180014230
0x180009401  lea     rbx, [rcx+2Ch]
0x180009405  mov     rdi, rdx
0x180009408  cmp     eax, 4
0x18000940b  jbe     short loc_18000944C
0x18000940d  mov     eax, [rbx]
0x18000940f  lea     rdx, byte_1800109D9
0x180009416  mov     [rsp+78h+var_48], eax
0x18000941a  lea     rcx, dword_180014230
0x180009421  lea     rax, [r11-48h]
0x180009425  mov     qword ptr [r11-18h], 4
0x18000942d  mov     [r11-20h], rax
0x180009431  xor     r9d, r9d
0x180009434  lea     rax, [r11-40h]
0x180009438  xor     r8d, r8d
0x18000943b  mov     [r11-50h], rax
0x18000943f  mov     [rsp+78h+var_58], 3
0x180009447  call    _tlgWriteTransfer_EventWriteTransfer
0x18000944c  test    rdi, rdi
0x18000944f  jnz     short loc_180009458
0x180009451  mov     edx, 80070057h
0x180009456  jmp     short loc_180009475
0x180009458  mov     ecx, [rbx]
0x18000945a  xor     edx, edx
0x18000945c  sub     ecx, 1
0x18000945f  jz      short loc_180009475
0x180009461  sub     ecx, 1
0x180009464  jz      short loc_180009475
0x180009466  sub     ecx, 3
0x180009469  jz      short loc_180009475
0x18000946b  cmp     ecx, 1
0x18000946e  jz      short loc_180009475
0x180009470  mov     edx, 86000011h
0x180009475  mov     eax, edx
0x180009477  mov     rcx, [rsp+78h+var_10]
0x18000947c  xor     rcx, rsp; StackCookie
0x18000947f  call    __security_check_cookie
0x180009484  mov     rbx, [rsp+78h+arg_0]
0x18000948c  add     rsp, 70h
0x180009490  pop     rdi
0x180009491  retn
```
