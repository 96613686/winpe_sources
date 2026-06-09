# CSoundSettingsDialog::OnCommand(HWND__ *,ushort,ushort,HWND__ *,int &)

- ea: `0x180012ce0`
- end: `0x180012e08`
- name: `?OnCommand@CSoundSettingsDialog@@UEAAKPEAUHWND__@@GG0AEAH@Z`
- size: `296`
- prototype: `unsigned int __usercall@<eax>(CSoundSettingsDialog *__hidden this@<rcx>, HWND@<rdx>, unsigned __int16@<r8w>, unsigned __int16@<r9w>, HWND, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000edb0`
- `0x180012ce0`
- `0x1800130d4`

## import_xrefs

- `USER32!EndDialog` at `0x180012df5`
- `USER32!EndDialog` at `0x180012df5`

## pseudocode

```c
__int64 __fastcall CSoundSettingsDialog::OnCommand(
        CSoundSettingsDialog *this,
        HWND a2,
        __int64 a3,
        unsigned __int16 a4,
        HWND a5,
        int *a6)
{
  int v6; // ebp
  unsigned int v9; // ebx
  INT_PTR v10; // rdx
  unsigned int v11; // eax

  v6 = a4;
  v9 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids);
  }
  *a6 = 1;
  if ( v6 != 1 )
  {
    if ( v6 != 2 )
    {
      *a6 = 0;
      return v9;
    }
    v10 = 2;
LABEL_17:
    EndDialog(a2, v10);
    return v9;
  }
  v11 = CSoundSettingsDialog::SaveSoundSettings(this, a2);
  v9 = v11;
  if ( !v11 )
  {
    v10 = 1;
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids, v11);
  }
  if ( v9 != 1003 )
    FaxMsgBox(a2, *((_QWORD *)this + 1), 4656);
  return v9;
}

```

## disassembly

```asm
0x180012ce0  push    rbx
0x180012ce2  push    rbp
0x180012ce3  push    rsi
0x180012ce4  push    rdi
0x180012ce5  push    r12
0x180012ce7  sub     rsp, 30h
0x180012ceb  movzx   ebp, r9w
0x180012cef  mov     rdi, rdx
0x180012cf2  mov     rsi, rcx
0x180012cf5  xor     ebx, ebx
0x180012cf7  mov     rcx, cs:WPP_GLOBAL_Control
0x180012cfe  lea     r12, WPP_GLOBAL_Control
0x180012d05  cmp     rcx, r12
0x180012d08  jz      short loc_180012D2C
0x180012d0a  test    dword ptr [rcx+1Ch], 100h
0x180012d11  jz      short loc_180012D2C
0x180012d13  cmp     byte ptr [rcx+19h], 5
0x180012d17  jb      short loc_180012D2C
0x180012d19  mov     rcx, [rcx+10h]
0x180012d1d  lea     edx, [rbx+14h]
0x180012d20  lea     r8, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids
0x180012d27  call    WPP_SF_
0x180012d2c  mov     rdx, [rsp+58h+arg_28]
0x180012d34  mov     ecx, ebp
0x180012d36  mov     dword ptr [rdx], 1
0x180012d3c  sub     ecx, 1
0x180012d3f  jz      short loc_180012D57
0x180012d41  cmp     ecx, 1
0x180012d44  jz      short loc_180012D4D
0x180012d46  mov     [rdx], ebx
0x180012d48  jmp     loc_180012DFB
0x180012d4d  mov     edx, 2
0x180012d52  jmp     loc_180012DF2
0x180012d57  mov     rdx, rdi; HWND
0x180012d5a  mov     rcx, rsi; this
0x180012d5d  call    ?SaveSoundSettings@CSoundSettingsDialog@@AEAAKPEAUHWND__@@@Z; CSoundSettingsDialog::SaveSoundSettings(HWND__ *)
0x180012d62  mov     ebx, eax
0x180012d64  test    eax, eax
0x180012d66  jz      loc_180012DED
0x180012d6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d73  cmp     rcx, r12
0x180012d76  jz      short loc_180012D9F
0x180012d78  test    dword ptr [rcx+1Ch], 100h
0x180012d7f  jz      short loc_180012D9F
0x180012d81  cmp     byte ptr [rcx+19h], 2
0x180012d85  jb      short loc_180012D9F
0x180012d87  mov     rcx, [rcx+10h]
0x180012d8b  lea     r8, WPP_b0c54980ff523b2dce304010425a5b8e_Traceguids
0x180012d92  mov     edx, 15h
0x180012d97  mov     r9d, eax
0x180012d9a  call    WPP_SF_d
0x180012d9f  cmp     ebx, 3EBh
0x180012da5  jz      short loc_180012DFB
0x180012da7  cmp     ebx, 5
0x180012daa  jz      short loc_180012DCB
0x180012dac  cmp     ebx, 8
0x180012daf  jz      short loc_180012DC3
0x180012db1  mov     eax, 1236h
0x180012db6  cmp     ebx, 7Ah ; 'z'
0x180012db9  lea     r9d, [rax-2]
0x180012dbd  cmovnz  r9d, eax
0x180012dc1  jmp     short loc_180012DD1
0x180012dc3  mov     r9d, 1237h
0x180012dc9  jmp     short loc_180012DD1
0x180012dcb  mov     r9d, 1235h
0x180012dd1  mov     rdx, [rsi+8]
0x180012dd5  mov     r8d, 1230h
0x180012ddb  mov     rcx, rdi
0x180012dde  mov     [rsp+58h+var_38], 10h
0x180012de6  call    FaxMsgBox
0x180012deb  jmp     short loc_180012DFB
0x180012ded  mov     edx, 1; nResult
0x180012df2  mov     rcx, rdi; hDlg
0x180012df5  call    cs:__imp_EndDialog
0x180012dfb  mov     eax, ebx
0x180012dfd  add     rsp, 30h
0x180012e01  pop     r12
0x180012e03  pop     rdi
0x180012e04  pop     rsi
0x180012e05  pop     rbp
0x180012e06  pop     rbx
0x180012e07  retn
```
