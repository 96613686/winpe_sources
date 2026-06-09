# CProvisioningCommandsNode::DeleteChild(IConfigManager2URI *)

- ea: `0x180008fc0`
- end: `0x180009072`
- name: `?DeleteChild@CProvisioningCommandsNode@@UEAAJPEAUIConfigManager2URI@@@Z`
- size: `178`
- prototype: `__int64 __fastcall(CProvisioningCommandsNode *__hidden this, struct IConfigManager2URI *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000108c`
- `0x180008fc0`
- `0x18000c600`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::DeleteChild(
        CProvisioningCommandsNode *this,
        struct IConfigManager2URI *a2)
{
  int *v2; // rbx
  unsigned int v4; // edx
  int v6; // [rsp+30h] [rbp-48h] BYREF
  int *v7; // [rsp+58h] [rbp-20h]
  __int64 v8; // [rsp+60h] [rbp-18h]

  v2 = (int *)((char *)this + 44);
  if ( (unsigned int)dword_180014230 > 4 )
  {
    v6 = *v2;
    v8 = 4;
    v7 = &v6;
    tlgWriteTransfer_EventWriteTransfer(&dword_180014230, byte_1800109D9, 0, 0);
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
0x180008fc0  mov     r11, rsp
0x180008fc3  mov     [r11+8], rbx
0x180008fc7  push    rdi
0x180008fc8  sub     rsp, 70h
0x180008fcc  mov     rax, cs:__security_cookie
0x180008fd3  xor     rax, rsp
0x180008fd6  mov     [rsp+78h+var_10], rax
0x180008fdb  mov     eax, cs:dword_180014230
0x180008fe1  lea     rbx, [rcx+2Ch]
0x180008fe5  mov     rdi, rdx
0x180008fe8  cmp     eax, 4
0x180008feb  jbe     short loc_18000902C
0x180008fed  mov     eax, [rbx]
0x180008fef  lea     rdx, byte_1800109D9
0x180008ff6  mov     [rsp+78h+var_48], eax
0x180008ffa  lea     rcx, dword_180014230
0x180009001  lea     rax, [r11-48h]
0x180009005  mov     qword ptr [r11-18h], 4
0x18000900d  mov     [r11-20h], rax
0x180009011  xor     r9d, r9d
0x180009014  lea     rax, [r11-40h]
0x180009018  xor     r8d, r8d
0x18000901b  mov     [r11-50h], rax
0x18000901f  mov     [rsp+78h+var_58], 3
0x180009027  call    _tlgWriteTransfer_EventWriteTransfer
0x18000902c  test    rdi, rdi
0x18000902f  jnz     short loc_180009038
0x180009031  mov     edx, 80070057h
0x180009036  jmp     short loc_180009055
0x180009038  mov     ecx, [rbx]
0x18000903a  xor     edx, edx
0x18000903c  sub     ecx, 1
0x18000903f  jz      short loc_180009055
0x180009041  sub     ecx, 1
0x180009044  jz      short loc_180009055
0x180009046  sub     ecx, 3
0x180009049  jz      short loc_180009055
0x18000904b  cmp     ecx, 1
0x18000904e  jz      short loc_180009055
0x180009050  mov     edx, 86000011h
0x180009055  mov     eax, edx
0x180009057  mov     rcx, [rsp+78h+var_10]
0x18000905c  xor     rcx, rsp; StackCookie
0x18000905f  call    __security_check_cookie
0x180009064  mov     rbx, [rsp+78h+arg_0]
0x18000906c  add     rsp, 70h
0x180009070  pop     rdi
0x180009071  retn
```
