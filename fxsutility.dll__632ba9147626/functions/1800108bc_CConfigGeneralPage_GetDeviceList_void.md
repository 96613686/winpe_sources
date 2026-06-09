# CConfigGeneralPage::GetDeviceList(void)

- ea: `0x1800108bc`
- end: `0x180010968`
- name: `?GetDeviceList@CConfigGeneralPage@@AEAAKXZ`
- size: `172`
- prototype: `unsigned int __fastcall(CConfigGeneralPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180010970`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x1800108bc`

## import_xrefs

- `FXSAPI!FaxEnumPortsExW` at `0x180010911`
- `FXSAPI!FaxEnumPortsExW` at `0x180010911`
- `KERNEL32!GetLastError` at `0x18001091b`
- `KERNEL32!GetLastError` at `0x18001091b`

## pseudocode

```c
__int64 __fastcall CConfigGeneralPage::GetDeviceList(CConfigGeneralPage *this)
{
  DWORD v2; // ebx
  DWORD LastError; // eax

  v2 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_f5b496eade1b3798203481970613ce29_Traceguids);
  }
  if ( !(unsigned int)FaxEnumPortsExW(*((_QWORD *)this + 15), (char *)this + 32, (char *)this + 40) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_f5b496eade1b3798203481970613ce29_Traceguids, LastError);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800108bc  mov     [rsp+arg_0], rbx
0x1800108c1  mov     [rsp+arg_8], rbp
0x1800108c6  push    rdi
0x1800108c7  sub     rsp, 20h
0x1800108cb  mov     rdi, rcx
0x1800108ce  xor     ebx, ebx
0x1800108d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108d7  lea     rbp, WPP_GLOBAL_Control
0x1800108de  cmp     rcx, rbp
0x1800108e1  jz      short loc_180010905
0x1800108e3  test    dword ptr [rcx+1Ch], 100h
0x1800108ea  jz      short loc_180010905
0x1800108ec  cmp     byte ptr [rcx+19h], 5
0x1800108f0  jb      short loc_180010905
0x1800108f2  mov     rcx, [rcx+10h]
0x1800108f6  lea     edx, [rbx+0Bh]
0x1800108f9  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180010900  call    WPP_SF_
0x180010905  mov     rcx, [rdi+78h]
0x180010909  lea     r8, [rdi+28h]
0x18001090d  lea     rdx, [rdi+20h]
0x180010911  call    cs:__imp_FaxEnumPortsExW
0x180010917  test    eax, eax
0x180010919  jnz     short loc_180010956
0x18001091b  call    cs:__imp_GetLastError
0x180010921  mov     ebx, eax
0x180010923  mov     rcx, cs:WPP_GLOBAL_Control
0x18001092a  cmp     rcx, rbp
0x18001092d  jz      short loc_180010956
0x18001092f  test    dword ptr [rcx+1Ch], 100h
0x180010936  jz      short loc_180010956
0x180010938  cmp     byte ptr [rcx+19h], 2
0x18001093c  jb      short loc_180010956
0x18001093e  mov     rcx, [rcx+10h]
0x180010942  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180010949  mov     edx, 0Ch
0x18001094e  mov     r9d, eax
0x180010951  call    WPP_SF_d
0x180010956  mov     rbp, [rsp+28h+arg_8]
0x18001095b  mov     eax, ebx
0x18001095d  mov     rbx, [rsp+28h+arg_0]
0x180010962  add     rsp, 20h
0x180010966  pop     rdi
0x180010967  retn
```
