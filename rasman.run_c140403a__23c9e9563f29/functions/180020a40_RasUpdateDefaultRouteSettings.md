# RasUpdateDefaultRouteSettings

- ea: `0x180020a40`
- end: `0x180020b1b`
- name: `RasUpdateDefaultRouteSettings`
- size: `219`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callees

- `0x180002f80`
- `0x180020a40`
- `0x180021000`
- `0x180021040`

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
0x180020a40  push    rbx
0x180020a42  push    rbp
0x180020a43  push    rsi
0x180020a44  push    rdi
0x180020a45  push    r15
0x180020a47  sub     rsp, 40h
0x180020a4b  movzx   edi, r9b
0x180020a4f  mov     rbx, r8
0x180020a52  movzx   esi, dl
0x180020a55  movzx   ebp, cl
0x180020a58  mov     rcx, cs:WPP_GLOBAL_Control
0x180020a5f  lea     r15, WPP_GLOBAL_Control
0x180020a66  cmp     rcx, r15
0x180020a69  jz      short loc_180020A92
0x180020a6b  test    byte ptr [rcx+1Ch], 40h
0x180020a6f  jz      short loc_180020A92
0x180020a71  cmp     byte ptr [rcx+19h], 6
0x180020a75  jb      short loc_180020A92
0x180020a77  mov     rcx, [rcx+10h]
0x180020a7b  mov     r9, rbx
0x180020a7e  mov     [rsp+68h+var_38], dil
0x180020a83  mov     [rsp+68h+var_40], sil
0x180020a88  mov     byte ptr [rsp+68h+var_48], bpl
0x180020a8d  call    WPP_SF_Iccc
0x180020a92  mov     r8d, esi
0x180020a95  mov     dword ptr [rsp+68h+var_48], edi
0x180020a99  mov     edx, ebp
0x180020a9b  mov     ecx, 7Fh
0x180020aa0  mov     r9, rbx
0x180020aa3  call    SubmitLocalRequest
0x180020aa8  mov     ebx, eax
0x180020aaa  test    eax, eax
0x180020aac  jz      short loc_180020ADE
0x180020aae  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ab5  cmp     rcx, r15
0x180020ab8  jz      short loc_180020B0E
0x180020aba  test    byte ptr [rcx+1Ch], 40h
0x180020abe  jz      short loc_180020AE5
0x180020ac0  cmp     byte ptr [rcx+19h], 2
0x180020ac4  jb      short loc_180020AE5
0x180020ac6  mov     rcx, [rcx+10h]
0x180020aca  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020ad1  mov     edx, 25Ch
0x180020ad6  mov     r9d, eax
0x180020ad9  call    WPP_SF_d
0x180020ade  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ae5  cmp     rcx, r15
0x180020ae8  jz      short loc_180020B0E
0x180020aea  test    byte ptr [rcx+1Ch], 40h
0x180020aee  jz      short loc_180020B0E
0x180020af0  cmp     byte ptr [rcx+19h], 6
0x180020af4  jb      short loc_180020B0E
0x180020af6  mov     rcx, [rcx+10h]
0x180020afa  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020b01  mov     edx, 25Dh
0x180020b06  mov     r9d, ebx
0x180020b09  call    WPP_SF_d
0x180020b0e  mov     eax, ebx
0x180020b10  add     rsp, 40h
0x180020b14  pop     r15
0x180020b16  pop     rdi
0x180020b17  pop     rsi
0x180020b18  pop     rbp
0x180020b19  pop     rbx
0x180020b1a  retn
```
