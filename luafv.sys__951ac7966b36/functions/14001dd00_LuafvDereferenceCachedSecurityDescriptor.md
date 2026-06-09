# LuafvDereferenceCachedSecurityDescriptor

- ea: `0x14001dd00`
- end: `0x14001dd89`
- name: `LuafvDereferenceCachedSecurityDescriptor`
- size: `137`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001730`
- `0x14001d3cc`
- `0x14001f620`

## callees

- `0x14001dd00`
- `0x14001dd90`

## import_xrefs

- `FLTMGR!FltReleasePushLockEx` at `0x14001dd47`
- `FLTMGR!FltReleasePushLockEx` at `0x14001dd47`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001dd27`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001dd27`

## pseudocode

```c
__int64 __fastcall LuafvDereferenceCachedSecurityDescriptor(__int64 *a1)
{
  __int64 *v2; // rbx
  __int64 *v4; // rax
  __int64 **v5; // rcx

  v2 = &qword_14000E8F0[3 * (*((_DWORD *)a1 + 7) & 0xF)];
  FltAcquirePushLockExclusiveEx(v2, 0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 8, 0xFFFFFFFF) == 1 )
  {
    v4 = (__int64 *)*a1;
    if ( *(__int64 **)(*a1 + 8) != a1 || (v5 = (__int64 **)a1[1], *v5 != a1) )
      __fastfail(3u);
    *v5 = v4;
    v4[1] = (__int64)v5;
    LuafvFreePool(a1);
  }
  return FltReleasePushLockEx(v2, 0);
}

```

## disassembly

```asm
0x14001dd00  mov     [rsp+arg_0], rbx
0x14001dd05  push    rdi
0x14001dd06  sub     rsp, 20h
0x14001dd0a  mov     eax, [rcx+1Ch]
0x14001dd0d  mov     rdi, rcx
0x14001dd10  and     eax, 0Fh
0x14001dd13  lea     rcx, qword_14000E8F0
0x14001dd1a  xor     edx, edx
0x14001dd1c  lea     rax, [rax+rax*2]
0x14001dd20  lea     rbx, [rcx+rax*8]
0x14001dd24  mov     rcx, rbx
0x14001dd27  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001dd2e  nop     dword ptr [rax+rax+00h]
0x14001dd33  mov     eax, 0FFFFFFFFh
0x14001dd38  lock xadd [rdi+20h], eax
0x14001dd3d  cmp     eax, 1
0x14001dd40  jz      short loc_14001DD5F
0x14001dd42  xor     edx, edx
0x14001dd44  mov     rcx, rbx
0x14001dd47  call    cs:__imp_FltReleasePushLockEx
0x14001dd4e  nop     dword ptr [rax+rax+00h]
0x14001dd53  mov     rbx, [rsp+28h+arg_0]
0x14001dd58  add     rsp, 20h
0x14001dd5c  pop     rdi
0x14001dd5d  retn
0x14001dd5f  mov     rax, [rdi]
0x14001dd62  cmp     [rax+8], rdi
0x14001dd66  jnz     short loc_14001DD82
0x14001dd68  mov     rcx, [rdi+8]
0x14001dd6c  cmp     [rcx], rdi
0x14001dd6f  jnz     short loc_14001DD82
0x14001dd71  mov     [rcx], rax
0x14001dd74  mov     [rax+8], rcx
0x14001dd78  mov     rcx, rdi
0x14001dd7b  call    LuafvFreePool
0x14001dd80  jmp     short loc_14001DD42
0x14001dd82  mov     ecx, 3
0x14001dd87  int     29h; Win8: RtlFailFast(ecx)
```
