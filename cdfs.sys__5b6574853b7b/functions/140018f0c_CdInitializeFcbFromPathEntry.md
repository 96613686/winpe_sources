# CdInitializeFcbFromPathEntry

- ea: `0x140018f0c`
- end: `0x140019046`
- name: `CdInitializeFcbFromPathEntry`
- size: `314`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e1d0`
- `0x140019a00`

## callees

- `0x140018f0c`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTable` at `0x140019027`
- `ntoskrnl!RtlInsertElementGenericTable` at `0x140019027`

## pseudocode

```c
PVOID __fastcall CdInitializeFcbFromPathEntry(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  __int64 v4; // r10
  unsigned __int64 *v7; // r8
  unsigned __int64 v8; // rdx
  __int64 v9; // rax
  _QWORD *v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rax
  struct _RTL_GENERIC_TABLE *v13; // rcx
  PVOID result; // rax
  _QWORD Buffer[3]; // [rsp+20h] [rbp-18h] BYREF

  v4 = *(_QWORD *)(a2 + 120);
  v7 = *(unsigned __int64 **)(a2 + 288);
  *(_DWORD *)(a2 + 480) = (a4[2] & (*(_DWORD *)(v4 + 436) - 1)) << *(_DWORD *)(v4 + 432);
  *(_DWORD *)(a2 + 504) = *a4;
  *(_QWORD *)(a2 + 8) = v4 + 232;
  *(_QWORD *)(a2 + 40) = 2048;
  *(_QWORD *)(a2 + 32) = 2048;
  *(_QWORD *)(a2 + 24) = 2048;
  v8 = (unsigned __int64)(unsigned int)a4[2] << *(_DWORD *)(v4 + 432);
  *v7 = v8;
  v9 = *(unsigned int *)(a2 + 480);
  v7[1] = 2048;
  *v7 = v8 - v9;
  v7[2] = 0;
  v7[4] = 2048;
  v7[3] = 2048;
  *(_DWORD *)(a2 + 176) |= 0x10u;
  *(_DWORD *)(a2 + 284) = 1;
  if ( a3 )
  {
    *(_QWORD *)(a2 + 128) = a3;
    v10 = *(_QWORD **)(a3 + 496);
    if ( *v10 != a3 + 488 )
      __fastfail(3u);
    *(_QWORD *)(a2 + 136) = a3 + 488;
    *(_QWORD *)(a2 + 144) = v10;
    *v10 = a2 + 136;
    *(_QWORD *)(a3 + 496) = a2 + 136;
    v11 = *(_QWORD *)(a3 + 120);
    ++*(_DWORD *)(a3 + 164);
    ++*(_DWORD *)(a3 + 168);
    ++*(_DWORD *)(v11 + 60);
    ++*(_DWORD *)(*(_QWORD *)(a3 + 120) + 64LL);
  }
  v12 = *(_QWORD *)(a2 + 152);
  v13 = (struct _RTL_GENERIC_TABLE *)(*(_QWORD *)(a2 + 120) + 448LL);
  Buffer[1] = a2;
  Buffer[0] = v12;
  result = RtlInsertElementGenericTable(v13, Buffer, 0x10u, 0);
  *(_DWORD *)(a2 + 172) |= 2u;
  return result;
}

```

## disassembly

```asm
0x140018f0c  mov     [rsp+arg_0], rbx
0x140018f11  push    rdi
0x140018f12  sub     rsp, 30h
0x140018f16  mov     r10, [rdx+78h]
0x140018f1a  mov     edi, 800h
0x140018f1f  mov     rbx, rdx
0x140018f22  mov     r11, r8
0x140018f25  mov     r8, [rdx+120h]
0x140018f2c  mov     eax, [r10+1B4h]
0x140018f33  mov     ecx, [r10+1B0h]
0x140018f3a  dec     eax
0x140018f3c  and     eax, [r9+8]
0x140018f40  shl     eax, cl
0x140018f42  mov     [rdx+1E0h], eax
0x140018f48  mov     eax, [r9]
0x140018f4b  mov     [rdx+1F8h], eax
0x140018f51  lea     rax, [r10+0E8h]
0x140018f58  mov     [rdx+8], rax
0x140018f5c  mov     [rdx+28h], rdi
0x140018f60  mov     [rdx+20h], rdi
0x140018f64  mov     [rdx+18h], rdi
0x140018f68  mov     edx, [r9+8]
0x140018f6c  mov     ecx, [r10+1B0h]
0x140018f73  shl     rdx, cl
0x140018f76  mov     [r8], rdx
0x140018f79  mov     eax, [rbx+1E0h]
0x140018f7f  mov     [r8+8], rdi
0x140018f83  sub     rdx, rax
0x140018f86  mov     [r8], rdx
0x140018f89  mov     qword ptr [r8+10h], 0
0x140018f91  mov     [r8+20h], rdi
0x140018f95  mov     [r8+18h], rdi
0x140018f99  mov     r8d, 10h; BufferSize
0x140018f9f  or      [rbx+0B0h], r8d
0x140018fa6  mov     dword ptr [rbx+11Ch], 1
0x140018fb0  test    r11, r11
0x140018fb3  jz      short loc_140019003
0x140018fb5  lea     rcx, [r11+1E8h]
0x140018fbc  mov     [rbx+80h], r11
0x140018fc3  mov     rdx, [rcx+8]
0x140018fc7  cmp     [rdx], rcx
0x140018fca  jz      short loc_140018FD2
0x140018fcc  lea     ecx, [r8-0Dh]
0x140018fd0  int     29h; Win8: RtlFailFast(ecx)
0x140018fd2  lea     rax, [rbx+88h]
0x140018fd9  mov     [rax], rcx
0x140018fdc  mov     [rax+8], rdx
0x140018fe0  mov     [rdx], rax
0x140018fe3  mov     [rcx+8], rax
0x140018fe7  mov     rax, [r11+78h]
0x140018feb  inc     dword ptr [r11+0A4h]
0x140018ff2  inc     dword ptr [r11+0A8h]
0x140018ff9  inc     dword ptr [rax+3Ch]
0x140018ffc  mov     rax, [r11+78h]
0x140019000  inc     dword ptr [rax+40h]
0x140019003  mov     rcx, [rbx+78h]
0x140019007  lea     rdx, [rsp+38h+Buffer]; Buffer
0x14001900c  mov     rax, [rbx+98h]
0x140019013  add     rcx, 1C0h; Table
0x14001901a  xor     r9d, r9d; NewElement
0x14001901d  mov     [rsp+38h+var_10], rbx
0x140019022  mov     [rsp+38h+Buffer], rax
0x140019027  call    cs:__imp_RtlInsertElementGenericTable
0x14001902e  nop     dword ptr [rax+rax+00h]
0x140019033  or      dword ptr [rbx+0ACh], 2
0x14001903a  mov     rbx, [rsp+38h+arg_0]
0x14001903f  add     rsp, 30h
0x140019043  pop     rdi
0x140019044  retn
```
