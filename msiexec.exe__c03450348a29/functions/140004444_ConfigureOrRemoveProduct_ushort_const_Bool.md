# ConfigureOrRemoveProduct(ushort const *,Bool)

- ea: `0x140004444`
- end: `0x140004533`
- name: `?ConfigureOrRemoveProduct@@YAHPEBGW4Bool@@@Z`
- size: `239`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140006300`
- `0x140008b10`

## callees

- `0x1400042b4`
- `0x140004444`
- `0x140005084`
- `0x140009820`

## import_xrefs

- `msi!__imp_MsiGetProductInfoW` at `0x1400044b8`
- `msi!__imp_MsiGetProductInfoW` at `0x1400044b8`
- `msi!__imp_MsiSetInternalUI` at `0x140004486`
- `msi!__imp_MsiSetInternalUI` at `0x140004486`
- `msi!__imp_MsiConfigureProductExW` at `0x1400044ea`
- `msi!__imp_MsiConfigureProductExW` at `0x1400044ea`

## pseudocode

```c
__int64 __fastcall ConfigureOrRemoveProduct(const WCHAR *a1, int a2)
{
  INSTALLUILEVEL v4; // ecx
  WCHAR *v5; // rcx
  UINT v6; // eax
  UINT v7; // ebx
  DWORD pcchValueBuf[4]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR ValueBuf[264]; // [rsp+30h] [rbp-228h] BYREF

  v4 = g_INSTALLUILEVEL;
  if ( g_INSTALLUILEVEL == -1 )
    v4 = a2 != 0 ? INSTALLUILEVEL_BASIC : INSTALLUILEVEL_FULL;
  MsiSetInternalUI(v4, 0);
  if ( byte_140010F60 )
  {
    ValueBuf[0] = 0;
    pcchValueBuf[0] = 260;
    MsiGetProductInfoW(a1, L"LocalPackage", ValueBuf, pcchValueBuf);
    v5 = ValueBuf;
    if ( !ValueBuf[0] )
      v5 = (WCHAR *)a1;
    ConfigureMIF(v5);
  }
  v6 = MsiConfigureProductExW(
         a1,
         0,
         (INSTALLSTATE)(a2 != 0 ? INSTALLSTATE_ABSENT : INSTALLSTATE_DEFAULT),
         g_szCommandLine);
  v7 = v6;
  if ( byte_140010F60 )
    GenerateMIF(v6);
  if ( !v7 )
    return 0x8000;
  return v7;
}

```

## disassembly

```asm
0x140004444  mov     [rsp+arg_8], rbx
0x140004449  mov     [rsp+arg_10], rsi
0x14000444e  push    rdi
0x14000444f  sub     rsp, 250h
0x140004456  mov     rax, cs:__security_cookie
0x14000445d  xor     rax, rsp
0x140004460  mov     [rsp+258h+var_18], rax
0x140004468  mov     rdi, rcx
0x14000446b  mov     ebx, edx
0x14000446d  mov     ecx, cs:?g_INSTALLUILEVEL@@3W4tagINSTALLUILEVEL@@A; tagINSTALLUILEVEL g_INSTALLUILEVEL
0x140004473  cmp     ecx, 0FFFFFFFFh
0x140004476  jnz     short loc_140004484
0x140004478  mov     eax, edx
0x14000447a  neg     eax
0x14000447c  sbb     ecx, ecx
0x14000447e  and     ecx, 0FFFFFFFEh
0x140004481  add     ecx, 5; dwUILevel
0x140004484  xor     edx, edx; phWnd
0x140004486  call    cs:__imp_MsiSetInternalUI
0x14000448c  xor     esi, esi
0x14000448e  cmp     cs:byte_140010F60, sil
0x140004495  jz      short loc_1400044D1
0x140004497  lea     r9, [rsp+258h+pcchValueBuf]; pcchValueBuf
0x14000449c  mov     [rsp+258h+ValueBuf], si
0x1400044a1  lea     r8, [rsp+258h+ValueBuf]; lpValueBuf
0x1400044a6  mov     [rsp+258h+pcchValueBuf], 104h
0x1400044ae  lea     rdx, szAttribute; "LocalPackage"
0x1400044b5  mov     rcx, rdi; szProduct
0x1400044b8  call    cs:__imp_MsiGetProductInfoW
0x1400044be  cmp     [rsp+258h+ValueBuf], si
0x1400044c3  lea     rcx, [rsp+258h+ValueBuf]
0x1400044c8  cmovz   rcx, rdi; lpWideCharStr
0x1400044cc  call    ?ConfigureMIF@@YAXPEBG@Z; ConfigureMIF(ushort const *)
0x1400044d1  mov     r9, cs:?g_szCommandLine@@3V?$CAPITempBuffer@G$0EAA@@@A; szCommandLine
0x1400044d8  neg     ebx
0x1400044da  mov     rcx, rdi; szProduct
0x1400044dd  sbb     r8d, r8d
0x1400044e0  xor     edx, edx; iInstallLevel
0x1400044e2  and     r8d, 0FFFFFFFDh
0x1400044e6  add     r8d, 5; eInstallState
0x1400044ea  call    cs:__imp_MsiConfigureProductExW
0x1400044f0  cmp     cs:byte_140010F60, sil
0x1400044f7  mov     ebx, eax
0x1400044f9  jz      short loc_140004502
0x1400044fb  mov     ecx, eax; dwMessageId
0x1400044fd  call    ?GenerateMIF@@YAXI@Z; GenerateMIF(uint)
0x140004502  mov     eax, 8000h
0x140004507  test    ebx, ebx
0x140004509  cmovz   ebx, eax
0x14000450c  mov     eax, ebx
0x14000450e  mov     rcx, [rsp+258h+var_18]
0x140004516  xor     rcx, rsp; StackCookie
0x140004519  call    __security_check_cookie
0x14000451e  lea     r11, [rsp+258h+var_8]
0x140004526  mov     rbx, [r11+18h]
0x14000452a  mov     rsi, [r11+20h]
0x14000452e  mov     rsp, r11
0x140004531  pop     rdi
0x140004532  retn
```
