# CConfigAdvancedPage::SetArchiveSettings(void)

- ea: `0x180015018`
- end: `0x180015146`
- name: `?SetArchiveSettings@CConfigAdvancedPage@@AEBAKXZ`
- size: `302`
- prototype: `unsigned int __fastcall(CConfigAdvancedPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014920`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x180015018`

## import_xrefs

- `FXSAPI!FaxSetGeneralConfiguration` at `0x1800150dc`
- `FXSAPI!FaxSetGeneralConfiguration` at `0x1800150dc`
- `FXSAPI!FaxGetGeneralConfiguration` at `0x180015070`
- `FXSAPI!FaxGetGeneralConfiguration` at `0x180015070`
- `FXSAPI!FaxFreeBuffer` at `0x180015134`
- `FXSAPI!FaxFreeBuffer` at `0x180015134`
- `KERNEL32!GetLastError` at `0x18001507a`
- `KERNEL32!GetLastError` at `0x1800150ef`
- `KERNEL32!GetLastError` at `0x18001507a`
- `KERNEL32!GetLastError` at `0x1800150ef`

## pseudocode

```c
__int64 __fastcall CConfigAdvancedPage::SetArchiveSettings(CConfigAdvancedPage *this)
{
  DWORD LastError; // eax
  DWORD v3; // edi
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rbx
  int v7; // eax
  LPVOID Buffer; // [rsp+50h] [rbp+8h] BYREF

  Buffer = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids);
  }
  if ( (unsigned int)FaxGetGeneralConfiguration(*((_QWORD *)this + 4), 0, &Buffer) )
  {
    v3 = 0;
    *((_DWORD *)Buffer + 1) = *((_DWORD *)this + 140);
    v6 = *((_QWORD *)Buffer + 1);
    *((_QWORD *)Buffer + 1) = (char *)this + 40;
    v7 = FaxSetGeneralConfiguration(*((_QWORD *)this + 4), 0, Buffer);
    *((_QWORD *)Buffer + 1) = v6;
    if ( !v7 )
    {
      LastError = GetLastError();
      v3 = LastError;
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v5 = 19;
        goto LABEL_15;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 18;
LABEL_15:
      WPP_SF_d(v4[2], v5, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids, LastError);
    }
  }
  if ( Buffer )
    FaxFreeBuffer(Buffer);
  return v3;
}

```

## disassembly

```asm
0x180015018  push    rbx
0x18001501a  push    rsi
0x18001501b  push    rdi
0x18001501c  push    r14
0x18001501e  sub     rsp, 28h
0x180015022  mov     rsi, rcx
0x180015025  mov     [rsp+48h+Buffer], 0
0x18001502e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015035  lea     r14, WPP_GLOBAL_Control
0x18001503c  cmp     rcx, r14
0x18001503f  jz      short loc_180015065
0x180015041  test    dword ptr [rcx+1Ch], 100h
0x180015048  jz      short loc_180015065
0x18001504a  cmp     byte ptr [rcx+19h], 5
0x18001504e  jb      short loc_180015065
0x180015050  mov     rcx, [rcx+10h]
0x180015054  lea     r8, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids
0x18001505b  mov     edx, 11h
0x180015060  call    WPP_SF_
0x180015065  mov     rcx, [rsi+20h]
0x180015069  lea     r8, [rsp+48h+Buffer]
0x18001506e  xor     edx, edx
0x180015070  call    cs:__imp_FaxGetGeneralConfiguration
0x180015076  test    eax, eax
0x180015078  jnz     short loc_1800150B0
0x18001507a  call    cs:__imp_GetLastError
0x180015080  mov     edi, eax
0x180015082  mov     rcx, cs:WPP_GLOBAL_Control
0x180015089  cmp     rcx, r14
0x18001508c  jz      loc_18001512A
0x180015092  test    dword ptr [rcx+1Ch], 100h
0x180015099  jz      loc_18001512A
0x18001509f  cmp     byte ptr [rcx+19h], 2
0x1800150a3  jb      loc_18001512A
0x1800150a9  mov     edx, 12h
0x1800150ae  jmp     short loc_180015117
0x1800150b0  mov     rax, [rsp+48h+Buffer]
0x1800150b5  xor     edx, edx
0x1800150b7  mov     ecx, [rsi+230h]
0x1800150bd  xor     edi, edi
0x1800150bf  mov     [rax+4], ecx
0x1800150c2  lea     rax, [rsi+28h]
0x1800150c6  mov     rcx, [rsp+48h+Buffer]
0x1800150cb  mov     rbx, [rcx+8]
0x1800150cf  mov     [rcx+8], rax
0x1800150d3  mov     r8, [rsp+48h+Buffer]
0x1800150d8  mov     rcx, [rsi+20h]
0x1800150dc  call    cs:__imp_FaxSetGeneralConfiguration
0x1800150e2  mov     rcx, [rsp+48h+Buffer]
0x1800150e7  mov     [rcx+8], rbx
0x1800150eb  test    eax, eax
0x1800150ed  jnz     short loc_18001512A
0x1800150ef  call    cs:__imp_GetLastError
0x1800150f5  mov     edi, eax
0x1800150f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150fe  cmp     rcx, r14
0x180015101  jz      short loc_18001512A
0x180015103  test    dword ptr [rcx+1Ch], 100h
0x18001510a  jz      short loc_18001512A
0x18001510c  cmp     byte ptr [rcx+19h], 2
0x180015110  jb      short loc_18001512A
0x180015112  mov     edx, 13h
0x180015117  mov     rcx, [rcx+10h]
0x18001511b  lea     r8, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids
0x180015122  mov     r9d, eax
0x180015125  call    WPP_SF_d
0x18001512a  mov     rcx, [rsp+48h+Buffer]; Buffer
0x18001512f  test    rcx, rcx
0x180015132  jz      short loc_18001513A
0x180015134  call    cs:__imp_FaxFreeBuffer
0x18001513a  mov     eax, edi
0x18001513c  add     rsp, 28h
0x180015140  pop     r14
0x180015142  pop     rdi
0x180015143  pop     rsi
0x180015144  pop     rbx
0x180015145  retn
```
