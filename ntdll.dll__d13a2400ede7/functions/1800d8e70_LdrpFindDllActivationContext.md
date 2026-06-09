# LdrpFindDllActivationContext

- ea: `0x1800d8e70`
- end: `0x1800d901d`
- name: `LdrpFindDllActivationContext`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18011ae8c`

## callees

- `0x18001b530`
- `0x18001eb80`
- `0x1800d8e70`
- `0x18016f020`

## string_xrefs

- `0x1800d8eee`: `LdrpFindDllActivationContext`
- `0x1800d8f3f`: `LdrpFindDllActivationContext`
- `0x1800d8ef5`: `Probing for the manifest of DLL "%wZ" failed with status 0x%08lx\n`

## pseudocode

```c
__int64 __fastcall LdrpFindDllActivationContext(_QWORD *a1)
{
  __int64 result; // rax
  struct _PEB *v3; // rcx
  _WORD *v4; // rax
  int v5; // eax
  int ArgList; // edi
  __int64 v7; // rax
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  result = 0;
  v8 = 0;
  if ( LdrpManifestProberRoutine )
  {
    v3 = NtCurrentPeb();
    if ( a1 != (_QWORD *)LdrpImageEntry || !v3->ActivationContextData )
    {
      v4 = (_WORD *)a1[10];
      if ( a1 == (_QWORD *)LdrpImageEntry
        && *v4 == 92
        && v4[1] == 63
        && v4[2] == 63
        && v4[3] == 92
        && v4[4]
        && v4[5] == 58
        && v4[6] == 92 )
      {
        v4 += 4;
      }
      v5 = ((__int64 (__fastcall *)(_QWORD, _WORD *, __int64 *))LdrpManifestProberRoutine)(a1[6], v4, &v8);
      ArgList = v5;
      if ( v5 == -1073741809
        || (unsigned int)(v5 + 1073741687) <= 2
        || v5 == -1073741637
        || v5 == -1073741822
        || v5 == -1073741308 )
      {
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrsnap.c",
          743,
          (int)"LdrpFindDllActivationContext",
          2,
          "Probing for the manifest of DLL \"%wZ\" failed with status 0x%08lx\n",
          (_BYTE)a1 + 72);
        ArgList = 0;
      }
      v7 = v8;
      if ( v8 )
      {
        if ( a1[17] )
        {
          RtlReleaseActivationContext();
          v7 = v8;
        }
        a1[17] = v7;
      }
      if ( ArgList < 0 )
        LdrpLogInternal(
          (int)"minkernel\\ldr\\ldrsnap.c",
          772,
          (int)"LdrpFindDllActivationContext",
          0,
          "Querying the active activation context failed with status 0x%08lx\n",
          ArgList);
      return (unsigned int)ArgList;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800d8e70  push    rbx
0x1800d8e72  sub     rsp, 40h
0x1800d8e76  xor     eax, eax
0x1800d8e78  mov     [rsp+48h+arg_8], 0
0x1800d8e81  cmp     cs:LdrpManifestProberRoutine, rax
0x1800d8e88  mov     rbx, rcx
0x1800d8e8b  jz      loc_1800D8F5E
0x1800d8e91  mov     rcx, gs:60h
0x1800d8e9a  mov     rdx, cs:LdrpImageEntry
0x1800d8ea1  cmp     rbx, rdx
0x1800d8ea4  jz      loc_1800D8F99
0x1800d8eaa  mov     rax, [rbx+50h]
0x1800d8eae  mov     [rsp+48h+arg_0], rdi
0x1800d8eb3  cmp     rbx, rdx
0x1800d8eb6  jz      loc_1800D8FCA
0x1800d8ebc  mov     rcx, [rbx+30h]
0x1800d8ec0  lea     r8, [rsp+48h+arg_8]
0x1800d8ec5  mov     rdx, rax
0x1800d8ec8  mov     rax, cs:LdrpManifestProberRoutine
0x1800d8ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8ed4  mov     edi, eax
0x1800d8ed6  cmp     eax, 0C000000Fh
0x1800d8edb  jnz     loc_1800D8F65
0x1800d8ee1  lea     rax, [rbx+48h]
0x1800d8ee5  mov     [rsp+48h+var_18], edi
0x1800d8ee9  mov     qword ptr [rsp+48h+ArgList], rax; ArgList
0x1800d8eee  lea     r8, aLdrpfinddllact; "LdrpFindDllActivationContext"
0x1800d8ef5  lea     rax, aProbingForTheM; "Probing for the manifest of DLL \"%wZ\""...
0x1800d8efc  mov     r9d, 2; int
0x1800d8f02  mov     edx, 2E7h; int
0x1800d8f07  mov     [rsp+48h+Format], rax; Format
0x1800d8f0c  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800d8f13  call    LdrpLogInternal
0x1800d8f18  xor     edi, edi
0x1800d8f1a  mov     rax, [rsp+48h+arg_8]
0x1800d8f1f  test    rax, rax
0x1800d8f22  jnz     loc_1800D8FA8
0x1800d8f28  test    edi, edi
0x1800d8f2a  jns     short loc_1800D8F57
0x1800d8f2c  lea     rax, aQueryingTheAct; "Querying the active activation context "...
0x1800d8f33  mov     dword ptr [rsp+48h+ArgList], edi; ArgList
0x1800d8f37  xor     r9d, r9d; int
0x1800d8f3a  mov     [rsp+48h+Format], rax; Format
0x1800d8f3f  lea     r8, aLdrpfinddllact; "LdrpFindDllActivationContext"
0x1800d8f46  mov     edx, 304h; int
0x1800d8f4b  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800d8f52  call    LdrpLogInternal
0x1800d8f57  mov     eax, edi
0x1800d8f59  mov     rdi, [rsp+48h+arg_0]
0x1800d8f5e  add     rsp, 40h
0x1800d8f62  pop     rbx
0x1800d8f63  retn
0x1800d8f65  lea     ecx, [rax+3FFFFF77h]
0x1800d8f6b  cmp     ecx, 2
0x1800d8f6e  jbe     loc_1800D8EE1
0x1800d8f74  cmp     edi, 0C00000BBh
0x1800d8f7a  jz      loc_1800D8EE1
0x1800d8f80  cmp     edi, 0C0000002h
0x1800d8f86  jz      loc_1800D8EE1
0x1800d8f8c  cmp     edi, 0C0000204h
0x1800d8f92  jnz     short loc_1800D8F1A
0x1800d8f94  jmp     loc_1800D8EE1
0x1800d8f99  cmp     [rcx+2F8h], rax
0x1800d8fa0  jz      loc_1800D8EAA
0x1800d8fa6  jmp     short loc_1800D8F5E
0x1800d8fa8  mov     rcx, [rbx+88h]
0x1800d8faf  test    rcx, rcx
0x1800d8fb2  jz      short loc_1800D8FBE
0x1800d8fb4  call    RtlReleaseActivationContext
0x1800d8fb9  mov     rax, [rsp+48h+arg_8]
0x1800d8fbe  mov     [rbx+88h], rax
0x1800d8fc5  jmp     loc_1800D8F28
0x1800d8fca  cmp     word ptr [rax], 5Ch ; '\'
0x1800d8fce  jnz     loc_1800D8EBC
0x1800d8fd4  cmp     word ptr [rax+2], 3Fh ; '?'
0x1800d8fd9  jnz     loc_1800D8EBC
0x1800d8fdf  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800d8fe4  jnz     loc_1800D8EBC
0x1800d8fea  cmp     word ptr [rax+6], 5Ch ; '\'
0x1800d8fef  jnz     loc_1800D8EBC
0x1800d8ff5  cmp     word ptr [rax+8], 0
0x1800d8ffa  lea     rcx, [rax+8]
0x1800d8ffe  jz      loc_1800D8EBC
0x1800d9004  cmp     word ptr [rax+0Ah], 3Ah ; ':'
0x1800d9009  jnz     loc_1800D8EBC
0x1800d900f  cmp     word ptr [rax+0Ch], 5Ch ; '\'
0x1800d9014  cmovz   rax, rcx
0x1800d9018  jmp     loc_1800D8EBC
```
