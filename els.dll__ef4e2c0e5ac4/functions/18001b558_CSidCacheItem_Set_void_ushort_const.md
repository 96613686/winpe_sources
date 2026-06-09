# CSidCacheItem::_Set(void *,ushort const *)

- ea: `0x18001b558`
- end: `0x18001b651`
- name: `?_Set@CSidCacheItem@@AEAAJPEAXPEBG@Z`
- size: `249`
- prototype: `int(CSidCacheItem *__hidden this, void *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18001b3f8`
- `0x18001b4d0`

## callees

- `0x180002bb8`
- `0x1800036a6`
- `0x18001b558`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b5f3`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001b5f3`
- `msvcrt!wcscpy_s` at `0x18001b627`
- `msvcrt!wcscpy_s` at `0x18001b627`
- `ADVAPI32!GetLengthSid` at `0x18001b575`
- `ADVAPI32!GetLengthSid` at `0x18001b575`
- `KERNEL32!GetTickCount` at `0x18001b62d`
- `KERNEL32!GetTickCount` at `0x18001b62d`

## pseudocode

```c
__int64 __fastcall CSidCacheItem::_Set(CSidCacheItem *this, void *a2, const unsigned __int16 *a3)
{
  size_t LengthSid; // r15
  const unsigned __int16 *v7; // r11
  __int64 v8; // r9
  unsigned int v9; // edi
  int v10; // ebx
  unsigned int v11; // ebp
  char *v12; // r14
  unsigned int v13; // ebx

  LengthSid = GetLengthSid(a2);
  if ( a3 )
  {
    v7 = a3;
    v8 = 0x7FFFFFFF;
    do
    {
      if ( !*v7 )
        break;
      ++v7;
      --v8;
    }
    while ( v8 );
    v9 = v8 == 0 ? 0x80070057 : 0;
    if ( v8 )
    {
      v10 = (LengthSid + 3) & 0xFFFFFFFC;
      v11 = v10 + 2 * (v8 != 0 ? 0x7FFFFFFF - v8 + 1 : 1);
      v12 = (char *)operator new[](v11);
      if ( v12 )
      {
        v13 = v10 - LengthSid;
        operator delete[](*((void **)this + 4));
        *((_QWORD *)this + 4) = v12;
        *((_QWORD *)this + 5) = &v12[LengthSid + v13];
        memcpy_0(v12, a2, LengthSid);
        wcscpy_s(*((wchar_t **)this + 5), (unsigned __int64)(v11 - v13 - (unsigned int)LengthSid) >> 1, a3);
        *((_DWORD *)this + 6) = GetTickCount();
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v9;
}

```

## disassembly

```asm
0x18001b558  push    rbx
0x18001b55a  push    rbp
0x18001b55b  push    rsi
0x18001b55c  push    rdi
0x18001b55d  push    r12
0x18001b55f  push    r13
0x18001b561  push    r14
0x18001b563  push    r15
0x18001b565  sub     rsp, 28h
0x18001b569  mov     r13, rcx
0x18001b56c  mov     rsi, r8
0x18001b56f  mov     rcx, rdx; pSid
0x18001b572  mov     r12, rdx
0x18001b575  call    cs:__imp_GetLengthSid
0x18001b57b  xor     edx, edx
0x18001b57d  mov     r15d, eax
0x18001b580  test    rsi, rsi
0x18001b583  jz      loc_18001B639
0x18001b589  mov     r10d, 7FFFFFFFh
0x18001b58f  mov     r11, rsi
0x18001b592  mov     r9d, r10d
0x18001b595  cmp     [r11], dx
0x18001b599  jz      short loc_18001B5A5
0x18001b59b  add     r11, 2
0x18001b59f  sub     r9, 1
0x18001b5a3  jnz     short loc_18001B595
0x18001b5a5  mov     rax, r9
0x18001b5a8  neg     rax
0x18001b5ab  mov     rax, r9
0x18001b5ae  sbb     edi, edi
0x18001b5b0  sub     r10, r9
0x18001b5b3  not     edi
0x18001b5b5  and     edi, 80070057h
0x18001b5bb  neg     rax
0x18001b5be  sbb     rcx, rcx
0x18001b5c1  and     rcx, r10
0x18001b5c4  test    r9, r9
0x18001b5c7  jz      short loc_18001B63E
0x18001b5c9  lea     ecx, [rcx+1]
0x18001b5cc  lea     ebx, [r15+3]
0x18001b5d0  and     ebx, 0FFFFFFFCh
0x18001b5d3  lea     ebp, [rbx+rcx*2]
0x18001b5d6  mov     ecx, ebp; unsigned __int64
0x18001b5d8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001b5dd  mov     r14, rax
0x18001b5e0  test    rax, rax
0x18001b5e3  jnz     short loc_18001B5EC
0x18001b5e5  mov     edi, 8007000Eh
0x18001b5ea  jmp     short loc_18001B63E
0x18001b5ec  mov     rcx, [r13+20h]
0x18001b5f0  sub     ebx, r15d
0x18001b5f3  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001b5f9  lea     rax, [r15+rbx]
0x18001b5fd  mov     [r13+20h], r14
0x18001b601  add     rax, r14
0x18001b604  mov     r8, r15; Size
0x18001b607  mov     rdx, r12; Src
0x18001b60a  mov     [r13+28h], rax
0x18001b60e  mov     rcx, r14; void *
0x18001b611  call    memcpy_0
0x18001b616  mov     rcx, [r13+28h]; Destination
0x18001b61a  sub     ebp, ebx
0x18001b61c  sub     ebp, r15d
0x18001b61f  mov     r8, rsi; Source
0x18001b622  mov     edx, ebp
0x18001b624  shr     rdx, 1; SizeInWords
0x18001b627  call    cs:__imp_wcscpy_s
0x18001b62d  call    cs:__imp_GetTickCount
0x18001b633  mov     [r13+18h], eax
0x18001b637  jmp     short loc_18001B63E
0x18001b639  mov     edi, 80070057h
0x18001b63e  mov     eax, edi
0x18001b640  add     rsp, 28h
0x18001b644  pop     r15
0x18001b646  pop     r14
0x18001b648  pop     r13
0x18001b64a  pop     r12
0x18001b64c  pop     rdi
0x18001b64d  pop     rsi
0x18001b64e  pop     rbp
0x18001b64f  pop     rbx
0x18001b650  retn
```
