# TdhpGetWPPCache(TDH_MOF_INFO *,_EVENT_RECORD *,ulong,_TDH_CONTEXT *,_STRUCTUREDMESSAGE * *,ulong *)

- ea: `0x180016df4`
- end: `0x180017069`
- name: `?TdhpGetWPPCache@@YAKPEAUTDH_MOF_INFO@@PEAU_EVENT_RECORD@@KPEAU_TDH_CONTEXT@@PEAPEAU_STRUCTUREDMESSAGE@@PEAK@Z`
- size: `629`
- prototype: `unsigned int __fastcall(struct TDH_MOF_INFO *, struct _EVENT_RECORD *, unsigned int, struct _TDH_CONTEXT *, struct _STRUCTUREDMESSAGE **, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800010c0`
- `0x180001730`
- `0x180003270`

## callees

- `0x18000f870`
- `0x180016df4`
- `0x180023af9`
- `0x18002b5b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016ee3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016ee3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016f09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016f5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016f70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016fe7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001700c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017028`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016f09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016f5c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016f70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016fe7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001700c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017028`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016ecf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016efb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016f4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016f62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016fd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016ffe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001701a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016ecf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016efb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016f4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016f62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016fd9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016ffe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001701a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int __fastcall TdhpGetWPPCache(
        struct TDH_MOF_INFO *a1,
        struct _EVENT_RECORD *a2,
        unsigned int a3,
        struct _TDH_CONTEXT *a4,
        struct _STRUCTUREDMESSAGE **a5,
        unsigned int *a6)
{
  struct TDH_MOF_INFO *v6; // rdi
  struct TDH_MOF_INFO *v7; // rbx
  struct TDH_MOF_INFO *v12; // r14
  PVOID UserData; // rdx
  void *v15; // rbp
  unsigned int v16; // r14d
  unsigned int result; // eax
  HANDLE ProcessHeap; // rax
  char *v19; // rax
  _QWORD *v20; // rbx
  void *v21; // rbx
  HANDLE v22; // rax
  unsigned int v23; // esi
  HANDLE v24; // rax
  HANDLE v25; // rax
  __int64 v26; // rax
  _QWORD *v27; // rsi
  __int64 v28; // rax
  _QWORD *v29; // rcx
  void *v30; // r15
  HANDLE v31; // rax
  void *v32; // r15
  HANDLE v33; // rax
  HANDLE v34; // rax
  __int64 v35; // rax
  LPVOID lpMem; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v37; // [rsp+90h] [rbp+8h] BYREF

  v6 = (struct TDH_MOF_INFO *)((char *)a1 + 6280);
  v37 = 0;
  v7 = (struct TDH_MOF_INFO *)*((_QWORD *)a1 + 785);
  lpMem = 0;
  if ( v7 != (struct TDH_MOF_INFO *)((char *)a1 + 6280) )
  {
    while ( 1 )
    {
      if ( v6 == v7 )
        goto LABEL_11;
      v12 = v7;
      v7 = *(struct TDH_MOF_INFO **)v7;
      if ( !memcmp_0((char *)v12 + 16, a2, 0x50u)
        && *((_DWORD *)v12 + 24) == *(_DWORD *)&a2->BufferContext.ProcessorNumber
        && *((_WORD *)v12 + 50) == a2->UserDataLength )
      {
        UserData = a2->UserData;
        if ( UserData
           ? memcmp_0(*((const void **)v12 + 13), UserData, *((unsigned __int16 *)v12 + 50)) == 0
           : *((_QWORD *)v12 + 13) == 0 )
        {
          break;
        }
      }
    }
    v15 = (void *)*((_QWORD *)v12 + 14);
    v16 = *((_DWORD *)v12 + 30);
    lpMem = v15;
    v37 = v16;
    if ( v15 )
      goto LABEL_32;
  }
LABEL_11:
  result = TdhpGetWPPStructMessage(0, a2, a3, a4, (struct _STRUCTUREDMESSAGE **)&lpMem, &v37);
  if ( result )
    return result;
  ProcessHeap = GetProcessHeap();
  v19 = (char *)HeapAlloc(ProcessHeap, 8u, 0x80u);
  v20 = v19;
  if ( !v19 )
  {
    v21 = lpMem;
    if ( lpMem )
    {
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v21);
    }
    return 8;
  }
  v15 = lpMem;
  v16 = v37;
  *((_QWORD *)v19 + 14) = lpMem;
  *((_DWORD *)v19 + 30) = v16;
  v23 = TdhpCopyWppEventRecord((struct WPPEVENT_RECORD *)(v19 + 16), a2);
  if ( !v23 )
  {
    if ( *((_DWORD *)a1 + 1574) >= 0x40u )
    {
      v27 = (_QWORD *)*((_QWORD *)v6 + 1);
      v28 = *v27;
      if ( *(_QWORD **)(*v27 + 8LL) == v27 )
      {
        v29 = (_QWORD *)v27[1];
        if ( (_QWORD *)*v29 == v27 )
        {
          *v29 = v28;
          *(_QWORD *)(v28 + 8) = v29;
          v30 = (void *)v27[14];
          if ( v30 )
          {
            v31 = GetProcessHeap();
            HeapFree(v31, 0, v30);
            v27[14] = 0;
          }
          v32 = (void *)v27[13];
          if ( v32 )
          {
            v33 = GetProcessHeap();
            HeapFree(v33, 0, v32);
            v27[13] = 0;
          }
          v34 = GetProcessHeap();
          HeapFree(v34, 0, v27);
          v35 = *(_QWORD *)v6;
          if ( *(struct TDH_MOF_INFO **)(*(_QWORD *)v6 + 8LL) == v6 )
          {
            *v20 = v35;
            v20[1] = v6;
            *(_QWORD *)(v35 + 8) = v20;
            *(_QWORD *)v6 = v20;
            goto LABEL_32;
          }
        }
      }
    }
    else
    {
      v26 = *(_QWORD *)v6;
      if ( *(struct TDH_MOF_INFO **)(*(_QWORD *)v6 + 8LL) == v6 )
      {
        *v20 = v26;
        v20[1] = v6;
        *(_QWORD *)(v26 + 8) = v20;
        *(_QWORD *)v6 = v20;
        ++*((_DWORD *)a1 + 1574);
LABEL_32:
        *a5 = (struct _STRUCTUREDMESSAGE *)v15;
        *a6 = v16;
        return 0;
      }
    }
    __fastfail(3u);
  }
  if ( v15 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v15);
  }
  v25 = GetProcessHeap();
  HeapFree(v25, 0, v20);
  return v23;
}

```

## disassembly

```asm
0x180016df4  mov     rax, rsp
0x180016df7  push    rbx
0x180016df8  push    rbp
0x180016df9  push    rsi
0x180016dfa  push    rdi
0x180016dfb  push    r12
0x180016dfd  push    r13
0x180016dff  push    r14
0x180016e01  push    r15
0x180016e03  sub     rsp, 48h
0x180016e07  lea     rdi, [rcx+1888h]
0x180016e0e  mov     dword ptr [rax+8], 0
0x180016e15  mov     rbx, [rdi]
0x180016e18  mov     r12, r9
0x180016e1b  mov     qword ptr [rax-58h], 0
0x180016e23  mov     r13d, r8d
0x180016e26  mov     rsi, rdx
0x180016e29  mov     r15, rcx
0x180016e2c  cmp     rbx, rdi
0x180016e2f  jz      short loc_180016EA4
0x180016e31  cmp     rdi, rbx
0x180016e34  jz      short loc_180016EA4
0x180016e36  mov     r14, rbx
0x180016e39  mov     r8d, 50h ; 'P'; Size
0x180016e3f  mov     rbx, [rbx]
0x180016e42  mov     rdx, rsi; Buf2
0x180016e45  lea     rcx, [r14+10h]; Buf1
0x180016e49  call    memcmp_0
0x180016e4e  test    eax, eax
0x180016e50  jnz     short loc_180016E31
0x180016e52  mov     eax, [r14+60h]
0x180016e56  cmp     eax, [rsi+50h]
0x180016e59  jnz     short loc_180016E31
0x180016e5b  movzx   eax, word ptr [r14+64h]
0x180016e60  cmp     ax, [rsi+56h]
0x180016e64  jnz     short loc_180016E31
0x180016e66  mov     rdx, [rsi+60h]; Buf2
0x180016e6a  test    rdx, rdx
0x180016e6d  jz      short loc_180016E7F
0x180016e6f  mov     rcx, [r14+68h]; Buf1
0x180016e73  mov     r8d, eax; Size
0x180016e76  call    memcmp_0
0x180016e7b  test    eax, eax
0x180016e7d  jmp     short loc_180016E84
0x180016e7f  cmp     qword ptr [r14+68h], 0
0x180016e84  jnz     short loc_180016E31
0x180016e86  mov     rbp, [r14+70h]
0x180016e8a  mov     r14d, [r14+78h]
0x180016e8e  mov     [rsp+88h+lpMem], rbp
0x180016e93  mov     [rsp+88h+arg_0], r14d
0x180016e9b  test    rbp, rbp
0x180016e9e  jnz     loc_180017045
0x180016ea4  lea     rax, [rsp+88h+arg_0]
0x180016eac  mov     r9, r12; struct _TDH_CONTEXT *
0x180016eaf  mov     [rsp+88h+var_60], rax; unsigned int *
0x180016eb4  mov     r8d, r13d; unsigned int
0x180016eb7  lea     rax, [rsp+88h+lpMem]
0x180016ebc  mov     rdx, rsi; struct _EVENT_RECORD *
0x180016ebf  xor     ecx, ecx; void *
0x180016ec1  mov     [rsp+88h+var_68], rax; struct _STRUCTUREDMESSAGE **
0x180016ec6  call    ?TdhpGetWPPStructMessage@@YAKPEAXPEAU_EVENT_RECORD@@KPEAU_TDH_CONTEXT@@PEAPEAU_STRUCTUREDMESSAGE@@PEAK@Z; TdhpGetWPPStructMessage(void *,_EVENT_RECORD *,ulong,_TDH_CONTEXT *,_STRUCTUREDMESSAGE * *,ulong *)
0x180016ecb  test    eax, eax
0x180016ecd  jnz     short loc_180016F11
0x180016ecf  call    cs:__imp_GetProcessHeap
0x180016ed5  mov     ebp, 8
0x180016eda  mov     rcx, rax; hHeap
0x180016edd  mov     edx, ebp; dwFlags
0x180016edf  lea     r8d, [rbp+78h]; dwBytes
0x180016ee3  call    cs:__imp_HeapAlloc
0x180016ee9  mov     rbx, rax
0x180016eec  test    rax, rax
0x180016eef  jnz     short loc_180016F22
0x180016ef1  mov     rbx, [rsp+88h+lpMem]
0x180016ef6  test    rbx, rbx
0x180016ef9  jz      short loc_180016F0F
0x180016efb  call    cs:__imp_GetProcessHeap
0x180016f01  mov     r8, rbx; lpMem
0x180016f04  xor     edx, edx; dwFlags
0x180016f06  mov     rcx, rax; hHeap
0x180016f09  call    cs:__imp_HeapFree
0x180016f0f  mov     eax, ebp
0x180016f11  add     rsp, 48h
0x180016f15  pop     r15
0x180016f17  pop     r14
0x180016f19  pop     r13
0x180016f1b  pop     r12
0x180016f1d  pop     rdi
0x180016f1e  pop     rsi
0x180016f1f  pop     rbp
0x180016f20  pop     rbx
0x180016f21  retn
0x180016f22  mov     rbp, [rsp+88h+lpMem]
0x180016f27  lea     rcx, [rax+10h]; struct WPPEVENT_RECORD *
0x180016f2b  mov     r14d, [rsp+88h+arg_0]
0x180016f33  mov     rdx, rsi; struct _EVENT_RECORD *
0x180016f36  mov     [rax+70h], rbp
0x180016f3a  mov     [rax+78h], r14d
0x180016f3e  call    ?TdhpCopyWppEventRecord@@YAKPEAUWPPEVENT_RECORD@@PEAU_EVENT_RECORD@@@Z; TdhpCopyWppEventRecord(WPPEVENT_RECORD *,_EVENT_RECORD *)
0x180016f43  mov     esi, eax
0x180016f45  test    eax, eax
0x180016f47  jz      short loc_180016F7A
0x180016f49  test    rbp, rbp
0x180016f4c  jz      short loc_180016F62
0x180016f4e  call    cs:__imp_GetProcessHeap
0x180016f54  mov     r8, rbp; lpMem
0x180016f57  xor     edx, edx; dwFlags
0x180016f59  mov     rcx, rax; hHeap
0x180016f5c  call    cs:__imp_HeapFree
0x180016f62  call    cs:__imp_GetProcessHeap
0x180016f68  mov     r8, rbx; lpMem
0x180016f6b  xor     edx, edx; dwFlags
0x180016f6d  mov     rcx, rax; hHeap
0x180016f70  call    cs:__imp_HeapFree
0x180016f76  mov     eax, esi
0x180016f78  jmp     short loc_180016F11
0x180016f7a  cmp     dword ptr [r15+1898h], 40h ; '@'
0x180016f82  jnb     short loc_180016FAB
0x180016f84  mov     rax, [rdi]
0x180016f87  cmp     [rax+8], rdi
0x180016f8b  jnz     loc_180017062
0x180016f91  mov     [rbx], rax
0x180016f94  mov     [rbx+8], rdi
0x180016f98  mov     [rax+8], rbx
0x180016f9c  mov     [rdi], rbx
0x180016f9f  inc     dword ptr [r15+1898h]
0x180016fa6  jmp     loc_180017045
0x180016fab  mov     rsi, [rdi+8]
0x180016faf  mov     rax, [rsi]
0x180016fb2  cmp     [rax+8], rsi
0x180016fb6  jnz     loc_180017062
0x180016fbc  mov     rcx, [rsi+8]
0x180016fc0  cmp     [rcx], rsi
0x180016fc3  jnz     loc_180017062
0x180016fc9  mov     [rcx], rax
0x180016fcc  mov     [rax+8], rcx
0x180016fd0  mov     r15, [rsi+70h]
0x180016fd4  test    r15, r15
0x180016fd7  jz      short loc_180016FF5
0x180016fd9  call    cs:__imp_GetProcessHeap
0x180016fdf  mov     r8, r15; lpMem
0x180016fe2  xor     edx, edx; dwFlags
0x180016fe4  mov     rcx, rax; hHeap
0x180016fe7  call    cs:__imp_HeapFree
0x180016fed  mov     qword ptr [rsi+70h], 0
0x180016ff5  mov     r15, [rsi+68h]
0x180016ff9  test    r15, r15
0x180016ffc  jz      short loc_18001701A
0x180016ffe  call    cs:__imp_GetProcessHeap
0x180017004  mov     r8, r15; lpMem
0x180017007  xor     edx, edx; dwFlags
0x180017009  mov     rcx, rax; hHeap
0x18001700c  call    cs:__imp_HeapFree
0x180017012  mov     qword ptr [rsi+68h], 0
0x18001701a  call    cs:__imp_GetProcessHeap
0x180017020  mov     r8, rsi; lpMem
0x180017023  xor     edx, edx; dwFlags
0x180017025  mov     rcx, rax; hHeap
0x180017028  call    cs:__imp_HeapFree
0x18001702e  mov     rax, [rdi]
0x180017031  cmp     [rax+8], rdi
0x180017035  jnz     short loc_180017062
0x180017037  mov     [rbx], rax
0x18001703a  mov     [rbx+8], rdi
0x18001703e  mov     [rax+8], rbx
0x180017042  mov     [rdi], rbx
0x180017045  mov     rax, [rsp+88h+arg_20]
0x18001704d  mov     [rax], rbp
0x180017050  mov     rax, [rsp+88h+arg_28]
0x180017058  mov     [rax], r14d
0x18001705b  xor     eax, eax
0x18001705d  jmp     loc_180016F11
0x180017062  mov     ecx, 3
0x180017067  int     29h; Win8: RtlFailFast(ecx)
```
