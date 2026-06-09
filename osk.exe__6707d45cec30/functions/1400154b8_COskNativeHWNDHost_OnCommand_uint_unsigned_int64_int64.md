# COskNativeHWNDHost::OnCommand(uint,unsigned __int64,__int64)

- ea: `0x1400154b8`
- end: `0x14001567d`
- name: `?OnCommand@COskNativeHWNDHost@@AEAAXI_K_J@Z`
- size: `453`
- prototype: `void __fastcall(COskNativeHWNDHost *__hidden this, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400156e0`

## callees

- `0x14000dd8c`
- `0x140012db0`
- `0x1400154b8`
- `0x140016a5c`
- `0x140016abc`
- `0x14001a4d8`
- `0x14001a894`
- `0x14001b7bc`
- `0x140025d70`
- `0x140027010`

## import_xrefs

- `USER32!GetForegroundWindow` at `0x14001556c`
- `USER32!GetForegroundWindow` at `0x14001556c`
- `ole32!CoCreateInstance` at `0x1400155f6`
- `ole32!CoCreateInstance` at `0x1400155f6`

## pseudocode

```c
void __fastcall COskNativeHWNDHost::OnCommand(HWND *this, __int64 a2, __int64 a3, unsigned int a4)
{
  unsigned __int16 v5; // r14
  int v6; // edx
  HWND v7; // rdi
  HWND ForegroundWindow; // rax
  int v9; // r8d
  HWND v10; // rbx
  COSKPredictionManager *v11; // rcx
  LPVOID ppv[2]; // [rsp+30h] [rbp-48h] BYREF

  v5 = a4;
  if ( (unsigned __int16)a3 == 5100 )
  {
    if ( (Microsoft_Windows_oskEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer((unsigned int)(unsigned __int16)a3 - 5100, LaunchOptionsDlg_Start, a3, 1, ppv);
    v6 = 5100;
    goto LABEL_24;
  }
  if ( (unsigned __int16)a3 == 5102 )
  {
    LOBYTE(a2) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::GetImpl'::`2'::impl,
      a2);
    if ( !COSKUtils::ShouldRunSecureOnLockScreen() )
    {
      ppv[0] = 0;
      if ( CoCreateInstance(
             &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
             0,
             1u,
             &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
             ppv) >= 0 )
      {
        (*(void (__fastcall **)(LPVOID, const wchar_t *))(*(_QWORD *)ppv[0] + 24LL))(
          ppv[0],
          L"mshelp://windows/?id=106e6689-2545-4d29-8821-f0c22259a63a");
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv[0] + 16LL))(ppv[0]);
      }
    }
  }
  else
  {
    if ( (unsigned __int16)a3 != 5103 )
    {
      if ( (unsigned __int16)a3 != 5104 )
      {
        if ( (unsigned __int16)a3 == 5105 )
        {
          if ( a4 )
            (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)COSKKeyboardManager::s_pCOSKKeyboardManager
                                                               + 10)
                                                            + 64LL))(
              *((_QWORD *)COSKKeyboardManager::s_pCOSKKeyboardManager + 10),
              a4,
              102);
        }
        else if ( (unsigned __int16)a3 == 5106 )
        {
          COSKPredictionManager::InsertPredictionInternal(
            (COSKPredictionManager *)((unsigned int)(unsigned __int16)a3 - 5105),
            a4);
        }
        return;
      }
      v6 = 5104;
LABEL_24:
      COskNativeHWNDHost::ShowOSKModelessDialog((COskNativeHWNDHost *)this, v6);
      return;
    }
    if ( WORD1(a3) == 1 )
    {
      v7 = this[1];
      ForegroundWindow = GetForegroundWindow();
      v9 = 1040;
      v10 = ForegroundWindow;
      if ( v7 != ForegroundWindow )
        v9 = 0;
      COskNativeHWNDHost::ShowOSKToolTip((COskNativeHWNDHost *)this, v7 == ForegroundWindow, v9);
      if ( v7 != v10 && COSKPredictionManager::s_pCOSKPredictionManager )
        COSKPredictionManager::ProcessKeyPressInternal(v11, v5);
      ++COskNativeHWNDHost::m_keyCount;
    }
  }
}

```

## disassembly

```asm
0x1400154b8  mov     [rsp+arg_8], rbx
0x1400154bd  push    rbp
0x1400154be  push    rsi
0x1400154bf  push    rdi
0x1400154c0  push    r14
0x1400154c2  push    r15
0x1400154c4  sub     rsp, 50h
0x1400154c8  mov     rax, cs:__security_cookie
0x1400154cf  xor     rax, rsp
0x1400154d2  mov     [rsp+78h+var_38], rax
0x1400154d7  mov     r15, rcx
0x1400154da  mov     ebx, 13ECh
0x1400154df  movzx   ecx, r8w
0x1400154e3  mov     r14, r9
0x1400154e6  sub     ecx, ebx
0x1400154e8  jz      loc_14001562B
0x1400154ee  sub     ecx, 2
0x1400154f1  jz      loc_1400155B1
0x1400154f7  sub     ecx, 1
0x1400154fa  jz      short loc_140015555
0x1400154fc  sub     ecx, 1
0x1400154ff  jz      short loc_14001554B
0x140015501  sub     ecx, 1; this
0x140015504  jz      short loc_14001551D
0x140015506  cmp     ecx, 1
0x140015509  jnz     loc_14001565C
0x14001550f  movzx   edx, r14w; unsigned __int16
0x140015513  call    ?InsertPredictionInternal@COSKPredictionManager@@AEAAXG@Z; COSKPredictionManager::InsertPredictionInternal(ushort)
0x140015518  jmp     loc_14001565C
0x14001551d  xor     ebp, ebp
0x14001551f  test    r14d, r14d
0x140015522  jz      loc_14001565C
0x140015528  mov     rax, cs:?s_pCOSKKeyboardManager@COSKKeyboardManager@@0PEAV1@EA; COSKKeyboardManager * COSKKeyboardManager::s_pCOSKKeyboardManager
0x14001552f  lea     r8d, [rbp+66h]
0x140015533  mov     edx, r14d
0x140015536  mov     rcx, [rax+50h]
0x14001553a  mov     rax, [rcx]
0x14001553d  mov     rax, [rax+40h]
0x140015541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015546  jmp     loc_14001565C
0x14001554b  mov     edx, 13F0h
0x140015550  jmp     loc_140015654
0x140015555  shr     r8, 10h
0x140015559  mov     esi, 1
0x14001555e  cmp     si, r8w
0x140015562  jnz     loc_14001565C
0x140015568  mov     rdi, [r15+8]
0x14001556c  call    cs:__imp_GetForegroundWindow
0x140015572  xor     ebp, ebp
0x140015574  mov     r8d, 410h
0x14001557a  cmp     rdi, rax
0x14001557d  mov     rcx, r15; this
0x140015580  mov     rbx, rax
0x140015583  cmovnz  r8d, ebp; int
0x140015587  setz    dl; bool
0x14001558a  call    ?ShowOSKToolTip@COskNativeHWNDHost@@AEAAX_NH@Z; COskNativeHWNDHost::ShowOSKToolTip(bool,int)
0x14001558f  cmp     rdi, rbx
0x140015592  jz      short loc_1400155A6
0x140015594  cmp     cs:?s_pCOSKPredictionManager@COSKPredictionManager@@0PEAV1@EA, rbp; COSKPredictionManager * COSKPredictionManager::s_pCOSKPredictionManager
0x14001559b  jz      short loc_1400155A6
0x14001559d  movzx   edx, r14w; unsigned __int16
0x1400155a1  call    ?ProcessKeyPressInternal@COSKPredictionManager@@AEAAXG@Z; COSKPredictionManager::ProcessKeyPressInternal(ushort)
0x1400155a6  add     cs:?m_keyCount@COskNativeHWNDHost@@0IA, esi; uint COskNativeHWNDHost::m_keyCount
0x1400155ac  jmp     loc_14001565C
0x1400155b1  mov     esi, 1
0x1400155b6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen> `wil::Feature<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::GetImpl(void)'::`2'::impl
0x1400155bd  mov     dl, sil
0x1400155c0  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1400155c5  call    ?ShouldRunSecureOnLockScreen@COSKUtils@@SA_NXZ; COSKUtils::ShouldRunSecureOnLockScreen(void)
0x1400155ca  xor     ebp, ebp
0x1400155cc  test    al, al
0x1400155ce  jnz     loc_14001565C
0x1400155d4  lea     rax, [rsp+78h+var_48]
0x1400155d9  mov     [rsp+78h+var_48], rbp
0x1400155de  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x1400155e5  mov     [rsp+78h+ppv], rax; ppv
0x1400155ea  mov     r8d, esi; dwClsContext
0x1400155ed  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x1400155f4  xor     edx, edx; pUnkOuter
0x1400155f6  call    cs:__imp_CoCreateInstance
0x1400155fc  test    eax, eax
0x1400155fe  js      short loc_14001565C
0x140015600  mov     rcx, [rsp+78h+var_48]
0x140015605  lea     rdx, aMshelpWindowsI; "mshelp://windows/?id=106e6689-2545-4d29"...
0x14001560c  mov     rax, [rcx]
0x14001560f  mov     rax, [rax+18h]
0x140015613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015618  mov     rcx, [rsp+78h+var_48]
0x14001561d  mov     rax, [rcx]
0x140015620  mov     rax, [rax+10h]
0x140015624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015629  jmp     short loc_14001565C
0x14001562b  mov     esi, 1
0x140015630  test    cs:Microsoft_Windows_oskEnableBits, sil
0x140015637  jz      short loc_140015652
0x140015639  lea     rax, [rsp+78h+var_48]
0x14001563e  mov     r9d, esi
0x140015641  lea     rdx, LaunchOptionsDlg_Start
0x140015648  mov     [rsp+78h+ppv], rax
0x14001564d  call    McGenEventWrite_EventWriteTransfer
0x140015652  mov     edx, ebx; int
0x140015654  mov     rcx, r15; this
0x140015657  call    ?ShowOSKModelessDialog@COskNativeHWNDHost@@AEAAXH@Z; COskNativeHWNDHost::ShowOSKModelessDialog(int)
0x14001565c  mov     rcx, [rsp+78h+var_38]
0x140015661  xor     rcx, rsp; StackCookie
0x140015664  call    __security_check_cookie
0x140015669  mov     rbx, [rsp+78h+arg_8]
0x140015671  add     rsp, 50h
0x140015675  pop     r15
0x140015677  pop     r14
0x140015679  pop     rdi
0x14001567a  pop     rsi
0x14001567b  pop     rbp
0x14001567c  retn
```
