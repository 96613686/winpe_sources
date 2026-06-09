# CConfigAdvancedPage::GetOutboxConfiguration(void)

- ea: `0x1800144e8`
- end: `0x1800145ab`
- name: `?GetOutboxConfiguration@CConfigAdvancedPage@@AEAAKXZ`
- size: `195`
- prototype: `unsigned int __fastcall(CConfigAdvancedPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800145b4`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x1800144e8`

## import_xrefs

- `FXSAPI!FaxGetOutboxConfiguration` at `0x18001453a`
- `FXSAPI!FaxGetOutboxConfiguration` at `0x18001453a`
- `KERNEL32!GetLastError` at `0x180014544`
- `KERNEL32!GetLastError` at `0x180014544`

## pseudocode

```c
__int64 __fastcall CConfigAdvancedPage::GetOutboxConfiguration(CConfigAdvancedPage *this)
{
  DWORD v2; // ebx
  char *v3; // rdi
  DWORD LastError; // eax

  v2 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids);
  }
  v3 = (char *)this + 568;
  if ( !(unsigned int)FaxGetOutboxConfiguration(*((_QWORD *)this + 4), (char *)this + 568) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids, LastError);
    }
  }
  if ( *(_DWORD *)(*(_QWORD *)v3 + 12LL) > 0x63u )
    *(_DWORD *)(*(_QWORD *)v3 + 12LL) = 99;
  if ( *(_DWORD *)(*(_QWORD *)v3 + 16LL) > 0x3E7u )
    *(_DWORD *)(*(_QWORD *)v3 + 16LL) = 999;
  return v2;
}

```

## disassembly

```asm
0x1800144e8  push    rbx
0x1800144ea  push    rsi
0x1800144eb  push    rdi
0x1800144ec  push    r14
0x1800144ee  sub     rsp, 28h
0x1800144f2  mov     rsi, rcx
0x1800144f5  xor     ebx, ebx
0x1800144f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800144fe  lea     r14, WPP_GLOBAL_Control
0x180014505  cmp     rcx, r14
0x180014508  jz      short loc_18001452C
0x18001450a  test    dword ptr [rcx+1Ch], 100h
0x180014511  jz      short loc_18001452C
0x180014513  cmp     byte ptr [rcx+19h], 5
0x180014517  jb      short loc_18001452C
0x180014519  mov     rcx, [rcx+10h]
0x18001451d  lea     edx, [rbx+14h]
0x180014520  lea     r8, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids
0x180014527  call    WPP_SF_
0x18001452c  mov     rcx, [rsi+20h]
0x180014530  lea     rdi, [rsi+238h]
0x180014537  mov     rdx, rdi
0x18001453a  call    cs:__imp_FaxGetOutboxConfiguration
0x180014540  test    eax, eax
0x180014542  jnz     short loc_18001457F
0x180014544  call    cs:__imp_GetLastError
0x18001454a  mov     ebx, eax
0x18001454c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014553  cmp     rcx, r14
0x180014556  jz      short loc_18001457F
0x180014558  test    dword ptr [rcx+1Ch], 100h
0x18001455f  jz      short loc_18001457F
0x180014561  cmp     byte ptr [rcx+19h], 2
0x180014565  jb      short loc_18001457F
0x180014567  mov     rcx, [rcx+10h]
0x18001456b  lea     r8, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids
0x180014572  mov     edx, 15h
0x180014577  mov     r9d, eax
0x18001457a  call    WPP_SF_d
0x18001457f  mov     rax, [rdi]
0x180014582  cmp     dword ptr [rax+0Ch], 63h ; 'c'
0x180014586  jbe     short loc_18001458F
0x180014588  mov     dword ptr [rax+0Ch], 63h ; 'c'
0x18001458f  mov     rax, [rdi]
0x180014592  mov     ecx, 3E7h
0x180014597  cmp     [rax+10h], ecx
0x18001459a  jbe     short loc_18001459F
0x18001459c  mov     [rax+10h], ecx
0x18001459f  mov     eax, ebx
0x1800145a1  add     rsp, 28h
0x1800145a5  pop     r14
0x1800145a7  pop     rdi
0x1800145a8  pop     rsi
0x1800145a9  pop     rbx
0x1800145aa  retn
```
