# CWaveIn::~CWaveIn(void)

- ea: `0x180003210`
- end: `0x180003301`
- name: `??1CWaveIn@@QEAA@XZ`
- size: `241`
- prototype: `void __fastcall(CWaveIn *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180005dd0`
- `0x1800061a0`

## callees

- `0x180001514`
- `0x180003210`
- `0x180007d50`

## pseudocode

```c
void __fastcall CWaveIn::~CWaveIn(CWaveIn *this)
{
  __int64 v1; // rbx
  _QWORD *v3; // rcx
  _QWORD *v4; // rdx
  CWaveArt *v5; // rcx

  v1 = *(_QWORD *)this;
  v3 = (_QWORD *)CWaveIn::m_sFreeList;
  if ( v1 )
  {
    v4 = (_QWORD *)v1;
    do
    {
      if ( *(__int64 *)(v1 + 8) >= 0x7FFFFFFF )
        break;
      if ( v4 )
      {
        *(_QWORD *)this = *v4;
        *v4 = 0;
      }
      *((_QWORD *)this + 1) = *(_QWORD *)(v1 + 8);
      *((_OWORD *)this + 1) = *(_OWORD *)(v1 + 16);
      *((_OWORD *)this + 2) = *(_OWORD *)(v1 + 32);
      *((_OWORD *)this + 3) = *(_OWORD *)(v1 + 48);
      *((_QWORD *)this + 8) = *(_QWORD *)(v1 + 64);
      v5 = *(CWaveArt **)(v1 + 64);
      if ( v5 )
      {
        if ( (*((_WORD *)v5 + 36))-- == 1 )
          CWaveArt::`scalar deleting destructor'(v5);
        *(_QWORD *)(v1 + 64) = 0;
      }
      v3 = (_QWORD *)v1;
      *(_QWORD *)v1 = CWaveIn::m_sFreeList;
      CWaveIn::m_sFreeList = v1;
      v1 = *(_QWORD *)this;
      v4 = *(_QWORD **)this;
    }
    while ( *(_QWORD *)this );
  }
  if ( !--CWaveIn::m_sUsageCount )
  {
    while ( v3 )
    {
      CWaveIn::m_sFreeList = *v3;
      *v3 = 0;
      operator delete(v3);
      v3 = (_QWORD *)CWaveIn::m_sFreeList;
    }
  }
}

```

## disassembly

```asm
0x180003210  push    rsi
0x180003212  sub     rsp, 20h
0x180003216  mov     [rsp+28h+arg_8], rbx
0x18000321b  xor     esi, esi
0x18000321d  mov     rbx, [rcx]
0x180003220  mov     [rsp+28h+arg_10], rbp
0x180003225  mov     [rsp+28h+arg_18], rdi
0x18000322a  mov     rdi, rcx
0x18000322d  mov     rcx, cs:?m_sFreeList@CWaveIn@@2VCWaveDataList@@A; CWaveDataList CWaveIn::m_sFreeList
0x180003234  test    rbx, rbx
0x180003237  jz      loc_1800032BE
0x18000323d  mov     rdx, rbx; unsigned int
0x180003240  mov     ebp, 0FFFFh
0x180003245  cmp     qword ptr [rbx+8], 7FFFFFFFh
0x18000324d  jge     short loc_1800032BE
0x18000324f  test    rdx, rdx
0x180003252  jz      short loc_18000325D
0x180003254  mov     rax, [rdx]
0x180003257  mov     [rdi], rax
0x18000325a  mov     [rdx], rsi
0x18000325d  mov     rax, [rbx+8]
0x180003261  mov     [rdi+8], rax
0x180003265  movups  xmm0, xmmword ptr [rbx+10h]
0x180003269  movups  xmmword ptr [rdi+10h], xmm0
0x18000326d  movups  xmm1, xmmword ptr [rbx+20h]
0x180003271  movups  xmmword ptr [rdi+20h], xmm1
0x180003275  movups  xmm0, xmmword ptr [rbx+30h]
0x180003279  movups  xmmword ptr [rdi+30h], xmm0
0x18000327d  movsd   xmm1, qword ptr [rbx+40h]
0x180003282  movsd   qword ptr [rdi+40h], xmm1
0x180003287  mov     rcx, [rbx+40h]; this
0x18000328b  test    rcx, rcx
0x18000328e  jz      short loc_18000329F
0x180003290  add     [rcx+48h], bp
0x180003294  jnz     short loc_18000329B
0x180003296  call    ??_GCWaveArt@@QEAAPEAXI@Z; CWaveArt::`scalar deleting destructor'(uint)
0x18000329b  mov     [rbx+40h], rsi
0x18000329f  mov     rax, cs:?m_sFreeList@CWaveIn@@2VCWaveDataList@@A; CWaveDataList CWaveIn::m_sFreeList
0x1800032a6  mov     rcx, rbx; void *
0x1800032a9  mov     [rbx], rax
0x1800032ac  mov     cs:?m_sFreeList@CWaveIn@@2VCWaveDataList@@A, rbx; CWaveDataList CWaveIn::m_sFreeList
0x1800032b3  mov     rbx, [rdi]
0x1800032b6  mov     rdx, rbx
0x1800032b9  test    rbx, rbx
0x1800032bc  jnz     short loc_180003245
0x1800032be  add     cs:?m_sUsageCount@CWaveIn@@0KA, 0FFFFFFFFh; ulong CWaveIn::m_sUsageCount
0x1800032c5  mov     rdi, [rsp+28h+arg_18]
0x1800032ca  mov     rbp, [rsp+28h+arg_10]
0x1800032cf  mov     rbx, [rsp+28h+arg_8]
0x1800032d4  jnz     short loc_1800032FB
0x1800032d6  test    rcx, rcx
0x1800032d9  jz      short loc_1800032FB
0x1800032db  mov     rax, [rcx]
0x1800032de  mov     edx, 48h ; 'H'; unsigned __int64
0x1800032e3  mov     cs:?m_sFreeList@CWaveIn@@2VCWaveDataList@@A, rax; CWaveDataList CWaveIn::m_sFreeList
0x1800032ea  mov     [rcx], rsi
0x1800032ed  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800032f2  mov     rcx, cs:?m_sFreeList@CWaveIn@@2VCWaveDataList@@A; CWaveDataList CWaveIn::m_sFreeList
0x1800032f9  jmp     short loc_1800032D6
0x1800032fb  add     rsp, 20h
0x1800032ff  pop     rsi
0x180003300  retn
```
