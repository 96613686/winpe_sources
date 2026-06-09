# CTouchSelectionHandle::GetPostWidth(void)

- ea: `0x180200d04`
- end: `0x180200de2`
- name: `?GetPostWidth@CTouchSelectionHandle@@IEBAHXZ`
- size: `222`
- prototype: `__int64 __fastcall(CTouchSelectionHandle *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180200628`
- `0x180200ff4`

## callees

- `0x18013ce80`
- `0x1801fed3c`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180200d58`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180200d94`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180200d58`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180200d94`
- `ext-ms-win-gdi-font-l1-1-1!GetCharABCWidthsW` at `0x180200d82`
- `ext-ms-win-gdi-font-l1-1-1!GetCharABCWidthsW` at `0x180200d82`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180200da3`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180200da3`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x180200d43`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x180200d43`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x180200db4`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x180200db4`

## pseudocode

```c
__int64 __fastcall CTouchSelectionHandle::GetPostWidth(CTouchSelectionHandle *this)
{
  __int64 v1; // rdx
  HFONT v2; // rsi
  HDC DC; // rdi
  HGDIOBJ v4; // rbx
  int v6; // [rsp+20h] [rbp-28h] BYREF
  _ABC ABC; // [rsp+28h] [rbp-20h] BYREF

  v1 = *((_QWORD *)this + 16);
  v6 = 0;
  v2 = CTouchSelectionHandle::CreateGripperFont(this, *(_DWORD *)(v1 + 24), &v6);
  DC = GetDC(0);
  v4 = SelectObject(DC, v2);
  *(_QWORD *)&ABC.abcA = 0;
  ABC.abcC = 0;
  GetCharABCWidthsW(DC, 0xE2A2u, 0xE2A2u, &ABC);
  SelectObject(DC, v4);
  DeleteObject(v2);
  ReleaseDC(0, DC);
  return ABC.abcB;
}

```

## disassembly

```asm
0x180200d04  mov     [rsp+arg_8], rbx
0x180200d09  mov     [rsp+arg_10], rsi
0x180200d0e  push    rdi
0x180200d0f  sub     rsp, 40h
0x180200d13  mov     rax, cs:__security_cookie
0x180200d1a  xor     rax, rsp
0x180200d1d  mov     [rsp+48h+var_10], rax
0x180200d22  mov     rdx, [rcx+80h]
0x180200d29  lea     r8, [rsp+48h+var_28]; int *
0x180200d2e  mov     [rsp+48h+var_28], 0
0x180200d36  mov     edx, [rdx+18h]; int
0x180200d39  call    ?CreateGripperFont@CTouchSelectionHandle@@IEBAPEAUHFONT__@@HPEAH@Z; CTouchSelectionHandle::CreateGripperFont(int,int *)
0x180200d3e  xor     ecx, ecx; hWnd
0x180200d40  mov     rsi, rax
0x180200d43  call    cs:__imp_GetDC
0x180200d4a  nop     dword ptr [rax+rax+00h]
0x180200d4f  mov     rcx, rax; hdc
0x180200d52  mov     rdx, rsi; h
0x180200d55  mov     rdi, rax
0x180200d58  call    cs:__imp_SelectObject
0x180200d5f  nop     dword ptr [rax+rax+00h]
0x180200d64  mov     edx, 0E2A2h; wFirst
0x180200d69  lea     r9, [rsp+48h+ABC]; lpABC
0x180200d6e  mov     rbx, rax
0x180200d71  mov     r8d, edx; wLast
0x180200d74  xor     eax, eax
0x180200d76  mov     rcx, rdi; hdc
0x180200d79  mov     qword ptr [rsp+48h+ABC.abcA], rax
0x180200d7e  mov     [rsp+48h+ABC.abcC], eax
0x180200d82  call    cs:__imp_GetCharABCWidthsW
0x180200d89  nop     dword ptr [rax+rax+00h]
0x180200d8e  mov     rdx, rbx; h
0x180200d91  mov     rcx, rdi; hdc
0x180200d94  call    cs:__imp_SelectObject
0x180200d9b  nop     dword ptr [rax+rax+00h]
0x180200da0  mov     rcx, rsi; ho
0x180200da3  call    cs:__imp_DeleteObject
0x180200daa  nop     dword ptr [rax+rax+00h]
0x180200daf  mov     rdx, rdi; hDC
0x180200db2  xor     ecx, ecx; hWnd
0x180200db4  call    cs:__imp_ReleaseDC
0x180200dbb  nop     dword ptr [rax+rax+00h]
0x180200dc0  mov     eax, [rsp+48h+ABC.abcB]
0x180200dc4  mov     rcx, [rsp+48h+var_10]
0x180200dc9  xor     rcx, rsp; StackCookie
0x180200dcc  call    __security_check_cookie
0x180200dd1  mov     rbx, [rsp+48h+arg_8]
0x180200dd6  mov     rsi, [rsp+48h+arg_10]
0x180200ddb  add     rsp, 40h
0x180200ddf  pop     rdi
0x180200de0  retn
```
