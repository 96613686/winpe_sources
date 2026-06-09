# GetBitLockerCSPRegValueName(BITLOCKER_CSP_STATUS,ushort const * *)

- ea: `0x18002ba18`
- end: `0x18002bb54`
- name: `?GetBitLockerCSPRegValueName@@YAJW4BITLOCKER_CSP_STATUS@@PEAPEBG@Z`
- size: `316`
- prototype: `__int64 __fastcall(int, const wchar_t **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002b894`

## callees

- `0x1800037a0`
- `0x18000e354`
- `0x18002ba18`

## string_xrefs

- `0x18002bae9`: `TPMNotReady`

## pseudocode

```c
__int64 __fastcall GetBitLockerCSPRegValueName(int a1, const wchar_t **a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  const wchar_t *v12; // rax

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    *a2 = 0;
    if ( a1 )
    {
      v7 = a1 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            v10 = v9 - 1;
            if ( v10 )
            {
              v11 = v10 - 1;
              if ( v11 )
              {
                if ( v11 != 1 )
                {
                  v5 = -2147024809;
                  if ( v4 == &WPP_GLOBAL_Control )
                    return v5;
                  if ( (*((_BYTE *)v4 + 28) & 0x40) == 0 )
                    goto LABEL_27;
                  v6 = 72;
                  goto LABEL_8;
                }
                v12 = L"NetworkUnavailable";
              }
              else
              {
                v12 = L"TPMNotReady";
              }
            }
            else
            {
              v12 = L"TPMUnavailable";
            }
          }
          else
          {
            v12 = L"WinReUnavailable";
          }
        }
        else
        {
          v12 = L"NonAdminUserPolicyRequired";
        }
      }
      else
      {
        v12 = L"RecoveryKeyBackupFailed";
      }
    }
    else
    {
      v12 = L"EncryptionConsentMissing";
    }
    v5 = 0;
    *a2 = v12;
    goto LABEL_27;
  }
  v5 = -2147467261;
  if ( v4 == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)v4 + 28) & 0x40) != 0 )
  {
    v6 = 71;
LABEL_8:
    WPP_SF_d(v4[2], v6, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids, v5);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_27:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_(v4[2], 73, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids);
  return v5;
}

```

## disassembly

```asm
0x18002ba18  mov     [rsp+arg_0], rbx
0x18002ba1d  mov     [rsp+arg_8], rsi
0x18002ba22  push    rdi
0x18002ba23  sub     rsp, 20h
0x18002ba27  mov     rdi, rdx
0x18002ba2a  mov     ebx, ecx
0x18002ba2c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba33  lea     rsi, WPP_GLOBAL_Control
0x18002ba3a  cmp     rcx, rsi
0x18002ba3d  jz      short loc_18002BA61
0x18002ba3f  test    byte ptr [rcx+1Ch], 20h
0x18002ba43  jz      short loc_18002BA61
0x18002ba45  mov     rcx, [rcx+10h]
0x18002ba49  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18002ba50  mov     edx, 46h ; 'F'
0x18002ba55  call    WPP_SF_
0x18002ba5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba61  test    rdi, rdi
0x18002ba64  jnz     short loc_18002BAA0
0x18002ba66  mov     ebx, 80004003h
0x18002ba6b  cmp     rcx, rsi
0x18002ba6e  jz      loc_18002BB42
0x18002ba74  test    byte ptr [rcx+1Ch], 40h
0x18002ba78  jz      loc_18002BB22
0x18002ba7e  lea     edx, [rdi+47h]
0x18002ba81  mov     rcx, [rcx+10h]
0x18002ba85  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18002ba8c  mov     r9d, ebx
0x18002ba8f  call    WPP_SF_d
0x18002ba94  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba9b  jmp     loc_18002BB22
0x18002baa0  mov     qword ptr [rdi], 0
0x18002baa7  test    ebx, ebx
0x18002baa9  jz      short loc_18002BB16
0x18002baab  sub     ebx, 1
0x18002baae  jz      short loc_18002BB0D
0x18002bab0  sub     ebx, 1
0x18002bab3  jz      short loc_18002BB04
0x18002bab5  sub     ebx, 1
0x18002bab8  jz      short loc_18002BAFB
0x18002baba  sub     ebx, 1
0x18002babd  jz      short loc_18002BAF2
0x18002babf  sub     ebx, 1
0x18002bac2  jz      short loc_18002BAE9
0x18002bac4  cmp     ebx, 1
0x18002bac7  jz      short loc_18002BAE0
0x18002bac9  mov     ebx, 80070057h
0x18002bace  cmp     rcx, rsi
0x18002bad1  jz      short loc_18002BB42
0x18002bad3  test    byte ptr [rcx+1Ch], 40h
0x18002bad7  jz      short loc_18002BB22
0x18002bad9  mov     edx, 48h ; 'H'
0x18002bade  jmp     short loc_18002BA81
0x18002bae0  lea     rax, aNetworkunavail; "NetworkUnavailable"
0x18002bae7  jmp     short loc_18002BB1D
0x18002bae9  lea     rax, aTpmnotready; "TPMNotReady"
0x18002baf0  jmp     short loc_18002BB1D
0x18002baf2  lea     rax, aTpmunavailable; "TPMUnavailable"
0x18002baf9  jmp     short loc_18002BB1D
0x18002bafb  lea     rax, aWinreunavailab; "WinReUnavailable"
0x18002bb02  jmp     short loc_18002BB1D
0x18002bb04  lea     rax, aNonadminuserpo; "NonAdminUserPolicyRequired"
0x18002bb0b  jmp     short loc_18002BB1D
0x18002bb0d  lea     rax, aRecoverykeybac; "RecoveryKeyBackupFailed"
0x18002bb14  jmp     short loc_18002BB1D
0x18002bb16  lea     rax, aEncryptioncons; "EncryptionConsentMissing"
0x18002bb1d  xor     ebx, ebx
0x18002bb1f  mov     [rdi], rax
0x18002bb22  cmp     rcx, rsi
0x18002bb25  jz      short loc_18002BB42
0x18002bb27  test    byte ptr [rcx+1Ch], 20h
0x18002bb2b  jz      short loc_18002BB42
0x18002bb2d  mov     rcx, [rcx+10h]
0x18002bb31  lea     r8, WPP_6b6c66d645af38831ef4d71af1711f48_Traceguids
0x18002bb38  mov     edx, 49h ; 'I'
0x18002bb3d  call    WPP_SF_
0x18002bb42  mov     rsi, [rsp+28h+arg_8]
0x18002bb47  mov     eax, ebx
0x18002bb49  mov     rbx, [rsp+28h+arg_0]
0x18002bb4e  add     rsp, 20h
0x18002bb52  pop     rdi
0x18002bb53  retn
```
