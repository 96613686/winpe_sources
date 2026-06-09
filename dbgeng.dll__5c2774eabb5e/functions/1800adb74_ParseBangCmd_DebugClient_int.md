# ParseBangCmd(DebugClient *,int)

- ea: `0x1800adb74`
- end: `0x1800ae59f`
- name: `?ParseBangCmd@@YAXPEAVDebugClient@@H@Z`
- size: `2603`
- prototype: `void __fastcall(struct DebugClient *, int)`
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800eb6bc`

## callees

- `0x1800727b8`
- `0x180075b88`
- `0x1800793cc`
- `0x18007cf9c`
- `0x18007daa4`
- `0x18007fc7c`
- `0x18007fca0`
- `0x180080424`
- `0x180080468`
- `0x180098d04`
- `0x18009fb80`
- `0x1800adad8`
- `0x1800adb74`
- `0x1800ae5a8`
- `0x1800ae784`
- `0x1800aeb4c`
- `0x1800c12b8`
- `0x1800c1e94`
- `0x1800de908`
- `0x1800f0f40`
- `0x180199514`
- `0x180199a48`
- `0x1801c1df4`
- `0x1801f8310`
- `0x1801fb94c`
- `0x180241638`
- `0x180241710`
- `0x180242d0c`
- `0x180242de4`
- `0x18024320c`
- `0x180243264`
- `0x180247e3c`
- `0x180280968`
- `0x1802e7c48`
- `0x1802f8640`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800adfee`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800ae177`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800ae202`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800ae280`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800ae47c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800adfee`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800ae177`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800ae202`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800ae280`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1800ae47c`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1800ae1a7`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1800ae1ca`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1800ae1a7`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1800ae1ca`

## string_xrefs

- `0x1800ae1f6`: `setdll`
- `0x1800adc36`: `Unable to copy shell command string\n`
- `0x1800ae263`: `Added %s to extension DLL chain\n`
- `0x1800ae54c`: `Syntax error in extension string\n`
- `0x1800ae2d8`: `Warning: Deferring unload of '%s' extension.  Objects are still active.\n`
- `0x1800ae453`: `No extension named '%s' in chain\n`
- `0x1800ae45c`: `Error: Extension could not be unloaded.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall ParseBangCmd(struct DebugClient *a1, int a2)
{
  struct DebugClient *v3; // r15
  int v4; // edi
  Debugger::DataModel::Host::DataModelHost *v5; // r13
  unsigned __int16 *v6; // rsi
  unsigned __int16 *v7; // r14
  unsigned __int16 *v8; // rcx
  unsigned __int16 *v9; // rbx
  __int64 v10; // rdx
  unsigned __int16 *v11; // rax
  wchar_t *v12; // rbx
  bool v13; // cl
  int v14; // edx
  unsigned int v15; // r14d
  __int64 v16; // rdx
  const unsigned __int16 *v17; // rax
  struct IModelObject *v18; // rdx
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // rax
  bool v21; // cl
  int v22; // edx
  unsigned int v23; // esi
  unsigned __int16 *v24; // rsi
  unsigned __int16 *v25; // rcx
  struct ExtensionInfo *v26; // r14
  unsigned __int16 *v27; // r14
  char v28; // bl
  char v29; // bl
  __int64 v30; // rdx
  const unsigned __int16 *v31; // rax
  const unsigned __int16 *v32; // r8
  unsigned __int16 *v33; // rdx
  ExtensionInfo *v34; // rcx
  char v35; // bl
  struct TargetInfo *v36; // rdx
  char v37; // r12
  __int64 v38; // rdx
  wchar_t *v39; // rax
  struct TargetInfo *v40; // rdx
  bool v41; // cl
  __int64 v42; // rax
  __int64 v43; // rdx
  const unsigned __int16 *v44; // rax
  __int64 v45; // [rsp+0h] [rbp-598h] BYREF
  int *v46; // [rsp+20h] [rbp-578h]
  unsigned __int16 v47; // [rsp+40h] [rbp-558h] BYREF
  unsigned __int16 *v48; // [rsp+48h] [rbp-550h] BYREF
  struct IModelObject *v49; // [rsp+50h] [rbp-548h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-540h] BYREF
  unsigned __int16 *v51; // [rsp+60h] [rbp-538h] BYREF
  int v52; // [rsp+68h] [rbp-530h] BYREF
  struct DebugClient *v53; // [rsp+70h] [rbp-528h] BYREF
  unsigned __int16 **v54; // [rsp+78h] [rbp-520h]
  unsigned __int16 *v55; // [rsp+88h] [rbp-510h]
  __int16 v56; // [rsp+90h] [rbp-508h]
  __int64 v57; // [rsp+98h] [rbp-500h]
  __int128 v58; // [rsp+A0h] [rbp-4F8h] BYREF
  __int128 v59; // [rsp+B0h] [rbp-4E8h]
  __int128 v60; // [rsp+C0h] [rbp-4D8h] BYREF
  __int128 v61; // [rsp+D0h] [rbp-4C8h]
  _BYTE v62[32]; // [rsp+E0h] [rbp-4B8h] BYREF
  _BYTE v63[32]; // [rsp+100h] [rbp-498h] BYREF
  _BYTE v64[32]; // [rsp+120h] [rbp-478h] BYREF
  unsigned __int16 *v65; // [rsp+140h] [rbp-458h] BYREF
  unsigned int v66; // [rsp+14Ch] [rbp-44Ch]

  v57 = -2;
  v3 = a1;
  v53 = a1;
  v4 = 0;
  v48 = 0;
  String1 = 0;
  DbsDeclDynamicString<unsigned short,512,1>::DbsDeclDynamicString<unsigned short,512,1>(&v65);
  v49 = 0;
  if ( *g_CurCmd == 33 )
  {
    ++g_CurCmd;
    DotShell(0, v3);
    *g_CurCmd = 0;
    goto LABEL_123;
  }
  v5 = (Debugger::DataModel::Host::DataModelHost *)Debugger::DataModel::Host::DataModelHost::s_pHostSingleton;
  GetNextChar((const unsigned __int16 **)&g_CurCmd);
  if ( !DbsDynamicString<unsigned short>::CopyStr(&v65, g_CurCmd, 0xFFFFFFFFLL) )
  {
    ErrOut(L"Unable to copy shell command string\n");
    goto LABEL_123;
  }
  v6 = v65;
  v48 = v65;
  String1 = 0;
  v52 = 0;
  v7 = 0;
  v8 = 0;
  while ( 1 )
  {
    v9 = v6;
    v51 = v6;
    if ( *v6 == 32 || *v6 == 9 )
    {
      *v6++ = 0;
      v51 = v9 + 1;
LABEL_37:
      DebuggerEngineCommandExecutionTraceLoggingHelper::Global_AppendToSingleCommandName(v48);
      while ( 1 )
      {
        if ( *v9 == 46 )
          goto LABEL_42;
        if ( v9 == v48 )
          break;
        --v9;
      }
      if ( *v9 == 46 )
      {
LABEL_42:
        if ( !a2 )
        {
          *v9 = 0;
          String1 = v9 + 1;
          v19 = v48;
LABEL_45:
          if ( !v19 && !a2 )
          {
            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v49);
            if ( (int)Debugger::DataModel::Host::DataModelHost::GetFunctionAlias(v5, String1, &v49) >= 0 )
            {
              if ( v49 )
              {
                v20 = 0;
                if ( v66 >= 2 )
                  v20 = v65;
                v12 = &g_CurCmd[v6 - v20];
                g_CurCmd = v12;
                v21 = 0;
                v22 = 9217;
                while ( 1 )
                {
                  while ( 1 )
                  {
                    v23 = *v12;
                    if ( v23 <= 0xD && _bittest(&v22, v23) )
                    {
LABEL_56:
                      v53 = (struct DebugClient *)v12;
                      LOWORD(v54) = v23;
                      *v12 = 0;
                      ExtensionInfo::CallAlias(String1, (struct IModelObject *)0x2401, g_CurCmd);
                      *v12 = v23;
                      goto LABEL_30;
                    }
                    if ( v23 != 59 )
                      break;
                    if ( !v21 )
                      goto LABEL_56;
LABEL_59:
                    ++v12;
                  }
                  if ( v23 != 92 )
                  {
                    if ( v23 == 34 )
                      v21 = !v21;
                    goto LABEL_59;
                  }
                  if ( *++v12 == 34 )
                    goto LABEL_59;
                }
              }
            }
          }
          v24 = BufferStringValue(&v51, 0x1Cu, 0, &v47, 0);
          v55 = v24;
          if ( !v24 )
            goto LABEL_122;
          v25 = 0;
          if ( v66 >= 2 )
            v25 = v65;
          g_CurCmd += v51 - v25;
          if ( v48 )
          {
            v26 = ExtensionInfo::CheckAdd(v3, v48, 0, 0, (bool)v46);
            if ( !v26 )
              goto LABEL_123;
          }
          else
          {
            v26 = ExtensionInfo::s_Chain;
          }
          if ( !_wcsicmp(String1, L"load") )
          {
            if ( v48 )
              goto LABEL_123;
            v27 = 0;
            v51 = 0;
            std::wstring::wstring(&v60);
            v28 = IsFolderAndDllFileName(&v60);
            std::wstring::_Tidy_deallocate(&v60);
            if ( !v28 )
            {
              try
              {
                v60 = 0;
                v61 = 0;
                v29 = 0;
                LOBYTE(v47) = 0;
                if ( (unsigned int)PushOutCtl(3u, v3, (struct OutCtlSave *)&v60, 0) )
                {
                  v29 = 1;
                  LOBYTE(v47) = 1;
                  std::wstring::wstring(v62);
                  std::wstring::wstring(v63);
                  GetFileNameNoExtensionFromPathName(&v58, v62, v63, 0);
                  if ( (_QWORD)v59 )
                  {
                    v31 = (const unsigned __int16 *)std::wstring::c_str(&v58, v30);
                    v27 = (unsigned __int16 *)ExtensionInfo::CheckAdd(v3, v31, 0, L"ExplicitLoad", (bool)v46);
                    v51 = v27;
                  }
                  std::wstring::_Tidy_deallocate(&v58);
                  std::wstring::_Tidy_deallocate(v63);
                  std::wstring::_Tidy_deallocate(v62);
                }
              }
              catch ( ... )
              {
                v24 = v55;
                v27 = v51;
                v29 = v47;
                v3 = v53;
              }
              if ( v29 )
                PopOutCtl((struct OutCtlSave *)&v60);
              if ( v27 )
                goto LABEL_123;
            }
            v32 = 0;
            v33 = v24;
LABEL_90:
            ExtensionInfo::CheckAdd(v3, v33, v32, L"ExplicitLoad", (bool)v46);
            goto LABEL_123;
          }
          if ( !_wcsicmp(String1, L"loadby") )
          {
            if ( v48 )
              goto LABEL_123;
            v48 = v24;
            do
            {
              if ( !*++v24 )
                goto LABEL_122;
            }
            while ( !iswspace(*v24) );
            if ( *v24 )
            {
              *v24 = 0;
              do
                ++v24;
              while ( iswspace(*v24) );
              v32 = v24;
              v33 = v48;
              goto LABEL_90;
            }
LABEL_122:
            ErrOut(L"Syntax error in extension string\n");
            goto LABEL_123;
          }
          if ( !_wcsicmp(String1, L"setdll") )
          {
            if ( v48 || (v26 = ExtensionInfo::CheckAdd(v3, v24, 0, L"ExplicitLoad", (bool)v46)) != 0 )
            {
              ExtensionInfo::Unlink(v26);
              ExtensionInfo::Link(v34);
              if ( v48 )
              {
                if ( !*((_QWORD *)v26 + 206) )
                  dprintf(L"Added %s to extension DLL chain\n", *((_QWORD *)v26 + 1));
              }
            }
            goto LABEL_123;
          }
          if ( _wcsicmp(String1, L"unload") )
          {
            if ( _wcsicmp(String1, L"unloadall") )
            {
              if ( a2 )
                ReportError(0x1001u, 0);
              std::wstring::wstring(v64);
              v42 = _lambda_76f9c64a032fbd1a1a45cf69e5e1ac85_::_lambda_76f9c64a032fbd1a1a45cf69e5e1ac85_(
                      &v53,
                      v64,
                      &v48,
                      &String1);
              Debugger::Utils::ConvertException__lambda_08447e234112fb2f8cf1c7e9b987b1be___(v42);
              v44 = (const unsigned __int16 *)std::wstring::c_str(v64, v43);
              LOBYTE(v4) = v48 != 0;
              ExtensionInfo::CallAny(v3, v26, String1, v24, v4, 1, v44, &v52);
              std::wstring::_Tidy_deallocate(v64);
            }
            else
            {
              ++g_EngNotify;
              ExtensionInfo::DeleteAll(v41);
              --g_EngNotify;
              NotifyChangeEngineState(0x400u, 0, 1);
            }
            goto LABEL_123;
          }
          if ( !v48 )
          {
            if ( *v24 )
            {
              v26 = 0;
              v51 = 0;
              std::wstring::wstring(v62);
              v35 = IsFolderAndDllFileName(v62);
              std::wstring::_Tidy_deallocate(v62);
              if ( v35 )
                goto LABEL_136;
              try
              {
                v58 = 0;
                v59 = 0;
                v37 = 0;
                LOBYTE(v47) = 0;
                if ( (unsigned int)PushOutCtl(3u, v3, (struct OutCtlSave *)&v58, 0) )
                {
                  v37 = 1;
                  LOBYTE(v47) = 1;
                  std::wstring::wstring(v63);
                  std::wstring::wstring(v62);
                  GetFileNameNoExtensionFromPathName(&v60, v63, v62, 0);
                  if ( (_QWORD)v61 )
                  {
                    v39 = (wchar_t *)std::wstring::c_str(&v60, v38);
                    v26 = ExtensionInfo::FindByName(v39, v40);
                    v51 = (unsigned __int16 *)v26;
                  }
                  std::wstring::_Tidy_deallocate(&v60);
                  std::wstring::_Tidy_deallocate(v62);
                  std::wstring::_Tidy_deallocate(v63);
                }
              }
              catch ( ... )
              {
                v36 = (struct TargetInfo *)&v45;
                v26 = (struct ExtensionInfo *)v51;
                v24 = v55;
                v37 = v47;
              }
              if ( v37 )
                PopOutCtl((struct OutCtlSave *)&v58);
              if ( !v26 )
              {
LABEL_136:
                v26 = ExtensionInfo::FindByName(v24, v36);
                if ( !v26 )
                {
                  ErrOut(L"No extension named '%s' in chain\n", v24);
                  goto LABEL_123;
                }
              }
LABEL_102:
              if ( !ExtensionInfo::Delete(v26, 1) )
              {
                if ( *((_DWORD *)v26 + 418) == 3 )
                  WarnOut(L"Warning: Deferring unload of '%s' extension.  Objects are still active.\n", v24);
                else
                  ErrOut(L"Error: Extension could not be unloaded.\n", v24);
              }
              goto LABEL_123;
            }
            v26 = ExtensionInfo::s_Chain;
          }
          if ( !v26 )
            goto LABEL_123;
          goto LABEL_102;
        }
      }
      String1 = v48;
      v19 = 0;
      v48 = 0;
      goto LABEL_45;
    }
    if ( *v6 <= 0x3Bu )
    {
      v10 = 0x800000400000001LL;
      if ( _bittest64(&v10, *v6) )
        goto LABEL_37;
    }
    if ( *v6 == 46 )
    {
      v7 = v6;
      goto LABEL_19;
    }
    if ( *v6 == 40 && !v7 && !v8 && !a2 )
      break;
LABEL_19:
    ++v6;
  }
  *v6 = 0;
  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v49);
  if ( (int)Debugger::DataModel::Host::DataModelHost::GetFunctionAlias(v5, v65, &v49) < 0 || !v49 )
  {
    *v6 = 40;
    v8 = v6;
    goto LABEL_19;
  }
  v11 = 0;
  if ( v66 >= 2 )
    v11 = v65;
  v12 = &g_CurCmd[v6 - v11];
  g_CurCmd = v12;
  v13 = 0;
  v14 = 9217;
  while ( 1 )
  {
    v15 = *v12;
    if ( v15 <= 0xD )
    {
      if ( _bittest(&v14, v15) )
        break;
    }
    if ( v15 == 59 )
    {
      if ( !v13 )
        break;
      goto LABEL_33;
    }
    if ( v15 != 92 )
    {
      if ( v15 == 34 )
        v13 = !v13;
LABEL_33:
      ++v12;
      continue;
    }
    if ( *++v12 == 34 )
      goto LABEL_33;
  }
  v55 = v12;
  v56 = v15;
  *v12 = 0;
  std::wstring::wstring(&v58);
  v53 = (struct DebugClient *)&v58;
  v54 = &v65;
  if ( (int)Debugger::Utils::ConvertException__lambda_89c4ab373aae663c84270ad3efbe5815___(&v53) < 0 )
    ErrOut(L"Internal error in execution of '%s' function alias", v65);
  *v6 = 40;
  v17 = (const unsigned __int16 *)std::wstring::c_str(&v58, v16);
  ExtensionInfo::CallAlias(v17, v18, g_CurCmd);
  std::wstring::_Tidy_deallocate(&v58);
  *v12 = v15;
LABEL_30:
  g_CurCmd = v12;
  GetNextChar((const unsigned __int16 **)&g_CurCmd);
LABEL_123:
  Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v49);
  DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&v65);
}

```

## disassembly

```asm
0x1800adb74  mov     r11, rsp
0x1800adb77  push    rdi
0x1800adb78  push    r12
0x1800adb7a  push    r13
0x1800adb7c  push    r14
0x1800adb7e  push    r15
0x1800adb80  sub     rsp, 570h
0x1800adb87  mov     qword ptr [r11-500h], 0FFFFFFFFFFFFFFFEh
0x1800adb92  mov     [r11+10h], rbx
0x1800adb96  mov     [r11+18h], rsi
0x1800adb9a  mov     rax, cs:__security_cookie
0x1800adba1  xor     rax, rsp
0x1800adba4  mov     [rsp+598h+var_38], rax
0x1800adbac  mov     r12d, edx
0x1800adbaf  mov     r15, rcx
0x1800adbb2  mov     [rsp+598h+var_528], rcx
0x1800adbb7  xor     edi, edi
0x1800adbb9  mov     [rsp+598h+var_550], rdi
0x1800adbbe  mov     [rsp+598h+String1], rdi
0x1800adbc3  lea     rcx, [r11-458h]
0x1800adbca  call    ??0?$DbsDeclDynamicString@G$0CAA@$00@@QEAA@XZ; DbsDeclDynamicString<ushort,512,1>::DbsDeclDynamicString<ushort,512,1>(void)
0x1800adbcf  nop
0x1800adbd0  mov     [rsp+598h+var_548], rdi
0x1800adbd5  mov     rax, cs:?g_CurCmd@@3PEAGEA; ushort * g_CurCmd
0x1800adbdc  cmp     word ptr [rax], 21h ; '!'
0x1800adbe0  jnz     short loc_1800ADC06
0x1800adbe2  add     rax, 2
0x1800adbe6  mov     cs:?g_CurCmd@@3PEAGEA, rax; ushort * g_CurCmd
0x1800adbed  mov     rdx, r15; struct DebugClient *
0x1800adbf0  xor     ecx, ecx; struct _DOT_COMMAND *
0x1800adbf2  call    ?DotShell@@YAXPEAU_DOT_COMMAND@@PEAVDebugClient@@@Z; DotShell(_DOT_COMMAND *,DebugClient *)
0x1800adbf7  mov     rax, cs:?g_CurCmd@@3PEAGEA; ushort * g_CurCmd
0x1800adbfe  mov     [rax], di
0x1800adc01  jmp     loc_1800AE559
0x1800adc06  mov     r13, cs:?s_pHostSingleton@DataModelHost@Host@DataModel@Debugger@@0PEAV1234@EA; Debugger::DataModel::Host::DataModelHost * Debugger::DataModel::Host::DataModelHost::s_pHostSingleton
0x1800adc0d  lea     rcx, ?g_CurCmd@@3PEAGEA; unsigned __int16 **
0x1800adc14  call    ?GetNextChar@@YAGPEAPEBG@Z; GetNextChar(ushort const * *)
0x1800adc19  or      r8d, 0FFFFFFFFh
0x1800adc1d  mov     rdx, cs:?g_CurCmd@@3PEAGEA; ushort * g_CurCmd
0x1800adc24  lea     rcx, [rsp+598h+var_458]
0x1800adc2c  call    ?CopyStr@?$DbsDynamicString@G@@QEAAPEAGPEBGK@Z; DbsDynamicString<ushort>::CopyStr(ushort const *,ulong)
0x1800adc31  test    rax, rax
0x1800adc34  jnz     short loc_1800ADC42
0x1800adc36  lea     rcx, aUnableToCopySh; "Unable to copy shell command string\n"
0x1800adc3d  jmp     loc_1800AE553
0x1800adc42  mov     rsi, [rsp+598h+var_458]
0x1800adc4a  mov     [rsp+598h+var_550], rsi
0x1800adc4f  mov     [rsp+598h+String1], rdi
0x1800adc54  mov     [rsp+598h+var_530], edi
0x1800adc58  mov     r14, rdi
0x1800adc5b  mov     rcx, rdi
0x1800adc5e  mov     eax, 28h ; '('
0x1800adc63  mov     rbx, rsi
0x1800adc66  mov     [rsp+598h+var_538], rsi
0x1800adc6b  cmp     word ptr [rsi], 20h ; ' '
0x1800adc6f  jz      loc_1800ADE2B
0x1800adc75  cmp     word ptr [rsi], 9
0x1800adc79  jz      loc_1800ADE2B
0x1800adc7f  cmp     word ptr [rsi], 3Bh ; ';'
0x1800adc83  ja      short loc_1800ADCA1
0x1800adc85  movzx   eax, word ptr [rsi]
0x1800adc88  mov     rdx, 800000400000001h
0x1800adc92  bt      rdx, rax
0x1800adc96  jb      loc_1800ADE37
0x1800adc9c  mov     eax, 28h ; '('
0x1800adca1  cmp     word ptr [rsi], 2Eh ; '.'
0x1800adca5  jnz     short loc_1800ADCAC
0x1800adca7  mov     r14, rbx
0x1800adcaa  jmp     short loc_1800ADCF8
0x1800adcac  cmp     [rsi], ax
0x1800adcaf  jnz     short loc_1800ADCF8
0x1800adcb1  test    r14, r14
0x1800adcb4  jnz     short loc_1800ADCF8
0x1800adcb6  test    rcx, rcx
0x1800adcb9  jnz     short loc_1800ADCF8
0x1800adcbb  test    r12d, r12d
0x1800adcbe  jnz     short loc_1800ADCF8
0x1800adcc0  mov     [rsi], di
0x1800adcc3  lea     rcx, [rsp+598h+var_548]
0x1800adcc8  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1800adccd  lea     r8, [rsp+598h+var_548]; struct IModelObject **
0x1800adcd2  mov     rdx, [rsp+598h+var_458]; unsigned __int16 *
0x1800adcda  mov     rcx, r13; this
0x1800adcdd  call    ?GetFunctionAlias@DataModelHost@Host@DataModel@Debugger@@QEAAJPEBGPEAPEAUIModelObject@@@Z; Debugger::DataModel::Host::DataModelHost::GetFunctionAlias(ushort const *,IModelObject * *)
0x1800adce2  test    eax, eax
0x1800adce4  js      short loc_1800ADCED
0x1800adce6  cmp     [rsp+598h+var_548], rdi
0x1800adceb  jnz     short loc_1800ADD01
0x1800adced  mov     eax, 28h ; '('
0x1800adcf2  mov     [rsi], ax
0x1800adcf5  mov     rcx, rbx
0x1800adcf8  lea     rsi, [rbx+2]
0x1800adcfc  jmp     loc_1800ADC63
0x1800add01  mov     rax, rdi
0x1800add04  cmp     [rsp+598h+var_44C], 2
0x1800add0c  cmovnb  rax, [rsp+598h+var_458]
0x1800add15  sub     rbx, rax
0x1800add18  sar     rbx, 1
0x1800add1b  mov     rax, cs:?g_CurCmd@@3PEAGEA; ushort * g_CurCmd
0x1800add22  lea     rbx, [rax+rbx*2]
0x1800add26  mov     cs:?g_CurCmd@@3PEAGEA, rbx; ushort * g_CurCmd
0x1800add2d  mov     cl, dil
0x1800add30  mov     edx, 2401h
0x1800add35  movzx   r14d, word ptr [rbx]
0x1800add39  cmp     r14d, 0Dh
0x1800add3d  ja      short loc_1800ADD45
0x1800add3f  bt      edx, r14d
0x1800add43  jb      short loc_1800ADD57
0x1800add45  cmp     r14d, 3Bh ; ';'
0x1800add49  jnz     loc_1800ADE01
0x1800add4f  test    cl, cl
0x1800add51  jnz     loc_1800ADE15
0x1800add57  mov     [rsp+598h+var_510], rbx
0x1800add5f  mov     [rsp+598h+var_508], r14w
0x1800add68  mov     [rbx], di
0x1800add6b  lea     rcx, [rsp+598h+var_4F8]
0x1800add73  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800add78  nop
0x1800add79  lea     rax, [rsp+598h+var_4F8]
0x1800add81  mov     [rsp+598h+var_528], rax
0x1800add86  lea     rax, [rsp+598h+var_458]
0x1800add8e  mov     [rsp+598h+var_520], rax
0x1800add93  lea     rcx, [rsp+598h+var_528]
0x1800add98  call    Debugger__Utils__ConvertException__lambda_89c4ab373aae663c84270ad3efbe5815___
0x1800add9d  test    eax, eax
0x1800add9f  jns     short loc_1800ADDB5
0x1800adda1  mov     rdx, [rsp+598h+var_458]
0x1800adda9  lea     rcx, aInternalErrorI_0; "Internal error in execution of '%s' fun"...
0x1800addb0  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800addb5  mov     word ptr [rsi], 28h ; '('
0x1800addba  lea     rcx, [rsp+598h+var_4F8]
0x1800addc2  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1800addc7  mov     rcx, rax; unsigned __int16 *
0x1800addca  mov     r8, cs:?g_CurCmd@@3PEAGEA; unsigned __int16 *
0x1800addd1  call    ?CallAlias@ExtensionInfo@@SAJPEBGPEAUIModelObject@@0@Z; ExtensionInfo::CallAlias(ushort const *,IModelObject *,ushort const *)
0x1800addd6  nop
0x1800addd7  lea     rcx, [rsp+598h+var_4F8]
0x1800adddf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800adde4  nop
0x1800adde5  mov     [rbx], r14w
0x1800adde9  mov     cs:?g_CurCmd@@3PEAGEA, rbx; ushort * g_CurCmd
0x1800addf0  lea     rcx, ?g_CurCmd@@3PEAGEA; unsigned __int16 **
0x1800addf7  call    ?GetNextChar@@YAGPEAPEBG@Z; GetNextChar(ushort const * *)
0x1800addfc  jmp     loc_1800AE559
0x1800ade01  cmp     r14d, 5Ch ; '\'
0x1800ade05  jnz     short loc_1800ADE1E
0x1800ade07  add     rbx, 2
0x1800ade0b  cmp     word ptr [rbx], 22h ; '"'
0x1800ade0f  jnz     loc_1800ADD35
0x1800ade15  add     rbx, 2
0x1800ade19  jmp     loc_1800ADD35
0x1800ade1e  cmp     r14d, 22h ; '"'
0x1800ade22  jnz     short loc_1800ADE15
0x1800ade24  test    cl, cl
0x1800ade26  setz    cl
0x1800ade29  jmp     short loc_1800ADE15
0x1800ade2b  mov     [rsi], di
0x1800ade2e  lea     rsi, [rbx+2]
0x1800ade32  mov     [rsp+598h+var_538], rsi
0x1800ade37  mov     rcx, [rsp+598h+var_550]; unsigned __int16 *
0x1800ade3c  call    ?Global_AppendToSingleCommandName@DebuggerEngineCommandExecutionTraceLoggingHelper@@SAXPEBG@Z; DebuggerEngineCommandExecutionTraceLoggingHelper::Global_AppendToSingleCommandName(ushort const *)
0x1800ade41  mov     rax, [rsp+598h+var_550]
0x1800ade46  cmp     word ptr [rbx], 2Eh ; '.'
0x1800ade4a  jz      short loc_1800ADE5D
0x1800ade4c  cmp     rbx, rax
0x1800ade4f  jz      short loc_1800ADE57
0x1800ade51  sub     rbx, 2
0x1800ade55  jmp     short loc_1800ADE46
0x1800ade57  cmp     word ptr [rbx], 2Eh ; '.'
0x1800ade5b  jnz     short loc_1800ADE75
0x1800ade5d  test    r12d, r12d
0x1800ade60  jnz     short loc_1800ADE75
0x1800ade62  mov     [rbx], di
0x1800ade65  lea     rax, [rbx+2]
0x1800ade69  mov     [rsp+598h+String1], rax
0x1800ade6e  mov     rax, [rsp+598h+var_550]
0x1800ade73  jmp     short loc_1800ADE82
0x1800ade75  mov     [rsp+598h+String1], rax
0x1800ade7a  mov     rax, rdi
0x1800ade7d  mov     [rsp+598h+var_550], rax
0x1800ade82  test    rax, rax
0x1800ade85  jnz     loc_1800ADF55
0x1800ade8b  test    r12d, r12d
0x1800ade8e  jnz     loc_1800ADF55
0x1800ade94  lea     rcx, [rsp+598h+var_548]
0x1800ade99  call    ?InternalRelease@?$ComPtr@VInjectedInlineFrame@Host@TargetComposition@Debugger@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(void)
0x1800ade9e  lea     r8, [rsp+598h+var_548]; struct IModelObject **
0x1800adea3  mov     rdx, [rsp+598h+String1]; unsigned __int16 *
0x1800adea8  mov     rcx, r13; this
0x1800adeab  call    ?GetFunctionAlias@DataModelHost@Host@DataModel@Debugger@@QEAAJPEBGPEAPEAUIModelObject@@@Z; Debugger::DataModel::Host::DataModelHost::GetFunctionAlias(ushort const *,IModelObject * *)
0x1800adeb0  test    eax, eax
0x1800adeb2  js      loc_1800ADF55
0x1800adeb8  cmp     [rsp+598h+var_548], rdi
0x1800adebd  jz      loc_1800ADF55
0x1800adec3  mov     rax, rdi
0x1800adec6  cmp     [rsp+598h+var_44C], 2
0x1800adece  cmovnb  rax, [rsp+598h+var_458]
0x1800aded7  sub     rsi, rax
0x1800adeda  sar     rsi, 1
0x1800adedd  mov     rax, cs:?g_CurCmd@@3PEAGEA; ushort * g_CurCmd
0x1800adee4  lea     rbx, [rax+rsi*2]
0x1800adee8  mov     cs:?g_CurCmd@@3PEAGEA, rbx; ushort * g_CurCmd
0x1800adeef  mov     cl, dil
0x1800adef2  mov     edx, 2401h; struct IModelObject *
0x1800adef7  movzx   esi, word ptr [rbx]
0x1800adefa  cmp     esi, 0Dh
0x1800adefd  ja      short loc_1800ADF04
0x1800adeff  bt      edx, esi
0x1800adf02  jb      short loc_1800ADF0D
0x1800adf04  cmp     esi, 3Bh ; ';'
0x1800adf07  jnz     short loc_1800ADF34
0x1800adf09  test    cl, cl
0x1800adf0b  jnz     short loc_1800ADF43
0x1800adf0d  mov     [rsp+598h+var_528], rbx
0x1800adf12  mov     word ptr [rsp+598h+var_520], si
0x1800adf17  mov     [rbx], di
0x1800adf1a  mov     r8, cs:?g_CurCmd@@3PEAGEA; unsigned __int16 *
0x1800adf21  mov     rcx, [rsp+598h+String1]; unsigned __int16 *
0x1800adf26  call    ?CallAlias@ExtensionInfo@@SAJPEBGPEAUIModelObject@@0@Z; ExtensionInfo::CallAlias(ushort const *,IModelObject *,ushort const *)
0x1800adf2b  nop
0x1800adf2c  mov     [rbx], si
0x1800adf2f  jmp     loc_1800ADDE9
0x1800adf34  cmp     esi, 5Ch ; '\'
0x1800adf37  jnz     short loc_1800ADF49
0x1800adf39  add     rbx, 2
0x1800adf3d  cmp     word ptr [rbx], 22h ; '"'
0x1800adf41  jnz     short loc_1800ADEF7
0x1800adf43  add     rbx, 2
0x1800adf47  jmp     short loc_1800ADEF7
0x1800adf49  cmp     esi, 22h ; '"'
0x1800adf4c  jnz     short loc_1800ADF43
0x1800adf4e  test    cl, cl
0x1800adf50  setz    cl
0x1800adf53  jmp     short loc_1800ADF43
0x1800adf55  mov     [rsp+598h+var_578], rdi; bool
0x1800adf5a  lea     r9, [rsp+598h+var_558]; unsigned __int16 *
0x1800adf5f  xor     r8d, r8d; unsigned int *
0x1800adf62  lea     edx, [r8+1Ch]; unsigned int
0x1800adf66  lea     rcx, [rsp+598h+var_538]; unsigned __int16 **
0x1800adf6b  call    ?BufferStringValue@@YAPEAGPEAPEAGKPEAKPEAGPEAH@Z; BufferStringValue(ushort * *,ulong,ulong *,ushort *,int *)
0x1800adf70  mov     rsi, rax
0x1800adf73  mov     [rsp+598h+var_510], rax
0x1800adf7b  test    rax, rax
0x1800adf7e  jz      loc_1800AE54C
0x1800adf84  mov     rcx, rdi
0x1800adf87  cmp     [rsp+598h+var_44C], 2
0x1800adf8f  cmovnb  rcx, [rsp+598h+var_458]
0x1800adf98  mov     rdx, [rsp+598h+var_538]
0x1800adf9d  sub     rdx, rcx
0x1800adfa0  sar     rdx, 1
0x1800adfa3  mov     rcx, cs:?g_CurCmd@@3PEAGEA; ushort * g_CurCmd
0x1800adfaa  lea     rax, [rcx+rdx*2]
0x1800adfae  mov     cs:?g_CurCmd@@3PEAGEA, rax; ushort * g_CurCmd
0x1800adfb5  mov     rdx, [rsp+598h+var_550]; unsigned __int16 *
0x1800adfba  test    rdx, rdx
0x1800adfbd  jz      short loc_1800ADFDB
0x1800adfbf  xor     r9d, r9d; unsigned __int16 *
0x1800adfc2  xor     r8d, r8d; unsigned __int16 *
0x1800adfc5  mov     rcx, r15; struct DebugClient *
0x1800adfc8  call    ?CheckAdd@ExtensionInfo@@SAPEAV1@PEAVDebugClient@@PEBG11_N@Z; ExtensionInfo::CheckAdd(DebugClient *,ushort const *,ushort const *,ushort const *,bool)
0x1800adfcd  mov     r14, rax
0x1800adfd0  test    rax, rax
0x1800adfd3  jz      loc_1800AE559
0x1800adfd9  jmp     short loc_1800ADFE2
0x1800adfdb  mov     r14, cs:?s_Chain@ExtensionInfo@@2PEAV1@EA; ExtensionInfo * ExtensionInfo::s_Chain
0x1800adfe2  lea     rdx, aLoad_0; "load"
0x1800adfe9  mov     rcx, [rsp+598h+String1]; String1
0x1800adfee  call    cs:__imp__wcsicmp
0x1800adff5  nop     dword ptr [rax+rax+00h]
0x1800adffa  test    eax, eax
0x1800adffc  jnz     loc_1800AE16B
0x1800ae002  cmp     [rsp+598h+var_550], rdi
0x1800ae007  jnz     loc_1800AE559
0x1800ae00d  mov     r14, rdi
0x1800ae010  mov     [rsp+598h+var_538], rdi
0x1800ae015  mov     rdx, rsi
0x1800ae018  lea     rcx, [rsp+598h+var_4D8]
0x1800ae020  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ae025  nop
0x1800ae026  lea     rcx, [rsp+598h+var_4D8]
0x1800ae02e  call    ?IsFolderAndDllFileName@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IsFolderAndDllFileName(std::wstring const &)
0x1800ae033  mov     bl, al
0x1800ae035  lea     rcx, [rsp+598h+var_4D8]
0x1800ae03d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ae042  test    bl, bl
0x1800ae044  jnz     loc_1800AE163
0x1800ae04a  xorps   xmm0, xmm0
0x1800ae04d  movups  [rsp+598h+var_4D8], xmm0
0x1800ae055  movups  [rsp+598h+var_4C8], xmm0
0x1800ae05d  mov     bl, dil
0x1800ae060  mov     byte ptr [rsp+598h+var_558], bl
0x1800ae064  xor     r9d, r9d; unsigned int *
0x1800ae067  lea     r8, [rsp+598h+var_4D8]; struct OutCtlSave *
0x1800ae06f  mov     rdx, r15; struct DebugClient *
0x1800ae072  lea     ecx, [r9+3]; unsigned int
0x1800ae076  call    ?PushOutCtl@@YAHKPEAVDebugClient@@PEAUOutCtlSave@@PEAK@Z; PushOutCtl(ulong,DebugClient *,OutCtlSave *,ulong *)
0x1800ae07b  test    eax, eax
0x1800ae07d  jz      loc_1800AE131
0x1800ae083  mov     ebx, 1
0x1800ae088  mov     byte ptr [rsp+598h+var_558], bl
  ... truncated ...
```
