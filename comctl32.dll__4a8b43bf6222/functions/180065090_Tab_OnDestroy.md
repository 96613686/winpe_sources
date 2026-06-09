# Tab_OnDestroy

- ea: `0x180065090`
- end: `0x18006517a`
- name: `Tab_OnDestroy`
- size: `234`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180066d40`

## callees

- `0x18002ec60`
- `0x18002fd4c`
- `0x180065090`
- `0x18008698c`
- `0x1800876c0`
- `0x180090020`

## import_xrefs

- `GDI32!DeleteObject` at `0x180065149`
- `GDI32!DeleteObject` at `0x180065149`
- `KERNEL32!LocalFree` at `0x180065116`
- `KERNEL32!LocalFree` at `0x180065160`
- `KERNEL32!LocalFree` at `0x180065116`
- `KERNEL32!LocalFree` at `0x180065160`
- `USER32!IsWindow` at `0x1800650d6`
- `USER32!IsWindow` at `0x1800650d6`
- `USER32!DestroyWindow` at `0x1800650e7`
- `USER32!DestroyWindow` at `0x1800650e7`
- `USER32!SetWindowLongPtrW` at `0x180065157`
- `USER32!SetWindowLongPtrW` at `0x180065157`

## pseudocode

```c
__int64 __fastcall Tab_OnDestroy(char *hMem)
{
  struct _DPA *v2; // rax
  int v3; // edi
  char *v4; // rsi

  if ( g_fDBCSInputEnabled && g_pfnImmAssociateContext )
    g_pfnImmAssociateContext(*(_QWORD *)hMem, *((_QWORD *)hMem + 23));
  if ( (*((_DWORD *)hMem + 4) & 0x4000) != 0 && IsWindow(*((HWND *)hMem + 22)) )
    DestroyWindow(*((HWND *)hMem + 22));
  v2 = (struct _DPA *)*((_QWORD *)hMem + 8);
  if ( *(int *)v2 > 0 )
  {
    v3 = 0;
    do
    {
      v4 = *(char **)(*((_QWORD *)v2 + 1) + 8LL * v3);
      if ( v4 )
      {
        Str_Set(v4 + 48, 0);
        LocalFree(v4);
      }
      v2 = (struct _DPA *)*((_QWORD *)hMem + 8);
      ++v3;
    }
    while ( v3 < *(_DWORD *)v2 );
  }
  DPA_Destroy(v2);
  if ( *((_QWORD *)hMem + 24) )
    DestroyDragProxy();
  if ( hMem[72] < 0 )
    DeleteObject(*((HGDIOBJ *)hMem + 11));
  SetWindowLongPtrW(*(HWND *)hMem, 0, 0);
  LocalFree(hMem);
  return TerminateDitherBrush();
}

```

## disassembly

```asm
0x180065090  mov     [rsp+arg_0], rbx
0x180065095  mov     [rsp+arg_8], rsi
0x18006509a  push    rdi
0x18006509b  sub     rsp, 20h
0x18006509f  cmp     cs:g_fDBCSInputEnabled, 0
0x1800650a6  mov     rbx, rcx
0x1800650a9  jz      short loc_1800650C6
0x1800650ab  mov     rax, cs:g_pfnImmAssociateContext
0x1800650b2  test    rax, rax
0x1800650b5  jz      short loc_1800650C6
0x1800650b7  mov     rdx, [rcx+0B8h]
0x1800650be  mov     rcx, [rcx]
0x1800650c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800650c6  test    dword ptr [rbx+10h], 4000h
0x1800650cd  jz      short loc_1800650ED
0x1800650cf  mov     rcx, [rbx+0B0h]; hWnd
0x1800650d6  call    cs:__imp_IsWindow
0x1800650dc  test    eax, eax
0x1800650de  jz      short loc_1800650ED
0x1800650e0  mov     rcx, [rbx+0B0h]; hWnd
0x1800650e7  call    cs:__imp_DestroyWindow
0x1800650ed  mov     rax, [rbx+40h]
0x1800650f1  cmp     dword ptr [rax], 0
0x1800650f4  jle     short loc_180065126
0x1800650f6  xor     edi, edi
0x1800650f8  mov     rax, [rax+8]
0x1800650fc  movsxd  rcx, edi
0x1800650ff  mov     rsi, [rax+rcx*8]
0x180065103  test    rsi, rsi
0x180065106  jz      short loc_18006511C
0x180065108  lea     rcx, [rsi+30h]
0x18006510c  xor     edx, edx
0x18006510e  call    Str_Set
0x180065113  mov     rcx, rsi; hMem
0x180065116  call    cs:__imp_LocalFree
0x18006511c  mov     rax, [rbx+40h]
0x180065120  inc     edi
0x180065122  cmp     edi, [rax]
0x180065124  jl      short loc_1800650F8
0x180065126  mov     rcx, rax; hdpa
0x180065129  call    DPA_Destroy
0x18006512e  mov     rcx, [rbx+0C0h]
0x180065135  test    rcx, rcx
0x180065138  jz      short loc_18006513F
0x18006513a  call    DestroyDragProxy
0x18006513f  test    byte ptr [rbx+48h], 80h
0x180065143  jz      short loc_18006514F
0x180065145  mov     rcx, [rbx+58h]; ho
0x180065149  call    cs:__imp_DeleteObject
0x18006514f  mov     rcx, [rbx]; hWnd
0x180065152  xor     r8d, r8d; dwNewLong
0x180065155  xor     edx, edx; nIndex
0x180065157  call    cs:__imp_SetWindowLongPtrW
0x18006515d  mov     rcx, rbx; hMem
0x180065160  call    cs:__imp_LocalFree
0x180065166  mov     rbx, [rsp+28h+arg_0]
0x18006516b  mov     rsi, [rsp+28h+arg_8]
0x180065170  add     rsp, 20h
0x180065174  pop     rdi
0x180065175  jmp     TerminateDitherBrush
```
