# DiscpAddRemoveiSNSServerForHBA

- ea: `0x180004cf8`
- end: `0x180004e7c`
- name: `DiscpAddRemoveiSNSServerForHBA`
- size: `388`
- prototype: `__int64 __fastcall(__int64, __int64, char)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180004380`
- `0x180004a50`

## callees

- `0x180001410`
- `0x180001cfe`
- `0x180004cf8`
- `0x180006998`

## import_xrefs

- `ISCSIUM!DiscpCopyToCountedString` at `0x180004dab`
- `ISCSIUM!DiscpCopyToCountedString` at `0x180004dab`
- `ISCSIUM!DiscpExecuteMethod` at `0x180004e19`
- `ISCSIUM!DiscpExecuteMethod` at `0x180004e19`
- `ISCSIUM!DiscpFreeMemory` at `0x180004e30`
- `ISCSIUM!DiscpFreeMemory` at `0x180004e4a`
- `ISCSIUM!DiscpFreeMemory` at `0x180004e30`
- `ISCSIUM!DiscpFreeMemory` at `0x180004e4a`

## pseudocode

```c
__int64 __fastcall DiscpAddRemoveiSNSServerForHBA(__int64 a1, __int64 a2, char a3)
{
  unsigned int InitiatorInstanceList; // esi
  unsigned int v7; // r14d
  __int64 *v8; // rbx
  unsigned int v9; // edi
  int v10; // r15d
  __int64 v11; // r13
  unsigned int v13; // [rsp+50h] [rbp-B0h] BYREF
  int v14; // [rsp+54h] [rbp-ACh] BYREF
  __int64 *v15; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v18[448]; // [rsp+70h] [rbp-90h] BYREF

  v17 = a1;
  v13 = 0;
  v15 = 0;
  memset_0(v18, 0, sizeof(v18));
  v16 = 0;
  v14 = 0;
  if ( a1 )
  {
    v8 = &v17;
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
    v7 = 1;
    InitiatorInstanceList = 0;
  }
  else
  {
    InitiatorInstanceList = DiscpGetInitiatorInstanceList(0, &v13, &v15);
    if ( InitiatorInstanceList )
      return InitiatorInstanceList;
    v7 = v13;
    v8 = v15;
  }
  DiscpCopyToCountedString(v18, a2, 223);
  v9 = 0;
  if ( v7 )
  {
    v10 = -(a3 != 0);
    do
    {
      v11 = v8[v9];
      v14 = 4;
      v16 = 0;
      DiscpExecuteMethod(
        MSiSCSI_Operations_GUID,
        0,
        *(_QWORD *)(v11 + 40),
        (unsigned int)(v10 + 102),
        v18,
        448,
        &v16,
        &v14,
        4);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 16), 0xFFFFFFFF) == 1 )
        DiscpFreeMemory(v11);
      ++v9;
    }
    while ( v9 < v7 );
  }
  if ( v8 != &v17 )
    DiscpFreeMemory(v8);
  return InitiatorInstanceList;
}

```

## disassembly

```asm
0x180004cf8  mov     [rsp-8+arg_10], rbx
0x180004cfd  push    rbp
0x180004cfe  push    rsi
0x180004cff  push    rdi
0x180004d00  push    r12
0x180004d02  push    r13
0x180004d04  push    r14
0x180004d06  push    r15
0x180004d08  lea     rbp, [rsp-140h]
0x180004d10  sub     rsp, 240h
0x180004d17  mov     rax, cs:__security_cookie
0x180004d1e  xor     rax, rsp
0x180004d21  mov     [rbp+170h+var_40], rax
0x180004d28  mov     r15b, r8b
0x180004d2b  mov     [rsp+270h+var_208], rcx
0x180004d30  mov     r12, rdx
0x180004d33  mov     rdi, rcx
0x180004d36  xor     r13d, r13d
0x180004d39  lea     rcx, [rsp+270h+var_200]; void *
0x180004d3e  xor     edx, edx; Val
0x180004d40  mov     [rsp+270h+var_220], r13d
0x180004d45  mov     r8d, 1C0h; Size
0x180004d4b  mov     [rsp+270h+var_218], r13
0x180004d50  call    memset_0
0x180004d55  mov     [rsp+270h+var_210], r13
0x180004d5a  mov     [rsp+270h+var_21C], r13d
0x180004d5f  test    rdi, rdi
0x180004d62  jnz     short loc_180004D8B
0x180004d64  lea     r8, [rsp+270h+var_218]
0x180004d69  xor     ecx, ecx
0x180004d6b  lea     rdx, [rsp+270h+var_220]
0x180004d70  call    DiscpGetInitiatorInstanceList
0x180004d75  mov     esi, eax
0x180004d77  test    eax, eax
0x180004d79  jnz     loc_180004E50
0x180004d7f  mov     r14d, [rsp+270h+var_220]
0x180004d84  mov     rbx, [rsp+270h+var_218]
0x180004d89  jmp     short loc_180004D9D
0x180004d8b  lea     rbx, [rsp+270h+var_208]
0x180004d90  lock inc dword ptr [rdi+10h]
0x180004d94  mov     r14d, 1
0x180004d9a  mov     esi, r13d
0x180004d9d  mov     r8d, 0DFh
0x180004da3  lea     rcx, [rsp+270h+var_200]
0x180004da8  mov     rdx, r12
0x180004dab  call    cs:__imp_DiscpCopyToCountedString
0x180004db1  mov     edi, r13d
0x180004db4  test    r14d, r14d
0x180004db7  jz      loc_180004E3D
0x180004dbd  neg     r15b
0x180004dc0  mov     r12d, 4
0x180004dc6  sbb     r15d, r15d
0x180004dc9  mov     [rsp+270h+var_230], r12d
0x180004dce  lea     r9d, [r15+66h]
0x180004dd2  mov     eax, edi
0x180004dd4  lea     rcx, MSiSCSI_Operations_GUID
0x180004ddb  xor     edx, edx
0x180004ddd  mov     r13, [rbx+rax*8]
0x180004de1  lea     rax, [rsp+270h+var_21C]
0x180004de6  mov     [rsp+270h+var_238], rax
0x180004deb  lea     rax, [rsp+270h+var_210]
0x180004df0  mov     [rsp+270h+var_240], rax
0x180004df5  lea     rax, [rsp+270h+var_200]
0x180004dfa  mov     [rsp+270h+var_21C], r12d
0x180004dff  mov     [rsp+270h+var_210], 0
0x180004e08  mov     r8, [r13+28h]
0x180004e0c  mov     [rsp+270h+var_248], 1C0h
0x180004e14  mov     [rsp+270h+var_250], rax
0x180004e19  call    cs:__imp_DiscpExecuteMethod
0x180004e1f  or      eax, 0FFFFFFFFh
0x180004e22  lock xadd [r13+10h], eax
0x180004e28  cmp     eax, 1
0x180004e2b  jnz     short loc_180004E36
0x180004e2d  mov     rcx, r13
0x180004e30  call    cs:__imp_DiscpFreeMemory
0x180004e36  inc     edi
0x180004e38  cmp     edi, r14d
0x180004e3b  jb      short loc_180004DC9
0x180004e3d  lea     rax, [rsp+270h+var_208]
0x180004e42  cmp     rbx, rax
0x180004e45  jz      short loc_180004E50
0x180004e47  mov     rcx, rbx
0x180004e4a  call    cs:__imp_DiscpFreeMemory
0x180004e50  mov     eax, esi
0x180004e52  mov     rcx, [rbp+170h+var_40]
0x180004e59  xor     rcx, rsp; StackCookie
0x180004e5c  call    __security_check_cookie
0x180004e61  mov     rbx, [rsp+270h+arg_10]
0x180004e69  add     rsp, 240h
0x180004e70  pop     r15
0x180004e72  pop     r14
0x180004e74  pop     r13
0x180004e76  pop     r12
0x180004e78  pop     rdi
0x180004e79  pop     rsi
0x180004e7a  pop     rbp
0x180004e7b  retn
```
