# ORDeleteValue

- ea: `0x140025640`
- end: `0x14002575c`
- name: `ORDeleteValue`
- size: `284`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140021c34`

## callees

- `0x140025640`
- `0x14002593c`
- `0x1400259f0`
- `0x140026fa8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140025689`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140025689`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400256a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400256a4`

## pseudocode

```c
__int64 __fastcall ORDeleteValue(__int64 a1, __int64 a2)
{
  __int64 v4; // rsi
  unsigned int v5; // edi
  _QWORD *v6; // rdi
  __int64 v7; // rax
  _QWORD *v8; // rcx
  __int64 v9; // rcx
  _QWORD *v12; // [rsp+40h] [rbp+8h] BYREF

  v12 = 0;
  if ( *(_WORD *)(a1 + 28) == 29806 && (v4 = *(_QWORD *)(a1 + 16), *(_DWORD *)v4 == -1092567328) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 136));
    if ( *(_WORD *)(a1 + 30) )
    {
      v5 = 1018;
    }
    else
    {
      v5 = ORFindValue(a2, a1, &v12);
      if ( !v5 )
      {
        v6 = v12;
        v7 = *v12;
        if ( *(_QWORD **)(*v12 + 8LL) != v12 || (v8 = (_QWORD *)v12[1], (_QWORD *)*v8 != v12) )
          __fastfail(3u);
        *v8 = v7;
        *(_QWORD *)(v7 + 8) = v8;
        v12 = v6;
        ORFreeDataAttachedToValue(v4, v6);
        ORFreeOrNop(v4, v6 + 3);
        ORFreeOrNop(v4, &v12);
        v9 = *(_QWORD *)(a1 + 40);
        if ( (*(_DWORD *)(v9 + 36))-- == 1 )
          *(_DWORD *)(v9 + 40) = -1;
        ++*(_QWORD *)(a1 + 168);
        v5 = 0;
        *(_DWORD *)(v4 + 180) = 1;
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 136));
  }
  else
  {
    return 6;
  }
  return v5;
}

```

## disassembly

```asm
0x140025640  mov     [rsp+arg_8], rbx
0x140025645  mov     [rsp+arg_10], rbp
0x14002564a  push    rsi
0x14002564b  push    rdi
0x14002564c  push    r14
0x14002564e  sub     rsp, 20h
0x140025652  xor     r14d, r14d
0x140025655  mov     eax, 746Eh
0x14002565a  mov     rdi, rdx
0x14002565d  mov     rbx, rcx
0x140025660  mov     [rsp+38h+arg_0], r14
0x140025665  cmp     [rcx+1Ch], ax
0x140025669  jnz     loc_140025741
0x14002566f  mov     rsi, [rcx+10h]
0x140025673  cmp     dword ptr [rsi], 0BEE0BEE0h
0x140025679  jnz     loc_140025741
0x14002567f  lea     rbp, [rsi+88h]
0x140025686  mov     rcx, rbp; lpCriticalSection
0x140025689  call    cs:__imp_EnterCriticalSection
0x140025690  nop     dword ptr [rax+rax+00h]
0x140025695  cmp     [rbx+1Eh], r14w
0x14002569a  jz      short loc_1400256B5
0x14002569c  mov     edi, 3FAh
0x1400256a1  mov     rcx, rbp; lpCriticalSection
0x1400256a4  call    cs:__imp_LeaveCriticalSection
0x1400256ab  nop     dword ptr [rax+rax+00h]
0x1400256b0  jmp     loc_140025746
0x1400256b5  lea     r8, [rsp+38h+arg_0]
0x1400256ba  mov     rdx, rbx
0x1400256bd  mov     rcx, rdi
0x1400256c0  call    ORFindValue
0x1400256c5  mov     edi, eax
0x1400256c7  test    eax, eax
0x1400256c9  jnz     short loc_1400256A1
0x1400256cb  mov     rdi, [rsp+38h+arg_0]
0x1400256d0  mov     rax, [rdi]
0x1400256d3  cmp     [rax+8], rdi
0x1400256d7  jnz     short loc_14002573A
0x1400256d9  mov     rcx, [rdi+8]
0x1400256dd  cmp     [rcx], rdi
0x1400256e0  jnz     short loc_14002573A
0x1400256e2  mov     [rcx], rax
0x1400256e5  mov     rdx, rdi
0x1400256e8  mov     [rax+8], rcx
0x1400256ec  mov     rcx, rsi
0x1400256ef  mov     [rsp+38h+arg_0], rdi
0x1400256f4  call    ORFreeDataAttachedToValue
0x1400256f9  lea     rdx, [rdi+18h]
0x1400256fd  mov     rcx, rsi
0x140025700  call    ORFreeOrNop
0x140025705  lea     rdx, [rsp+38h+arg_0]
0x14002570a  mov     rcx, rsi
0x14002570d  call    ORFreeOrNop
0x140025712  mov     rcx, [rbx+28h]
0x140025716  or      edx, 0FFFFFFFFh
0x140025719  add     [rcx+24h], edx
0x14002571c  jnz     short loc_140025721
0x14002571e  mov     [rcx+28h], edx
0x140025721  inc     qword ptr [rbx+0A8h]
0x140025728  mov     edi, r14d
0x14002572b  mov     dword ptr [rsi+0B4h], 1
0x140025735  jmp     loc_1400256A1
0x14002573a  mov     ecx, 3
0x14002573f  int     29h; Win8: RtlFailFast(ecx)
0x140025741  mov     edi, 6
0x140025746  mov     rbx, [rsp+38h+arg_8]
0x14002574b  mov     eax, edi
0x14002574d  mov     rbp, [rsp+38h+arg_10]
0x140025752  add     rsp, 20h
0x140025756  pop     r14
0x140025758  pop     rdi
0x140025759  pop     rsi
0x14002575a  retn
```
