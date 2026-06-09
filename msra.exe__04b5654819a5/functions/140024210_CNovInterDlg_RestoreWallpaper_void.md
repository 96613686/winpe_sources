# CNovInterDlg::RestoreWallpaper(void)

- ea: `0x140024210`
- end: `0x1400242f4`
- name: `?RestoreWallpaper@CNovInterDlg@@QEAAJXZ`
- size: `228`
- prototype: `__int64 __fastcall(CNovInterDlg *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000ea24`
- `0x1400241a0`
- `0x140025138`

## callees

- `0x140024210`
- `0x140034ce4`
- `0x140035288`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140024296`
- `KERNEL32!HeapFree` at `0x140024296`
- `KERNEL32!GetProcessHeap` at `0x140024282`
- `KERNEL32!GetProcessHeap` at `0x140024282`
- `USER32!SystemParametersInfoW` at `0x14002423d`
- `USER32!SystemParametersInfoW` at `0x14002423d`

## string_xrefs

- `0x1400242ad`: `Wallpaper Path`

## pseudocode

```c
__int64 __fastcall CNovInterDlg::RestoreWallpaper(CNovInterDlg *this)
{
  void *v1; // r8
  unsigned int v2; // ebx
  CEventLogger *v4; // rcx
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  signed int v7; // eax
  CEventLogger *v8; // rcx

  v1 = (void *)*((_QWORD *)this + 16);
  v2 = 0;
  if ( v1 )
  {
    if ( !SystemParametersInfoW(0x14u, 0, v1, 3u) )
      CEventLogger::LogError(
        v4,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
        0xDC4u,
        L"CNovInterDlg::RestoreWallpaper",
        0);
    v5 = (void *)*((_QWORD *)this + 16);
    if ( v5 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
      *((_QWORD *)this + 16) = 0;
    }
    v7 = DeleteRegistryValue(L"Wallpaper Path");
    v2 = v7;
    if ( v7 < 0 )
      CEventLogger::LogError(
        v8,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
        0xDCEu,
        L"CNovInterDlg::RestoreWallpaper",
        v7);
  }
  return v2;
}

```

## disassembly

```asm
0x140024210  mov     [rsp+arg_0], rbx
0x140024215  mov     [rsp+arg_8], rsi
0x14002421a  push    rdi
0x14002421b  sub     rsp, 30h
0x14002421f  mov     r8, [rcx+80h]; pvParam
0x140024226  xor     ebx, ebx
0x140024228  mov     rdi, rcx
0x14002422b  test    r8, r8
0x14002422e  jz      loc_1400242E1
0x140024234  xor     edx, edx; uiParam
0x140024236  lea     ecx, [rbx+14h]; uiAction
0x140024239  lea     r9d, [rbx+3]; fWinIni
0x14002423d  call    cs:__imp_SystemParametersInfoW
0x140024244  nop     dword ptr [rax+rax+00h]
0x140024249  lea     rsi, aCnovinterdlgRe_1; "CNovInterDlg::RestoreWallpaper"
0x140024250  test    eax, eax
0x140024252  jnz     short loc_140024276
0x140024254  mov     [rsp+38h+var_10], ebx; unsigned int
0x140024258  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x14002425f  mov     r9d, 0DC4h; unsigned int
0x140024265  mov     [rsp+38h+var_18], rsi; unsigned __int16 *
0x14002426a  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140024271  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140024276  mov     rbx, [rdi+80h]
0x14002427d  test    rbx, rbx
0x140024280  jz      short loc_1400242AD
0x140024282  call    cs:__imp_GetProcessHeap
0x140024289  nop     dword ptr [rax+rax+00h]
0x14002428e  mov     r8, rbx; lpMem
0x140024291  xor     edx, edx; dwFlags
0x140024293  mov     rcx, rax; hHeap
0x140024296  call    cs:__imp_HeapFree
0x14002429d  nop     dword ptr [rax+rax+00h]
0x1400242a2  mov     qword ptr [rdi+80h], 0
0x1400242ad  lea     rcx, aWallpaperPath; "Wallpaper Path"
0x1400242b4  call    ?DeleteRegistryValue@@YAJPEAG@Z; DeleteRegistryValue(ushort *)
0x1400242b9  mov     ebx, eax
0x1400242bb  test    eax, eax
0x1400242bd  jns     short loc_1400242E1
0x1400242bf  mov     [rsp+38h+var_10], eax; unsigned int
0x1400242c3  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x1400242ca  mov     r9d, 0DCEh; unsigned int
0x1400242d0  mov     [rsp+38h+var_18], rsi; unsigned __int16 *
0x1400242d5  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400242dc  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400242e1  mov     rsi, [rsp+38h+arg_8]
0x1400242e6  mov     eax, ebx
0x1400242e8  mov     rbx, [rsp+38h+arg_0]
0x1400242ed  add     rsp, 30h
0x1400242f1  pop     rdi
0x1400242f2  retn
```
