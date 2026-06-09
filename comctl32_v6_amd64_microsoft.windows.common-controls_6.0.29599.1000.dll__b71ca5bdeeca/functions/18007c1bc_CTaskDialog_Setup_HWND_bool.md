# CTaskDialog::Setup(HWND__ *,bool)

- ea: `0x18007c1bc`
- end: `0x18007c885`
- name: `?Setup@CTaskDialog@@AEAAJPEAUHWND__@@_N@Z`
- size: `1737`
- prototype: `__int64 __fastcall(CTaskDialog *__hidden this, HWND, bool)`
- caller_count: `1`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c5b28`

## callees

- `0x180005a6c`
- `0x180022bec`
- `0x180022c58`
- `0x18006a640`
- `0x18007b798`
- `0x18007bea0`
- `0x18007c1bc`
- `0x18007c88c`
- `0x18007cb88`
- `0x18007cd18`
- `0x18007d274`
- `0x18007d2b4`
- `0x18007d330`
- `0x18007d508`
- `0x18008344c`
- `0x1800849fc`
- `0x1800b2b5c`
- `0x1800d3294`
- `0x1800f71ac`
- `0x1800f9b08`
- `0x1800fde64`
- `0x180101804`
- `0x180102a20`
- `0x180102afc`
- `0x180104f84`
- `0x180106e3c`
- `0x180114520`
- `0x18012cd2c`
- `0x18012cfd4`
- `0x18012d12c`
- `0x18012d2a0`
- `0x18012d3a8`
- `0x18012d498`
- `0x18012d550`
- `0x18012ed40`
- `0x18012f62c`
- `0x18012f68c`
- `0x18012f8e8`
- `0x180130574`
- `0x1801d1010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007c36f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007c3aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007c36f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007c3aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18007c417`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18007c417`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007c7b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007c7b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007c84b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007c84b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x18007c422`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x18007c422`
- `USER32!ShowWindow` at `0x18007c736`
- `USER32!ShowWindow` at `0x18007c736`
- `USER32!SetWindowTextW` at `0x18007c44e`
- `USER32!SetWindowTextW` at `0x18007c44e`
- `USER32!SetTimer` at `0x18007c7d7`
- `USER32!SetTimer` at `0x18007c7d7`
- `USER32!KillTimer` at `0x18007c7a1`
- `USER32!KillTimer` at `0x18007c7a1`
- `USER32!SetWindowLongPtrW` at `0x18007c4de`
- `USER32!SetWindowLongPtrW` at `0x18007c4de`
- `USER32!GetWindowLongPtrW` at `0x18007c4c6`
- `USER32!GetWindowLongPtrW` at `0x18007c4c6`
- `UxTheme!IsThemeActive` at `0x18007c318`
- `UxTheme!IsThemeActive` at `0x18007c318`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007c788`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007c788`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007c755`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18007c755`

## pseudocode

```c
__int64 __fastcall CTaskDialog::Setup(CTaskDialog *this, HWND a2, bool a3)
{
  const struct _TASKDIALOGCONFIG *v6; // rcx
  bool CanBeMinimized; // al
  __int64 v8; // rcx
  int v9; // edx
  char v10; // al
  HWND v11; // rdx
  BOOL v12; // eax
  __int64 v13; // rax
  unsigned int v14; // ebx
  unsigned int v15; // ecx
  HANDLE ProcessHeap; // rax
  __int64 v17; // rax
  int v18; // ebx
  HANDLE v19; // rax
  __int64 v20; // rax
  int inserted; // esi
  __int64 v22; // rdx
  WCHAR *v23; // rbx
  int v24; // eax
  unsigned int v25; // r15d
  int v26; // eax
  LONG_PTR WindowLongPtrW; // rax
  bool v28; // dl
  __int64 v29; // rax
  _QWORD *v30; // r14
  CTaskDialog *v31; // rcx
  HWND v32; // rax
  bool v33; // al
  DWORD TickCount; // eax
  HWND v35; // rcx
  _DWORD *v36; // rax
  int *v37; // rdx
  DirectUI *v38; // r14
  void *v39; // rdx
  unsigned int *ppv; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpString; // [rsp+30h] [rbp-D0h] BYREF
  struct DirectUI::Element *v43; // [rsp+38h] [rbp-C8h] BYREF
  ULONG_PTR ulCookie[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-B0h] BYREF

  ulCookie[0] = 0;
  SHActivateContext(ulCookie);
  v6 = (const struct _TASKDIALOGCONFIG *)*((_QWORD *)this + 41);
  *((_QWORD *)this + 39) = a2;
  CanBeMinimized = CTaskDialog::CanBeMinimized(v6);
  *((_BYTE *)this + 387) = CanBeMinimized;
  if ( CanBeMinimized )
    SetWindowStyle(a2, 0x20000);
  else
    ClearWindowStyle(a2, 0x20000);
  CTaskDialog::SetupCancelCapability(this);
  v8 = *((_QWORD *)this + 41);
  *((_BYTE *)this + 385) = (*(_DWORD *)(v8 + 20) & 0x40) != 0;
  v9 = *(_DWORD *)(v8 + 20) & 0x10;
  *((_BYTE *)this + 394) = v9 != 0;
  if ( (*(_BYTE *)(v8 + 20) & 0x20) != 0 || (v10 = 0, v9) )
    v10 = 1;
  v11 = (HWND)*((_QWORD *)this + 39);
  *((_BYTE *)this + 393) = v10;
  *((_BYTE *)this + 416) = (*(_DWORD *)(v8 + 20) & 0x80) != 0;
  *((_BYTE *)this + 424) = (*(_DWORD *)(v8 + 20) & 0x4000) != 0;
  *((_BYTE *)this + 425) = (*(_DWORD *)(v8 + 20) & 0x800000) != 0;
  *((_BYTE *)this + 426) = *(_BYTE *)(v8 + 23) & 1;
  *((_BYTE *)this + 417) = (*(_DWORD *)(v8 + 20) & 0x1000) != 0;
  *((_QWORD *)this + 44) = *(_QWORD *)(v8 + 140);
  *((_QWORD *)this + 45) = *(_QWORD *)(v8 + 148);
  *((_DWORD *)this + 107) = *(_DWORD *)(v8 + 156);
  *((_DWORD *)this + 97) = 0;
  DPISCALEINFO::Initialize((CTaskDialog *)((char *)this + 848), v11);
  IsWindowAnimationEnabled((bool *)this + 432);
  v12 = IsThemeActive();
  *((_BYTE *)this + 297) = v12;
  if ( !v12 )
    DisableAnimations();
  v13 = *((_QWORD *)this + 41);
  v14 = *(_DWORD *)(v13 + 60);
  *((_DWORD *)this + 94) = v14;
  v15 = *(_DWORD *)(v13 + 24);
  if ( v15 )
  {
    do
    {
      v14 += v15 & 1;
      v15 >>= 1;
    }
    while ( v15 );
    *((_DWORD *)this + 94) = v14;
  }
  if ( !v14 )
  {
    *((_DWORD *)this + 94) = 1;
    v14 = 1;
  }
  *((_DWORD *)this + 95) = 0;
  ProcessHeap = GetProcessHeap();
  v17 = CCHeapAllocArraySize(ProcessHeap, 8, 16, v14);
  *((_QWORD *)this + 43) = v17;
  if ( v17
    && ((v18 = *(_DWORD *)(*((_QWORD *)this + 41) + 76LL), *((_DWORD *)this + 114) = v18, v18 <= 0)
     || (v19 = GetProcessHeap(),
         v20 = CCHeapAllocArraySize(v19, 8, 16, (unsigned int)v18),
         (*((_QWORD *)this + 56) = v20) != 0)) )
  {
    v22 = *((_QWORD *)this + 41);
    lpString = 0;
    inserted = CResolvedString::Resolve(
                 (CResolvedString *)&lpString,
                 *(HINSTANCE *)(v22 + 12),
                 *(const unsigned __int16 **)(v22 + 28));
    if ( inserted >= 0 && (v23 = (WCHAR *)lpString) != 0
      || (GetModuleFileNameW(0, Filename, 0x104u),
          PathStripPathW(Filename),
          v24 = CResolvedString::Resolve((CResolvedString *)&lpString, 0, Filename),
          v23 = (WCHAR *)lpString,
          inserted = v24,
          v24 >= 0) )
    {
      if ( !SetWindowTextW(*((HWND *)this + 39), v23) )
        inserted = -2147467259;
    }
    v43 = 0;
    v25 = 0;
    LODWORD(lpString) = 0;
    if ( inserted >= 0 )
    {
      v26 = DirectUI::HWNDElement::Initialize(this, *((HWND *)this + 39), 1u, 0, 0, (unsigned int *)&lpString);
      v25 = (unsigned int)lpString;
      inserted = v26;
    }
    if ( CTaskDialog::ShouldForceRtlLayout(this) )
      DirectUI::Element::SetDirection(this, 1);
    if ( (*((_BYTE *)this + 152) & 0x40) != 0 )
    {
      WindowLongPtrW = GetWindowLongPtrW(*((HWND *)this + 39), -20);
      SetWindowLongPtrW(*((HWND *)this + 39), -20, WindowLongPtrW | 0x400000);
    }
    if ( inserted >= 0 )
    {
      inserted = (*(__int64 (__fastcall **)(CTaskDialog *, char *))(*(_QWORD *)this + 440LL))(this, (char *)this + 336);
      if ( inserted >= 0 )
      {
        inserted = DirectUI::DUIXmlParser::CreateElement(
                     *((DirectUI::DUIXmlParser **)this + 42),
                     L"main",
                     this,
                     0,
                     ppv,
                     &v43);
        if ( inserted >= 0 )
        {
          inserted = DirectUI::Element::SetAccessible(v43, v28);
          if ( inserted >= 0 )
          {
            inserted = DirectUI::Element::SetAccName(v43, v23);
            if ( inserted >= 0 )
            {
              inserted = CTaskDialog::BuildMainInstructionArea(this);
              if ( inserted >= 0 )
              {
                inserted = CTaskDialog::BuildMainIconArea(this, a3);
                if ( inserted >= 0 )
                {
                  inserted = CTaskDialog::BuildContentArea(this);
                  if ( inserted >= 0 )
                  {
                    inserted = CTaskDialog::BuildProgressArea(this);
                    if ( inserted >= 0 )
                    {
                      inserted = CTaskDialog::BuildFooterExpando(this);
                      if ( inserted >= 0 )
                      {
                        inserted = CTaskDialog::BuildLinkArea(this);
                        if ( inserted >= 0 )
                        {
                          inserted = CTaskDialog::BuildRadioButtonArea(this);
                          if ( inserted >= 0 )
                          {
                            inserted = CTaskDialog::BuildControlArea(this);
                            if ( inserted >= 0 )
                            {
                              inserted = CTaskDialog::BuildFootnoteArea(this);
                              if ( inserted >= 0 )
                              {
                                DirectUI::Element::SetAccRole(this, 16);
                                v29 = *((_QWORD *)this + 80);
                                v30 = (_QWORD *)((char *)this + 616);
                                if ( v29 )
                                {
                                  if ( *v30 )
                                  {
                                    inserted = CTaskDialog::InsertArea(this, L"FootnoteSeparator", L"Separator", 0);
                                    v29 = *((_QWORD *)this + 80);
                                  }
                                }
                                else
                                {
                                  v29 = 0;
                                }
                                if ( *((_QWORD *)this + 86) && (v29 || *v30) && inserted >= 0 )
                                  inserted = CTaskDialog::InsertArea(
                                               this,
                                               L"ExpandedFooterSeparator",
                                               L"Separator",
                                               (struct DirectUI::Element **)this + 85);
                                if ( !*((_QWORD *)this + 80) && !*v30 && !*((_QWORD *)this + 86) )
                                {
                                  if ( inserted >= 0 )
                                    inserted = DirectUI::Element::Destroy(*((DirectUI::Element **)this + 76), 1);
                                  *((_QWORD *)this + 76) = 0;
                                }
                                if ( inserted >= 0 )
                                {
                                  inserted = CTaskDialog::InitializeButtons(this);
                                  if ( inserted >= 0 )
                                  {
                                    CTaskDialog::InitializeSysLinks(this);
                                    CTaskDialog::SwapLinkAreas(v31);
                                    inserted = CTaskDialog::SetBasicLayout(this, 1, 0);
                                  }
                                }
                                DirectUI::Element::EndDefer(this, v25);
                                if ( inserted >= 0 )
                                {
                                  inserted = CTaskDialog::AdjustScrollerHeightAsNeeded(this);
                                  if ( inserted >= 0 )
                                  {
                                    CTaskDialog::CallCallback(this, 7u, 0, 0);
                                    v32 = (HWND)(*(__int64 (__fastcall **)(CTaskDialog *))(*(_QWORD *)this + 360LL))(this);
                                    ShowWindow(v32, 5);
                                  }
                                }
                                if ( *((_BYTE *)this + 432) )
                                {
                                  if ( *((_QWORD *)this + 93) )
                                  {
                                    v33 = CoInitializeEx(0, 6u) >= 0;
                                    *((_BYTE *)this + 296) = v33;
                                    if ( v33 )
                                      CoCreateInstance(
                                        &CLSID_AnimateWindowSize,
                                        0,
                                        1u,
                                        &GUID_22e4c895_8ab9_40bb_b81a_001dd9b1f449,
                                        (LPVOID *)this + 103);
                                  }
                                }
                                else
                                {
                                  DisableAnimations();
                                }
                                KillTimer(*((HWND *)this + 39), 1u);
                                if ( (*(_DWORD *)(*((_QWORD *)this + 41) + 20LL) & 0x800) == 0
                                  || (TickCount = GetTickCount(),
                                      v35 = (HWND)*((_QWORD *)this + 39),
                                      *((_DWORD *)this + 92) = TickCount,
                                      SetTimer(v35, 1u, 0xC8u, 0)) )
                                {
                                  if ( inserted >= 0 )
                                  {
                                    v36 = (_DWORD *)*((_QWORD *)this + 50);
                                    if ( v36 )
                                      *v36 = 2;
                                    v37 = (int *)*((_QWORD *)this + 51);
                                    if ( v37 )
                                      *v37 = (*(_DWORD *)(*((_QWORD *)this + 41) + 20LL) >> 8) & 1;
                                  }
                                }
                                else
                                {
                                  inserted = -2147467259;
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    v38 = (DirectUI *)*((_QWORD *)this + 42);
    if ( v38 )
    {
      (**(void (__fastcall ***)(_QWORD, _QWORD))v38)(*((_QWORD *)this + 42), 0);
      DirectUI::AccHFree(v38, v39);
      *((_QWORD *)this + 42) = 0;
    }
    LocalFree(v23);
  }
  else
  {
    inserted = -2147024882;
  }
  if ( ulCookie[0] )
    PropPageDeactivateContext(ulCookie[0]);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18007c1bc  push    rbp
0x18007c1be  push    rbx
0x18007c1bf  push    rsi
0x18007c1c0  push    rdi
0x18007c1c1  push    r12
0x18007c1c3  push    r13
0x18007c1c5  push    r14
0x18007c1c7  push    r15
0x18007c1c9  lea     rbp, [rsp-178h]
0x18007c1d1  sub     rsp, 278h
0x18007c1d8  mov     rax, cs:__security_cookie
0x18007c1df  xor     rax, rsp
0x18007c1e2  mov     [rbp+1B0h+var_50], rax
0x18007c1e9  mov     rdi, rcx
0x18007c1ec  xor     r13d, r13d
0x18007c1ef  lea     rcx, [rsp+2B0h+ulCookie]
0x18007c1f4  mov     [rsp+2B0h+ulCookie], r13
0x18007c1f9  mov     r12b, r8b
0x18007c1fc  mov     rbx, rdx
0x18007c1ff  call    SHActivateContext
0x18007c204  mov     rcx, [rdi+148h]; struct _TASKDIALOGCONFIG *
0x18007c20b  mov     [rdi+138h], rbx
0x18007c212  call    ?CanBeMinimized@CTaskDialog@@CA_NPEBU_TASKDIALOGCONFIG@@@Z; CTaskDialog::CanBeMinimized(_TASKDIALOGCONFIG const *)
0x18007c217  mov     [rdi+183h], al
0x18007c21d  mov     edx, 20000h
0x18007c222  mov     rcx, rbx
0x18007c225  test    al, al
0x18007c227  jz      short loc_18007C230
0x18007c229  call    SetWindowStyle
0x18007c22e  jmp     short loc_18007C235
0x18007c230  call    ClearWindowStyle
0x18007c235  mov     rcx, rdi; this
0x18007c238  call    ?SetupCancelCapability@CTaskDialog@@AEAAXXZ; CTaskDialog::SetupCancelCapability(void)
0x18007c23d  mov     rcx, [rdi+148h]
0x18007c244  mov     r14d, 1
0x18007c24a  mov     eax, [rcx+14h]
0x18007c24d  lea     r15d, [r14+0Fh]
0x18007c251  shr     eax, 6
0x18007c254  and     al, r14b
0x18007c257  mov     [rdi+181h], al
0x18007c25d  mov     edx, [rcx+14h]
0x18007c260  and     edx, r15d
0x18007c263  setnz   al
0x18007c266  mov     [rdi+18Ah], al
0x18007c26c  test    byte ptr [rcx+14h], 20h
0x18007c270  jnz     short loc_18007C279
0x18007c272  mov     al, r13b
0x18007c275  test    edx, edx
0x18007c277  jz      short loc_18007C27C
0x18007c279  mov     al, r14b
0x18007c27c  mov     rdx, [rdi+138h]; HWND
0x18007c283  mov     [rdi+189h], al
0x18007c289  mov     eax, [rcx+14h]
0x18007c28c  shr     eax, 7
0x18007c28f  and     al, r14b
0x18007c292  mov     [rdi+1A0h], al
0x18007c298  mov     eax, [rcx+14h]
0x18007c29b  shr     eax, 0Eh
0x18007c29e  and     al, r14b
0x18007c2a1  mov     [rdi+1A8h], al
0x18007c2a7  mov     eax, [rcx+14h]
0x18007c2aa  shr     eax, 17h
0x18007c2ad  and     al, r14b
0x18007c2b0  mov     [rdi+1A9h], al
0x18007c2b6  mov     al, [rcx+17h]
0x18007c2b9  and     al, r14b
0x18007c2bc  mov     [rdi+1AAh], al
0x18007c2c2  mov     eax, [rcx+14h]
0x18007c2c5  shr     eax, 0Ch
0x18007c2c8  and     al, r14b
0x18007c2cb  mov     [rdi+1A1h], al
0x18007c2d1  mov     rax, [rcx+8Ch]
0x18007c2d8  mov     [rdi+160h], rax
0x18007c2df  mov     rax, [rcx+94h]
0x18007c2e6  mov     [rdi+168h], rax
0x18007c2ed  mov     eax, [rcx+9Ch]
0x18007c2f3  lea     rcx, [rdi+350h]; this
0x18007c2fa  mov     [rdi+1ACh], eax
0x18007c300  mov     [rdi+184h], r13d
0x18007c307  call    ?Initialize@DPISCALEINFO@@QEAAXPEAUHWND__@@@Z; DPISCALEINFO::Initialize(HWND__ *)
0x18007c30c  lea     rcx, [rdi+1B0h]; bool *
0x18007c313  call    ?IsWindowAnimationEnabled@@YAJPEA_N@Z; IsWindowAnimationEnabled(bool *)
0x18007c318  call    cs:__imp_IsThemeActive
0x18007c31e  test    eax, eax
0x18007c320  setnz   cl
0x18007c323  mov     [rdi+129h], cl
0x18007c329  test    eax, eax
0x18007c32b  jnz     short loc_18007C332
0x18007c32d  call    DisableAnimations
0x18007c332  mov     rax, [rdi+148h]
0x18007c339  mov     ebx, [rax+3Ch]
0x18007c33c  mov     [rdi+178h], ebx
0x18007c342  mov     ecx, [rax+18h]
0x18007c345  test    ecx, ecx
0x18007c347  jz      short loc_18007C35A
0x18007c349  mov     eax, ecx
0x18007c34b  and     eax, r14d
0x18007c34e  add     ebx, eax
0x18007c350  shr     ecx, 1
0x18007c352  jnz     short loc_18007C349
0x18007c354  mov     [rdi+178h], ebx
0x18007c35a  test    ebx, ebx
0x18007c35c  jnz     short loc_18007C368
0x18007c35e  mov     [rdi+178h], r14d
0x18007c365  mov     ebx, r14d
0x18007c368  mov     [rdi+17Ch], r13d
0x18007c36f  call    cs:__imp_GetProcessHeap
0x18007c375  mov     esi, 8
0x18007c37a  mov     r9d, ebx
0x18007c37d  mov     edx, esi
0x18007c37f  mov     rcx, rax
0x18007c382  mov     r8, r15
0x18007c385  call    CCHeapAllocArraySize
0x18007c38a  mov     [rdi+158h], rax
0x18007c391  test    rax, rax
0x18007c394  jz      short loc_18007C3CC
0x18007c396  mov     rax, [rdi+148h]
0x18007c39d  mov     ebx, [rax+4Ch]
0x18007c3a0  mov     [rdi+1C8h], ebx
0x18007c3a6  test    ebx, ebx
0x18007c3a8  jle     short loc_18007C3D6
0x18007c3aa  call    cs:__imp_GetProcessHeap
0x18007c3b0  mov     r9d, ebx
0x18007c3b3  mov     r8, r15
0x18007c3b6  mov     rcx, rax
0x18007c3b9  mov     edx, esi
0x18007c3bb  call    CCHeapAllocArraySize
0x18007c3c0  mov     [rdi+1C0h], rax
0x18007c3c7  test    rax, rax
0x18007c3ca  jnz     short loc_18007C3D6
0x18007c3cc  mov     esi, 8007000Eh
0x18007c3d1  jmp     loc_18007C851
0x18007c3d6  mov     rdx, [rdi+148h]
0x18007c3dd  lea     rcx, [rsp+2B0h+lpString]; this
0x18007c3e2  mov     [rsp+2B0h+lpString], r13
0x18007c3e7  mov     r8, [rdx+1Ch]; unsigned __int16 *
0x18007c3eb  mov     rdx, [rdx+0Ch]; hModule
0x18007c3ef  call    ?Resolve@CResolvedString@@QEAAJPEAUHINSTANCE__@@PEBG@Z; CResolvedString::Resolve(HINSTANCE__ *,ushort const *)
0x18007c3f4  mov     esi, eax
0x18007c3f6  mov     r15d, 80004005h
0x18007c3fc  test    eax, eax
0x18007c3fe  js      short loc_18007C40A
0x18007c400  mov     rbx, [rsp+2B0h+lpString]
0x18007c405  test    rbx, rbx
0x18007c408  jnz     short loc_18007C444
0x18007c40a  mov     r8d, 104h; nSize
0x18007c410  lea     rdx, [rsp+2B0h+Filename]; lpFilename
0x18007c415  xor     ecx, ecx; hModule
0x18007c417  call    cs:__imp_GetModuleFileNameW
0x18007c41d  lea     rcx, [rsp+2B0h+Filename]; pszPath
0x18007c422  call    cs:__imp_PathStripPathW
0x18007c428  lea     r8, [rsp+2B0h+Filename]; unsigned __int16 *
0x18007c42d  xor     edx, edx; hModule
0x18007c42f  lea     rcx, [rsp+2B0h+lpString]; this
0x18007c434  call    ?Resolve@CResolvedString@@QEAAJPEAUHINSTANCE__@@PEBG@Z; CResolvedString::Resolve(HINSTANCE__ *,ushort const *)
0x18007c439  mov     rbx, [rsp+2B0h+lpString]
0x18007c43e  mov     esi, eax
0x18007c440  test    eax, eax
0x18007c442  js      short loc_18007C45A
0x18007c444  mov     rcx, [rdi+138h]; hWnd
0x18007c44b  mov     rdx, rbx; lpString
0x18007c44e  call    cs:__imp_SetWindowTextW
0x18007c454  test    eax, eax
0x18007c456  cmovz   esi, r15d
0x18007c45a  mov     [rsp+2B0h+var_278], r13
0x18007c45f  mov     r15d, r13d
0x18007c462  mov     dword ptr [rsp+2B0h+lpString], r13d
0x18007c467  test    esi, esi
0x18007c469  js      short loc_18007C496
0x18007c46b  mov     rdx, [rdi+138h]; hWnd
0x18007c472  lea     rax, [rsp+2B0h+lpString]
0x18007c477  mov     [rsp+2B0h+var_288], rax; unsigned int *
0x18007c47c  xor     r9d, r9d; unsigned int
0x18007c47f  mov     r8b, r14b; bool
0x18007c482  mov     [rsp+2B0h+ppv], r13; unsigned int *
0x18007c487  mov     rcx, rdi; this
0x18007c48a  call    ?Initialize@HWNDElement@DirectUI@@QEAAJPEAUHWND__@@_NIPEAVElement@2@PEAK@Z; DirectUI::HWNDElement::Initialize(HWND__ *,bool,uint,DirectUI::Element *,ulong *)
0x18007c48f  mov     r15d, dword ptr [rsp+2B0h+lpString]
0x18007c494  mov     esi, eax
0x18007c496  mov     rcx, rdi; this
0x18007c499  call    ?ShouldForceRtlLayout@CTaskDialog@@AEAA_NXZ; CTaskDialog::ShouldForceRtlLayout(void)
0x18007c49e  test    al, al
0x18007c4a0  jz      short loc_18007C4AD
0x18007c4a2  mov     edx, r14d; int
0x18007c4a5  mov     rcx, rdi; this
0x18007c4a8  call    ?SetDirection@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetDirection(int)
0x18007c4ad  test    byte ptr [rdi+98h], 40h
0x18007c4b4  jz      short loc_18007C4E4
0x18007c4b6  mov     rcx, [rdi+138h]; hWnd
0x18007c4bd  mov     r14d, 0FFFFFFECh
0x18007c4c3  mov     edx, r14d; nIndex
0x18007c4c6  call    cs:__imp_GetWindowLongPtrW
0x18007c4cc  mov     rcx, [rdi+138h]; hWnd
0x18007c4d3  mov     edx, r14d; nIndex
0x18007c4d6  bts     rax, 16h
0x18007c4db  mov     r8, rax; dwNewLong
0x18007c4de  call    cs:__imp_SetWindowLongPtrW
0x18007c4e4  test    esi, esi
0x18007c4e6  js      loc_18007C81D
0x18007c4ec  mov     rax, [rdi]
0x18007c4ef  lea     r14, [rdi+150h]
0x18007c4f6  mov     rdx, r14
0x18007c4f9  mov     rcx, rdi
0x18007c4fc  mov     rax, [rax+1B8h]
0x18007c503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c508  mov     esi, eax
0x18007c50a  test    eax, eax
0x18007c50c  js      loc_18007C81D
0x18007c512  mov     rcx, [r14]; this
0x18007c515  lea     rax, [rsp+2B0h+var_278]
0x18007c51a  xor     r9d, r9d; struct DirectUI::Element *
0x18007c51d  mov     [rsp+2B0h+var_288], rax; struct DirectUI::Element **
0x18007c522  mov     r8, rdi; struct DirectUI::Element *
0x18007c525  lea     rdx, aMain; "main"
0x18007c52c  call    ?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18007c531  mov     esi, eax
0x18007c533  test    eax, eax
0x18007c535  js      loc_18007C81D
0x18007c53b  mov     rcx, [rsp+2B0h+var_278]; this
0x18007c540  call    ?SetAccessible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetAccessible(bool)
0x18007c545  mov     esi, eax
0x18007c547  test    eax, eax
0x18007c549  js      loc_18007C81D
0x18007c54f  mov     rcx, [rsp+2B0h+var_278]; this
0x18007c554  mov     rdx, rbx; unsigned __int16 *
0x18007c557  call    ?SetAccName@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetAccName(ushort const *)
0x18007c55c  mov     esi, eax
0x18007c55e  test    eax, eax
0x18007c560  js      loc_18007C81D
0x18007c566  mov     rcx, rdi; this
0x18007c569  call    ?BuildMainInstructionArea@CTaskDialog@@AEAAJXZ; CTaskDialog::BuildMainInstructionArea(void)
0x18007c56e  mov     esi, eax
0x18007c570  test    eax, eax
0x18007c572  js      loc_18007C81D
0x18007c578  mov     dl, r12b; bool
0x18007c57b  mov     rcx, rdi; this
0x18007c57e  call    ?BuildMainIconArea@CTaskDialog@@AEAAJ_N@Z; CTaskDialog::BuildMainIconArea(bool)
0x18007c583  mov     esi, eax
0x18007c585  test    eax, eax
0x18007c587  js      loc_18007C81D
0x18007c58d  mov     rcx, rdi; this
0x18007c590  call    ?BuildContentArea@CTaskDialog@@AEAAJXZ; CTaskDialog::BuildContentArea(void)
0x18007c595  mov     esi, eax
0x18007c597  test    eax, eax
0x18007c599  js      loc_18007C81D
0x18007c59f  mov     rcx, rdi; this
0x18007c5a2  call    ?BuildProgressArea@CTaskDialog@@AEAAJXZ; CTaskDialog::BuildProgressArea(void)
0x18007c5a7  mov     esi, eax
0x18007c5a9  test    eax, eax
0x18007c5ab  js      loc_18007C81D
0x18007c5b1  mov     rcx, rdi; this
0x18007c5b4  call    ?BuildFooterExpando@CTaskDialog@@AEAAJXZ; CTaskDialog::BuildFooterExpando(void)
0x18007c5b9  mov     esi, eax
0x18007c5bb  test    eax, eax
0x18007c5bd  js      loc_18007C81D
0x18007c5c3  mov     rcx, rdi; this
0x18007c5c6  call    ?BuildLinkArea@CTaskDialog@@AEAAJXZ; CTaskDialog::BuildLinkArea(void)
0x18007c5cb  mov     esi, eax
0x18007c5cd  test    eax, eax
0x18007c5cf  js      loc_18007C81D
0x18007c5d5  mov     rcx, rdi; this
0x18007c5d8  call    ?BuildRadioButtonArea@CTaskDialog@@AEAAJXZ; CTaskDialog::BuildRadioButtonArea(void)
0x18007c5dd  mov     esi, eax
0x18007c5df  test    eax, eax
0x18007c5e1  js      loc_18007C81D
0x18007c5e7  mov     rcx, rdi; this
0x18007c5ea  call    ?BuildControlArea@CTaskDialog@@AEAAJXZ; CTaskDialog::BuildControlArea(void)
0x18007c5ef  mov     esi, eax
0x18007c5f1  test    eax, eax
0x18007c5f3  js      loc_18007C81D
0x18007c5f9  mov     rcx, rdi; this
0x18007c5fc  call    ?BuildFootnoteArea@CTaskDialog@@AEAAJXZ; CTaskDialog::BuildFootnoteArea(void)
0x18007c601  mov     esi, eax
0x18007c603  test    eax, eax
0x18007c605  js      loc_18007C81D
0x18007c60b  mov     edx, 10h; int
0x18007c610  mov     rcx, rdi; this
0x18007c613  call    ?SetAccRole@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetAccRole(int)
0x18007c618  mov     rax, [rdi+280h]
0x18007c61f  lea     r14, [rdi+268h]
0x18007c626  test    rax, rax
0x18007c629  jz      short loc_18007C654
0x18007c62b  cmp     [r14], r13
0x18007c62e  jz      short loc_18007C657
0x18007c630  xor     r9d, r9d; struct DirectUI::Element **
0x18007c633  lea     r8, aSeparator; "Separator"
0x18007c63a  lea     rdx, aFootnotesepara; "FootnoteSeparator"
0x18007c641  mov     rcx, rdi; this
0x18007c644  call    ?InsertArea@CTaskDialog@@AEAAJPEBG0PEAPEAVElement@DirectUI@@@Z; CTaskDialog::InsertArea(ushort const *,ushort const *,DirectUI::Element * *)
0x18007c649  mov     esi, eax
0x18007c64b  mov     rax, [rdi+280h]
0x18007c652  jmp     short loc_18007C657
0x18007c654  mov     rax, r13
0x18007c657  cmp     [rdi+2B0h], r13
0x18007c65e  jz      short loc_18007C68D
0x18007c660  test    rax, rax
0x18007c663  jnz     short loc_18007C66A
0x18007c665  cmp     [r14], r13
0x18007c668  jz      short loc_18007C68D
0x18007c66a  test    esi, esi
  ... truncated ...
```
