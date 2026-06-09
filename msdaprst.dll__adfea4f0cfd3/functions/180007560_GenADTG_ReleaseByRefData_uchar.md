# GenADTG::ReleaseByRefData(uchar *)

- ea: `0x180007560`
- end: `0x1800075f5`
- name: `?ReleaseByRefData@GenADTG@@AEAAXPEAE@Z`
- size: `149`
- prototype: `void __fastcall(GenADTG *__hidden this, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180008e00`
- `0x18002f8cb`

## callees

- `0x180007560`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800075bb`
- `ole32!CoTaskMemFree` at `0x1800075bb`

## pseudocode

```c
void __fastcall GenADTG::ReleaseByRefData(GenADTG *this, unsigned __int8 *a2)
{
  int v2; // ebp
  __int64 v5; // rbx
  __int64 v6; // r14
  unsigned int v7; // ecx
  int v8; // eax
  __int64 v9; // rbx

  if ( a2 )
  {
    v2 = 0;
    if ( *((_WORD *)this + 32) )
    {
      do
      {
        v5 = *((_QWORD *)this + 7);
        v6 = 88LL * v2;
        if ( (*(_WORD *)(v5 + v6 + 84) & 0x4000) != 0 )
        {
          v7 = *(_DWORD *)&a2[*(_QWORD *)(v5 + v6 + 24)];
          if ( v7 <= 0xD )
          {
            v8 = 8209;
            if ( _bittest(&v8, v7) )
            {
              v9 = *(_QWORD *)(v5 + v6 + 8);
              CoTaskMemFree(*(LPVOID *)&a2[v9]);
              *(_QWORD *)&a2[v9] = 0;
            }
          }
          *(_DWORD *)&a2[*(_QWORD *)(*((_QWORD *)this + 7) + v6 + 24)] = 3;
        }
        ++v2;
      }
      while ( v2 < *((unsigned __int16 *)this + 32) );
    }
  }
}

```

## disassembly

```asm
0x180007560  test    rdx, rdx
0x180007563  jz      locret_1800075F3
0x180007569  push    rbx
0x18000756a  push    rbp
0x18000756b  push    rsi
0x18000756c  push    rdi
0x18000756d  push    r14
0x18000756f  sub     rsp, 20h
0x180007573  xor     ebp, ebp
0x180007575  xor     eax, eax
0x180007577  mov     rdi, rdx
0x18000757a  mov     rsi, rcx
0x18000757d  cmp     ax, [rcx+40h]
0x180007581  jnb     short loc_1800075E9
0x180007583  mov     rbx, [rsi+38h]
0x180007587  movsxd  rax, ebp
0x18000758a  imul    r14, rax, 58h ; 'X'
0x18000758e  mov     eax, 4000h
0x180007593  test    [rbx+r14+54h], ax
0x180007599  jz      short loc_1800075DF
0x18000759b  mov     rax, [rbx+r14+18h]
0x1800075a0  mov     ecx, [rdi+rax]
0x1800075a3  cmp     ecx, 0Dh
0x1800075a6  ja      short loc_1800075CF
0x1800075a8  mov     eax, 2011h
0x1800075ad  bt      eax, ecx
0x1800075b0  jnb     short loc_1800075CF
0x1800075b2  mov     rbx, [rbx+r14+8]
0x1800075b7  mov     rcx, [rbx+rdi]; pv
0x1800075bb  call    cs:__imp_CoTaskMemFree
0x1800075c2  nop     dword ptr [rax+rax+00h]
0x1800075c7  mov     qword ptr [rbx+rdi], 0
0x1800075cf  mov     rax, [rsi+38h]
0x1800075d3  mov     rcx, [rax+r14+18h]
0x1800075d8  mov     dword ptr [rdi+rcx], 3
0x1800075df  movzx   eax, word ptr [rsi+40h]
0x1800075e3  inc     ebp
0x1800075e5  cmp     ebp, eax
0x1800075e7  jl      short loc_180007583
0x1800075e9  add     rsp, 20h
0x1800075ed  pop     r14
0x1800075ef  pop     rdi
0x1800075f0  pop     rsi
0x1800075f1  pop     rbp
0x1800075f2  pop     rbx
0x1800075f3  retn
```
