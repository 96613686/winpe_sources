# IcmReleaseCachedColorSpace

- ea: `0x180038c70`
- end: `0x180038e47`
- name: `IcmReleaseCachedColorSpace`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x1800384e8`

## callees

- `0x180038c70`
- `0x18003acb8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180038e2f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180038e2f`
- `ntdll!RtlFreeHeap` at `0x180038d15`
- `ntdll!RtlFreeHeap` at `0x180038d3d`
- `ntdll!RtlFreeHeap` at `0x180038d93`
- `ntdll!RtlFreeHeap` at `0x180038e13`
- `ntdll!RtlFreeHeap` at `0x180038d15`
- `ntdll!RtlFreeHeap` at `0x180038d3d`
- `ntdll!RtlFreeHeap` at `0x180038d93`
- `ntdll!RtlFreeHeap` at `0x180038e13`
- `ntdll!RtlEnterCriticalSection` at `0x180038c85`
- `ntdll!RtlEnterCriticalSection` at `0x180038cbf`
- `ntdll!RtlEnterCriticalSection` at `0x180038c85`
- `ntdll!RtlEnterCriticalSection` at `0x180038cbf`
- `ntdll!RtlLeaveCriticalSection` at `0x180038da6`
- `ntdll!RtlLeaveCriticalSection` at `0x180038dc5`
- `ntdll!RtlLeaveCriticalSection` at `0x180038da6`
- `ntdll!RtlLeaveCriticalSection` at `0x180038dc5`

## pseudocode

```c
__int64 __fastcall IcmReleaseCachedColorSpace(PVOID a1)
{
  PVOID *v2; // rbx
  PVOID *v3; // rdi
  int v4; // eax
  bool v5; // zf
  PVOID v6; // r8
  PVOID v7; // r8
  PVOID *v8; // rax
  PVOID *v9; // rcx

  RtlEnterCriticalSection(&semColorSpaceCache);
  v2 = (PVOID *)ListCachedColorSpace;
  if ( ListCachedColorSpace != &ListCachedColorSpace )
  {
    while ( 1 )
    {
      v3 = (PVOID *)*v2;
      if ( v2[2] == a1 )
        break;
LABEL_20:
      v2 = v3;
      if ( v3 == &ListCachedColorSpace )
        goto LABEL_21;
    }
    RtlEnterCriticalSection(&semColorSpaceCache);
    v4 = --*((_DWORD *)v2 + 7);
    if ( ((_DWORD)v2[3] & 0x10000) != 0 )
    {
      v5 = v4 == 0;
    }
    else
    {
      if ( !v4 )
        goto LABEL_6;
      v5 = v2[2] == a1;
    }
    if ( !v5 )
    {
LABEL_19:
      RtlLeaveCriticalSection(&semColorSpaceCache);
      goto LABEL_20;
    }
LABEL_6:
    if ( v2[4] )
      IcmUnrealizeColorProfile(v2);
    if ( ((_DWORD)v2[3] & 0x40000) != 0 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2[7]);
      v2[7] = 0;
    }
    v6 = v2[9];
    if ( v6 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      v2[9] = 0;
    }
    v7 = v2[10];
    if ( v7 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
      v2[10] = 0;
    }
    if ( ((_DWORD)v2[3] & 0x80000) != 0 )
      DeleteFileW((LPCWSTR)v2 + 78);
    v8 = (PVOID *)*v2;
    if ( *((PVOID **)*v2 + 1) != v2 || (v9 = (PVOID *)v2[1], *v9 != v2) )
      __fastfail(3u);
    --cCachedColorSpace;
    *v9 = v8;
    v8[1] = v9;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
    goto LABEL_19;
  }
LABEL_21:
  RtlLeaveCriticalSection(&semColorSpaceCache);
  return 1;
}

```

## disassembly

```asm
0x180038c70  push    rbx
0x180038c72  push    rbp
0x180038c73  push    rsi
0x180038c74  push    rdi
0x180038c75  push    r14
0x180038c77  sub     rsp, 20h
0x180038c7b  mov     rsi, rcx
0x180038c7e  lea     rcx, semColorSpaceCache; CriticalSection
0x180038c85  call    cs:__imp_RtlEnterCriticalSection
0x180038c8c  nop     dword ptr [rax+rax+00h]
0x180038c91  mov     rbx, cs:ListCachedColorSpace
0x180038c98  lea     rbp, ListCachedColorSpace
0x180038c9f  cmp     rbx, rbp
0x180038ca2  jz      loc_180038DBE
0x180038ca8  xor     r14d, r14d
0x180038cab  mov     rdi, [rbx]
0x180038cae  cmp     [rbx+10h], rsi
0x180038cb2  jnz     loc_180038DB2
0x180038cb8  lea     rcx, semColorSpaceCache; CriticalSection
0x180038cbf  call    cs:__imp_RtlEnterCriticalSection
0x180038cc6  nop     dword ptr [rax+rax+00h]
0x180038ccb  dec     dword ptr [rbx+1Ch]
0x180038cce  test    dword ptr [rbx+18h], 10000h
0x180038cd5  mov     eax, [rbx+1Ch]
0x180038cd8  jz      loc_180038DE2
0x180038cde  test    eax, eax
0x180038ce0  jnz     loc_180038D9F
0x180038ce6  cmp     [rbx+20h], r14
0x180038cea  jnz     loc_180038DF3
0x180038cf0  test    dword ptr [rbx+18h], 40000h
0x180038cf7  jnz     loc_180038E00
0x180038cfd  mov     r8, [rbx+48h]; P
0x180038d01  test    r8, r8
0x180038d04  jz      short loc_180038D25
0x180038d06  mov     rcx, gs:60h
0x180038d0f  xor     edx, edx; Flags
0x180038d11  mov     rcx, [rcx+30h]; HeapHandle
0x180038d15  call    cs:__imp_RtlFreeHeap
0x180038d1c  nop     dword ptr [rax+rax+00h]
0x180038d21  mov     [rbx+48h], r14
0x180038d25  mov     r8, [rbx+50h]; P
0x180038d29  test    r8, r8
0x180038d2c  jz      short loc_180038D4D
0x180038d2e  mov     rcx, gs:60h
0x180038d37  xor     edx, edx; Flags
0x180038d39  mov     rcx, [rcx+30h]; HeapHandle
0x180038d3d  call    cs:__imp_RtlFreeHeap
0x180038d44  nop     dword ptr [rax+rax+00h]
0x180038d49  mov     [rbx+50h], r14
0x180038d4d  test    dword ptr [rbx+18h], 80000h
0x180038d54  jnz     loc_180038E28
0x180038d5a  mov     rax, [rbx]
0x180038d5d  cmp     [rax+8], rbx
0x180038d61  jnz     loc_180038E40
0x180038d67  mov     rcx, [rbx+8]
0x180038d6b  cmp     [rcx], rbx
0x180038d6e  jnz     loc_180038E40
0x180038d74  dec     cs:?cCachedColorSpace@@3KA; ulong cCachedColorSpace
0x180038d7a  mov     r8, rbx; P
0x180038d7d  mov     [rcx], rax
0x180038d80  xor     edx, edx; Flags
0x180038d82  mov     [rax+8], rcx
0x180038d86  mov     rcx, gs:60h
0x180038d8f  mov     rcx, [rcx+30h]; HeapHandle
0x180038d93  call    cs:__imp_RtlFreeHeap
0x180038d9a  nop     dword ptr [rax+rax+00h]
0x180038d9f  lea     rcx, semColorSpaceCache; CriticalSection
0x180038da6  call    cs:__imp_RtlLeaveCriticalSection
0x180038dad  nop     dword ptr [rax+rax+00h]
0x180038db2  mov     rbx, rdi
0x180038db5  cmp     rdi, rbp
0x180038db8  jnz     loc_180038CAB
0x180038dbe  lea     rcx, semColorSpaceCache; CriticalSection
0x180038dc5  call    cs:__imp_RtlLeaveCriticalSection
0x180038dcc  nop     dword ptr [rax+rax+00h]
0x180038dd1  mov     eax, 1
0x180038dd6  add     rsp, 20h
0x180038dda  pop     r14
0x180038ddc  pop     rdi
0x180038ddd  pop     rsi
0x180038dde  pop     rbp
0x180038ddf  pop     rbx
0x180038de0  retn
0x180038de2  test    eax, eax
0x180038de4  jz      loc_180038CE6
0x180038dea  cmp     [rbx+10h], rsi
0x180038dee  jmp     loc_180038CE0
0x180038df3  mov     rcx, rbx
0x180038df6  call    IcmUnrealizeColorProfile
0x180038dfb  jmp     loc_180038CF0
0x180038e00  mov     rcx, gs:60h
0x180038e09  xor     edx, edx; Flags
0x180038e0b  mov     r8, [rbx+38h]; P
0x180038e0f  mov     rcx, [rcx+30h]; HeapHandle
0x180038e13  call    cs:__imp_RtlFreeHeap
0x180038e1a  nop     dword ptr [rax+rax+00h]
0x180038e1f  mov     [rbx+38h], r14
0x180038e23  jmp     loc_180038CFD
0x180038e28  lea     rcx, [rbx+9Ch]; lpFileName
0x180038e2f  call    cs:__imp_DeleteFileW
0x180038e36  nop     dword ptr [rax+rax+00h]
0x180038e3b  jmp     loc_180038D5A
0x180038e40  mov     ecx, 3
0x180038e45  int     29h; Win8: RtlFailFast(ecx)
```
