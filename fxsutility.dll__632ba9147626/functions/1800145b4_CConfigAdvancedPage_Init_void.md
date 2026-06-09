# CConfigAdvancedPage::Init(void *)

- ea: `0x1800145b4`
- end: `0x1800146c1`
- name: `?Init@CConfigAdvancedPage@@QEAAKPEAX@Z`
- size: `269`
- prototype: `unsigned int __fastcall(CConfigAdvancedPage *__hidden this, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000fd8c`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x180014360`
- `0x1800144e8`
- `0x1800145b4`

## import_xrefs

- `FXSAPI!FaxAccessCheckEx2` at `0x180014613`
- `FXSAPI!FaxAccessCheckEx2` at `0x180014613`
- `KERNEL32!GetLastError` at `0x18001461d`
- `KERNEL32!GetLastError` at `0x18001461d`

## pseudocode

```c
__int64 __fastcall CConfigAdvancedPage::Init(CConfigAdvancedPage *this, void *a2)
{
  DWORD ArchiveSettings; // eax
  DWORD v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids);
  }
  *((_QWORD *)this + 4) = a2;
  *((_DWORD *)this + 144) = 1;
  if ( (unsigned int)FaxAccessCheckEx2(a2, 64, 0) )
  {
LABEL_8:
    ArchiveSettings = CConfigAdvancedPage::GetArchiveSettings(this);
    v5 = ArchiveSettings;
    if ( ArchiveSettings )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = 12;
LABEL_22:
        WPP_SF_d(v6[2], v7, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids, ArchiveSettings);
        return v5;
      }
    }
    else
    {
      ArchiveSettings = CConfigAdvancedPage::GetOutboxConfiguration(this);
      v5 = ArchiveSettings;
      if ( ArchiveSettings )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = 13;
          goto LABEL_22;
        }
      }
    }
    return v5;
  }
  ArchiveSettings = GetLastError();
  v5 = ArchiveSettings;
  if ( !ArchiveSettings )
  {
    *((_DWORD *)this + 144) = 0;
    goto LABEL_8;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = 11;
    goto LABEL_22;
  }
  return v5;
}

```

## disassembly

```asm
0x1800145b4  push    rbx
0x1800145b6  push    rbp
0x1800145b7  push    rsi
0x1800145b8  push    rdi
0x1800145b9  sub     rsp, 28h
0x1800145bd  mov     rbx, rdx
0x1800145c0  mov     rdi, rcx
0x1800145c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800145ca  lea     rbp, WPP_GLOBAL_Control
0x1800145d1  mov     esi, 100h
0x1800145d6  cmp     rcx, rbp
0x1800145d9  jz      short loc_1800145FB
0x1800145db  test    [rcx+1Ch], esi
0x1800145de  jz      short loc_1800145FB
0x1800145e0  cmp     byte ptr [rcx+19h], 5
0x1800145e4  jb      short loc_1800145FB
0x1800145e6  mov     rcx, [rcx+10h]
0x1800145ea  lea     r8, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids
0x1800145f1  mov     edx, 0Ah
0x1800145f6  call    WPP_SF_
0x1800145fb  xor     r8d, r8d
0x1800145fe  mov     [rdi+20h], rbx
0x180014602  mov     rcx, rbx
0x180014605  mov     dword ptr [rdi+240h], 1
0x18001460f  lea     edx, [r8+40h]
0x180014613  call    cs:__imp_FaxAccessCheckEx2
0x180014619  test    eax, eax
0x18001461b  jnz     short loc_18001462F
0x18001461d  call    cs:__imp_GetLastError
0x180014623  mov     ebx, eax
0x180014625  test    eax, eax
0x180014627  jnz     short loc_18001465B
0x180014629  mov     [rdi+240h], eax
0x18001462f  mov     rcx, rdi; this
0x180014632  call    ?GetArchiveSettings@CConfigAdvancedPage@@AEAAKXZ; CConfigAdvancedPage::GetArchiveSettings(void)
0x180014637  mov     ebx, eax
0x180014639  test    eax, eax
0x18001463b  jz      short loc_180014679
0x18001463d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014644  cmp     rcx, rbp
0x180014647  jz      short loc_1800146B6
0x180014649  test    [rcx+1Ch], esi
0x18001464c  jz      short loc_1800146B6
0x18001464e  cmp     byte ptr [rcx+19h], 2
0x180014652  jb      short loc_1800146B6
0x180014654  mov     edx, 0Ch
0x180014659  jmp     short loc_1800146A3
0x18001465b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014662  cmp     rcx, rbp
0x180014665  jz      short loc_1800146B6
0x180014667  test    [rcx+1Ch], esi
0x18001466a  jz      short loc_1800146B6
0x18001466c  cmp     byte ptr [rcx+19h], 2
0x180014670  jb      short loc_1800146B6
0x180014672  mov     edx, 0Bh
0x180014677  jmp     short loc_1800146A3
0x180014679  mov     rcx, rdi; this
0x18001467c  call    ?GetOutboxConfiguration@CConfigAdvancedPage@@AEAAKXZ; CConfigAdvancedPage::GetOutboxConfiguration(void)
0x180014681  mov     ebx, eax
0x180014683  test    eax, eax
0x180014685  jz      short loc_1800146B6
0x180014687  mov     rcx, cs:WPP_GLOBAL_Control
0x18001468e  cmp     rcx, rbp
0x180014691  jz      short loc_1800146B6
0x180014693  test    [rcx+1Ch], esi
0x180014696  jz      short loc_1800146B6
0x180014698  cmp     byte ptr [rcx+19h], 2
0x18001469c  jb      short loc_1800146B6
0x18001469e  mov     edx, 0Dh
0x1800146a3  mov     rcx, [rcx+10h]
0x1800146a7  lea     r8, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids
0x1800146ae  mov     r9d, eax
0x1800146b1  call    WPP_SF_d
0x1800146b6  mov     eax, ebx
0x1800146b8  add     rsp, 28h
0x1800146bc  pop     rdi
0x1800146bd  pop     rsi
0x1800146be  pop     rbp
0x1800146bf  pop     rbx
0x1800146c0  retn
```
