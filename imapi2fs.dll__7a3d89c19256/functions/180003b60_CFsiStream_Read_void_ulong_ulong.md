# CFsiStream::Read(void *,ulong,ulong *)

- ea: `0x180003b60`
- end: `0x180003e56`
- name: `?Read@CFsiStream@@UEAAJPEAXKPEAK@Z`
- size: `758`
- prototype: `int(CFsiStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003580`
- `0x180003a20`
- `0x180003b60`
- `0x180005040`
- `0x18000960c`
- `0x1800251dc`
- `0x18002d4e4`
- `0x18002db48`
- `0x18008170e`
- `0x180088010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x180003be2`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180003be2`
- `KERNEL32!LeaveCriticalSection` at `0x180003e0a`
- `KERNEL32!LeaveCriticalSection` at `0x180003e0a`
- `KERNEL32!EnterCriticalSection` at `0x180003c18`
- `KERNEL32!EnterCriticalSection` at `0x180003c18`

## string_xrefs

- `0x180003b88`: `CFsiStream::Read`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFsiStream::Read(CFsiStream *this, void *a2, unsigned int a3, unsigned int *a4)
{
  size_t v5; // r12
  CIMAPIException *v8; // rax
  _DWORD *v9; // rbx
  _DWORD *v10; // r8
  char *v11; // rsi
  int v12; // r9d
  unsigned __int64 v13; // rdx
  unsigned int v14; // ecx
  _DWORD *v16; // [rsp+30h] [rbp-B8h]
  _DWORD *pExceptionObject; // [rsp+38h] [rbp-B0h] BYREF
  unsigned __int64 v18; // [rsp+40h] [rbp-A8h]
  const char *v19; // [rsp+48h] [rbp-A0h]
  char *v20; // [rsp+50h] [rbp-98h]
  _BYTE v21[144]; // [rsp+58h] [rbp-90h] BYREF
  void *v22; // [rsp+F8h] [rbp+10h] BYREF
  IErrorInfo *pperrinfo; // [rsp+108h] [rbp+20h] BYREF

  v22 = a2;
  v5 = a3;
  v19 = "CFsiStream::Read";
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      10,
      WPP_3fd13933099034642aae2217eb139841_Traceguids,
      "CFsiStream::Read");
  }
  pperrinfo = 0;
  if ( GetErrorInfo(0, &pperrinfo) >= 0 && pperrinfo )
    ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
  v20 = (char *)this - 64;
  if ( *((_BYTE *)this - 64) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this - 56));
  if ( a4 )
    *a4 = 0;
  try
  {
    if ( !a2 )
    {
      v8 = (CIMAPIException *)operator new(0x58u);
      v22 = v8;
      if ( v8 )
        v8 = CIMAPIException::CIMAPIException(v8, -2147467261, L"pBuffer");
      SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(&v22, v8);
      v9 = v22;
      if ( v22 && *(_QWORD *)v22 )
      {
        CIMAPIException::SetCodeRefInfo(
          *(CIMAPIException **)v22,
          "drivers\\storage\\imapi2\\filesystemimaging\\fsi\\fsistream.cpp",
          34);
        pExceptionObject = v9;
        if ( v9 )
          ++v9[2];
        throw (SmartClassPtr<CIMAPIException,CIMAPIException> *)&pExceptionObject;
      }
      CIMAPIException::CIMAPIException(
        (CIMAPIException *)v21,
        (const struct CIMAPIException *)&CIMAPIException::badAlloc);
      throw (CIMAPIException *)v21;
    }
    v16 = (_DWORD *)**((_QWORD **)this + 9);
    LODWORD(pperrinfo) = 0;
    if ( a4 )
      *a4 = 0;
    memset_0(v22, 0, v5);
    v10 = v16;
    if ( v5 >= *((_QWORD *)v16 + 2) - *((_QWORD *)v16 + 1) )
      LODWORD(v5) = v16[4] - v16[2];
    v11 = (char *)v22;
    v12 = (int)pperrinfo;
    do
    {
      if ( !(_DWORD)v5 )
        break;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v10 + 24LL))(v10);
      LODWORD(v22) = 0;
      v13 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v16 + 8LL))(v16);
      if ( v13 >= (unsigned int)v5 )
        v13 = (unsigned int)v5;
      v18 = v13;
      LODWORD(v22) = 0;
      (*(void (__fastcall **)(_DWORD *, char *, _QWORD, void **))(*(_QWORD *)v16 + 32LL))(
        v16,
        v11,
        (unsigned int)v13,
        &v22);
      v14 = (unsigned int)v22;
      v12 = (_DWORD)v22 + (_DWORD)pperrinfo;
      LODWORD(pperrinfo) = (_DWORD)v22 + (_DWORD)pperrinfo;
      LODWORD(v5) = v5 - (_DWORD)v22;
      v11 += (unsigned int)v22;
      v10 = v16;
      *((_QWORD *)v16 + 1) += (unsigned int)v22;
    }
    while ( v14 >= (unsigned int)v18 );
    if ( a4 )
      *a4 = v12;
  }
  catch ( ... )
  {
    ExceptionDispatcher(&CLSID_FsiStream);
  }
  if ( *((_BYTE *)this - 64) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this - 56));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      11,
      WPP_3fd13933099034642aae2217eb139841_Traceguids,
      "CFsiStream::Read");
  }
  return 0;
}

```

## disassembly

```asm
0x180003b60  mov     [rsp+arg_8], rdx
0x180003b65  mov     [rsp+arg_0], rcx
0x180003b6a  push    rbx
0x180003b6b  push    rsi
0x180003b6c  push    rdi
0x180003b6d  push    r12
0x180003b6f  push    r13
0x180003b71  push    r14
0x180003b73  push    r15
0x180003b75  sub     rsp, 0B0h
0x180003b7c  mov     r14, r9
0x180003b7f  mov     r12d, r8d
0x180003b82  mov     rsi, rdx
0x180003b85  mov     r15, rcx
0x180003b88  lea     rbx, aCfsistreamRead; "CFsiStream::Read"
0x180003b8f  mov     [rsp+0E8h+var_A0], rbx
0x180003b94  lea     r13, WPP_GLOBAL_Control
0x180003b9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ba2  cmp     rcx, r13
0x180003ba5  jz      short loc_180003BCC
0x180003ba7  test    byte ptr [rcx+44h], 8
0x180003bab  jz      short loc_180003BCC
0x180003bad  cmp     byte ptr [rcx+41h], 5
0x180003bb1  jb      short loc_180003BCC
0x180003bb3  mov     edx, 0Ah
0x180003bb8  mov     r9, rbx
0x180003bbb  lea     r8, WPP_3fd13933099034642aae2217eb139841_Traceguids
0x180003bc2  mov     rcx, [rcx+38h]
0x180003bc6  call    WPP_SF_s
0x180003bcb  nop
0x180003bcc  mov     [rsp+0E8h+pperrinfo], 0
0x180003bd8  lea     rdx, [rsp+0E8h+pperrinfo]; pperrinfo
0x180003be0  xor     ecx, ecx; dwReserved
0x180003be2  call    cs:__imp_GetErrorInfo
0x180003be8  test    eax, eax
0x180003bea  js      short loc_180003C06
0x180003bec  mov     rcx, [rsp+0E8h+pperrinfo]
0x180003bf4  test    rcx, rcx
0x180003bf7  jz      short loc_180003C06
0x180003bf9  mov     rax, [rcx]
0x180003bfc  mov     rax, [rax+10h]
0x180003c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c05  nop
0x180003c06  lea     rdi, [r15-40h]
0x180003c0a  mov     [rsp+0E8h+var_98], rdi
0x180003c0f  cmp     byte ptr [rdi], 0
0x180003c12  jz      short loc_180003C1E
0x180003c14  lea     rcx, [r15-38h]; lpCriticalSection
0x180003c18  call    cs:__imp_EnterCriticalSection
0x180003c1e  xor     ecx, ecx
0x180003c20  test    r14, r14
0x180003c23  jz      short loc_180003C28
0x180003c25  mov     [r14], ecx
0x180003c28  test    rsi, rsi
0x180003c2b  jnz     loc_180003CD6
0x180003c31  mov     ecx, 58h ; 'X'; unsigned __int64
0x180003c36  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003c3b  mov     [rsp+0E8h+arg_8], rax
0x180003c43  test    rax, rax
0x180003c46  jz      short loc_180003C5D
0x180003c48  lea     r8, aPbuffer; "pBuffer"
0x180003c4f  mov     edx, 80004003h; int
0x180003c54  mov     rcx, rax; this
0x180003c57  call    ??0CIMAPIException@@QEAA@JZZ; CIMAPIException::CIMAPIException(long,...)
0x180003c5c  nop
0x180003c5d  mov     rdx, rax
0x180003c60  lea     rcx, [rsp+0E8h+arg_8]
0x180003c68  call    ??0?$SmartPtr@VCIMAPIException@@@@QEAA@PEAVCIMAPIException@@@Z; SmartPtr<CIMAPIException>::SmartPtr<CIMAPIException>(CIMAPIException *)
0x180003c6d  nop
0x180003c6e  mov     rbx, [rsp+0E8h+arg_8]
0x180003c76  test    rbx, rbx
0x180003c79  jz      short loc_180003CB3
0x180003c7b  mov     rcx, [rbx]; this
0x180003c7e  test    rcx, rcx
0x180003c81  jz      short loc_180003CB3
0x180003c83  mov     r8d, 22h ; '"'; int
0x180003c89  lea     rdx, aDriversStorage_4; "drivers\\storage\\imapi2\\filesystemima"...
0x180003c90  call    ?SetCodeRefInfo@CIMAPIException@@QEAAXPEBDH@Z; CIMAPIException::SetCodeRefInfo(char const *,int)
0x180003c95  mov     [rsp+0E8h+pExceptionObject], rbx
0x180003c9a  test    rbx, rbx
0x180003c9d  jz      short loc_180003CA2
0x180003c9f  inc     dword ptr [rbx+8]
0x180003ca2  lea     rdx, _TI2?AV?$SmartClassPtr@VCIMAPIException@@V1@@@; pThrowInfo
0x180003ca9  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x180003cae  call    _CxxThrowException_0
0x180003cb3  lea     rdx, ?badAlloc@CIMAPIException@@2V1@A; struct CIMAPIException *
0x180003cba  lea     rcx, [rsp+0E8h+var_90]; this
0x180003cbf  call    ??0CIMAPIException@@QEAA@AEBV0@@Z; CIMAPIException::CIMAPIException(CIMAPIException const &)
0x180003cc4  lea     rdx, _TI1?AVCIMAPIException@@; pThrowInfo
0x180003ccb  lea     rcx, [rsp+0E8h+var_90]; pExceptionObject
0x180003cd0  call    _CxxThrowException_0
0x180003cd6  mov     rax, [r15+48h]
0x180003cda  mov     rax, [rax]
0x180003cdd  mov     [rsp+0E8h+var_B8], rax
0x180003ce2  mov     dword ptr [rsp+0E8h+pperrinfo], ecx
0x180003ce9  test    r14, r14
0x180003cec  jz      short loc_180003CF1
0x180003cee  mov     [r14], ecx
0x180003cf1  mov     r8, r12; Size
0x180003cf4  xor     edx, edx; Val
0x180003cf6  mov     rcx, [rsp+0E8h+arg_8]; void *
0x180003cfe  call    memset_0
0x180003d03  mov     r8, [rsp+0E8h+var_B8]
0x180003d08  mov     rdx, [r8+8]
0x180003d0c  mov     rax, [r8+10h]
0x180003d10  sub     rax, rdx
0x180003d13  cmp     r12, rax
0x180003d16  jb      short loc_180003D1B
0x180003d18  mov     r12d, eax
0x180003d1b  mov     rsi, [rsp+0E8h+arg_8]
0x180003d23  mov     r9d, dword ptr [rsp+0E8h+pperrinfo]
0x180003d2b  test    r12d, r12d
0x180003d2e  jz      loc_180003DD5
0x180003d34  mov     rax, [r8]
0x180003d37  mov     rcx, r8
0x180003d3a  mov     rax, [rax+18h]
0x180003d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d43  mov     dword ptr [rsp+0E8h+arg_8], 0
0x180003d4e  mov     rcx, [rsp+0E8h+var_B8]
0x180003d53  mov     rax, [rcx]
0x180003d56  mov     rax, [rax+8]
0x180003d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d5f  mov     rdx, rax
0x180003d62  mov     ecx, r12d
0x180003d65  cmp     rax, rcx
0x180003d68  cmovnb  edx, r12d
0x180003d6c  mov     [rsp+0E8h+var_A8], rdx
0x180003d71  mov     dword ptr [rsp+0E8h+arg_8], 0
0x180003d7c  mov     r10, [rsp+0E8h+var_B8]
0x180003d81  mov     rcx, [r10]
0x180003d84  mov     rax, [rcx+20h]
0x180003d88  lea     r9, [rsp+0E8h+arg_8]
0x180003d90  mov     r8d, edx
0x180003d93  mov     rdx, rsi
0x180003d96  mov     rcx, r10
0x180003d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d9e  mov     ecx, dword ptr [rsp+0E8h+arg_8]
0x180003da5  mov     r9d, dword ptr [rsp+0E8h+pperrinfo]
0x180003dad  add     r9d, ecx
0x180003db0  mov     dword ptr [rsp+0E8h+pperrinfo], r9d
0x180003db8  sub     r12d, ecx
0x180003dbb  add     rsi, rcx
0x180003dbe  mov     r8, [rsp+0E8h+var_B8]
0x180003dc3  add     [r8+8], rcx
0x180003dc7  mov     rdx, [r8+8]
0x180003dcb  cmp     ecx, dword ptr [rsp+0E8h+var_A8]
0x180003dcf  jnb     loc_180003D2B
0x180003dd5  xor     esi, esi
0x180003dd7  test    r14, r14
0x180003dda  jz      short loc_180003DDF
0x180003ddc  mov     [r14], r9d
0x180003ddf  jmp     short loc_180003E01
0x180003de1  lea     r13, WPP_GLOBAL_Control
0x180003de8  mov     r15, [rsp+0E8h+arg_0]
0x180003df0  mov     rbx, [rsp+0E8h+var_A0]
0x180003df5  mov     esi, dword ptr [rsp+0E8h+arg_8]
0x180003dfc  mov     rdi, [rsp+0E8h+var_98]
0x180003e01  cmp     byte ptr [rdi], 0
0x180003e04  jz      short loc_180003E11
0x180003e06  lea     rcx, [r15-38h]; lpCriticalSection
0x180003e0a  call    cs:__imp_LeaveCriticalSection
0x180003e10  nop
0x180003e11  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e18  cmp     rcx, r13
0x180003e1b  jz      short loc_180003E41
0x180003e1d  test    byte ptr [rcx+44h], 8
0x180003e21  jz      short loc_180003E41
0x180003e23  cmp     byte ptr [rcx+41h], 5
0x180003e27  jb      short loc_180003E41
0x180003e29  mov     edx, 0Bh
0x180003e2e  mov     r9, rbx
0x180003e31  lea     r8, WPP_3fd13933099034642aae2217eb139841_Traceguids
0x180003e38  mov     rcx, [rcx+38h]
0x180003e3c  call    WPP_SF_s
0x180003e41  mov     eax, esi
0x180003e43  add     rsp, 0B0h
0x180003e4a  pop     r15
0x180003e4c  pop     r14
0x180003e4e  pop     r13
0x180003e50  pop     r12
0x180003e52  pop     rdi
0x180003e53  pop     rsi
0x180003e54  pop     rbx
0x180003e55  retn
```
