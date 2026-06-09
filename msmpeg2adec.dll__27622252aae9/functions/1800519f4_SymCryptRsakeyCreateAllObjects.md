# SymCryptRsakeyCreateAllObjects

- ea: `0x1800519f4`
- end: `0x180051b5f`
- name: `SymCryptRsakeyCreateAllObjects`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180051c08`

## callees

- `0x1800519f4`
- `0x1800553b8`
- `0x18005796c`

## pseudocode

```c
__int64 __fastcall SymCryptRsakeyCreateAllObjects(_DWORD *a1)
{
  __int64 v1; // rdi
  int v3; // r8d
  unsigned int v4; // eax
  unsigned int v5; // eax
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // rcx
  unsigned int v9; // eax
  __int64 i; // rdi
  int v11; // r8d
  unsigned int v12; // eax
  __int64 result; // rax
  __int64 j; // r11
  int v15; // r8d
  unsigned int v16; // eax
  _DWORD *v17; // rax
  __int64 v18; // r11

  v1 = 0;
  if ( a1[7] )
  {
    do
    {
      v3 = a1[v1 + 10];
      if ( (unsigned int)(v3 - 1) > 0x7FF )
        v4 = 0;
      else
        v4 = 192 * v3 + 128;
      *(_QWORD *)&a1[2 * v1 + 32] = SymCryptFdefModulusCreate(*(_QWORD *)&a1[2 * v1 + 16], v4);
      v1 = (unsigned int)(v1 + 1);
      v5 = a1[7];
    }
    while ( (unsigned int)v1 < v5 );
    v6 = 0;
    if ( v5 )
    {
      do
      {
        v7 = *(_QWORD *)&a1[2 * v6 + 20];
        v8 = (unsigned int)((*(_DWORD *)(*(_QWORD *)&a1[2 * v6 + 32] + 4LL) << 6) - 64);
        *(_QWORD *)(v8 + v7) = 0;
        *(_QWORD *)(v8 + v7 + 8) = 0;
        *(_QWORD *)(v8 + v7 + 16) = 0;
        *(_QWORD *)(v8 + v7 + 24) = 0;
        *(_QWORD *)(v8 + v7 + 32) = 0;
        *(_QWORD *)(v8 + v7 + 40) = 0;
        *(_QWORD *)(v8 + v7 + 48) = 0;
        *(_QWORD *)(v8 + v7 + 56) = 0;
        *(_QWORD *)&a1[2 * v6 + 36] = v7;
        v6 = (unsigned int)(v6 + 1);
      }
      while ( (unsigned int)v6 < a1[7] );
    }
  }
  v9 = a1[6];
  for ( i = 0; (unsigned int)i < v9; v9 = a1[6] )
  {
    v11 = a1[5];
    if ( (unsigned int)(v11 - 1) > 0x7FF )
      v12 = 0;
    else
      v12 = (v11 << 6) + 32;
    *(_QWORD *)&a1[2 * i + 40] = SymCryptIntCreate(*(_DWORD **)&a1[2 * i + 24], v12, v11);
    i = (unsigned int)(i + 1);
  }
  result = a1[7] * v9;
  for ( j = 0; (unsigned int)j < (unsigned int)result; result = (unsigned int)(a1[6] * a1[7]) )
  {
    v15 = a1[j + 10];
    if ( (unsigned int)(v15 - 1) > 0x7FF )
      v16 = 0;
    else
      v16 = (v15 << 6) + 32;
    v17 = SymCryptIntCreate(*(_DWORD **)&a1[2 * j + 26], v16, v15);
    *(_QWORD *)&a1[2 * v18 + 42] = v17;
    j = (unsigned int)(v18 + 1);
  }
  return result;
}

```

## disassembly

```asm
0x1800519f4  mov     [rsp+arg_0], rbx
0x1800519f9  mov     [rsp+arg_8], rsi
0x1800519fe  push    rdi
0x1800519ff  sub     rsp, 20h
0x180051a03  xor     edi, edi
0x180051a05  mov     rbx, rcx
0x180051a08  cmp     [rcx+1Ch], edi
0x180051a0b  jbe     loc_180051AC1
0x180051a11  mov     r8d, [rbx+rdi*4+28h]
0x180051a16  lea     eax, [r8-1]
0x180051a1a  cmp     eax, 7FFh
0x180051a1f  ja      short loc_180051A2D
0x180051a21  lea     eax, [r8+r8*2]
0x180051a25  shl     eax, 6
0x180051a28  sub     eax, 0FFFFFF80h
0x180051a2b  jmp     short loc_180051A2F
0x180051a2d  xor     eax, eax
0x180051a2f  mov     rcx, [rbx+rdi*8+40h]
0x180051a34  mov     edx, eax
0x180051a36  call    SymCryptFdefModulusCreate
0x180051a3b  mov     [rbx+rdi*8+80h], rax
0x180051a43  inc     edi
0x180051a45  mov     eax, [rbx+1Ch]
0x180051a48  cmp     edi, eax
0x180051a4a  jb      short loc_180051A11
0x180051a4c  xor     r9d, r9d
0x180051a4f  test    eax, eax
0x180051a51  jz      short loc_180051AC1
0x180051a53  mov     rax, [rbx+r9*8+80h]
0x180051a5b  mov     rdx, [rbx+r9*8+50h]
0x180051a60  mov     ecx, [rax+4]
0x180051a63  shl     ecx, 6
0x180051a66  sub     ecx, 40h ; '@'
0x180051a69  mov     qword ptr [rcx+rdx], 0
0x180051a71  mov     qword ptr [rcx+rdx+8], 0
0x180051a7a  mov     qword ptr [rcx+rdx+10h], 0
0x180051a83  mov     qword ptr [rcx+rdx+18h], 0
0x180051a8c  mov     qword ptr [rcx+rdx+20h], 0
0x180051a95  mov     qword ptr [rcx+rdx+28h], 0
0x180051a9e  mov     qword ptr [rcx+rdx+30h], 0
0x180051aa7  mov     qword ptr [rcx+rdx+38h], 0
0x180051ab0  mov     [rbx+r9*8+90h], rdx
0x180051ab8  inc     r9d
0x180051abb  cmp     r9d, [rbx+1Ch]
0x180051abf  jb      short loc_180051A53
0x180051ac1  mov     eax, [rbx+18h]
0x180051ac4  xor     edi, edi
0x180051ac6  test    eax, eax
0x180051ac8  jz      short loc_180051B03
0x180051aca  mov     r8d, [rbx+14h]
0x180051ace  lea     eax, [r8-1]
0x180051ad2  cmp     eax, 7FFh
0x180051ad7  ja      short loc_180051AE4
0x180051ad9  mov     eax, r8d
0x180051adc  shl     eax, 6
0x180051adf  add     eax, 20h ; ' '
0x180051ae2  jmp     short loc_180051AE6
0x180051ae4  xor     eax, eax
0x180051ae6  mov     rcx, [rbx+rdi*8+60h]
0x180051aeb  mov     edx, eax
0x180051aed  call    SymCryptIntCreate
0x180051af2  mov     [rbx+rdi*8+0A0h], rax
0x180051afa  inc     edi
0x180051afc  mov     eax, [rbx+18h]
0x180051aff  cmp     edi, eax
0x180051b01  jb      short loc_180051ACA
0x180051b03  imul    eax, [rbx+1Ch]
0x180051b07  xor     r11d, r11d
0x180051b0a  test    eax, eax
0x180051b0c  jz      short loc_180051B4E
0x180051b0e  mov     r8d, [rbx+r11*4+28h]
0x180051b13  lea     eax, [r8-1]
0x180051b17  cmp     eax, 7FFh
0x180051b1c  ja      short loc_180051B29
0x180051b1e  mov     eax, r8d
0x180051b21  shl     eax, 6
0x180051b24  add     eax, 20h ; ' '
0x180051b27  jmp     short loc_180051B2B
0x180051b29  xor     eax, eax
0x180051b2b  mov     rcx, [rbx+r11*8+68h]
0x180051b30  mov     edx, eax
0x180051b32  call    SymCryptIntCreate
0x180051b37  mov     [rbx+r11*8+0A8h], rax
0x180051b3f  inc     r11d
0x180051b42  mov     eax, [rbx+1Ch]
0x180051b45  imul    eax, [rbx+18h]
0x180051b49  cmp     r11d, eax
0x180051b4c  jb      short loc_180051B0E
0x180051b4e  mov     rbx, [rsp+28h+arg_0]
0x180051b53  mov     rsi, [rsp+28h+arg_8]
0x180051b58  add     rsp, 20h
0x180051b5c  pop     rdi
0x180051b5d  retn
```
