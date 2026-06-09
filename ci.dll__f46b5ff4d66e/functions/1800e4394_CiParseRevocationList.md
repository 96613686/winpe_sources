# CiParseRevocationList

- ea: `0x1800e4394`
- end: `0x1800e454e`
- name: `CiParseRevocationList`
- size: `442`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800719f4`
- `0x180071f94`

## callees

- `0x180076338`
- `0x18008de28`
- `0x180091898`
- `0x180093e18`
- `0x180096fa4`
- `0x1800e4394`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800e43bf`
- `ntoskrnl!ExAllocatePool2` at `0x1800e43bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e4525`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800e4525`
- `ntoskrnl!RtlCompareMemory` at `0x1800e443f`
- `ntoskrnl!RtlCompareMemory` at `0x1800e443f`

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
      if ( *(_DWORD *)v10 == 9 && RtlCompareMemory(qword_180036218, *((const void **)v10 + 1), 9u) == 9 )
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
0x1800e4394  mov     [rsp+arg_18], r9
0x1800e4399  push    rbx
0x1800e439a  push    rsi
0x1800e439b  push    rdi
0x1800e439c  push    r12
0x1800e439e  push    r14
0x1800e43a0  push    r15
0x1800e43a2  sub     rsp, 68h
0x1800e43a6  mov     r14, r9
0x1800e43a9  mov     r12, r8
0x1800e43ac  mov     ebx, edx
0x1800e43ae  mov     r15, rcx
0x1800e43b1  mov     edx, 140h
0x1800e43b6  lea     ecx, [rdx-3Eh]
0x1800e43b9  mov     r8d, 72634943h
0x1800e43bf  call    cs:__imp_ExAllocatePool2
0x1800e43c6  nop     dword ptr [rax+rax+00h]
0x1800e43cb  mov     rdi, rax
0x1800e43ce  mov     [rsp+98h+var_40], rax
0x1800e43d3  test    rax, rax
0x1800e43d6  jnz     short loc_1800E43E2
0x1800e43d8  mov     ebx, 0C0000017h
0x1800e43dd  jmp     loc_1800E4518
0x1800e43e2  mov     [rsp+98h+var_58], 0; __int64
0x1800e43eb  mov     [rsp+98h+var_60], 0; __int64
0x1800e43f4  mov     [rsp+98h+var_68], rdi; void *
0x1800e43f9  mov     qword ptr [rsp+98h+var_70], r14; int
0x1800e43fe  mov     [rsp+98h+var_78], 0; __int64
0x1800e4407  xor     r9d, r9d; int
0x1800e440a  xor     r8d, r8d; int
0x1800e440d  mov     edx, ebx; int
0x1800e440f  mov     rcx, r15; int
0x1800e4412  call    MinCrypK_VerifySignedDataKModeEx
0x1800e4417  mov     ebx, eax
0x1800e4419  mov     [rsp+98h+var_48], eax
0x1800e441d  test    eax, eax
0x1800e441f  js      loc_1800E4518
0x1800e4425  cmp     dword ptr [rdi], 9
0x1800e4428  jnz     loc_1800E44FA
0x1800e442e  mov     r8d, 9; Length
0x1800e4434  mov     rdx, [rdi+8]; Source2
0x1800e4438  lea     rcx, qword_180036218; Source1
0x1800e443f  call    cs:__imp_RtlCompareMemory
0x1800e4446  nop     dword ptr [rax+rax+00h]
0x1800e444b  cmp     rax, 9
0x1800e444f  jnz     loc_1800E44FA
0x1800e4455  lea     rcx, [rdi+10h]
0x1800e4459  lea     rdx, [rdi+50h]
0x1800e445d  call    MinAsn1ParseCTL
0x1800e4462  test    eax, eax
0x1800e4464  jns     short loc_1800E4474
0x1800e4466  mov     ebx, 0C0000428h
0x1800e446b  mov     [rsp+98h+var_48], ebx
0x1800e446f  jmp     loc_1800E4518
0x1800e4474  cmp     dword ptr [rdi+80h], 0Eh
0x1800e447b  jnz     short loc_1800E44EF
0x1800e447d  mov     rdx, [rdi+88h]
0x1800e4484  mov     rcx, cs:qword_180036228
0x1800e448b  sub     rcx, [rdx]
0x1800e448e  jnz     short loc_1800E44AC
0x1800e4490  mov     ecx, cs:dword_180036230
0x1800e4496  mov     eax, [rdx+8]
0x1800e4499  sub     rcx, rax
0x1800e449c  jnz     short loc_1800E44AC
0x1800e449e  movzx   ecx, cs:word_180036234
0x1800e44a5  movzx   eax, word ptr [rdx+0Ch]
0x1800e44a9  sub     rcx, rax
0x1800e44ac  test    rcx, rcx
0x1800e44af  jnz     short loc_1800E44EF
0x1800e44b1  lea     rcx, [rdi+0B0h]
0x1800e44b8  mov     rdx, [rsp+98h+arg_20]
0x1800e44c0  call    MinAsn1DecodeTime
0x1800e44c5  test    al, al
0x1800e44c7  jnz     short loc_1800E44D4
0x1800e44c9  mov     ebx, 0C0000428h
0x1800e44ce  mov     [rsp+98h+var_48], ebx
0x1800e44d2  jmp     short loc_1800E4518
0x1800e44d4  lea     rcx, [rdi+0F0h]
0x1800e44db  mov     r8, r12
0x1800e44de  call    MinCryptParseRevocationList
0x1800e44e3  mov     ebx, eax
0x1800e44e5  mov     [rsp+98h+var_48], eax
0x1800e44e9  test    eax, eax
0x1800e44eb  js      short loc_1800E4518
0x1800e44ed  jmp     short loc_1800E4518
0x1800e44ef  mov     ebx, 0C0000428h
0x1800e44f4  mov     [rsp+98h+var_48], ebx
0x1800e44f8  jmp     short loc_1800E4518
0x1800e44fa  mov     ebx, 0C0000428h
0x1800e44ff  mov     [rsp+98h+var_48], ebx
0x1800e4503  jmp     short loc_1800E4518
0x1800e4505  mov     ebx, eax
0x1800e4507  mov     [rsp+98h+var_48], eax
0x1800e450b  mov     r14, [rsp+98h+arg_18]
0x1800e4513  mov     rdi, [rsp+98h+var_40]
0x1800e4518  test    rdi, rdi
0x1800e451b  jz      short loc_1800E4531
0x1800e451d  mov     edx, 63734943h; Tag
0x1800e4522  mov     rcx, rdi; P
0x1800e4525  call    cs:__imp_ExFreePoolWithTag
0x1800e452c  nop     dword ptr [rax+rax+00h]
0x1800e4531  test    ebx, ebx
0x1800e4533  jns     short loc_1800E453D
0x1800e4535  mov     rcx, r14
0x1800e4538  call    MincryptFreePolicyInfo
0x1800e453d  mov     eax, ebx
0x1800e453f  add     rsp, 68h
0x1800e4543  pop     r15
0x1800e4545  pop     r14
0x1800e4547  pop     r12
0x1800e4549  pop     rdi
0x1800e454a  pop     rsi
0x1800e454b  pop     rbx
0x1800e454c  retn
```
