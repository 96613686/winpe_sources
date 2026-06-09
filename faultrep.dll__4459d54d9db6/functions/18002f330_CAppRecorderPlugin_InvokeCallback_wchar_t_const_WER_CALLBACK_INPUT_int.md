# CAppRecorderPlugin::InvokeCallback(wchar_t const *,_WER_CALLBACK_INPUT *,int *)

- ea: `0x18002f330`
- end: `0x18002f65a`
- name: `?InvokeCallback@CAppRecorderPlugin@@UEAAJPEB_WPEAU_WER_CALLBACK_INPUT@@PEAH@Z`
- size: `810`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *__hidden this, const wchar_t *, struct _WER_CALLBACK_INPUT *, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003b38`
- `0x180009ed8`
- `0x180009f00`
- `0x18002ecac`
- `0x18002f330`
- `0x18002fb3c`
- `0x18002fe98`
- `0x18003056c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f4b8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002f4b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f531`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f531`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18002f46d`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x18002f46d`
- `wer!WerpSetReportFlags` at `0x18002f42f`
- `wer!WerpSetReportFlags` at `0x18002f5be`
- `wer!WerpSetReportFlags` at `0x18002f42f`
- `wer!WerpSetReportFlags` at `0x18002f5be`
- `wer!WerpGetReportFlags` at `0x18002f3e0`
- `wer!WerpGetReportFlags` at `0x18002f5a7`
- `wer!WerpGetReportFlags` at `0x18002f3e0`
- `wer!WerpGetReportFlags` at `0x18002f5a7`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002f523`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002f523`

## string_xrefs

- `0x18002f515`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\AppRecorder`

## pseudocode

```c
__int64 __fastcall CAppRecorderPlugin::InvokeCallback(
        CAppRecorderPlugin *this,
        const wchar_t *a2,
        struct _WER_CALLBACK_INPUT *a3,
        int *a4)
{
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  int ReportFlags; // eax
  unsigned int v11; // ebx
  _BYTE *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v17; // rcx
  int v18; // eax
  signed int LastError; // eax
  int v20; // [rsp+58h] [rbp+10h] BYREF

  v20 = 0;
  if ( a2 && a3 && a4 )
  {
    *a4 = 0;
    if ( (*((_DWORD *)a3 + 2) == 12 || *((_DWORD *)a3 + 2) == 6) && *((_DWORD *)this + 14) )
    {
      if ( !*((_DWORD *)this + 16) )
      {
        v7 = CAppRecorderPlugin::StopRecordingSession(this, *((_DWORD *)this + 10));
        if ( v7 >= 0 )
        {
          *((_DWORD *)this + 16) = 1;
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, *((unsigned int *)this + 10), v7);
        }
      }
      ReportFlags = WerpGetReportFlags(*(_QWORD *)a3, &v20);
      v11 = ReportFlags;
      if ( ReportFlags < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v11;
        v13 = 17;
        goto LABEL_17;
      }
      v15 = *(_QWORD *)a3;
      v20 |= 0x800u;
      ReportFlags = WerpSetReportFlags(v15);
      v11 = ReportFlags;
      if ( ReportFlags < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          return v11;
        v13 = 18;
        goto LABEL_17;
      }
    }
    if ( *((_DWORD *)a3 + 2) == 9
      && *((_DWORD *)a3 + 6) == 2
      && (unsigned __int8)IsGetShellWindowPresent(this, a2)
      && IsWindow(*((HWND *)a3 + 4)) )
    {
      *((_QWORD *)this + 9) = *((_QWORD *)a3 + 4);
      goto LABEL_28;
    }
    if ( *((_DWORD *)a3 + 2) == 1 )
    {
      v17 = *((_QWORD *)a3 + 3);
      if ( v17 )
      {
        if ( *((_QWORD *)a3 + 4) && !(unsigned int)_o__wcsicmp(v17, L"ApplicationRecorder") )
        {
          if ( *((_DWORD *)this + 14) )
          {
            v18 = CAppRecorderPlugin::RemoveAppCompatLayer(this);
            v11 = v18;
            if ( v18 >= 0 )
            {
              if ( !RegDeleteKeyW(
                      HKEY_CURRENT_USER,
                      L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\AppRecorder") )
                goto LABEL_28;
              LastError = GetLastError();
              v11 = LastError;
              if ( LastError > 0 )
                v11 = (unsigned __int16)LastError | 0x80070000;
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids, v11);
                v12 = WPP_GLOBAL_Control;
              }
              if ( (v11 & 0x80000000) == 0 )
                goto LABEL_28;
            }
            else
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
                return v11;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  21,
                  WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids,
                  (unsigned int)v18);
                v12 = WPP_GLOBAL_Control;
              }
            }
            if ( v12 == (_BYTE *)&WPP_GLOBAL_Control || (v12[28] & 1) == 0 )
              return v11;
            v13 = 19;
            v14 = v11;
            goto LABEL_18;
          }
          if ( (int)WerpGetReportFlags(*(_QWORD *)a3, &v20) >= 0 )
            WerpSetReportFlags(*(_QWORD *)a3);
          if ( !*((_DWORD *)this + 15) )
          {
            ReportFlags = CAppRecorderPlugin::EnableAppRecorder(this, *((const wchar_t **)a3 + 4), *(wchar_t **)a3);
            v11 = ReportFlags;
            if ( ReportFlags < 0 )
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                return v11;
              }
              v13 = 20;
LABEL_17:
              v14 = (unsigned int)ReportFlags;
LABEL_18:
              WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids, v14);
              return v11;
            }
          }
LABEL_28:
          v11 = 0;
          *a4 = 1;
          return v11;
        }
      }
    }
    return 2147500033LL;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18002f330  mov     [rsp+arg_0], rbx
0x18002f335  mov     [rsp+arg_10], rbp
0x18002f33a  push    rdi
0x18002f33b  push    r14
0x18002f33d  push    r15
0x18002f33f  sub     rsp, 30h
0x18002f343  mov     [rsp+48h+arg_8], 0
0x18002f34b  mov     r15, r9
0x18002f34e  mov     rdi, r8
0x18002f351  mov     r14, rcx
0x18002f354  test    rdx, rdx
0x18002f357  jz      loc_18002F613
0x18002f35d  test    r8, r8
0x18002f360  jz      loc_18002F613
0x18002f366  test    r9, r9
0x18002f369  jz      loc_18002F613
0x18002f36f  mov     dword ptr [r9], 0
0x18002f376  lea     rbp, WPP_GLOBAL_Control
0x18002f37d  cmp     dword ptr [r8+8], 0Ch
0x18002f382  jz      short loc_18002F38F
0x18002f384  cmp     dword ptr [r8+8], 6
0x18002f389  jnz     loc_18002F454
0x18002f38f  cmp     dword ptr [rcx+38h], 0
0x18002f393  jz      loc_18002F454
0x18002f399  cmp     dword ptr [rcx+40h], 0
0x18002f39d  jnz     short loc_18002F3D8
0x18002f39f  mov     edx, [rcx+28h]; unsigned int
0x18002f3a2  call    ?StopRecordingSession@CAppRecorderPlugin@@AEAAJK@Z; CAppRecorderPlugin::StopRecordingSession(ulong)
0x18002f3a7  test    eax, eax
0x18002f3a9  jns     short loc_18002F3D0
0x18002f3ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f3b2  cmp     rcx, rbp
0x18002f3b5  jz      short loc_18002F3D8
0x18002f3b7  test    byte ptr [rcx+1Ch], 2
0x18002f3bb  jz      short loc_18002F3D8
0x18002f3bd  mov     r9d, [r14+28h]
0x18002f3c1  mov     rcx, [rcx+10h]
0x18002f3c5  mov     [rsp+48h+var_28], eax
0x18002f3c9  call    WPP_SF_dD
0x18002f3ce  jmp     short loc_18002F3D8
0x18002f3d0  mov     dword ptr [r14+40h], 1
0x18002f3d8  mov     rcx, [rdi]
0x18002f3db  lea     rdx, [rsp+48h+arg_8]
0x18002f3e0  call    cs:__imp_WerpGetReportFlags
0x18002f3e6  mov     ebx, eax
0x18002f3e8  test    eax, eax
0x18002f3ea  jns     short loc_18002F420
0x18002f3ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f3f3  cmp     rcx, rbp
0x18002f3f6  jz      loc_18002F488
0x18002f3fc  test    byte ptr [rcx+1Ch], 1
0x18002f400  jz      loc_18002F488
0x18002f406  mov     edx, 11h
0x18002f40b  mov     r9d, eax
0x18002f40e  mov     rcx, [rcx+10h]
0x18002f412  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x18002f419  call    WPP_SF_d
0x18002f41e  jmp     short loc_18002F488
0x18002f420  mov     edx, [rsp+48h+arg_8]
0x18002f424  mov     rcx, [rdi]
0x18002f427  bts     edx, 0Bh
0x18002f42b  mov     [rsp+48h+arg_8], edx
0x18002f42f  call    cs:__imp_WerpSetReportFlags
0x18002f435  mov     ebx, eax
0x18002f437  test    eax, eax
0x18002f439  jns     short loc_18002F454
0x18002f43b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f442  cmp     rcx, rbp
0x18002f445  jz      short loc_18002F488
0x18002f447  test    byte ptr [rcx+1Ch], 1
0x18002f44b  jz      short loc_18002F488
0x18002f44d  mov     edx, 12h
0x18002f452  jmp     short loc_18002F40B
0x18002f454  cmp     dword ptr [rdi+8], 9
0x18002f458  jnz     short loc_18002F48F
0x18002f45a  cmp     dword ptr [rdi+18h], 2
0x18002f45e  jnz     short loc_18002F48F
0x18002f460  call    IsGetShellWindowPresent
0x18002f465  test    al, al
0x18002f467  jz      short loc_18002F48F
0x18002f469  mov     rcx, [rdi+20h]; hWnd
0x18002f46d  call    cs:__imp_IsWindow
0x18002f473  test    eax, eax
0x18002f475  jz      short loc_18002F48F
0x18002f477  mov     rax, [rdi+20h]
0x18002f47b  mov     [r14+48h], rax
0x18002f47f  xor     ebx, ebx
0x18002f481  mov     dword ptr [r15], 1
0x18002f488  mov     eax, ebx
0x18002f48a  jmp     loc_18002F646
0x18002f48f  cmp     dword ptr [rdi+8], 1
0x18002f493  jnz     loc_18002F60C
0x18002f499  mov     rcx, [rdi+18h]
0x18002f49d  test    rcx, rcx
0x18002f4a0  jz      loc_18002F60C
0x18002f4a6  cmp     qword ptr [rdi+20h], 0
0x18002f4ab  jz      loc_18002F60C
0x18002f4b1  lea     rdx, aApplicationrec; "ApplicationRecorder"
0x18002f4b8  call    cs:__imp__o__wcsicmp
0x18002f4be  test    eax, eax
0x18002f4c0  jnz     loc_18002F60C
0x18002f4c6  cmp     [r14+38h], eax
0x18002f4ca  jz      loc_18002F59F
0x18002f4d0  mov     rcx, r14; this
0x18002f4d3  call    ?RemoveAppCompatLayer@CAppRecorderPlugin@@AEAAJXZ; CAppRecorderPlugin::RemoveAppCompatLayer(void)
0x18002f4d8  mov     ebx, eax
0x18002f4da  test    eax, eax
0x18002f4dc  jns     short loc_18002F515
0x18002f4de  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f4e5  cmp     rcx, rbp
0x18002f4e8  jz      short loc_18002F488
0x18002f4ea  test    byte ptr [rcx+1Ch], 1
0x18002f4ee  jz      loc_18002F57F
0x18002f4f4  mov     rcx, [rcx+10h]
0x18002f4f8  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x18002f4ff  mov     edx, 15h
0x18002f504  mov     r9d, eax
0x18002f507  call    WPP_SF_d
0x18002f50c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f513  jmp     short loc_18002F57F
0x18002f515  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\Windows E"...
0x18002f51c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002f523  call    cs:__imp_RegDeleteKeyW
0x18002f529  test    eax, eax
0x18002f52b  jz      loc_18002F47F
0x18002f531  call    cs:__imp_GetLastError
0x18002f537  mov     ebx, eax
0x18002f539  test    eax, eax
0x18002f53b  jle     short loc_18002F546
0x18002f53d  movzx   ebx, ax
0x18002f540  or      ebx, 80070000h
0x18002f546  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f54d  cmp     rcx, rbp
0x18002f550  jz      short loc_18002F577
0x18002f552  test    byte ptr [rcx+1Ch], 4
0x18002f556  jz      short loc_18002F577
0x18002f558  mov     rcx, [rcx+10h]
0x18002f55c  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x18002f563  mov     edx, 16h
0x18002f568  mov     r9d, ebx
0x18002f56b  call    WPP_SF_d
0x18002f570  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f577  test    ebx, ebx
0x18002f579  jns     loc_18002F47F
0x18002f57f  cmp     rcx, rbp
0x18002f582  jz      loc_18002F488
0x18002f588  test    byte ptr [rcx+1Ch], 1
0x18002f58c  jz      loc_18002F488
0x18002f592  mov     edx, 13h
0x18002f597  mov     r9d, ebx
0x18002f59a  jmp     loc_18002F40E
0x18002f59f  mov     rcx, [rdi]
0x18002f5a2  lea     rdx, [rsp+48h+arg_8]
0x18002f5a7  call    cs:__imp_WerpGetReportFlags
0x18002f5ad  test    eax, eax
0x18002f5af  js      short loc_18002F5C4
0x18002f5b1  mov     edx, [rsp+48h+arg_8]
0x18002f5b5  mov     rcx, [rdi]
0x18002f5b8  or      edx, 48000000h
0x18002f5be  call    cs:__imp_WerpSetReportFlags
0x18002f5c4  cmp     dword ptr [r14+3Ch], 0
0x18002f5c9  jnz     loc_18002F47F
0x18002f5cf  mov     r8, [rdi]; void *
0x18002f5d2  mov     rcx, r14; this
0x18002f5d5  mov     rdx, [rdi+20h]; wchar_t *
0x18002f5d9  call    ?EnableAppRecorder@CAppRecorderPlugin@@AEAAJPEB_WPEAX@Z; CAppRecorderPlugin::EnableAppRecorder(wchar_t const *,void *)
0x18002f5de  mov     ebx, eax
0x18002f5e0  test    eax, eax
0x18002f5e2  jns     loc_18002F47F
0x18002f5e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f5ef  cmp     rcx, rbp
0x18002f5f2  jz      loc_18002F488
0x18002f5f8  test    byte ptr [rcx+1Ch], 1
0x18002f5fc  jz      loc_18002F488
0x18002f602  mov     edx, 14h
0x18002f607  jmp     loc_18002F40B
0x18002f60c  mov     eax, 80004001h
0x18002f611  jmp     short loc_18002F646
0x18002f613  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f61a  lea     rbp, WPP_GLOBAL_Control
0x18002f621  cmp     rcx, rbp
0x18002f624  jz      short loc_18002F641
0x18002f626  test    byte ptr [rcx+1Ch], 1
0x18002f62a  jz      short loc_18002F641
0x18002f62c  mov     rcx, [rcx+10h]
0x18002f630  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x18002f637  mov     edx, 0Fh
0x18002f63c  call    WPP_SF_
0x18002f641  mov     eax, 80070057h
0x18002f646  mov     rbx, [rsp+48h+arg_0]
0x18002f64b  mov     rbp, [rsp+48h+arg_10]
0x18002f650  add     rsp, 30h
0x18002f654  pop     r15
0x18002f656  pop     r14
0x18002f658  pop     rdi
0x18002f659  retn
```
