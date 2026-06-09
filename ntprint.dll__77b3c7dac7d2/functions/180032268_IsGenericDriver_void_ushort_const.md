# IsGenericDriver(void *,ushort const *)

- ea: `0x180032268`
- end: `0x1800323bd`
- name: `?IsGenericDriver@@YAHPEAXPEBG@Z`
- size: `341`
- prototype: `__int64 __fastcall(HINF InfHandle, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180033f80`

## callees

- `0x18000d624`
- `0x180032268`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003232b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003232b`
- `SETUPAPI!pSetupGetField` at `0x1800322cf`
- `SETUPAPI!pSetupGetField` at `0x18003231b`
- `SETUPAPI!pSetupGetField` at `0x1800322cf`
- `SETUPAPI!pSetupGetField` at `0x18003231b`
- `SETUPAPI!SetupFindNextMatchLineW` at `0x180032395`
- `SETUPAPI!SetupFindNextMatchLineW` at `0x180032395`
- `SETUPAPI!SetupFindNextLine` at `0x180032372`
- `SETUPAPI!SetupFindNextLine` at `0x180032372`
- `SETUPAPI!SetupGetFieldCount` at `0x1800322a7`
- `SETUPAPI!SetupGetFieldCount` at `0x1800322a7`
- `SETUPAPI!SetupFindFirstLineW` at `0x180032298`
- `SETUPAPI!SetupFindFirstLineW` at `0x1800322ee`
- `SETUPAPI!SetupFindFirstLineW` at `0x180032298`
- `SETUPAPI!SetupFindFirstLineW` at `0x1800322ee`
- `SETUPAPI!SetupGetIntField` at `0x180032343`
- `SETUPAPI!SetupGetIntField` at `0x180032343`

## string_xrefs

- `0x180032351`: `GenericDriverInstalled property found, value=%d`
- `0x180032324`: `GenericDriverInstalled`

## pseudocode

```c
BOOL __fastcall IsGenericDriver(HINF InfHandle, const unsigned __int16 *a2)
{
  BOOL result; // eax
  unsigned int v4; // ebx
  DWORD FieldCount; // esi
  const WCHAR *Field; // rax
  const WCHAR *v7; // rdi
  __int64 v8; // rax
  struct _INFCONTEXT ContextIn; // [rsp+20h] [rbp-30h] BYREF
  struct _INFCONTEXT Context; // [rsp+38h] [rbp-18h] BYREF
  int IntegerValue; // [rsp+80h] [rbp+30h] BYREF

  memset(&Context, 0, sizeof(Context));
  for ( result = SetupFindFirstLineW(InfHandle, a2, L"AddProperty", &Context);
        result;
        result = SetupFindNextMatchLineW(&Context, L"AddProperty", &Context) )
  {
    v4 = 1;
    FieldCount = SetupGetFieldCount(&Context);
    if ( FieldCount )
    {
      while ( 1 )
      {
        memset(&ContextIn, 0, sizeof(ContextIn));
        Field = (const WCHAR *)pSetupGetField(&Context, v4);
        v7 = Field;
        if ( Field )
        {
          if ( SetupFindFirstLineW(InfHandle, Field, 0, &ContextIn) )
            break;
        }
LABEL_10:
        if ( ++v4 > FieldCount )
          goto LABEL_11;
      }
      ClassInstallerTelemetry::WriteDbgTraceInfo("IsGenericDriver", L"AddProperty section found: [%ws]", v7);
      while ( 1 )
      {
        v8 = pSetupGetField(&ContextIn, 1);
        if ( !(unsigned int)_o__wcsicmp(v8, L"GenericDriverInstalled") )
        {
          IntegerValue = 0;
          if ( SetupGetIntField(&ContextIn, 5u, &IntegerValue) )
          {
            ClassInstallerTelemetry::WriteDbgTraceInfo(
              "IsGenericDriver",
              L"GenericDriverInstalled property found, value=%d",
              (unsigned int)IntegerValue);
            if ( IntegerValue )
              return 1;
          }
        }
        if ( !SetupFindNextLine(&ContextIn, &ContextIn) )
          goto LABEL_10;
      }
    }
LABEL_11:
    ;
  }
  return result;
}

```

## disassembly

```asm
0x180032268  mov     [rsp-18h+arg_0], rbx
0x18003226d  mov     [rsp-18h+arg_8], rsi
0x180032272  push    rbp
0x180032273  push    rdi
0x180032274  push    r14
0x180032276  mov     rbp, rsp
0x180032279  sub     rsp, 50h
0x18003227d  xorps   xmm0, xmm0
0x180032280  lea     r9, [rbp+Context]; Context
0x180032284  xor     eax, eax
0x180032286  lea     r8, aAddproperty; "AddProperty"
0x18003228d  movups  xmmword ptr [rbp+Context.Inf], xmm0
0x180032291  mov     qword ptr [rbp+Context.Section], rax
0x180032295  mov     r14, rcx
0x180032298  call    cs:__imp_SetupFindFirstLineW
0x18003229e  jmp     loc_18003239B
0x1800322a3  lea     rcx, [rbp+Context]; Context
0x1800322a7  call    cs:__imp_SetupGetFieldCount
0x1800322ad  mov     ebx, 1
0x1800322b2  mov     esi, eax
0x1800322b4  cmp     eax, ebx
0x1800322b6  jb      loc_180032386
0x1800322bc  xorps   xmm0, xmm0
0x1800322bf  lea     rcx, [rbp+Context]
0x1800322c3  xor     eax, eax
0x1800322c5  mov     edx, ebx
0x1800322c7  movups  xmmword ptr [rbp+ContextIn.Inf], xmm0
0x1800322cb  mov     qword ptr [rbp+ContextIn.Section], rax
0x1800322cf  call    cs:__imp_pSetupGetField
0x1800322d5  mov     rdi, rax
0x1800322d8  test    rax, rax
0x1800322db  jz      loc_18003237C
0x1800322e1  lea     r9, [rbp+ContextIn]; Context
0x1800322e5  xor     r8d, r8d; Key
0x1800322e8  mov     rdx, rax; Section
0x1800322eb  mov     rcx, r14; InfHandle
0x1800322ee  call    cs:__imp_SetupFindFirstLineW
0x1800322f4  test    eax, eax
0x1800322f6  jz      loc_18003237C
0x1800322fc  mov     r8, rdi
0x1800322ff  lea     rdx, aAddpropertySec; "AddProperty section found: [%ws]"
0x180032306  lea     rcx, aIsgenericdrive; "IsGenericDriver"
0x18003230d  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180032312  mov     edx, 1
0x180032317  lea     rcx, [rbp+ContextIn]
0x18003231b  call    cs:__imp_pSetupGetField
0x180032321  mov     rcx, rax
0x180032324  lea     rdx, aGenericdriveri_0; "GenericDriverInstalled"
0x18003232b  call    cs:__imp__o__wcsicmp
0x180032331  test    eax, eax
0x180032333  jnz     short loc_18003236A
0x180032335  lea     r8, [rbp+IntegerValue]; IntegerValue
0x180032339  mov     [rbp+IntegerValue], eax
0x18003233c  lea     edx, [rax+5]; FieldIndex
0x18003233f  lea     rcx, [rbp+ContextIn]; Context
0x180032343  call    cs:__imp_SetupGetIntField
0x180032349  test    eax, eax
0x18003234b  jz      short loc_18003236A
0x18003234d  mov     r8d, [rbp+IntegerValue]
0x180032351  lea     rdx, aGenericdriveri; "GenericDriverInstalled property found, "...
0x180032358  lea     rcx, aIsgenericdrive; "IsGenericDriver"
0x18003235f  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180032364  cmp     [rbp+IntegerValue], 0
0x180032368  jnz     short loc_1800323B6
0x18003236a  lea     rdx, [rbp+ContextIn]; ContextOut
0x18003236e  lea     rcx, [rbp+ContextIn]; ContextIn
0x180032372  call    cs:__imp_SetupFindNextLine
0x180032378  test    eax, eax
0x18003237a  jnz     short loc_180032312
0x18003237c  inc     ebx
0x18003237e  cmp     ebx, esi
0x180032380  jbe     loc_1800322BC
0x180032386  lea     r8, [rbp+Context]; ContextOut
0x18003238a  lea     rdx, aAddproperty; "AddProperty"
0x180032391  lea     rcx, [rbp+Context]; ContextIn
0x180032395  call    cs:__imp_SetupFindNextMatchLineW
0x18003239b  test    eax, eax
0x18003239d  jnz     loc_1800322A3
0x1800323a3  mov     rbx, [rsp+50h+arg_0]
0x1800323a8  mov     rsi, [rsp+50h+arg_8]
0x1800323ad  add     rsp, 50h
0x1800323b1  pop     r14
0x1800323b3  pop     rdi
0x1800323b4  pop     rbp
0x1800323b5  retn
0x1800323b6  mov     eax, 1
0x1800323bb  jmp     short loc_1800323A3
```
