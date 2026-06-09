# W3_APPLICATION::ResolveModules(void)

- ea: `0x180031534`
- end: `0x1800315c2`
- name: `?ResolveModules@W3_APPLICATION@@QEAAJXZ`
- size: `142`
- prototype: `__int64 __fastcall(W3_APPLICATION *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cf40`

## callees

- `0x18000ac10`
- `0x180031534`
- `0x180038010`

## import_xrefs

- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x18003159c`
- `iisutil!?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z` at `0x18003159c`

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
0x180031534  mov     [rsp+arg_0], rbx
0x180031539  mov     [rsp+arg_8], rsi
0x18003153e  push    rdi
0x18003153f  sub     rsp, 20h
0x180031543  cmp     byte ptr [rcx+0DBh], 0
0x18003154a  lea     rsi, [rcx+120h]
0x180031551  mov     rdi, rcx
0x180031554  jnz     short loc_1800315AF
0x180031556  lea     rdx, [rcx+8]
0x18003155a  mov     rax, rcx
0x18003155d  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180031564  neg     rax
0x180031567  sbb     r8, r8
0x18003156a  and     r8, rdx
0x18003156d  mov     edx, 400h
0x180031572  call    ?GlobalNotify@W3_SERVER@@QEAA?AW4GLOBAL_NOTIFICATION_STATUS@@KPEAVIHttpEventProvider@@@Z; W3_SERVER::GlobalNotify(ulong,IHttpEventProvider *)
0x180031577  cmp     dword ptr [rsi], 0
0x18003157a  jge     short loc_1800315A8
0x18003157c  mov     rax, [rdi]
0x18003157f  mov     rcx, rdi
0x180031582  mov     rbx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180031589  mov     rax, [rax+10h]
0x18003158d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031592  mov     rdx, rax
0x180031595  lea     rcx, [rbx+568h]
0x18003159c  call    cs:__imp_?DeletePath@TREE_HASH_TABLE@@QEAAXPEBG@Z; TREE_HASH_TABLE::DeletePath(ushort const *)
0x1800315a3  nop     dword ptr [rax+rax+00h]
0x1800315a8  mov     byte ptr [rdi+0DBh], 1
0x1800315af  mov     eax, [rsi]
0x1800315b1  mov     rsi, [rsp+28h+arg_8]
0x1800315b6  mov     rbx, [rsp+28h+arg_0]
0x1800315bb  add     rsp, 20h
0x1800315bf  pop     rdi
0x1800315c0  retn
```
