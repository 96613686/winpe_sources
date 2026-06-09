# ReadProviderSupportedProtocolsFromRegistry

- ea: `0x1800355e4`
- end: `0x1800356f0`
- name: `ReadProviderSupportedProtocolsFromRegistry`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034ff0`

## callees

- `0x1800327a8`
- `0x180034b9c`
- `0x1800355e4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18003569a`
- `ntdll!RtlFreeHeap` at `0x1800356d1`
- `ntdll!RtlFreeHeap` at `0x18003569a`
- `ntdll!RtlFreeHeap` at `0x1800356d1`

## string_xrefs

- `0x18003562c`: `Failed to read mapping data`

## pseudocode

```c
__int64 __fastcall ReadProviderSupportedProtocolsFromRegistry(HKEY a1, _QWORD *a2)
{
  unsigned int v3; // eax
  PVOID v4; // rbx
  unsigned int v5; // edi
  const wchar_t *v6; // rdx
  unsigned int v7; // r8d
  __int64 v8; // rdx
  __int64 i; // r9
  int v10; // r10d
  __int64 v11; // rcx
  DWORD v13; // [rsp+38h] [rbp+10h] BYREF
  PVOID P; // [rsp+40h] [rbp+18h] BYREF

  *a2 = 0;
  v13 = 0;
  P = 0;
  v3 = ReadBinary(a1, L"Mapping", (BYTE **)&P, &v13);
  v4 = P;
  v5 = v3;
  if ( v3 )
  {
    v6 = L"Failed to read mapping data";
    goto LABEL_17;
  }
  if ( v13 < 0x14 || (v7 = *(_DWORD *)P) == 0 || *((_DWORD *)P + 1) != 3 )
  {
    v5 = 31;
    v6 = L"Mapping data is invalid";
LABEL_17:
    LogError(v5, v6);
    if ( v4 )
      RtlFreeHeap(SockPrivateHeap, 0, v4);
    return v5;
  }
  v8 = 0;
  for ( i = 0; (unsigned int)i < v7; i = (unsigned int)(i + 1) )
  {
    v10 = *((_DWORD *)v4 + 3 * i + 4);
    if ( v10 )
    {
      v11 = 0;
      if ( (_DWORD)v8 )
      {
        while ( *((_DWORD *)v4 + v11) != v10 )
        {
          v11 = (unsigned int)(v11 + 1);
          if ( (unsigned int)v11 >= (unsigned int)v8 )
            goto LABEL_11;
        }
      }
      else
      {
LABEL_11:
        *((_DWORD *)v4 + v8) = v10;
        v8 = (unsigned int)(v8 + 1);
      }
    }
  }
  *((_DWORD *)v4 + v8) = 0;
  if ( !(_DWORD)v8 )
  {
    RtlFreeHeap(SockPrivateHeap, 0, v4);
    v4 = 0;
  }
  *a2 = v4;
  return v5;
}

```

## disassembly

```asm
0x1800355e4  mov     rax, rsp
0x1800355e7  mov     [rax+8], rbx
0x1800355eb  mov     [rax+20h], rsi
0x1800355ef  push    rdi
0x1800355f0  sub     rsp, 20h
0x1800355f4  mov     rsi, rdx
0x1800355f7  mov     qword ptr [rdx], 0
0x1800355fe  lea     rdx, aMapping; "Mapping"
0x180035605  mov     dword ptr [rax+10h], 0
0x18003560c  lea     r9, [rax+10h]
0x180035610  mov     qword ptr [rax+18h], 0
0x180035618  lea     r8, [rax+18h]
0x18003561c  call    ReadBinary
0x180035621  mov     rbx, [rsp+28h+P]
0x180035626  mov     edi, eax
0x180035628  test    eax, eax
0x18003562a  jz      short loc_180035638
0x18003562c  lea     rdx, aFailedToReadMa; "Failed to read mapping data"
0x180035633  jmp     loc_1800356B9
0x180035638  cmp     [rsp+28h+arg_8], 14h
0x18003563d  jb      short loc_1800356AD
0x18003563f  mov     r8d, [rbx]
0x180035642  test    r8d, r8d
0x180035645  jz      short loc_1800356AD
0x180035647  cmp     dword ptr [rbx+4], 3
0x18003564b  jnz     short loc_1800356AD
0x18003564d  xor     edx, edx
0x18003564f  xor     r9d, r9d
0x180035652  test    r8d, r8d
0x180035655  jz      short loc_180035685
0x180035657  lea     rcx, [r9+r9*2]
0x18003565b  mov     r10d, [rbx+rcx*4+10h]
0x180035660  test    r10d, r10d
0x180035663  jz      short loc_18003567D
0x180035665  xor     ecx, ecx
0x180035667  test    edx, edx
0x180035669  jz      short loc_180035677
0x18003566b  cmp     [rbx+rcx*4], r10d
0x18003566f  jz      short loc_18003567D
0x180035671  inc     ecx
0x180035673  cmp     ecx, edx
0x180035675  jb      short loc_18003566B
0x180035677  mov     [rbx+rdx*4], r10d
0x18003567b  inc     edx; Flags
0x18003567d  inc     r9d
0x180035680  cmp     r9d, r8d
0x180035683  jb      short loc_180035657
0x180035685  mov     dword ptr [rbx+rdx*4], 0
0x18003568c  test    edx, edx
0x18003568e  jnz     short loc_1800356A8
0x180035690  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x180035697  mov     r8, rbx; P
0x18003569a  call    cs:__imp_RtlFreeHeap
0x1800356a1  nop     dword ptr [rax+rax+00h]
0x1800356a6  xor     ebx, ebx
0x1800356a8  mov     [rsi], rbx
0x1800356ab  jmp     short loc_1800356DD
0x1800356ad  mov     edi, 1Fh
0x1800356b2  lea     rdx, aMappingDataIsI; "Mapping data is invalid"
0x1800356b9  mov     ecx, edi
0x1800356bb  call    LogError
0x1800356c0  test    rbx, rbx
0x1800356c3  jz      short loc_1800356DD
0x1800356c5  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x1800356cc  mov     r8, rbx; P
0x1800356cf  xor     edx, edx; Flags
0x1800356d1  call    cs:__imp_RtlFreeHeap
0x1800356d8  nop     dword ptr [rax+rax+00h]
0x1800356dd  mov     rbx, [rsp+28h+arg_0]
0x1800356e2  mov     eax, edi
0x1800356e4  mov     rsi, [rsp+28h+arg_18]
0x1800356e9  add     rsp, 20h
0x1800356ed  pop     rdi
0x1800356ee  retn
```
