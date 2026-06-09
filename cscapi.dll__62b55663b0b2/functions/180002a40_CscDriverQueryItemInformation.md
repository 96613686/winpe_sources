# CscDriverQueryItemInformation

- ea: `0x180002a40`
- end: `0x180002b5c`
- name: `CscDriverQueryItemInformation`
- size: `284`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180002080`
- `0x180002820`
- `0x1800060c0`

## callees

- `0x180002a40`
- `0x1800036b0`
- `0x180009462`
- `0x180009490`

## pseudocode

```c
__int64 __fastcall CscDriverQueryItemInformation(HANDLE FileHandle, __int64 a2, _OWORD *a3)
{
  __int64 v6; // rdx
  __int64 result; // rax
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  int v14; // [rsp+40h] [rbp-C8h] BYREF
  _DWORD v15[2]; // [rsp+48h] [rbp-C0h] BYREF
  _OWORD v16[3]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+80h] [rbp-88h]
  __int128 v18; // [rsp+88h] [rbp-80h]
  __int128 v19; // [rsp+98h] [rbp-70h]
  __int128 v20; // [rsp+A8h] [rbp-60h]
  __int128 v21; // [rsp+B8h] [rbp-50h]
  __int128 v22; // [rsp+C8h] [rbp-40h]

  v14 = 0;
  memset_0(v16, 0, 0x88u);
  if ( !a2 && !a3 )
    return 3221225485LL;
  v15[0] = 8;
  v15[1] = 2;
  result = CscDriverpFsControlEx(FileHandle, v6, &v14, v15, 8u, v16, 0x88u);
  if ( (int)result >= 0 )
  {
    if ( a2 )
    {
      v8 = v16[1];
      *(_OWORD *)a2 = v16[0];
      v9 = v16[2];
      *(_OWORD *)(a2 + 16) = v8;
      *(_QWORD *)&v8 = v17;
      *(_OWORD *)(a2 + 32) = v9;
      *(_QWORD *)(a2 + 48) = v8;
    }
    if ( a3 )
    {
      v10 = v19;
      *a3 = v18;
      v11 = v20;
      a3[1] = v10;
      v12 = v21;
      a3[2] = v11;
      v13 = v22;
      a3[3] = v12;
      a3[4] = v13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002a40  push    rbx
0x180002a42  push    rsi
0x180002a43  push    rdi
0x180002a44  sub     rsp, 0F0h
0x180002a4b  mov     rax, cs:__security_cookie
0x180002a52  xor     rax, rsp
0x180002a55  mov     [rsp+108h+var_28], rax
0x180002a5d  mov     rdi, r8
0x180002a60  mov     [rsp+108h+var_C8], 0
0x180002a68  mov     rbx, rdx
0x180002a6b  mov     rsi, rcx
0x180002a6e  xor     edx, edx; Val
0x180002a70  lea     rcx, [rsp+108h+var_B8]; void *
0x180002a75  mov     r8d, 88h; Size
0x180002a7b  call    memset_0
0x180002a80  test    rbx, rbx
0x180002a83  jnz     short loc_180002A94
0x180002a85  test    rdi, rdi
0x180002a88  jnz     short loc_180002A94
0x180002a8a  mov     eax, 0C000000Dh
0x180002a8f  jmp     loc_180002B41
0x180002a94  lea     rax, [rsp+108h+var_B8]
0x180002a99  mov     [rsp+108h+var_D8], 88h; ULONG
0x180002aa1  mov     [rsp+108h+var_E0], rax; PVOID
0x180002aa6  lea     r9, [rsp+108h+var_C0]
0x180002aab  lea     r8, [rsp+108h+var_C8]
0x180002ab0  mov     [rsp+108h+var_E8], 8; ULONG
0x180002ab8  mov     rcx, rsi; FileHandle
0x180002abb  mov     [rsp+108h+var_C0], 8
0x180002ac3  mov     [rsp+108h+var_BC], 2
0x180002acb  call    CscDriverpFsControlEx
0x180002ad0  test    eax, eax
0x180002ad2  js      short loc_180002B41
0x180002ad4  test    rbx, rbx
0x180002ad7  jz      short loc_180002B01
0x180002ad9  movaps  xmm0, [rsp+108h+var_B8]
0x180002ade  movaps  xmm1, [rsp+108h+var_A8]
0x180002ae3  movups  xmmword ptr [rbx], xmm0
0x180002ae6  movaps  xmm0, [rsp+108h+var_98]
0x180002aeb  movups  xmmword ptr [rbx+10h], xmm1
0x180002aef  movsd   xmm1, [rsp+108h+var_88]
0x180002af8  movups  xmmword ptr [rbx+20h], xmm0
0x180002afc  movsd   qword ptr [rbx+30h], xmm1
0x180002b01  test    rdi, rdi
0x180002b04  jz      short loc_180002B41
0x180002b06  movups  xmm0, [rsp+108h+var_80]
0x180002b0e  movups  xmm1, [rsp+108h+var_70]
0x180002b16  movaps  xmmword ptr [rdi], xmm0
0x180002b19  movups  xmm0, [rsp+108h+var_60]
0x180002b21  movaps  xmmword ptr [rdi+10h], xmm1
0x180002b25  movups  xmm1, [rsp+108h+var_50]
0x180002b2d  movaps  xmmword ptr [rdi+20h], xmm0
0x180002b31  movups  xmm0, [rsp+108h+var_40]
0x180002b39  movaps  xmmword ptr [rdi+30h], xmm1
0x180002b3d  movaps  xmmword ptr [rdi+40h], xmm0
0x180002b41  mov     rcx, [rsp+108h+var_28]
0x180002b49  xor     rcx, rsp; StackCookie
0x180002b4c  call    __security_check_cookie
0x180002b51  add     rsp, 0F0h
0x180002b58  pop     rdi
0x180002b59  pop     rsi
0x180002b5a  pop     rbx
0x180002b5b  retn
```
