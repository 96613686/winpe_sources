# CBackupSession::SetBackupLimit(unsigned __int64)

- ea: `0x180021bc0`
- end: `0x180021d89`
- name: `?SetBackupLimit@CBackupSession@@UEAAJ_K@Z`
- size: `457`
- prototype: `__int64 __fastcall(CBackupSession *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800077f0`
- `0x180007818`
- `0x18001622c`
- `0x180016aec`
- `0x180021bc0`
- `0x18002204c`
- `0x180022558`
- `0x180031680`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180021cc5`
- `ADVAPI32!SetThreadToken` at `0x180021d1b`
- `ADVAPI32!SetThreadToken` at `0x180021cc5`
- `ADVAPI32!SetThreadToken` at `0x180021d1b`
- `KERNEL32!GetLastError` at `0x180021cd4`
- `KERNEL32!GetLastError` at `0x180021d37`
- `KERNEL32!GetLastError` at `0x180021cd4`
- `KERNEL32!GetLastError` at `0x180021d37`

## pseudocode

```c
__int64 __fastcall CBackupSession::SetBackupLimit(CBackupSession *this, __int64 a2, __int64 a3)
{
  PVOID v5; // rcx
  signed int LastError; // eax
  signed int v7; // eax
  __int64 v9; // [rsp+30h] [rbp-58h] BYREF
  __int64 v10; // [rsp+38h] [rbp-50h] BYREF
  char v11[16]; // [rsp+40h] [rbp-48h] BYREF
  __int64 *v12; // [rsp+50h] [rbp-38h]
  __int64 v13; // [rsp+58h] [rbp-30h]
  __int64 *v14; // [rsp+60h] [rbp-28h]
  __int64 v15; // [rsp+68h] [rbp-20h]

  if ( a2 == -1 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids);
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, a3, a2);
  }
  if ( (Microsoft_Windows_FileHistory_EngineEnableBits & 1) != 0 )
  {
    v9 = *((_QWORD *)this + 54);
    v10 = a2;
    v12 = &v9;
    v14 = &v10;
    v13 = 8;
    v15 = 8;
    McGenEventWrite_EventWriteTransfer(v5, BackupSizeQuotaChangeInfo, a3, 3, v11);
  }
  _InterlockedExchange64((volatile __int64 *)this + 54, a2);
  *((_DWORD *)this + 110) = 0;
  CBackupSession::CalculateTransferQuotas(this, 0);
  if ( SetThreadToken(0, *((HANDLE *)this + 48)) )
  {
    CBackupSession::CalculateRetentionThresholds(this);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        77,
        &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
        (unsigned int)LastError);
  }
  if ( !SetThreadToken(0, 0)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = GetLastError();
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      78,
      &WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids,
      (unsigned int)v7);
  }
  return 0;
}

```

## disassembly

```asm
0x180021bc0  mov     [rsp+arg_10], rbx
0x180021bc5  mov     [rsp+arg_18], rsi
0x180021bca  push    rdi
0x180021bcb  sub     rsp, 80h
0x180021bd2  mov     rax, cs:__security_cookie
0x180021bd9  xor     rax, rsp
0x180021bdc  mov     [rsp+88h+var_18], rax
0x180021be1  mov     rsi, rdx
0x180021be4  mov     rdi, rcx
0x180021be7  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180021beb  jnz     short loc_180021C1B
0x180021bed  mov     rcx, cs:WPP_GLOBAL_Control
0x180021bf4  lea     rbx, WPP_GLOBAL_Control
0x180021bfb  cmp     rcx, rbx
0x180021bfe  jz      short loc_180021C45
0x180021c00  test    byte ptr [rcx+1Ch], 8
0x180021c04  jz      short loc_180021C45
0x180021c06  mov     rcx, [rcx+10h]
0x180021c0a  lea     edx, [rsi+4Ch]
0x180021c0d  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180021c14  call    WPP_SF_
0x180021c19  jmp     short loc_180021C45
0x180021c1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c22  lea     rbx, WPP_GLOBAL_Control
0x180021c29  cmp     rcx, rbx
0x180021c2c  jz      short loc_180021C45
0x180021c2e  test    byte ptr [rcx+1Ch], 8
0x180021c32  jz      short loc_180021C45
0x180021c34  mov     rcx, [rcx+10h]
0x180021c38  mov     edx, 4Ch ; 'L'
0x180021c3d  mov     r9, rsi
0x180021c40  call    WPP_SF_i
0x180021c45  test    cs:Microsoft_Windows_FileHistory_EngineEnableBits, 1
0x180021c4c  jz      short loc_180021CA1
0x180021c4e  mov     rax, [rdi+1B0h]
0x180021c55  lea     rdx, BackupSizeQuotaChangeInfo
0x180021c5c  mov     [rsp+88h+var_58], rax
0x180021c61  mov     r9d, 3
0x180021c67  lea     rax, [rsp+88h+var_58]
0x180021c6c  mov     [rsp+88h+var_50], rsi
0x180021c71  mov     [rsp+88h+var_38], rax
0x180021c76  lea     rax, [rsp+88h+var_50]
0x180021c7b  mov     [rsp+88h+var_28], rax
0x180021c80  lea     rax, [rsp+88h+var_48]
0x180021c85  mov     [rsp+88h+var_68], rax
0x180021c8a  mov     [rsp+88h+var_30], 8
0x180021c93  mov     [rsp+88h+var_20], 8
0x180021c9c  call    McGenEventWrite_EventWriteTransfer
0x180021ca1  xchg    rsi, [rdi+1B0h]
0x180021ca8  xor     edx, edx; int
0x180021caa  mov     dword ptr [rdi+1B8h], 0
0x180021cb4  mov     rcx, rdi; this
0x180021cb7  call    ?CalculateTransferQuotas@CBackupSession@@AEAAXH@Z; CBackupSession::CalculateTransferQuotas(int)
0x180021cbc  mov     rdx, [rdi+180h]; Token
0x180021cc3  xor     ecx, ecx; Thread
0x180021cc5  call    cs:__imp_SetThreadToken
0x180021ccb  mov     esi, 80070000h
0x180021cd0  test    eax, eax
0x180021cd2  jnz     short loc_180021D0F
0x180021cd4  call    cs:__imp_GetLastError
0x180021cda  test    eax, eax
0x180021cdc  jle     short loc_180021CE3
0x180021cde  movzx   eax, ax
0x180021ce1  or      eax, esi
0x180021ce3  mov     rcx, cs:WPP_GLOBAL_Control
0x180021cea  cmp     rcx, rbx
0x180021ced  jz      short loc_180021D17
0x180021cef  test    byte ptr [rcx+1Ch], 1
0x180021cf3  jz      short loc_180021D17
0x180021cf5  mov     rcx, [rcx+10h]
0x180021cf9  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180021d00  mov     edx, 4Dh ; 'M'
0x180021d05  mov     r9d, eax
0x180021d08  call    WPP_SF_d
0x180021d0d  jmp     short loc_180021D17
0x180021d0f  mov     rcx, rdi; this
0x180021d12  call    ?CalculateRetentionThresholds@CBackupSession@@AEAAXXZ; CBackupSession::CalculateRetentionThresholds(void)
0x180021d17  xor     edx, edx; Token
0x180021d19  xor     ecx, ecx; Thread
0x180021d1b  call    cs:__imp_SetThreadToken
0x180021d21  test    eax, eax
0x180021d23  jnz     short loc_180021D65
0x180021d25  mov     rax, cs:WPP_GLOBAL_Control
0x180021d2c  cmp     rax, rbx
0x180021d2f  jz      short loc_180021D65
0x180021d31  test    byte ptr [rax+1Ch], 1
0x180021d35  jz      short loc_180021D65
0x180021d37  call    cs:__imp_GetLastError
0x180021d3d  test    eax, eax
0x180021d3f  jle     short loc_180021D46
0x180021d41  movzx   eax, ax
0x180021d44  or      eax, esi
0x180021d46  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d4d  lea     r8, WPP_8d97dc09e3d434ad11bd00bd3b095546_Traceguids
0x180021d54  mov     edx, 4Eh ; 'N'
0x180021d59  mov     r9d, eax
0x180021d5c  mov     rcx, [rcx+10h]
0x180021d60  call    WPP_SF_d
0x180021d65  xor     eax, eax
0x180021d67  mov     rcx, [rsp+88h+var_18]
0x180021d6c  xor     rcx, rsp; StackCookie
0x180021d6f  call    __security_check_cookie
0x180021d74  lea     r11, [rsp+88h+var_8]
0x180021d7c  mov     rbx, [r11+20h]
0x180021d80  mov     rsi, [r11+28h]
0x180021d84  mov     rsp, r11
0x180021d87  pop     rdi
0x180021d88  retn
```
