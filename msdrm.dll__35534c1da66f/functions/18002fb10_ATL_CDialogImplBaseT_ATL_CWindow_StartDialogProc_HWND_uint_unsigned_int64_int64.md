# ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18002fb10`
- end: `0x18002fbb2`
- name: `?StartDialogProc@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `162`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18002fb10`
- `0x18004f65c`
- `0x18004f6d4`
- `0x18004f778`
- `0x18005f010`

## import_xrefs

- `ATL!__imp_AtlModuleExtractCreateWndData` at `0x18002fb30`
- `ATL!__imp_AtlModuleExtractCreateWndData` at `0x18002fb30`
- `USER32!SetWindowLongPtrW` at `0x18002fb8b`
- `USER32!SetWindowLongPtrW` at `0x18002fb8b`

## pseudocode

```c
INT_PTR __fastcall ATL::CDialogImplBaseT<ATL::CWindow>::StartDialogProc(
        HWND a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4)
{
  size_t WndData; // rbx
  __int64 v9; // r10
  void *v10; // rdi
  AtlThunkData_t *Data; // rax
  WNDPROC v12; // rbx

  WndData = AtlModuleExtractCreateWndData(&_Module);
  v9 = *(_QWORD *)WndData;
  *(_QWORD *)(WndData + 8) = a1;
  v10 = (void *)(*(__int64 (__fastcall **)(size_t))(v9 + 8))(WndData);
  Data = *(AtlThunkData_t **)(WndData + 40);
  if ( Data || (Data = AtlThunk_AllocateData(), (*(_QWORD *)(WndData + 40) = Data) != 0) )
    AtlThunk_InitData(Data, v10, WndData);
  v12 = AtlThunk_DataToCode(*(AtlThunkData_t **)(WndData + 40));
  SetWindowLongPtrW(a1, 8, (LONG_PTR)v12);
  return ((__int64 (__fastcall *)(HWND, _QWORD, __int64, __int64))v12)(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18002fb10  push    rbx
0x18002fb12  push    rbp
0x18002fb13  push    rsi
0x18002fb14  push    rdi
0x18002fb15  push    r14
0x18002fb17  push    r15
0x18002fb19  sub     rsp, 38h
0x18002fb1d  mov     rsi, rcx
0x18002fb20  mov     rbp, r9
0x18002fb23  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18002fb2a  mov     r14, r8
0x18002fb2d  mov     r15d, edx
0x18002fb30  call    cs:__imp_AtlModuleExtractCreateWndData
0x18002fb36  mov     rbx, rax
0x18002fb39  mov     rcx, rax
0x18002fb3c  mov     r10, [rax]
0x18002fb3f  mov     [rax+8], rsi
0x18002fb43  mov     rax, [r10+8]
0x18002fb47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb4c  mov     rdi, rax
0x18002fb4f  mov     rax, [rbx+28h]
0x18002fb53  test    rax, rax
0x18002fb56  jnz     short loc_18002FB66
0x18002fb58  call    AtlThunk_AllocateData
0x18002fb5d  mov     [rbx+28h], rax
0x18002fb61  test    rax, rax
0x18002fb64  jz      short loc_18002FB74
0x18002fb66  mov     r8, rbx; FirstParameter
0x18002fb69  mov     rdx, rdi; Proc
0x18002fb6c  mov     rcx, rax; Thunk
0x18002fb6f  call    AtlThunk_InitData
0x18002fb74  mov     rcx, [rbx+28h]; AtlThunkData_t *
0x18002fb78  call    AtlThunk_DataToCode
0x18002fb7d  mov     r8, rax; dwNewLong
0x18002fb80  mov     edx, 8; nIndex
0x18002fb85  mov     rcx, rsi; hWnd
0x18002fb88  mov     rbx, rax
0x18002fb8b  call    cs:__imp_SetWindowLongPtrW
0x18002fb91  mov     r9, rbp
0x18002fb94  mov     r8, r14
0x18002fb97  mov     edx, r15d
0x18002fb9a  mov     rcx, rsi
0x18002fb9d  mov     rax, rbx
0x18002fba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fba5  add     rsp, 38h
0x18002fba9  pop     r15
0x18002fbab  pop     r14
0x18002fbad  pop     rdi
0x18002fbae  pop     rsi
0x18002fbaf  pop     rbp
0x18002fbb0  pop     rbx
0x18002fbb1  retn
```
