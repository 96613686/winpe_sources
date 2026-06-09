# PCW_USER_REGISTRATION::Disconnect(void)

- ea: `0x14000c08c`
- end: `0x14000c1ac`
- name: `?Disconnect@PCW_USER_REGISTRATION@@QEAA_NXZ`
- size: `288`
- prototype: `bool __fastcall(PVOID Object)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a320`
- `0x14000bc80`
- `0x14000ca60`

## callees

- `0x14000b76c`
- `0x14000c08c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c09c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000c09c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c163`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000c163`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c0ae`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000c0ae`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c157`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000c157`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c17b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c18f`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c17b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000c18f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c129`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c0f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c129`

## pseudocode

```c
char __fastcall PCW_USER_REGISTRATION::Disconnect(char *Object)
{
  char v2; // r15
  _QWORD **v3; // rsi
  _QWORD *v4; // rcx
  _QWORD *v5; // rax
  volatile signed __int32 *v6; // rbx
  void *v7; // rsi
  char v8; // bp
  char v9; // bl

  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(Object + 32, 0);
  v2 = Object[93];
  v3 = (_QWORD **)(Object + 64);
  *(_WORD *)(Object + 93) = 1;
  while ( 1 )
  {
    v4 = *v3;
    if ( *v3 == v3 )
      break;
    if ( (_QWORD **)v4[1] != v3 || (v5 = (_QWORD *)*v4, *(_QWORD **)(*v4 + 8LL) != v4) )
      __fastfail(3u);
    *v3 = v5;
    v5[1] = v3;
    v6 = (volatile signed __int32 *)v4[2];
    v4[2] = 0;
    if ( v4 )
      ExFreePoolWithTag(v4, 0);
    PCW_NOTIFICATION::Complete((PCW_NOTIFICATION *)v6, 0, 0);
    if ( v6 )
    {
      if ( _InterlockedExchangeAdd(v6 + 19, 0xFFFFFFFF) == 1 )
        ExFreePoolWithTag((PVOID)v6, 0);
    }
  }
  v7 = (void *)*((_QWORD *)Object + 5);
  v8 = Object[95];
  v9 = Object[92];
  *((_QWORD *)Object + 5) = 0;
  ExReleasePushLockExclusiveEx(Object + 32, 0);
  KeLeaveCriticalRegion();
  if ( !v9 && !v2 )
    ObfDereferenceObject(Object);
  if ( v7 )
    ObfDereferenceObject(v7);
  return v8;
}

```

## disassembly

```asm
0x14000c08c  push    rbx
0x14000c08e  push    rbp
0x14000c08f  push    rsi
0x14000c090  push    rdi
0x14000c091  push    r14
0x14000c093  push    r15
0x14000c095  sub     rsp, 28h
0x14000c099  mov     rdi, rcx
0x14000c09c  call    cs:__imp_KeEnterCriticalRegion
0x14000c0a3  nop     dword ptr [rax+rax+00h]
0x14000c0a8  xor     edx, edx
0x14000c0aa  lea     rcx, [rdi+20h]
0x14000c0ae  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000c0b5  nop     dword ptr [rax+rax+00h]
0x14000c0ba  mov     r15b, [rdi+5Dh]
0x14000c0be  lea     rsi, [rdi+40h]
0x14000c0c2  mov     word ptr [rdi+5Dh], 1
0x14000c0c8  mov     rcx, [rsi]; P
0x14000c0cb  cmp     rcx, rsi
0x14000c0ce  jz      short loc_14000C13E
0x14000c0d0  cmp     [rcx+8], rsi
0x14000c0d4  jnz     short loc_14000C137
0x14000c0d6  mov     rax, [rcx]
0x14000c0d9  cmp     [rax+8], rcx
0x14000c0dd  jnz     short loc_14000C137
0x14000c0df  mov     [rsi], rax
0x14000c0e2  mov     [rax+8], rsi
0x14000c0e6  mov     rbx, [rcx+10h]
0x14000c0ea  mov     qword ptr [rcx+10h], 0
0x14000c0f2  test    rcx, rcx
0x14000c0f5  jz      short loc_14000C105
0x14000c0f7  xor     edx, edx; Tag
0x14000c0f9  call    cs:__imp_ExFreePoolWithTag
0x14000c100  nop     dword ptr [rax+rax+00h]
0x14000c105  xor     r8d, r8d; void *
0x14000c108  xor     edx, edx; struct PCW_REPLYITEM_BUFFER *
0x14000c10a  mov     rcx, rbx; this
0x14000c10d  call    ?Complete@PCW_NOTIFICATION@@QEAAJPEAUPCW_REPLYITEM_BUFFER@@PEBX@Z; PCW_NOTIFICATION::Complete(PCW_REPLYITEM_BUFFER *,void const *)
0x14000c112  test    rbx, rbx
0x14000c115  jz      short loc_14000C0C8
0x14000c117  or      eax, 0FFFFFFFFh
0x14000c11a  lock xadd [rbx+4Ch], eax
0x14000c11f  cmp     eax, 1
0x14000c122  jnz     short loc_14000C0C8
0x14000c124  xor     edx, edx; Tag
0x14000c126  mov     rcx, rbx; P
0x14000c129  call    cs:__imp_ExFreePoolWithTag
0x14000c130  nop     dword ptr [rax+rax+00h]
0x14000c135  jmp     short loc_14000C0C8
0x14000c137  mov     ecx, 3
0x14000c13c  int     29h; Win8: RtlFailFast(ecx)
0x14000c13e  mov     rsi, [rdi+28h]
0x14000c142  lea     rcx, [rdi+20h]
0x14000c146  mov     bpl, [rdi+5Fh]
0x14000c14a  xor     edx, edx
0x14000c14c  mov     bl, [rdi+5Ch]
0x14000c14f  mov     qword ptr [rdi+28h], 0
0x14000c157  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000c15e  nop     dword ptr [rax+rax+00h]
0x14000c163  call    cs:__imp_KeLeaveCriticalRegion
0x14000c16a  nop     dword ptr [rax+rax+00h]
0x14000c16f  test    bl, bl
0x14000c171  jnz     short loc_14000C187
0x14000c173  test    r15b, r15b
0x14000c176  jnz     short loc_14000C187
0x14000c178  mov     rcx, rdi; Object
0x14000c17b  call    cs:__imp_ObfDereferenceObject
0x14000c182  nop     dword ptr [rax+rax+00h]
0x14000c187  test    rsi, rsi
0x14000c18a  jz      short loc_14000C19B
0x14000c18c  mov     rcx, rsi; Object
0x14000c18f  call    cs:__imp_ObfDereferenceObject
0x14000c196  nop     dword ptr [rax+rax+00h]
0x14000c19b  mov     al, bpl
0x14000c19e  add     rsp, 28h
0x14000c1a2  pop     r15
0x14000c1a4  pop     r14
0x14000c1a6  pop     rdi
0x14000c1a7  pop     rsi
0x14000c1a8  pop     rbp
0x14000c1a9  pop     rbx
0x14000c1aa  retn
```
