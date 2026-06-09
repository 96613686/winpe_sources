# PktMonClientComponentUnregister

- ea: `0x140065740`
- end: `0x14006584b`
- name: `PktMonClientComponentUnregister`
- size: `267`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140143c14`
- `0x140163cc0`
- `0x1401663e0`
- `0x1401722c0`
- `0x140176610`
- `0x14017ea10`

## callees

- `0x140065740`
- `0x1400e6240`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140065808`
- `ntoskrnl!KeReleaseMutex` at `0x140065808`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006576f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006576f`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140065789`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140065789`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400657bb`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400657bb`

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
        (*(void (__fastcall **)(_QWORD, _QWORD))(*((_QWORD *)&xmmword_14011D750 + 1) + 16LL))(xmmword_14011D750, a1[5]);
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
0x140065740  push    rbx
0x140065742  sub     rsp, 30h
0x140065746  cmp     qword ptr [rcx+28h], 0
0x14006574b  mov     rbx, rcx
0x14006574e  jnz     short loc_140065757
0x140065750  add     rsp, 30h
0x140065754  pop     rbx
0x140065755  retn
0x140065757  xor     r9d, r9d; Alertable
0x14006575a  mov     [rsp+38h+Timeout], 0; Timeout
0x140065763  xor     r8d, r8d; WaitMode
0x140065766  lea     rcx, PktMonCompMutex; Object
0x14006576d  xor     edx, edx; WaitReason
0x14006576f  call    cs:__imp_KeWaitForSingleObject
0x140065776  nop     dword ptr [rax+rax+00h]
0x14006577b  cmp     qword ptr [rbx+28h], 0
0x140065780  jz      short loc_1400657FF
0x140065782  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x140065789  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140065790  nop     dword ptr [rax+rax+00h]
0x140065795  test    al, al
0x140065797  jz      short loc_1400657C7
0x140065799  mov     rax, qword ptr cs:xmmword_14011D750+8
0x1400657a0  mov     rdx, [rbx+28h]
0x1400657a4  mov     rcx, qword ptr cs:xmmword_14011D750
0x1400657ab  mov     rax, [rax+10h]
0x1400657af  call    _guard_dispatch_icall
0x1400657b4  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x1400657bb  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400657c2  nop     dword ptr [rax+rax+00h]
0x1400657c7  mov     rax, [rbx]
0x1400657ca  cmp     [rax+8], rbx
0x1400657ce  jnz     short loc_140065819
0x1400657d0  mov     rcx, [rbx+8]
0x1400657d4  cmp     [rcx], rbx
0x1400657d7  jnz     short loc_140065819
0x1400657d9  dec     cs:PktMonCompCount
0x1400657df  mov     [rcx], rax
0x1400657e2  mov     [rax+8], rcx
0x1400657e6  lea     rax, [rbx+10h]
0x1400657ea  cmp     [rax], rax
0x1400657ed  jnz     short loc_140065820
0x1400657ef  xor     edx, edx; Val
0x1400657f1  mov     r8d, 40h ; '@'; Size
0x1400657f7  mov     rcx, rbx; void *
0x1400657fa  call    memset
0x1400657ff  xor     edx, edx; Wait
0x140065801  lea     rcx, PktMonCompMutex; Mutex
0x140065808  call    cs:__imp_KeReleaseMutex
0x14006580f  nop     dword ptr [rax+rax+00h]
0x140065814  jmp     loc_140065750
0x140065819  mov     ecx, 3
0x14006581e  int     29h; Win8: RtlFailFast(ecx)
0x140065820  mov     rcx, [rax+8]
0x140065824  cmp     [rcx], rax
0x140065827  jnz     short loc_140065819
0x140065829  mov     rdx, [rcx+8]
0x14006582d  cmp     [rdx], rcx
0x140065830  jnz     short loc_140065819
0x140065832  mov     [rax+8], rdx
0x140065836  xorps   xmm0, xmm0
0x140065839  mov     [rdx], rax
0x14006583c  xor     edx, edx
0x14006583e  movups  xmmword ptr [rcx], xmm0
0x140065841  movups  xmmword ptr [rcx+10h], xmm0
0x140065845  mov     [rcx+20h], rdx
0x140065849  jmp     short loc_1400657EA
```
