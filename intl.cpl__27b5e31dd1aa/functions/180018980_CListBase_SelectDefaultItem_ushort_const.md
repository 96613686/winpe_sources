# CListBase::_SelectDefaultItem(ushort const *)

- ea: `0x180018980`
- end: `0x1800189f8`
- name: `?_SelectDefaultItem@CListBase@@IEAAHPEBG@Z`
- size: `120`
- prototype: `int(CListBase *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800129bc`
- `0x18002200c`

## callees

- `0x180018980`
- `0x180029b74`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800189d1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800189d1`

## pseudocode

```c
__int64 __fastcall CListBase::_SelectDefaultItem(CListBase *this, const unsigned __int16 *a2)
{
  int *v2; // rax
  unsigned int v3; // esi
  int v6; // ebp
  int i; // ebx
  const WCHAR *ItemPtr; // rax

  v2 = (int *)*((_QWORD *)this + 1);
  v3 = 0;
  if ( v2 )
    v6 = *v2;
  else
    v6 = 0;
  for ( i = 0; i < v6; ++i )
  {
    ItemPtr = (const WCHAR *)DSA_GetItemPtr(*((HDSA *)this + 1), i);
    if ( ItemPtr && CompareStringW(0x7Fu, 0, ItemPtr, -1, a2, -1) == 2 )
    {
      *((_DWORD *)this + 5) = i;
      v3 = 1;
      *((_DWORD *)this + 4) = i;
      return v3;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180018980  push    rbx
0x180018982  push    rbp
0x180018983  push    rsi
0x180018984  push    rdi
0x180018985  push    r14
0x180018987  sub     rsp, 30h
0x18001898b  mov     rax, [rcx+8]
0x18001898f  xor     esi, esi
0x180018991  mov     r14, rdx
0x180018994  mov     rdi, rcx
0x180018997  test    rax, rax
0x18001899a  jz      short loc_1800189A0
0x18001899c  mov     ebp, [rax]
0x18001899e  jmp     short loc_1800189A2
0x1800189a0  xor     ebp, ebp
0x1800189a2  xor     ebx, ebx
0x1800189a4  cmp     ebx, ebp
0x1800189a6  jge     short loc_1800189EB
0x1800189a8  mov     rcx, [rdi+8]; hdsa
0x1800189ac  mov     edx, ebx; i
0x1800189ae  call    DSA_GetItemPtr
0x1800189b3  test    rax, rax
0x1800189b6  jz      short loc_1800189DC
0x1800189b8  xor     edx, edx; dwCmpFlags
0x1800189ba  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800189c2  or      r9d, 0FFFFFFFFh; cchCount1
0x1800189c6  mov     [rsp+58h+lpString2], r14; lpString2
0x1800189cb  mov     r8, rax; lpString1
0x1800189ce  lea     ecx, [rdx+7Fh]; Locale
0x1800189d1  call    cs:__imp_CompareStringW
0x1800189d7  cmp     eax, 2
0x1800189da  jz      short loc_1800189E0
0x1800189dc  inc     ebx
0x1800189de  jmp     short loc_1800189A4
0x1800189e0  mov     [rdi+14h], ebx
0x1800189e3  mov     esi, 1
0x1800189e8  mov     [rdi+10h], ebx
0x1800189eb  mov     eax, esi
0x1800189ed  add     rsp, 30h
0x1800189f1  pop     r14
0x1800189f3  pop     rdi
0x1800189f4  pop     rsi
0x1800189f5  pop     rbp
0x1800189f6  pop     rbx
0x1800189f7  retn
```
