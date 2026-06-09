# XMLScrSite::OnError(ulong,IScriptletError *)

- ea: `0x1400114e0`
- end: `0x1400117b4`
- name: `?OnError@XMLScrSite@@UEAAJKPEAUIScriptletError@@@Z`
- size: `724`
- prototype: `__int64 __fastcall(XMLScrSite *__hidden this, unsigned int, struct IScriptletError *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callees

- `0x14000cd9c`
- `0x14000f180`
- `0x1400114e0`
- `0x14001619a`
- `0x140017010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140011756`
- `OLEAUT32!__imp_SysFreeString` at `0x140011760`
- `OLEAUT32!__imp_SysFreeString` at `0x14001176a`
- `OLEAUT32!__imp_SysFreeString` at `0x140011774`
- `OLEAUT32!__imp_SysFreeString` at `0x14001177d`
- `OLEAUT32!__imp_SysFreeString` at `0x140011756`
- `OLEAUT32!__imp_SysFreeString` at `0x140011760`
- `OLEAUT32!__imp_SysFreeString` at `0x14001176a`
- `OLEAUT32!__imp_SysFreeString` at `0x140011774`
- `OLEAUT32!__imp_SysFreeString` at `0x14001177d`

## pseudocode

```c
__int64 __fastcall XMLScrSite::OnError(XMLScrSite *this, char a2, struct IScriptletError *a3)
{
  __int64 v6; // rax
  OLECHAR *v7; // r14
  struct IDispatch *v8; // rdi
  __int64 (__fastcall *v9)(struct IScriptletError *, _BYTE *); // rax
  __int64 result; // rax
  BSTR v11; // rbx
  int v12; // eax
  int v13; // ebx
  BSTR v14; // r9
  int v15; // eax
  __int64 v16; // rcx
  int ScriptDispatch; // eax
  int v18; // eax
  int v19; // [rsp+20h] [rbp-89h]
  unsigned int v20; // [rsp+50h] [rbp-59h] BYREF
  BSTR v21; // [rsp+58h] [rbp-51h] BYREF
  BSTR v22; // [rsp+60h] [rbp-49h] BYREF
  struct IDispatch *v23; // [rsp+68h] [rbp-41h] BYREF
  const wchar_t *v24; // [rsp+70h] [rbp-39h] BYREF
  __int128 v25; // [rsp+78h] [rbp-31h] BYREF
  __int64 v26; // [rsp+88h] [rbp-21h]
  _BYTE v27[8]; // [rsp+90h] [rbp-19h] BYREF
  BSTR v28; // [rsp+98h] [rbp-11h]
  BSTR bstrString; // [rsp+A0h] [rbp-9h]
  BSTR v30; // [rsp+A8h] [rbp-1h]
  DWORD dwMessageId; // [rsp+C8h] [rbp+1Fh]
  int v32; // [rsp+120h] [rbp+77h] BYREF
  unsigned int v33; // [rsp+128h] [rbp+7Fh] BYREF

  memset_0(v27, 0, 0x40u);
  v33 = 0;
  v26 = 0;
  v6 = *(_QWORD *)a3;
  v32 = 0;
  v7 = 0;
  v20 = 0;
  v8 = 0;
  v25 = 0;
  v9 = *(__int64 (__fastcall **)(struct IScriptletError *, _BYTE *))(v6 + 24);
  v24 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  result = v9(a3, v27);
  if ( (int)result < 0 )
    return result;
  _InterlockedExchange((volatile __int32 *)(*((_QWORD *)this + 4) + 40LL), 0);
  if ( dwMessageId == -2147467260 )
    goto LABEL_26;
  if ( dwMessageId != -2147155972 )
  {
    if ( dwMessageId == -2147155971 )
    {
LABEL_17:
      v13 = 0;
      goto LABEL_28;
    }
    if ( dwMessageId != -2147155970 )
    {
      v11 = bstrString;
      if ( !bstrString || !*bstrString )
      {
        v12 = FormatHResult(dwMessageId, &v22);
        v7 = v22;
        v13 = v12;
        if ( v12 < 0 )
          goto LABEL_28;
        v11 = v22;
      }
      if ( (*(int (__fastcall **)(struct IScriptletError *, unsigned int *, int *))(*(_QWORD *)a3 + 32LL))(
             a3,
             &v33,
             &v32) < 0 )
      {
        v33 = 0;
        v32 = -1;
      }
      if ( (*(int (__fastcall **)(struct IScriptletError *, BSTR *))(*(_QWORD *)a3 + 40LL))(a3, &v21) >= 0 )
      {
        v14 = v21;
      }
      else
      {
        v14 = 0;
        v21 = 0;
      }
      v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, BSTR, BSTR, BSTR, DWORD, int))(**((_QWORD **)this + 4)
                                                                                            + 40LL))(
              *((_QWORD *)this + 4),
              v33,
              (unsigned int)(v32 + 1),
              v28,
              v11,
              v14,
              dwMessageId,
              a2 & 1);
      goto LABEL_16;
    }
LABEL_26:
    v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 64LL))(*((_QWORD *)this + 4));
    if ( v13 >= 0 )
      v13 = 0;
    goto LABEL_28;
  }
  if ( *((_DWORD *)this + 12) )
    goto LABEL_17;
  v16 = *((_QWORD *)this + 5);
  *((_DWORD *)this + 12) = 1;
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 40LL))(v16);
  if ( v13 < 0 )
    goto LABEL_28;
  ScriptDispatch = CHost::GetScriptDispatch(*((CHost **)this + 4), &v23);
  v8 = v23;
  v13 = ScriptDispatch;
  if ( ScriptDispatch < 0 )
    goto LABEL_28;
  v20 = 0;
  v24 = L"WScript_OnScriptTerminate";
  v18 = ((__int64 (__fastcall *)(struct IDispatch *, GUID *, const wchar_t **, __int64, int, unsigned int *))v23->lpVtbl->GetIDsOfNames)(
          v23,
          &GUID_NULL,
          &v24,
          1,
          1024,
          &v20);
  if ( v18 < 0 )
  {
    v13 = 0;
    if ( v18 != -2147352570 )
      v13 = v18;
    goto LABEL_28;
  }
  v25 = 0;
  v26 = 0;
  LOWORD(v19) = 1;
  v15 = ((__int64 (__fastcall *)(struct IDispatch *, _QWORD, GUID *, __int64, int, __int128 *, _QWORD, _QWORD, _QWORD))v8->lpVtbl->Invoke)(
          v8,
          v20,
          &GUID_NULL,
          1024,
          v19,
          &v25,
          0,
          0,
          0);
LABEL_16:
  v13 = v15;
  if ( v15 >= 0 )
    goto LABEL_17;
LABEL_28:
  SysFreeString(bstrString);
  SysFreeString(v28);
  SysFreeString(v30);
  SysFreeString(v21);
  SysFreeString(v7);
  if ( v8 )
    ((void (__fastcall *)(struct IDispatch *))v8->lpVtbl->Release)(v8);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1400114e0  mov     [rsp-8+arg_0], rbx
0x1400114e5  push    rbp
0x1400114e6  push    rsi
0x1400114e7  push    rdi
0x1400114e8  push    r12
0x1400114ea  push    r13
0x1400114ec  push    r14
0x1400114ee  push    r15
0x1400114f0  lea     rbp, [rsp-27h]
0x1400114f5  sub     rsp, 0D0h
0x1400114fc  mov     r12d, edx
0x1400114ff  mov     r15, r8
0x140011502  xor     edx, edx; Val
0x140011504  mov     rsi, rcx
0x140011507  lea     rcx, [rbp+57h+var_70]; void *
0x14001150b  lea     r8d, [rdx+40h]; Size
0x14001150f  call    memset_0
0x140011514  xor     r13d, r13d
0x140011517  lea     rdx, [rbp+57h+var_70]
0x14001151b  xor     eax, eax
0x14001151d  mov     [rbp+57h+arg_18], r13d
0x140011521  mov     [rbp+57h+var_78], rax
0x140011525  xorps   xmm0, xmm0
0x140011528  mov     rax, [r15]
0x14001152b  mov     rcx, r15
0x14001152e  mov     [rbp+57h+arg_10], r13d
0x140011532  mov     r14d, r13d
0x140011535  mov     [rbp+57h+var_B0], r13d
0x140011539  mov     edi, r13d
0x14001153c  movups  [rbp+57h+var_88], xmm0
0x140011540  mov     rax, [rax+18h]
0x140011544  mov     [rbp+57h+var_90], r13
0x140011548  mov     [rbp+57h+var_A8], r13
0x14001154c  mov     [rbp+57h+var_A0], r13
0x140011550  mov     [rbp+57h+var_98], r13
0x140011554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011559  test    eax, eax
0x14001155b  js      loc_140011799
0x140011561  mov     rcx, [rsi+20h]
0x140011565  mov     eax, r13d
0x140011568  xchg    eax, [rcx+28h]
0x14001156b  mov     ecx, [rbp+57h+dwMessageId]; dwMessageId
0x14001156e  cmp     ecx, 80004004h
0x140011574  jz      loc_14001173A
0x14001157a  cmp     ecx, 8004FFFCh
0x140011580  jz      loc_14001165B
0x140011586  cmp     ecx, 8004FFFDh
0x14001158c  jz      loc_140011653
0x140011592  cmp     ecx, 8004FFFEh
0x140011598  jz      loc_14001173A
0x14001159e  mov     rbx, [rbp+57h+bstrString]
0x1400115a2  test    rbx, rbx
0x1400115a5  jz      short loc_1400115AD
0x1400115a7  cmp     r13w, [rbx]
0x1400115ab  jnz     short loc_1400115C7
0x1400115ad  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 **
0x1400115b1  call    ?FormatHResult@@YAJJPEAPEAG@Z; FormatHResult(long,ushort * *)
0x1400115b6  mov     r14, [rbp+57h+var_A0]
0x1400115ba  mov     ebx, eax
0x1400115bc  test    eax, eax
0x1400115be  js      loc_140011752
0x1400115c4  mov     rbx, r14
0x1400115c7  mov     rax, [r15]
0x1400115ca  lea     r8, [rbp+57h+arg_10]
0x1400115ce  lea     rdx, [rbp+57h+arg_18]
0x1400115d2  mov     rcx, r15
0x1400115d5  mov     rax, [rax+20h]
0x1400115d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400115de  test    eax, eax
0x1400115e0  jns     short loc_1400115ED
0x1400115e2  mov     [rbp+57h+arg_18], r13d
0x1400115e6  mov     [rbp+57h+arg_10], 0FFFFFFFFh
0x1400115ed  mov     rax, [r15]
0x1400115f0  lea     rdx, [rbp+57h+var_A8]
0x1400115f4  mov     rcx, r15
0x1400115f7  mov     rax, [rax+28h]
0x1400115fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011600  test    eax, eax
0x140011602  jns     short loc_14001160D
0x140011604  mov     r9, r13
0x140011607  mov     [rbp+57h+var_A8], r13
0x14001160b  jmp     short loc_140011611
0x14001160d  mov     r9, [rbp+57h+var_A8]
0x140011611  mov     edx, [rbp+57h+dwMessageId]
0x140011614  and     r12d, 1
0x140011618  mov     rcx, [rsi+20h]
0x14001161c  mov     r8d, [rbp+57h+arg_10]
0x140011620  mov     dword ptr [rsp+100h+var_C8], r12d
0x140011625  inc     r8d
0x140011628  mov     dword ptr [rsp+100h+var_D0], edx
0x14001162c  mov     rax, [rcx]
0x14001162f  mov     edx, [rbp+57h+arg_18]
0x140011632  mov     [rsp+100h+var_D8], r9
0x140011637  mov     r9, [rbp+57h+var_68]
0x14001163b  mov     rax, [rax+28h]
0x14001163f  mov     [rsp+100h+var_E0], rbx
0x140011644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011649  mov     ebx, eax
0x14001164b  test    eax, eax
0x14001164d  js      loc_140011752
0x140011653  mov     ebx, r13d
0x140011656  jmp     loc_140011752
0x14001165b  cmp     [rsi+30h], r13d
0x14001165f  jnz     short loc_140011653
0x140011661  mov     rcx, [rsi+28h]
0x140011665  mov     r15d, 1
0x14001166b  mov     [rsi+30h], r15d
0x14001166f  mov     rax, [rcx]
0x140011672  mov     rax, [rax+28h]
0x140011676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001167b  mov     ebx, eax
0x14001167d  test    eax, eax
0x14001167f  js      loc_140011752
0x140011685  mov     rcx, [rsi+20h]; this
0x140011689  lea     rdx, [rbp+57h+var_98]; struct IDispatch **
0x14001168d  call    ?GetScriptDispatch@CHost@@QEAAJPEAPEAUIDispatch@@@Z; CHost::GetScriptDispatch(IDispatch * *)
0x140011692  mov     rdi, [rbp+57h+var_98]
0x140011696  mov     ebx, eax
0x140011698  test    eax, eax
0x14001169a  js      loc_140011752
0x1400116a0  lea     rax, aWscriptOnscrip; "WScript_OnScriptTerminate"
0x1400116a7  mov     [rbp+57h+var_B0], r13d
0x1400116ab  mov     [rbp+57h+var_90], rax
0x1400116af  lea     rcx, [rbp+57h+var_B0]
0x1400116b3  mov     rax, [rdi]
0x1400116b6  lea     r8, [rbp+57h+var_90]
0x1400116ba  mov     [rsp+100h+var_D8], rcx
0x1400116bf  lea     rdx, GUID_NULL
0x1400116c6  mov     ebx, 400h
0x1400116cb  mov     r9d, r15d
0x1400116ce  mov     rcx, rdi
0x1400116d1  mov     dword ptr [rsp+100h+var_E0], ebx
0x1400116d5  mov     rax, [rax+28h]
0x1400116d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400116de  test    eax, eax
0x1400116e0  jns     short loc_1400116EF
0x1400116e2  cmp     eax, 80020006h
0x1400116e7  mov     ebx, r13d
0x1400116ea  cmovnz  ebx, eax
0x1400116ed  jmp     short loc_140011752
0x1400116ef  mov     edx, [rbp+57h+var_B0]
0x1400116f2  lea     rcx, [rbp+57h+var_88]
0x1400116f6  mov     [rsp+100h+var_C0], r13
0x1400116fb  lea     r8, GUID_NULL
0x140011702  mov     [rsp+100h+var_C8], r13
0x140011707  xorps   xmm0, xmm0
0x14001170a  movdqu  [rbp+57h+var_88], xmm0
0x14001170f  mov     [rbp+57h+var_78], r13
0x140011713  mov     r9d, ebx
0x140011716  mov     rax, [rdi]
0x140011719  mov     [rsp+100h+var_D0], r13
0x14001171e  mov     [rsp+100h+var_D8], rcx
0x140011723  mov     rcx, rdi
0x140011726  mov     word ptr [rsp+100h+var_E0], r15w
0x14001172c  mov     rax, [rax+30h]
0x140011730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011735  jmp     loc_140011649
0x14001173a  mov     rcx, [rsi+20h]
0x14001173e  mov     rax, [rcx]
0x140011741  mov     rax, [rax+40h]
0x140011745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001174a  test    eax, eax
0x14001174c  mov     ebx, eax
0x14001174e  cmovns  ebx, r13d
0x140011752  mov     rcx, [rbp+57h+bstrString]; bstrString
0x140011756  call    cs:__imp_SysFreeString
0x14001175c  mov     rcx, [rbp+57h+var_68]; bstrString
0x140011760  call    cs:__imp_SysFreeString
0x140011766  mov     rcx, [rbp+57h+var_58]; bstrString
0x14001176a  call    cs:__imp_SysFreeString
0x140011770  mov     rcx, [rbp+57h+var_A8]; bstrString
0x140011774  call    cs:__imp_SysFreeString
0x14001177a  mov     rcx, r14; bstrString
0x14001177d  call    cs:__imp_SysFreeString
0x140011783  test    rdi, rdi
0x140011786  jz      short loc_140011797
0x140011788  mov     rax, [rdi]
0x14001178b  mov     rcx, rdi
0x14001178e  mov     rax, [rax+10h]
0x140011792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011797  mov     eax, ebx
0x140011799  mov     rbx, [rsp+100h+arg_0]
0x1400117a1  add     rsp, 0D0h
0x1400117a8  pop     r15
0x1400117aa  pop     r14
0x1400117ac  pop     r13
0x1400117ae  pop     r12
0x1400117b0  pop     rdi
0x1400117b1  pop     rsi
0x1400117b2  pop     rbp
0x1400117b3  retn
```
