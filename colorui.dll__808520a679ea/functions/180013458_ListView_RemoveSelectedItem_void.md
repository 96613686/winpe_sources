# ListView::RemoveSelectedItem(void)

- ea: `0x180013458`
- end: `0x180013513`
- name: `?RemoveSelectedItem@ListView@@QEAAJXZ`
- size: `187`
- prototype: `__int64 __fastcall(HWND *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000dcdc`
- `0x18000f654`

## callees

- `0x180001334`
- `0x1800131ec`
- `0x18001327c`
- `0x180013458`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800134c2`
- `KERNEL32!GetLastError` at `0x1800134c2`
- `USER32!SendMessageW` at `0x1800134b8`
- `USER32!SendMessageW` at `0x1800134ef`
- `USER32!SendMessageW` at `0x1800134b8`
- `USER32!SendMessageW` at `0x1800134ef`

## pseudocode

```c
__int64 __fastcall ListView::RemoveSelectedItem(HWND *this)
{
  __int64 result; // rax
  unsigned int v3; // ebx
  signed int LastError; // eax
  int v5; // [rsp+38h] [rbp+10h] BYREF
  void *Block; // [rsp+40h] [rbp+18h] BYREF

  Block = 0;
  v5 = 0;
  result = ListView::GetSelectedItemIndex(this, (unsigned int *)&v5);
  if ( (int)result >= 0 )
  {
    if ( v5 == -1 )
      return 2147500037LL;
    result = ListView::GetItemLParam(this, v5, (struct Profile **)&Block);
    v3 = result;
    if ( (int)result >= 0 )
    {
      if ( !(unsigned int)SendMessageW(*this, 0x1008u, v5, 0) )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( !LastError )
          return (unsigned int)-2147467259;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        if ( (v3 & 0x80000000) != 0 )
          return v3;
      }
      SendMessageW(*this, 0x1030u, (WPARAM)this, (LPARAM)ListView::SubItemCompareFuncUpdated);
      operator delete(Block);
      return v3;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180013458  mov     rax, rsp
0x18001345b  mov     [rax+8], rbx
0x18001345f  push    rdi
0x180013460  sub     rsp, 20h
0x180013464  lea     rdx, [rax+10h]; int *
0x180013468  mov     qword ptr [rax+18h], 0
0x180013470  mov     rdi, rcx
0x180013473  mov     dword ptr [rax+10h], 0
0x18001347a  call    ?GetSelectedItemIndex@ListView@@QEBAJPEAH@Z; ListView::GetSelectedItemIndex(int *)
0x18001347f  test    eax, eax
0x180013481  js      short loc_180013501
0x180013483  cmp     [rsp+28h+arg_8], 0FFFFFFFFh
0x180013488  jnz     short loc_180013491
0x18001348a  mov     eax, 80004005h
0x18001348f  jmp     short loc_180013501
0x180013491  mov     edx, [rsp+28h+arg_8]; int
0x180013495  lea     r8, [rsp+28h+Block]; struct Profile **
0x18001349a  mov     rcx, rdi; this
0x18001349d  call    ?GetItemLParam@ListView@@QEBAJHPEAPEAUProfile@@@Z; ListView::GetItemLParam(int,Profile * *)
0x1800134a2  mov     ebx, eax
0x1800134a4  test    eax, eax
0x1800134a6  js      short loc_180013501
0x1800134a8  movsxd  r8, [rsp+28h+arg_8]; wParam
0x1800134ad  xor     r9d, r9d; lParam
0x1800134b0  mov     rcx, [rdi]; hWnd
0x1800134b3  mov     edx, 1008h; Msg
0x1800134b8  call    cs:__imp_SendMessageW
0x1800134be  test    eax, eax
0x1800134c0  jnz     short loc_1800134DD
0x1800134c2  call    cs:__imp_GetLastError
0x1800134c8  mov     ebx, eax
0x1800134ca  test    eax, eax
0x1800134cc  jz      short loc_18001350C
0x1800134ce  jle     short loc_1800134D9
0x1800134d0  movzx   ebx, ax
0x1800134d3  or      ebx, 80070000h
0x1800134d9  test    ebx, ebx
0x1800134db  js      short loc_1800134FF
0x1800134dd  mov     rcx, [rdi]; hWnd
0x1800134e0  lea     r9, ?SubItemCompareFuncUpdated@ListView@@CAH_J00@Z; lParam
0x1800134e7  mov     r8, rdi; wParam
0x1800134ea  mov     edx, 1030h; Msg
0x1800134ef  call    cs:__imp_SendMessageW
0x1800134f5  mov     rcx, [rsp+28h+Block]; Block
0x1800134fa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800134ff  mov     eax, ebx
0x180013501  mov     rbx, [rsp+28h+arg_0]
0x180013506  add     rsp, 20h
0x18001350a  pop     rdi
0x18001350b  retn
0x18001350c  mov     ebx, 80004005h
0x180013511  jmp     short loc_1800134FF
```
