# PktMonClientComponentUnregister

- ea: `0x14006b6d0`
- end: `0x14006b7db`
- name: `PktMonClientComponentUnregister`
- size: `267`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14014abb4`
- `0x14016ac50`
- `0x14016d280`
- `0x1401782c0`
- `0x14017c5e0`
- `0x140184cd0`

## callees

- `0x14006b6d0`
- `0x1400eb460`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14006b798`
- `ntoskrnl!KeReleaseMutex` at `0x14006b798`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006b6ff`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006b6ff`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14006b719`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14006b719`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14006b74b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14006b74b`

## pseudocode

```c
void __fastcall PktMonClientComponentUnregister(_QWORD *a1)
{
  _QWORD *v2; // rax
  void **v3; // rcx
  _QWORD *v4; // rax
  __int64 v5; // rcx
  _QWORD *v6; // rdx

  if ( a1[5] )
  {
    KeWaitForSingleObject(&PktMonCompMutex, Executive, 0, 0, 0);
    if ( a1[5] )
    {
      if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
      {
        (*(void (__fastcall **)(_QWORD, _QWORD))(*((_QWORD *)&xmmword_140123740 + 1) + 16LL))(xmmword_140123740, a1[5]);
        ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
      }
      v2 = (_QWORD *)*a1;
      if ( *(_QWORD **)(*a1 + 8LL) != a1 || (v3 = (void **)a1[1], *v3 != a1) )
LABEL_11:
        __fastfail(3u);
      --PktMonCompCount;
      *v3 = v2;
      v2[1] = v3;
      v4 = a1 + 2;
      while ( (_QWORD *)*v4 != v4 )
      {
        v5 = a1[3];
        if ( *(_QWORD **)v5 != v4 )
          goto LABEL_11;
        v6 = *(_QWORD **)(v5 + 8);
        if ( *v6 != v5 )
          goto LABEL_11;
        a1[3] = v6;
        *v6 = v4;
        *(_OWORD *)v5 = 0;
        *(_OWORD *)(v5 + 16) = 0;
        *(_QWORD *)(v5 + 32) = 0;
      }
      memset(a1, 0, 0x40u);
    }
    KeReleaseMutex(&PktMonCompMutex, 0);
  }
}

```

## disassembly

```asm
0x14006b6d0  push    rbx
0x14006b6d2  sub     rsp, 30h
0x14006b6d6  cmp     qword ptr [rcx+28h], 0
0x14006b6db  mov     rbx, rcx
0x14006b6de  jnz     short loc_14006B6E7
0x14006b6e0  add     rsp, 30h
0x14006b6e4  pop     rbx
0x14006b6e5  retn
0x14006b6e7  xor     r9d, r9d; Alertable
0x14006b6ea  mov     [rsp+38h+Timeout], 0; Timeout
0x14006b6f3  xor     r8d, r8d; WaitMode
0x14006b6f6  lea     rcx, PktMonCompMutex; Object
0x14006b6fd  xor     edx, edx; WaitReason
0x14006b6ff  call    cs:__imp_KeWaitForSingleObject
0x14006b706  nop     dword ptr [rax+rax+00h]
0x14006b70b  cmp     qword ptr [rbx+28h], 0
0x14006b710  jz      short loc_14006B78F
0x14006b712  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x14006b719  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14006b720  nop     dword ptr [rax+rax+00h]
0x14006b725  test    al, al
0x14006b727  jz      short loc_14006B757
0x14006b729  mov     rax, qword ptr cs:xmmword_140123740+8
0x14006b730  mov     rdx, [rbx+28h]
0x14006b734  mov     rcx, qword ptr cs:xmmword_140123740
0x14006b73b  mov     rax, [rax+10h]
0x14006b73f  call    _guard_dispatch_icall
0x14006b744  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x14006b74b  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x14006b752  nop     dword ptr [rax+rax+00h]
0x14006b757  mov     rax, [rbx]
0x14006b75a  cmp     [rax+8], rbx
0x14006b75e  jnz     short loc_14006B7A9
0x14006b760  mov     rcx, [rbx+8]
0x14006b764  cmp     [rcx], rbx
0x14006b767  jnz     short loc_14006B7A9
0x14006b769  dec     cs:PktMonCompCount
0x14006b76f  mov     [rcx], rax
0x14006b772  mov     [rax+8], rcx
0x14006b776  lea     rax, [rbx+10h]
0x14006b77a  cmp     [rax], rax
0x14006b77d  jnz     short loc_14006B7B0
0x14006b77f  xor     edx, edx; Val
0x14006b781  mov     r8d, 40h ; '@'; Size
0x14006b787  mov     rcx, rbx; void *
0x14006b78a  call    memset
0x14006b78f  xor     edx, edx; Wait
0x14006b791  lea     rcx, PktMonCompMutex; Mutex
0x14006b798  call    cs:__imp_KeReleaseMutex
0x14006b79f  nop     dword ptr [rax+rax+00h]
0x14006b7a4  jmp     loc_14006B6E0
0x14006b7a9  mov     ecx, 3
0x14006b7ae  int     29h; Win8: RtlFailFast(ecx)
0x14006b7b0  mov     rcx, [rax+8]
0x14006b7b4  cmp     [rcx], rax
0x14006b7b7  jnz     short loc_14006B7A9
0x14006b7b9  mov     rdx, [rcx+8]
0x14006b7bd  cmp     [rdx], rcx
0x14006b7c0  jnz     short loc_14006B7A9
0x14006b7c2  mov     [rax+8], rdx
0x14006b7c6  xorps   xmm0, xmm0
0x14006b7c9  mov     [rdx], rax
0x14006b7cc  xor     edx, edx
0x14006b7ce  movups  xmmword ptr [rcx], xmm0
0x14006b7d1  movups  xmmword ptr [rcx+10h], xmm0
0x14006b7d5  mov     [rcx+20h], rdx
0x14006b7d9  jmp     short loc_14006B77A
```
