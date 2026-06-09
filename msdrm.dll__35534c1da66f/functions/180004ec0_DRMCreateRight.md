# DRMCreateRight

- ea: `0x180004ec0`
- end: `0x1800050c8`
- name: `DRMCreateRight`
- size: `520`
- prototype: `HRESULT __stdcall(PWSTR wszRightName, SYSTEMTIME *pstFrom, SYSTEMTIME *pstUntil, UINT cExtendedInfo, PWSTR *pwszExtendedInfoName, PWSTR *pwszExtendedInfoValue, DRMPUBHANDLE *phRight)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callees

- `0x180001244`
- `0x180001284`
- `0x18000420c`
- `0x180004328`
- `0x180004610`
- `0x1800046c8`
- `0x180004ec0`
- `0x180008260`
- `0x1800156a0`
- `0x1800164e4`
- `0x180016b00`
- `0x18001ffd8`
- `0x18003b3b8`

## string_xrefs

- `0x180004edd`: `+DRMCreateRight (right=%ls, # of ExtendedInfo =%d)\n`
- `0x180004f68`: `-DRMCreateRight HR=%x\n`

## pseudocode

```c
HRESULT __stdcall DRMCreateRight(
        PWSTR wszRightName,
        SYSTEMTIME *pstFrom,
        SYSTEMTIME *pstUntil,
        UINT cExtendedInfo,
        PWSTR *pwszExtendedInfoName,
        PWSTR *pwszExtendedInfoValue,
        DRMPUBHANDLE *phRight)
{
  CRight *v11; // rdi
  unsigned __int16 *v12; // r15
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // r9
  PWSTR *v16; // r8
  HRESULT Handle; // ebx
  int v19; // ebx
  __int64 v20; // r8
  __int64 v21; // r9
  CRight *v22; // rax
  int v23; // eax
  unsigned __int16 *v24; // [rsp+20h] [rbp-58h] BYREF

  _RTLTRACE("+DRMCreateRight (right=%ls, # of ExtendedInfo =%d)\n", wszRightName, cExtendedInfo);
  v24 = 0;
  v11 = 0;
  v12 = 0;
  if ( !(unsigned __int8)DRMIsValidStringT<unsigned short>(wszRightName, 0, v13, v14) )
    goto LABEL_11;
  if ( !*wszRightName )
    goto LABEL_11;
  v16 = pwszExtendedInfoName;
  if ( cExtendedInfo )
  {
    if ( !pwszExtendedInfoName || !pwszExtendedInfoValue )
      goto LABEL_11;
  }
  if ( !phRight || pstFrom && !pstUntil )
    goto LABEL_11;
  if ( pstUntil )
  {
    if ( !pstFrom )
    {
LABEL_11:
      Handle = -2147024809;
      goto LABEL_12;
    }
  }
  else if ( !pstFrom )
  {
    goto LABEL_19;
  }
  if ( !IsSystemTimeValid(pstFrom) || pstUntil && !IsSystemTimeValid(pstUntil) )
    goto LABEL_11;
LABEL_19:
  v19 = 0;
  if ( cExtendedInfo )
  {
    while ( (unsigned __int8)DRMIsValidStringT<unsigned short>(v16[v19], 0, v16, v15)
         && (unsigned __int8)DRMIsValidStringT<unsigned short>(pwszExtendedInfoValue[v19], 0, v20, v21) )
    {
      v16 = pwszExtendedInfoName;
      if ( ++v19 >= cExtendedInfo )
        goto LABEL_23;
    }
    goto LABEL_11;
  }
LABEL_23:
  v22 = (CRight *)operator new(0xD8u);
  if ( !v22 )
  {
    v11 = 0;
    goto LABEL_35;
  }
  v11 = CRight::CRight(v22);
  if ( !v11 )
  {
LABEL_35:
    Handle = -2147024882;
    goto LABEL_12;
  }
  v23 = EscapeXML(wszRightName, &v24);
  v12 = v24;
  Handle = v23;
  if ( v23 >= 0 )
  {
    Handle = CRight::SetRightName(v11, v24);
    if ( Handle >= 0 )
    {
      if ( !pstFrom || !pstUntil || (Handle = CRight::SetValidityTime(v11, pstFrom, pstUntil), Handle >= 0) )
      {
        if ( !cExtendedInfo
          || (Handle = CRight::SetExtendedInfo(v11, cExtendedInfo, pwszExtendedInfoName, pwszExtendedInfoValue),
              Handle >= 0) )
        {
          Handle = DRMCInt::CreateHandle(6u, v11, phRight);
          if ( Handle >= 0 )
            v11 = 0;
        }
      }
    }
  }
LABEL_12:
  operator delete(v12);
  if ( v11 )
    CDRMCBase::Release(v11);
  _RTLTRACE("-DRMCreateRight HR=%x\n", Handle);
  return Handle;
}

```

## disassembly

```asm
0x180004ec0  push    rbx
0x180004ec2  push    rbp
0x180004ec3  push    rsi
0x180004ec4  push    rdi
0x180004ec5  push    r12
0x180004ec7  push    r13
0x180004ec9  push    r14
0x180004ecb  push    r15
0x180004ecd  sub     rsp, 38h
0x180004ed1  mov     rbp, rdx
0x180004ed4  mov     rsi, r8
0x180004ed7  mov     rdx, rcx
0x180004eda  mov     r13, rcx
0x180004edd  lea     rcx, aDrmcreateright_0; "+DRMCreateRight (right=%ls, # of Extend"...
0x180004ee4  mov     r8d, r9d
0x180004ee7  mov     r14d, r9d
0x180004eea  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180004eef  xor     r12d, r12d
0x180004ef2  xor     edx, edx
0x180004ef4  mov     rcx, r13
0x180004ef7  mov     [rsp+78h+var_58], r12
0x180004efc  mov     edi, r12d
0x180004eff  mov     r15d, r12d
0x180004f02  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x180004f07  test    al, al
0x180004f09  jz      short loc_180004F4C
0x180004f0b  cmp     [r13+0], r12w
0x180004f10  jz      short loc_180004F4C
0x180004f12  mov     r8, [rsp+78h+pwszExtendedInfoName]
0x180004f1a  test    r14d, r14d
0x180004f1d  jz      short loc_180004F2E
0x180004f1f  test    r8, r8
0x180004f22  jz      short loc_180004F4C
0x180004f24  cmp     [rsp+78h+pwszExtendedInfoValue], r12
0x180004f2c  jz      short loc_180004F4C
0x180004f2e  cmp     [rsp+78h+phRight], r12
0x180004f36  jz      short loc_180004F4C
0x180004f38  test    rbp, rbp
0x180004f3b  jz      short loc_180004F42
0x180004f3d  test    rsi, rsi
0x180004f40  jz      short loc_180004F4C
0x180004f42  test    rsi, rsi
0x180004f45  jz      short loc_180004F87
0x180004f47  test    rbp, rbp
0x180004f4a  jnz     short loc_180004F8C
0x180004f4c  mov     ebx, 80070057h
0x180004f51  mov     rcx, r15; Block
0x180004f54  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004f59  test    rdi, rdi
0x180004f5c  jz      short loc_180004F66
0x180004f5e  mov     rcx, rdi; this
0x180004f61  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x180004f66  mov     edx, ebx
0x180004f68  lea     rcx, aDrmcreateright_1; "-DRMCreateRight HR=%x\n"
0x180004f6f  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180004f74  mov     eax, ebx
0x180004f76  add     rsp, 38h
0x180004f7a  pop     r15
0x180004f7c  pop     r14
0x180004f7e  pop     r13
0x180004f80  pop     r12
0x180004f82  pop     rdi
0x180004f83  pop     rsi
0x180004f84  pop     rbp
0x180004f85  pop     rbx
0x180004f86  retn
0x180004f87  test    rbp, rbp
0x180004f8a  jz      short loc_180004FA9
0x180004f8c  mov     rcx, rbp; struct _SYSTEMTIME *
0x180004f8f  call    ?IsSystemTimeValid@@YA_NPEAU_SYSTEMTIME@@@Z; IsSystemTimeValid(_SYSTEMTIME *)
0x180004f94  test    al, al
0x180004f96  jz      short loc_180004F4C
0x180004f98  test    rsi, rsi
0x180004f9b  jz      short loc_180004FA9
0x180004f9d  mov     rcx, rsi; struct _SYSTEMTIME *
0x180004fa0  call    ?IsSystemTimeValid@@YA_NPEAU_SYSTEMTIME@@@Z; IsSystemTimeValid(_SYSTEMTIME *)
0x180004fa5  test    al, al
0x180004fa7  jz      short loc_180004F4C
0x180004fa9  mov     ebx, r12d
0x180004fac  test    r14d, r14d
0x180004faf  jz      short loc_180004FF0
0x180004fb1  mov     r12d, ebx
0x180004fb4  xor     edx, edx
0x180004fb6  mov     rcx, [r8+r12*8]
0x180004fba  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x180004fbf  test    al, al
0x180004fc1  jz      short loc_180004F4C
0x180004fc3  mov     rax, [rsp+78h+pwszExtendedInfoValue]
0x180004fcb  xor     edx, edx
0x180004fcd  mov     rcx, [rax+r12*8]
0x180004fd1  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x180004fd6  xor     r12d, r12d
0x180004fd9  test    al, al
0x180004fdb  jz      loc_180004F4C
0x180004fe1  mov     r8, [rsp+78h+pwszExtendedInfoName]
0x180004fe9  inc     ebx
0x180004feb  cmp     ebx, r14d
0x180004fee  jb      short loc_180004FB1
0x180004ff0  mov     ecx, 0D8h; Size
0x180004ff5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004ffa  test    rax, rax
0x180004ffd  jz      loc_1800050BB
0x180005003  mov     rcx, rax; this
0x180005006  call    ??0CRight@@QEAA@XZ; CRight::CRight(void)
0x18000500b  mov     rdi, rax
0x18000500e  test    rax, rax
0x180005011  jz      loc_1800050BE
0x180005017  lea     rdx, [rsp+78h+var_58]; unsigned __int16 **
0x18000501c  mov     rcx, r13; unsigned __int16 *
0x18000501f  call    ?EscapeXML@@YAJPEAGPEAPEAG@Z; EscapeXML(ushort *,ushort * *)
0x180005024  mov     r15, [rsp+78h+var_58]
0x180005029  mov     ebx, eax
0x18000502b  test    eax, eax
0x18000502d  js      loc_180004F51
0x180005033  mov     rdx, r15; unsigned __int16 *
0x180005036  mov     rcx, rdi; this
0x180005039  call    ?SetRightName@CRight@@QEAAJPEAG@Z; CRight::SetRightName(ushort *)
0x18000503e  mov     ebx, eax
0x180005040  test    eax, eax
0x180005042  js      loc_180004F51
0x180005048  test    rbp, rbp
0x18000504b  jz      short loc_18000506A
0x18000504d  test    rsi, rsi
0x180005050  jz      short loc_18000506A
0x180005052  mov     r8, rsi; struct _SYSTEMTIME *
0x180005055  mov     rdx, rbp; struct _SYSTEMTIME *
0x180005058  mov     rcx, rdi; this
0x18000505b  call    ?SetValidityTime@CRight@@QEAAJPEAU_SYSTEMTIME@@0@Z; CRight::SetValidityTime(_SYSTEMTIME *,_SYSTEMTIME *)
0x180005060  mov     ebx, eax
0x180005062  test    eax, eax
0x180005064  js      loc_180004F51
0x18000506a  test    r14d, r14d
0x18000506d  jz      short loc_180005094
0x18000506f  mov     r9, [rsp+78h+pwszExtendedInfoValue]; unsigned __int16 **
0x180005077  mov     edx, r14d; unsigned int
0x18000507a  mov     r8, [rsp+78h+pwszExtendedInfoName]; unsigned __int16 **
0x180005082  mov     rcx, rdi; this
0x180005085  call    ?SetExtendedInfo@CRight@@QEAAJIPEAPEAG0@Z; CRight::SetExtendedInfo(uint,ushort * *,ushort * *)
0x18000508a  mov     ebx, eax
0x18000508c  test    eax, eax
0x18000508e  js      loc_180004F51
0x180005094  mov     r8, [rsp+78h+phRight]; unsigned int *
0x18000509c  mov     rdx, rdi; void *
0x18000509f  mov     ecx, 6; unsigned int
0x1800050a4  call    ?CreateHandle@DRMCInt@@SAJIPEAXPEAK@Z; DRMCInt::CreateHandle(uint,void *,ulong *)
0x1800050a9  mov     ebx, eax
0x1800050ab  test    eax, eax
0x1800050ad  js      loc_180004F51
0x1800050b3  mov     rdi, r12
0x1800050b6  jmp     loc_180004F51
0x1800050bb  mov     rdi, r12
0x1800050be  mov     ebx, 8007000Eh
0x1800050c3  jmp     loc_180004F51
```
