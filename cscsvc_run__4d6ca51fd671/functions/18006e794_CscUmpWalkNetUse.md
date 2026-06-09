# CscUmpWalkNetUse

- ea: `0x18006e794`
- end: `0x18006ea04`
- name: `CscUmpWalkNetUse`
- size: `624`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18006dbdc`
- `0x18006dd24`

## callees

- `0x180036394`
- `0x180039fb4`
- `0x18003e928`
- `0x180047d2c`
- `0x18006d0f4`
- `0x18006e794`
- `0x180089010`

## import_xrefs

- `MPR!WNetEnumResourceW` at `0x18006e87e`
- `MPR!WNetEnumResourceW` at `0x18006e87e`
- `MPR!WNetOpenEnumW` at `0x18006e7e2`
- `MPR!WNetOpenEnumW` at `0x18006e7e2`
- `MPR!WNetCloseEnum` at `0x18006e9b0`
- `MPR!WNetCloseEnum` at `0x18006e9b0`

## pseudocode

```c
__int64 __fastcall CscUmpWalkNetUse(__int64 a1, __int64 (__fastcall *a2)(__int64, __int128 *, char *))
{
  DWORD v4; // eax
  int v5; // ebx
  CObjectMonitor *v6; // rcx
  int v7; // edi
  void *v8; // rsi
  DWORD v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  DWORD v13; // edi
  DWORD i; // r14d
  __int64 v15; // rax
  __int64 v16; // r9
  DWORD cCount; // [rsp+30h] [rbp-20h] BYREF
  HANDLE hEnum; // [rsp+38h] [rbp-18h] BYREF
  __int128 v20; // [rsp+40h] [rbp-10h] BYREF
  char v21; // [rsp+A0h] [rbp+50h] BYREF
  size_t Size; // [rsp+A8h] [rbp+58h] BYREF

  v21 = 1;
  LODWORD(Size) = 4096;
  hEnum = 0;
  cCount = 0;
  v20 = 0;
  v4 = WNetOpenEnumW(1u, 0, 0, 0, &hEnum);
  if ( v4 )
  {
    v5 = -1073741823;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 17), 13, WPP_ce165737b0b032d8c1fd7d39d565dd7e_Traceguids, v4);
      v6 = WPP_GLOBAL_Control;
    }
    v7 = 518;
  }
  else
  {
    v8 = (void *)CscUmpAllocate((unsigned int)Size);
    if ( v8 )
    {
      v5 = 0;
      do
      {
        memset_0(v8, 0, (unsigned int)Size);
        cCount = -1;
        v9 = WNetEnumResourceW(hEnum, &cCount, v8, (LPDWORD)&Size);
        v13 = v9;
        if ( v9 )
        {
          if ( v9 != 234 )
            break;
          CscUmpFree(v8, v10, v11, v12);
          v8 = (void *)CscUmpAllocate((unsigned int)Size);
          if ( !v8 )
          {
            v5 = -1073741670;
            v7 = 569;
            goto LABEL_33;
          }
          v13 = 0;
        }
        else
        {
          for ( i = 0; i < cCount; ++i )
          {
            v15 = -1;
            do
              ++v15;
            while ( *(_WORD *)(*((_QWORD *)v8 + 6 * i + 3) + 2 * v15) );
            LOWORD(v20) = 2 * v15;
            WORD1(v20) = 2 * v15;
            *((_QWORD *)&v20 + 1) = *((_QWORD *)v8 + 6 * i + 3);
            v5 = a2(a1, &v20, &v21);
            if ( v5 < 0 || !v21 )
            {
              v21 = 0;
              goto LABEL_21;
            }
          }
        }
      }
      while ( v21 );
LABEL_21:
      v16 = 0;
      if ( v13 != 259 )
        v16 = v13;
      if ( (_DWORD)v16 && v5 >= 0 )
      {
        v5 = -1073741823;
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 148) & 2) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 17), 14, WPP_ce165737b0b032d8c1fd7d39d565dd7e_Traceguids, v16);
        }
        v7 = 585;
      }
      else
      {
        v7 = 0;
      }
      CscUmpFree(v8, v10, v11, v16);
    }
    else
    {
      v5 = -1073741670;
      v7 = 526;
    }
LABEL_33:
    v6 = WPP_GLOBAL_Control;
  }
  if ( hEnum )
  {
    WNetCloseEnum(hEnum);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v6 + 148) & 2) != 0 )
    WPP_SF_dd(*((_QWORD *)v6 + 17), 15, WPP_ce165737b0b032d8c1fd7d39d565dd7e_Traceguids, (unsigned int)v5, v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006e794  mov     [rsp-38h+arg_0], rbx
0x18006e799  push    rbp
0x18006e79a  push    rsi
0x18006e79b  push    rdi
0x18006e79c  push    r12
0x18006e79e  push    r13
0x18006e7a0  push    r14
0x18006e7a2  push    r15
0x18006e7a4  mov     rbp, rsp
0x18006e7a7  sub     rsp, 50h
0x18006e7ab  mov     r15, rdx
0x18006e7ae  mov     [rbp+arg_10], 1
0x18006e7b2  xor     edx, edx; dwType
0x18006e7b4  mov     dword ptr [rbp+Size], 1000h
0x18006e7bb  mov     r12, rcx
0x18006e7be  lea     rax, [rbp+hEnum]
0x18006e7c2  xor     r13d, r13d
0x18006e7c5  mov     [rsp+50h+lphEnum], rax; lphEnum
0x18006e7ca  xorps   xmm0, xmm0
0x18006e7cd  mov     [rbp+hEnum], r13
0x18006e7d1  lea     ecx, [rdx+1]; dwScope
0x18006e7d4  mov     [rbp+cCount], r13d
0x18006e7d8  xor     r9d, r9d; lpNetResource
0x18006e7db  xor     r8d, r8d; dwUsage
0x18006e7de  movups  [rbp+var_10], xmm0
0x18006e7e2  call    cs:__imp_WNetOpenEnumW
0x18006e7e8  lea     r14, WPP_GLOBAL_Control
0x18006e7ef  test    eax, eax
0x18006e7f1  jz      short loc_18006E838
0x18006e7f3  mov     ebx, 0C0000001h
0x18006e7f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e7ff  cmp     rcx, r14
0x18006e802  jz      short loc_18006E82E
0x18006e804  test    byte ptr [rcx+94h], 2
0x18006e80b  jz      short loc_18006E82E
0x18006e80d  mov     rcx, [rcx+88h]
0x18006e814  lea     edx, [r13+0Dh]
0x18006e818  mov     r9d, eax
0x18006e81b  lea     r8, WPP_ce165737b0b032d8c1fd7d39d565dd7e_Traceguids
0x18006e822  call    WPP_SF_d
0x18006e827  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e82e  mov     edi, 206h
0x18006e833  jmp     loc_18006E9A4
0x18006e838  mov     ecx, dword ptr [rbp+Size]
0x18006e83b  call    CscUmpAllocate
0x18006e840  mov     rsi, rax
0x18006e843  test    rax, rax
0x18006e846  jnz     short loc_18006E857
0x18006e848  mov     ebx, 0C000009Ah
0x18006e84d  mov     edi, 20Eh
0x18006e852  jmp     loc_18006E99D
0x18006e857  mov     ebx, r13d
0x18006e85a  mov     r8d, dword ptr [rbp+Size]; Size
0x18006e85e  xor     edx, edx; Val
0x18006e860  mov     rcx, rsi; void *
0x18006e863  call    memset_0
0x18006e868  mov     rcx, [rbp+hEnum]; hEnum
0x18006e86c  lea     r9, [rbp+Size]; lpBufferSize
0x18006e870  mov     r8, rsi; lpBuffer
0x18006e873  mov     [rbp+cCount], 0FFFFFFFFh
0x18006e87a  lea     rdx, [rbp+cCount]; lpcCount
0x18006e87e  call    cs:__imp_WNetEnumResourceW
0x18006e884  mov     edi, eax
0x18006e886  test    eax, eax
0x18006e888  jnz     short loc_18006E8F0
0x18006e88a  mov     r14d, r13d
0x18006e88d  cmp     r14d, [rbp+cCount]
0x18006e891  jnb     short loc_18006E912
0x18006e893  mov     ecx, r14d
0x18006e896  lea     rdx, [rcx+rcx*2]
0x18006e89a  add     rdx, rdx
0x18006e89d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006e8a1  mov     rcx, [rsi+rdx*8+18h]
0x18006e8a6  inc     rax
0x18006e8a9  cmp     [rcx+rax*2], r13w
0x18006e8ae  jnz     short loc_18006E8A6
0x18006e8b0  add     ax, ax
0x18006e8b3  lea     r8, [rbp+arg_10]
0x18006e8b7  mov     word ptr [rbp+var_10], ax
0x18006e8bb  mov     rcx, r12
0x18006e8be  mov     word ptr [rbp+var_10+2], ax
0x18006e8c2  mov     rax, [rsi+rdx*8+18h]
0x18006e8c7  lea     rdx, [rbp+var_10]
0x18006e8cb  mov     qword ptr [rbp+var_10+8], rax
0x18006e8cf  mov     rax, r15
0x18006e8d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e8d7  mov     ebx, eax
0x18006e8d9  test    eax, eax
0x18006e8db  js      loc_18006E972
0x18006e8e1  cmp     [rbp+arg_10], r13b
0x18006e8e5  jz      loc_18006E972
0x18006e8eb  inc     r14d
0x18006e8ee  jmp     short loc_18006E88D
0x18006e8f0  cmp     eax, 0EAh
0x18006e8f5  jnz     short loc_18006E91C
0x18006e8f7  mov     rcx, rsi
0x18006e8fa  call    CscUmpFree
0x18006e8ff  mov     ecx, dword ptr [rbp+Size]
0x18006e902  call    CscUmpAllocate
0x18006e907  mov     rsi, rax
0x18006e90a  test    rax, rax
0x18006e90d  jz      short loc_18006E978
0x18006e90f  mov     edi, r13d
0x18006e912  cmp     [rbp+arg_10], r13b
0x18006e916  jnz     loc_18006E85A
0x18006e91c  cmp     edi, 103h
0x18006e922  mov     r9d, r13d
0x18006e925  cmovnz  r9d, edi
0x18006e929  test    r9d, r9d
0x18006e92c  jz      short loc_18006E98B
0x18006e92e  test    ebx, ebx
0x18006e930  js      short loc_18006E98B
0x18006e932  mov     ebx, 0C0000001h
0x18006e937  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e93e  lea     r14, WPP_GLOBAL_Control
0x18006e945  cmp     rcx, r14
0x18006e948  jz      short loc_18006E96B
0x18006e94a  test    byte ptr [rcx+94h], 2
0x18006e951  jz      short loc_18006E96B
0x18006e953  mov     rcx, [rcx+88h]
0x18006e95a  lea     r8, WPP_ce165737b0b032d8c1fd7d39d565dd7e_Traceguids
0x18006e961  mov     edx, 0Eh
0x18006e966  call    WPP_SF_d
0x18006e96b  mov     edi, 249h
0x18006e970  jmp     short loc_18006E995
0x18006e972  mov     [rbp+arg_10], r13b
0x18006e976  jmp     short loc_18006E91C
0x18006e978  mov     ebx, 0C000009Ah
0x18006e97d  lea     r14, WPP_GLOBAL_Control
0x18006e984  mov     edi, 239h
0x18006e989  jmp     short loc_18006E99D
0x18006e98b  mov     edi, r13d
0x18006e98e  lea     r14, WPP_GLOBAL_Control
0x18006e995  mov     rcx, rsi
0x18006e998  call    CscUmpFree
0x18006e99d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e9a4  mov     rax, [rbp+hEnum]
0x18006e9a8  test    rax, rax
0x18006e9ab  jz      short loc_18006E9BD
0x18006e9ad  mov     rcx, rax; hEnum
0x18006e9b0  call    cs:__imp_WNetCloseEnum
0x18006e9b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e9bd  cmp     rcx, r14
0x18006e9c0  jz      short loc_18006E9EA
0x18006e9c2  test    byte ptr [rcx+94h], 2
0x18006e9c9  jz      short loc_18006E9EA
0x18006e9cb  mov     rcx, [rcx+88h]
0x18006e9d2  lea     r8, WPP_ce165737b0b032d8c1fd7d39d565dd7e_Traceguids
0x18006e9d9  mov     edx, 0Fh
0x18006e9de  mov     dword ptr [rsp+50h+lphEnum], edi
0x18006e9e2  mov     r9d, ebx
0x18006e9e5  call    WPP_SF_dd
0x18006e9ea  mov     eax, ebx
0x18006e9ec  mov     rbx, [rsp+50h+arg_0]
0x18006e9f4  add     rsp, 50h
0x18006e9f8  pop     r15
0x18006e9fa  pop     r14
0x18006e9fc  pop     r13
0x18006e9fe  pop     r12
0x18006ea00  pop     rdi
0x18006ea01  pop     rsi
0x18006ea02  pop     rbp
0x18006ea03  retn
```
