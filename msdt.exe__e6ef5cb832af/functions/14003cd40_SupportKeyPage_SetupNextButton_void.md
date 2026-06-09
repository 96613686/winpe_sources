# SupportKeyPage::SetupNextButton(void)

- ea: `0x14003cd40`
- end: `0x14003ce62`
- name: `?SetupNextButton@SupportKeyPage@@IEAAJXZ`
- size: `290`
- prototype: `__int64 __fastcall(SupportKeyPage *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x14003b1c0`
- `0x14003b260`
- `0x14003b500`

## callees

- `0x140010eb4`
- `0x140020420`
- `0x14003cd40`

## import_xrefs

- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x14003ce43`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x14003ce43`
- `DUI70!StrToID` at `0x14003cd72`
- `DUI70!StrToID` at `0x14003cd72`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14003cd84`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14003cd84`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14003cd5c`
- `DUI70!?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ` at `0x14003cd5c`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14003ce2d`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14003ce2d`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x14003cdc8`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x14003cdc8`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x14003cdd9`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x14003cdd9`

## pseudocode

```c
__int64 __fastcall SupportKeyPage::SetupNextButton(SupportKeyPage *this)
{
  DirectUI::Element *Element; // rbx
  unsigned __int16 v3; // ax
  DirectUI::Element *Descendent; // rax
  unsigned int v5; // ebx
  const unsigned __int16 *String; // rax
  __int64 v7; // r9
  unsigned __int64 v8; // rcx
  int v9; // eax
  unsigned __int64 v10; // r8
  unsigned int v12; // [rsp+48h] [rbp+10h] BYREF
  struct DirectUI::Value *v13; // [rsp+50h] [rbp+18h] BYREF

  v13 = 0;
  v12 = 0;
  Element = DirectUI::TaskPage::GetElement(this);
  v3 = StrToID(L"edit");
  Descendent = DirectUI::Element::FindDescendent(Element, v3);
  if ( Descendent )
  {
    v5 = 0;
    DirectUI::Element::GetContentString(Descendent, &v13);
    String = DirectUI::Value::GetString(v13);
    v7 = 2;
    if ( !String )
      goto LABEL_10;
    v8 = -1;
    do
      ++v8;
    while ( String[v8] );
    v9 = ULongLongToULong(v8, &v12);
    v5 = v9;
    if ( v9 < 0 )
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "SupportKeyPage::SetupNextButton", 364, v9);
      goto LABEL_12;
    }
    v10 = v7;
    if ( !v12 )
LABEL_10:
      v10 = 0;
    DirectUI::TaskPage::PropSheet_SendMessage(this, 0x48Bu, v10, v7);
  }
  else
  {
    v5 = -2147467259;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "SupportKeyPage::SetupNextButton", 354, -2147467259);
  }
LABEL_12:
  if ( v13 )
    DirectUI::Value::Release(v13);
  return v5;
}

```

## disassembly

```asm
0x14003cd40  mov     rax, rsp
0x14003cd43  mov     [rax+8], rbx
0x14003cd47  mov     [rax+20h], rsi
0x14003cd4b  push    rdi
0x14003cd4c  sub     rsp, 30h
0x14003cd50  xor     esi, esi
0x14003cd52  mov     rdi, rcx
0x14003cd55  mov     [rax+18h], rsi
0x14003cd59  mov     [rax+10h], esi
0x14003cd5c  call    cs:__imp_?GetElement@TaskPage@DirectUI@@IEAAPEAVElement@2@XZ; DirectUI::TaskPage::GetElement(void)
0x14003cd63  nop     dword ptr [rax+rax+00h]
0x14003cd68  lea     rcx, ClassName; "edit"
0x14003cd6f  mov     rbx, rax
0x14003cd72  call    cs:__imp_StrToID
0x14003cd79  nop     dword ptr [rax+rax+00h]
0x14003cd7e  movzx   edx, ax
0x14003cd81  mov     rcx, rbx
0x14003cd84  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x14003cd8b  nop     dword ptr [rax+rax+00h]
0x14003cd90  test    rax, rax
0x14003cd93  jnz     short loc_14003CDBE
0x14003cd95  mov     ebx, 80004005h
0x14003cd9a  mov     r9d, 162h
0x14003cda0  mov     [rsp+38h+var_18], ebx
0x14003cda4  lea     r8, aSupportkeypage; "SupportKeyPage::SetupNextButton"
0x14003cdab  mov     ecx, 1; Level
0x14003cdb0  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14003cdb7  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14003cdbc  jmp     short loc_14003CE39
0x14003cdbe  lea     rdx, [rsp+38h+arg_10]
0x14003cdc3  mov     rcx, rax
0x14003cdc6  mov     ebx, esi
0x14003cdc8  call    cs:__imp_?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetContentString(DirectUI::Value * *)
0x14003cdcf  nop     dword ptr [rax+rax+00h]
0x14003cdd4  mov     rcx, [rsp+38h+arg_10]
0x14003cdd9  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x14003cde0  nop     dword ptr [rax+rax+00h]
0x14003cde5  mov     r9d, 2
0x14003cdeb  test    rax, rax
0x14003cdee  jz      short loc_14003CE22
0x14003cdf0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x14003cdf4  inc     rcx; unsigned __int64
0x14003cdf7  cmp     [rax+rcx*2], si
0x14003cdfb  jnz     short loc_14003CDF4
0x14003cdfd  lea     rdx, [rsp+38h+arg_8]; unsigned int *
0x14003ce02  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x14003ce07  mov     ebx, eax
0x14003ce09  test    eax, eax
0x14003ce0b  jns     short loc_14003CE19
0x14003ce0d  mov     [rsp+38h+var_18], eax
0x14003ce11  mov     r9d, 16Ch
0x14003ce17  jmp     short loc_14003CDA4
0x14003ce19  mov     r8, r9
0x14003ce1c  cmp     [rsp+38h+arg_8], esi
0x14003ce20  jnz     short loc_14003CE25
0x14003ce22  mov     r8, rsi
0x14003ce25  mov     edx, 48Bh
0x14003ce2a  mov     rcx, rdi
0x14003ce2d  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x14003ce34  nop     dword ptr [rax+rax+00h]
0x14003ce39  mov     rcx, [rsp+38h+arg_10]
0x14003ce3e  test    rcx, rcx
0x14003ce41  jz      short loc_14003CE4F
0x14003ce43  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x14003ce4a  nop     dword ptr [rax+rax+00h]
0x14003ce4f  mov     rsi, [rsp+38h+arg_18]
0x14003ce54  mov     eax, ebx
0x14003ce56  mov     rbx, [rsp+38h+arg_0]
0x14003ce5b  add     rsp, 30h
0x14003ce5f  pop     rdi
0x14003ce60  retn
```
