# CiParseRevocationList

- ea: `0x1800e4384`
- end: `0x1800e453e`
- name: `CiParseRevocationList`
- size: `442`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180072ca4`
- `0x180073244`

## callees

- `0x1800778e8`
- `0x18008f458`
- `0x180092ec8`
- `0x180095448`
- `0x1800985d4`
- `0x1800e4384`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800e43af`
- `ntoskrnl!ExAllocatePool2` at `0x1800e43af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e4515`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e4515`
- `ntoskrnl!RtlCompareMemory` at `0x1800e442f`
- `ntoskrnl!RtlCompareMemory` at `0x1800e442f`

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
      if ( *(_DWORD *)v10 == 9 && RtlCompareMemory(qword_1800362D8, *((const void **)v10 + 1), 9u) == 9 )
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
0x1800e4384  mov     [rsp+arg_18], r9
0x1800e4389  push    rbx
0x1800e438a  push    rsi
0x1800e438b  push    rdi
0x1800e438c  push    r12
0x1800e438e  push    r14
0x1800e4390  push    r15
0x1800e4392  sub     rsp, 68h
0x1800e4396  mov     r14, r9
0x1800e4399  mov     r12, r8
0x1800e439c  mov     ebx, edx
0x1800e439e  mov     r15, rcx
0x1800e43a1  mov     edx, 140h
0x1800e43a6  lea     ecx, [rdx-3Eh]
0x1800e43a9  mov     r8d, 72634943h
0x1800e43af  call    cs:__imp_ExAllocatePool2
0x1800e43b6  nop     dword ptr [rax+rax+00h]
0x1800e43bb  mov     rdi, rax
0x1800e43be  mov     [rsp+98h+var_40], rax
0x1800e43c3  test    rax, rax
0x1800e43c6  jnz     short loc_1800E43D2
0x1800e43c8  mov     ebx, 0C0000017h
0x1800e43cd  jmp     loc_1800E4508
0x1800e43d2  mov     [rsp+98h+var_58], 0; __int64
0x1800e43db  mov     [rsp+98h+var_60], 0; __int64
0x1800e43e4  mov     [rsp+98h+var_68], rdi; void *
0x1800e43e9  mov     qword ptr [rsp+98h+var_70], r14; int
0x1800e43ee  mov     [rsp+98h+var_78], 0; __int64
0x1800e43f7  xor     r9d, r9d; int
0x1800e43fa  xor     r8d, r8d; int
0x1800e43fd  mov     edx, ebx; int
0x1800e43ff  mov     rcx, r15; int
0x1800e4402  call    MinCrypK_VerifySignedDataKModeEx
0x1800e4407  mov     ebx, eax
0x1800e4409  mov     [rsp+98h+var_48], eax
0x1800e440d  test    eax, eax
0x1800e440f  js      loc_1800E4508
0x1800e4415  cmp     dword ptr [rdi], 9
0x1800e4418  jnz     loc_1800E44EA
0x1800e441e  mov     r8d, 9; Length
0x1800e4424  mov     rdx, [rdi+8]; Source2
0x1800e4428  lea     rcx, qword_1800362D8; Source1
0x1800e442f  call    cs:__imp_RtlCompareMemory
0x1800e4436  nop     dword ptr [rax+rax+00h]
0x1800e443b  cmp     rax, 9
0x1800e443f  jnz     loc_1800E44EA
0x1800e4445  lea     rcx, [rdi+10h]
0x1800e4449  lea     rdx, [rdi+50h]
0x1800e444d  call    MinAsn1ParseCTL
0x1800e4452  test    eax, eax
0x1800e4454  jns     short loc_1800E4464
0x1800e4456  mov     ebx, 0C0000428h
0x1800e445b  mov     [rsp+98h+var_48], ebx
0x1800e445f  jmp     loc_1800E4508
0x1800e4464  cmp     dword ptr [rdi+80h], 0Eh
0x1800e446b  jnz     short loc_1800E44DF
0x1800e446d  mov     rdx, [rdi+88h]
0x1800e4474  mov     rcx, cs:qword_1800362F0
0x1800e447b  sub     rcx, [rdx]
0x1800e447e  jnz     short loc_1800E449C
0x1800e4480  mov     ecx, cs:dword_1800362F8
0x1800e4486  mov     eax, [rdx+8]
0x1800e4489  sub     rcx, rax
0x1800e448c  jnz     short loc_1800E449C
0x1800e448e  movzx   ecx, cs:word_1800362FC
0x1800e4495  movzx   eax, word ptr [rdx+0Ch]
0x1800e4499  sub     rcx, rax
0x1800e449c  test    rcx, rcx
0x1800e449f  jnz     short loc_1800E44DF
0x1800e44a1  lea     rcx, [rdi+0B0h]
0x1800e44a8  mov     rdx, [rsp+98h+arg_20]
0x1800e44b0  call    MinAsn1DecodeTime
0x1800e44b5  test    al, al
0x1800e44b7  jnz     short loc_1800E44C4
0x1800e44b9  mov     ebx, 0C0000428h
0x1800e44be  mov     [rsp+98h+var_48], ebx
0x1800e44c2  jmp     short loc_1800E4508
0x1800e44c4  lea     rcx, [rdi+0F0h]
0x1800e44cb  mov     r8, r12
0x1800e44ce  call    MinCryptParseRevocationList
0x1800e44d3  mov     ebx, eax
0x1800e44d5  mov     [rsp+98h+var_48], eax
0x1800e44d9  test    eax, eax
0x1800e44db  js      short loc_1800E4508
0x1800e44dd  jmp     short loc_1800E4508
0x1800e44df  mov     ebx, 0C0000428h
0x1800e44e4  mov     [rsp+98h+var_48], ebx
0x1800e44e8  jmp     short loc_1800E4508
0x1800e44ea  mov     ebx, 0C0000428h
0x1800e44ef  mov     [rsp+98h+var_48], ebx
0x1800e44f3  jmp     short loc_1800E4508
0x1800e44f5  mov     ebx, eax
0x1800e44f7  mov     [rsp+98h+var_48], eax
0x1800e44fb  mov     r14, [rsp+98h+arg_18]
0x1800e4503  mov     rdi, [rsp+98h+var_40]
0x1800e4508  test    rdi, rdi
0x1800e450b  jz      short loc_1800E4521
0x1800e450d  mov     edx, 63734943h; Tag
0x1800e4512  mov     rcx, rdi; P
0x1800e4515  call    cs:__imp_ExFreePoolWithTag
0x1800e451c  nop     dword ptr [rax+rax+00h]
0x1800e4521  test    ebx, ebx
0x1800e4523  jns     short loc_1800E452D
0x1800e4525  mov     rcx, r14
0x1800e4528  call    MincryptFreePolicyInfo
0x1800e452d  mov     eax, ebx
0x1800e452f  add     rsp, 68h
0x1800e4533  pop     r15
0x1800e4535  pop     r14
0x1800e4537  pop     r12
0x1800e4539  pop     rdi
0x1800e453a  pop     rsi
0x1800e453b  pop     rbx
0x1800e453c  retn
```
