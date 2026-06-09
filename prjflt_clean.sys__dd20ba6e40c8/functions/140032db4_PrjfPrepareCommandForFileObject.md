# PrjfPrepareCommandForFileObject

- ea: `0x140032db4`
- end: `0x140032fd2`
- name: `PrjfPrepareCommandForFileObject`
- size: `542`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140034428`
- `0x1400346f0`
- `0x1400349fc`
- `0x140035060`

## callees

- `0x140002d9c`
- `0x14000f4e4`
- `0x140032db4`
- `0x140032fd8`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x140032f88`
- `FLTMGR!FltReleaseContext` at `0x140032f9c`
- `FLTMGR!FltReleaseContext` at `0x140032fb1`
- `FLTMGR!FltReleaseContext` at `0x140032f88`
- `FLTMGR!FltReleaseContext` at `0x140032f9c`
- `FLTMGR!FltReleaseContext` at `0x140032fb1`

## pseudocode

```c
__int64 __fastcall PrjfPrepareCommandForFileObject(
        struct _FLT_INSTANCE *a1,
        struct _FILE_OBJECT *a2,
        int a3,
        _OWORD *a4,
        __int64 a5,
        _QWORD *a6,
        unsigned int *a7)
{
  int v7; // esi
  char ContextFileObject; // al
  char *v11; // rdi
  _QWORD *v12; // rbx
  __int64 v13; // rcx
  int v14; // edx
  int v15; // r8d
  __int64 v16; // r8
  _OWORD *v17; // rax
  _OWORD *v18; // rdx
  __int64 v19; // rcx
  __int128 v20; // xmm1
  int v22; // [rsp+20h] [rbp-81h]
  PFLT_CONTEXT v23; // [rsp+70h] [rbp-31h] BYREF
  PFLT_CONTEXT v24; // [rsp+78h] [rbp-29h]
  PFLT_CONTEXT Context[2]; // [rsp+80h] [rbp-21h] BYREF
  __int64 v26; // [rsp+90h] [rbp-11h] BYREF
  _OWORD v27[4]; // [rsp+98h] [rbp-9h] BYREF

  v7 = 0;
  v24 = 0;
  Context[0] = 0;
  *a6 = 0;
  v23 = 0;
  v26 = 0;
  v27[0] = 0;
  ContextFileObject = PrjfGetContextFileObjectEx(a1, a2, &v23);
  v11 = (char *)v24;
  v12 = Context[0];
  if ( ContextFileObject )
  {
    v13 = *((_QWORD *)Context[0] + 9);
    LOWORD(v27[0]) = *(_WORD *)(v13 + 288);
    WORD1(v27[0]) = *(_WORD *)(v13 + 288);
    *((_QWORD *)&v27[0] + 1) = v13 + 290;
    *(_OWORD *)Context = *((_OWORD *)Context[0] + 6);
    v7 = PrjfPrepareCommandForFilePath((unsigned __int16 *)v27, Context, a3, 0, a4, (__int64)v23, 0, &v26, a7);
    if ( v7 >= 0 )
    {
      v16 = v26;
      *(_OWORD *)(v26 + 28) = *(_OWORD *)(v11 + 24);
      if ( v23 )
        *(_OWORD *)(v16 + 44) = *(_OWORD *)((char *)v23 + 56);
      v17 = (_OWORD *)v12[14];
      v18 = (_OWORD *)(v16 + 60);
      v19 = 2;
      do
      {
        *v18 = *v17;
        v18[1] = v17[1];
        v18[2] = v17[2];
        v18[3] = v17[3];
        v18[4] = v17[4];
        v18[5] = v17[5];
        v18[6] = v17[6];
        v20 = v17[7];
        v17 += 8;
        v18[7] = v20;
        v18 += 8;
        --v19;
      }
      while ( v19 );
      *a6 = v16;
    }
    else if ( (BYTE1(xmmword_14001A3D0) & 0x40) != 0
           || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = BYTE1(xmmword_14001A3D0) & 0x40;
      LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdLZ(
        526,
        v14,
        v15,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v22,
        14,
        133,
        (__int64)&WPP_c505924bdc6333f282870af0a028ded4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\message.c",
        22,
        v7,
        a3,
        (__int64)v27);
    }
  }
  if ( v12 )
    FltReleaseContext(v12);
  if ( v11 )
    FltReleaseContext(v11);
  if ( v23 )
    FltReleaseContext(v23);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140032db4  push    rbp
0x140032db6  push    rbx
0x140032db7  push    rsi
0x140032db8  push    rdi
0x140032db9  push    r12
0x140032dbb  push    r14
0x140032dbd  push    r15
0x140032dbf  lea     rbp, [rsp-0Fh]
0x140032dc4  sub     rsp, 0B0h
0x140032dcb  mov     r14, [rbp+3Fh+arg_28]
0x140032dcf  lea     rax, [rbp+3Fh+var_70]
0x140032dd3  xor     esi, esi
0x140032dd5  mov     [rsp+0E0h+var_C0], rax; Context
0x140032dda  mov     r12, r9
0x140032ddd  mov     [rbp+3Fh+var_68], rsi
0x140032de1  mov     r15d, r8d
0x140032de4  mov     [rbp+3Fh+Context], rsi
0x140032de8  xorps   xmm0, xmm0
0x140032deb  mov     [r14], rsi
0x140032dee  lea     r9, [rbp+3Fh+var_68]
0x140032df2  mov     [rbp+3Fh+var_70], rsi
0x140032df6  lea     r8, [rbp+3Fh+Context]
0x140032dfa  mov     [rbp+3Fh+var_50], rsi
0x140032dfe  movups  [rbp+3Fh+var_48], xmm0
0x140032e02  call    PrjfGetContextFileObjectEx
0x140032e07  mov     rdi, [rbp+3Fh+var_68]
0x140032e0b  mov     rbx, [rbp+3Fh+Context]
0x140032e0f  test    al, al
0x140032e11  jz      loc_140032F80
0x140032e17  mov     rcx, [rbx+48h]
0x140032e1b  lea     rdx, [rbp+3Fh+Context]
0x140032e1f  xor     r9d, r9d
0x140032e22  mov     r8d, r15d
0x140032e25  movzx   eax, word ptr [rcx+120h]
0x140032e2c  mov     word ptr [rbp+3Fh+var_48], ax
0x140032e30  movzx   eax, word ptr [rcx+120h]
0x140032e37  mov     word ptr [rbp+3Fh+var_48+2], ax
0x140032e3b  lea     rax, [rcx+122h]
0x140032e42  mov     qword ptr [rbp+3Fh+var_48+8], rax
0x140032e46  lea     rcx, [rbp+3Fh+var_48]
0x140032e4a  mov     rax, [rbp+3Fh+arg_30]
0x140032e4e  movups  xmm0, xmmword ptr [rbx+60h]
0x140032e52  mov     [rsp+0E0h+var_A0], rax
0x140032e57  lea     rax, [rbp+3Fh+var_50]
0x140032e5b  mov     [rsp+0E0h+var_A8], rax
0x140032e60  mov     rax, [rbp+3Fh+var_70]
0x140032e64  mov     [rsp+0E0h+var_B0], rsi
0x140032e69  mov     [rsp+0E0h+var_B8], rax
0x140032e6e  mov     [rsp+0E0h+var_C0], r12
0x140032e73  movdqu  xmmword ptr [rbp+3Fh+Context], xmm0
0x140032e78  call    PrjfPrepareCommandForFilePath
0x140032e7d  mov     esi, eax
0x140032e7f  test    eax, eax
0x140032e81  jns     short loc_140032F01
0x140032e83  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140032e89  lea     rax, WPP_RECORDER_INITIALIZED
0x140032e90  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140032e97  setnz   r8b
0x140032e9b  and     dl, 40h
0x140032e9e  jnz     short loc_140032EA9
0x140032ea0  test    r8b, r8b
0x140032ea3  jz      loc_140032F80
0x140032ea9  mov     r9, cs:WPP_GLOBAL_Control
0x140032eb0  lea     rax, [rbp+3Fh+var_48]
0x140032eb4  mov     [rsp+0E0h+var_80], rax
0x140032eb9  mov     ecx, 20Eh
0x140032ebe  mov     [rsp+0E0h+var_88], r15d
0x140032ec3  lea     rax, aOnecoreBaseFsG_5; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140032eca  mov     [rsp+0E0h+var_90], esi
0x140032ece  mov     r9, [r9+40h]
0x140032ed2  mov     [rsp+0E0h+var_98], 0E16h
0x140032eda  mov     [rsp+0E0h+var_A0], rax
0x140032edf  lea     rax, WPP_c505924bdc6333f282870af0a028ded4_Traceguids
0x140032ee6  mov     [rsp+0E0h+var_A8], rax
0x140032eeb  mov     word ptr [rsp+0E0h+var_B0], 85h
0x140032ef2  mov     dword ptr [rsp+0E0h+var_B8], 0Eh
0x140032efa  call    WPP_RECORDER_AND_TRACE_SF_sDdLZ
0x140032eff  jmp     short loc_140032F80
0x140032f01  mov     r8, [rbp+3Fh+var_50]
0x140032f05  movups  xmm0, xmmword ptr [rdi+18h]
0x140032f09  movdqu  xmmword ptr [r8+1Ch], xmm0
0x140032f0f  mov     rax, [rbp+3Fh+var_70]
0x140032f13  test    rax, rax
0x140032f16  jz      short loc_140032F22
0x140032f18  movups  xmm0, xmmword ptr [rax+38h]
0x140032f1c  movdqu  xmmword ptr [r8+2Ch], xmm0
0x140032f22  mov     rax, [rbx+70h]
0x140032f26  lea     rdx, [r8+3Ch]
0x140032f2a  mov     ecx, 2
0x140032f2f  lea     r9d, [rcx+7Eh]
0x140032f33  movups  xmm0, xmmword ptr [rax]
0x140032f36  movups  xmmword ptr [rdx], xmm0
0x140032f39  movups  xmm1, xmmword ptr [rax+10h]
0x140032f3d  movups  xmmword ptr [rdx+10h], xmm1
0x140032f41  movups  xmm0, xmmword ptr [rax+20h]
0x140032f45  movups  xmmword ptr [rdx+20h], xmm0
0x140032f49  movups  xmm1, xmmword ptr [rax+30h]
0x140032f4d  movups  xmmword ptr [rdx+30h], xmm1
0x140032f51  movups  xmm0, xmmword ptr [rax+40h]
0x140032f55  movups  xmmword ptr [rdx+40h], xmm0
0x140032f59  movups  xmm1, xmmword ptr [rax+50h]
0x140032f5d  movups  xmmword ptr [rdx+50h], xmm1
0x140032f61  movups  xmm0, xmmword ptr [rax+60h]
0x140032f65  movups  xmmword ptr [rdx+60h], xmm0
0x140032f69  movups  xmm1, xmmword ptr [rax+70h]
0x140032f6d  add     rax, r9
0x140032f70  movups  xmmword ptr [rdx+70h], xmm1
0x140032f74  add     rdx, r9
0x140032f77  sub     rcx, 1
0x140032f7b  jnz     short loc_140032F33
0x140032f7d  mov     [r14], r8
0x140032f80  test    rbx, rbx
0x140032f83  jz      short loc_140032F94
0x140032f85  mov     rcx, rbx; Context
0x140032f88  call    cs:__imp_FltReleaseContext
0x140032f8f  nop     dword ptr [rax+rax+00h]
0x140032f94  test    rdi, rdi
0x140032f97  jz      short loc_140032FA8
0x140032f99  mov     rcx, rdi; Context
0x140032f9c  call    cs:__imp_FltReleaseContext
0x140032fa3  nop     dword ptr [rax+rax+00h]
0x140032fa8  mov     rcx, [rbp+3Fh+var_70]; Context
0x140032fac  test    rcx, rcx
0x140032faf  jz      short loc_140032FBD
0x140032fb1  call    cs:__imp_FltReleaseContext
0x140032fb8  nop     dword ptr [rax+rax+00h]
0x140032fbd  mov     eax, esi
0x140032fbf  add     rsp, 0B0h
0x140032fc6  pop     r15
0x140032fc8  pop     r14
0x140032fca  pop     r12
0x140032fcc  pop     rdi
0x140032fcd  pop     rsi
0x140032fce  pop     rbx
0x140032fcf  pop     rbp
0x140032fd0  retn
```
