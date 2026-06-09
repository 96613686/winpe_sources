# CTxtRange::Delete(long,long,long *)

- ea: `0x180089fe0`
- end: `0x18008a262`
- name: `?Delete@CTxtRange@@UEAAJJJPEAJ@Z`
- size: `642`
- prototype: `__int64 __fastcall(CTxtRange *__hidden this, int, int, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x18004a97c`

## callees

- `0x18000fe40`
- `0x180010260`
- `0x180016700`
- `0x18002a6f0`
- `0x18002a790`
- `0x18002ac10`
- `0x18002af90`
- `0x18003ca50`
- `0x18003cc90`
- `0x18004b874`
- `0x180089fe0`
- `0x18008b588`
- `0x180095010`

## pseudocode

```c
__int64 __fastcall CTxtRange::Delete(CTxtRange *this, unsigned int a2, int a3, int *a4)
{
  int v4; // edi
  struct CTxtEdit *v8; // rdx
  unsigned int v10; // edi
  int AdjustedTextLength; // eax
  unsigned int v12; // esi
  int v13; // r12d
  bool v14; // zf
  unsigned int v15; // ecx
  int v16; // edx
  unsigned int v17; // r13d
  __int64 v18; // r8
  int v19; // r12d
  struct CTxtEdit *v20; // rdx
  struct IUndoBuilder *v21; // rsi
  int v22; // ecx
  int v23; // [rsp+40h] [rbp-59h] BYREF
  int v24; // [rsp+44h] [rbp-55h]
  _BYTE v25[40]; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v26[128]; // [rsp+70h] [rbp-29h] BYREF
  struct IUndoBuilder *v27; // [rsp+100h] [rbp+67h] BYREF
  unsigned int v28; // [rsp+108h] [rbp+6Fh]
  int v29; // [rsp+118h] [rbp+7Fh] BYREF

  v28 = a2;
  v4 = 0;
  if ( a4 )
    *a4 = 0;
  v8 = (struct CTxtEdit *)*((_QWORD *)this + 6);
  if ( !v8 )
    return 2147746303LL;
  CCallMgr::CCallMgr((CCallMgr *)v25, v8);
  if ( !(unsigned int)CTxtRange::WriteAccessDenied(this) )
  {
    v24 = *((_DWORD *)this + 22);
    AdjustedTextLength = CTxtRange::GetAdjustedTextLength(this);
    v23 = 0;
    v29 = 0;
    LODWORD(v27) = 0;
    v12 = ((a3 >> 31) & 0xFFFFFFFE) + 1;
    v13 = AdjustedTextLength;
    CTxtRange::GetRange(this, &v23, &v29);
    if ( v29 <= v13 )
    {
      v14 = a3 == 0;
    }
    else
    {
      CTxtRange::Set(this, v23, v23 - v13);
      v14 = a3 == 0;
      if ( a3 > 0 )
      {
        v15 = *((_DWORD *)this + 22) != 0 ? v12 : 0;
        goto LABEL_24;
      }
    }
    if ( !v14 )
    {
      v16 = *((_DWORD *)this + 22);
      if ( ((v16 ^ v12) & 0x80000000) != 0 )
      {
        CRchTxtPtr::Advance((CTxtRange *)((char *)this + 8), -v16);
        *((_DWORD *)this + 22) = -*((_DWORD *)this + 22);
      }
      v17 = v28;
      v18 = a3 - v12;
      if ( !v24 )
        v18 = (unsigned int)a3;
      v10 = -2147024809;
      if ( (unsigned int)CTxtRange::Mover(this, v28, v18, &v27, v12) == -2147024809 )
      {
        if ( a4 )
          *a4 = 0;
        goto LABEL_45;
      }
      v4 = (int)v27;
      if ( *((_DWORD *)this + 10) > v13 && (int)v27 > 0 )
      {
        if ( v17 != 1 )
        {
          v15 = ((a3 >> 31) & 0xFFFFFFFE) + 1;
          if ( v17 == 2 )
            v4 = (_DWORD)v27 - 1;
LABEL_24:
          v19 = v24;
          if ( v24 )
            v4 += v15;
          if ( a4 )
            *a4 = v4;
          if ( *((_DWORD *)this + 22) )
          {
            v20 = (struct CTxtEdit *)*((_QWORD *)this + 6);
            v27 = 0;
            CGenUndoBuilder::CGenUndoBuilder((CGenUndoBuilder *)v26, v20, 1u, &v27);
            v21 = v27;
            if ( v27 )
            {
              (*(void (__fastcall **)(struct IUndoBuilder *))(*(_QWORD *)v27 + 48LL))(v27);
              (**(void (__fastcall ***)(struct IUndoBuilder *, __int64))v21)(v21, 2);
            }
            if ( (*((_BYTE *)this + 98) & 2) == 0 || v19 )
              v22 = 1;
            else
              v22 = (a3 <= 0) + 2;
            (*(void (__fastcall **)(CTxtRange *, _QWORD, _QWORD, struct IUndoBuilder *, int, _QWORD, _DWORD))(*(_QWORD *)this + 560LL))(
              this,
              0,
              0,
              v21,
              v22,
              0,
              0);
            if ( v4 == a3 || v4 == 1 && !a3 )
            {
              CGenUndoBuilder::~CGenUndoBuilder((CGenUndoBuilder *)v26);
              v10 = 0;
              goto LABEL_45;
            }
            CGenUndoBuilder::~CGenUndoBuilder((CGenUndoBuilder *)v26);
          }
          else if ( v19 )
          {
            (*(void (__fastcall **)(CTxtRange *, __int64))(*(_QWORD *)this + 568LL))(this, 1);
          }
          v10 = 1;
          goto LABEL_45;
        }
        v4 += v13 - CTxtPtr::GetTextLength((CTxtRange *)((char *)this + 24));
      }
    }
    v15 = ((a3 >> 31) & 0xFFFFFFFE) + 1;
    goto LABEL_24;
  }
  v10 = -2147024891;
LABEL_45:
  CCallMgr::~CCallMgr((CCallMgr *)v25);
  return v10;
}

```

## disassembly

```asm
0x180089fe0  mov     [rsp-8+arg_10], rbx
0x180089fe5  mov     [rsp-8+arg_8], edx
0x180089fe9  push    rbp
0x180089fea  push    rsi
0x180089feb  push    rdi
0x180089fec  push    r12
0x180089fee  push    r13
0x180089ff0  push    r14
0x180089ff2  push    r15
0x180089ff4  lea     rbp, [rsp-27h]
0x180089ff9  sub     rsp, 0C0h
0x18008a000  xor     edi, edi
0x18008a002  mov     r14, r9
0x18008a005  mov     r15d, r8d
0x18008a008  mov     rbx, rcx
0x18008a00b  test    r9, r9
0x18008a00e  jz      short loc_18008A013
0x18008a010  mov     [r9], edi
0x18008a013  mov     rdx, [rcx+30h]; struct CTxtEdit *
0x18008a017  test    rdx, rdx
0x18008a01a  jnz     short loc_18008A026
0x18008a01c  mov     eax, 800401FFh
0x18008a021  jmp     loc_18008A246
0x18008a026  lea     rcx, [rbp+57h+var_A8]; this
0x18008a02a  call    ??0CCallMgr@@QEAA@PEAVCTxtEdit@@@Z; CCallMgr::CCallMgr(CTxtEdit *)
0x18008a02f  mov     rcx, rbx; this
0x18008a032  call    ?WriteAccessDenied@CTxtRange@@QEAAHXZ; CTxtRange::WriteAccessDenied(void)
0x18008a037  test    eax, eax
0x18008a039  jz      short loc_18008A045
0x18008a03b  mov     edi, 80070005h
0x18008a040  jmp     loc_18008A23B
0x18008a045  mov     eax, [rbx+58h]
0x18008a048  mov     rcx, rbx; this
0x18008a04b  mov     [rbp+57h+var_AC], eax
0x18008a04e  call    ?GetAdjustedTextLength@CTxtRange@@QEBAJXZ; CTxtRange::GetAdjustedTextLength(void)
0x18008a053  mov     esi, r15d
0x18008a056  mov     [rbp+57h+var_B0], edi
0x18008a059  sar     esi, 1Fh
0x18008a05c  lea     r8, [rbp+57h+arg_18]; int *
0x18008a060  and     esi, 0FFFFFFFEh
0x18008a063  mov     [rbp+57h+arg_18], edi
0x18008a066  lea     rdx, [rbp+57h+var_B0]; int *
0x18008a06a  mov     dword ptr [rbp+57h+arg_0], edi
0x18008a06d  mov     rcx, rbx; this
0x18008a070  inc     esi
0x18008a072  mov     r12d, eax
0x18008a075  call    ?GetRange@CTxtRange@@QEBAJAEAJ0@Z; CTxtRange::GetRange(long &,long &)
0x18008a07a  cmp     [rbp+57h+arg_18], r12d
0x18008a07e  jle     short loc_18008A0A4
0x18008a080  mov     edx, [rbp+57h+var_B0]; int
0x18008a083  mov     rcx, rbx; this
0x18008a086  mov     r8d, edx
0x18008a089  sub     r8d, r12d; int
0x18008a08c  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x18008a091  test    r15d, r15d
0x18008a094  jle     short loc_18008A0A7
0x18008a096  mov     eax, [rbx+58h]
0x18008a099  neg     eax
0x18008a09b  sbb     ecx, ecx
0x18008a09d  and     ecx, esi
0x18008a09f  jmp     loc_18008A133
0x18008a0a4  test    r15d, r15d
0x18008a0a7  jz      loc_18008A131
0x18008a0ad  mov     edx, [rbx+58h]
0x18008a0b0  mov     eax, esi
0x18008a0b2  xor     eax, edx
0x18008a0b4  jge     short loc_18008A0C9
0x18008a0b6  neg     edx; int
0x18008a0b8  lea     rcx, [rbx+8]; this
0x18008a0bc  call    ?Advance@CRchTxtPtr@@QEAAJJ@Z; CRchTxtPtr::Advance(long)
0x18008a0c1  mov     eax, [rbx+58h]
0x18008a0c4  neg     eax
0x18008a0c6  mov     [rbx+58h], eax
0x18008a0c9  mov     r13d, [rbp+57h+arg_8]
0x18008a0cd  lea     r9, [rbp+57h+arg_0]
0x18008a0d1  mov     r8d, r15d
0x18008a0d4  mov     [rsp+0F0h+var_D0], esi
0x18008a0d8  sub     r8d, esi
0x18008a0db  mov     edx, r13d
0x18008a0de  cmp     [rbp+57h+var_AC], edi
0x18008a0e1  mov     rcx, rbx
0x18008a0e4  cmovz   r8d, r15d
0x18008a0e8  call    ?Mover@CTxtRange@@AEAAJJJPEAJW4MOVES@@@Z; CTxtRange::Mover(long,long,long *,MOVES)
0x18008a0ed  mov     edi, 80070057h
0x18008a0f2  cmp     eax, edi
0x18008a0f4  jnz     short loc_18008A10B
0x18008a0f6  test    r14, r14
0x18008a0f9  jz      loc_18008A23B
0x18008a0ff  mov     dword ptr [r14], 0
0x18008a106  jmp     loc_18008A23B
0x18008a10b  mov     edi, dword ptr [rbp+57h+arg_0]
0x18008a10e  cmp     [rbx+28h], r12d
0x18008a112  jle     short loc_18008A131
0x18008a114  test    edi, edi
0x18008a116  jle     short loc_18008A131
0x18008a118  cmp     r13d, 1
0x18008a11c  jnz     loc_18008A1B2
0x18008a122  lea     rcx, [rbx+18h]; this
0x18008a126  call    ?GetTextLength@CTxtPtr@@QEBAJXZ; CTxtPtr::GetTextLength(void)
0x18008a12b  sub     r12d, eax
0x18008a12e  add     edi, r12d
0x18008a131  mov     ecx, esi
0x18008a133  mov     r12d, [rbp+57h+var_AC]
0x18008a137  xor     r13d, r13d
0x18008a13a  test    r12d, r12d
0x18008a13d  jz      short loc_18008A141
0x18008a13f  add     edi, ecx
0x18008a141  test    r14, r14
0x18008a144  jz      short loc_18008A149
0x18008a146  mov     [r14], edi
0x18008a149  cmp     [rbx+58h], r13d
0x18008a14d  jz      loc_18008A21A
0x18008a153  mov     rdx, [rbx+30h]; struct CTxtEdit *
0x18008a157  lea     r9, [rbp+57h+arg_0]; struct IUndoBuilder **
0x18008a15b  mov     r8d, 1; unsigned int
0x18008a161  mov     [rbp+57h+arg_0], r13
0x18008a165  lea     rcx, [rbp+57h+var_80]; this
0x18008a169  call    ??0CGenUndoBuilder@@QEAA@PEAVCTxtEdit@@KPEAPEAVIUndoBuilder@@@Z; CGenUndoBuilder::CGenUndoBuilder(CTxtEdit *,ulong,IUndoBuilder * *)
0x18008a16e  mov     rsi, [rbp+57h+arg_0]
0x18008a172  test    rsi, rsi
0x18008a175  jz      short loc_18008A199
0x18008a177  mov     rax, [rsi]
0x18008a17a  mov     rcx, rsi
0x18008a17d  mov     rax, [rax+30h]
0x18008a181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a186  mov     rax, [rsi]
0x18008a189  mov     edx, 2
0x18008a18e  mov     rcx, rsi
0x18008a191  mov     rax, [rax]
0x18008a194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a199  test    byte ptr [rbx+62h], 2
0x18008a19d  jz      short loc_18008A1C5
0x18008a19f  test    r12d, r12d
0x18008a1a2  jnz     short loc_18008A1C5
0x18008a1a4  test    r15d, r15d
0x18008a1a7  mov     ecx, r13d
0x18008a1aa  setle   cl
0x18008a1ad  add     ecx, 2
0x18008a1b0  jmp     short loc_18008A1CA
0x18008a1b2  mov     ecx, esi
0x18008a1b4  cmp     r13d, 2
0x18008a1b8  jnz     loc_18008A133
0x18008a1be  dec     edi
0x18008a1c0  jmp     loc_18008A133
0x18008a1c5  mov     ecx, 1
0x18008a1ca  mov     rax, [rbx]
0x18008a1cd  mov     r9, rsi
0x18008a1d0  mov     [rsp+0F0h+var_C0], r13d
0x18008a1d5  xor     r8d, r8d
0x18008a1d8  mov     [rsp+0F0h+var_C8], r13
0x18008a1dd  xor     edx, edx
0x18008a1df  mov     [rsp+0F0h+var_D0], ecx
0x18008a1e3  mov     rcx, rbx
0x18008a1e6  mov     rax, [rax+230h]
0x18008a1ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a1f2  cmp     edi, r15d
0x18008a1f5  jz      short loc_18008A20C
0x18008a1f7  cmp     edi, 1
0x18008a1fa  jnz     short loc_18008A201
0x18008a1fc  test    r15d, r15d
0x18008a1ff  jz      short loc_18008A20C
0x18008a201  lea     rcx, [rbp+57h+var_80]; this
0x18008a205  call    ??1CGenUndoBuilder@@QEAA@XZ; CGenUndoBuilder::~CGenUndoBuilder(void)
0x18008a20a  jmp     short loc_18008A236
0x18008a20c  lea     rcx, [rbp+57h+var_80]; this
0x18008a210  call    ??1CGenUndoBuilder@@QEAA@XZ; CGenUndoBuilder::~CGenUndoBuilder(void)
0x18008a215  mov     edi, r13d
0x18008a218  jmp     short loc_18008A23B
0x18008a21a  test    r12d, r12d
0x18008a21d  jz      short loc_18008A236
0x18008a21f  mov     rax, [rbx]
0x18008a222  mov     edx, 1
0x18008a227  mov     rcx, rbx
0x18008a22a  mov     rax, [rax+238h]
0x18008a231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a236  mov     edi, 1
0x18008a23b  lea     rcx, [rbp+57h+var_A8]; this
0x18008a23f  call    ??1CCallMgr@@QEAA@XZ; CCallMgr::~CCallMgr(void)
0x18008a244  mov     eax, edi
0x18008a246  mov     rbx, [rsp+0F0h+arg_10]
0x18008a24e  add     rsp, 0C0h
0x18008a255  pop     r15
0x18008a257  pop     r14
0x18008a259  pop     r13
0x18008a25b  pop     r12
0x18008a25d  pop     rdi
0x18008a25e  pop     rsi
0x18008a25f  pop     rbp
0x18008a260  retn
```
