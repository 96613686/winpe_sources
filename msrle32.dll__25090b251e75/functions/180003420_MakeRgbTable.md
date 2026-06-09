# MakeRgbTable

- ea: `0x180003420`
- end: `0x1800035d1`
- name: `MakeRgbTable`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000241c`

## callees

- `0x180003420`
- `0x18000375c`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003498`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003498`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000348f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000348f`

## pseudocode

```c
__int64 __fastcall MakeRgbTable(__int64 a1)
{
  int v2; // eax
  HGLOBAL v3; // rax
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r9
  int *v7; // rdi
  __int64 v8; // r11
  int v9; // eax
  __int16 v10; // dx
  int v11; // r8d
  __int16 v12; // dx
  int v13; // r8d
  int v14; // ecx
  int v15; // r8d
  __int16 v16; // cx
  bool v17; // cc
  __int16 v18; // ax
  int v19; // r8d
  __int64 v20; // rcx
  int v21; // edx

  if ( a1 )
  {
    v2 = *(_DWORD *)(a1 + 32);
    if ( !v2 )
    {
      v2 = 1 << *(_BYTE *)(a1 + 14);
      *(_DWORD *)(a1 + 32) = v2;
    }
    if ( pMem )
    {
      if ( v2 == gRgbTol[0] && !memcmp_0((const void *)(a1 + 40), &dword_180006124, 4LL * gRgbTol[0]) )
        return 1;
LABEL_9:
      v4 = *(_DWORD *)(a1 + 32);
      v5 = 0;
      for ( gRgbTol[0] = v4; (unsigned int)v5 < gRgbTol[0]; v4 = gRgbTol[0] )
      {
        gRgbTol[v5 + 1] = *(_DWORD *)(a1 + 4 * v5 + 40);
        v5 = (unsigned int)(v5 + 1);
      }
      v6 = 0;
      if ( v4 )
      {
        do
        {
          v7 = &gRgbTol[v6];
          v8 = 0;
          do
          {
            v9 = gRgbTol[v8 + 1];
            v10 = (unsigned __int8)BYTE2(v7[1]);
            if ( (unsigned __int8)v10 <= BYTE2(v9) )
              v11 = (unsigned __int16)(BYTE2(v9) - v10);
            else
              v11 = (unsigned __int16)(v10 - BYTE2(v9));
            v12 = (unsigned __int8)BYTE1(v7[1]);
            v13 = v11 * v11;
            if ( (unsigned __int8)v12 <= BYTE1(v9) )
              v14 = (unsigned __int16)(BYTE1(v9) - v12);
            else
              v14 = (unsigned __int16)(v12 - BYTE1(v9));
            v15 = v14 * v14 + v13;
            v16 = (unsigned __int8)v9;
            v17 = *((_BYTE *)v7 + 4) <= (unsigned __int8)v9;
            v18 = *((unsigned __int8 *)v7 + 4);
            if ( v17 )
              v19 = (unsigned __int16)(v16 - v18) * (unsigned __int16)(v16 - v18) + v15;
            else
              v19 = (unsigned __int16)(v18 - v16) * (unsigned __int16)(v18 - v16) + v15;
            v20 = (unsigned int)(((_DWORD)v6 << 8) + v8);
            v21 = v8;
            v8 = (unsigned int)(v8 + 1);
            *((_DWORD *)pMem + v20) = v19;
            *((_DWORD *)pMem + (unsigned int)(v6 + (v21 << 8))) = v19;
          }
          while ( (unsigned int)v8 <= (unsigned int)v6 );
          v6 = (unsigned int)(v6 + 1);
        }
        while ( (unsigned int)v6 < gRgbTol[0] );
      }
      return 1;
    }
    v3 = GlobalAlloc(0x2042u, 0x40000u);
    pMem = GlobalLock(v3);
    if ( pMem )
      goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x180003420  mov     [rsp+arg_0], rbx
0x180003425  mov     [rsp+arg_8], rbp
0x18000342a  push    rdi
0x18000342b  sub     rsp, 20h
0x18000342f  mov     rbx, rcx
0x180003432  test    rcx, rcx
0x180003435  jz      loc_1800035BF
0x18000343b  mov     eax, [rcx+20h]
0x18000343e  test    eax, eax
0x180003440  jnz     short loc_18000344F
0x180003442  mov     cl, [rcx+0Eh]
0x180003445  mov     eax, 1
0x18000344a  shl     eax, cl
0x18000344c  mov     [rbx+20h], eax
0x18000344f  cmp     cs:pMem, 0
0x180003457  jz      short loc_180003485
0x180003459  movsxd  rcx, cs:gRgbTol
0x180003460  cmp     eax, ecx
0x180003462  jnz     short loc_1800034AE
0x180003464  mov     r8, rcx
0x180003467  lea     rdx, dword_180006124; Buf2
0x18000346e  shl     r8, 2; Size
0x180003472  lea     rcx, [rbx+28h]; Buf1
0x180003476  call    memcmp_0
0x18000347b  test    eax, eax
0x18000347d  jz      loc_1800035B8
0x180003483  jmp     short loc_1800034AE
0x180003485  mov     edx, 40000h; dwBytes
0x18000348a  mov     ecx, 2042h; uFlags
0x18000348f  call    cs:__imp_GlobalAlloc
0x180003495  mov     rcx, rax; hMem
0x180003498  call    cs:__imp_GlobalLock
0x18000349e  mov     cs:pMem, rax
0x1800034a5  test    rax, rax
0x1800034a8  jz      loc_1800035BF
0x1800034ae  mov     eax, [rbx+20h]
0x1800034b1  lea     rbp, gRgbTol
0x1800034b8  xor     edx, edx
0x1800034ba  mov     cs:gRgbTol, eax
0x1800034c0  test    eax, eax
0x1800034c2  jz      short loc_1800034D8
0x1800034c4  mov     eax, [rbx+rdx*4+28h]
0x1800034c8  mov     [rbp+rdx*4+4], eax
0x1800034cc  inc     edx
0x1800034ce  mov     eax, cs:gRgbTol
0x1800034d4  cmp     edx, eax
0x1800034d6  jb      short loc_1800034C4
0x1800034d8  xor     r9d, r9d
0x1800034db  test    eax, eax
0x1800034dd  jz      loc_1800035B8
0x1800034e3  lea     rdi, ds:0[r9*4]
0x1800034eb  mov     ebx, r9d
0x1800034ee  add     rdi, rbp
0x1800034f1  xor     r11d, r11d
0x1800034f4  shl     ebx, 8
0x1800034f7  mov     ecx, [rdi+4]
0x1800034fa  mov     eax, [rbp+r11*4+4]
0x1800034ff  shr     ecx, 10h
0x180003502  movzx   edx, cl
0x180003505  mov     ecx, eax
0x180003507  shr     ecx, 10h
0x18000350a  movzx   r8d, cl
0x18000350e  cmp     dl, r8b
0x180003511  jbe     short loc_18000351C
0x180003513  sub     edx, r8d
0x180003516  movzx   r8d, dx
0x18000351a  jmp     short loc_180003523
0x18000351c  sub     r8d, edx
0x18000351f  movzx   r8d, r8w
0x180003523  mov     ecx, [rdi+4]
0x180003526  shr     ecx, 8
0x180003529  movzx   edx, cl
0x18000352c  mov     ecx, eax
0x18000352e  shr     ecx, 8
0x180003531  movzx   r10d, cl
0x180003535  imul    r8d, r8d
0x180003539  cmp     dl, r10b
0x18000353c  jbe     short loc_180003546
0x18000353e  sub     edx, r10d
0x180003541  movzx   ecx, dx
0x180003544  jmp     short loc_18000354D
0x180003546  sub     r10d, edx
0x180003549  movzx   ecx, r10w
0x18000354d  imul    ecx, ecx
0x180003550  add     r8d, ecx
0x180003553  movzx   ecx, al
0x180003556  cmp     [rdi+4], al
0x180003559  movzx   eax, byte ptr [rdi+4]
0x18000355d  jbe     short loc_18000356D
0x18000355f  sub     ax, cx
0x180003562  movzx   ecx, ax
0x180003565  imul    ecx, ecx
0x180003568  add     r8d, ecx
0x18000356b  jmp     short loc_180003579
0x18000356d  sub     cx, ax
0x180003570  movzx   eax, cx
0x180003573  imul    eax, eax
0x180003576  add     r8d, eax
0x180003579  mov     rax, cs:pMem
0x180003580  lea     ecx, [rbx+r11]
0x180003584  mov     edx, r11d
0x180003587  inc     r11d
0x18000358a  shl     edx, 8
0x18000358d  add     edx, r9d
0x180003590  mov     [rax+rcx*4], r8d
0x180003594  mov     rcx, cs:pMem
0x18000359b  mov     [rcx+rdx*4], r8d
0x18000359f  cmp     r11d, r9d
0x1800035a2  jbe     loc_1800034F7
0x1800035a8  inc     r9d
0x1800035ab  cmp     r9d, cs:gRgbTol
0x1800035b2  jb      loc_1800034E3
0x1800035b8  mov     eax, 1
0x1800035bd  jmp     short loc_1800035C1
0x1800035bf  xor     eax, eax
0x1800035c1  mov     rbx, [rsp+28h+arg_0]
0x1800035c6  mov     rbp, [rsp+28h+arg_8]
0x1800035cb  add     rsp, 20h
0x1800035cf  pop     rdi
0x1800035d0  retn
```
