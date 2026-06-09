# CDSLink::KsProperty(KSIDENTIFIER *,ulong,void *,ulong,ulong *)

- ea: `0x18000fd20`
- end: `0x18000fefd`
- name: `?KsProperty@CDSLink@@UEAAJPEAUKSIDENTIFIER@@KPEAXKPEAK@Z`
- size: `477`
- prototype: `int(CDSLink *__hidden this, struct KSIDENTIFIER *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x18000fd20`
- `0x1800148d1`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall CDSLink::KsProperty(
        CDSLink *this,
        struct KSIDENTIFIER *a2,
        int a3,
        _DWORD *a4,
        unsigned int Size,
        unsigned int *a6)
{
  __int64 result; // rax
  ULONG Id; // r10d
  struct SINKPROPERTY near **v9; // rax
  int v10; // ecx
  unsigned int v11; // ecx
  __int64 v12; // rdx
  struct SINKPROPERTY near *v13; // rax
  unsigned int v14; // ebx

  if ( a3 && !a2 || !a6 )
    return 2147500035LL;
  Id = a2->Id;
  v9 = &CDSLink::m_aProperty;
  while ( *(_QWORD *)*v9 != a2->Alignment || *((_QWORD *)*v9 + 1) != *(&a2->Alignment + 1) || *((_DWORD *)v9 + 2) != Id )
  {
    v9 += 7;
    if ( v9 == (struct SINKPROPERTY near **)&qword_18001E118 )
      return 2289570082LL;
  }
  if ( !a4 )
    return 2147942487LL;
  if ( (a2->Flags & 0x203) == 1 )
  {
    if ( (*((_BYTE *)v9 + 12) & 1) != 0 )
    {
      if ( ((_BYTE)v9[2] & 2) != 0 )
      {
        v12 = *((int *)v9 + 10);
        v13 = v9[4];
        *a6 = Size;
        return ((__int64 (__fastcall *)(char *, _QWORD, _QWORD))v13)((char *)this + v12 - 8, a2->Id, 0);
      }
      else
      {
        v14 = Size;
        if ( Size > *((_DWORD *)v9 + 7) )
          v14 = *((_DWORD *)v9 + 7);
        memcpy_0(a4, *(struct SINKPROPERTY near **)((char *)v9 + 20), v14);
        *a6 = v14;
        return 0;
      }
    }
    else
    {
      return 2289570084LL;
    }
  }
  else if ( (a2->Flags & 0x203) == 2 )
  {
    if ( (*((_BYTE *)v9 + 12) & 2) != 0 )
    {
      if ( ((_BYTE)v9[2] & 2) != 0 )
      {
        return ((__int64 (__fastcall *)(char *, _QWORD, __int64))v9[4])((char *)this + *((int *)v9 + 10) - 8, Id, 1);
      }
      else
      {
        v11 = Size;
        if ( Size > *((_DWORD *)v9 + 7) )
          v11 = *((_DWORD *)v9 + 7);
        memcpy_0(*(struct SINKPROPERTY near **)((char *)v9 + 20), a4, v11);
        return 0;
      }
    }
    else
    {
      return 2289570083LL;
    }
  }
  else
  {
    if ( (a2->Flags & 0x203) != 0x200 || Size < 4 )
      return 2147942487LL;
    v10 = *((_DWORD *)v9 + 3);
    result = 0;
    *a4 = v10;
    *a6 = 4;
  }
  return result;
}

```

## disassembly

```asm
0x18000fd20  mov     [rsp+arg_0], rbx
0x18000fd25  push    rdi
0x18000fd26  sub     rsp, 30h
0x18000fd2a  mov     r11, rdx
0x18000fd2d  mov     rbx, rcx
0x18000fd30  test    r8d, r8d
0x18000fd33  jz      short loc_18000FD3A
0x18000fd35  test    rdx, rdx
0x18000fd38  jz      short loc_18000FD44
0x18000fd3a  mov     rdi, [rsp+38h+arg_28]
0x18000fd3f  test    rdi, rdi
0x18000fd42  jnz     short loc_18000FD54
0x18000fd44  mov     eax, 80004003h
0x18000fd49  mov     rbx, [rsp+38h+arg_0]
0x18000fd4e  add     rsp, 30h
0x18000fd52  pop     rdi
0x18000fd53  retn
0x18000fd54  mov     r10d, [rdx+10h]
0x18000fd58  lea     rax, ?m_aProperty@CDSLink@@0PAUSINKPROPERTY@@A; SINKPROPERTY near * CDSLink::m_aProperty
0x18000fd5f  lea     r8, qword_18001E118
0x18000fd66  nop     word ptr [rax+rax+00000000h]
0x18000fd70  mov     ecx, [rax]
0x18000fd72  xor     edx, edx
0x18000fd74  or      rdx, rcx
0x18000fd77  mov     ecx, [rax+4]
0x18000fd7a  shl     rcx, 20h
0x18000fd7e  or      rdx, rcx
0x18000fd81  mov     rcx, [rdx]
0x18000fd84  cmp     rcx, [r11]
0x18000fd87  jnz     short loc_18000FD99
0x18000fd89  mov     rcx, [rdx+8]
0x18000fd8d  cmp     rcx, [r11+8]
0x18000fd91  jnz     short loc_18000FD99
0x18000fd93  cmp     [rax+8], r10d
0x18000fd97  jz      short loc_18000FDB2
0x18000fd99  add     rax, 38h ; '8'
0x18000fd9d  cmp     rax, r8
0x18000fda0  jnz     short loc_18000FD70
0x18000fda2  mov     eax, 88781122h
0x18000fda7  mov     rbx, [rsp+38h+arg_0]
0x18000fdac  add     rsp, 30h
0x18000fdb0  pop     rdi
0x18000fdb1  retn
0x18000fdb2  test    r9, r9
0x18000fdb5  jnz     short loc_18000FDC7
0x18000fdb7  mov     eax, 80070057h
0x18000fdbc  mov     rbx, [rsp+38h+arg_0]
0x18000fdc1  add     rsp, 30h
0x18000fdc5  pop     rdi
0x18000fdc6  retn
0x18000fdc7  mov     ecx, [r11+14h]
0x18000fdcb  and     ecx, 203h
0x18000fdd1  sub     ecx, 1
0x18000fdd4  jz      loc_18000FE7E
0x18000fdda  sub     ecx, 1
0x18000fddd  jz      short loc_18000FE07
0x18000fddf  cmp     ecx, 1FEh
0x18000fde5  jnz     short loc_18000FDB7
0x18000fde7  cmp     dword ptr [rsp+38h+Size], 4
0x18000fdec  jb      short loc_18000FDB7
0x18000fdee  mov     ecx, [rax+0Ch]
0x18000fdf1  xor     eax, eax
0x18000fdf3  mov     [r9], ecx
0x18000fdf6  mov     dword ptr [rdi], 4
0x18000fdfc  mov     rbx, [rsp+38h+arg_0]
0x18000fe01  add     rsp, 30h
0x18000fe05  pop     rdi
0x18000fe06  retn
0x18000fe07  test    byte ptr [rax+0Ch], 2
0x18000fe0b  jnz     short loc_18000FE1D
0x18000fe0d  mov     eax, 88781123h
0x18000fe12  mov     rbx, [rsp+38h+arg_0]
0x18000fe17  add     rsp, 30h
0x18000fe1b  pop     rdi
0x18000fe1c  retn
0x18000fe1d  test    byte ptr [rax+10h], 2
0x18000fe21  jz      short loc_18000FE55
0x18000fe23  movsxd  rcx, dword ptr [rax+28h]
0x18000fe27  lea     rdx, [rsp+38h+Size]
0x18000fe2c  mov     rax, [rax+20h]
0x18000fe30  add     rcx, 0FFFFFFFFFFFFFFF8h
0x18000fe34  mov     [rsp+38h+var_18], rdx
0x18000fe39  add     rcx, rbx
0x18000fe3c  mov     r8d, 1
0x18000fe42  mov     edx, r10d
0x18000fe45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe4a  mov     rbx, [rsp+38h+arg_0]
0x18000fe4f  add     rsp, 30h
0x18000fe53  pop     rdi
0x18000fe54  retn
0x18000fe55  mov     edx, [rax+1Ch]
0x18000fe58  mov     ecx, dword ptr [rsp+38h+Size]
0x18000fe5c  cmp     ecx, edx
0x18000fe5e  jbe     short loc_18000FE62
0x18000fe60  mov     ecx, edx
0x18000fe62  mov     r8d, ecx; Size
0x18000fe65  mov     rdx, r9; Src
0x18000fe68  mov     rcx, [rax+14h]; void *
0x18000fe6c  call    memcpy_0
0x18000fe71  xor     eax, eax
0x18000fe73  mov     rbx, [rsp+38h+arg_0]
0x18000fe78  add     rsp, 30h
0x18000fe7c  pop     rdi
0x18000fe7d  retn
0x18000fe7e  test    byte ptr [rax+0Ch], 1
0x18000fe82  jnz     short loc_18000FE94
0x18000fe84  mov     eax, 88781124h
0x18000fe89  mov     rbx, [rsp+38h+arg_0]
0x18000fe8e  add     rsp, 30h
0x18000fe92  pop     rdi
0x18000fe93  retn
0x18000fe94  test    byte ptr [rax+10h], 2
0x18000fe98  jz      short loc_18000FECE
0x18000fe9a  movsxd  rdx, dword ptr [rax+28h]
0x18000fe9e  xor     r8d, r8d
0x18000fea1  mov     r10, [rax+20h]
0x18000fea5  mov     ecx, dword ptr [rsp+38h+Size]
0x18000fea9  mov     rax, r10
0x18000feac  mov     [rdi], ecx
0x18000feae  lea     rcx, [rbx-8]
0x18000feb2  add     rcx, rdx
0x18000feb5  mov     [rsp+38h+var_18], rdi
0x18000feba  mov     edx, [r11+10h]
0x18000febe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fec3  mov     rbx, [rsp+38h+arg_0]
0x18000fec8  add     rsp, 30h
0x18000fecc  pop     rdi
0x18000fecd  retn
0x18000fece  mov     ecx, [rax+1Ch]
0x18000fed1  mov     ebx, dword ptr [rsp+38h+Size]
0x18000fed5  cmp     ebx, ecx
0x18000fed7  jbe     short loc_18000FEDF
0x18000fed9  mov     ebx, ecx
0x18000fedb  mov     dword ptr [rsp+38h+Size], ecx
0x18000fedf  mov     rdx, [rax+14h]; Src
0x18000fee3  mov     rcx, r9; void *
0x18000fee6  mov     r8d, ebx; Size
0x18000fee9  call    memcpy_0
0x18000feee  mov     [rdi], ebx
0x18000fef0  xor     eax, eax
0x18000fef2  mov     rbx, [rsp+38h+arg_0]
0x18000fef7  add     rsp, 30h
0x18000fefb  pop     rdi
0x18000fefc  retn
```
