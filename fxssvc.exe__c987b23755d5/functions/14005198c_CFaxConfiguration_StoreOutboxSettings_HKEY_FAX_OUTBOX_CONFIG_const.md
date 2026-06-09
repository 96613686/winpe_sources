# CFaxConfiguration::StoreOutboxSettings(HKEY__ *,_FAX_OUTBOX_CONFIG * const)

- ea: `0x14005198c`
- end: `0x140051c54`
- name: `?StoreOutboxSettings@CFaxConfiguration@@AEBAKPEAUHKEY__@@QEAU_FAX_OUTBOX_CONFIG@@@Z`
- size: `712`
- prototype: `unsigned int __fastcall(CFaxConfiguration *__hidden this, HKEY, struct _FAX_OUTBOX_CONFIG *const)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14005144c`
- `0x140052188`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x14005198c`
- `0x1400709fc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400519ec`
- `KERNEL32!GetLastError` at `0x140051a39`
- `KERNEL32!GetLastError` at `0x140051a86`
- `KERNEL32!GetLastError` at `0x140051ad3`
- `KERNEL32!GetLastError` at `0x140051b20`
- `KERNEL32!GetLastError` at `0x140051b6d`
- `KERNEL32!GetLastError` at `0x140051bc6`
- `KERNEL32!GetLastError` at `0x140051c12`
- `KERNEL32!GetLastError` at `0x1400519ec`
- `KERNEL32!GetLastError` at `0x140051a39`
- `KERNEL32!GetLastError` at `0x140051a86`
- `KERNEL32!GetLastError` at `0x140051ad3`
- `KERNEL32!GetLastError` at `0x140051b20`
- `KERNEL32!GetLastError` at `0x140051b6d`
- `KERNEL32!GetLastError` at `0x140051bc6`
- `KERNEL32!GetLastError` at `0x140051c12`

## string_xrefs

- `0x140051b0d`: `UseDeviceTsid`

## pseudocode

```c
__int64 __fastcall CFaxConfiguration::StoreOutboxSettings(
        CFaxConfiguration *this,
        HKEY a2,
        struct _FAX_OUTBOX_CONFIG *const a3)
{
  DWORD LastError; // eax
  DWORD v6; // ebx
  CMapDeviceId *v7; // rcx
  __int64 v8; // rdx

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids);
  }
  if ( (unsigned int)SetRegistryDword(a2, L"Retries", *((_DWORD *)a3 + 3)) )
  {
    if ( (unsigned int)SetRegistryDword(a2, L"Retry Delay", *((_DWORD *)a3 + 4)) )
    {
      if ( (unsigned int)SetRegistryDword(a2, L"QueueAgeLimit", *((_DWORD *)a3 + 7)) )
      {
        if ( (unsigned int)SetRegistryDword(a2, L"Branding", *((_DWORD *)a3 + 8)) )
        {
          if ( (unsigned int)SetRegistryDword(a2, L"UseDeviceTsid", *((_DWORD *)a3 + 2)) )
          {
            if ( (unsigned int)SetRegistryDword(a2, L"AllowPersonalCoverPages", *((_DWORD *)a3 + 1)) )
            {
              if ( (unsigned int)SetRegistryDword(a2, L"StartCheapTime", *((_DWORD *)a3 + 5)) )
              {
                v6 = 0;
                if ( !(unsigned int)SetRegistryDword(a2, L"StopCheapTime", *((_DWORD *)a3 + 6)) )
                {
                  LastError = GetLastError();
                  v6 = LastError;
                  v7 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v8 = 47;
                    goto LABEL_45;
                  }
                }
              }
              else
              {
                LastError = GetLastError();
                v6 = LastError;
                v7 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v8 = 46;
                  goto LABEL_45;
                }
              }
            }
            else
            {
              LastError = GetLastError();
              v6 = LastError;
              v7 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v8 = 45;
                goto LABEL_45;
              }
            }
          }
          else
          {
            LastError = GetLastError();
            v6 = LastError;
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v8 = 44;
              goto LABEL_45;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          v6 = LastError;
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v8 = 43;
            goto LABEL_45;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v8 = 42;
          goto LABEL_45;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = 41;
        goto LABEL_45;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = 40;
LABEL_45:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids, LastError);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x14005198c  push    rbx
0x14005198e  push    rsi
0x14005198f  push    rdi
0x140051990  push    r14
0x140051992  push    r15
0x140051994  sub     rsp, 20h
0x140051998  mov     rdi, r8
0x14005199b  mov     rsi, rdx
0x14005199e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400519a5  lea     r14, WPP_GLOBAL_Control
0x1400519ac  lea     r15, WPP_6e5b2a13775b32d2447bcd169ef7aa87_Traceguids
0x1400519b3  cmp     rcx, r14
0x1400519b6  jz      short loc_1400519D5
0x1400519b8  test    byte ptr [rcx+1Ch], 4
0x1400519bc  jz      short loc_1400519D5
0x1400519be  cmp     byte ptr [rcx+19h], 5
0x1400519c2  jb      short loc_1400519D5
0x1400519c4  mov     rcx, [rcx+10h]
0x1400519c8  mov     edx, 27h ; '''
0x1400519cd  mov     r8, r15
0x1400519d0  call    WPP_SF_
0x1400519d5  mov     r8d, [rdi+0Ch]
0x1400519d9  lea     rdx, aRetries; "Retries"
0x1400519e0  mov     rcx, rsi
0x1400519e3  call    SetRegistryDword
0x1400519e8  test    eax, eax
0x1400519ea  jnz     short loc_140051A22
0x1400519ec  call    cs:__imp_GetLastError
0x1400519f2  mov     ebx, eax
0x1400519f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400519fb  cmp     rcx, r14
0x1400519fe  jz      loc_140051C46
0x140051a04  test    byte ptr [rcx+1Ch], 4
0x140051a08  jz      loc_140051C46
0x140051a0e  cmp     byte ptr [rcx+19h], 2
0x140051a12  jb      loc_140051C46
0x140051a18  mov     edx, 28h ; '('
0x140051a1d  jmp     loc_140051C37
0x140051a22  mov     r8d, [rdi+10h]
0x140051a26  lea     rdx, aRetryDelay; "Retry Delay"
0x140051a2d  mov     rcx, rsi
0x140051a30  call    SetRegistryDword
0x140051a35  test    eax, eax
0x140051a37  jnz     short loc_140051A6F
0x140051a39  call    cs:__imp_GetLastError
0x140051a3f  mov     ebx, eax
0x140051a41  mov     rcx, cs:WPP_GLOBAL_Control
0x140051a48  cmp     rcx, r14
0x140051a4b  jz      loc_140051C46
0x140051a51  test    byte ptr [rcx+1Ch], 4
0x140051a55  jz      loc_140051C46
0x140051a5b  cmp     byte ptr [rcx+19h], 2
0x140051a5f  jb      loc_140051C46
0x140051a65  mov     edx, 29h ; ')'
0x140051a6a  jmp     loc_140051C37
0x140051a6f  mov     r8d, [rdi+1Ch]
0x140051a73  lea     rdx, aQueueagelimit; "QueueAgeLimit"
0x140051a7a  mov     rcx, rsi
0x140051a7d  call    SetRegistryDword
0x140051a82  test    eax, eax
0x140051a84  jnz     short loc_140051ABC
0x140051a86  call    cs:__imp_GetLastError
0x140051a8c  mov     ebx, eax
0x140051a8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140051a95  cmp     rcx, r14
0x140051a98  jz      loc_140051C46
0x140051a9e  test    byte ptr [rcx+1Ch], 4
0x140051aa2  jz      loc_140051C46
0x140051aa8  cmp     byte ptr [rcx+19h], 2
0x140051aac  jb      loc_140051C46
0x140051ab2  mov     edx, 2Ah ; '*'
0x140051ab7  jmp     loc_140051C37
0x140051abc  mov     r8d, [rdi+20h]
0x140051ac0  lea     rdx, aBranding; "Branding"
0x140051ac7  mov     rcx, rsi
0x140051aca  call    SetRegistryDword
0x140051acf  test    eax, eax
0x140051ad1  jnz     short loc_140051B09
0x140051ad3  call    cs:__imp_GetLastError
0x140051ad9  mov     ebx, eax
0x140051adb  mov     rcx, cs:WPP_GLOBAL_Control
0x140051ae2  cmp     rcx, r14
0x140051ae5  jz      loc_140051C46
0x140051aeb  test    byte ptr [rcx+1Ch], 4
0x140051aef  jz      loc_140051C46
0x140051af5  cmp     byte ptr [rcx+19h], 2
0x140051af9  jb      loc_140051C46
0x140051aff  mov     edx, 2Bh ; '+'
0x140051b04  jmp     loc_140051C37
0x140051b09  mov     r8d, [rdi+8]
0x140051b0d  lea     rdx, aUsedevicetsid; "UseDeviceTsid"
0x140051b14  mov     rcx, rsi
0x140051b17  call    SetRegistryDword
0x140051b1c  test    eax, eax
0x140051b1e  jnz     short loc_140051B56
0x140051b20  call    cs:__imp_GetLastError
0x140051b26  mov     ebx, eax
0x140051b28  mov     rcx, cs:WPP_GLOBAL_Control
0x140051b2f  cmp     rcx, r14
0x140051b32  jz      loc_140051C46
0x140051b38  test    byte ptr [rcx+1Ch], 4
0x140051b3c  jz      loc_140051C46
0x140051b42  cmp     byte ptr [rcx+19h], 2
0x140051b46  jb      loc_140051C46
0x140051b4c  mov     edx, 2Ch ; ','
0x140051b51  jmp     loc_140051C37
0x140051b56  mov     r8d, [rdi+4]
0x140051b5a  lea     rdx, aAllowpersonalc; "AllowPersonalCoverPages"
0x140051b61  mov     rcx, rsi
0x140051b64  call    SetRegistryDword
0x140051b69  test    eax, eax
0x140051b6b  jnz     short loc_140051BA3
0x140051b6d  call    cs:__imp_GetLastError
0x140051b73  mov     ebx, eax
0x140051b75  mov     rcx, cs:WPP_GLOBAL_Control
0x140051b7c  cmp     rcx, r14
0x140051b7f  jz      loc_140051C46
0x140051b85  test    byte ptr [rcx+1Ch], 4
0x140051b89  jz      loc_140051C46
0x140051b8f  cmp     byte ptr [rcx+19h], 2
0x140051b93  jb      loc_140051C46
0x140051b99  mov     edx, 2Dh ; '-'
0x140051b9e  jmp     loc_140051C37
0x140051ba3  movzx   r8d, word ptr [rdi+16h]
0x140051ba8  lea     rdx, aStartcheaptime; "StartCheapTime"
0x140051baf  movzx   eax, word ptr [rdi+14h]
0x140051bb3  mov     rcx, rsi
0x140051bb6  shl     r8d, 10h
0x140051bba  or      r8d, eax
0x140051bbd  call    SetRegistryDword
0x140051bc2  test    eax, eax
0x140051bc4  jnz     short loc_140051BED
0x140051bc6  call    cs:__imp_GetLastError
0x140051bcc  mov     ebx, eax
0x140051bce  mov     rcx, cs:WPP_GLOBAL_Control
0x140051bd5  cmp     rcx, r14
0x140051bd8  jz      short loc_140051C46
0x140051bda  test    byte ptr [rcx+1Ch], 4
0x140051bde  jz      short loc_140051C46
0x140051be0  cmp     byte ptr [rcx+19h], 2
0x140051be4  jb      short loc_140051C46
0x140051be6  mov     edx, 2Eh ; '.'
0x140051beb  jmp     short loc_140051C37
0x140051bed  movzx   r8d, word ptr [rdi+1Ah]
0x140051bf2  lea     rdx, aStopcheaptime; "StopCheapTime"
0x140051bf9  movzx   eax, word ptr [rdi+18h]
0x140051bfd  mov     rcx, rsi
0x140051c00  shl     r8d, 10h
0x140051c04  xor     ebx, ebx
0x140051c06  or      r8d, eax
0x140051c09  call    SetRegistryDword
0x140051c0e  test    eax, eax
0x140051c10  jnz     short loc_140051C46
0x140051c12  call    cs:__imp_GetLastError
0x140051c18  mov     ebx, eax
0x140051c1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140051c21  cmp     rcx, r14
0x140051c24  jz      short loc_140051C46
0x140051c26  test    byte ptr [rcx+1Ch], 4
0x140051c2a  jz      short loc_140051C46
0x140051c2c  cmp     byte ptr [rcx+19h], 2
0x140051c30  jb      short loc_140051C46
0x140051c32  mov     edx, 2Fh ; '/'
0x140051c37  mov     rcx, [rcx+10h]
0x140051c3b  mov     r9d, eax
0x140051c3e  mov     r8, r15
0x140051c41  call    WPP_SF_d
0x140051c46  mov     eax, ebx
0x140051c48  add     rsp, 20h
0x140051c4c  pop     r15
0x140051c4e  pop     r14
0x140051c50  pop     rdi
0x140051c51  pop     rsi
0x140051c52  pop     rbx
0x140051c53  retn
```
