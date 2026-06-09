# CiParseRevocationList

- ea: `0x1800e4904`
- end: `0x1800e4abe`
- name: `CiParseRevocationList`
- size: `442`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180072f84`
- `0x180073524`

## callees

- `0x180077bc8`
- `0x18008eda4`
- `0x180094db8`
- `0x180098828`
- `0x18009ada8`
- `0x1800e4904`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800e492f`
- `ntoskrnl!ExAllocatePool2` at `0x1800e492f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e4a95`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e4a95`
- `ntoskrnl!RtlCompareMemory` at `0x1800e49af`
- `ntoskrnl!RtlCompareMemory` at `0x1800e49af`

## pseudocode

```c
__int64 __fastcall CiParseRevocationList(int a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  char *Pool2; // rax
  char *v10; // rdi
  int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdx

  Pool2 = (char *)ExAllocatePool2(258, 320, 1919109443);
  v10 = Pool2;
  if ( Pool2 )
  {
    v11 = MinCrypK_VerifySignedDataKModeEx(a1, a2, 0, 0, 0, a4, Pool2, 0, 0);
    if ( v11 >= 0 )
    {
      if ( *(_DWORD *)v10 == 9 && RtlCompareMemory(qword_180036150, *((const void **)v10 + 1), 9u) == 9 )
      {
        if ( (int)MinAsn1ParseCTL(v10 + 16, v10 + 80) >= 0 )
        {
          if ( *((_DWORD *)v10 + 32) != 14 )
            goto LABEL_16;
          v12 = *((_QWORD *)v10 + 17);
          v13 = 0x401062B0A060C30LL - *(_QWORD *)v12;
          if ( *(_QWORD *)v12 == 0x401062B0A060C30LL )
          {
            v14 = *(unsigned int *)(v12 + 8);
            v13 = 1027047937 - v14;
            if ( v14 == 1027047937 )
              v13 = 259LL - *(unsigned __int16 *)(v12 + 12);
          }
          if ( v13 )
          {
LABEL_16:
            v11 = -1073740760;
          }
          else if ( (unsigned __int8)MinAsn1DecodeTime(v10 + 176, a5) )
          {
            v11 = MinCryptParseRevocationList(v10 + 240, v15, a3);
          }
          else
          {
            v11 = -1073740760;
          }
        }
        else
        {
          v11 = -1073740760;
        }
      }
      else
      {
        v11 = -1073740760;
      }
    }
  }
  else
  {
    v11 = -1073741801;
  }
  if ( v10 )
    ExFreePoolWithTag(v10, 0x63734943u);
  if ( v11 < 0 )
    MincryptFreePolicyInfo(a4);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800e4904  mov     [rsp+arg_18], r9
0x1800e4909  push    rbx
0x1800e490a  push    rsi
0x1800e490b  push    rdi
0x1800e490c  push    r12
0x1800e490e  push    r14
0x1800e4910  push    r15
0x1800e4912  sub     rsp, 68h
0x1800e4916  mov     r14, r9
0x1800e4919  mov     r12, r8
0x1800e491c  mov     ebx, edx
0x1800e491e  mov     r15, rcx
0x1800e4921  mov     edx, 140h
0x1800e4926  lea     ecx, [rdx-3Eh]
0x1800e4929  mov     r8d, 72634943h
0x1800e492f  call    cs:__imp_ExAllocatePool2
0x1800e4936  nop     dword ptr [rax+rax+00h]
0x1800e493b  mov     rdi, rax
0x1800e493e  mov     [rsp+98h+var_40], rax
0x1800e4943  test    rax, rax
0x1800e4946  jnz     short loc_1800E4952
0x1800e4948  mov     ebx, 0C0000017h
0x1800e494d  jmp     loc_1800E4A88
0x1800e4952  mov     [rsp+98h+var_58], 0; __int64
0x1800e495b  mov     [rsp+98h+var_60], 0; __int64
0x1800e4964  mov     [rsp+98h+var_68], rdi; void *
0x1800e4969  mov     qword ptr [rsp+98h+var_70], r14; int
0x1800e496e  mov     [rsp+98h+var_78], 0; __int64
0x1800e4977  xor     r9d, r9d; int
0x1800e497a  xor     r8d, r8d; int
0x1800e497d  mov     edx, ebx; int
0x1800e497f  mov     rcx, r15; int
0x1800e4982  call    MinCrypK_VerifySignedDataKModeEx
0x1800e4987  mov     ebx, eax
0x1800e4989  mov     [rsp+98h+var_48], eax
0x1800e498d  test    eax, eax
0x1800e498f  js      loc_1800E4A88
0x1800e4995  cmp     dword ptr [rdi], 9
0x1800e4998  jnz     loc_1800E4A6A
0x1800e499e  mov     r8d, 9; Length
0x1800e49a4  mov     rdx, [rdi+8]; Source2
0x1800e49a8  lea     rcx, qword_180036150; Source1
0x1800e49af  call    cs:__imp_RtlCompareMemory
0x1800e49b6  nop     dword ptr [rax+rax+00h]
0x1800e49bb  cmp     rax, 9
0x1800e49bf  jnz     loc_1800E4A6A
0x1800e49c5  lea     rcx, [rdi+10h]
0x1800e49c9  lea     rdx, [rdi+50h]
0x1800e49cd  call    MinAsn1ParseCTL
0x1800e49d2  test    eax, eax
0x1800e49d4  jns     short loc_1800E49E4
0x1800e49d6  mov     ebx, 0C0000428h
0x1800e49db  mov     [rsp+98h+var_48], ebx
0x1800e49df  jmp     loc_1800E4A88
0x1800e49e4  cmp     dword ptr [rdi+80h], 0Eh
0x1800e49eb  jnz     short loc_1800E4A5F
0x1800e49ed  mov     rdx, [rdi+88h]
0x1800e49f4  mov     rcx, cs:qword_180036168
0x1800e49fb  sub     rcx, [rdx]
0x1800e49fe  jnz     short loc_1800E4A1C
0x1800e4a00  mov     ecx, cs:dword_180036170
0x1800e4a06  mov     eax, [rdx+8]
0x1800e4a09  sub     rcx, rax
0x1800e4a0c  jnz     short loc_1800E4A1C
0x1800e4a0e  movzx   ecx, cs:word_180036174
0x1800e4a15  movzx   eax, word ptr [rdx+0Ch]
0x1800e4a19  sub     rcx, rax
0x1800e4a1c  test    rcx, rcx
0x1800e4a1f  jnz     short loc_1800E4A5F
0x1800e4a21  lea     rcx, [rdi+0B0h]
0x1800e4a28  mov     rdx, [rsp+98h+arg_20]
0x1800e4a30  call    MinAsn1DecodeTime
0x1800e4a35  test    al, al
0x1800e4a37  jnz     short loc_1800E4A44
0x1800e4a39  mov     ebx, 0C0000428h
0x1800e4a3e  mov     [rsp+98h+var_48], ebx
0x1800e4a42  jmp     short loc_1800E4A88
0x1800e4a44  lea     rcx, [rdi+0F0h]
0x1800e4a4b  mov     r8, r12
0x1800e4a4e  call    MinCryptParseRevocationList
0x1800e4a53  mov     ebx, eax
0x1800e4a55  mov     [rsp+98h+var_48], eax
0x1800e4a59  test    eax, eax
0x1800e4a5b  js      short loc_1800E4A88
0x1800e4a5d  jmp     short loc_1800E4A88
0x1800e4a5f  mov     ebx, 0C0000428h
0x1800e4a64  mov     [rsp+98h+var_48], ebx
0x1800e4a68  jmp     short loc_1800E4A88
0x1800e4a6a  mov     ebx, 0C0000428h
0x1800e4a6f  mov     [rsp+98h+var_48], ebx
0x1800e4a73  jmp     short loc_1800E4A88
0x1800e4a75  mov     ebx, eax
0x1800e4a77  mov     [rsp+98h+var_48], eax
0x1800e4a7b  mov     r14, [rsp+98h+arg_18]
0x1800e4a83  mov     rdi, [rsp+98h+var_40]
0x1800e4a88  test    rdi, rdi
0x1800e4a8b  jz      short loc_1800E4AA1
0x1800e4a8d  mov     edx, 63734943h; Tag
0x1800e4a92  mov     rcx, rdi; P
0x1800e4a95  call    cs:__imp_ExFreePoolWithTag
0x1800e4a9c  nop     dword ptr [rax+rax+00h]
0x1800e4aa1  test    ebx, ebx
0x1800e4aa3  jns     short loc_1800E4AAD
0x1800e4aa5  mov     rcx, r14
0x1800e4aa8  call    MincryptFreePolicyInfo
0x1800e4aad  mov     eax, ebx
0x1800e4aaf  add     rsp, 68h
0x1800e4ab3  pop     r15
0x1800e4ab5  pop     r14
0x1800e4ab7  pop     r12
0x1800e4ab9  pop     rdi
0x1800e4aba  pop     rsi
0x1800e4abb  pop     rbx
0x1800e4abc  retn
```
