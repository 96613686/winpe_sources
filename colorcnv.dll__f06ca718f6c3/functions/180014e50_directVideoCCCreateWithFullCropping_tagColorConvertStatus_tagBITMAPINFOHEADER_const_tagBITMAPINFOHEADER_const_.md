# directVideoCCCreateWithFullCropping(tagColorConvertStatus *,tagBITMAPINFOHEADER const *,tagBITMAPINFOHEADER const *,long,long,long,long,long,long,long,int)

- ea: `0x180014e50`
- end: `0x1800150b4`
- name: `?directVideoCCCreateWithFullCropping@@YAPEAXPEAW4tagColorConvertStatus@@PEBUtagBITMAPINFOHEADER@@1JJJJJJJH@Z`
- size: `612`
- prototype: `struct DIRECTCOLORCONVFRM *__fastcall(enum tagColorConvertStatus *, const struct tagBITMAPINFOHEADER *, const struct tagBITMAPINFOHEADER *, int, int, int, int, LONG, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c8bc`

## callees

- `0x18000a6d0`
- `0x18000a71c`
- `0x18000f148`
- `0x180011650`
- `0x180014d84`
- `0x180014e50`
- `0x180029fc0`

## pseudocode

```c
struct DIRECTCOLORCONVFRM *__fastcall directVideoCCCreateWithFullCropping(
        enum tagColorConvertStatus *a1,
        const struct tagBITMAPINFOHEADER *a2,
        const struct tagBITMAPINFOHEADER *a3,
        int a4,
        int a5,
        int a6,
        int a7,
        LONG a8,
        int a9,
        int a10,
        unsigned int a11)
{
  int v14; // ebx
  LONG biHeight; // ecx
  LONG v16; // ecx
  struct tagBITMAPINFOHEADER *v17; // rax
  struct tagBITMAPINFOHEADER *v18; // r14
  struct tagBITMAPINFOHEADER *v19; // rax
  unsigned __int64 v20; // rdx
  struct tagBITMAPINFOHEADER *v21; // rdx
  int v22; // eax
  unsigned __int64 v23; // rdx
  struct DIRECTCOLORCONVFRM *v24; // rbx
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // rdx
  void *v28; // rcx
  size_t Size; // [rsp+30h] [rbp-28h] BYREF
  struct tagBITMAPINFOHEADER *v30; // [rsp+38h] [rbp-20h] BYREF
  size_t v31[3]; // [rsp+40h] [rbp-18h] BYREF

  if ( a4 < 0 )
    goto LABEL_35;
  if ( a5 < 0 )
    goto LABEL_35;
  if ( a8 < 0 )
    goto LABEL_35;
  v14 = a9;
  if ( a9 < 0 || a6 < 0 || a7 < 0 || a8 + a4 > a2->biWidth )
    goto LABEL_35;
  biHeight = -a2->biHeight;
  if ( a2->biHeight > 0 )
    biHeight = a2->biHeight;
  if ( a9 + a5 > biHeight || a6 + a8 > a3->biWidth )
    goto LABEL_35;
  v16 = -a3->biHeight;
  if ( a3->biHeight > 0 )
    v16 = a3->biHeight;
  if ( a7 + a9 > v16 )
  {
LABEL_35:
    *(_DWORD *)a1 = 1;
  }
  else
  {
    a11 = 0;
    LODWORD(v30) = 0;
    LODWORD(Size) = 0;
    LODWORD(v31[0]) = 0;
    if ( (unsigned int)ComputeBitMapInfoHeaderSize(a2, (unsigned int *)&Size, &a11) )
    {
      if ( (unsigned int)ComputeBitMapInfoHeaderSize(a3, (unsigned int *)v31, (unsigned int *)&v30) )
      {
        v17 = (struct tagBITMAPINFOHEADER *)operator new[](a11);
        v18 = v17;
        if ( v17 )
        {
          memcpy_0(v17, a2, (unsigned int)Size);
          v19 = (struct tagBITMAPINFOHEADER *)operator new[]((unsigned int)v30);
          v30 = v19;
          if ( v19 )
          {
            memcpy_0(v19, a3, LODWORD(v31[0]));
            v21 = v30;
            v18->biWidth = a8;
            v22 = a9;
            v21->biWidth = a8;
            if ( a2->biHeight <= 0 )
              v22 = -a9;
            v18->biHeight = v22;
            if ( a3->biHeight <= 0 )
              v14 = -a9;
            v21->biHeight = v14;
            v24 = directVideoCCCreate(a1, v18, v21, a10);
            if ( v24 )
            {
              operator delete(v18, v23);
              operator delete(v30, v25);
              if ( !*(_DWORD *)a1 )
              {
                *((_DWORD *)v24 + 3826) = a4;
                *((_DWORD *)v24 + 3828) = a6;
                *((_DWORD *)v24 + 3829) = a7;
                *((_DWORD *)v24 + 3821) = 1;
                *((_DWORD *)v24 + 3827) = a5;
                ReSetSequencePointers(v24, a2->biWidth, a2->biHeight, a3->biWidth, a3->biHeight);
                return v24;
              }
              if ( *(_QWORD *)v24 )
              {
                operator delete(*(void **)v24, v26);
                *(_QWORD *)v24 = 0;
              }
              v28 = (void *)*((_QWORD *)v24 + 1);
              if ( v28 )
              {
                operator delete(v28, v26);
                *((_QWORD *)v24 + 1) = 0;
              }
              operator delete(v24, 0x3C58u);
            }
          }
          else
          {
            *(_DWORD *)a1 = 2;
            operator delete(v18, v20);
          }
        }
        else
        {
          *(_DWORD *)a1 = 2;
        }
      }
      else
      {
        *(_DWORD *)a1 = 4;
      }
    }
    else
    {
      *(_DWORD *)a1 = 3;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180014e50  mov     [rsp-40h+arg_18], r9d
0x180014e55  push    rbp
0x180014e56  push    rbx
0x180014e57  push    rsi
0x180014e58  push    rdi
0x180014e59  push    r12
0x180014e5b  push    r13
0x180014e5d  push    r14
0x180014e5f  push    r15
0x180014e61  mov     rbp, rsp
0x180014e64  sub     rsp, 58h
0x180014e68  xor     r14d, r14d
0x180014e6b  mov     eax, r9d
0x180014e6e  mov     r15, r8
0x180014e71  mov     rsi, rdx
0x180014e74  mov     rdi, rcx
0x180014e77  test    r9d, r9d
0x180014e7a  js      loc_18001509B
0x180014e80  mov     r13d, [rbp+arg_20]
0x180014e84  test    r13d, r13d
0x180014e87  js      loc_18001509B
0x180014e8d  mov     r12d, [rbp+arg_38]
0x180014e94  test    r12d, r12d
0x180014e97  js      loc_18001509B
0x180014e9d  mov     ebx, [rbp+arg_40]
0x180014ea3  test    ebx, ebx
0x180014ea5  js      loc_18001509B
0x180014eab  mov     edx, [rbp+arg_28]
0x180014eae  test    edx, edx
0x180014eb0  js      loc_18001509B
0x180014eb6  mov     r8d, [rbp+arg_30]
0x180014eba  test    r8d, r8d
0x180014ebd  js      loc_18001509B
0x180014ec3  add     eax, r12d
0x180014ec6  cmp     eax, [rsi+4]
0x180014ec9  jg      loc_18001509B
0x180014ecf  mov     ecx, [rsi+8]
0x180014ed2  lea     eax, [rbx+r13]
0x180014ed6  neg     ecx
0x180014ed8  cmovs   ecx, [rsi+8]
0x180014edc  cmp     eax, ecx
0x180014ede  jg      loc_18001509B
0x180014ee4  lea     eax, [rdx+r12]
0x180014ee8  cmp     eax, [r15+4]
0x180014eec  jg      loc_18001509B
0x180014ef2  mov     ecx, [r15+8]
0x180014ef6  lea     eax, [r8+rbx]
0x180014efa  neg     ecx
0x180014efc  cmovs   ecx, [r15+8]
0x180014f01  cmp     eax, ecx
0x180014f03  jg      loc_18001509B
0x180014f09  lea     r8, [rbp+arg_50]; unsigned int *
0x180014f10  mov     [rbp+arg_50], r14d
0x180014f17  lea     rdx, [rbp+Size]; unsigned int *
0x180014f1b  mov     dword ptr [rbp+var_20], r14d
0x180014f1f  mov     rcx, rsi; struct tagBITMAPINFOHEADER *
0x180014f22  mov     dword ptr [rbp+Size], r14d
0x180014f26  mov     dword ptr [rbp+var_18], r14d
0x180014f2a  call    ?ComputeBitMapInfoHeaderSize@@YAHPEBUtagBITMAPINFOHEADER@@PEAI1@Z; ComputeBitMapInfoHeaderSize(tagBITMAPINFOHEADER const *,uint *,uint *)
0x180014f2f  test    eax, eax
0x180014f31  jnz     short loc_180014F3E
0x180014f33  mov     dword ptr [rdi], 3
0x180014f39  jmp     loc_1800150A1
0x180014f3e  lea     r8, [rbp+var_20]; unsigned int *
0x180014f42  mov     rcx, r15; struct tagBITMAPINFOHEADER *
0x180014f45  lea     rdx, [rbp+var_18]; unsigned int *
0x180014f49  call    ?ComputeBitMapInfoHeaderSize@@YAHPEBUtagBITMAPINFOHEADER@@PEAI1@Z; ComputeBitMapInfoHeaderSize(tagBITMAPINFOHEADER const *,uint *,uint *)
0x180014f4e  test    eax, eax
0x180014f50  jnz     short loc_180014F5D
0x180014f52  mov     dword ptr [rdi], 4
0x180014f58  jmp     loc_1800150A1
0x180014f5d  mov     ecx, [rbp+arg_50]; unsigned __int64
0x180014f63  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014f68  mov     r14, rax
0x180014f6b  test    rax, rax
0x180014f6e  jnz     short loc_180014F7B
0x180014f70  mov     dword ptr [rdi], 2
0x180014f76  jmp     loc_1800150A1
0x180014f7b  mov     r8d, dword ptr [rbp+Size]; Size
0x180014f7f  mov     rdx, rsi; Src
0x180014f82  mov     rcx, r14; void *
0x180014f85  call    memcpy_0
0x180014f8a  mov     ecx, dword ptr [rbp+var_20]; unsigned __int64
0x180014f8d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014f92  mov     [rbp+var_20], rax
0x180014f96  test    rax, rax
0x180014f99  jnz     short loc_180014FAE
0x180014f9b  mov     dword ptr [rdi], 2
0x180014fa1  mov     rcx, r14; void *
0x180014fa4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014fa9  jmp     loc_1800150A1
0x180014fae  mov     r8d, dword ptr [rbp+var_18]; Size
0x180014fb2  mov     rdx, r15; Src
0x180014fb5  mov     rcx, rax; void *
0x180014fb8  call    memcpy_0
0x180014fbd  mov     rdx, [rbp+var_20]
0x180014fc1  mov     ecx, ebx
0x180014fc3  mov     r9d, [rbp+arg_48]; int
0x180014fca  neg     ecx
0x180014fcc  mov     [r14+4], r12d
0x180014fd0  mov     eax, ebx
0x180014fd2  mov     r8, rdx; struct tagBITMAPINFOHEADER *
0x180014fd5  mov     [rdx+4], r12d
0x180014fd9  xor     r12d, r12d
0x180014fdc  cmp     [rsi+8], r12d
0x180014fe0  cmovle  eax, ecx
0x180014fe3  mov     [r14+8], eax
0x180014fe7  cmp     [r15+8], r12d
0x180014feb  cmovle  ebx, ecx
0x180014fee  mov     rcx, rdi; enum tagColorConvertStatus *
0x180014ff1  mov     [rdx+8], ebx
0x180014ff4  mov     rdx, r14; struct tagBITMAPINFOHEADER *
0x180014ff7  call    ?directVideoCCCreate@@YAPEAXPEAW4tagColorConvertStatus@@PEBUtagBITMAPINFOHEADER@@1JH@Z; directVideoCCCreate(tagColorConvertStatus *,tagBITMAPINFOHEADER const *,tagBITMAPINFOHEADER const *,long,int)
0x180014ffc  mov     rbx, rax
0x180014fff  test    rax, rax
0x180015002  jz      loc_1800150A1
0x180015008  mov     rcx, r14; void *
0x18001500b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015010  mov     rcx, [rbp+var_20]; void *
0x180015014  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015019  cmp     [rdi], r12d
0x18001501c  jnz     short loc_18001506A
0x18001501e  mov     eax, [rbp+arg_18]
0x180015021  mov     rcx, rbx; struct DIRECTCOLORCONVFRM *
0x180015024  mov     [rbx+3BC8h], eax
0x18001502a  mov     eax, [rbp+arg_28]
0x18001502d  mov     [rbx+3BD0h], eax
0x180015033  mov     eax, [rbp+arg_30]
0x180015036  mov     [rbx+3BD4h], eax
0x18001503c  mov     dword ptr [rbx+3BB4h], 1
0x180015046  mov     [rbx+3BCCh], r13d
0x18001504d  mov     eax, [r15+8]
0x180015051  mov     r9d, [r15+4]; int
0x180015055  mov     r8d, [rsi+8]; int
0x180015059  mov     edx, [rsi+4]; int
0x18001505c  mov     [rsp+58h+var_38], eax; int
0x180015060  call    ?ReSetSequencePointers@@YAXPEAUDIRECTCOLORCONVFRM@@JJJJ@Z; ReSetSequencePointers(DIRECTCOLORCONVFRM *,long,long,long,long)
0x180015065  mov     rax, rbx
0x180015068  jmp     short loc_1800150A3
0x18001506a  mov     rcx, [rbx]; void *
0x18001506d  test    rcx, rcx
0x180015070  jz      short loc_18001507A
0x180015072  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015077  mov     [rbx], r12
0x18001507a  mov     rcx, [rbx+8]; void *
0x18001507e  test    rcx, rcx
0x180015081  jz      short loc_18001508C
0x180015083  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015088  mov     [rbx+8], r12
0x18001508c  mov     edx, 3C58h; unsigned __int64
0x180015091  mov     rcx, rbx; void *
0x180015094  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015099  jmp     short loc_1800150A1
0x18001509b  mov     dword ptr [rdi], 1
0x1800150a1  xor     eax, eax
0x1800150a3  add     rsp, 58h
0x1800150a7  pop     r15
0x1800150a9  pop     r14
0x1800150ab  pop     r13
0x1800150ad  pop     r12
0x1800150af  pop     rdi
0x1800150b0  pop     rsi
0x1800150b1  pop     rbx
0x1800150b2  pop     rbp
0x1800150b3  retn
```
