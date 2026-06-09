# EAPTranslator::translate(_EAP_ATTRIBUTE &,_IASATTRIBUTE const &)

- ea: `0x18001be30`
- end: `0x18001c00f`
- name: `?translate@EAPTranslator@@YAHAEAU_EAP_ATTRIBUTE@@AEBU_IASATTRIBUTE@@@Z`
- size: `479`
- prototype: `__int64 __fastcall(EAPTranslator *__hidden this, struct _EAP_ATTRIBUTE *, const struct _IASATTRIBUTE *)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b170`
- `0x18001c018`

## callees

- `0x180001f0c`
- `0x180001f26`
- `0x18000ac10`
- `0x18000b81c`
- `0x18000c4a4`
- `0x18001be30`
- `0x1800254a0`
- `0x18002b472`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18001bfb8`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x18001bfb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bf3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bf3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EAPTranslator::translate(
        EAPTranslator *this,
        struct _EAP_ATTRIBUTE *a2,
        const struct _IASATTRIBUTE *a3)
{
  BYTE *v6; // rax
  __int64 v7; // rbx
  BYTE *p_pValue; // rbx
  unsigned int v9; // eax
  signed int v10; // eax
  int v11; // edx
  BYTE *v12; // rcx
  __int64 v13; // rax
  BYTE *pValue; // rax
  __int64 v15; // rbx
  void *v16; // rax
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF
  const char *v18; // [rsp+50h] [rbp+8h] BYREF

  *(_DWORD *)this = a2->pValue;
  switch ( a2[1].eaType )
  {
    case eatUserName:
    case eatUserPassword:
    case eatMD5CHAPPassword:
      p_pValue = (BYTE *)&a2[1].pValue;
LABEL_27:
      v9 = 4;
      *((_DWORD *)this + 1) = 4;
      break;
    case eatNASIPAddress:
      pValue = a2[1].pValue;
      v15 = 8;
      if ( *(_WORD *)pValue != 23 )
        v15 = 4;
      p_pValue = &pValue[v15];
      goto LABEL_27;
    case eatNASPort:
      v10 = IASAttributeAnsiAlloc((__int64)a2);
      if ( v10 )
      {
        if ( v10 > 0 )
          v10 = (unsigned __int16)v10 | 0x80070000;
        IASTL::issue_error((IASTL *)(unsigned int)v10, v11);
      }
      v12 = a2[1].pValue;
      if ( v12 )
      {
        v13 = -1;
        do
          ++v13;
        while ( v12[v13] );
        v9 = v13 + 1;
        *((_DWORD *)this + 1) = v9;
        p_pValue = a2[1].pValue;
      }
      else
      {
        p_pValue = 0;
        *((_DWORD *)this + 1) = 0;
        *((_QWORD *)this + 1) = 0;
        v9 = 0;
      }
      break;
    case eatServiceType:
    case eatFramedIPAddress:
      v9 = (unsigned int)a2[1].pValue;
      *((_DWORD *)this + 1) = v9;
      p_pValue = *(BYTE **)&a2[2].eaType;
      break;
    case eatFramedRouting:
      v6 = a2[1].pValue;
      v7 = 8;
      if ( *(_WORD *)v6 != 23 )
        v7 = 4;
      p_pValue = &v6[v7];
      v9 = 16;
      *((_DWORD *)this + 1) = 16;
      break;
    default:
      return 0;
  }
  if ( p_pValue )
  {
    v16 = CoTaskMemAlloc(v9);
    *((_QWORD *)this + 1) = v16;
    if ( !v16 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WppDbgPrint("Not enough memory to allocate EAP_ATTRIBUTE value");
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_0729333d348337bd43d2a4b59100ecc2_Traceguids, "NPSSVC");
      }
      v18 = "bad allocation";
      exception::exception((exception *)pExceptionObject, &v18, 1);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
    memset_0(v16, 0, *((unsigned int *)this + 1));
    memcpy_0(*((void **)this + 1), p_pValue, *((unsigned int *)this + 1));
  }
  return 1;
}

```

## disassembly

```asm
0x18001be30  mov     [rsp+arg_8], rbx
0x18001be35  mov     [rsp+arg_10], rbp
0x18001be3a  push    rdi
0x18001be3b  sub     rsp, 40h
0x18001be3f  mov     rbx, rdx
0x18001be42  mov     rdi, rcx
0x18001be45  mov     eax, [rdx+8]
0x18001be48  mov     [rcx], eax
0x18001be4a  mov     r8d, [rdx+10h]
0x18001be4e  mov     ebp, 4
0x18001be53  sub     r8d, 1
0x18001be57  jz      loc_18001BF26
0x18001be5d  sub     r8d, 1
0x18001be61  jz      loc_18001BF26
0x18001be67  sub     r8d, 1
0x18001be6b  jz      loc_18001BF26
0x18001be71  sub     r8d, 1
0x18001be75  jz      loc_18001BF10
0x18001be7b  sub     r8d, 1
0x18001be7f  jz      short loc_18001BEC4
0x18001be81  sub     r8d, 1
0x18001be85  jz      short loc_18001BEB8
0x18001be87  sub     r8d, 2
0x18001be8b  jz      short loc_18001BEB8
0x18001be8d  cmp     r8d, 2
0x18001be91  jz      short loc_18001BE9A
0x18001be93  xor     eax, eax
0x18001be95  jmp     loc_18001BFFF
0x18001be9a  mov     rax, [rdx+18h]
0x18001be9e  mov     ebx, 8
0x18001bea3  cmp     word ptr [rax], 17h
0x18001bea7  cmovnz  rbx, rbp
0x18001beab  add     rbx, rax
0x18001beae  mov     eax, 10h
0x18001beb3  mov     [rcx+4], eax
0x18001beb6  jmp     short loc_18001BF2F
0x18001beb8  mov     eax, [rdx+18h]
0x18001bebb  mov     [rcx+4], eax
0x18001bebe  mov     rbx, [rdx+20h]
0x18001bec2  jmp     short loc_18001BF2F
0x18001bec4  mov     rcx, rbx
0x18001bec7  call    IASAttributeAnsiAlloc
0x18001becc  test    eax, eax
0x18001bece  jz      short loc_18001BEE2
0x18001bed0  jle     short loc_18001BEDA
0x18001bed2  movzx   eax, ax
0x18001bed5  or      eax, 80070000h
0x18001beda  mov     ecx, eax; this
0x18001bedc  call    ?issue_error@IASTL@@YAXJ@Z; IASTL::issue_error(long)
0x18001bee2  mov     rcx, [rbx+18h]
0x18001bee6  test    rcx, rcx
0x18001bee9  jz      short loc_18001BF03
0x18001beeb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001beef  inc     rax
0x18001bef2  cmp     byte ptr [rcx+rax], 0
0x18001bef6  jnz     short loc_18001BEEF
0x18001bef8  inc     eax
0x18001befa  mov     [rdi+4], eax
0x18001befd  mov     rbx, [rbx+18h]
0x18001bf01  jmp     short loc_18001BF2F
0x18001bf03  xor     ebx, ebx
0x18001bf05  mov     [rdi+4], ebx
0x18001bf08  mov     [rdi+8], rbx
0x18001bf0c  xor     eax, eax
0x18001bf0e  jmp     short loc_18001BF2F
0x18001bf10  mov     rax, [rdx+18h]
0x18001bf14  mov     ebx, 8
0x18001bf19  cmp     word ptr [rax], 17h
0x18001bf1d  cmovnz  rbx, rbp
0x18001bf21  add     rbx, rax
0x18001bf24  jmp     short loc_18001BF2A
0x18001bf26  add     rbx, 18h
0x18001bf2a  mov     eax, ebp
0x18001bf2c  mov     [rcx+4], ebp
0x18001bf2f  test    rbx, rbx
0x18001bf32  jz      loc_18001BFFA
0x18001bf38  mov     ecx, eax; cb
0x18001bf3a  call    cs:__imp_CoTaskMemAlloc
0x18001bf40  mov     [rdi+8], rax
0x18001bf44  test    rax, rax
0x18001bf47  jnz     loc_18001BFDC
0x18001bf4d  lea     rcx, WPP_GLOBAL_Control
0x18001bf54  mov     rax, cs:WPP_GLOBAL_Control
0x18001bf5b  cmp     rax, rcx
0x18001bf5e  jz      short loc_18001BF9C
0x18001bf60  cmp     byte ptr [rax+19h], 2
0x18001bf64  jb      short loc_18001BF9C
0x18001bf66  test    [rax+1Ch], bpl
0x18001bf6a  jz      short loc_18001BF9C
0x18001bf6c  lea     rcx, aNotEnoughMemor_0; "Not enough memory to allocate EAP_ATTRI"...
0x18001bf73  call    WppDbgPrint
0x18001bf78  mov     edx, 0Ah
0x18001bf7d  lea     r9, aNpssvc; "NPSSVC"
0x18001bf84  lea     r8, WPP_0729333d348337bd43d2a4b59100ecc2_Traceguids
0x18001bf8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf92  mov     rcx, [rcx+10h]
0x18001bf96  call    WPP_SF_s
0x18001bf9b  nop
0x18001bf9c  lea     rax, aBadAllocation; "bad allocation"
0x18001bfa3  mov     [rsp+48h+arg_0], rax
0x18001bfa8  mov     r8d, 1
0x18001bfae  lea     rdx, [rsp+48h+arg_0]
0x18001bfb3  lea     rcx, [rsp+48h+pExceptionObject]
0x18001bfb8  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18001bfbe  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001bfc5  mov     [rsp+48h+pExceptionObject], rax
0x18001bfca  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001bfd1  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001bfd6  call    _CxxThrowException_0
0x18001bfdc  mov     r8d, [rdi+4]; Size
0x18001bfe0  xor     edx, edx; Val
0x18001bfe2  mov     rcx, rax; void *
0x18001bfe5  call    memset_0
0x18001bfea  mov     r8d, [rdi+4]; Size
0x18001bfee  mov     rdx, rbx; Src
0x18001bff1  mov     rcx, [rdi+8]; void *
0x18001bff5  call    memcpy_0
0x18001bffa  mov     eax, 1
0x18001bfff  mov     rbx, [rsp+48h+arg_8]
0x18001c004  mov     rbp, [rsp+48h+arg_10]
0x18001c009  add     rsp, 40h
0x18001c00d  pop     rdi
0x18001c00e  retn
```
