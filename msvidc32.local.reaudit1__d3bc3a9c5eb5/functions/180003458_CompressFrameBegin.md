# CompressFrameBegin

- ea: `0x180003458`
- end: `0x18000363a`
- name: `CompressFrameBegin`
- size: `482`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005e00`
- `0x1800064e8`

## callees

- `0x180003458`
- `0x180007978`
- `0x180007c89`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000351c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000359d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003604`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000351c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000359d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003604`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000355b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003583`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000355b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003583`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003513`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003525`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003594`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800035a6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800035fb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000360d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003513`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003525`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003594`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800035a6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800035fb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000360d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000352e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800035af`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180003616`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000352e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800035af`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180003616`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003552`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000357a`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003552`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000357a`

## pseudocode

```c
__int64 __fastcall CompressFrameBegin(__int64 a1, __int64 a2, LPCVOID *a3, _DWORD *a4)
{
  __int64 v7; // r8
  int v8; // edi
  int v9; // edx
  __int64 v10; // rcx
  HGLOBAL v11; // rax
  HGLOBAL v12; // rax
  int v13; // ebp
  HGLOBAL v14; // rax
  const void *v15; // rbx
  HGLOBAL v16; // rax
  __int64 v17; // rdx
  const void *v18; // rdi
  __int64 v19; // r8
  HGLOBAL v20; // rax
  HGLOBAL v21; // rax
  __int64 i; // rcx
  HGLOBAL v23; // rax
  HGLOBAL v24; // rax

  if ( byte_18000B080[0] )
  {
    v7 = 0;
    do
    {
      byte_18000B080[v7] = 255 * (int)v7 / 31;
      v7 = (unsigned int)(v7 + 1);
    }
    while ( (int)v7 < 32 );
  }
  v8 = 256;
  if ( *(_WORD *)(a1 + 14) == 8 && !*(_DWORD *)(a1 + 32) )
    *(_DWORD *)(a1 + 32) = 256;
  if ( *(_WORD *)(a2 + 14) == 8 )
  {
    if ( *(_DWORD *)(a2 + 32) )
      v8 = *(_DWORD *)(a2 + 32);
    else
      *(_DWORD *)(a2 + 32) = 256;
    if ( memcmp_0(a4, (const void *)(a2 + 40), 4LL * v8) )
    {
      v9 = 0;
      if ( v8 > 0 )
      {
        do
        {
          v10 = v9++;
          a4[v10] = *(_DWORD *)(a2 + 4 * v10 + 40);
        }
        while ( v9 < *(_DWORD *)(a2 + 32) );
      }
      if ( *a3 )
      {
        v11 = GlobalHandle(*a3);
        GlobalUnlock(v11);
        v12 = GlobalHandle(*a3);
        GlobalFree(v12);
      }
      *a3 = 0;
    }
    if ( !*a3 )
    {
      v13 = *(_DWORD *)(a2 + 32);
      v14 = GlobalAlloc(0x2042u, 0x8000u);
      v15 = GlobalLock(v14);
      if ( v15 )
      {
        v16 = GlobalAlloc(0x42u, 0x20000u);
        v18 = GlobalLock(v16);
        if ( v18 )
        {
          for ( i = 0; (int)i < v13; i = (unsigned int)(i + 1) )
          {
            *((_BYTE *)NewMap + i) = BYTE2(a4[i]);
            *((_BYTE *)&NewMap[32] + i) = BYTE1(a4[i]);
            *((_BYTE *)&NewMap[64] + i) = a4[i];
          }
          inv_cmap_2((unsigned int)v13, v17, v19, v18, v15);
          v23 = GlobalHandle(v18);
          GlobalUnlock(v23);
          v24 = GlobalHandle(v18);
          GlobalFree(v24);
          goto LABEL_25;
        }
        v20 = GlobalHandle(v15);
        GlobalUnlock(v20);
        v21 = GlobalHandle(v15);
        GlobalFree(v21);
      }
      v15 = 0;
LABEL_25:
      *a3 = v15;
      return v15 == 0 ? 0xFFFFFFFD : 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003458  push    rbx
0x18000345a  push    rbp
0x18000345b  push    rsi
0x18000345c  push    rdi
0x18000345d  push    r12
0x18000345f  push    r14
0x180003461  sub     rsp, 38h
0x180003465  cmp     cs:byte_18000B080, 0
0x18000346c  lea     r12, cs:180000000h
0x180003473  mov     r14, r9
0x180003476  mov     rsi, r8
0x180003479  mov     rbx, rdx
0x18000347c  jz      short loc_1800034AE
0x18000347e  xor     r8d, r8d
0x180003481  imul    r9d, r8d, 0FFh
0x180003488  mov     eax, 84210843h
0x18000348d  imul    r9d
0x180003490  add     edx, r9d
0x180003493  sar     edx, 4
0x180003496  mov     eax, edx
0x180003498  shr     eax, 1Fh
0x18000349b  add     edx, eax
0x18000349d  mov     [r8+r12+0B080h], dl
0x1800034a5  inc     r8d
0x1800034a8  cmp     r8d, 20h ; ' '
0x1800034ac  jl      short loc_180003481
0x1800034ae  cmp     word ptr [rcx+0Eh], 8
0x1800034b3  mov     edi, 100h
0x1800034b8  jnz     short loc_1800034C3
0x1800034ba  cmp     dword ptr [rcx+20h], 0
0x1800034be  jnz     short loc_1800034C3
0x1800034c0  mov     [rcx+20h], edi
0x1800034c3  cmp     word ptr [rbx+0Eh], 8
0x1800034c8  jnz     loc_18000362B
0x1800034ce  cmp     dword ptr [rbx+20h], 0
0x1800034d2  jnz     short loc_1800034D9
0x1800034d4  mov     [rbx+20h], edi
0x1800034d7  jmp     short loc_1800034DC
0x1800034d9  mov     edi, [rbx+20h]
0x1800034dc  movsxd  r8, edi
0x1800034df  lea     rdx, [rbx+28h]; Buf2
0x1800034e3  shl     r8, 2; Size
0x1800034e7  mov     rcx, r14; Buf1
0x1800034ea  call    memcmp_0
0x1800034ef  test    eax, eax
0x1800034f1  jz      short loc_18000353B
0x1800034f3  xor     edx, edx
0x1800034f5  test    edi, edi
0x1800034f7  jle     short loc_18000350B
0x1800034f9  movsxd  rcx, edx
0x1800034fc  inc     edx
0x1800034fe  mov     eax, [rbx+rcx*4+28h]
0x180003502  mov     [r14+rcx*4], eax
0x180003506  cmp     edx, [rbx+20h]
0x180003509  jl      short loc_1800034F9
0x18000350b  mov     rcx, [rsi]; pMem
0x18000350e  test    rcx, rcx
0x180003511  jz      short loc_180003534
0x180003513  call    cs:__imp_GlobalHandle
0x180003519  mov     rcx, rax; hMem
0x18000351c  call    cs:__imp_GlobalUnlock
0x180003522  mov     rcx, [rsi]; pMem
0x180003525  call    cs:__imp_GlobalHandle
0x18000352b  mov     rcx, rax; hMem
0x18000352e  call    cs:__imp_GlobalFree
0x180003534  mov     qword ptr [rsi], 0
0x18000353b  cmp     qword ptr [rsi], 0
0x18000353f  jnz     loc_18000362B
0x180003545  mov     ebp, [rbx+20h]
0x180003548  mov     edx, 8000h; dwBytes
0x18000354d  mov     ecx, 2042h; uFlags
0x180003552  call    cs:__imp_GlobalAlloc
0x180003558  mov     rcx, rax; hMem
0x18000355b  call    cs:__imp_GlobalLock
0x180003561  mov     rbx, rax
0x180003564  test    rax, rax
0x180003567  jnz     short loc_180003570
0x180003569  xor     ebx, ebx
0x18000356b  jmp     loc_18000361C
0x180003570  mov     edx, 20000h; dwBytes
0x180003575  mov     ecx, 42h ; 'B'; uFlags
0x18000357a  call    cs:__imp_GlobalAlloc
0x180003580  mov     rcx, rax; hMem
0x180003583  call    cs:__imp_GlobalLock
0x180003589  mov     rdi, rax
0x18000358c  test    rax, rax
0x18000358f  jnz     short loc_1800035B7
0x180003591  mov     rcx, rbx; pMem
0x180003594  call    cs:__imp_GlobalHandle
0x18000359a  mov     rcx, rax; hMem
0x18000359d  call    cs:__imp_GlobalUnlock
0x1800035a3  mov     rcx, rbx; pMem
0x1800035a6  call    cs:__imp_GlobalHandle
0x1800035ac  mov     rcx, rax; hMem
0x1800035af  call    cs:__imp_GlobalFree
0x1800035b5  jmp     short loc_180003569
0x1800035b7  xor     ecx, ecx
0x1800035b9  test    ebp, ebp
0x1800035bb  jle     short loc_1800035E9
0x1800035bd  mov     al, [r14+rcx*4+2]
0x1800035c2  mov     [rcx+r12+0B500h], al
0x1800035ca  mov     al, [r14+rcx*4+1]
0x1800035cf  mov     [rcx+r12+0B600h], al
0x1800035d7  mov     al, [r14+rcx*4]
0x1800035db  mov     [rcx+r12+0B700h], al
0x1800035e3  inc     ecx
0x1800035e5  cmp     ecx, ebp
0x1800035e7  jl      short loc_1800035BD
0x1800035e9  mov     r9, rdi
0x1800035ec  mov     [rsp+68h+var_48], rbx
0x1800035f1  mov     ecx, ebp
0x1800035f3  call    inv_cmap_2
0x1800035f8  mov     rcx, rdi; pMem
0x1800035fb  call    cs:__imp_GlobalHandle
0x180003601  mov     rcx, rax; hMem
0x180003604  call    cs:__imp_GlobalUnlock
0x18000360a  mov     rcx, rdi; pMem
0x18000360d  call    cs:__imp_GlobalHandle
0x180003613  mov     rcx, rax; hMem
0x180003616  call    cs:__imp_GlobalFree
0x18000361c  mov     [rsi], rbx
0x18000361f  neg     rbx
0x180003622  sbb     eax, eax
0x180003624  not     eax
0x180003626  and     eax, 0FFFFFFFDh
0x180003629  jmp     short loc_18000362D
0x18000362b  xor     eax, eax
0x18000362d  add     rsp, 38h
0x180003631  pop     r14
0x180003633  pop     r12
0x180003635  pop     rdi
0x180003636  pop     rsi
0x180003637  pop     rbp
0x180003638  pop     rbx
0x180003639  retn
```
