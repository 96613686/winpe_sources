# RasUpdateDefaultRouteSettings

- ea: `0x180021530`
- end: `0x18002160c`
- name: `RasUpdateDefaultRouteSettings`
- size: `220`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x1800030d0`
- `0x180021530`
- `0x180021b14`
- `0x180021b58`

## pseudocode

```c
__int64 __fastcall RasUpdateDefaultRouteSettings(unsigned __int8 a1, __int64 a2, __int64 a3, unsigned __int8 a4)
{
  int v4; // edi
  unsigned int v6; // esi
  unsigned int v7; // ebp
  unsigned int v8; // eax
  unsigned int v9; // ebx
  PVOID *v10; // rcx
  __int64 v12; // [rsp+20h] [rbp-48h]

  v4 = a4;
  v6 = (unsigned __int8)a2;
  v7 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_Iccc(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a3, a1, (_BYTE)a2, a4);
  }
  LODWORD(v12) = v4;
  v8 = SubmitLocalRequest(0x7Fu, v7, v6, a3, v12);
  v9 = v8;
  if ( !v8 )
    goto LABEL_10;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 604, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v8);
LABEL_10:
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 605, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x180021530  push    rbx
0x180021532  push    rbp
0x180021533  push    rsi
0x180021534  push    rdi
0x180021535  push    r15
0x180021537  sub     rsp, 40h
0x18002153b  movzx   edi, r9b
0x18002153f  mov     rbx, r8
0x180021542  movzx   esi, dl
0x180021545  movzx   ebp, cl
0x180021548  mov     rcx, cs:WPP_GLOBAL_Control
0x18002154f  lea     r15, WPP_GLOBAL_Control
0x180021556  cmp     rcx, r15
0x180021559  jz      short loc_180021582
0x18002155b  test    byte ptr [rcx+1Ch], 40h
0x18002155f  jz      short loc_180021582
0x180021561  cmp     byte ptr [rcx+19h], 6
0x180021565  jb      short loc_180021582
0x180021567  mov     rcx, [rcx+10h]
0x18002156b  mov     r9, rbx
0x18002156e  mov     [rsp+68h+var_38], dil
0x180021573  mov     [rsp+68h+var_40], sil
0x180021578  mov     byte ptr [rsp+68h+var_48], bpl
0x18002157d  call    WPP_SF_Iccc
0x180021582  mov     r8d, esi
0x180021585  mov     dword ptr [rsp+68h+var_48], edi
0x180021589  mov     edx, ebp
0x18002158b  mov     ecx, 7Fh
0x180021590  mov     r9, rbx
0x180021593  call    SubmitLocalRequest
0x180021598  mov     ebx, eax
0x18002159a  test    eax, eax
0x18002159c  jz      short loc_1800215CE
0x18002159e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215a5  cmp     rcx, r15
0x1800215a8  jz      short loc_1800215FE
0x1800215aa  test    byte ptr [rcx+1Ch], 40h
0x1800215ae  jz      short loc_1800215D5
0x1800215b0  cmp     byte ptr [rcx+19h], 2
0x1800215b4  jb      short loc_1800215D5
0x1800215b6  mov     rcx, [rcx+10h]
0x1800215ba  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800215c1  mov     edx, 25Ch
0x1800215c6  mov     r9d, eax
0x1800215c9  call    WPP_SF_d
0x1800215ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215d5  cmp     rcx, r15
0x1800215d8  jz      short loc_1800215FE
0x1800215da  test    byte ptr [rcx+1Ch], 40h
0x1800215de  jz      short loc_1800215FE
0x1800215e0  cmp     byte ptr [rcx+19h], 6
0x1800215e4  jb      short loc_1800215FE
0x1800215e6  mov     rcx, [rcx+10h]
0x1800215ea  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800215f1  mov     edx, 25Dh
0x1800215f6  mov     r9d, ebx
0x1800215f9  call    WPP_SF_d
0x1800215fe  mov     eax, ebx
0x180021600  add     rsp, 40h
0x180021604  pop     r15
0x180021606  pop     rdi
0x180021607  pop     rsi
0x180021608  pop     rbp
0x180021609  pop     rbx
0x18002160a  retn
```
