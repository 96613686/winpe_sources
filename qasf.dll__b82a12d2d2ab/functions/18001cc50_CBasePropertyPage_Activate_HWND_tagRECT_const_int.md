# CBasePropertyPage::Activate(HWND__ *,tagRECT const *,int)

- ea: `0x18001cc50`
- end: `0x18001ccf3`
- name: `?Activate@CBasePropertyPage@@UEAAJPEAUHWND__@@PEBUtagRECT@@H@Z`
- size: `163`
- prototype: `__int64 __fastcall(LPARAM dwInitParam, HWND hWndParent, const struct tagRECT *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001cc50`
- `0x18001f010`

## import_xrefs

- `USER32!CreateDialogParamW` at `0x18001cc93`
- `USER32!CreateDialogParamW` at `0x18001cc93`

## pseudocode

```c
__int64 __fastcall CBasePropertyPage::Activate(LPARAM dwInitParam, HWND hWndParent, const struct tagRECT *a3)
{
  HWND DialogParamW; // rax

  if ( !a3 )
    return 2147500035LL;
  if ( !*(_DWORD *)(dwInitParam + 68) || *(_QWORD *)(dwInitParam + 40) )
    return 2147549183LL;
  DialogParamW = CreateDialogParamW(
                   g_hInst,
                   (LPCWSTR)*(unsigned __int16 *)(dwInitParam + 64),
                   hWndParent,
                   CBasePropertyPage::DialogProc,
                   dwInitParam);
  *(_QWORD *)(dwInitParam + 40) = DialogParamW;
  if ( !DialogParamW )
    return 2147942414LL;
  (*(void (__fastcall **)(LPARAM))(*(_QWORD *)dwInitParam + 128LL))(dwInitParam);
  (*(void (__fastcall **)(LPARAM, const struct tagRECT *))(*(_QWORD *)dwInitParam + 72LL))(dwInitParam, a3);
  return (*(__int64 (__fastcall **)(LPARAM, __int64))(*(_QWORD *)dwInitParam + 64LL))(dwInitParam, 1);
}

```

## disassembly

```asm
0x18001cc50  mov     [rsp+arg_0], rbx
0x18001cc55  push    rdi
0x18001cc56  sub     rsp, 30h
0x18001cc5a  mov     rdi, r8
0x18001cc5d  mov     rbx, rcx
0x18001cc60  mov     r8, rdx; hWndParent
0x18001cc63  test    rdi, rdi
0x18001cc66  jnz     short loc_18001CC6F
0x18001cc68  mov     eax, 80004003h
0x18001cc6d  jmp     short loc_18001CCE8
0x18001cc6f  cmp     dword ptr [rcx+44h], 0
0x18001cc73  jz      short loc_18001CCE3
0x18001cc75  cmp     qword ptr [rcx+28h], 0
0x18001cc7a  jnz     short loc_18001CCE3
0x18001cc7c  movzx   edx, word ptr [rcx+40h]; lpTemplateName
0x18001cc80  lea     r9, ?DialogProc@CBasePropertyPage@@KA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18001cc87  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x18001cc8e  mov     [rsp+38h+dwInitParam], rbx; dwInitParam
0x18001cc93  call    cs:__imp_CreateDialogParamW
0x18001cc99  mov     [rbx+28h], rax
0x18001cc9d  test    rax, rax
0x18001cca0  jnz     short loc_18001CCA9
0x18001cca2  mov     eax, 8007000Eh
0x18001cca7  jmp     short loc_18001CCE8
0x18001cca9  mov     rax, [rbx]
0x18001ccac  mov     rcx, rbx
0x18001ccaf  mov     rax, [rax+80h]
0x18001ccb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccbb  mov     rax, [rbx]
0x18001ccbe  mov     rdx, rdi
0x18001ccc1  mov     rcx, rbx
0x18001ccc4  mov     rax, [rax+48h]
0x18001ccc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cccd  mov     rax, [rbx]
0x18001ccd0  mov     edx, 1
0x18001ccd5  mov     rcx, rbx
0x18001ccd8  mov     rax, [rax+40h]
0x18001ccdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cce1  jmp     short loc_18001CCE8
0x18001cce3  mov     eax, 8000FFFFh
0x18001cce8  mov     rbx, [rsp+38h+arg_0]
0x18001cced  add     rsp, 30h
0x18001ccf1  pop     rdi
0x18001ccf2  retn
```
