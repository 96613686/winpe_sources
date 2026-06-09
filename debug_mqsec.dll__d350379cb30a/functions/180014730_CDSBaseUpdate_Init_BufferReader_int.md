# CDSBaseUpdate::Init(BufferReader *,int)

- ea: `0x180014730`
- end: `0x18001491d`
- name: `?Init@CDSBaseUpdate@@QEAAJPEAVBufferReader@@H@Z`
- size: `493`
- prototype: `__int64 __fastcall(CDSBaseUpdate *__hidden this, struct BufferReader *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180014730`
- `0x180014c50`
- `0x18001513c`
- `0x1800151d0`
- `0x18001722c`

## import_xrefs

- `msvcrt!free` at `0x1800147ce`
- `msvcrt!free` at `0x1800148bd`
- `msvcrt!free` at `0x1800148c7`
- `msvcrt!free` at `0x1800148eb`
- `msvcrt!free` at `0x1800148f4`
- `msvcrt!free` at `0x1800147ce`
- `msvcrt!free` at `0x1800148bd`
- `msvcrt!free` at `0x1800148c7`
- `msvcrt!free` at `0x1800148eb`
- `msvcrt!free` at `0x1800148f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDSBaseUpdate::Init(CDSBaseUpdate *this, struct BufferReader *a2, int a3)
{
  int v6; // eax
  void *v7; // r14
  unsigned __int8 *v8; // r12
  unsigned __int64 v9; // rbx
  void *v10; // r15
  struct tagPROPVARIANT *v11; // rbx
  unsigned int i; // r14d
  int inited; // r13d
  __int64 result; // rax
  void *v15; // [rsp+50h] [rbp+8h] BYREF
  struct tagPROPVARIANT *v16; // [rsp+68h] [rbp+20h]

  *((_DWORD *)this + 23) = 1;
  try
  {
    BufferReader::ReadBytes(a2, this, 1u);
    LOBYTE(v15) = 0;
    BufferReader::ReadBytes(a2, &v15, 1u);
    v6 = (unsigned __int8)v15;
    *((_DWORD *)this + 22) = (unsigned __int8)v15;
    if ( v6 )
    {
      *((_QWORD *)this + 6) = 0;
      v7 = MmAllocate(0x10u);
      v15 = v7;
      BufferReader::ReadBytes(a2, v7, 0x10u);
      *((_QWORD *)this + 10) = v7;
      free(0);
    }
    else
    {
      *((_QWORD *)this + 10) = 0;
      BufferReader::ReadNullTerminated(a2, (wchar_t **)this + 6);
    }
    BufferReader::ReadBytes(a2, (char *)this + 4, 0x10u);
    BufferReader::ReadBytes(a2, (char *)this + 20, 8u);
    BufferReader::ReadBytes(a2, (char *)this + 32, 8u);
    BufferReader::ReadBytes(a2, (char *)this + 40, 8u);
    v8 = (unsigned __int8 *)this + 56;
    BufferReader::ReadBytes(a2, (char *)this + 56, 1u);
    v9 = (unsigned int)*((unsigned __int8 *)this + 56) + 2;
    if ( !a3 )
      v9 = *((unsigned __int8 *)this + 56);
    v10 = MmAllocate(saturated_mul(v9, 4u));
    v15 = v10;
    BufferReader::ReadBytes(a2, v10, 4LL * *v8);
    v11 = (struct tagPROPVARIANT *)MmAllocate(saturated_mul(v9, 0x18u));
    v16 = v11;
    for ( i = 0; i < *v8; ++i )
    {
      inited = CDSBaseUpdate::InitProperty(this, a2, *((_DWORD *)v10 + i), &v11[i]);
      if ( inited < 0 )
      {
        free(v11);
        free(v10);
        return (unsigned int)inited;
      }
    }
    v15 = 0;
    *((_QWORD *)this + 8) = v10;
    *((_QWORD *)this + 9) = v11;
    free(0);
    free(0);
    result = 0;
  }
  catch ( std::range_error )
  {
    return 3222143015LL;
  }
  return result;
}

```

## disassembly

```asm
0x180014730  mov     [rsp+arg_8], rbx
0x180014735  mov     [rsp+arg_10], rsi
0x18001473a  push    rdi
0x18001473b  push    r12
0x18001473d  push    r13
0x18001473f  push    r14
0x180014741  push    r15
0x180014743  sub     rsp, 20h
0x180014747  mov     r15d, r8d
0x18001474a  mov     rsi, rdx
0x18001474d  mov     rdi, rcx
0x180014750  mov     r14d, 1
0x180014756  mov     [rcx+5Ch], r14d
0x18001475a  mov     r8d, r14d; unsigned __int64
0x18001475d  mov     rdx, rcx; void *
0x180014760  mov     rcx, rsi; this
0x180014763  call    ?ReadBytes@BufferReader@@QEAAXPEAX_K@Z; BufferReader::ReadBytes(void *,unsigned __int64)
0x180014768  xor     r13d, r13d
0x18001476b  mov     byte ptr [rsp+48h+arg_0], r13b
0x180014770  mov     r8d, r14d; unsigned __int64
0x180014773  lea     rdx, [rsp+48h+arg_0]; void *
0x180014778  mov     rcx, rsi; this
0x18001477b  call    ?ReadBytes@BufferReader@@QEAAXPEAX_K@Z; BufferReader::ReadBytes(void *,unsigned __int64)
0x180014780  movzx   eax, byte ptr [rsp+48h+arg_0]
0x180014785  mov     [rdi+58h], eax
0x180014788  test    eax, eax
0x18001478a  jnz     short loc_1800147A2
0x18001478c  mov     [rdi+50h], r13
0x180014790  lea     rdx, [rdi+30h]; wchar_t **
0x180014794  mov     rcx, rsi; this
0x180014797  call    ?ReadNullTerminated@BufferReader@@QEAAXPEAPEA_W@Z; BufferReader::ReadNullTerminated(wchar_t * *)
0x18001479c  lea     ebx, [r14+0Fh]
0x1800147a0  jmp     short loc_1800147D9
0x1800147a2  mov     [rdi+30h], r13
0x1800147a6  mov     ebx, 10h
0x1800147ab  mov     ecx, ebx; unsigned __int64
0x1800147ad  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800147b2  mov     r14, rax
0x1800147b5  mov     [rsp+48h+arg_0], rax
0x1800147ba  mov     r8d, ebx; unsigned __int64
0x1800147bd  mov     rdx, rax; void *
0x1800147c0  mov     rcx, rsi; this
0x1800147c3  call    ?ReadBytes@BufferReader@@QEAAXPEAX_K@Z; BufferReader::ReadBytes(void *,unsigned __int64)
0x1800147c8  mov     [rdi+50h], r14
0x1800147cc  xor     ecx, ecx; Block
0x1800147ce  call    cs:__imp_free
0x1800147d4  nop
0x1800147d5  lea     r14d, [rbx-0Fh]
0x1800147d9  lea     rdx, [rdi+4]; void *
0x1800147dd  mov     r8, rbx; unsigned __int64
0x1800147e0  mov     rcx, rsi; this
0x1800147e3  call    ?ReadBytes@BufferReader@@QEAAXPEAX_K@Z; BufferReader::ReadBytes(void *,unsigned __int64)
0x1800147e8  lea     rdx, [rdi+14h]; void *
0x1800147ec  mov     ebx, 8
0x1800147f1  mov     r8d, ebx; unsigned __int64
0x1800147f4  mov     rcx, rsi; this
0x1800147f7  call    ?ReadBytes@BufferReader@@QEAAXPEAX_K@Z; BufferReader::ReadBytes(void *,unsigned __int64)
0x1800147fc  lea     rdx, [rdi+20h]; void *
0x180014800  mov     r8d, ebx; unsigned __int64
0x180014803  mov     rcx, rsi; this
0x180014806  call    ?ReadBytes@BufferReader@@QEAAXPEAX_K@Z; BufferReader::ReadBytes(void *,unsigned __int64)
0x18001480b  lea     rdx, [rdi+28h]; void *
0x18001480f  mov     r8d, ebx; unsigned __int64
0x180014812  mov     rcx, rsi; this
0x180014815  call    ?ReadBytes@BufferReader@@QEAAXPEAX_K@Z; BufferReader::ReadBytes(void *,unsigned __int64)
0x18001481a  lea     r12, [rdi+38h]
0x18001481e  mov     r8, r14; unsigned __int64
0x180014821  mov     rdx, r12; void *
0x180014824  mov     rcx, rsi; this
0x180014827  call    ?ReadBytes@BufferReader@@QEAAXPEAX_K@Z; BufferReader::ReadBytes(void *,unsigned __int64)
0x18001482c  movzx   ecx, byte ptr [r12]
0x180014831  lea     ebx, [rcx+2]
0x180014834  test    r15d, r15d
0x180014837  cmovz   ebx, ecx
0x18001483a  mov     eax, 4
0x18001483f  mul     rbx
0x180014842  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180014849  cmovb   rax, r14
0x18001484d  mov     rcx, rax; unsigned __int64
0x180014850  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180014855  mov     r15, rax
0x180014858  mov     [rsp+48h+arg_0], rax
0x18001485d  movzx   r8d, byte ptr [r12]
0x180014862  shl     r8, 2; unsigned __int64
0x180014866  mov     rdx, rax; void *
0x180014869  mov     rcx, rsi; this
0x18001486c  call    ?ReadBytes@BufferReader@@QEAAXPEAX_K@Z; BufferReader::ReadBytes(void *,unsigned __int64)
0x180014871  lea     eax, [r14+19h]
0x180014875  mul     rbx
0x180014878  cmovb   rax, r14
0x18001487c  mov     rcx, rax; unsigned __int64
0x18001487f  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180014884  mov     rbx, rax
0x180014887  mov     [rsp+48h+arg_18], rax
0x18001488c  mov     r14d, r13d
0x18001488f  movzx   eax, byte ptr [r12]
0x180014894  cmp     r14d, eax
0x180014897  jnb     short loc_1800148D8
0x180014899  mov     r8d, r14d
0x18001489c  lea     rax, [r8+r8*2]
0x1800148a0  lea     r9, [rbx+rax*8]; struct tagPROPVARIANT *
0x1800148a4  mov     r8d, [r15+r8*4]; unsigned int
0x1800148a8  mov     rdx, rsi; struct BufferReader *
0x1800148ab  mov     rcx, rdi; this
0x1800148ae  call    ?InitProperty@CDSBaseUpdate@@AEAAJPEAVBufferReader@@KAEAUtagPROPVARIANT@@@Z; CDSBaseUpdate::InitProperty(BufferReader *,ulong,tagPROPVARIANT &)
0x1800148b3  mov     r13d, eax
0x1800148b6  test    eax, eax
0x1800148b8  jns     short loc_1800148D3
0x1800148ba  mov     rcx, rbx; Block
0x1800148bd  call    cs:__imp_free
0x1800148c3  nop
0x1800148c4  mov     rcx, r15; Block
0x1800148c7  call    cs:__imp_free
0x1800148cd  nop
0x1800148ce  mov     eax, r13d
0x1800148d1  jmp     short loc_180014904
0x1800148d3  inc     r14d
0x1800148d6  jmp     short loc_18001488F
0x1800148d8  mov     [rsp+48h+arg_0], 0
0x1800148e1  mov     [rdi+40h], r15
0x1800148e5  mov     [rdi+48h], rbx
0x1800148e9  xor     ecx, ecx; Block
0x1800148eb  call    cs:__imp_free
0x1800148f1  nop
0x1800148f2  xor     ecx, ecx; Block
0x1800148f4  call    cs:__imp_free
0x1800148fa  nop
0x1800148fb  xor     eax, eax
0x1800148fd  jmp     short loc_180014904
0x1800148ff  mov     eax, 0C00E0027h
0x180014904  mov     rbx, [rsp+48h+arg_8]
0x180014909  mov     rsi, [rsp+48h+arg_10]
0x18001490e  add     rsp, 20h
0x180014912  pop     r15
0x180014914  pop     r14
0x180014916  pop     r13
0x180014918  pop     r12
0x18001491a  pop     rdi
0x18001491b  retn
```
