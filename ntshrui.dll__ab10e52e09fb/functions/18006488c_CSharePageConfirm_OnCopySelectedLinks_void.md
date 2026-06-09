# CSharePageConfirm::_OnCopySelectedLinks(void)

- ea: `0x18006488c`
- end: `0x180064a51`
- name: `?_OnCopySelectedLinks@CSharePageConfirm@@AEAAXXZ`
- size: `453`
- prototype: `void __fastcall(CSharePageConfirm *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180064a58`

## callees

- `0x180010cf0`
- `0x1800120e0`
- `0x180013220`
- `0x180017410`
- `0x1800645f4`
- `0x18006488c`
- `0x180065f88`
- `0x180072bb8`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180064a06`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180064a06`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800649a6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800649a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064a0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180064a0f`
- `KERNEL32!GlobalLock` at `0x1800649b7`
- `KERNEL32!GlobalLock` at `0x1800649b7`
- `KERNEL32!GlobalUnlock` at `0x1800649d3`
- `KERNEL32!GlobalUnlock` at `0x1800649d3`
- `USER32!SetClipboardData` at `0x1800649f5`
- `USER32!SetClipboardData` at `0x1800649f5`
- `USER32!EmptyClipboard` at `0x1800649e7`
- `USER32!EmptyClipboard` at `0x1800649e7`
- `USER32!OpenClipboard` at `0x1800649dd`
- `USER32!OpenClipboard` at `0x1800649dd`
- `USER32!CloseClipboard` at `0x1800649fb`
- `USER32!CloseClipboard` at `0x1800649fb`
- `USER32!GetDlgItem` at `0x1800648ca`
- `USER32!GetDlgItem` at `0x1800648ca`
- `USER32!SendMessageW` at `0x1800648e1`
- `USER32!SendMessageW` at `0x180064907`
- `USER32!SendMessageW` at `0x1800648e1`
- `USER32!SendMessageW` at `0x180064907`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSharePageConfirm::_OnCopySelectedLinks(HWND *this)
{
  int ItemAt; // esi
  HWND DlgItem; // r13
  int v4; // r12d
  int v5; // edi
  struct _DPA *v6; // rbx
  LPVOID v7; // r14
  unsigned int v8; // edx
  unsigned __int16 *v9; // rsi
  __int64 v10; // rax
  unsigned __int64 v11; // r14
  HGLOBAL v12; // rax
  void *v13; // rdi
  unsigned __int16 *v14; // rax
  HDPA hdpa; // [rsp+68h] [rbp+48h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+50h] BYREF

  hdpa = 0;
  if ( (unsigned int)CDPA_Base<CShareItemResult,CTContainer_PolicyRelease<CShareItemResult>>::Create(&hdpa) )
  {
    ItemAt = 0;
    DlgItem = GetDlgItem(this[1], 4102);
    v4 = SendMessageW(DlgItem, 0x1004u, 0, 0);
    v5 = 0;
    while ( 1 )
    {
      v6 = hdpa;
      if ( v5 >= v4 )
        break;
      if ( (unsigned int)SendMessageW(DlgItem, 0x102Cu, v5, 2) )
      {
        pv = 0;
        ItemAt = CResultsList::GetItemAt((CResultsList *)(this + 6), v5, (struct IShellItem **)&pv);
        if ( ItemAt >= 0 )
        {
          v7 = pv;
          ItemAt = CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(&hdpa, pv);
          if ( ItemAt < 0 )
          {
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
            goto LABEL_22;
          }
        }
      }
      ++v5;
      if ( ItemAt < 0 )
        goto LABEL_22;
    }
    pv = 0;
    if ( hdpa )
      v8 = *(_DWORD *)hdpa;
    else
      v8 = 0;
    if ( (int)FormatPathsAsLinks(*((struct IShellItem ***)hdpa + 1), v8, (unsigned __int16 **)&pv) >= 0 )
    {
      v9 = (unsigned __int16 *)pv;
      v10 = -1;
      do
        ++v10;
      while ( *((_WORD *)pv + v10) );
      v11 = v10 + 1;
      v12 = GlobalAlloc(0x2042u, 2 * (v10 + 1));
      v13 = v12;
      if ( v12 )
      {
        v14 = (unsigned __int16 *)GlobalLock(v12);
        if ( v14 && (StringCchCopyW(v14, v11, v9), GlobalUnlock(v13), OpenClipboard(this[1])) )
        {
          EmptyClipboard();
          SetClipboardData(0xDu, v13);
          CloseClipboard();
        }
        else
        {
          GlobalFree(v13);
        }
      }
      CoTaskMemFree(v9);
    }
LABEL_22:
    if ( v6 )
    {
      DPA_DestroyCallback(v6, DPA_ReleaseCB<ISharePermissionList>, 0);
      hdpa = 0;
    }
  }
  CDPA_Base<CUserObject,CTContainer_PolicyUnOwned<CUserObject>>::~CDPA_Base<CUserObject,CTContainer_PolicyUnOwned<CUserObject>>(&hdpa);
}

```

## disassembly

```asm
0x18006488c  mov     [rsp-38h+arg_0], rbx
0x180064891  push    rbp
0x180064892  push    rsi
0x180064893  push    rdi
0x180064894  push    r12
0x180064896  push    r13
0x180064898  push    r14
0x18006489a  push    r15
0x18006489c  mov     rbp, rsp
0x18006489f  sub     rsp, 20h
0x1800648a3  mov     r15, rcx
0x1800648a6  xor     r14d, r14d
0x1800648a9  mov     [rbp+hdpa], r14
0x1800648ad  lea     rcx, [rbp+hdpa]
0x1800648b1  call    ?Create@?$CDPA_Base@VCShareItemResult@@V?$CTContainer_PolicyRelease@VCShareItemResult@@@@@@QEAAHH@Z; CDPA_Base<CShareItemResult,CTContainer_PolicyRelease<CShareItemResult>>::Create(int)
0x1800648b6  test    eax, eax
0x1800648b8  jz      loc_180064A33
0x1800648be  mov     esi, r14d
0x1800648c1  mov     edx, 1006h; nIDDlgItem
0x1800648c6  mov     rcx, [r15+8]; hDlg
0x1800648ca  call    cs:__imp_GetDlgItem
0x1800648d0  mov     r13, rax
0x1800648d3  xor     r9d, r9d; lParam
0x1800648d6  xor     r8d, r8d; wParam
0x1800648d9  mov     edx, 1004h; Msg
0x1800648de  mov     rcx, rax; hWnd
0x1800648e1  call    cs:__imp_SendMessageW
0x1800648e7  mov     r12, rax
0x1800648ea  mov     edi, r14d
0x1800648ed  mov     rbx, [rbp+hdpa]
0x1800648f1  cmp     edi, r12d
0x1800648f4  jge     short loc_180064962
0x1800648f6  movsxd  r8, edi; wParam
0x1800648f9  mov     edx, 102Ch; Msg
0x1800648fe  mov     r9d, 2; lParam
0x180064904  mov     rcx, r13; hWnd
0x180064907  call    cs:__imp_SendMessageW
0x18006490d  test    eax, eax
0x18006490f  jz      short loc_180064943
0x180064911  mov     [rbp+pv], r14
0x180064915  lea     rcx, [r15+30h]; this
0x180064919  lea     r8, [rbp+pv]; struct IShellItem **
0x18006491d  mov     edx, edi; int
0x18006491f  call    ?GetItemAt@CResultsList@@QEAAJHPEAPEAUIShellItem@@@Z; CResultsList::GetItemAt(int,IShellItem * *)
0x180064924  mov     esi, eax
0x180064926  test    eax, eax
0x180064928  js      short loc_180064943
0x18006492a  mov     r14, [rbp+pv]
0x18006492e  mov     rdx, r14
0x180064931  lea     rcx, [rbp+hdpa]
0x180064935  call    ?AppendPtr@?$CDPA_Base@VCShareUserInfo@@VCTContainer_PolicyNewMem@@@@QEAAJPEAVCShareUserInfo@@PEAH@Z; CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(CShareUserInfo *,int *)
0x18006493a  mov     esi, eax
0x18006493c  test    eax, eax
0x18006493e  js      short loc_18006494E
0x180064940  xor     r14d, r14d
0x180064943  inc     edi
0x180064945  test    esi, esi
0x180064947  jns     short loc_1800648ED
0x180064949  jmp     loc_180064A18
0x18006494e  mov     rax, [r14]
0x180064951  mov     rcx, r14
0x180064954  mov     rax, [rax+10h]
0x180064958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006495d  jmp     loc_180064A15
0x180064962  mov     [rbp+pv], r14
0x180064966  test    rbx, rbx
0x180064969  jz      short loc_18006496F
0x18006496b  mov     edx, [rbx]
0x18006496d  jmp     short loc_180064972
0x18006496f  mov     edx, r14d; unsigned int
0x180064972  lea     r8, [rbp+pv]; unsigned __int16 **
0x180064976  mov     rcx, [rbx+8]; struct IShellItem **
0x18006497a  call    ?FormatPathsAsLinks@@YAJPEAPEAUIShellItem@@KPEAPEAG@Z; FormatPathsAsLinks(IShellItem * *,ulong,ushort * *)
0x18006497f  test    eax, eax
0x180064981  js      loc_180064A18
0x180064987  mov     rsi, [rbp+pv]
0x18006498b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006498f  inc     rax
0x180064992  cmp     [rsi+rax*2], r14w
0x180064997  jnz     short loc_18006498F
0x180064999  lea     r14, [rax+1]
0x18006499d  lea     rdx, [r14+r14]; dwBytes
0x1800649a1  mov     ecx, 2042h; uFlags
0x1800649a6  call    cs:__imp_GlobalAlloc
0x1800649ac  mov     rdi, rax
0x1800649af  test    rax, rax
0x1800649b2  jz      short loc_180064A0C
0x1800649b4  mov     rcx, rax; hMem
0x1800649b7  call    cs:__imp_GlobalLock
0x1800649bd  test    rax, rax
0x1800649c0  jz      short loc_180064A03
0x1800649c2  mov     r8, rsi; unsigned __int16 *
0x1800649c5  mov     rdx, r14; unsigned __int64
0x1800649c8  mov     rcx, rax; unsigned __int16 *
0x1800649cb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800649d0  mov     rcx, rdi; hMem
0x1800649d3  call    cs:__imp_GlobalUnlock
0x1800649d9  mov     rcx, [r15+8]; hWndNewOwner
0x1800649dd  call    cs:__imp_OpenClipboard
0x1800649e3  test    eax, eax
0x1800649e5  jz      short loc_180064A03
0x1800649e7  call    cs:__imp_EmptyClipboard
0x1800649ed  mov     rdx, rdi; hMem
0x1800649f0  mov     ecx, 0Dh; uFormat
0x1800649f5  call    cs:__imp_SetClipboardData
0x1800649fb  call    cs:__imp_CloseClipboard
0x180064a01  jmp     short loc_180064A0C
0x180064a03  mov     rcx, rdi; hMem
0x180064a06  call    cs:__imp_GlobalFree
0x180064a0c  mov     rcx, rsi; pv
0x180064a0f  call    cs:__imp_CoTaskMemFree
0x180064a15  xor     r14d, r14d
0x180064a18  test    rbx, rbx
0x180064a1b  jz      short loc_180064A33
0x180064a1d  xor     r8d, r8d; pData
0x180064a20  lea     rdx, ??$DPA_ReleaseCB@UISharePermissionList@@@@YAHPEAUISharePermissionList@@PEAX@Z; pfnCB
0x180064a27  mov     rcx, rbx; hdpa
0x180064a2a  call    DPA_DestroyCallback
0x180064a2f  mov     [rbp+hdpa], r14
0x180064a33  lea     rcx, [rbp+hdpa]
0x180064a37  call    ??1?$CDPA_Base@VCUserObject@@V?$CTContainer_PolicyUnOwned@VCUserObject@@@@@@QEAA@XZ; CDPA_Base<CUserObject,CTContainer_PolicyUnOwned<CUserObject>>::~CDPA_Base<CUserObject,CTContainer_PolicyUnOwned<CUserObject>>(void)
0x180064a3c  mov     rbx, [rsp+20h+arg_0]
0x180064a41  add     rsp, 20h
0x180064a45  pop     r15
0x180064a47  pop     r14
0x180064a49  pop     r13
0x180064a4b  pop     r12
0x180064a4d  pop     rdi
0x180064a4e  pop     rsi
0x180064a4f  pop     rbp
0x180064a50  retn
```
