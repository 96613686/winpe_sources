# CConfigAdvancedPage::ValidateFolderForAchive(HWND__ *)

- ea: `0x180015200`
- end: `0x1800152d1`
- name: `?ValidateFolderForAchive@CConfigAdvancedPage@@AEBAXPEAUHWND__@@@Z`
- size: `209`
- prototype: `void __fastcall(CConfigAdvancedPage *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180014ad0`

## callees

- `0x180005eac`
- `0x18000edb0`
- `0x18000f1dc`
- `0x180015200`
- `0x180017010`

## pseudocode

```c
void __fastcall CConfigAdvancedPage::ValidateFolderForAchive(CConfigAdvancedPage *this, HWND a2)
{
  unsigned int v4; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids);
  }
  v4 = ValidateFolderForStore(*((_QWORD *)this + 4), a2, (char *)this + 40);
  if ( v4 )
  {
    if ( v4 != 161 )
    {
      (*(__int64 (__fastcall **)(CConfigAdvancedPage *, _QWORD))(*(_QWORD *)this + 48LL))(this, v4);
      FaxMsgBox(a2, *((_QWORD *)this + 1), 4656);
    }
  }
}

```

## disassembly

```asm
0x180015200  mov     [rsp+arg_0], rbx
0x180015205  mov     [rsp+arg_8], rsi
0x18001520a  push    rdi
0x18001520b  sub     rsp, 30h
0x18001520f  mov     rsi, rdx
0x180015212  mov     rdi, rcx
0x180015215  mov     rcx, cs:WPP_GLOBAL_Control
0x18001521c  lea     rax, WPP_GLOBAL_Control
0x180015223  cmp     rcx, rax
0x180015226  jz      short loc_18001524C
0x180015228  test    dword ptr [rcx+1Ch], 100h
0x18001522f  jz      short loc_18001524C
0x180015231  cmp     byte ptr [rcx+19h], 5
0x180015235  jb      short loc_18001524C
0x180015237  mov     rcx, [rcx+10h]
0x18001523b  lea     r8, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids
0x180015242  mov     edx, 21h ; '!'
0x180015247  call    WPP_SF_
0x18001524c  mov     rcx, [rdi+20h]
0x180015250  lea     r8, [rdi+28h]
0x180015254  mov     rdx, rsi
0x180015257  call    ValidateFolderForStore
0x18001525c  mov     ebx, eax
0x18001525e  test    eax, eax
0x180015260  jz      short loc_1800152C1
0x180015262  cmp     eax, 0A1h
0x180015267  jz      short loc_1800152C1
0x180015269  mov     rcx, [rdi]
0x18001526c  mov     edx, ebx
0x18001526e  mov     rax, [rcx+30h]
0x180015272  mov     rcx, rdi
0x180015275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001527a  test    eax, eax
0x18001527c  jnz     short loc_1800152A4
0x18001527e  cmp     ebx, 5
0x180015281  jz      short loc_18001529F
0x180015283  cmp     ebx, 8
0x180015286  jz      short loc_180015298
0x180015288  mov     eax, 1234h
0x18001528d  cmp     ebx, 7Ah ; 'z'
0x180015290  lea     ecx, [rax+2]
0x180015293  cmovnz  eax, ecx
0x180015296  jmp     short loc_1800152A4
0x180015298  mov     eax, 1237h
0x18001529d  jmp     short loc_1800152A4
0x18001529f  mov     eax, 1235h
0x1800152a4  mov     rdx, [rdi+8]
0x1800152a8  mov     r9d, eax
0x1800152ab  mov     r8d, 1230h
0x1800152b1  mov     [rsp+38h+var_18], 10h
0x1800152b9  mov     rcx, rsi
0x1800152bc  call    FaxMsgBox
0x1800152c1  mov     rbx, [rsp+38h+arg_0]
0x1800152c6  mov     rsi, [rsp+38h+arg_8]
0x1800152cb  add     rsp, 30h
0x1800152cf  pop     rdi
0x1800152d0  retn
```
