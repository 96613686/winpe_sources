# W3_APPLICATION::ResolveModules(void)

- ea: `0x18002e960`
- end: `0x18002e9e7`
- name: `?ResolveModules@W3_APPLICATION@@QEAAJXZ`
- size: `135`
- prototype: `__int64 __fastcall(W3_APPLICATION *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000bfe0`

## callees

- `0x18000a340`
- `0x18002e960`
- `0x180035010`

## import_xrefs

- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x18002e9c8`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x18002e9c8`

## pseudocode

```c
__int64 __fastcall W3_APPLICATION::ResolveModules(W3_APPLICATION *this)
{
  unsigned int *v1; // rsi
  W3_SERVER *v3; // rbx
  const unsigned __int16 *v4; // rax

  v1 = (unsigned int *)((char *)this + 288);
  if ( !*((_BYTE *)this + 219) )
  {
    W3_SERVER::GlobalNotify((__int64)g_pW3Server, 0x400u, ((unsigned __int64)this + 8) & -(__int64)(this != 0));
    if ( (*v1 & 0x80000000) != 0 )
    {
      v3 = g_pW3Server;
      v4 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(W3_APPLICATION *))(*(_QWORD *)this + 16LL))(this);
      TREE_HASH_TABLE::DeletePath((W3_SERVER *)((char *)v3 + 1384), v4);
    }
    *((_BYTE *)this + 219) = 1;
  }
  return *v1;
}

```

## disassembly

```asm
0x18002e960  mov     [rsp+arg_0], rbx
0x18002e965  mov     [rsp+arg_8], rsi
0x18002e96a  push    rdi
0x18002e96b  sub     rsp, 20h
0x18002e96f  cmp     byte ptr [rcx+0DBh], 0
0x18002e976  lea     rsi, [rcx+120h]
0x18002e97d  mov     rdi, rcx
0x18002e980  jnz     short loc_18002E9D5
0x18002e982  lea     rdx, [rcx+8]
0x18002e986  mov     rax, rcx
0x18002e989  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18002e990  neg     rax
0x18002e993  sbb     r8, r8
0x18002e996  and     r8, rdx
0x18002e999  mov     edx, 400h
0x18002e99e  call    ?GlobalNotify@W3_SERVER@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; W3_SERVER::GlobalNotify(ulong,IHttpEventProvider *)
0x18002e9a3  cmp     dword ptr [rsi], 0
0x18002e9a6  jge     short loc_18002E9CE
0x18002e9a8  mov     rax, [rdi]
0x18002e9ab  mov     rcx, rdi
0x18002e9ae  mov     rbx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18002e9b5  mov     rax, [rax+10h]
0x18002e9b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e9be  mov     rdx, rax
0x18002e9c1  lea     rcx, [rbx+568h]
0x18002e9c8  call    cs:__imp_?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z; TREE_HASH_TABLE::DeletePath(ushort const *)
0x18002e9ce  mov     byte ptr [rdi+0DBh], 1
0x18002e9d5  mov     eax, [rsi]
0x18002e9d7  mov     rsi, [rsp+28h+arg_8]
0x18002e9dc  mov     rbx, [rsp+28h+arg_0]
0x18002e9e1  add     rsp, 20h
0x18002e9e5  pop     rdi
0x18002e9e6  retn
```
