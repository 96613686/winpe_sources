# WSTCompareContexts(_WST_CONTEXT *,_WST_CONTEXT *)

- ea: `0x18000e8f0`
- end: `0x18000e987`
- name: `?WSTCompareContexts@@YAHPEAU_WST_CONTEXT@@0@Z`
- size: `151`
- prototype: `__int64 __fastcall(struct _WST_CONTEXT *, struct _WST_CONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cae0`

## callees

- `0x18000e8f0`
- `0x18001a390`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x18000e945`
- `ntdll!RtlCompareUnicodeString` at `0x18000e945`

## pseudocode

```c
__int64 __fastcall WSTCompareContexts(struct _WST_CONTEXT *a1, struct _WST_CONTEXT *a2)
{
  __int64 v3; // r9
  __int64 v4; // r10
  signed __int64 v5; // rcx
  __int64 result; // rax

  if ( *(_QWORD *)a1 == 0x545854434F545357LL && *(_QWORD *)a2 == 0x545854434F545357LL )
  {
    v3 = *((_QWORD *)a2 + 3);
    v4 = *((_QWORD *)a1 + 3);
    v5 = *(unsigned int *)(v4 + 40) - (unsigned __int64)*(unsigned int *)(v3 + 40);
    if ( !v5 )
    {
      v5 = *(unsigned int *)(v4 + 44) - (unsigned __int64)*(unsigned int *)(v3 + 44);
      if ( !v5 )
        v5 = RtlCompareUnicodeString((PCUNICODE_STRING)((char *)a1 + 168), (PCUNICODE_STRING)((char *)a2 + 168), 1u);
    }
    result = -1;
  }
  else
  {
    result = -1;
    v5 = -1;
  }
  if ( !v5 )
    return 0;
  if ( v5 > 0 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x18000e8f0  push    rbx
0x18000e8f2  sub     rsp, 30h
0x18000e8f6  mov     r8, rcx
0x18000e8f9  mov     rax, 545854434F545357h
0x18000e903  cmp     [rcx], rax
0x18000e906  jnz     short loc_18000E954
0x18000e908  cmp     [rdx], rax
0x18000e90b  jnz     short loc_18000E954
0x18000e90d  mov     r9, [rdx+18h]
0x18000e911  mov     r10, [rcx+18h]
0x18000e915  mov     ecx, [r10+28h]
0x18000e919  mov     eax, [r9+28h]
0x18000e91d  sub     rcx, rax
0x18000e920  mov     ebx, 1
0x18000e925  jnz     short loc_18000E94E
0x18000e927  mov     ecx, [r10+2Ch]
0x18000e92b  mov     eax, [r9+2Ch]
0x18000e92f  sub     rcx, rax
0x18000e932  jnz     short loc_18000E94E
0x18000e934  add     rdx, 0A8h; String2
0x18000e93b  lea     rcx, [r8+0A8h]; String1
0x18000e942  mov     r8b, bl; CaseInsensitive
0x18000e945  call    cs:__imp_RtlCompareUnicodeString
0x18000e94b  movsxd  rcx, eax
0x18000e94e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e952  jmp     short loc_18000E975
0x18000e954  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e958  mov     rcx, rax
0x18000e95b  mov     [rsp+38h+var_18], rax
0x18000e960  lea     ebx, [rax+2]
0x18000e963  jmp     short loc_18000E975
0x18000e965  mov     ecx, 1
0x18000e96a  mov     [rsp+38h+var_18], rcx
0x18000e96f  mov     ebx, ecx
0x18000e971  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e975  test    rcx, rcx
0x18000e978  jz      short loc_18000E97F
0x18000e97a  cmovg   eax, ebx
0x18000e97d  jmp     short loc_18000E981
0x18000e97f  xor     eax, eax
0x18000e981  add     rsp, 30h
0x18000e985  pop     rbx
0x18000e986  retn
0x18001efc0  push    rbp
0x18001efc2  sub     rsp, 20h
0x18001efc6  mov     rbp, rdx
0x18001efc9  call    ?WSTExceptionFilter@@YAKXZ; WSTExceptionFilter(void)
0x18001efce  nop
0x18001efcf  add     rsp, 20h
0x18001efd3  pop     rbp
0x18001efd4  retn
```
