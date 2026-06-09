# CDiscReader::BlockRead(void *,ulong,ulong *)

- ea: `0x18004ef10`
- end: `0x18004f33c`
- name: `?BlockRead@CDiscReader@@UEAAXPEAXKPEAK@Z`
- size: `1068`
- prototype: `void __fastcall(CDiscReader *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180003580`
- `0x180003a20`
- `0x180005040`
- `0x18000960c`
- `0x1800251dc`
- `0x180028568`
- `0x18002d4e4`
- `0x18004ef10`
- `0x1800516d4`
- `0x180081750`
- `0x180088010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18004f06f`
- `KERNEL32!Sleep` at `0x18004f0e6`
- `KERNEL32!Sleep` at `0x18004f06f`
- `KERNEL32!Sleep` at `0x18004f0e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CDiscReader::BlockRead(CDiscReader *this, CIMAPIException **a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v7; // edi
  unsigned int v8; // r15d
  unsigned int v9; // r13d
  int v10; // r12d
  int v11; // r8d
  unsigned int v12; // eax
  __int16 v13; // cx
  __int16 v14; // r9
  __int16 v15; // r10
  int v16; // eax
  __int64 v17; // r8
  __int64 v18; // r8
  CIMAPIException *v19; // rax
  CIMAPIException **v20; // rbx
  unsigned int v21; // r8d
  CIMAPIException *v22; // rax
  CIMAPIException **v23; // rbx
  unsigned int v24; // [rsp+50h] [rbp-B0h] BYREF
  CIMAPIException **v25; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v26; // [rsp+60h] [rbp-A0h]
  __int16 v27; // [rsp+62h] [rbp-9Eh]
  unsigned int v28; // [rsp+64h] [rbp-9Ch]
  CIMAPIException **pExceptionObject; // [rsp+68h] [rbp-98h] BYREF
  int v30; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v31; // [rsp+74h] [rbp-8Ch]
  _BYTE v32[88]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v33; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v34; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v35; // [rsp+F0h] [rbp-10h]

  v25 = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 65, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids);
    a2 = v25;
  }
  v7 = *((_DWORD *)this + 8);
  if ( *((_QWORD *)this + 3) )
  {
    v8 = a3;
    while ( v8 )
    {
      v34 = 0;
      v35 = 0;
      v9 = 0;
      v10 = 16;
      if ( v8 < 0x10 )
        v10 = v8;
      v11 = v10 << 11;
      v28 = v10 << 11;
      v12 = HIWORD(v7);
      LODWORD(pExceptionObject) = HIWORD(v7);
      v13 = HIBYTE(HIWORD(v7));
      v26 = HIBYTE(HIWORD(v7));
      v14 = BYTE1(v7);
      v27 = BYTE1(v7);
      v15 = BYTE1(v10);
      LOWORD(v24) = BYTE1(v10);
      while ( 1 )
      {
        v30 = v11;
        v33 = 0;
        LOBYTE(v33) = 40;
        BYTE2(v33) = v13;
        BYTE3(v33) = v12;
        BYTE4(v33) = v14;
        BYTE5(v33) = v7;
        BYTE7(v33) = v15;
        BYTE8(v33) = v10;
        v16 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64, __int128 *, int, CIMAPIException **, int, int *))(**((_QWORD **)this + 3) + 40LL))(
                *((_QWORD *)this + 3),
                &v33,
                10,
                &v34,
                12,
                a2,
                v11,
                &v30);
        v31 = v16;
        if ( v16 == 11141632 )
          break;
        if ( v16 >= 0 )
          goto LABEL_23;
        Sleep(0x7D0u);
        ++v9;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
        {
          WPP_SF_dDD(*((_QWORD *)WPP_GLOBAL_Control + 7), 67, v17, v31, v7, v9);
        }
        if ( v9 >= 5 )
        {
          v19 = (CIMAPIException *)operator new(0x58u);
          v25 = (CIMAPIException **)v19;
          if ( v19 )
            v19 = CIMAPIException::CIMAPIException(v19, -1062555305, v7);
          SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v25, v19);
          v20 = v25;
          if ( v25 && *v25 )
          {
            CIMAPIException::SetCodeRefInfo(*v25, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiimp.cpp", 1013);
            pExceptionObject = v20;
            if ( v20 )
              ++*((_DWORD *)v20 + 2);
            throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
          }
          CIMAPIException::CIMAPIException(
            (CIMAPIException *)v32,
            (const struct CIMAPIException *)&CIMAPIException::badAlloc);
          throw (CIMAPIException *)v32;
        }
        a2 = v25;
        v11 = v28;
        LOBYTE(v12) = (_BYTE)pExceptionObject;
        LOBYTE(v13) = v26;
        LOBYTE(v14) = v27;
        LOBYTE(v15) = v24;
      }
      Sleep(0x7D0u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_dDD(*((_QWORD *)WPP_GLOBAL_Control + 7), 66, v18, 11141632, v7, v9 + 1);
      }
LABEL_23:
      v8 -= v10;
      v7 += v10;
      a2 = (CIMAPIException **)((char *)v25 + v28);
      v25 = a2;
    }
    if ( a4 )
      *a4 = a3;
    *((_DWORD *)this + 8) += a3;
  }
  else
  {
    v24 = 0;
    v21 = *((_DWORD *)this + 10) - v7;
    if ( a3 < v21 )
      v21 = a3;
    if ( (*(int (__fastcall **)(_QWORD, CIMAPIException **, _QWORD, unsigned int *))(**((_QWORD **)this + 1) + 24LL))(
           *((_QWORD *)this + 1),
           a2,
           *((_DWORD *)this + 11) * v21,
           &v24) < 0 )
    {
      v22 = (CIMAPIException *)operator new(0x58u);
      v25 = (CIMAPIException **)v22;
      if ( v22 )
        v22 = CIMAPIException::CIMAPIException(v22, -1062555305, *((unsigned int *)this + 8));
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v25, v22);
      v23 = v25;
      if ( v25 && *v25 )
      {
        CIMAPIException::SetCodeRefInfo(*v25, "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsiimp.cpp", 1046);
        pExceptionObject = v23;
        if ( v23 )
          ++*((_DWORD *)v23 + 2);
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v32,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v32;
    }
    if ( a4 )
      *a4 = v24 / *((_DWORD *)this + 11);
    *((_DWORD *)this + 8) += v24 / *((_DWORD *)this + 11);
  }
  *((_DWORD *)this + 9) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 69, &WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids);
  }
}

```

## disassembly

```asm
0x18004ef10  push    rbp
0x18004ef12  push    rbx
0x18004ef13  push    rsi
0x18004ef14  push    rdi
0x18004ef15  push    r12
0x18004ef17  push    r13
0x18004ef19  push    r14
0x18004ef1b  push    r15
0x18004ef1d  lea     rbp, [rsp-8]
0x18004ef22  sub     rsp, 108h
0x18004ef29  mov     rax, cs:__security_cookie
0x18004ef30  xor     rax, rsp
0x18004ef33  mov     [rbp+40h+var_48], rax
0x18004ef37  mov     rsi, r9
0x18004ef3a  mov     r14d, r8d
0x18004ef3d  mov     [rsp+140h+var_E8], rdx
0x18004ef42  mov     rbx, rcx
0x18004ef45  lea     r12, WPP_GLOBAL_Control
0x18004ef4c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ef53  cmp     rcx, r12
0x18004ef56  jz      short loc_18004EF7E
0x18004ef58  test    byte ptr [rcx+44h], 8
0x18004ef5c  jz      short loc_18004EF7E
0x18004ef5e  cmp     byte ptr [rcx+41h], 5
0x18004ef62  jb      short loc_18004EF7E
0x18004ef64  mov     edx, 41h ; 'A'
0x18004ef69  lea     r8, WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids
0x18004ef70  mov     rcx, [rcx+38h]
0x18004ef74  call    WPP_SF_
0x18004ef79  mov     rdx, [rsp+140h+var_E8]
0x18004ef7e  cmp     qword ptr [rbx+18h], 0
0x18004ef83  setnz   al
0x18004ef86  mov     edi, [rbx+20h]
0x18004ef89  test    al, al
0x18004ef8b  jz      loc_18004F1F9
0x18004ef91  mov     r15d, r14d
0x18004ef94  test    r15d, r15d
0x18004ef97  jz      loc_18004F1E1
0x18004ef9d  xorps   xmm0, xmm0
0x18004efa0  xor     eax, eax
0x18004efa2  movups  [rbp+40h+var_60], xmm0
0x18004efa6  mov     [rbp+40h+var_50], ax
0x18004efaa  xor     r13d, r13d
0x18004efad  lea     r12d, [rax+10h]
0x18004efb1  cmp     r15d, r12d
0x18004efb4  cmovb   r12d, r15d
0x18004efb8  mov     r8d, r12d
0x18004efbb  shl     r8d, 0Bh
0x18004efbf  mov     [rsp+140h+var_DC], r8d
0x18004efc4  mov     eax, edi
0x18004efc6  shr     eax, 10h
0x18004efc9  mov     dword ptr [rsp+140h+pExceptionObject], eax
0x18004efcd  movzx   ecx, ax
0x18004efd0  shr     cx, 8
0x18004efd4  mov     [rsp+140h+var_E0], cx
0x18004efd9  movzx   r9d, di
0x18004efdd  shr     r9w, 8
0x18004efe2  mov     [rsp+140h+var_DE], r9w
0x18004efe8  movzx   r10d, r12w
0x18004efec  shr     r10w, 8
0x18004eff1  mov     word ptr [rsp+140h+var_F0], r10w
0x18004eff7  mov     [rsp+140h+var_D0], r8d
0x18004effc  xorps   xmm0, xmm0
0x18004efff  movups  [rbp+40h+var_70], xmm0
0x18004f003  mov     byte ptr [rbp+40h+var_70], 28h ; '('
0x18004f007  mov     byte ptr [rbp+40h+var_70+2], cl
0x18004f00a  mov     byte ptr [rbp+40h+var_70+3], al
0x18004f00d  mov     byte ptr [rbp+40h+var_70+4], r9b
0x18004f011  mov     byte ptr [rbp+40h+var_70+5], dil
0x18004f015  mov     byte ptr [rbp+40h+var_70+7], r10b
0x18004f019  mov     byte ptr [rbp+40h+var_70+8], r12b
0x18004f01d  mov     rcx, [rbx+18h]
0x18004f021  mov     rax, [rcx]
0x18004f024  lea     r9, [rsp+140h+var_D0]
0x18004f029  mov     [rsp+140h+var_108], r9
0x18004f02e  mov     [rsp+140h+var_110], r8d
0x18004f033  mov     [rsp+140h+var_118], rdx
0x18004f038  mov     [rsp+140h+var_120], 0Ch
0x18004f040  lea     r9, [rbp+40h+var_60]
0x18004f044  mov     r8d, 0Ah
0x18004f04a  lea     rdx, [rbp+40h+var_70]
0x18004f04e  mov     rax, [rax+28h]
0x18004f052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f057  mov     [rsp+140h+var_CC], eax
0x18004f05b  cmp     eax, 0AA0200h
0x18004f060  jz      short loc_18004F0E1
0x18004f062  test    eax, eax
0x18004f064  jns     loc_18004F12B
0x18004f06a  mov     ecx, 7D0h; dwMilliseconds
0x18004f06f  call    cs:__imp_Sleep
0x18004f075  inc     r13d
0x18004f078  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f07f  lea     rax, WPP_GLOBAL_Control
0x18004f086  cmp     rcx, rax
0x18004f089  jz      short loc_18004F0B3
0x18004f08b  test    byte ptr [rcx+44h], 4
0x18004f08f  jz      short loc_18004F0B3
0x18004f091  cmp     byte ptr [rcx+41h], 2
0x18004f095  jb      short loc_18004F0B3
0x18004f097  mov     edx, 43h ; 'C'
0x18004f09c  mov     dword ptr [rsp+140h+var_118], r13d
0x18004f0a1  mov     [rsp+140h+var_120], edi
0x18004f0a5  mov     r9d, [rsp+140h+var_CC]
0x18004f0aa  mov     rcx, [rcx+38h]
0x18004f0ae  call    WPP_SF_dDD
0x18004f0b3  cmp     r13d, 5
0x18004f0b7  jnb     loc_18004F147
0x18004f0bd  mov     rdx, [rsp+140h+var_E8]
0x18004f0c2  mov     r8d, [rsp+140h+var_DC]
0x18004f0c7  mov     eax, dword ptr [rsp+140h+pExceptionObject]
0x18004f0cb  movzx   ecx, [rsp+140h+var_E0]
0x18004f0d0  movzx   r9d, [rsp+140h+var_DE]
0x18004f0d6  movzx   r10d, word ptr [rsp+140h+var_F0]
0x18004f0dc  jmp     loc_18004EFF7
0x18004f0e1  mov     ecx, 7D0h; dwMilliseconds
0x18004f0e6  call    cs:__imp_Sleep
0x18004f0ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f0f3  lea     rax, WPP_GLOBAL_Control
0x18004f0fa  cmp     rcx, rax
0x18004f0fd  jz      short loc_18004F12B
0x18004f0ff  test    byte ptr [rcx+44h], 4
0x18004f103  jz      short loc_18004F12B
0x18004f105  cmp     byte ptr [rcx+41h], 2
0x18004f109  jb      short loc_18004F12B
0x18004f10b  lea     eax, [r13+1]
0x18004f10f  mov     edx, 42h ; 'B'
0x18004f114  mov     dword ptr [rsp+140h+var_118], eax
0x18004f118  mov     [rsp+140h+var_120], edi
0x18004f11c  mov     r9d, 0AA0200h
0x18004f122  mov     rcx, [rcx+38h]
0x18004f126  call    WPP_SF_dDD
0x18004f12b  sub     r15d, r12d
0x18004f12e  add     edi, r12d
0x18004f131  mov     eax, [rsp+140h+var_DC]
0x18004f135  mov     rdx, [rsp+140h+var_E8]
0x18004f13a  add     rdx, rax
0x18004f13d  mov     [rsp+140h+var_E8], rdx
0x18004f142  jmp     loc_18004EF94
0x18004f147  mov     ecx, 58h ; 'X'; unsigned __int64
0x18004f14c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f151  mov     [rsp+140h+var_E8], rax
0x18004f156  test    rax, rax
0x18004f159  jz      short loc_18004F16C
0x18004f15b  mov     r8d, edi
0x18004f15e  mov     edx, 0C0AAB157h; int
0x18004f163  mov     rcx, rax; this
0x18004f166  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18004f16b  nop
0x18004f16c  mov     rdx, rax
0x18004f16f  lea     rcx, [rsp+140h+var_E8]
0x18004f174  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18004f179  nop
0x18004f17a  mov     rbx, [rsp+140h+var_E8]
0x18004f17f  test    rbx, rbx
0x18004f182  jz      short loc_18004F1BE
0x18004f184  cmp     qword ptr [rbx], 0
0x18004f188  jz      short loc_18004F1BE
0x18004f18a  mov     r8d, 3F5h; int
0x18004f190  lea     rdx, aDriversStorage_9; "drivers\\storage\\imapi2\\filesystemima"...
0x18004f197  mov     rcx, [rbx]; this
0x18004f19a  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18004f19f  mov     [rsp+140h+pExceptionObject], rbx
0x18004f1a4  test    rbx, rbx
0x18004f1a7  jz      short loc_18004F1AC
0x18004f1a9  inc     dword ptr [rbx+8]
0x18004f1ac  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18004f1b3  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18004f1b8  call    _CxxThrowException_0
0x18004f1be  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18004f1c5  lea     rcx, [rsp+140h+var_C8]; this
0x18004f1ca  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18004f1cf  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18004f1d6  lea     rcx, [rsp+140h+var_C8]; pExceptionObject
0x18004f1db  call    _CxxThrowException_0
0x18004f1e1  test    rsi, rsi
0x18004f1e4  jz      short loc_18004F1E9
0x18004f1e6  mov     [rsi], r14d
0x18004f1e9  add     [rbx+20h], r14d
0x18004f1ed  lea     r12, WPP_GLOBAL_Control
0x18004f1f4  jmp     loc_18004F2E8
0x18004f1f9  mov     [rsp+140h+var_F0], 0
0x18004f201  mov     r8d, [rbx+28h]
0x18004f205  sub     r8d, edi
0x18004f208  cmp     r14d, r8d
0x18004f20b  cmovb   r8d, r14d
0x18004f20f  mov     rcx, [rbx+8]
0x18004f213  mov     rax, [rcx]
0x18004f216  imul    r8d, [rbx+2Ch]
0x18004f21b  lea     r9, [rsp+140h+var_F0]
0x18004f220  mov     rax, [rax+18h]
0x18004f224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f229  test    eax, eax
0x18004f22b  jns     loc_18004F2CC
0x18004f231  mov     ecx, 58h ; 'X'; unsigned __int64
0x18004f236  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004f23b  mov     [rsp+140h+var_E8], rax
0x18004f240  test    rax, rax
0x18004f243  jz      short loc_18004F257
0x18004f245  mov     r8d, [rbx+20h]
0x18004f249  mov     edx, 0C0AAB157h; int
0x18004f24e  mov     rcx, rax; this
0x18004f251  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x18004f256  nop
0x18004f257  mov     rdx, rax
0x18004f25a  lea     rcx, [rsp+140h+var_E8]
0x18004f25f  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x18004f264  nop
0x18004f265  mov     rbx, [rsp+140h+var_E8]
0x18004f26a  test    rbx, rbx
0x18004f26d  jz      short loc_18004F2A9
0x18004f26f  cmp     qword ptr [rbx], 0
0x18004f273  jz      short loc_18004F2A9
0x18004f275  mov     r8d, 416h; int
0x18004f27b  lea     rdx, aDriversStorage_9; "drivers\\storage\\imapi2\\filesystemima"...
0x18004f282  mov     rcx, [rbx]; this
0x18004f285  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x18004f28a  mov     [rsp+140h+pExceptionObject], rbx
0x18004f28f  test    rbx, rbx
0x18004f292  jz      short loc_18004F297
0x18004f294  inc     dword ptr [rbx+8]
0x18004f297  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x18004f29e  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18004f2a3  call    _CxxThrowException_0
0x18004f2a9  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x18004f2b0  lea     rcx, [rsp+140h+var_C8]; this
0x18004f2b5  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x18004f2ba  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x18004f2c1  lea     rcx, [rsp+140h+var_C8]; pExceptionObject
0x18004f2c6  call    _CxxThrowException_0
0x18004f2cc  test    rsi, rsi
0x18004f2cf  jz      short loc_18004F2DC
0x18004f2d1  xor     edx, edx
0x18004f2d3  mov     eax, [rsp+140h+var_F0]
0x18004f2d7  div     dword ptr [rbx+2Ch]
0x18004f2da  mov     [rsi], eax
0x18004f2dc  xor     edx, edx
0x18004f2de  mov     eax, [rsp+140h+var_F0]
0x18004f2e2  div     dword ptr [rbx+2Ch]
0x18004f2e5  add     [rbx+20h], eax
0x18004f2e8  mov     dword ptr [rbx+24h], 0
0x18004f2ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f2f6  cmp     rcx, r12
0x18004f2f9  jz      short loc_18004F31C
0x18004f2fb  test    byte ptr [rcx+44h], 8
0x18004f2ff  jz      short loc_18004F31C
0x18004f301  cmp     byte ptr [rcx+41h], 5
0x18004f305  jb      short loc_18004F31C
0x18004f307  mov     edx, 45h ; 'E'
0x18004f30c  lea     r8, WPP_8e2b0b69082e3632e54b14a24be2ca55_Traceguids
0x18004f313  mov     rcx, [rcx+38h]
0x18004f317  call    WPP_SF_
0x18004f31c  mov     rcx, [rbp+40h+var_48]
0x18004f320  xor     rcx, rsp; StackCookie
0x18004f323  call    __security_check_cookie
0x18004f328  add     rsp, 108h
0x18004f32f  pop     r15
0x18004f331  pop     r14
0x18004f333  pop     r13
0x18004f335  pop     r12
0x18004f337  pop     rdi
0x18004f338  pop     rsi
0x18004f339  pop     rbx
0x18004f33a  pop     rbp
0x18004f33b  retn
```
