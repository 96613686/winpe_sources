# CConfigGeneralPage::EnableActiveControls(HWND__ *,int)

- ea: `0x180010748`
- end: `0x1800107a6`
- name: `?EnableActiveControls@CConfigGeneralPage@@AEBAXPEAUHWND__@@H@Z`
- size: `94`
- prototype: `void(CConfigGeneralPage *__hidden this, HWND, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800115b0`

## callees

- `0x180010748`

## import_xrefs

- `USER32!EnableWindow` at `0x18001078c`
- `USER32!EnableWindow` at `0x18001078c`
- `USER32!GetDlgItem` at `0x180010781`
- `USER32!GetDlgItem` at `0x180010781`

## pseudocode

```c
void __fastcall CConfigGeneralPage::EnableActiveControls(CConfigGeneralPage *this, HWND a2)
{
  __int64 v3; // rbx
  HWND DlgItem; // rax
  __m128i nIDDlgItem; // [rsp+20h] [rbp-38h]
  __m128i si128; // [rsp+30h] [rbp-28h]
  int v7; // [rsp+40h] [rbp-18h]

  v3 = 0;
  nIDDlgItem = _mm_load_si128((const __m128i *)&_xmm);
  v7 = 4512;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  do
  {
    DlgItem = GetDlgItem(a2, nIDDlgItem.m128i_i32[v3]);
    EnableWindow(DlgItem, 0);
    ++v3;
  }
  while ( v3 != 9 );
}

```

## disassembly

```asm
0x180010748  mov     rax, rsp
0x18001074b  mov     [rax+8], rbx
0x18001074f  push    rdi
0x180010750  sub     rsp, 50h
0x180010754  movdqa  xmm0, cs:__xmm@0000119b0000119a0000119900001198
0x18001075c  mov     rdi, rdx
0x18001075f  movdqa  xmm1, cs:__xmm@0000119f0000119e0000119d0000119c
0x180010767  xor     ebx, ebx
0x180010769  movdqu  xmmword ptr [rax-38h], xmm0
0x18001076e  mov     dword ptr [rax-18h], 11A0h
0x180010775  movdqu  xmmword ptr [rax-28h], xmm1
0x18001077a  mov     edx, dword ptr [rsp+rbx*4+58h+nIDDlgItem]; nIDDlgItem
0x18001077e  mov     rcx, rdi; hDlg
0x180010781  call    cs:__imp_GetDlgItem
0x180010787  mov     rcx, rax; hWnd
0x18001078a  xor     edx, edx; bEnable
0x18001078c  call    cs:__imp_EnableWindow
0x180010792  inc     rbx
0x180010795  cmp     rbx, 9
0x180010799  jnz     short loc_18001077A
0x18001079b  mov     rbx, [rsp+58h+arg_0]
0x1800107a0  add     rsp, 50h
0x1800107a4  pop     rdi
0x1800107a5  retn
```
