# ShortcutSerialization::s_SetLinkValues(_CONSOLE_STATE_INFO *,int,int,bool)

- ea: `0x1800180bc`
- end: `0x180018514`
- name: `?s_SetLinkValues@ShortcutSerialization@@SAJPEAU_CONSOLE_STATE_INFO@@HH_N@Z`
- size: `1112`
- prototype: `__int64 __fastcall(struct _CONSOLE_STATE_INFO *, int, int, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180007e0c`

## callees

- `0x1800015b0`
- `0x180002088`
- `0x1800179d0`
- `0x180018010`
- `0x18001806c`
- `0x1800180bc`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800183d7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800183d7`

## pseudocode

```c
__int64 __fastcall ShortcutSerialization::s_SetLinkValues(
        struct _CONSOLE_STATE_INFO *a1,
        __int64 a2,
        __int64 a3,
        char a4)
{
  struct _CONSOLE_STATE_INFO *v4; // rdi
  int v5; // r15d
  BOOL v7; // esi
  const wchar_t *v8; // rcx
  int LoadedShellLinkForShortcut; // ebx
  unsigned int v10; // ecx
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  int v14; // eax
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int64 v21; // [rsp+20h] [rbp-E0h] BYREF
  struct IShellLinkW *v22; // [rsp+28h] [rbp-D8h] BYREF
  struct IPersistFile *v23; // [rsp+30h] [rbp-D0h] BYREF
  PROPVARIANT pvar; // [rsp+38h] [rbp-C8h] BYREF
  struct IPropertyStore *v25; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+58h] [rbp-A8h]
  _DWORD v27[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v28; // [rsp+68h] [rbp-98h]
  __int16 v29; // [rsp+6Ah] [rbp-96h]
  int v30; // [rsp+6Ch] [rbp-94h]
  int v31; // [rsp+70h] [rbp-90h]
  __int16 v32; // [rsp+74h] [rbp-8Ch]
  __int16 v33; // [rsp+76h] [rbp-8Ah]
  __int64 v34; // [rsp+78h] [rbp-88h]
  int v35; // [rsp+80h] [rbp-80h]
  int v36; // [rsp+84h] [rbp-7Ch]
  int v37; // [rsp+88h] [rbp-78h]
  __int128 v38; // [rsp+8Ch] [rbp-74h]
  __int128 v39; // [rsp+9Ch] [rbp-64h]
  __int128 v40; // [rsp+ACh] [rbp-54h]
  __int128 v41; // [rsp+BCh] [rbp-44h]
  int v42; // [rsp+CCh] [rbp-34h]
  int v43; // [rsp+D0h] [rbp-30h]
  int v44; // [rsp+D4h] [rbp-2Ch]
  int v45; // [rsp+D8h] [rbp-28h]
  int v46; // [rsp+DCh] [rbp-24h]
  int v47; // [rsp+E0h] [rbp-20h]
  int v48; // [rsp+E4h] [rbp-1Ch]
  int v49; // [rsp+E8h] [rbp-18h]
  __int128 v50; // [rsp+ECh] [rbp-14h]
  __int128 v51; // [rsp+FCh] [rbp-4h]
  __int128 v52; // [rsp+10Ch] [rbp+Ch]
  __int128 v53; // [rsp+11Ch] [rbp+1Ch]

  v4 = gpStateInfo;
  v5 = g_fForceV2;
  v7 = g_fEastAsianSystem;
  v22 = 0;
  v8 = (const wchar_t *)*((_QWORD *)gpStateInfo + 25);
  v23 = 0;
  LoadedShellLinkForShortcut = ShortcutSerialization::s_GetLoadedShellLinkForShortcut(v8, 0x12u, &v22, &v23);
  if ( LoadedShellLinkForShortcut >= 0 )
  {
    v21 = 0;
    LoadedShellLinkForShortcut = ((__int64 (__fastcall *)(struct IShellLinkW *, GUID *, __int64 *))v22->lpVtbl->QueryInterface)(
                                   v22,
                                   &GUID_45e2b4ae_b1c3_11d0_b92f_00a0c90312e1,
                                   &v21);
    if ( LoadedShellLinkForShortcut >= 0 )
    {
      memset_0(v27, 0, 0xCCu);
      v10 = *((_DWORD *)v4 + 24);
      v11 = *(_OWORD *)((char *)v4 + 28);
      v28 = *((_WORD *)v4 + 50);
      v12 = *(_OWORD *)((char *)v4 + 44);
      v29 = *((_WORD *)v4 + 51);
      v30 = *(_DWORD *)v4;
      v31 = *((_DWORD *)v4 + 1);
      v32 = *((_WORD *)v4 + 4);
      v33 = *((_WORD *)v4 + 6);
      v35 = *((_DWORD *)v4 + 4);
      v36 = *((_DWORD *)v4 + 5);
      v37 = *((_DWORD *)v4 + 6);
      v42 = *((_DWORD *)v4 + 23);
      v27[0] = 204;
      v43 = v10 & 1;
      v27[1] = -1610612734;
      v44 = (v10 >> 1) & 1;
      v34 = 0;
      v45 = (v10 >> 3) & 1;
      v38 = v11;
      v46 = (v10 >> 2) & 1;
      v13 = *(_OWORD *)((char *)v4 + 60);
      v47 = *((_DWORD *)v4 + 26);
      v14 = *((_DWORD *)v4 + 27);
      v39 = v12;
      v49 = (v10 >> 4) & 1;
      v15 = *(_OWORD *)((char *)v4 + 76);
      v40 = v13;
      v48 = v14;
      v16 = *((_OWORD *)v4 + 7);
      v41 = v15;
      v17 = *((_OWORD *)v4 + 8);
      v50 = v16;
      v18 = *((_OWORD *)v4 + 9);
      v51 = v17;
      v19 = *((_OWORD *)v4 + 10);
      v52 = v18;
      v53 = v19;
      LoadedShellLinkForShortcut = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 40LL))(v21);
      if ( LoadedShellLinkForShortcut >= 0 )
      {
        LoadedShellLinkForShortcut = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v21 + 24LL))(v21, v27);
        if ( LoadedShellLinkForShortcut >= 0 )
        {
          if ( !v7
            || (v26 = *((_DWORD *)v4 + 52),
                v25 = (struct IPropertyStore *)0xA00000040000000CLL,
                LoadedShellLinkForShortcut = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 40LL))(v21),
                LoadedShellLinkForShortcut >= 0)
            && (LoadedShellLinkForShortcut = (*(__int64 (__fastcall **)(__int64, struct IPropertyStore **))(*(_QWORD *)v21 + 24LL))(
                                               v21,
                                               &v25),
                LoadedShellLinkForShortcut >= 0) )
          {
            v25 = 0;
            LoadedShellLinkForShortcut = ((__int64 (__fastcall *)(struct IShellLinkW *, GUID *, struct IPropertyStore **))v22->lpVtbl->QueryInterface)(
                                           v22,
                                           &IID_IPropertyStore,
                                           &v25);
            if ( LoadedShellLinkForShortcut >= 0 )
            {
              ShortcutSerialization::s_SetLinkPropertyBoolValue(v25, &PKEY_Console_ForceV2, v5);
              ShortcutSerialization::s_SetLinkPropertyBoolValue(v25, &PKEY_Console_WrapText, *((_DWORD *)v4 + 54));
              ShortcutSerialization::s_SetLinkPropertyBoolValue(v25, &PKEY_Console_FilterOnPaste, *((_DWORD *)v4 + 55));
              ShortcutSerialization::s_SetLinkPropertyBoolValue(
                v25,
                &PKEY_Console_CtrlKeyShortcutsDisabled,
                *((_DWORD *)v4 + 56));
              ShortcutSerialization::s_SetLinkPropertyBoolValue(v25, &PKEY_Console_LineSelection, *((_DWORD *)v4 + 57));
              memset(&pvar, 0, sizeof(pvar));
              pvar.vt = 2;
              pvar.iVal = *((unsigned __int8 *)v4 + 232);
              ((void (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v25->lpVtbl->SetValue)(
                v25,
                PKEY_Console_WindowTransparency,
                &pvar);
              PropVariantClear(&pvar);
              ShortcutSerialization::s_SetLinkPropertyBoolValue(
                v25,
                &PKEY_Console_InterceptCopyPaste,
                *((_DWORD *)v4 + 62));
              if ( a4 )
              {
                ShortcutSerialization::s_SetLinkPropertyDwordValue(v25, &PKEY_Console_CursorType, *((_DWORD *)v4 + 60));
                ShortcutSerialization::s_SetLinkPropertyDwordValue(v25, &PKEY_Console_CursorColor, *((_DWORD *)v4 + 61));
                ShortcutSerialization::s_SetLinkPropertyDwordValue(
                  v25,
                  &PKEY_Console_DefaultForeground,
                  *((_DWORD *)v4 + 63));
                ShortcutSerialization::s_SetLinkPropertyDwordValue(
                  v25,
                  &PKEY_Console_DefaultBackground,
                  *((_DWORD *)v4 + 64));
                ShortcutSerialization::s_SetLinkPropertyBoolValue(
                  v25,
                  &PKEY_Console_TerminalScrolling,
                  *((_DWORD *)v4 + 65));
              }
              LoadedShellLinkForShortcut = ((__int64 (__fastcall *)(struct IPropertyStore *))v25->lpVtbl->Commit)(v25);
              ((void (__fastcall *)(struct IPropertyStore *))v25->lpVtbl->Release)(v25);
            }
          }
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      if ( LoadedShellLinkForShortcut >= 0 )
        LoadedShellLinkForShortcut = ((__int64 (__fastcall *)(struct IPersistFile *, _QWORD, __int64))v23->lpVtbl->Save)(
                                       v23,
                                       0,
                                       1);
    }
    ((void (__fastcall *)(struct IPersistFile *))v23->lpVtbl->Release)(v23);
    ((void (__fastcall *)(struct IShellLinkW *))v22->lpVtbl->Release)(v22);
  }
  return (LoadedShellLinkForShortcut >> 31) & 0xC0000001;
}

```

## disassembly

```asm
0x1800180bc  push    rbp
0x1800180be  push    rbx
0x1800180bf  push    rsi
0x1800180c0  push    rdi
0x1800180c1  push    r14
0x1800180c3  push    r15
0x1800180c5  lea     rbp, [rsp-48h]
0x1800180ca  sub     rsp, 148h
0x1800180d1  mov     rax, cs:__security_cookie
0x1800180d8  xor     rax, rsp
0x1800180db  mov     [rbp+70h+var_40], rax
0x1800180df  mov     rdi, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x1800180e6  lea     r8, [rsp+170h+var_148]; struct IShellLinkW **
0x1800180eb  mov     r15d, cs:?g_fForceV2@@3HA; int g_fForceV2
0x1800180f2  mov     r14b, r9b
0x1800180f5  mov     esi, cs:?g_fEastAsianSystem@@3HA; int g_fEastAsianSystem
0x1800180fb  lea     r9, [rsp+170h+var_140]; struct IPersistFile **
0x180018100  mov     edx, 12h; unsigned int
0x180018105  mov     [rsp+170h+var_148], 0
0x18001810e  mov     rcx, [rdi+0C8h]; wchar_t *
0x180018115  mov     [rsp+170h+var_140], 0
0x18001811e  call    ?s_GetLoadedShellLinkForShortcut@ShortcutSerialization@@CAJPEB_WKPEAPEAUIShellLinkW@@PEAPEAUIPersistFile@@@Z; ShortcutSerialization::s_GetLoadedShellLinkForShortcut(wchar_t const *,ulong,IShellLinkW * *,IPersistFile * *)
0x180018123  mov     ebx, eax
0x180018125  test    eax, eax
0x180018127  js      loc_1800184EC
0x18001812d  mov     rcx, [rsp+170h+var_148]
0x180018132  lea     r8, [rsp+170h+var_150]
0x180018137  mov     [rsp+170h+var_150], 0
0x180018140  lea     rdx, _GUID_45e2b4ae_b1c3_11d0_b92f_00a0c90312e1
0x180018147  mov     rax, [rcx]
0x18001814a  mov     rax, [rax]
0x18001814d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018152  mov     ebx, eax
0x180018154  test    eax, eax
0x180018156  js      loc_1800184CA
0x18001815c  mov     ebx, 0CCh
0x180018161  lea     rcx, [rsp+170h+var_110]; void *
0x180018166  mov     r8d, ebx; Size
0x180018169  xor     edx, edx; Val
0x18001816b  call    memset_0
0x180018170  mov     ecx, [rdi+60h]
0x180018173  mov     edx, 0A0000002h
0x180018178  movzx   eax, word ptr [rdi+64h]
0x18001817c  movups  xmm0, xmmword ptr [rdi+1Ch]
0x180018180  mov     [rsp+170h+var_108], ax
0x180018185  movzx   eax, word ptr [rdi+66h]
0x180018189  movups  xmm1, xmmword ptr [rdi+2Ch]
0x18001818d  mov     [rsp+170h+var_106], ax
0x180018192  mov     eax, [rdi]
0x180018194  mov     [rsp+170h+var_104], eax
0x180018198  mov     eax, [rdi+4]
0x18001819b  mov     [rsp+170h+var_100], eax
0x18001819f  movzx   eax, word ptr [rdi+8]
0x1800181a3  mov     [rsp+170h+var_FC], ax
0x1800181a8  movzx   eax, word ptr [rdi+0Ch]
0x1800181ac  mov     [rsp+170h+var_FA], ax
0x1800181b1  mov     eax, [rdi+10h]
0x1800181b4  mov     [rbp+70h+var_F0], eax
0x1800181b7  mov     eax, [rdi+14h]
0x1800181ba  mov     [rbp+70h+var_EC], eax
0x1800181bd  mov     eax, [rdi+18h]
0x1800181c0  mov     [rbp+70h+var_E8], eax
0x1800181c3  mov     eax, [rdi+5Ch]
0x1800181c6  mov     [rbp+70h+var_A4], eax
0x1800181c9  mov     eax, ecx
0x1800181cb  and     eax, 1
0x1800181ce  mov     [rsp+170h+var_110], ebx
0x1800181d2  mov     [rbp+70h+var_A0], eax
0x1800181d5  mov     eax, ecx
0x1800181d7  shr     eax, 1
0x1800181d9  and     eax, 1
0x1800181dc  mov     [rsp+170h+var_10C], edx
0x1800181e0  mov     [rbp+70h+var_9C], eax
0x1800181e3  mov     eax, ecx
0x1800181e5  shr     eax, 3
0x1800181e8  and     eax, 1
0x1800181eb  mov     [rsp+170h+var_F8], 0
0x1800181f4  mov     [rbp+70h+var_98], eax
0x1800181f7  mov     eax, ecx
0x1800181f9  shr     eax, 2
0x1800181fc  and     eax, 1
0x1800181ff  shr     ecx, 4
0x180018202  movups  [rbp+70h+var_E4], xmm0
0x180018206  mov     [rbp+70h+var_94], eax
0x180018209  and     ecx, 1
0x18001820c  mov     eax, [rdi+68h]
0x18001820f  movups  xmm0, xmmword ptr [rdi+3Ch]
0x180018213  mov     [rbp+70h+var_90], eax
0x180018216  mov     eax, [rdi+6Ch]
0x180018219  movups  [rbp+70h+var_D4], xmm1
0x18001821d  mov     [rbp+70h+var_88], ecx
0x180018220  movups  xmm1, xmmword ptr [rdi+4Ch]
0x180018224  mov     rcx, [rsp+170h+var_150]
0x180018229  movups  [rbp+70h+var_C4], xmm0
0x18001822d  mov     [rbp+70h+var_8C], eax
0x180018230  movups  xmm0, xmmword ptr [rdi+70h]
0x180018234  movups  [rbp+70h+var_B4], xmm1
0x180018238  movups  xmm1, xmmword ptr [rdi+80h]
0x18001823f  movups  [rbp+70h+var_84], xmm0
0x180018243  movups  xmm0, xmmword ptr [rdi+90h]
0x18001824a  movups  [rbp+70h+var_74], xmm1
0x18001824e  movups  xmm1, xmmword ptr [rdi+0A0h]
0x180018255  movups  [rbp+70h+var_64], xmm0
0x180018259  movups  [rbp+70h+var_54], xmm1
0x18001825d  mov     rax, [rcx]
0x180018260  mov     rax, [rax+28h]
0x180018264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018269  mov     ebx, eax
0x18001826b  test    eax, eax
0x18001826d  js      loc_18001849C
0x180018273  mov     rcx, [rsp+170h+var_150]
0x180018278  lea     rdx, [rsp+170h+var_110]
0x18001827d  mov     rax, [rcx]
0x180018280  mov     rax, [rax+18h]
0x180018284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018289  mov     ebx, eax
0x18001828b  test    eax, eax
0x18001828d  js      loc_18001849C
0x180018293  test    esi, esi
0x180018295  jz      short loc_1800182ED
0x180018297  mov     eax, [rdi+0D0h]
0x18001829d  mov     edx, 0A0000004h
0x1800182a2  mov     rcx, [rsp+170h+var_150]
0x1800182a7  mov     [rsp+170h+var_118], eax
0x1800182ab  mov     dword ptr [rsp+170h+var_120], 0Ch
0x1800182b3  mov     dword ptr [rsp+170h+var_120+4], edx
0x1800182b7  mov     rax, [rcx]
0x1800182ba  mov     rax, [rax+28h]
0x1800182be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182c3  mov     ebx, eax
0x1800182c5  test    eax, eax
0x1800182c7  js      loc_18001849C
0x1800182cd  mov     rcx, [rsp+170h+var_150]
0x1800182d2  lea     rdx, [rsp+170h+var_120]
0x1800182d7  mov     rax, [rcx]
0x1800182da  mov     rax, [rax+18h]
0x1800182de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182e3  mov     ebx, eax
0x1800182e5  test    eax, eax
0x1800182e7  js      loc_18001849C
0x1800182ed  mov     rcx, [rsp+170h+var_148]
0x1800182f2  lea     r8, [rsp+170h+var_120]
0x1800182f7  mov     [rsp+170h+var_120], 0
0x180018300  lea     rdx, IID_IPropertyStore
0x180018307  mov     rax, [rcx]
0x18001830a  mov     rax, [rax]
0x18001830d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018312  mov     ebx, eax
0x180018314  test    eax, eax
0x180018316  js      loc_18001849C
0x18001831c  mov     rcx, [rsp+170h+var_120]; struct IPropertyStore *
0x180018321  lea     rdx, PKEY_Console_ForceV2; struct _tagpropertykey *
0x180018328  mov     r8d, r15d; int
0x18001832b  call    ?s_SetLinkPropertyBoolValue@ShortcutSerialization@@CAXPEAUIPropertyStore@@AEBU_tagpropertykey@@H@Z; ShortcutSerialization::s_SetLinkPropertyBoolValue(IPropertyStore *,_tagpropertykey const &,int)
0x180018330  mov     r8d, [rdi+0D8h]; int
0x180018337  lea     rdx, PKEY_Console_WrapText; struct _tagpropertykey *
0x18001833e  mov     rcx, [rsp+170h+var_120]; struct IPropertyStore *
0x180018343  call    ?s_SetLinkPropertyBoolValue@ShortcutSerialization@@CAXPEAUIPropertyStore@@AEBU_tagpropertykey@@H@Z; ShortcutSerialization::s_SetLinkPropertyBoolValue(IPropertyStore *,_tagpropertykey const &,int)
0x180018348  mov     r8d, [rdi+0DCh]; int
0x18001834f  lea     rdx, PKEY_Console_FilterOnPaste; struct _tagpropertykey *
0x180018356  mov     rcx, [rsp+170h+var_120]; struct IPropertyStore *
0x18001835b  call    ?s_SetLinkPropertyBoolValue@ShortcutSerialization@@CAXPEAUIPropertyStore@@AEBU_tagpropertykey@@H@Z; ShortcutSerialization::s_SetLinkPropertyBoolValue(IPropertyStore *,_tagpropertykey const &,int)
0x180018360  mov     r8d, [rdi+0E0h]; int
0x180018367  lea     rdx, PKEY_Console_CtrlKeyShortcutsDisabled; struct _tagpropertykey *
0x18001836e  mov     rcx, [rsp+170h+var_120]; struct IPropertyStore *
0x180018373  call    ?s_SetLinkPropertyBoolValue@ShortcutSerialization@@CAXPEAUIPropertyStore@@AEBU_tagpropertykey@@H@Z; ShortcutSerialization::s_SetLinkPropertyBoolValue(IPropertyStore *,_tagpropertykey const &,int)
0x180018378  mov     r8d, [rdi+0E4h]; int
0x18001837f  lea     rdx, PKEY_Console_LineSelection; struct _tagpropertykey *
0x180018386  mov     rcx, [rsp+170h+var_120]; struct IPropertyStore *
0x18001838b  call    ?s_SetLinkPropertyBoolValue@ShortcutSerialization@@CAXPEAUIPropertyStore@@AEBU_tagpropertykey@@H@Z; ShortcutSerialization::s_SetLinkPropertyBoolValue(IPropertyStore *,_tagpropertykey const &,int)
0x180018390  mov     rcx, [rsp+170h+var_120]
0x180018395  lea     r8, [rsp+170h+pvar]
0x18001839a  xor     eax, eax
0x18001839c  lea     rdx, PKEY_Console_WindowTransparency
0x1800183a3  mov     qword ptr [rsp+170h+pvar+10h], rax
0x1800183a8  xorps   xmm0, xmm0
0x1800183ab  mov     eax, 2
0x1800183b0  movups  xmmword ptr [rsp+170h+pvar], xmm0
0x1800183b5  mov     word ptr [rsp+170h+pvar], ax
0x1800183ba  movzx   eax, byte ptr [rdi+0E8h]
0x1800183c1  mov     word ptr [rsp+170h+pvar+8], ax
0x1800183c6  mov     rax, [rcx]
0x1800183c9  mov     rax, [rax+30h]
0x1800183cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183d2  lea     rcx, [rsp+170h+pvar]; pvar
0x1800183d7  call    cs:__imp_PropVariantClear
0x1800183de  nop     dword ptr [rax+rax+00h]
0x1800183e3  mov     r8d, [rdi+0F8h]; int
0x1800183ea  lea     rdx, PKEY_Console_InterceptCopyPaste; struct _tagpropertykey *
0x1800183f1  mov     rcx, [rsp+170h+var_120]; struct IPropertyStore *
0x1800183f6  call    ?s_SetLinkPropertyBoolValue@ShortcutSerialization@@CAXPEAUIPropertyStore@@AEBU_tagpropertykey@@H@Z; ShortcutSerialization::s_SetLinkPropertyBoolValue(IPropertyStore *,_tagpropertykey const &,int)
0x1800183fb  test    r14b, r14b
0x1800183fe  jz      short loc_180018478
0x180018400  mov     r8d, [rdi+0F0h]; unsigned int
0x180018407  lea     rdx, PKEY_Console_CursorType; struct _tagpropertykey *
0x18001840e  mov     rcx, [rsp+170h+var_120]; struct IPropertyStore *
0x180018413  call    ?s_SetLinkPropertyDwordValue@ShortcutSerialization@@CAXPEAUIPropertyStore@@AEBU_tagpropertykey@@K@Z; ShortcutSerialization::s_SetLinkPropertyDwordValue(IPropertyStore *,_tagpropertykey const &,ulong)
0x180018418  mov     r8d, [rdi+0F4h]; unsigned int
0x18001841f  lea     rdx, PKEY_Console_CursorColor; struct _tagpropertykey *
0x180018426  mov     rcx, [rsp+170h+var_120]; struct IPropertyStore *
0x18001842b  call    ?s_SetLinkPropertyDwordValue@ShortcutSerialization@@CAXPEAUIPropertyStore@@AEBU_tagpropertykey@@K@Z; ShortcutSerialization::s_SetLinkPropertyDwordValue(IPropertyStore *,_tagpropertykey const &,ulong)
0x180018430  mov     r8d, [rdi+0FCh]; unsigned int
0x180018437  lea     rdx, PKEY_Console_DefaultForeground; struct _tagpropertykey *
0x18001843e  mov     rcx, [rsp+170h+var_120]; struct IPropertyStore *
0x180018443  call    ?s_SetLinkPropertyDwordValue@ShortcutSerialization@@CAXPEAUIPropertyStore@@AEBU_tagpropertykey@@K@Z; ShortcutSerialization::s_SetLinkPropertyDwordValue(IPropertyStore *,_tagpropertykey const &,ulong)
0x180018448  mov     r8d, [rdi+100h]; unsigned int
0x18001844f  lea     rdx, PKEY_Console_DefaultBackground; struct _tagpropertykey *
0x180018456  mov     rcx, [rsp+170h+var_120]; struct IPropertyStore *
0x18001845b  call    ?s_SetLinkPropertyDwordValue@ShortcutSerialization@@CAXPEAUIPropertyStore@@AEBU_tagpropertykey@@K@Z; ShortcutSerialization::s_SetLinkPropertyDwordValue(IPropertyStore *,_tagpropertykey const &,ulong)
0x180018460  mov     r8d, [rdi+104h]; int
0x180018467  lea     rdx, PKEY_Console_TerminalScrolling; struct _tagpropertykey *
0x18001846e  mov     rcx, [rsp+170h+var_120]; struct IPropertyStore *
0x180018473  call    ?s_SetLinkPropertyBoolValue@ShortcutSerialization@@CAXPEAUIPropertyStore@@AEBU_tagpropertykey@@H@Z; ShortcutSerialization::s_SetLinkPropertyBoolValue(IPropertyStore *,_tagpropertykey const &,int)
0x180018478  mov     rcx, [rsp+170h+var_120]
0x18001847d  mov     rax, [rcx]
0x180018480  mov     rax, [rax+38h]
0x180018484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018489  mov     rcx, [rsp+170h+var_120]
0x18001848e  mov     ebx, eax
0x180018490  mov     rax, [rcx]
0x180018493  mov     rax, [rax+10h]
0x180018497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001849c  mov     rcx, [rsp+170h+var_150]
0x1800184a1  mov     rax, [rcx]
0x1800184a4  mov     rax, [rax+10h]
0x1800184a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184ad  test    ebx, ebx
0x1800184af  js      short loc_1800184CA
0x1800184b1  mov     rcx, [rsp+170h+var_140]
0x1800184b6  xor     edx, edx
0x1800184b8  mov     rax, [rcx]
0x1800184bb  lea     r8d, [rdx+1]
0x1800184bf  mov     rax, [rax+30h]
0x1800184c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184c8  mov     ebx, eax
0x1800184ca  mov     rcx, [rsp+170h+var_140]
0x1800184cf  mov     rax, [rcx]
0x1800184d2  mov     rax, [rax+10h]
0x1800184d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184db  mov     rcx, [rsp+170h+var_148]
0x1800184e0  mov     rax, [rcx]
0x1800184e3  mov     rax, [rax+10h]
0x1800184e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184ec  sar     ebx, 1Fh
0x1800184ef  and     ebx, 0C0000001h
0x1800184f5  mov     eax, ebx
0x1800184f7  mov     rcx, [rbp+70h+var_40]
0x1800184fb  xor     rcx, rsp; StackCookie
0x1800184fe  call    __security_check_cookie
0x180018503  add     rsp, 148h
0x18001850a  pop     r15
0x18001850c  pop     r14
0x18001850e  pop     rdi
0x18001850f  pop     rsi
0x180018510  pop     rbx
0x180018511  pop     rbp
0x180018512  retn
```
