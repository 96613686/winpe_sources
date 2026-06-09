# FveConfigSubscriberBaseRelease

- ea: `0x1400827f0`
- end: `0x1400828ce`
- name: `FveConfigSubscriberBaseRelease`
- size: `222`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1400219a0`
- `0x140021d00`
- `0x1400827f0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14008289c`
- `ntoskrnl!ObfDereferenceObject` at `0x14008289c`
- `ntoskrnl!ExDeleteResourceLite` at `0x140082887`
- `ntoskrnl!ExDeleteResourceLite` at `0x140082887`
- `ntoskrnl!ExReleaseResourceLite` at `0x140082858`
- `ntoskrnl!ExReleaseResourceLite` at `0x140082858`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140082828`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140082828`

## pseudocode

```c
__int64 __fastcall FveConfigSubscriberBaseRelease(__int64 a1, char *a2)
{
  __int64 v2; // rdi
  void (__fastcall *v5)(__int64, char *); // rbp
  unsigned __int32 v6; // esi
  _QWORD *v7; // rcx
  void **v8; // rax
  void *v9; // rcx

  v2 = *((_QWORD *)a2 + 2);
  v5 = *(void (__fastcall **)(__int64, char *))(v2 + 160);
  v6 = _InterlockedDecrement((volatile signed __int32 *)a2 + 11);
  if ( !v6 )
  {
    if ( *(char **)a2 != a2 )
    {
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v2 + 8), 1u);
      v7 = *(_QWORD **)a2;
      if ( *(char **)(*(_QWORD *)a2 + 8LL) != a2 || (v8 = (void **)*((_QWORD *)a2 + 1), *v8 != a2) )
        __fastfail(3u);
      *v8 = v7;
      v7[1] = v8;
      --*(_DWORD *)(v2 + 20);
      ExReleaseResourceLite(*(PERESOURCE *)(v2 + 8));
    }
    if ( v5 && (char *)v5 != (char *)&FveConfigSubscriberBaseRelease )
      v5(a1, a2);
    ExDeleteResourceLite((PERESOURCE)(a2 + 64));
    v9 = (void *)*((_QWORD *)a2 + 3);
    if ( v9 )
      ObfDereferenceObject(v9);
    memset(a2, 0, *(unsigned int *)(v2 + 132));
  }
  return v6;
}

```

## disassembly

```asm
0x1400827f0  push    rbx
0x1400827f2  push    rbp
0x1400827f3  push    rsi
0x1400827f4  push    rdi
0x1400827f5  push    r14
0x1400827f7  sub     rsp, 20h
0x1400827fb  mov     rdi, [rdx+10h]
0x1400827ff  mov     rbx, rdx
0x140082802  mov     r14, rcx
0x140082805  or      esi, 0FFFFFFFFh
0x140082808  mov     rbp, [rdi+0A0h]
0x14008280f  lock xadd [rdx+2Ch], esi
0x140082814  sub     esi, 1
0x140082817  jnz     loc_1400828B9
0x14008281d  cmp     [rdx], rdx
0x140082820  jz      short loc_140082864
0x140082822  mov     rcx, [rdi+8]; Resource
0x140082826  mov     dl, 1; Wait
0x140082828  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14008282f  nop     dword ptr [rax+rax+00h]
0x140082834  mov     rcx, [rbx]
0x140082837  cmp     [rcx+8], rbx
0x14008283b  jnz     loc_1400828C7
0x140082841  mov     rax, [rbx+8]
0x140082845  cmp     [rax], rbx
0x140082848  jnz     short loc_1400828C7
0x14008284a  mov     [rax], rcx
0x14008284d  mov     [rcx+8], rax
0x140082851  dec     dword ptr [rdi+14h]
0x140082854  mov     rcx, [rdi+8]; Resource
0x140082858  call    cs:__imp_ExReleaseResourceLite
0x14008285f  nop     dword ptr [rax+rax+00h]
0x140082864  test    rbp, rbp
0x140082867  jz      short loc_140082883
0x140082869  lea     rax, FveConfigSubscriberBaseRelease
0x140082870  cmp     rbp, rax
0x140082873  jz      short loc_140082883
0x140082875  mov     rdx, rbx
0x140082878  mov     rcx, r14
0x14008287b  mov     rax, rbp
0x14008287e  call    _guard_dispatch_icall
0x140082883  lea     rcx, [rbx+40h]; Resource
0x140082887  call    cs:__imp_ExDeleteResourceLite
0x14008288e  nop     dword ptr [rax+rax+00h]
0x140082893  mov     rcx, [rbx+18h]; Object
0x140082897  test    rcx, rcx
0x14008289a  jz      short loc_1400828A8
0x14008289c  call    cs:__imp_ObfDereferenceObject
0x1400828a3  nop     dword ptr [rax+rax+00h]
0x1400828a8  mov     r8d, [rdi+84h]; Size
0x1400828af  xor     edx, edx; Val
0x1400828b1  mov     rcx, rbx; void *
0x1400828b4  call    memset
0x1400828b9  mov     eax, esi
0x1400828bb  add     rsp, 20h
0x1400828bf  pop     r14
0x1400828c1  pop     rdi
0x1400828c2  pop     rsi
0x1400828c3  pop     rbp
0x1400828c4  pop     rbx
0x1400828c5  retn
0x1400828c7  mov     ecx, 3
0x1400828cc  int     29h; Win8: RtlFailFast(ecx)
```
