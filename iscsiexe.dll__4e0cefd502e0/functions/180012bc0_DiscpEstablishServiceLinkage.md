# DiscpEstablishServiceLinkage

- ea: `0x180012bc0`
- end: `0x180012bf5`
- name: `DiscpEstablishServiceLinkage`
- size: `53`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180012bc0`

## pseudocode

```c
__int64 __fastcall DiscpEstablishServiceLinkage(__int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)a1;
  if ( *(int *)a1 >= 2 )
  {
    DiscpEDLinkage = *(_OWORD *)a1;
    *(_OWORD *)&xmmword_180027870 = *(_OWORD *)(a1 + 16);
    qword_180027880 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(a1 + 32);
  }
  result = 0;
  if ( v1 < 2 )
    return 50;
  return result;
}

```

## disassembly

```asm
0x180012bc0  mov     edx, [rcx]
0x180012bc2  cmp     edx, 2
0x180012bc5  jl      short loc_180012BE9
0x180012bc7  movups  xmm0, xmmword ptr [rcx]
0x180012bca  movups  cs:DiscpEDLinkage, xmm0
0x180012bd1  movups  xmm1, xmmword ptr [rcx+10h]
0x180012bd5  movups  cs:xmmword_180027870, xmm1
0x180012bdc  movsd   xmm0, qword ptr [rcx+20h]
0x180012be1  movsd   cs:qword_180027880, xmm0
0x180012be9  xor     eax, eax
0x180012beb  cmp     edx, 2
0x180012bee  lea     ecx, [rax+32h]
0x180012bf1  cmovl   eax, ecx
0x180012bf4  retn
```
