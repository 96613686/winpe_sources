# ShouldSkipUserCacheCleanup(void *,bool *)

- ea: `0x180041d58`
- end: `0x180041dd7`
- name: `?ShouldSkipUserCacheCleanup@@YAJPEAXPEA_N@Z`
- size: `127`
- prototype: `__int64 __fastcall(PSID Sid2, bool *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180041770`
- `0x180041820`

## callees

- `0x180041d58`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180041d79`
- `ntdll!RtlAcquireResourceExclusive` at `0x180041d79`
- `ntdll!RtlReleaseResource` at `0x180041dbf`
- `ntdll!RtlReleaseResource` at `0x180041dbf`
- `ntdll!RtlEqualSid` at `0x180041da1`
- `ntdll!RtlEqualSid` at `0x180041da1`

## pseudocode

```c
__int64 __fastcall ShouldSkipUserCacheCleanup(PSID Sid2, bool *a2)
{
  struct _LIST_ENTRY *i; // rbx
  struct _LIST_ENTRY *Flink; // rcx

  *a2 = 0;
  RtlAcquireResourceExclusive(&g_UserCacheListLock, 1u);
  for ( i = g_UserCacheList.Flink; i != &g_UserCacheList; i = i->Flink )
  {
    Flink = i[15].Flink;
    if ( Flink && RtlEqualSid(Flink, Sid2) )
    {
      if ( i )
        *a2 = 1;
      break;
    }
  }
  RtlReleaseResource(&g_UserCacheListLock);
  return 0;
}

```

## disassembly

```asm
0x180041d58  mov     [rsp+arg_0], rbx
0x180041d5d  mov     [rsp+arg_8], rsi
0x180041d62  push    rdi
0x180041d63  sub     rsp, 20h
0x180041d67  mov     rdi, rdx
0x180041d6a  mov     byte ptr [rdx], 0
0x180041d6d  mov     rsi, rcx
0x180041d70  mov     dl, 1; Wait
0x180041d72  lea     rcx, ?g_UserCacheListLock@@3U_RTL_RESOURCE@@A; Resource
0x180041d79  call    cs:__imp_RtlAcquireResourceExclusive
0x180041d7f  mov     rbx, cs:?g_UserCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_UserCacheList
0x180041d86  lea     rax, ?g_UserCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_UserCacheList
0x180041d8d  cmp     rbx, rax
0x180041d90  jz      short loc_180041DB8
0x180041d92  mov     rcx, [rbx+0F0h]; Sid1
0x180041d99  test    rcx, rcx
0x180041d9c  jz      short loc_180041DAB
0x180041d9e  mov     rdx, rsi; Sid2
0x180041da1  call    cs:__imp_RtlEqualSid
0x180041da7  test    al, al
0x180041da9  jnz     short loc_180041DB0
0x180041dab  mov     rbx, [rbx]
0x180041dae  jmp     short loc_180041D86
0x180041db0  test    rbx, rbx
0x180041db3  jz      short loc_180041DB8
0x180041db5  mov     byte ptr [rdi], 1
0x180041db8  lea     rcx, ?g_UserCacheListLock@@3U_RTL_RESOURCE@@A; Resource
0x180041dbf  call    cs:__imp_RtlReleaseResource
0x180041dc5  mov     rbx, [rsp+28h+arg_0]
0x180041dca  xor     eax, eax
0x180041dcc  mov     rsi, [rsp+28h+arg_8]
0x180041dd1  add     rsp, 20h
0x180041dd5  pop     rdi
0x180041dd6  retn
```
