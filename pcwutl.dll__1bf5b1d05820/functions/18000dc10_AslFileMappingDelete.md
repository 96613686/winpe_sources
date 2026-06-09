# AslFileMappingDelete

- ea: `0x18000dc10`
- end: `0x18000dcec`
- name: `AslFileMappingDelete`
- size: `220`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800039c8`
- `0x18000d824`
- `0x18000d910`

## callees

- `0x18000dc10`

## import_xrefs

- `ntdll!ZwClose` at `0x18000dc3d`
- `ntdll!ZwClose` at `0x18000dc6b`
- `ntdll!ZwClose` at `0x18000dc3d`
- `ntdll!ZwClose` at `0x18000dc6b`
- `ntdll!ZwUnmapViewOfSection` at `0x18000dc56`
- `ntdll!ZwUnmapViewOfSection` at `0x18000dc56`
- `ntdll!RtlFreeHeap` at `0x18000dc97`
- `ntdll!RtlFreeHeap` at `0x18000dcbc`
- `ntdll!RtlFreeHeap` at `0x18000dcdb`
- `ntdll!RtlFreeHeap` at `0x18000dc97`
- `ntdll!RtlFreeHeap` at `0x18000dcbc`
- `ntdll!RtlFreeHeap` at `0x18000dcdb`

## pseudocode

```c
BOOLEAN __fastcall AslFileMappingDelete(_BYTE *P)
{
  char *v1; // rbx
  void *v3; // rdx
  void *v4; // rcx
  void *v5; // r8
  BOOLEAN result; // al

  if ( P )
  {
    v1 = P + 8;
    if ( P != (_BYTE *)-8LL )
    {
      if ( P[48] && *(_QWORD *)v1 )
        ZwClose(*(HANDLE *)v1);
      if ( v1[42] )
      {
        v3 = (void *)*((_QWORD *)v1 + 3);
        if ( v3 )
          ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, v3);
      }
      if ( v1[41] )
      {
        v4 = (void *)*((_QWORD *)v1 + 1);
        if ( v4 )
          ZwClose(v4);
      }
      *(_OWORD *)v1 = 0;
      *((_OWORD *)v1 + 1) = 0;
      *((_OWORD *)v1 + 2) = 0;
    }
    v5 = (void *)*((_QWORD *)P + 8);
    if ( v5 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
      *((_QWORD *)P + 8) = 0;
    }
    if ( *(_QWORD *)P )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)P);
      *(_QWORD *)P = 0;
    }
    return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  }
  return result;
}

```

## disassembly

```asm
0x18000dc10  test    rcx, rcx
0x18000dc13  jz      locret_18000DCEB
0x18000dc19  mov     [rsp+arg_0], rbx
0x18000dc1e  push    rdi
0x18000dc1f  sub     rsp, 20h
0x18000dc23  lea     rbx, [rcx+8]
0x18000dc27  mov     rdi, rcx
0x18000dc2a  test    rbx, rbx
0x18000dc2d  jz      short loc_18000DC7F
0x18000dc2f  cmp     byte ptr [rbx+28h], 0
0x18000dc33  jz      short loc_18000DC43
0x18000dc35  mov     rcx, [rbx]; Handle
0x18000dc38  test    rcx, rcx
0x18000dc3b  jz      short loc_18000DC43
0x18000dc3d  call    cs:__imp_ZwClose
0x18000dc43  cmp     byte ptr [rbx+2Ah], 0
0x18000dc47  jz      short loc_18000DC5C
0x18000dc49  mov     rdx, [rbx+18h]; BaseAddress
0x18000dc4d  test    rdx, rdx
0x18000dc50  jz      short loc_18000DC5C
0x18000dc52  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000dc56  call    cs:__imp_ZwUnmapViewOfSection
0x18000dc5c  cmp     byte ptr [rbx+29h], 0
0x18000dc60  jz      short loc_18000DC71
0x18000dc62  mov     rcx, [rbx+8]; Handle
0x18000dc66  test    rcx, rcx
0x18000dc69  jz      short loc_18000DC71
0x18000dc6b  call    cs:__imp_ZwClose
0x18000dc71  xorps   xmm0, xmm0
0x18000dc74  movups  xmmword ptr [rbx], xmm0
0x18000dc77  movups  xmmword ptr [rbx+10h], xmm0
0x18000dc7b  movups  xmmword ptr [rbx+20h], xmm0
0x18000dc7f  mov     r8, [rdi+40h]; P
0x18000dc83  test    r8, r8
0x18000dc86  jz      short loc_18000DCA5
0x18000dc88  mov     rcx, gs:60h
0x18000dc91  xor     edx, edx; Flags
0x18000dc93  mov     rcx, [rcx+30h]; HeapHandle
0x18000dc97  call    cs:__imp_RtlFreeHeap
0x18000dc9d  mov     qword ptr [rdi+40h], 0
0x18000dca5  mov     r8, [rdi]; P
0x18000dca8  test    r8, r8
0x18000dcab  jz      short loc_18000DCC9
0x18000dcad  mov     rcx, gs:60h
0x18000dcb6  xor     edx, edx; Flags
0x18000dcb8  mov     rcx, [rcx+30h]; HeapHandle
0x18000dcbc  call    cs:__imp_RtlFreeHeap
0x18000dcc2  mov     qword ptr [rdi], 0
0x18000dcc9  mov     rcx, gs:60h
0x18000dcd2  mov     r8, rdi; P
0x18000dcd5  xor     edx, edx; Flags
0x18000dcd7  mov     rcx, [rcx+30h]; HeapHandle
0x18000dcdb  call    cs:__imp_RtlFreeHeap
0x18000dce1  mov     rbx, [rsp+28h+arg_0]
0x18000dce6  add     rsp, 20h
0x18000dcea  pop     rdi
0x18000dceb  retn
```
