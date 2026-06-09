# Js::JavascriptString::EntryLocaleCompare(Js::RecyclableObject *,Js::CallInfo,...)

- ea: `0x1802c0290`
- end: `0x1802c04d7`
- name: `?EntryLocaleCompare@JavascriptString@Js@@SAPEAXPEAVRecyclableObject@2@UCallInfo@2@ZZ`
- size: `583`
- prototype: `__int64(__int64, ...)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180036e50`
- `0x180037618`
- `0x1800392e8`
- `0x180064f20`
- `0x18007278c`
- `0x18007434c`
- `0x1800d1648`
- `0x180129440`
- `0x18015fe58`
- `0x1801ab0d0`
- `0x1802c0290`
- `0x1802da368`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1802c0488`
- `KERNEL32!CompareStringW` at `0x1802c0488`
- `KERNEL32!GetUserDefaultLCID` at `0x1802c0469`
- `KERNEL32!GetUserDefaultLCID` at `0x1802c0469`

## string_xrefs

- `0x1802c031d`: `String.prototype.localeCompare`
- `0x1802c034c`: `String.prototype.localeCompare`

## pseudocode

```c
__int64 Js::JavascriptString::EntryLocaleCompare(__int64 a1, ...)
{
  ThreadContext **v2; // r8
  struct Js::ScriptContext *v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rbx
  unsigned int v6; // r14d
  struct Js::JavascriptString **v7; // rsi
  int v8; // eax
  struct Js::EngineInterfaceObject *IntlObject_EngineInterface; // rax
  struct Js::JavascriptString *v10; // r9
  struct Js::JavascriptString *v11; // rdi
  __int64 v12; // r8
  const WCHAR *OriginalStringReference; // r12
  int v14; // r13d
  const WCHAR *lpString2; // rbp
  struct Js::JavascriptString *v16; // rdi
  __int64 v17; // r8
  const WCHAR *v18; // rax
  int cchCount2; // ebx
  _QWORD *v20; // rcx
  LCID UserDefaultLCID; // eax
  int v23; // eax
  unsigned __int64 v24; // [rsp+38h] [rbp-70h]
  __int64 v25; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int64 *v26; // [rsp+58h] [rbp-50h]
  __int64 v27; // [rsp+B8h] [rbp+10h] BYREF
  va_list va; // [rsp+B8h] [rbp+10h]
  va_list va1; // [rsp+C0h] [rbp+18h] BYREF

  va_start(va1, a1);
  va_start(va, a1);
  v27 = va_arg(va1, _QWORD);
  v2 = *(ThreadContext ***)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1072LL);
  ThreadContext::ProbeStack(v2[148], 0x450u, (struct Js::ScriptContext *)v2, 0);
  v25 = 0;
  Js::ArgumentReader::ArgumentReader((Js::ArgumentReader *)&v25, (struct Js::CallInfo *)va, (void **)va1);
  v4 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL);
  v5 = *(_QWORD *)(v4 + 1072);
  v6 = v25 & 0xFFFFFF;
  if ( (v25 & 0xFFFFFF) == 0 )
    Js::JavascriptError::ThrowTypeError(
      *(Js::JavascriptLibrary ***)(v4 + 1072),
      -2146823231,
      L"String.prototype.localeCompare");
  v7 = (struct Js::JavascriptString **)v26;
  if ( *(int *)(v5 + 2336) >= 3 )
  {
    LOBYTE(v8) = Js::JavascriptConversion::CheckObjectCoercible(*v26, v3);
    if ( !v8 )
      Js::JavascriptError::ThrowTypeError((Js::JavascriptLibrary **)v5, -2146823234, L"String.prototype.localeCompare");
  }
  IntlObject_EngineInterface = Js::JavascriptLibraryBase::GetIntlObject_EngineInterface(*(Js::JavascriptLibraryBase **)v5);
  if ( IntlObject_EngineInterface )
  {
    if ( v6 == 2 )
    {
      v10 = *v7;
      v24 = *(_QWORD *)(*(_QWORD *)v5 + 1056LL);
      v25 = (unsigned int)v27 & 0xFF000000 | 7LL;
      Js::EngineInterfaceObject::EntryIntl_CompareString(a1, v27 & 0xFF000000 | 7, v24, v10, v7[1], v24, v24, v24, v24);
    }
    else
    {
      v20 = (_QWORD *)*((_QWORD *)IntlObject_EngineInterface + 9);
      if ( v20 )
        return Js::JavascriptFunction::CallFunction(v20, &v25);
    }
  }
  v11 = *v7;
  if ( !Js::JavascriptString::Is((unsigned __int64)*v7) )
    v11 = Js::JavascriptConversion::ToString((unsigned __int64)v11, (char **)v5, v12);
  OriginalStringReference = (const WCHAR *)Js::JavascriptString::GetOriginalStringReference(v11);
  v14 = *((_DWORD *)v11 + 4);
  lpString2 = (const WCHAR *)Js::JavascriptString::GetOriginalStringReference(*(Js::JavascriptString **)(*(_QWORD *)v5 + 3296LL));
  if ( v6 <= 1 )
  {
    cchCount2 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v5 + 3296LL) + 16LL);
  }
  else
  {
    v16 = v7[1];
    if ( !Js::JavascriptString::Is((unsigned __int64)v16) )
      v16 = Js::JavascriptConversion::ToString((unsigned __int64)v16, (char **)v5, v17);
    v18 = (const WCHAR *)Js::JavascriptString::GetOriginalStringReference(v16);
    cchCount2 = *((_DWORD *)v16 + 4);
    lpString2 = v18;
  }
  UserDefaultLCID = GetUserDefaultLCID();
  v23 = CompareStringW(UserDefaultLCID, 0, OriginalStringReference, v14, lpString2, cchCount2);
  if ( !v23 )
    Js::JavascriptError::ThrowRangeError(
      *(Js::JavascriptLibrary ***)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1072LL),
      -2146828237,
      0);
  return (unsigned int)(v23 - 2) | 0x1000000000000LL;
}

```

## disassembly

```asm
0x1802c0290  mov     rax, rsp
0x1802c0293  mov     [rax+10h], rdx
0x1802c0297  mov     [rax+8], rcx
0x1802c029b  mov     [rax+18h], r8
0x1802c029f  mov     [rax+20h], r9
0x1802c02a3  push    rbx
0x1802c02a4  push    rbp
0x1802c02a5  push    rsi
0x1802c02a6  push    rdi
0x1802c02a7  push    r12
0x1802c02a9  push    r13
0x1802c02ab  push    r14
0x1802c02ad  push    r15
0x1802c02af  sub     rsp, 68h
0x1802c02b3  mov     r15, [rax+8]
0x1802c02b7  xor     r9d, r9d; void *
0x1802c02ba  mov     edx, 450h; unsigned __int64
0x1802c02bf  mov     rax, [r15+8]
0x1802c02c3  mov     rcx, [rax+8]
0x1802c02c7  mov     rcx, [rcx+430h]
0x1802c02ce  mov     r8, rcx; struct Js::ScriptContext *
0x1802c02d1  mov     rcx, [rcx+4A0h]; this
0x1802c02d8  call    ?ProbeStack@ThreadContext@@QEAAX_KPEAVScriptContext@Js@@PEAX@Z; ThreadContext::ProbeStack(unsigned __int64,Js::ScriptContext *,void *)
0x1802c02dd  lea     r8, [rsp+0A8h+arg_10]; void **
0x1802c02e5  mov     qword ptr [rsp+0A8h+var_58], 0
0x1802c02ee  lea     rdx, [rsp+0A8h+arg_8]; struct Js::CallInfo *
0x1802c02f6  lea     rcx, [rsp+0A8h+var_58]; this
0x1802c02fb  call    ??0ArgumentReader@Js@@QEAA@PEAUCallInfo@1@PEAPEAX@Z; Js::ArgumentReader::ArgumentReader(Js::CallInfo *,void * *)
0x1802c0300  mov     r10, [r15+8]
0x1802c0304  mov     r14d, dword ptr [rsp+0A8h+var_58]
0x1802c0309  mov     rax, [r10+8]
0x1802c030d  mov     rbx, [rax+430h]
0x1802c0314  and     r14d, 0FFFFFFh
0x1802c031b  jnz     short loc_1802C0332
0x1802c031d  lea     r8, aStringPrototyp_10; "String.prototype.localeCompare"
0x1802c0324  mov     edx, 800A13C1h; int
0x1802c0329  mov     rcx, rbx; struct Js::ScriptContext *
0x1802c032c  call    ?ThrowTypeError@JavascriptError@Js@@SAXPEAVScriptContext@2@JPEBG@Z; Js::JavascriptError::ThrowTypeError(Js::ScriptContext *,long,ushort const *)
0x1802c0332  cmp     dword ptr [rbx+920h], 3
0x1802c0339  mov     rsi, qword ptr [rsp+0A8h+var_58+8]
0x1802c033e  jl      short loc_1802C0361
0x1802c0340  mov     rcx, [rsi]; void *
0x1802c0343  call    ?CheckObjectCoercible@JavascriptConversion@Js@@SAHPEAXPEAVScriptContext@2@@Z; Js::JavascriptConversion::CheckObjectCoercible(void *,Js::ScriptContext *)
0x1802c0348  test    eax, eax
0x1802c034a  jnz     short loc_1802C0361
0x1802c034c  lea     r8, aStringPrototyp_10; "String.prototype.localeCompare"
0x1802c0353  mov     edx, 800A13BEh; int
0x1802c0358  mov     rcx, rbx; struct Js::ScriptContext *
0x1802c035b  call    ?ThrowTypeError@JavascriptError@Js@@SAXPEAVScriptContext@2@JPEBG@Z; Js::JavascriptError::ThrowTypeError(Js::ScriptContext *,long,ushort const *)
0x1802c0361  mov     rcx, [rbx]; this
0x1802c0364  call    ?GetIntlObject_EngineInterface@JavascriptLibraryBase@Js@@QEAAPEAVEngineInterfaceObject@2@XZ; Js::JavascriptLibraryBase::GetIntlObject_EngineInterface(void)
0x1802c0369  test    rax, rax
0x1802c036c  jz      short loc_1802C03CA
0x1802c036e  cmp     r14d, 2
0x1802c0372  jnz     loc_1802C043C
0x1802c0378  mov     rax, [rbx]
0x1802c037b  mov     rcx, r15
0x1802c037e  mov     r9, [rsi]
0x1802c0381  mov     dword ptr [rsp+0A8h+var_58+4], 0
0x1802c0389  mov     r8, [rax+420h]
0x1802c0390  mov     eax, dword ptr [rsp+0A8h+arg_8]
0x1802c0397  mov     [rsp+0A8h+var_68], r8
0x1802c039c  and     eax, 0FF000007h
0x1802c03a1  mov     [rsp+0A8h+var_70], r8
0x1802c03a6  or      eax, 7
0x1802c03a9  mov     dword ptr [rsp+0A8h+var_58], eax
0x1802c03ad  mov     rax, [rsi+8]
0x1802c03b1  mov     rdx, qword ptr [rsp+0A8h+var_58]
0x1802c03b6  mov     [rsp+0A8h+var_78], r8
0x1802c03bb  mov     qword ptr [rsp+0A8h+cchCount2], r8
0x1802c03c0  mov     [rsp+0A8h+lpString2], rax
0x1802c03c5  call    ?EntryIntl_CompareString@EngineInterfaceObject@Js@@SAPEAXPEAVRecyclableObject@2@UCallInfo@2@ZZ; Js::EngineInterfaceObject::EntryIntl_CompareString(Js::RecyclableObject *,Js::CallInfo,...)
0x1802c03ca  mov     rdi, [rsi]
0x1802c03cd  mov     rcx, rdi; void *
0x1802c03d0  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x1802c03d5  test    al, al
0x1802c03d7  jnz     short loc_1802C03E7
0x1802c03d9  mov     rdx, rbx; struct Js::ScriptContext *
0x1802c03dc  mov     rcx, rdi; this
0x1802c03df  call    ?ToString@JavascriptConversion@Js@@SAPEAVJavascriptString@2@PEAXPEAVScriptContext@2@@Z; Js::JavascriptConversion::ToString(void *,Js::ScriptContext *)
0x1802c03e4  mov     rdi, rax
0x1802c03e7  mov     rcx, rdi; this
0x1802c03ea  call    ?GetOriginalStringReference@JavascriptString@Js@@UEAAPEBXXZ; Js::JavascriptString::GetOriginalStringReference(void)
0x1802c03ef  mov     rcx, [rbx]
0x1802c03f2  mov     r12, rax
0x1802c03f5  mov     r13d, [rdi+10h]
0x1802c03f9  mov     rcx, [rcx+0CE0h]; this
0x1802c0400  call    ?GetOriginalStringReference@JavascriptString@Js@@UEAAPEBXXZ; Js::JavascriptString::GetOriginalStringReference(void)
0x1802c0405  mov     rbp, rax
0x1802c0408  cmp     r14d, 1
0x1802c040c  jbe     short loc_1802C045C
0x1802c040e  mov     rdi, [rsi+8]
0x1802c0412  mov     rcx, rdi; void *
0x1802c0415  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x1802c041a  test    al, al
0x1802c041c  jnz     short loc_1802C042C
0x1802c041e  mov     rdx, rbx; struct Js::ScriptContext *
0x1802c0421  mov     rcx, rdi; this
0x1802c0424  call    ?ToString@JavascriptConversion@Js@@SAPEAVJavascriptString@2@PEAXPEAVScriptContext@2@@Z; Js::JavascriptConversion::ToString(void *,Js::ScriptContext *)
0x1802c0429  mov     rdi, rax
0x1802c042c  mov     rcx, rdi; this
0x1802c042f  call    ?GetOriginalStringReference@JavascriptString@Js@@UEAAPEBXXZ; Js::JavascriptString::GetOriginalStringReference(void)
0x1802c0434  mov     ebx, [rdi+10h]
0x1802c0437  mov     rbp, rax
0x1802c043a  jmp     short loc_1802C0469
0x1802c043c  mov     rcx, [rax+48h]
0x1802c0440  test    rcx, rcx
0x1802c0443  jz      short loc_1802C03CA
0x1802c0445  movaps  xmm0, [rsp+0A8h+var_58]
0x1802c044a  lea     rdx, [rsp+0A8h+var_58]
0x1802c044f  movdqa  [rsp+0A8h+var_58], xmm0
0x1802c0455  call    ?CallFunction@JavascriptFunction@Js@@QEAAPEAXUArguments@2@@Z; Js::JavascriptFunction::CallFunction(Js::Arguments)
0x1802c045a  jmp     short loc_1802C04C5
0x1802c045c  mov     rax, [rbx]
0x1802c045f  mov     rcx, [rax+0CE0h]
0x1802c0466  mov     ebx, [rcx+10h]
0x1802c0469  call    cs:__imp_GetUserDefaultLCID
0x1802c0470  nop     dword ptr [rax+rax+00h]
0x1802c0475  mov     [rsp+0A8h+cchCount2], ebx; cchCount2
0x1802c0479  mov     r9d, r13d; cchCount1
0x1802c047c  mov     ecx, eax; Locale
0x1802c047e  mov     [rsp+0A8h+lpString2], rbp; lpString2
0x1802c0483  mov     r8, r12; lpString1
0x1802c0486  xor     edx, edx; dwCmpFlags
0x1802c0488  call    cs:__imp_CompareStringW
0x1802c048f  nop     dword ptr [rax+rax+00h]
0x1802c0494  test    eax, eax
0x1802c0496  jnz     short loc_1802C04B5
0x1802c0498  mov     rax, [r15+8]
0x1802c049c  xor     r8d, r8d; unsigned __int16 *
0x1802c049f  mov     edx, 800A0033h; int
0x1802c04a4  mov     rcx, [rax+8]
0x1802c04a8  mov     rcx, [rcx+430h]; struct Js::ScriptContext *
0x1802c04af  call    ?ThrowRangeError@JavascriptError@Js@@SAXPEAVScriptContext@2@JPEBG@Z; Js::JavascriptError::ThrowRangeError(Js::ScriptContext *,long,ushort const *)
0x1802c04b5  add     eax, 0FFFFFFFEh
0x1802c04b8  mov     rcx, 1000000000000h
0x1802c04c2  or      rax, rcx
0x1802c04c5  add     rsp, 68h
0x1802c04c9  pop     r15
0x1802c04cb  pop     r14
0x1802c04cd  pop     r13
0x1802c04cf  pop     r12
0x1802c04d1  pop     rdi
0x1802c04d2  pop     rsi
0x1802c04d3  pop     rbp
0x1802c04d4  pop     rbx
0x1802c04d5  retn
```
