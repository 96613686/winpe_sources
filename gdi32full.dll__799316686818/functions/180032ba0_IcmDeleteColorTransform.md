# IcmDeleteColorTransform

- ea: `0x180032ba0`
- end: `0x180032cc7`
- name: `IcmDeleteColorTransform`
- size: `295`
- prototype: ``
- caller_count: `10`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001ec70`
- `0x18001f310`
- `0x180032848`
- `0x180032cd0`
- `0x180032d38`
- `0x18003e184`
- `0x18006a7c4`
- `0x18006b93c`
- `0x180072b80`
- `0x1800891e4`

## callees

- `0x180032a24`
- `0x180032ba0`
- `0x180088f4c`
- `0x1800a5010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180032c0b`
- `ntdll!RtlFreeHeap` at `0x180032c0b`
- `ntdll!RtlEnterCriticalSection` at `0x180032c27`
- `ntdll!RtlEnterCriticalSection` at `0x180032c27`
- `ntdll!RtlLeaveCriticalSection` at `0x180032c18`
- `ntdll!RtlLeaveCriticalSection` at `0x180032c18`
- `win32u!NtGdiDeleteColorTransform` at `0x180032ca4`
- `win32u!NtGdiDeleteColorTransform` at `0x180032ca4`

## pseudocode

```c
__int64 __fastcall IcmDeleteColorTransform(__int64 a1, int a2)
{
  unsigned int v4; // esi
  _QWORD *v6; // rax
  void **v7; // rdx
  bool v8; // zf
  _QWORD *FirstNonUsedColorTransform; // rbx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  unsigned int v13; // eax

  v4 = 1;
  if ( a1 )
  {
    RtlEnterCriticalSection(&semColorTransformCache);
    v8 = (*(_DWORD *)(a1 + 32))-- == 1;
    if ( v8 || a2 )
    {
      if ( (*(_BYTE *)(a1 + 16) & 0x10) == 0 || a2 )
        goto LABEL_13;
      if ( cCachedColorTransform >= 0xA )
      {
        FirstNonUsedColorTransform = (_QWORD *)IcmGetFirstNonUsedColorTransform();
        if ( FirstNonUsedColorTransform )
        {
LABEL_14:
          v10 = FirstNonUsedColorTransform[6];
          if ( v10 )
            IcmReleaseColorSpace(0, v10, 0);
          v11 = FirstNonUsedColorTransform[7];
          if ( v11 )
            IcmReleaseColorSpace(0, v11, 0);
          v12 = FirstNonUsedColorTransform[8];
          if ( v12 )
            IcmReleaseColorSpace(0, v12, 0);
          if ( (FirstNonUsedColorTransform[2] & 4) != 0 )
            v13 = NtGdiDeleteColorTransform(FirstNonUsedColorTransform[3], FirstNonUsedColorTransform[5]);
          else
            v13 = ((__int64 (__fastcall *)(_QWORD))fpDeleteColorTransform)(FirstNonUsedColorTransform[5]);
          v4 = v13;
          v6 = (_QWORD *)*FirstNonUsedColorTransform;
          if ( *(_QWORD **)(*FirstNonUsedColorTransform + 8LL) != FirstNonUsedColorTransform
            || (v7 = (void **)FirstNonUsedColorTransform[1], *v7 != FirstNonUsedColorTransform) )
          {
            __fastfail(3u);
          }
          --cCachedColorTransform;
          *v7 = v6;
          v6[1] = v7;
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, FirstNonUsedColorTransform);
          goto LABEL_6;
        }
LABEL_13:
        FirstNonUsedColorTransform = (_QWORD *)a1;
        goto LABEL_14;
      }
    }
LABEL_6:
    RtlLeaveCriticalSection(&semColorTransformCache);
  }
  return v4;
}

```

## disassembly

```asm
0x180032ba0  mov     [rsp+arg_8], rbx
0x180032ba5  mov     [rsp+arg_10], rsi
0x180032baa  push    rdi
0x180032bab  sub     rsp, 20h
0x180032baf  mov     ebx, edx
0x180032bb1  mov     rdi, rcx
0x180032bb4  mov     esi, 1
0x180032bb9  test    rcx, rcx
0x180032bbc  jnz     short loc_180032C20
0x180032bbe  mov     rbx, [rsp+28h+arg_8]
0x180032bc3  mov     eax, esi
0x180032bc5  mov     rsi, [rsp+28h+arg_10]
0x180032bca  add     rsp, 20h
0x180032bce  pop     rdi
0x180032bcf  retn
0x180032bd0  mov     esi, eax
0x180032bd2  mov     rax, [rbx]
0x180032bd5  cmp     [rax+8], rbx
0x180032bd9  jnz     loc_180032CC0
0x180032bdf  mov     rdx, [rbx+8]
0x180032be3  cmp     [rdx], rbx
0x180032be6  jnz     loc_180032CC0
0x180032bec  dec     cs:?cCachedColorTransform@@3KA; ulong cCachedColorTransform
0x180032bf2  mov     r8, rbx; P
0x180032bf5  mov     [rdx], rax
0x180032bf8  mov     [rax+8], rdx
0x180032bfc  xor     edx, edx; Flags
0x180032bfe  mov     rcx, gs:60h
0x180032c07  mov     rcx, [rcx+30h]; HeapHandle
0x180032c0b  call    cs:__imp_RtlFreeHeap
0x180032c11  lea     rcx, semColorTransformCache; CriticalSection
0x180032c18  call    cs:__imp_RtlLeaveCriticalSection
0x180032c1e  jmp     short loc_180032BBE
0x180032c20  lea     rcx, semColorTransformCache; CriticalSection
0x180032c27  call    cs:__imp_RtlEnterCriticalSection
0x180032c2d  add     dword ptr [rdi+20h], 0FFFFFFFFh
0x180032c31  jz      short loc_180032C37
0x180032c33  test    ebx, ebx
0x180032c35  jz      short loc_180032C11
0x180032c37  test    byte ptr [rdi+10h], 10h
0x180032c3b  jz      short loc_180032C57
0x180032c3d  test    ebx, ebx
0x180032c3f  jnz     short loc_180032C57
0x180032c41  cmp     cs:?cCachedColorTransform@@3KA, 0Ah; ulong cCachedColorTransform
0x180032c48  jb      short loc_180032C11
0x180032c4a  call    IcmGetFirstNonUsedColorTransform
0x180032c4f  mov     rbx, rax
0x180032c52  test    rax, rax
0x180032c55  jnz     short loc_180032C5A
0x180032c57  mov     rbx, rdi
0x180032c5a  mov     rdx, [rbx+30h]
0x180032c5e  test    rdx, rdx
0x180032c61  jz      short loc_180032C6D
0x180032c63  xor     r8d, r8d
0x180032c66  xor     ecx, ecx
0x180032c68  call    IcmReleaseColorSpace
0x180032c6d  mov     rdx, [rbx+38h]
0x180032c71  test    rdx, rdx
0x180032c74  jz      short loc_180032C80
0x180032c76  xor     r8d, r8d
0x180032c79  xor     ecx, ecx
0x180032c7b  call    IcmReleaseColorSpace
0x180032c80  mov     rdx, [rbx+40h]
0x180032c84  test    rdx, rdx
0x180032c87  jz      short loc_180032C93
0x180032c89  xor     r8d, r8d
0x180032c8c  xor     ecx, ecx
0x180032c8e  call    IcmReleaseColorSpace
0x180032c93  test    byte ptr [rbx+10h], 4
0x180032c97  mov     rcx, [rbx+28h]
0x180032c9b  jz      short loc_180032CAF
0x180032c9d  mov     rdx, rcx
0x180032ca0  mov     rcx, [rbx+18h]
0x180032ca4  call    cs:__imp_NtGdiDeleteColorTransform
0x180032caa  jmp     loc_180032BD0
0x180032caf  mov     rax, cs:fpDeleteColorTransform
0x180032cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032cbb  jmp     loc_180032BD0
0x180032cc0  mov     ecx, 3
0x180032cc5  int     29h; Win8: RtlFailFast(ecx)
```
