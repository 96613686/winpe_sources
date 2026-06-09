# ReadRawBits

- ea: `0x18000bdb0`
- end: `0x18000beb8`
- name: `ReadRawBits`
- size: `264`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009650`
- `0x18000b0e0`

## callees

- `0x18000bdb0`

## pseudocode

```c
__int64 __fastcall ReadRawBits(int *a1, unsigned int a2)
{
  unsigned int v2; // r11d
  char v3; // r8
  int v4; // r9d
  int v6; // r10d
  int v7; // r9d
  unsigned __int64 v8; // rcx
  unsigned __int16 *v9; // rbx
  unsigned __int64 v10; // rcx
  int v12; // edx
  unsigned int v13; // r11d
  unsigned __int64 v14; // r10
  unsigned __int16 *v15; // rdi
  int v16; // ebp
  unsigned __int16 *v17; // rsi
  unsigned int v18; // ebp
  unsigned int v19; // ebp
  int v20; // r8d
  int v21; // edx

  v2 = a1[2];
  v3 = a2;
  v4 = *a1;
  if ( a2 > 0x10 )
  {
    v14 = *((_QWORD *)a1 + 4);
    v15 = (unsigned __int16 *)*((_QWORD *)a1 + 2);
    a1[2] = v2 << 16;
    *a1 = v4 - 16;
    if ( (unsigned __int64)v15 >= v14 )
    {
      v16 = *v15;
      v17 = v15 - 1;
      *((_QWORD *)a1 + 2) = v15 - 1;
      v18 = (v2 << 16) + (v16 << (16 - v4));
      v13 = (v18 >> (32 - (a2 - 16))) + (HIWORD(v2) << (a2 - 16));
      v19 = v18 << (a2 - 16);
      a1[2] = v19;
      v20 = v4 - (a2 - 16);
      *a1 = v20;
      if ( v20 >= 0 )
        return v13;
      if ( (unsigned __int64)v17 >= v14 )
      {
        v21 = *v17 << (a2 - 16 - v4);
        *((_QWORD *)a1 + 2) = v15 - 2;
        a1[2] = v19 + v21;
        *a1 = v20 + 16;
        return v13;
      }
    }
    v10 = v14 - 4;
    goto LABEL_5;
  }
  v6 = v2 << a2;
  v7 = v4 - a2;
  a1[2] = v2 << a2;
  *a1 = v7;
  if ( v7 < 0 )
  {
    v8 = *((_QWORD *)a1 + 4);
    v9 = (unsigned __int16 *)*((_QWORD *)a1 + 2);
    if ( (unsigned __int64)v9 < v8 )
    {
      v10 = v8 - 4;
LABEL_5:
      *((_QWORD *)a1 + 2) = v10;
      return 0;
    }
    v12 = *v9 << -(char)v7;
    *((_QWORD *)a1 + 2) = v9 - 1;
    a1[2] = v6 + v12;
    *a1 = v7 + 16;
  }
  return v2 >> (32 - v3);
}

```

## disassembly

```asm
0x18000bdb0  push    rbx
0x18000bdb2  push    rbp
0x18000bdb3  push    rsi
0x18000bdb4  push    rdi
0x18000bdb5  mov     r11d, [rcx+8]
0x18000bdb9  mov     r8d, edx
0x18000bdbc  mov     r9d, [rcx]
0x18000bdbf  mov     rax, rcx
0x18000bdc2  cmp     edx, 10h
0x18000bdc5  ja      short loc_18000BE28
0x18000bdc7  mov     ecx, edx
0x18000bdc9  mov     r10d, r11d
0x18000bdcc  shl     r10d, cl
0x18000bdcf  sub     r9d, edx
0x18000bdd2  mov     [rax+8], r10d
0x18000bdd6  mov     [rax], r9d
0x18000bdd9  jns     short loc_18000BE15
0x18000bddb  mov     rcx, [rax+20h]
0x18000bddf  mov     rbx, [rax+10h]
0x18000bde3  cmp     rbx, rcx
0x18000bde6  jnb     short loc_18000BDF7
0x18000bde8  add     rcx, 0FFFFFFFFFFFFFFFCh
0x18000bdec  mov     [rax+10h], rcx
0x18000bdf0  xor     eax, eax
0x18000bdf2  pop     rdi
0x18000bdf3  pop     rsi
0x18000bdf4  pop     rbp
0x18000bdf5  pop     rbx
0x18000bdf6  retn
0x18000bdf7  movzx   edx, word ptr [rbx]
0x18000bdfa  mov     ecx, r9d
0x18000bdfd  neg     ecx
0x18000bdff  shl     edx, cl
0x18000be01  lea     rcx, [rbx-2]
0x18000be05  mov     [rax+10h], rcx
0x18000be09  add     edx, r10d
0x18000be0c  lea     ecx, [r9+10h]
0x18000be10  mov     [rax+8], edx
0x18000be13  mov     [rax], ecx
0x18000be15  mov     ecx, 20h ; ' '
0x18000be1a  sub     ecx, r8d
0x18000be1d  shr     r11d, cl
0x18000be20  mov     eax, r11d
0x18000be23  pop     rdi
0x18000be24  pop     rsi
0x18000be25  pop     rbp
0x18000be26  pop     rbx
0x18000be27  retn
0x18000be28  mov     r10, [rax+20h]
0x18000be2c  mov     ebx, r11d
0x18000be2f  mov     rdi, [rax+10h]
0x18000be33  shl     ebx, 10h
0x18000be36  mov     [rcx+8], ebx
0x18000be39  lea     ecx, [r9-10h]
0x18000be3d  mov     [rax], ecx
0x18000be3f  cmp     rdi, r10
0x18000be42  jb      short loc_18000BEAF
0x18000be44  movzx   ebp, word ptr [rdi]
0x18000be47  lea     rsi, [rdi-2]
0x18000be4b  shr     r11d, 10h
0x18000be4f  mov     ecx, 10h
0x18000be54  sub     ecx, r9d
0x18000be57  mov     [rax+10h], rsi
0x18000be5b  shl     ebp, cl
0x18000be5d  mov     ecx, 20h ; ' '
0x18000be62  add     ebp, ebx
0x18000be64  lea     ebx, [rdx-10h]
0x18000be67  sub     ecx, ebx
0x18000be69  mov     r8d, ebp
0x18000be6c  shr     r8d, cl
0x18000be6f  mov     ecx, ebx
0x18000be71  shl     r11d, cl
0x18000be74  add     r11d, r8d
0x18000be77  shl     ebp, cl
0x18000be79  mov     r8d, r9d
0x18000be7c  mov     [rax+8], ebp
0x18000be7f  sub     r8d, ebx
0x18000be82  mov     [rax], r8d
0x18000be85  jns     short loc_18000BE20
0x18000be87  cmp     rsi, r10
0x18000be8a  jb      short loc_18000BEAF
0x18000be8c  movzx   edx, word ptr [rsi]
0x18000be8f  sub     ebx, r9d
0x18000be92  movzx   ecx, bl
0x18000be95  shl     edx, cl
0x18000be97  lea     rcx, [rdi-4]
0x18000be9b  mov     [rax+10h], rcx
0x18000be9f  add     edx, ebp
0x18000bea1  lea     ecx, [r8+10h]
0x18000bea5  mov     [rax+8], edx
0x18000bea8  mov     [rax], ecx
0x18000beaa  jmp     loc_18000BE20
0x18000beaf  lea     rcx, [r10-4]
0x18000beb3  jmp     loc_18000BDEC
```
