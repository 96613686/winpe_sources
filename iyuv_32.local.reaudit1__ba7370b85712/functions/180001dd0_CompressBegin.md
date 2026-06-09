# CompressBegin

- ea: `0x180001dd0`
- end: `0x180001f28`
- name: `CompressBegin`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002710`

## callees

- `0x180001dd0`
- `0x180002084`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180001e4e`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180001e90`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180001ebb`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180001ee9`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180001e4e`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180001e90`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180001ebb`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180001ee9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180001e5b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180001e9d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180001ec8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180001ef6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180001e5b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180001e9d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180001ec8`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180001ef6`

## pseudocode

```c
__int64 __fastcall CompressBegin(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  __int16 v6; // ax
  __int16 v7; // cx
  int v8; // edi
  int v9; // ecx
  __int16 v10; // ax
  int v11; // edi
  bool v12; // zf
  HGLOBAL v13; // rax
  LPVOID v14; // rax
  SIZE_T v15; // rsi
  HGLOBAL v16; // rax
  LPVOID v17; // rax
  HGLOBAL v18; // rax
  LPVOID v19; // rax
  HGLOBAL v20; // rax
  LPVOID v21; // rax

  result = CompressQuery(a2, a3);
  if ( !(_DWORD)result )
  {
    *(_BYTE *)(a1 + 10) = 0;
    v6 = *(_WORD *)(a2 + 4);
    *(_WORD *)(a1 + 80) = v6;
    v7 = *(_WORD *)(a2 + 8);
    v8 = v6 & 0xFFFC;
    *(_WORD *)(a1 + 82) = v7;
    v9 = v7 & 0xFFFC;
    *(_WORD *)(a1 + 84) = v8;
    *(_WORD *)(a1 + 86) = v9;
    v10 = *(_WORD *)(a2 + 4);
    *(_WORD *)(a1 + 6) = v8;
    v11 = v9 * v8;
    v12 = *(_DWORD *)a1 == 0;
    *(_WORD *)(a1 + 4) = v10;
    *(_WORD *)(a1 + 8) = v9;
    *(_DWORD *)(a1 + 88) = v11;
    if ( !v12 )
      return 0;
    v13 = GlobalAlloc(0x42u, v11);
    *(_QWORD *)(a1 + 16) = v13;
    v14 = GlobalLock(v13);
    v12 = *(_QWORD *)(a1 + 16) == 0;
    *(_QWORD *)(a1 + 48) = v14;
    if ( !v12 )
    {
      if ( v14 )
      {
        v15 = (v11 + 3) / 4;
        v16 = GlobalAlloc(0x42u, v15);
        *(_QWORD *)(a1 + 32) = v16;
        v17 = GlobalLock(v16);
        v12 = *(_QWORD *)(a1 + 32) == 0;
        *(_QWORD *)(a1 + 64) = v17;
        if ( !v12 )
        {
          if ( v17 )
          {
            v18 = GlobalAlloc(0x42u, v15);
            *(_QWORD *)(a1 + 24) = v18;
            v19 = GlobalLock(v18);
            v12 = *(_QWORD *)(a1 + 24) == 0;
            *(_QWORD *)(a1 + 56) = v19;
            if ( !v12 )
            {
              if ( v19 )
              {
                v20 = GlobalAlloc(0x42u, 2 * v11);
                *(_QWORD *)(a1 + 40) = v20;
                v21 = GlobalLock(v20);
                v12 = *(_QWORD *)(a1 + 40) == 0;
                *(_QWORD *)(a1 + 72) = v21;
                if ( !v12 )
                {
                  if ( v21 )
                  {
                    ++*(_DWORD *)a1;
                    return 0;
                  }
                }
              }
            }
          }
        }
      }
    }
    return 4294967293LL;
  }
  return result;
}

```

## disassembly

```asm
0x180001dd0  mov     [rsp+arg_0], rbx
0x180001dd5  mov     [rsp+arg_8], rsi
0x180001dda  push    rdi
0x180001ddb  sub     rsp, 20h
0x180001ddf  mov     rsi, rdx
0x180001de2  mov     rbx, rcx
0x180001de5  mov     rcx, rsi
0x180001de8  mov     rdx, r8
0x180001deb  call    CompressQuery
0x180001df0  test    eax, eax
0x180001df2  jnz     loc_180001F18
0x180001df8  mov     [rbx+0Ah], al
0x180001dfb  mov     edx, 0FFFCh
0x180001e00  movzx   eax, word ptr [rsi+4]
0x180001e04  mov     [rbx+50h], ax
0x180001e08  and     ax, dx
0x180001e0b  movzx   ecx, word ptr [rsi+8]
0x180001e0f  movzx   edi, ax
0x180001e12  mov     [rbx+52h], cx
0x180001e16  and     cx, dx
0x180001e19  movzx   ecx, cx
0x180001e1c  mov     [rbx+54h], di
0x180001e20  mov     [rbx+56h], cx
0x180001e24  movzx   eax, word ptr [rsi+4]
0x180001e28  mov     [rbx+6], di
0x180001e2c  imul    edi, ecx
0x180001e2f  cmp     dword ptr [rbx], 0
0x180001e32  mov     [rbx+4], ax
0x180001e36  mov     [rbx+8], cx
0x180001e3a  mov     [rbx+58h], edi
0x180001e3d  jz      short loc_180001E46
0x180001e3f  xor     eax, eax
0x180001e41  jmp     loc_180001F18
0x180001e46  movsxd  rdx, edi; dwBytes
0x180001e49  mov     ecx, 42h ; 'B'; uFlags
0x180001e4e  call    cs:__imp_GlobalAlloc
0x180001e54  mov     rcx, rax; hMem
0x180001e57  mov     [rbx+10h], rax
0x180001e5b  call    cs:__imp_GlobalLock
0x180001e61  cmp     qword ptr [rbx+10h], 0
0x180001e66  mov     [rbx+30h], rax
0x180001e6a  jz      loc_180001F13
0x180001e70  test    rax, rax
0x180001e73  jz      loc_180001F13
0x180001e79  lea     eax, [rdi+3]
0x180001e7c  mov     ecx, 42h ; 'B'; uFlags
0x180001e81  cdq
0x180001e82  and     edx, 3
0x180001e85  add     eax, edx
0x180001e87  sar     eax, 2
0x180001e8a  movsxd  rsi, eax
0x180001e8d  mov     rdx, rsi; dwBytes
0x180001e90  call    cs:__imp_GlobalAlloc
0x180001e96  mov     rcx, rax; hMem
0x180001e99  mov     [rbx+20h], rax
0x180001e9d  call    cs:__imp_GlobalLock
0x180001ea3  cmp     qword ptr [rbx+20h], 0
0x180001ea8  mov     [rbx+40h], rax
0x180001eac  jz      short loc_180001F13
0x180001eae  test    rax, rax
0x180001eb1  jz      short loc_180001F13
0x180001eb3  mov     rdx, rsi; dwBytes
0x180001eb6  mov     ecx, 42h ; 'B'; uFlags
0x180001ebb  call    cs:__imp_GlobalAlloc
0x180001ec1  mov     rcx, rax; hMem
0x180001ec4  mov     [rbx+18h], rax
0x180001ec8  call    cs:__imp_GlobalLock
0x180001ece  cmp     qword ptr [rbx+18h], 0
0x180001ed3  mov     [rbx+38h], rax
0x180001ed7  jz      short loc_180001F13
0x180001ed9  test    rax, rax
0x180001edc  jz      short loc_180001F13
0x180001ede  lea     eax, [rdi+rdi]
0x180001ee1  mov     ecx, 42h ; 'B'; uFlags
0x180001ee6  movsxd  rdx, eax; dwBytes
0x180001ee9  call    cs:__imp_GlobalAlloc
0x180001eef  mov     rcx, rax; hMem
0x180001ef2  mov     [rbx+28h], rax
0x180001ef6  call    cs:__imp_GlobalLock
0x180001efc  cmp     qword ptr [rbx+28h], 0
0x180001f01  mov     [rbx+48h], rax
0x180001f05  jz      short loc_180001F13
0x180001f07  test    rax, rax
0x180001f0a  jz      short loc_180001F13
0x180001f0c  inc     dword ptr [rbx]
0x180001f0e  jmp     loc_180001E3F
0x180001f13  mov     eax, 0FFFFFFFDh
0x180001f18  mov     rbx, [rsp+28h+arg_0]
0x180001f1d  mov     rsi, [rsp+28h+arg_8]
0x180001f22  add     rsp, 20h
0x180001f26  pop     rdi
0x180001f27  retn
```
