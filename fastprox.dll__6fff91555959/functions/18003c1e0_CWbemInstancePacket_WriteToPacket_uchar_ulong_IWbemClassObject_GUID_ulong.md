# CWbemInstancePacket::WriteToPacket(uchar *,ulong,IWbemClassObject *,_GUID &,ulong *)

- ea: `0x18003c1e0`
- end: `0x18003c52d`
- name: `?WriteToPacket@CWbemInstancePacket@@QEAAJPEAEKPEAUIWbemClassObject@@AEAU_GUID@@PEAK@Z`
- size: `845`
- prototype: `__int64 __fastcall(CWbemInstancePacket *__hidden this, unsigned __int8 *, unsigned int, struct IWbemClassObject *, struct _GUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18003a890`

## callees

- `0x180035b08`
- `0x180037120`
- `0x18003c1e0`
- `0x18006fa4c`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18003c391`
- `wbemcomn!GetMemLogObject` at `0x18003c3ee`
- `wbemcomn!GetMemLogObject` at `0x18003c455`
- `wbemcomn!GetMemLogObject` at `0x18003c4bc`
- `wbemcomn!GetMemLogObject` at `0x18003c517`
- `wbemcomn!GetMemLogObject` at `0x18003c391`
- `wbemcomn!GetMemLogObject` at `0x18003c3ee`
- `wbemcomn!GetMemLogObject` at `0x18003c455`
- `wbemcomn!GetMemLogObject` at `0x18003c4bc`
- `wbemcomn!GetMemLogObject` at `0x18003c517`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c39c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c3fc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c463`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c4cc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c522`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c39c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c3fc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c463`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c4cc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003c522`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemInstancePacket::WriteToPacket(
        CWbemInstancePacket *this,
        unsigned __int8 *a2,
        unsigned int a3,
        struct IWbemClassObject *a4,
        struct _GUID *a5,
        unsigned int *a6)
{
  unsigned int v8; // ecx
  unsigned int *v9; // r14
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  char v14; // al
  __int64 v15; // r8
  _DWORD *v16; // r8
  __int64 v17; // rax
  CWbemRefreshingSvc *v18; // rcx
  CMemoryLog *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r9
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v24; // rax
  CMemoryLog *v25; // rax
  CMemoryLog *v26; // rax
  _DWORD v27[6]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int pExceptionObject; // [rsp+88h] [rbp+40h] BYREF

  if ( a2 )
  {
    if ( a2 + 9 < a2 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
          "SafeIntException(ERROR_INVALID_PARAMETER)");
      }
      pExceptionObject = 87;
      throw (SafeIntException *)&pExceptionObject;
    }
    *((_QWORD *)this + 3) = a2 + 9;
    if ( a3 < 0x21 )
    {
      v24 = GetMemLogObject();
      CMemoryLog::Write(v24, -2);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids,
          "SafeIntException(ERROR_INVALID_PARAMETER)");
      }
      pExceptionObject = 87;
      throw (SafeIntException *)&pExceptionObject;
    }
    v8 = a3 - 9;
  }
  else
  {
    *((_QWORD *)this + 3) = 0;
    v8 = 0;
  }
  v9 = a6;
  *((_DWORD *)this + 8) = v8;
  *((_QWORD *)this + 1) = a2;
  *((_DWORD *)this + 4) = a3;
  if ( v9 )
  {
    v10 = *(_QWORD *)this;
    pExceptionObject = 0;
    v11 = (*(__int64 (__fastcall **)(CWbemInstancePacket *, struct IWbemClassObject *, _QWORD, _QWORD, unsigned int *))(v10 + 8))(
            this,
            a4,
            0,
            0,
            &pExceptionObject);
    v12 = v11;
    if ( v11 >= 0 )
    {
LABEL_16:
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = 25;
        v22 = v12;
LABEL_26:
        WPP_SF_d(*((_QWORD *)v18 + 2), v21, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids, v22);
        return v12;
      }
      return v12;
    }
    if ( v11 != -2147217348 )
    {
LABEL_42:
      v26 = GetMemLogObject();
      CMemoryLog::Write(v26, v12);
      goto LABEL_16;
    }
    v13 = pExceptionObject + 24;
    v14 = (**(__int64 (__fastcall ***)(CWbemInstancePacket *))this)(this);
    v15 = *((_QWORD *)this + 1);
    if ( v15 )
    {
      if ( *((unsigned int *)this + 4) >= (unsigned __int64)v13 + 9 )
      {
        *(_QWORD *)v15 = 0;
        *(_BYTE *)(v15 + 8) = 0;
        **((_DWORD **)this + 1) = 9;
        *(_DWORD *)(*((_QWORD *)this + 1) + 4LL) = v13;
        v12 = 0;
        *(_BYTE *)(*((_QWORD *)this + 1) + 8LL) = v14;
LABEL_11:
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids, v12);
        }
        if ( (v12 & 0x80000000) == 0 )
        {
          v16 = (_DWORD *)*((_QWORD *)this + 3);
          *v16 = 24;
          *(_DWORD *)(*((_QWORD *)this + 3) + 4LL) = pExceptionObject;
          *(struct _GUID *)(*((_QWORD *)this + 3) + 8LL) = *a5;
          v17 = *(_QWORD *)this;
          v27[0] = 0;
          v12 = (*(__int64 (__fastcall **)(CWbemInstancePacket *, struct IWbemClassObject *, _DWORD *, _QWORD, _DWORD *))(v17 + 8))(
                  this,
                  a4,
                  v16 + 6,
                  pExceptionObject,
                  v27);
          if ( (v12 & 0x80000000) == 0 )
          {
            *v9 = pExceptionObject + 33;
            goto LABEL_16;
          }
        }
        goto LABEL_42;
      }
      v12 = -2147217348;
    }
    else
    {
      v12 = -2147217400;
    }
    v20 = GetMemLogObject();
    CMemoryLog::Write(v20, v12);
    goto LABEL_11;
  }
  v25 = GetMemLogObject();
  v12 = -2147217400;
  CMemoryLog::Write(v25, -2147217400);
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v21 = 24;
    v22 = 2147749896LL;
    goto LABEL_26;
  }
  return v12;
}

```

## disassembly

```asm
0x18003c1e0  push    rbp
0x18003c1e2  push    rbx
0x18003c1e3  push    rsi
0x18003c1e4  push    rdi
0x18003c1e5  push    r14
0x18003c1e7  push    r15
0x18003c1e9  mov     rbp, rsp
0x18003c1ec  sub     rsp, 48h
0x18003c1f0  mov     r15, r9
0x18003c1f3  mov     rdi, rcx
0x18003c1f6  test    rdx, rdx
0x18003c1f9  jz      loc_18003C37D
0x18003c1ff  lea     rax, [rdx+9]
0x18003c203  cmp     rax, rdx
0x18003c206  jbe     loc_18003C3EE
0x18003c20c  mov     [rcx+18h], rax
0x18003c210  cmp     r8d, 21h ; '!'
0x18003c214  jb      loc_18003C455
0x18003c21a  lea     ecx, [r8-9]
0x18003c21e  mov     r14, [rbp+arg_28]
0x18003c222  mov     eax, 20h ; ' '
0x18003c227  mov     r9, rdi
0x18003c22a  mov     [rax+rdi], ecx
0x18003c22d  mov     [rdi+8], rdx
0x18003c231  mov     [rdi+10h], r8d
0x18003c235  test    r14, r14
0x18003c238  jz      loc_18003C4BC
0x18003c23e  mov     rax, [rdi]
0x18003c241  lea     rcx, [rbp+pExceptionObject]
0x18003c245  mov     [rsp+48h+var_28], rcx
0x18003c24a  xor     r9d, r9d
0x18003c24d  xor     r8d, r8d
0x18003c250  mov     [rbp+pExceptionObject], 0
0x18003c257  mov     rdx, r15
0x18003c25a  mov     rcx, rdi
0x18003c25d  mov     rax, [rax+8]
0x18003c261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c266  lea     rsi, WPP_GLOBAL_Control
0x18003c26d  mov     ebx, eax
0x18003c26f  test    eax, eax
0x18003c271  jns     loc_18003C35C
0x18003c277  cmp     eax, 8004103Ch
0x18003c27c  jnz     loc_18003C517
0x18003c282  mov     rax, [rdi]
0x18003c285  mov     rcx, rdi
0x18003c288  mov     ebx, [rbp+pExceptionObject]
0x18003c28b  add     ebx, 18h
0x18003c28e  mov     rax, [rax]
0x18003c291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c296  mov     r8, [rdi+8]
0x18003c29a  mov     r9b, al
0x18003c29d  test    r8, r8
0x18003c2a0  jz      loc_18003C38C
0x18003c2a6  mov     ecx, [rdi+10h]
0x18003c2a9  mov     edx, ebx
0x18003c2ab  add     rdx, 9
0x18003c2af  cmp     rcx, rdx
0x18003c2b2  jb      loc_18003C50D
0x18003c2b8  xor     eax, eax
0x18003c2ba  mov     [r8], rax
0x18003c2bd  mov     [r8+8], al
0x18003c2c1  mov     rax, [rdi+8]
0x18003c2c5  mov     dword ptr [rax], 9
0x18003c2cb  mov     rax, [rdi+8]
0x18003c2cf  mov     [rax+4], ebx
0x18003c2d2  xor     ebx, ebx
0x18003c2d4  mov     rax, [rdi+8]
0x18003c2d8  mov     [rax+8], r9b
0x18003c2dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c2e3  cmp     rcx, rsi
0x18003c2e6  jz      short loc_18003C2F2
0x18003c2e8  test    byte ptr [rcx+1Ch], 1
0x18003c2ec  jnz     loc_18003C3A7
0x18003c2f2  test    ebx, ebx
0x18003c2f4  js      loc_18003C517
0x18003c2fa  mov     r8, [rdi+18h]
0x18003c2fe  mov     rdx, r15
0x18003c301  mov     dword ptr [r8], 18h
0x18003c308  add     r8, 18h
0x18003c30c  mov     rcx, [rdi+18h]
0x18003c310  mov     eax, [rbp+pExceptionObject]
0x18003c313  mov     [rcx+4], eax
0x18003c316  mov     rcx, [rdi+18h]
0x18003c31a  mov     rax, [rbp+arg_20]
0x18003c31e  movups  xmm0, xmmword ptr [rax]
0x18003c321  movdqu  xmmword ptr [rcx+8], xmm0
0x18003c326  mov     rax, [rdi]
0x18003c329  lea     rcx, [rbp+var_18]
0x18003c32d  mov     r9d, [rbp+pExceptionObject]
0x18003c331  mov     [rsp+48h+var_28], rcx
0x18003c336  mov     rcx, rdi
0x18003c339  mov     [rbp+var_18], 0
0x18003c340  mov     rax, [rax+8]
0x18003c344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c349  mov     ebx, eax
0x18003c34b  test    eax, eax
0x18003c34d  js      loc_18003C517
0x18003c353  mov     eax, [rbp+pExceptionObject]
0x18003c356  add     eax, 21h ; '!'
0x18003c359  mov     [r14], eax
0x18003c35c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c363  cmp     rcx, rsi
0x18003c366  jz      short loc_18003C36E
0x18003c368  test    byte ptr [rcx+1Ch], 1
0x18003c36c  jnz     short loc_18003C3CE
0x18003c36e  mov     eax, ebx
0x18003c370  add     rsp, 48h
0x18003c374  pop     r15
0x18003c376  pop     r14
0x18003c378  pop     rdi
0x18003c379  pop     rsi
0x18003c37a  pop     rbx
0x18003c37b  pop     rbp
0x18003c37c  retn
0x18003c37d  mov     qword ptr [rcx+18h], 0
0x18003c385  xor     ecx, ecx
0x18003c387  jmp     loc_18003C21E
0x18003c38c  mov     ebx, 80041008h
0x18003c391  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003c397  mov     rcx, rax
0x18003c39a  mov     edx, ebx
0x18003c39c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003c3a2  jmp     loc_18003C2DC
0x18003c3a7  cmp     byte ptr [rcx+19h], 2
0x18003c3ab  jb      loc_18003C2F2
0x18003c3b1  mov     rcx, [rcx+10h]
0x18003c3b5  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x18003c3bc  mov     edx, 0Ah
0x18003c3c1  mov     r9d, ebx
0x18003c3c4  call    WPP_SF_d
0x18003c3c9  jmp     loc_18003C2F2
0x18003c3ce  cmp     byte ptr [rcx+19h], 2
0x18003c3d2  jb      short loc_18003C36E
0x18003c3d4  mov     edx, 19h
0x18003c3d9  mov     r9d, ebx
0x18003c3dc  mov     rcx, [rcx+10h]
0x18003c3e0  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x18003c3e7  call    WPP_SF_d
0x18003c3ec  jmp     short loc_18003C36E
0x18003c3ee  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003c3f4  mov     rcx, rax
0x18003c3f7  mov     edx, 0FFFFFFFEh
0x18003c3fc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003c402  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c409  lea     rsi, WPP_GLOBAL_Control
0x18003c410  cmp     rcx, rsi
0x18003c413  jz      short loc_18003C43D
0x18003c415  test    byte ptr [rcx+1Ch], 1
0x18003c419  jz      short loc_18003C43D
0x18003c41b  cmp     byte ptr [rcx+19h], 2
0x18003c41f  jb      short loc_18003C43D
0x18003c421  mov     rcx, [rcx+10h]
0x18003c425  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x18003c42c  mov     edx, 1Eh
0x18003c431  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x18003c438  call    WPP_SF_s
0x18003c43d  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18003c444  mov     [rbp+pExceptionObject], 57h ; 'W'
0x18003c44b  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003c44f  call    _CxxThrowException_0
0x18003c455  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003c45b  mov     rcx, rax
0x18003c45e  mov     edx, 0FFFFFFFEh
0x18003c463  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003c469  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c470  lea     rsi, WPP_GLOBAL_Control
0x18003c477  cmp     rcx, rsi
0x18003c47a  jz      short loc_18003C4A4
0x18003c47c  test    byte ptr [rcx+1Ch], 1
0x18003c480  jz      short loc_18003C4A4
0x18003c482  cmp     byte ptr [rcx+19h], 2
0x18003c486  jb      short loc_18003C4A4
0x18003c488  mov     rcx, [rcx+10h]
0x18003c48c  lea     r9, aSafeintexcepti_0; "SafeIntException(ERROR_INVALID_PARAMETE"...
0x18003c493  mov     edx, 1Fh
0x18003c498  lea     r8, WPP_36ee4cad28293dac31d6ed11fc4e5245_Traceguids
0x18003c49f  call    WPP_SF_s
0x18003c4a4  lea     rdx, _TI2?AVSafeIntException@@; pThrowInfo
0x18003c4ab  mov     [rbp+pExceptionObject], 57h ; 'W'
0x18003c4b2  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18003c4b6  call    _CxxThrowException_0
0x18003c4bc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003c4c2  mov     ebx, 80041008h
0x18003c4c7  mov     rcx, rax
0x18003c4ca  mov     edx, ebx
0x18003c4cc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003c4d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c4d9  lea     rsi, WPP_GLOBAL_Control
0x18003c4e0  cmp     rcx, rsi
0x18003c4e3  jz      loc_18003C36E
0x18003c4e9  test    byte ptr [rcx+1Ch], 1
0x18003c4ed  jz      loc_18003C36E
0x18003c4f3  cmp     byte ptr [rcx+19h], 2
0x18003c4f7  jb      loc_18003C36E
0x18003c4fd  mov     edx, 18h
0x18003c502  mov     r9d, 80041008h
0x18003c508  jmp     loc_18003C3DC
0x18003c50d  mov     ebx, 8004103Ch
0x18003c512  jmp     loc_18003C391
0x18003c517  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003c51d  mov     rcx, rax
0x18003c520  mov     edx, ebx
0x18003c522  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003c528  jmp     loc_18003C35C
```
