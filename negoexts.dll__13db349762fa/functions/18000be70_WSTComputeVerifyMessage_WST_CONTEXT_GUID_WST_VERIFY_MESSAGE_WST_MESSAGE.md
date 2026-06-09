# WSTComputeVerifyMessage(_WST_CONTEXT *,_GUID *,_WST_VERIFY_MESSAGE *,_WST_MESSAGE * *)

- ea: `0x18000be70`
- end: `0x18000bf16`
- name: `?WSTComputeVerifyMessage@@YAJPEAU_WST_CONTEXT@@PEAU_GUID@@PEAU_WST_VERIFY_MESSAGE@@PEAPEAU_WST_MESSAGE@@@Z`
- size: `166`
- prototype: `int __fastcall(struct _WST_CONTEXT *, struct _GUID *, struct _WST_VERIFY_MESSAGE *, struct _WST_MESSAGE **)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800070d0`
- `0x180008e60`
- `0x18001a3b4`

## callees

- `0x18000be70`
- `0x18000bf1c`
- `0x18000c528`

## pseudocode

```c
int __fastcall WSTComputeVerifyMessage(
        struct _WST_CONTEXT *a1,
        struct _GUID *a2,
        struct _WST_VERIFY_MESSAGE *a3,
        struct _WST_MESSAGE **a4)
{
  struct _WST_ACTIVE_ENGINE_CONTEXT *v8; // rax
  int result; // eax
  struct basessp::_WST_ENCRYPTION_KEY *v10; // rbx
  struct basessp::_WST_ENCRYPTION_KEY *v11; // rsi
  struct basessp::_WST_ENCRYPTION_KEY *v12; // rdi

  v8 = WSTGetActiveContextByAuthScheme(a1, (struct _GUID *)((char *)a1 + 228));
  if ( !v8 )
    return -2146893052;
  v10 = (struct _WST_ACTIVE_ENGINE_CONTEXT *)((char *)v8 + 112);
  if ( a3 && *((_DWORD *)v8 + 30) )
  {
    v11 = (struct _WST_ACTIVE_ENGINE_CONTEXT *)((char *)v8 + 112);
    v12 = (struct _WST_ACTIVE_ENGINE_CONTEXT *)((char *)v8 + 88);
  }
  else
  {
    v12 = (struct _WST_ACTIVE_ENGINE_CONTEXT *)((char *)v8 + 88);
    v11 = (struct _WST_ACTIVE_ENGINE_CONTEXT *)((char *)v8 + 88);
  }
  result = WSTComputeVerifyMessageByKey(v11, a1, a2, a3, a4);
  if ( a3 && result == -2146893041 )
  {
    if ( v11 != v12 )
      v10 = v12;
    if ( *((_DWORD *)v10 + 2) )
      return WSTComputeVerifyMessageByKey(v10, a1, a2, a3, a4);
  }
  return result;
}

```

## disassembly

```asm
0x18000be70  push    rbx
0x18000be72  push    rbp
0x18000be73  push    rsi
0x18000be74  push    rdi
0x18000be75  push    r12
0x18000be77  push    r14
0x18000be79  push    r15
0x18000be7b  sub     rsp, 30h
0x18000be7f  mov     r12, rdx
0x18000be82  mov     r15, r9
0x18000be85  lea     rdx, [rcx+0E4h]; struct _GUID *
0x18000be8c  mov     rbp, r8
0x18000be8f  mov     r14, rcx
0x18000be92  call    ?WSTGetActiveContextByAuthScheme@@YAPEAU_WST_ACTIVE_ENGINE_CONTEXT@@PEAU_WST_CONTEXT@@PEAU_GUID@@@Z; WSTGetActiveContextByAuthScheme(_WST_CONTEXT *,_GUID *)
0x18000be97  test    rax, rax
0x18000be9a  jnz     short loc_18000BEA3
0x18000be9c  mov     eax, 80090304h
0x18000bea1  jmp     short loc_18000BF07
0x18000bea3  lea     rbx, [rax+70h]
0x18000bea7  test    rbp, rbp
0x18000beaa  jz      short loc_18000BEBB
0x18000beac  cmp     dword ptr [rbx+8], 0
0x18000beb0  jz      short loc_18000BEBB
0x18000beb2  mov     rsi, rbx
0x18000beb5  lea     rdi, [rax+58h]
0x18000beb9  jmp     short loc_18000BEC2
0x18000bebb  lea     rdi, [rax+58h]
0x18000bebf  mov     rsi, rdi
0x18000bec2  mov     r9, rbp; struct _WST_VERIFY_MESSAGE *
0x18000bec5  mov     [rsp+68h+var_48], r15; struct _WST_MESSAGE **
0x18000beca  mov     r8, r12; struct _GUID *
0x18000becd  mov     rdx, r14; struct _WST_CONTEXT *
0x18000bed0  mov     rcx, rsi; struct basessp::_WST_ENCRYPTION_KEY *
0x18000bed3  call    ?WSTComputeVerifyMessageByKey@@YAJPEAU_WST_ENCRYPTION_KEY@basessp@@PEAU_WST_CONTEXT@@PEAU_GUID@@PEAU_WST_VERIFY_MESSAGE@@PEAPEAU_WST_MESSAGE@@@Z; WSTComputeVerifyMessageByKey(basessp::_WST_ENCRYPTION_KEY *,_WST_CONTEXT *,_GUID *,_WST_VERIFY_MESSAGE *,_WST_MESSAGE * *)
0x18000bed8  test    rbp, rbp
0x18000bedb  jz      short loc_18000BF07
0x18000bedd  cmp     eax, 8009030Fh
0x18000bee2  jnz     short loc_18000BF07
0x18000bee4  cmp     rsi, rdi
0x18000bee7  cmovnz  rbx, rdi
0x18000beeb  cmp     dword ptr [rbx+8], 0
0x18000beef  jz      short loc_18000BF07
0x18000bef1  mov     r9, rbp; struct _WST_VERIFY_MESSAGE *
0x18000bef4  mov     [rsp+68h+var_48], r15; struct _WST_MESSAGE **
0x18000bef9  mov     r8, r12; struct _GUID *
0x18000befc  mov     rdx, r14; struct _WST_CONTEXT *
0x18000beff  mov     rcx, rbx; struct basessp::_WST_ENCRYPTION_KEY *
0x18000bf02  call    ?WSTComputeVerifyMessageByKey@@YAJPEAU_WST_ENCRYPTION_KEY@basessp@@PEAU_WST_CONTEXT@@PEAU_GUID@@PEAU_WST_VERIFY_MESSAGE@@PEAPEAU_WST_MESSAGE@@@Z; WSTComputeVerifyMessageByKey(basessp::_WST_ENCRYPTION_KEY *,_WST_CONTEXT *,_GUID *,_WST_VERIFY_MESSAGE *,_WST_MESSAGE * *)
0x18000bf07  add     rsp, 30h
0x18000bf0b  pop     r15
0x18000bf0d  pop     r14
0x18000bf0f  pop     r12
0x18000bf11  pop     rdi
0x18000bf12  pop     rsi
0x18000bf13  pop     rbp
0x18000bf14  pop     rbx
0x18000bf15  retn
```
