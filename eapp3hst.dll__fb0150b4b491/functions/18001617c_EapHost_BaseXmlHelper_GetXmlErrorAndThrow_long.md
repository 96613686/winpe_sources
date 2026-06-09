# EapHost::BaseXmlHelper::GetXmlErrorAndThrow(long)

- ea: `0x18001617c`
- end: `0x18001629d`
- name: `?GetXmlErrorAndThrow@BaseXmlHelper@EapHost@@SAXJ@Z`
- size: `289`
- prototype: `void __fastcall __noreturn(unsigned int)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015f10`
- `0x180015fc4`
- `0x1800160ac`
- `0x1800162d4`

## callees

- `0x1800139a4`
- `0x1800151ec`
- `0x18001549c`
- `0x18001617c`
- `0x1800165a4`
- `0x180034010`

## import_xrefs

- `combase!GetErrorInfo` at `0x1800161ca`
- `combase!GetErrorInfo` at `0x1800161ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall __noreturn EapHost::BaseXmlHelper::GetXmlErrorAndThrow(unsigned int a1)
{
  HRESULT ErrorInfo; // eax
  unsigned int v3; // ecx
  unsigned int v4; // edx
  unsigned int v5; // ecx
  IErrorInfo *pperrinfo; // [rsp+20h] [rbp-49h] BYREF
  __int64 v7; // [rsp+28h] [rbp-41h] BYREF
  void **v8; // [rsp+30h] [rbp-39h] BYREF
  char v9; // [rsp+38h] [rbp-31h]
  __int64 v10; // [rsp+3Ch] [rbp-2Dh]
  int v11; // [rsp+48h] [rbp-21h]
  _BYTE v12[96]; // [rsp+50h] [rbp-19h] BYREF

  pperrinfo = 0;
  v9 = 0;
  v10 = 0;
  v8 = &EapHost::EapMethodType::`vftable';
  v11 = 0;
  ErrorInfo = GetErrorInfo(0, &pperrinfo);
  if ( ErrorInfo >= 0 && ErrorInfo != 1 )
  {
    v7 = 0;
    if ( ((int (__fastcall *)(IErrorInfo *, __int64 *))pperrinfo->lpVtbl->GetDescription)(pperrinfo, &v7) < 0 )
    {
      v3 = (unsigned __int16)a1;
      if ( (a1 & 0x1FFF0000) != 0x70000 )
        v3 = a1;
      EapHost::EapException::Throw(v3, (const struct EapHost::EapMethodType *)&v8, a1);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_1dc4107c12973fe87cbae404ee4330ac_Traceguids, v7);
    v4 = (unsigned __int16)a1;
    if ( (a1 & 0x1FFF0000) != 0x70000 )
      v4 = a1;
    EapHost::EapError::EapError((EapHost::EapError *)v12, v4, 0, 0);
    EapHost::EapException::Throw((const struct EapHost::EapError *)v12);
  }
  v5 = (unsigned __int16)a1;
  if ( (a1 & 0x1FFF0000) != 0x70000 )
    v5 = a1;
  EapHost::EapException::Throw(v5, (const struct EapHost::EapMethodType *)&v8, a1);
}

```

## disassembly

```asm
0x18001617c  mov     [rsp-8+arg_8], rbx
0x180016181  push    rbp
0x180016182  lea     rbp, [rsp-57h]
0x180016187  sub     rsp, 0C0h
0x18001618e  mov     rax, cs:__security_cookie
0x180016195  xor     rax, rsp
0x180016198  mov     [rbp+57h+var_10], rax
0x18001619c  mov     ebx, ecx
0x18001619e  mov     [rbp+57h+pperrinfo], 0
0x1800161a6  mov     [rbp+57h+var_88], 0
0x1800161aa  mov     [rbp+57h+var_84], 0
0x1800161b2  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x1800161b9  mov     [rbp+57h+var_90], rax
0x1800161bd  mov     [rbp+57h+var_78], 0
0x1800161c4  lea     rdx, [rbp+57h+pperrinfo]; pperrinfo
0x1800161c8  xor     ecx, ecx; dwReserved
0x1800161ca  call    cs:__imp_GetErrorInfo
0x1800161d0  test    eax, eax
0x1800161d2  js      loc_18001627E
0x1800161d8  cmp     eax, 1
0x1800161db  jz      loc_18001627E
0x1800161e1  mov     [rbp+57h+var_98], 0
0x1800161e9  mov     rcx, [rbp+57h+pperrinfo]
0x1800161ed  mov     rax, [rcx]
0x1800161f0  lea     rdx, [rbp+57h+var_98]
0x1800161f4  mov     rax, [rax+28h]
0x1800161f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161fd  test    eax, eax
0x1800161ff  jns     short loc_180016220
0x180016201  mov     eax, ebx
0x180016203  and     eax, 1FFF0000h
0x180016208  movzx   ecx, bx
0x18001620b  cmp     eax, 70000h
0x180016210  cmovnz  ecx, ebx; unsigned int
0x180016213  mov     r8d, ebx; unsigned int
0x180016216  lea     rdx, [rbp+57h+var_90]; struct EapHost::EapMethodType *
0x18001621a  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x180016220  lea     rax, WPP_GLOBAL_Control
0x180016227  mov     rcx, cs:WPP_GLOBAL_Control
0x18001622e  cmp     rcx, rax
0x180016231  jz      short loc_180016252
0x180016233  test    byte ptr [rcx+1Ch], 1
0x180016237  jz      short loc_180016252
0x180016239  mov     edx, 0Ah
0x18001623e  mov     r9, [rbp+57h+var_98]
0x180016242  lea     r8, WPP_1dc4107c12973fe87cbae404ee4330ac_Traceguids
0x180016249  mov     rcx, [rcx+10h]
0x18001624d  call    WPP_SF_S
0x180016252  mov     eax, ebx
0x180016254  and     eax, 1FFF0000h
0x180016259  movzx   edx, bx
0x18001625c  cmp     eax, 70000h
0x180016261  cmovnz  edx, ebx; unsigned int
0x180016264  xor     r9d, r9d; unsigned int
0x180016267  xor     r8d, r8d; struct EapHost::EapMethodType *
0x18001626a  lea     rcx, [rbp+57h+var_70]; this
0x18001626e  call    ??0EapError@EapHost@@QEAA@IPEBVEapMethodType@1@I@Z; EapHost::EapError::EapError(uint,EapHost::EapMethodType const *,uint)
0x180016273  nop
0x180016274  lea     rcx, [rbp+57h+var_70]; struct EapHost::EapError *
0x180016278  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x18001627e  mov     eax, ebx
0x180016280  and     eax, 1FFF0000h
0x180016285  movzx   ecx, bx
0x180016288  cmp     eax, 70000h
0x18001628d  cmovnz  ecx, ebx; unsigned int
0x180016290  mov     r8d, ebx; unsigned int
0x180016293  lea     rdx, [rbp+57h+var_90]; struct EapHost::EapMethodType *
0x180016297  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
```
