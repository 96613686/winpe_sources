# FatFlushFile

- ea: `0x14003e870`
- end: `0x14003e944`
- name: `FatFlushFile`
- size: `212`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x14000363c`
- `0x140003e9c`
- `0x1400040e4`
- `0x140004264`
- `0x140004554`
- `0x140024bd4`
- `0x14003d974`
- `0x14003dba0`
- `0x14003e028`

## callees

- `0x14003e870`
- `0x140049bd4`

## import_xrefs

- `ntoskrnl!CcFlushCache` at `0x14003e8a1`
- `ntoskrnl!CcFlushCache` at `0x14003e8df`
- `ntoskrnl!CcFlushCache` at `0x14003e8a1`
- `ntoskrnl!CcFlushCache` at `0x14003e8df`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003e8fd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003e8fd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003e923`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003e923`

## pseudocode

```c
__int64 __fastcall FatFlushFile(__int64 a1, __int64 a2, int a3)
{
  __int64 v3; // rdi
  __int64 v6; // rcx
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+20h] [rbp-18h] BYREF

  v3 = *(_QWORD *)(a2 + 184);
  IoStatus = 0;
  CcFlushCache(*(PSECTION_OBJECT_POINTERS *)(a2 + 120), 0, 0, &IoStatus);
  if ( (*(_DWORD *)(v3 + 200) & 0x100) == 0 && *(_WORD *)a2 == 1282 && *(_QWORD *)(a2 + 424) )
    CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(a2 + 120) + 96LL), 0, 0, &IoStatus);
  if ( (*(_DWORD *)(v3 + 200) & 0x100) == 0 )
  {
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a2 + 16), 1u);
    if ( a3 == 2 )
      FatMarkFcbCondition(v6, a2, 2, 0);
    ExReleaseResourceLite(*(PERESOURCE *)(a2 + 16));
  }
  return (unsigned int)IoStatus.Status;
}

```

## disassembly

```asm
0x14003e870  mov     rax, rsp
0x14003e873  mov     [rax+8], rbx
0x14003e877  mov     [rax+10h], rsi
0x14003e87b  push    rdi
0x14003e87c  sub     rsp, 30h
0x14003e880  mov     rdi, [rdx+0B8h]
0x14003e887  lea     r9, [rax-18h]; IoStatus
0x14003e88b  mov     rbx, rdx
0x14003e88e  mov     esi, r8d
0x14003e891  xorps   xmm0, xmm0
0x14003e894  xor     r8d, r8d; Length
0x14003e897  xor     edx, edx; FileOffset
0x14003e899  movups  xmmword ptr [rax-18h], xmm0
0x14003e89d  mov     rcx, [rbx+78h]; SectionObjectPointer
0x14003e8a1  call    cs:__imp_CcFlushCache
0x14003e8a8  nop     dword ptr [rax+rax+00h]
0x14003e8ad  mov     eax, [rdi+0C8h]
0x14003e8b3  bt      eax, 8
0x14003e8b7  jb      short loc_14003E8EB
0x14003e8b9  mov     eax, 502h
0x14003e8be  cmp     [rbx], ax
0x14003e8c1  jnz     short loc_14003E8EB
0x14003e8c3  cmp     qword ptr [rbx+1A8h], 0
0x14003e8cb  jz      short loc_14003E8EB
0x14003e8cd  mov     rcx, [rbx+78h]
0x14003e8d1  lea     r9, [rsp+38h+IoStatus]; IoStatus
0x14003e8d6  add     rcx, 60h ; '`'; SectionObjectPointer
0x14003e8da  xor     r8d, r8d; Length
0x14003e8dd  xor     edx, edx; FileOffset
0x14003e8df  call    cs:__imp_CcFlushCache
0x14003e8e6  nop     dword ptr [rax+rax+00h]
0x14003e8eb  mov     eax, [rdi+0C8h]
0x14003e8f1  bt      eax, 8
0x14003e8f5  jb      short loc_14003E92F
0x14003e8f7  mov     rcx, [rbx+10h]; Resource
0x14003e8fb  mov     dl, 1; Wait
0x14003e8fd  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14003e904  nop     dword ptr [rax+rax+00h]
0x14003e909  mov     r8d, 2
0x14003e90f  cmp     esi, r8d
0x14003e912  jnz     short loc_14003E91F
0x14003e914  xor     r9d, r9d
0x14003e917  mov     rdx, rbx
0x14003e91a  call    FatMarkFcbCondition
0x14003e91f  mov     rcx, [rbx+10h]; Resource
0x14003e923  call    cs:__imp_ExReleaseResourceLite
0x14003e92a  nop     dword ptr [rax+rax+00h]
0x14003e92f  mov     eax, dword ptr [rsp+38h+IoStatus]
0x14003e933  mov     rbx, [rsp+38h+arg_0]
0x14003e938  mov     rsi, [rsp+38h+arg_8]
0x14003e93d  add     rsp, 30h
0x14003e941  pop     rdi
0x14003e942  retn
```
