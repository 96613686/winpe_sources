# CFtpDialogTemplate::InitDialog(HWND__ *,int,uint,CFtpFolder *,CFtpPidlList *)

- ea: `0x180010390`
- end: `0x180010584`
- name: `?InitDialog@CFtpDialogTemplate@@QEAAJPEAUHWND__@@HIPEAVCFtpFolder@@PEAVCFtpPidlList@@@Z`
- size: `500`
- prototype: `int(CFtpDialogTemplate *__hidden this, HWND, int, unsigned int, struct CFtpFolder *, struct CFtpPidlList *)`
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18001058c`
- `0x180011eec`
- `0x18001e754`

## callees

- `0x180002240`
- `0x18001016c`
- `0x1800101fc`
- `0x180010390`
- `0x1800108e4`
- `0x1800109dc`
- `0x180010ad4`
- `0x180010cd4`
- `0x180010e2c`
- `0x180010f08`
- `0x1800252fc`

## import_xrefs

- `USER32!GetDlgItem` at `0x1800103e9`
- `USER32!GetDlgItem` at `0x1800103fe`
- `USER32!GetDlgItem` at `0x1800103e9`
- `USER32!GetDlgItem` at `0x1800103fe`

## pseudocode

```c
__int64 __fastcall CFtpDialogTemplate::InitDialog(
        CFtpDialogTemplate *this,
        HWND a2,
        int a3,
        int a4,
        struct CFtpFolder *a5,
        struct CFtpPidlList *a6)
{
  int v6; // r15d
  int v7; // r14d
  HWND v9; // rax
  unsigned int v11; // edi
  HWND DlgItem; // rbx
  HWND v13; // r8
  struct CFtpFolder *v14; // r9
  int inited; // eax
  CFtpDialogTemplate *v16; // rcx
  int v17; // edx
  CFtpDialogTemplate *v18; // rcx
  unsigned __int16 v21[264]; // [rsp+40h] [rbp-258h] BYREF

  v6 = 0;
  v7 = 0;
  v9 = a2;
  *(_DWORD *)this = a3;
  do
  {
    v11 = 0;
    DlgItem = GetDlgItem(v9, v7 + a4);
    v13 = GetDlgItem(a2, v7 + a4 + 20);
    if ( !DlgItem )
      goto LABEL_24;
    if ( v7 )
    {
      if ( v7 == 1 )
      {
        GetItemName(a5, a6, v21, (unsigned int)v14);
        v11 = CFtpDialogTemplate::_ReinsertDlgText(v16, DlgItem, v21, L"%s");
        if ( !*(_DWORD *)this || !(unsigned int)CanEditName(a5, a6) )
          goto LABEL_23;
      }
      else
      {
        switch ( v7 )
        {
          case 2:
            inited = CFtpDialogTemplate::_InitIcon(0, DlgItem, a5, a6);
            break;
          case 3:
            inited = CFtpDialogTemplate::_InitSize((CFtpDialogTemplate *)(unsigned int)(v7 - 3), DlgItem, v13, v14, a6);
            break;
          case 4:
            inited = CFtpDialogTemplate::_InitTime((CFtpDialogTemplate *)(unsigned int)(v7 - 4), DlgItem, v13, a5, a6);
            break;
          case 5:
            inited = CFtpDialogTemplate::_InitType((CFtpDialogTemplate *)(unsigned int)(v7 - 5), DlgItem, a5, a6);
            break;
          case 6:
            inited = CFtpDialogTemplate::_InitLocation((CFtpDialogTemplate *)(unsigned int)(v7 - 6), DlgItem, a5, a6);
            break;
          case 7:
            inited = CFtpDialogTemplate::_ReinsertDlgText(
                       *(CFtpDialogTemplate **)(*((_QWORD *)a6 + 2) + 16LL),
                       DlgItem,
                       (const void *)**(int **)(*((_QWORD *)a6 + 2) + 16LL),
                       L"%u");
            break;
          default:
            goto LABEL_24;
        }
        v11 = inited;
      }
    }
    else
    {
      GetItemName(a5, a6, v21, (unsigned int)v14);
      v11 = CFtpDialogTemplate::_ReinsertDlgText(v18, DlgItem, v21, L"%s");
      if ( *(_DWORD *)this && (unsigned int)CanEditName(a5, a6) )
LABEL_23:
        ShowEnableWindow(DlgItem, v17);
    }
LABEL_24:
    v9 = a2;
    if ( v6 < 0 )
      v11 = v6;
    ++v7;
    v6 = v11;
  }
  while ( v7 < 8 );
  return v11;
}

```

## disassembly

```asm
0x180010390  mov     [rsp+arg_10], rbx
0x180010395  push    rbp
0x180010396  push    rsi
0x180010397  push    rdi
0x180010398  push    r12
0x18001039a  push    r13
0x18001039c  push    r14
0x18001039e  push    r15
0x1800103a0  sub     rsp, 260h
0x1800103a7  mov     rax, cs:__security_cookie
0x1800103ae  xor     rax, rsp
0x1800103b1  mov     [rsp+298h+var_48], rax
0x1800103b9  mov     rbp, [rsp+298h+arg_20]
0x1800103c1  xor     r15d, r15d
0x1800103c4  mov     rsi, [rsp+298h+arg_28]
0x1800103cc  xor     r14d, r14d
0x1800103cf  mov     r13d, r9d
0x1800103d2  mov     [rsp+298h+hDlg], rdx
0x1800103d7  mov     rax, rdx
0x1800103da  mov     [rcx], r8d
0x1800103dd  mov     r12, rcx
0x1800103e0  lea     edx, [r14+r13]; nIDDlgItem
0x1800103e4  mov     rcx, rax; hDlg
0x1800103e7  xor     edi, edi
0x1800103e9  call    cs:__imp_GetDlgItem
0x1800103ef  mov     rcx, [rsp+298h+hDlg]; hDlg
0x1800103f4  lea     edx, [r13+14h]
0x1800103f8  add     edx, r14d; nIDDlgItem
0x1800103fb  mov     rbx, rax
0x1800103fe  call    cs:__imp_GetDlgItem
0x180010404  mov     r8, rax; HWND
0x180010407  test    rbx, rbx
0x18001040a  jz      loc_18001053B
0x180010410  mov     ecx, r14d
0x180010413  test    r14d, r14d
0x180010416  jz      loc_1800104F7
0x18001041c  sub     ecx, 1
0x18001041f  jz      loc_1800104B9
0x180010425  sub     ecx, 1; this
0x180010428  jz      short loc_1800104A4
0x18001042a  sub     ecx, 1; this
0x18001042d  jz      short loc_180010495
0x18001042f  sub     ecx, 1; this
0x180010432  jz      short loc_180010483
0x180010434  sub     ecx, 1; this
0x180010437  jz      short loc_180010473
0x180010439  sub     ecx, 1; this
0x18001043c  jz      short loc_180010463
0x18001043e  cmp     ecx, 1
0x180010441  jnz     loc_18001053B
0x180010447  mov     rax, [rsi+10h]
0x18001044b  lea     r9, aU; "%u"
0x180010452  mov     rdx, rbx; HWND
0x180010455  mov     rcx, [rax+10h]; this
0x180010459  movsxd  r8, dword ptr [rcx]; void *
0x18001045c  call    ?_ReinsertDlgText@CFtpDialogTemplate@@AEAAJPEAUHWND__@@PEBXPEBG@Z; CFtpDialogTemplate::_ReinsertDlgText(HWND__ *,void const *,ushort const *)
0x180010461  jmp     short loc_1800104B2
0x180010463  mov     r9, rsi; struct CFtpPidlList *
0x180010466  mov     r8, rbp; struct CFtpFolder *
0x180010469  mov     rdx, rbx; HWND
0x18001046c  call    ?_InitLocation@CFtpDialogTemplate@@AEAAJPEAUHWND__@@PEAVCFtpFolder@@PEAVCFtpPidlList@@@Z; CFtpDialogTemplate::_InitLocation(HWND__ *,CFtpFolder *,CFtpPidlList *)
0x180010471  jmp     short loc_1800104B2
0x180010473  mov     r9, rsi; struct CFtpPidlList *
0x180010476  mov     r8, rbp; struct CFtpFolder *
0x180010479  mov     rdx, rbx; HWND
0x18001047c  call    ?_InitType@CFtpDialogTemplate@@AEAAJPEAUHWND__@@PEAVCFtpFolder@@PEAVCFtpPidlList@@@Z; CFtpDialogTemplate::_InitType(HWND__ *,CFtpFolder *,CFtpPidlList *)
0x180010481  jmp     short loc_1800104B2
0x180010483  mov     r9, rbp; struct CFtpFolder *
0x180010486  mov     [rsp+298h+var_278], rsi; struct CFtpPidlList *
0x18001048b  mov     rdx, rbx; HWND
0x18001048e  call    ?_InitTime@CFtpDialogTemplate@@AEAAJPEAUHWND__@@0PEAVCFtpFolder@@PEAVCFtpPidlList@@@Z; CFtpDialogTemplate::_InitTime(HWND__ *,HWND__ *,CFtpFolder *,CFtpPidlList *)
0x180010493  jmp     short loc_1800104B2
0x180010495  mov     rdx, rbx; HWND
0x180010498  mov     [rsp+298h+var_278], rsi; struct CFtpPidlList *
0x18001049d  call    ?_InitSize@CFtpDialogTemplate@@AEAAJPEAUHWND__@@0PEAVCFtpFolder@@PEAVCFtpPidlList@@@Z; CFtpDialogTemplate::_InitSize(HWND__ *,HWND__ *,CFtpFolder *,CFtpPidlList *)
0x1800104a2  jmp     short loc_1800104B2
0x1800104a4  mov     r9, rsi; struct CFtpPidlList *
0x1800104a7  mov     r8, rbp; struct CFtpFolder *
0x1800104aa  mov     rdx, rbx; HWND
0x1800104ad  call    ?_InitIcon@CFtpDialogTemplate@@AEAAJPEAUHWND__@@PEAVCFtpFolder@@PEAVCFtpPidlList@@@Z; CFtpDialogTemplate::_InitIcon(HWND__ *,CFtpFolder *,CFtpPidlList *)
0x1800104b2  mov     edi, eax
0x1800104b4  jmp     loc_18001053B
0x1800104b9  lea     r8, [rsp+298h+var_258]; unsigned __int16 *
0x1800104be  mov     rdx, rsi; struct CFtpPidlList *
0x1800104c1  mov     rcx, rbp; struct CFtpFolder *
0x1800104c4  call    ?GetItemName@@YAXPEAVCFtpFolder@@PEAVCFtpPidlList@@PEAGK@Z; GetItemName(CFtpFolder *,CFtpPidlList *,ushort *,ulong)
0x1800104c9  lea     r9, aS; "%s"
0x1800104d0  mov     rdx, rbx; HWND
0x1800104d3  lea     r8, [rsp+298h+var_258]; void *
0x1800104d8  call    ?_ReinsertDlgText@CFtpDialogTemplate@@AEAAJPEAUHWND__@@PEBXPEBG@Z; CFtpDialogTemplate::_ReinsertDlgText(HWND__ *,void const *,ushort const *)
0x1800104dd  cmp     dword ptr [r12], 0
0x1800104e2  mov     edi, eax
0x1800104e4  jz      short loc_180010533
0x1800104e6  mov     rdx, rsi; struct CFtpPidlList *
0x1800104e9  mov     rcx, rbp; struct CFtpFolder *
0x1800104ec  call    ?CanEditName@@YAHPEAVCFtpFolder@@PEAVCFtpPidlList@@@Z; CanEditName(CFtpFolder *,CFtpPidlList *)
0x1800104f1  test    eax, eax
0x1800104f3  jnz     short loc_18001053B
0x1800104f5  jmp     short loc_180010533
0x1800104f7  lea     r8, [rsp+298h+var_258]; unsigned __int16 *
0x1800104fc  mov     rdx, rsi; struct CFtpPidlList *
0x1800104ff  mov     rcx, rbp; struct CFtpFolder *
0x180010502  call    ?GetItemName@@YAXPEAVCFtpFolder@@PEAVCFtpPidlList@@PEAGK@Z; GetItemName(CFtpFolder *,CFtpPidlList *,ushort *,ulong)
0x180010507  lea     r9, aS; "%s"
0x18001050e  mov     rdx, rbx; HWND
0x180010511  lea     r8, [rsp+298h+var_258]; void *
0x180010516  call    ?_ReinsertDlgText@CFtpDialogTemplate@@AEAAJPEAUHWND__@@PEBXPEBG@Z; CFtpDialogTemplate::_ReinsertDlgText(HWND__ *,void const *,ushort const *)
0x18001051b  cmp     dword ptr [r12], 0
0x180010520  mov     edi, eax
0x180010522  jz      short loc_18001053B
0x180010524  mov     rdx, rsi; struct CFtpPidlList *
0x180010527  mov     rcx, rbp; struct CFtpFolder *
0x18001052a  call    ?CanEditName@@YAHPEAVCFtpFolder@@PEAVCFtpPidlList@@@Z; CanEditName(CFtpFolder *,CFtpPidlList *)
0x18001052f  test    eax, eax
0x180010531  jz      short loc_18001053B
0x180010533  mov     rcx, rbx; HWND
0x180010536  call    ?ShowEnableWindow@@YAXPEAUHWND__@@H@Z; ShowEnableWindow(HWND__ *,int)
0x18001053b  mov     rax, [rsp+298h+hDlg]
0x180010540  test    r15d, r15d
0x180010543  cmovs   edi, r15d
0x180010547  inc     r14d
0x18001054a  mov     r15d, edi
0x18001054d  cmp     r14d, 8
0x180010551  jl      loc_1800103E0
0x180010557  mov     eax, edi
0x180010559  mov     rcx, [rsp+298h+var_48]
0x180010561  xor     rcx, rsp; StackCookie
0x180010564  call    __security_check_cookie
0x180010569  mov     rbx, [rsp+298h+arg_10]
0x180010571  add     rsp, 260h
0x180010578  pop     r15
0x18001057a  pop     r14
0x18001057c  pop     r13
0x18001057e  pop     r12
0x180010580  pop     rdi
0x180010581  pop     rsi
0x180010582  pop     rbp
0x180010583  retn
```
