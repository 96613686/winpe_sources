# GpDevice::GetScanBuffers(int,void * *,HDC__ * *,ColorPalette *,int *,int,void * * const)

- ea: `0x18009571c`
- end: `0x180095856`
- name: `?GetScanBuffers@GpDevice@@QEAAHHPEAPEAXPEAPEAUHDC__@@PEAUColorPalette@@PEAHHQEAPEAX@Z`
- size: `314`
- prototype: `__int64 __fastcall(GpDevice *__hidden this, int, void **, HDC *, struct ColorPalette *, int *, int, void **const)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800218ac`

## callees

- `0x180017b00`
- `0x18001f950`
- `0x18009571c`
- `0x1800e5044`

## import_xrefs

- `GDI32!SelectObject` at `0x1800957fb`
- `GDI32!SelectObject` at `0x1800957fb`
- `GDI32!DeleteObject` at `0x1800957ac`
- `GDI32!DeleteObject` at `0x1800957ac`

## pseudocode

```c
__int64 __fastcall GpDevice::GetScanBuffers(
        GpDevice *this,
        int a2,
        void **a3,
        HDC *a4,
        struct ColorPalette *a5,
        int *a6,
        int a7,
        void **const a8)
{
  unsigned __int64 v8; // rbp
  _DWORD *v9; // rsi
  unsigned int v10; // ebx
  void **v12; // rdx
  __int64 v14; // r8
  _QWORD *v15; // rdx
  __int64 v16; // r8
  void *v17; // rcx
  HBITMAP SemiCompatibleDIB; // rax
  HDC v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rdi

  v8 = a2;
  v9 = (_DWORD *)((char *)this + 12);
  v10 = 0;
  if ( a2 > *((_DWORD *)this + 3) )
  {
    v17 = (void *)*((_QWORD *)this + 2);
    if ( v17 )
      DeleteObject(v17);
    SemiCompatibleDIB = CreateSemiCompatibleDIB(
                          *((HDC *)this + 188),
                          v8,
                          1,
                          *((struct ColorPalette **)this + 197),
                          (void **)this + 4,
                          (int *)this + 20,
                          0);
    *((_QWORD *)this + 2) = SemiCompatibleDIB;
    if ( SemiCompatibleDIB )
    {
      v19 = (HDC)*((_QWORD *)this + 3);
      *v9 = v8;
      SelectObject(v19, SemiCompatibleDIB);
    }
    else
    {
      *v9 = 0;
    }
    v20 = *((_QWORD *)this + 5);
    if ( v20 )
      GpFree(v20);
    if ( is_mul_ok(0x28u, v8)
      && (v21 = GpMallocEx(40 * v8, (0x28 * (unsigned __int128)v8) >> 64), (*((_QWORD *)this + 5) = v21) != 0) )
    {
      v15 = (_QWORD *)((char *)this + 48);
      v16 = 4;
      do
      {
        *v15 = *(v15 - 1) + 8 * v8;
        ++v15;
        --v16;
      }
      while ( v16 );
    }
    else
    {
      *v9 = 0;
    }
  }
  v12 = a8;
  if ( a8 )
  {
    v22 = this - (GpDevice *)a8;
    v14 = 5;
    do
    {
      *v12 = *(void **)((char *)v12 + v22 + 40);
      ++v12;
      --v14;
    }
    while ( v14 );
  }
  LOBYTE(v10) = *v9 != 0;
  return v10;
}

```

## disassembly

```asm
0x18009571c  mov     [rsp+arg_0], rbx
0x180095721  mov     [rsp+arg_8], rbp
0x180095726  mov     [rsp+arg_10], rsi
0x18009572b  push    rdi
0x18009572c  sub     rsp, 40h
0x180095730  movsxd  rbp, edx
0x180095733  lea     rsi, [rcx+0Ch]
0x180095737  xor     ebx, ebx
0x180095739  mov     rdi, rcx
0x18009573c  cmp     ebp, [rsi]
0x18009573e  jg      short loc_1800957A3
0x180095740  mov     rdx, [rsp+48h+arg_38]
0x180095748  test    rdx, rdx
0x18009574b  jnz     loc_180095848
0x180095751  cmp     [rsi], ebx
0x180095753  mov     rbp, [rsp+48h+arg_8]
0x180095758  mov     rsi, [rsp+48h+arg_10]
0x18009575d  setnz   bl
0x180095760  mov     eax, ebx
0x180095762  mov     rbx, [rsp+48h+arg_0]
0x180095767  add     rsp, 40h
0x18009576b  pop     rdi
0x18009576c  retn
0x18009576e  mov     rcx, [rdi+rdx+28h]
0x180095773  mov     [rdx], rcx
0x180095776  lea     rdx, [rdx+8]
0x18009577a  sub     r8, 1
0x18009577e  jnz     short loc_18009576E
0x180095780  jmp     short loc_180095751
0x180095782  lea     rdx, [rdi+30h]
0x180095786  mov     r8d, 4
0x18009578c  mov     rax, [rdx-8]
0x180095790  lea     rcx, [rax+rbp*8]
0x180095794  mov     [rdx], rcx
0x180095797  lea     rdx, [rdx+8]
0x18009579b  sub     r8, 1
0x18009579f  jnz     short loc_18009578C
0x1800957a1  jmp     short loc_180095740
0x1800957a3  mov     rcx, [rcx+10h]; ho
0x1800957a7  test    rcx, rcx
0x1800957aa  jz      short loc_1800957B8
0x1800957ac  call    cs:__imp_DeleteObject
0x1800957b3  nop     dword ptr [rax+rax+00h]
0x1800957b8  mov     r9, [rdi+628h]; struct ColorPalette *
0x1800957bf  lea     rax, [rdi+50h]
0x1800957c3  lea     rcx, [rdi+20h]
0x1800957c7  mov     [rsp+48h+var_18], ebx; int
0x1800957cb  mov     [rsp+48h+var_20], rax; int *
0x1800957d0  mov     r8d, 1; unsigned int
0x1800957d6  mov     [rsp+48h+var_28], rcx; void **
0x1800957db  mov     edx, ebp; unsigned int
0x1800957dd  mov     rcx, [rdi+5E0h]; hdc
0x1800957e4  call    ?CreateSemiCompatibleDIB@@YAPEAUHBITMAP__@@PEAUHDC__@@KKPEAUColorPalette@@PEAPEAXPEAHH@Z; CreateSemiCompatibleDIB(HDC__ *,ulong,ulong,ColorPalette *,void * *,int *,int)
0x1800957e9  mov     [rdi+10h], rax
0x1800957ed  test    rax, rax
0x1800957f0  jz      short loc_18009583D
0x1800957f2  mov     rcx, [rdi+18h]; hdc
0x1800957f6  mov     rdx, rax; h
0x1800957f9  mov     [rsi], ebp
0x1800957fb  call    cs:__imp_SelectObject
0x180095802  nop     dword ptr [rax+rax+00h]
0x180095807  mov     rcx, [rdi+28h]
0x18009580b  test    rcx, rcx
0x18009580e  jnz     short loc_180095841
0x180095810  mov     ecx, 28h ; '('
0x180095815  mov     rax, rbp
0x180095818  mul     rcx
0x18009581b  test    rdx, rdx
0x18009581e  jz      short loc_180095827
0x180095820  mov     [rsi], ebx
0x180095822  jmp     loc_180095740
0x180095827  mov     rcx, rax
0x18009582a  call    GpMallocEx
0x18009582f  mov     [rdi+28h], rax
0x180095833  test    rax, rax
0x180095836  jz      short loc_180095820
0x180095838  jmp     loc_180095782
0x18009583d  mov     [rsi], ebx
0x18009583f  jmp     short loc_180095807
0x180095841  call    GpFree
0x180095846  jmp     short loc_180095810
0x180095848  sub     rdi, rdx
0x18009584b  mov     r8d, 5
0x180095851  jmp     loc_18009576E
```
