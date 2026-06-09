# GenerateSlotTables

- ea: `0x180003e30`
- end: `0x180003f21`
- name: `GenerateSlotTables`
- size: `241`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003df0`

## callees

- `0x180003e30`
- `0x180006ad5`

## pseudocode

```c
void *GenerateSlotTables()
{
  int v0; // edi
  __int64 v1; // rbx
  int v2; // ebp
  int v3; // esi
  __int64 v4; // rax
  int v5; // edi
  __int64 v6; // rbx
  int v7; // ebp
  int v8; // esi
  int v9; // edi
  void *result; // rax
  int v11; // esi
  int v12; // ebp

  v0 = 0;
  v1 = 0;
  do
  {
    v2 = 1 << *((_BYTE *)&g_ExtraLengthBits + v1);
    v3 = 0;
    if ( v2 > 0 )
    {
      memset_0((char *)g_LengthLookup + v0, (unsigned __int8)v1, v2);
      do
      {
        ++v0;
        ++v3;
      }
      while ( v3 < v2 );
    }
    v1 = (unsigned int)(v1 + 1);
  }
  while ( (int)v1 < 28 );
  v4 = v0;
  v5 = 0;
  *((_BYTE *)g_LengthLookup + v4 - 1) = v1;
  v6 = 0;
  do
  {
    v7 = 1 << g_ExtraDistanceBits[v6];
    v8 = 0;
    if ( v7 > 0 )
    {
      memset_0((char *)g_DistLookup + v5, (unsigned __int8)v6, v7);
      do
      {
        ++v5;
        ++v8;
      }
      while ( v8 < v7 );
    }
    v6 = (unsigned int)(v6 + 1);
  }
  while ( (int)v6 < 16 );
  v9 = v5 >> 7;
  do
  {
    result = (void *)(int)v6;
    v11 = 0;
    v12 = 1 << (g_ExtraDistanceBits[(int)v6] - 7);
    if ( v12 > 0 )
    {
      result = memset_0((char *)qword_18000AC20 + v9, (unsigned __int8)v6, v12);
      do
      {
        ++v9;
        ++v11;
      }
      while ( v11 < v12 );
    }
    LODWORD(v6) = v6 + 1;
  }
  while ( (int)v6 < 30 );
  return result;
}

```

## disassembly

```asm
0x180003e30  push    rbx
0x180003e32  push    rbp
0x180003e33  push    rsi
0x180003e34  push    rdi
0x180003e35  push    r14
0x180003e37  push    r15
0x180003e39  sub     rsp, 28h
0x180003e3d  xor     edi, edi
0x180003e3f  lea     r15, cs:180000000h
0x180003e46  xor     ebx, ebx
0x180003e48  lea     r14, g_LengthLookup
0x180003e4f  movzx   ecx, byte ptr [rbx+r15+7940h]
0x180003e58  mov     ebp, 1
0x180003e5d  shl     ebp, cl
0x180003e5f  xor     esi, esi
0x180003e61  test    ebp, ebp
0x180003e63  jle     short loc_180003E7E
0x180003e65  movsxd  rcx, edi
0x180003e68  movzx   edx, bl; Val
0x180003e6b  add     rcx, r14; void *
0x180003e6e  movsxd  r8, ebp; Size
0x180003e71  call    memset_0
0x180003e76  inc     edi
0x180003e78  inc     esi
0x180003e7a  cmp     esi, ebp
0x180003e7c  jl      short loc_180003E76
0x180003e7e  inc     ebx
0x180003e80  cmp     ebx, 1Ch
0x180003e83  jl      short loc_180003E4F
0x180003e85  movsxd  rax, edi
0x180003e88  xor     edi, edi
0x180003e8a  mov     [rax+r14-1], bl
0x180003e8f  xor     ebx, ebx
0x180003e91  lea     r14, g_DistLookup
0x180003e98  movzx   ecx, byte ptr [rbx+r15+7920h]
0x180003ea1  mov     ebp, 1
0x180003ea6  shl     ebp, cl
0x180003ea8  xor     esi, esi
0x180003eaa  test    ebp, ebp
0x180003eac  jle     short loc_180003EC7
0x180003eae  movsxd  rcx, edi
0x180003eb1  movzx   edx, bl; Val
0x180003eb4  add     rcx, r14; void *
0x180003eb7  movsxd  r8, ebp; Size
0x180003eba  call    memset_0
0x180003ebf  inc     edi
0x180003ec1  inc     esi
0x180003ec3  cmp     esi, ebp
0x180003ec5  jl      short loc_180003EBF
0x180003ec7  inc     ebx
0x180003ec9  cmp     ebx, 10h
0x180003ecc  jl      short loc_180003E98
0x180003ece  sar     edi, 7
0x180003ed1  lea     r14, qword_18000AC20
0x180003ed8  movsxd  rax, ebx
0x180003edb  mov     ebp, 1
0x180003ee0  xor     esi, esi
0x180003ee2  movzx   ecx, byte ptr [rax+r15+7920h]
0x180003eeb  sub     ecx, 7
0x180003eee  shl     ebp, cl
0x180003ef0  test    ebp, ebp
0x180003ef2  jle     short loc_180003F0D
0x180003ef4  movsxd  rcx, edi
0x180003ef7  movzx   edx, bl; Val
0x180003efa  add     rcx, r14; void *
0x180003efd  movsxd  r8, ebp; Size
0x180003f00  call    memset_0
0x180003f05  inc     edi
0x180003f07  inc     esi
0x180003f09  cmp     esi, ebp
0x180003f0b  jl      short loc_180003F05
0x180003f0d  inc     ebx
0x180003f0f  cmp     ebx, 1Eh
0x180003f12  jl      short loc_180003ED8
0x180003f14  add     rsp, 28h
0x180003f18  pop     r15
0x180003f1a  pop     r14
0x180003f1c  pop     rdi
0x180003f1d  pop     rsi
0x180003f1e  pop     rbp
0x180003f1f  pop     rbx
0x180003f20  retn
```
