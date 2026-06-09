# LDIDecompress

- ea: `0x180005380`
- end: `0x180005429`
- name: `LDIDecompress`
- size: `169`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800051d0`

## callees

- `0x180005380`
- `0x180005430`
- `0x18000548c`

## pseudocode

```c
__int64 __fastcall LDIDecompress(__int64 a1, __int64 a2, unsigned int a3, __int64 a4, int *a5)
{
  unsigned int v5; // eax
  __int64 v6; // rbx
  unsigned int v7; // r10d
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // ecx

  if ( *(_DWORD *)a1 != 1128875084 )
    return 2;
  v5 = *(_DWORD *)(a1 + 64);
  if ( *a5 > v5 )
    return 3;
  if ( a3 <= v5 + 6144 )
  {
    v6 = *(_QWORD *)(a1 + 72);
    *(_QWORD *)(v6 + 11016) = a2;
    *(_QWORD *)(v6 + 11032) = a4;
    *(_QWORD *)(v6 + 11024) = a2 + 4 + (int)a3;
    initialise_decoder_bitbuf(v6);
    v9 = decode_data(v8, v7);
    v10 = *(_DWORD *)(v6 + 11996);
    if ( v10 < 0x8000 )
      *(_DWORD *)(v6 + 11996) = v10 + 1;
    if ( v9 >= 0 )
    {
      *(_DWORD *)(v6 + 11040) += v9;
      *a5 = v9;
      return 0;
    }
    *a5 = 0;
  }
  return 4;
}

```

## disassembly

```asm
0x180005380  mov     [rsp+arg_0], rbx
0x180005385  push    rdi
0x180005386  sub     rsp, 20h
0x18000538a  cmp     dword ptr [rcx], 4349444Ch
0x180005390  jnz     short loc_18000540E
0x180005392  mov     rdi, [rsp+28h+arg_20]
0x180005397  mov     eax, [rcx+40h]
0x18000539a  mov     r10d, [rdi]
0x18000539d  cmp     r10d, eax
0x1800053a0  ja      short loc_180005415
0x1800053a2  add     eax, 1800h
0x1800053a7  cmp     r8d, eax
0x1800053aa  ja      short loc_180005422
0x1800053ac  mov     rbx, [rcx+48h]
0x1800053b0  movsxd  rcx, r8d
0x1800053b3  mov     [rbx+2B08h], rdx
0x1800053ba  add     rdx, 4
0x1800053be  add     rcx, rdx
0x1800053c1  mov     [rbx+2B18h], r9
0x1800053c8  mov     [rbx+2B10h], rcx
0x1800053cf  mov     rcx, rbx
0x1800053d2  call    initialise_decoder_bitbuf
0x1800053d7  mov     edx, r10d
0x1800053da  call    decode_data
0x1800053df  mov     ecx, [rbx+2EDCh]
0x1800053e5  cmp     ecx, 8000h
0x1800053eb  jnb     short loc_1800053F5
0x1800053ed  inc     ecx
0x1800053ef  mov     [rbx+2EDCh], ecx
0x1800053f5  test    eax, eax
0x1800053f7  js      short loc_18000541C
0x1800053f9  add     [rbx+2B20h], eax
0x1800053ff  mov     [rdi], eax
0x180005401  xor     eax, eax
0x180005403  mov     rbx, [rsp+28h+arg_0]
0x180005408  add     rsp, 20h
0x18000540c  pop     rdi
0x18000540d  retn
0x18000540e  mov     eax, 2
0x180005413  jmp     short loc_180005403
0x180005415  mov     eax, 3
0x18000541a  jmp     short loc_180005403
0x18000541c  mov     dword ptr [rdi], 0
0x180005422  mov     eax, 4
0x180005427  jmp     short loc_180005403
```
