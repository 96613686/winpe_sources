# CConfigTrackingPage::OnHelp(void)

- ea: `0x180012e10`
- end: `0x180012ea3`
- name: `?OnHelp@CConfigTrackingPage@@UEAAKXZ`
- size: `147`
- prototype: `unsigned int __fastcall(CConfigTrackingPage *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x180012e10`
- `0x1800154ac`

## pseudocode

```c
__int64 __fastcall CConfigTrackingPage::OnHelp(CConfigTrackingPage *this)
{
  unsigned int v1; // eax
  unsigned int v2; // ebx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids);
  }
  v1 = ShowHelp((OLECHAR *)L"mshelp://windows/?id=f69cf803-19a5-43d8-bfe9-a2c963bf35de");
  v2 = v1;
  if ( v1
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids, v1);
  }
  return v2;
}

```

## disassembly

```asm
0x180012e10  mov     [rsp+arg_0], rbx
0x180012e15  push    rsi
0x180012e16  sub     rsp, 20h
0x180012e1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e21  lea     rsi, WPP_GLOBAL_Control
0x180012e28  cmp     rcx, rsi
0x180012e2b  jz      short loc_180012E51
0x180012e2d  test    dword ptr [rcx+1Ch], 100h
0x180012e34  jz      short loc_180012E51
0x180012e36  cmp     byte ptr [rcx+19h], 5
0x180012e3a  jb      short loc_180012E51
0x180012e3c  mov     rcx, [rcx+10h]
0x180012e40  lea     r8, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids
0x180012e47  mov     edx, 12h
0x180012e4c  call    WPP_SF_
0x180012e51  lea     rcx, aMshelpWindowsI; "mshelp://windows/?id=f69cf803-19a5-43d8"...
0x180012e58  call    ?ShowHelp@@YAKPEBG@Z; ShowHelp(ushort const *)
0x180012e5d  mov     ebx, eax
0x180012e5f  test    eax, eax
0x180012e61  jz      short loc_180012E96
0x180012e63  mov     rcx, cs:WPP_GLOBAL_Control
0x180012e6a  cmp     rcx, rsi
0x180012e6d  jz      short loc_180012E96
0x180012e6f  test    dword ptr [rcx+1Ch], 100h
0x180012e76  jz      short loc_180012E96
0x180012e78  cmp     byte ptr [rcx+19h], 2
0x180012e7c  jb      short loc_180012E96
0x180012e7e  mov     rcx, [rcx+10h]
0x180012e82  lea     r8, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids
0x180012e89  mov     edx, 13h
0x180012e8e  mov     r9d, eax
0x180012e91  call    WPP_SF_d
0x180012e96  mov     eax, ebx
0x180012e98  mov     rbx, [rsp+28h+arg_0]
0x180012e9d  add     rsp, 20h
0x180012ea1  pop     rsi
0x180012ea2  retn
```
