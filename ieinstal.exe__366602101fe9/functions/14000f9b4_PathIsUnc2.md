# PathIsUnc2

- ea: `0x14000f9b4`
- end: `0x14000fa4a`
- name: `PathIsUnc2`
- size: `150`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400105d8`
- `0x140010820`

## callees

- `0x14000f3c0`
- `0x14000f9b4`
- `0x14000fa50`
- `0x1400100b8`

## pseudocode

```c
__int64 __fastcall PathIsUnc2(unsigned __int16 *a1, _QWORD *a2)
{
  unsigned int v2; // edi
  bool v5; // al
  __int64 v6; // rax

  v2 = 0;
  if ( a2 )
    *a2 = 0;
  if ( (unsigned __int8)IsBackslash(*a1) && (unsigned __int8)IsBackslash(a1[1]) )
  {
    if ( a1[2] == 63 )
    {
      if ( !StrIsEqualCaseInsensitive(a1 + 3, L"\\UNC\\", 5) )
        return v2;
      v6 = 8;
      v2 = 1;
    }
    else
    {
      v5 = !PathIsVolumeGUIDWorker(a1);
      v2 = v5;
      if ( !v5 )
        return v2;
      v6 = 2LL * v5;
    }
    if ( a2 )
      *a2 = &a1[v6];
  }
  return v2;
}

```

## disassembly

```asm
0x14000f9b4  mov     [rsp+arg_0], rbx
0x14000f9b9  mov     [rsp+arg_8], rsi
0x14000f9be  push    rdi
0x14000f9bf  sub     rsp, 20h
0x14000f9c3  xor     edi, edi
0x14000f9c5  mov     rsi, rdx
0x14000f9c8  mov     rbx, rcx
0x14000f9cb  test    rdx, rdx
0x14000f9ce  jz      short loc_14000F9D3
0x14000f9d0  mov     [rdx], rdi
0x14000f9d3  movzx   ecx, word ptr [rcx]
0x14000f9d6  call    IsBackslash
0x14000f9db  test    al, al
0x14000f9dd  jz      short loc_14000FA37
0x14000f9df  movzx   ecx, word ptr [rbx+2]
0x14000f9e3  call    IsBackslash
0x14000f9e8  test    al, al
0x14000f9ea  jz      short loc_14000FA37
0x14000f9ec  cmp     word ptr [rbx+4], 3Fh ; '?'
0x14000f9f1  jz      short loc_14000FA09
0x14000f9f3  mov     rcx, rbx; unsigned __int16 *
0x14000f9f6  call    ?PathIsVolumeGUIDWorker@@YA_NPEBG@Z; PathIsVolumeGUIDWorker(ushort const *)
0x14000f9fb  xor     al, 1
0x14000f9fd  movzx   edi, al
0x14000fa00  jz      short loc_14000FA37
0x14000fa02  mov     eax, edi
0x14000fa04  add     rax, rax
0x14000fa07  jmp     short loc_14000FA2B
0x14000fa09  lea     rcx, [rbx+6]; unsigned __int16 *
0x14000fa0d  mov     r8d, 5; int
0x14000fa13  lea     rdx, aUnc; "\\UNC\\"
0x14000fa1a  call    ?StrIsEqualCaseInsensitive@@YA_NPEBG0H@Z; StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)
0x14000fa1f  test    al, al
0x14000fa21  jz      short loc_14000FA37
0x14000fa23  mov     eax, 8
0x14000fa28  lea     edi, [rax-7]
0x14000fa2b  test    rsi, rsi
0x14000fa2e  jz      short loc_14000FA37
0x14000fa30  lea     rcx, [rbx+rax*2]
0x14000fa34  mov     [rsi], rcx
0x14000fa37  mov     rbx, [rsp+28h+arg_0]
0x14000fa3c  mov     eax, edi
0x14000fa3e  mov     rsi, [rsp+28h+arg_8]
0x14000fa43  add     rsp, 20h
0x14000fa47  pop     rdi
0x14000fa48  retn
```
