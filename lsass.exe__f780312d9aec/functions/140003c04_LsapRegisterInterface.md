# LsapRegisterInterface

- ea: `0x140003c04`
- end: `0x140003ce2`
- name: `LsapRegisterInterface`
- size: `222`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140002b9c`
- `0x140003570`
- `0x1400038cc`

## callees

- `0x140001a80`
- `0x14000362c`
- `0x140003c04`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x140003c43`
- `ntdll!RtlAcquireResourceExclusive` at `0x140003c43`
- `ntdll!RtlReleaseResource` at `0x140003cce`
- `ntdll!RtlReleaseResource` at `0x140003cce`

## pseudocode

```c
__int64 __fastcall LsapRegisterInterface(__int64 a1, unsigned int a2, __int64 a3)
{
  unsigned int v7; // ebx
  _QWORD *LsaHeap; // rax
  _QWORD *v9; // rcx
  _QWORD *v10; // r9

  if ( !gHasInitLsaIfConfig )
    return 3221225701LL;
  RtlAcquireResourceExclusive(&gLsaIfLock, 1u);
  if ( LsapFindRegisteredInterface(a2) )
  {
    v7 = -1073740008;
  }
  else
  {
    LsaHeap = LsapAllocateLsaHeap(0x38u);
    if ( LsaHeap )
    {
      LsaHeap[6] = a3;
      *((_DWORD *)LsaHeap + 4) = a2;
      LsaHeap[3] = a1;
      v9 = (_QWORD *)qword_14000C278;
      if ( *(__int64 **)qword_14000C278 == &gLsapIfList )
      {
        *LsaHeap = &gLsapIfList;
        v7 = 0;
        LsaHeap[1] = v9;
        *v9 = LsaHeap;
        qword_14000C278 = (__int64)LsaHeap;
        if ( !a1 )
          goto LABEL_11;
        v10 = *(_QWORD **)(a1 + 24);
        if ( *v10 == a1 + 16 )
        {
          LsaHeap[4] = a1 + 16;
          LsaHeap[5] = v10;
          *v10 = LsaHeap + 4;
          *(_QWORD *)(a1 + 24) = LsaHeap + 4;
          goto LABEL_11;
        }
      }
      __fastfail(3u);
    }
    v7 = -1073741801;
  }
LABEL_11:
  RtlReleaseResource(&gLsaIfLock);
  return v7;
}

```

## disassembly

```asm
0x140003c04  mov     [rsp+arg_0], rbx
0x140003c09  mov     [rsp+arg_8], rsi
0x140003c0e  push    rdi
0x140003c0f  sub     rsp, 20h
0x140003c13  mov     eax, cs:gHasInitLsaIfConfig
0x140003c19  mov     rsi, r8
0x140003c1c  mov     ebx, edx
0x140003c1e  mov     rdi, rcx
0x140003c21  test    eax, eax
0x140003c23  jnz     short loc_140003C3A
0x140003c25  mov     eax, 0C00000E5h
0x140003c2a  mov     rbx, [rsp+28h+arg_0]
0x140003c2f  mov     rsi, [rsp+28h+arg_8]
0x140003c34  add     rsp, 20h
0x140003c38  pop     rdi
0x140003c39  retn
0x140003c3a  mov     dl, 1; Wait
0x140003c3c  lea     rcx, gLsaIfLock; Resource
0x140003c43  call    cs:__imp_RtlAcquireResourceExclusive
0x140003c49  mov     ecx, ebx
0x140003c4b  call    LsapFindRegisteredInterface
0x140003c50  test    rax, rax
0x140003c53  jz      short loc_140003C5C
0x140003c55  mov     ebx, 0C0000718h
0x140003c5a  jmp     short loc_140003CC7
0x140003c5c  mov     ecx, 38h ; '8'
0x140003c61  call    LsapAllocateLsaHeap
0x140003c66  test    rax, rax
0x140003c69  jnz     short loc_140003C72
0x140003c6b  mov     ebx, 0C0000017h
0x140003c70  jmp     short loc_140003CC7
0x140003c72  mov     [rax+30h], rsi
0x140003c76  lea     rdx, gLsapIfList
0x140003c7d  mov     [rax+10h], ebx
0x140003c80  mov     [rax+18h], rdi
0x140003c84  mov     rcx, cs:qword_14000C278
0x140003c8b  cmp     [rcx], rdx
0x140003c8e  jnz     short loc_140003CDB
0x140003c90  mov     [rax], rdx
0x140003c93  xor     ebx, ebx
0x140003c95  mov     [rax+8], rcx
0x140003c99  mov     [rcx], rax
0x140003c9c  mov     cs:qword_14000C278, rax
0x140003ca3  test    rdi, rdi
0x140003ca6  jz      short loc_140003CC7
0x140003ca8  lea     r8, [rdi+10h]
0x140003cac  mov     r9, [r8+8]
0x140003cb0  cmp     [r9], r8
0x140003cb3  jnz     short loc_140003CDB
0x140003cb5  lea     rdx, [rax+20h]
0x140003cb9  mov     [rdx], r8
0x140003cbc  mov     [rdx+8], r9
0x140003cc0  mov     [r9], rdx
0x140003cc3  mov     [r8+8], rdx
0x140003cc7  lea     rcx, gLsaIfLock; Resource
0x140003cce  call    cs:__imp_RtlReleaseResource
0x140003cd4  mov     eax, ebx
0x140003cd6  jmp     loc_140003C2A
0x140003cdb  mov     ecx, 3
0x140003ce0  int     29h; Win8: RtlFailFast(ecx)
```
