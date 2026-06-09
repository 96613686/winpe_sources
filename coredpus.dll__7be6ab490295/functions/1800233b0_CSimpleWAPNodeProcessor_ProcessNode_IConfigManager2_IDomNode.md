# CSimpleWAPNodeProcessor::ProcessNode(IConfigManager2 *,IDomNode *)

- ea: `0x1800233b0`
- end: `0x1800234b0`
- name: `?ProcessNode@CSimpleWAPNodeProcessor@@UEAAJPEAUIConfigManager2@@PEAUIDomNode@@@Z`
- size: `256`
- prototype: `__int64 __fastcall(CSimpleWAPNodeProcessor *__hidden this, struct IConfigManager2 *, struct IDomNode *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001488`
- `0x180012b94`
- `0x1800233b0`
- `0x1800237f8`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002347d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002348d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002347d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002348d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSimpleWAPNodeProcessor::ProcessNode(
        CSimpleWAPNodeProcessor *this,
        struct IConfigManager2 *a2,
        struct IDomNode *a3,
        __int64 a4)
{
  OLECHAR *v7; // rbx
  int TranslatedPath; // edi
  OLECHAR *v10; // [rsp+40h] [rbp-10h] BYREF
  const OLECHAR *v11; // [rsp+48h] [rbp-8h] BYREF
  BSTR v12; // [rsp+88h] [rbp+38h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp+48h] BYREF

  v7 = 0;
  v12 = 0;
  if ( a2 && a3 )
  {
    TranslatedPath = *((_DWORD *)this + 6);
    if ( TranslatedPath >= 0 )
    {
      TranslatedPath = CWAPNodeProcessorBase::GetTranslatedPath(this, a3, &v12);
      v7 = v12;
      if ( TranslatedPath >= 0 )
      {
        TranslatedPath = CSimpleWAPNodeProcessor::ProcessNodeInternal(this, a2, a3, v12);
        if ( TranslatedPath >= 0 )
          goto LABEL_12;
      }
    }
  }
  else
  {
    TranslatedPath = -2147024809;
  }
  bstrString = 0;
  if ( a3 )
    (*(void (__fastcall **)(struct IDomNode *, BSTR *))(*(_QWORD *)a3 + 64LL))(a3, &bstrString);
  if ( (unsigned int)dword_18003E080 > 2 )
  {
    v10 = v7;
    v11 = bstrString;
    LODWORD(v12) = TranslatedPath;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)this,
      (unsigned __int8 *)byte_180037675,
      (__int64)a3,
      a4,
      (__int64)&v12,
      &v11,
      (const OLECHAR **)&v10);
  }
  SysFreeString(bstrString);
LABEL_12:
  SysFreeString(v7);
  return (unsigned int)TranslatedPath;
}

```

## disassembly

```asm
0x1800233b0  mov     [rsp-28h+arg_0], rbx
0x1800233b5  push    rbp
0x1800233b6  push    rsi
0x1800233b7  push    rdi
0x1800233b8  push    r14
0x1800233ba  push    r15
0x1800233bc  mov     rbp, rsp
0x1800233bf  sub     rsp, 50h
0x1800233c3  mov     rsi, r8
0x1800233c6  mov     r15, rdx
0x1800233c9  mov     r14, rcx
0x1800233cc  xor     ebx, ebx
0x1800233ce  mov     [rbp+arg_8], rbx
0x1800233d2  test    rdx, rdx
0x1800233d5  jnz     short loc_1800233DE
0x1800233d7  mov     edi, 80070057h
0x1800233dc  jmp     short loc_180023417
0x1800233de  test    rsi, rsi
0x1800233e1  jz      short loc_1800233D7
0x1800233e3  mov     edi, [rcx+18h]
0x1800233e6  test    edi, edi
0x1800233e8  js      short loc_180023417
0x1800233ea  lea     r8, [rbp+arg_8]; unsigned __int16 **
0x1800233ee  mov     rdx, rsi; struct IDomNode *
0x1800233f1  call    ?GetTranslatedPath@CWAPNodeProcessorBase@@IEAAJPEAUIDomNode@@PEAPEAG@Z; CWAPNodeProcessorBase::GetTranslatedPath(IDomNode *,ushort * *)
0x1800233f6  mov     edi, eax
0x1800233f8  mov     rbx, [rbp+arg_8]
0x1800233fc  test    eax, eax
0x1800233fe  js      short loc_180023417
0x180023400  mov     r9, rbx; unsigned __int16 *
0x180023403  mov     r8, rsi; struct IDomNode *
0x180023406  mov     rdx, r15; struct IConfigManager2 *
0x180023409  mov     rcx, r14; this
0x18002340c  call    ?ProcessNodeInternal@CSimpleWAPNodeProcessor@@AEAAJPEAUIConfigManager2@@PEAUIDomNode@@PEBG@Z; CSimpleWAPNodeProcessor::ProcessNodeInternal(IConfigManager2 *,IDomNode *,ushort const *)
0x180023411  mov     edi, eax
0x180023413  test    eax, eax
0x180023415  jns     short loc_18002348A
0x180023417  mov     [rbp+bstrString], 0
0x18002341f  test    rsi, rsi
0x180023422  jz      short loc_180023437
0x180023424  mov     rax, [rsi]
0x180023427  lea     rdx, [rbp+bstrString]
0x18002342b  mov     rcx, rsi
0x18002342e  mov     rax, [rax+40h]
0x180023432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023437  mov     eax, cs:dword_18003E080
0x18002343d  cmp     eax, 2
0x180023440  jbe     short loc_180023479
0x180023442  mov     [rbp+var_10], rbx
0x180023446  mov     rax, [rbp+bstrString]
0x18002344a  mov     [rbp+var_8], rax
0x18002344e  mov     dword ptr [rbp+arg_8], edi
0x180023451  lea     rax, [rbp+var_10]
0x180023455  mov     [rsp+50h+var_20], rax
0x18002345a  lea     rax, [rbp+var_8]
0x18002345e  mov     [rsp+50h+var_28], rax
0x180023463  lea     rax, [rbp+arg_8]
0x180023467  mov     [rsp+50h+var_30], rax
0x18002346c  lea     rdx, byte_180037675
0x180023473  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180023478  nop
0x180023479  mov     rcx, [rbp+bstrString]; bstrString
0x18002347d  call    cs:__imp_SysFreeString
0x180023484  nop     dword ptr [rax+rax+00h]
0x180023489  nop
0x18002348a  mov     rcx, rbx; bstrString
0x18002348d  call    cs:__imp_SysFreeString
0x180023494  nop     dword ptr [rax+rax+00h]
0x180023499  mov     eax, edi
0x18002349b  mov     rbx, [rsp+50h+arg_0]
0x1800234a3  add     rsp, 50h
0x1800234a7  pop     r15
0x1800234a9  pop     r14
0x1800234ab  pop     rdi
0x1800234ac  pop     rsi
0x1800234ad  pop     rbp
0x1800234ae  retn
```
