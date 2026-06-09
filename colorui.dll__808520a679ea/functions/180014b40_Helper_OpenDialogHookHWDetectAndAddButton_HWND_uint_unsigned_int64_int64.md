# Helper::OpenDialogHookHWDetectAndAddButton(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180014b40`
- end: `0x180014b71`
- name: `?OpenDialogHookHWDetectAndAddButton@Helper@@YA_KPEAUHWND__@@I_K_J@Z`
- size: `49`
- prototype: `unsigned __int64 __fastcall(Helper *hWnd, HWND, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180014a30`
- `0x180014ab0`

## pseudocode

```c
unsigned __int64 __fastcall Helper::OpenDialogHookHWDetectAndAddButton(Helper *hWnd, HWND a2, __int64 a3, __int64 a4)
{
  unsigned int v6; // esi

  v6 = (unsigned int)a2;
  Helper::OpenDialogHookHWDetect(hWnd, a2);
  return Helper::OpenDialogHookAddButton((HWND)hWnd, (HWND)v6, a3, a4);
}

```

## disassembly

```asm
0x180014b40  push    rbx
0x180014b42  push    rbp
0x180014b43  push    rsi
0x180014b44  push    rdi
0x180014b45  sub     rsp, 28h
0x180014b49  mov     rbx, r9
0x180014b4c  mov     rdi, r8
0x180014b4f  mov     esi, edx
0x180014b51  mov     rbp, rcx
0x180014b54  call    ?OpenDialogHookHWDetect@Helper@@YA_KPEAUHWND__@@I_K_J@Z; Helper::OpenDialogHookHWDetect(HWND__ *,uint,unsigned __int64,__int64)
0x180014b59  mov     r9, rbx; unsigned __int64
0x180014b5c  mov     r8, rdi; unsigned int
0x180014b5f  mov     edx, esi; HWND
0x180014b61  mov     rcx, rbp; hWnd
0x180014b64  add     rsp, 28h
0x180014b68  pop     rdi
0x180014b69  pop     rsi
0x180014b6a  pop     rbp
0x180014b6b  pop     rbx
0x180014b6c  jmp     ?OpenDialogHookAddButton@Helper@@YA_KPEAUHWND__@@I_K_J@Z; Helper::OpenDialogHookAddButton(HWND__ *,uint,unsigned __int64,__int64)
```
