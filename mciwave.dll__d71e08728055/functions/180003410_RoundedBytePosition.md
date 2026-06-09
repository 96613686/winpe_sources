# RoundedBytePosition

- ea: `0x180003410`
- end: `0x18000349f`
- name: `RoundedBytePosition`
- size: `143`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003568`
- `0x180003d64`
- `0x18000492c`
- `0x1800050b0`
- `0x180005170`

## callees

- `0x180003410`

## import_xrefs

- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000343b`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180003465`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000343b`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180003465`

## pseudocode

```c
__int64 __fastcall RoundedBytePosition(__int64 a1, int a2, int a3)
{
  unsigned int v3; // r9d
  __int64 v5; // rdx
  int v6; // ebx
  __int64 result; // rax

  v3 = a2;
  if ( a3 == 9 )
  {
    v5 = *(_QWORD *)(a1 + 168);
    v6 = *(unsigned __int16 *)(v5 + 12);
    v3 = v6 * (MulDiv(v3, *(_DWORD *)(v5 + 8), *(_DWORD *)(v5 + 4)) / v6);
  }
  else if ( !a3 )
  {
    v3 = MulDiv(a2, *(_DWORD *)(*(_QWORD *)(a1 + 168) + 8LL), 1000);
  }
  result = *(unsigned int *)(a1 + 76);
  if ( v3 < (unsigned int)result || *(_DWORD *)(a1 + 28) != 1 )
    return v3 - v3 % *(unsigned __int16 *)(*(_QWORD *)(a1 + 168) + 12LL);
  return result;
}

```

## disassembly

```asm
0x180003410  mov     [rsp+arg_0], rbx
0x180003415  push    rdi
0x180003416  sub     rsp, 20h
0x18000341a  mov     r9d, edx
0x18000341d  mov     rdi, rcx
0x180003420  cmp     r8d, 9
0x180003424  jnz     short loc_18000344D
0x180003426  mov     rdx, [rcx+0A8h]
0x18000342d  mov     ecx, r9d; nNumber
0x180003430  movzx   ebx, word ptr [rdx+0Ch]
0x180003434  mov     r8d, [rdx+4]; nDenominator
0x180003438  mov     edx, [rdx+8]; nNumerator
0x18000343b  call    cs:__imp_MulDiv
0x180003441  cdq
0x180003442  idiv    ebx
0x180003444  mov     r9d, eax
0x180003447  imul    r9d, ebx
0x18000344b  jmp     short loc_18000346E
0x18000344d  test    r8d, r8d
0x180003450  jnz     short loc_18000346E
0x180003452  mov     rdx, [rcx+0A8h]
0x180003459  mov     r8d, 3E8h; nDenominator
0x18000345f  mov     ecx, r9d; nNumber
0x180003462  mov     edx, [rdx+8]; nNumerator
0x180003465  call    cs:__imp_MulDiv
0x18000346b  mov     r9d, eax
0x18000346e  mov     eax, [rdi+4Ch]
0x180003471  cmp     r9d, eax
0x180003474  jb      short loc_18000347C
0x180003476  cmp     dword ptr [rdi+1Ch], 1
0x18000347a  jz      short loc_180003494
0x18000347c  mov     rax, [rdi+0A8h]
0x180003483  xor     edx, edx
0x180003485  movzx   ecx, word ptr [rax+0Ch]
0x180003489  mov     eax, r9d
0x18000348c  div     ecx
0x18000348e  sub     r9d, edx
0x180003491  mov     eax, r9d
0x180003494  mov     rbx, [rsp+28h+arg_0]
0x180003499  add     rsp, 20h
0x18000349d  pop     rdi
0x18000349e  retn
```
