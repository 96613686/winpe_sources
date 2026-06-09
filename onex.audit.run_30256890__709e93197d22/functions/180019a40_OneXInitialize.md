# OneXInitialize

- ea: `0x180019a40`
- end: `0x180019b56`
- name: `OneXInitialize`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005440`
- `0x180010ae0`
- `0x180019a40`
- `0x180019b60`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180019b16`
- `MobileNetworking!ReleaseWriteLock` at `0x180019b16`
- `MobileNetworking!AcquireWriteLock` at `0x180019ac0`
- `MobileNetworking!AcquireWriteLock` at `0x180019ac0`

## pseudocode

```c
__int64 OneXInitialize()
{
  _QWORD *v0; // rcx
  unsigned int v1; // eax
  unsigned int v2; // ebx

  v0 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
      v0 = WPP_GLOBAL_Control;
    }
    if ( v0 != &WPP_GLOBAL_Control && (*((_DWORD *)v0 + 17) & 0x100) != 0 )
      WPP_SF_(v0[7], 11, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids);
  }
  AcquireWriteLock(g_OneXInfo, g_OneXInfo, "OneXInitialize", 31);
  v1 = IncrementOneXRefCount();
  v2 = v1;
  if ( v1 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 12, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v1);
  ReleaseWriteLock(g_OneXInfo, g_OneXInfo, "OneXInitialize", 37);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180019a40  mov     [rsp+arg_0], rbx
0x180019a45  push    rdi
0x180019a46  sub     rsp, 20h
0x180019a4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019a51  lea     rdi, WPP_GLOBAL_Control
0x180019a58  cmp     rcx, rdi
0x180019a5b  jz      short loc_180019AA5
0x180019a5d  test    dword ptr [rcx+44h], 800h
0x180019a64  jz      short loc_180019A82
0x180019a66  mov     rcx, [rcx+38h]
0x180019a6a  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180019a71  mov     edx, 0Ah
0x180019a76  call    WPP_SF_
0x180019a7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180019a82  cmp     rcx, rdi
0x180019a85  jz      short loc_180019AA5
0x180019a87  test    dword ptr [rcx+44h], 100h
0x180019a8e  jz      short loc_180019AA5
0x180019a90  mov     rcx, [rcx+38h]
0x180019a94  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180019a9b  mov     edx, 0Bh
0x180019aa0  call    WPP_SF_
0x180019aa5  mov     r9d, 1Fh
0x180019aab  lea     r8, aOnexinitialize_0; "OneXInitialize"
0x180019ab2  lea     rdx, g_OneXInfo
0x180019ab9  lea     rcx, g_OneXInfo
0x180019ac0  call    cs:__imp_AcquireWriteLock
0x180019ac6  call    IncrementOneXRefCount
0x180019acb  mov     ebx, eax
0x180019acd  test    eax, eax
0x180019acf  jz      short loc_180019AFB
0x180019ad1  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ad8  cmp     rcx, rdi
0x180019adb  jz      short loc_180019AFB
0x180019add  test    byte ptr [rcx+44h], 1
0x180019ae1  jz      short loc_180019AFB
0x180019ae3  mov     rcx, [rcx+38h]
0x180019ae7  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180019aee  mov     edx, 0Ch
0x180019af3  mov     r9d, eax
0x180019af6  call    WPP_SF_d
0x180019afb  mov     r9d, 25h ; '%'
0x180019b01  lea     r8, aOnexinitialize_0; "OneXInitialize"
0x180019b08  lea     rdx, g_OneXInfo
0x180019b0f  lea     rcx, g_OneXInfo
0x180019b16  call    cs:__imp_ReleaseWriteLock
0x180019b1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b23  cmp     rcx, rdi
0x180019b26  jz      short loc_180019B49
0x180019b28  test    dword ptr [rcx+44h], 800h
0x180019b2f  jz      short loc_180019B49
0x180019b31  mov     rcx, [rcx+38h]
0x180019b35  lea     r8, WPP_5fb92ce32e3a364cc9ca876c215b1f83_Traceguids
0x180019b3c  mov     edx, 0Dh
0x180019b41  mov     r9d, ebx
0x180019b44  call    WPP_SF_D
0x180019b49  mov     eax, ebx
0x180019b4b  mov     rbx, [rsp+28h+arg_0]
0x180019b50  add     rsp, 20h
0x180019b54  pop     rdi
0x180019b55  retn
```
