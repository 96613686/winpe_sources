# MupiCheckForProviderAvoidPath

- ea: `0x140001360`
- end: `0x1400013d8`
- name: `MupiCheckForProviderAvoidPath`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001cf8`
- `0x14001a920`

## callees

- `0x140001360`
- `0x1400013e0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14000139f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000139f`

## pseudocode

```c
char __fastcall MupiCheckForProviderAvoidPath(__int64 a1, _QWORD *a2, _BYTE *a3)
{
  UNICODE_STRING String2; // [rsp+30h] [rbp-18h] BYREF

  String2 = 0;
  MupiGetPathComponents(a1, 0, &String2, 0, 0);
  if ( RtlCompareUnicodeString(&MupiDavShareName, &String2, 1u) )
    return 0;
  if ( a2 )
    *a2 = MupiDavAvoidProviderName;
  if ( a3 )
    *a3 = 0;
  return 1;
}

```

## disassembly

```asm
0x140001360  mov     [rsp+arg_0], rbx
0x140001365  push    rdi
0x140001366  sub     rsp, 40h
0x14000136a  mov     rbx, r8
0x14000136d  mov     [rsp+48h+var_28], 0
0x140001376  mov     rdi, rdx
0x140001379  lea     r8, [rsp+48h+String2]
0x14000137e  xorps   xmm0, xmm0
0x140001381  xor     edx, edx
0x140001383  xor     r9d, r9d
0x140001386  movups  xmmword ptr [rsp+48h+String2.Length], xmm0
0x14000138b  call    MupiGetPathComponents
0x140001390  mov     r8b, 1; CaseInSensitive
0x140001393  lea     rdx, [rsp+48h+String2]; String2
0x140001398  lea     rcx, MupiDavShareName; String1
0x14000139f  call    cs:__imp_RtlCompareUnicodeString
0x1400013a6  nop     dword ptr [rax+rax+00h]
0x1400013ab  test    eax, eax
0x1400013ad  jz      short loc_1400013BD
0x1400013af  xor     al, al
0x1400013b1  mov     rbx, [rsp+48h+arg_0]
0x1400013b6  add     rsp, 40h
0x1400013ba  pop     rdi
0x1400013bb  retn
0x1400013bd  test    rdi, rdi
0x1400013c0  jz      short loc_1400013CC
0x1400013c2  lea     rax, MupiDavAvoidProviderName; "00"
0x1400013c9  mov     [rdi], rax
0x1400013cc  test    rbx, rbx
0x1400013cf  jz      short loc_1400013D4
0x1400013d1  mov     byte ptr [rbx], 0
0x1400013d4  mov     al, 1
0x1400013d6  jmp     short loc_1400013B1
```
