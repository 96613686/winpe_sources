# CSysString::Compare(ushort const *,int)

- ea: `0x18004d990`
- end: `0x18004da44`
- name: `?Compare@CSysString@@QEBAHPEBGH@Z`
- size: `180`
- prototype: `int(CSysString *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18009a094`

## callees

- `0x18004d990`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18004d9ec`
- `KERNEL32!CompareStringW` at `0x18004d9ec`
- `OLEAUT32!__imp_SysStringLen` at `0x18004d9a7`
- `OLEAUT32!__imp_SysStringLen` at `0x18004d9a7`

## pseudocode

```c
__int64 __fastcall CSysString::Compare(BSTR *this, const unsigned __int16 *a2, int a3)
{
  UINT v6; // eax
  unsigned __int64 v7; // rbp
  unsigned __int64 v8; // rbx
  int cchCount2; // r9d
  int v10; // eax

  v6 = SysStringLen(*this);
  v7 = v6;
  if ( a2 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
  }
  else
  {
    v8 = 0;
  }
  cchCount2 = v6;
  if ( v6 >= v8 )
    cchCount2 = v8;
  v10 = CompareStringW(0x400u, 0x30000u, *this, cchCount2, a2, cchCount2);
  switch ( v10 )
  {
    case 1:
      return 0xFFFFFFFFLL;
    case 2:
      if ( a3 )
        return 0;
      if ( v7 >= v8 )
        return v7 > v8;
      return 0xFFFFFFFFLL;
    case 3:
      return 1;
    default:
      return 2;
  }
}

```

## disassembly

```asm
0x18004d990  push    rbx
0x18004d992  push    rbp
0x18004d993  push    rsi
0x18004d994  push    rdi
0x18004d995  push    r14
0x18004d997  sub     rsp, 30h
0x18004d99b  mov     rsi, rcx
0x18004d99e  mov     r14d, r8d
0x18004d9a1  mov     rcx, [rcx]; pbstr
0x18004d9a4  mov     rdi, rdx
0x18004d9a7  call    cs:__imp_SysStringLen
0x18004d9ae  nop     dword ptr [rax+rax+00h]
0x18004d9b3  mov     ebp, eax
0x18004d9b5  test    rdi, rdi
0x18004d9b8  jz      short loc_18004DA1A
0x18004d9ba  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18004d9c1  inc     rbx
0x18004d9c4  cmp     word ptr [rdi+rbx*2], 0
0x18004d9c9  jnz     short loc_18004D9C1
0x18004d9cb  mov     r8, [rsi]; lpString1
0x18004d9ce  mov     r9d, ebp
0x18004d9d1  cmp     rbp, rbx
0x18004d9d4  mov     edx, 30000h; dwCmpFlags
0x18004d9d9  mov     ecx, 400h; Locale
0x18004d9de  cmovnb  r9d, ebx; cchCount1
0x18004d9e2  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x18004d9e7  mov     [rsp+58h+lpString2], rdi; lpString2
0x18004d9ec  call    cs:__imp_CompareStringW
0x18004d9f3  nop     dword ptr [rax+rax+00h]
0x18004d9f8  mov     ecx, eax
0x18004d9fa  sub     ecx, 1
0x18004d9fd  jz      short loc_18004DA3D
0x18004d9ff  sub     ecx, 1
0x18004da02  jz      short loc_18004DA25
0x18004da04  cmp     ecx, 1
0x18004da07  jz      short loc_18004DA1E
0x18004da09  mov     eax, 2
0x18004da0e  add     rsp, 30h
0x18004da12  pop     r14
0x18004da14  pop     rdi
0x18004da15  pop     rsi
0x18004da16  pop     rbp
0x18004da17  pop     rbx
0x18004da18  retn
0x18004da1a  xor     ebx, ebx
0x18004da1c  jmp     short loc_18004D9CB
0x18004da1e  mov     eax, 1
0x18004da23  jmp     short loc_18004DA0E
0x18004da25  test    r14d, r14d
0x18004da28  jz      short loc_18004DA2E
0x18004da2a  xor     eax, eax
0x18004da2c  jmp     short loc_18004DA0E
0x18004da2e  cmp     rbp, rbx
0x18004da31  jb      short loc_18004DA3D
0x18004da33  xor     eax, eax
0x18004da35  cmp     rbp, rbx
0x18004da38  setnbe  al
0x18004da3b  jmp     short loc_18004DA0E
0x18004da3d  mov     eax, 0FFFFFFFFh
0x18004da42  jmp     short loc_18004DA0E
```
