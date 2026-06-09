# ShowPasswordDialog(ushort * *,HWND__ *,int,int)

- ea: `0x14002c4bc`
- end: `0x14002c5ec`
- name: `?ShowPasswordDialog@@YAIPEAPEAGPEAUHWND__@@HH@Z`
- size: `304`
- prototype: `unsigned int __fastcall(unsigned __int16 **, HWND, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001c9c8`

## callees

- `0x140026c48`
- `0x14002c4bc`
- `0x140034ce4`
- `0x14004d010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14002c57a`
- `KERNEL32!GetProcAddress` at `0x14002c57a`
- `USER32!CreateWindowExW` at `0x14002c515`
- `USER32!CreateWindowExW` at `0x14002c515`
- `USER32!DestroyWindow` at `0x14002c5d0`
- `USER32!DestroyWindow` at `0x14002c5d0`

## string_xrefs

- `0x14002c54b`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c
__int64 __fastcall ShowPasswordDialog(unsigned __int16 **a1, HWND a2, unsigned int a3, unsigned int a4)
{
  unsigned int v4; // ebx
  HWND Window; // rdi
  signed int v10; // eax
  CEventLogger *v11; // rcx
  FARPROC ProcAddress; // rax
  CEventLogger *v13; // rcx
  struct IRaContactControl *v15; // [rsp+60h] [rbp-48h] BYREF

  v4 = 0;
  v15 = 0;
  Window = CreateWindowExW(0, L"STATIC", L"MSRA", 0, 0x80000000, 0x80000000, 0x80000000, 0x80000000, 0, 0, 0, 0);
  v10 = CreateRAContactControl(Window, 0, 0, &v15);
  if ( v10 >= 0 )
  {
    ProcAddress = GetProcAddress(*((HMODULE *)_AtlModule + 79), "ShowPasswordDialog");
    if ( ProcAddress )
      v4 = ((__int64 (__fastcall *)(unsigned __int16 **, HWND, _QWORD, _QWORD))ProcAddress)(a1, a2, a3, a4);
    else
      CEventLogger::LogError(
        v13,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x1A72u,
        L"ShowPasswordDialog",
        0x80004003);
  }
  else
  {
    CEventLogger::LogError(
      v11,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x1A6Du,
      L"ShowPasswordDialog",
      v10);
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(struct IRaContactControl *))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  DestroyWindow(Window);
  return v4;
}

```

## disassembly

```asm
0x14002c4bc  mov     rax, rsp
0x14002c4bf  push    rbx
0x14002c4c0  push    rbp
0x14002c4c1  push    rsi
0x14002c4c2  push    rdi
0x14002c4c3  push    r14
0x14002c4c5  push    r15
0x14002c4c7  sub     rsp, 78h
0x14002c4cb  xor     ebx, ebx
0x14002c4cd  mov     esi, r9d
0x14002c4d0  mov     [rax-50h], rbx
0x14002c4d4  mov     ebp, r8d
0x14002c4d7  mov     [rax-58h], rbx
0x14002c4db  lea     r8, WindowName; "MSRA"
0x14002c4e2  mov     [rax-60h], rbx
0x14002c4e6  mov     r14, rdx
0x14002c4e9  mov     [rax-68h], rbx
0x14002c4ed  lea     rdx, ClassName; "STATIC"
0x14002c4f4  mov     [rax-48h], rbx
0x14002c4f8  mov     r15, rcx
0x14002c4fb  mov     eax, 80000000h
0x14002c500  xor     r9d, r9d; dwStyle
0x14002c503  mov     [rsp+0A8h+nHeight], eax; nHeight
0x14002c507  xor     ecx, ecx; dwExStyle
0x14002c509  mov     [rsp+0A8h+nWidth], eax; nWidth
0x14002c50d  mov     [rsp+0A8h+Y], eax; Y
0x14002c511  mov     [rsp+0A8h+X], eax; X
0x14002c515  call    cs:__imp_CreateWindowExW
0x14002c51c  nop     dword ptr [rax+rax+00h]
0x14002c521  lea     r9, [rsp+0A8h+var_48]; struct IRaContactControl **
0x14002c526  xor     r8d, r8d; void (*)(unsigned __int16 *, int)
0x14002c529  mov     rcx, rax; hWnd
0x14002c52c  xor     edx, edx; int
0x14002c52e  mov     rdi, rax
0x14002c531  call    ?CreateRAContactControl@@YAJPEAUHWND__@@HP6AXPEAGH@ZPEAPEAUIRaContactControl@@@Z; CreateRAContactControl(HWND__ *,int,void (*)(ushort *,int),IRaContactControl * *)
0x14002c536  test    eax, eax
0x14002c538  jns     short loc_14002C565
0x14002c53a  mov     [rsp+0A8h+Y], eax; unsigned int
0x14002c53e  mov     r9d, 1A6Dh; unsigned int
0x14002c544  lea     rax, aShowpassworddi_0; "ShowPasswordDialog"
0x14002c54b  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002c552  mov     qword ptr [rsp+0A8h+X], rax; unsigned __int16 *
0x14002c557  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002c55e  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002c563  jmp     short loc_14002C5AE
0x14002c565  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002c56c  lea     rdx, aShowpassworddi; "ShowPasswordDialog"
0x14002c573  mov     rcx, [rcx+278h]; hModule
0x14002c57a  call    cs:__imp_GetProcAddress
0x14002c581  nop     dword ptr [rax+rax+00h]
0x14002c586  test    rax, rax
0x14002c589  jnz     short loc_14002C59B
0x14002c58b  mov     [rsp+0A8h+Y], 80004003h
0x14002c593  mov     r9d, 1A72h
0x14002c599  jmp     short loc_14002C544
0x14002c59b  mov     r9d, esi
0x14002c59e  mov     r8d, ebp
0x14002c5a1  mov     rdx, r14
0x14002c5a4  mov     rcx, r15
0x14002c5a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c5ac  mov     ebx, eax
0x14002c5ae  mov     rcx, [rsp+0A8h+var_48]
0x14002c5b3  test    rcx, rcx
0x14002c5b6  jz      short loc_14002C5CD
0x14002c5b8  mov     rdx, [rcx]
0x14002c5bb  mov     rax, [rdx+10h]
0x14002c5bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c5c4  mov     [rsp+0A8h+var_48], 0
0x14002c5cd  mov     rcx, rdi; hWnd
0x14002c5d0  call    cs:__imp_DestroyWindow
0x14002c5d7  nop     dword ptr [rax+rax+00h]
0x14002c5dc  mov     eax, ebx
0x14002c5de  add     rsp, 78h
0x14002c5e2  pop     r15
0x14002c5e4  pop     r14
0x14002c5e6  pop     rdi
0x14002c5e7  pop     rsi
0x14002c5e8  pop     rbp
0x14002c5e9  pop     rbx
0x14002c5ea  retn
```
