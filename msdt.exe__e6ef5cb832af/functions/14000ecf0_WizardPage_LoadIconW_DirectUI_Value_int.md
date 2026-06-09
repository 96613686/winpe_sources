# WizardPage::LoadIconW(DirectUI::Value * *,int *)

- ea: `0x14000ecf0`
- end: `0x14000ee35`
- name: `?LoadIconW@WizardPage@@IEAAJPEAPEAVValue@DirectUI@@PEAH@Z`
- size: `325`
- prototype: `__int64 __fastcall(WizardPage *__hidden this, struct DirectUI::Value **, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140015580`
- `0x14003b500`

## callees

- `0x14000ecf0`
- `0x140020420`
- `0x140041a90`
- `0x14004a1d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000eded`
- `KERNEL32!GetLastError` at `0x14000eded`
- `USER32!LoadImageW` at `0x14000ed9b`
- `USER32!LoadImageW` at `0x14000ed9b`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x14000ed45`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x14000edc2`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x14000ed45`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x14000edc2`

## pseudocode

```c
__int64 __fastcall WizardPage::LoadIconW(WizardPage *this, struct DirectUI::Value **a2, int *a3)
{
  const unsigned __int16 *v5; // rax
  signed int v6; // ebx
  struct DirectUI::Value *Graphic; // rax
  HICON ImageW; // rcx
  struct DirectUI::Value *v9; // rax
  signed int LastError; // eax
  HICON v12; // [rsp+60h] [rbp+8h] BYREF

  v12 = 0;
  *a3 = 1;
  if ( Packages_Icon() && (v5 = Packages_Icon(), v6 = DwzLoadIcon(v5, &v12), v6 >= 0) )
  {
    Graphic = DirectUI::Value::CreateGraphic(v12, 0, 0, 0);
    *a2 = Graphic;
    if ( Graphic )
    {
      *a3 = 0;
    }
    else
    {
      v6 = -2147418113;
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WizardPage::LoadIconW", 1062, -2147418113);
    }
  }
  else
  {
    ImageW = (HICON)LoadImageW(g_hInstance, (LPCWSTR)0x6B, 1u, 0, 0, 0x40u);
    if ( (unsigned __int64)ImageW - 1 > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WizardPage::LoadIconW", 1080, v6);
    }
    else
    {
      *a2 = 0;
      v9 = DirectUI::Value::CreateGraphic(ImageW, 0, 0, 0);
      *a2 = v9;
      if ( v9 )
      {
        return 0;
      }
      else
      {
        v6 = -2147418113;
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "WizardPage::LoadIconW", 1085, -2147418113);
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000ecf0  mov     [rsp+arg_0], rcx
0x14000ecf5  push    rbx
0x14000ecf6  push    rsi
0x14000ecf7  push    rdi
0x14000ecf8  push    r14
0x14000ecfa  sub     rsp, 38h
0x14000ecfe  mov     r14d, 1
0x14000ed04  mov     [rsp+58h+arg_0], 0
0x14000ed0d  mov     [r8], r14d
0x14000ed10  mov     rdi, r8
0x14000ed13  mov     rsi, rdx
0x14000ed16  call    ?Packages_Icon@@YAPEBGXZ; Packages_Icon(void)
0x14000ed1b  test    rax, rax
0x14000ed1e  jz      short loc_14000ED7A
0x14000ed20  call    ?Packages_Icon@@YAPEBGXZ; Packages_Icon(void)
0x14000ed25  mov     rcx, rax; unsigned __int16 *
0x14000ed28  lea     rdx, [rsp+58h+arg_0]; HICON *
0x14000ed2d  call    ?DwzLoadIcon@@YAJPEBGPEAPEAUHICON__@@@Z; DwzLoadIcon(ushort const *,HICON__ * *)
0x14000ed32  mov     ebx, eax
0x14000ed34  test    eax, eax
0x14000ed36  js      short loc_14000ED7A
0x14000ed38  mov     rcx, [rsp+58h+arg_0]
0x14000ed3d  xor     r9d, r9d
0x14000ed40  xor     r8d, r8d
0x14000ed43  xor     edx, edx
0x14000ed45  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z; DirectUI::Value::CreateGraphic(HICON__ *,bool,bool,bool)
0x14000ed4c  nop     dword ptr [rax+rax+00h]
0x14000ed51  mov     [rsi], rax
0x14000ed54  test    rax, rax
0x14000ed57  jnz     short loc_14000ED6F
0x14000ed59  mov     eax, 8000FFFFh
0x14000ed5e  mov     r9d, 426h
0x14000ed64  mov     ebx, eax
0x14000ed66  mov     [rsp+58h+cy], eax
0x14000ed6a  jmp     loc_14000EE12
0x14000ed6f  mov     dword ptr [rdi], 0
0x14000ed75  jmp     loc_14000EE28
0x14000ed7a  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInst
0x14000ed81  xor     r9d, r9d; cx
0x14000ed84  mov     [rsp+58h+fuLoad], 40h ; '@'; fuLoad
0x14000ed8c  mov     r8d, r14d; type
0x14000ed8f  mov     [rsp+58h+cy], 0; cy
0x14000ed97  lea     edx, [r9+6Bh]; name
0x14000ed9b  call    cs:__imp_LoadImageW
0x14000eda2  nop     dword ptr [rax+rax+00h]
0x14000eda7  mov     rcx, rax
0x14000edaa  dec     rax
0x14000edad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000edb1  ja      short loc_14000EDED
0x14000edb3  xor     r9d, r9d
0x14000edb6  mov     qword ptr [rsi], 0
0x14000edbd  xor     r8d, r8d
0x14000edc0  xor     edx, edx
0x14000edc2  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z; DirectUI::Value::CreateGraphic(HICON__ *,bool,bool,bool)
0x14000edc9  nop     dword ptr [rax+rax+00h]
0x14000edce  mov     [rsi], rax
0x14000edd1  test    rax, rax
0x14000edd4  jnz     short loc_14000EDE9
0x14000edd6  mov     eax, 8000FFFFh
0x14000eddb  mov     r9d, 43Dh
0x14000ede1  mov     ebx, eax
0x14000ede3  mov     [rsp+58h+cy], eax
0x14000ede7  jmp     short loc_14000EE12
0x14000ede9  xor     ebx, ebx
0x14000edeb  jmp     short loc_14000EE28
0x14000eded  call    cs:__imp_GetLastError
0x14000edf4  nop     dword ptr [rax+rax+00h]
0x14000edf9  mov     ebx, eax
0x14000edfb  test    eax, eax
0x14000edfd  jle     short loc_14000EE08
0x14000edff  movzx   ebx, ax
0x14000ee02  or      ebx, 80070000h
0x14000ee08  mov     [rsp+58h+cy], ebx
0x14000ee0c  mov     r9d, 438h
0x14000ee12  lea     r8, aWizardpageLoad; "WizardPage::LoadIconW"
0x14000ee19  mov     ecx, r14d; Level
0x14000ee1c  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14000ee23  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14000ee28  mov     eax, ebx
0x14000ee2a  add     rsp, 38h
0x14000ee2e  pop     r14
0x14000ee30  pop     rdi
0x14000ee31  pop     rsi
0x14000ee32  pop     rbx
0x14000ee33  retn
```
