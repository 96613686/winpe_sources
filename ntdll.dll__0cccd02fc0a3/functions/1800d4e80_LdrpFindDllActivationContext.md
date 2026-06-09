# LdrpFindDllActivationContext

- ea: `0x1800d4e80`
- end: `0x1800d502d`
- name: `LdrpFindDllActivationContext`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18011a39c`

## callees

- `0x18001b530`
- `0x18001eb80`
- `0x1800d4e80`
- `0x18016f020`

## string_xrefs

- `0x1800d4efe`: `LdrpFindDllActivationContext`
- `0x1800d4f4f`: `LdrpFindDllActivationContext`
- `0x1800d4f05`: `Probing for the manifest of DLL "%wZ" failed with status 0x%08lx\n`

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
0x1800d4e80  push    rbx
0x1800d4e82  sub     rsp, 40h
0x1800d4e86  xor     eax, eax
0x1800d4e88  mov     [rsp+48h+arg_8], 0
0x1800d4e91  cmp     cs:LdrpManifestProberRoutine, rax
0x1800d4e98  mov     rbx, rcx
0x1800d4e9b  jz      loc_1800D4F6E
0x1800d4ea1  mov     rcx, gs:60h
0x1800d4eaa  mov     rdx, cs:LdrpImageEntry
0x1800d4eb1  cmp     rbx, rdx
0x1800d4eb4  jz      loc_1800D4FA9
0x1800d4eba  mov     rax, [rbx+50h]
0x1800d4ebe  mov     [rsp+48h+arg_0], rdi
0x1800d4ec3  cmp     rbx, rdx
0x1800d4ec6  jz      loc_1800D4FDA
0x1800d4ecc  mov     rcx, [rbx+30h]
0x1800d4ed0  lea     r8, [rsp+48h+arg_8]
0x1800d4ed5  mov     rdx, rax
0x1800d4ed8  mov     rax, cs:LdrpManifestProberRoutine
0x1800d4edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d4ee4  mov     edi, eax
0x1800d4ee6  cmp     eax, 0C000000Fh
0x1800d4eeb  jnz     loc_1800D4F75
0x1800d4ef1  lea     rax, [rbx+48h]
0x1800d4ef5  mov     [rsp+48h+var_18], edi
0x1800d4ef9  mov     qword ptr [rsp+48h+ArgList], rax; ArgList
0x1800d4efe  lea     r8, aLdrpfinddllact; "LdrpFindDllActivationContext"
0x1800d4f05  lea     rax, aProbingForTheM; "Probing for the manifest of DLL \"%wZ\""...
0x1800d4f0c  mov     r9d, 2; int
0x1800d4f12  mov     edx, 2E7h; int
0x1800d4f17  mov     [rsp+48h+Format], rax; Format
0x1800d4f1c  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800d4f23  call    LdrpLogInternal
0x1800d4f28  xor     edi, edi
0x1800d4f2a  mov     rax, [rsp+48h+arg_8]
0x1800d4f2f  test    rax, rax
0x1800d4f32  jnz     loc_1800D4FB8
0x1800d4f38  test    edi, edi
0x1800d4f3a  jns     short loc_1800D4F67
0x1800d4f3c  lea     rax, aQueryingTheAct; "Querying the active activation context "...
0x1800d4f43  mov     dword ptr [rsp+48h+ArgList], edi; ArgList
0x1800d4f47  xor     r9d, r9d; int
0x1800d4f4a  mov     [rsp+48h+Format], rax; Format
0x1800d4f4f  lea     r8, aLdrpfinddllact; "LdrpFindDllActivationContext"
0x1800d4f56  mov     edx, 304h; int
0x1800d4f5b  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800d4f62  call    LdrpLogInternal
0x1800d4f67  mov     eax, edi
0x1800d4f69  mov     rdi, [rsp+48h+arg_0]
0x1800d4f6e  add     rsp, 40h
0x1800d4f72  pop     rbx
0x1800d4f73  retn
0x1800d4f75  lea     ecx, [rax+3FFFFF77h]
0x1800d4f7b  cmp     ecx, 2
0x1800d4f7e  jbe     loc_1800D4EF1
0x1800d4f84  cmp     edi, 0C00000BBh
0x1800d4f8a  jz      loc_1800D4EF1
0x1800d4f90  cmp     edi, 0C0000002h
0x1800d4f96  jz      loc_1800D4EF1
0x1800d4f9c  cmp     edi, 0C0000204h
0x1800d4fa2  jnz     short loc_1800D4F2A
0x1800d4fa4  jmp     loc_1800D4EF1
0x1800d4fa9  cmp     [rcx+2F8h], rax
0x1800d4fb0  jz      loc_1800D4EBA
0x1800d4fb6  jmp     short loc_1800D4F6E
0x1800d4fb8  mov     rcx, [rbx+88h]
0x1800d4fbf  test    rcx, rcx
0x1800d4fc2  jz      short loc_1800D4FCE
0x1800d4fc4  call    RtlReleaseActivationContext
0x1800d4fc9  mov     rax, [rsp+48h+arg_8]
0x1800d4fce  mov     [rbx+88h], rax
0x1800d4fd5  jmp     loc_1800D4F38
0x1800d4fda  cmp     word ptr [rax], 5Ch ; '\'
0x1800d4fde  jnz     loc_1800D4ECC
0x1800d4fe4  cmp     word ptr [rax+2], 3Fh ; '?'
0x1800d4fe9  jnz     loc_1800D4ECC
0x1800d4fef  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800d4ff4  jnz     loc_1800D4ECC
0x1800d4ffa  cmp     word ptr [rax+6], 5Ch ; '\'
0x1800d4fff  jnz     loc_1800D4ECC
0x1800d5005  cmp     word ptr [rax+8], 0
0x1800d500a  lea     rcx, [rax+8]
0x1800d500e  jz      loc_1800D4ECC
0x1800d5014  cmp     word ptr [rax+0Ah], 3Ah ; ':'
0x1800d5019  jnz     loc_1800D4ECC
0x1800d501f  cmp     word ptr [rax+0Ch], 5Ch ; '\'
0x1800d5024  cmovz   rax, rcx
0x1800d5028  jmp     loc_1800D4ECC
```
