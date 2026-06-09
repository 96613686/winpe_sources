# LsaApLogonTerminated

- ea: `0x18000b890`
- end: `0x18000b959`
- name: `LsaApLogonTerminated`
- size: `201`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800193e0`
- `0x18001a470`

## callees

- `0x18000b890`
- `0x18000c630`
- `0x18000ceb0`
- `0x18006d010`

## import_xrefs

- `ntdll!RtlConvertSharedToExclusive` at `0x18000b8fb`
- `ntdll!RtlConvertSharedToExclusive` at `0x18000b8fb`
- `ntdll!RtlAvlRemoveNode` at `0x18000b925`
- `ntdll!RtlAvlRemoveNode` at `0x18000b925`
- `ntdll!RtlReleaseResource` at `0x18000b8e5`
- `ntdll!RtlReleaseResource` at `0x18000b932`
- `ntdll!RtlReleaseResource` at `0x18000b8e5`
- `ntdll!RtlReleaseResource` at `0x18000b932`
- `ntdll!RtlAcquireResourceShared` at `0x18000b8a6`
- `ntdll!RtlAcquireResourceShared` at `0x18000b8a6`

## pseudocode

```c
void __fastcall LsaApLogonTerminated(void *a1)
{
  struct _RTL_BALANCED_NODE *v2; // rbx
  int active; // eax
  char *v4; // rbx
  __int64 v5; // rcx
  char **v6; // rax

  RtlAcquireResourceShared(&NlpActiveLogonLock, 1u);
  v2 = NlpActiveLogonTable;
  while ( v2 )
  {
    active = NlpActiveLogonCompare(a1, v2);
    if ( active < 0 )
    {
      v2 = v2->Children[0];
    }
    else
    {
      if ( active <= 0 )
        break;
      v2 = v2->Children[1];
    }
  }
  v4 = (char *)((unsigned __int64)&v2[-1].Children[1] & -(__int64)(v2 != 0));
  if ( v4 )
  {
    RtlConvertSharedToExclusive(&NlpActiveLogonLock);
    v5 = *(_QWORD *)v4;
    if ( *(char **)(*(_QWORD *)v4 + 8LL) != v4 || (v6 = (char **)*((_QWORD *)v4 + 1), *v6 != v4) )
      __fastfail(3u);
    *v6 = (char *)v5;
    *(_QWORD *)(v5 + 8) = v6;
    RtlAvlRemoveNode(&NlpActiveLogonTable, v4 + 16);
    RtlReleaseResource(&NlpActiveLogonLock);
    NlpDeletePrimaryCredential(v4 + 44);
    ((void (__fastcall *)(char *))qword_180088398)(v4);
  }
  else
  {
    RtlReleaseResource(&NlpActiveLogonLock);
  }
}

```

## disassembly

```asm
0x18000b890  mov     [rsp+arg_0], rbx
0x18000b895  push    rdi
0x18000b896  sub     rsp, 20h
0x18000b89a  mov     rdi, rcx
0x18000b89d  mov     dl, 1; Wait
0x18000b89f  lea     rcx, NlpActiveLogonLock; Resource
0x18000b8a6  call    cs:__imp_RtlAcquireResourceShared
0x18000b8ac  mov     rbx, cs:NlpActiveLogonTable
0x18000b8b3  jmp     short loc_18000B8CA
0x18000b8b5  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x18000b8b8  mov     rcx, rdi; void *
0x18000b8bb  call    ?NlpActiveLogonCompare@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; NlpActiveLogonCompare(void *,_RTL_BALANCED_NODE *)
0x18000b8c0  test    eax, eax
0x18000b8c2  js      short loc_18000B8F6
0x18000b8c4  jle     short loc_18000B8CF
0x18000b8c6  mov     rbx, [rbx+8]
0x18000b8ca  test    rbx, rbx
0x18000b8cd  jnz     short loc_18000B8B5
0x18000b8cf  lea     rax, [rbx-10h]
0x18000b8d3  neg     rbx
0x18000b8d6  lea     rcx, NlpActiveLogonLock; Resource
0x18000b8dd  sbb     rbx, rbx
0x18000b8e0  and     rbx, rax
0x18000b8e3  jnz     short loc_18000B8FB
0x18000b8e5  call    cs:__imp_RtlReleaseResource
0x18000b8eb  mov     rbx, [rsp+28h+arg_0]
0x18000b8f0  add     rsp, 20h
0x18000b8f4  pop     rdi
0x18000b8f5  retn
0x18000b8f6  mov     rbx, [rbx]
0x18000b8f9  jmp     short loc_18000B8CA
0x18000b8fb  call    cs:__imp_RtlConvertSharedToExclusive
0x18000b901  mov     rcx, [rbx]
0x18000b904  cmp     [rcx+8], rbx
0x18000b908  jnz     short loc_18000B952
0x18000b90a  mov     rax, [rbx+8]
0x18000b90e  cmp     [rax], rbx
0x18000b911  jnz     short loc_18000B952
0x18000b913  mov     [rax], rcx
0x18000b916  lea     rdx, [rbx+10h]
0x18000b91a  mov     [rcx+8], rax
0x18000b91e  lea     rcx, NlpActiveLogonTable
0x18000b925  call    cs:__imp_RtlAvlRemoveNode
0x18000b92b  lea     rcx, NlpActiveLogonLock; Resource
0x18000b932  call    cs:__imp_RtlReleaseResource
0x18000b938  lea     rcx, [rbx+2Ch]
0x18000b93c  call    NlpDeletePrimaryCredential
0x18000b941  mov     rax, cs:qword_180088398
0x18000b948  mov     rcx, rbx
0x18000b94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b950  jmp     short loc_18000B8EB
0x18000b952  mov     ecx, 3
0x18000b957  int     29h; Win8: RtlFailFast(ecx)
```
