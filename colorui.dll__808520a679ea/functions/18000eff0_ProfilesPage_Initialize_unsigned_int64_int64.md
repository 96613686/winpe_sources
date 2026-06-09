# ProfilesPage::Initialize(unsigned __int64,__int64)

- ea: `0x18000eff0`
- end: `0x18000f06d`
- name: `?Initialize@ProfilesPage@@MEAAJ_K_J@Z`
- size: `125`
- prototype: `__int64 __fastcall(ProfilesPage *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18000134c`
- `0x18000eff0`
- `0x180013370`

## import_xrefs

- `USER32!GetDlgItem` at `0x18000f021`
- `USER32!GetDlgItem` at `0x18000f021`
- `mscms!WcsGpCanInstallOrUninstallProfiles` at `0x18000f057`
- `mscms!WcsGpCanInstallOrUninstallProfiles` at `0x18000f057`

## pseudocode

```c
__int64 __fastcall ProfilesPage::Initialize(ProfilesPage *this)
{
  HWND *v2; // rdi
  HWND v3; // rbx
  __int64 result; // rax

  v2 = (HWND *)operator new(0x18u);
  if ( v2 )
  {
    v3 = (HWND)*((_QWORD *)this + 2);
    *v2 = GetDlgItem(*((HWND *)this + 1), 1201);
    v2[1] = v3;
  }
  else
  {
    v2 = 0;
  }
  *((_QWORD *)this + 5) = v2;
  if ( !v2 )
    return 2147942414LL;
  result = ListView::Initialize(v2, 1);
  if ( (int)result >= 0 )
    return WcsGpCanInstallOrUninstallProfiles((char *)this + 48);
  return result;
}

```

## disassembly

```asm
0x18000eff0  mov     [rsp+arg_0], rbx
0x18000eff5  mov     [rsp+arg_8], rsi
0x18000effa  push    rdi
0x18000effb  sub     rsp, 20h
0x18000efff  mov     rsi, rcx
0x18000f002  mov     ecx, 18h; Size
0x18000f007  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f00c  mov     rdi, rax
0x18000f00f  test    rax, rax
0x18000f012  jz      short loc_18000F030
0x18000f014  mov     rcx, [rsi+8]; hDlg
0x18000f018  mov     edx, 4B1h; nIDDlgItem
0x18000f01d  mov     rbx, [rsi+10h]
0x18000f021  call    cs:__imp_GetDlgItem
0x18000f027  mov     [rdi], rax
0x18000f02a  mov     [rdi+8], rbx
0x18000f02e  jmp     short loc_18000F032
0x18000f030  xor     edi, edi
0x18000f032  mov     [rsi+28h], rdi
0x18000f036  test    rdi, rdi
0x18000f039  jnz     short loc_18000F042
0x18000f03b  mov     eax, 8007000Eh
0x18000f040  jmp     short loc_18000F05D
0x18000f042  mov     edx, 1
0x18000f047  mov     rcx, rdi
0x18000f04a  call    ?Initialize@ListView@@QEAAJW4Enum@ListViewStyle@@@Z; ListView::Initialize(ListViewStyle::Enum)
0x18000f04f  test    eax, eax
0x18000f051  js      short loc_18000F05D
0x18000f053  lea     rcx, [rsi+30h]
0x18000f057  call    cs:__imp_WcsGpCanInstallOrUninstallProfiles
0x18000f05d  mov     rbx, [rsp+28h+arg_0]
0x18000f062  mov     rsi, [rsp+28h+arg_8]
0x18000f067  add     rsp, 20h
0x18000f06b  pop     rdi
0x18000f06c  retn
```
