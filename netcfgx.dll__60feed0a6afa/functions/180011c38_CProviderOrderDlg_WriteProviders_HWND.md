# CProviderOrderDlg::WriteProviders(HWND__ *)

- ea: `0x180011c38`
- end: `0x180011dc2`
- name: `?WriteProviders@CProviderOrderDlg@@AEAAJPEAUHWND__@@@Z`
- size: `394`
- prototype: `__int64 __fastcall(LPARAM *this, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1800115f0`

## callees

- `0x180001f90`
- `0x1800030e0`
- `0x180008560`
- `0x180011780`
- `0x180011c38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011d71`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011d71`
- `USER32!SendMessageW` at `0x180011ce6`
- `USER32!SendMessageW` at `0x180011d15`
- `USER32!SendMessageW` at `0x180011d2f`
- `USER32!SendMessageW` at `0x180011ce6`
- `USER32!SendMessageW` at `0x180011d15`
- `USER32!SendMessageW` at `0x180011d2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProviderOrderDlg::WriteProviders(LPARAM *this, HWND a2)
{
  unsigned int v4; // ebx
  LPARAM v5; // r9
  LRESULT v6; // rsi
  LPCWSTR v7; // rdi
  int v8; // eax
  LSTATUS v9; // eax
  BYTE Data[8]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  LPARAM lParam[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v14; // [rsp+50h] [rbp-B0h]
  __int128 v15; // [rsp+60h] [rbp-A0h]
  LPCWSTR lpValueName; // [rsp+70h] [rbp-90h]
  char v17; // [rsp+80h] [rbp-80h] BYREF

  lpValueName = 0;
  hKey = 0;
  *(_OWORD *)lParam = 0;
  v14 = 0;
  v15 = 0;
  v4 = HrRegOpenKeyEx(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\NetworkProvider\\ProviderOrder",
         0x20006u,
         &hKey);
  if ( !v4 )
  {
    CProviderOrderDlg::UpdateProviderPriorities((CProviderOrderDlg *)this, a2);
    v5 = this[6];
    *((_QWORD *)&v14 + 1) = &v17;
    LODWORD(lParam[0]) = 5;
    LODWORD(v15) = 128;
    v6 = SendMessageW(a2, 0x110Au, 4u, v5);
    while ( v6 )
    {
      if ( v4 )
        break;
      lParam[1] = v6;
      SendMessageW(a2, 0x113Eu, 0, (LPARAM)lParam);
      v7 = lpValueName;
      v6 = SendMessageW(a2, 0x110Au, 1u, v6);
      if ( *((_BYTE *)v7 + 68) )
      {
        v8 = *((_DWORD *)v7 + 16);
        if ( *((_QWORD *)v7 + 3) > 7u )
          v7 = *(LPCWSTR *)v7;
        *(_DWORD *)Data = v8;
        v9 = RegSetValueExW(hKey, v7, 0, 4u, Data, 4u);
        v4 = v9;
        if ( v9 > 0 )
          v4 = (unsigned __int16)v9 | 0x80070000;
      }
    }
  }
  ATL::CRegKey::~CRegKey((ATL::CRegKey *)&hKey);
  return v4;
}

```

## disassembly

```asm
0x180011c38  mov     [rsp-8+arg_10], rbx
0x180011c3d  mov     [rsp-8+arg_18], rsi
0x180011c42  push    rbp
0x180011c43  push    rdi
0x180011c44  push    r14
0x180011c46  lea     rbp, [rsp-0A0h]
0x180011c4e  sub     rsp, 1A0h
0x180011c55  mov     rax, cs:__security_cookie
0x180011c5c  xor     rax, rsp
0x180011c5f  mov     [rbp+0B0h+var_20], rax
0x180011c66  xorps   xmm0, xmm0
0x180011c69  lea     r9, [rsp+1B0h+hKey]; HKEY *
0x180011c6e  xor     eax, eax
0x180011c70  mov     r14, rdx
0x180011c73  mov     rdi, rcx
0x180011c76  mov     [rsp+1B0h+lpValueName], rax
0x180011c7b  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Net"...
0x180011c82  mov     [rsp+1B0h+hKey], rax
0x180011c87  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180011c8e  mov     r8d, 20006h; unsigned int
0x180011c94  movups  xmmword ptr [rsp+1B0h+lParam], xmm0
0x180011c99  movups  [rsp+1B0h+var_160], xmm0
0x180011c9e  movups  [rsp+1B0h+var_150], xmm0
0x180011ca3  call    ?HrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z; HrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,HKEY__ * *)
0x180011ca8  mov     ebx, eax
0x180011caa  test    eax, eax
0x180011cac  jnz     loc_180011D8F
0x180011cb2  mov     rdx, r14; HWND
0x180011cb5  mov     rcx, rdi; this
0x180011cb8  call    ?UpdateProviderPriorities@CProviderOrderDlg@@AEAAXPEAUHWND__@@@Z; CProviderOrderDlg::UpdateProviderPriorities(HWND__ *)
0x180011cbd  mov     r9, [rdi+30h]; lParam
0x180011cc1  lea     rax, [rbp+0B0h+var_130]
0x180011cc5  mov     edx, 110Ah; Msg
0x180011cca  mov     qword ptr [rsp+1B0h+var_160+8], rax
0x180011ccf  lea     r8d, [rbx+4]; wParam
0x180011cd3  mov     dword ptr [rsp+1B0h+lParam], 5
0x180011cdb  mov     rcx, r14; hWnd
0x180011cde  mov     dword ptr [rsp+1B0h+var_150], 80h
0x180011ce6  call    cs:__imp_SendMessageW
0x180011cec  mov     rsi, rax
0x180011cef  test    rax, rax
0x180011cf2  jz      loc_180011D8F
0x180011cf8  test    ebx, ebx
0x180011cfa  jnz     loc_180011D8F
0x180011d00  lea     r9, [rsp+1B0h+lParam]; lParam
0x180011d05  mov     [rsp+1B0h+lParam+8], rsi
0x180011d0a  xor     r8d, r8d; wParam
0x180011d0d  mov     edx, 113Eh; Msg
0x180011d12  mov     rcx, r14; hWnd
0x180011d15  call    cs:__imp_SendMessageW
0x180011d1b  mov     rdi, [rsp+1B0h+lpValueName]
0x180011d20  lea     r8d, [rbx+1]; wParam
0x180011d24  mov     r9, rsi; lParam
0x180011d27  mov     edx, 110Ah; Msg
0x180011d2c  mov     rcx, r14; hWnd
0x180011d2f  call    cs:__imp_SendMessageW
0x180011d35  mov     rsi, rax
0x180011d38  cmp     [rdi+44h], bl
0x180011d3b  jz      short loc_180011D86
0x180011d3d  cmp     qword ptr [rdi+18h], 7
0x180011d42  mov     eax, [rdi+40h]
0x180011d45  jbe     short loc_180011D4A
0x180011d47  mov     rdi, [rdi]
0x180011d4a  mov     rcx, [rsp+1B0h+hKey]; hKey
0x180011d4f  mov     r9d, 4; dwType
0x180011d55  mov     dword ptr [rsp+1B0h+Data], eax
0x180011d59  xor     r8d, r8d; Reserved
0x180011d5c  lea     rax, [rsp+1B0h+Data]
0x180011d61  mov     [rsp+1B0h+cbData], 4; cbData
0x180011d69  mov     rdx, rdi; lpValueName
0x180011d6c  mov     [rsp+1B0h+lpData], rax; lpData
0x180011d71  call    cs:__imp_RegSetValueExW
0x180011d77  mov     ebx, eax
0x180011d79  test    eax, eax
0x180011d7b  jle     short loc_180011D86
0x180011d7d  movzx   ebx, ax
0x180011d80  or      ebx, 80070000h
0x180011d86  test    rsi, rsi
0x180011d89  jnz     loc_180011CF8
0x180011d8f  lea     rcx, [rsp+1B0h+hKey]; this
0x180011d94  call    ??1CRegKey@ATL@@QEAA@XZ; ATL::CRegKey::~CRegKey(void)
0x180011d99  mov     eax, ebx
0x180011d9b  mov     rcx, [rbp+0B0h+var_20]
0x180011da2  xor     rcx, rsp; StackCookie
0x180011da5  call    __security_check_cookie
0x180011daa  lea     r11, [rsp+1B0h+var_10]
0x180011db2  mov     rbx, [r11+30h]
0x180011db6  mov     rsi, [r11+38h]
0x180011dba  mov     rsp, r11
0x180011dbd  pop     r14
0x180011dbf  pop     rdi
0x180011dc0  pop     rbp
0x180011dc1  retn
```
