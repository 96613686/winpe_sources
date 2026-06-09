# CConfigAdvancedPage::SetOutboxConfiguration(void)

- ea: `0x18001514c`
- end: `0x1800151f7`
- name: `?SetOutboxConfiguration@CConfigAdvancedPage@@AEBAKXZ`
- size: `171`
- prototype: `unsigned int __fastcall(CConfigAdvancedPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014920`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18001514c`

## import_xrefs

- `FXSAPI!FaxSetOutboxConfiguration` at `0x1800151a0`
- `FXSAPI!FaxSetOutboxConfiguration` at `0x1800151a0`
- `KERNEL32!GetLastError` at `0x1800151aa`
- `KERNEL32!GetLastError` at `0x1800151aa`

## pseudocode

```c
__int64 __fastcall CConfigAdvancedPage::SetOutboxConfiguration(CConfigAdvancedPage *this)
{
  DWORD v2; // ebx
  DWORD LastError; // eax

  v2 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids);
  }
  if ( !(unsigned int)FaxSetOutboxConfiguration(*((_QWORD *)this + 4), *((_QWORD *)this + 71)) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids, LastError);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001514c  mov     [rsp+arg_0], rbx
0x180015151  mov     [rsp+arg_8], rbp
0x180015156  push    rdi
0x180015157  sub     rsp, 20h
0x18001515b  mov     rdi, rcx
0x18001515e  xor     ebx, ebx
0x180015160  mov     rcx, cs:WPP_GLOBAL_Control
0x180015167  lea     rbp, WPP_GLOBAL_Control
0x18001516e  cmp     rcx, rbp
0x180015171  jz      short loc_180015195
0x180015173  test    dword ptr [rcx+1Ch], 100h
0x18001517a  jz      short loc_180015195
0x18001517c  cmp     byte ptr [rcx+19h], 5
0x180015180  jb      short loc_180015195
0x180015182  mov     rcx, [rcx+10h]
0x180015186  lea     edx, [rbx+16h]
0x180015189  lea     r8, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids
0x180015190  call    WPP_SF_
0x180015195  mov     rdx, [rdi+238h]
0x18001519c  mov     rcx, [rdi+20h]
0x1800151a0  call    cs:__imp_FaxSetOutboxConfiguration
0x1800151a6  test    eax, eax
0x1800151a8  jnz     short loc_1800151E5
0x1800151aa  call    cs:__imp_GetLastError
0x1800151b0  mov     ebx, eax
0x1800151b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800151b9  cmp     rcx, rbp
0x1800151bc  jz      short loc_1800151E5
0x1800151be  test    dword ptr [rcx+1Ch], 100h
0x1800151c5  jz      short loc_1800151E5
0x1800151c7  cmp     byte ptr [rcx+19h], 2
0x1800151cb  jb      short loc_1800151E5
0x1800151cd  mov     rcx, [rcx+10h]
0x1800151d1  lea     r8, WPP_d1a7ef1228df3ccd06e3100a081ff2e3_Traceguids
0x1800151d8  mov     edx, 17h
0x1800151dd  mov     r9d, eax
0x1800151e0  call    WPP_SF_d
0x1800151e5  mov     rbp, [rsp+28h+arg_8]
0x1800151ea  mov     eax, ebx
0x1800151ec  mov     rbx, [rsp+28h+arg_0]
0x1800151f1  add     rsp, 20h
0x1800151f5  pop     rdi
0x1800151f6  retn
```
