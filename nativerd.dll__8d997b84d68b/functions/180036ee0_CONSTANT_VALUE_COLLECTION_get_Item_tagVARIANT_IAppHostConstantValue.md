# CONSTANT_VALUE_COLLECTION::get_Item(tagVARIANT,IAppHostConstantValue * *)

- ea: `0x180036ee0`
- end: `0x1800370aa`
- name: `?get_Item@CONSTANT_VALUE_COLLECTION@@UEAAJUtagVARIANT@@PEAPEAUIAppHostConstantValue@@@Z`
- size: `458`
- prototype: `int(CONSTANT_VALUE_COLLECTION *__hidden this, struct tagVARIANT *__struct_ptr, struct IAppHostConstantValue **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x180010468`
- `0x18001c250`
- `0x180036338`
- `0x1800369f0`
- `0x180036ee0`
- `0x180059bea`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180037080`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180037080`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003703e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003703e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180036f40`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180036f40`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003700b`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003700b`
- `OLEAUT32!__imp_VariantInit` at `0x180036f62`
- `OLEAUT32!__imp_VariantInit` at `0x180036f62`
- `OLEAUT32!__imp_VariantChangeType` at `0x180036fa9`
- `OLEAUT32!__imp_VariantChangeType` at `0x180036fa9`

## pseudocode

```c
__int64 __fastcall CONSTANT_VALUE_COLLECTION::get_Item(
        SCHEMA_ATTRIBUTE **this,
        struct tagVARIANT *a2,
        struct IAppHostConstantValue **a3)
{
  HRESULT StringValueByName; // ebx
  unsigned int v7; // ebx
  __int64 v8; // rcx
  int v9; // eax
  __int64 **v10; // rcx
  __int64 *v11; // rdi
  const unsigned __int16 *v12; // rdx
  CONSTANT_VALUE *v13; // rax
  struct IAppHostConstantValue *v14; // rdi
  const unsigned __int16 *Str; // rax
  unsigned int v17; // [rsp+20h] [rbp-E0h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v19[64]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v20[256]; // [rsp+80h] [rbp-80h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  memset_0(v20, 0, sizeof(v20));
  STRU::STRU((STRU *)v19, v20, 0x100u);
  v17 = 0;
  if ( a3 )
  {
    VariantInit(&pvarg);
    if ( a2->vt == 8 )
    {
      StringValueByName = SCHEMA_ATTRIBUTE::GetStringValueByName(this[3], a2->bstrVal, (struct STRU *)v19, &v17);
      if ( StringValueByName >= 0 )
      {
        v7 = v17;
LABEL_17:
        v13 = (CONSTANT_VALUE *)operator new(0x20u);
        if ( v13 && (v14 = (struct IAppHostConstantValue *)CONSTANT_VALUE::CONSTANT_VALUE(v13)) != 0 )
        {
          Str = STRU::QueryStr((STRU *)v19);
          HIDWORD(v14[2].lpVtbl) = v7;
          StringValueByName = SMALL_STRU::Copy((SMALL_STRU *)&v14[3], Str);
          if ( StringValueByName < 0 )
            ((void (__fastcall *)(struct IAppHostConstantValue *))v14->lpVtbl->Release)(v14);
          else
            *a3 = v14;
        }
        else
        {
          StringValueByName = -2147024888;
        }
      }
    }
    else
    {
      StringValueByName = VariantChangeType(&pvarg, a2, 0, 0x12u);
      if ( StringValueByName >= 0 )
      {
        v8 = *((_QWORD *)this[3] + 7);
        if ( v8 )
        {
          v9 = 0;
          v10 = (__int64 **)(v8 + 16);
          v11 = *v10;
          while ( v11 != (__int64 *)v10 )
          {
            if ( v9 == pvarg.uiVal )
            {
              if ( !v11 )
                break;
              v12 = &szDomain;
              if ( v11[2] )
                v12 = (const unsigned __int16 *)v11[2];
              StringValueByName = STRU::Copy((STRU *)v19, v12);
              if ( StringValueByName >= 0 )
              {
                v7 = *((_DWORD *)v11 + 6);
                goto LABEL_17;
              }
              goto LABEL_24;
            }
            v11 = (__int64 *)*v11;
            ++v9;
          }
        }
        StringValueByName = -2147023483;
      }
    }
  }
  else
  {
    StringValueByName = -2147024809;
  }
LABEL_24:
  STRU::~STRU((STRU *)v19);
  return (unsigned int)StringValueByName;
}

```

## disassembly

```asm
0x180036ee0  mov     [rsp-8+arg_18], rbx
0x180036ee5  push    rbp
0x180036ee6  push    rsi
0x180036ee7  push    rdi
0x180036ee8  lea     rbp, [rsp-190h]
0x180036ef0  sub     rsp, 290h
0x180036ef7  mov     rax, cs:__security_cookie
0x180036efe  xor     rax, rsp
0x180036f01  mov     [rbp+1A0h+var_20], rax
0x180036f08  mov     rsi, r8
0x180036f0b  mov     rbx, rdx
0x180036f0e  mov     rdi, rcx
0x180036f11  xorps   xmm0, xmm0
0x180036f14  xor     eax, eax
0x180036f16  lea     rcx, [rbp+1A0h+var_220]; void *
0x180036f1a  xor     edx, edx; Val
0x180036f1c  mov     qword ptr [rsp+2A0h+pvarg+10h], rax
0x180036f21  mov     r8d, 200h; Size
0x180036f27  movups  xmmword ptr [rsp+2A0h+pvarg], xmm0
0x180036f2c  call    memset_0
0x180036f31  mov     r8d, 100h
0x180036f37  lea     rdx, [rbp+1A0h+var_220]
0x180036f3b  lea     rcx, [rsp+2A0h+var_260]
0x180036f40  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180036f46  mov     [rsp+2A0h+var_280], 0
0x180036f4e  test    rsi, rsi
0x180036f51  jnz     short loc_180036F5D
0x180036f53  mov     ebx, 80070057h
0x180036f58  jmp     loc_18003707B
0x180036f5d  lea     rcx, [rsp+2A0h+pvarg]; pvarg
0x180036f62  call    cs:__imp_VariantInit
0x180036f68  cmp     word ptr [rbx], 8
0x180036f6c  jnz     short loc_180036F98
0x180036f6e  mov     rdx, [rbx+8]; unsigned __int16 *
0x180036f72  lea     r9, [rsp+2A0h+var_280]; unsigned int *
0x180036f77  mov     rcx, [rdi+18h]; this
0x180036f7b  lea     r8, [rsp+2A0h+var_260]; struct STRU *
0x180036f80  call    ?GetStringValueByName@SCHEMA_ATTRIBUTE@@QEAAJPEBGPEAVSTRU@@PEAK@Z; SCHEMA_ATTRIBUTE::GetStringValueByName(ushort const *,STRU *,ulong *)
0x180036f85  mov     ebx, eax
0x180036f87  test    eax, eax
0x180036f89  js      loc_18003707B
0x180036f8f  mov     ebx, [rsp+2A0h+var_280]
0x180036f93  jmp     loc_18003701A
0x180036f98  mov     r9d, 12h; vt
0x180036f9e  lea     rcx, [rsp+2A0h+pvarg]; pvargDest
0x180036fa3  xor     r8d, r8d; wFlags
0x180036fa6  mov     rdx, rbx; pvarSrc
0x180036fa9  call    cs:__imp_VariantChangeType
0x180036faf  mov     ebx, eax
0x180036fb1  test    eax, eax
0x180036fb3  js      loc_18003707B
0x180036fb9  mov     rax, [rdi+18h]
0x180036fbd  mov     rcx, [rax+38h]
0x180036fc1  test    rcx, rcx
0x180036fc4  jz      loc_180037076
0x180036fca  movzx   edx, word ptr [rsp+2A0h+pvarg+8]
0x180036fcf  xor     eax, eax
0x180036fd1  add     rcx, 10h
0x180036fd5  mov     rdi, [rcx]
0x180036fd8  cmp     rdi, rcx
0x180036fdb  jz      loc_180037076
0x180036fe1  cmp     eax, edx
0x180036fe3  jz      short loc_180036FEC
0x180036fe5  mov     rdi, [rdi]
0x180036fe8  inc     eax
0x180036fea  jmp     short loc_180036FD8
0x180036fec  test    rdi, rdi
0x180036fef  jz      loc_180037076
0x180036ff5  cmp     qword ptr [rdi+10h], 0
0x180036ffa  lea     rdx, szDomain
0x180037001  lea     rcx, [rsp+2A0h+var_260]
0x180037006  cmovnz  rdx, [rdi+10h]
0x18003700b  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180037011  mov     ebx, eax
0x180037013  test    eax, eax
0x180037015  js      short loc_18003707B
0x180037017  mov     ebx, [rdi+18h]
0x18003701a  mov     ecx, 20h ; ' '; Size
0x18003701f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180037024  test    rax, rax
0x180037027  jz      short loc_18003706F
0x180037029  mov     rcx, rax; this
0x18003702c  call    ??0CONSTANT_VALUE@@QEAA@XZ; CONSTANT_VALUE::CONSTANT_VALUE(void)
0x180037031  mov     rdi, rax
0x180037034  test    rax, rax
0x180037037  jz      short loc_18003706F
0x180037039  lea     rcx, [rsp+2A0h+var_260]
0x18003703e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180037044  lea     rcx, [rdi+18h]; this
0x180037048  mov     [rdi+14h], ebx
0x18003704b  mov     rdx, rax; unsigned __int16 *
0x18003704e  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x180037053  mov     ebx, eax
0x180037055  test    eax, eax
0x180037057  js      short loc_18003705E
0x180037059  mov     [rsi], rdi
0x18003705c  jmp     short loc_18003707B
0x18003705e  mov     rax, [rdi]
0x180037061  mov     rcx, rdi
0x180037064  mov     rax, [rax+10h]
0x180037068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003706d  jmp     short loc_18003707B
0x18003706f  mov     ebx, 80070008h
0x180037074  jmp     short loc_18003707B
0x180037076  mov     ebx, 80070585h
0x18003707b  lea     rcx, [rsp+2A0h+var_260]
0x180037080  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180037086  mov     eax, ebx
0x180037088  mov     rcx, [rbp+1A0h+var_20]
0x18003708f  xor     rcx, rsp; StackCookie
0x180037092  call    __security_check_cookie
0x180037097  mov     rbx, [rsp+2A0h+arg_18]
0x18003709f  add     rsp, 290h
0x1800370a6  pop     rdi
0x1800370a7  pop     rsi
0x1800370a8  pop     rbp
0x1800370a9  retn
```
