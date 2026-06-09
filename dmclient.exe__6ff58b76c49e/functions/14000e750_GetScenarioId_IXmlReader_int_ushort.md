# GetScenarioId(IXmlReader *,int *,ushort *)

- ea: `0x14000e750`
- end: `0x14000e91e`
- name: `?GetScenarioId@@YAJPEAUIXmlReader@@PEAHPEAG@Z`
- size: `462`
- prototype: `__int64 __fastcall(struct IXmlReader *, int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000e924`

## callees

- `0x140001414`
- `0x14000e750`
- `0x1400187b2`
- `0x140019010`

## string_xrefs

- `0x14000e82e`: `MoveToAttributeByName failed`

## pseudocode

```c
__int64 __fastcall GetScenarioId(struct IXmlReader *a1, int *a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // rdi
  int v6; // ebx
  struct IXmlReaderVtbl *lpVtbl; // rax
  __int64 v8; // r9
  __int64 v9; // rax
  __int64 v10; // rcx
  unsigned __int16 *v11; // rdx
  __int64 v12; // rax
  unsigned __int16 *v13; // rcx
  __int64 v15; // [rsp+50h] [rbp-30h] BYREF
  __int64 v16; // [rsp+58h] [rbp-28h] BYREF
  const char *v17; // [rsp+60h] [rbp-20h] BYREF
  const char *v18; // [rsp+68h] [rbp-18h] BYREF
  const char *v19; // [rsp+70h] [rbp-10h] BYREF
  int v20; // [rsp+B0h] [rbp+30h] BYREF
  int v21; // [rsp+C8h] [rbp+48h] BYREF

  v3 = a3;
  v15 = 0;
  if ( a1 && a2 && a3 )
  {
    memset_0(a3, 0, 0x4Au);
    lpVtbl = a1->lpVtbl;
    *a2 = 0;
    v6 = ((__int64 (__fastcall *)(struct IXmlReader *, const wchar_t *, _QWORD))lpVtbl->MoveToAttributeByName)(
           a1,
           L"scenarioid",
           0);
    if ( v6 >= 0 )
    {
      if ( v6 == 1 )
      {
        return 0;
      }
      else
      {
        v6 = ((__int64 (__fastcall *)(struct IXmlReader *, __int64 *, _QWORD))a1->lpVtbl->GetValue)(a1, &v15, 0);
        if ( v6 >= 0 )
        {
          v9 = -1;
          do
            ++v9;
          while ( *(_WORD *)(v15 + 2 * v9) );
          if ( v9 == 38 )
          {
            v10 = 2147483646;
            v11 = (unsigned __int16 *)(v15 + 2);
            v12 = 37;
            do
            {
              if ( !v10 )
                break;
              if ( !*v11 )
                break;
              *v3++ = *v11++;
              --v10;
              --v12;
            }
            while ( v12 );
            *a2 = 1;
            v13 = v3 - 1;
            if ( v12 )
              v13 = v3;
            *v13 = 0;
          }
        }
      }
    }
    else if ( (unsigned int)dword_140027000 > 2
           && (qword_140027010 & 0x400000000000LL) != 0
           && (qword_140027018 & 0x400000000000LL) == qword_140027018 )
    {
      v16 = 0x1000000;
      v17 = "GetScenarioId";
      v20 = 207;
      v18 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
      v19 = "MoveToAttributeByName failed";
      v21 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_140027010,
        (__int64)byte_14002171D,
        0x400000000000LL,
        v8,
        (const unsigned __int16 **)&v19,
        (__int64)&v21,
        (const unsigned __int16 **)&v18,
        (const unsigned __int16 **)&v17,
        (__int64)&v20,
        (__int64)&v16);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000e750  mov     [rsp-28h+arg_8], rbx
0x14000e755  push    rbp
0x14000e756  push    rsi
0x14000e757  push    rdi
0x14000e758  push    r14
0x14000e75a  push    r15
0x14000e75c  mov     rbp, rsp
0x14000e75f  sub     rsp, 80h
0x14000e766  xor     r15d, r15d
0x14000e769  mov     rdi, r8
0x14000e76c  mov     [rbp+var_30], r15
0x14000e770  mov     r14, rdx
0x14000e773  mov     rsi, rcx
0x14000e776  test    rcx, rcx
0x14000e779  jnz     short loc_14000E785
0x14000e77b  mov     ebx, 80004003h
0x14000e780  jmp     loc_14000E905
0x14000e785  test    r14, r14
0x14000e788  jz      short loc_14000E77B
0x14000e78a  test    rdi, rdi
0x14000e78d  jz      short loc_14000E77B
0x14000e78f  xor     edx, edx; Val
0x14000e791  mov     rcx, rdi; void *
0x14000e794  lea     r8d, [rdx+4Ah]; Size
0x14000e798  call    memset_0
0x14000e79d  mov     rax, [rsi]
0x14000e7a0  lea     rdx, aScenarioid_0; "scenarioid"
0x14000e7a7  xor     r8d, r8d
0x14000e7aa  mov     [r14], r15d
0x14000e7ad  mov     rcx, rsi
0x14000e7b0  mov     rax, [rax+50h]
0x14000e7b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e7b9  mov     ebx, eax
0x14000e7bb  test    eax, eax
0x14000e7bd  jns     loc_14000E87C
0x14000e7c3  mov     ecx, cs:dword_140027000
0x14000e7c9  cmp     ecx, 2
0x14000e7cc  jbe     loc_14000E905
0x14000e7d2  mov     rdx, cs:qword_140027018
0x14000e7d9  mov     r8, 400000000000h
0x14000e7e3  mov     rcx, cs:qword_140027010
0x14000e7ea  test    r8, rcx
0x14000e7ed  jz      loc_14000E905
0x14000e7f3  mov     rax, rdx
0x14000e7f6  and     rax, r8
0x14000e7f9  cmp     rax, rdx
0x14000e7fc  jnz     loc_14000E905
0x14000e802  lea     rax, aGetscenarioid; "GetScenarioId"
0x14000e809  mov     [rbp+var_28], 1000000h
0x14000e811  mov     [rbp+var_20], rax
0x14000e815  lea     rdx, byte_14002171D
0x14000e81c  lea     rax, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000e823  mov     [rbp+arg_0], 0CFh
0x14000e82a  mov     [rbp+var_18], rax
0x14000e82e  lea     rax, aMovetoattribut; "MoveToAttributeByName failed"
0x14000e835  mov     [rbp+var_10], rax
0x14000e839  lea     rax, [rbp+var_28]
0x14000e83d  mov     [rsp+80h+var_38], rax
0x14000e842  lea     rax, [rbp+arg_0]
0x14000e846  mov     [rsp+80h+var_40], rax
0x14000e84b  lea     rax, [rbp+var_20]
0x14000e84f  mov     [rsp+80h+var_48], rax
0x14000e854  lea     rax, [rbp+var_18]
0x14000e858  mov     [rsp+80h+var_50], rax
0x14000e85d  lea     rax, [rbp+arg_18]
0x14000e861  mov     [rsp+80h+var_58], rax
0x14000e866  lea     rax, [rbp+var_10]
0x14000e86a  mov     [rsp+80h+var_60], rax
0x14000e86f  mov     [rbp+arg_18], ebx
0x14000e872  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000e877  jmp     loc_14000E905
0x14000e87c  cmp     ebx, 1
0x14000e87f  jnz     short loc_14000E886
0x14000e881  mov     ebx, r15d
0x14000e884  jmp     short loc_14000E905
0x14000e886  mov     rax, [rsi]
0x14000e889  lea     rdx, [rbp+var_30]
0x14000e88d  xor     r8d, r8d
0x14000e890  mov     rcx, rsi
0x14000e893  mov     rax, [rax+80h]
0x14000e89a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e89f  mov     ebx, eax
0x14000e8a1  test    eax, eax
0x14000e8a3  js      short loc_14000E905
0x14000e8a5  mov     rdx, [rbp+var_30]
0x14000e8a9  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000e8ad  inc     rax
0x14000e8b0  cmp     [rdx+rax*2], r15w
0x14000e8b5  jnz     short loc_14000E8AD
0x14000e8b7  cmp     rax, 26h ; '&'
0x14000e8bb  jnz     short loc_14000E905
0x14000e8bd  mov     ecx, 7FFFFFFEh
0x14000e8c2  add     rdx, 2
0x14000e8c6  mov     eax, 25h ; '%'
0x14000e8cb  test    rcx, rcx
0x14000e8ce  jz      short loc_14000E8EF
0x14000e8d0  movzx   r8d, word ptr [rdx]
0x14000e8d4  test    r8w, r8w
0x14000e8d8  jz      short loc_14000E8EF
0x14000e8da  mov     [rdi], r8w
0x14000e8de  add     rdx, 2
0x14000e8e2  add     rdi, 2
0x14000e8e6  dec     rcx
0x14000e8e9  sub     rax, 1
0x14000e8ed  jnz     short loc_14000E8CB
0x14000e8ef  test    rax, rax
0x14000e8f2  mov     dword ptr [r14], 1
0x14000e8f9  lea     rcx, [rdi-2]
0x14000e8fd  cmovnz  rcx, rdi
0x14000e901  mov     [rcx], r15w
0x14000e905  mov     eax, ebx
0x14000e907  mov     rbx, [rsp+80h+arg_8]
0x14000e90f  add     rsp, 80h
0x14000e916  pop     r15
0x14000e918  pop     r14
0x14000e91a  pop     rdi
0x14000e91b  pop     rsi
0x14000e91c  pop     rbp
0x14000e91d  retn
```
