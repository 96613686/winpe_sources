# CRAHelperClass::LowHealth(ushort const *,ushort * *,long *,tagDIAGNOSIS_STATUS *)

- ea: `0x18000e4d0`
- end: `0x18000e9aa`
- name: `?LowHealth@CRAHelperClass@@UEAAJPEBGPEAPEAGPEAJPEAW4tagDIAGNOSIS_STATUS@@@Z`
- size: `1242`
- prototype: `__int64 __fastcall(CRAHelperClass *this, const struct _EVENT_DESCRIPTOR *, unsigned __int16 **, int *, enum tagDIAGNOSIS_STATUS *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config`

## callees

- `0x18000c998`
- `0x18000cb0c`
- `0x18000cc10`
- `0x18000ccd0`
- `0x18000cdf8`
- `0x18000ceb0`
- `0x18000e008`
- `0x18000e4d0`
- `0x180011224`
- `0x18001194c`
- `0x180011a04`
- `0x1800120b0`
- `0x18001223c`
- `0x180014660`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000e8b5`
- `KERNEL32!GetProcessHeap` at `0x18000e8b5`
- `KERNEL32!HeapFree` at `0x18000e8c3`
- `KERNEL32!HeapFree` at `0x18000e8c3`

## pseudocode

```c
__int64 __fastcall CRAHelperClass::LowHealth(
        CRAHelperClass *this,
        const struct _EVENT_DESCRIPTOR *a2,
        unsigned __int16 **a3,
        int *a4,
        enum tagDIAGNOSIS_STATUS *a5)
{
  enum tagDIAGNOSIS_STATUS *v5; // rsi
  unsigned int v8; // r9d
  unsigned int v10; // ebx
  int v11; // ecx
  signed int inited; // eax
  CEventLogger *v13; // rcx
  unsigned int v14; // r9d
  bool v15; // zf
  signed int v16; // eax
  const struct _EVENT_DESCRIPTOR *v17; // rdx
  CEventLogger *v18; // rcx
  __int64 v19; // r8
  const struct _EVENT_DESCRIPTOR *v20; // rdx
  CEventLogger *v21; // rcx
  __int64 v22; // rcx
  int v23; // eax
  int v24; // edx
  __int64 v25; // r8
  signed int v26; // eax
  const struct _EVENT_DESCRIPTOR *v27; // rdx
  CEventLogger *v28; // rcx
  const struct _EVENT_DESCRIPTOR *v29; // rdx
  CEventLogger *v30; // rcx
  unsigned __int16 **v31; // r12
  void *v32; // rbx
  HANDLE ProcessHeap; // rax
  int v34[4]; // [rsp+30h] [rbp-10h] BYREF

  v5 = a5;
  if ( !a5 )
  {
    v8 = 438;
LABEL_3:
    CEventLogger::LogError(
      this,
      a2,
      L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
      v8,
      L"CRAHelperClass::LowHealth",
      0x80070057);
    return 2147942487LL;
  }
  if ( !a3 )
  {
    v8 = 439;
    goto LABEL_3;
  }
  v10 = 0;
  LODWORD(a5) = 0;
  v34[0] = 0;
  *v5 = DS_REJECTED;
  *((_DWORD *)this + 43) = 0;
  *(_OWORD *)((char *)this + 280) = 0;
  *((_DWORD *)this + 80) = 0;
  v11 = *((_DWORD *)this + 40);
  if ( v11 == 1 || v11 == 2 )
  {
    if ( v11 == 1 )
    {
      *v5 = DS_REJECTED;
    }
    else
    {
      *v5 = DS_INDETERMINATE;
      inited = CRAHelperClass::InitTraceFilePath(this);
      v10 = inited;
      if ( inited < 0 )
      {
        v14 = 510;
        goto LABEL_73;
      }
    }
    v23 = IsNetworkAvailable();
    *((_DWORD *)this + 64) = v23;
    if ( !v23 )
    {
      v26 = StringCchCopyWithAlloc(a3, v24, 802);
      v10 = v26;
      if ( v26 < 0 )
      {
        CEventLogger::LogError(
          v28,
          v27,
          L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
          0x724u,
          L"CRAHelperClass::CheckNetworkHealth",
          v26);
        CEventLogger::LogError(
          v30,
          v29,
          L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
          0x207u,
          L"CRAHelperClass::LowHealth",
          v10);
        return v10;
      }
      v22 = 802;
      goto LABEL_42;
    }
    LogRAProblem(802, 2, v25);
    inited = CRAHelperClass::CheckRASettings(this, a3, v5, (int *)&a5);
    v10 = inited;
    if ( inited < 0 )
    {
      v14 = 526;
      goto LABEL_73;
    }
    if ( (_DWORD)a5 != 1 )
    {
      inited = CRAHelperClass::CheckMsraWFStatus(this, a3, v5, (int *)&a5);
      v10 = inited;
      if ( inited < 0 )
      {
        v14 = 533;
        goto LABEL_73;
      }
      if ( (_DWORD)a5 != 1 )
      {
        if ( *((_DWORD *)this + 40) != 2 )
          goto LABEL_77;
        if ( (unsigned int)(*((_DWORD *)this + 54) - 7) > 1 )
          goto LABEL_68;
        inited = CRAHelperClass::CheckPnrpFWStatus(this, a3, v5, (int *)&a5);
        v10 = inited;
        if ( inited < 0 )
        {
          v14 = 557;
          goto LABEL_73;
        }
        if ( (_DWORD)a5 != 1 )
        {
          if ( *((_DWORD *)this + 54) != 7 )
            goto LABEL_68;
          inited = CRAHelperClass::CheckLocalTimeOffset(this, a3, v5, (int *)&a5);
          v10 = inited;
          if ( inited < 0 )
          {
            v14 = 566;
            goto LABEL_73;
          }
          if ( (_DWORD)a5 != 1 )
          {
LABEL_68:
            if ( *((_DWORD *)this + 40) != 2 )
              goto LABEL_77;
            v31 = (unsigned __int16 **)((char *)this + 264);
            v32 = (void *)*((_QWORD *)this + 33);
            if ( v32 )
            {
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v32);
              *v31 = 0;
            }
            inited = GetRATicketString(*((const unsigned __int16 **)this + 24), (unsigned __int16 **)this + 33);
            v10 = inited;
            if ( inited < 0 )
            {
              v14 = 582;
              goto LABEL_73;
            }
            inited = CRAHelperClass::CheckForChangedPublicAddr(
                       this,
                       *v31,
                       *((unsigned __int16 **)this + 34),
                       a3,
                       v5,
                       (int *)&a5);
            v10 = inited;
            if ( inited < 0 )
            {
              v14 = 593;
              goto LABEL_73;
            }
            if ( (_DWORD)a5 != 1 )
            {
              inited = CRAHelperClass::CheckForGlobalAddresses(this, *v31, a3, v5, (int *)&a5);
              v10 = inited;
              if ( inited < 0 )
              {
                v14 = 602;
                goto LABEL_73;
              }
              if ( (_DWORD)a5 != 1 )
              {
LABEL_77:
                if ( *v5 != DS_INDETERMINATE )
                  return v10;
                if ( *a3 )
                  return v10;
                inited = StringCchCopyWithAlloc(a3, (int)a2, 800);
                v10 = inited;
                if ( inited >= 0 )
                  return v10;
                v14 = 613;
                goto LABEL_73;
              }
            }
          }
        }
      }
    }
  }
  else if ( v11 == 3 )
  {
    inited = CRAHelperClass::InitTraceFilePath(this);
    v10 = inited;
    if ( inited < 0 )
    {
      v14 = 461;
      goto LABEL_73;
    }
    inited = SearchForSockFailure(*((const unsigned __int16 **)this + 24), v34, (unsigned int *)this + 84);
    v10 = inited;
    if ( inited < 0 )
    {
      v14 = 468;
      goto LABEL_73;
    }
    if ( v34[0] )
    {
      *v5 = DS_INDETERMINATE;
      inited = StringCchCopyWithAlloc(a3, (int)a2, 801);
      v10 = inited;
      if ( inited < 0 )
      {
        v14 = 481;
        goto LABEL_73;
      }
    }
    else
    {
      *v5 = DS_REJECTED;
    }
  }
  else
  {
    if ( v11 != 4 && (unsigned int)(v11 - 5) > 1 )
      return v10;
    *v5 = DS_REJECTED;
    if ( *((_DWORD *)this + 40) == 4 )
      goto LABEL_15;
    inited = CRAHelperClass::CheckPnrpFWStatus(this, a3, v5, (int *)&a5);
    v10 = inited;
    if ( inited < 0 )
    {
      v14 = 641;
LABEL_73:
      CEventLogger::LogError(
        v13,
        a2,
        L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
        v14,
        L"CRAHelperClass::LowHealth",
        inited);
      return v10;
    }
    if ( (_DWORD)a5 != 1 )
    {
LABEL_15:
      v15 = *((_DWORD *)this + 65) == 0;
      LODWORD(a5) = 0;
      if ( !v15 )
      {
        LogRAProblem(807, 2, a3);
        v10 = 0;
        if ( *((_DWORD *)this + 40) == 4 || *((_DWORD *)this + 74) )
          return v10;
        inited = CRAHelperClass::CheckLocalTimeOffset(this, a3, v5, (int *)&a5);
        v10 = inited;
        if ( inited >= 0 )
        {
          if ( (_DWORD)a5 == 1 )
            return v10;
          *v5 = DS_INDETERMINATE;
          inited = StringCchCopyWithAlloc(a3, (int)a2, 808);
          v10 = inited;
          if ( inited >= 0 )
            return v10;
          v14 = 670;
        }
        else
        {
          v14 = 661;
        }
        goto LABEL_73;
      }
      v16 = StringCchCopyWithAlloc(a3, (int)a2, 807);
      v10 = v16;
      if ( v16 < 0 )
      {
        CEventLogger::LogError(
          v18,
          v17,
          L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
          0x981u,
          L"CRAHelperClass::CheckPNRPGlobalCloud",
          v16);
        CEventLogger::LogError(
          v21,
          v20,
          L"base\\diagnosis\\ra\\rahelperclass\\rahc.cpp",
          0x28Au,
          L"CRAHelperClass::LowHealth",
          v10);
        return v10;
      }
      v22 = 807;
LABEL_42:
      *v5 = DS_CONFIRMED;
      LogRAProblem(v22, 1, v19);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18000e4d0  push    rbp
0x18000e4d2  push    rbx
0x18000e4d3  push    rsi
0x18000e4d4  push    rdi
0x18000e4d5  push    r12
0x18000e4d7  push    r14
0x18000e4d9  push    r15
0x18000e4db  mov     rbp, rsp
0x18000e4de  sub     rsp, 40h
0x18000e4e2  mov     rsi, [rbp+arg_20]
0x18000e4e6  mov     r15, r8
0x18000e4e9  mov     rdi, rcx
0x18000e4ec  test    rsi, rsi
0x18000e4ef  jnz     short loc_18000E521
0x18000e4f1  mov     r9d, 1B6h; unsigned int
0x18000e4f7  lea     rax, aCrahelperclass_15; "CRAHelperClass::LowHealth"
0x18000e4fe  mov     dword ptr [rsp+40h+var_18], 80070057h; unsigned int
0x18000e506  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000e50d  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x18000e512  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000e517  mov     eax, 80070057h
0x18000e51c  jmp     loc_18000E99B
0x18000e521  test    r15, r15
0x18000e524  jnz     short loc_18000E52E
0x18000e526  mov     r9d, 1B7h
0x18000e52c  jmp     short loc_18000E4F7
0x18000e52e  xor     ebx, ebx
0x18000e530  xorps   xmm0, xmm0
0x18000e533  mov     dword ptr [rbp+arg_20], ebx
0x18000e536  mov     [rbp+var_10], ebx
0x18000e539  lea     r12d, [rbx+2]
0x18000e53d  mov     [rsi], r12d
0x18000e540  mov     [rcx+0ACh], ebx
0x18000e546  movups  xmmword ptr [rcx+118h], xmm0
0x18000e54d  mov     [rcx+140h], ebx
0x18000e553  mov     ecx, [rcx+0A0h]
0x18000e559  mov     eax, ecx
0x18000e55b  sub     eax, 1
0x18000e55e  jz      loc_18000E71D
0x18000e564  sub     eax, 1
0x18000e567  jz      loc_18000E71D
0x18000e56d  sub     eax, 1
0x18000e570  jz      loc_18000E6A5
0x18000e576  sub     eax, 1
0x18000e579  jz      short loc_18000E589
0x18000e57b  sub     eax, 1
0x18000e57e  jz      short loc_18000E589
0x18000e580  cmp     eax, 1
0x18000e583  jnz     loc_18000E999
0x18000e589  mov     [rsi], r12d
0x18000e58c  mov     r14d, 1
0x18000e592  cmp     dword ptr [rdi+0A0h], 4
0x18000e599  jz      short loc_18000E5C8
0x18000e59b  lea     r9, [rbp+arg_20]; int *
0x18000e59f  mov     r8, rsi; enum tagDIAGNOSIS_STATUS *
0x18000e5a2  mov     rdx, r15; unsigned __int16 **
0x18000e5a5  mov     rcx, rdi; this
0x18000e5a8  call    ?CheckPnrpFWStatus@CRAHelperClass@@AEAAJPEAPEAGPEAW4tagDIAGNOSIS_STATUS@@PEAH@Z; CRAHelperClass::CheckPnrpFWStatus(ushort * *,tagDIAGNOSIS_STATUS *,int *)
0x18000e5ad  mov     ebx, eax
0x18000e5af  test    eax, eax
0x18000e5b1  jns     short loc_18000E5BE
0x18000e5b3  mov     r9d, 281h
0x18000e5b9  jmp     loc_18000E97D
0x18000e5be  cmp     dword ptr [rbp+arg_20], r14d
0x18000e5c2  jz      loc_18000E999
0x18000e5c8  cmp     dword ptr [rdi+104h], 0
0x18000e5cf  mov     dword ptr [rbp+arg_20], 0
0x18000e5d6  jnz     short loc_18000E627
0x18000e5d8  mov     r8d, 327h; int
0x18000e5de  mov     rcx, r15; unsigned __int16 **
0x18000e5e1  call    ?StringCchCopyWithAlloc@@YAJPEAPEAGHH@Z; StringCchCopyWithAlloc(ushort * *,int,int)
0x18000e5e6  mov     ebx, eax
0x18000e5e8  test    eax, eax
0x18000e5ea  jns     short loc_18000E61D
0x18000e5ec  mov     dword ptr [rsp+40h+var_18], eax; unsigned int
0x18000e5f0  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000e5f7  lea     rax, aCrahelperclass_16; "CRAHelperClass::CheckPNRPGlobalCloud"
0x18000e5fe  mov     r9d, 981h; unsigned int
0x18000e604  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x18000e609  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000e60e  mov     r9d, 28Ah
0x18000e614  mov     dword ptr [rsp+40h+var_18], ebx
0x18000e618  jmp     loc_18000E981
0x18000e61d  mov     ecx, 327h
0x18000e622  jmp     loc_18000E7A3
0x18000e627  mov     edx, r12d
0x18000e62a  mov     ecx, 327h
0x18000e62f  call    ?LogRAProblem@@YAXHW4_RADIAG_PROBLEMSTATUS@@@Z; LogRAProblem(int,_RADIAG_PROBLEMSTATUS)
0x18000e634  xor     ebx, ebx
0x18000e636  cmp     dword ptr [rdi+0A0h], 4
0x18000e63d  jz      loc_18000E999
0x18000e643  cmp     [rdi+128h], ebx
0x18000e649  jnz     loc_18000E999
0x18000e64f  lea     r9, [rbp+arg_20]; int *
0x18000e653  mov     r8, rsi; enum tagDIAGNOSIS_STATUS *
0x18000e656  mov     rdx, r15; unsigned __int16 **
0x18000e659  mov     rcx, rdi; this
0x18000e65c  call    ?CheckLocalTimeOffset@CRAHelperClass@@AEAAJPEAPEAGPEAW4tagDIAGNOSIS_STATUS@@PEAH@Z; CRAHelperClass::CheckLocalTimeOffset(ushort * *,tagDIAGNOSIS_STATUS *,int *)
0x18000e661  mov     ebx, eax
0x18000e663  test    eax, eax
0x18000e665  jns     short loc_18000E672
0x18000e667  mov     r9d, 295h
0x18000e66d  jmp     loc_18000E97D
0x18000e672  cmp     dword ptr [rbp+arg_20], r14d
0x18000e676  jz      loc_18000E999
0x18000e67c  mov     r8d, 328h; int
0x18000e682  mov     dword ptr [rsi], 3
0x18000e688  mov     rcx, r15; unsigned __int16 **
0x18000e68b  call    ?StringCchCopyWithAlloc@@YAJPEAPEAGHH@Z; StringCchCopyWithAlloc(ushort * *,int,int)
0x18000e690  mov     ebx, eax
0x18000e692  test    eax, eax
0x18000e694  jns     loc_18000E999
0x18000e69a  mov     r9d, 29Eh
0x18000e6a0  jmp     loc_18000E97D
0x18000e6a5  mov     rcx, rdi; this
0x18000e6a8  call    ?InitTraceFilePath@CRAHelperClass@@AEAAJXZ; CRAHelperClass::InitTraceFilePath(void)
0x18000e6ad  mov     ebx, eax
0x18000e6af  test    eax, eax
0x18000e6b1  jns     short loc_18000E6BE
0x18000e6b3  mov     r9d, 1CDh
0x18000e6b9  jmp     loc_18000E97D
0x18000e6be  mov     rcx, [rdi+0C0h]; unsigned __int16 *
0x18000e6c5  lea     r8, [rdi+150h]; unsigned int *
0x18000e6cc  lea     rdx, [rbp+var_10]; int *
0x18000e6d0  call    ?SearchForSockFailure@@YAJPEBGPEAHPEAK@Z; SearchForSockFailure(ushort const *,int *,ulong *)
0x18000e6d5  mov     ebx, eax
0x18000e6d7  test    eax, eax
0x18000e6d9  jns     short loc_18000E6E6
0x18000e6db  mov     r9d, 1D4h
0x18000e6e1  jmp     loc_18000E97D
0x18000e6e6  cmp     [rbp+var_10], 0
0x18000e6ea  jnz     short loc_18000E6F4
0x18000e6ec  mov     [rsi], r12d
0x18000e6ef  jmp     loc_18000E999
0x18000e6f4  mov     r8d, 321h; int
0x18000e6fa  mov     dword ptr [rsi], 3
0x18000e700  mov     rcx, r15; unsigned __int16 **
0x18000e703  call    ?StringCchCopyWithAlloc@@YAJPEAPEAGHH@Z; StringCchCopyWithAlloc(ushort * *,int,int)
0x18000e708  mov     ebx, eax
0x18000e70a  test    eax, eax
0x18000e70c  jns     loc_18000E999
0x18000e712  mov     r9d, 1E1h
0x18000e718  jmp     loc_18000E97D
0x18000e71d  mov     r14d, 1
0x18000e723  cmp     ecx, r14d
0x18000e726  jnz     short loc_18000E77F
0x18000e728  mov     [rsi], r12d
0x18000e72b  call    ?IsNetworkAvailable@@YAHXZ; IsNetworkAvailable(void)
0x18000e730  mov     [rdi+100h], eax
0x18000e736  test    eax, eax
0x18000e738  jnz     short loc_18000E7B3
0x18000e73a  mov     r8d, 322h; int
0x18000e740  mov     rcx, r15; unsigned __int16 **
0x18000e743  call    ?StringCchCopyWithAlloc@@YAJPEAPEAGHH@Z; StringCchCopyWithAlloc(ushort * *,int,int)
0x18000e748  mov     ebx, eax
0x18000e74a  test    eax, eax
0x18000e74c  jns     short loc_18000E79E
0x18000e74e  mov     dword ptr [rsp+40h+var_18], eax; unsigned int
0x18000e752  lea     r8, aBaseDiagnosisR_2; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000e759  lea     rax, aCrahelperclass_8; "CRAHelperClass::CheckNetworkHealth"
0x18000e760  mov     r9d, 724h; unsigned int
0x18000e766  mov     [rsp+40h+var_20], rax; unsigned __int16 *
0x18000e76b  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000e770  mov     r9d, 207h
0x18000e776  mov     dword ptr [rsp+40h+var_18], ebx
0x18000e77a  jmp     loc_18000E981
0x18000e77f  mov     rcx, rdi; this
0x18000e782  mov     dword ptr [rsi], 3
0x18000e788  call    ?InitTraceFilePath@CRAHelperClass@@AEAAJXZ; CRAHelperClass::InitTraceFilePath(void)
0x18000e78d  mov     ebx, eax
0x18000e78f  test    eax, eax
0x18000e791  jns     short loc_18000E72B
0x18000e793  mov     r9d, 1FEh
0x18000e799  jmp     loc_18000E97D
0x18000e79e  mov     ecx, 322h
0x18000e7a3  mov     edx, r14d
0x18000e7a6  mov     [rsi], r14d
0x18000e7a9  call    ?LogRAProblem@@YAXHW4_RADIAG_PROBLEMSTATUS@@@Z; LogRAProblem(int,_RADIAG_PROBLEMSTATUS)
0x18000e7ae  jmp     loc_18000E999
0x18000e7b3  mov     edx, r12d
0x18000e7b6  mov     ecx, 322h
0x18000e7bb  call    ?LogRAProblem@@YAXHW4_RADIAG_PROBLEMSTATUS@@@Z; LogRAProblem(int,_RADIAG_PROBLEMSTATUS)
0x18000e7c0  lea     r9, [rbp+arg_20]; int *
0x18000e7c4  mov     r8, rsi; enum tagDIAGNOSIS_STATUS *
0x18000e7c7  mov     rdx, r15; unsigned __int16 **
0x18000e7ca  mov     rcx, rdi; this
0x18000e7cd  call    ?CheckRASettings@CRAHelperClass@@AEAAJPEAPEAGPEAW4tagDIAGNOSIS_STATUS@@PEAH@Z; CRAHelperClass::CheckRASettings(ushort * *,tagDIAGNOSIS_STATUS *,int *)
0x18000e7d2  mov     ebx, eax
0x18000e7d4  test    eax, eax
0x18000e7d6  jns     short loc_18000E7E3
0x18000e7d8  mov     r9d, 20Eh
0x18000e7de  jmp     loc_18000E97D
0x18000e7e3  cmp     dword ptr [rbp+arg_20], r14d
0x18000e7e7  jz      loc_18000E999
0x18000e7ed  lea     r9, [rbp+arg_20]; int *
0x18000e7f1  mov     r8, rsi; enum tagDIAGNOSIS_STATUS *
0x18000e7f4  mov     rdx, r15; unsigned __int16 **
0x18000e7f7  mov     rcx, rdi; this
0x18000e7fa  call    ?CheckMsraWFStatus@CRAHelperClass@@AEAAJPEAPEAGPEAW4tagDIAGNOSIS_STATUS@@PEAH@Z; CRAHelperClass::CheckMsraWFStatus(ushort * *,tagDIAGNOSIS_STATUS *,int *)
0x18000e7ff  mov     ebx, eax
0x18000e801  test    eax, eax
0x18000e803  jns     short loc_18000E810
0x18000e805  mov     r9d, 215h
0x18000e80b  jmp     loc_18000E97D
0x18000e810  cmp     dword ptr [rbp+arg_20], r14d
0x18000e814  jz      loc_18000E999
0x18000e81a  cmp     [rdi+0A0h], r12d
0x18000e821  jnz     loc_18000E958
0x18000e827  mov     eax, [rdi+0D8h]
0x18000e82d  sub     eax, 7
0x18000e830  cmp     eax, r14d
0x18000e833  ja      short loc_18000E898
0x18000e835  lea     r9, [rbp+arg_20]; int *
0x18000e839  mov     r8, rsi; enum tagDIAGNOSIS_STATUS *
0x18000e83c  mov     rdx, r15; unsigned __int16 **
0x18000e83f  mov     rcx, rdi; this
0x18000e842  call    ?CheckPnrpFWStatus@CRAHelperClass@@AEAAJPEAPEAGPEAW4tagDIAGNOSIS_STATUS@@PEAH@Z; CRAHelperClass::CheckPnrpFWStatus(ushort * *,tagDIAGNOSIS_STATUS *,int *)
0x18000e847  mov     ebx, eax
0x18000e849  test    eax, eax
0x18000e84b  jns     short loc_18000E858
0x18000e84d  mov     r9d, 22Dh
0x18000e853  jmp     loc_18000E97D
0x18000e858  cmp     dword ptr [rbp+arg_20], r14d
0x18000e85c  jz      loc_18000E999
0x18000e862  cmp     dword ptr [rdi+0D8h], 7
0x18000e869  jnz     short loc_18000E898
0x18000e86b  lea     r9, [rbp+arg_20]; int *
0x18000e86f  mov     r8, rsi; enum tagDIAGNOSIS_STATUS *
0x18000e872  mov     rdx, r15; unsigned __int16 **
0x18000e875  mov     rcx, rdi; this
0x18000e878  call    ?CheckLocalTimeOffset@CRAHelperClass@@AEAAJPEAPEAGPEAW4tagDIAGNOSIS_STATUS@@PEAH@Z; CRAHelperClass::CheckLocalTimeOffset(ushort * *,tagDIAGNOSIS_STATUS *,int *)
0x18000e87d  mov     ebx, eax
0x18000e87f  test    eax, eax
0x18000e881  jns     short loc_18000E88E
0x18000e883  mov     r9d, 236h
0x18000e889  jmp     loc_18000E97D
0x18000e88e  cmp     dword ptr [rbp+arg_20], r14d
0x18000e892  jz      loc_18000E999
0x18000e898  cmp     [rdi+0A0h], r12d
0x18000e89f  jnz     loc_18000E958
0x18000e8a5  lea     r12, [rdi+108h]
0x18000e8ac  mov     rbx, [r12]
0x18000e8b0  test    rbx, rbx
0x18000e8b3  jz      short loc_18000E8D1
0x18000e8b5  call    cs:__imp_GetProcessHeap
0x18000e8bb  mov     r8, rbx; lpMem
0x18000e8be  xor     edx, edx; dwFlags
0x18000e8c0  mov     rcx, rax; hHeap
0x18000e8c3  call    cs:__imp_HeapFree
0x18000e8c9  mov     qword ptr [r12], 0
0x18000e8d1  mov     rcx, [rdi+0C0h]; unsigned __int16 *
0x18000e8d8  mov     rdx, r12; unsigned __int16 **
0x18000e8db  call    ?GetRATicketString@@YAJPEBGPEAPEAG@Z; GetRATicketString(ushort const *,ushort * *)
0x18000e8e0  mov     ebx, eax
0x18000e8e2  test    eax, eax
0x18000e8e4  jns     short loc_18000E8F1
0x18000e8e6  mov     r9d, 246h
0x18000e8ec  jmp     loc_18000E97D
0x18000e8f1  mov     r8, [rdi+110h]; unsigned __int16 *
0x18000e8f8  lea     rax, [rbp+arg_20]
0x18000e8fc  mov     rdx, [r12]; unsigned __int16 *
0x18000e900  mov     r9, r15; unsigned __int16 **
0x18000e903  mov     [rsp+40h+var_18], rax; int *
0x18000e908  mov     rcx, rdi; this
0x18000e90b  mov     [rsp+40h+var_20], rsi; enum tagDIAGNOSIS_STATUS *
0x18000e910  call    ?CheckForChangedPublicAddr@CRAHelperClass@@AEAAJPEAG0PEAPEAGPEAW4tagDIAGNOSIS_STATUS@@PEAH@Z; CRAHelperClass::CheckForChangedPublicAddr(ushort *,ushort *,ushort * *,tagDIAGNOSIS_STATUS *,int *)
0x18000e915  mov     ebx, eax
0x18000e917  test    eax, eax
0x18000e919  jns     short loc_18000E923
0x18000e91b  mov     r9d, 251h
0x18000e921  jmp     short loc_18000E97D
0x18000e923  cmp     dword ptr [rbp+arg_20], r14d
0x18000e927  jz      short loc_18000E999
0x18000e929  mov     rdx, [r12]; unsigned __int16 *
0x18000e92d  lea     rax, [rbp+arg_20]
0x18000e931  mov     r9, rsi; enum tagDIAGNOSIS_STATUS *
0x18000e934  mov     [rsp+40h+var_20], rax; int *
0x18000e939  mov     r8, r15; unsigned __int16 **
0x18000e93c  mov     rcx, rdi; this
0x18000e93f  call    ?CheckForGlobalAddresses@CRAHelperClass@@AEAAJPEAGPEAPEAGPEAW4tagDIAGNOSIS_STATUS@@PEAH@Z; CRAHelperClass::CheckForGlobalAddresses(ushort *,ushort * *,tagDIAGNOSIS_STATUS *,int *)
0x18000e944  mov     ebx, eax
0x18000e946  test    eax, eax
0x18000e948  jns     short loc_18000E952
0x18000e94a  mov     r9d, 25Ah
0x18000e950  jmp     short loc_18000E97D
0x18000e952  cmp     dword ptr [rbp+arg_20], r14d
0x18000e956  jz      short loc_18000E999
0x18000e958  cmp     dword ptr [rsi], 3
0x18000e95b  jnz     short loc_18000E999
0x18000e95d  cmp     qword ptr [r15], 0
0x18000e961  jnz     short loc_18000E999
0x18000e963  mov     r8d, 320h; int
0x18000e969  mov     rcx, r15; unsigned __int16 **
0x18000e96c  call    ?StringCchCopyWithAlloc@@YAJPEAPEAGHH@Z; StringCchCopyWithAlloc(ushort * *,int,int)
0x18000e971  mov     ebx, eax
0x18000e973  test    eax, eax
0x18000e975  jns     short loc_18000E999
0x18000e977  mov     r9d, 265h; unsigned int
0x18000e97d  mov     dword ptr [rsp+40h+var_18], eax; unsigned int
0x18000e981  lea     rax, aCrahelperclass_15; "CRAHelperClass::LowHealth"
  ... truncated ...
```
