# DwReplaceEapUserInfo

- ea: `0x18002420c`
- end: `0x180024321`
- name: `DwReplaceEapUserInfo`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180024358`

## callees

- `0x180024140`
- `0x18002420c`
- `0x180024328`
- `0x1800263b6`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024308`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024308`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002429d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002429d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800242ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800242ab`

## pseudocode

```c
__int64 __fastcall DwReplaceEapUserInfo(
        __int128 *a1,
        const void *a2,
        unsigned int a3,
        const void *a4,
        size_t Size,
        HKEY a6,
        int a7)
{
  unsigned int v7; // ebx
  size_t v8; // r14
  int v12; // r12d
  size_t v13; // rbx
  unsigned int v14; // eax
  DWORD v15; // esi
  BYTE *v16; // rax
  BYTE *v17; // rdi
  __int128 v18; // xmm0

  v7 = 0;
  v8 = a3;
  if ( a1 )
  {
    v12 = a7;
    v7 = DwRemoveEapUserInfo((_DWORD)a1, (_DWORD)a4, (unsigned int)&Size, (_DWORD)a6, 0, a7);
    if ( !v7 )
    {
      if ( (unsigned int)v8 >= 0xFFFFFFE0 )
        return 534;
      v13 = (unsigned int)Size;
      v14 = (v8 + 39) & 0xFFFFFFF8;
      v15 = v14 + Size;
      if ( v14 + (unsigned int)Size < v14 )
      {
        return 534;
      }
      else
      {
        v16 = (BYTE *)LocalAlloc(0x40u, v15);
        v17 = v16;
        if ( v16 )
        {
          memcpy_0(v16, a4, v13);
          v18 = *a1;
          *(_DWORD *)&v17[v13 + 4] = v12;
          *(_DWORD *)&v17[v13 + 24] = v8;
          *(_DWORD *)&v17[v13] = 844120389;
          *(_OWORD *)&v17[v13 + 8] = v18;
          memcpy_0(&v17[v13 + 28], a2, v8);
          v7 = DwSetEapInfo(a6, v17, v15);
          LocalFree(v17);
        }
        else
        {
          return GetLastError();
        }
      }
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18002420c  mov     r11, rsp
0x18002420f  push    rbx
0x180024210  push    rbp
0x180024211  push    rsi
0x180024212  push    rdi
0x180024213  push    r12
0x180024215  push    r13
0x180024217  push    r14
0x180024219  push    r15
0x18002421b  sub     rsp, 38h
0x18002421f  mov     eax, dword ptr [rsp+78h+Size]
0x180024226  xor     ebx, ebx
0x180024228  mov     r14d, r8d
0x18002422b  mov     r15, r9
0x18002422e  mov     [r11+28h], eax
0x180024232  mov     r13, rdx
0x180024235  mov     rbp, rcx
0x180024238  test    rcx, rcx
0x18002423b  jz      loc_18002430E
0x180024241  mov     r12d, [rsp+78h+arg_30]
0x180024249  lea     r8, [r11+28h]
0x18002424d  mov     r9, [rsp+78h+arg_28]
0x180024255  mov     rdx, r15
0x180024258  mov     [r11-50h], r12d
0x18002425c  mov     [rsp+78h+var_58], ebx
0x180024260  call    DwRemoveEapUserInfo
0x180024265  mov     ebx, eax
0x180024267  test    eax, eax
0x180024269  jnz     loc_18002430E
0x18002426f  lea     eax, [r14+20h]
0x180024273  cmp     eax, 20h ; ' '
0x180024276  jnb     short loc_180024282
0x180024278  mov     ebx, 216h
0x18002427d  jmp     loc_18002430E
0x180024282  mov     ebx, dword ptr [rsp+78h+Size]
0x180024289  add     eax, 7
0x18002428c  and     eax, 0FFFFFFF8h
0x18002428f  lea     esi, [rax+rbx]
0x180024292  cmp     esi, eax
0x180024294  jb      short loc_180024278
0x180024296  mov     edx, esi; uBytes
0x180024298  mov     ecx, 40h ; '@'; uFlags
0x18002429d  call    cs:__imp_LocalAlloc
0x1800242a3  mov     rdi, rax
0x1800242a6  test    rax, rax
0x1800242a9  jnz     short loc_1800242B5
0x1800242ab  call    cs:__imp_GetLastError
0x1800242b1  mov     ebx, eax
0x1800242b3  jmp     short loc_18002430E
0x1800242b5  mov     r8, rbx; Size
0x1800242b8  mov     rdx, r15; Src
0x1800242bb  mov     rcx, rdi; void *
0x1800242be  call    memcpy_0
0x1800242c3  movups  xmm0, xmmword ptr [rbp+0]
0x1800242c7  lea     rcx, [rbx+1Ch]
0x1800242cb  mov     [rbx+rdi+4], r12d
0x1800242d0  mov     r8, r14; Size
0x1800242d3  mov     [rbx+rdi+18h], r14d
0x1800242d8  add     rcx, rdi; void *
0x1800242db  mov     dword ptr [rbx+rdi], 32504145h
0x1800242e2  mov     rdx, r13; Src
0x1800242e5  movdqu  xmmword ptr [rbx+rdi+8], xmm0
0x1800242eb  call    memcpy_0
0x1800242f0  mov     rcx, [rsp+78h+arg_28]
0x1800242f8  mov     r8d, esi
0x1800242fb  mov     rdx, rdi
0x1800242fe  call    DwSetEapInfo
0x180024303  mov     ebx, eax
0x180024305  mov     rcx, rdi; hMem
0x180024308  call    cs:__imp_LocalFree
0x18002430e  mov     eax, ebx
0x180024310  add     rsp, 38h
0x180024314  pop     r15
0x180024316  pop     r14
0x180024318  pop     r13
0x18002431a  pop     r12
0x18002431c  pop     rdi
0x18002431d  pop     rsi
0x18002431e  pop     rbp
0x18002431f  pop     rbx
0x180024320  retn
```
