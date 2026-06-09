# GetObjectPath(CMDBaseObject *,BUFFER *,ulong *,CMDBaseObject *,int)

- ea: `0x18001e4c0`
- end: `0x18001e710`
- name: `?GetObjectPath@@YAJPEAVCMDBaseObject@@PEAVBUFFER@@PEAK0H@Z`
- size: `592`
- prototype: `__int64 __usercall@<rax>(struct CMDBaseObject *this@<rcx>, struct BUFFER *@<rdx>, unsigned int *@<r8>, struct CMDBaseObject *@<r9>, int)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180001ef4`
- `0x180014488`
- `0x18001870c`
- `0x18001919c`

## callees

- `0x180007810`
- `0x180013c4c`
- `0x18001e4c0`
- `0x18003098e`
- `0x1800309d0`

## import_xrefs

- `IisRTL!?Resize@BUFFER@@QEAA_NKK@Z` at `0x18001e5a3`
- `IisRTL!?Resize@BUFFER@@QEAA_NKK@Z` at `0x18001e5a3`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001e5f9`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18001e5f9`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x18001e525`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x18001e525`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x18001e6de`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x18001e6de`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001e5b2`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001e606`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001e6b0`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001e5b2`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001e606`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001e6b0`

## pseudocode

```c
__int64 __fastcall GetObjectPath(
        struct CMDBaseObject *this,
        struct BUFFER *a2,
        unsigned int *a3,
        struct CMDBaseObject *a4,
        int a5)
{
  struct CMDBaseObject *v7; // rbx
  int v9; // ebx
  unsigned int v10; // r15d
  _QWORD *Ptr; // rax
  _WORD *v12; // rdi
  int v13; // esi
  CMDBaseObject *v14; // rcx
  __int64 v15; // r15
  char *Name; // rax
  __int64 v17; // rbx
  unsigned int v18; // eax
  size_t Size; // [rsp+20h] [rbp-E0h] BYREF
  CMDBaseObject *v21; // [rsp+28h] [rbp-D8h] BYREF
  unsigned int *v22; // [rsp+30h] [rbp-D0h]
  _BYTE v23[48]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v24[512]; // [rsp+70h] [rbp-90h] BYREF
  int v25; // [rsp+270h] [rbp+170h]

  v22 = a3;
  v7 = this;
  v21 = this;
  LODWORD(Size) = 0;
  BUFFER::BUFFER((BUFFER *)v23, v24, 0x200u);
  v25 = 0;
  if ( v7 && a2 && a3 )
  {
    if ( v7 == a4 )
    {
      *a3 = 0;
LABEL_29:
      v9 = 0;
      goto LABEL_30;
    }
    v10 = (a5 != 0) + 1;
    while ( a4 != v7 )
    {
      if ( !v7 )
      {
        v9 = -2147467259;
        goto LABEL_30;
      }
      if ( !CMDBaseObject::GetName(v7, a5, (unsigned int *)&Size)
        || !BUFFER::Resize((BUFFER *)v23, 8 * v25 + 8, 8 * v25 + 8) )
      {
        goto LABEL_13;
      }
      Ptr = BUFFER::QueryPtr((BUFFER *)v23);
      Ptr[v25++] = v7;
      v7 = (struct CMDBaseObject *)*((_QWORD *)v7 + 23);
      v10 += (a5 != 0) + 1 + Size;
      v21 = v7;
    }
    if ( !BUFFER::Resize(a2, v10) )
    {
LABEL_13:
      v9 = -2147024882;
      goto LABEL_30;
    }
    v12 = BUFFER::QueryPtr(a2);
    v9 = STACK::Pop((STACK *)v23, (void **)&v21);
    if ( v9 >= 0 )
    {
      v13 = 2;
      while ( 1 )
      {
        v14 = v21;
        if ( !v21 )
          break;
        if ( a5 )
        {
          *v12 = 47;
          v15 = 2;
        }
        else
        {
          *(_BYTE *)v12 = 47;
          v15 = 1;
        }
        Name = CMDBaseObject::GetName(v14, a5, (unsigned int *)&Size);
        if ( !Name )
          goto LABEL_13;
        v17 = (unsigned int)Size;
        memcpy_0((char *)v12 + v15, Name, (unsigned int)Size);
        v12 = (_WORD *)((char *)v12 + v17 + v15);
        v9 = STACK::Pop((STACK *)v23, (void **)&v21);
        if ( v9 < 0 )
          goto LABEL_30;
      }
      if ( a5 )
      {
        *v12 = 0;
      }
      else
      {
        *(_BYTE *)v12 = 0;
        v13 = 1;
      }
      v18 = (unsigned int)BUFFER::QueryPtr(a2);
      *v22 = (unsigned __int64)((unsigned int)v12 + v13 - v18 - 1) >> (a5 != 0);
      goto LABEL_29;
    }
  }
  else
  {
    v9 = -2147024809;
  }
LABEL_30:
  v25 = 0;
  BUFFER::~BUFFER((BUFFER *)v23);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001e4c0  mov     [rsp-8+arg_18], rbx
0x18001e4c5  push    rbp
0x18001e4c6  push    rsi
0x18001e4c7  push    rdi
0x18001e4c8  push    r12
0x18001e4ca  push    r13
0x18001e4cc  push    r14
0x18001e4ce  push    r15
0x18001e4d0  lea     rbp, [rsp-190h]
0x18001e4d8  sub     rsp, 290h
0x18001e4df  mov     rax, cs:__security_cookie
0x18001e4e6  xor     rax, rsp
0x18001e4e9  mov     [rbp+1C0h+var_40], rax
0x18001e4f0  mov     r14d, [rbp+1C0h+arg_20]
0x18001e4f7  mov     rdi, r8
0x18001e4fa  mov     [rsp+2C0h+var_290], r8
0x18001e4ff  mov     r12, rdx
0x18001e502  mov     rbx, rcx
0x18001e505  mov     [rsp+2C0h+var_298], rcx
0x18001e50a  mov     r8d, 200h
0x18001e510  mov     dword ptr [rsp+2C0h+Size], 0
0x18001e518  lea     rdx, [rsp+2C0h+var_250]
0x18001e51d  mov     r13, r9
0x18001e520  lea     rcx, [rsp+2C0h+var_280]
0x18001e525  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x18001e52b  mov     [rbp+1C0h+var_50], 0
0x18001e535  test    rbx, rbx
0x18001e538  jnz     short loc_18001E544
0x18001e53a  mov     ebx, 80070057h
0x18001e53f  jmp     loc_18001E6CF
0x18001e544  test    r12, r12
0x18001e547  jz      short loc_18001E53A
0x18001e549  test    rdi, rdi
0x18001e54c  jz      short loc_18001E53A
0x18001e54e  cmp     rbx, r13
0x18001e551  jnz     short loc_18001E55E
0x18001e553  mov     dword ptr [rdi], 0
0x18001e559  jmp     loc_18001E6CD
0x18001e55e  mov     eax, r14d
0x18001e561  neg     eax
0x18001e563  sbb     edi, edi
0x18001e565  neg     edi
0x18001e567  inc     edi
0x18001e569  mov     r15d, edi
0x18001e56c  mov     rsi, rbx
0x18001e56f  cmp     r13, rbx
0x18001e572  jz      short loc_18001E5F3
0x18001e574  test    rbx, rbx
0x18001e577  jz      short loc_18001E5E9
0x18001e579  lea     r8, [rsp+2C0h+Size]; unsigned int *
0x18001e57e  mov     edx, r14d; int
0x18001e581  mov     rcx, rbx; this
0x18001e584  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x18001e589  test    rax, rax
0x18001e58c  jz      short loc_18001E5DF
0x18001e58e  mov     eax, [rbp+1C0h+var_50]
0x18001e594  lea     rcx, [rsp+2C0h+var_280]
0x18001e599  lea     edx, ds:8[rax*8]
0x18001e5a0  mov     r8d, edx
0x18001e5a3  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x18001e5a9  test    al, al
0x18001e5ab  jz      short loc_18001E5DF
0x18001e5ad  lea     rcx, [rsp+2C0h+var_280]
0x18001e5b2  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001e5b8  mov     ecx, [rbp+1C0h+var_50]
0x18001e5be  mov     [rax+rcx*8], rbx
0x18001e5c2  inc     [rbp+1C0h+var_50]
0x18001e5c8  mov     ecx, dword ptr [rsp+2C0h+Size]
0x18001e5cc  mov     rbx, [rbx+0B8h]
0x18001e5d3  add     ecx, edi
0x18001e5d5  add     r15d, ecx
0x18001e5d8  mov     [rsp+2C0h+var_298], rbx
0x18001e5dd  jmp     short loc_18001E56C
0x18001e5df  mov     ebx, 8007000Eh
0x18001e5e4  jmp     loc_18001E6CF
0x18001e5e9  mov     ebx, 80004005h
0x18001e5ee  jmp     loc_18001E6CF
0x18001e5f3  mov     edx, r15d
0x18001e5f6  mov     rcx, r12
0x18001e5f9  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18001e5ff  test    al, al
0x18001e601  jz      short loc_18001E5DF
0x18001e603  mov     rcx, r12
0x18001e606  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001e60c  lea     rdx, [rsp+2C0h+var_298]; void **
0x18001e611  mov     rdi, rax
0x18001e614  lea     rcx, [rsp+2C0h+var_280]; this
0x18001e619  call    ?Pop@STACK@@QEAAJPEAPEAX@Z; STACK::Pop(void * *)
0x18001e61e  mov     ebx, eax
0x18001e620  test    eax, eax
0x18001e622  js      loc_18001E6CF
0x18001e628  mov     esi, 2
0x18001e62d  lea     r13d, [rsi+2Dh]
0x18001e631  mov     rcx, [rsp+2C0h+var_298]; this
0x18001e636  test    rcx, rcx
0x18001e639  jz      short loc_18001E699
0x18001e63b  test    r14d, r14d
0x18001e63e  jz      short loc_18001E649
0x18001e640  mov     [rdi], r13w
0x18001e644  mov     r15, rsi
0x18001e647  jmp     short loc_18001E652
0x18001e649  mov     [rdi], r13b
0x18001e64c  mov     r15d, 1
0x18001e652  lea     r8, [rsp+2C0h+Size]; unsigned int *
0x18001e657  mov     edx, r14d; int
0x18001e65a  call    ?GetName@CMDBaseObject@@QEAAPEADHPEAK@Z; CMDBaseObject::GetName(int,ulong *)
0x18001e65f  test    rax, rax
0x18001e662  jz      loc_18001E5DF
0x18001e668  mov     ebx, dword ptr [rsp+2C0h+Size]
0x18001e66c  lea     rcx, [r15+rdi]; void *
0x18001e670  mov     r8d, ebx; Size
0x18001e673  mov     rdx, rax; Src
0x18001e676  call    memcpy_0
0x18001e67b  lea     rax, [rbx+r15]
0x18001e67f  lea     rdx, [rsp+2C0h+var_298]; void **
0x18001e684  add     rdi, rax
0x18001e687  lea     rcx, [rsp+2C0h+var_280]; this
0x18001e68c  call    ?Pop@STACK@@QEAAJPEAPEAX@Z; STACK::Pop(void * *)
0x18001e691  mov     ebx, eax
0x18001e693  test    eax, eax
0x18001e695  jns     short loc_18001E631
0x18001e697  jmp     short loc_18001E6CF
0x18001e699  test    r14d, r14d
0x18001e69c  jz      short loc_18001E6A5
0x18001e69e  xor     eax, eax
0x18001e6a0  mov     [rdi], ax
0x18001e6a3  jmp     short loc_18001E6AD
0x18001e6a5  mov     byte ptr [rdi], 0
0x18001e6a8  mov     esi, 1
0x18001e6ad  mov     rcx, r12
0x18001e6b0  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001e6b6  sub     esi, eax
0x18001e6b8  mov     rax, [rsp+2C0h+var_290]
0x18001e6bd  lea     edx, [rsi-1]
0x18001e6c0  add     edx, edi
0x18001e6c2  test    r14d, r14d
0x18001e6c5  setnz   cl
0x18001e6c8  shr     rdx, cl
0x18001e6cb  mov     [rax], edx
0x18001e6cd  xor     ebx, ebx
0x18001e6cf  lea     rcx, [rsp+2C0h+var_280]
0x18001e6d4  mov     [rbp+1C0h+var_50], 0
0x18001e6de  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18001e6e4  mov     eax, ebx
0x18001e6e6  mov     rcx, [rbp+1C0h+var_40]
0x18001e6ed  xor     rcx, rsp; StackCookie
0x18001e6f0  call    __security_check_cookie
0x18001e6f5  mov     rbx, [rsp+2C0h+arg_18]
0x18001e6fd  add     rsp, 290h
0x18001e704  pop     r15
0x18001e706  pop     r14
0x18001e708  pop     r13
0x18001e70a  pop     r12
0x18001e70c  pop     rdi
0x18001e70d  pop     rsi
0x18001e70e  pop     rbp
0x18001e70f  retn
```
