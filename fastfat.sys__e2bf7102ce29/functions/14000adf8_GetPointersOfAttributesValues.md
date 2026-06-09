# GetPointersOfAttributesValues

- ea: `0x14000adf8`
- end: `0x14000afbe`
- name: `GetPointersOfAttributesValues`
- size: `454`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b278`
- `0x14000b308`

## callees

- `0x14000adf8`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000aed0`
- `ntoskrnl!RtlCompareMemory` at `0x14000af17`
- `ntoskrnl!RtlCompareMemory` at `0x14000af8a`
- `ntoskrnl!RtlCompareMemory` at `0x14000aed0`
- `ntoskrnl!RtlCompareMemory` at `0x14000af17`
- `ntoskrnl!RtlCompareMemory` at `0x14000af8a`

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
0x14000adf8  mov     [rsp+arg_0], rcx
0x14000adfd  push    rbx
0x14000adfe  push    rbp
0x14000adff  push    rsi
0x14000ae00  push    rdi
0x14000ae01  push    r12
0x14000ae03  push    r13
0x14000ae05  push    r14
0x14000ae07  push    r15
0x14000ae09  sub     rsp, 28h
0x14000ae0d  mov     r15, r9
0x14000ae10  mov     r12, r8
0x14000ae13  mov     rbp, rdx
0x14000ae16  mov     rsi, rcx
0x14000ae19  test    r8, r8
0x14000ae1c  jz      short loc_14000AE25
0x14000ae1e  mov     qword ptr [r8], 0
0x14000ae25  test    r15, r15
0x14000ae28  jz      short loc_14000AE31
0x14000ae2a  mov     dword ptr [r9], 0
0x14000ae31  mov     r14, [rsp+68h+arg_20]
0x14000ae39  test    r14, r14
0x14000ae3c  jz      short loc_14000AE45
0x14000ae3e  mov     qword ptr [r14], 0
0x14000ae45  test    rbp, rbp
0x14000ae48  jz      short loc_14000AE51
0x14000ae4a  mov     qword ptr [rdx], 0
0x14000ae51  test    r12, r12
0x14000ae54  jnz     short loc_14000AE69
0x14000ae56  test    r15, r15
0x14000ae59  jnz     short loc_14000AE69
0x14000ae5b  test    r14, r14
0x14000ae5e  jnz     short loc_14000AE69
0x14000ae60  test    rbp, rbp
0x14000ae63  jz      loc_14000AF48
0x14000ae69  test    rcx, rcx
0x14000ae6c  jz      loc_14000AF48
0x14000ae72  xor     r13d, r13d
0x14000ae75  cmp     [rcx+4], r13d
0x14000ae79  jbe     loc_14000AF48
0x14000ae7f  mov     edx, 0FFFEh
0x14000ae84  mov     rsi, [rsi+8]
0x14000ae88  lea     rdi, ds:0[r13*4]
0x14000ae90  add     rdi, r13
0x14000ae93  cmp     dword ptr [rsi+rdi*8+18h], 0
0x14000ae98  jz      loc_14000AF36
0x14000ae9e  cmp     qword ptr [rsi+rdi*8+20h], 0
0x14000aea4  jz      loc_14000AF36
0x14000aeaa  test    r12, r12
0x14000aead  jz      short loc_14000AEF1
0x14000aeaf  movzx   ecx, word ptr [rsi+rdi*8]
0x14000aeb3  movzx   eax, cx
0x14000aeb6  and     ax, dx
0x14000aeb9  cmp     ax, 22h ; '"'
0x14000aebd  jnz     short loc_14000AEF1
0x14000aebf  mov     ebx, ecx
0x14000aec1  lea     rdx, aEdpPolicyflags; "EDP://PolicyFlags"
0x14000aec8  mov     r8d, ecx; Length
0x14000aecb  mov     rcx, [rsi+rdi*8+8]; Source1
0x14000aed0  call    cs:__imp_RtlCompareMemory
0x14000aed7  nop     dword ptr [rax+rax+00h]
0x14000aedc  mov     edx, 0FFFEh
0x14000aee1  cmp     rax, rbx
0x14000aee4  jnz     short loc_14000AEF1
0x14000aee6  mov     rax, [rsi+rdi*8+20h]
0x14000aeeb  mov     [r12], rax
0x14000aeef  jmp     short loc_14000AF36
0x14000aef1  test    rbp, rbp
0x14000aef4  jz      short loc_14000AF5A
0x14000aef6  movzx   ecx, word ptr [rsi+rdi*8]
0x14000aefa  movzx   eax, cx
0x14000aefd  and     ax, dx
0x14000af00  cmp     ax, 2Ah ; '*'
0x14000af04  jnz     short loc_14000AF5A
0x14000af06  mov     ebx, ecx
0x14000af08  lea     rdx, aEdpEvaluationf; "EDP://EvaluationFlags"
0x14000af0f  mov     r8d, ecx; Length
0x14000af12  mov     rcx, [rsi+rdi*8+8]; Source1
0x14000af17  call    cs:__imp_RtlCompareMemory
0x14000af1e  nop     dword ptr [rax+rax+00h]
0x14000af23  cmp     rax, rbx
0x14000af26  jnz     short loc_14000AF5A
0x14000af28  mov     rax, [rsi+rdi*8+20h]
0x14000af2d  mov     [rbp+0], rax
0x14000af31  mov     edx, 0FFFEh
0x14000af36  mov     rsi, [rsp+68h+arg_0]
0x14000af3b  inc     r13d
0x14000af3e  cmp     r13d, [rsi+4]
0x14000af42  jb      loc_14000AE84
0x14000af48  add     rsp, 28h
0x14000af4c  pop     r15
0x14000af4e  pop     r14
0x14000af50  pop     r13
0x14000af52  pop     r12
0x14000af54  pop     rdi
0x14000af55  pop     rsi
0x14000af56  pop     rbp
0x14000af57  pop     rbx
0x14000af58  retn
0x14000af5a  test    r15, r15
0x14000af5d  jnz     short loc_14000AF64
0x14000af5f  test    r14, r14
0x14000af62  jz      short loc_14000AF31
0x14000af64  movzx   ecx, word ptr [rsi+rdi*8]
0x14000af68  mov     edx, 0FFFEh
0x14000af6d  movzx   eax, cx
0x14000af70  and     ax, dx
0x14000af73  cmp     ax, 26h ; '&'
0x14000af77  jnz     short loc_14000AF36
0x14000af79  mov     ebx, ecx
0x14000af7b  lea     rdx, aEdpEnterprisei; "EDP://EnterpriseIds"
0x14000af82  mov     r8d, ecx; Length
0x14000af85  mov     rcx, [rsi+rdi*8+8]; Source1
0x14000af8a  call    cs:__imp_RtlCompareMemory
0x14000af91  nop     dword ptr [rax+rax+00h]
0x14000af96  cmp     rax, rbx
0x14000af99  jnz     short loc_14000AF31
0x14000af9b  test    r15, r15
0x14000af9e  jz      short loc_14000AFA7
0x14000afa0  mov     eax, [rsi+rdi*8+18h]
0x14000afa4  mov     [r15], eax
0x14000afa7  mov     edx, 0FFFEh
0x14000afac  test    r14, r14
0x14000afaf  jz      short loc_14000AF36
0x14000afb1  mov     rax, [rsi+rdi*8+20h]
0x14000afb6  mov     [r14], rax
0x14000afb9  jmp     loc_14000AF36
```
