# _GetFveAuthInfo

- ea: `0x18000d0a4`
- end: `0x18000d240`
- name: `_GetFveAuthInfo`
- size: `412`
- prototype: `__int64 __fastcall(__int64, __int128 *, int, _QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007e20`
- `0x18000d248`
- `0x18000d66c`

## callees

- `0x180001bb0`
- `0x18000d0a4`

## import_xrefs

- `KERNEL32!HeapSize` at `0x18000d1f1`
- `KERNEL32!HeapSize` at `0x18000d1f1`
- `KERNEL32!HeapFree` at `0x18000d21f`
- `KERNEL32!HeapFree` at `0x18000d21f`
- `KERNEL32!HeapAlloc` at `0x18000d170`
- `KERNEL32!HeapAlloc` at `0x18000d170`
- `KERNEL32!GetProcessHeap` at `0x18000d15f`
- `KERNEL32!GetProcessHeap` at `0x18000d1e3`
- `KERNEL32!GetProcessHeap` at `0x18000d211`
- `KERNEL32!GetProcessHeap` at `0x18000d15f`
- `KERNEL32!GetProcessHeap` at `0x18000d1e3`
- `KERNEL32!GetProcessHeap` at `0x18000d211`
- `FVEAPI!FveGetAuthMethodInformation` at `0x18000d148`
- `FVEAPI!FveGetAuthMethodInformation` at `0x18000d1b5`
- `FVEAPI!FveGetAuthMethodInformation` at `0x18000d148`
- `FVEAPI!FveGetAuthMethodInformation` at `0x18000d1b5`
- `FVEAPI!FveCloseVolume` at `0x18000d1d0`
- `FVEAPI!FveCloseVolume` at `0x18000d1d0`
- `FVEAPI!FveOpenVolumeW` at `0x18000d10c`
- `FVEAPI!FveOpenVolumeW` at `0x18000d10c`

## pseudocode

```c
__int64 __fastcall GetFveAuthInfo(__int64 a1, __int128 *a2, int a3, _QWORD *a4)
{
  int v7; // ebx
  void *v8; // rdi
  __int128 v9; // xmm0
  int AuthMethodInformation; // eax
  SIZE_T v11; // rbx
  HANDLE ProcessHeap; // rax
  _OWORD *v13; // rax
  HANDLE v14; // rax
  SIZE_T v15; // rax
  _BYTE *i; // rcx
  HANDLE v17; // rax
  SIZE_T dwBytes; // [rsp+20h] [rbp-58h] BYREF
  __int64 v20; // [rsp+28h] [rbp-50h] BYREF
  __int128 v21; // [rsp+30h] [rbp-48h] BYREF
  __int128 v22; // [rsp+40h] [rbp-38h]
  _BYTE v23[24]; // [rsp+50h] [rbp-28h] BYREF

  dwBytes = 0;
  v20 = -1;
  v21 = 0;
  v22 = 0;
  memset(v23, 0, sizeof(v23));
  if ( a2 && a4 )
  {
    v8 = 0;
    v7 = FveOpenVolumeW(a1, 0, &v20);
    if ( v7 >= 0 )
    {
      v9 = *a2;
      dwBytes = 56;
      *(_QWORD *)&v21 = 0x100000038LL;
      *(_OWORD *)&v23[8] = v9;
      DWORD2(v21) = a3;
      AuthMethodInformation = FveGetAuthMethodInformation(v20, &v21, 56, &dwBytes);
      v7 = AuthMethodInformation;
      if ( !AuthMethodInformation || AuthMethodInformation == -2147024774 )
      {
        v11 = dwBytes;
        ProcessHeap = GetProcessHeap();
        v13 = HeapAlloc(ProcessHeap, 8u, v11);
        v8 = v13;
        if ( v13 )
        {
          *v13 = v21;
          v13[1] = v22;
          v13[2] = *(_OWORD *)v23;
          *((_QWORD *)v13 + 6) = *(_QWORD *)&v23[16];
          v7 = FveGetAuthMethodInformation(v20, v13, dwBytes, &dwBytes);
          if ( v7 >= 0 )
          {
            *a4 = v8;
            v8 = 0;
          }
        }
        else
        {
          v7 = -2147024882;
        }
      }
    }
    if ( v20 != -1 )
    {
      FveCloseVolume();
      v20 = -1;
    }
    if ( v8 )
    {
      v14 = GetProcessHeap();
      v15 = HeapSize(v14, 0, v8);
      if ( v15 != -1 )
      {
        for ( i = v8; v15; --v15 )
          *i++ = 0;
        v17 = GetProcessHeap();
        HeapFree(v17, 0, v8);
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d0a4  push    rbp
0x18000d0a6  push    rbx
0x18000d0a7  push    rsi
0x18000d0a8  push    rdi
0x18000d0a9  push    r14
0x18000d0ab  push    r15
0x18000d0ad  mov     rbp, rsp
0x18000d0b0  sub     rsp, 78h
0x18000d0b4  mov     rax, cs:__security_cookie
0x18000d0bb  xor     rax, rsp
0x18000d0be  mov     [rbp+var_10], rax
0x18000d0c2  xorps   xmm0, xmm0
0x18000d0c5  mov     [rbp+dwBytes], 0
0x18000d0cd  xor     eax, eax
0x18000d0cf  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFFh
0x18000d0d7  mov     [rbp+var_18], rax
0x18000d0db  mov     rsi, r9
0x18000d0de  mov     r15d, r8d
0x18000d0e1  mov     r14, rdx
0x18000d0e4  movups  [rbp+var_48], xmm0
0x18000d0e8  movups  [rbp+var_38], xmm0
0x18000d0ec  movups  [rbp+var_28], xmm0
0x18000d0f0  test    rdx, rdx
0x18000d0f3  jnz     short loc_18000D0FF
0x18000d0f5  mov     ebx, 80004003h
0x18000d0fa  jmp     loc_18000D225
0x18000d0ff  test    rsi, rsi
0x18000d102  jz      short loc_18000D0F5
0x18000d104  lea     r8, [rbp+var_50]
0x18000d108  xor     edx, edx
0x18000d10a  xor     edi, edi
0x18000d10c  call    cs:__imp_FveOpenVolumeW
0x18000d112  mov     ebx, eax
0x18000d114  test    eax, eax
0x18000d116  js      loc_18000D1C6
0x18000d11c  movups  xmm0, xmmword ptr [r14]
0x18000d120  mov     rcx, [rbp+var_50]
0x18000d124  lea     r8d, [rdi+38h]
0x18000d128  lea     r9, [rbp+dwBytes]
0x18000d12c  mov     [rbp+dwBytes], r8
0x18000d130  lea     rdx, [rbp+var_48]
0x18000d134  mov     dword ptr [rbp+var_48], r8d
0x18000d138  movdqu  [rbp+var_28+8], xmm0
0x18000d13d  mov     dword ptr [rbp+var_48+4], 1
0x18000d144  mov     dword ptr [rbp+var_48+8], r15d
0x18000d148  call    cs:__imp_FveGetAuthMethodInformation
0x18000d14e  mov     ebx, eax
0x18000d150  test    eax, eax
0x18000d152  jz      short loc_18000D15B
0x18000d154  cmp     eax, 8007007Ah
0x18000d159  jnz     short loc_18000D1C6
0x18000d15b  mov     rbx, [rbp+dwBytes]
0x18000d15f  call    cs:__imp_GetProcessHeap
0x18000d165  mov     r8, rbx; dwBytes
0x18000d168  mov     edx, 8; dwFlags
0x18000d16d  mov     rcx, rax; hHeap
0x18000d170  call    cs:__imp_HeapAlloc
0x18000d176  mov     rdi, rax
0x18000d179  test    rax, rax
0x18000d17c  jnz     short loc_18000D185
0x18000d17e  mov     ebx, 8007000Eh
0x18000d183  jmp     short loc_18000D1C6
0x18000d185  movups  xmm0, [rbp+var_48]
0x18000d189  lea     r9, [rbp+dwBytes]
0x18000d18d  mov     rdx, rdi
0x18000d190  movups  xmmword ptr [rax], xmm0
0x18000d193  movups  xmm1, [rbp+var_38]
0x18000d197  movups  xmmword ptr [rax+10h], xmm1
0x18000d19b  movups  xmm0, [rbp+var_28]
0x18000d19f  movups  xmmword ptr [rax+20h], xmm0
0x18000d1a3  movsd   xmm1, [rbp+var_18]
0x18000d1a8  movsd   qword ptr [rax+30h], xmm1
0x18000d1ad  mov     r8, [rbp+dwBytes]
0x18000d1b1  mov     rcx, [rbp+var_50]
0x18000d1b5  call    cs:__imp_FveGetAuthMethodInformation
0x18000d1bb  mov     ebx, eax
0x18000d1bd  test    eax, eax
0x18000d1bf  js      short loc_18000D1C6
0x18000d1c1  mov     [rsi], rdi
0x18000d1c4  xor     edi, edi
0x18000d1c6  mov     rcx, [rbp+var_50]
0x18000d1ca  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000d1ce  jz      short loc_18000D1DE
0x18000d1d0  call    cs:__imp_FveCloseVolume
0x18000d1d6  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFFh
0x18000d1de  test    rdi, rdi
0x18000d1e1  jz      short loc_18000D225
0x18000d1e3  call    cs:__imp_GetProcessHeap
0x18000d1e9  mov     r8, rdi; lpMem
0x18000d1ec  xor     edx, edx; dwFlags
0x18000d1ee  mov     rcx, rax; hHeap
0x18000d1f1  call    cs:__imp_HeapSize
0x18000d1f7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d1fb  jz      short loc_18000D225
0x18000d1fd  mov     rcx, rdi
0x18000d200  test    rax, rax
0x18000d203  jz      short loc_18000D211
0x18000d205  mov     byte ptr [rcx], 0
0x18000d208  inc     rcx
0x18000d20b  sub     rax, 1
0x18000d20f  jnz     short loc_18000D205
0x18000d211  call    cs:__imp_GetProcessHeap
0x18000d217  mov     r8, rdi; lpMem
0x18000d21a  xor     edx, edx; dwFlags
0x18000d21c  mov     rcx, rax; hHeap
0x18000d21f  call    cs:__imp_HeapFree
0x18000d225  mov     eax, ebx
0x18000d227  mov     rcx, [rbp+var_10]
0x18000d22b  xor     rcx, rsp; StackCookie
0x18000d22e  call    __security_check_cookie
0x18000d233  add     rsp, 78h
0x18000d237  pop     r15
0x18000d239  pop     r14
0x18000d23b  pop     rdi
0x18000d23c  pop     rsi
0x18000d23d  pop     rbx
0x18000d23e  pop     rbp
0x18000d23f  retn
```
