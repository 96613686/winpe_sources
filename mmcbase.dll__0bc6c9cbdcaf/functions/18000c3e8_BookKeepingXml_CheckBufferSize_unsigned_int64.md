# BookKeepingXml::CheckBufferSize(unsigned __int64)

- ea: `0x18000c3e8`
- end: `0x18000c45e`
- name: `?CheckBufferSize@BookKeepingXml@@AEAAJ_K@Z`
- size: `118`
- prototype: `__int64 __fastcall(BookKeepingXml *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000bfcc`
- `0x18000c550`
- `0x18000c88c`
- `0x18000c914`

## callees

- `0x180008630`
- `0x18000c3e8`
- `0x18000c6e0`

## pseudocode

```c
__int64 __fastcall BookKeepingXml::CheckBufferSize(const WCHAR *this, unsigned __int64 a2)
{
  int v2; // ebx

  if ( a2 < 0x1000 )
  {
    v2 = 0;
    if ( *((_QWORD *)this + 4) <= a2 + 2LL * *((_QWORD *)this + 1030) + *((_QWORD *)this + 1030) )
    {
      v2 = BookKeepingXml::Flush(this);
      if ( v2 < 0
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          22,
          WPP_9741a39f05e03860cc0b7f50af82ce94_Traceguids,
          (unsigned int)v2);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000c3e8  push    rbx
0x18000c3ea  sub     rsp, 20h
0x18000c3ee  mov     r8, rcx
0x18000c3f1  cmp     rdx, 1000h
0x18000c3f8  jb      short loc_18000C401
0x18000c3fa  mov     ebx, 8007000Eh
0x18000c3ff  jmp     short loc_18000C456
0x18000c401  mov     rcx, [rcx+2030h]
0x18000c408  xor     ebx, ebx
0x18000c40a  lea     rax, [rdx+rcx*2]
0x18000c40e  add     rcx, rax
0x18000c411  cmp     [r8+20h], rcx
0x18000c415  ja      short loc_18000C456
0x18000c417  mov     rcx, r8; this
0x18000c41a  call    ?Flush@BookKeepingXml@@AEAAJXZ; BookKeepingXml::Flush(void)
0x18000c41f  mov     ebx, eax
0x18000c421  test    eax, eax
0x18000c423  jns     short loc_18000C456
0x18000c425  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c42c  lea     rax, WPP_GLOBAL_Control
0x18000c433  cmp     rcx, rax
0x18000c436  jz      short loc_18000C456
0x18000c438  cmp     byte ptr [rcx+19h], 2
0x18000c43c  jb      short loc_18000C456
0x18000c43e  mov     rcx, [rcx+10h]
0x18000c442  lea     r8, WPP_9741a39f05e03860cc0b7f50af82ce94_Traceguids
0x18000c449  mov     edx, 16h
0x18000c44e  mov     r9d, ebx
0x18000c451  call    WPP_SF_d
0x18000c456  mov     eax, ebx
0x18000c458  add     rsp, 20h
0x18000c45c  pop     rbx
0x18000c45d  retn
```
