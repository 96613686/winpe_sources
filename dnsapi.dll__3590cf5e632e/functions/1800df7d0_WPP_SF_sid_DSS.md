# WPP_SF__sid_DSS

- ea: `0x1800df7d0`
- end: `0x1800df90e`
- name: `WPP_SF__sid_DSS`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bc874`

## callees

- `0x1800750c0`
- `0x1800df7d0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800df86d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800df86d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800df85a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800df88a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800df85a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800df88a`

## pseudocode

```c

```

## disassembly

```asm
0x1800df7d0  mov     [rsp+arg_0], rbx
0x1800df7d5  mov     [rsp+arg_8], rbp
0x1800df7da  push    rsi
0x1800df7db  push    rdi
0x1800df7dc  push    r12
0x1800df7de  push    r14
0x1800df7e0  push    r15
0x1800df7e2  sub     rsp, 60h
0x1800df7e6  mov     rbp, [rsp+88h+arg_30]
0x1800df7ee  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800df7f2  mov     rsi, [rsp+88h+arg_28]
0x1800df7fa  xor     r12d, r12d
0x1800df7fd  mov     rbx, r9
0x1800df800  mov     r14d, 0Ah
0x1800df806  test    rbp, rbp
0x1800df809  jz      short loc_1800DF823
0x1800df80b  mov     rax, rcx
0x1800df80e  inc     rax
0x1800df811  cmp     [rbp+rax*2+0], r12w
0x1800df817  jnz     short loc_1800DF80E
0x1800df819  lea     r15, ds:2[rax*2]
0x1800df821  jmp     short loc_1800DF826
0x1800df823  mov     r15, r14
0x1800df826  test    rbp, rbp
0x1800df829  lea     rax, aNull_0; "NULL"
0x1800df830  cmovz   rbp, rax
0x1800df834  test    rsi, rsi
0x1800df837  jz      short loc_1800DF84E
0x1800df839  inc     rcx
0x1800df83c  cmp     [rsi+rcx*2], r12w
0x1800df841  jnz     short loc_1800DF839
0x1800df843  lea     r14, ds:2[rcx*2]
0x1800df84b  test    rsi, rsi
0x1800df84e  cmovz   rsi, rax
0x1800df852  test    rbx, rbx
0x1800df855  jz      short loc_1800DF87D
0x1800df857  mov     rcx, rbx; pSid
0x1800df85a  call    cs:__imp_IsValidSid
0x1800df861  nop     dword ptr [rax+rax+00h]
0x1800df866  test    eax, eax
0x1800df868  jz      short loc_1800DF87D
0x1800df86a  mov     rcx, rbx; pSid
0x1800df86d  call    cs:__imp_GetLengthSid
0x1800df874  nop     dword ptr [rax+rax+00h]
0x1800df879  mov     edi, eax
0x1800df87b  jmp     short loc_1800DF887
0x1800df87d  mov     edi, 5
0x1800df882  test    rbx, rbx
0x1800df885  jz      short loc_1800DF89A
0x1800df887  mov     rcx, rbx; pSid
0x1800df88a  call    cs:__imp_IsValidSid
0x1800df891  nop     dword ptr [rax+rax+00h]
0x1800df896  test    eax, eax
0x1800df898  jnz     short loc_1800DF8A1
0x1800df89a  lea     rbx, aNull; "NULL"
0x1800df8a1  mov     [rsp+88h+var_30], r12
0x1800df8a6  lea     rcx, [rsp+88h+arg_20]
0x1800df8ae  mov     [rsp+88h+var_38], r15
0x1800df8b3  lea     r8, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids
0x1800df8ba  mov     [rsp+88h+var_40], rbp
0x1800df8bf  mov     r10d, 41Eh
0x1800df8c5  mov     [rsp+88h+var_48], r14
0x1800df8ca  mov     edx, 13h
0x1800df8cf  mov     [rsp+88h+var_50], rsi
0x1800df8d4  mov     r9, rbx
0x1800df8d7  mov     [rsp+88h+var_58], 4
0x1800df8e0  mov     [rsp+88h+var_60], rcx
0x1800df8e5  mov     ecx, r10d
0x1800df8e8  mov     eax, edi
0x1800df8ea  mov     [rsp+88h+var_68], rax
0x1800df8ef  call    FastWppTraceMessage
0x1800df8f4  lea     r11, [rsp+88h+var_28]
0x1800df8f9  mov     rbx, [r11+30h]
0x1800df8fd  mov     rbp, [r11+38h]
0x1800df901  mov     rsp, r11
0x1800df904  pop     r15
0x1800df906  pop     r14
0x1800df908  pop     r12
0x1800df90a  pop     rdi
0x1800df90b  pop     rsi
0x1800df90c  retn
```
