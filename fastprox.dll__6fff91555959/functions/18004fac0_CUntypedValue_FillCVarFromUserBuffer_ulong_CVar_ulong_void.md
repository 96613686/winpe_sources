# CUntypedValue::FillCVarFromUserBuffer(ulong,CVar *,ulong,void *)

- ea: `0x18004fac0`
- end: `0x18004fe1d`
- name: `?FillCVarFromUserBuffer@CUntypedValue@@SAJKPEAVCVar@@KPEAX@Z`
- size: `861`
- prototype: `__int64 __fastcall(unsigned int, struct CVar *, unsigned int, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004fe30`
- `0x18005f9e0`
- `0x18007f0a0`
- `0x18007f2f0`
- `0x18007f6c0`

## callees

- `0x1800088d0`
- `0x180034cf8`
- `0x180037120`
- `0x180045140`
- `0x18004f730`
- `0x18004fac0`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18004fbde`
- `wbemcomn!GetMemLogObject` at `0x18004fc1f`
- `wbemcomn!GetMemLogObject` at `0x18004fc6d`
- `wbemcomn!GetMemLogObject` at `0x18004fcda`
- `wbemcomn!GetMemLogObject` at `0x18004fd52`
- `wbemcomn!GetMemLogObject` at `0x18004fdae`
- `wbemcomn!GetMemLogObject` at `0x18004fbde`
- `wbemcomn!GetMemLogObject` at `0x18004fc1f`
- `wbemcomn!GetMemLogObject` at `0x18004fc6d`
- `wbemcomn!GetMemLogObject` at `0x18004fcda`
- `wbemcomn!GetMemLogObject` at `0x18004fd52`
- `wbemcomn!GetMemLogObject` at `0x18004fdae`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x18004fbf4`
- `wbemcomn!?SetAsNull@CVar@@QEAAXXZ` at `0x18004fbf4`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18004faed`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18004faed`
- `wbemcomn!?SetLPWSTR@CVar@@QEAAHPEAGH@Z` at `0x18004fb69`
- `wbemcomn!?SetLPWSTR@CVar@@QEAAHPEAGH@Z` at `0x18004fb69`
- `wbemcomn!?SetUnknown@CVar@@QEAAXPEAUIUnknown@@@Z` at `0x18004fcbc`
- `wbemcomn!?SetUnknown@CVar@@QEAAXPEAUIUnknown@@@Z` at `0x18004fcbc`
- `wbemcomn!?SetRaw@CVar@@QEAAXHPEAXH@Z` at `0x18004fda3`
- `wbemcomn!?SetRaw@CVar@@QEAAXHPEAXH@Z` at `0x18004fda3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004fbe9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004fc2d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004fc7b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004fce8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004fd60`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004fdbc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004fbe9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004fc2d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004fc7b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004fce8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004fd60`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004fdbc`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004fb75`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004fe02`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004fb75`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18004fe02`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004fb2f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18004fb2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall CUntypedValue::FillCVarFromUserBuffer(
        unsigned int a1,
        struct CVar *a2,
        unsigned int a3,
        unsigned __int16 *a4)
{
  int v8; // edi
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rbx
  const unsigned __int16 *v11; // r8
  int v12; // r8d
  unsigned __int16 *v13; // rdx
  CMemoryLog *v15; // rax
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v17; // rcx
  __int64 v18; // rdx
  CMemoryLog *v19; // rax
  unsigned int Length; // eax
  unsigned int v21; // r15d
  CMemoryLog *v22; // rax
  int v23; // r9d
  unsigned __int16 *v24; // r8
  int VARTYPE; // edx
  CMemoryLog *v26; // rax
  CMemoryLog *v27; // rax
  _BYTE v28[88]; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int8 v29; // [rsp+80h] [rbp+8h] BYREF
  char v30; // [rsp+81h] [rbp+9h]

  if ( (a1 & 0x2000) == 0 || !a4 )
  {
    v8 = 0;
    CVar::CVar((CVar *)v28);
    if ( !a4 )
    {
      CVar::SetAsNull(a2);
      goto LABEL_12;
    }
    if ( (unsigned int)CType::IsStringType(a1) )
    {
      if ( a3 >= 2 && (a3 & 1) == 0 && !a4[(a3 >> 1) - 1] )
      {
        v12 = 0;
        v13 = a4;
LABEL_11:
        CVar::SetLPWSTR(a2, v13, v12);
        goto LABEL_12;
      }
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -2147217400);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_55;
      }
      v18 = 19;
    }
    else
    {
      if ( a1 != 13 )
      {
        if ( a1 - 20 > 1 )
        {
          Length = CType::GetLength(a1);
          v21 = Length;
          if ( a1 == 16 )
          {
            if ( a3 != Length )
            {
              v22 = GetMemLogObject();
              CMemoryLog::Write(v22, -2147217400);
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_55;
              }
              v18 = 22;
              goto LABEL_54;
            }
            v29 = *(_BYTE *)a4;
            v30 = -(v29 > 0x8Fu);
            v23 = 2;
            v24 = (unsigned __int16 *)&v29;
            VARTYPE = 2;
          }
          else
          {
            if ( a3 != Length )
            {
              v26 = GetMemLogObject();
              CMemoryLog::Write(v26, -2147217400);
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_55;
              }
              v18 = 23;
              goto LABEL_54;
            }
            VARTYPE = CType::GetVARTYPE(a1);
            v23 = v21;
            v24 = a4;
          }
          CVar::SetRaw(a2, VARTYPE, v24, v23);
          goto LABEL_12;
        }
        if ( a3 == 8 )
        {
          v9 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x100u);
          v10 = v9;
          if ( v9 )
          {
            v11 = L"%I64d";
            if ( a1 != 20 )
              v11 = L"%I64u";
            StringCchPrintfW(v9, 0x80u, v11, *(_QWORD *)a4);
            v12 = 1;
            v13 = v10;
            goto LABEL_11;
          }
          v8 = -2147217402;
LABEL_12:
          CVar::~CVar((CVar *)v28);
          if ( v8 >= 0 )
            goto LABEL_13;
          goto LABEL_20;
        }
        v27 = GetMemLogObject();
        CMemoryLog::Write(v27, -2147217400);
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = 21;
          goto LABEL_54;
        }
LABEL_55:
        CVar::~CVar((CVar *)v28);
        return 2147749896LL;
      }
      if ( a3 == 8 )
      {
        CVar::SetUnknown(a2, *(struct IUnknown **)a4);
        goto LABEL_12;
      }
      v19 = GetMemLogObject();
      CMemoryLog::Write(v19, -2147217400);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_55;
      }
      v18 = 20;
    }
LABEL_54:
    WPP_SF_d(*((_QWORD *)v17 + 2), v18, WPP_96cfe318c29f370e5bbbcdc23009322b_Traceguids, 2147749896LL);
    goto LABEL_55;
  }
  v8 = -2147217378;
LABEL_20:
  v15 = GetMemLogObject();
  CMemoryLog::Write(v15, v8);
LABEL_13:
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_96cfe318c29f370e5bbbcdc23009322b_Traceguids, (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004fac0  push    rbx
0x18004fac2  push    rbp
0x18004fac3  push    rsi
0x18004fac4  push    rdi
0x18004fac5  push    r14
0x18004fac7  push    r15
0x18004fac9  sub     rsp, 48h
0x18004facd  mov     rsi, r9
0x18004fad0  mov     ebx, r8d
0x18004fad3  mov     r14, rdx
0x18004fad6  mov     ebp, ecx
0x18004fad8  xor     r15d, r15d
0x18004fadb  bt      ecx, 0Dh
0x18004fadf  jb      loc_18004FBD0
0x18004fae5  mov     edi, r15d
0x18004fae8  lea     rcx, [rsp+78h+var_58]
0x18004faed  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18004faf3  nop
0x18004faf4  test    rsi, rsi
0x18004faf7  jz      loc_18004FBF1
0x18004fafd  mov     ecx, ebp; unsigned int
0x18004faff  call    ?IsStringType@CType@@SAHK@Z; CType::IsStringType(ulong)
0x18004fb04  test    eax, eax
0x18004fb06  jnz     loc_18004FBFF
0x18004fb0c  cmp     ebp, 0Dh
0x18004fb0f  jz      loc_18004FC68
0x18004fb15  lea     eax, [rbp-14h]
0x18004fb18  cmp     eax, 1
0x18004fb1b  ja      loc_18004FCC7
0x18004fb21  cmp     ebx, 8
0x18004fb24  jnz     loc_18004FDAE
0x18004fb2a  mov     ecx, 100h
0x18004fb2f  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18004fb35  mov     rbx, rax
0x18004fb38  test    rax, rax
0x18004fb3b  jz      loc_18004FE12
0x18004fb41  mov     r9, [rsi]
0x18004fb44  mov     edx, 80h; unsigned __int64
0x18004fb49  mov     rcx, rax; unsigned __int16 *
0x18004fb4c  cmp     ebp, 14h
0x18004fb4f  lea     r8, aI64d; "%I64d"
0x18004fb56  jnz     short loc_18004FBC7
0x18004fb58  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004fb5d  mov     r8d, 1
0x18004fb63  mov     rdx, rbx
0x18004fb66  mov     rcx, r14
0x18004fb69  call    cs:__imp_?SetLPWSTR@CVar@@QEAAHPEAGH@Z; CVar::SetLPWSTR(ushort *,int)
0x18004fb6f  nop
0x18004fb70  lea     rcx, [rsp+78h+var_58]
0x18004fb75  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18004fb7b  test    edi, edi
0x18004fb7d  js      short loc_18004FBDE
0x18004fb7f  lea     rax, WPP_GLOBAL_Control
0x18004fb86  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fb8d  cmp     rcx, rax
0x18004fb90  jnz     short loc_18004FBA1
0x18004fb92  mov     eax, edi
0x18004fb94  add     rsp, 48h
0x18004fb98  pop     r15
0x18004fb9a  pop     r14
0x18004fb9c  pop     rdi
0x18004fb9d  pop     rsi
0x18004fb9e  pop     rbp
0x18004fb9f  pop     rbx
0x18004fba0  retn
0x18004fba1  test    byte ptr [rcx+1Ch], 1
0x18004fba5  jz      short loc_18004FB92
0x18004fba7  cmp     byte ptr [rcx+19h], 2
0x18004fbab  jb      short loc_18004FB92
0x18004fbad  mov     edx, 18h
0x18004fbb2  mov     r9d, edi
0x18004fbb5  lea     r8, WPP_96cfe318c29f370e5bbbcdc23009322b_Traceguids
0x18004fbbc  mov     rcx, [rcx+10h]
0x18004fbc0  call    WPP_SF_d
0x18004fbc5  jmp     short loc_18004FB92
0x18004fbc7  lea     r8, aI64u; "%I64u"
0x18004fbce  jmp     short loc_18004FB58
0x18004fbd0  test    rsi, rsi
0x18004fbd3  jz      loc_18004FAE5
0x18004fbd9  mov     edi, 8004101Eh
0x18004fbde  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004fbe4  mov     edx, edi
0x18004fbe6  mov     rcx, rax
0x18004fbe9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004fbef  jmp     short loc_18004FB7F
0x18004fbf1  mov     rcx, r14
0x18004fbf4  call    cs:__imp_?SetAsNull@CVar@@QEAAXXZ; CVar::SetAsNull(void)
0x18004fbfa  jmp     loc_18004FB70
0x18004fbff  cmp     ebx, 2
0x18004fc02  jb      short loc_18004FC1F
0x18004fc04  test    bl, 1
0x18004fc07  jnz     short loc_18004FC1F
0x18004fc09  shr     ebx, 1
0x18004fc0b  dec     ebx
0x18004fc0d  cmp     [rsi+rbx*2], r15w
0x18004fc12  jnz     short loc_18004FC1F
0x18004fc14  xor     r8d, r8d
0x18004fc17  mov     rdx, rsi
0x18004fc1a  jmp     loc_18004FB66
0x18004fc1f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004fc25  mov     edx, 80041008h
0x18004fc2a  mov     rcx, rax
0x18004fc2d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004fc33  lea     rax, WPP_GLOBAL_Control
0x18004fc3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fc41  cmp     rcx, rax
0x18004fc44  jz      loc_18004FDFD
0x18004fc4a  test    byte ptr [rcx+1Ch], 1
0x18004fc4e  jz      loc_18004FDFD
0x18004fc54  cmp     byte ptr [rcx+19h], 2
0x18004fc58  jb      loc_18004FDFD
0x18004fc5e  mov     edx, 13h
0x18004fc63  jmp     loc_18004FDE6
0x18004fc68  cmp     ebx, 8
0x18004fc6b  jz      short loc_18004FCB6
0x18004fc6d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004fc73  mov     edx, 80041008h
0x18004fc78  mov     rcx, rax
0x18004fc7b  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004fc81  lea     rax, WPP_GLOBAL_Control
0x18004fc88  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fc8f  cmp     rcx, rax
0x18004fc92  jz      loc_18004FDFD
0x18004fc98  test    byte ptr [rcx+1Ch], 1
0x18004fc9c  jz      loc_18004FDFD
0x18004fca2  cmp     byte ptr [rcx+19h], 2
0x18004fca6  jb      loc_18004FDFD
0x18004fcac  mov     edx, 14h
0x18004fcb1  jmp     loc_18004FDE6
0x18004fcb6  mov     rdx, [rsi]
0x18004fcb9  mov     rcx, r14
0x18004fcbc  call    cs:__imp_?SetUnknown@CVar@@QEAAXPEAUIUnknown@@@Z; CVar::SetUnknown(IUnknown *)
0x18004fcc2  jmp     loc_18004FB70
0x18004fcc7  mov     ecx, ebp; unsigned int
0x18004fcc9  call    ?GetLength@CType@@SAKK@Z; CType::GetLength(ulong)
0x18004fcce  mov     r15d, eax
0x18004fcd1  cmp     ebp, 10h
0x18004fcd4  jnz     short loc_18004FD4D
0x18004fcd6  cmp     ebx, eax
0x18004fcd8  jz      short loc_18004FD21
0x18004fcda  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004fce0  mov     edx, 80041008h
0x18004fce5  mov     rcx, rax
0x18004fce8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004fcee  lea     rax, WPP_GLOBAL_Control
0x18004fcf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fcfc  cmp     rcx, rax
0x18004fcff  jz      loc_18004FDFD
0x18004fd05  test    byte ptr [rcx+1Ch], 1
0x18004fd09  jz      loc_18004FDFD
0x18004fd0f  cmp     byte ptr [rcx+19h], 2
0x18004fd13  jb      loc_18004FDFD
0x18004fd19  lea     edx, [rbp+6]
0x18004fd1c  jmp     loc_18004FDE6
0x18004fd21  mov     al, [rsi]
0x18004fd23  mov     [rsp+78h+arg_0], al
0x18004fd2a  mov     ecx, 8Fh
0x18004fd2f  cmp     cl, al
0x18004fd31  sbb     al, al
0x18004fd33  mov     [rsp+78h+arg_1], al
0x18004fd3a  mov     r9d, 2
0x18004fd40  lea     r8, [rsp+78h+arg_0]
0x18004fd48  mov     edx, r9d
0x18004fd4b  jmp     short loc_18004FDA0
0x18004fd4d  cmp     ebx, r15d
0x18004fd50  jz      short loc_18004FD90
0x18004fd52  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004fd58  mov     edx, 80041008h
0x18004fd5d  mov     rcx, rax
0x18004fd60  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004fd66  lea     rax, WPP_GLOBAL_Control
0x18004fd6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fd74  cmp     rcx, rax
0x18004fd77  jz      loc_18004FDFD
0x18004fd7d  test    byte ptr [rcx+1Ch], 1
0x18004fd81  jz      short loc_18004FDFD
0x18004fd83  cmp     byte ptr [rcx+19h], 2
0x18004fd87  jb      short loc_18004FDFD
0x18004fd89  mov     edx, 17h
0x18004fd8e  jmp     short loc_18004FDE6
0x18004fd90  mov     ecx, ebp; unsigned int
0x18004fd92  call    ?GetVARTYPE@CType@@SAGK@Z; CType::GetVARTYPE(ulong)
0x18004fd97  movzx   edx, ax
0x18004fd9a  mov     r9d, r15d
0x18004fd9d  mov     r8, rsi
0x18004fda0  mov     rcx, r14
0x18004fda3  call    cs:__imp_?SetRaw@CVar@@QEAAXHPEAXH@Z; CVar::SetRaw(int,void *,int)
0x18004fda9  jmp     loc_18004FB70
0x18004fdae  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004fdb4  mov     edx, 80041008h
0x18004fdb9  mov     rcx, rax
0x18004fdbc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004fdc2  lea     rax, WPP_GLOBAL_Control
0x18004fdc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fdd0  cmp     rcx, rax
0x18004fdd3  jz      short loc_18004FDFD
0x18004fdd5  test    byte ptr [rcx+1Ch], 1
0x18004fdd9  jz      short loc_18004FDFD
0x18004fddb  cmp     byte ptr [rcx+19h], 2
0x18004fddf  jb      short loc_18004FDFD
0x18004fde1  mov     edx, 15h
0x18004fde6  mov     r9d, 80041008h
0x18004fdec  lea     r8, WPP_96cfe318c29f370e5bbbcdc23009322b_Traceguids
0x18004fdf3  mov     rcx, [rcx+10h]
0x18004fdf7  call    WPP_SF_d
0x18004fdfc  nop
0x18004fdfd  lea     rcx, [rsp+78h+var_58]
0x18004fe02  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18004fe08  mov     eax, 80041008h
0x18004fe0d  jmp     loc_18004FB94
0x18004fe12  mov     edi, 80041006h
0x18004fe17  jmp     loc_18004FB70
```
