# EtwpInsertBuffer(_TRACELOG_CONTEXT *,_TRACE_BUFFER_LIST_ENTRY *)

- ea: `0x180015578`
- end: `0x180015659`
- name: `?EtwpInsertBuffer@@YAXPEAU_TRACELOG_CONTEXT@@PEAU_TRACE_BUFFER_LIST_ENTRY@@@Z`
- size: `225`
- prototype: `void __fastcall(struct _TRACELOG_CONTEXT *, struct _TRACE_BUFFER_LIST_ENTRY *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014b10`
- `0x180014e88`
- `0x18001502c`

## callees

- `0x180010cf0`
- `0x180015578`

## pseudocode

```c
void __fastcall EtwpInsertBuffer(struct _TRACELOG_CONTEXT *a1, struct _TRACE_BUFFER_LIST_ENTRY *a2)
{
  _QWORD *v2; // rsi
  __int64 *i; // rbx
  unsigned int v6; // eax
  unsigned int v7; // ecx
  union _LARGE_INTEGER v8; // [rsp+40h] [rbp+8h] BYREF
  union _LARGE_INTEGER v9; // [rsp+48h] [rbp+10h] BYREF

  v2 = (_QWORD *)((char *)a1 + 792);
  for ( i = (__int64 *)*((_QWORD *)a1 + 99); i; i = (__int64 *)*i )
  {
    v8.QuadPart = 0;
    v9.QuadPart = 0;
    EtwpGetComparableEventTimeStamp(a1, (struct _TRACE_BUFFER_LIST_ENTRY *)((char *)a2 + 40), &v8);
    EtwpGetComparableEventTimeStamp(a1, (struct _ETW_EVENT_INFO *)(i + 5), &v9);
    if ( v8.QuadPart < v9.QuadPart )
      break;
    if ( v8.QuadPart == v9.QuadPart )
    {
      if ( (*((_DWORD *)a1 + 58) & 0xC000) == 0 )
        break;
      if ( (*((_DWORD *)a1 + 8) & 0x10000000) != 0 )
      {
        if ( (*((_BYTE *)a2 + 44) & 8) == 0
          || (*((_BYTE *)a2 + 46) & 1) == 0
          || (*((_BYTE *)i + 44) & 8) == 0
          || (*((_BYTE *)i + 46) & 1) == 0 )
        {
          break;
        }
        v6 = *((_DWORD *)i + 26);
        v7 = *((_DWORD *)a2 + 26);
      }
      else
      {
        if ( (*((_BYTE *)a2 + 42) & 4) == 0 || (*((_BYTE *)i + 42) & 4) == 0 )
          break;
        v6 = *((_DWORD *)i + 22);
        v7 = *((_DWORD *)a2 + 22);
      }
      if ( v7 <= v6 )
        break;
    }
    v2 = i;
  }
  *(_QWORD *)a2 = *v2;
  *v2 = a2;
}

```

## disassembly

```asm
0x180015578  mov     [rsp+arg_10], rbx
0x18001557d  mov     [rsp+arg_18], rbp
0x180015582  push    rsi
0x180015583  push    rdi
0x180015584  push    r14
0x180015586  sub     rsp, 20h
0x18001558a  lea     rsi, [rcx+318h]
0x180015591  mov     rdi, rdx
0x180015594  mov     rbx, [rsi]
0x180015597  mov     rbp, rcx
0x18001559a  jmp     loc_180015634
0x18001559f  lea     r8, [rsp+38h+arg_0]; union _LARGE_INTEGER *
0x1800155a4  mov     qword ptr [rsp+38h+arg_0], 0
0x1800155ad  lea     rdx, [rdi+28h]; struct _ETW_EVENT_INFO *
0x1800155b1  mov     qword ptr [rsp+38h+arg_8], 0
0x1800155ba  mov     rcx, rbp; struct _TRACELOG_CONTEXT *
0x1800155bd  call    ?EtwpGetComparableEventTimeStamp@@YAXPEAU_TRACELOG_CONTEXT@@PEAU_ETW_EVENT_INFO@@PEAT_LARGE_INTEGER@@@Z; EtwpGetComparableEventTimeStamp(_TRACELOG_CONTEXT *,_ETW_EVENT_INFO *,_LARGE_INTEGER *)
0x1800155c2  lea     r8, [rsp+38h+arg_8]; union _LARGE_INTEGER *
0x1800155c7  mov     rcx, rbp; struct _TRACELOG_CONTEXT *
0x1800155ca  lea     rdx, [rbx+28h]; struct _ETW_EVENT_INFO *
0x1800155ce  call    ?EtwpGetComparableEventTimeStamp@@YAXPEAU_TRACELOG_CONTEXT@@PEAU_ETW_EVENT_INFO@@PEAT_LARGE_INTEGER@@@Z; EtwpGetComparableEventTimeStamp(_TRACELOG_CONTEXT *,_ETW_EVENT_INFO *,_LARGE_INTEGER *)
0x1800155d3  mov     rax, qword ptr [rsp+38h+arg_8]
0x1800155d8  cmp     qword ptr [rsp+38h+arg_0], rax
0x1800155dd  jl      short loc_18001563D
0x1800155df  jnz     short loc_18001562E
0x1800155e1  test    dword ptr [rbp+0E8h], 0C000h
0x1800155eb  jz      short loc_18001563D
0x1800155ed  test    dword ptr [rbp+20h], 10000000h
0x1800155f4  jz      short loc_180015616
0x1800155f6  test    byte ptr [rdi+2Ch], 8
0x1800155fa  jz      short loc_18001563D
0x1800155fc  test    byte ptr [rdi+2Eh], 1
0x180015600  jz      short loc_18001563D
0x180015602  test    byte ptr [rbx+2Ch], 8
0x180015606  jz      short loc_18001563D
0x180015608  test    byte ptr [rbx+2Eh], 1
0x18001560c  jz      short loc_18001563D
0x18001560e  mov     eax, [rbx+68h]
0x180015611  mov     ecx, [rdi+68h]
0x180015614  jmp     short loc_180015628
0x180015616  test    byte ptr [rdi+2Ah], 4
0x18001561a  jz      short loc_18001563D
0x18001561c  test    byte ptr [rbx+2Ah], 4
0x180015620  jz      short loc_18001563D
0x180015622  mov     eax, [rbx+58h]
0x180015625  mov     ecx, [rdi+58h]
0x180015628  cmp     ecx, eax
0x18001562a  jb      short loc_18001563D
0x18001562c  jz      short loc_18001563D
0x18001562e  mov     rsi, rbx
0x180015631  mov     rbx, [rbx]
0x180015634  test    rbx, rbx
0x180015637  jnz     loc_18001559F
0x18001563d  mov     rax, [rsi]
0x180015640  mov     rbx, [rsp+38h+arg_10]
0x180015645  mov     rbp, [rsp+38h+arg_18]
0x18001564a  mov     [rdi], rax
0x18001564d  mov     [rsi], rdi
0x180015650  add     rsp, 20h
0x180015654  pop     r14
0x180015656  pop     rdi
0x180015657  pop     rsi
0x180015658  retn
```
