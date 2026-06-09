# IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_STORE_SET_DEPLOYMENT_METADATA const *,Windows::Isolation::Rtl::_COMPONENT_STORE_OPERATION_ *)

- ea: `0x180032214`
- end: `0x1800324f4`
- name: `?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_STORE_SET_DEPLOYMENT_METADATA@@PEAU_COMPONENT_STORE_OPERATION_@Rtl@Isolation@Windows@@@Z`
- size: `736`
- prototype: `__int64 __fastcall(IsolationImplementation::Com *__hidden this, struct _RTL_ALLOCATION_LIST *, const struct _STORE_SET_DEPLOYMENT_METADATA *, struct Windows::Isolation::Rtl::_COMPONENT_STORE_OPERATION_ *)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800af644`

## callees

- `0x180012acc`
- `0x180012b38`
- `0x1800187f0`
- `0x180018940`
- `0x180018a34`
- `0x180018acc`
- `0x18002dde4`
- `0x18002decc`
- `0x180030508`
- `0x180030ab8`
- `0x180031b3c`
- `0x180032214`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180032499`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800324af`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180032499`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800324af`

## string_xrefs

- `0x180032239`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`
- `0x180032364`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`
- `0x1800323cf`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`
- `0x1800324be`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::ConvertIn(
        IsolationImplementation::Com *this,
        struct _RTL_ALLOCATION_LIST *a2,
        const struct _STORE_SET_DEPLOYMENT_METADATA *a3,
        struct Windows::Isolation::Rtl::_COMPONENT_STORE_OPERATION_ *a4)
{
  unsigned int v6; // ebx
  char *v7; // rcx
  IsolationImplementation::Com **v8; // rsi
  struct _RTL_ALLOCATION_LIST **v9; // r15
  _QWORD *v10; // r9
  __int64 *v11; // r14
  _QWORD *v12; // r13
  int AllocationListArray; // ebx
  struct Windows::Isolation::Rtl::_DEFINITION_APPID *v14; // r8
  __int64 v15; // rdi
  struct IDefinitionAppId *v16; // rdx
  int v17; // eax
  const struct Windows::Isolation::Rtl::_COMPONENT_STORE_REFERENCE_ **v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rsi
  __int64 v23; // r15
  __int64 v24; // r8
  int v25; // edx
  unsigned int v27; // [rsp+20h] [rbp-30h]
  const char *v28; // [rsp+30h] [rbp-20h] BYREF
  int v29; // [rsp+38h] [rbp-18h]
  unsigned int v30; // [rsp+40h] [rbp-10h]
  __int64 v32; // [rsp+98h] [rbp+48h] BYREF

  v30 = -2147023537;
  v28 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp";
  if ( a2 )
  {
    v7 = (char *)a2 + *(unsigned int *)a2;
    if ( (char *)a2 + 4 > v7 )
    {
      v29 = 608;
LABEL_31:
      Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v28);
      return v30;
    }
    v8 = (IsolationImplementation::Com **)((char *)a2 + 8);
    if ( (char *)a2 + 8 > v7 )
    {
      v29 = 609;
      goto LABEL_31;
    }
    v9 = (struct _RTL_ALLOCATION_LIST **)((char *)a2 + 16);
    if ( (char *)a2 + 16 > v7 )
    {
      v29 = 610;
      goto LABEL_31;
    }
    v10 = (_QWORD *)((char *)a2 + 24);
    if ( (char *)a2 + 24 > v7 )
    {
      v29 = 611;
      goto LABEL_31;
    }
    if ( (char *)a2 + 32 > v7 )
    {
      v29 = 612;
      goto LABEL_31;
    }
    v11 = (__int64 *)((char *)a2 + 40);
    if ( (char *)a2 + 40 > v7 )
    {
      v29 = 613;
      goto LABEL_31;
    }
    v12 = (_QWORD *)((char *)a2 + 48);
    if ( (char *)a2 + 48 > v7 )
    {
      v29 = 614;
      goto LABEL_31;
    }
    if ( (char *)a2 + 56 > v7 )
    {
      v29 = 615;
      goto LABEL_31;
    }
    if ( *((_DWORD *)a2 + 1) )
    {
      v29 = 616;
      goto LABEL_31;
    }
    if ( !*v8 )
    {
      v29 = 617;
      goto LABEL_3;
    }
    if ( *v10 && !*((_QWORD *)a2 + 4) )
    {
      v29 = 618;
      goto LABEL_31;
    }
    if ( *v11 && !*v12 )
    {
      v29 = 619;
      goto LABEL_31;
    }
    if ( *v10 )
    {
      v6 = -2147467263;
      Windows::ErrorHandling::COM::ReportErrorOrigination(
        (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp",
        (const char *)0x271,
        -2147467263,
        (int)v10);
      return v6;
    }
    v32 = 0;
    AllocationListArray = RtlAllocateAllocationListMemory(
                            this,
                            40,
                            Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_SET_DEPLOYMENT_METADATA_>,
                            &v32);
    if ( AllocationListArray < 0 )
    {
      if ( AllocationListArray == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      v24 = 630;
    }
    else
    {
      v15 = v32;
      v16 = (struct IDefinitionAppId *)(v32 + 8);
      *(_QWORD *)(v32 + 8) = 0;
      *(_QWORD *)v15 = 40;
      v17 = IsolationImplementation::Com::ConvertIn(*v8, v16, v14);
      v6 = v17;
      if ( v17 < 0 )
      {
        v19 = 635;
LABEL_37:
        Windows::ErrorHandling::COM::ReportErrorPropagation(
          (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp",
          (const char *)v19,
          v17,
          (int)v18);
        return v6;
      }
      v17 = IsolationImplementation::Com::ConvertIn(
              this,
              *v9,
              (const struct _STORE_ASSEMBLY_INSTALLATION_REFERENCE *)(v15 + 16),
              v18);
      v6 = v17;
      if ( v17 < 0 )
      {
        v19 = 636;
        goto LABEL_37;
      }
      v20 = *v11;
      if ( !*v11 )
      {
LABEL_46:
        *(_DWORD *)a3 = 3;
        v6 = 0;
        *((_QWORD *)a3 + 1) = v15;
        return v6;
      }
      v32 = 0;
      AllocationListArray = RtlAllocateAllocationListArray(
                              (_DWORD)this,
                              v20,
                              64,
                              (unsigned int)Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>,
                              (__int64)&v32);
      if ( AllocationListArray >= 0 )
      {
        v21 = *v11;
        v22 = 0;
        v23 = v32;
        if ( *v11 )
        {
          while ( 1 )
          {
            v17 = IsolationImplementation::Com::ConvertIn(
                    (IsolationImplementation::Com *)(5 * v22),
                    (struct _RTL_ALLOCATION_LIST *)(*v12 + 40 * v22),
                    (const struct _STORE_SET_DEPLOYMENT_METADATA_PROPERTY *)(v23 + (v22 << 6)),
                    (struct Windows::Isolation::Rtl::_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_ *)v18);
            v6 = v17;
            if ( v17 < 0 )
              break;
            v21 = *v11;
            if ( ++v22 == *v11 )
              goto LABEL_45;
          }
          v19 = 648;
          goto LABEL_37;
        }
LABEL_45:
        *(_QWORD *)(v15 + 24) = v21;
        *(_QWORD *)(v15 + 32) = v23;
        goto LABEL_46;
      }
      if ( AllocationListArray == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      v24 = 645;
    }
    Windows::ErrorHandling::COM::ReportError(
      (Windows::ErrorHandling::COM *)"Status propagated",
      "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp",
      (const char *)v24,
      AllocationListArray,
      v27);
    return (unsigned int)Windows::ErrorHandling::COM::ConvertNtStatusToHResult(
                           (Windows::ErrorHandling::COM *)(unsigned int)AllocationListArray,
                           v25);
  }
  v29 = 607;
LABEL_3:
  Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v28);
  return v30;
}

```

## disassembly

```asm
0x180032214  mov     [rsp-38h+arg_10], rbx
0x180032219  mov     [rsp-38h+arg_0], rcx
0x18003221e  push    rbp
0x18003221f  push    rsi
0x180032220  push    rdi
0x180032221  push    r12
0x180032223  push    r13
0x180032225  push    r14
0x180032227  push    r15
0x180032229  mov     rbp, rsp
0x18003222c  sub     rsp, 50h
0x180032230  xor     edi, edi
0x180032232  mov     [rbp+var_10], 8007054Fh
0x180032239  lea     rax, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180032240  mov     r12, r8
0x180032243  mov     [rbp+var_20], rax
0x180032247  mov     r11, rcx
0x18003224a  test    rdx, rdx
0x18003224d  jnz     short loc_180032267
0x18003224f  mov     [rbp+var_18], 25Fh
0x180032256  lea     rcx, [rbp+var_20]
0x18003225a  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x18003225f  mov     ebx, [rbp+var_10]
0x180032262  jmp     loc_1800324DA
0x180032267  mov     ecx, [rdx]
0x180032269  lea     r8, [rdx+4]
0x18003226d  add     rcx, rdx
0x180032270  cmp     r8, rcx
0x180032273  jbe     short loc_180032281
0x180032275  mov     [rbp+var_18], 260h
0x18003227c  jmp     loc_18003234C
0x180032281  lea     rsi, [rdx+8]
0x180032285  cmp     rsi, rcx
0x180032288  jbe     short loc_180032296
0x18003228a  mov     [rbp+var_18], 261h
0x180032291  jmp     loc_18003234C
0x180032296  lea     r15, [rdx+10h]
0x18003229a  cmp     r15, rcx
0x18003229d  jbe     short loc_1800322AB
0x18003229f  mov     [rbp+var_18], 262h
0x1800322a6  jmp     loc_18003234C
0x1800322ab  lea     r9, [rdx+18h]; int
0x1800322af  cmp     r9, rcx
0x1800322b2  jbe     short loc_1800322C0
0x1800322b4  mov     [rbp+var_18], 263h
0x1800322bb  jmp     loc_18003234C
0x1800322c0  lea     r10, [rdx+20h]
0x1800322c4  cmp     r10, rcx
0x1800322c7  jbe     short loc_1800322D2
0x1800322c9  mov     [rbp+var_18], 264h
0x1800322d0  jmp     short loc_18003234C
0x1800322d2  lea     r14, [rdx+28h]
0x1800322d6  cmp     r14, rcx
0x1800322d9  jbe     short loc_1800322E4
0x1800322db  mov     [rbp+var_18], 265h
0x1800322e2  jmp     short loc_18003234C
0x1800322e4  lea     r13, [rdx+30h]
0x1800322e8  cmp     r13, rcx
0x1800322eb  jbe     short loc_1800322F6
0x1800322ed  mov     [rbp+var_18], 266h
0x1800322f4  jmp     short loc_18003234C
0x1800322f6  lea     rax, [rdx+38h]
0x1800322fa  cmp     rax, rcx
0x1800322fd  jbe     short loc_180032308
0x1800322ff  mov     [rbp+var_18], 267h
0x180032306  jmp     short loc_18003234C
0x180032308  cmp     [r8], edi
0x18003230b  jz      short loc_180032316
0x18003230d  mov     [rbp+var_18], 268h
0x180032314  jmp     short loc_18003234C
0x180032316  cmp     [rsi], rdi
0x180032319  jnz     short loc_180032327
0x18003231b  mov     [rbp+var_18], 269h
0x180032322  jmp     loc_180032256
0x180032327  cmp     [r9], rdi
0x18003232a  jz      short loc_18003233A
0x18003232c  cmp     [r10], rdi
0x18003232f  jnz     short loc_18003233A
0x180032331  mov     [rbp+var_18], 26Ah
0x180032338  jmp     short loc_18003234C
0x18003233a  cmp     [r14], rdi
0x18003233d  jz      short loc_18003235A
0x18003233f  cmp     [r13+0], rdi
0x180032343  jnz     short loc_18003235A
0x180032345  mov     [rbp+var_18], 26Bh
0x18003234c  lea     rcx, [rbp+var_20]
0x180032350  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x180032355  jmp     loc_18003225F
0x18003235a  cmp     [r9], rdi
0x18003235d  jz      short loc_18003237D
0x18003235f  mov     ebx, 80004001h
0x180032364  lea     rcx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18003236b  mov     r8d, ebx; int
0x18003236e  mov     edx, 271h; char *
0x180032373  call    ?ReportErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorOrigination(char const *,int,long)
0x180032378  jmp     loc_1800324DA
0x18003237d  lea     r9, [rbp+arg_8]
0x180032381  mov     [rbp+arg_8], rdi
0x180032385  lea     r8, ??$AllocationListObjectDestroyer@U_COMPONENT_STORE_SET_DEPLOYMENT_METADATA_@Rtl@Isolation@Windows@@@Rtl@Windows@@YAXPEAX@Z; Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_SET_DEPLOYMENT_METADATA_>(void *)
0x18003238c  mov     edx, 28h ; '('
0x180032391  mov     rcx, r11
0x180032394  call    RtlAllocateAllocationListMemory
0x180032399  mov     ebx, eax
0x18003239b  test    eax, eax
0x18003239d  js      loc_1800324A7
0x1800323a3  mov     rdi, [rbp+arg_8]
0x1800323a7  lea     rdx, [rdi+8]; struct IDefinitionAppId *
0x1800323ab  mov     qword ptr [rdx], 0
0x1800323b2  mov     qword ptr [rdi], 28h ; '('
0x1800323b9  mov     rcx, [rsi]; this
0x1800323bc  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAUIDefinitionAppId@@PEAU_DEFINITION_APPID@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(IDefinitionAppId *,Windows::Isolation::Rtl::_DEFINITION_APPID *)
0x1800323c1  mov     ebx, eax
0x1800323c3  test    eax, eax
0x1800323c5  jns     short loc_1800323E0
0x1800323c7  mov     edx, 27Bh; char *
0x1800323cc  mov     r8d, eax; int
0x1800323cf  lea     rcx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800323d6  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x1800323db  jmp     loc_1800324DA
0x1800323e0  mov     rsi, [rbp+arg_0]
0x1800323e4  lea     r8, [rdi+10h]; struct _STORE_ASSEMBLY_INSTALLATION_REFERENCE *
0x1800323e8  mov     rdx, [r15]; struct _RTL_ALLOCATION_LIST *
0x1800323eb  mov     rcx, rsi; this
0x1800323ee  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_STORE_ASSEMBLY_INSTALLATION_REFERENCE@@AEAPEBU_COMPONENT_STORE_REFERENCE_@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_STORE_ASSEMBLY_INSTALLATION_REFERENCE const *,Windows::Isolation::Rtl::_COMPONENT_STORE_REFERENCE_ const * &)
0x1800323f3  mov     ebx, eax
0x1800323f5  test    eax, eax
0x1800323f7  jns     short loc_180032400
0x1800323f9  mov     edx, 27Ch
0x1800323fe  jmp     short loc_1800323CC
0x180032400  mov     rdx, [r14]
0x180032403  test    rdx, rdx
0x180032406  jz      short loc_180032476
0x180032408  lea     rax, [rbp+arg_8]
0x18003240c  mov     [rbp+arg_8], 0
0x180032414  lea     r9, ??$AllocationListObjectDestroyer@U_COMPONENT_STORE_LOCK_APPLICATION_PATH_@Rtl@Isolation@Windows@@@Rtl@Windows@@YAXPEAX@Z; Windows::Rtl::AllocationListObjectDestroyer<Windows::Isolation::Rtl::_COMPONENT_STORE_LOCK_APPLICATION_PATH_>(void *)
0x18003241b  mov     qword ptr [rsp+50h+var_30], rax
0x180032420  mov     r8d, 40h ; '@'
0x180032426  mov     rcx, rsi
0x180032429  call    RtlAllocateAllocationListArray
0x18003242e  mov     ebx, eax
0x180032430  test    eax, eax
0x180032432  js      short loc_180032491
0x180032434  mov     rax, [r14]
0x180032437  xor     esi, esi
0x180032439  mov     r15, [rbp+arg_8]
0x18003243d  test    rax, rax
0x180032440  jz      short loc_18003246E
0x180032442  mov     rax, [r13+0]
0x180032446  lea     rcx, [rsi+rsi*4]; this
0x18003244a  mov     r8, rsi
0x18003244d  shl     r8, 6
0x180032451  add     r8, r15; struct _STORE_SET_DEPLOYMENT_METADATA_PROPERTY *
0x180032454  lea     rdx, [rax+rcx*8]; struct _RTL_ALLOCATION_LIST *
0x180032458  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@AEBU_STORE_SET_DEPLOYMENT_METADATA_PROPERTY@@AEAU_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_STORE_SET_DEPLOYMENT_METADATA_PROPERTY const &,Windows::Isolation::Rtl::_COMPONENT_STORE_DEPLOYMENT_METADATA_PROPERTY_ &)
0x18003245d  mov     ebx, eax
0x18003245f  test    eax, eax
0x180032461  js      short loc_180032487
0x180032463  mov     rax, [r14]
0x180032466  inc     rsi
0x180032469  cmp     rsi, rax
0x18003246c  jnz     short loc_180032442
0x18003246e  mov     [rdi+18h], rax
0x180032472  mov     [rdi+20h], r15
0x180032476  mov     dword ptr [r12], 3
0x18003247e  xor     ebx, ebx
0x180032480  mov     [r12+8], rdi
0x180032485  jmp     short loc_1800324DA
0x180032487  mov     edx, 288h
0x18003248c  jmp     loc_1800323CC
0x180032491  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x180032497  jnz     short loc_18003249F
0x180032499  call    cs:__imp_DebugBreak
0x18003249f  mov     r8d, 285h
0x1800324a5  jmp     short loc_1800324BB
0x1800324a7  cmp     ebx, cs:g_NTSTATUS_to_break_on_propagate
0x1800324ad  jnz     short loc_1800324B5
0x1800324af  call    cs:__imp_DebugBreak
0x1800324b5  mov     r8d, 276h; char *
0x1800324bb  mov     r9d, ebx; int
0x1800324be  lea     rdx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800324c5  lea     rcx, aStatusPropagat; "Status propagated"
0x1800324cc  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x1800324d1  mov     ecx, ebx; this
0x1800324d3  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x1800324d8  mov     ebx, eax
0x1800324da  mov     eax, ebx
0x1800324dc  mov     rbx, [rsp+50h+arg_10]
0x1800324e4  add     rsp, 50h
0x1800324e8  pop     r15
0x1800324ea  pop     r14
0x1800324ec  pop     r13
0x1800324ee  pop     r12
0x1800324f0  pop     rdi
0x1800324f1  pop     rsi
0x1800324f2  pop     rbp
0x1800324f3  retn
```
