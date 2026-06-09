# LsaIfIsDcTargetForRecovery(_LUID *,ushort const *,int *)

- ea: `0x18000c010`
- end: `0x18000c1ad`
- name: `?LsaIfIsDcTargetForRecovery@@YAJPEAU_LUID@@PEBGPEAH@Z`
- size: `413`
- prototype: `__int64 __fastcall(struct _LUID *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002677c`

## callees

- `0x180007f10`
- `0x18000c010`
- `0x18000c1b4`
- `0x18001d810`
- `0x18001eb8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18000c053`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18000c053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c068`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c114`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c114`

## string_xrefs

- `0x18000c0ba`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`
- `0x18000c175`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keybckup.cpp`

## pseudocode

```c
__int64 __fastcall LsaIfIsDcTargetForRecovery(struct _LUID *a1, const unsigned __int16 *a2, int *a3)
{
  unsigned int DcMutexName; // eax
  int v5; // edx
  unsigned int v6; // ebx
  HANDLE v7; // rax
  DWORD LastError; // eax
  __int64 v9; // rcx
  __int64 v11; // rcx
  WCHAR Name[72]; // [rsp+40h] [rbp-B8h] BYREF

  *a3 = 0;
  DcMutexName = GetDcMutexName(a1, a2, (__int64)a3, Name);
  v6 = DcMutexName;
  if ( DcMutexName )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v5,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwRetVal",
        DcMutexName,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp",
        102);
      v11 = WPP_GLOBAL_Control;
    }
    if ( (int)v6 > 0 )
      v6 = (unsigned __int16)v6 | 0xC0070000;
    if ( (_UNKNOWN *)v11 != &WPP_GLOBAL_Control && (*(_BYTE *)(v11 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v11 + 16),
        v5,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"status",
        v6,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp",
        104);
  }
  else
  {
    v7 = OpenMutexW(0x20000u, 0, Name);
    if ( v7 )
    {
      *a3 = 1;
      v6 = 0;
      CloseHandle(v7);
    }
    else
    {
      LastError = GetLastError();
      v9 = 0;
      if ( LastError != 2 )
        v9 = LastError;
      if ( (int)v9 > 0 )
        v6 = (unsigned __int16)v9 | 0xC0070000;
      else
        v6 = v9;
      if ( (_DWORD)v9 )
      {
        DebugTraceError(v9, "dwRetVal", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 2942);
        DebugTraceError(v6, "status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keybckup.cpp", 2943);
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000c010  push    rbx
0x18000c012  push    rsi
0x18000c013  push    rdi
0x18000c014  sub     rsp, 0E0h
0x18000c01b  mov     rax, cs:__security_cookie
0x18000c022  xor     rax, rsp
0x18000c025  mov     [rsp+0F8h+var_28], rax
0x18000c02d  lea     r9, [rsp+0F8h+Name]; unsigned __int16 *
0x18000c032  mov     dword ptr [r8], 0
0x18000c039  mov     rdi, r8
0x18000c03c  call    ?GetDcMutexName@@YAKPEAU_LUID@@PEBGKPEAG@Z; GetDcMutexName(_LUID *,ushort const *,ulong,ushort *)
0x18000c041  mov     ebx, eax
0x18000c043  test    eax, eax
0x18000c045  jnz     short loc_18000C0AC
0x18000c047  lea     r8, [rsp+0F8h+Name]; lpName
0x18000c04c  xor     edx, edx; bInheritHandle
0x18000c04e  mov     ecx, 20000h; dwDesiredAccess
0x18000c053  call    cs:__imp_OpenMutexW
0x18000c05a  nop     dword ptr [rax+rax+00h]
0x18000c05f  test    rax, rax
0x18000c062  jnz     loc_18000C109
0x18000c068  call    cs:__imp_GetLastError
0x18000c06f  nop     dword ptr [rax+rax+00h]
0x18000c074  xor     ecx, ecx
0x18000c076  cmp     eax, 2
0x18000c079  cmovnz  ecx, eax
0x18000c07c  test    ecx, ecx
0x18000c07e  jg      loc_18000C125
0x18000c084  mov     ebx, ecx
0x18000c086  test    ecx, ecx
0x18000c088  jnz     loc_18000C175
0x18000c08e  mov     eax, ebx
0x18000c090  mov     rcx, [rsp+0F8h+var_28]
0x18000c098  xor     rcx, rsp; StackCookie
0x18000c09b  call    __security_check_cookie
0x18000c0a0  add     rsp, 0E0h
0x18000c0a7  pop     rdi
0x18000c0a8  pop     rsi
0x18000c0a9  pop     rbx
0x18000c0aa  retn
0x18000c0ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0b3  lea     rsi, WPP_GLOBAL_Control
0x18000c0ba  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000c0c1  cmp     rcx, rsi
0x18000c0c4  jz      short loc_18000C0CC
0x18000c0c6  test    byte ptr [rcx+1Ch], 1
0x18000c0ca  jnz     short loc_18000C133
0x18000c0cc  test    ebx, ebx
0x18000c0ce  jg      loc_18000C167
0x18000c0d4  cmp     rcx, rsi
0x18000c0d7  jz      short loc_18000C08E
0x18000c0d9  test    byte ptr [rcx+1Ch], 1
0x18000c0dd  jz      short loc_18000C08E
0x18000c0df  mov     rcx, [rcx+10h]
0x18000c0e3  lea     r9, aStatus_0; "status"
0x18000c0ea  mov     [rsp+0F8h+var_C8], 0B68h
0x18000c0f2  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000c0f9  mov     [rsp+0F8h+var_D0], rdi
0x18000c0fe  mov     [rsp+0F8h+var_D8], ebx
0x18000c102  call    WPP_SF_sDsd
0x18000c107  jmp     short loc_18000C08E
0x18000c109  mov     dword ptr [rdi], 1
0x18000c10f  xor     ebx, ebx
0x18000c111  mov     rcx, rax; hObject
0x18000c114  call    cs:__imp_CloseHandle
0x18000c11b  nop     dword ptr [rax+rax+00h]
0x18000c120  jmp     loc_18000C08E
0x18000c125  movzx   ebx, cx
0x18000c128  or      ebx, 0C0070000h
0x18000c12e  jmp     loc_18000C086
0x18000c133  mov     rcx, [rcx+10h]
0x18000c137  lea     r9, aDwretval; "dwRetVal"
0x18000c13e  mov     [rsp+0F8h+var_C8], 0B66h
0x18000c146  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000c14d  mov     [rsp+0F8h+var_D0], rdi
0x18000c152  mov     [rsp+0F8h+var_D8], ebx
0x18000c156  call    WPP_SF_sDsd
0x18000c15b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c162  jmp     loc_18000C0CC
0x18000c167  movzx   ebx, bx
0x18000c16a  or      ebx, 0C0070000h
0x18000c170  jmp     loc_18000C0D4
0x18000c175  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000c17c  mov     r9d, 0B7Eh
0x18000c182  mov     r8, rdi
0x18000c185  lea     rdx, aDwretval; "dwRetVal"
0x18000c18c  call    DebugTraceError
0x18000c191  mov     r9d, 0B7Fh
0x18000c197  lea     rdx, aStatus_0; "status"
0x18000c19e  mov     r8, rdi
0x18000c1a1  mov     ecx, ebx
0x18000c1a3  call    DebugTraceError
0x18000c1a8  jmp     loc_18000C08E
```
