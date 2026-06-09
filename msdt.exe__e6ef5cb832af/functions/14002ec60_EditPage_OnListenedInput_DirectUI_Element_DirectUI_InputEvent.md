# EditPage::OnListenedInput(DirectUI::Element *,DirectUI::InputEvent *)

- ea: `0x14002ec60`
- end: `0x14002eda0`
- name: `?OnListenedInput@EditPage@@MEAAXPEAVElement@DirectUI@@PEAUInputEvent@3@@Z`
- size: `320`
- prototype: `void __fastcall(EditPage *__hidden this, struct DirectUI::Element *, struct DirectUI::InputEvent *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x140029e80`
- `0x14002a0b8`
- `0x14002d82c`
- `0x14002ec60`
- `0x140063010`

## import_xrefs

- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x14002ed8a`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x14002ed8a`
- `DUI70!StrToID` at `0x14002ecc6`
- `DUI70!StrToID` at `0x14002ecc6`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14002ecd8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14002ecd8`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14002ecb4`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14002ecb4`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14002ed71`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14002ed71`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x14002ecf9`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x14002ecf9`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x14002ed0d`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x14002ed0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall EditPage::OnListenedInput(EditPage *this, struct DirectUI::Element *a2, DirectUI::Element **a3)
{
  const unsigned __int16 *v5; // rsi
  DirectUI::Element *Element; // rbx
  unsigned __int16 v7; // ax
  DirectUI::Element *Descendent; // rax
  const unsigned __int16 *String; // rbx
  int v10; // ebx
  unsigned __int64 v11; // r8
  _BYTE v12[120]; // [rsp+20h] [rbp-78h] BYREF
  struct DirectUI::Value *v13; // [rsp+A0h] [rbp+8h] BYREF

  v13 = 0;
  if ( !(*(unsigned int (__fastcall **)(EditPage *, struct DirectUI::Element *))(*(_QWORD *)this + 264LL))(this, a2)
    || (v5 = L"fileedit", !*((_DWORD *)this + 56)) )
  {
    v5 = L"edit";
  }
  if ( *((_QWORD *)this + 27) )
  {
    Element = DirectUI::TaskPage::GetElement(this);
    v7 = StrToID(v5);
    Descendent = DirectUI::Element::FindDescendent(Element, v7);
    if ( *a3 == Descendent )
    {
      DirectUI::Element::GetContentString(Descendent, &v13);
      String = DirectUI::Value::GetString(v13);
      if ( String
        && (ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v12),
            v10 = ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(*((_QWORD *)this + 27), String, v12, 0),
            ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v12),
            v10) )
      {
        v11 = 2;
      }
      else
      {
        v11 = 0;
      }
      DirectUI::TaskPage::PropSheet_SendMessage(this, 0x48Bu, v11, 2);
    }
  }
  if ( v13 )
    DirectUI::Value::Release(v13);
}

```

## disassembly

```asm
0x14002ec60  mov     rax, rsp
0x14002ec63  push    rbx
0x14002ec64  push    rbp
0x14002ec65  push    rsi
0x14002ec66  push    rdi
0x14002ec67  sub     rsp, 78h
0x14002ec6b  mov     rbp, r8
0x14002ec6e  mov     rdi, rcx
0x14002ec71  mov     qword ptr [rax+8], 0
0x14002ec79  mov     rax, [rcx]
0x14002ec7c  mov     rax, [rax+108h]
0x14002ec83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ec88  test    eax, eax
0x14002ec8a  jz      short loc_14002EC9C
0x14002ec8c  cmp     dword ptr [rdi+0E0h], 0
0x14002ec93  lea     rsi, aFileedit; "fileedit"
0x14002ec9a  jnz     short loc_14002ECA3
0x14002ec9c  lea     rsi, ClassName; "edit"
0x14002eca3  cmp     qword ptr [rdi+0D8h], 0
0x14002ecab  jz      loc_14002ED7D
0x14002ecb1  mov     rcx, rdi
0x14002ecb4  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x14002ecbb  nop     dword ptr [rax+rax+00h]
0x14002ecc0  mov     rbx, rax
0x14002ecc3  mov     rcx, rsi
0x14002ecc6  call    cs:__imp_StrToID
0x14002eccd  nop     dword ptr [rax+rax+00h]
0x14002ecd2  movzx   edx, ax
0x14002ecd5  mov     rcx, rbx
0x14002ecd8  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x14002ecdf  nop     dword ptr [rax+rax+00h]
0x14002ece4  cmp     [rbp+0], rax
0x14002ece8  jnz     loc_14002ED7D
0x14002ecee  lea     rdx, [rsp+98h+arg_0]
0x14002ecf6  mov     rcx, rax
0x14002ecf9  call    cs:__imp_?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetContentString(DirectUI::Value * *)
0x14002ed00  nop     dword ptr [rax+rax+00h]
0x14002ed05  mov     rcx, [rsp+98h+arg_0]
0x14002ed0d  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x14002ed14  nop     dword ptr [rax+rax+00h]
0x14002ed19  mov     rbx, rax
0x14002ed1c  test    rax, rax
0x14002ed1f  jz      short loc_14002ED60
0x14002ed21  lea     rcx, [rsp+98h+var_78]
0x14002ed26  call    ??0?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@_K@Z; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(unsigned __int64)
0x14002ed2b  nop
0x14002ed2c  xor     r9d, r9d
0x14002ed2f  lea     r8, [rsp+98h+var_78]
0x14002ed34  mov     rdx, rbx
0x14002ed37  mov     rcx, [rdi+0D8h]
0x14002ed3e  call    ?Match@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAHPEBGPEAV?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@2@PEAPEBG@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(ushort const *,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW> *,ushort const * *)
0x14002ed43  mov     ebx, eax
0x14002ed45  lea     rcx, [rsp+98h+var_78]
0x14002ed4a  call    ??1?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@XZ; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(void)
0x14002ed4f  test    ebx, ebx
0x14002ed51  jz      short loc_14002ED60
0x14002ed53  mov     eax, 2
0x14002ed58  mov     r9d, eax
0x14002ed5b  mov     r8d, eax
0x14002ed5e  jmp     short loc_14002ED69
0x14002ed60  mov     r9d, 2
0x14002ed66  xor     r8d, r8d
0x14002ed69  mov     edx, 48Bh
0x14002ed6e  mov     rcx, rdi
0x14002ed71  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x14002ed78  nop     dword ptr [rax+rax+00h]
0x14002ed7d  mov     rcx, [rsp+98h+arg_0]
0x14002ed85  test    rcx, rcx
0x14002ed88  jz      short loc_14002ED96
0x14002ed8a  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x14002ed91  nop     dword ptr [rax+rax+00h]
0x14002ed96  add     rsp, 78h
0x14002ed9a  pop     rdi
0x14002ed9b  pop     rsi
0x14002ed9c  pop     rbp
0x14002ed9d  pop     rbx
0x14002ed9e  retn
```
