# FILE_ICB_DESCRIPTOR::ReadData(void *,unsigned __int64,ulong,ulong *)

- ea: `0x180063df0`
- end: `0x180064290`
- name: `?ReadData@FILE_ICB_DESCRIPTOR@@QEAAEPEAX_KKPEAK@Z`
- size: `1184`
- prototype: `unsigned __int8(FILE_ICB_DESCRIPTOR *__hidden this, void *, unsigned __int64, unsigned int, unsigned int *)`
- caller_count: `5`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180061098`
- `0x180061840`
- `0x18006259c`
- `0x18006e044`
- `0x18006e10c`

## callees

- `0x1800251f6`
- `0x180028568`
- `0x18005fae0`
- `0x180063df0`
- `0x180067f4c`
- `0x18006da80`
- `0x18006dae8`
- `0x18008170e`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18006427f`
- `ntdll!RtlFreeHeap` at `0x18006427f`
- `ntdll!RtlAllocateHeap` at `0x180063f79`
- `ntdll!RtlAllocateHeap` at `0x180063f79`

## pseudocode

```c
unsigned __int8 __fastcall FILE_ICB_DESCRIPTOR::ReadData(
        FILE_ICB_DESCRIPTOR *this,
        char *a2,
        unsigned __int64 a3,
        unsigned int a4,
        unsigned int *a5)
{
  __int64 v5; // r12
  __int64 v7; // rsi
  unsigned __int64 v10; // rbx
  char v11; // al
  unsigned int SectorSize; // r15d
  unsigned __int64 v13; // rcx
  unsigned __int16 v14; // dx
  __int64 v15; // rax
  __int64 v16; // rdx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v20; // rcx
  unsigned int v21; // ebx
  char *Heap; // r12
  unsigned __int64 v23; // rcx
  UDF_EXTENT_LIST **i; // r10
  unsigned __int64 v25; // rdx
  int v26; // eax
  UDF_EXTENT_LIST *v27; // rcx
  __int64 v28; // rcx
  unsigned int v29; // r9d
  unsigned int v30; // [rsp+30h] [rbp-28h] BYREF
  size_t Size; // [rsp+38h] [rbp-20h] BYREF
  UDF_EXTENT_LIST **v32; // [rsp+40h] [rbp-18h]
  unsigned __int64 v33; // [rsp+48h] [rbp-10h]
  unsigned int v34; // [rsp+A0h] [rbp+48h] BYREF

  v5 = *((_QWORD *)this + 2);
  v7 = a4;
  v30 = 0;
  LODWORD(Size) = 0;
  v10 = *(_QWORD *)(v5 + 56);
  v11 = *(_BYTE *)(v5 + 34) & 7;
  v34 = 0;
  if ( v11 == 3 )
  {
    SectorSize = 0;
    v13 = v10;
  }
  else
  {
    SectorSize = UDF_SA::QuerySectorSize(*(UDF_SA **)(*((_QWORD *)this + 4) + 32LL));
    if ( !UDF_EXTENT_LIST::QueryInformationLength(*((UDF_EXTENT_LIST **)this + 5), (unsigned int *)&Size) )
      return 0;
    v13 = (unsigned int)Size * SectorSize;
    if ( v13 > v10 )
      v13 = v10;
  }
  if ( v10 > a3 )
  {
    if ( v10 < a3 + v7 )
      v7 = (unsigned int)(v10 - a3);
  }
  else
  {
    v7 = 0;
  }
  v14 = *(_WORD *)(*((_QWORD *)this + 2) + 34LL) & 7;
  if ( v14 == 3 )
  {
    v15 = 168;
    v16 = 176;
    if ( *(_WORD *)v5 != 261 )
    {
      v15 = 208;
      v16 = 216;
    }
    memcpy_0(a2, (const void *)(a3 + v5 + *(unsigned int *)(v15 + v5) + v16), (unsigned int)v7);
    goto LABEL_78;
  }
  if ( v14 >= 2u )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v18 = 21;
    goto LABEL_68;
  }
  if ( v13 <= a3 )
  {
    memset_0(a2, 0, (unsigned int)v7);
    *a5 = v7;
    return 1;
  }
  if ( v13 >= v7 + a3 )
  {
    LODWORD(Size) = 0;
    v21 = v7;
  }
  else
  {
    v20 = (unsigned int)(v13 - a3);
    v21 = v20;
    Size = (unsigned int)(v7 - v20);
    memset_0(&a2[v20], 0, Size);
  }
  if ( !v21 )
  {
LABEL_78:
    *a5 = v7;
    return 1;
  }
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 10 * SectorSize);
  if ( !Heap )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v18 = 14;
    goto LABEL_68;
  }
  v23 = SectorSize;
  i = (UDF_EXTENT_LIST **)((char *)this + 48);
  v25 = a3 % SectorSize;
  v32 = (UDF_EXTENT_LIST **)((char *)this + 48);
  v33 = v25;
  if ( !(_DWORD)v25 )
  {
    v32 = (UDF_EXTENT_LIST **)((char *)this + 48);
    goto LABEL_45;
  }
  v26 = v7 - Size;
  if ( (int)v7 - (int)Size >= SectorSize - (unsigned int)v25 )
    v26 = SectorSize - v25;
  v27 = *i;
  LODWORD(Size) = v26;
  if ( !UDF_EXTENT_LIST::QueryLbnFromVbn(v27, a3 / SectorSize, &v34, &v30) )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v18 = 15;
    goto LABEL_68;
  }
  if ( v34 == -1 )
  {
    memset_0(a2, 0, (unsigned int)Size);
  }
  else
  {
    if ( !UDF_LVOL::Read(*((UDF_LVOL **)this + 4), *((_WORD *)this + 12), v34, 1u, Heap) )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return 0;
      v18 = 16;
LABEL_68:
      WPP_SF_(v17[2], v18, &WPP_5a183823c4533aac4dc0f098fe52d790_Traceguids);
      return 0;
    }
    memcpy_0(a2, &Heap[(unsigned int)v33], (unsigned int)Size);
  }
  v28 = (unsigned int)Size;
  for ( i = (UDF_EXTENT_LIST **)((char *)this + 48); ; i = v32 )
  {
    v21 -= v28;
    a2 += v28;
    a3 += v28;
    v23 = SectorSize;
LABEL_45:
    if ( v21 < SectorSize )
      break;
    if ( !UDF_EXTENT_LIST::QueryLbnFromVbn(*i, a3 / v23, &v34, &v30) )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v18 = 17;
        goto LABEL_68;
      }
      return 0;
    }
    v29 = v30;
    if ( v30 > 0xA )
      v29 = 10;
    if ( SectorSize * v29 > v21 )
      v29 = v21 / SectorSize;
    LODWORD(Size) = SectorSize * v29;
    if ( v34 == -1 )
    {
      memset_0(a2, 0, SectorSize * v29);
    }
    else
    {
      if ( !UDF_LVOL::Read(*((UDF_LVOL **)this + 4), *((_WORD *)this + 12), v34, v29, Heap) )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v18 = 18;
          goto LABEL_68;
        }
        return 0;
      }
      memcpy_0(a2, Heap, (unsigned int)Size);
    }
    v28 = (unsigned int)Size;
  }
  if ( !v21 )
    goto LABEL_77;
  if ( UDF_EXTENT_LIST::QueryLbnFromVbn(*i, a3 / v23, &v34, &v30) )
  {
    if ( v34 == -1 )
    {
      memset_0(a2, 0, v21);
    }
    else
    {
      if ( !UDF_LVOL::Read(*((UDF_LVOL **)this + 4), *((_WORD *)this + 12), v34, 1u, Heap) )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v18 = 20;
          goto LABEL_68;
        }
        return 0;
      }
      memcpy_0(a2, Heap, v21);
    }
LABEL_77:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    goto LABEL_78;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v18 = 19;
    goto LABEL_68;
  }
  return 0;
}

```

## disassembly

```asm
0x180063df0  push    rbp
0x180063df2  push    rbx
0x180063df3  push    rsi
0x180063df4  push    rdi
0x180063df5  push    r12
0x180063df7  push    r13
0x180063df9  push    r14
0x180063dfb  push    r15
0x180063dfd  mov     rbp, rsp
0x180063e00  sub     rsp, 58h
0x180063e04  mov     r12, [rcx+10h]
0x180063e08  mov     rdi, r8
0x180063e0b  mov     esi, r9d
0x180063e0e  mov     r14, rdx
0x180063e11  mov     r13, rcx
0x180063e14  mov     [rbp+var_28], 0
0x180063e1b  mov     dword ptr [rbp+Size], 0
0x180063e22  mov     al, [r12+22h]
0x180063e27  mov     rbx, [r12+38h]
0x180063e2c  and     al, 7
0x180063e2e  mov     [rbp+arg_0], 0
0x180063e35  cmp     al, 3
0x180063e37  jnz     short loc_180063E41
0x180063e39  xor     r15d, r15d
0x180063e3c  mov     rcx, rbx
0x180063e3f  jmp     short loc_180063E74
0x180063e41  mov     rcx, [rcx+20h]
0x180063e45  mov     rcx, [rcx+20h]; this
0x180063e49  call    ?QuerySectorSize@UDF_SA@@QEBAKXZ; UDF_SA::QuerySectorSize(void)
0x180063e4e  mov     rcx, [r13+28h]; this
0x180063e52  lea     rdx, [rbp+Size]; unsigned int *
0x180063e56  mov     r15d, eax
0x180063e59  call    ?QueryInformationLength@UDF_EXTENT_LIST@@QEBAEPEAK@Z; UDF_EXTENT_LIST::QueryInformationLength(ulong *)
0x180063e5e  test    al, al
0x180063e60  jz      loc_1800641F6
0x180063e66  mov     ecx, r15d
0x180063e69  imul    ecx, dword ptr [rbp+Size]
0x180063e6d  cmp     rcx, rbx
0x180063e70  cmova   rcx, rbx
0x180063e74  cmp     rbx, rdi
0x180063e77  ja      short loc_180063E7D
0x180063e79  xor     esi, esi
0x180063e7b  jmp     short loc_180063E8A
0x180063e7d  lea     rax, [rdi+rsi]
0x180063e81  cmp     rbx, rax
0x180063e84  jnb     short loc_180063E8A
0x180063e86  mov     esi, ebx
0x180063e88  sub     esi, edi
0x180063e8a  mov     rax, [r13+10h]
0x180063e8e  movzx   edx, word ptr [rax+22h]
0x180063e92  and     dx, 7
0x180063e96  cmp     dx, 3
0x180063e9a  jnz     short loc_180063ED8
0x180063e9c  mov     eax, 0A8h
0x180063ea1  mov     r8d, esi; Size
0x180063ea4  lea     r9d, [rax+5Dh]
0x180063ea8  cmp     [r12], r9w
0x180063ead  lea     ecx, [rax+28h]
0x180063eb0  lea     edx, [r9-55h]
0x180063eb4  cmovnz  eax, ecx
0x180063eb7  mov     ecx, [rax+r12]
0x180063ebb  lea     eax, [rdx+28h]
0x180063ebe  cmovnz  edx, eax
0x180063ec1  lea     rax, [r12+rcx]
0x180063ec5  mov     rcx, r14; void *
0x180063ec8  add     rdx, rax
0x180063ecb  add     rdx, rdi; Src
0x180063ece  call    memcpy_0
0x180063ed3  jmp     loc_180064285
0x180063ed8  cmp     dx, 2
0x180063edc  jb      short loc_180063F09
0x180063ede  mov     rcx, cs:WPP_GLOBAL_Control
0x180063ee5  lea     rax, WPP_GLOBAL_Control
0x180063eec  cmp     rcx, rax
0x180063eef  jz      loc_1800641F6
0x180063ef5  test    byte ptr [rcx+1Ch], 1
0x180063ef9  jz      loc_1800641F6
0x180063eff  mov     edx, 15h
0x180063f04  jmp     loc_1800641E6
0x180063f09  mov     edx, esi
0x180063f0b  cmp     rcx, rdi
0x180063f0e  ja      short loc_180063F2A
0x180063f10  mov     r8d, edx; Size
0x180063f13  mov     rcx, r14; void *
0x180063f16  xor     edx, edx; Val
0x180063f18  call    memset_0
0x180063f1d  mov     rcx, [rbp+arg_20]
0x180063f21  mov     [rcx], esi
0x180063f23  mov     al, 1
0x180063f25  jmp     loc_1800641F8
0x180063f2a  lea     rax, [rsi+rdi]
0x180063f2e  cmp     rcx, rax
0x180063f31  jnb     short loc_180063F51
0x180063f33  sub     ecx, edi
0x180063f35  mov     eax, esi
0x180063f37  sub     eax, ecx
0x180063f39  mov     ebx, ecx
0x180063f3b  mov     r12d, eax
0x180063f3e  add     rcx, r14; void *
0x180063f41  mov     r8d, eax; Size
0x180063f44  xor     edx, edx; Val
0x180063f46  mov     [rbp+Size], r12
0x180063f4a  call    memset_0
0x180063f4f  jmp     short loc_180063F5A
0x180063f51  mov     dword ptr [rbp+Size], 0
0x180063f58  mov     ebx, esi
0x180063f5a  test    ebx, ebx
0x180063f5c  jz      loc_180064285
0x180063f62  mov     rcx, gs:60h
0x180063f6b  lea     eax, [r15+r15*4]
0x180063f6f  lea     r8d, [rax+rax]; Size
0x180063f73  xor     edx, edx; Flags
0x180063f75  mov     rcx, [rcx+30h]; HeapHandle
0x180063f79  call    cs:__imp_RtlAllocateHeap
0x180063f7f  mov     r12, rax
0x180063f82  test    rax, rax
0x180063f85  jnz     short loc_180063FB2
0x180063f87  mov     rcx, cs:WPP_GLOBAL_Control
0x180063f8e  lea     rax, WPP_GLOBAL_Control
0x180063f95  cmp     rcx, rax
0x180063f98  jz      loc_1800641F6
0x180063f9e  test    byte ptr [rcx+1Ch], 1
0x180063fa2  jz      loc_1800641F6
0x180063fa8  lea     edx, [r12+0Eh]
0x180063fad  jmp     loc_1800641E6
0x180063fb2  xor     edx, edx
0x180063fb4  mov     ecx, r15d
0x180063fb7  mov     rax, rdi
0x180063fba  lea     r10, [r13+30h]
0x180063fbe  div     rcx
0x180063fc1  mov     [rbp+var_18], r10
0x180063fc5  mov     [rbp+var_10], rdx
0x180063fc9  mov     r8, rax
0x180063fcc  test    edx, edx
0x180063fce  jz      loc_1800640A8
0x180063fd4  mov     ecx, r15d
0x180063fd7  lea     r9, [rbp+var_28]; unsigned int *
0x180063fdb  sub     ecx, edx
0x180063fdd  mov     eax, esi
0x180063fdf  sub     eax, dword ptr [rbp+Size]
0x180063fe2  mov     edx, r8d; unsigned int
0x180063fe5  cmp     eax, ecx
0x180063fe7  lea     r8, [rbp+arg_0]; unsigned int *
0x180063feb  cmovnb  eax, ecx
0x180063fee  mov     rcx, [r10]; this
0x180063ff1  mov     dword ptr [rbp+Size], eax
0x180063ff4  call    ?QueryLbnFromVbn@UDF_EXTENT_LIST@@QEBAEKPEAK0@Z; UDF_EXTENT_LIST::QueryLbnFromVbn(ulong,ulong *,ulong *)
0x180063ff9  test    al, al
0x180063ffb  jnz     short loc_180064028
0x180063ffd  mov     rcx, cs:WPP_GLOBAL_Control
0x180064004  lea     rax, WPP_GLOBAL_Control
0x18006400b  cmp     rcx, rax
0x18006400e  jz      loc_1800641F6
0x180064014  test    byte ptr [rcx+1Ch], 1
0x180064018  jz      loc_1800641F6
0x18006401e  mov     edx, 0Fh
0x180064023  jmp     loc_1800641E6
0x180064028  mov     r8d, [rbp+arg_0]; unsigned int
0x18006402c  cmp     r8d, 0FFFFFFFFh
0x180064030  jnz     short loc_180064042
0x180064032  mov     r8d, dword ptr [rbp+Size]; Size
0x180064036  xor     edx, edx; Val
0x180064038  mov     rcx, r14; void *
0x18006403b  call    memset_0
0x180064040  jmp     short loc_18006409C
0x180064042  movzx   edx, word ptr [r13+18h]; unsigned __int16
0x180064047  mov     r9d, 1; unsigned int
0x18006404d  mov     rcx, [r13+20h]; this
0x180064051  mov     [rsp+58h+var_38], r12; void *
0x180064056  call    ?Read@UDF_LVOL@@QEAAEGKKPEAX@Z; UDF_LVOL::Read(ushort,ulong,ulong,void *)
0x18006405b  test    al, al
0x18006405d  jnz     short loc_18006408A
0x18006405f  mov     rcx, cs:WPP_GLOBAL_Control
0x180064066  lea     rax, WPP_GLOBAL_Control
0x18006406d  cmp     rcx, rax
0x180064070  jz      loc_1800641F6
0x180064076  test    byte ptr [rcx+1Ch], 1
0x18006407a  jz      loc_1800641F6
0x180064080  mov     edx, 10h
0x180064085  jmp     loc_1800641E6
0x18006408a  mov     edx, dword ptr [rbp+var_10]
0x18006408d  mov     rcx, r14; void *
0x180064090  mov     r8d, dword ptr [rbp+Size]; Size
0x180064094  add     rdx, r12; Src
0x180064097  call    memcpy_0
0x18006409c  mov     ecx, dword ptr [rbp+Size]
0x18006409f  lea     r10, [r13+30h]
0x1800640a3  jmp     loc_18006414D
0x1800640a8  mov     [rbp+var_18], r10
0x1800640ac  cmp     ebx, r15d
0x1800640af  jb      loc_1800641A1
0x1800640b5  xor     edx, edx
0x1800640b7  lea     r9, [rbp+var_28]; unsigned int *
0x1800640bb  mov     rax, rdi
0x1800640be  lea     r8, [rbp+arg_0]; unsigned int *
0x1800640c2  div     rcx
0x1800640c5  mov     rcx, [r10]; this
0x1800640c8  mov     rdx, rax; unsigned int
0x1800640cb  call    ?QueryLbnFromVbn@UDF_EXTENT_LIST@@QEBAEKPEAK0@Z; UDF_EXTENT_LIST::QueryLbnFromVbn(ulong,ulong *,ulong *)
0x1800640d0  test    al, al
0x1800640d2  jz      loc_180064181
0x1800640d8  mov     r9d, [rbp+var_28]
0x1800640dc  mov     eax, 0Ah
0x1800640e1  cmp     r9d, eax
0x1800640e4  cmova   r9d, eax
0x1800640e8  mov     eax, r9d
0x1800640eb  imul    eax, r15d
0x1800640ef  cmp     eax, ebx
0x1800640f1  jbe     short loc_1800640FD
0x1800640f3  xor     edx, edx
0x1800640f5  mov     eax, ebx
0x1800640f7  div     r15d
0x1800640fa  mov     r9d, eax; unsigned int
0x1800640fd  mov     r8d, [rbp+arg_0]; unsigned int
0x180064101  mov     eax, r9d
0x180064104  imul    eax, r15d
0x180064108  mov     dword ptr [rbp+Size], eax
0x18006410b  cmp     r8d, 0FFFFFFFFh
0x18006410f  jnz     short loc_180064120
0x180064111  mov     r8d, eax; Size
0x180064114  xor     edx, edx; Val
0x180064116  mov     rcx, r14; void *
0x180064119  call    memset_0
0x18006411e  jmp     short loc_180064146
0x180064120  movzx   edx, word ptr [r13+18h]; unsigned __int16
0x180064125  mov     rcx, [r13+20h]; this
0x180064129  mov     [rsp+58h+var_38], r12; void *
0x18006412e  call    ?Read@UDF_LVOL@@QEAAEGKKPEAX@Z; UDF_LVOL::Read(ushort,ulong,ulong,void *)
0x180064133  test    al, al
0x180064135  jz      short loc_18006415D
0x180064137  mov     r8d, dword ptr [rbp+Size]; Size
0x18006413b  mov     rdx, r12; Src
0x18006413e  mov     rcx, r14; void *
0x180064141  call    memcpy_0
0x180064146  mov     ecx, dword ptr [rbp+Size]
0x180064149  mov     r10, [rbp+var_18]
0x18006414d  sub     ebx, ecx
0x18006414f  add     r14, rcx
0x180064152  add     rdi, rcx
0x180064155  mov     ecx, r15d
0x180064158  jmp     loc_1800640AC
0x18006415d  mov     rcx, cs:WPP_GLOBAL_Control
0x180064164  lea     rax, WPP_GLOBAL_Control
0x18006416b  cmp     rcx, rax
0x18006416e  jz      loc_1800641F6
0x180064174  test    byte ptr [rcx+1Ch], 1
0x180064178  jz      short loc_1800641F6
0x18006417a  mov     edx, 12h
0x18006417f  jmp     short loc_1800641E6
0x180064181  mov     rcx, cs:WPP_GLOBAL_Control
0x180064188  lea     rax, WPP_GLOBAL_Control
0x18006418f  cmp     rcx, rax
0x180064192  jz      short loc_1800641F6
0x180064194  test    byte ptr [rcx+1Ch], 1
0x180064198  jz      short loc_1800641F6
0x18006419a  mov     edx, 11h
0x18006419f  jmp     short loc_1800641E6
0x1800641a1  test    ebx, ebx
0x1800641a3  jz      loc_18006426D
0x1800641a9  xor     edx, edx
0x1800641ab  lea     r9, [rbp+var_28]; unsigned int *
0x1800641af  mov     rax, rdi
0x1800641b2  lea     r8, [rbp+arg_0]; unsigned int *
0x1800641b6  div     rcx
0x1800641b9  mov     rcx, [r10]; this
0x1800641bc  mov     rdx, rax; unsigned int
0x1800641bf  call    ?QueryLbnFromVbn@UDF_EXTENT_LIST@@QEBAEKPEAK0@Z; UDF_EXTENT_LIST::QueryLbnFromVbn(ulong,ulong *,ulong *)
0x1800641c4  test    al, al
0x1800641c6  jnz     short loc_180064209
0x1800641c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800641cf  lea     rax, WPP_GLOBAL_Control
0x1800641d6  cmp     rcx, rax
0x1800641d9  jz      short loc_1800641F6
0x1800641db  test    byte ptr [rcx+1Ch], 1
0x1800641df  jz      short loc_1800641F6
0x1800641e1  mov     edx, 13h
0x1800641e6  mov     rcx, [rcx+10h]
0x1800641ea  lea     r8, WPP_5a183823c4533aac4dc0f098fe52d790_Traceguids
0x1800641f1  call    WPP_SF_
0x1800641f6  xor     al, al
0x1800641f8  add     rsp, 58h
0x1800641fc  pop     r15
0x1800641fe  pop     r14
0x180064200  pop     r13
0x180064202  pop     r12
0x180064204  pop     rdi
0x180064205  pop     rsi
0x180064206  pop     rbx
0x180064207  pop     rbp
0x180064208  retn
0x180064209  mov     r8d, [rbp+arg_0]; unsigned int
0x18006420d  cmp     r8d, 0FFFFFFFFh
0x180064211  jnz     short loc_180064222
0x180064213  mov     r8d, ebx; Size
0x180064216  xor     edx, edx; Val
0x180064218  mov     rcx, r14; void *
0x18006421b  call    memset_0
0x180064220  jmp     short loc_18006426D
0x180064222  movzx   edx, word ptr [r13+18h]; unsigned __int16
0x180064227  mov     r9d, 1; unsigned int
  ... truncated ...
```
