# GraphicClose

- ea: `0x180004de0`
- end: `0x180004e51`
- name: `GraphicClose`
- size: `113`
- prototype: `__int64 __fastcall(struct _MCIGRAPHIC *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000485c`
- `0x1800050c0`

## callees

- `0x180001f60`
- `0x180004de0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180004e35`
- `KERNEL32!LocalFree` at `0x180004e3e`
- `KERNEL32!LocalFree` at `0x180004e35`
- `KERNEL32!LocalFree` at `0x180004e3e`
- `USER32!SendMessageW` at `0x180004e0c`
- `USER32!SendMessageW` at `0x180004e0c`

## pseudocode

```c
__int64 __fastcall GraphicClose(struct _MCIGRAPHIC *a1)
{
  unsigned int v1; // edi
  void *v4; // rcx

  v1 = 0;
  if ( a1 )
  {
    if ( hwndConfigure )
      SendMessageW(hwndConfigure, 0x111u, 2u, 0);
    v1 = DeviceClose(a1);
    if ( gfEvil )
      return 272;
    v4 = (void *)*((_QWORD *)a1 + 8);
    if ( v4 )
      LocalFree(v4);
    LocalFree(a1);
  }
  return v1;
}

```

## disassembly

```asm
0x180004de0  mov     [rsp+arg_0], rbx
0x180004de5  push    rdi
0x180004de6  sub     rsp, 20h
0x180004dea  xor     edi, edi
0x180004dec  mov     rbx, rcx
0x180004def  test    rcx, rcx
0x180004df2  jz      short loc_180004E44
0x180004df4  mov     rcx, cs:?hwndConfigure@@3PEAUHWND__@@EA; hWnd
0x180004dfb  test    rcx, rcx
0x180004dfe  jz      short loc_180004E12
0x180004e00  xor     r9d, r9d; lParam
0x180004e03  lea     r8d, [rdi+2]; wParam
0x180004e07  mov     edx, 111h; Msg
0x180004e0c  call    cs:__imp_SendMessageW
0x180004e12  mov     rcx, rbx; struct _MCIGRAPHIC *
0x180004e15  call    ?DeviceClose@@YAKPEAU_MCIGRAPHIC@@@Z; DeviceClose(_MCIGRAPHIC *)
0x180004e1a  cmp     cs:?gfEvil@@3HA, 0; int gfEvil
0x180004e21  mov     edi, eax
0x180004e23  jz      short loc_180004E2C
0x180004e25  mov     eax, 110h
0x180004e2a  jmp     short loc_180004E46
0x180004e2c  mov     rcx, [rbx+40h]; hMem
0x180004e30  test    rcx, rcx
0x180004e33  jz      short loc_180004E3B
0x180004e35  call    cs:__imp_LocalFree
0x180004e3b  mov     rcx, rbx; hMem
0x180004e3e  call    cs:__imp_LocalFree
0x180004e44  mov     eax, edi
0x180004e46  mov     rbx, [rsp+28h+arg_0]
0x180004e4b  add     rsp, 20h
0x180004e4f  pop     rdi
0x180004e50  retn
```
