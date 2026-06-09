# CreateUserContext(ulong)

- ea: `0x140002c20`
- end: `0x140002db5`
- name: `?CreateUserContext@@YAPEAUCSslUserContext@@K@Z`
- size: `405`
- prototype: `struct CSslUserContext *__fastcall(size_t Size)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140002410`

## callees

- `0x140002c20`
- `0x140002dc0`
- `0x140004800`
- `0x1400105c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140002d76`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140002d76`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002d93`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140002d93`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002d13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002d13`
- `ntoskrnl!ExAllocatePool2` at `0x140002c6b`
- `ntoskrnl!ExAllocatePool2` at `0x140002cc4`
- `ntoskrnl!ExAllocatePool2` at `0x140002c6b`
- `ntoskrnl!ExAllocatePool2` at `0x140002cc4`
- `ntoskrnl!KeInitializeEvent` at `0x140002c97`
- `ntoskrnl!KeInitializeEvent` at `0x140002c97`

## pseudocode

```c
struct CSslUserContext *__fastcall CreateUserContext(size_t Size)
{
  size_t v1; // rbx
  struct _KEVENT *Pool2; // rax
  int v3; // esi
  CSslUserContext *v4; // rax
  CSslUserContext *v5; // rdi
  CSslUserContext *v6; // rbx
  void **v8; // [rsp+20h] [rbp-18h] BYREF
  PVOID P; // [rsp+28h] [rbp-10h]

  v1 = (unsigned int)Size;
  if ( (unsigned int)Size < 0x210 )
    return 0;
  if ( (unsigned int)g_dwMaxContextLength <= (unsigned int)Size )
    LODWORD(g_dwMaxContextLength) = Size;
  v8 = &CEvent::`vftable';
  Pool2 = (struct _KEVENT *)ExAllocatePool2(64, 24, 1131180883);
  P = Pool2;
  if ( !Pool2 )
    return 0;
  KeInitializeEvent(Pool2, NotificationEvent, 1u);
  if ( g_dwLookasideLen >= (unsigned int)v1 && g_pSchannelPagedSlist && g_pSchannelNonPagedSlist )
  {
    if ( g_CurrentPoolType == 1 )
    {
      v3 = 1;
      v4 = (CSslUserContext *)ExAllocateFromPagedLookasideList(g_pSchannelPagedSlist);
    }
    else
    {
      v3 = 512;
      v4 = (CSslUserContext *)ExAllocateFromNPagedLookasideList(g_pSchannelNonPagedSlist);
    }
  }
  else
  {
    v3 = -1;
    v4 = (CSslUserContext *)ExAllocatePool2(SslPoolType, v1, 1131180883);
  }
  v5 = v4;
  if ( v4 )
  {
    memset(v4, 0, v1);
    v6 = CSslUserContext::CSslUserContext(v5, (struct CEvent *)&v8);
    *((_DWORD *)v6 + 106) = v3;
    v8 = &CEvent::`vftable';
    if ( P )
      ExFreePoolWithTag(P, 0x436C7353u);
    return v6;
  }
  else
  {
    CEvent::~CEvent((CEvent *)&v8);
    return 0;
  }
}

```

## disassembly

```asm
0x140002c20  mov     [rsp+arg_10], rbx
0x140002c25  push    rbp
0x140002c26  sub     rsp, 30h
0x140002c2a  mov     ebx, ecx
0x140002c2c  cmp     ecx, 210h
0x140002c32  jb      loc_140002D38
0x140002c38  cmp     cs:?g_dwMaxContextLength@@3KA, ebx; ulong g_dwMaxContextLength
0x140002c3e  ja      short loc_140002C46
0x140002c40  mov     cs:?g_dwMaxContextLength@@3KA, ebx; ulong g_dwMaxContextLength
0x140002c46  lea     rbp, ??_7CEvent@@6B@; const CEvent::`vftable'
0x140002c4d  mov     [rsp+38h+P], 0
0x140002c56  mov     edx, 18h
0x140002c5b  mov     [rsp+38h+var_18], rbp
0x140002c60  mov     ecx, 40h ; '@'
0x140002c65  mov     r8d, 436C7353h
0x140002c6b  call    cs:__imp_ExAllocatePool2
0x140002c72  nop     dword ptr [rax+rax+00h]
0x140002c77  mov     [rsp+38h+P], rax
0x140002c7c  test    rax, rax
0x140002c7f  jz      loc_140002D38
0x140002c85  mov     [rsp+38h+arg_8], rdi
0x140002c8a  mov     r8b, 1; State
0x140002c8d  xor     edx, edx; Type
0x140002c8f  mov     [rsp+38h+arg_0], rsi
0x140002c94  mov     rcx, rax; Event
0x140002c97  call    cs:__imp_KeInitializeEvent
0x140002c9e  nop     dword ptr [rax+rax+00h]
0x140002ca3  cmp     cs:?g_dwLookasideLen@@3KA, ebx; ulong g_dwLookasideLen
0x140002ca9  jnb     loc_140002D46
0x140002caf  mov     rcx, cs:?SslPoolType@@3_KA; unsigned __int64 SslPoolType
0x140002cb6  mov     r8d, 436C7353h
0x140002cbc  mov     rdx, rbx
0x140002cbf  mov     esi, 0FFFFFFFFh
0x140002cc4  call    cs:__imp_ExAllocatePool2
0x140002ccb  nop     dword ptr [rax+rax+00h]
0x140002cd0  mov     rdi, rax
0x140002cd3  test    rax, rax
0x140002cd6  jz      loc_140002DA4
0x140002cdc  mov     r8, rbx; Size
0x140002cdf  xor     edx, edx; Val
0x140002ce1  mov     rcx, rax; void *
0x140002ce4  call    memset
0x140002ce9  lea     rdx, [rsp+38h+var_18]; struct CEvent *
0x140002cee  mov     rcx, rdi; this
0x140002cf1  call    ??0CSslUserContext@@QEAA@AEAVCEvent@@@Z; CSslUserContext::CSslUserContext(CEvent &)
0x140002cf6  mov     rbx, rax
0x140002cf9  mov     [rax+1A8h], esi
0x140002cff  mov     rcx, [rsp+38h+P]; P
0x140002d04  mov     [rsp+38h+var_18], rbp
0x140002d09  test    rcx, rcx
0x140002d0c  jz      short loc_140002D1F
0x140002d0e  mov     edx, 436C7353h; Tag
0x140002d13  call    cs:__imp_ExFreePoolWithTag
0x140002d1a  nop     dword ptr [rax+rax+00h]
0x140002d1f  mov     rax, rbx
0x140002d22  mov     rsi, [rsp+38h+arg_0]
0x140002d27  mov     rdi, [rsp+38h+arg_8]
0x140002d2c  mov     rbx, [rsp+38h+arg_10]
0x140002d31  add     rsp, 30h
0x140002d35  pop     rbp
0x140002d36  retn
0x140002d38  mov     rbx, [rsp+38h+arg_10]
0x140002d3d  xor     eax, eax
0x140002d3f  add     rsp, 30h
0x140002d43  pop     rbp
0x140002d44  retn
0x140002d46  cmp     cs:?g_pSchannelPagedSlist@@3PEAU_PAGED_LOOKASIDE_LIST@@EA, 0; _PAGED_LOOKASIDE_LIST * g_pSchannelPagedSlist
0x140002d4e  jz      loc_140002CAF
0x140002d54  cmp     cs:?g_pSchannelNonPagedSlist@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA, 0; _NPAGED_LOOKASIDE_LIST * g_pSchannelNonPagedSlist
0x140002d5c  jz      loc_140002CAF
0x140002d62  mov     eax, cs:?g_CurrentPoolType@@3JC; long volatile g_CurrentPoolType
0x140002d68  cmp     eax, 1
0x140002d6b  jnz     short loc_140002D87
0x140002d6d  mov     rcx, cs:?g_pSchannelPagedSlist@@3PEAU_PAGED_LOOKASIDE_LIST@@EA; Lookaside
0x140002d74  mov     esi, eax
0x140002d76  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140002d7d  nop     dword ptr [rax+rax+00h]
0x140002d82  jmp     loc_140002CD0
0x140002d87  mov     rcx, cs:?g_pSchannelNonPagedSlist@@3PEAU_NPAGED_LOOKASIDE_LIST@@EA; Lookaside
0x140002d8e  mov     esi, 200h
0x140002d93  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140002d9a  nop     dword ptr [rax+rax+00h]
0x140002d9f  jmp     loc_140002CD0
0x140002da4  lea     rcx, [rsp+38h+var_18]; this
0x140002da9  call    ??1CEvent@@UEAA@XZ; CEvent::~CEvent(void)
0x140002dae  xor     eax, eax
0x140002db0  jmp     loc_140002D22
```
