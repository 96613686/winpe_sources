# CopyAndAllocateString(ushort const *,ushort * *)

- ea: `0x100255a0`
- end: `0x10025623`
- name: `?CopyAndAllocateString@@YGJPBGPAPAG@Z`
- size: `131`
- prototype: `int __stdcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x100108b0`
- `0x100109e0`
- `0x10011740`
- `0x100118b0`
- `0x10011d40`

## callees

- `0x1000d4a0`
- `0x1001c6d0`
- `0x100255a0`

## pseudocode

```c
int __fastcall CopyAndAllocateString(unsigned __int16 *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v5; // eax
  unsigned __int16 *v7; // eax
  const unsigned __int16 *v8; // [esp+0h] [ebp-Ch]
  unsigned int v9; // [esp+4h] [ebp-8h]
  unsigned __int16 *v10; // [esp+8h] [ebp-4h]

  if ( a1 )
  {
    v5 = a1;
    while ( *v5++ )
      ;
    v10 = (unsigned __int16 *)(2 * (v5 - (a1 + 1)) + 2);
    v7 = (unsigned __int16 *)(*(int (__thiscall **)(_DWORD, int, unsigned __int16 *))(*(_DWORD *)Sys + 12))(
                               *(_DWORD *)(*(_DWORD *)Sys + 12),
                               Sys,
                               v10);
    *a2 = v7;
    if ( v7 )
      return WCSCPY(a1, v7, v10, v8, v9) != 0 ? 0 : -2147467259;
    else
      return -2147024882;
  }
  else
  {
    *a2 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x100255a0  mov     edi, edi
0x100255a2  push    ebp
0x100255a3  mov     ebp, esp
0x100255a5  push    ecx
0x100255a6  push    ebx; unsigned int
0x100255a7  push    edi; unsigned __int16 *
0x100255a8  mov     edi, ecx
0x100255aa  mov     ebx, edx
0x100255ac  test    edi, edi
0x100255ae  jnz     short loc_100255BA
0x100255b0  pop     edi
0x100255b1  mov     [ebx], ecx
0x100255b3  xor     eax, eax
0x100255b5  pop     ebx
0x100255b6  mov     esp, ebp
0x100255b8  pop     ebp
0x100255b9  retn
0x100255ba  mov     eax, edi
0x100255bc  lea     edx, [eax+2]
0x100255bf  nop
0x100255c0  mov     cx, [eax]
0x100255c3  add     eax, 2
0x100255c6  test    cx, cx
0x100255c9  jnz     short loc_100255C0
0x100255cb  mov     ecx, ?Sys@@3VSystem@@A; System Sys
0x100255d1  sub     eax, edx
0x100255d3  sar     eax, 1
0x100255d5  push    esi
0x100255d6  lea     edx, ds:2[eax*2]
0x100255dd  mov     eax, [ecx]
0x100255df  push    edx
0x100255e0  push    ecx
0x100255e1  mov     [ebp+var_4], edx
0x100255e4  mov     esi, [eax+0Ch]
0x100255e7  mov     ecx, esi
0x100255e9  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100255ef  call    esi
0x100255f1  mov     [ebx], eax
0x100255f3  pop     esi
0x100255f4  test    eax, eax
0x100255f6  jnz     short loc_10025603
0x100255f8  pop     edi
0x100255f9  mov     eax, 8007000Eh
0x100255fe  pop     ebx
0x100255ff  mov     esp, ebp
0x10025601  pop     ebp
0x10025602  retn
0x10025603  push    [ebp+var_4]; unsigned __int16 *
0x10025606  mov     edx, edi
0x10025608  mov     ecx, eax
0x1002560a  call    ?WCSCPY@@YGPAGPAGPBGI@Z; WCSCPY(ushort *,ushort const *,uint)
0x1002560f  neg     eax
0x10025611  sbb     eax, eax
0x10025613  and     eax, 7FFFBFFBh
0x10025618  add     eax, 80004005h
0x1002561d  pop     edi
0x1002561e  pop     ebx
0x1002561f  mov     esp, ebp
0x10025621  pop     ebp
0x10025622  retn
```
