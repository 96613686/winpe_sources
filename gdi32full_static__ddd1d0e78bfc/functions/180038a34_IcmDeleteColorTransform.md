# IcmDeleteColorTransform

- ea: `0x180038a34`
- end: `0x180038b74`
- name: `IcmDeleteColorTransform`
- size: `320`
- prototype: ``
- caller_count: `10`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001f090`
- `0x180035af0`
- `0x1800386a8`
- `0x180038b7c`
- `0x180038be8`
- `0x1800499a4`
- `0x18006efa0`
- `0x180070288`
- `0x1800772b0`
- `0x18008e7d8`

## callees

- `0x18003888c`
- `0x180038a34`
- `0x18008e51c`
- `0x1800a8010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180038aa0`
- `ntdll!RtlFreeHeap` at `0x180038aa0`
- `ntdll!RtlEnterCriticalSection` at `0x180038ac8`
- `ntdll!RtlEnterCriticalSection` at `0x180038ac8`
- `ntdll!RtlLeaveCriticalSection` at `0x180038ab3`
- `ntdll!RtlLeaveCriticalSection` at `0x180038ab3`
- `win32u!NtGdiDeleteColorTransform` at `0x180038b4b`
- `win32u!NtGdiDeleteColorTransform` at `0x180038b4b`

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
0x180038a34  mov     [rsp+arg_8], rbx
0x180038a39  mov     [rsp+arg_10], rsi
0x180038a3e  push    rdi
0x180038a3f  sub     rsp, 20h
0x180038a43  mov     ebx, edx
0x180038a45  mov     rdi, rcx
0x180038a48  mov     esi, 1
0x180038a4d  test    rcx, rcx
0x180038a50  jnz     short loc_180038AC1
0x180038a52  mov     rbx, [rsp+28h+arg_8]
0x180038a57  mov     eax, esi
0x180038a59  mov     rsi, [rsp+28h+arg_10]
0x180038a5e  add     rsp, 20h
0x180038a62  pop     rdi
0x180038a63  retn
0x180038a65  mov     esi, eax
0x180038a67  mov     rax, [rbx]
0x180038a6a  cmp     [rax+8], rbx
0x180038a6e  jnz     loc_180038B6D
0x180038a74  mov     rdx, [rbx+8]
0x180038a78  cmp     [rdx], rbx
0x180038a7b  jnz     loc_180038B6D
0x180038a81  dec     cs:?cCachedColorTransform@@3KA; ulong cCachedColorTransform
0x180038a87  mov     r8, rbx; P
0x180038a8a  mov     [rdx], rax
0x180038a8d  mov     [rax+8], rdx
0x180038a91  xor     edx, edx; Flags
0x180038a93  mov     rcx, gs:60h
0x180038a9c  mov     rcx, [rcx+30h]; HeapHandle
0x180038aa0  call    cs:__imp_RtlFreeHeap
0x180038aa7  nop     dword ptr [rax+rax+00h]
0x180038aac  lea     rcx, semColorTransformCache; CriticalSection
0x180038ab3  call    cs:__imp_RtlLeaveCriticalSection
0x180038aba  nop     dword ptr [rax+rax+00h]
0x180038abf  jmp     short loc_180038A52
0x180038ac1  lea     rcx, semColorTransformCache; CriticalSection
0x180038ac8  call    cs:__imp_RtlEnterCriticalSection
0x180038acf  nop     dword ptr [rax+rax+00h]
0x180038ad4  add     dword ptr [rdi+20h], 0FFFFFFFFh
0x180038ad8  jz      short loc_180038ADE
0x180038ada  test    ebx, ebx
0x180038adc  jz      short loc_180038AAC
0x180038ade  test    byte ptr [rdi+10h], 10h
0x180038ae2  jz      short loc_180038AFE
0x180038ae4  test    ebx, ebx
0x180038ae6  jnz     short loc_180038AFE
0x180038ae8  cmp     cs:?cCachedColorTransform@@3KA, 0Ah; ulong cCachedColorTransform
0x180038aef  jb      short loc_180038AAC
0x180038af1  call    IcmGetFirstNonUsedColorTransform
0x180038af6  mov     rbx, rax
0x180038af9  test    rax, rax
0x180038afc  jnz     short loc_180038B01
0x180038afe  mov     rbx, rdi
0x180038b01  mov     rdx, [rbx+30h]
0x180038b05  test    rdx, rdx
0x180038b08  jz      short loc_180038B14
0x180038b0a  xor     r8d, r8d
0x180038b0d  xor     ecx, ecx
0x180038b0f  call    IcmReleaseColorSpace
0x180038b14  mov     rdx, [rbx+38h]
0x180038b18  test    rdx, rdx
0x180038b1b  jz      short loc_180038B27
0x180038b1d  xor     r8d, r8d
0x180038b20  xor     ecx, ecx
0x180038b22  call    IcmReleaseColorSpace
0x180038b27  mov     rdx, [rbx+40h]
0x180038b2b  test    rdx, rdx
0x180038b2e  jz      short loc_180038B3A
0x180038b30  xor     r8d, r8d
0x180038b33  xor     ecx, ecx
0x180038b35  call    IcmReleaseColorSpace
0x180038b3a  test    byte ptr [rbx+10h], 4
0x180038b3e  mov     rcx, [rbx+28h]
0x180038b42  jz      short loc_180038B5C
0x180038b44  mov     rdx, rcx
0x180038b47  mov     rcx, [rbx+18h]
0x180038b4b  call    cs:__imp_NtGdiDeleteColorTransform
0x180038b52  nop     dword ptr [rax+rax+00h]
0x180038b57  jmp     loc_180038A65
0x180038b5c  mov     rax, cs:fpDeleteColorTransform
0x180038b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b68  jmp     loc_180038A65
0x180038b6d  mov     ecx, 3
0x180038b72  int     29h; Win8: RtlFailFast(ecx)
```
