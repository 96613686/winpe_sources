# CSchedulePage::_ShowControls(int,int)

- ea: `0x180016598`
- end: `0x180016626`
- name: `?_ShowControls@CSchedulePage@@AEAAXHH@Z`
- size: `142`
- prototype: `void(CSchedulePage *__hidden this, int, int)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180013c28`
- `0x180013fd8`
- `0x180014aa0`
- `0x180015db8`

## callees

- `0x180016598`

## import_xrefs

- `USER32!EnableWindow` at `0x180016608`
- `USER32!EnableWindow` at `0x180016608`
- `USER32!GetDlgItem` at `0x1800165df`
- `USER32!GetDlgItem` at `0x1800165fc`
- `USER32!GetDlgItem` at `0x1800165df`
- `USER32!GetDlgItem` at `0x1800165fc`
- `USER32!ShowWindow` at `0x1800165ea`
- `USER32!ShowWindow` at `0x1800165ea`

## pseudocode

```c
void __fastcall CSchedulePage::_ShowControls(HWND *this, int a2, int a3)
{
  __int64 v3; // rsi
  __int64 v6; // rdi
  int v7; // r15d
  BOOL v8; // r14d
  HWND DlgItem; // rax
  HWND v10; // rax

  v3 = 0;
  v6 = 3LL * a2;
  v7 = *((_DWORD *)&ttd + 6 * a2 + 4);
  if ( v7 > 0 )
  {
    v8 = a3 != 0;
    do
    {
      DlgItem = GetDlgItem(this[14], *((_DWORD *)*(&ttd + v6 + 1) + v3));
      ShowWindow(DlgItem, a3);
      v10 = GetDlgItem(this[14], *((_DWORD *)*(&ttd + v6 + 1) + v3));
      EnableWindow(v10, v8);
      v3 = (unsigned int)(v3 + 1);
    }
    while ( (int)v3 < v7 );
  }
}

```

## disassembly

```asm
0x180016598  push    rbx
0x18001659a  push    rbp
0x18001659b  push    rsi
0x18001659c  push    rdi
0x18001659d  push    r12
0x18001659f  push    r13
0x1800165a1  push    r14
0x1800165a3  push    r15
0x1800165a5  sub     rsp, 28h
0x1800165a9  movsxd  rax, edx
0x1800165ac  lea     r12, ?ttd@@3PAU_STriggerTypeData@@A; _STriggerTypeData near * ttd
0x1800165b3  xor     esi, esi
0x1800165b5  mov     ebp, r8d
0x1800165b8  mov     r13, rcx
0x1800165bb  lea     rdi, [rax+rax*2]
0x1800165bf  mov     r15d, [r12+rdi*8+10h]
0x1800165c4  test    r15d, r15d
0x1800165c7  jle     short loc_180016615
0x1800165c9  xor     r14d, r14d
0x1800165cc  test    r8d, r8d
0x1800165cf  setnz   r14b
0x1800165d3  mov     rdx, [r12+rdi*8+8]
0x1800165d8  mov     rcx, [r13+70h]; hDlg
0x1800165dc  mov     edx, [rdx+rsi*4]; nIDDlgItem
0x1800165df  call    cs:__imp_GetDlgItem
0x1800165e5  mov     rcx, rax; hWnd
0x1800165e8  mov     edx, ebp; nCmdShow
0x1800165ea  call    cs:__imp_ShowWindow
0x1800165f0  mov     rdx, [r12+rdi*8+8]
0x1800165f5  mov     rcx, [r13+70h]; hDlg
0x1800165f9  mov     edx, [rdx+rsi*4]; nIDDlgItem
0x1800165fc  call    cs:__imp_GetDlgItem
0x180016602  mov     rcx, rax; hWnd
0x180016605  mov     edx, r14d; bEnable
0x180016608  call    cs:__imp_EnableWindow
0x18001660e  inc     esi
0x180016610  cmp     esi, r15d
0x180016613  jl      short loc_1800165D3
0x180016615  add     rsp, 28h
0x180016619  pop     r15
0x18001661b  pop     r14
0x18001661d  pop     r13
0x18001661f  pop     r12
0x180016621  pop     rdi
0x180016622  pop     rsi
0x180016623  pop     rbp
0x180016624  pop     rbx
0x180016625  retn
```
