# CWbemContext::CContextObj::Marshal(IStream *)

- ea: `0x180052a30`
- end: `0x180052daf`
- name: `?Marshal@CContextObj@CWbemContext@@QEAAJPEAUIStream@@@Z`
- size: `895`
- prototype: `__int64 __fastcall(CWbemContext::CContextObj *this, struct IStream *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180052810`

## callees

- `0x180037120`
- `0x180052a30`
- `0x180052db8`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180052d35`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180052d35`
- `wbemcomn!GetMemLogObject` at `0x180052bd6`
- `wbemcomn!GetMemLogObject` at `0x180052c09`
- `wbemcomn!GetMemLogObject` at `0x180052c45`
- `wbemcomn!GetMemLogObject` at `0x180052cbe`
- `wbemcomn!GetMemLogObject` at `0x180052d40`
- `wbemcomn!GetMemLogObject` at `0x180052d92`
- `wbemcomn!GetMemLogObject` at `0x180052bd6`
- `wbemcomn!GetMemLogObject` at `0x180052c09`
- `wbemcomn!GetMemLogObject` at `0x180052c45`
- `wbemcomn!GetMemLogObject` at `0x180052cbe`
- `wbemcomn!GetMemLogObject` at `0x180052d40`
- `wbemcomn!GetMemLogObject` at `0x180052d92`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052be1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052c14`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052c50`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052cc9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052d4b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052d9d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052be1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052c14`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052c50`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052cc9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052d4b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180052d9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWbemContext::CContextObj::Marshal(CWbemContext::CContextObj *this, struct IStream *a2)
{
  __int64 v2; // r13
  __int64 v3; // r12
  __int64 v5; // rax
  int v7; // ebx
  int v8; // edx
  char *v9; // r14
  struct IStreamVtbl *lpVtbl; // rax
  char *v11; // rdx
  __int64 v12; // r8
  struct IStream *v13; // rcx
  int v14; // eax
  CWbemRefreshingSvc *v15; // rcx
  CMemoryLog *v17; // rax
  __int64 v18; // rdx
  CMemoryLog *v19; // rax
  CMemoryLog *v20; // rax
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  int v24; // [rsp+70h] [rbp+8h] BYREF

  v2 = *(_QWORD *)this;
  v3 = -1;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(v2 + 2 * v5) );
  v24 = v5;
  v7 = ((__int64 (__fastcall *)(struct IStream *, int *, __int64))a2->lpVtbl->Write)(a2, &v24, 4);
  if ( v7 < 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, v7);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
        (unsigned int)v7);
    }
    goto LABEL_24;
  }
  v7 = ((__int64 (__fastcall *)(struct IStream *, __int64, _QWORD, _QWORD))a2->lpVtbl->Write)(
         a2,
         v2,
         (unsigned int)(2 * v24),
         0);
  if ( v7 < 0 )
  {
LABEL_24:
    v17 = GetMemLogObject();
    CMemoryLog::Write(v17, v7);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v7;
    }
    v18 = 43;
    goto LABEL_39;
  }
  v7 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64))a2->lpVtbl->Write)(a2, (char *)this + 8, 4);
  if ( v7 < 0 )
  {
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, v7);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v7;
    }
    v18 = 44;
    goto LABEL_39;
  }
  v7 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64))a2->lpVtbl->Write)(a2, (char *)this + 16, 2);
  if ( v7 < 0 )
  {
    v19 = GetMemLogObject();
    CMemoryLog::Write(v19, v7);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v7;
    }
    v18 = 45;
    goto LABEL_39;
  }
  v8 = *((unsigned __int16 *)this + 8);
  if ( v8 == 1 )
    goto LABEL_51;
  if ( *((_WORD *)this + 8) == 8 )
  {
    v9 = (char *)*((_QWORD *)this + 3);
    do
      ++v3;
    while ( *(_WORD *)&v9[2 * v3] );
    lpVtbl = a2->lpVtbl;
    v24 = v3;
    v7 = ((__int64 (__fastcall *)(struct IStream *, int *, __int64))lpVtbl->Write)(a2, &v24, 4);
    if ( v7 < 0 )
    {
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, v7);
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_16;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids,
        (unsigned int)v7);
LABEL_15:
      v15 = WPP_GLOBAL_Control;
LABEL_16:
      if ( v7 >= 0 )
        goto LABEL_17;
      v23 = GetMemLogObject();
      CMemoryLog::Write(v23, v7);
LABEL_51:
      v15 = WPP_GLOBAL_Control;
LABEL_17:
      if ( v15 == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)v15 + 28) & 1) == 0
        || *((_BYTE *)v15 + 25) < 2u )
      {
        return (unsigned int)v7;
      }
      v18 = 46;
LABEL_39:
      WPP_SF_d(*((_QWORD *)v15 + 2), v18, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids, (unsigned int)v7);
      return (unsigned int)v7;
    }
    v11 = v9;
    v12 = (unsigned int)(2 * v24);
    v13 = a2;
    goto LABEL_13;
  }
  if ( *((_WORD *)this + 8) == 13 )
  {
    v14 = CoMarshalInterface(a2, &IID_IWbemClassObject, *((LPUNKNOWN *)this + 3), 0, 0, 0);
    goto LABEL_14;
  }
  if ( (v8 & 0xFFFFDFFF) != 9 )
  {
    v13 = a2;
    if ( (v8 & 0x2000) != 0 )
    {
      v14 = MarshalSafeArray(a2, v8 & 0xDFFF, *((struct tagSAFEARRAY **)this + 3));
      goto LABEL_14;
    }
    v12 = 8;
    v11 = (char *)this + 24;
LABEL_13:
    v14 = ((__int64 (__fastcall *)(struct IStream *, char *, __int64, _QWORD))a2->lpVtbl->Write)(v13, v11, v12, 0);
LABEL_14:
    v7 = v14;
    goto LABEL_15;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180052a30  push    rbx
0x180052a32  push    rdi
0x180052a33  push    r12
0x180052a35  push    r13
0x180052a37  push    r14
0x180052a39  push    r15
0x180052a3b  sub     rsp, 38h
0x180052a3f  mov     r13, [rcx]
0x180052a42  or      r12, 0FFFFFFFFFFFFFFFFh
0x180052a46  mov     r14, rcx
0x180052a49  mov     rax, r12
0x180052a4c  xor     ecx, ecx
0x180052a4e  mov     rdi, rdx
0x180052a51  inc     rax
0x180052a54  cmp     [r13+rax*2+0], cx
0x180052a5a  jnz     short loc_180052A51
0x180052a5c  mov     [rsp+68h+arg_0], eax
0x180052a60  xor     r9d, r9d
0x180052a63  mov     rax, [rdx]
0x180052a66  mov     rcx, rdi
0x180052a69  lea     rdx, [rsp+68h+arg_0]
0x180052a6e  lea     r8d, [r9+4]
0x180052a72  mov     rax, [rax+20h]
0x180052a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052a7b  lea     r15, WPP_GLOBAL_Control
0x180052a82  mov     ebx, eax
0x180052a84  test    eax, eax
0x180052a86  js      loc_180052CBE
0x180052a8c  mov     rax, [rdi]
0x180052a8f  xor     r9d, r9d
0x180052a92  mov     r8d, [rsp+68h+arg_0]
0x180052a97  mov     rdx, r13
0x180052a9a  add     r8d, r8d
0x180052a9d  mov     rcx, rdi
0x180052aa0  mov     rax, [rax+20h]
0x180052aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052aa9  mov     ebx, eax
0x180052aab  test    eax, eax
0x180052aad  js      loc_180052BD6
0x180052ab3  mov     rax, [rdi]
0x180052ab6  lea     rdx, [r14+8]
0x180052aba  xor     r9d, r9d
0x180052abd  mov     rcx, rdi
0x180052ac0  mov     rax, [rax+20h]
0x180052ac4  lea     r8d, [r9+4]
0x180052ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052acd  mov     ebx, eax
0x180052acf  test    eax, eax
0x180052ad1  js      loc_180052C45
0x180052ad7  mov     rax, [rdi]
0x180052ada  lea     rdx, [r14+10h]
0x180052ade  xor     r9d, r9d
0x180052ae1  mov     rcx, rdi
0x180052ae4  mov     rax, [rax+20h]
0x180052ae8  lea     r8d, [r9+2]
0x180052aec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052af1  xor     r8d, r8d
0x180052af4  mov     ebx, eax
0x180052af6  test    eax, eax
0x180052af8  js      loc_180052C09
0x180052afe  movzx   edx, word ptr [r14+10h]
0x180052b03  lea     r15, WPP_GLOBAL_Control
0x180052b0a  mov     ecx, edx
0x180052b0c  sub     ecx, 1
0x180052b0f  jz      loc_180052DA3
0x180052b15  sub     ecx, 7
0x180052b18  jnz     loc_180052BA4
0x180052b1e  mov     r14, [r14+18h]
0x180052b22  inc     r12
0x180052b25  cmp     [r14+r12*2], r8w
0x180052b2a  jnz     short loc_180052B22
0x180052b2c  mov     rax, [rdi]
0x180052b2f  lea     rdx, [rsp+68h+arg_0]
0x180052b34  xor     r9d, r9d
0x180052b37  mov     [rsp+68h+arg_0], r12d
0x180052b3c  mov     rcx, rdi
0x180052b3f  mov     rax, [rax+20h]
0x180052b43  lea     r8d, [r9+4]
0x180052b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b4c  mov     ebx, eax
0x180052b4e  test    eax, eax
0x180052b50  js      loc_180052D40
0x180052b56  mov     r8d, [rsp+68h+arg_0]
0x180052b5b  mov     rdx, r14
0x180052b5e  add     r8d, r8d
0x180052b61  mov     rcx, rdi
0x180052b64  mov     rax, [rdi]
0x180052b67  xor     r9d, r9d
0x180052b6a  mov     rax, [rax+20h]
0x180052b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b73  mov     ebx, eax
0x180052b75  mov     rcx, cs:WPP_GLOBAL_Control
0x180052b7c  test    ebx, ebx
0x180052b7e  js      loc_180052D92
0x180052b84  cmp     rcx, r15
0x180052b87  jz      short loc_180052B93
0x180052b89  test    byte ptr [rcx+1Ch], 1
0x180052b8d  jnz     loc_180052C97
0x180052b93  mov     eax, ebx
0x180052b95  add     rsp, 38h
0x180052b99  pop     r15
0x180052b9b  pop     r14
0x180052b9d  pop     r13
0x180052b9f  pop     r12
0x180052ba1  pop     rdi
0x180052ba2  pop     rbx
0x180052ba3  retn
0x180052ba4  cmp     ecx, 5
0x180052ba7  jz      loc_180052D1A
0x180052bad  mov     eax, edx
0x180052baf  btr     eax, 0Dh
0x180052bb3  cmp     eax, 9
0x180052bb6  jz      loc_180052D10
0x180052bbc  bt      dx, 0Dh
0x180052bc1  mov     rcx, rdi; struct IStream *
0x180052bc4  jb      loc_180052C81
0x180052bca  mov     r8d, 8
0x180052bd0  lea     rdx, [r14+18h]
0x180052bd4  jmp     short loc_180052B64
0x180052bd6  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180052bdc  mov     rcx, rax
0x180052bdf  mov     edx, ebx
0x180052be1  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180052be7  mov     rcx, cs:WPP_GLOBAL_Control
0x180052bee  cmp     rcx, r15
0x180052bf1  jz      short loc_180052B93
0x180052bf3  test    byte ptr [rcx+1Ch], 1
0x180052bf7  jz      short loc_180052B93
0x180052bf9  cmp     byte ptr [rcx+19h], 2
0x180052bfd  jb      short loc_180052B93
0x180052bff  mov     edx, 2Bh ; '+'
0x180052c04  jmp     loc_180052CA6
0x180052c09  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180052c0f  mov     rcx, rax
0x180052c12  mov     edx, ebx
0x180052c14  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180052c1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180052c21  cmp     rcx, r15
0x180052c24  jz      loc_180052B93
0x180052c2a  test    byte ptr [rcx+1Ch], 1
0x180052c2e  jz      loc_180052B93
0x180052c34  cmp     byte ptr [rcx+19h], 2
0x180052c38  jb      loc_180052B93
0x180052c3e  mov     edx, 2Dh ; '-'
0x180052c43  jmp     short loc_180052CA6
0x180052c45  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180052c4b  mov     rcx, rax
0x180052c4e  mov     edx, ebx
0x180052c50  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180052c56  mov     rcx, cs:WPP_GLOBAL_Control
0x180052c5d  cmp     rcx, r15
0x180052c60  jz      loc_180052B93
0x180052c66  test    byte ptr [rcx+1Ch], 1
0x180052c6a  jz      loc_180052B93
0x180052c70  cmp     byte ptr [rcx+19h], 2
0x180052c74  jb      loc_180052B93
0x180052c7a  mov     edx, 2Ch ; ','
0x180052c7f  jmp     short loc_180052CA6
0x180052c81  mov     r8, [r14+18h]; struct tagSAFEARRAY *
0x180052c85  mov     eax, 0DFFFh
0x180052c8a  and     dx, ax; unsigned __int16
0x180052c8d  call    ?MarshalSafeArray@@YAJPEAUIStream@@GPEAUtagSAFEARRAY@@@Z; MarshalSafeArray(IStream *,ushort,tagSAFEARRAY *)
0x180052c92  jmp     loc_180052B73
0x180052c97  cmp     byte ptr [rcx+19h], 2
0x180052c9b  jb      loc_180052B93
0x180052ca1  mov     edx, 2Eh ; '.'
0x180052ca6  mov     rcx, [rcx+10h]
0x180052caa  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180052cb1  mov     r9d, ebx
0x180052cb4  call    WPP_SF_d
0x180052cb9  jmp     loc_180052B93
0x180052cbe  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180052cc4  mov     rcx, rax
0x180052cc7  mov     edx, ebx
0x180052cc9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180052ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180052cd6  cmp     rcx, r15
0x180052cd9  jz      loc_180052BD6
0x180052cdf  test    byte ptr [rcx+1Ch], 1
0x180052ce3  jz      loc_180052BD6
0x180052ce9  cmp     byte ptr [rcx+19h], 2
0x180052ced  jb      loc_180052BD6
0x180052cf3  mov     rcx, [rcx+10h]
0x180052cf7  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180052cfe  mov     edx, 0Ah
0x180052d03  mov     r9d, ebx
0x180052d06  call    WPP_SF_d
0x180052d0b  jmp     loc_180052BD6
0x180052d10  mov     eax, 80004005h
0x180052d15  jmp     loc_180052B95
0x180052d1a  mov     [rsp+68h+mshlflags], r8d; mshlflags
0x180052d1f  lea     rdx, IID_IWbemClassObject; riid
0x180052d26  mov     [rsp+68h+pvDestContext], r8; pvDestContext
0x180052d2b  xor     r9d, r9d; dwDestContext
0x180052d2e  mov     r8, [r14+18h]; pUnk
0x180052d32  mov     rcx, rdi; pStm
0x180052d35  call    cs:__imp_CoMarshalInterface
0x180052d3b  jmp     loc_180052B73
0x180052d40  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180052d46  mov     rcx, rax
0x180052d49  mov     edx, ebx
0x180052d4b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180052d51  mov     rcx, cs:WPP_GLOBAL_Control
0x180052d58  cmp     rcx, r15
0x180052d5b  jz      loc_180052B7C
0x180052d61  test    byte ptr [rcx+1Ch], 1
0x180052d65  jz      loc_180052B7C
0x180052d6b  cmp     byte ptr [rcx+19h], 2
0x180052d6f  jb      loc_180052B7C
0x180052d75  mov     rcx, [rcx+10h]
0x180052d79  lea     r8, WPP_fd1f582ee25a35696b713d99f0d4f31b_Traceguids
0x180052d80  mov     edx, 0Ah
0x180052d85  mov     r9d, ebx
0x180052d88  call    WPP_SF_d
0x180052d8d  jmp     loc_180052B75
0x180052d92  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180052d98  mov     rcx, rax
0x180052d9b  mov     edx, ebx
0x180052d9d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180052da3  mov     rcx, cs:WPP_GLOBAL_Control
0x180052daa  jmp     loc_180052B84
```
