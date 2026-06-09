# NsippCleanupNotification

- ea: `0x140005b04`
- end: `0x140005bb2`
- name: `NsippCleanupNotification`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14000d180`

## callees

- `0x140005b04`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140005b8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005b8a`
- `NETIO!NsiDeregisterChangeNotificationEx` at `0x140005b77`
- `NETIO!NsiDeregisterChangeNotificationEx` at `0x140005b77`

## pseudocode

```c
__int64 NsippCleanupNotification()
{
  unsigned int v0; // edi
  char *v1; // rbx
  __int64 v2; // rax
  __int128 v4; // [rsp+20h] [rbp-38h] BYREF
  __int128 v5; // [rsp+30h] [rbp-28h]
  int v6; // [rsp+40h] [rbp-18h]

  v6 = 0;
  v4 = 0;
  v0 = 0;
  v5 = 0;
  while ( 1 )
  {
    v1 = (char *)NsippNotificationHandleList;
    if ( NsippNotificationHandleList == &NsippNotificationHandleList )
      break;
    if ( *((PVOID **)NsippNotificationHandleList + 1) != &NsippNotificationHandleList
      || (v2 = *(_QWORD *)NsippNotificationHandleList,
          *(PVOID *)(*(_QWORD *)NsippNotificationHandleList + 8LL) != NsippNotificationHandleList) )
    {
      __fastfail(3u);
    }
    NsippNotificationHandleList = *(PVOID *)NsippNotificationHandleList;
    *(_QWORD *)(v2 + 8) = &NsippNotificationHandleList;
    v4 = *(_OWORD *)(v1 + 24);
    v5 = *(_OWORD *)(v1 + 40);
    v0 = NsiDeregisterChangeNotificationEx(&v4);
    ExFreePoolWithTag(v1, 0);
  }
  return v0;
}

```

## disassembly

```asm
0x140005b04  mov     [rsp+arg_0], rbx
0x140005b09  mov     [rsp+arg_8], rsi
0x140005b0e  push    rdi
0x140005b0f  sub     rsp, 50h
0x140005b13  xor     eax, eax
0x140005b15  lea     rsi, NsippNotificationHandleList
0x140005b1c  xorps   xmm0, xmm0
0x140005b1f  mov     [rsp+58h+var_18], eax
0x140005b23  movups  [rsp+58h+var_38], xmm0
0x140005b28  xor     edi, edi
0x140005b2a  movups  [rsp+58h+var_28], xmm0
0x140005b2f  mov     rbx, cs:NsippNotificationHandleList
0x140005b36  cmp     rbx, rsi
0x140005b39  jz      short loc_140005B9F
0x140005b3b  cmp     [rbx+8], rsi
0x140005b3f  jnz     short loc_140005B98
0x140005b41  mov     rax, [rbx]
0x140005b44  cmp     [rax+8], rbx
0x140005b48  jnz     short loc_140005B98
0x140005b4a  mov     cs:NsippNotificationHandleList, rax
0x140005b51  lea     rcx, [rsp+58h+var_38]
0x140005b56  mov     [rax+8], rsi
0x140005b5a  movups  xmm0, xmmword ptr [rbx+18h]
0x140005b5e  movups  [rsp+58h+var_38], xmm0
0x140005b63  movsd   xmm1, qword ptr [rbx+28h]
0x140005b68  movsd   qword ptr [rsp+58h+var_28], xmm1
0x140005b6e  mov     rax, [rbx+30h]
0x140005b72  mov     qword ptr [rsp+58h+var_28+8], rax
0x140005b77  call    cs:__imp_NsiDeregisterChangeNotificationEx
0x140005b7e  nop     dword ptr [rax+rax+00h]
0x140005b83  xor     edx, edx; Tag
0x140005b85  mov     rcx, rbx; P
0x140005b88  mov     edi, eax
0x140005b8a  call    cs:__imp_ExFreePoolWithTag
0x140005b91  nop     dword ptr [rax+rax+00h]
0x140005b96  jmp     short loc_140005B2F
0x140005b98  mov     ecx, 3
0x140005b9d  int     29h; Win8: RtlFailFast(ecx)
0x140005b9f  mov     rbx, [rsp+58h+arg_0]
0x140005ba4  mov     eax, edi
0x140005ba6  mov     rsi, [rsp+58h+arg_8]
0x140005bab  add     rsp, 50h
0x140005baf  pop     rdi
0x140005bb0  retn
```
