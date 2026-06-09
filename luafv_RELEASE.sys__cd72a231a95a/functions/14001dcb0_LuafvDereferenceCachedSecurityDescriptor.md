# LuafvDereferenceCachedSecurityDescriptor

- ea: `0x14001dcb0`
- end: `0x14001dd39`
- name: `LuafvDereferenceCachedSecurityDescriptor`
- size: `137`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001730`
- `0x14001d37c`
- `0x14001f5d0`

## callees

- `0x14001dcb0`
- `0x14001dd40`

## import_xrefs

- `FLTMGR!FltReleasePushLockEx` at `0x14001dcf7`
- `FLTMGR!FltReleasePushLockEx` at `0x14001dcf7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001dcd7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001dcd7`

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
0x14001dcb0  mov     [rsp+arg_0], rbx
0x14001dcb5  push    rdi
0x14001dcb6  sub     rsp, 20h
0x14001dcba  mov     eax, [rcx+1Ch]
0x14001dcbd  mov     rdi, rcx
0x14001dcc0  and     eax, 0Fh
0x14001dcc3  lea     rcx, qword_14000E8F0
0x14001dcca  xor     edx, edx
0x14001dccc  lea     rax, [rax+rax*2]
0x14001dcd0  lea     rbx, [rcx+rax*8]
0x14001dcd4  mov     rcx, rbx
0x14001dcd7  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14001dcde  nop     dword ptr [rax+rax+00h]
0x14001dce3  mov     eax, 0FFFFFFFFh
0x14001dce8  lock xadd [rdi+20h], eax
0x14001dced  cmp     eax, 1
0x14001dcf0  jz      short loc_14001DD0F
0x14001dcf2  xor     edx, edx
0x14001dcf4  mov     rcx, rbx
0x14001dcf7  call    cs:__imp_FltReleasePushLockEx
0x14001dcfe  nop     dword ptr [rax+rax+00h]
0x14001dd03  mov     rbx, [rsp+28h+arg_0]
0x14001dd08  add     rsp, 20h
0x14001dd0c  pop     rdi
0x14001dd0d  retn
0x14001dd0f  mov     rax, [rdi]
0x14001dd12  cmp     [rax+8], rdi
0x14001dd16  jnz     short loc_14001DD32
0x14001dd18  mov     rcx, [rdi+8]
0x14001dd1c  cmp     [rcx], rdi
0x14001dd1f  jnz     short loc_14001DD32
0x14001dd21  mov     [rcx], rax
0x14001dd24  mov     [rax+8], rcx
0x14001dd28  mov     rcx, rdi
0x14001dd2b  call    LuafvFreePool
0x14001dd30  jmp     short loc_14001DCF2
0x14001dd32  mov     ecx, 3
0x14001dd37  int     29h; Win8: RtlFailFast(ecx)
```
