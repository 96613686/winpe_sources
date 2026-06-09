# CVerifiedTrustUI::OnLinkClicked(unsigned __int64,tagLITEM const *)

- ea: `0x18003cd70`
- end: `0x18003cdfa`
- name: `?OnLinkClicked@CVerifiedTrustUI@@UEAAH_KPEBUtagLITEM@@@Z`
- size: `138`
- prototype: `__int64 __fastcall(CVerifiedTrustUI *this, __int64, const struct tagLITEM *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18003a4c8`
- `0x18003ae00`
- `0x18003c2c8`
- `0x18003cd70`

## import_xrefs

- `SHELL32!ShellExecuteW` at `0x18003cde8`
- `SHELL32!ShellExecuteW` at `0x18003cde8`

## string_xrefs

- `0x18003cdd6`: `https://go.microsoft.com/fwlink/?LinkId=229453`
- `0x18003cde1`: `https://go.microsoft.com/fwlink/?LinkId=229454`

## pseudocode

```c
__int64 __fastcall CVerifiedTrustUI::OnLinkClicked(CVerifiedTrustUI *this, __int64 a2, const struct tagLITEM *a3)
{
  unsigned int v3; // ebx
  const WCHAR *v4; // rdx
  unsigned int v5; // eax
  const WCHAR *v6; // r8

  v3 = 1;
  if ( a2 == 10509 )
  {
    v4 = *(const WCHAR **)(*((_QWORD *)this + 1) + 64LL);
    if ( v4 )
    {
      TUIGoLink(*((HWND *)this + 6), v4);
      return v3;
    }
    return 0;
  }
  if ( a2 == 10503 )
  {
    CInvokeInfoHelper::CallCertViewProperties(*((CInvokeInfoHelper **)this + 1), *((HWND *)this + 6));
    return v3;
  }
  if ( a2 != 10511 )
    return 0;
  v5 = CInvokeInfoHelper::UIContext(*((CInvokeInfoHelper **)this + 1));
  v6 = L"https://go.microsoft.com/fwlink/?LinkId=229453";
  if ( v5 == 1 )
    v6 = L"https://go.microsoft.com/fwlink/?LinkId=229454";
  ShellExecuteW(0, 0, v6, 0, 0, 1);
  return v3;
}

```

## disassembly

```asm
0x18003cd70  push    rbx
0x18003cd72  sub     rsp, 30h
0x18003cd76  mov     ebx, 1
0x18003cd7b  cmp     rdx, 290Dh
0x18003cd82  jnz     short loc_18003CD9C
0x18003cd84  mov     rax, [rcx+8]
0x18003cd88  mov     rdx, [rax+40h]; lpFile
0x18003cd8c  test    rdx, rdx
0x18003cd8f  jz      short loc_18003CDF0
0x18003cd91  mov     rcx, [rcx+30h]; hwnd
0x18003cd95  call    ?TUIGoLink@@YAJPEAUHWND__@@PEBG@Z; TUIGoLink(HWND__ *,ushort const *)
0x18003cd9a  jmp     short loc_18003CDF2
0x18003cd9c  cmp     rdx, 2907h
0x18003cda3  jnz     short loc_18003CDB4
0x18003cda5  mov     rdx, [rcx+30h]; HWND
0x18003cda9  mov     rcx, [rcx+8]; this
0x18003cdad  call    ?CallCertViewProperties@CInvokeInfoHelper@@QEBAHPEAUHWND__@@@Z; CInvokeInfoHelper::CallCertViewProperties(HWND__ *)
0x18003cdb2  jmp     short loc_18003CDF2
0x18003cdb4  cmp     rdx, 290Fh
0x18003cdbb  jnz     short loc_18003CDF0
0x18003cdbd  mov     rcx, [rcx+8]; this
0x18003cdc1  call    ?UIContext@CInvokeInfoHelper@@QEBAKXZ; CInvokeInfoHelper::UIContext(void)
0x18003cdc6  xor     ecx, ecx; hwnd
0x18003cdc8  mov     [rsp+38h+nShowCmd], ebx; nShowCmd
0x18003cdcc  xor     edx, edx; lpOperation
0x18003cdce  mov     [rsp+38h+lpDirectory], rcx; lpDirectory
0x18003cdd3  xor     r9d, r9d; lpParameters
0x18003cdd6  lea     r8, aHttpsGoMicroso_0; "https://go.microsoft.com/fwlink/?LinkId"...
0x18003cddd  cmp     eax, ebx
0x18003cddf  jnz     short loc_18003CDE8
0x18003cde1  lea     r8, aHttpsGoMicroso; "https://go.microsoft.com/fwlink/?LinkId"...
0x18003cde8  call    cs:__imp_ShellExecuteW
0x18003cdee  jmp     short loc_18003CDF2
0x18003cdf0  xor     ebx, ebx
0x18003cdf2  mov     eax, ebx
0x18003cdf4  add     rsp, 30h
0x18003cdf8  pop     rbx
0x18003cdf9  retn
```
