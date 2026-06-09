# DfdManager::LogSMARTEvent(unsigned __int64,bool)

- ea: `0x180006c74`
- end: `0x180006e6a`
- name: `?LogSMARTEvent@DfdManager@@QEAAK_K_N@Z`
- size: `502`
- prototype: `__int64 __fastcall(DiskContext **this, REGHANDLE, char)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002ed8`

## callees

- `0x180002c90`
- `0x180003e3c`
- `0x180003e8c`
- `0x180003edc`
- `0x18000462c`
- `0x180004d68`
- `0x180006c74`
- `0x180008370`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x180006e0a`
- `ADVAPI32!EventWrite` at `0x180006e0a`

## pseudocode

```c
__int64 __fastcall DfdManager::LogSMARTEvent(DiskContext **this, REGHANDLE a2, char a3)
{
  ULONG v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  const wchar_t *FriendlyName; // rbx
  int FriendlyNameSize; // eax
  int v11; // esi
  ULONG v12; // eax
  DiskContext *v13; // rbx
  const wchar_t *v14; // rbp
  DiskContext *v15; // rbx
  DiskContext *v16; // rcx
  int v17; // eax
  int v18; // eax
  unsigned __int16 *HardwareId; // rax
  DiskContext *v20; // rdi
  const wchar_t *v21; // rbp
  _DWORD *v22; // rbx
  const EVENT_DESCRIPTOR *v23; // rdx
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+20h] [rbp-68h] BYREF
  const wchar_t *v26; // [rsp+30h] [rbp-58h]
  int v27; // [rsp+38h] [rbp-50h]
  int v28; // [rsp+3Ch] [rbp-4Ch]
  const wchar_t *v29; // [rsp+40h] [rbp-48h]
  int v30; // [rsp+48h] [rbp-40h]
  int v31; // [rsp+4Ch] [rbp-3Ch]

  if ( a2 )
  {
    FriendlyName = DiskContext::GetFriendlyName(*this);
    FriendlyNameSize = DiskContext::GetFriendlyNameSize(*this);
    v11 = 16;
    if ( FriendlyName && FriendlyNameSize )
    {
      v12 = 2 * FriendlyNameSize + 2;
    }
    else
    {
      FriendlyName = L"Unknown";
      v12 = 16;
    }
    UserData.Ptr = (ULONGLONG)FriendlyName;
    v13 = *this;
    UserData.Size = v12;
    UserData.Reserved = 0;
    if ( *((_BYTE *)v13 + 600) == 48 )
    {
      DiskContext::SetVolumeList(v13);
      *((_BYTE *)v13 + 600) = 49;
    }
    v14 = (const wchar_t *)*((_QWORD *)v13 + 76);
    v15 = *this;
    v16 = *this;
    if ( *((_BYTE *)*this + 600) == 48 )
    {
      DiskContext::SetVolumeList(v16);
      *((_BYTE *)v15 + 600) = 49;
      v16 = *this;
    }
    if ( v14 && (v17 = *((_DWORD *)v15 + 154)) != 0 )
    {
      v18 = 2 * v17 + 2;
    }
    else
    {
      v14 = L"Unknown";
      v18 = 16;
    }
    v26 = v14;
    v27 = v18;
    v28 = 0;
    HardwareId = DiskContext::GetHardwareId(v16);
    v20 = *this;
    v21 = HardwareId;
    v22 = (_DWORD *)((char *)v20 + 568);
    if ( *((_BYTE *)v20 + 556) == 48 )
    {
      DiskContext::SetDiskProperty(v20, (unsigned __int16 **)v20 + 70, (unsigned int *)v20 + 142, 1u);
      *((_BYTE *)v20 + 556) = 49;
    }
    if ( v21 && *v22 )
      v11 = 2 * *v22 + 2;
    else
      v21 = L"Unknown";
    v29 = v21;
    v30 = v11;
    v31 = 0;
    v23 = (const EVENT_DESCRIPTOR *)DFD_TS_ETW_EVENT_IGNORE_LIST;
    if ( !a3 )
      v23 = &DFD_TS_ETW_EVENT_SMART_FAILURE;
    v6 = EventWrite(a2, v23, 3u, &UserData);
    if ( v6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v8 = 51;
        goto LABEL_29;
      }
    }
  }
  else
  {
    v6 = 87;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 50;
LABEL_29:
      WPP_SF_d(v7[2], v8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids, v6);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180006c74  mov     [rsp+arg_10], rbx
0x180006c79  push    rbp
0x180006c7a  push    rsi
0x180006c7b  push    rdi
0x180006c7c  push    r14
0x180006c7e  push    r15
0x180006c80  sub     rsp, 60h
0x180006c84  mov     rax, cs:__security_cookie
0x180006c8b  xor     rax, rsp
0x180006c8e  mov     [rsp+88h+var_38], rax
0x180006c93  mov     r15b, r8b
0x180006c96  mov     r14, rdx
0x180006c99  mov     rdi, rcx
0x180006c9c  test    rdx, rdx
0x180006c9f  jnz     short loc_180006CCD
0x180006ca1  lea     ebx, [rdx+57h]
0x180006ca4  mov     rcx, cs:WPP_GLOBAL_Control
0x180006cab  lea     rax, WPP_GLOBAL_Control
0x180006cb2  cmp     rcx, rax
0x180006cb5  jz      loc_180006E47
0x180006cbb  test    byte ptr [rcx+1Ch], 1
0x180006cbf  jz      loc_180006E47
0x180006cc5  lea     edx, [rbx-25h]
0x180006cc8  jmp     loc_180006E34
0x180006ccd  mov     rcx, [rcx]; this
0x180006cd0  call    ?GetFriendlyName@DiskContext@@QEAAPEAGXZ; DiskContext::GetFriendlyName(void)
0x180006cd5  mov     rcx, [rdi]; this
0x180006cd8  mov     rbx, rax
0x180006cdb  call    ?GetFriendlyNameSize@DiskContext@@QEAA_KXZ; DiskContext::GetFriendlyNameSize(void)
0x180006ce0  mov     esi, 10h
0x180006ce5  test    rbx, rbx
0x180006ce8  jz      short loc_180006CF7
0x180006cea  test    eax, eax
0x180006cec  jz      short loc_180006CF7
0x180006cee  lea     eax, ds:2[rax*2]
0x180006cf5  jmp     short loc_180006D00
0x180006cf7  lea     rbx, aUnknown; "Unknown"
0x180006cfe  mov     eax, esi
0x180006d00  mov     [rsp+88h+UserData.Ptr], rbx
0x180006d05  mov     rbx, [rdi]
0x180006d08  mov     [rsp+88h+UserData.Size], eax
0x180006d0c  mov     dword ptr [rsp+88h+UserData.0Ch], 0
0x180006d14  cmp     byte ptr [rbx+258h], 30h ; '0'
0x180006d1b  jnz     short loc_180006D2C
0x180006d1d  mov     rcx, rbx; this
0x180006d20  call    ?SetVolumeList@DiskContext@@AEAAKXZ; DiskContext::SetVolumeList(void)
0x180006d25  mov     byte ptr [rbx+258h], 31h ; '1'
0x180006d2c  mov     rbp, [rbx+260h]
0x180006d33  mov     rbx, [rdi]
0x180006d36  mov     rcx, rbx; this
0x180006d39  cmp     byte ptr [rbx+258h], 30h ; '0'
0x180006d40  jnz     short loc_180006D51
0x180006d42  call    ?SetVolumeList@DiskContext@@AEAAKXZ; DiskContext::SetVolumeList(void)
0x180006d47  mov     byte ptr [rbx+258h], 31h ; '1'
0x180006d4e  mov     rcx, [rdi]; this
0x180006d51  test    rbp, rbp
0x180006d54  jz      short loc_180006D69
0x180006d56  mov     eax, [rbx+268h]
0x180006d5c  test    eax, eax
0x180006d5e  jz      short loc_180006D69
0x180006d60  lea     eax, ds:2[rax*2]
0x180006d67  jmp     short loc_180006D72
0x180006d69  lea     rbp, aUnknown; "Unknown"
0x180006d70  mov     eax, esi
0x180006d72  mov     [rsp+88h+var_58], rbp
0x180006d77  mov     [rsp+88h+var_50], eax
0x180006d7b  mov     [rsp+88h+var_4C], 0
0x180006d83  call    ?GetHardwareId@DiskContext@@QEAAPEAGXZ; DiskContext::GetHardwareId(void)
0x180006d88  mov     rdi, [rdi]
0x180006d8b  mov     rbp, rax
0x180006d8e  cmp     byte ptr [rdi+22Ch], 30h ; '0'
0x180006d95  lea     rbx, [rdi+238h]
0x180006d9c  jnz     short loc_180006DBD
0x180006d9e  lea     rdx, [rdi+230h]; unsigned __int16 **
0x180006da5  mov     r9d, 1; unsigned int
0x180006dab  mov     r8, rbx; unsigned int *
0x180006dae  mov     rcx, rdi; this
0x180006db1  call    ?SetDiskProperty@DiskContext@@AEAAKPEAPEAGPEAKK@Z; DiskContext::SetDiskProperty(ushort * *,ulong *,ulong)
0x180006db6  mov     byte ptr [rdi+22Ch], 31h ; '1'
0x180006dbd  test    rbp, rbp
0x180006dc0  jz      short loc_180006DD1
0x180006dc2  mov     eax, [rbx]
0x180006dc4  test    eax, eax
0x180006dc6  jz      short loc_180006DD1
0x180006dc8  lea     esi, ds:2[rax*2]
0x180006dcf  jmp     short loc_180006DD8
0x180006dd1  lea     rbp, aUnknown; "Unknown"
0x180006dd8  mov     [rsp+88h+var_48], rbp
0x180006ddd  lea     r9, [rsp+88h+UserData]; UserData
0x180006de2  mov     [rsp+88h+var_40], esi
0x180006de6  mov     r8d, 3; UserDataCount
0x180006dec  mov     [rsp+88h+var_3C], 0
0x180006df4  mov     rcx, r14; RegHandle
0x180006df7  lea     rdx, DFD_TS_ETW_EVENT_IGNORE_LIST
0x180006dfe  test    r15b, r15b
0x180006e01  jnz     short loc_180006E0A
0x180006e03  lea     rdx, DFD_TS_ETW_EVENT_SMART_FAILURE; EventDescriptor
0x180006e0a  call    cs:__imp_EventWrite
0x180006e10  mov     ebx, eax
0x180006e12  test    eax, eax
0x180006e14  jz      short loc_180006E47
0x180006e16  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e1d  lea     rax, WPP_GLOBAL_Control
0x180006e24  cmp     rcx, rax
0x180006e27  jz      short loc_180006E47
0x180006e29  test    byte ptr [rcx+1Ch], 1
0x180006e2d  jz      short loc_180006E47
0x180006e2f  mov     edx, 33h ; '3'
0x180006e34  mov     rcx, [rcx+10h]
0x180006e38  lea     r8, WPP_3ef5aefce1013aeb7f7a24910fe71d4f_Traceguids
0x180006e3f  mov     r9d, ebx
0x180006e42  call    WPP_SF_d
0x180006e47  mov     eax, ebx
0x180006e49  mov     rcx, [rsp+88h+var_38]
0x180006e4e  xor     rcx, rsp; StackCookie
0x180006e51  call    __security_check_cookie
0x180006e56  mov     rbx, [rsp+88h+arg_10]
0x180006e5e  add     rsp, 60h
0x180006e62  pop     r15
0x180006e64  pop     r14
0x180006e66  pop     rdi
0x180006e67  pop     rsi
0x180006e68  pop     rbp
0x180006e69  retn
```
