# SetQoSPoliciesOnLink

- ea: `0x140011850`
- end: `0x140011939`
- name: `SetQoSPoliciesOnLink`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140026c80`

## callees

- `0x14000a2c0`
- `0x140011064`
- `0x140011780`
- `0x140011850`

## pseudocode

```c
__int64 __fastcall SetQoSPoliciesOnLink(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  int v4; // eax
  __int64 v5; // rcx
  __int64 v7; // rax
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx

  if ( *(_DWORD *)(a2 + 1656) > 2u )
    return (unsigned int)-1073741811;
  v4 = *(_DWORD *)(a2 + 1048);
  v5 = *(_QWORD *)(a1 + 48);
  if ( !v4 )
  {
    if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)(v5 + 72) + 124LL) - 13) > 1 )
      return 0;
    goto LABEL_9;
  }
  if ( v4 != 2 )
    return 0;
  v7 = *(_QWORD *)(v5 + 72);
  if ( *(_DWORD *)(v7 + 124) == 15 )
  {
LABEL_9:
    v3 = ApplyQoSPoliciesOnLink(a1, (_DWORD *)(a2 + 1656));
    if ( v3 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v9 = 11;
LABEL_14:
        WPP_SF_d(v8->AttachedDevice, v9, WPP_8149dd890ba53a7fe788edfac8207806_Traceguids, v3);
        return v3;
      }
    }
    return v3;
  }
  v3 = 0;
  if ( *(_DWORD *)(v7 + 124) == 14 )
  {
    v3 = SendQoSPoliciesToMiniport(a1);
    if ( v3 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v9 = 12;
        goto LABEL_14;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x140011850  push    rbx
0x140011852  sub     rsp, 20h
0x140011856  lea     r9, [rdx+678h]
0x14001185d  mov     r8, rcx
0x140011860  cmp     dword ptr [r9], 2
0x140011864  jbe     short loc_14001186D
0x140011866  mov     ebx, 0C000000Dh
0x14001186b  jmp     short loc_14001188C
0x14001186d  mov     eax, [rdx+418h]
0x140011873  mov     rcx, [rcx+30h]
0x140011877  test    eax, eax
0x140011879  jnz     short loc_140011895
0x14001187b  mov     rax, [rcx+48h]
0x14001187f  mov     ecx, [rax+7Ch]
0x140011882  sub     ecx, 0Dh
0x140011885  cmp     ecx, 1
0x140011888  jbe     short loc_1400118A4
0x14001188a  xor     ebx, ebx
0x14001188c  mov     eax, ebx
0x14001188e  add     rsp, 20h
0x140011892  pop     rbx
0x140011893  retn
0x140011895  cmp     eax, 2
0x140011898  jnz     short loc_14001188A
0x14001189a  mov     rax, [rcx+48h]
0x14001189e  cmp     dword ptr [rax+7Ch], 0Fh
0x1400118a2  jnz     short loc_1400118F0
0x1400118a4  mov     rdx, r9
0x1400118a7  mov     rcx, r8
0x1400118aa  call    ApplyQoSPoliciesOnLink
0x1400118af  mov     ebx, eax
0x1400118b1  test    eax, eax
0x1400118b3  jz      short loc_14001188C
0x1400118b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400118bc  lea     rax, WPP_GLOBAL_Control
0x1400118c3  cmp     rcx, rax
0x1400118c6  jz      short loc_14001188C
0x1400118c8  mov     edx, [rcx+2Ch]
0x1400118cb  test    dl, 20h
0x1400118ce  jz      short loc_14001188C
0x1400118d0  cmp     byte ptr [rcx+29h], 3
0x1400118d4  jb      short loc_14001188C
0x1400118d6  mov     edx, 0Bh
0x1400118db  mov     rcx, [rcx+18h]
0x1400118df  lea     r8, WPP_8149dd890ba53a7fe788edfac8207806_Traceguids
0x1400118e6  mov     r9d, ebx
0x1400118e9  call    WPP_SF_d
0x1400118ee  jmp     short loc_14001188C
0x1400118f0  xor     ebx, ebx
0x1400118f2  cmp     dword ptr [rax+7Ch], 0Eh
0x1400118f6  jnz     short loc_14001188C
0x1400118f8  mov     rcx, r8
0x1400118fb  call    SendQoSPoliciesToMiniport
0x140011900  mov     ebx, eax
0x140011902  test    eax, eax
0x140011904  jz      short loc_14001188C
0x140011906  mov     rcx, cs:WPP_GLOBAL_Control
0x14001190d  lea     rax, WPP_GLOBAL_Control
0x140011914  cmp     rcx, rax
0x140011917  jz      loc_14001188C
0x14001191d  mov     eax, [rcx+2Ch]
0x140011920  test    al, 20h
0x140011922  jz      loc_14001188C
0x140011928  cmp     byte ptr [rcx+29h], 3
0x14001192c  jb      loc_14001188C
0x140011932  mov     edx, 0Ch
0x140011937  jmp     short loc_1400118DB
```
