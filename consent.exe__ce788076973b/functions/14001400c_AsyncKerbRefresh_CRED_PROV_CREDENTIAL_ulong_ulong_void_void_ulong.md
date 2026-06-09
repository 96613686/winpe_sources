# AsyncKerbRefresh(_CRED_PROV_CREDENTIAL *,ulong,ulong,void *,void * *,ulong *)

- ea: `0x14001400c`
- end: `0x1400140c2`
- name: `?AsyncKerbRefresh@@YAKPEAU_CRED_PROV_CREDENTIAL@@KKPEAXPEAPEAXPEAK@Z`
- size: `182`
- prototype: `__int64 __fastcall(struct _CRED_PROV_CREDENTIAL *, int, int, void *, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001700c`

## callees

- `0x14001400c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001402b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140014058`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001402b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140014058`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14001409c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14001409c`

## pseudocode

```c
__int64 __fastcall AsyncKerbRefresh(
        struct _CRED_PROV_CREDENTIAL *a1,
        int a2,
        int a3,
        void *a4,
        void **a5,
        unsigned int *a6)
{
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  _DWORD *v13; // rax
  HANDLE Thread; // rax

  v10 = LocalAlloc(0x40u, 0x18u);
  v11 = v10;
  if ( !v10 )
    return 8;
  *(_OWORD *)v10 = *(_OWORD *)a1;
  v10[2] = *((_QWORD *)a1 + 2);
  v13 = LocalAlloc(0x40u, 0x20u);
  if ( !v13 )
    return 8;
  *(_QWORD *)v13 = v11;
  v13[2] = a2;
  v13[3] = a3;
  *((_QWORD *)v13 + 2) = a4;
  *((_QWORD *)v13 + 3) = a6;
  Thread = CreateThread(0, 0, AttemptKerbRefresh, v13, 0, 0);
  if ( !Thread )
    return 8;
  *a5 = Thread;
  return 0;
}

```

## disassembly

```asm
0x14001400c  push    rbx
0x14001400e  push    rbp
0x14001400f  push    rsi
0x140014010  push    rdi
0x140014011  push    r14
0x140014013  sub     rsp, 30h
0x140014017  mov     r14d, edx
0x14001401a  mov     rdi, rcx
0x14001401d  mov     edx, 18h; uBytes
0x140014022  mov     rsi, r9
0x140014025  mov     ebp, r8d
0x140014028  lea     ecx, [rdx+28h]; uFlags
0x14001402b  call    cs:__imp_LocalAlloc
0x140014031  mov     rbx, rax
0x140014034  test    rax, rax
0x140014037  jnz     short loc_140014040
0x140014039  mov     eax, 8
0x14001403e  jmp     short loc_1400140B7
0x140014040  movups  xmm0, xmmword ptr [rdi]
0x140014043  mov     edx, 20h ; ' '; uBytes
0x140014048  movups  xmmword ptr [rax], xmm0
0x14001404b  movsd   xmm1, qword ptr [rdi+10h]
0x140014050  lea     ecx, [rdx+20h]; uFlags
0x140014053  movsd   qword ptr [rax+10h], xmm1
0x140014058  call    cs:__imp_LocalAlloc
0x14001405e  mov     r9, rax; lpParameter
0x140014061  test    rax, rax
0x140014064  jz      short loc_140014039
0x140014066  mov     [rax], rbx
0x140014069  lea     r8, ?AttemptKerbRefresh@@YAKPEAX@Z; lpStartAddress
0x140014070  mov     [rax+8], r14d
0x140014074  xor     edx, edx; dwStackSize
0x140014076  mov     [rax+0Ch], ebp
0x140014079  xor     ecx, ecx; lpThreadAttributes
0x14001407b  mov     [rax+10h], rsi
0x14001407f  mov     rax, [rsp+58h+arg_28]
0x140014087  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x140014090  mov     [r9+18h], rax
0x140014094  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x14001409c  call    cs:__imp_CreateThread
0x1400140a2  mov     rcx, rax
0x1400140a5  test    rax, rax
0x1400140a8  jz      short loc_140014039
0x1400140aa  mov     rax, [rsp+58h+arg_20]
0x1400140b2  mov     [rax], rcx
0x1400140b5  xor     eax, eax
0x1400140b7  add     rsp, 30h
0x1400140bb  pop     r14
0x1400140bd  pop     rdi
0x1400140be  pop     rsi
0x1400140bf  pop     rbp
0x1400140c0  pop     rbx
0x1400140c1  retn
```
