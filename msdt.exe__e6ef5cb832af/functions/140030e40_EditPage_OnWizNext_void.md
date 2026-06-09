# EditPage::OnWizNext(void)

- ea: `0x140030e40`
- end: `0x140030fc9`
- name: `?OnWizNext@EditPage@@MEAA_JXZ`
- size: `393`
- prototype: `__int64 __fastcall(EditPage *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x140020420`
- `0x140029e80`
- `0x14002a0b8`
- `0x14002d82c`
- `0x140030e40`
- `0x140030fd0`
- `0x140063010`

## import_xrefs

- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x140030fa4`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x140030fa4`
- `DUI70!StrToID` at `0x140030eae`
- `DUI70!StrToID` at `0x140030eae`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x140030ec0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x140030ec0`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x140030e9c`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x140030e9c`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x140030f66`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x140030f66`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x140030f09`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x140030f09`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x140030f1d`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x140030f1d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EditPage::OnWizNext(EditPage *this)
{
  const unsigned __int16 *v2; // rsi
  DirectUI::Element *Element; // rbx
  unsigned __int16 v4; // ax
  DirectUI::Element *Descendent; // rax
  __int64 v6; // rbx
  const unsigned __int16 *String; // rbx
  _BYTE v9[80]; // [rsp+30h] [rbp-58h] BYREF
  struct DirectUI::Value *v10; // [rsp+90h] [rbp+8h] BYREF

  if ( !(*(unsigned int (__fastcall **)(EditPage *))(*(_QWORD *)this + 264LL))(this)
    || (v2 = L"fileedit", !*((_DWORD *)this + 56)) )
  {
    v2 = L"edit";
  }
  v10 = 0;
  if ( *((_QWORD *)this + 27) )
  {
    Element = DirectUI::TaskPage::GetElement(this);
    v4 = StrToID(v2);
    Descendent = DirectUI::Element::FindDescendent(Element, v4);
    if ( !Descendent )
    {
      v6 = -1;
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "EditPage::OnWizNext", 1556, -2147418113);
      goto LABEL_12;
    }
    DirectUI::Element::GetContentString(Descendent, &v10);
    String = DirectUI::Value::GetString(v10);
    if ( String )
    {
      ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v9);
      if ( !(unsigned int)ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(*((_QWORD *)this + 27), String, v9, 0) )
      {
        DirectUI::TaskPage::PropSheet_SendMessage(this, 0x48Bu, 0, 2);
        v6 = -1;
        ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v9);
        goto LABEL_12;
      }
      ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(v9);
    }
  }
  v6 = InteractivityPage::OnWizNext(this);
LABEL_12:
  if ( v10 )
    DirectUI::Value::Release(v10);
  return v6;
}

```

## disassembly

```asm
0x140030e40  mov     [rsp+arg_8], rbx
0x140030e45  mov     [rsp+arg_10], rsi
0x140030e4a  push    rdi
0x140030e4b  sub     rsp, 80h
0x140030e52  mov     rdi, rcx
0x140030e55  mov     rax, [rcx]
0x140030e58  mov     rax, [rax+108h]
0x140030e5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030e64  test    eax, eax
0x140030e66  jz      short loc_140030E78
0x140030e68  cmp     dword ptr [rdi+0E0h], 0
0x140030e6f  lea     rsi, aFileedit; "fileedit"
0x140030e76  jnz     short loc_140030E7F
0x140030e78  lea     rsi, ClassName; "edit"
0x140030e7f  mov     [rsp+88h+arg_0], 0
0x140030e8b  cmp     qword ptr [rdi+0D8h], 0
0x140030e93  jz      loc_140030F8C
0x140030e99  mov     rcx, rdi
0x140030e9c  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x140030ea3  nop     dword ptr [rax+rax+00h]
0x140030ea8  mov     rbx, rax
0x140030eab  mov     rcx, rsi
0x140030eae  call    cs:__imp_StrToID
0x140030eb5  nop     dword ptr [rax+rax+00h]
0x140030eba  movzx   edx, ax
0x140030ebd  mov     rcx, rbx
0x140030ec0  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x140030ec7  nop     dword ptr [rax+rax+00h]
0x140030ecc  test    rax, rax
0x140030ecf  jnz     short loc_140030EFE
0x140030ed1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140030ed5  mov     [rsp+88h+var_68], 8000FFFFh
0x140030edd  mov     r9d, 614h
0x140030ee3  lea     r8, aEditpageOnwizn; "EditPage::OnWizNext"
0x140030eea  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140030ef1  lea     ecx, [rax+1]; Level
0x140030ef4  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140030ef9  jmp     loc_140030F97
0x140030efe  lea     rdx, [rsp+88h+arg_0]
0x140030f06  mov     rcx, rax
0x140030f09  call    cs:__imp_?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetContentString(DirectUI::Value * *)
0x140030f10  nop     dword ptr [rax+rax+00h]
0x140030f15  mov     rcx, [rsp+88h+arg_0]
0x140030f1d  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x140030f24  nop     dword ptr [rax+rax+00h]
0x140030f29  mov     rbx, rax
0x140030f2c  test    rax, rax
0x140030f2f  jz      short loc_140030F8C
0x140030f31  lea     rcx, [rsp+88h+var_58]
0x140030f36  call    ??0?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@_K@Z; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::CAtlREMatchContext<ATL::CAtlRECharTraitsW>(unsigned __int64)
0x140030f3b  nop
0x140030f3c  xor     r9d, r9d
0x140030f3f  lea     r8, [rsp+88h+var_58]
0x140030f44  mov     rdx, rbx
0x140030f47  mov     rcx, [rdi+0D8h]
0x140030f4e  call    ?Match@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@QEAAHPEBGPEAV?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@2@PEAPEBG@Z; ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::Match(ushort const *,ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW> *,ushort const * *)
0x140030f53  test    eax, eax
0x140030f55  jnz     short loc_140030F82
0x140030f57  lea     r9d, [rax+2]
0x140030f5b  xor     r8d, r8d
0x140030f5e  mov     edx, 48Bh
0x140030f63  mov     rcx, rdi
0x140030f66  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x140030f6d  nop     dword ptr [rax+rax+00h]
0x140030f72  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140030f76  lea     rcx, [rsp+88h+var_58]
0x140030f7b  call    ??1?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@XZ; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(void)
0x140030f80  jmp     short loc_140030F97
0x140030f82  lea     rcx, [rsp+88h+var_58]
0x140030f87  call    ??1?$CAtlREMatchContext@VCAtlRECharTraitsW@ATL@@@ATL@@QEAA@XZ; ATL::CAtlREMatchContext<ATL::CAtlRECharTraitsW>::~CAtlREMatchContext<ATL::CAtlRECharTraitsW>(void)
0x140030f8c  mov     rcx, rdi; this
0x140030f8f  call    ?OnWizNext@InteractivityPage@@UEAA_JXZ; InteractivityPage::OnWizNext(void)
0x140030f94  mov     rbx, rax
0x140030f97  mov     rcx, [rsp+88h+arg_0]
0x140030f9f  test    rcx, rcx
0x140030fa2  jz      short loc_140030FB0
0x140030fa4  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x140030fab  nop     dword ptr [rax+rax+00h]
0x140030fb0  mov     rax, rbx
0x140030fb3  lea     r11, [rsp+88h+var_8]
0x140030fbb  mov     rbx, [r11+18h]
0x140030fbf  mov     rsi, [r11+20h]
0x140030fc3  mov     rsp, r11
0x140030fc6  pop     rdi
0x140030fc7  retn
```
