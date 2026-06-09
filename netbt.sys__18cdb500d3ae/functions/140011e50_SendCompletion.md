# SendCompletion

- ea: `0x140011e50`
- end: `0x140011f41`
- name: `SendCompletion`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140011e50`
- `0x140013184`
- `0x14004025c`
- `0x140040294`

## import_xrefs

- `ntoskrnl!ExInterlockedPushEntryList` at `0x140011e8f`
- `ntoskrnl!ExInterlockedPushEntryList` at `0x140011e8f`

## pseudocode

```c
__int64 __fastcall SendCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // r9
  unsigned __int64 v6; // rax

  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  v5 = *(_QWORD *)(a2 + 8);
  if ( _bittest16((const signed __int16 *)(v5 + 10), 0xCu) )
  {
    *(_QWORD *)(v5 + 24) += 4LL;
    *(_DWORD *)(v5 + 44) += 4;
    *(_DWORD *)(v5 + 40) -= 4;
    if ( (BYTE3(xmmword_140038420) & 4) != 0 )
      WPP_SF_q(1050, 66, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids, v5);
  }
  else
  {
    *(_QWORD *)(a2 + 8) = *(_QWORD *)v5;
    ExInterlockedPushEntryList((PSINGLE_LIST_ENTRY)&Mdl, (PSINGLE_LIST_ENTRY)v5, &Lock);
  }
  v6 = *(_QWORD *)(a2 + 56);
  if ( v6 <= 4 )
  {
    *(_QWORD *)(a2 + 56) = 0;
    if ( (BYTE3(xmmword_140038420) & 4) != 0 )
      WPP_SF_(1050, 67, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids);
  }
  else
  {
    *(_QWORD *)(a2 + 56) = v6 - 4;
  }
  NbtDereferenceLowerConnection(a3, a2, a3, 87, (__int64)"minio\\netbt\\sys\\nt\\ntisol.c");
  return 0;
}

```

## disassembly

```asm
0x140011e50  mov     [rsp+arg_0], rbx
0x140011e55  push    rdi
0x140011e56  sub     rsp, 30h
0x140011e5a  cmp     byte ptr [rdx+41h], 0
0x140011e5e  mov     rdi, r8
0x140011e61  mov     rbx, rdx
0x140011e64  jnz     loc_140011F05
0x140011e6a  mov     r9, [rdx+8]
0x140011e6e  bt      word ptr [r9+0Ah], 0Ch
0x140011e75  jb      short loc_140011ED5
0x140011e77  mov     rax, [r9]
0x140011e7a  lea     r8, Lock; Lock
0x140011e81  mov     [rdx+8], rax
0x140011e85  lea     rcx, Mdl; ListHead
0x140011e8c  mov     rdx, r9; ListEntry
0x140011e8f  call    cs:__imp_ExInterlockedPushEntryList
0x140011e96  nop     dword ptr [rax+rax+00h]
0x140011e9b  mov     rax, [rbx+38h]
0x140011e9f  cmp     rax, 4
0x140011ea3  jbe     short loc_140011F15
0x140011ea5  add     rax, 0FFFFFFFFFFFFFFFCh
0x140011ea9  mov     [rbx+38h], rax
0x140011ead  lea     rax, aMinioNetbtSysN; "minio\\netbt\\sys\\nt\\ntisol.c"
0x140011eb4  mov     r9d, 1557h
0x140011eba  mov     rcx, rdi
0x140011ebd  mov     [rsp+38h+var_18], rax
0x140011ec2  call    NbtDereferenceLowerConnection
0x140011ec7  mov     rbx, [rsp+38h+arg_0]
0x140011ecc  xor     eax, eax
0x140011ece  add     rsp, 30h
0x140011ed2  pop     rdi
0x140011ed3  retn
0x140011ed5  add     qword ptr [r9+18h], 4
0x140011eda  add     dword ptr [r9+2Ch], 4
0x140011edf  add     dword ptr [r9+28h], 0FFFFFFFCh
0x140011ee4  test    byte ptr cs:xmmword_140038420+3, 4
0x140011eeb  jz      short loc_140011E9B
0x140011eed  mov     edx, 42h ; 'B'
0x140011ef2  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x140011ef9  mov     ecx, 41Ah
0x140011efe  call    WPP_SF_q
0x140011f03  jmp     short loc_140011E9B
0x140011f05  mov     rax, [rdx+0B8h]
0x140011f0c  or      byte ptr [rax+3], 1
0x140011f10  jmp     loc_140011E6A
0x140011f15  mov     qword ptr [rbx+38h], 0
0x140011f1d  test    byte ptr cs:xmmword_140038420+3, 4
0x140011f24  jz      short loc_140011EAD
0x140011f26  mov     edx, 43h ; 'C'
0x140011f2b  lea     r8, WPP_6b9f19545c09309b41b2cc145fe7b9db_Traceguids
0x140011f32  mov     ecx, 41Ah
0x140011f37  call    WPP_SF_
0x140011f3c  jmp     loc_140011EAD
```
