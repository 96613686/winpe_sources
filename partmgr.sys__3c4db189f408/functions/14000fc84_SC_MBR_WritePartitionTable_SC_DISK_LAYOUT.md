# SC_MBR::WritePartitionTable(SC_DISK_LAYOUT *)

- ea: `0x14000fc84`
- end: `0x14000fec1`
- name: `?WritePartitionTable@SC_MBR@@QEAAJPEAVSC_DISK_LAYOUT@@@Z`
- size: `573`
- prototype: `__int64 __fastcall(SC_DISK **this, struct SC_DISK_LAYOUT *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000f180`
- `0x14000fbd4`

## callees

- `0x14000590c`
- `0x140005950`
- `0x14000f264`
- `0x14000fb14`
- `0x14000fc84`
- `0x140010f20`
- `0x14001c3bc`

## pseudocode

```c
__int64 __fastcall SC_MBR::WritePartitionTable(SC_DISK **this, struct SC_DISK_LAYOUT *a2)
{
  unsigned int v3; // edx
  __int64 v4; // r13
  int Sectors; // edi
  char v6; // si
  __int64 v7; // r15
  unsigned int v8; // eax
  __int64 v10; // r14
  unsigned int i; // ebp
  __int64 v12; // r9
  char v13; // cl
  unsigned int v14; // r10d
  bool v15; // zf
  __int64 v16; // rdx
  __int64 v17; // rdx
  unsigned int v18; // eax
  unsigned int v19; // ecx
  unsigned int v21; // [rsp+20h] [rbp-58h]
  unsigned int v22; // [rsp+24h] [rbp-54h]
  struct _GUID v23; // [rsp+28h] [rbp-50h] BYREF

  v3 = 0;
  v22 = 0;
  v4 = 0;
  v21 = 0;
  Sectors = 0;
  v6 = 0;
  v7 = *((_QWORD *)*this + 33);
  v8 = *((_DWORD *)a2 + 2);
  v23 = 0;
  if ( !v8 )
  {
    SC_ENV::CreateGuid(&v23);
    v3 = 0;
    v8 = *(_DWORD *)&v23.Data4[4] ^ *(_DWORD *)v23.Data4 ^ *(_DWORD *)&v23.Data2 ^ v23.Data1;
    *((_DWORD *)a2 + 2) = v8;
  }
  if ( *(_DWORD *)(v7 + 440) != v8 )
  {
    *(_DWORD *)(v7 + 440) = v8;
    v6 = 1;
    *((_DWORD *)a2 + 3) = MBR_HEADER::CheckSum((MBR_HEADER *)v7);
  }
  while ( 2 )
  {
    v10 = 0;
    for ( i = 0; i < 4 && (unsigned int)v4 < *((_DWORD *)a2 + 1); ++i )
    {
      v12 = v7 + 16LL * i + 446;
      v13 = *((_BYTE *)a2 + 144 * v4 + 80);
      if ( v13 == 5 || v13 == 15 )
      {
        if ( v10 )
          return (unsigned int)-1073741823;
        v14 = v22;
        v10 = v7 + 16LL * i + 446;
      }
      else
      {
        v14 = v3;
      }
      *((_DWORD *)a2 + 36 * v4 + 22) = *((_DWORD *)a2 + 2);
      v15 = *((_BYTE *)a2 + 144 * v4 + 76) == 0;
      *((_DWORD *)a2 + 36 * v4 + 23) = 0;
      *((_QWORD *)a2 + 18 * v4 + 12) = *((_QWORD *)a2 + 18 * v4 + 7);
      if ( !v15 )
      {
        if ( v13 )
        {
          *(_BYTE *)v12 = *((_BYTE *)a2 + 144 * v4 + 81) != 0 ? 0x80 : 0;
          *(_BYTE *)(v12 + 4) = *((_BYTE *)a2 + 144 * v4 + 80);
          v16 = *((_QWORD *)a2 + 18 * v4 + 7);
          if ( *((_DWORD *)*this + 59) )
            v16 /= (__int64)*((unsigned int *)*this + 59);
          *(_DWORD *)(v12 + 8) = v16 - v14;
          v17 = *((_QWORD *)a2 + 18 * v4 + 8);
          if ( *((_DWORD *)*this + 59) )
            v17 /= (__int64)*((unsigned int *)*this + 59);
          *(_DWORD *)(v12 + 12) = v17;
          MBR_ENTRY::ComputeChs((MBR_ENTRY *)(v7 + 16LL * i + 446), (struct _DISK_GEOMETRY *)*this + 9);
        }
        else
        {
          *(_OWORD *)v12 = 0;
        }
        v6 = 1;
      }
      v3 = v21;
      v4 = (unsigned int)(v4 + 1);
    }
    if ( v6 )
    {
      Sectors = SC_DISK::WriteSectors(*this, 1u, v3, 0);
      if ( Sectors < 0 )
        return (unsigned int)Sectors;
      v6 = 0;
    }
    if ( v10 )
    {
      v18 = *(_DWORD *)(v10 + 8);
      v19 = v18 + v22;
      if ( v22 )
        v18 = v22;
      v21 = v19;
      v22 = v18;
      Sectors = SC_DISK::ReadSectors(*this, 1, v19, 0);
      if ( Sectors >= 0 )
      {
        v3 = v21;
        *(_WORD *)(v7 + 510) = -21931;
        continue;
      }
    }
    break;
  }
  return (unsigned int)Sectors;
}

```

## disassembly

```asm
0x14000fc84  mov     [rsp+arg_10], rbx
0x14000fc89  push    rbp
0x14000fc8a  push    rsi
0x14000fc8b  push    rdi
0x14000fc8c  push    r12
0x14000fc8e  push    r13
0x14000fc90  push    r14
0x14000fc92  push    r15
0x14000fc94  sub     rsp, 40h
0x14000fc98  mov     rax, cs:__security_cookie
0x14000fc9f  xor     rax, rsp
0x14000fca2  mov     [rsp+78h+var_40], rax
0x14000fca7  mov     rax, [rcx]
0x14000fcaa  mov     rbx, rdx
0x14000fcad  xor     edx, edx
0x14000fcaf  mov     [rsp+78h+var_54], 0
0x14000fcb7  xor     r13d, r13d
0x14000fcba  mov     [rsp+78h+var_58], edx
0x14000fcbe  xor     edi, edi
0x14000fcc0  xor     sil, sil
0x14000fcc3  mov     r15, [rax+108h]
0x14000fcca  xorps   xmm0, xmm0
0x14000fccd  mov     eax, [rbx+8]
0x14000fcd0  mov     r12, rcx
0x14000fcd3  movups  xmmword ptr [rsp+78h+var_50.Data1], xmm0
0x14000fcd8  test    eax, eax
0x14000fcda  jnz     short loc_14000FCFB
0x14000fcdc  lea     rcx, [rsp+78h+var_50]; struct _GUID *
0x14000fce1  call    ?CreateGuid@SC_ENV@@SAJPEAU_GUID@@@Z; SC_ENV::CreateGuid(_GUID *)
0x14000fce6  mov     eax, [rsp+78h+var_50.Data1]
0x14000fcea  mov     edx, edi
0x14000fcec  xor     eax, dword ptr [rsp+78h+var_50.Data2]
0x14000fcf0  xor     eax, dword ptr [rsp+78h+var_50.Data4]
0x14000fcf4  xor     eax, dword ptr [rsp+78h+var_50.Data4+4]
0x14000fcf8  mov     [rbx+8], eax
0x14000fcfb  cmp     [r15+1B8h], eax
0x14000fd02  jz      short loc_14000FD19
0x14000fd04  mov     rcx, r15; this
0x14000fd07  mov     [r15+1B8h], eax
0x14000fd0e  mov     sil, 1
0x14000fd11  call    ?CheckSum@MBR_HEADER@@QEAAKXZ; MBR_HEADER::CheckSum(void)
0x14000fd16  mov     [rbx+0Ch], eax
0x14000fd19  xor     r14d, r14d
0x14000fd1c  xor     ebp, ebp
0x14000fd1e  cmp     ebp, 4
0x14000fd21  jnb     loc_14000FE2A
0x14000fd27  cmp     r13d, [rbx+4]
0x14000fd2b  jnb     loc_14000FE2A
0x14000fd31  lea     r8, ds:0[r13*8]
0x14000fd39  mov     r9d, ebp
0x14000fd3c  shl     r9, 4
0x14000fd40  add     r8, r13
0x14000fd43  add     r8, r8
0x14000fd46  add     r9, 1BEh
0x14000fd4d  add     r9, r15
0x14000fd50  mov     cl, [rbx+r8*8+50h]
0x14000fd55  cmp     cl, 5
0x14000fd58  jz      short loc_14000FD64
0x14000fd5a  cmp     cl, 0Fh
0x14000fd5d  jz      short loc_14000FD64
0x14000fd5f  mov     r10d, edx
0x14000fd62  jmp     short loc_14000FD75
0x14000fd64  test    r14, r14
0x14000fd67  jnz     loc_14000FE94
0x14000fd6d  mov     r10d, [rsp+78h+var_54]
0x14000fd72  mov     r14, r9
0x14000fd75  mov     eax, [rbx+8]
0x14000fd78  mov     [rbx+r8*8+58h], eax
0x14000fd7d  xor     eax, eax
0x14000fd7f  cmp     byte ptr [rbx+r8*8+4Ch], 0
0x14000fd85  mov     [rbx+r8*8+5Ch], eax
0x14000fd8a  mov     rax, [rbx+r8*8+38h]
0x14000fd8f  mov     [rbx+r8*8+60h], rax
0x14000fd94  jz      loc_14000FE1C
0x14000fd9a  test    cl, cl
0x14000fd9c  jz      short loc_14000FE12
0x14000fd9e  mov     al, [rbx+r8*8+51h]
0x14000fda3  neg     al
0x14000fda5  sbb     cl, cl
0x14000fda7  and     cl, 80h
0x14000fdaa  mov     [r9], cl
0x14000fdad  mov     al, [rbx+r8*8+50h]
0x14000fdb2  mov     [r9+4], al
0x14000fdb6  mov     rax, [r12]
0x14000fdba  mov     rdx, [rbx+r8*8+38h]
0x14000fdbf  mov     ecx, [rax+0ECh]
0x14000fdc5  test    ecx, ecx
0x14000fdc7  jz      short loc_14000FDD4
0x14000fdc9  mov     rax, rdx
0x14000fdcc  cqo
0x14000fdce  idiv    rcx
0x14000fdd1  mov     rdx, rax
0x14000fdd4  sub     edx, r10d
0x14000fdd7  mov     [r9+8], edx
0x14000fddb  mov     rax, [r12]
0x14000fddf  mov     rdx, [rbx+r8*8+40h]
0x14000fde4  mov     ecx, [rax+0ECh]
0x14000fdea  test    ecx, ecx
0x14000fdec  jz      short loc_14000FDF9
0x14000fdee  mov     rax, rdx
0x14000fdf1  cqo
0x14000fdf3  idiv    rcx
0x14000fdf6  mov     rdx, rax
0x14000fdf9  mov     [r9+0Ch], edx
0x14000fdfd  mov     rcx, r9; this
0x14000fe00  mov     rdx, [r12]
0x14000fe04  add     rdx, 0D8h; struct _DISK_GEOMETRY *
0x14000fe0b  call    ?ComputeChs@MBR_ENTRY@@QEAAXPEAU_DISK_GEOMETRY@@@Z; MBR_ENTRY::ComputeChs(_DISK_GEOMETRY *)
0x14000fe10  jmp     short loc_14000FE19
0x14000fe12  xorps   xmm0, xmm0
0x14000fe15  movups  xmmword ptr [r9], xmm0
0x14000fe19  mov     sil, 1
0x14000fe1c  mov     edx, [rsp+78h+var_58]
0x14000fe20  inc     ebp
0x14000fe22  inc     r13d
0x14000fe25  jmp     loc_14000FD1E
0x14000fe2a  test    sil, sil
0x14000fe2d  jz      short loc_14000FE4B
0x14000fe2f  mov     rcx, [r12]; this
0x14000fe33  xor     r9d, r9d; void *
0x14000fe36  mov     r8d, edx; unsigned __int64
0x14000fe39  lea     edx, [r9+1]; unsigned int
0x14000fe3d  call    ?WriteSectors@SC_DISK@@QEAAJK_KPEAX@Z; SC_DISK::WriteSectors(ulong,unsigned __int64,void *)
0x14000fe42  mov     edi, eax
0x14000fe44  test    eax, eax
0x14000fe46  js      short loc_14000FE99
0x14000fe48  xor     sil, sil
0x14000fe4b  test    r14, r14
0x14000fe4e  jz      short loc_14000FE99
0x14000fe50  mov     edx, [rsp+78h+var_54]
0x14000fe54  test    edx, edx
0x14000fe56  mov     eax, [r14+8]
0x14000fe5a  lea     ecx, [rax+rdx]
0x14000fe5d  cmovnz  eax, edx
0x14000fe60  xor     r9d, r9d; void *
0x14000fe63  mov     [rsp+78h+var_58], ecx
0x14000fe67  mov     r8d, ecx; unsigned __int64
0x14000fe6a  mov     rcx, [r12]; this
0x14000fe6e  mov     [rsp+78h+var_54], eax
0x14000fe72  lea     edx, [r9+1]; unsigned int
0x14000fe76  call    ?ReadSectors@SC_DISK@@QEAAJK_KPEAX@Z; SC_DISK::ReadSectors(ulong,unsigned __int64,void *)
0x14000fe7b  mov     edi, eax
0x14000fe7d  test    eax, eax
0x14000fe7f  js      short loc_14000FE99
0x14000fe81  mov     edx, [rsp+78h+var_58]
0x14000fe85  mov     word ptr [r15+1FEh], 0AA55h
0x14000fe8f  jmp     loc_14000FD19
0x14000fe94  mov     edi, 0C0000001h
0x14000fe99  mov     eax, edi
0x14000fe9b  mov     rcx, [rsp+78h+var_40]
0x14000fea0  xor     rcx, rsp; StackCookie
0x14000fea3  call    __security_check_cookie
0x14000fea8  mov     rbx, [rsp+78h+arg_10]
0x14000feb0  add     rsp, 40h
0x14000feb4  pop     r15
0x14000feb6  pop     r14
0x14000feb8  pop     r13
0x14000feba  pop     r12
0x14000febc  pop     rdi
0x14000febd  pop     rsi
0x14000febe  pop     rbp
0x14000febf  retn
```
