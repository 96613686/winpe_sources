# DeleteFont(HFONT__ *)

- ea: `0x1800763c0`
- end: `0x1800764e3`
- name: `?DeleteFont@@YAHPEAUHFONT__@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(HFONT)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180041cb8`
- `0x1800756cc`
- `0x1800763c0`

## import_xrefs

- `GDI32!GdiGetEntry` at `0x18007641a`
- `GDI32!GdiGetEntry` at `0x180076498`
- `GDI32!GdiGetEntry` at `0x18007641a`
- `GDI32!GdiGetEntry` at `0x180076498`
- `GDI32!gW32PID` at `0x180076449`
- `GDI32!gCookie` at `0x180076463`
- `GDI32!gMaxGdiHandleCount` at `0x1800763f8`
- `ntdll!RtlEnterCriticalSection` at `0x1800763e4`
- `ntdll!RtlEnterCriticalSection` at `0x1800763e4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800764c9`
- `ntdll!RtlLeaveCriticalSection` at `0x1800764c9`
- `win32u!NtGdiDeleteObjectApp` at `0x1800764b4`
- `win32u!NtGdiDeleteObjectApp` at `0x1800764b4`

## pseudocode

```c
__int64 __fastcall DeleteFont(unsigned __int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // rdx
  unsigned int v4; // eax
  unsigned __int64 v5; // rcx
  unsigned int v6; // ebx
  __int128 v8; // [rsp+20h] [rbp-30h] BYREF
  __int64 v9; // [rsp+30h] [rbp-20h]
  __int128 v10; // [rsp+38h] [rbp-18h] BYREF
  __int64 v11; // [rsp+48h] [rbp-8h]

  v10 = 0;
  v11 = 0;
  RtlEnterCriticalSection(&semLocal);
  v2 = HANDLE_TO_INDEX(a1);
  if ( v2 < gMaxGdiHandleCount )
  {
    v9 = 0;
    v8 = 0;
    if ( (int)GdiGetEntry(v2, &v8) >= 0
      && BYTE14(v8) == 10
      && WORD6(v8) == WORD1(a1)
      && (DWORD2(v8) & 0xFFFFFFFE) == gW32PID )
    {
      if ( v9 )
      {
        v3 = __ROR8__(v9, 64 - (gCookie & 0x3Fu));
        if ( v3 != gCookie )
          vDeleteLOCALFONT((struct _LOCALFONT *)(v3 ^ gCookie));
      }
    }
  }
  v4 = HANDLE_TO_INDEX(a1);
  GdiGetEntry(v4, &v10);
  v5 = a1 | 0x800000;
  if ( (SBYTE12(v10) & 0x80u) == 0 )
    v5 = a1;
  v6 = NtGdiDeleteObjectApp(v5);
  RtlLeaveCriticalSection(&semLocal);
  return v6;
}

```

## disassembly

```asm
0x1800763c0  mov     [rsp-8+arg_0], rbx
0x1800763c5  push    rbp
0x1800763c6  mov     rbp, rsp
0x1800763c9  sub     rsp, 50h
0x1800763cd  mov     rbx, rcx
0x1800763d0  xorps   xmm0, xmm0
0x1800763d3  xor     eax, eax
0x1800763d5  lea     rcx, semLocal; CriticalSection
0x1800763dc  movups  [rbp+var_18], xmm0
0x1800763e0  mov     [rbp+var_8], rax
0x1800763e4  call    cs:__imp_RtlEnterCriticalSection
0x1800763eb  nop     dword ptr [rax+rax+00h]
0x1800763f0  mov     rcx, rbx
0x1800763f3  call    HANDLE_TO_INDEX
0x1800763f8  mov     rcx, cs:__imp_gMaxGdiHandleCount
0x1800763ff  cmp     eax, [rcx]
0x180076401  jnb     loc_18007648A
0x180076407  xor     ecx, ecx
0x180076409  lea     rdx, [rbp+var_30]
0x18007640d  mov     [rbp+var_20], rcx
0x180076411  xorps   xmm0, xmm0
0x180076414  mov     ecx, eax
0x180076416  movups  [rbp+var_30], xmm0
0x18007641a  call    cs:__imp_GdiGetEntry
0x180076421  nop     dword ptr [rax+rax+00h]
0x180076426  test    eax, eax
0x180076428  js      short loc_18007648A
0x18007642a  cmp     byte ptr [rbp+var_30+0Eh], 0Ah
0x18007642e  jnz     short loc_18007648A
0x180076430  movzx   eax, byte ptr [rbp+var_30+0Ch]
0x180076434  movzx   ecx, byte ptr [rbp+var_30+0Dh]
0x180076438  shl     cx, 8
0x18007643c  or      cx, ax
0x18007643f  mov     eax, ebx
0x180076441  shr     eax, 10h
0x180076444  cmp     cx, ax
0x180076447  jnz     short loc_18007648A
0x180076449  mov     rax, cs:__imp_gW32PID
0x180076450  mov     ecx, dword ptr [rbp+var_30+8]
0x180076453  and     ecx, 0FFFFFFFEh
0x180076456  cmp     ecx, [rax]
0x180076458  jnz     short loc_18007648A
0x18007645a  mov     rdx, [rbp+var_20]
0x18007645e  test    rdx, rdx
0x180076461  jz      short loc_18007648A
0x180076463  mov     rax, cs:__imp_gCookie
0x18007646a  mov     ecx, 40h ; '@'
0x18007646f  mov     r8, [rax]
0x180076472  mov     eax, r8d
0x180076475  and     eax, 3Fh
0x180076478  sub     ecx, eax
0x18007647a  ror     rdx, cl
0x18007647d  xor     r8, rdx
0x180076480  jz      short loc_18007648A
0x180076482  mov     rcx, r8; struct _LOCALFONT *
0x180076485  call    ?vDeleteLOCALFONT@@YAXPEAU_LOCALFONT@@@Z; vDeleteLOCALFONT(_LOCALFONT *)
0x18007648a  mov     rcx, rbx
0x18007648d  call    HANDLE_TO_INDEX
0x180076492  mov     ecx, eax
0x180076494  lea     rdx, [rbp+var_18]
0x180076498  call    cs:__imp_GdiGetEntry
0x18007649f  nop     dword ptr [rax+rax+00h]
0x1800764a4  mov     rcx, rbx
0x1800764a7  bts     rcx, 17h
0x1800764ac  test    byte ptr [rbp+var_18+0Ch], 80h
0x1800764b0  cmovz   rcx, rbx
0x1800764b4  call    cs:__imp_NtGdiDeleteObjectApp
0x1800764bb  nop     dword ptr [rax+rax+00h]
0x1800764c0  lea     rcx, semLocal; CriticalSection
0x1800764c7  mov     ebx, eax
0x1800764c9  call    cs:__imp_RtlLeaveCriticalSection
0x1800764d0  nop     dword ptr [rax+rax+00h]
0x1800764d5  mov     eax, ebx
0x1800764d7  mov     rbx, [rsp+50h+arg_0]
0x1800764dc  add     rsp, 50h
0x1800764e0  pop     rbp
0x1800764e1  retn
```
