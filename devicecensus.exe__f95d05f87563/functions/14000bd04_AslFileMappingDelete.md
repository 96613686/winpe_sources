# AslFileMappingDelete

- ea: `0x14000bd04`
- end: `0x14000bde0`
- name: `AslFileMappingDelete`
- size: `220`
- prototype: `BOOLEAN __fastcall(_BYTE *P)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140007184`
- `0x14000ba04`

## callees

- `0x14000bd04`

## import_xrefs

- `ntdll!ZwUnmapViewOfSection` at `0x14000bd4a`
- `ntdll!ZwUnmapViewOfSection` at `0x14000bd4a`
- `ntdll!ZwClose` at `0x14000bd31`
- `ntdll!ZwClose` at `0x14000bd5f`
- `ntdll!ZwClose` at `0x14000bd31`
- `ntdll!ZwClose` at `0x14000bd5f`
- `ntdll!RtlFreeHeap` at `0x14000bd8b`
- `ntdll!RtlFreeHeap` at `0x14000bdb0`
- `ntdll!RtlFreeHeap` at `0x14000bdcf`
- `ntdll!RtlFreeHeap` at `0x14000bd8b`
- `ntdll!RtlFreeHeap` at `0x14000bdb0`
- `ntdll!RtlFreeHeap` at `0x14000bdcf`

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
0x14000bd04  test    rcx, rcx
0x14000bd07  jz      locret_14000BDDF
0x14000bd0d  mov     [rsp+arg_0], rbx
0x14000bd12  push    rdi
0x14000bd13  sub     rsp, 20h
0x14000bd17  lea     rbx, [rcx+8]
0x14000bd1b  mov     rdi, rcx
0x14000bd1e  test    rbx, rbx
0x14000bd21  jz      short loc_14000BD73
0x14000bd23  cmp     byte ptr [rbx+28h], 0
0x14000bd27  jz      short loc_14000BD37
0x14000bd29  mov     rcx, [rbx]; Handle
0x14000bd2c  test    rcx, rcx
0x14000bd2f  jz      short loc_14000BD37
0x14000bd31  call    cs:__imp_ZwClose
0x14000bd37  cmp     byte ptr [rbx+2Ah], 0
0x14000bd3b  jz      short loc_14000BD50
0x14000bd3d  mov     rdx, [rbx+18h]; BaseAddress
0x14000bd41  test    rdx, rdx
0x14000bd44  jz      short loc_14000BD50
0x14000bd46  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14000bd4a  call    cs:__imp_ZwUnmapViewOfSection
0x14000bd50  cmp     byte ptr [rbx+29h], 0
0x14000bd54  jz      short loc_14000BD65
0x14000bd56  mov     rcx, [rbx+8]; Handle
0x14000bd5a  test    rcx, rcx
0x14000bd5d  jz      short loc_14000BD65
0x14000bd5f  call    cs:__imp_ZwClose
0x14000bd65  xorps   xmm0, xmm0
0x14000bd68  movups  xmmword ptr [rbx], xmm0
0x14000bd6b  movups  xmmword ptr [rbx+10h], xmm0
0x14000bd6f  movups  xmmword ptr [rbx+20h], xmm0
0x14000bd73  mov     r8, [rdi+40h]; P
0x14000bd77  test    r8, r8
0x14000bd7a  jz      short loc_14000BD99
0x14000bd7c  mov     rcx, gs:60h
0x14000bd85  xor     edx, edx; Flags
0x14000bd87  mov     rcx, [rcx+30h]; HeapHandle
0x14000bd8b  call    cs:__imp_RtlFreeHeap
0x14000bd91  mov     qword ptr [rdi+40h], 0
0x14000bd99  mov     r8, [rdi]; P
0x14000bd9c  test    r8, r8
0x14000bd9f  jz      short loc_14000BDBD
0x14000bda1  mov     rcx, gs:60h
0x14000bdaa  xor     edx, edx; Flags
0x14000bdac  mov     rcx, [rcx+30h]; HeapHandle
0x14000bdb0  call    cs:__imp_RtlFreeHeap
0x14000bdb6  mov     qword ptr [rdi], 0
0x14000bdbd  mov     rcx, gs:60h
0x14000bdc6  mov     r8, rdi; P
0x14000bdc9  xor     edx, edx; Flags
0x14000bdcb  mov     rcx, [rcx+30h]; HeapHandle
0x14000bdcf  call    cs:__imp_RtlFreeHeap
0x14000bdd5  mov     rbx, [rsp+28h+arg_0]
0x14000bdda  add     rsp, 20h
0x14000bdde  pop     rdi
0x14000bddf  retn
```
