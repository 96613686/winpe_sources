# CSyncMLCmdAlert::ParseUIOptions(void)

- ea: `0x180020fa8`
- end: `0x180021286`
- name: `?ParseUIOptions@CSyncMLCmdAlert@@AEAAJXZ`
- size: `734`
- prototype: `__int64 __fastcall(CSyncMLCmdAlert *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800216cc`

## callees

- `0x1800034d0`
- `0x18001650c`
- `0x180020fa8`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800211ec`
- `OLEAUT32!__imp_SysFreeString` at `0x180021216`
- `OLEAUT32!__imp_SysFreeString` at `0x1800211ec`
- `OLEAUT32!__imp_SysFreeString` at `0x180021216`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800211a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021225`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800211a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021225`
- `DMCmnUtils!InvStrCmpW` at `0x1800210fd`
- `DMCmnUtils!InvStrCmpW` at `0x180021123`
- `DMCmnUtils!InvStrCmpW` at `0x180021151`
- `DMCmnUtils!InvStrCmpW` at `0x18002116c`
- `DMCmnUtils!InvStrCmpW` at `0x1800210fd`
- `DMCmnUtils!InvStrCmpW` at `0x180021123`
- `DMCmnUtils!InvStrCmpW` at `0x180021151`
- `DMCmnUtils!InvStrCmpW` at `0x18002116c`
- `DMCmnUtils!CopyString` at `0x1800211bb`
- `DMCmnUtils!CopyString` at `0x1800211bb`
- `DMCmnUtils!BigStrcat` at `0x180020ff0`
- `DMCmnUtils!BigStrcat` at `0x180020ff0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002102b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002102b`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdAlert::ParseUIOptions(CSyncMLCmdAlert *this)
{
  __int64 v1; // rax
  HRESULT v2; // ebx
  unsigned __int16 *v3; // r14
  _WORD *v5; // r8
  int v6; // eax
  __int64 v7; // rsi
  int v8; // eax
  int v9; // eax
  unsigned int *v10; // rdx
  int v11; // eax
  int v12; // r8d
  int v13; // r9d
  HRESULT v15; // [rsp+60h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp+38h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp+40h] BYREF

  v1 = *((_QWORD *)this + 1);
  v2 = 0;
  bstrString = 0;
  v3 = 0;
  ppv = 0;
  v5 = *(_WORD **)(*(_QWORD *)v1 + 80LL);
  if ( v5 && *v5 )
  {
    v3 = BigStrcat(2u, L".?");
    if ( !v3 )
    {
      v2 = -2147024882;
      goto LABEL_38;
    }
    v2 = CoCreateInstance(
           &GUID_50a41ef1_6bfa_4b7e_973e_798ea0bebad4,
           0,
           1u,
           &GUID_e34e5896_40b2_45c4_a9c0_8a9601c3b0a6,
           &ppv);
    if ( v2 >= 0 )
    {
      v6 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)ppv + 40LL))(ppv, v3);
      v2 = v6;
      if ( v6 != -2147418113 && v6 != -2147024882 )
      {
        if ( v6 < 0 )
        {
          v2 = -2102788095;
          goto LABEL_38;
        }
        v7 = 0;
        while ( 1 )
        {
          v8 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 * near *, BSTR *))(*(_QWORD *)ppv + 128LL))(
                 ppv,
                 (&CSyncMLCmdAlert::c_rgszUIOptions)[v7],
                 &bstrString);
          v2 = v8;
          if ( v8 != -2147023728 )
            break;
          v2 = 0;
LABEL_35:
          v7 = (unsigned int)(v7 + 1);
          if ( (unsigned int)v7 >= 6 )
            goto LABEL_38;
        }
        if ( v8 < 0 )
          goto LABEL_38;
        if ( !bstrString )
        {
LABEL_34:
          SysFreeString(bstrString);
          bstrString = 0;
          goto LABEL_35;
        }
        if ( (_DWORD)v7 )
        {
          if ( (_DWORD)v7 == 1 )
          {
            v10 = (unsigned int *)((char *)this + 188);
          }
          else
          {
            if ( (_DWORD)v7 == 2 )
            {
              LocalFree(*((HLOCAL *)this + 22));
              v11 = CopyString(bstrString, 0xFFFFFFFF, (unsigned __int16 **)this + 22);
              goto LABEL_33;
            }
            if ( (_DWORD)v7 != 3 )
            {
              if ( (_DWORD)v7 == 4 )
              {
                v9 = InvStrCmpW(L"A", bstrString);
                if ( v9 )
                {
                  if ( InvStrCmpW(L"N", bstrString) )
                  {
LABEL_37:
                    v2 = -2046820333;
                    goto LABEL_38;
                  }
                  v9 = 1;
                }
                *((_DWORD *)this + 50) = v9;
              }
              else if ( InvStrCmpW(L"T", bstrString) )
              {
                if ( InvStrCmpW(L"P", bstrString) )
                  goto LABEL_37;
                *((_DWORD *)this + 51) = 1;
              }
              else
              {
                *((_DWORD *)this + 51) = 0;
              }
              goto LABEL_34;
            }
            v10 = (unsigned int *)((char *)this + 192);
          }
        }
        else
        {
          v10 = (unsigned int *)((char *)this + 184);
        }
        v11 = TToDword(bstrString, v10);
LABEL_33:
        v2 = v11;
        if ( v11 < 0 )
          goto LABEL_38;
        goto LABEL_34;
      }
    }
  }
LABEL_38:
  SysFreeString(bstrString);
  LocalFree(v3);
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v15 = v2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (int)&dword_18003E048,
      (int)&byte_18003664F,
      v12,
      v13,
      (__int64)&v15);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180020fa8  push    rbp
0x180020faa  push    rbx
0x180020fab  push    rsi
0x180020fac  push    rdi
0x180020fad  push    r14
0x180020faf  mov     rbp, rsp
0x180020fb2  sub     rsp, 30h
0x180020fb6  mov     rax, [rcx+8]
0x180020fba  xor     ebx, ebx
0x180020fbc  mov     [rbp+bstrString], rbx
0x180020fc0  xor     r14d, r14d
0x180020fc3  mov     [rbp+arg_10], rbx
0x180020fc7  mov     rdi, rcx
0x180020fca  mov     rdx, [rax]
0x180020fcd  mov     r8, [rdx+50h]
0x180020fd1  test    r8, r8
0x180020fd4  jz      loc_180021212
0x180020fda  xor     eax, eax
0x180020fdc  cmp     ax, [r8]
0x180020fe0  jz      loc_180021212
0x180020fe6  lea     rdx, asc_1800344D0; ".?"
0x180020fed  lea     ecx, [rbx+2]
0x180020ff0  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x180020ff7  nop     dword ptr [rax+rax+00h]
0x180020ffc  mov     r14, rax
0x180020fff  test    rax, rax
0x180021002  jnz     short loc_18002100E
0x180021004  mov     ebx, 8007000Eh
0x180021009  jmp     loc_180021212
0x18002100e  xor     edx, edx; pUnkOuter
0x180021010  lea     rax, [rbp+arg_10]
0x180021014  lea     r9, _GUID_e34e5896_40b2_45c4_a9c0_8a9601c3b0a6; riid
0x18002101b  mov     [rsp+30h+ppv], rax; ppv
0x180021020  lea     rcx, _GUID_50a41ef1_6bfa_4b7e_973e_798ea0bebad4; rclsid
0x180021027  lea     r8d, [rdx+1]; dwClsContext
0x18002102b  call    cs:__imp_CoCreateInstance
0x180021032  nop     dword ptr [rax+rax+00h]
0x180021037  mov     ebx, eax
0x180021039  test    eax, eax
0x18002103b  js      loc_180021212
0x180021041  mov     rcx, [rbp+arg_10]
0x180021045  mov     rdx, r14
0x180021048  mov     rax, [rcx]
0x18002104b  mov     rax, [rax+28h]
0x18002104f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021054  mov     ebx, eax
0x180021056  cmp     eax, 8000FFFFh
0x18002105b  jz      loc_180021212
0x180021061  cmp     eax, 8007000Eh
0x180021066  jz      loc_180021212
0x18002106c  test    eax, eax
0x18002106e  jns     short loc_18002107A
0x180021070  mov     ebx, 82AA0001h
0x180021075  jmp     loc_180021212
0x18002107a  xor     esi, esi
0x18002107c  mov     rcx, [rbp+arg_10]
0x180021080  lea     r9, ?c_rgszUIOptions@CSyncMLCmdAlert@@0PAPEBGA; ushort const * near * CSyncMLCmdAlert::c_rgszUIOptions
0x180021087  mov     rdx, [r9+rsi*8]
0x18002108b  lea     r8, [rbp+bstrString]
0x18002108f  mov     rax, [rcx]
0x180021092  mov     rax, [rax+80h]
0x180021099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002109e  mov     ebx, eax
0x1800210a0  cmp     eax, 80070490h
0x1800210a5  jnz     short loc_1800210AE
0x1800210a7  xor     ebx, ebx
0x1800210a9  jmp     loc_180021200
0x1800210ae  test    eax, eax
0x1800210b0  js      loc_180021212
0x1800210b6  mov     rdx, [rbp+bstrString]
0x1800210ba  test    rdx, rdx
0x1800210bd  jz      loc_1800211E8
0x1800210c3  mov     ecx, esi
0x1800210c5  test    esi, esi
0x1800210c7  jz      loc_1800211D2
0x1800210cd  sub     ecx, 1
0x1800210d0  jz      loc_1800211C9
0x1800210d6  sub     ecx, 1
0x1800210d9  jz      loc_18002119B
0x1800210df  sub     ecx, 1
0x1800210e2  jz      loc_180021192
0x1800210e8  sub     ecx, 1
0x1800210eb  jz      short loc_180021146
0x1800210ed  cmp     ecx, 1
0x1800210f0  jnz     loc_1800211E8
0x1800210f6  lea     rcx, ?sc_szAlertEchoTypeText@CSyncMLCmdAlert@@0QBGB; "T"
0x1800210fd  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x180021104  nop     dword ptr [rax+rax+00h]
0x180021109  test    eax, eax
0x18002110b  jnz     short loc_180021118
0x18002110d  mov     [rdi+0CCh], eax
0x180021113  jmp     loc_1800211E8
0x180021118  mov     rdx, [rbp+bstrString]
0x18002111c  lea     rcx, ?sc_szAlertEchoTypePassword@CSyncMLCmdAlert@@0QBGB; "P"
0x180021123  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x18002112a  nop     dword ptr [rax+rax+00h]
0x18002112f  test    eax, eax
0x180021131  jnz     loc_18002120D
0x180021137  mov     dword ptr [rdi+0CCh], 1
0x180021141  jmp     loc_1800211E8
0x180021146  mov     rdx, [rbp+bstrString]
0x18002114a  lea     rcx, ?sc_szAlertInputTypeAlphanum@CSyncMLCmdAlert@@0QBGB; "A"
0x180021151  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x180021158  nop     dword ptr [rax+rax+00h]
0x18002115d  test    eax, eax
0x18002115f  jz      short loc_180021185
0x180021161  mov     rdx, [rbp+bstrString]
0x180021165  lea     rcx, ?sc_szAlertInputTypeNum@CSyncMLCmdAlert@@0QBGB; "N"
0x18002116c  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x180021173  nop     dword ptr [rax+rax+00h]
0x180021178  test    eax, eax
0x18002117a  jnz     loc_18002120D
0x180021180  mov     eax, 1
0x180021185  mov     edx, 0C8h
0x18002118a  mov     rcx, rdi
0x18002118d  mov     [rdx+rcx], eax
0x180021190  jmp     short loc_1800211E8
0x180021192  lea     rdx, [rdi+0C0h]
0x180021199  jmp     short loc_1800211D9
0x18002119b  lea     rbx, [rdi+0B0h]
0x1800211a2  mov     rcx, [rbx]; hMem
0x1800211a5  call    cs:__imp_LocalFree
0x1800211ac  nop     dword ptr [rax+rax+00h]
0x1800211b1  mov     rcx, [rbp+bstrString]
0x1800211b5  mov     r8, rbx
0x1800211b8  or      edx, 0FFFFFFFFh
0x1800211bb  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800211c2  nop     dword ptr [rax+rax+00h]
0x1800211c7  jmp     short loc_1800211E2
0x1800211c9  lea     rdx, [rdi+0BCh]
0x1800211d0  jmp     short loc_1800211D9
0x1800211d2  lea     rdx, [rdi+0B8h]; unsigned int *
0x1800211d9  mov     rcx, [rbp+bstrString]; unsigned __int16 *
0x1800211dd  call    ?TToDword@@YAJPEBGPEAK@Z; TToDword(ushort const *,ulong *)
0x1800211e2  mov     ebx, eax
0x1800211e4  test    eax, eax
0x1800211e6  js      short loc_180021212
0x1800211e8  mov     rcx, [rbp+bstrString]; bstrString
0x1800211ec  call    cs:__imp_SysFreeString
0x1800211f3  nop     dword ptr [rax+rax+00h]
0x1800211f8  mov     [rbp+bstrString], 0
0x180021200  inc     esi
0x180021202  cmp     esi, 6
0x180021205  jb      loc_18002107C
0x18002120b  jmp     short loc_180021212
0x18002120d  mov     ebx, 86000013h
0x180021212  mov     rcx, [rbp+bstrString]; bstrString
0x180021216  call    cs:__imp_SysFreeString
0x18002121d  nop     dword ptr [rax+rax+00h]
0x180021222  mov     rcx, r14; hMem
0x180021225  call    cs:__imp_LocalFree
0x18002122c  nop     dword ptr [rax+rax+00h]
0x180021231  mov     rcx, [rbp+arg_10]
0x180021235  test    rcx, rcx
0x180021238  jz      short loc_18002124E
0x18002123a  mov     rax, [rcx]
0x18002123d  mov     rax, [rax+10h]
0x180021241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021246  mov     [rbp+arg_10], 0
0x18002124e  mov     eax, cs:dword_18003E048
0x180021254  cmp     eax, 5
0x180021257  jbe     short loc_180021278
0x180021259  lea     rax, [rbp+arg_0]
0x18002125d  mov     [rbp+arg_0], ebx
0x180021260  lea     rdx, byte_18003664F
0x180021267  mov     [rsp+30h+ppv], rax
0x18002126c  lea     rcx, dword_18003E048
0x180021273  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180021278  mov     eax, ebx
0x18002127a  add     rsp, 30h
0x18002127e  pop     r14
0x180021280  pop     rdi
0x180021281  pop     rsi
0x180021282  pop     rbx
0x180021283  pop     rbp
0x180021284  retn
```
