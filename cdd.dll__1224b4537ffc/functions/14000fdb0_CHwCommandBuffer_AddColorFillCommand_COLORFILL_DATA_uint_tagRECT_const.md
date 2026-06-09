# CHwCommandBuffer::AddColorFillCommand(COLORFILL_DATA *,uint,tagRECT const *)

- ea: `0x14000fdb0`
- end: `0x140010194`
- name: `?AddColorFillCommand@CHwCommandBuffer@@QEAAHPEAUCOLORFILL_DATA@@IPEBUtagRECT@@@Z`
- size: `996`
- prototype: `__int64 __fastcall(CDDPDEV **this, struct COLORFILL_DATA *, unsigned int, const struct tagRECT *)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140005cc0`
- `0x140007b00`
- `0x14001f5d0`
- `0x140033800`
- `0x1400339f0`

## callees

- `0x14000fdb0`
- `0x1400101a0`
- `0x1400372d0`
- `0x140037340`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14001012d`
- `ntoskrnl!DbgPrint` at `0x14001012d`
- `ntoskrnl!KdDebuggerEnabled` at `0x140010116`
- `watchdog!WdLogNewEntry5_WdError` at `0x140010154`
- `watchdog!WdLogNewEntry5_WdError` at `0x140010154`
- `watchdog!WdLogSingleEntry0` at `0x14001013e`
- `watchdog!WdLogSingleEntry0` at `0x14001013e`

## string_xrefs

- `0x140010126`: `Attempt to insert NULL allocation to the allocation list`

## pseudocode

```c
__int64 __fastcall CHwCommandBuffer::AddColorFillCommand(
        CDDPDEV **this,
        struct COLORFILL_DATA *a2,
        unsigned int a3,
        const struct tagRECT *a4)
{
  struct CCommandBufferMutex *v4; // r15
  unsigned int v7; // ebp
  unsigned int v10; // r13d
  CDDPDEV *v11; // r10
  unsigned int v12; // ecx
  __int64 v13; // r8
  _DWORD *v14; // r8
  bool v15; // zf
  int v16; // edi
  __int64 i; // rcx
  CDDPDEV *v18; // r8
  CDDPDEV *v19; // r15
  __int128 v20; // xmm0
  __int64 v21; // r9
  const struct tagRECT *v22; // r8
  CDDPDEV *v23; // rbx
  int v25; // ecx
  int v26; // edx
  int v27; // ecx
  int v28; // edx
  int v29; // ecx
  int v30; // edx
  int v31; // ecx
  __int64 v32; // r9
  const struct tagRECT *v33; // r8
  _QWORD *v34; // rax
  _OWORD v35[3]; // [rsp+30h] [rbp-58h] BYREF

  v4 = (struct CCommandBufferMutex *)*((_QWORD *)a2 + 4);
  v7 = 16 * a3;
  v10 = 16 * a3 + 48;
  if ( (CDDPDEV *)((char *)this[4] + v10) > this[3]
    || (v11 = *this, v12 = *((_DWORD *)this + 530), v12 > *((_DWORD *)*this + 3178)) )
  {
    CDDPDEV::FlushNoMutex(*this, *((struct CCommandBufferMutex **)a2 + 4), 0, 2u);
    return 0;
  }
  else
  {
    v13 = *(_QWORD *)a2;
    if ( *(_QWORD *)a2 && *(_BYTE *)(v13 + 20) )
      v14 = (_DWORD *)(v13 + 4);
    else
      v14 = (_DWORD *)*((_QWORD *)a2 + 3);
    v15 = *((_BYTE *)this + 2144) == 0;
    *((_DWORD *)this + 530) = v12 + (v14[2] - *v14) * (v14[3] - v14[1]);
    if ( v15 )
    {
      v16 = *((_DWORD *)a2 + 22);
      if ( !v16 && (*((_DWORD *)v11 + 686) & 0x100) != 0 && (_BYTE)KdDebuggerEnabled )
      {
        DbgPrint("Attempt to insert NULL allocation to the allocation list");
        WdLogSingleEntry0(2);
        WdLogGlobalForLineNumber = 28;
        v34 = (_QWORD *)WdLogNewEntry5_WdError();
        v34[3] = gCddImageInfo;
        v34[4] = (unsigned int)dword_14003E570;
        v34[5] = 215857758;
        WdLogGlobalForLineNumber = 28;
        __debugbreak();
      }
      for ( i = 0; (unsigned int)i < *((_DWORD *)this + 524); i = (unsigned int)(i + 1) )
      {
        if ( LODWORD(this[i + 6]) == v16 )
        {
          HIDWORD(this[i + 6]) |= 1u;
          goto LABEL_11;
        }
      }
      if ( (_DWORD)i == 256 )
        goto LABEL_39;
      this[i + 6] = 0;
      LODWORD(this[i + 6]) = v16;
      HIDWORD(this[i + 6]) = 1;
      *((_DWORD *)this + 524) = i + 1;
LABEL_11:
      if ( (_DWORD)i == -1 )
      {
LABEL_39:
        CDDPDEV::FlushNoMutex(*this, v4, 0, 2u);
        return 0;
      }
      v18 = this[5];
      if ( v18
        && *(_DWORD *)v18 == 2
        && *((_DWORD *)v18 + 10) == *((_DWORD *)a2 + 23)
        && *((unsigned __int16 *)v18 + 22) == *((_DWORD *)a2 + 24)
        && *((_DWORD *)v18 + 6) == (_DWORD)i )
      {
        *((_DWORD *)v18 + 7) += a3;
        v25 = **((_DWORD **)a2 + 2);
        if ( v25 >= *((_DWORD *)v18 + 2) )
          v25 = *((_DWORD *)v18 + 2);
        v26 = *((_DWORD *)v18 + 4);
        *((_DWORD *)v18 + 2) = v25;
        v27 = *(_DWORD *)(*((_QWORD *)a2 + 2) + 8LL);
        if ( v27 <= v26 )
          v27 = v26;
        v28 = *((_DWORD *)v18 + 3);
        *((_DWORD *)v18 + 4) = v27;
        v29 = *(_DWORD *)(*((_QWORD *)a2 + 2) + 4LL);
        if ( v29 >= v28 )
          v29 = v28;
        v30 = *((_DWORD *)v18 + 5);
        *((_DWORD *)v18 + 3) = v29;
        v31 = *(_DWORD *)(*((_QWORD *)a2 + 2) + 12LL);
        if ( v31 <= v30 )
          v31 = v30;
        *((_DWORD *)v18 + 5) = v31;
        memmove((char *)this[5] + *((unsigned int *)this[5] + 1), a4, v7);
        *((_DWORD *)this[5] + 1) += v7;
        this[4] = (CDDPDEV *)((char *)this[4] + v7);
        if ( a3 > 8 )
        {
          v33 = (const struct tagRECT *)*((_QWORD *)a2 + 2);
          v32 = 1;
        }
        else
        {
          v32 = a3;
          v33 = a4;
        }
        (***((void (__fastcall ****)(_QWORD, CDDPDEV **, const struct tagRECT *, __int64, _QWORD))a2 + 10))(
          *((_QWORD *)a2 + 10),
          this,
          v33,
          v32,
          0);
      }
      else
      {
        v19 = this[4];
        *(_DWORD *)v19 = 2;
        *((_DWORD *)v19 + 1) = v10;
        *((_DWORD *)v19 + 6) = i;
        v20 = *(_OWORD *)*((_QWORD *)a2 + 2);
        *((_DWORD *)v19 + 7) = a3;
        *((_QWORD *)v19 + 4) = (char *)v19 + 48;
        *(_OWORD *)((char *)v19 + 8) = v20;
        *((_DWORD *)v19 + 10) = *((_DWORD *)a2 + 23);
        *((_WORD *)v19 + 22) = *((_WORD *)a2 + 48);
        *((_WORD *)v19 + 23) = *((_WORD *)a2 + 49);
        memmove((char *)v19 + 48, a4, v7);
        this[4] = (CDDPDEV *)((char *)this[4] + v10);
        *((_BYTE *)*this + 2753) = 1;
        if ( a3 > 8 )
        {
          v21 = 1;
          v22 = (const struct tagRECT *)((char *)v19 + 8);
        }
        else
        {
          v21 = a3;
          v22 = a4;
        }
        (***((void (__fastcall ****)(_QWORD, CDDPDEV **, const struct tagRECT *, __int64, _QWORD))a2 + 10))(
          *((_QWORD *)a2 + 10),
          this,
          v22,
          v21,
          0);
        this[5] = v19;
        v23 = *this;
        memset(v35, 0, sizeof(v35));
        LODWORD(v35[0]) = 1;
        if ( (*((unsigned int (**)(void))v23 + 10))() )
          (*((void (__fastcall **)(__int64, _QWORD, _OWORD *))v23 + 33))(3039, 0, v35);
      }
      return 1;
    }
    else
    {
      CDDPDEV::FlushNoMutex(v11, v4, 0, 2u);
      return 0;
    }
  }
}

```

## disassembly

```asm
0x14000fdb0  mov     [rsp+arg_8], rbx
0x14000fdb5  mov     [rsp+arg_10], rbp
0x14000fdba  push    rsi
0x14000fdbb  push    r12
0x14000fdbd  push    r13
0x14000fdbf  push    r14
0x14000fdc1  push    r15
0x14000fdc3  sub     rsp, 60h
0x14000fdc7  mov     r15, [rdx+20h]
0x14000fdcb  mov     rbx, rcx
0x14000fdce  mov     ebp, r8d
0x14000fdd1  mov     r12, r9
0x14000fdd4  shl     ebp, 4
0x14000fdd7  mov     r14d, r8d
0x14000fdda  mov     rsi, rdx
0x14000fddd  lea     r13d, [rbp+30h]
0x14000fde1  mov     ecx, r13d
0x14000fde4  add     rcx, [rbx+20h]
0x14000fde8  cmp     rcx, [rbx+18h]
0x14000fdec  ja      loc_14000FF78
0x14000fdf2  mov     r10, [rbx]
0x14000fdf5  mov     ecx, [rbx+848h]
0x14000fdfb  cmp     ecx, [r10+31A8h]
0x14000fe02  ja      loc_14000FF78
0x14000fe08  mov     r8, [rdx]
0x14000fe0b  test    r8, r8
0x14000fe0e  jnz     loc_14000FF90
0x14000fe14  mov     r8, [rdx+18h]
0x14000fe18  mov     r9d, [r8+0Ch]
0x14000fe1c  sub     r9d, [r8+4]
0x14000fe20  mov     eax, [r8]
0x14000fe23  mov     r8d, [r8+8]
0x14000fe27  sub     r8d, eax
0x14000fe2a  imul    r9d, r8d
0x14000fe2e  add     r9d, ecx
0x14000fe31  cmp     byte ptr [rbx+860h], 0
0x14000fe38  mov     [rbx+848h], r9d
0x14000fe3f  jnz     loc_1400100CD
0x14000fe45  mov     [rsp+88h+arg_0], rdi
0x14000fe4d  mov     edi, [rdx+58h]
0x14000fe50  test    edi, edi
0x14000fe52  jz      loc_140010105
0x14000fe58  mov     edx, [rbx+830h]
0x14000fe5e  xor     ecx, ecx
0x14000fe60  cmp     ecx, edx
0x14000fe62  jnb     loc_14000FFA4
0x14000fe68  cmp     [rbx+rcx*8+30h], edi
0x14000fe6c  jnz     loc_14001018D
0x14000fe72  or      dword ptr [rbx+rcx*8+34h], 1
0x14000fe77  cmp     ecx, 0FFFFFFFFh
0x14000fe7a  jz      loc_1400100A6
0x14000fe80  mov     r8, [rbx+28h]
0x14000fe84  test    r8, r8
0x14000fe87  jz      short loc_14000FE93
0x14000fe89  cmp     dword ptr [r8], 2
0x14000fe8d  jz      loc_14000FFD1
0x14000fe93  mov     r15, [rbx+20h]
0x14000fe97  mov     rdx, r12; Src
0x14000fe9a  mov     r8d, ebp; Size
0x14000fe9d  mov     dword ptr [r15], 2
0x14000fea4  mov     [r15+4], r13d
0x14000fea8  mov     [r15+18h], ecx
0x14000feac  lea     rcx, [r15+30h]; void *
0x14000feb0  mov     rax, [rsi+10h]
0x14000feb4  movups  xmm0, xmmword ptr [rax]
0x14000feb7  mov     [r15+1Ch], r14d
0x14000febb  mov     [r15+20h], rcx
0x14000febf  movups  xmmword ptr [r15+8], xmm0
0x14000fec4  mov     eax, [rsi+5Ch]
0x14000fec7  mov     [r15+28h], eax
0x14000fecb  movzx   eax, word ptr [rsi+60h]
0x14000fecf  mov     [r15+2Ch], ax
0x14000fed4  movzx   eax, word ptr [rsi+62h]
0x14000fed8  mov     [r15+2Eh], ax
0x14000fedd  call    memmove
0x14000fee2  mov     eax, r13d
0x14000fee5  mov     rdx, rbx
0x14000fee8  add     [rbx+20h], rax
0x14000feec  mov     rax, [rbx]
0x14000feef  mov     [rsp+88h+var_68], 0
0x14000fef8  mov     byte ptr [rax+0AC1h], 1
0x14000feff  mov     rcx, [rsi+50h]
0x14000ff03  mov     rax, [rcx]
0x14000ff06  mov     rax, [rax]
0x14000ff09  cmp     r14d, 8
0x14000ff0d  ja      loc_140010097
0x14000ff13  mov     r9d, r14d
0x14000ff16  mov     r8, r12
0x14000ff19  call    _guard_dispatch_icall
0x14000ff1e  xorps   xmm0, xmm0
0x14000ff21  mov     [rbx+28h], r15
0x14000ff25  mov     rbx, [rbx]
0x14000ff28  movups  [rsp+88h+var_58], xmm0
0x14000ff2d  mov     dword ptr [rsp+88h+var_58], 1
0x14000ff35  movups  [rsp+88h+var_48], xmm0
0x14000ff3a  movups  [rsp+88h+var_38], xmm0
0x14000ff3f  mov     rax, [rbx+50h]
0x14000ff43  call    _guard_dispatch_icall
0x14000ff48  test    eax, eax
0x14000ff4a  jnz     loc_1400100E8
0x14000ff50  mov     eax, 1
0x14000ff55  mov     rdi, [rsp+88h+arg_0]
0x14000ff5d  lea     r11, [rsp+88h+var_28]
0x14000ff62  mov     rbx, [r11+38h]
0x14000ff66  mov     rbp, [r11+40h]
0x14000ff6a  mov     rsp, r11
0x14000ff6d  pop     r15
0x14000ff6f  pop     r14
0x14000ff71  pop     r13
0x14000ff73  pop     r12
0x14000ff75  pop     rsi
0x14000ff76  retn
0x14000ff78  mov     rcx, [rbx]; this
0x14000ff7b  mov     r9d, 2; unsigned int
0x14000ff81  xor     r8d, r8d; int
0x14000ff84  mov     rdx, r15; struct CCommandBufferMutex *
0x14000ff87  call    ?FlushNoMutex@CDDPDEV@@QEAAJPEAVCCommandBufferMutex@@HI@Z; CDDPDEV::FlushNoMutex(CCommandBufferMutex *,int,uint)
0x14000ff8c  xor     eax, eax
0x14000ff8e  jmp     short loc_14000FF5D
0x14000ff90  cmp     byte ptr [r8+14h], 0
0x14000ff95  jz      loc_14000FE14
0x14000ff9b  add     r8, 4
0x14000ff9f  jmp     loc_14000FE18
0x14000ffa4  cmp     ecx, 100h
0x14000ffaa  jz      loc_1400100A6
0x14000ffb0  xor     edx, edx
0x14000ffb2  lea     eax, [rcx+1]
0x14000ffb5  mov     [rbx+rcx*8+30h], rdx
0x14000ffba  mov     [rbx+rcx*8+30h], edi
0x14000ffbe  mov     dword ptr [rbx+rcx*8+34h], 1
0x14000ffc6  mov     [rbx+830h], eax
0x14000ffcc  jmp     loc_14000FE77
0x14000ffd1  mov     eax, [rsi+5Ch]
0x14000ffd4  cmp     [r8+28h], eax
0x14000ffd8  jnz     loc_14000FE93
0x14000ffde  movzx   eax, word ptr [r8+2Ch]
0x14000ffe3  cmp     eax, [rsi+60h]
0x14000ffe6  jnz     loc_14000FE93
0x14000ffec  cmp     [r8+18h], ecx
0x14000fff0  jnz     loc_14000FE93
0x14000fff6  add     [r8+1Ch], r14d
0x14000fffa  mov     rax, [rsi+10h]
0x14000fffe  mov     edx, [r8+8]
0x140010002  mov     edi, ebp
0x140010004  mov     ecx, [rax]
0x140010006  cmp     ecx, edx
0x140010008  cmovge  ecx, edx
0x14001000b  mov     edx, [r8+10h]
0x14001000f  mov     [r8+8], ecx
0x140010013  mov     rax, [rsi+10h]
0x140010017  mov     ecx, [rax+8]
0x14001001a  cmp     ecx, edx
0x14001001c  cmovle  ecx, edx
0x14001001f  mov     edx, [r8+0Ch]
0x140010023  mov     [r8+10h], ecx
0x140010027  mov     rax, [rsi+10h]
0x14001002b  mov     ecx, [rax+4]
0x14001002e  cmp     ecx, edx
0x140010030  cmovge  ecx, edx
0x140010033  mov     edx, [r8+14h]
0x140010037  mov     [r8+0Ch], ecx
0x14001003b  mov     rax, [rsi+10h]
0x14001003f  mov     ecx, [rax+0Ch]
0x140010042  cmp     ecx, edx
0x140010044  cmovle  ecx, edx
0x140010047  mov     rdx, r12; Src
0x14001004a  mov     [r8+14h], ecx
0x14001004e  mov     rax, [rbx+28h]
0x140010052  mov     r8d, ebp; Size
0x140010055  mov     ecx, [rax+4]
0x140010058  add     rcx, rax; void *
0x14001005b  call    memmove
0x140010060  mov     rax, [rbx+28h]
0x140010064  mov     rdx, rbx
0x140010067  mov     [rsp+88h+var_68], 0
0x140010070  add     [rax+4], ebp
0x140010073  add     [rbx+20h], rdi
0x140010077  mov     rcx, [rsi+50h]
0x14001007b  mov     rax, [rcx]
0x14001007e  mov     rax, [rax]
0x140010081  cmp     r14d, 8
0x140010085  ja      short loc_1400100C1
0x140010087  mov     r9d, r14d
0x14001008a  mov     r8, r12
0x14001008d  call    _guard_dispatch_icall
0x140010092  jmp     loc_14000FF50
0x140010097  mov     r9d, 1
0x14001009d  lea     r8, [r15+8]
0x1400100a1  jmp     loc_14000FF19
0x1400100a6  mov     rcx, [rbx]; this
0x1400100a9  mov     r9d, 2; unsigned int
0x1400100af  xor     r8d, r8d; int
0x1400100b2  mov     rdx, r15; struct CCommandBufferMutex *
0x1400100b5  call    ?FlushNoMutex@CDDPDEV@@QEAAJPEAVCCommandBufferMutex@@HI@Z; CDDPDEV::FlushNoMutex(CCommandBufferMutex *,int,uint)
0x1400100ba  xor     eax, eax
0x1400100bc  jmp     loc_14000FF55
0x1400100c1  mov     r8, [rsi+10h]
0x1400100c5  mov     r9d, 1
0x1400100cb  jmp     short loc_14001008D
0x1400100cd  mov     r9d, 2; unsigned int
0x1400100d3  xor     r8d, r8d; int
0x1400100d6  mov     rdx, r15; struct CCommandBufferMutex *
0x1400100d9  mov     rcx, r10; this
0x1400100dc  call    ?FlushNoMutex@CDDPDEV@@QEAAJPEAVCCommandBufferMutex@@HI@Z; CDDPDEV::FlushNoMutex(CCommandBufferMutex *,int,uint)
0x1400100e1  xor     eax, eax
0x1400100e3  jmp     loc_14000FF5D
0x1400100e8  mov     rax, [rbx+108h]
0x1400100ef  lea     r8, [rsp+88h+var_58]
0x1400100f4  xor     edx, edx
0x1400100f6  mov     ecx, 0BDFh
0x1400100fb  call    _guard_dispatch_icall
0x140010100  jmp     loc_14000FF50
0x140010105  test    dword ptr [r10+0AB8h], 100h
0x140010110  jz      loc_14000FE58
0x140010116  mov     rax, cs:KdDebuggerEnabled
0x14001011d  cmp     byte ptr [rax], 0
0x140010120  jz      loc_14000FE58
0x140010126  lea     rcx, aAttemptToInser; "Attempt to insert NULL allocation to th"...
0x14001012d  call    cs:__imp_DbgPrint
0x140010134  nop     dword ptr [rax+rax+00h]
0x140010139  mov     ecx, 2
0x14001013e  call    cs:__imp_WdLogSingleEntry0
0x140010145  nop     dword ptr [rax+rax+00h]
0x14001014a  mov     cs:WdLogGlobalForLineNumber, 1Ch
0x140010154  call    cs:__imp_WdLogNewEntry5_WdError
0x14001015b  nop     dword ptr [rax+rax+00h]
0x140010160  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140010167  mov     [rax+18h], rcx
0x14001016b  mov     ecx, cs:dword_14003E570
0x140010171  mov     [rax+20h], rcx
0x140010175  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001017d  mov     cs:WdLogGlobalForLineNumber, 1Ch
0x140010187  int     3; Trap to Debugger
0x140010188  jmp     loc_14000FE58
0x14001018d  inc     ecx
0x14001018f  jmp     loc_14000FE60
```
