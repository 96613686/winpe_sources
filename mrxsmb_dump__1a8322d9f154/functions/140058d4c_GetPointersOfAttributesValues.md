# GetPointersOfAttributesValues

- ea: `0x140058d4c`
- end: `0x140058f12`
- name: `GetPointersOfAttributesValues`
- size: `454`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140059338`
- `0x1400593c8`

## callees

- `0x140058d4c`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140058e24`
- `ntoskrnl!RtlCompareMemory` at `0x140058e6b`
- `ntoskrnl!RtlCompareMemory` at `0x140058ede`
- `ntoskrnl!RtlCompareMemory` at `0x140058e24`
- `ntoskrnl!RtlCompareMemory` at `0x140058e6b`
- `ntoskrnl!RtlCompareMemory` at `0x140058ede`

## pseudocode

```c
void __fastcall GetPointersOfAttributesValues(__int64 a1, _QWORD *a2, _QWORD *a3, _DWORD *a4, _QWORD *a5)
{
  __int64 v8; // rsi
  __int64 i; // r13
  __int64 v10; // rsi
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx

  v8 = a1;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 || a4 || a5 || a2 )
  {
    if ( a1 )
    {
      for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 4); i = (unsigned int)(i + 1) )
      {
        v10 = *(_QWORD *)(v8 + 8);
        if ( *(_DWORD *)(v10 + 40 * i + 24) && *(_QWORD *)(v10 + 40 * i + 32) )
        {
          if ( a3
            && (v11 = *(unsigned __int16 *)(v10 + 40 * i), (v11 & 0xFFFE) == 0x22)
            && RtlCompareMemory(
                 *(const void **)(v10 + 40 * i + 8),
                 L"EDP://PolicyFlags",
                 *(unsigned __int16 *)(v10 + 40 * i)) == v11 )
          {
            *a3 = *(_QWORD *)(v10 + 40 * i + 32);
          }
          else if ( a2
                 && (v12 = *(unsigned __int16 *)(v10 + 40 * i), (v12 & 0xFFFE) == 0x2A)
                 && RtlCompareMemory(
                      *(const void **)(v10 + 40 * i + 8),
                      L"EDP://EvaluationFlags",
                      *(unsigned __int16 *)(v10 + 40 * i)) == v12 )
          {
            *a2 = *(_QWORD *)(v10 + 40 * i + 32);
          }
          else if ( a4 || a5 )
          {
            v13 = *(unsigned __int16 *)(v10 + 40 * i);
            if ( (v13 & 0xFFFE) == 0x26
              && RtlCompareMemory(
                   *(const void **)(v10 + 40 * i + 8),
                   L"EDP://EnterpriseIds",
                   *(unsigned __int16 *)(v10 + 40 * i)) == v13 )
            {
              if ( a4 )
                *a4 = *(_DWORD *)(v10 + 40 * i + 24);
              if ( a5 )
                *a5 = *(_QWORD *)(v10 + 40 * i + 32);
            }
          }
        }
        v8 = a1;
      }
    }
  }
}

```

## disassembly

```asm
0x140058d4c  mov     [rsp+arg_0], rcx
0x140058d51  push    rbx
0x140058d52  push    rbp
0x140058d53  push    rsi
0x140058d54  push    rdi
0x140058d55  push    r12
0x140058d57  push    r13
0x140058d59  push    r14
0x140058d5b  push    r15
0x140058d5d  sub     rsp, 28h
0x140058d61  mov     r15, r9
0x140058d64  mov     r12, r8
0x140058d67  mov     rbp, rdx
0x140058d6a  mov     rsi, rcx
0x140058d6d  test    r8, r8
0x140058d70  jz      short loc_140058D79
0x140058d72  mov     qword ptr [r8], 0
0x140058d79  test    r15, r15
0x140058d7c  jz      short loc_140058D85
0x140058d7e  mov     dword ptr [r9], 0
0x140058d85  mov     r14, [rsp+68h+arg_20]
0x140058d8d  test    r14, r14
0x140058d90  jz      short loc_140058D99
0x140058d92  mov     qword ptr [r14], 0
0x140058d99  test    rbp, rbp
0x140058d9c  jz      short loc_140058DA5
0x140058d9e  mov     qword ptr [rdx], 0
0x140058da5  test    r12, r12
0x140058da8  jnz     short loc_140058DBD
0x140058daa  test    r15, r15
0x140058dad  jnz     short loc_140058DBD
0x140058daf  test    r14, r14
0x140058db2  jnz     short loc_140058DBD
0x140058db4  test    rbp, rbp
0x140058db7  jz      loc_140058E9C
0x140058dbd  test    rcx, rcx
0x140058dc0  jz      loc_140058E9C
0x140058dc6  xor     r13d, r13d
0x140058dc9  cmp     [rcx+4], r13d
0x140058dcd  jbe     loc_140058E9C
0x140058dd3  mov     edx, 0FFFEh
0x140058dd8  mov     rsi, [rsi+8]
0x140058ddc  lea     rdi, ds:0[r13*4]
0x140058de4  add     rdi, r13
0x140058de7  cmp     dword ptr [rsi+rdi*8+18h], 0
0x140058dec  jz      loc_140058E8A
0x140058df2  cmp     qword ptr [rsi+rdi*8+20h], 0
0x140058df8  jz      loc_140058E8A
0x140058dfe  test    r12, r12
0x140058e01  jz      short loc_140058E45
0x140058e03  movzx   ecx, word ptr [rsi+rdi*8]
0x140058e07  movzx   eax, cx
0x140058e0a  and     ax, dx
0x140058e0d  cmp     ax, 22h ; '"'
0x140058e11  jnz     short loc_140058E45
0x140058e13  mov     ebx, ecx
0x140058e15  lea     rdx, aEdpPolicyflags; "EDP://PolicyFlags"
0x140058e1c  mov     r8d, ecx; Length
0x140058e1f  mov     rcx, [rsi+rdi*8+8]; Source1
0x140058e24  call    cs:__imp_RtlCompareMemory
0x140058e2b  nop     dword ptr [rax+rax+00h]
0x140058e30  mov     edx, 0FFFEh
0x140058e35  cmp     rax, rbx
0x140058e38  jnz     short loc_140058E45
0x140058e3a  mov     rax, [rsi+rdi*8+20h]
0x140058e3f  mov     [r12], rax
0x140058e43  jmp     short loc_140058E8A
0x140058e45  test    rbp, rbp
0x140058e48  jz      short loc_140058EAE
0x140058e4a  movzx   ecx, word ptr [rsi+rdi*8]
0x140058e4e  movzx   eax, cx
0x140058e51  and     ax, dx
0x140058e54  cmp     ax, 2Ah ; '*'
0x140058e58  jnz     short loc_140058EAE
0x140058e5a  mov     ebx, ecx
0x140058e5c  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x140058e63  mov     r8d, ecx; Length
0x140058e66  mov     rcx, [rsi+rdi*8+8]; Source1
0x140058e6b  call    cs:__imp_RtlCompareMemory
0x140058e72  nop     dword ptr [rax+rax+00h]
0x140058e77  cmp     rax, rbx
0x140058e7a  jnz     short loc_140058EAE
0x140058e7c  mov     rax, [rsi+rdi*8+20h]
0x140058e81  mov     [rbp+0], rax
0x140058e85  mov     edx, 0FFFEh
0x140058e8a  mov     rsi, [rsp+68h+arg_0]
0x140058e8f  inc     r13d
0x140058e92  cmp     r13d, [rsi+4]
0x140058e96  jb      loc_140058DD8
0x140058e9c  add     rsp, 28h
0x140058ea0  pop     r15
0x140058ea2  pop     r14
0x140058ea4  pop     r13
0x140058ea6  pop     r12
0x140058ea8  pop     rdi
0x140058ea9  pop     rsi
0x140058eaa  pop     rbp
0x140058eab  pop     rbx
0x140058eac  retn
0x140058eae  test    r15, r15
0x140058eb1  jnz     short loc_140058EB8
0x140058eb3  test    r14, r14
0x140058eb6  jz      short loc_140058E85
0x140058eb8  movzx   ecx, word ptr [rsi+rdi*8]
0x140058ebc  mov     edx, 0FFFEh
0x140058ec1  movzx   eax, cx
0x140058ec4  and     ax, dx
0x140058ec7  cmp     ax, 26h ; '&'
0x140058ecb  jnz     short loc_140058E8A
0x140058ecd  mov     ebx, ecx
0x140058ecf  lea     rdx, aEdpEnterprisei; "EDP://EnterpriseIds"
0x140058ed6  mov     r8d, ecx; Length
0x140058ed9  mov     rcx, [rsi+rdi*8+8]; Source1
0x140058ede  call    cs:__imp_RtlCompareMemory
0x140058ee5  nop     dword ptr [rax+rax+00h]
0x140058eea  cmp     rax, rbx
0x140058eed  jnz     short loc_140058E85
0x140058eef  test    r15, r15
0x140058ef2  jz      short loc_140058EFB
0x140058ef4  mov     eax, [rsi+rdi*8+18h]
0x140058ef8  mov     [r15], eax
0x140058efb  mov     edx, 0FFFEh
0x140058f00  test    r14, r14
0x140058f03  jz      short loc_140058E8A
0x140058f05  mov     rax, [rsi+rdi*8+20h]
0x140058f0a  mov     [r14], rax
0x140058f0d  jmp     loc_140058E8A
```
