# EtwpHeapPush(_TRACE_STREAM_HEAP *,_TRACE_STREAM_CONTEXT *)

- ea: `0x180014558`
- end: `0x180014682`
- name: `?EtwpHeapPush@@YAXPEAU_TRACE_STREAM_HEAP@@PEAU_TRACE_STREAM_CONTEXT@@@Z`
- size: `298`
- prototype: `void __fastcall(struct _TRACE_STREAM_HEAP *, struct _TRACE_STREAM_CONTEXT *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ece4`
- `0x180010634`
- `0x1800148b8`

## callees

- `0x180010cf0`
- `0x180014558`

## pseudocode

```c
void __fastcall EtwpHeapPush(struct _TRACE_STREAM_HEAP *a1, struct _TRACE_STREAM_CONTEXT *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r14
  __int64 v6; // rax
  __int64 v7; // r13
  __int64 v8; // r12
  __int64 v9; // rsi
  __int64 v10; // rbp
  __int64 v11; // rdi
  unsigned int v12; // ecx
  unsigned int v13; // eax
  union _LARGE_INTEGER v14; // [rsp+60h] [rbp+8h] BYREF
  union _LARGE_INTEGER v15; // [rsp+68h] [rbp+10h] BYREF
  __int64 v16; // [rsp+70h] [rbp+18h]

  v4 = *(unsigned int *)a1;
  *((_QWORD *)a1 + v4 + 1) = a2;
  if ( (_DWORD)v4 )
  {
    while ( 1 )
    {
      v16 = (unsigned int)v4;
      v5 = (unsigned int)(v4 - 1) >> 1;
      v14.QuadPart = 0;
      v6 = *((_QWORD *)a1 + (unsigned int)v4 + 1);
      v15.QuadPart = 0;
      v7 = *((_QWORD *)a1 + v5 + 1);
      v8 = *(_QWORD *)(v6 + 64);
      v9 = *(_QWORD *)(v6 + 56);
      v10 = *(_QWORD *)(v7 + 64);
      v11 = *(_QWORD *)(v7 + 56);
      EtwpGetComparableEventTimeStamp((struct _TRACELOG_CONTEXT *)v10, (struct _ETW_EVENT_INFO *)v11, &v14);
      EtwpGetComparableEventTimeStamp((struct _TRACELOG_CONTEXT *)v8, (struct _ETW_EVENT_INFO *)v9, &v15);
      if ( v14.QuadPart < v15.QuadPart )
        break;
      if ( v14.QuadPart == v15.QuadPart )
      {
        if ( (*(_DWORD *)(v10 + 232) & 0xC000) == 0 )
          break;
        if ( (*(_DWORD *)(v10 + 32) & 0x10000000) != 0 )
        {
          if ( (*(_BYTE *)(v11 + 4) & 8) == 0 || (*(_BYTE *)(v11 + 6) & 1) == 0 )
            break;
          v12 = *(_DWORD *)(v11 + 64);
        }
        else
        {
          if ( (*(_BYTE *)(v11 + 2) & 4) == 0 )
            break;
          v12 = *(_DWORD *)(v11 + 48);
        }
        if ( (*(_DWORD *)(v8 + 232) & 0xC000) == 0 )
          break;
        if ( (*(_DWORD *)(v8 + 32) & 0x10000000) != 0 )
        {
          if ( (*(_BYTE *)(v9 + 4) & 8) == 0 || (*(_BYTE *)(v9 + 6) & 1) == 0 )
            break;
          v13 = *(_DWORD *)(v9 + 64);
        }
        else
        {
          if ( (*(_BYTE *)(v9 + 2) & 4) == 0 )
            break;
          v13 = *(_DWORD *)(v9 + 48);
        }
        if ( v12 <= v13 )
          break;
      }
      *((_QWORD *)a1 + v16 + 1) = v7;
      *((_QWORD *)a1 + v5 + 1) = a2;
      if ( !(_DWORD)v5 )
        break;
      LODWORD(v4) = v5;
    }
  }
  ++*(_DWORD *)a1;
}

```

## disassembly

```asm
0x180014558  mov     [rsp+arg_18], rbx
0x18001455d  push    rbp
0x18001455e  push    rsi
0x18001455f  push    rdi
0x180014560  push    r12
0x180014562  push    r13
0x180014564  push    r14
0x180014566  push    r15
0x180014568  sub     rsp, 20h
0x18001456c  mov     rbx, rcx
0x18001456f  mov     r15, rdx
0x180014572  mov     ecx, [rcx]
0x180014574  mov     [rbx+rcx*8+8], rdx
0x180014579  test    ecx, ecx
0x18001457b  jz      loc_18001466B
0x180014581  lea     r14d, [rcx-1]
0x180014585  mov     eax, ecx
0x180014587  mov     [rsp+58h+arg_10], rax
0x18001458c  lea     r8, [rsp+58h+arg_0]; union _LARGE_INTEGER *
0x180014591  shr     r14d, 1
0x180014594  mov     qword ptr [rsp+58h+arg_0], 0
0x18001459d  mov     rax, [rbx+rax*8+8]
0x1800145a2  mov     qword ptr [rsp+58h+arg_8], 0
0x1800145ab  mov     r13, [rbx+r14*8+8]
0x1800145b0  mov     r12, [rax+40h]
0x1800145b4  mov     rsi, [rax+38h]
0x1800145b8  mov     rbp, [r13+40h]
0x1800145bc  mov     rdi, [r13+38h]
0x1800145c0  mov     rcx, rbp; struct _TRACELOG_CONTEXT *
0x1800145c3  mov     rdx, rdi; struct _ETW_EVENT_INFO *
0x1800145c6  call    ?EtwpGetComparableEventTimeStamp@@YAXPEAU_TRACELOG_CONTEXT@@PEAU_ETW_EVENT_INFO@@PEAT_LARGE_INTEGER@@@Z; EtwpGetComparableEventTimeStamp(_TRACELOG_CONTEXT *,_ETW_EVENT_INFO *,_LARGE_INTEGER *)
0x1800145cb  lea     r8, [rsp+58h+arg_8]; union _LARGE_INTEGER *
0x1800145d0  mov     rcx, r12; struct _TRACELOG_CONTEXT *
0x1800145d3  mov     rdx, rsi; struct _ETW_EVENT_INFO *
0x1800145d6  call    ?EtwpGetComparableEventTimeStamp@@YAXPEAU_TRACELOG_CONTEXT@@PEAU_ETW_EVENT_INFO@@PEAT_LARGE_INTEGER@@@Z; EtwpGetComparableEventTimeStamp(_TRACELOG_CONTEXT *,_ETW_EVENT_INFO *,_LARGE_INTEGER *)
0x1800145db  mov     rax, qword ptr [rsp+58h+arg_8]
0x1800145e0  cmp     qword ptr [rsp+58h+arg_0], rax
0x1800145e5  jl      loc_18001466B
0x1800145eb  jnz     short loc_18001464F
0x1800145ed  mov     eax, 0C000h
0x1800145f2  test    [rbp+0E8h], eax
0x1800145f8  jz      short loc_18001466B
0x1800145fa  mov     edx, 10000000h
0x1800145ff  test    [rbp+20h], edx
0x180014602  jz      short loc_180014615
0x180014604  test    byte ptr [rdi+4], 8
0x180014608  jz      short loc_18001466B
0x18001460a  test    byte ptr [rdi+6], 1
0x18001460e  jz      short loc_18001466B
0x180014610  mov     ecx, [rdi+40h]
0x180014613  jmp     short loc_18001461E
0x180014615  test    byte ptr [rdi+2], 4
0x180014619  jz      short loc_18001466B
0x18001461b  mov     ecx, [rdi+30h]
0x18001461e  test    [r12+0E8h], eax
0x180014626  jz      short loc_18001466B
0x180014628  test    [r12+20h], edx
0x18001462d  jz      short loc_180014640
0x18001462f  test    byte ptr [rsi+4], 8
0x180014633  jz      short loc_18001466B
0x180014635  test    byte ptr [rsi+6], 1
0x180014639  jz      short loc_18001466B
0x18001463b  mov     eax, [rsi+40h]
0x18001463e  jmp     short loc_180014649
0x180014640  test    byte ptr [rsi+2], 4
0x180014644  jz      short loc_18001466B
0x180014646  mov     eax, [rsi+30h]
0x180014649  cmp     ecx, eax
0x18001464b  jb      short loc_18001466B
0x18001464d  jz      short loc_18001466B
0x18001464f  mov     rax, [rsp+58h+arg_10]
0x180014654  mov     [rbx+rax*8+8], r13
0x180014659  mov     [rbx+r14*8+8], r15
0x18001465e  test    r14d, r14d
0x180014661  jz      short loc_18001466B
0x180014663  mov     ecx, r14d
0x180014666  jmp     loc_180014581
0x18001466b  inc     dword ptr [rbx]
0x18001466d  mov     rbx, [rsp+58h+arg_18]
0x180014672  add     rsp, 20h
0x180014676  pop     r15
0x180014678  pop     r14
0x18001467a  pop     r13
0x18001467c  pop     r12
0x18001467e  pop     rdi
0x18001467f  pop     rsi
0x180014680  pop     rbp
0x180014681  retn
```
