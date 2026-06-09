# InteractivityPage::SetInteractionIcon(void)

- ea: `0x14003285c`
- end: `0x140032a1f`
- name: `?SetInteractionIcon@InteractivityPage@@QEAAJXZ`
- size: `451`
- prototype: `__int64 __fastcall(InteractivityPage *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14002fc60`

## callees

- `0x14000e6bc`
- `0x14000e978`
- `0x1400108b0`
- `0x140020420`
- `0x14003285c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140032924`
- `KERNEL32!GetLastError` at `0x140032924`
- `USER32!LoadImageW` at `0x14003290b`
- `USER32!LoadImageW` at `0x14003290b`
- `USER32!GetSystemMetrics` at `0x1400328cc`
- `USER32!GetSystemMetrics` at `0x1400328df`
- `USER32!GetSystemMetrics` at `0x1400328cc`
- `USER32!GetSystemMetrics` at `0x1400328df`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1400329a0`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1400329a0`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x140032959`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x140032959`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x1400329ba`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z` at `0x1400329ba`

## pseudocode

```c
__int64 __fastcall InteractivityPage::SetInteractionIcon(InteractivityPage *this)
{
  int NamedElement; // eax
  unsigned int v3; // ebx
  int v4; // r9d
  HICON ImageW; // rax
  int cy; // ebx
  int SystemMetrics; // eax
  signed int LastError; // eax
  struct DirectUI::Value *Graphic; // rsi
  const struct DirectUI::PropertyInfo *v10; // rax
  struct DirectUI::Element *v12; // [rsp+68h] [rbp+10h] BYREF

  v12 = 0;
  NamedElement = WizardPage::ShowNamedElement(this, L"interactionIcon", 1);
  v3 = NamedElement;
  if ( NamedElement < 0 )
  {
    v4 = 1014;
LABEL_19:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "InteractivityPage::SetInteractionIcon", v4, NamedElement);
    return v3;
  }
  NamedElement = WizardPage::ShowNamedElement(this, L"interactionIconViewer", 1);
  v3 = NamedElement;
  if ( NamedElement < 0 )
  {
    v4 = 1016;
    goto LABEL_19;
  }
  ImageW = 0;
  if ( !*((_DWORD *)this + 38)
    || (cy = GetSystemMetrics(12),
        SystemMetrics = GetSystemMetrics(11),
        ImageW = (HICON)LoadImageW(g_hInstance, (LPCWSTR)*((unsigned __int16 *)this + 76), 1u, SystemMetrics, cy, 0),
        (((unsigned __int64)ImageW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0) )
  {
    Graphic = DirectUI::Value::CreateGraphic(ImageW, 0, 0, 0);
    if ( Graphic )
    {
      NamedElement = WizardPage::GetNamedElement(this, L"interactionIcon", &v12);
      v3 = NamedElement;
      if ( NamedElement < 0 )
      {
        v4 = 1038;
        goto LABEL_19;
      }
      v10 = (const struct DirectUI::PropertyInfo *)DirectUI::Element::ContentProp();
      NamedElement = DirectUI::Element::SetValue(v12, v10, 1, Graphic);
      v3 = NamedElement;
      if ( NamedElement < 0 )
      {
        v4 = 1041;
        goto LABEL_19;
      }
      if ( *((_DWORD *)this + 38) == 109 )
      {
        NamedElement = WizardPage::HideNamedElement(this, L"interactionIconViewer");
        v3 = NamedElement;
        if ( NamedElement < 0 )
        {
          v4 = 1046;
          goto LABEL_19;
        }
      }
    }
    else
    {
      v3 = -2147418113;
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "InteractivityPage::SetInteractionIcon", 1032, -2147418113);
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "InteractivityPage::SetInteractionIcon", 1027, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x14003285c  push    rbx
0x14003285e  push    rsi
0x14003285f  push    rdi
0x140032860  push    r14
0x140032862  sub     rsp, 38h
0x140032866  mov     r14d, 1
0x14003286c  mov     [rsp+58h+arg_8], 0
0x140032875  mov     r8d, r14d; int
0x140032878  lea     rdx, aInteractionico; "interactionIcon"
0x14003287f  mov     rdi, rcx
0x140032882  call    ?ShowNamedElement@WizardPage@@IEAAJPEBGH@Z; WizardPage::ShowNamedElement(ushort const *,int)
0x140032887  mov     ebx, eax
0x140032889  test    eax, eax
0x14003288b  jns     short loc_140032898
0x14003288d  mov     r9d, 3F6h
0x140032893  jmp     loc_1400329F8
0x140032898  mov     r8d, r14d; int
0x14003289b  lea     rdx, aInteractionico_0; "interactionIconViewer"
0x1400328a2  mov     rcx, rdi; this
0x1400328a5  call    ?ShowNamedElement@WizardPage@@IEAAJPEBGH@Z; WizardPage::ShowNamedElement(ushort const *,int)
0x1400328aa  mov     ebx, eax
0x1400328ac  test    eax, eax
0x1400328ae  jns     short loc_1400328BB
0x1400328b0  mov     r9d, 3F8h
0x1400328b6  jmp     loc_1400329F8
0x1400328bb  xor     eax, eax
0x1400328bd  cmp     [rdi+98h], eax
0x1400328c3  jz      loc_14003294E
0x1400328c9  lea     ecx, [rax+0Ch]; nIndex
0x1400328cc  call    cs:__imp_GetSystemMetrics
0x1400328d3  nop     dword ptr [rax+rax+00h]
0x1400328d8  mov     ecx, 0Bh; nIndex
0x1400328dd  mov     ebx, eax
0x1400328df  call    cs:__imp_GetSystemMetrics
0x1400328e6  nop     dword ptr [rax+rax+00h]
0x1400328eb  movzx   edx, word ptr [rdi+98h]; name
0x1400328f2  mov     r8d, r14d; type
0x1400328f5  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInst
0x1400328fc  mov     r9d, eax; cx
0x1400328ff  mov     [rsp+58h+fuLoad], 0; fuLoad
0x140032907  mov     [rsp+58h+cy], ebx; cy
0x14003290b  call    cs:__imp_LoadImageW
0x140032912  nop     dword ptr [rax+rax+00h]
0x140032917  lea     rcx, [rax+1]
0x14003291b  test    rcx, 0FFFFFFFFFFFFFFFEh
0x140032922  jnz     short loc_14003294E
0x140032924  call    cs:__imp_GetLastError
0x14003292b  nop     dword ptr [rax+rax+00h]
0x140032930  mov     ebx, eax
0x140032932  test    eax, eax
0x140032934  jle     short loc_14003293F
0x140032936  movzx   ebx, ax
0x140032939  or      ebx, 80070000h
0x14003293f  mov     [rsp+58h+cy], ebx
0x140032943  mov     r9d, 403h
0x140032949  jmp     loc_1400329FC
0x14003294e  xor     r9d, r9d
0x140032951  xor     r8d, r8d
0x140032954  xor     edx, edx
0x140032956  mov     rcx, rax
0x140032959  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z; DirectUI::Value::CreateGraphic(HICON__ *,bool,bool,bool)
0x140032960  nop     dword ptr [rax+rax+00h]
0x140032965  mov     rsi, rax
0x140032968  test    rax, rax
0x14003296b  jnz     short loc_14003297E
0x14003296d  mov     ebx, 8000FFFFh
0x140032972  mov     r9d, 408h
0x140032978  mov     [rsp+58h+cy], ebx
0x14003297c  jmp     short loc_1400329FC
0x14003297e  lea     r8, [rsp+58h+arg_8]; struct DirectUI::Element **
0x140032983  mov     rcx, rdi; this
0x140032986  lea     rdx, aInteractionico; "interactionIcon"
0x14003298d  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x140032992  mov     ebx, eax
0x140032994  test    eax, eax
0x140032996  jns     short loc_1400329A0
0x140032998  mov     r9d, 40Eh
0x14003299e  jmp     short loc_1400329F8
0x1400329a0  call    cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1400329a7  nop     dword ptr [rax+rax+00h]
0x1400329ac  mov     rcx, [rsp+58h+arg_8]
0x1400329b1  mov     r9, rsi
0x1400329b4  mov     rdx, rax
0x1400329b7  mov     r8d, r14d
0x1400329ba  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJPEBUPropertyInfo@2@HPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const *,int,DirectUI::Value *)
0x1400329c1  nop     dword ptr [rax+rax+00h]
0x1400329c6  mov     ebx, eax
0x1400329c8  test    eax, eax
0x1400329ca  jns     short loc_1400329D4
0x1400329cc  mov     r9d, 411h
0x1400329d2  jmp     short loc_1400329F8
0x1400329d4  cmp     dword ptr [rdi+98h], 6Dh ; 'm'
0x1400329db  jnz     short loc_140032A12
0x1400329dd  lea     rdx, aInteractionico_0; "interactionIconViewer"
0x1400329e4  mov     rcx, rdi; this
0x1400329e7  call    ?HideNamedElement@WizardPage@@IEAAJPEBG@Z; WizardPage::HideNamedElement(ushort const *)
0x1400329ec  mov     ebx, eax
0x1400329ee  test    eax, eax
0x1400329f0  jns     short loc_140032A12
0x1400329f2  mov     r9d, 416h
0x1400329f8  mov     [rsp+58h+cy], eax
0x1400329fc  lea     r8, aInteractivityp_4; "InteractivityPage::SetInteractionIcon"
0x140032a03  mov     ecx, r14d; Level
0x140032a06  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x140032a0d  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140032a12  mov     eax, ebx
0x140032a14  add     rsp, 38h
0x140032a18  pop     r14
0x140032a1a  pop     rdi
0x140032a1b  pop     rsi
0x140032a1c  pop     rbx
0x140032a1d  retn
```
