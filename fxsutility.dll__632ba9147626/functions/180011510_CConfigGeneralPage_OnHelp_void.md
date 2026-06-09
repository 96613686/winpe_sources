# CConfigGeneralPage::OnHelp(void)

- ea: `0x180011510`
- end: `0x1800115a3`
- name: `?OnHelp@CConfigGeneralPage@@UEAAKXZ`
- size: `147`
- prototype: `unsigned int __fastcall(CConfigGeneralPage *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x180011510`
- `0x1800154ac`

## pseudocode

```c
__int64 __fastcall CConfigGeneralPage::OnHelp(CConfigGeneralPage *this)
{
  unsigned int v1; // eax
  unsigned int v2; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_f5b496eade1b3798203481970613ce29_Traceguids);
  }
  v1 = ShowHelp((OLECHAR *)L"mshelp://windows/?id=811d861e-177b-475d-a34e-72948adb7a06");
  v2 = v1;
  if ( v1
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_f5b496eade1b3798203481970613ce29_Traceguids, v1);
  }
  return v2;
}

```

## disassembly

```asm
0x180011510  mov     [rsp+arg_0], rbx
0x180011515  push    rsi
0x180011516  sub     rsp, 20h
0x18001151a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011521  lea     rsi, WPP_GLOBAL_Control
0x180011528  cmp     rcx, rsi
0x18001152b  jz      short loc_180011551
0x18001152d  test    dword ptr [rcx+1Ch], 100h
0x180011534  jz      short loc_180011551
0x180011536  cmp     byte ptr [rcx+19h], 5
0x18001153a  jb      short loc_180011551
0x18001153c  mov     rcx, [rcx+10h]
0x180011540  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180011547  mov     edx, 1Ah
0x18001154c  call    WPP_SF_
0x180011551  lea     rcx, psz; "mshelp://windows/?id=811d861e-177b-475d"...
0x180011558  call    ?ShowHelp@@YAKPEBG@Z; ShowHelp(ushort const *)
0x18001155d  mov     ebx, eax
0x18001155f  test    eax, eax
0x180011561  jz      short loc_180011596
0x180011563  mov     rcx, cs:WPP_GLOBAL_Control
0x18001156a  cmp     rcx, rsi
0x18001156d  jz      short loc_180011596
0x18001156f  test    dword ptr [rcx+1Ch], 100h
0x180011576  jz      short loc_180011596
0x180011578  cmp     byte ptr [rcx+19h], 2
0x18001157c  jb      short loc_180011596
0x18001157e  mov     rcx, [rcx+10h]
0x180011582  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180011589  mov     edx, 1Bh
0x18001158e  mov     r9d, eax
0x180011591  call    WPP_SF_d
0x180011596  mov     eax, ebx
0x180011598  mov     rbx, [rsp+28h+arg_0]
0x18001159d  add     rsp, 20h
0x1800115a1  pop     rsi
0x1800115a2  retn
```
