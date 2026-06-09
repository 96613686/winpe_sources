# CreateFaxSecurityPage(void *,HINSTANCE__ *)

- ea: `0x180013b44`
- end: `0x180013c75`
- name: `?CreateFaxSecurityPage@@YAPEAU_PSP@@PEAXPEAUHINSTANCE__@@@Z`
- size: `305`
- prototype: `struct _PSP *__fastcall(void *, HINSTANCE)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fd8c`

## callees

- `0x180001284`
- `0x180005eac`
- `0x180005ed4`
- `0x180013b44`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180013c3f`
- `KERNEL32!SetLastError` at `0x180013c3f`
- `KERNEL32!GetLastError` at `0x180013bf9`
- `KERNEL32!GetLastError` at `0x180013bf9`
- `ACLUI!__imp_CreateSecurityPage` at `0x180013bd0`
- `ACLUI!__imp_CreateSecurityPage` at `0x180013bd0`

## pseudocode

```c
HPROPSHEETPAGE __fastcall CreateFaxSecurityPage(
        struct ISecurityInformationVtbl *a1,
        struct ISecurityInformationVtbl *a2)
{
  LPSECURITYINFO v4; // rax
  HPROPSHEETPAGE SecurityPage; // rbx
  DWORD LastError; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids);
  }
  v4 = g_pFaxSecurity;
  if ( g_pFaxSecurity )
    goto LABEL_8;
  v4 = (LPSECURITYINFO)operator new(0x20u);
  if ( v4 )
  {
    v4[1].lpVtbl = a1;
    v4->lpVtbl = (struct ISecurityInformationVtbl *)&CFaxSecurity::`vftable';
    v4[2].lpVtbl = a2;
    LODWORD(v4[3].lpVtbl) = 1;
    g_pFaxSecurity = v4;
LABEL_8:
    SecurityPage = CreateSecurityPage(v4);
    if ( !SecurityPage
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids, LastError);
    }
    return SecurityPage;
  }
  SecurityPage = 0;
  g_pFaxSecurity = 0;
  SetLastError(8u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids);
  }
  return SecurityPage;
}

```

## disassembly

```asm
0x180013b44  mov     [rsp+arg_0], rbx
0x180013b49  mov     [rsp+arg_8], rbp
0x180013b4e  push    rdi
0x180013b4f  sub     rsp, 20h
0x180013b53  mov     rbx, rdx
0x180013b56  mov     rdi, rcx
0x180013b59  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b60  lea     rbp, WPP_GLOBAL_Control
0x180013b67  cmp     rcx, rbp
0x180013b6a  jz      short loc_180013B90
0x180013b6c  test    dword ptr [rcx+1Ch], 100h
0x180013b73  jz      short loc_180013B90
0x180013b75  cmp     byte ptr [rcx+19h], 5
0x180013b79  jb      short loc_180013B90
0x180013b7b  mov     rcx, [rcx+10h]
0x180013b7f  lea     r8, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids
0x180013b86  mov     edx, 18h
0x180013b8b  call    WPP_SF_
0x180013b90  mov     rax, cs:?g_pFaxSecurity@@3PEAVCFaxSecurity@@EA; CFaxSecurity * g_pFaxSecurity
0x180013b97  test    rax, rax
0x180013b9a  jnz     short loc_180013BCD
0x180013b9c  lea     ecx, [rax+20h]; Size
0x180013b9f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013ba4  test    rax, rax
0x180013ba7  jz      loc_180013C2F
0x180013bad  lea     rcx, ??_7CFaxSecurity@@6B@; const CFaxSecurity::`vftable'
0x180013bb4  mov     [rax+8], rdi
0x180013bb8  mov     [rax], rcx
0x180013bbb  mov     [rax+10h], rbx
0x180013bbf  mov     dword ptr [rax+18h], 1
0x180013bc6  mov     cs:?g_pFaxSecurity@@3PEAVCFaxSecurity@@EA, rax; CFaxSecurity * g_pFaxSecurity
0x180013bcd  mov     rcx, rax; psi
0x180013bd0  call    cs:__imp_CreateSecurityPage
0x180013bd6  mov     rbx, rax
0x180013bd9  test    rax, rax
0x180013bdc  jnz     short loc_180013C1C
0x180013bde  mov     rcx, cs:WPP_GLOBAL_Control
0x180013be5  cmp     rcx, rbp
0x180013be8  jz      short loc_180013C1C
0x180013bea  test    dword ptr [rcx+1Ch], 100h
0x180013bf1  jz      short loc_180013C1C
0x180013bf3  cmp     byte ptr [rcx+19h], 2
0x180013bf7  jb      short loc_180013C1C
0x180013bf9  call    cs:__imp_GetLastError
0x180013bff  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c06  lea     edx, [rbx+1Ah]
0x180013c09  mov     r9d, eax
0x180013c0c  lea     r8, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids
0x180013c13  mov     rcx, [rcx+10h]
0x180013c17  call    WPP_SF_d
0x180013c1c  mov     rbp, [rsp+28h+arg_8]
0x180013c21  mov     rax, rbx
0x180013c24  mov     rbx, [rsp+28h+arg_0]
0x180013c29  add     rsp, 20h
0x180013c2d  pop     rdi
0x180013c2e  retn
0x180013c2f  xor     ebx, ebx
0x180013c31  mov     cs:?g_pFaxSecurity@@3PEAVCFaxSecurity@@EA, 0; CFaxSecurity * g_pFaxSecurity
0x180013c3c  lea     ecx, [rbx+8]; dwErrCode
0x180013c3f  call    cs:__imp_SetLastError
0x180013c45  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c4c  cmp     rcx, rbp
0x180013c4f  jz      short loc_180013C1C
0x180013c51  test    dword ptr [rcx+1Ch], 100h
0x180013c58  jz      short loc_180013C1C
0x180013c5a  cmp     byte ptr [rcx+19h], 2
0x180013c5e  jb      short loc_180013C1C
0x180013c60  mov     rcx, [rcx+10h]
0x180013c64  lea     edx, [rbx+19h]
0x180013c67  lea     r8, WPP_1fc9d9685e7d345d59657ab86e202994_Traceguids
0x180013c6e  call    WPP_SF_
0x180013c73  jmp     short loc_180013C1C
```
