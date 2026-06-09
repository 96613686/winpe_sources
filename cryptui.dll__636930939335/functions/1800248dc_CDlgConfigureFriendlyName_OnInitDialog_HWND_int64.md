# CDlgConfigureFriendlyName::OnInitDialog(HWND__ *,__int64)

- ea: `0x1800248dc`
- end: `0x1800249a2`
- name: `?OnInitDialog@CDlgConfigureFriendlyName@@AEAA_JPEAUHWND__@@_J@Z`
- size: `198`
- prototype: `__int64 __fastcall(CDlgConfigureFriendlyName *__hidden this, HWND, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180026394`

## callees

- `0x180014440`
- `0x1800248dc`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024907`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024907`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180024954`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180024954`
- `USER32!SetWindowTextW` at `0x180024976`
- `USER32!SetWindowTextW` at `0x180024976`

## pseudocode

```c
__int64 __fastcall CDlgConfigureFriendlyName::OnInitDialog(CDlgConfigureFriendlyName *this, HWND a2)
{
  void *v3; // rcx
  HWND *DlgItem; // rax
  WCHAR *v5; // rdx
  _BYTE v7[16]; // [rsp+20h] [rbp-228h] BYREF
  WCHAR Buffer[256]; // [rsp+30h] [rbp-218h] BYREF

  v3 = (void *)*((_QWORD *)this + 9);
  if ( v3 )
  {
    LocalFree(v3);
    *((_QWORD *)this + 9) = 0;
  }
  if ( *((_QWORD *)this + 10) )
  {
    DlgItem = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, v7, 1019);
    v5 = (WCHAR *)*((_QWORD *)this + 10);
  }
  else
  {
    Buffer[0] = 0;
    LoadStringW(hInstance, 0xD79u, Buffer, 256);
    DlgItem = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, v7, 1019);
    v5 = Buffer;
  }
  SetWindowTextW(*DlgItem, v5);
  return 1;
}

```

## disassembly

```asm
0x1800248dc  mov     [rsp+arg_8], rbx
0x1800248e1  push    rdi
0x1800248e2  sub     rsp, 240h
0x1800248e9  mov     rax, cs:__security_cookie
0x1800248f0  xor     rax, rsp
0x1800248f3  mov     [rsp+248h+var_18], rax
0x1800248fb  mov     rbx, rcx
0x1800248fe  mov     rcx, [rcx+48h]; hMem
0x180024902  test    rcx, rcx
0x180024905  jz      short loc_180024915
0x180024907  call    cs:__imp_LocalFree
0x18002490d  mov     qword ptr [rbx+48h], 0
0x180024915  cmp     qword ptr [rbx+50h], 0
0x18002491a  jz      short loc_180024936
0x18002491c  mov     r8d, 3FBh
0x180024922  lea     rdx, [rsp+248h+var_228]
0x180024927  lea     rcx, [rbx+8]
0x18002492b  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180024930  mov     rdx, [rbx+50h]
0x180024934  jmp     short loc_180024973
0x180024936  mov     rcx, cs:hInstance; hInstance
0x18002493d  lea     r8, [rsp+248h+Buffer]; lpBuffer
0x180024942  xor     eax, eax
0x180024944  mov     r9d, 100h; cchBufferMax
0x18002494a  mov     edx, 0D79h; uID
0x18002494f  mov     [rsp+248h+Buffer], ax
0x180024954  call    cs:__imp_LoadStringW
0x18002495a  mov     r8d, 3FBh
0x180024960  lea     rdx, [rsp+248h+var_228]
0x180024965  lea     rcx, [rbx+8]
0x180024969  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x18002496e  lea     rdx, [rsp+248h+Buffer]; lpString
0x180024973  mov     rcx, [rax]; hWnd
0x180024976  call    cs:__imp_SetWindowTextW
0x18002497c  mov     eax, 1
0x180024981  mov     rcx, [rsp+248h+var_18]
0x180024989  xor     rcx, rsp; StackCookie
0x18002498c  call    __security_check_cookie
0x180024991  mov     rbx, [rsp+248h+arg_8]
0x180024999  add     rsp, 240h
0x1800249a0  pop     rdi
0x1800249a1  retn
```
