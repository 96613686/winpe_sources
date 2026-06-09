# CCertRequest::_FindCAPropInfo(ushort *,long,_CAPROP const * *)

- ea: `0x18000ffc4`
- end: `0x180010198`
- name: `?_FindCAPropInfo@CCertRequest@@AEAAJPEAGJPEAPEBU_CAPROP@@@Z`
- size: `468`
- prototype: `__int64 __fastcall(CCertRequest *this, unsigned __int16 *, int, const struct _CAPROP **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e680`
- `0x18000e720`

## callees

- `0x18000ffc4`
- `0x18001053c`
- `0x18003f010`

## import_xrefs

- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180010056`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180010091`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x1800100db`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180010108`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180010056`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180010091`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x1800100db`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x180010108`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010178`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010178`
- `certca!__imp_?myCAPropInfoUnmarshal@@YAJPEBU_CATRANSPROP@@JKPEAPEAU_CAPROP@@@Z` at `0x1800100f9`
- `certca!__imp_?myCAPropInfoUnmarshal@@YAJPEBU_CATRANSPROP@@JKPEAPEAU_CAPROP@@@Z` at `0x1800100f9`
- `certca!__imp_?myCAPropInfoLookup@@YAJPEBU_CAPROP@@JJPEAPEBU1@@Z` at `0x180010155`
- `certca!__imp_?myCAPropInfoLookup@@YAJPEBU_CAPROP@@JJPEAPEBU1@@Z` at `0x180010155`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180010168`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180010168`

## pseudocode

```c
__int64 __fastcall CCertRequest::_FindCAPropInfo(
        CCertRequest *this,
        unsigned __int16 *a2,
        int a3,
        const struct _CAPROP **a4)
{
  const struct _CAPROP **v4; // r12
  CCertRequest *v5; // rsi
  unsigned int v6; // eax
  unsigned int v7; // edi
  unsigned int v8; // ecx
  struct _CAPROP **v9; // r15
  void (*v10)(unsigned int, struct _EXCEPTION_POINTERS *); // rbx
  unsigned int v11; // edx
  void (*v12)(unsigned int, struct _EXCEPTION_POINTERS *); // rbx
  const unsigned __int16 *v13; // r14
  const unsigned __int16 *v15; // [rsp+38h] [rbp-70h] BYREF
  CCertRequest *v16; // [rsp+40h] [rbp-68h]
  struct _CAPROP **v17; // [rsp+48h] [rbp-60h]
  void (*v18)(unsigned int, struct _EXCEPTION_POINTERS *); // [rsp+50h] [rbp-58h]
  const struct _EXCEPTION_POINTERS *v19; // [rsp+58h] [rbp-50h] BYREF
  const struct _EXCEPTION_POINTERS *v20; // [rsp+60h] [rbp-48h] BYREF
  __int64 v21; // [rsp+68h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-38h]

  v4 = a4;
  v5 = this;
  v15 = 0;
  v21 = 0;
  pv = 0;
  *a4 = 0;
  v6 = ((__int64 (__usercall *)@<rax>(CCertRequest *@<rcx>, int@<edx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, const unsigned __int16 **))CCertRequest::_OpenConnection)(
         this,
         0,
         a2,
         2u,
         &v15);
  v7 = v6;
  if ( v6 )
  {
    v8 = 27002633;
LABEL_13:
    v11 = v6;
    goto LABEL_14;
  }
  v16 = v5;
  v9 = (struct _CAPROP **)((char *)v5 + 280);
  v17 = (struct _CAPROP **)((char *)v5 + 280);
  if ( *((_QWORD *)v5 + 35) )
  {
    v13 = (const unsigned __int16 *)((char *)v5 + 288);
    goto LABEL_11;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v10 = _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))SeTranslator);
    v18 = v10;
    v13 = (const unsigned __int16 *)((char *)v5 + 288);
    v7 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, char *, __int64 *))(**((_QWORD **)v5 + 10) + 64LL))(
           *((_QWORD *)v5 + 10),
           v15,
           (char *)v5 + 288,
           &v21);
    _set_se_translator(v10);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &StructuredException `RTTI Type Descriptor', (const StructuredException **)&v19) )
    {
      __eh34_try_continuation(0, &StructuredException `RTTI Type Descriptor', &loc_18001009A);
      v13 = (const unsigned __int16 *)((char *)this + 288);
      v4 = a4;
      v7 = myHExceptionCodePrint(v19 + 77, 0, 0x709u, 0x1ABu);
      v5 = v16;
      v9 = v17;
    }
  }
  v15 = v13;
  if ( !v7 )
  {
    if ( __eh34_try(-1, 2) )
    {
      __eh34_scope_strut(2);
      v12 = _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))SeTranslator);
      v18 = v12;
      v7 = myCAPropInfoUnmarshal((const struct _CATRANSPROP *)pv, *(_DWORD *)v13, v21, v9);
      _set_se_translator(v12);
    }
    if ( __eh34_catch(2) )
    {
      if ( __eh34_catch_type(2, &StructuredException `RTTI Type Descriptor', (const StructuredException **)&v20) )
      {
        __eh34_try_continuation(2, &StructuredException `RTTI Type Descriptor', &loc_180010111);
        v4 = a4;
        v7 = myHExceptionCodePrint(v20 + 77, 0, 0x709u, 0x1C2u);
        v13 = v15;
        v5 = v16;
      }
    }
    if ( v7 )
    {
      v11 = v7;
      v8 = 29624073;
      goto LABEL_14;
    }
    v9 = (struct _CAPROP **)((char *)v5 + 280);
LABEL_11:
    v6 = myCAPropInfoLookup(*v9, *(_DWORD *)v13, a3, v4);
    v7 = v6;
    if ( !v6 )
      goto LABEL_15;
    v8 = 29886217;
    goto LABEL_13;
  }
  v11 = v7;
  v8 = 28116745;
LABEL_14:
  CSPrintErrorLineFile(v8, v11);
LABEL_15:
  if ( pv )
    CoTaskMemFree(pv);
  return v7;
}

```

## disassembly

```asm
0x18000ffc4  mov     rax, rsp
0x18000ffc7  mov     [rax+10h], rbx
0x18000ffcb  mov     [rax+20h], r9
0x18000ffcf  mov     [rax+18h], r8d
0x18000ffd3  mov     [rax+8], rcx
0x18000ffd7  push    rsi
0x18000ffd8  push    rdi
0x18000ffd9  push    r12
0x18000ffdb  push    r14
0x18000ffdd  push    r15
0x18000ffdf  sub     rsp, 80h
0x18000ffe6  mov     r12, r9
0x18000ffe9  mov     rsi, rcx
0x18000ffec  mov     qword ptr [rax-70h], 0
0x18000fff4  mov     qword ptr [rax-40h], 0
0x18000fffc  mov     qword ptr [rax-38h], 0
0x180010004  mov     qword ptr [r9], 0
0x18001000b  lea     rax, [rax-70h]
0x18001000f  mov     [rsp+0A8h+var_88], rax; unsigned __int16 **
0x180010014  mov     r9d, 2; unsigned int
0x18001001a  mov     r8, rdx; unsigned __int16 *
0x18001001d  xor     edx, edx; int
0x18001001f  call    ?_OpenConnection@CCertRequest@@AEAAJHPEBGKPEAPEBG@Z; CCertRequest::_OpenConnection(int,ushort const *,ulong,ushort const * *)
0x180010024  mov     edi, eax
0x180010026  test    eax, eax
0x180010028  jz      short loc_180010034
0x18001002a  mov     ecx, 19C0709h
0x18001002f  jmp     loc_180010166
0x180010034  mov     [rsp+0A8h+var_68], rsi
0x180010039  lea     r15, [rsi+118h]
0x180010040  mov     [rsp+0A8h+var_60], r15
0x180010045  cmp     qword ptr [r15], 0
0x180010049  jnz     loc_18001013D
0x18001004f  lea     rcx, ?SeTranslator@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTranslator(uint,_EXCEPTION_POINTERS *)
0x180010056  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18001005c  mov     rbx, rax
0x18001005f  mov     [rsp+0A8h+var_58], rax
0x180010064  mov     rcx, [rsi+50h]
0x180010068  lea     r14, [rsi+120h]
0x18001006f  mov     rax, [rcx]
0x180010072  lea     r9, [rsp+0A8h+var_40]
0x180010077  mov     r8, r14
0x18001007a  mov     rdx, [rsp+0A8h+var_70]
0x18001007f  mov     rax, [rax+40h]
0x180010083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010088  mov     edi, eax
0x18001008a  mov     [rsp+0A8h+var_78], eax
0x18001008e  mov     rcx, rbx
0x180010091  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x180010097  nop
0x180010098  jmp     short loc_1800100BF
0x18001009a  mov     r14, [rsp+0A8h+arg_0]
0x1800100a2  add     r14, 120h
0x1800100a9  mov     r12, [rsp+0A8h+arg_18]
0x1800100b1  mov     edi, [rsp+0A8h+var_78]
0x1800100b5  mov     rsi, [rsp+0A8h+var_68]
0x1800100ba  mov     r15, [rsp+0A8h+var_60]
0x1800100bf  mov     [rsp+0A8h+var_70], r14
0x1800100c4  test    edi, edi
0x1800100c6  jz      short loc_1800100D4
0x1800100c8  mov     edx, edi
0x1800100ca  mov     ecx, 1AD0709h
0x1800100cf  jmp     loc_180010168
0x1800100d4  lea     rcx, ?SeTranslator@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTranslator(uint,_EXCEPTION_POINTERS *)
0x1800100db  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x1800100e1  mov     rbx, rax
0x1800100e4  mov     [rsp+0A8h+var_58], rax
0x1800100e9  mov     r9, r15
0x1800100ec  mov     r8d, dword ptr [rsp+0A8h+var_40]
0x1800100f1  mov     edx, [r14]
0x1800100f4  mov     rcx, [rsp+0A8h+pv]
0x1800100f9  call    cs:__imp_?myCAPropInfoUnmarshal@@YAJPEBU_CATRANSPROP@@JKPEAPEAU_CAPROP@@@Z; myCAPropInfoUnmarshal(_CATRANSPROP const *,long,ulong,_CAPROP * *)
0x1800100ff  mov     edi, eax
0x180010101  mov     [rsp+0A8h+var_78], eax
0x180010105  mov     rcx, rbx
0x180010108  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x18001010e  nop
0x18001010f  jmp     short loc_180010127
0x180010111  mov     r12, [rsp+0A8h+arg_18]
0x180010119  mov     edi, [rsp+0A8h+var_78]
0x18001011d  mov     r14, [rsp+0A8h+var_70]
0x180010122  mov     rsi, [rsp+0A8h+var_68]
0x180010127  test    edi, edi
0x180010129  jz      short loc_180010134
0x18001012b  mov     edx, edi
0x18001012d  mov     ecx, 1C40709h
0x180010132  jmp     short loc_180010168
0x180010134  lea     r15, [rsi+118h]
0x18001013b  jmp     short loc_180010144
0x18001013d  lea     r14, [rsi+120h]
0x180010144  mov     r9, r12
0x180010147  mov     r8d, [rsp+0A8h+arg_10]
0x18001014f  mov     edx, [r14]
0x180010152  mov     rcx, [r15]
0x180010155  call    cs:__imp_?myCAPropInfoLookup@@YAJPEBU_CAPROP@@JJPEAPEBU1@@Z; myCAPropInfoLookup(_CAPROP const *,long,long,_CAPROP const * *)
0x18001015b  mov     edi, eax
0x18001015d  test    eax, eax
0x18001015f  jz      short loc_18001016E
0x180010161  mov     ecx, 1C80709h
0x180010166  mov     edx, eax
0x180010168  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001016e  mov     rcx, [rsp+0A8h+pv]; pv
0x180010173  test    rcx, rcx
0x180010176  jz      short loc_18001017E
0x180010178  call    cs:__imp_CoTaskMemFree
0x18001017e  mov     eax, edi
0x180010180  mov     rbx, [rsp+0A8h+arg_8]
0x180010188  add     rsp, 80h
0x18001018f  pop     r15
0x180010191  pop     r14
0x180010193  pop     r12
0x180010195  pop     rdi
0x180010196  pop     rsi
0x180010197  retn
```
