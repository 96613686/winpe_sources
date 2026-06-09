# CdpAllocateServer

- ea: `0x14000d930`
- end: `0x14000dad5`
- name: `CdpAllocateServer`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d5c0`

## callees

- `0x14000d930`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000d94d`
- `ntoskrnl!ExAllocatePool2` at `0x14000d94d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000da42`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000da42`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000daa0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000daa0`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000da57`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000da57`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000da94`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000da94`

## pseudocode

```c
__int64 __fastcall CdpAllocateServer(__int64 *a1)
{
  __int64 Pool2; // rax
  __int64 v3; // rbx
  _QWORD *v4; // rcx
  __int64 result; // rax

  Pool2 = ExAllocatePool2(257, 264, 1699963971);
  v3 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  *(_OWORD *)(Pool2 + 8) = 0;
  *(_QWORD *)(Pool2 + 32) = 0;
  *(_OWORD *)(Pool2 + 48) = 0;
  *(_DWORD *)(Pool2 + 73) = 0;
  *(_WORD *)(Pool2 + 77) = 0;
  *(_BYTE *)(Pool2 + 79) = 0;
  *(_OWORD *)(Pool2 + 184) = 0;
  *(_OWORD *)(Pool2 + 224) = 0;
  *(_QWORD *)(Pool2 + 256) = 0;
  *(_QWORD *)Pool2 = CdServerType;
  *(_QWORD *)(Pool2 + 24) = 1;
  *(_QWORD *)(Pool2 + 40) = 0;
  *(_QWORD *)(Pool2 + 216) = 0;
  *(_QWORD *)(Pool2 + 208) = Pool2 + 200;
  *(_QWORD *)(Pool2 + 200) = Pool2 + 200;
  *(_QWORD *)(Pool2 + 248) = Pool2 + 240;
  *(_QWORD *)(Pool2 + 240) = Pool2 + 240;
  *(_QWORD *)(Pool2 + 64) = Pool2 + 40;
  *(_BYTE *)(Pool2 + 72) = 1;
  *(_QWORD *)(Pool2 + 80) = 0;
  *(_QWORD *)(Pool2 + 96) = Pool2 + 88;
  *(_QWORD *)(Pool2 + 88) = Pool2 + 88;
  *(_QWORD *)(Pool2 + 112) = Pool2 + 104;
  *(_QWORD *)(Pool2 + 104) = Pool2 + 104;
  *(_QWORD *)(Pool2 + 128) = Pool2 + 120;
  *(_QWORD *)(Pool2 + 120) = Pool2 + 120;
  *(_QWORD *)(Pool2 + 144) = Pool2 + 136;
  *(_QWORD *)(Pool2 + 136) = Pool2 + 136;
  *(_QWORD *)(Pool2 + 160) = Pool2 + 152;
  *(_QWORD *)(Pool2 + 152) = Pool2 + 152;
  *(_QWORD *)(Pool2 + 176) = Pool2 + 168;
  *(_QWORD *)(Pool2 + 168) = Pool2 + 168;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&CdpServerListLock, 0);
  v4 = (_QWORD *)qword_140005188;
  if ( *(__int64 **)qword_140005188 != &CdpServerList )
    __fastfail(3u);
  *(_QWORD *)(v3 + 8) = &CdpServerList;
  *(_QWORD *)(v3 + 16) = v4;
  *v4 = v3 + 8;
  qword_140005188 = v3 + 8;
  ExReleasePushLockExclusiveEx(&CdpServerListLock, 0);
  KeLeaveCriticalRegion();
  result = 0;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x14000d930  mov     [rsp+arg_0], rbx
0x14000d935  push    rdi
0x14000d936  sub     rsp, 20h
0x14000d93a  mov     rdi, rcx
0x14000d93d  mov     edx, 108h
0x14000d942  mov     ecx, 101h
0x14000d947  mov     r8d, 65536443h
0x14000d94d  call    cs:__imp_ExAllocatePool2
0x14000d954  nop     dword ptr [rax+rax+00h]
0x14000d959  mov     rbx, rax
0x14000d95c  test    rax, rax
0x14000d95f  jz      loc_14000DABD
0x14000d965  xorps   xmm0, xmm0
0x14000d968  lea     rcx, [rbx+28h]
0x14000d96c  movups  xmmword ptr [rax+8], xmm0
0x14000d970  xor     eax, eax
0x14000d972  xor     edx, edx
0x14000d974  mov     [rbx+20h], rax
0x14000d978  xorps   xmm1, xmm1
0x14000d97b  movups  xmmword ptr [rbx+30h], xmm0
0x14000d97f  mov     [rbx+49h], eax
0x14000d982  mov     [rbx+4Dh], ax
0x14000d986  mov     [rbx+4Fh], al
0x14000d989  movups  xmmword ptr [rbx+0B8h], xmm0
0x14000d990  movups  xmmword ptr [rbx+0E0h], xmm1
0x14000d997  mov     [rbx+100h], rax
0x14000d99e  lea     rax, CdServerType
0x14000d9a5  mov     [rbx], rax
0x14000d9a8  lea     rax, [rbx+0C8h]
0x14000d9af  mov     qword ptr [rbx+18h], 1
0x14000d9b7  mov     [rcx], rdx
0x14000d9ba  mov     [rbx+0D8h], rdx
0x14000d9c1  mov     [rax+8], rax
0x14000d9c5  mov     [rax], rax
0x14000d9c8  lea     rax, [rbx+0F0h]
0x14000d9cf  mov     [rax+8], rax
0x14000d9d3  mov     [rax], rax
0x14000d9d6  lea     rax, [rbx+58h]
0x14000d9da  mov     [rbx+40h], rcx
0x14000d9de  mov     byte ptr [rbx+48h], 1
0x14000d9e2  mov     [rbx+50h], rdx
0x14000d9e6  mov     [rax+8], rax
0x14000d9ea  mov     [rax], rax
0x14000d9ed  lea     rax, [rbx+68h]
0x14000d9f1  mov     [rbx+70h], rax
0x14000d9f5  mov     [rax], rax
0x14000d9f8  lea     rax, [rbx+78h]
0x14000d9fc  mov     [rbx+80h], rax
0x14000da03  mov     [rbx+78h], rax
0x14000da07  lea     rax, [rbx+88h]
0x14000da0e  mov     [rbx+90h], rax
0x14000da15  mov     [rax], rax
0x14000da18  lea     rax, [rbx+98h]
0x14000da1f  mov     [rbx+0A0h], rax
0x14000da26  mov     [rbx+98h], rax
0x14000da2d  lea     rax, [rbx+0A8h]
0x14000da34  mov     [rbx+0B0h], rax
0x14000da3b  mov     [rbx+0A8h], rax
0x14000da42  call    cs:__imp_KeEnterCriticalRegion
0x14000da49  nop     dword ptr [rax+rax+00h]
0x14000da4e  xor     edx, edx
0x14000da50  lea     rcx, CdpServerListLock
0x14000da57  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000da5e  nop     dword ptr [rax+rax+00h]
0x14000da63  mov     rcx, cs:qword_140005188
0x14000da6a  lea     rdx, CdpServerList
0x14000da71  cmp     [rcx], rdx
0x14000da74  jnz     short loc_14000DACE
0x14000da76  lea     rax, [rbx+8]
0x14000da7a  mov     [rax], rdx
0x14000da7d  xor     edx, edx
0x14000da7f  mov     [rax+8], rcx
0x14000da83  mov     [rcx], rax
0x14000da86  lea     rcx, CdpServerListLock
0x14000da8d  mov     cs:qword_140005188, rax
0x14000da94  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000da9b  nop     dword ptr [rax+rax+00h]
0x14000daa0  call    cs:__imp_KeLeaveCriticalRegion
0x14000daa7  nop     dword ptr [rax+rax+00h]
0x14000daac  xor     eax, eax
0x14000daae  mov     [rdi], rbx
0x14000dab1  mov     rbx, [rsp+28h+arg_0]
0x14000dab6  add     rsp, 20h
0x14000daba  pop     rdi
0x14000dabb  retn
0x14000dabd  mov     rbx, [rsp+28h+arg_0]
0x14000dac2  mov     eax, 0C000009Ah
0x14000dac7  add     rsp, 20h
0x14000dacb  pop     rdi
0x14000dacc  retn
0x14000dace  mov     ecx, 3
0x14000dad3  int     29h; Win8: RtlFailFast(ecx)
```
