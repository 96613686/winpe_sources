# CColour::SetMediaType(_PinDirection,CMediaType const *)

- ea: `0x1800978c0`
- end: `0x180097988`
- name: `?SetMediaType@CColour@@UEAAJW4_PinDirection@@PEBVCMediaType@@@Z`
- size: `200`
- prototype: `int(CColour *__hidden this, enum _PinDirection, const struct CMediaType *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18002e488`
- `0x1800978c0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18009796e`
- `KERNEL32!LeaveCriticalSection` at `0x18009796e`
- `KERNEL32!EnterCriticalSection` at `0x1800978dd`
- `KERNEL32!EnterCriticalSection` at `0x1800978dd`
- `USER32!IsRectEmpty` at `0x180097914`
- `USER32!IsRectEmpty` at `0x180097941`
- `USER32!IsRectEmpty` at `0x180097914`
- `USER32!IsRectEmpty` at `0x180097941`

## pseudocode

```c
__int64 __fastcall CColour::SetMediaType(CColour *this, enum _PinDirection a2, const struct _AMMediaType *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  __int64 v7; // rbp
  const RECT *v8; // rbx
  int v9; // eax
  bool v10; // sf
  int right; // eax

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 176);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  if ( a2 )
  {
    v7 = *(_QWORD *)(*((_QWORD *)this + 27) + 184LL);
    CMediaType::Set((struct _AMMediaType *)((char *)this + 816), a3);
    v8 = (const RECT *)*((_QWORD *)this + 112);
    if ( IsRectEmpty(v8) )
    {
      *(_QWORD *)&v8->left = 0;
      v8->right = *(_DWORD *)(v7 + 52);
      v9 = -*(_DWORD *)(v7 + 56);
      if ( *(int *)(v7 + 56) > 0 )
        v9 = *(_DWORD *)(v7 + 56);
      v8->bottom = v9;
    }
    if ( IsRectEmpty(v8 + 1) )
    {
      v8[1].right = v8[3].top;
      v10 = -v8[3].right < 0;
      right = -v8[3].right;
      *(_QWORD *)&v8[1].left = 0;
      if ( v10 )
        right = v8[3].right;
      v8[1].bottom = right;
    }
  }
  LeaveCriticalSection(v3);
  return 0;
}

```

## disassembly

```asm
0x1800978c0  push    rbx
0x1800978c2  push    rbp
0x1800978c3  push    rsi
0x1800978c4  push    rdi
0x1800978c5  push    r14
0x1800978c7  sub     rsp, 20h
0x1800978cb  lea     rsi, [rcx+0B0h]
0x1800978d2  mov     rdi, rcx
0x1800978d5  mov     rcx, rsi; lpCriticalSection
0x1800978d8  mov     r14, r8
0x1800978db  mov     ebx, edx
0x1800978dd  call    cs:__imp_EnterCriticalSection
0x1800978e4  nop     dword ptr [rax+rax+00h]
0x1800978e9  test    ebx, ebx
0x1800978eb  jz      short loc_18009796B
0x1800978ed  mov     rax, [rdi+0D8h]
0x1800978f4  lea     rcx, [rdi+330h]; this
0x1800978fb  mov     rdx, r14; struct _AMMediaType *
0x1800978fe  mov     rbp, [rax+0B8h]
0x180097905  call    ?Set@CMediaType@@QEAAJAEBU_AMMediaType@@@Z; CMediaType::Set(_AMMediaType const &)
0x18009790a  mov     rbx, [rdi+380h]
0x180097911  mov     rcx, rbx; lprc
0x180097914  call    cs:__imp_IsRectEmpty
0x18009791b  nop     dword ptr [rax+rax+00h]
0x180097920  test    eax, eax
0x180097922  jz      short loc_18009793D
0x180097924  mov     qword ptr [rbx], 0
0x18009792b  mov     eax, [rbp+34h]
0x18009792e  mov     [rbx+8], eax
0x180097931  mov     eax, [rbp+38h]
0x180097934  neg     eax
0x180097936  cmovs   eax, [rbp+38h]
0x18009793a  mov     [rbx+0Ch], eax
0x18009793d  lea     rcx, [rbx+10h]; lprc
0x180097941  call    cs:__imp_IsRectEmpty
0x180097948  nop     dword ptr [rax+rax+00h]
0x18009794d  test    eax, eax
0x18009794f  jz      short loc_18009796B
0x180097951  mov     eax, [rbx+34h]
0x180097954  mov     [rbx+18h], eax
0x180097957  mov     eax, [rbx+38h]
0x18009795a  neg     eax
0x18009795c  mov     qword ptr [rbx+10h], 0
0x180097964  cmovs   eax, [rbx+38h]
0x180097968  mov     [rbx+1Ch], eax
0x18009796b  mov     rcx, rsi; lpCriticalSection
0x18009796e  call    cs:__imp_LeaveCriticalSection
0x180097975  nop     dword ptr [rax+rax+00h]
0x18009797a  xor     eax, eax
0x18009797c  add     rsp, 20h
0x180097980  pop     r14
0x180097982  pop     rdi
0x180097983  pop     rsi
0x180097984  pop     rbp
0x180097985  pop     rbx
0x180097986  retn
```
