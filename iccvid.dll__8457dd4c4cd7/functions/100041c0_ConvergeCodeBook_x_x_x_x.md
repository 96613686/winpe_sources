# ConvergeCodeBook(x,x,x,x)

- ea: `0x100041c0`
- end: `0x10004224`
- name: `_ConvergeCodeBook@16`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x10010735`
- `0x10010a12`

## callees

- `0x100041c0`
- `0x10011341`

## pseudocode

```c
unsigned int __fastcall ConvergeCodeBook(int a1, int *a2, char a3, unsigned __int8 a4)
{
  int v4; // edi
  unsigned int result; // eax
  unsigned int v7; // esi

  v4 = 16;
  result = MatchAndRefine((int *)a1, a2, 2, a3, a4);
  v7 = result;
  do
  {
    --v4;
    if ( !v7 )
      break;
    result = MatchAndRefine((int *)a1, a2, v4 > *(__int16 *)(a1 + 190), a3, a4);
    if ( !result )
      break;
    if ( a2[4] * (v7 - result) < result )
      break;
    v7 = result;
  }
  while ( v4 );
  return result;
}

```

## disassembly

```asm
0x100041c0  mov     edi, edi
0x100041c2  push    ebp
0x100041c3  mov     ebp, esp
0x100041c5  push    ecx
0x100041c6  push    ebx
0x100041c7  push    esi
0x100041c8  push    edi
0x100041c9  push    10h
0x100041cb  pop     edi
0x100041cc  push    [ebp+arg_4]; int
0x100041cf  mov     eax, ecx
0x100041d1  mov     ebx, edx
0x100041d3  push    dword ptr [ebp+arg_0]; char
0x100041d6  mov     [ebp+Buf], eax
0x100041d9  push    2; int
0x100041db  call    _MatchAndRefine@20; MatchAndRefine(x,x,x,x,x)
0x100041e0  mov     esi, eax
0x100041e2  dec     edi
0x100041e3  test    esi, esi
0x100041e5  jz      short loc_1000421D
0x100041e7  mov     eax, [ebp+Buf]
0x100041ea  xor     ecx, ecx
0x100041ec  push    [ebp+arg_4]; int
0x100041ef  mov     edx, ebx
0x100041f1  push    dword ptr [ebp+arg_0]; char
0x100041f4  movsx   eax, word ptr [eax+0BEh]
0x100041fb  cmp     edi, eax
0x100041fd  setnle  cl
0x10004200  push    ecx; int
0x10004201  mov     ecx, [ebp+Buf]; Buf
0x10004204  call    _MatchAndRefine@20; MatchAndRefine(x,x,x,x,x)
0x10004209  test    eax, eax
0x1000420b  jz      short loc_1000421D
0x1000420d  sub     esi, eax
0x1000420f  imul    esi, [ebx+10h]
0x10004213  cmp     esi, eax
0x10004215  jb      short loc_1000421D
0x10004217  mov     esi, eax
0x10004219  test    edi, edi
0x1000421b  jnz     short loc_100041E2
0x1000421d  pop     edi
0x1000421e  pop     esi
0x1000421f  pop     ebx
0x10004220  leave
0x10004221  retn    8
```
