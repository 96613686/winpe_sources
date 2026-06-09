# CSecConLib::SetMultiSZPropVal(ushort const *,ulong,ushort *,ulong)

- ea: `0x18001011c`
- end: `0x18001020f`
- name: `?SetMultiSZPropVal@CSecConLib@@AEAAJPEBGKPEAGK@Z`
- size: `243`
- prototype: `__int64 __fastcall(CSecConLib *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e408`
- `0x18000e83c`
- `0x18000ec68`
- `0x18000fb88`
- `0x18000fd64`
- `0x180010218`
- `0x1800103ac`

## callees

- `0x18001011c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CSecConLib::SetMultiSZPropVal(
        CSecConLib *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  __int64 v7; // rcx
  int v9; // ebx
  __int64 v10; // rcx
  int v11; // eax
  __int128 v13; // [rsp+40h] [rbp-30h] BYREF
  __int128 v14; // [rsp+50h] [rbp-20h]
  __int64 v15; // [rsp+60h] [rbp-10h]
  unsigned int v16; // [rsp+90h] [rbp+20h] BYREF

  v15 = 0;
  v16 = 0;
  v7 = *((_QWORD *)this + 7);
  v13 = 0;
  v14 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *, __int64, int, unsigned int *))(*(_QWORD *)v7 + 136LL))(
         v7,
         0,
         a2,
         2,
         30000,
         &v16);
  if ( v9 >= 0 )
  {
    v10 = *((_QWORD *)this + 7);
    if ( a4 )
    {
      v13 = a3;
      LODWORD(v14) = 2 * a5;
      *((_QWORD *)&v14 + 1) = a4;
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, const WCHAR *, __int128 *))(*(_QWORD *)v10 + 72LL))(
              v10,
              v16,
              &hMem,
              &v13);
    }
    else
    {
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, const WCHAR *, _QWORD, _DWORD))(*(_QWORD *)v10 + 88LL))(
              v10,
              v16,
              &hMem,
              a3,
              0);
    }
    v9 = v11;
  }
  (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 7) + 144LL))(*((_QWORD *)this + 7), v16);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001011c  mov     [rsp-18h+arg_8], rbx
0x180010121  mov     [rsp-18h+arg_10], rsi
0x180010126  push    rbp
0x180010127  push    rdi
0x180010128  push    r14
0x18001012a  mov     rbp, rsp
0x18001012d  sub     rsp, 70h
0x180010131  xor     eax, eax
0x180010133  xorps   xmm0, xmm0
0x180010136  mov     [rbp+var_10], rax
0x18001013a  mov     r14d, r8d
0x18001013d  mov     [rbp+arg_0], eax
0x180010140  lea     r8, [rbp+arg_0]
0x180010144  mov     [rsp+70h+var_48], r8
0x180010149  mov     rdi, rcx
0x18001014c  mov     rcx, [rcx+38h]
0x180010150  mov     rsi, r9
0x180010153  movups  [rbp+var_30], xmm0
0x180010157  mov     r8, rdx
0x18001015a  mov     r9d, 2
0x180010160  movups  [rbp+var_20], xmm0
0x180010164  mov     rax, [rcx]
0x180010167  xor     edx, edx
0x180010169  mov     [rsp+70h+var_50], 7530h
0x180010171  mov     rax, [rax+88h]
0x180010178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001017d  mov     ebx, eax
0x18001017f  test    eax, eax
0x180010181  js      short loc_1800101E2
0x180010183  mov     rcx, [rdi+38h]
0x180010187  lea     r8, hMem
0x18001018e  mov     edx, [rbp+arg_0]
0x180010191  test    rsi, rsi
0x180010194  jnz     short loc_1800101AB
0x180010196  mov     rax, [rcx]
0x180010199  mov     r9d, r14d
0x18001019c  mov     [rsp+70h+var_50], esi
0x1800101a0  mov     rax, [rax+58h]
0x1800101a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101a9  jmp     short loc_1800101E0
0x1800101ab  mov     eax, [rbp+arg_20]
0x1800101ae  lea     r9, [rbp+var_30]
0x1800101b2  add     eax, eax
0x1800101b4  mov     dword ptr [rbp+var_30], r14d
0x1800101b8  mov     dword ptr [rbp+var_20], eax
0x1800101bb  mov     dword ptr [rbp+var_30+4], 0
0x1800101c2  mov     dword ptr [rbp+var_30+8], 1
0x1800101c9  mov     dword ptr [rbp+var_30+0Ch], 5
0x1800101d0  mov     qword ptr [rbp+var_20+8], rsi
0x1800101d4  mov     rax, [rcx]
0x1800101d7  mov     rax, [rax+48h]
0x1800101db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101e0  mov     ebx, eax
0x1800101e2  mov     rcx, [rdi+38h]
0x1800101e6  mov     edx, [rbp+arg_0]
0x1800101e9  mov     rax, [rcx]
0x1800101ec  mov     rax, [rax+90h]
0x1800101f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101f8  lea     r11, [rsp+70h+var_s0]
0x1800101fd  mov     eax, ebx
0x1800101ff  mov     rbx, [r11+28h]
0x180010203  mov     rsi, [r11+30h]
0x180010207  mov     rsp, r11
0x18001020a  pop     r14
0x18001020c  pop     rdi
0x18001020d  pop     rbp
0x18001020e  retn
```
