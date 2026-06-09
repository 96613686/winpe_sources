# CMp3Decode::Init(bool)

- ea: `0x180005000`
- end: `0x180005103`
- name: `?Init@CMp3Decode@@QEAAX_N@Z`
- size: `259`
- prototype: `void __fastcall(CMp3Decode *__hidden this, bool)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180003a70`
- `0x180003ce0`
- `0x180003f50`
- `0x180003fa0`

## callees

- `0x180001cd4`
- `0x180005000`
- `0x180005380`
- `0x18000e130`
- `0x18000f9c0`
- `0x180012010`

## pseudocode

```c
void __fastcall CMp3Decode::Init(CMp3Decode *this, char a2)
{
  __int64 i; // rbx
  char *v5; // rdi
  __int64 j; // r8
  __int64 v7; // rcx
  _OWORD *v8; // rax

  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 3795) + 8LL))((char *)this + 30360);
  if ( a2 )
  {
    CMdct::Init((CMp3Decode *)((char *)this + 80));
    for ( i = 0; i != 2; ++i )
      memset_0(*((void **)this + i + 616), 0, 0x800u);
    *((_DWORD *)this + 1230) = 32;
    CErrorConcealment::Init((CMp3Decode *)((char *)this + 4976));
    memset_0((char *)this + 31680, 0, 0x900u);
    memset_0((char *)this + 33984, 0, 0x900u);
    CMp3Decode::ZeroSpectrum(this);
    v5 = (char *)this + 40896;
    for ( j = 0; j != 2; ++j )
    {
      v7 = 0;
      do
      {
        v8 = *(_OWORD **)&v5[144 * j + 8 * v7++];
        *v8 = 0;
        v8[1] = 0;
        v8[2] = 0;
        v8[3] = 0;
        v8[4] = 0;
        v8[5] = 0;
        v8[6] = 0;
        v8[7] = 0;
      }
      while ( v7 != 18 );
    }
  }
}

```

## disassembly

```asm
0x180005000  mov     [rsp+arg_0], rbx
0x180005005  push    rdi
0x180005006  sub     rsp, 20h
0x18000500a  mov     rdi, rcx
0x18000500d  movzx   ebx, dl
0x180005010  add     rcx, 7698h
0x180005017  mov     rax, [rcx]
0x18000501a  mov     rax, [rax+8]
0x18000501e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005023  test    bl, bl
0x180005025  jz      loc_1800050F8
0x18000502b  lea     rcx, [rdi+50h]; this
0x18000502f  call    ?Init@CMdct@@QEAAXXZ; CMdct::Init(void)
0x180005034  xor     ebx, ebx
0x180005036  nop     word ptr [rax+rax+00000000h]
0x180005040  mov     rcx, [rdi+rbx*8+1340h]; void *
0x180005048  xor     edx, edx; Val
0x18000504a  mov     r8d, 800h; Size
0x180005050  call    memset_0
0x180005055  inc     rbx
0x180005058  cmp     rbx, 2
0x18000505c  jnz     short loc_180005040
0x18000505e  lea     rcx, [rdi+1370h]; this
0x180005065  mov     dword ptr [rdi+1338h], 20h ; ' '
0x18000506f  call    ?Init@CErrorConcealment@@QEAAXXZ; CErrorConcealment::Init(void)
0x180005074  lea     rcx, [rdi+7BC0h]; void *
0x18000507b  xor     edx, edx; Val
0x18000507d  mov     r8d, 900h; Size
0x180005083  call    memset_0
0x180005088  lea     rcx, [rdi+84C0h]; void *
0x18000508f  xor     edx, edx; Val
0x180005091  mov     r8d, 900h; Size
0x180005097  call    memset_0
0x18000509c  mov     rcx, rdi; this
0x18000509f  call    ?ZeroSpectrum@CMp3Decode@@IEAAXXZ; CMp3Decode::ZeroSpectrum(void)
0x1800050a4  add     rdi, 9FC0h
0x1800050ab  xor     r8d, r8d
0x1800050ae  xchg    ax, ax
0x1800050b0  lea     rdx, [r8+r8*8]
0x1800050b4  shl     rdx, 4
0x1800050b8  add     rdx, rdi
0x1800050bb  xor     ecx, ecx
0x1800050bd  nop     dword ptr [rax]
0x1800050c0  mov     rax, [rdx+rcx*8]
0x1800050c4  xorps   xmm0, xmm0
0x1800050c7  inc     rcx
0x1800050ca  movups  xmmword ptr [rax], xmm0
0x1800050cd  movups  xmmword ptr [rax+10h], xmm0
0x1800050d1  movups  xmmword ptr [rax+20h], xmm0
0x1800050d5  movups  xmmword ptr [rax+30h], xmm0
0x1800050d9  movups  xmmword ptr [rax+40h], xmm0
0x1800050dd  movups  xmmword ptr [rax+50h], xmm0
0x1800050e1  movups  xmmword ptr [rax+60h], xmm0
0x1800050e5  movups  xmmword ptr [rax+70h], xmm0
0x1800050e9  cmp     rcx, 12h
0x1800050ed  jnz     short loc_1800050C0
0x1800050ef  inc     r8
0x1800050f2  cmp     r8, 2
0x1800050f6  jnz     short loc_1800050B0
0x1800050f8  mov     rbx, [rsp+28h+arg_0]
0x1800050fd  add     rsp, 20h
0x180005101  pop     rdi
0x180005102  retn
```
