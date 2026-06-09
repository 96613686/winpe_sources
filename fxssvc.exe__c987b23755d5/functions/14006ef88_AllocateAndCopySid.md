# AllocateAndCopySid

- ea: `0x14006ef88`
- end: `0x14006f108`
- name: `AllocateAndCopySid`
- size: `384`
- prototype: `__int64 __fastcall(PSID pSourceSid)`
- caller_count: `10`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000c950`
- `0x14000d244`
- `0x14000d680`
- `0x14002f9f0`
- `0x140031b6c`
- `0x14003567c`
- `0x140053f38`
- `0x1400540a4`
- `0x140054448`
- `0x14005451c`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x140065d14`
- `0x140065dbc`
- `0x14006ef88`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x14006f059`
- `ADVAPI32!GetLengthSid` at `0x14006f059`
- `ADVAPI32!IsValidSid` at `0x14006f007`
- `ADVAPI32!IsValidSid` at `0x14006f007`
- `ADVAPI32!CopySid` at `0x14006f0a9`
- `ADVAPI32!CopySid` at `0x14006f0a9`
- `KERNEL32!GetLastError` at `0x14006f011`
- `KERNEL32!GetLastError` at `0x14006f0b3`
- `KERNEL32!GetLastError` at `0x14006f011`
- `KERNEL32!GetLastError` at `0x14006f0b3`

## pseudocode

```c
__int64 __fastcall AllocateAndCopySid(PSID pSourceSid, LPVOID *a2)
{
  CMapDeviceId *v4; // rcx
  DWORD v5; // ebx
  DWORD LastError; // eax
  DWORD LengthSid; // esi
  void *v8; // rax
  DWORD v10; // eax

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !pSourceSid )
  {
    if ( v4 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
      WPP_SF_(*((_QWORD *)v4 + 2), 21, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids);
    v5 = 0;
LABEL_28:
    *a2 = 0;
    return v5;
  }
  if ( !IsValidSid(pSourceSid) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids, LastError);
    }
    return v5;
  }
  LengthSid = GetLengthSid(pSourceSid);
  v8 = (void *)pMemAlloc(LengthSid);
  *a2 = v8;
  if ( v8 )
  {
    if ( !CopySid(LengthSid, v8, pSourceSid) )
    {
      v10 = GetLastError();
      v5 = v10;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids, v10);
      }
      pMemFree(*a2);
      goto LABEL_28;
    }
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids, LengthSid);
    }
    return 14;
  }
}

```

## disassembly

```asm
0x14006ef88  push    rbx
0x14006ef8a  push    rsi
0x14006ef8b  push    rdi
0x14006ef8c  push    r14
0x14006ef8e  push    r15
0x14006ef90  sub     rsp, 20h
0x14006ef94  mov     rdi, rdx
0x14006ef97  mov     rbx, rcx
0x14006ef9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006efa1  lea     r14, WPP_GLOBAL_Control
0x14006efa8  lea     r15, WPP_987eb3bb399c3a7d72322ad52d5235ad_Traceguids
0x14006efaf  cmp     rcx, r14
0x14006efb2  jz      short loc_14006EFD8
0x14006efb4  test    byte ptr [rcx+1Ch], 2
0x14006efb8  jz      short loc_14006EFD8
0x14006efba  cmp     byte ptr [rcx+19h], 5
0x14006efbe  jb      short loc_14006EFD8
0x14006efc0  mov     rcx, [rcx+10h]
0x14006efc4  mov     edx, 14h
0x14006efc9  mov     r8, r15
0x14006efcc  call    WPP_SF_
0x14006efd1  mov     rcx, cs:WPP_GLOBAL_Control
0x14006efd8  test    rbx, rbx
0x14006efdb  jnz     short loc_14006F004
0x14006efdd  cmp     rcx, r14
0x14006efe0  jz      short loc_14006EFFD
0x14006efe2  test    byte ptr [rcx+1Ch], 2
0x14006efe6  jz      short loc_14006EFFD
0x14006efe8  cmp     byte ptr [rcx+19h], 5
0x14006efec  jb      short loc_14006EFFD
0x14006efee  mov     rcx, [rcx+10h]
0x14006eff2  lea     edx, [rbx+15h]
0x14006eff5  mov     r8, r15
0x14006eff8  call    WPP_SF_
0x14006effd  xor     ebx, ebx
0x14006efff  jmp     loc_14006F0EF
0x14006f004  mov     rcx, rbx; pSid
0x14006f007  call    cs:__imp_IsValidSid
0x14006f00d  test    eax, eax
0x14006f00f  jnz     short loc_14006F056
0x14006f011  call    cs:__imp_GetLastError
0x14006f017  mov     ebx, eax
0x14006f019  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f020  cmp     rcx, r14
0x14006f023  jz      loc_14006F0F6
0x14006f029  test    byte ptr [rcx+1Ch], 2
0x14006f02d  jz      loc_14006F0F6
0x14006f033  cmp     byte ptr [rcx+19h], 2
0x14006f037  jb      loc_14006F0F6
0x14006f03d  mov     rcx, [rcx+10h]
0x14006f041  mov     edx, 16h
0x14006f046  mov     r9d, eax
0x14006f049  mov     r8, r15
0x14006f04c  call    WPP_SF_d
0x14006f051  jmp     loc_14006F0F6
0x14006f056  mov     rcx, rbx; pSid
0x14006f059  call    cs:__imp_GetLengthSid
0x14006f05f  mov     ecx, eax; dwBytes
0x14006f061  mov     esi, eax
0x14006f063  call    pMemAlloc
0x14006f068  mov     [rdi], rax
0x14006f06b  test    rax, rax
0x14006f06e  jnz     short loc_14006F0A1
0x14006f070  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f077  cmp     rcx, r14
0x14006f07a  jz      short loc_14006F09A
0x14006f07c  test    byte ptr [rcx+1Ch], 2
0x14006f080  jz      short loc_14006F09A
0x14006f082  cmp     byte ptr [rcx+19h], 2
0x14006f086  jb      short loc_14006F09A
0x14006f088  mov     rcx, [rcx+10h]
0x14006f08c  lea     edx, [rax+17h]
0x14006f08f  mov     r9d, esi
0x14006f092  mov     r8, r15
0x14006f095  call    WPP_SF_d
0x14006f09a  mov     eax, 0Eh
0x14006f09f  jmp     short loc_14006F0FC
0x14006f0a1  mov     r8, rbx; pSourceSid
0x14006f0a4  mov     rdx, rax; pDestinationSid
0x14006f0a7  mov     ecx, esi; nDestinationSidLength
0x14006f0a9  call    cs:__imp_CopySid
0x14006f0af  test    eax, eax
0x14006f0b1  jnz     short loc_14006F0FA
0x14006f0b3  call    cs:__imp_GetLastError
0x14006f0b9  mov     ebx, eax
0x14006f0bb  mov     rcx, cs:WPP_GLOBAL_Control
0x14006f0c2  cmp     rcx, r14
0x14006f0c5  jz      short loc_14006F0E7
0x14006f0c7  test    byte ptr [rcx+1Ch], 2
0x14006f0cb  jz      short loc_14006F0E7
0x14006f0cd  cmp     byte ptr [rcx+19h], 2
0x14006f0d1  jb      short loc_14006F0E7
0x14006f0d3  mov     rcx, [rcx+10h]
0x14006f0d7  mov     edx, 18h
0x14006f0dc  mov     r9d, eax
0x14006f0df  mov     r8, r15
0x14006f0e2  call    WPP_SF_d
0x14006f0e7  mov     rcx, [rdi]; lpMem
0x14006f0ea  call    pMemFree
0x14006f0ef  mov     qword ptr [rdi], 0
0x14006f0f6  mov     eax, ebx
0x14006f0f8  jmp     short loc_14006F0FC
0x14006f0fa  xor     eax, eax
0x14006f0fc  add     rsp, 20h
0x14006f100  pop     r15
0x14006f102  pop     r14
0x14006f104  pop     rdi
0x14006f105  pop     rsi
0x14006f106  pop     rbx
0x14006f107  retn
```
