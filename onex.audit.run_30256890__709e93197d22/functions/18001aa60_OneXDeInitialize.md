# OneXDeInitialize

- ea: `0x18001aa60`
- end: `0x18001abad`
- name: `OneXDeInitialize`
- size: `333`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005440`
- `0x180010ae0`
- `0x18001aa60`
- `0x18001ee7c`
- `0x18001f04c`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x18001ab6c`
- `MobileNetworking!ReleaseWriteLock` at `0x18001ab6c`
- `MobileNetworking!AcquireWriteLock` at `0x18001aae4`
- `MobileNetworking!AcquireWriteLock` at `0x18001aae4`

## pseudocode

```c
__int64 OneXDeInitialize()
{
  _QWORD *v0; // rcx
  unsigned int v1; // ebx
  unsigned int v2; // eax

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v0 = WPP_GLOBAL_Control;
    }
    if ( v0 != &WPP_GLOBAL_Control && (*((_DWORD *)v0 + 17) & 0x100) != 0 )
      WPP_SF_(v0[7], 15, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
  }
  AcquireWriteLock(g_OneXInfo, g_OneXInfo, "OneXDeInitialize", 66);
  if ( HIDWORD(qword_18003DD5C) )
  {
    RemoveSavedCredentials();
    v2 = DecrementOneXRefCount();
    v1 = v2;
    if ( v2 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 17, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v2);
  }
  else
  {
    v1 = 21;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 16, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
  }
  ReleaseWriteLock(g_OneXInfo, g_OneXInfo, "OneXDeInitialize", 82);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x18001aa60  mov     [rsp+arg_0], rbx
0x18001aa65  mov     [rsp+arg_8], rsi
0x18001aa6a  push    rdi
0x18001aa6b  sub     rsp, 20h
0x18001aa6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa76  lea     rdi, WPP_GLOBAL_Control
0x18001aa7d  lea     rsi, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x18001aa84  cmp     rcx, rdi
0x18001aa87  jz      short loc_18001AAC9
0x18001aa89  test    dword ptr [rcx+44h], 800h
0x18001aa90  jz      short loc_18001AAAA
0x18001aa92  mov     rcx, [rcx+38h]
0x18001aa96  mov     edx, 0Eh
0x18001aa9b  mov     r8, rsi
0x18001aa9e  call    WPP_SF_
0x18001aaa3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aaaa  cmp     rcx, rdi
0x18001aaad  jz      short loc_18001AAC9
0x18001aaaf  test    dword ptr [rcx+44h], 100h
0x18001aab6  jz      short loc_18001AAC9
0x18001aab8  mov     rcx, [rcx+38h]
0x18001aabc  mov     edx, 0Fh
0x18001aac1  mov     r8, rsi
0x18001aac4  call    WPP_SF_
0x18001aac9  mov     r9d, 42h ; 'B'
0x18001aacf  lea     r8, aOnexdeinitiali_0; "OneXDeInitialize"
0x18001aad6  lea     rdx, g_OneXInfo
0x18001aadd  lea     rcx, g_OneXInfo
0x18001aae4  call    cs:__imp_AcquireWriteLock
0x18001aaea  cmp     dword ptr cs:qword_18003DD5C+4, 0
0x18001aaf1  jnz     short loc_18001AB1B
0x18001aaf3  mov     ebx, 15h
0x18001aaf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aaff  cmp     rcx, rdi
0x18001ab02  jz      short loc_18001AB51
0x18001ab04  test    byte ptr [rcx+44h], 1
0x18001ab08  jz      short loc_18001AB51
0x18001ab0a  mov     rcx, [rcx+38h]
0x18001ab0e  lea     edx, [rbx-5]
0x18001ab11  mov     r8, rsi
0x18001ab14  call    WPP_SF_
0x18001ab19  jmp     short loc_18001AB51
0x18001ab1b  call    RemoveSavedCredentials
0x18001ab20  call    DecrementOneXRefCount
0x18001ab25  mov     ebx, eax
0x18001ab27  test    eax, eax
0x18001ab29  jz      short loc_18001AB51
0x18001ab2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab32  cmp     rcx, rdi
0x18001ab35  jz      short loc_18001AB51
0x18001ab37  test    byte ptr [rcx+44h], 1
0x18001ab3b  jz      short loc_18001AB51
0x18001ab3d  mov     rcx, [rcx+38h]
0x18001ab41  mov     edx, 11h
0x18001ab46  mov     r9d, eax
0x18001ab49  mov     r8, rsi
0x18001ab4c  call    WPP_SF_d
0x18001ab51  mov     r9d, 52h ; 'R'
0x18001ab57  lea     r8, aOnexdeinitiali_0; "OneXDeInitialize"
0x18001ab5e  lea     rdx, g_OneXInfo
0x18001ab65  lea     rcx, g_OneXInfo
0x18001ab6c  call    cs:__imp_ReleaseWriteLock
0x18001ab72  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab79  cmp     rcx, rdi
0x18001ab7c  jz      short loc_18001AB9B
0x18001ab7e  test    dword ptr [rcx+44h], 800h
0x18001ab85  jz      short loc_18001AB9B
0x18001ab87  mov     rcx, [rcx+38h]
0x18001ab8b  mov     edx, 12h
0x18001ab90  mov     r9d, ebx
0x18001ab93  mov     r8, rsi
0x18001ab96  call    WPP_SF_D
0x18001ab9b  mov     rsi, [rsp+28h+arg_8]
0x18001aba0  mov     eax, ebx
0x18001aba2  mov     rbx, [rsp+28h+arg_0]
0x18001aba7  add     rsp, 20h
0x18001abab  pop     rdi
0x18001abac  retn
```
