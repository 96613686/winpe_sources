# IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_CREATE_APP_CONTEXT_DATA_SOURCE const *,Windows::Isolation::Rtl::_CREATE_APPLICATION_CONTEXT_DATA_SOURCE * &)

- ea: `0x180031454`
- end: `0x1800316ad`
- name: `?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_CREATE_APP_CONTEXT_DATA_SOURCE@@AEAPEAU_CREATE_APPLICATION_CONTEXT_DATA_SOURCE@Rtl@Isolation@Windows@@@Z`
- size: `601`
- prototype: `__int64 __fastcall(IsolationImplementation::Com *__hidden this, struct _RTL_ALLOCATION_LIST *, const struct _CREATE_APP_CONTEXT_DATA_SOURCE *, struct Windows::Isolation::Rtl::_CREATE_APPLICATION_CONTEXT_DATA_SOURCE **)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180030b70`

## callees

- `0x180012acc`
- `0x180012b38`
- `0x1800187f0`
- `0x180018940`
- `0x180018acc`
- `0x18002decc`
- `0x180031454`
- `0x1800316b4`
- `0x180031800`
- `0x18003ef3c`
- `0x180042b98`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180031512`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800315ca`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180031641`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180031512`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800315ca`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180031641`

## string_xrefs

- `0x180031474`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`
- `0x18003151b`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`
- `0x180031614`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`
- `0x180031650`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\com\convertin.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Com::ConvertIn(
        IsolationImplementation::Com *this,
        struct _RTL_ALLOCATION_LIST **a2,
        const struct _CREATE_APP_CONTEXT_DATA_SOURCE *a3,
        struct Windows::Isolation::Rtl::_CREATE_APPLICATION_CONTEXT_DATA_SOURCE **a4)
{
  unsigned int v7; // ebx
  _DWORD *v8; // rsi
  struct _RTL_ALLOCATION_LIST **v9; // rcx
  int *v10; // r14
  int v11; // eax
  const struct Windows::Isolation::Rtl::_CREATE_APPLICATION_CONTEXT_DATA_SOURCE_APPLICATION_REFERENCE **v12; // r9
  unsigned int v13; // edi
  int v14; // edx
  Windows::ErrorHandling::COM *v15; // rcx
  _QWORD *v16; // rdi
  int v17; // ecx
  int v18; // ecx
  int v19; // eax
  __int64 v20; // rcx
  int v21; // r9d
  __int64 v22; // rdx
  int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // r8
  __int64 v26; // rcx
  int v27; // eax
  const char *v29; // [rsp+20h] [rbp-20h] BYREF
  int v30; // [rsp+28h] [rbp-18h]
  unsigned int v31; // [rsp+30h] [rbp-10h]
  _QWORD *v32; // [rsp+78h] [rbp+38h] BYREF

  v31 = -2147023537;
  v29 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp";
  v32 = 0;
  if ( a2 )
  {
    v8 = (_DWORD *)a2 + 1;
    v9 = (struct _RTL_ALLOCATION_LIST **)((char *)a2 + *(unsigned int *)a2);
    if ( (struct _RTL_ALLOCATION_LIST **)((char *)a2 + 4) > v9 )
    {
      v30 = 1143;
LABEL_40:
      Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(&v29);
      return v31;
    }
    v10 = (int *)(a2 + 1);
    if ( a2 + 1 > v9 )
    {
      v30 = 1144;
      goto LABEL_40;
    }
    if ( (struct _RTL_ALLOCATION_LIST **)((char *)a2 + 12) > v9 )
    {
      v30 = 1145;
      goto LABEL_40;
    }
    v11 = RtlAllocateAllocationListMemory(this, 24, 0, &v32);
    v13 = v11;
    if ( v11 < 0 )
    {
      if ( v11 == g_NTSTATUS_to_break_on_propagate )
        DebugBreak();
      Windows::ErrorHandling::COM::ReportError(
        (Windows::ErrorHandling::COM *)"Status propagated",
        "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp",
        (const char *)0x480,
        v13,
        (unsigned int)v29);
      v15 = (Windows::ErrorHandling::COM *)v13;
      return (unsigned int)Windows::ErrorHandling::COM::ConvertNtStatusToHResult(v15, v14);
    }
    v16 = v32;
    *v32 = 24;
    *((_DWORD *)v16 + 2) = 0;
    if ( *v8 )
    {
      v30 = 1158;
      goto LABEL_40;
    }
    v17 = *v10;
    if ( (unsigned int)(*v10 - 1) > 1 )
    {
      v30 = 1162;
      goto LABEL_40;
    }
    LOBYTE(v32) = 0;
    v18 = v17 - 1;
    if ( v18 )
    {
      if ( v18 == 1 )
      {
        v19 = IsolationImplementation::Com::ConvertIn(
                this,
                a2[2],
                (const struct _CREATE_APP_CONTEXT_DATA_SOURCE_APP_REFERENCE *)(v16 + 2),
                v12);
        v7 = v19;
        if ( v19 < 0 )
        {
          v22 = 1185;
LABEL_32:
          Windows::ErrorHandling::COM::ReportErrorPropagation(
            (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp",
            (const char *)v22,
            v19,
            v21);
          return v7;
        }
        v23 = RtlValidateReferenceAppIdContent(v20, *(_QWORD *)(v16[2] + 16LL), &v32);
        v24 = v23;
        if ( v23 < 0 )
        {
          if ( v23 == g_NTSTATUS_to_break_on_propagate )
            DebugBreak();
          v25 = 1188;
LABEL_37:
          Windows::ErrorHandling::COM::ReportError(
            (Windows::ErrorHandling::COM *)"Status propagated",
            "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\com\\convertin.cpp",
            (const char *)v25,
            v24,
            (unsigned int)v29);
          v15 = (Windows::ErrorHandling::COM *)v24;
          return (unsigned int)Windows::ErrorHandling::COM::ConvertNtStatusToHResult(v15, v14);
        }
        if ( !(_BYTE)v32 )
        {
          v30 = 1189;
          goto LABEL_40;
        }
        *((_DWORD *)v16 + 3) = 2;
      }
    }
    else
    {
      v19 = IsolationImplementation::Com::ConvertIn(
              this,
              a2[2],
              (const struct _CREATE_APP_CONTEXT_DATA_SOURCE_APP_DEFINITION *)(v16 + 2),
              v12);
      v7 = v19;
      if ( v19 < 0 )
      {
        v22 = 1171;
        goto LABEL_32;
      }
      v27 = RtlValidateDefinitionAppIdContent(v26, *(_QWORD *)(v16[2] + 16LL), &v32);
      v24 = v27;
      if ( v27 < 0 )
      {
        if ( v27 == g_NTSTATUS_to_break_on_propagate )
          DebugBreak();
        v25 = 1174;
        goto LABEL_37;
      }
      if ( !(_BYTE)v32 )
      {
        v30 = 1175;
        goto LABEL_40;
      }
      *((_DWORD *)v16 + 3) = 1;
    }
    *(_QWORD *)a3 = v16;
    return 0;
  }
  v30 = 1142;
  Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(&v29);
  return v31;
}

```

## disassembly

```asm
0x180031454  mov     [rsp-28h+arg_0], rbx
0x180031459  mov     [rsp-28h+arg_10], rsi
0x18003145e  push    rbp
0x18003145f  push    rdi
0x180031460  push    r12
0x180031462  push    r14
0x180031464  push    r15
0x180031466  mov     rbp, rsp
0x180031469  sub     rsp, 40h
0x18003146d  mov     [rbp+var_10], 8007054Fh
0x180031474  lea     rax, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18003147b  mov     [rbp+var_20], rax
0x18003147f  mov     r12, r8
0x180031482  mov     [rbp+arg_8], 0
0x18003148a  mov     rbx, rdx
0x18003148d  mov     r15, rcx
0x180031490  test    rdx, rdx
0x180031493  jnz     short loc_1800314AD
0x180031495  lea     rcx, [rbp+var_20]
0x180031499  mov     [rbp+var_18], 476h
0x1800314a0  call    ?SetInvalidParameter_NullPointer@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter_NullPointer(void)
0x1800314a5  mov     ebx, [rbp+var_10]
0x1800314a8  jmp     loc_180031692
0x1800314ad  mov     ecx, [rdx]
0x1800314af  lea     rsi, [rdx+4]
0x1800314b3  add     rcx, rbx
0x1800314b6  cmp     rsi, rcx
0x1800314b9  jbe     short loc_1800314C7
0x1800314bb  mov     [rbp+var_18], 477h
0x1800314c2  jmp     loc_180031677
0x1800314c7  lea     r14, [rdx+8]
0x1800314cb  cmp     r14, rcx
0x1800314ce  jbe     short loc_1800314DC
0x1800314d0  mov     [rbp+var_18], 478h
0x1800314d7  jmp     loc_180031677
0x1800314dc  lea     rax, [rdx+0Ch]
0x1800314e0  cmp     rax, rcx
0x1800314e3  jbe     short loc_1800314F1
0x1800314e5  mov     [rbp+var_18], 479h
0x1800314ec  jmp     loc_180031677
0x1800314f1  xor     r8d, r8d
0x1800314f4  lea     r9, [rbp+arg_8]
0x1800314f8  mov     rcx, r15
0x1800314fb  lea     edx, [r8+18h]
0x1800314ff  call    RtlAllocateAllocationListMemory
0x180031504  mov     edi, eax
0x180031506  test    eax, eax
0x180031508  jns     short loc_180031542
0x18003150a  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x180031510  jnz     short loc_180031518
0x180031512  call    cs:__imp_DebugBreak
0x180031518  mov     r9d, edi; int
0x18003151b  lea     rdx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180031522  mov     r8d, 480h; char *
0x180031528  lea     rcx, aStatusPropagat; "Status propagated"
0x18003152f  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180031534  mov     ecx, edi; this
0x180031536  call    ?ConvertNtStatusToHResult@COM@ErrorHandling@Windows@@YAJJ@Z; Windows::ErrorHandling::COM::ConvertNtStatusToHResult(long)
0x18003153b  mov     ebx, eax
0x18003153d  jmp     loc_180031692
0x180031542  mov     rdi, [rbp+arg_8]
0x180031546  mov     qword ptr [rdi], 18h
0x18003154d  mov     dword ptr [rdi+8], 0
0x180031554  cmp     dword ptr [rsi], 0
0x180031557  jz      short loc_180031565
0x180031559  mov     [rbp+var_18], 486h
0x180031560  jmp     loc_180031677
0x180031565  mov     ecx, [r14]
0x180031568  lea     eax, [rcx-1]
0x18003156b  cmp     eax, 1
0x18003156e  jbe     short loc_18003157C
0x180031570  mov     [rbp+var_18], 48Ah
0x180031577  jmp     loc_180031677
0x18003157c  mov     byte ptr [rbp+arg_8], 0
0x180031580  sub     ecx, 1
0x180031583  jz      short loc_1800315F6
0x180031585  cmp     ecx, 1
0x180031588  jnz     loc_18003168C
0x18003158e  mov     rdx, [rbx+10h]; struct _RTL_ALLOCATION_LIST *
0x180031592  lea     r8, [rdi+10h]; struct _CREATE_APP_CONTEXT_DATA_SOURCE_APP_REFERENCE *
0x180031596  mov     rcx, r15; this
0x180031599  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_CREATE_APP_CONTEXT_DATA_SOURCE_APP_REFERENCE@@AEAPEBU_CREATE_APPLICATION_CONTEXT_DATA_SOURCE_APPLICATION_REFERENCE@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_CREATE_APP_CONTEXT_DATA_SOURCE_APP_REFERENCE const *,Windows::Isolation::Rtl::_CREATE_APPLICATION_CONTEXT_DATA_SOURCE_APPLICATION_REFERENCE const * &)
0x18003159e  mov     ebx, eax
0x1800315a0  test    eax, eax
0x1800315a2  jns     short loc_1800315AB
0x1800315a4  mov     edx, 4A1h
0x1800315a9  jmp     short loc_180031611
0x1800315ab  mov     rdx, [rdi+10h]
0x1800315af  lea     r8, [rbp+arg_8]
0x1800315b3  mov     rdx, [rdx+10h]
0x1800315b7  call    RtlValidateReferenceAppIdContent
0x1800315bc  mov     ebx, eax
0x1800315be  test    eax, eax
0x1800315c0  jns     short loc_1800315D8
0x1800315c2  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x1800315c8  jnz     short loc_1800315D0
0x1800315ca  call    cs:__imp_DebugBreak
0x1800315d0  mov     r8d, 4A4h
0x1800315d6  jmp     short loc_18003164D
0x1800315d8  cmp     byte ptr [rbp+arg_8], 0
0x1800315dc  jnz     short loc_1800315EA
0x1800315de  mov     [rbp+var_18], 4A5h
0x1800315e5  jmp     loc_180031677
0x1800315ea  mov     dword ptr [rdi+0Ch], 2
0x1800315f1  jmp     loc_18003168C
0x1800315f6  mov     rdx, [rbx+10h]; struct _RTL_ALLOCATION_LIST *
0x1800315fa  lea     r8, [rdi+10h]; struct _CREATE_APP_CONTEXT_DATA_SOURCE_APP_DEFINITION *
0x1800315fe  mov     rcx, r15; this
0x180031601  call    ?ConvertIn@Com@IsolationImplementation@@YAJPEAU_RTL_ALLOCATION_LIST@@PEBU_CREATE_APP_CONTEXT_DATA_SOURCE_APP_DEFINITION@@AEAPEBU_CREATE_APPLICATION_CONTEXT_DATA_SOURCE_APPLICATION_DEFINITION@Rtl@Isolation@Windows@@@Z; IsolationImplementation::Com::ConvertIn(_RTL_ALLOCATION_LIST *,_CREATE_APP_CONTEXT_DATA_SOURCE_APP_DEFINITION const *,Windows::Isolation::Rtl::_CREATE_APPLICATION_CONTEXT_DATA_SOURCE_APPLICATION_DEFINITION const * &)
0x180031606  mov     ebx, eax
0x180031608  test    eax, eax
0x18003160a  jns     short loc_180031622
0x18003160c  mov     edx, 493h; char *
0x180031611  mov     r8d, eax; int
0x180031614  lea     rcx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x18003161b  call    ?ReportErrorPropagation@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportErrorPropagation(char const *,int,long)
0x180031620  jmp     short loc_180031692
0x180031622  mov     rdx, [rdi+10h]
0x180031626  lea     r8, [rbp+arg_8]
0x18003162a  mov     rdx, [rdx+10h]
0x18003162e  call    RtlValidateDefinitionAppIdContent
0x180031633  mov     ebx, eax
0x180031635  test    eax, eax
0x180031637  jns     short loc_18003166A
0x180031639  cmp     eax, cs:g_NTSTATUS_to_break_on_propagate
0x18003163f  jnz     short loc_180031647
0x180031641  call    cs:__imp_DebugBreak
0x180031647  mov     r8d, 496h; char *
0x18003164d  mov     r9d, ebx; int
0x180031650  lea     rdx, aOnecoreComNetf_74; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180031657  lea     rcx, aStatusPropagat; "Status propagated"
0x18003165e  call    ?ReportError@COM@ErrorHandling@Windows@@YAXPEBD0HK@Z; Windows::ErrorHandling::COM::ReportError(char const *,char const *,int,ulong)
0x180031663  mov     ecx, ebx
0x180031665  jmp     loc_180031536
0x18003166a  cmp     byte ptr [rbp+arg_8], 0
0x18003166e  jnz     short loc_180031685
0x180031670  mov     [rbp+var_18], 497h
0x180031677  lea     rcx, [rbp+var_20]
0x18003167b  call    ?SetInvalidParameter@?$CBaseFrame@VCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@@COM@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame>::SetInvalidParameter(void)
0x180031680  jmp     loc_1800314A5
0x180031685  mov     dword ptr [rdi+0Ch], 1
0x18003168c  mov     [r12], rdi
0x180031690  xor     ebx, ebx
0x180031692  lea     r11, [rsp+40h+var_s0]
0x180031697  mov     eax, ebx
0x180031699  mov     rbx, [r11+30h]
0x18003169d  mov     rsi, [r11+40h]
0x1800316a1  mov     rsp, r11
0x1800316a4  pop     r15
0x1800316a6  pop     r14
0x1800316a8  pop     r12
0x1800316aa  pop     rdi
0x1800316ab  pop     rbp
0x1800316ac  retn
```
