# CMethodPart::PutMethod(ushort const *,long,CWbemObject *,CWbemObject *)

- ea: `0x18002ca70`
- end: `0x18002cef5`
- name: `?PutMethod@CMethodPart@@QEAAJPEBGJPEAVCWbemObject@@1@Z`
- size: `1157`
- prototype: `__int64 __fastcall(CMethodPart *this, const unsigned __int16 *, __int64, struct CWbemObject *, struct CWbemObject *)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18002b7d0`
- `0x18007c170`

## callees

- `0x180006710`
- `0x18002ac20`
- `0x18002b350`
- `0x18002ca70`
- `0x18002cf00`
- `0x18002cfd0`
- `0x18002d170`
- `0x18002d910`
- `0x180037120`
- `0x180068580`
- `0x18009e010`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18002cc19`
- `wbemcomn!GetMemLogObject` at `0x18002cc89`
- `wbemcomn!GetMemLogObject` at `0x18002ccd4`
- `wbemcomn!GetMemLogObject` at `0x18002cd09`
- `wbemcomn!GetMemLogObject` at `0x18002cd6c`
- `wbemcomn!GetMemLogObject` at `0x18002cdd8`
- `wbemcomn!GetMemLogObject` at `0x18002ce37`
- `wbemcomn!GetMemLogObject` at `0x18002ceb7`
- `wbemcomn!GetMemLogObject` at `0x18002cc19`
- `wbemcomn!GetMemLogObject` at `0x18002cc89`
- `wbemcomn!GetMemLogObject` at `0x18002ccd4`
- `wbemcomn!GetMemLogObject` at `0x18002cd09`
- `wbemcomn!GetMemLogObject` at `0x18002cd6c`
- `wbemcomn!GetMemLogObject` at `0x18002cdd8`
- `wbemcomn!GetMemLogObject` at `0x18002ce37`
- `wbemcomn!GetMemLogObject` at `0x18002ceb7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002cc25`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002cc99`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002cce2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002cd14`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002cd7c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002cde6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ce42`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002cec2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002cc25`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002cc99`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002cce2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002cd14`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002cd7c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002cde6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ce42`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002cec2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMethodPart::PutMethod(
        CMethodPart *this,
        const unsigned __int16 *a2,
        __int64 a3,
        struct CWbemObject *a4,
        struct CWbemObject *a5)
{
  struct CWbemObject *v8; // r15
  int v9; // ebx
  struct CWbemObject *v10; // rbx
  int v11; // edi
  struct CWbemObject *v12; // rdi
  int v13; // esi
  int Method; // eax
  unsigned int v15; // r15d
  CWbemRefreshingSvc *v16; // rcx
  CMemoryLog *v18; // rax
  __int64 v19; // rdx
  CMemoryLog *v20; // rax
  CMemoryLog *MemLogObject; // rax
  CWbemRefreshingSvc *v22; // rcx
  CMemoryLog *v23; // rax
  CMemoryLog *v24; // rax
  __int64 v25; // r9
  __int64 v26; // rdx
  CMemoryLog *v27; // rax
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  struct CWbemObject *v30; // [rsp+20h] [rbp-18h] BYREF
  struct CWbemObject *v31; // [rsp+28h] [rbp-10h]
  struct CWbemObject *v32; // [rsp+98h] [rbp+60h] BYREF

  if ( a4 && (**((_BYTE **)a4 + 9) & 3) == 2 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217400);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v26 = 25;
    goto LABEL_50;
  }
  v8 = a5;
  if ( a5 && (**((_BYTE **)a5 + 9) & 3) == 2 )
  {
    v27 = GetMemLogObject();
    CMemoryLog::Write(v27, -2147217400);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 2147749896LL;
    }
    v26 = 26;
LABEL_50:
    WPP_SF_d(*((_QWORD *)v22 + 2), v26, WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids, 2147749896LL);
    return 2147749896LL;
  }
  v32 = 0;
  v30 = 0;
  v9 = CMethodPart::EnsureQualifier(this, a4, L"in", &v32);
  if ( v9 < 0 )
  {
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, v9);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids,
        (unsigned int)v9);
    }
    return (unsigned int)v9;
  }
  else
  {
    v10 = v32;
    v31 = v32;
    v11 = CMethodPart::EnsureQualifier(this, v8, L"out", &v30);
    if ( v11 >= 0 )
    {
      v12 = v30;
      v32 = v30;
      v13 = CMethodPart::ValidateOutParams(this, v30);
      if ( v13 < 0 )
      {
        v18 = GetMemLogObject();
        CMemoryLog::Write(v18, v13);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = 29;
LABEL_62:
          v25 = (unsigned int)v13;
          goto LABEL_63;
        }
LABEL_15:
        if ( !v12 )
        {
LABEL_17:
          v32 = 0;
          if ( v10 )
            (*(void (__fastcall **)(struct CWbemObject *))(*(_QWORD *)v10 + 16LL))(v10);
          v31 = 0;
          return (unsigned int)v13;
        }
LABEL_16:
        (*(void (__fastcall **)(struct CWbemObject *))(*(_QWORD *)v12 + 16LL))(v12);
        goto LABEL_17;
      }
      v13 = CMethodPart::CheckDuplicateParameters(this, v10, v12);
      if ( v13 < 0 || (v13 = CMethodPart::CheckIds(this, a4, v8), v13 < 0) )
      {
        v29 = GetMemLogObject();
        CMemoryLog::Write(v29, v13);
        goto LABEL_13;
      }
      Method = CMethodPart::FindMethod(this, a2);
      v15 = Method;
      if ( Method < 0 )
      {
        v13 = CMethodPart::CreateMethod(this, a2, v10, v12);
        if ( !v12 )
          goto LABEL_17;
        goto LABEL_16;
      }
      if ( (*(_BYTE *)(*((_QWORD *)this + 2) + 24LL * Method + 4) & 0x20) == 0 )
      {
        CMethodPart::SetSignature(this, (unsigned int)Method, 0, v10);
        CMethodPart::SetSignature(this, v15, 1, v12);
LABEL_13:
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = 32;
          goto LABEL_62;
        }
        goto LABEL_15;
      }
      if ( (unsigned int)CMethodPart::DoSignaturesMatch(this, (unsigned int)Method, 0, v10) )
      {
        if ( (unsigned int)CMethodPart::DoSignaturesMatch(this, v15, 1, v12) )
          goto LABEL_13;
        v24 = GetMemLogObject();
        v13 = -2147217356;
        CMemoryLog::Write(v24, -2147217356);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_15;
        }
        v19 = 31;
      }
      else
      {
        v20 = GetMemLogObject();
        v13 = -2147217356;
        CMemoryLog::Write(v20, -2147217356);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_15;
        }
        v19 = 30;
      }
      v25 = 2147749940LL;
LABEL_63:
      WPP_SF_d(*((_QWORD *)v16 + 2), v19, WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids, v25);
      goto LABEL_15;
    }
    v23 = GetMemLogObject();
    CMemoryLog::Write(v23, v11);
    if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids,
        (unsigned int)v11);
    }
    if ( v10 )
      (*(void (__fastcall **)(struct CWbemObject *))(*(_QWORD *)v10 + 16LL))(v10);
    v31 = 0;
    return (unsigned int)v11;
  }
}

```

## disassembly

```asm
0x18002ca70  push    rbp
0x18002ca72  push    rbx
0x18002ca73  push    rsi
0x18002ca74  push    rdi
0x18002ca75  push    r12
0x18002ca77  push    r13
0x18002ca79  push    r14
0x18002ca7b  push    r15
0x18002ca7d  mov     rbp, rsp
0x18002ca80  sub     rsp, 38h
0x18002ca84  mov     r13, r9
0x18002ca87  mov     r12, rdx
0x18002ca8a  mov     r14, rcx
0x18002ca8d  mov     dil, 2
0x18002ca90  xor     esi, esi
0x18002ca92  test    r9, r9
0x18002ca95  jz      short loc_18002CAAB
0x18002ca97  mov     rax, [r9+48h]
0x18002ca9b  mov     r8b, [rax]
0x18002ca9e  and     r8b, 3
0x18002caa2  cmp     r8b, dil
0x18002caa5  jz      loc_18002CCD4
0x18002caab  mov     r15, [rbp+arg_20]
0x18002caaf  test    r15, r15
0x18002cab2  jz      short loc_18002CAC6
0x18002cab4  mov     rax, [r15+48h]
0x18002cab8  mov     cl, [rax]
0x18002caba  and     cl, 3
0x18002cabd  cmp     cl, dil
0x18002cac0  jz      loc_18002CDD8
0x18002cac6  mov     [rbp+arg_18], rsi
0x18002caca  mov     [rbp+var_18], rsi
0x18002cace  lea     r9, [rbp+arg_18]; struct CWbemObject **
0x18002cad2  lea     r8, aIn; "in"
0x18002cad9  mov     rdx, r13; struct CWbemObject *
0x18002cadc  mov     rcx, r14; this
0x18002cadf  call    ?EnsureQualifier@CMethodPart@@QEAAJPEAVCWbemObject@@PEBGPEAPEAV2@@Z; CMethodPart::EnsureQualifier(CWbemObject *,ushort const *,CWbemObject * *)
0x18002cae4  mov     ebx, eax
0x18002cae6  test    eax, eax
0x18002cae8  js      loc_18002CE37
0x18002caee  mov     rbx, [rbp+arg_18]
0x18002caf2  mov     [rbp+var_10], rbx
0x18002caf6  lea     r9, [rbp+var_18]; struct CWbemObject **
0x18002cafa  lea     r8, aOut; "out"
0x18002cb01  mov     rdx, r15; struct CWbemObject *
0x18002cb04  mov     rcx, r14; this
0x18002cb07  call    ?EnsureQualifier@CMethodPart@@QEAAJPEAVCWbemObject@@PEBGPEAPEAV2@@Z; CMethodPart::EnsureQualifier(CWbemObject *,ushort const *,CWbemObject * *)
0x18002cb0c  mov     edi, eax
0x18002cb0e  test    eax, eax
0x18002cb10  js      loc_18002CD09
0x18002cb16  mov     rdi, [rbp+var_18]
0x18002cb1a  mov     [rbp+arg_18], rdi
0x18002cb1e  mov     rdx, rdi; struct CWbemObject *
0x18002cb21  mov     rcx, r14; this
0x18002cb24  call    ?ValidateOutParams@CMethodPart@@IEAAJPEAVCWbemObject@@@Z; CMethodPart::ValidateOutParams(CWbemObject *)
0x18002cb29  mov     esi, eax
0x18002cb2b  test    eax, eax
0x18002cb2d  js      loc_18002CC19
0x18002cb33  mov     r8, rdi; struct CWbemObject *
0x18002cb36  mov     rdx, rbx; struct CWbemObject *
0x18002cb39  mov     rcx, r14; this
0x18002cb3c  call    ?CheckDuplicateParameters@CMethodPart@@IEAAJPEAVCWbemObject@@0@Z; CMethodPart::CheckDuplicateParameters(CWbemObject *,CWbemObject *)
0x18002cb41  mov     esi, eax
0x18002cb43  test    eax, eax
0x18002cb45  js      loc_18002CEB7
0x18002cb4b  mov     r8, r15; struct CWbemClass *
0x18002cb4e  mov     rdx, r13; struct CWbemClass *
0x18002cb51  mov     rcx, r14; this
0x18002cb54  call    ?CheckIds@CMethodPart@@IEAAJPEAVCWbemClass@@0@Z; CMethodPart::CheckIds(CWbemClass *,CWbemClass *)
0x18002cb59  mov     esi, eax
0x18002cb5b  test    eax, eax
0x18002cb5d  js      loc_18002CEB7
0x18002cb63  mov     rdx, r12; unsigned __int16 *
0x18002cb66  mov     rcx, r14; this
0x18002cb69  call    ?FindMethod@CMethodPart@@IEAAHPEBG@Z; CMethodPart::FindMethod(ushort const *)
0x18002cb6e  movsxd  r15, eax
0x18002cb71  test    eax, eax
0x18002cb73  js      loc_18002CC54
0x18002cb79  lea     rcx, [r15+r15*2]
0x18002cb7d  mov     rax, [r14+10h]
0x18002cb81  mov     r9, rbx
0x18002cb84  xor     r8d, r8d
0x18002cb87  mov     edx, r15d
0x18002cb8a  test    byte ptr [rax+rcx*8+4], 20h
0x18002cb8f  mov     rcx, r14
0x18002cb92  jnz     loc_18002CC7C
0x18002cb98  call    ?SetSignature@CMethodPart@@IEAAJHW4METHOD_SIGNATURE_TYPE@@PEAVCWbemObject@@@Z; CMethodPart::SetSignature(int,METHOD_SIGNATURE_TYPE,CWbemObject *)
0x18002cb9d  mov     r9, rdi
0x18002cba0  mov     r8d, 1
0x18002cba6  mov     edx, r15d
0x18002cba9  mov     rcx, r14
0x18002cbac  call    ?SetSignature@CMethodPart@@IEAAJHW4METHOD_SIGNATURE_TYPE@@PEAVCWbemObject@@@Z; CMethodPart::SetSignature(int,METHOD_SIGNATURE_TYPE,CWbemObject *)
0x18002cbb1  lea     rax, WPP_GLOBAL_Control
0x18002cbb8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cbbf  cmp     rcx, rax
0x18002cbc2  jz      short loc_18002CBCE
0x18002cbc4  test    byte ptr [rcx+1Ch], 1
0x18002cbc8  jnz     loc_18002CECD
0x18002cbce  test    rdi, rdi
0x18002cbd1  jz      short loc_18002CBE2
0x18002cbd3  mov     rax, [rdi]
0x18002cbd6  mov     rax, [rax+10h]
0x18002cbda  mov     rcx, rdi
0x18002cbdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbe2  mov     [rbp+arg_18], 0
0x18002cbea  test    rbx, rbx
0x18002cbed  jz      short loc_18002CBFE
0x18002cbef  mov     rax, [rbx]
0x18002cbf2  mov     rcx, rbx
0x18002cbf5  mov     rax, [rax+10h]
0x18002cbf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbfe  mov     [rbp+var_10], 0
0x18002cc06  mov     eax, esi
0x18002cc08  add     rsp, 38h
0x18002cc0c  pop     r15
0x18002cc0e  pop     r14
0x18002cc10  pop     r13
0x18002cc12  pop     r12
0x18002cc14  pop     rdi
0x18002cc15  pop     rsi
0x18002cc16  pop     rbx
0x18002cc17  pop     rbp
0x18002cc18  retn
0x18002cc19  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002cc1f  nop
0x18002cc20  mov     edx, esi
0x18002cc22  mov     rcx, rax
0x18002cc25  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002cc2b  lea     rax, WPP_GLOBAL_Control
0x18002cc32  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc39  cmp     rcx, rax
0x18002cc3c  jz      short loc_18002CBCE
0x18002cc3e  test    byte ptr [rcx+1Ch], 1
0x18002cc42  jz      short loc_18002CBCE
0x18002cc44  cmp     byte ptr [rcx+19h], 2
0x18002cc48  jb      short loc_18002CBCE
0x18002cc4a  mov     edx, 1Dh
0x18002cc4f  jmp     loc_18002CEDC
0x18002cc54  mov     r9, rdi; struct CWbemObject *
0x18002cc57  mov     r8, rbx; struct CWbemObject *
0x18002cc5a  mov     rdx, r12; unsigned __int16 *
0x18002cc5d  mov     rcx, r14; this
0x18002cc60  call    ?CreateMethod@CMethodPart@@IEAAJPEBGPEAVCWbemObject@@1@Z; CMethodPart::CreateMethod(ushort const *,CWbemObject *,CWbemObject *)
0x18002cc65  mov     esi, eax
0x18002cc67  test    rdi, rdi
0x18002cc6a  jz      loc_18002CBE2
0x18002cc70  mov     rcx, [rdi]
0x18002cc73  mov     rax, [rcx+10h]
0x18002cc77  jmp     loc_18002CBDA
0x18002cc7c  call    ?DoSignaturesMatch@CMethodPart@@IEAAHHW4METHOD_SIGNATURE_TYPE@@PEAVCWbemObject@@@Z; CMethodPart::DoSignaturesMatch(int,METHOD_SIGNATURE_TYPE,CWbemObject *)
0x18002cc81  test    eax, eax
0x18002cc83  jnz     loc_18002CD50
0x18002cc89  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002cc8f  mov     esi, 80041034h
0x18002cc94  mov     edx, esi
0x18002cc96  mov     rcx, rax
0x18002cc99  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002cc9f  lea     rax, WPP_GLOBAL_Control
0x18002cca6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ccad  cmp     rcx, rax
0x18002ccb0  jz      loc_18002CBCE
0x18002ccb6  test    byte ptr [rcx+1Ch], 1
0x18002ccba  jz      loc_18002CBCE
0x18002ccc0  cmp     byte ptr [rcx+19h], 2
0x18002ccc4  jb      loc_18002CBCE
0x18002ccca  mov     edx, 1Eh
0x18002cccf  jmp     loc_18002CDB2
0x18002ccd4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002ccda  mov     edx, 80041008h
0x18002ccdf  mov     rcx, rax
0x18002cce2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002cce8  lea     rax, WPP_GLOBAL_Control
0x18002ccef  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ccf6  cmp     rcx, rax
0x18002ccf9  jnz     loc_18002CDBD
0x18002ccff  mov     eax, 80041008h
0x18002cd04  jmp     loc_18002CC08
0x18002cd09  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002cd0f  mov     edx, edi
0x18002cd11  mov     rcx, rax
0x18002cd14  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002cd1a  lea     rax, WPP_GLOBAL_Control
0x18002cd21  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd28  cmp     rcx, rax
0x18002cd2b  jnz     loc_18002CE86
0x18002cd31  test    rbx, rbx
0x18002cd34  jz      short loc_18002CD45
0x18002cd36  mov     rax, [rbx]
0x18002cd39  mov     rcx, rbx
0x18002cd3c  mov     rax, [rax+10h]
0x18002cd40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd45  mov     [rbp+var_10], rsi
0x18002cd49  mov     eax, edi
0x18002cd4b  jmp     loc_18002CC08
0x18002cd50  mov     r9, rdi
0x18002cd53  mov     r8d, 1
0x18002cd59  mov     edx, r15d
0x18002cd5c  mov     rcx, r14
0x18002cd5f  call    ?DoSignaturesMatch@CMethodPart@@IEAAHHW4METHOD_SIGNATURE_TYPE@@PEAVCWbemObject@@@Z; CMethodPart::DoSignaturesMatch(int,METHOD_SIGNATURE_TYPE,CWbemObject *)
0x18002cd64  test    eax, eax
0x18002cd66  jnz     loc_18002CBB1
0x18002cd6c  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002cd72  mov     esi, 80041034h
0x18002cd77  mov     edx, esi
0x18002cd79  mov     rcx, rax
0x18002cd7c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002cd82  lea     rax, WPP_GLOBAL_Control
0x18002cd89  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cd90  cmp     rcx, rax
0x18002cd93  jz      loc_18002CBCE
0x18002cd99  test    byte ptr [rcx+1Ch], 1
0x18002cd9d  jz      loc_18002CBCE
0x18002cda3  cmp     byte ptr [rcx+19h], 2
0x18002cda7  jb      loc_18002CBCE
0x18002cdad  mov     edx, 1Fh
0x18002cdb2  mov     r9d, 80041034h
0x18002cdb8  jmp     loc_18002CEDF
0x18002cdbd  test    byte ptr [rcx+1Ch], 1
0x18002cdc1  jz      loc_18002CCFF
0x18002cdc7  cmp     [rcx+19h], dil
0x18002cdcb  jb      loc_18002CCFF
0x18002cdd1  mov     edx, 19h
0x18002cdd6  jmp     short loc_18002CE1C
0x18002cdd8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002cdde  mov     edx, 80041008h
0x18002cde3  mov     rcx, rax
0x18002cde6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002cdec  lea     rax, WPP_GLOBAL_Control
0x18002cdf3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cdfa  cmp     rcx, rax
0x18002cdfd  jz      loc_18002CCFF
0x18002ce03  test    byte ptr [rcx+1Ch], 1
0x18002ce07  jz      loc_18002CCFF
0x18002ce0d  cmp     [rcx+19h], dil
0x18002ce11  jb      loc_18002CCFF
0x18002ce17  mov     edx, 1Ah
0x18002ce1c  mov     r9d, 80041008h
0x18002ce22  lea     r8, WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids
0x18002ce29  mov     rcx, [rcx+10h]
0x18002ce2d  call    WPP_SF_d
0x18002ce32  jmp     loc_18002CCFF
0x18002ce37  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002ce3d  mov     edx, ebx
0x18002ce3f  mov     rcx, rax
0x18002ce42  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002ce48  lea     rax, WPP_GLOBAL_Control
0x18002ce4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ce56  cmp     rcx, rax
0x18002ce59  jz      short loc_18002CE7F
0x18002ce5b  test    byte ptr [rcx+1Ch], 1
0x18002ce5f  jz      short loc_18002CE7F
0x18002ce61  cmp     [rcx+19h], dil
0x18002ce65  jb      short loc_18002CE7F
0x18002ce67  mov     edx, 1Bh
0x18002ce6c  mov     r9d, ebx
0x18002ce6f  lea     r8, WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids
0x18002ce76  mov     rcx, [rcx+10h]
0x18002ce7a  call    WPP_SF_d
0x18002ce7f  mov     eax, ebx
0x18002ce81  jmp     loc_18002CC08
0x18002ce86  test    byte ptr [rcx+1Ch], 1
0x18002ce8a  jz      loc_18002CD31
0x18002ce90  cmp     byte ptr [rcx+19h], 2
0x18002ce94  jb      loc_18002CD31
0x18002ce9a  mov     edx, 1Ch
0x18002ce9f  mov     r9d, edi
0x18002cea2  lea     r8, WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids
0x18002cea9  mov     rcx, [rcx+10h]
0x18002cead  call    WPP_SF_d
0x18002ceb2  jmp     loc_18002CD31
0x18002ceb7  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002cebd  mov     edx, esi
0x18002cebf  mov     rcx, rax
0x18002cec2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002cec8  jmp     loc_18002CBB1
0x18002cecd  cmp     byte ptr [rcx+19h], 2
0x18002ced1  jb      loc_18002CBCE
0x18002ced7  mov     edx, 20h ; ' '
0x18002cedc  mov     r9d, esi
0x18002cedf  lea     r8, WPP_fd56bafe8ef339ff81fc5cc004955919_Traceguids
0x18002cee6  mov     rcx, [rcx+10h]
0x18002ceea  call    WPP_SF_d
0x18002ceef  jmp     loc_18002CBCE
```
