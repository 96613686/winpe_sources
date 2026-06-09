# __FrameHandler4::FrameUnwindToState(unsigned __int64 *,_xDISPATCHER_CONTEXT *,FH4::FuncInfo4 *,int)

- ea: `0x1800047a0`
- end: `0x180004ab9`
- name: `?FrameUnwindToState@__FrameHandler4@@SAXPEA_KPEAU_xDISPATCHER_CONTEXT@@PEAUFuncInfo4@FH4@@H@Z`
- size: `793`
- prototype: `void __fastcall(unsigned __int64 *, struct _xDISPATCHER_CONTEXT *, struct FH4::FuncInfo4 *, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, installer_update`

## callers

- `0x180002144`
- `0x180003e28`

## callees

- `0x180001500`
- `0x1800026b0`
- `0x1800026e0`
- `0x180002978`
- `0x180002e18`
- `0x180002f7c`
- `0x1800047a0`
- `0x180004c28`
- `0x180004cf4`
- `0x180004dc8`
- `0x180004fb0`
- `0x180005060`
- `0x180005152`

## pseudocode

```c
void __fastcall __FrameHandler4::FrameUnwindToState(
        unsigned __int64 *a1,
        struct _xDISPATCHER_CONTEXT *a2,
        struct FH4::FuncInfo4 *a3,
        int a4)
{
  __int64 ImageBase; // rdi
  int v9; // esi
  struct _xDISPATCHER_CONTEXT *v10; // r15
  __int64 v11; // rax
  FH4::UWMap4 *v12; // rdx
  _BYTE *v13; // rdx
  __int64 v14; // rcx
  FH4::UWMap4 *v15; // r12
  FH4::UWMap4 *v16; // rbx
  int v17; // edi
  int StateFromIterators; // eax
  int v19; // r9d
  int v20; // ecx
  _QWORD *v21; // r8
  __int64 v22; // rax
  FH4::UWMap4 *v24[2]; // [rsp+40h] [rbp-F8h] BYREF
  int v25; // [rsp+50h] [rbp-E8h]
  int v26; // [rsp+54h] [rbp-E4h]
  unsigned int v27; // [rsp+58h] [rbp-E0h]
  int v28; // [rsp+5Ch] [rbp-DCh]
  int v29; // [rsp+60h] [rbp-D8h]
  __int64 v30; // [rsp+68h] [rbp-D0h]
  int *v31; // [rsp+70h] [rbp-C8h] BYREF
  FH4::UWMap4 *v32; // [rsp+78h] [rbp-C0h]
  unsigned __int64 *v33; // [rsp+80h] [rbp-B8h]
  __int64 v34; // [rsp+88h] [rbp-B0h]
  unsigned __int64 *v35; // [rsp+90h] [rbp-A8h]
  struct _xDISPATCHER_CONTEXT *v36; // [rsp+98h] [rbp-A0h]
  struct _xDISPATCHER_CONTEXT *v37; // [rsp+A0h] [rbp-98h]
  int *v38; // [rsp+A8h] [rbp-90h]
  FH4::UWMap4 *v39; // [rsp+B0h] [rbp-88h]
  __int128 v40; // [rsp+C0h] [rbp-78h] BYREF
  int v41; // [rsp+D0h] [rbp-68h] BYREF
  FH4::UWMap4 *v42; // [rsp+D8h] [rbp-60h]
  __int128 v43; // [rsp+E0h] [rbp-58h]

  v35 = a1;
  v36 = a2;
  v29 = a4;
  ImageBase = GetImageBase();
  v30 = ImageBase;
  v9 = __FrameHandler4::StateFromControlPc(a3, a2);
  v10 = a2 + 1;
  v37 = a2 + 1;
  if ( LODWORD(a2[1].ControlPc) )
  {
    if ( *(_DWORD *)(_vcrt_getptd() + 120) != -2 )
      abort_0();
    v9 = LODWORD(v10->ControlPc) - 2;
  }
  else if ( *(_DWORD *)(_vcrt_getptd() + 120) != -2 )
  {
    v9 = *(_DWORD *)(_vcrt_getptd() + 120);
    *(_DWORD *)(_vcrt_getptd() + 120) = -2;
  }
  v11 = _vcrt_getptd();
  ++*(_DWORD *)(v11 + 48);
  v12 = 0;
  v42 = 0;
  v43 = 0;
  if ( *((_DWORD *)a3 + 2) )
  {
    v13 = (_BYTE *)(*((int *)a3 + 2) + a2->ImageBase);
    v14 = *v13 & 0xF;
    v12 = (FH4::UWMap4 *)&v13[-*((char *)&FH4::s_negLengthTab + v14)];
    v41 = *((_DWORD *)v12 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v14);
    v42 = v12;
  }
  else
  {
    v41 = 0;
  }
  v24[0] = (FH4::UWMap4 *)&v41;
  v24[1] = v12;
  v31 = &v41;
  v32 = v12;
  v33 = a1;
  v34 = ImageBase;
  FH4::UWMap4::getStartStop(
    (FH4::UWMap4 *)&v41,
    v9,
    a4,
    (struct FH4::UWMap4::iterator *)v24,
    (struct FH4::UWMap4::iterator *)&v31);
  while ( 1 )
  {
    v38 = &v41;
    v39 = v42;
    v15 = v24[1];
    if ( v24[1] < v42 || v24[1] <= v32 )
      break;
    FH4::UWMap4::ReadEntry(v24[0], (unsigned __int8 **)&v24[1]);
    v24[1] = v15;
    v16 = v24[0];
    v25 = *((_DWORD *)v24[0] + 5);
    v17 = *((_DWORD *)v24[0] + 6);
    v27 = *((_DWORD *)v24[0] + 7);
    v40 = *(_OWORD *)v24;
    FH4::UWMap4::ReadEntry(v24[0], (unsigned __int8 **)&v24[1]);
    v24[1] = (FH4::UWMap4 *)((char *)v15 - *((unsigned int *)v16 + 4));
    StateFromIterators = FH4::UWMap4::getStateFromIterators(
                           (const struct FH4::UWMap4::iterator *)&v31,
                           a4,
                           (const struct FH4::UWMap4::iterator *)&v40,
                           v9,
                           (const struct FH4::UWMap4::iterator *)v24);
    v9 = StateFromIterators;
    v28 = StateFromIterators;
    v26 = 0;
    v19 = 0;
    v20 = v25;
    if ( v25 )
      v19 = v17;
    v26 = v19;
    if ( v19 )
    {
      LODWORD(v10->ControlPc) = StateFromIterators + 2;
      if ( (unsigned int)(v20 - 1) <= 1 )
      {
        v21 = (_QWORD *)(*v33 + v27);
        if ( v20 == 2 )
          v21 = (_QWORD *)*v21;
        CallSettingFrameEncoded(v19 + a2->ImageBase, *v33, v21, 259);
      }
      else
      {
        CallSettingFrame(v19 + a2->ImageBase, a1, 259);
      }
      SetImageBase(v30);
    }
  }
  if ( *(int *)(_vcrt_getptd() + 48) > 0 )
  {
    v22 = _vcrt_getptd();
    --*(_DWORD *)(v22 + 48);
  }
}

```

## disassembly

```asm
0x1800047a0  push    rbx
0x1800047a2  push    rsi
0x1800047a3  push    rdi
0x1800047a4  push    r12
0x1800047a6  push    r13
0x1800047a8  push    r14
0x1800047aa  push    r15
0x1800047ac  sub     rsp, 100h
0x1800047b3  mov     rax, cs:__security_cookie
0x1800047ba  xor     rax, rsp
0x1800047bd  mov     [rsp+138h+var_48], rax
0x1800047c5  mov     r12d, r9d
0x1800047c8  mov     [rsp+138h+var_108], r9d
0x1800047cd  mov     rbx, r8
0x1800047d0  mov     r14, rdx
0x1800047d3  mov     r13, rcx
0x1800047d6  mov     [rsp+138h+var_A8], rcx
0x1800047de  mov     [rsp+138h+var_A0], rdx
0x1800047e6  mov     [rsp+138h+var_D8], r9d
0x1800047eb  call    _GetImageBase
0x1800047f0  mov     rdi, rax
0x1800047f3  mov     [rsp+138h+var_D0], rax
0x1800047f8  mov     rdx, r14; struct _xDISPATCHER_CONTEXT *
0x1800047fb  mov     rcx, rbx; struct FH4::FuncInfo4 *
0x1800047fe  call    ?StateFromControlPc@__FrameHandler4@@SAHPEAUFuncInfo4@FH4@@PEAU_xDISPATCHER_CONTEXT@@@Z; __FrameHandler4::StateFromControlPc(FH4::FuncInfo4 *,_xDISPATCHER_CONTEXT *)
0x180004803  mov     esi, eax
0x180004805  lea     r15, [r14+48h]
0x180004809  mov     [rsp+138h+var_98], r15
0x180004811  cmp     dword ptr [r15], 0
0x180004815  jz      short loc_18000482E
0x180004817  call    __vcrt_getptd
0x18000481c  cmp     dword ptr [rax+78h], 0FFFFFFFEh
0x180004820  jnz     loc_180004AB3
0x180004826  mov     esi, [r15]
0x180004829  sub     esi, 2
0x18000482c  jmp     short loc_18000484D
0x18000482e  call    __vcrt_getptd
0x180004833  cmp     dword ptr [rax+78h], 0FFFFFFFEh
0x180004837  jz      short loc_18000484D
0x180004839  call    __vcrt_getptd
0x18000483e  mov     esi, [rax+78h]
0x180004841  call    __vcrt_getptd
0x180004846  mov     dword ptr [rax+78h], 0FFFFFFFEh
0x18000484d  call    __vcrt_getptd
0x180004852  inc     dword ptr [rax+30h]
0x180004855  xor     edx, edx
0x180004857  mov     [rsp+138h+var_60], rdx
0x18000485f  xorps   xmm0, xmm0
0x180004862  movups  [rsp+138h+var_58], xmm0
0x18000486a  cmp     [rbx+8], edx
0x18000486d  jz      short loc_1800048B1
0x18000486f  movsxd  rcx, dword ptr [rbx+8]
0x180004873  mov     rdx, [r14+8]
0x180004877  add     rdx, rcx
0x18000487a  movzx   ecx, byte ptr [rdx]
0x18000487d  and     ecx, 0Fh
0x180004880  lea     r8, cs:180000000h
0x180004887  movsx   rax, byte ptr [rcx+r8+10238h]
0x180004890  sub     rdx, rax
0x180004893  mov     cl, [rcx+r8+10248h]
0x18000489b  mov     eax, [rdx-4]
0x18000489e  shr     eax, cl
0x1800048a0  mov     [rsp+138h+var_68], eax
0x1800048a7  mov     [rsp+138h+var_60], rdx
0x1800048af  jmp     short loc_1800048B8
0x1800048b1  mov     [rsp+138h+var_68], edx
0x1800048b8  lea     rax, [rsp+138h+var_68]
0x1800048c0  mov     [rsp+138h+var_F8], rax
0x1800048c5  mov     [rsp+138h+var_F8+8], rdx
0x1800048ca  lea     rax, [rsp+138h+var_68]
0x1800048d2  mov     [rsp+138h+var_C8], rax
0x1800048d7  mov     [rsp+138h+var_C0], rdx
0x1800048dc  mov     [rsp+138h+var_B8], r13
0x1800048e4  mov     [rsp+138h+var_B0], rdi
0x1800048ec  lea     rax, [rsp+138h+var_C8]
0x1800048f1  mov     [rsp+138h+var_118], rax; struct FH4::UWMap4::iterator *
0x1800048f6  lea     r9, [rsp+138h+var_F8]; struct FH4::UWMap4::iterator *
0x1800048fb  mov     r8d, r12d; int
0x1800048fe  mov     edx, esi; int
0x180004900  lea     rcx, [rsp+138h+var_68]; this
0x180004908  call    ?getStartStop@UWMap4@FH4@@QEAAXHHAEAViterator@12@0@Z; FH4::UWMap4::getStartStop(int,int,FH4::UWMap4::iterator &,FH4::UWMap4::iterator &)
0x18000490d  nop
0x18000490e  lea     rax, [rsp+138h+var_68]
0x180004916  mov     [rsp+138h+var_90], rax
0x18000491e  mov     rax, [rsp+138h+var_60]
0x180004926  mov     [rsp+138h+var_88], rax
0x18000492e  mov     r12, [rsp+138h+var_F8+8]
0x180004933  cmp     r12, rax
0x180004936  jb      loc_180004A7D
0x18000493c  cmp     r12, [rsp+138h+var_C0]
0x180004941  jbe     loc_180004A7D
0x180004947  lea     rdx, [rsp+138h+var_F8+8]; unsigned __int8 **
0x18000494c  mov     rcx, [rsp+138h+var_F8]; this
0x180004951  call    ?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z; FH4::UWMap4::ReadEntry(uchar * *)
0x180004956  mov     [rsp+138h+var_F8+8], r12
0x18000495b  mov     rbx, [rsp+138h+var_F8]
0x180004960  mov     eax, [rbx+14h]
0x180004963  mov     [rsp+138h+var_E8], eax
0x180004967  mov     edi, [rbx+18h]
0x18000496a  mov     eax, [rbx+1Ch]
0x18000496d  mov     [rsp+138h+var_E0], eax
0x180004971  movaps  xmm0, xmmword ptr [rsp+138h+var_F8]
0x180004976  movdqa  [rsp+138h+var_78], xmm0
0x18000497f  lea     rdx, [rsp+138h+var_F8+8]; unsigned __int8 **
0x180004984  mov     rcx, rbx; this
0x180004987  call    ?ReadEntry@UWMap4@FH4@@AEAAXPEAPEAE@Z; FH4::UWMap4::ReadEntry(uchar * *)
0x18000498c  mov     eax, [rbx+10h]
0x18000498f  sub     r12, rax
0x180004992  mov     [rsp+138h+var_F8+8], r12
0x180004997  lea     rax, [rsp+138h+var_F8]
0x18000499c  mov     [rsp+138h+var_118], rax; struct FH4::UWMap4::iterator *
0x1800049a1  mov     r9d, esi; int
0x1800049a4  lea     r8, [rsp+138h+var_78]; struct FH4::UWMap4::iterator *
0x1800049ac  mov     edx, [rsp+138h+var_108]; int
0x1800049b0  lea     rcx, [rsp+138h+var_C8]; struct FH4::UWMap4::iterator *
0x1800049b5  call    ?getStateFromIterators@UWMap4@FH4@@SAHAEBViterator@12@H0H0@Z; FH4::UWMap4::getStateFromIterators(FH4::UWMap4::iterator const &,int,FH4::UWMap4::iterator const &,int,FH4::UWMap4::iterator const &)
0x1800049ba  mov     esi, eax
0x1800049bc  mov     [rsp+138h+var_DC], eax
0x1800049c0  mov     [rsp+138h+var_E4], 0
0x1800049c8  xor     r9d, r9d
0x1800049cb  mov     ecx, [rsp+138h+var_E8]
0x1800049cf  test    ecx, ecx
0x1800049d1  cmovnz  r9d, edi
0x1800049d5  mov     [rsp+138h+var_E4], r9d
0x1800049da  test    r9d, r9d
0x1800049dd  jz      loc_180004A78
0x1800049e3  lea     eax, [rax+2]
0x1800049e6  mov     [r15], eax
0x1800049e9  lea     eax, [rcx-1]
0x1800049ec  cmp     eax, 1
0x1800049ef  jbe     short loc_180004A0B
0x1800049f1  mov     rcx, [r14+8]
0x1800049f5  movsxd  rax, r9d
0x1800049f8  add     rcx, rax
0x1800049fb  mov     r8d, 103h
0x180004a01  mov     rdx, r13
0x180004a04  call    _CallSettingFrame
0x180004a09  jmp     short loc_180004A3B
0x180004a0b  mov     rax, [rsp+138h+var_B8]
0x180004a13  mov     rdx, [rax]
0x180004a16  mov     r8d, [rsp+138h+var_E0]
0x180004a1b  add     r8, rdx
0x180004a1e  cmp     ecx, 2
0x180004a21  jnz     short loc_180004A26
0x180004a23  mov     r8, [r8]
0x180004a26  mov     rcx, [r14+8]
0x180004a2a  movsxd  rax, r9d
0x180004a2d  add     rcx, rax
0x180004a30  mov     r9d, 103h
0x180004a36  call    _CallSettingFrameEncoded
0x180004a3b  mov     rcx, [rsp+138h+var_D0]
0x180004a40  call    _SetImageBase
0x180004a45  jmp     short loc_180004A78
0x180004a47  mov     rax, [rsp+138h+var_B0]
0x180004a4f  mov     [rsp+138h+var_D0], rax
0x180004a54  mov     esi, [rsp+138h+var_DC]
0x180004a58  mov     r13, [rsp+138h+var_A8]
0x180004a60  mov     r14, [rsp+138h+var_A0]
0x180004a68  mov     eax, [rsp+138h+var_D8]
0x180004a6c  mov     [rsp+138h+var_108], eax
0x180004a70  mov     r15, [rsp+138h+var_98]
0x180004a78  jmp     loc_18000490E
0x180004a7d  call    __vcrt_getptd
0x180004a82  cmp     dword ptr [rax+30h], 0
0x180004a86  jle     short loc_180004A90
0x180004a88  call    __vcrt_getptd
0x180004a8d  dec     dword ptr [rax+30h]
0x180004a90  mov     rcx, [rsp+138h+var_48]
0x180004a98  xor     rcx, rsp; StackCookie
0x180004a9b  call    __security_check_cookie
0x180004aa0  add     rsp, 100h
0x180004aa7  pop     r15
0x180004aa9  pop     r14
0x180004aab  pop     r13
0x180004aad  pop     r12
0x180004aaf  pop     rdi
0x180004ab0  pop     rsi
0x180004ab1  pop     rbx
0x180004ab2  retn
0x180004ab3  call    abort_0
0x18000bf18  push    rbp
0x18000bf1a  sub     rsp, 30h
0x18000bf1e  mov     rbp, rdx
0x18000bf21  call    __FrameUnwindFilter
0x18000bf26  nop
0x18000bf27  add     rsp, 30h
0x18000bf2b  pop     rbp
0x18000bf2c  retn
0x18000bf2e  push    rbp
0x18000bf30  sub     rsp, 30h
0x18000bf34  mov     rbp, rdx
0x18000bf37  call    __vcrt_getptd
0x18000bf3c  cmp     dword ptr [rax+30h], 0
0x18000bf40  jle     short loc_18000BF4A
0x18000bf42  call    __vcrt_getptd
0x18000bf47  dec     dword ptr [rax+30h]
0x18000bf4a  add     rsp, 30h
0x18000bf4e  pop     rbp
0x18000bf4f  retn
```
