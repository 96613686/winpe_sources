# CUnverifiedTrustUI::OnLinkClicked(unsigned __int64,tagLITEM const *)

- ea: `0x18003d240`
- end: `0x18003d2ca`
- name: `?OnLinkClicked@CUnverifiedTrustUI@@UEAAH_KPEBUtagLITEM@@@Z`
- size: `138`
- prototype: `__int64 __fastcall(CUnverifiedTrustUI *this, __int64, const struct tagLITEM *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003a4c8`
- `0x18003ae00`
- `0x18003d240`

## import_xrefs

- `SHELL32!ShellExecuteW` at `0x18003d2b6`
- `SHELL32!ShellExecuteW` at `0x18003d2b6`

## string_xrefs

- `0x18003d296`: `https://go.microsoft.com/fwlink/?LinkId=229456`
- `0x18003d29f`: `https://go.microsoft.com/fwlink/?LinkId=229457`
- `0x18003d288`: `https://go.microsoft.com/fwlink/?LinkId=229455`

## pseudocode

```c
__int64 __fastcall CUnverifiedTrustUI::OnLinkClicked(CUnverifiedTrustUI *this, __int64 a2, const struct tagLITEM *a3)
{
  unsigned int v3; // ebx
  unsigned int v4; // r9d
  __int64 v5; // r8
  const WCHAR *v6; // r8

  v3 = 1;
  if ( a2 != 10503 )
  {
    if ( a2 != 10511 )
      return 0;
    v4 = CInvokeInfoHelper::UIContext(*((CInvokeInfoHelper **)this + 1));
    if ( *(_DWORD *)(v5 + 72) )
    {
      if ( v4 == 1 )
      {
        v6 = L"https://go.microsoft.com/fwlink/?LinkId=229455";
LABEL_10:
        ShellExecuteW(0, 0, v6, 0, 0, 1);
        return v3;
      }
    }
    else if ( v4 == 1 )
    {
      v6 = L"https://go.microsoft.com/fwlink/?LinkId=229457";
      goto LABEL_10;
    }
    v6 = L"https://go.microsoft.com/fwlink/?LinkId=229456";
    goto LABEL_10;
  }
  CInvokeInfoHelper::CallCertViewProperties(*((CInvokeInfoHelper **)this + 1), *((HWND *)this + 6));
  return v3;
}

```

## disassembly

```asm
0x18003d240  push    rbx
0x18003d242  sub     rsp, 30h
0x18003d246  mov     r8, rcx
0x18003d249  mov     ebx, 1
0x18003d24e  cmp     rdx, 2907h
0x18003d255  jnz     short loc_18003D266
0x18003d257  mov     rdx, [rcx+30h]; HWND
0x18003d25b  mov     rcx, [rcx+8]; this
0x18003d25f  call    ?CallCertViewProperties@CInvokeInfoHelper@@QEBAHPEAUHWND__@@@Z; CInvokeInfoHelper::CallCertViewProperties(HWND__ *)
0x18003d264  jmp     short loc_18003D2C2
0x18003d266  cmp     rdx, 290Fh
0x18003d26d  jnz     short loc_18003D2BE
0x18003d26f  mov     rcx, [rcx+8]; this
0x18003d273  call    ?UIContext@CInvokeInfoHelper@@QEBAKXZ; CInvokeInfoHelper::UIContext(void)
0x18003d278  mov     r9d, eax
0x18003d27b  xor     eax, eax
0x18003d27d  cmp     [r8+48h], eax
0x18003d281  jz      short loc_18003D291
0x18003d283  cmp     r9d, ebx
0x18003d286  jnz     short loc_18003D296
0x18003d288  lea     r8, aHttpsGoMicroso_3; "https://go.microsoft.com/fwlink/?LinkId"...
0x18003d28f  jmp     short loc_18003D2A6
0x18003d291  cmp     r9d, ebx
0x18003d294  jz      short loc_18003D29F
0x18003d296  lea     r8, aHttpsGoMicroso_1; "https://go.microsoft.com/fwlink/?LinkId"...
0x18003d29d  jmp     short loc_18003D2A6
0x18003d29f  lea     r8, aHttpsGoMicroso_2; "https://go.microsoft.com/fwlink/?LinkId"...
0x18003d2a6  mov     [rsp+38h+nShowCmd], ebx; nShowCmd
0x18003d2aa  xor     r9d, r9d; lpParameters
0x18003d2ad  xor     edx, edx; lpOperation
0x18003d2af  mov     [rsp+38h+lpDirectory], rax; lpDirectory
0x18003d2b4  xor     ecx, ecx; hwnd
0x18003d2b6  call    cs:__imp_ShellExecuteW
0x18003d2bc  jmp     short loc_18003D2C2
0x18003d2be  xor     eax, eax
0x18003d2c0  mov     ebx, eax
0x18003d2c2  mov     eax, ebx
0x18003d2c4  add     rsp, 30h
0x18003d2c8  pop     rbx
0x18003d2c9  retn
```
