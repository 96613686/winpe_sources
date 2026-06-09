# _GetOpenSavedServer(HWND__ *,ushort *,ushort)

- ea: `0x180007724`
- end: `0x180007828`
- name: `?_GetOpenSavedServer@@YAXPEAUHWND__@@PEAGG@Z`
- size: `260`
- prototype: `void(HWND, unsigned __int16 *, unsigned __int16)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180007f70`
- `0x18000839c`

## callees

- `0x180007724`
- `0x180020ae0`
- `0x180020ee0`
- `0x1800222d0`

## import_xrefs

- `USER32!SendMessageW` at `0x1800077db`
- `USER32!SendMessageW` at `0x1800077db`
- `USER32!GetParent` at `0x18000774b`
- `USER32!GetParent` at `0x18000774b`
- `USER32!GetDlgItemTextW` at `0x180007767`
- `USER32!GetDlgItemTextW` at `0x180007767`

## pseudocode

```c
void __fastcall _GetOpenSavedServer(HWND a1, unsigned __int16 *a2)
{
  HWND Parent; // rdi
  WCHAR v4; // cx
  WCHAR *v5; // rdx
  WCHAR *v6; // rax
  WCHAR String[264]; // [rsp+30h] [rbp-228h] BYREF

  Parent = GetParent(a1);
  GetDlgItemTextW(Parent, 1148, String, 260);
  StripLeadTrailSpace(String);
  v4 = String[0];
  v5 = String;
  if ( String[0] )
  {
    v6 = String;
    do
    {
      if ( v4 != 34 )
        *v5++ = v4;
      v4 = *++v6;
    }
    while ( *v6 );
  }
  *v5 = 0;
  if ( (unsigned int)RemoteFileToServerAndUNCPath(String, a2, 0x104u, 0, 0) )
  {
    SendMessageW(Parent, 0x466u, 0x104u, (LPARAM)String);
    if ( (unsigned int)RemoteFileToServerAndUNCPath(String, a2, 0x104u, 0, 0) )
      *a2 = 0;
  }
}

```

## disassembly

```asm
0x180007724  mov     [rsp+arg_10], rbx
0x180007729  mov     [rsp+arg_18], rsi
0x18000772e  push    rdi
0x18000772f  sub     rsp, 250h
0x180007736  mov     rax, cs:__security_cookie
0x18000773d  xor     rax, rsp
0x180007740  mov     [rsp+258h+var_18], rax
0x180007748  mov     rbx, rdx
0x18000774b  call    cs:__imp_GetParent
0x180007751  mov     r9d, 104h; cchMax
0x180007757  lea     r8, [rsp+258h+String]; lpString
0x18000775c  mov     rcx, rax; hDlg
0x18000775f  mov     edx, 47Ch; nIDDlgItem
0x180007764  mov     rdi, rax
0x180007767  call    cs:__imp_GetDlgItemTextW
0x18000776d  lea     rcx, [rsp+258h+String]; unsigned __int16 *
0x180007772  call    ?StripLeadTrailSpace@@YAXPEAG@Z; StripLeadTrailSpace(ushort *)
0x180007777  movzx   ecx, [rsp+258h+String]
0x18000777c  lea     rdx, [rsp+258h+String]
0x180007781  xor     esi, esi
0x180007783  test    cx, cx
0x180007786  jz      short loc_1800077A6
0x180007788  lea     rax, [rsp+258h+String]
0x18000778d  cmp     cx, 22h ; '"'
0x180007791  jz      short loc_18000779A
0x180007793  mov     [rdx], cx
0x180007796  add     rdx, 2
0x18000779a  add     rax, 2
0x18000779e  movzx   ecx, word ptr [rax]
0x1800077a1  test    cx, cx
0x1800077a4  jnz     short loc_18000778D
0x1800077a6  mov     [rdx], si
0x1800077a9  lea     rcx, [rsp+258h+String]; Source
0x1800077ae  mov     rdx, rbx; unsigned __int16 *
0x1800077b1  mov     [rsp+258h+var_238], si; unsigned __int16
0x1800077b6  mov     r8d, 104h; unsigned __int16
0x1800077bc  xor     r9d, r9d; unsigned __int16 *
0x1800077bf  call    ?RemoteFileToServerAndUNCPath@@YAJPEBGPEAGG1G@Z; RemoteFileToServerAndUNCPath(ushort const *,ushort *,ushort,ushort *,ushort)
0x1800077c4  test    eax, eax
0x1800077c6  jz      short loc_180007803
0x1800077c8  lea     r9, [rsp+258h+String]; lParam
0x1800077cd  mov     edx, 466h; Msg
0x1800077d2  mov     r8d, 104h; wParam
0x1800077d8  mov     rcx, rdi; hWnd
0x1800077db  call    cs:__imp_SendMessageW
0x1800077e1  mov     r8d, 104h; unsigned __int16
0x1800077e7  mov     [rsp+258h+var_238], si; unsigned __int16
0x1800077ec  xor     r9d, r9d; unsigned __int16 *
0x1800077ef  lea     rcx, [rsp+258h+String]; Source
0x1800077f4  mov     rdx, rbx; unsigned __int16 *
0x1800077f7  call    ?RemoteFileToServerAndUNCPath@@YAJPEBGPEAGG1G@Z; RemoteFileToServerAndUNCPath(ushort const *,ushort *,ushort,ushort *,ushort)
0x1800077fc  test    eax, eax
0x1800077fe  jz      short loc_180007803
0x180007800  mov     [rbx], si
0x180007803  mov     rcx, [rsp+258h+var_18]
0x18000780b  xor     rcx, rsp; StackCookie
0x18000780e  call    __security_check_cookie
0x180007813  lea     r11, [rsp+258h+var_8]
0x18000781b  mov     rbx, [r11+20h]
0x18000781f  mov     rsi, [r11+28h]
0x180007823  mov     rsp, r11
0x180007826  pop     rdi
0x180007827  retn
```
