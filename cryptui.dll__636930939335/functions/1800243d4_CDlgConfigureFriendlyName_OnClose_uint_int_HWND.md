# CDlgConfigureFriendlyName::OnClose(uint,int,HWND__ *)

- ea: `0x1800243d4`
- end: `0x180024476`
- name: `?OnClose@CDlgConfigureFriendlyName@@AEAAXIHPEAUHWND__@@@Z`
- size: `162`
- prototype: `void __fastcall(CDlgConfigureFriendlyName *__hidden this, unsigned int, int, HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180026394`

## callees

- `0x180014440`
- `0x1800243d4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024421`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024421`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024449`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024449`
- `USER32!GetWindowTextLengthW` at `0x18002440b`
- `USER32!GetWindowTextLengthW` at `0x18002440b`
- `USER32!EndDialog` at `0x180024460`
- `USER32!EndDialog` at `0x180024460`
- `USER32!GetWindowTextW` at `0x18002443b`
- `USER32!GetWindowTextW` at `0x18002443b`

## pseudocode

```c
void __fastcall CDlgConfigureFriendlyName::OnClose(CDlgConfigureFriendlyName *this, __int64 a2, int a3, HWND a4)
{
  INT_PTR v4; // rdi
  int WindowTextLengthW; // eax
  int v7; // esi
  WCHAR *v8; // rax
  HWND hWnd; // [rsp+48h] [rbp+20h] BYREF

  hWnd = a4;
  v4 = a3;
  if ( a3 != 1 )
    goto LABEL_6;
  ATL::CWindow::GetDlgItem((char *)this + 8, &hWnd, 1019);
  WindowTextLengthW = GetWindowTextLengthW(hWnd);
  if ( !WindowTextLengthW )
    goto LABEL_6;
  v7 = WindowTextLengthW + 1;
  v8 = (WCHAR *)LocalAlloc((int)v4 + 63, 2LL * (WindowTextLengthW + 1));
  *((_QWORD *)this + 9) = v8;
  if ( !v8 )
    return;
  if ( !GetWindowTextW(hWnd, v8, v7) )
  {
    LocalFree(*((HLOCAL *)this + 9));
    *((_QWORD *)this + 9) = 0;
  }
  else
  {
LABEL_6:
    EndDialog(*((HWND *)this + 1), v4);
  }
}

```

## disassembly

```asm
0x1800243d4  mov     rax, rsp
0x1800243d7  mov     [rax+8], rbx
0x1800243db  mov     [rax+10h], rsi
0x1800243df  mov     [rax+20h], r9
0x1800243e3  push    rdi
0x1800243e4  sub     rsp, 20h
0x1800243e8  movsxd  rdi, r8d
0x1800243eb  mov     rbx, rcx
0x1800243ee  cmp     edi, 1
0x1800243f1  jnz     short loc_180024459
0x1800243f3  add     rcx, 8
0x1800243f7  lea     rdx, [rax+20h]
0x1800243fb  mov     r8d, 3FBh
0x180024401  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180024406  mov     rcx, [rsp+28h+hWnd]; hWnd
0x18002440b  call    cs:__imp_GetWindowTextLengthW
0x180024411  test    eax, eax
0x180024413  jz      short loc_180024459
0x180024415  lea     esi, [rax+1]
0x180024418  movsxd  rdx, esi
0x18002441b  lea     ecx, [rdi+3Fh]; uFlags
0x18002441e  add     rdx, rdx; uBytes
0x180024421  call    cs:__imp_LocalAlloc
0x180024427  mov     [rbx+48h], rax
0x18002442b  test    rax, rax
0x18002442e  jz      short loc_180024466
0x180024430  mov     rcx, [rsp+28h+hWnd]; hWnd
0x180024435  mov     r8d, esi; nMaxCount
0x180024438  mov     rdx, rax; lpString
0x18002443b  call    cs:__imp_GetWindowTextW
0x180024441  test    eax, eax
0x180024443  jnz     short loc_180024459
0x180024445  mov     rcx, [rbx+48h]; hMem
0x180024449  call    cs:__imp_LocalFree
0x18002444f  mov     qword ptr [rbx+48h], 0
0x180024457  jmp     short loc_180024466
0x180024459  mov     rcx, [rbx+8]; hDlg
0x18002445d  mov     rdx, rdi; nResult
0x180024460  call    cs:__imp_EndDialog
0x180024466  mov     rbx, [rsp+28h+arg_0]
0x18002446b  mov     rsi, [rsp+28h+arg_8]
0x180024470  add     rsp, 20h
0x180024474  pop     rdi
0x180024475  retn
```
