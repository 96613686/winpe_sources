# GetScenarioId(IXmlReader *,int *,ushort *)

- ea: `0x14000ecc0`
- end: `0x14000ee8f`
- name: `?GetScenarioId@@YAJPEAUIXmlReader@@PEAHPEAG@Z`
- size: `463`
- prototype: `int(struct IXmlReader *, int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000ee98`

## callees

- `0x140001418`
- `0x14000ecc0`
- `0x1400195e2`
- `0x14001a010`

## string_xrefs

- `0x14000ed9e`: `MoveToAttributeByName failed`

## pseudocode

```c
__int64 __fastcall GetScenarioId(struct IXmlReader *a1, int *a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // rdi
  int v6; // ebx
  struct IXmlReaderVtbl *lpVtbl; // rax
  int v8; // r9d
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
    else if ( (unsigned int)dword_140028000 > 2
           && (qword_140028010 & 0x400000000000LL) != 0
           && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
    {
      v16 = 0x1000000;
      v17 = "GetScenarioId";
      v20 = 207;
      v18 = "onecore\\base\\diagnosis\\feedback\\siuf\\libs\\telman\\telman.cpp";
      v19 = "MoveToAttributeByName failed";
      v21 = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_140028010,
        (unsigned int)byte_140022725,
        0,
        v8,
        (__int64)&v19,
        (__int64)&v21,
        (__int64)&v18,
        (__int64)&v17,
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
0x14000ecc0  mov     [rsp-28h+arg_8], rbx
0x14000ecc5  push    rbp
0x14000ecc6  push    rsi
0x14000ecc7  push    rdi
0x14000ecc8  push    r14
0x14000ecca  push    r15
0x14000eccc  mov     rbp, rsp
0x14000eccf  sub     rsp, 80h
0x14000ecd6  xor     r15d, r15d
0x14000ecd9  mov     rdi, r8
0x14000ecdc  mov     [rbp+var_30], r15
0x14000ece0  mov     r14, rdx
0x14000ece3  mov     rsi, rcx
0x14000ece6  test    rcx, rcx
0x14000ece9  jnz     short loc_14000ECF5
0x14000eceb  mov     ebx, 80004003h
0x14000ecf0  jmp     loc_14000EE75
0x14000ecf5  test    r14, r14
0x14000ecf8  jz      short loc_14000ECEB
0x14000ecfa  test    rdi, rdi
0x14000ecfd  jz      short loc_14000ECEB
0x14000ecff  xor     edx, edx; Val
0x14000ed01  mov     rcx, rdi; void *
0x14000ed04  lea     r8d, [rdx+4Ah]; Size
0x14000ed08  call    memset_0
0x14000ed0d  mov     rax, [rsi]
0x14000ed10  lea     rdx, aScenarioid_0; "scenarioid"
0x14000ed17  xor     r8d, r8d
0x14000ed1a  mov     [r14], r15d
0x14000ed1d  mov     rcx, rsi
0x14000ed20  mov     rax, [rax+50h]
0x14000ed24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ed29  mov     ebx, eax
0x14000ed2b  test    eax, eax
0x14000ed2d  jns     loc_14000EDEC
0x14000ed33  mov     ecx, cs:dword_140028000
0x14000ed39  cmp     ecx, 2
0x14000ed3c  jbe     loc_14000EE75
0x14000ed42  mov     rdx, cs:qword_140028018
0x14000ed49  mov     r8, 400000000000h
0x14000ed53  mov     rcx, cs:qword_140028010
0x14000ed5a  test    r8, rcx
0x14000ed5d  jz      loc_14000EE75
0x14000ed63  mov     rax, rdx
0x14000ed66  and     rax, r8
0x14000ed69  cmp     rax, rdx
0x14000ed6c  jnz     loc_14000EE75
0x14000ed72  lea     rax, aGetscenarioid; "GetScenarioId"
0x14000ed79  mov     [rbp+var_28], 1000000h
0x14000ed81  mov     [rbp+var_20], rax
0x14000ed85  lea     rdx, byte_140022725
0x14000ed8c  lea     rax, aOnecoreBaseDia_5; "onecore\\base\\diagnosis\\feedback\\siu"...
0x14000ed93  mov     [rbp+arg_0], 0CFh
0x14000ed9a  mov     [rbp+var_18], rax
0x14000ed9e  lea     rax, aMovetoattribut; "MoveToAttributeByName failed"
0x14000eda5  mov     [rbp+var_10], rax
0x14000eda9  lea     rax, [rbp+var_28]
0x14000edad  mov     [rsp+80h+var_38], rax
0x14000edb2  lea     rax, [rbp+arg_0]
0x14000edb6  mov     [rsp+80h+var_40], rax
0x14000edbb  lea     rax, [rbp+var_20]
0x14000edbf  mov     [rsp+80h+var_48], rax
0x14000edc4  lea     rax, [rbp+var_18]
0x14000edc8  mov     [rsp+80h+var_50], rax
0x14000edcd  lea     rax, [rbp+arg_18]
0x14000edd1  mov     [rsp+80h+var_58], rax
0x14000edd6  lea     rax, [rbp+var_10]
0x14000edda  mov     [rsp+80h+var_60], rax
0x14000eddf  mov     [rbp+arg_18], ebx
0x14000ede2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14000ede7  jmp     loc_14000EE75
0x14000edec  cmp     ebx, 1
0x14000edef  jnz     short loc_14000EDF6
0x14000edf1  mov     ebx, r15d
0x14000edf4  jmp     short loc_14000EE75
0x14000edf6  mov     rax, [rsi]
0x14000edf9  lea     rdx, [rbp+var_30]
0x14000edfd  xor     r8d, r8d
0x14000ee00  mov     rcx, rsi
0x14000ee03  mov     rax, [rax+80h]
0x14000ee0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ee0f  mov     ebx, eax
0x14000ee11  test    eax, eax
0x14000ee13  js      short loc_14000EE75
0x14000ee15  mov     rdx, [rbp+var_30]
0x14000ee19  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000ee1d  inc     rax
0x14000ee20  cmp     [rdx+rax*2], r15w
0x14000ee25  jnz     short loc_14000EE1D
0x14000ee27  cmp     rax, 26h ; '&'
0x14000ee2b  jnz     short loc_14000EE75
0x14000ee2d  mov     ecx, 7FFFFFFEh
0x14000ee32  add     rdx, 2
0x14000ee36  mov     eax, 25h ; '%'
0x14000ee3b  test    rcx, rcx
0x14000ee3e  jz      short loc_14000EE5F
0x14000ee40  movzx   r8d, word ptr [rdx]
0x14000ee44  test    r8w, r8w
0x14000ee48  jz      short loc_14000EE5F
0x14000ee4a  mov     [rdi], r8w
0x14000ee4e  add     rdx, 2
0x14000ee52  add     rdi, 2
0x14000ee56  dec     rcx
0x14000ee59  sub     rax, 1
0x14000ee5d  jnz     short loc_14000EE3B
0x14000ee5f  test    rax, rax
0x14000ee62  mov     dword ptr [r14], 1
0x14000ee69  lea     rcx, [rdi-2]
0x14000ee6d  cmovnz  rcx, rdi
0x14000ee71  mov     [rcx], r15w
0x14000ee75  mov     eax, ebx
0x14000ee77  mov     rbx, [rsp+80h+arg_8]
0x14000ee7f  add     rsp, 80h
0x14000ee86  pop     r15
0x14000ee88  pop     r14
0x14000ee8a  pop     rdi
0x14000ee8b  pop     rsi
0x14000ee8c  pop     rbp
0x14000ee8d  retn
```
