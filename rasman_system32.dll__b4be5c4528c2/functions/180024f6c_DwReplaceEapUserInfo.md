# DwReplaceEapUserInfo

- ea: `0x180024f6c`
- end: `0x180025094`
- name: `DwReplaceEapUserInfo`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800250d4`

## callees

- `0x180024ea0`
- `0x180024f6c`
- `0x18002509c`
- `0x180027386`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025074`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025074`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024ffd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024ffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025011`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025011`

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
0x180024f6c  mov     r11, rsp
0x180024f6f  push    rbx
0x180024f70  push    rbp
0x180024f71  push    rsi
0x180024f72  push    rdi
0x180024f73  push    r12
0x180024f75  push    r13
0x180024f77  push    r14
0x180024f79  push    r15
0x180024f7b  sub     rsp, 38h
0x180024f7f  mov     eax, dword ptr [rsp+78h+Size]
0x180024f86  xor     ebx, ebx
0x180024f88  mov     r14d, r8d
0x180024f8b  mov     r15, r9
0x180024f8e  mov     [r11+28h], eax
0x180024f92  mov     r13, rdx
0x180024f95  mov     rbp, rcx
0x180024f98  test    rcx, rcx
0x180024f9b  jz      loc_180025080
0x180024fa1  mov     r12d, [rsp+78h+arg_30]
0x180024fa9  lea     r8, [r11+28h]
0x180024fad  mov     r9, [rsp+78h+arg_28]
0x180024fb5  mov     rdx, r15
0x180024fb8  mov     [r11-50h], r12d
0x180024fbc  mov     [rsp+78h+var_58], ebx
0x180024fc0  call    DwRemoveEapUserInfo
0x180024fc5  mov     ebx, eax
0x180024fc7  test    eax, eax
0x180024fc9  jnz     loc_180025080
0x180024fcf  lea     eax, [r14+20h]
0x180024fd3  cmp     eax, 20h ; ' '
0x180024fd6  jnb     short loc_180024FE2
0x180024fd8  mov     ebx, 216h
0x180024fdd  jmp     loc_180025080
0x180024fe2  mov     ebx, dword ptr [rsp+78h+Size]
0x180024fe9  add     eax, 7
0x180024fec  and     eax, 0FFFFFFF8h
0x180024fef  lea     esi, [rax+rbx]
0x180024ff2  cmp     esi, eax
0x180024ff4  jb      short loc_180024FD8
0x180024ff6  mov     edx, esi; uBytes
0x180024ff8  mov     ecx, 40h ; '@'; uFlags
0x180024ffd  call    cs:__imp_LocalAlloc
0x180025004  nop     dword ptr [rax+rax+00h]
0x180025009  mov     rdi, rax
0x18002500c  test    rax, rax
0x18002500f  jnz     short loc_180025021
0x180025011  call    cs:__imp_GetLastError
0x180025018  nop     dword ptr [rax+rax+00h]
0x18002501d  mov     ebx, eax
0x18002501f  jmp     short loc_180025080
0x180025021  mov     r8, rbx; Size
0x180025024  mov     rdx, r15; Src
0x180025027  mov     rcx, rdi; void *
0x18002502a  call    memcpy_0
0x18002502f  movups  xmm0, xmmword ptr [rbp+0]
0x180025033  lea     rcx, [rbx+1Ch]
0x180025037  mov     [rbx+rdi+4], r12d
0x18002503c  mov     r8, r14; Size
0x18002503f  mov     [rbx+rdi+18h], r14d
0x180025044  add     rcx, rdi; void *
0x180025047  mov     dword ptr [rbx+rdi], 32504145h
0x18002504e  mov     rdx, r13; Src
0x180025051  movdqu  xmmword ptr [rbx+rdi+8], xmm0
0x180025057  call    memcpy_0
0x18002505c  mov     rcx, [rsp+78h+arg_28]
0x180025064  mov     r8d, esi
0x180025067  mov     rdx, rdi
0x18002506a  call    DwSetEapInfo
0x18002506f  mov     ebx, eax
0x180025071  mov     rcx, rdi; hMem
0x180025074  call    cs:__imp_LocalFree
0x18002507b  nop     dword ptr [rax+rax+00h]
0x180025080  mov     eax, ebx
0x180025082  add     rsp, 38h
0x180025086  pop     r15
0x180025088  pop     r14
0x18002508a  pop     r13
0x18002508c  pop     r12
0x18002508e  pop     rdi
0x18002508f  pop     rsi
0x180025090  pop     rbp
0x180025091  pop     rbx
0x180025092  retn
```
