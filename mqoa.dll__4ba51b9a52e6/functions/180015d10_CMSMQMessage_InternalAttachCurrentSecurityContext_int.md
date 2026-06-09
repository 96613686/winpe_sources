# CMSMQMessage::InternalAttachCurrentSecurityContext(int)

- ea: `0x180015d10`
- end: `0x180015db1`
- name: `?InternalAttachCurrentSecurityContext@CMSMQMessage@@IEAAJH@Z`
- size: `161`
- prototype: `__int64 __fastcall(CMSMQMessage *__hidden this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013eb0`
- `0x180013f10`

## callees

- `0x180015d10`
- `0x180029010`

## import_xrefs

- `mqrt!MQGetSecurityContext` at `0x180015d7c`
- `mqrt!MQGetSecurityContext` at `0x180015d7c`
- `mqrt!MQGetSecurityContextEx` at `0x180015d74`
- `mqrt!MQGetSecurityContextEx` at `0x180015d74`
- `mqrt!MQFreeSecurityContext` at `0x180015d94`
- `mqrt!MQFreeSecurityContext` at `0x180015d94`

## pseudocode

```c
__int64 __fastcall CMSMQMessage::InternalAttachCurrentSecurityContext(CMSMQMessage *this, int a2)
{
  char *v2; // rbx
  void *v5; // rsi
  __int64 v6; // rax
  DWORD v7; // eax
  HRESULT v8; // eax
  unsigned int v9; // ebx
  void *v10; // rcx
  HANDLE phSecurityContext; // [rsp+50h] [rbp+8h] BYREF

  v2 = (char *)this + 568;
  if ( (*(unsigned int (__fastcall **)(char *))(*((_QWORD *)this + 71) + 40LL))((char *)this + 568) )
    v5 = (void *)(*(__int64 (__fastcall **)(char *))(*(_QWORD *)v2 + 24LL))(v2);
  else
    v5 = 0;
  v6 = *(_QWORD *)v2;
  phSecurityContext = 0;
  v7 = (*(__int64 (__fastcall **)(char *))(v6 + 40))(v2);
  if ( a2 )
    v8 = MQGetSecurityContextEx(v5, v7, &phSecurityContext);
  else
    v8 = MQGetSecurityContext(v5, v7, &phSecurityContext);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v10 = (void *)*((_QWORD *)this + 333);
    if ( v10 )
      MQFreeSecurityContext(v10);
    *((_QWORD *)this + 333) = phSecurityContext;
  }
  return v9;
}

```

## disassembly

```asm
0x180015d10  push    rbx
0x180015d12  push    rbp
0x180015d13  push    rsi
0x180015d14  push    rdi
0x180015d15  sub     rsp, 28h
0x180015d19  lea     rbx, [rcx+238h]
0x180015d20  mov     rdi, rcx
0x180015d23  mov     rax, [rbx]
0x180015d26  mov     rcx, rbx
0x180015d29  mov     ebp, edx
0x180015d2b  mov     rax, [rax+28h]
0x180015d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d34  test    eax, eax
0x180015d36  jz      short loc_180015D4C
0x180015d38  mov     rax, [rbx]
0x180015d3b  mov     rcx, rbx
0x180015d3e  mov     rax, [rax+18h]
0x180015d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d47  mov     rsi, rax
0x180015d4a  jmp     short loc_180015D4E
0x180015d4c  xor     esi, esi
0x180015d4e  mov     rax, [rbx]
0x180015d51  mov     rcx, rbx
0x180015d54  mov     [rsp+48h+phSecurityContext], 0
0x180015d5d  mov     rax, [rax+28h]
0x180015d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d66  lea     r8, [rsp+48h+phSecurityContext]; phSecurityContext
0x180015d6b  mov     edx, eax; dwCertBufferLength
0x180015d6d  mov     rcx, rsi; lpCertBuffer
0x180015d70  test    ebp, ebp
0x180015d72  jz      short loc_180015D7C
0x180015d74  call    cs:__imp_MQGetSecurityContextEx
0x180015d7a  jmp     short loc_180015D82
0x180015d7c  call    cs:__imp_MQGetSecurityContext
0x180015d82  mov     ebx, eax
0x180015d84  test    eax, eax
0x180015d86  js      short loc_180015DA6
0x180015d88  mov     rcx, [rdi+0A68h]; hSecurityContext
0x180015d8f  test    rcx, rcx
0x180015d92  jz      short loc_180015D9A
0x180015d94  call    cs:__imp_MQFreeSecurityContext
0x180015d9a  mov     rax, [rsp+48h+phSecurityContext]
0x180015d9f  mov     [rdi+0A68h], rax
0x180015da6  mov     eax, ebx
0x180015da8  add     rsp, 28h
0x180015dac  pop     rdi
0x180015dad  pop     rsi
0x180015dae  pop     rbp
0x180015daf  pop     rbx
0x180015db0  retn
```
