# CCscWmiObject::CreateWbemClassObject(IWbemServices *,IWbemContext *,IWbemClassObject * *)

- ea: `0x18001d574`
- end: `0x18001d744`
- name: `?CreateWbemClassObject@CCscWmiObject@@QEAAJPEAUIWbemServices@@PEAUIWbemContext@@PEAPEAUIWbemClassObject@@@Z`
- size: `464`
- prototype: `__int64 __fastcall(CCscWmiObject *__hidden this, struct IWbemServices *, struct IWbemContext *, struct IWbemClassObject **)`
- caller_count: `7`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017830`
- `0x180017f3c`
- `0x1800181d0`
- `0x18001828c`
- `0x1800205ec`
- `0x18002273c`
- `0x1800228d8`

## callees

- `0x18000f5a4`
- `0x18000f5cc`
- `0x1800140c8`
- `0x18001c99c`
- `0x18001d574`
- `0x18002c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001d614`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d614`

## pseudocode

```c
__int64 __fastcall CCscWmiObject::CreateWbemClassObject(
        CCscWmiObject *this,
        struct IWbemServices *a2,
        struct IWbemContext *a3,
        BSTR *a4)
{
  struct IWbemServicesVtbl *lpVtbl; // rax
  const unsigned __int16 *v9; // rdx
  HRESULT (__stdcall *GetObjectA)(IWbemServices *, const BSTR, int, IWbemContext *, IWbemClassObject **, IWbemCallResult **); // rbx
  _QWORD *v11; // rax
  int v12; // ebx
  int v13; // eax
  BSTR v14; // rcx
  __int64 v15; // rcx
  BSTR bstrString; // [rsp+70h] [rbp+8h] BYREF
  __int64 v18; // [rsp+78h] [rbp+10h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(WPP_GLOBAL_Control + 28LL) & 0x4000000) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids);
  }
  *a4 = 0;
  lpVtbl = a2->lpVtbl;
  v9 = (const unsigned __int16 *)*((_QWORD *)this + 1);
  v18 = 0;
  GetObjectA = lpVtbl->GetObjectA;
  v11 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, v9);
  v12 = ((__int64 (__fastcall *)(struct IWbemServices *, _QWORD, _QWORD, struct IWbemContext *, __int64 *, _QWORD))GetObjectA)(
          a2,
          *v11,
          0,
          a3,
          &v18,
          0);
  SysFreeString(bstrString);
  if ( v12 >= 0 )
  {
    bstrString = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR *))(*(_QWORD *)v18 + 120LL))(v18, 0, &bstrString);
    v12 = v13;
    if ( v13 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_SD(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          11,
          (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
          *((_QWORD *)this + 1),
          v13);
    }
    else
    {
      v12 = (*(__int64 (__fastcall **)(CCscWmiObject *, struct IWbemServices *, struct IWbemContext *, BSTR))(*(_QWORD *)this + 8LL))(
              this,
              a2,
              a3,
              bstrString);
      if ( v12 >= 0 )
      {
        v14 = bstrString;
        *a4 = bstrString;
        (*(void (__fastcall **)(BSTR))(*(_QWORD *)v14 + 8LL))(v14);
      }
      (*(void (__fastcall **)(BSTR))(*(_QWORD *)bstrString + 16LL))(bstrString);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    goto LABEL_16;
  }
  v15 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)v12;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_SD(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      12,
      (unsigned int)WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids,
      *((_QWORD *)this + 1),
      v12);
LABEL_16:
    v15 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v15 != &WPP_GLOBAL_Control && (*(_DWORD *)(v15 + 28) & 0x4000000) != 0 )
    WPP_SF_d(*(_QWORD *)(v15 + 16), 13, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids, (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001d574  mov     [rsp+arg_10], rbx
0x18001d579  push    rbp
0x18001d57a  push    rsi
0x18001d57b  push    rdi
0x18001d57c  push    r14
0x18001d57e  push    r15
0x18001d580  sub     rsp, 40h
0x18001d584  mov     rsi, r9
0x18001d587  mov     rbp, r8
0x18001d58a  mov     r14, rdx
0x18001d58d  mov     rdi, rcx
0x18001d590  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d597  lea     r15, WPP_GLOBAL_Control
0x18001d59e  cmp     rcx, r15
0x18001d5a1  jz      short loc_18001D5C1
0x18001d5a3  test    dword ptr [rcx+1Ch], 4000000h
0x18001d5aa  jz      short loc_18001D5C1
0x18001d5ac  mov     rcx, [rcx+10h]
0x18001d5b0  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001d5b7  mov     edx, 0Ah
0x18001d5bc  call    WPP_SF_
0x18001d5c1  mov     qword ptr [rsi], 0
0x18001d5c8  lea     rcx, [rsp+68h+bstrString]; this
0x18001d5cd  mov     rax, [r14]
0x18001d5d0  mov     rdx, [rdi+8]; unsigned __int16 *
0x18001d5d4  mov     [rsp+68h+arg_8], 0
0x18001d5dd  mov     rbx, [rax+30h]
0x18001d5e1  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18001d5e6  lea     rcx, [rsp+68h+arg_8]
0x18001d5eb  mov     [rsp+68h+var_40], 0
0x18001d5f4  mov     [rsp+68h+var_48], rcx
0x18001d5f9  mov     r9, rbp
0x18001d5fc  xor     r8d, r8d
0x18001d5ff  mov     rcx, r14
0x18001d602  mov     rdx, [rax]
0x18001d605  mov     rax, rbx
0x18001d608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d60d  mov     rcx, [rsp+68h+bstrString]; bstrString
0x18001d612  mov     ebx, eax
0x18001d614  call    cs:__imp_SysFreeString
0x18001d61a  test    ebx, ebx
0x18001d61c  js      loc_18001D6D2
0x18001d622  mov     rcx, [rsp+68h+arg_8]
0x18001d627  lea     r8, [rsp+68h+bstrString]
0x18001d62c  mov     [rsp+68h+bstrString], 0
0x18001d635  xor     edx, edx
0x18001d637  mov     rax, [rcx]
0x18001d63a  mov     rax, [rax+78h]
0x18001d63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d643  mov     ebx, eax
0x18001d645  test    eax, eax
0x18001d647  js      short loc_18001D690
0x18001d649  mov     rax, [rdi]
0x18001d64c  mov     r8, rbp
0x18001d64f  mov     r9, [rsp+68h+bstrString]
0x18001d654  mov     rdx, r14
0x18001d657  mov     rcx, rdi
0x18001d65a  mov     rax, [rax+8]
0x18001d65e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d663  mov     ebx, eax
0x18001d665  test    eax, eax
0x18001d667  js      short loc_18001D67D
0x18001d669  mov     rcx, [rsp+68h+bstrString]
0x18001d66e  mov     [rsi], rcx
0x18001d671  mov     rax, [rcx]
0x18001d674  mov     rax, [rax+8]
0x18001d678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d67d  mov     rcx, [rsp+68h+bstrString]
0x18001d682  mov     rax, [rcx]
0x18001d685  mov     rax, [rax+10h]
0x18001d689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d68e  jmp     short loc_18001D6BF
0x18001d690  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d697  cmp     rcx, r15
0x18001d69a  jz      short loc_18001D6BF
0x18001d69c  test    byte ptr [rcx+1Ch], 2
0x18001d6a0  jz      short loc_18001D6BF
0x18001d6a2  mov     r9, [rdi+8]
0x18001d6a6  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001d6ad  mov     rcx, [rcx+10h]
0x18001d6b1  mov     edx, 0Bh
0x18001d6b6  mov     dword ptr [rsp+68h+var_48], eax
0x18001d6ba  call    WPP_SF_SD
0x18001d6bf  mov     rcx, [rsp+68h+arg_8]
0x18001d6c4  mov     rax, [rcx]
0x18001d6c7  mov     rax, [rax+10h]
0x18001d6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6d0  jmp     short loc_18001D701
0x18001d6d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d6d9  cmp     rcx, r15
0x18001d6dc  jz      short loc_18001D72E
0x18001d6de  test    byte ptr [rcx+1Ch], 2
0x18001d6e2  jz      short loc_18001D708
0x18001d6e4  mov     r9, [rdi+8]
0x18001d6e8  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001d6ef  mov     rcx, [rcx+10h]
0x18001d6f3  mov     edx, 0Ch
0x18001d6f8  mov     dword ptr [rsp+68h+var_48], ebx
0x18001d6fc  call    WPP_SF_SD
0x18001d701  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d708  cmp     rcx, r15
0x18001d70b  jz      short loc_18001D72E
0x18001d70d  test    dword ptr [rcx+1Ch], 4000000h
0x18001d714  jz      short loc_18001D72E
0x18001d716  mov     rcx, [rcx+10h]
0x18001d71a  lea     r8, WPP_a9b0d90f6b723a76085a448a6e9a8bc7_Traceguids
0x18001d721  mov     edx, 0Dh
0x18001d726  mov     r9d, ebx
0x18001d729  call    WPP_SF_d
0x18001d72e  mov     eax, ebx
0x18001d730  mov     rbx, [rsp+68h+arg_10]
0x18001d738  add     rsp, 40h
0x18001d73c  pop     r15
0x18001d73e  pop     r14
0x18001d740  pop     rdi
0x18001d741  pop     rsi
0x18001d742  pop     rbp
0x18001d743  retn
```
