# EditPage::GetUserChoices(tagSAFEARRAY * *)

- ea: `0x14002b100`
- end: `0x14002b29b`
- name: `?GetUserChoices@EditPage@@MEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(EditPage *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x140020420`
- `0x14002b100`
- `0x140063010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14002b20f`
- `OLEAUT32!__imp_SysAllocString` at `0x14002b20f`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b280`
- `OLEAUT32!__imp_SysFreeString` at `0x14002b280`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14002b167`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14002b167`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14002b239`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14002b239`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x14002b263`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x14002b263`
- `DUI70!StrToID` at `0x14002b1be`
- `DUI70!StrToID` at `0x14002b1be`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14002b1d0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14002b1d0`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14002b1ac`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14002b1ac`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x14002b1e4`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x14002b1e4`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x14002b1f5`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x14002b1f5`

## pseudocode

```c
__int64 __fastcall EditPage::GetUserChoices(EditPage *this, struct tagSAFEARRAY **a2)
{
  __int64 v2; // rax
  const unsigned __int16 *v5; // rdi
  SAFEARRAY *v6; // rsi
  OLECHAR *v7; // rdi
  int v8; // r9d
  HRESULT v9; // eax
  unsigned int v10; // ebx
  DirectUI::Element *Element; // rbx
  unsigned __int16 v12; // ax
  DirectUI::Element *Descendent; // rax
  const unsigned __int16 *String; // rax
  const OLECHAR *v15; // rcx
  BSTR v16; // rax
  LONG rgIndices; // [rsp+60h] [rbp+8h] BYREF
  struct DirectUI::Value *v19; // [rsp+70h] [rbp+18h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+78h] [rbp+20h] BYREF

  v2 = *(_QWORD *)this;
  rgIndices = 0;
  v19 = 0;
  if ( !(*(unsigned int (__fastcall **)(EditPage *))(v2 + 264))(this) || (v5 = L"fileedit", !*((_DWORD *)this + 56)) )
    v5 = L"edit";
  rgsabound = (SAFEARRAYBOUND)1LL;
  v6 = SafeArrayCreate(8u, 1u, &rgsabound);
  if ( !v6 )
  {
    v7 = 0;
    v8 = 1774;
LABEL_6:
    v9 = -2147024882;
    v10 = -2147024882;
LABEL_7:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EditPage::GetUserChoices", v8, v9);
    goto LABEL_15;
  }
  Element = DirectUI::TaskPage::GetElement(this);
  v12 = StrToID(v5);
  Descendent = DirectUI::Element::FindDescendent(Element, v12);
  DirectUI::Element::GetContentString(Descendent, &v19);
  String = DirectUI::Value::GetString(v19);
  v15 = &word_14006B9B8;
  if ( String )
    v15 = String;
  v16 = SysAllocString(v15);
  v7 = v16;
  if ( !v16 )
  {
    v8 = 1789;
    goto LABEL_6;
  }
  v9 = SafeArrayPutElement(v6, &rgIndices, v16);
  v10 = v9;
  if ( v9 < 0 )
  {
    v8 = 1795;
    goto LABEL_7;
  }
  *a2 = v6;
LABEL_15:
  if ( v19 )
  {
    DirectUI::Value::Release(v19);
    v19 = 0;
  }
  if ( v7 )
    SysFreeString(v7);
  return v10;
}

```

## disassembly

```asm
0x14002b100  push    rbx
0x14002b102  push    rsi
0x14002b103  push    rdi
0x14002b104  push    r14
0x14002b106  push    r15
0x14002b108  sub     rsp, 30h
0x14002b10c  mov     rax, [rcx]
0x14002b10f  mov     r14, rdx
0x14002b112  mov     rbx, rcx
0x14002b115  mov     [rsp+58h+rgIndices], 0
0x14002b11d  mov     [rsp+58h+arg_10], 0
0x14002b126  mov     rax, [rax+108h]
0x14002b12d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b132  test    eax, eax
0x14002b134  jz      short loc_14002B146
0x14002b136  cmp     dword ptr [rbx+0E0h], 0
0x14002b13d  lea     rdi, aFileedit; "fileedit"
0x14002b144  jnz     short loc_14002B14D
0x14002b146  lea     rdi, ClassName; "edit"
0x14002b14d  mov     ecx, 8; vt
0x14002b152  mov     qword ptr [rsp+58h+rgsabound.cElements], 1
0x14002b15b  lea     r8, [rsp+58h+rgsabound]; rgsabound
0x14002b160  lea     r15d, [rcx-7]
0x14002b164  mov     edx, r15d; cDims
0x14002b167  call    cs:__imp_SafeArrayCreate
0x14002b16e  nop     dword ptr [rax+rax+00h]
0x14002b173  mov     rsi, rax
0x14002b176  test    rax, rax
0x14002b179  jnz     short loc_14002B1A9
0x14002b17b  xor     edi, edi
0x14002b17d  mov     r9d, 6EEh
0x14002b183  mov     eax, 8007000Eh
0x14002b188  mov     ebx, eax
0x14002b18a  lea     r8, aEditpageGetuse; "EditPage::GetUserChoices"
0x14002b191  mov     [rsp+58h+var_38], eax
0x14002b195  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002b19c  mov     ecx, r15d; Level
0x14002b19f  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002b1a4  jmp     loc_14002B259
0x14002b1a9  mov     rcx, rbx
0x14002b1ac  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x14002b1b3  nop     dword ptr [rax+rax+00h]
0x14002b1b8  mov     rcx, rdi
0x14002b1bb  mov     rbx, rax
0x14002b1be  call    cs:__imp_StrToID
0x14002b1c5  nop     dword ptr [rax+rax+00h]
0x14002b1ca  movzx   edx, ax
0x14002b1cd  mov     rcx, rbx
0x14002b1d0  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x14002b1d7  nop     dword ptr [rax+rax+00h]
0x14002b1dc  mov     rcx, rax
0x14002b1df  lea     rdx, [rsp+58h+arg_10]
0x14002b1e4  call    cs:__imp_?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetContentString(DirectUI::Value * *)
0x14002b1eb  nop     dword ptr [rax+rax+00h]
0x14002b1f0  mov     rcx, [rsp+58h+arg_10]
0x14002b1f5  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x14002b1fc  nop     dword ptr [rax+rax+00h]
0x14002b201  test    rax, rax
0x14002b204  lea     rcx, word_14006B9B8
0x14002b20b  cmovnz  rcx, rax; psz
0x14002b20f  call    cs:__imp_SysAllocString
0x14002b216  nop     dword ptr [rax+rax+00h]
0x14002b21b  mov     rdi, rax
0x14002b21e  test    rax, rax
0x14002b221  jnz     short loc_14002B22E
0x14002b223  mov     r9d, 6FDh
0x14002b229  jmp     loc_14002B183
0x14002b22e  mov     r8, rax; pv
0x14002b231  lea     rdx, [rsp+58h+rgIndices]; rgIndices
0x14002b236  mov     rcx, rsi; psa
0x14002b239  call    cs:__imp_SafeArrayPutElement
0x14002b240  nop     dword ptr [rax+rax+00h]
0x14002b245  mov     ebx, eax
0x14002b247  test    eax, eax
0x14002b249  jns     short loc_14002B256
0x14002b24b  mov     r9d, 703h
0x14002b251  jmp     loc_14002B18A
0x14002b256  mov     [r14], rsi
0x14002b259  mov     rcx, [rsp+58h+arg_10]
0x14002b25e  test    rcx, rcx
0x14002b261  jz      short loc_14002B278
0x14002b263  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x14002b26a  nop     dword ptr [rax+rax+00h]
0x14002b26f  mov     [rsp+58h+arg_10], 0
0x14002b278  test    rdi, rdi
0x14002b27b  jz      short loc_14002B28C
0x14002b27d  mov     rcx, rdi; bstrString
0x14002b280  call    cs:__imp_SysFreeString
0x14002b287  nop     dword ptr [rax+rax+00h]
0x14002b28c  mov     eax, ebx
0x14002b28e  add     rsp, 30h
0x14002b292  pop     r15
0x14002b294  pop     r14
0x14002b296  pop     rdi
0x14002b297  pop     rsi
0x14002b298  pop     rbx
0x14002b299  retn
```
