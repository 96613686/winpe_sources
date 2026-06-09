# DecompressFrame16To565C

- ea: `0x1800055f0`
- end: `0x1800056db`
- name: `DecompressFrame16To565C`
- size: `235`
- prototype: `__int64 __fastcall(_DWORD *, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003b18`
- `0x1800055f0`
- `0x180005d98`

## pseudocode

```c
__int64 __fastcall DecompressFrame16To565C(_DWORD *a1, int a2, int a3, int a4, int a5, int a6)
{
  unsigned int v6; // r15d
  unsigned int v7; // r12d
  signed int v9; // r15d
  signed int v10; // r12d
  int v11; // ebp
  int v12; // ebx
  int v13; // r14d
  int v14; // esi
  int v15; // edi
  int v16; // eax
  int v18; // [rsp+30h] [rbp-48h] BYREF
  int v19; // [rsp+80h] [rbp+8h] BYREF
  int v20; // [rsp+88h] [rbp+10h] BYREF

  v6 = a1[1];
  v7 = a1[2];
  v18 = a1[5];
  v20 = 0;
  v19 = 0;
  v9 = v6 >> 2;
  v10 = v7 >> 2;
  v11 = 0;
  v12 = DibXY(a3, a4, a5, a6, (__int64)&v19);
  if ( v10 )
  {
    v13 = v19;
    do
    {
      v14 = 0;
      v15 = v12;
      if ( v9 )
      {
        do
        {
          v16 = DecompressCBlock16To565(v15, a2, (unsigned int)&v18, v13, (__int64)&v20);
          ++v14;
          v15 += 8;
          a2 = v16;
        }
        while ( v14 < v9 );
      }
      ++v11;
      v12 += 4 * v13;
    }
    while ( v11 < v10 );
  }
  return 0;
}

```

## disassembly

```asm
0x1800055f0  mov     [rsp+arg_10], rbx
0x1800055f5  push    rbp
0x1800055f6  push    rsi
0x1800055f7  push    rdi
0x1800055f8  push    r12
0x1800055fa  push    r13
0x1800055fc  push    r14
0x1800055fe  push    r15
0x180005600  sub     rsp, 40h
0x180005604  mov     eax, [rcx+14h]
0x180005607  mov     r11, r8
0x18000560a  mov     r15d, [rcx+4]
0x18000560e  mov     r10, r9
0x180005611  mov     r12d, [rcx+8]
0x180005615  mov     r13, rdx
0x180005618  mov     r8d, [rsp+78h+arg_20]
0x180005620  mov     rdx, r10
0x180005623  mov     r9d, [rsp+78h+arg_28]
0x18000562b  mov     rcx, r11
0x18000562e  mov     [rsp+78h+var_48], eax
0x180005632  lea     rax, [rsp+78h+arg_0]
0x18000563a  mov     [rsp+78h+var_58], rax
0x18000563f  mov     [rsp+78h+arg_8], 0
0x18000564a  mov     [rsp+78h+arg_0], 0
0x180005655  shr     r15d, 2
0x180005659  shr     r12d, 2
0x18000565d  call    DibXY
0x180005662  xor     ebp, ebp
0x180005664  mov     rbx, rax
0x180005667  test    r12d, r12d
0x18000566a  jz      short loc_1800056C1
0x18000566c  mov     r14d, [rsp+78h+arg_0]
0x180005674  xor     esi, esi
0x180005676  mov     rdi, rbx
0x180005679  test    r15d, r15d
0x18000567c  jz      short loc_1800056AC
0x18000567e  lea     rax, [rsp+78h+arg_8]
0x180005686  mov     r9d, r14d
0x180005689  lea     r8, [rsp+78h+var_48]
0x18000568e  mov     [rsp+78h+var_58], rax
0x180005693  mov     rdx, r13
0x180005696  mov     rcx, rdi
0x180005699  call    DecompressCBlock16To565
0x18000569e  inc     esi
0x1800056a0  add     rdi, 8
0x1800056a4  mov     r13, rax
0x1800056a7  cmp     esi, r15d
0x1800056aa  jl      short loc_18000567E
0x1800056ac  lea     eax, ds:0[r14*4]
0x1800056b4  inc     ebp
0x1800056b6  movsxd  rcx, eax
0x1800056b9  add     rbx, rcx
0x1800056bc  cmp     ebp, r12d
0x1800056bf  jl      short loc_180005674
0x1800056c1  mov     rbx, [rsp+78h+arg_10]
0x1800056c9  xor     eax, eax
0x1800056cb  add     rsp, 40h
0x1800056cf  pop     r15
0x1800056d1  pop     r14
0x1800056d3  pop     r13
0x1800056d5  pop     r12
0x1800056d7  pop     rdi
0x1800056d8  pop     rsi
0x1800056d9  pop     rbp
0x1800056da  retn
```
