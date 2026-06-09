# Container::Manager::Common::CoalesceActivityNotificationQueue(_CMS_ACTIVITY_NOTIFICATION const &,Csl::BlockingBoundedQueue<_CMS_ACTIVITY_NOTIFICATION,2> &,void *)

- ea: `0x180004410`
- end: `0x1800044aa`
- name: `?CoalesceActivityNotificationQueue@Common@Manager@Container@@YA_NAEBU_CMS_ACTIVITY_NOTIFICATION@@AEAV?$BlockingBoundedQueue@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@PEAX@Z`
- size: `154`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004410`
- `0x1800048a0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180004488`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180004488`

## pseudocode

```c
char __fastcall Container::Manager::Common::CoalesceActivityNotificationQueue(
        _DWORD *a1,
        RTL_CONDITION_VARIABLE *a2,
        __int64 a3,
        const char *a4)
{
  PVOID Ptr; // rcx
  unsigned __int64 i; // r8
  unsigned __int64 j; // rax
  char v7; // cl
  PVOID v8; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *a1 == 1 )
  {
    Ptr = a2[7].Ptr;
    for ( i = 0; (PVOID)i != Ptr; ++i )
    {
      if ( i >= (unsigned __int64)Ptr )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xFF,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslBuffer.h",
          a4);
      if ( LODWORD(a2[(((unsigned __int8)i + (unsigned __int8)a2[5].Ptr) & 1) + 3].Ptr) == 1 )
      {
        for ( j = (unsigned __int64)Ptr - 1; i < j; j = (unsigned __int64)a2[7].Ptr - 1 )
        {
          v7 = (char)a2[5].Ptr + i++;
          a2[(v7 & 1) + 3] = a2[((v7 - 1) & 1) + 3];
        }
        v8 = a2[6].Ptr;
        --a2[7].Ptr;
        a2[6].Ptr = (PVOID)(((_BYTE)v8 - 1) & 1);
        WakeConditionVariable(a2 + 1);
        return 1;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180004410  sub     rsp, 28h
0x180004414  cmp     dword ptr [rcx], 1
0x180004417  jnz     short loc_18000448E
0x180004419  mov     rcx, [rdx+38h]
0x18000441d  xor     r8d, r8d
0x180004420  cmp     r8, rcx
0x180004423  jz      short loc_18000448E
0x180004425  mov     rax, [rsp+28h]
0x18000442a  jnb     short loc_180004495
0x18000442c  mov     rax, [rdx+28h]
0x180004430  add     rax, r8
0x180004433  and     eax, 1
0x180004436  cmp     dword ptr [rdx+rax*8+18h], 1
0x18000443b  jz      short loc_180004442
0x18000443d  inc     r8
0x180004440  jmp     short loc_180004420
0x180004442  lea     rax, [rcx-1]
0x180004446  jmp     short loc_18000446D
0x180004448  mov     rcx, [rdx+28h]
0x18000444c  add     rcx, r8
0x18000444f  inc     r8
0x180004452  lea     rax, [rcx-1]
0x180004456  and     ecx, 1
0x180004459  and     eax, 1
0x18000445c  mov     rax, [rdx+rax*8+18h]
0x180004461  mov     [rdx+rcx*8+18h], rax
0x180004466  mov     rax, [rdx+38h]
0x18000446a  dec     rax
0x18000446d  cmp     r8, rax
0x180004470  jb      short loc_180004448
0x180004472  mov     rax, [rdx+30h]
0x180004476  lea     rcx, [rdx+8]; ConditionVariable
0x18000447a  dec     qword ptr [rdx+38h]
0x18000447e  dec     rax
0x180004481  and     eax, 1
0x180004484  mov     [rdx+30h], rax
0x180004488  call    cs:__imp_WakeConditionVariable
0x18000448e  mov     al, 1
0x180004490  add     rsp, 28h
0x180004494  retn
0x180004495  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000449c  mov     edx, 0FFh; void *
0x1800044a1  mov     rcx, rax; this
0x1800044a4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
