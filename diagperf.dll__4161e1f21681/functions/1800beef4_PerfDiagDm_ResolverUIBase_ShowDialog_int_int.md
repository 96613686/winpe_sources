# PerfDiagDm::ResolverUIBase::ShowDialog(int,int)

- ea: `0x1800beef4`
- end: `0x1800bf145`
- name: `?ShowDialog@ResolverUIBase@PerfDiagDm@@QEAAJHH@Z`
- size: `593`
- prototype: `__int64 __fastcall(PerfDiagDm::ResolverUIBase *__hidden this, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1800beea8`

## callees

- `0x180013870`
- `0x1800be3fc`
- `0x1800beef4`
- `0x1800bf790`
- `0x1800cf032`
- `0x1800cf080`
- `0x1800d6010`

## import_xrefs

- `USER32!LoadStringW` at `0x1800bf058`
- `USER32!LoadStringW` at `0x1800bf058`
- `ole32!CoUninitialize` at `0x1800bf11b`
- `ole32!CoUninitialize` at `0x1800bf11b`
- `SHELL32!SHGetStockIconInfo` at `0x1800bf0a0`
- `SHELL32!SHGetStockIconInfo` at `0x1800bf0a0`
- `DUI70!UnInitProcessPriv` at `0x1800bf115`
- `DUI70!UnInitProcessPriv` at `0x1800bf115`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800bf0fa`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x1800bf0fa`
- `DUI70!UnInitThread` at `0x1800bf108`
- `DUI70!UnInitThread` at `0x1800bf108`

## string_xrefs

- `0x1800bf06b`: `<A HREF="expandedinfolink">%ws</A>`

## pseudocode

```c
__int64 __fastcall PerfDiagDm::ResolverUIBase::ShowDialog(
        PerfDiagDm::ResolverUIBase *this,
        unsigned __int16 a2,
        int a3)
{
  __int64 v5; // rax
  __int64 (__fastcall *v6)(PerfDiagDm::ResolverUIBase *); // rax
  __int64 v7; // rax
  PerfDiagDm *v8; // rcx
  __int64 result; // rax
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // r8
  HRESULT v13; // eax
  HICON hIcon; // rcx
  unsigned int v15; // esi
  DirectUI::DUIXmlParser *v16; // rcx
  _QWORD v17[2]; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD v18[3]; // [rsp+30h] [rbp-D0h] BYREF
  HINSTANCE v19; // [rsp+3Ch] [rbp-C4h]
  int v20; // [rsp+44h] [rbp-BCh]
  int v21; // [rsp+48h] [rbp-B8h]
  __int64 v22; // [rsp+4Ch] [rbp-B4h]
  __int64 v23; // [rsp+5Ch] [rbp-A4h]
  __int64 v24; // [rsp+64h] [rbp-9Ch]
  int v25; // [rsp+6Ch] [rbp-94h]
  __int64 v26; // [rsp+70h] [rbp-90h]
  int v27; // [rsp+78h] [rbp-88h]
  HICON v28; // [rsp+ACh] [rbp-54h]
  unsigned __int16 *v29; // [rsp+B4h] [rbp-4Ch]
  __int64 (__fastcall *v30)(HWND, unsigned int, unsigned __int64, __int64, __int64); // [rsp+BCh] [rbp-44h]
  PerfDiagDm::ResolverUIBase *v31; // [rsp+C4h] [rbp-3Ch]
  SHSTOCKICONINFO psii; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Buffer[264]; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v34[264]; // [rsp+500h] [rbp+400h] BYREF

  *((_DWORD *)this + 12) = a3;
  v17[0] = 0;
  memset_0(v18, 0, 0xA0u);
  v19 = hInstance;
  v23 = a2;
  v5 = *(_QWORD *)this;
  v18[0] = 160;
  v20 = 197;
  v22 = 101;
  v6 = *(__int64 (__fastcall **)(PerfDiagDm::ResolverUIBase *))(v5 + 40);
  v21 = 1;
  v26 = v6(this);
  v7 = *(_QWORD *)this;
  v27 = 2;
  v25 = (*(__int64 (__fastcall **)(PerfDiagDm::ResolverUIBase *))(v7 + 48))(this);
  v31 = this;
  v30 = PerfDiagDm::ResolverUIBase::s_TaskDialogCallback;
  if ( (**(unsigned __int8 (__fastcall ***)(PerfDiagDm::ResolverUIBase *))this)(this) )
  {
    result = PerfDiagDm::InitializeDirectUI(v8);
    if ( (int)result < 0 )
      return result;
    v10 = (*(__int64 (__fastcall **)(PerfDiagDm::ResolverUIBase *))(*(_QWORD *)this + 8LL))(this);
    v20 |= 0x100000u;
    v11 = v10;
  }
  else
  {
    v11 = 0;
    v10 = (*(__int64 (__fastcall **)(PerfDiagDm::ResolverUIBase *))(*(_QWORD *)this + 16LL))(this);
  }
  v24 = v10;
  memset_0(Buffer, 0, 0x208u);
  memset_0(v34, 0, 0x208u);
  memset_0(&psii, 0, sizeof(psii));
  if ( LoadStringW(hInstance, 0x68u, Buffer, 260)
    && (int)StringCchPrintfW(v34, 0x104u, L"<A HREF=\"expandedinfolink\">%ws</A>", Buffer, v17[0]) >= 0 )
  {
    psii.cbSize = 544;
    v29 = v34;
    v13 = SHGetStockIconInfo(SIID_SHIELD, 0x101u, &psii);
    hIcon = v28;
    if ( v13 >= 0 )
      hIcon = psii.hIcon;
    v28 = hIcon;
  }
  v15 = IsolationAwareTaskDialogIndirect(v18, (char *)v17 + 4, v12, v17);
  if ( (**(unsigned __int8 (__fastcall ***)(PerfDiagDm::ResolverUIBase *))this)(this) )
  {
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v16 = (DirectUI::DUIXmlParser *)*((_QWORD *)this + 3);
    if ( v16 )
    {
      DirectUI::DUIXmlParser::Destroy(v16);
      *((_QWORD *)this + 3) = 0;
    }
    UnInitThread();
    UnInitProcessPriv(&_ImageBase);
    CoUninitialize();
  }
  return v15;
}

```

## disassembly

```asm
0x1800beef4  mov     [rsp-8+arg_10], rbx
0x1800beef9  push    rbp
0x1800beefa  push    rsi
0x1800beefb  push    rdi
0x1800beefc  lea     rbp, [rsp-620h]
0x1800bef04  sub     rsp, 720h
0x1800bef0b  mov     rax, cs:__security_cookie
0x1800bef12  xor     rax, rsp
0x1800bef15  mov     [rbp+630h+var_20], rax
0x1800bef1c  mov     [rcx+30h], r8d
0x1800bef20  mov     rdi, rcx
0x1800bef23  mov     ebx, edx
0x1800bef25  lea     rcx, [rsp+730h+var_700]; void *
0x1800bef2a  mov     esi, 0A0h
0x1800bef2f  mov     [rsp+730h+var_70C], 0
0x1800bef37  mov     r8d, esi; Size
0x1800bef3a  mov     [rsp+730h+var_710], 0
0x1800bef42  xor     edx, edx; Val
0x1800bef44  call    memset_0
0x1800bef49  mov     rax, cs:hInstance
0x1800bef50  mov     rcx, rdi
0x1800bef53  mov     [rsp+730h+var_6F4], rax
0x1800bef58  movzx   eax, bx
0x1800bef5b  mov     [rsp+730h+var_6D4], rax
0x1800bef60  mov     rax, [rdi]
0x1800bef63  mov     [rsp+730h+var_700], esi
0x1800bef67  mov     [rsp+730h+var_6EC], 0C5h
0x1800bef6f  mov     [rsp+730h+var_6E4], 65h ; 'e'
0x1800bef78  mov     rax, [rax+28h]
0x1800bef7c  mov     [rsp+730h+var_6E8], 1
0x1800bef84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bef89  mov     [rsp+730h+var_6C0], rax
0x1800bef8e  mov     rcx, rdi
0x1800bef91  mov     rax, [rdi]
0x1800bef94  mov     [rsp+730h+var_6B8], 2
0x1800bef9c  mov     rax, [rax+30h]
0x1800befa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800befa5  mov     [rsp+730h+var_6C4], eax
0x1800befa9  mov     rcx, rdi
0x1800befac  lea     rax, ?s_TaskDialogCallback@ResolverUIBase@PerfDiagDm@@CAJPEAUHWND__@@I_K_J2@Z; PerfDiagDm::ResolverUIBase::s_TaskDialogCallback(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x1800befb3  mov     [rbp+630h+var_66C], rdi
0x1800befb7  mov     [rbp+630h+var_674], rax
0x1800befbb  mov     rax, [rdi]
0x1800befbe  mov     rax, [rax]
0x1800befc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800befc6  test    al, al
0x1800befc8  jz      short loc_1800BEFF1
0x1800befca  call    ?InitializeDirectUI@PerfDiagDm@@YAJXZ; PerfDiagDm::InitializeDirectUI(void)
0x1800befcf  test    eax, eax
0x1800befd1  js      loc_1800BF123
0x1800befd7  mov     rax, [rdi]
0x1800befda  mov     rcx, rdi
0x1800befdd  mov     rax, [rax+8]
0x1800befe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800befe6  bts     [rsp+730h+var_6EC], 14h
0x1800befec  mov     rbx, rax
0x1800befef  jmp     short loc_1800BF002
0x1800beff1  mov     rax, [rdi]
0x1800beff4  xor     ebx, ebx
0x1800beff6  mov     rcx, rdi
0x1800beff9  mov     rax, [rax+10h]
0x1800beffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf002  mov     esi, 208h
0x1800bf007  mov     [rsp+730h+var_6CC], rax
0x1800bf00c  mov     r8d, esi; Size
0x1800bf00f  lea     rcx, [rbp+630h+Buffer]; void *
0x1800bf016  xor     edx, edx; Val
0x1800bf018  call    memset_0
0x1800bf01d  mov     r8d, esi; Size
0x1800bf020  lea     rcx, [rbp+630h+var_230]; void *
0x1800bf027  xor     edx, edx; Val
0x1800bf029  call    memset_0
0x1800bf02e  xor     edx, edx; Val
0x1800bf030  lea     r8d, [rsi+18h]; Size
0x1800bf034  lea     rcx, [rbp+630h+psii]; void *
0x1800bf038  call    memset_0
0x1800bf03d  mov     rcx, cs:hInstance; hInstance
0x1800bf044  lea     r8, [rbp+630h+Buffer]; lpBuffer
0x1800bf04b  mov     esi, 104h
0x1800bf050  mov     edx, 68h ; 'h'; uID
0x1800bf055  mov     r9d, esi; cchBufferMax
0x1800bf058  call    cs:__imp_LoadStringW
0x1800bf05e  test    eax, eax
0x1800bf060  jz      short loc_1800BF0B5
0x1800bf062  lea     r9, [rbp+630h+Buffer]
0x1800bf069  mov     edx, esi; unsigned __int64
0x1800bf06b  lea     r8, aAHrefExpandedi; "<A HREF=\"expandedinfolink\">%ws</A>"
0x1800bf072  lea     rcx, [rbp+630h+var_230]; unsigned __int16 *
0x1800bf079  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800bf07e  test    eax, eax
0x1800bf080  js      short loc_1800BF0B5
0x1800bf082  lea     rax, [rbp+630h+var_230]
0x1800bf089  mov     [rbp+630h+psii.cbSize], 220h
0x1800bf090  lea     r8, [rbp+630h+psii]; psii
0x1800bf094  mov     [rbp+630h+var_67C], rax
0x1800bf098  lea     edx, [rsi-3]; uFlags
0x1800bf09b  mov     ecx, 4Dh ; 'M'; siid
0x1800bf0a0  call    cs:__imp_SHGetStockIconInfo
0x1800bf0a6  mov     rcx, [rbp+630h+var_684]
0x1800bf0aa  test    eax, eax
0x1800bf0ac  cmovns  rcx, [rbp+630h+psii.hIcon]
0x1800bf0b1  mov     [rbp+630h+var_684], rcx
0x1800bf0b5  lea     r9, [rsp+730h+var_710]
0x1800bf0ba  lea     rdx, [rsp+730h+var_70C]
0x1800bf0bf  lea     rcx, [rsp+730h+var_700]
0x1800bf0c4  call    IsolationAwareTaskDialogIndirect
0x1800bf0c9  mov     rcx, [rdi]
0x1800bf0cc  mov     esi, eax
0x1800bf0ce  mov     rax, [rcx]
0x1800bf0d1  mov     rcx, rdi
0x1800bf0d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf0d9  test    al, al
0x1800bf0db  jz      short loc_1800BF121
0x1800bf0dd  test    rbx, rbx
0x1800bf0e0  jz      short loc_1800BF0F1
0x1800bf0e2  mov     rcx, [rbx]
0x1800bf0e5  mov     rax, [rcx+10h]
0x1800bf0e9  mov     rcx, rbx
0x1800bf0ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf0f1  mov     rcx, [rdi+18h]
0x1800bf0f5  test    rcx, rcx
0x1800bf0f8  jz      short loc_1800BF108
0x1800bf0fa  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x1800bf100  mov     qword ptr [rdi+18h], 0
0x1800bf108  call    cs:__imp_UnInitThread
0x1800bf10e  lea     rcx, __ImageBase
0x1800bf115  call    cs:__imp_UnInitProcessPriv
0x1800bf11b  call    cs:__imp_CoUninitialize
0x1800bf121  mov     eax, esi
0x1800bf123  mov     rcx, [rbp+630h+var_20]
0x1800bf12a  xor     rcx, rsp; StackCookie
0x1800bf12d  call    __security_check_cookie
0x1800bf132  mov     rbx, [rsp+730h+arg_10]
0x1800bf13a  add     rsp, 720h
0x1800bf141  pop     rdi
0x1800bf142  pop     rsi
0x1800bf143  pop     rbp
0x1800bf144  retn
```
