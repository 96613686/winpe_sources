# DiscpFilterConditionDestroy

- ea: `0x180016060`
- end: `0x1800160d8`
- name: `DiscpFilterConditionDestroy`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD *, _DWORD *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180015918`
- `0x180015c9c`
- `0x1800161c8`
- `0x1800165c4`
- `0x180016780`

## callees

- `0x180016060`

## import_xrefs

- `ISCSIUM!DiscpFreeMemory` at `0x1800160ad`
- `ISCSIUM!DiscpFreeMemory` at `0x1800160c2`
- `ISCSIUM!DiscpFreeMemory` at `0x1800160ad`
- `ISCSIUM!DiscpFreeMemory` at `0x1800160c2`

## pseudocode

```c
__int64 __fastcall DiscpFilterConditionDestroy(_QWORD *a1, _DWORD *a2)
{
  __int64 i; // rbx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 result; // rax

  if ( *a1 )
  {
    for ( i = 0; (unsigned int)i < *a2; i = (unsigned int)(i + 1) )
    {
      v5 = *a1;
      if ( *(_DWORD *)(*a1 + 40 * i + 24) == 256 || *(_DWORD *)(*a1 + 40 * i + 24) == 257 )
      {
        v6 = *(_QWORD *)(v5 + 40 * i + 32);
        if ( v6 )
        {
          *(_DWORD *)(v5 + 40 * i + 24) = 0;
          DiscpFreeMemory(v6);
        }
      }
    }
    *a2 = 0;
    return DiscpFreeMemory(*a1);
  }
  return result;
}

```

## disassembly

```asm
0x180016060  mov     [rsp+arg_0], rbx
0x180016065  mov     [rsp+arg_8], rsi
0x18001606a  push    rdi
0x18001606b  sub     rsp, 20h
0x18001606f  cmp     qword ptr [rcx], 0
0x180016073  mov     rdi, rdx
0x180016076  mov     rsi, rcx
0x180016079  jz      short loc_1800160C8
0x18001607b  xor     ebx, ebx
0x18001607d  cmp     [rdx], ebx
0x18001607f  jbe     short loc_1800160B9
0x180016081  mov     rdx, [rsi]
0x180016084  lea     r8, [rbx+rbx*4]
0x180016088  mov     ecx, [rdx+r8*8+18h]
0x18001608d  sub     ecx, 100h
0x180016093  jz      short loc_18001609A
0x180016095  cmp     ecx, 1
0x180016098  jnz     short loc_1800160B3
0x18001609a  mov     rcx, [rdx+r8*8+20h]
0x18001609f  test    rcx, rcx
0x1800160a2  jz      short loc_1800160B3
0x1800160a4  mov     dword ptr [rdx+r8*8+18h], 0
0x1800160ad  call    cs:__imp_DiscpFreeMemory
0x1800160b3  inc     ebx
0x1800160b5  cmp     ebx, [rdi]
0x1800160b7  jb      short loc_180016081
0x1800160b9  mov     dword ptr [rdi], 0
0x1800160bf  mov     rcx, [rsi]
0x1800160c2  call    cs:__imp_DiscpFreeMemory
0x1800160c8  mov     rbx, [rsp+28h+arg_0]
0x1800160cd  mov     rsi, [rsp+28h+arg_8]
0x1800160d2  add     rsp, 20h
0x1800160d6  pop     rdi
0x1800160d7  retn
```
