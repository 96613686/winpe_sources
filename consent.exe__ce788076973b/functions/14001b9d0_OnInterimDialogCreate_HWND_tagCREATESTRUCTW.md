# OnInterimDialogCreate(HWND__ *,tagCREATESTRUCTW *)

- ea: `0x14001b9d0`
- end: `0x14001ba20`
- name: `?OnInterimDialogCreate@@YAHPEAUHWND__@@PEAUtagCREATESTRUCTW@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(HWND, struct tagCREATESTRUCTW *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140005f70`

## import_xrefs

- `USER32!SetPropW` at `0x14001b9e6`
- `USER32!SetPropW` at `0x14001b9e6`
- `USER32!FlashWindowEx` at `0x14001ba0f`
- `USER32!FlashWindowEx` at `0x14001ba0f`

## pseudocode

```c
__int64 __fastcall OnInterimDialogCreate(HWND a1, struct tagCREATESTRUCTW *a2)
{
  $C811A85A3CBAF233E045382DA27E29BF pfwi; // [rsp+20h] [rbp-28h] BYREF

  SetPropW(a1, L"TwoFootCriticalNotification", HANDLE_FLAG_PROTECT_FROM_CLOSE);
  *(_QWORD *)&pfwi.cbSize = 32;
  *(_QWORD *)&pfwi.dwTimeout = 0;
  pfwi.hwnd = a1;
  *(_QWORD *)&pfwi.dwFlags = 6;
  FlashWindowEx(&pfwi);
  return 1;
}

```

## disassembly

```asm
0x14001b9d0  push    rbx
0x14001b9d2  sub     rsp, 40h
0x14001b9d6  mov     r8d, 2; hData
0x14001b9dc  lea     rdx, aTwofootcritica; "TwoFootCriticalNotification"
0x14001b9e3  mov     rbx, rcx
0x14001b9e6  call    cs:__imp_SetPropW
0x14001b9ec  xor     eax, eax
0x14001b9ee  mov     qword ptr [rsp+48h+pfwi.cbSize], 20h ; ' '
0x14001b9f7  lea     rcx, [rsp+48h+pfwi]; pfwi
0x14001b9fc  mov     qword ptr [rsp+48h+pfwi.dwTimeout], rax
0x14001ba01  mov     [rsp+48h+pfwi.hwnd], rbx
0x14001ba06  mov     qword ptr [rsp+48h+pfwi.dwFlags], 6
0x14001ba0f  call    cs:__imp_FlashWindowEx
0x14001ba15  mov     eax, 1
0x14001ba1a  add     rsp, 40h
0x14001ba1e  pop     rbx
0x14001ba1f  retn
```
