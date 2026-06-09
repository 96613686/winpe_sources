# CTxtRange::Delete(long,long,long *)

- ea: `0x1800879a0`
- end: `0x180087c21`
- name: `?Delete@CTxtRange@@UEAAJJJPEAJ@Z`
- size: `641`
- prototype: `__int64 __fastcall(CTxtRange *__hidden this, int, int, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x180049814`

## callees

- `0x1800110b0`
- `0x1800114d0`
- `0x180017860`
- `0x18002fb90`
- `0x18002fc30`
- `0x1800300b0`
- `0x180030420`
- `0x18003bfa4`
- `0x18003c4f4`
- `0x18004a6c4`
- `0x1800879a0`
- `0x180088f24`
- `0x180092010`

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
0x1800879a0  mov     [rsp-8+arg_10], rbx
0x1800879a5  mov     [rsp-8+arg_8], edx
0x1800879a9  push    rbp
0x1800879aa  push    rsi
0x1800879ab  push    rdi
0x1800879ac  push    r12
0x1800879ae  push    r13
0x1800879b0  push    r14
0x1800879b2  push    r15
0x1800879b4  lea     rbp, [rsp-27h]
0x1800879b9  sub     rsp, 0C0h
0x1800879c0  xor     edi, edi
0x1800879c2  mov     r14, r9
0x1800879c5  mov     r15d, r8d
0x1800879c8  mov     rbx, rcx
0x1800879cb  test    r9, r9
0x1800879ce  jz      short loc_1800879D3
0x1800879d0  mov     [r9], edi
0x1800879d3  mov     rdx, [rcx+30h]; struct CTxtEdit *
0x1800879d7  test    rdx, rdx
0x1800879da  jnz     short loc_1800879E6
0x1800879dc  mov     eax, 800401FFh
0x1800879e1  jmp     loc_180087C06
0x1800879e6  lea     rcx, [rbp+57h+var_A8]; this
0x1800879ea  call    ??0CCallMgr@@QEAA@PEAVCTxtEdit@@@Z; CCallMgr::CCallMgr(CTxtEdit *)
0x1800879ef  mov     rcx, rbx; this
0x1800879f2  call    ?WriteAccessDenied@CTxtRange@@QEAAHXZ; CTxtRange::WriteAccessDenied(void)
0x1800879f7  test    eax, eax
0x1800879f9  jz      short loc_180087A05
0x1800879fb  mov     edi, 80070005h
0x180087a00  jmp     loc_180087BFB
0x180087a05  mov     eax, [rbx+58h]
0x180087a08  mov     rcx, rbx; this
0x180087a0b  mov     [rbp+57h+var_AC], eax
0x180087a0e  call    ?GetAdjustedTextLength@CTxtRange@@QEBAJXZ; CTxtRange::GetAdjustedTextLength(void)
0x180087a13  mov     esi, r15d
0x180087a16  mov     [rbp+57h+var_B0], edi
0x180087a19  sar     esi, 1Fh
0x180087a1c  lea     r8, [rbp+57h+arg_18]; int *
0x180087a20  and     esi, 0FFFFFFFEh
0x180087a23  mov     [rbp+57h+arg_18], edi
0x180087a26  lea     rdx, [rbp+57h+var_B0]; int *
0x180087a2a  mov     dword ptr [rbp+57h+arg_0], edi
0x180087a2d  mov     rcx, rbx; this
0x180087a30  inc     esi
0x180087a32  mov     r12d, eax
0x180087a35  call    ?GetRange@CTxtRange@@QEBAJAEAJ0@Z; CTxtRange::GetRange(long &,long &)
0x180087a3a  cmp     [rbp+57h+arg_18], r12d
0x180087a3e  jle     short loc_180087A64
0x180087a40  mov     edx, [rbp+57h+var_B0]; int
0x180087a43  mov     rcx, rbx; this
0x180087a46  mov     r8d, edx
0x180087a49  sub     r8d, r12d; int
0x180087a4c  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180087a51  test    r15d, r15d
0x180087a54  jle     short loc_180087A67
0x180087a56  mov     eax, [rbx+58h]
0x180087a59  neg     eax
0x180087a5b  sbb     ecx, ecx
0x180087a5d  and     ecx, esi
0x180087a5f  jmp     loc_180087AF3
0x180087a64  test    r15d, r15d
0x180087a67  jz      loc_180087AF1
0x180087a6d  mov     edx, [rbx+58h]
0x180087a70  mov     eax, esi
0x180087a72  xor     eax, edx
0x180087a74  jge     short loc_180087A89
0x180087a76  neg     edx; int
0x180087a78  lea     rcx, [rbx+8]; this
0x180087a7c  call    ?Advance@CRchTxtPtr@@QEAAJJ@Z; CRchTxtPtr::Advance(long)
0x180087a81  mov     eax, [rbx+58h]
0x180087a84  neg     eax
0x180087a86  mov     [rbx+58h], eax
0x180087a89  mov     r13d, [rbp+57h+arg_8]
0x180087a8d  lea     r9, [rbp+57h+arg_0]
0x180087a91  mov     r8d, r15d
0x180087a94  mov     [rsp+0F0h+var_D0], esi
0x180087a98  sub     r8d, esi
0x180087a9b  mov     edx, r13d
0x180087a9e  cmp     [rbp+57h+var_AC], edi
0x180087aa1  mov     rcx, rbx
0x180087aa4  cmovz   r8d, r15d
0x180087aa8  call    ?Mover@CTxtRange@@AEAAJJJPEAJW4MOVES@@@Z; CTxtRange::Mover(long,long,long *,MOVES)
0x180087aad  mov     edi, 80070057h
0x180087ab2  cmp     eax, edi
0x180087ab4  jnz     short loc_180087ACB
0x180087ab6  test    r14, r14
0x180087ab9  jz      loc_180087BFB
0x180087abf  mov     dword ptr [r14], 0
0x180087ac6  jmp     loc_180087BFB
0x180087acb  mov     edi, dword ptr [rbp+57h+arg_0]
0x180087ace  cmp     [rbx+28h], r12d
0x180087ad2  jle     short loc_180087AF1
0x180087ad4  test    edi, edi
0x180087ad6  jle     short loc_180087AF1
0x180087ad8  cmp     r13d, 1
0x180087adc  jnz     loc_180087B72
0x180087ae2  lea     rcx, [rbx+18h]; this
0x180087ae6  call    ?GetTextLength@CTxtPtr@@QEBAJXZ; CTxtPtr::GetTextLength(void)
0x180087aeb  sub     r12d, eax
0x180087aee  add     edi, r12d
0x180087af1  mov     ecx, esi
0x180087af3  mov     r12d, [rbp+57h+var_AC]
0x180087af7  xor     r13d, r13d
0x180087afa  test    r12d, r12d
0x180087afd  jz      short loc_180087B01
0x180087aff  add     edi, ecx
0x180087b01  test    r14, r14
0x180087b04  jz      short loc_180087B09
0x180087b06  mov     [r14], edi
0x180087b09  cmp     [rbx+58h], r13d
0x180087b0d  jz      loc_180087BDA
0x180087b13  mov     rdx, [rbx+30h]; struct CTxtEdit *
0x180087b17  lea     r9, [rbp+57h+arg_0]; struct IUndoBuilder **
0x180087b1b  mov     r8d, 1; unsigned int
0x180087b21  mov     [rbp+57h+arg_0], r13
0x180087b25  lea     rcx, [rbp+57h+var_80]; this
0x180087b29  call    ??0CGenUndoBuilder@@QEAA@PEAVCTxtEdit@@KPEAPEAVIUndoBuilder@@@Z; CGenUndoBuilder::CGenUndoBuilder(CTxtEdit *,ulong,IUndoBuilder * *)
0x180087b2e  mov     rsi, [rbp+57h+arg_0]
0x180087b32  test    rsi, rsi
0x180087b35  jz      short loc_180087B59
0x180087b37  mov     rax, [rsi]
0x180087b3a  mov     rcx, rsi
0x180087b3d  mov     rax, [rax+30h]
0x180087b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087b46  mov     rax, [rsi]
0x180087b49  mov     edx, 2
0x180087b4e  mov     rcx, rsi
0x180087b51  mov     rax, [rax]
0x180087b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087b59  test    byte ptr [rbx+62h], 2
0x180087b5d  jz      short loc_180087B85
0x180087b5f  test    r12d, r12d
0x180087b62  jnz     short loc_180087B85
0x180087b64  test    r15d, r15d
0x180087b67  mov     ecx, r13d
0x180087b6a  setle   cl
0x180087b6d  add     ecx, 2
0x180087b70  jmp     short loc_180087B8A
0x180087b72  mov     ecx, esi
0x180087b74  cmp     r13d, 2
0x180087b78  jnz     loc_180087AF3
0x180087b7e  dec     edi
0x180087b80  jmp     loc_180087AF3
0x180087b85  mov     ecx, 1
0x180087b8a  mov     rax, [rbx]
0x180087b8d  mov     r9, rsi
0x180087b90  mov     [rsp+0F0h+var_C0], r13d
0x180087b95  xor     r8d, r8d
0x180087b98  mov     [rsp+0F0h+var_C8], r13
0x180087b9d  xor     edx, edx
0x180087b9f  mov     [rsp+0F0h+var_D0], ecx
0x180087ba3  mov     rcx, rbx
0x180087ba6  mov     rax, [rax+230h]
0x180087bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087bb2  cmp     edi, r15d
0x180087bb5  jz      short loc_180087BCC
0x180087bb7  cmp     edi, 1
0x180087bba  jnz     short loc_180087BC1
0x180087bbc  test    r15d, r15d
0x180087bbf  jz      short loc_180087BCC
0x180087bc1  lea     rcx, [rbp+57h+var_80]; this
0x180087bc5  call    ??1CGenUndoBuilder@@QEAA@XZ; CGenUndoBuilder::~CGenUndoBuilder(void)
0x180087bca  jmp     short loc_180087BF6
0x180087bcc  lea     rcx, [rbp+57h+var_80]; this
0x180087bd0  call    ??1CGenUndoBuilder@@QEAA@XZ; CGenUndoBuilder::~CGenUndoBuilder(void)
0x180087bd5  mov     edi, r13d
0x180087bd8  jmp     short loc_180087BFB
0x180087bda  test    r12d, r12d
0x180087bdd  jz      short loc_180087BF6
0x180087bdf  mov     rax, [rbx]
0x180087be2  mov     edx, 1
0x180087be7  mov     rcx, rbx
0x180087bea  mov     rax, [rax+238h]
0x180087bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087bf6  mov     edi, 1
0x180087bfb  lea     rcx, [rbp+57h+var_A8]; this
0x180087bff  call    ??1CCallMgr@@QEAA@XZ; CCallMgr::~CCallMgr(void)
0x180087c04  mov     eax, edi
0x180087c06  mov     rbx, [rsp+0F0h+arg_10]
0x180087c0e  add     rsp, 0C0h
0x180087c15  pop     r15
0x180087c17  pop     r14
0x180087c19  pop     r13
0x180087c1b  pop     r12
0x180087c1d  pop     rdi
0x180087c1e  pop     rsi
0x180087c1f  pop     rbp
0x180087c20  retn
```
