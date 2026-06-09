# CscForceFcbStoreEntryClosed

- ea: `0x14004fca4`
- end: `0x14004fe50`
- name: `CscForceFcbStoreEntryClosed`
- size: `428`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `8`
- tags: ``

## callers

- `0x14004fe58`
- `0x140062b70`
- `0x140074c74`
- `0x1400837e0`

## callees

- `0x14000eef0`
- `0x140016a04`
- `0x140018930`
- `0x14001c198`
- `0x14001d110`
- `0x14004fca4`
- `0x140074ff4`
- `0x140088580`

## import_xrefs

- `rdbss!RxIterateOnFcbOpens` at `0x14004fd4a`
- `rdbss!RxIterateOnFcbOpens` at `0x14004fd4a`

## pseudocode

```c
__int64 __fastcall CscForceFcbStoreEntryClosed(__int64 a1, char a2)
{
  __int64 v2; // rbp
  __int64 v5; // r15
  __int64 Timer_high; // rdx
  __int64 v7; // rdi
  __int64 v8; // r8
  unsigned int v9; // eax
  unsigned int v10; // ebx
  int v11; // esi
  __int64 v13; // [rsp+70h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  v5 = 0;
  v7 = CscFcbContext(v2);
  v13 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (Timer_high & 0x40) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 173, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v2);
  }
  if ( v7 && (!*(_BYTE *)(a1 + 32) || *(_QWORD *)(v7 + 56)) )
  {
    v13 = 0;
    BYTE4(v13) = a2;
    v9 = RxIterateOnFcbOpens(a1, v2, CscSrvOpenCloseStoreStateCallBack, 0, &v13, 0);
    v10 = v9;
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( (Timer_high & 0x40) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 174, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v9);
      }
      v11 = 9781;
    }
    else
    {
      Timer_high = (unsigned int)v13;
      v5 = *(_QWORD *)(v7 + 56);
      v11 = 0;
      if ( (_DWORD)v13 )
        CscNotifyReportChange(a1, (unsigned int)v13, 3);
      if ( v5 )
        CscClearFcbStoreEntry(v2);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( (Timer_high & 0x40) != 0 )
          WPP_SF_qqqd(WPP_GLOBAL_Control->AttachedDevice, 175, v8, v5, v2);
      }
      *(_DWORD *)(v7 + 4) &= ~0x20u;
    }
  }
  else
  {
    v10 = 0;
    v11 = 9764;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Ddqq(WPP_GLOBAL_Control->AttachedDevice, Timer_high, v8, v10, v11, v2, v5);
  return v10;
}

```

## disassembly

```asm
0x14004fca4  mov     [rsp+arg_8], rbx
0x14004fca9  mov     [rsp+arg_10], rbp
0x14004fcae  push    rsi
0x14004fcaf  push    rdi
0x14004fcb0  push    r12
0x14004fcb2  push    r14
0x14004fcb4  push    r15
0x14004fcb6  sub     rsp, 40h
0x14004fcba  mov     rbp, [rcx+38h]
0x14004fcbe  mov     r14, rcx
0x14004fcc1  mov     rcx, rbp
0x14004fcc4  mov     bl, dl
0x14004fcc6  call    CscFcbContext
0x14004fccb  xor     r15d, r15d
0x14004fcce  mov     rdi, rax
0x14004fcd1  mov     [rsp+68h+arg_0], r15
0x14004fcd6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fcdd  lea     rsi, WPP_GLOBAL_Control
0x14004fce4  cmp     rcx, rsi
0x14004fce7  jz      short loc_14004FD09
0x14004fce9  mov     edx, [rcx+2Ch]
0x14004fcec  test    dl, 40h
0x14004fcef  jz      short loc_14004FD09
0x14004fcf1  mov     rcx, [rcx+18h]
0x14004fcf5  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14004fcfc  mov     edx, 0ADh
0x14004fd01  mov     r9, rbp
0x14004fd04  call    WPP_SF_q
0x14004fd09  test    rdi, rdi
0x14004fd0c  jz      loc_14004FDF9
0x14004fd12  cmp     [r14+20h], r15b
0x14004fd16  jz      short loc_14004FD22
0x14004fd18  cmp     [rdi+38h], r15
0x14004fd1c  jz      loc_14004FDF9
0x14004fd22  lea     rax, [rsp+68h+arg_0]
0x14004fd27  mov     [rsp+68h+arg_0], r15
0x14004fd2c  mov     byte ptr [rsp+68h+var_40], r15b
0x14004fd31  lea     r8, CscSrvOpenCloseStoreStateCallBack
0x14004fd38  xor     r9d, r9d
0x14004fd3b  mov     [rsp+68h+var_48], rax
0x14004fd40  mov     rdx, rbp
0x14004fd43  mov     byte ptr [rsp+68h+arg_0+4], bl
0x14004fd47  mov     rcx, r14
0x14004fd4a  call    cs:__imp_RxIterateOnFcbOpens
0x14004fd51  nop     dword ptr [rax+rax+00h]
0x14004fd56  mov     ebx, eax
0x14004fd58  test    eax, eax
0x14004fd5a  jz      short loc_14004FD8F
0x14004fd5c  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fd63  cmp     rcx, rsi
0x14004fd66  jz      short loc_14004FD88
0x14004fd68  mov     edx, [rcx+2Ch]
0x14004fd6b  test    dl, 40h
0x14004fd6e  jz      short loc_14004FD88
0x14004fd70  mov     rcx, [rcx+18h]
0x14004fd74  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x14004fd7b  mov     edx, 0AEh
0x14004fd80  mov     r9d, eax
0x14004fd83  call    WPP_SF_d
0x14004fd88  mov     esi, 2635h
0x14004fd8d  jmp     short loc_14004FE00
0x14004fd8f  mov     edx, dword ptr [rsp+68h+arg_0]
0x14004fd93  xor     r12d, r12d
0x14004fd96  mov     r15, [rdi+38h]
0x14004fd9a  xor     esi, esi
0x14004fd9c  test    edx, edx
0x14004fd9e  jz      short loc_14004FDAD
0x14004fda0  lea     r8d, [r12+3]
0x14004fda5  mov     rcx, r14
0x14004fda8  call    CscNotifyReportChange
0x14004fdad  test    r15, r15
0x14004fdb0  jz      short loc_14004FDBD
0x14004fdb2  mov     rcx, rbp
0x14004fdb5  call    CscClearFcbStoreEntry
0x14004fdba  mov     r12d, eax
0x14004fdbd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fdc4  lea     r14, WPP_GLOBAL_Control
0x14004fdcb  cmp     rcx, r14
0x14004fdce  jz      short loc_14004FDF3
0x14004fdd0  mov     edx, [rcx+2Ch]
0x14004fdd3  test    dl, 40h
0x14004fdd6  jz      short loc_14004FDF3
0x14004fdd8  mov     rcx, [rcx+18h]
0x14004fddc  mov     edx, 0AFh
0x14004fde1  mov     dword ptr [rsp+68h+var_38], r12d
0x14004fde6  mov     r9, r15
0x14004fde9  mov     [rsp+68h+var_48], rbp
0x14004fdee  call    WPP_SF_qqqd
0x14004fdf3  and     dword ptr [rdi+4], 0FFFFFFDFh
0x14004fdf7  jmp     short loc_14004FE07
0x14004fdf9  xor     ebx, ebx
0x14004fdfb  mov     esi, 2624h
0x14004fe00  lea     r14, WPP_GLOBAL_Control
0x14004fe07  mov     rcx, cs:WPP_GLOBAL_Control
0x14004fe0e  cmp     rcx, r14
0x14004fe11  jz      short loc_14004FE34
0x14004fe13  mov     eax, [rcx+2Ch]
0x14004fe16  test    al, 20h
0x14004fe18  jz      short loc_14004FE34
0x14004fe1a  mov     rcx, [rcx+18h]
0x14004fe1e  mov     r9d, ebx
0x14004fe21  mov     [rsp+68h+var_38], r15
0x14004fe26  mov     [rsp+68h+var_40], rbp
0x14004fe2b  mov     dword ptr [rsp+68h+var_48], esi
0x14004fe2f  call    WPP_SF_Ddqq
0x14004fe34  lea     r11, [rsp+68h+var_28]
0x14004fe39  mov     eax, ebx
0x14004fe3b  mov     rbx, [r11+38h]
0x14004fe3f  mov     rbp, [r11+40h]
0x14004fe43  mov     rsp, r11
0x14004fe46  pop     r15
0x14004fe48  pop     r14
0x14004fe4a  pop     r12
0x14004fe4c  pop     rdi
0x14004fe4d  pop     rsi
0x14004fe4e  retn
```
