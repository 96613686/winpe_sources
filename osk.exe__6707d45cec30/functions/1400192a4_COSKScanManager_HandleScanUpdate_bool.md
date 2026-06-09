# COSKScanManager::HandleScanUpdate(bool)

- ea: `0x1400192a4`
- end: `0x1400193aa`
- name: `?HandleScanUpdate@COSKScanManager@@AEAAX_N@Z`
- size: `262`
- prototype: `void __fastcall(COSKScanManager *__hidden this, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400135c0`
- `0x140019ae8`

## callees

- `0x14000dd8c`
- `0x1400121a0`
- `0x14001274c`
- `0x140019194`
- `0x1400192a4`
- `0x1400193b0`
- `0x1400195f4`
- `0x1400197b0`
- `0x140019ae8`
- `0x140025d70`

## pseudocode

```c
void __fastcall COSKScanManager::HandleScanUpdate(COSKScanManager *this, char a2, __int64 a3)
{
  int v5; // ecx
  int v6; // ecx
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+30h] [rbp-28h] BYREF

  if ( !*((_BYTE *)this + 112) )
  {
    *((_BYTE *)this + 112) = 1;
    if ( (Microsoft_Windows_oskEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer((__int64)this, (const EVENT_DESCRIPTOR *)ScanTargetTransition, a3, 1u, &v7);
    if ( *((_DWORD *)this + 29) == *((_DWORD *)this + 30) )
    {
      if ( COSKKeyboardManager::IsNavKeyboardVisible() || *((_DWORD *)this + 22) != 1 )
      {
        if ( *((_DWORD *)this + 22) != 2 )
        {
          COSKScanManager::ClearOSKRowHighlight(this);
          *((_DWORD *)this + 34) = -1;
          COSKScanManager::SetScanState(this, 0);
          *((_DWORD *)this + 29) = 0;
LABEL_20:
          *((_BYTE *)this + 112) = 0;
          return;
        }
        *((_DWORD *)this + 22) = 1;
      }
      else
      {
        *((_DWORD *)this + 22) = 0;
      }
      *((_DWORD *)this + 29) = 0;
    }
    v5 = *((_DWORD *)this + 22);
    if ( v5 )
    {
      v6 = v5 - 1;
      if ( v6 )
      {
        if ( v6 == 1 )
          COSKScanManager::HighlightKey(this);
      }
      else
      {
        COSKScanManager::HighlightBlock(this);
      }
    }
    else
    {
      COSKScanManager::HighlightRow(this);
    }
    if ( a2 )
      COSKKeyboardManager::MakeSound(*(COSKKeyboardManager **)this, 2101);
    goto LABEL_20;
  }
}

```

## disassembly

```asm
0x1400192a4  mov     [rsp+arg_8], rbx
0x1400192a9  push    rdi
0x1400192aa  sub     rsp, 50h
0x1400192ae  mov     rax, cs:__security_cookie
0x1400192b5  xor     rax, rsp
0x1400192b8  mov     [rsp+58h+var_18], rax
0x1400192bd  cmp     byte ptr [rcx+70h], 0
0x1400192c1  mov     dil, dl
0x1400192c4  mov     rbx, rcx
0x1400192c7  jnz     loc_140019392
0x1400192cd  mov     byte ptr [rcx+70h], 1
0x1400192d1  test    cs:Microsoft_Windows_oskEnableBits, 1
0x1400192d8  jz      short loc_1400192F6
0x1400192da  lea     rax, [rsp+58h+var_28]
0x1400192df  mov     r9d, 1
0x1400192e5  lea     rdx, ScanTargetTransition
0x1400192ec  mov     [rsp+58h+var_38], rax
0x1400192f1  call    McGenEventWrite_EventWriteTransfer
0x1400192f6  mov     eax, [rbx+78h]
0x1400192f9  cmp     [rbx+74h], eax
0x1400192fc  jnz     short loc_14001931B
0x1400192fe  call    ?IsNavKeyboardVisible@COSKKeyboardManager@@SA_NXZ; COSKKeyboardManager::IsNavKeyboardVisible(void)
0x140019303  test    al, al
0x140019305  jnz     short loc_140019336
0x140019307  cmp     dword ptr [rbx+58h], 1
0x14001930b  jnz     short loc_140019336
0x14001930d  mov     dword ptr [rbx+58h], 0
0x140019314  mov     dword ptr [rbx+74h], 0
0x14001931b  mov     ecx, [rbx+58h]
0x14001931e  test    ecx, ecx
0x140019320  jz      short loc_140019374
0x140019322  sub     ecx, 1
0x140019325  jz      short loc_14001936A
0x140019327  cmp     ecx, 1
0x14001932a  jnz     short loc_14001937C
0x14001932c  mov     rcx, rbx; this
0x14001932f  call    ?HighlightKey@COSKScanManager@@AEAAXXZ; COSKScanManager::HighlightKey(void)
0x140019334  jmp     short loc_14001937C
0x140019336  cmp     dword ptr [rbx+58h], 2
0x14001933a  jnz     short loc_140019345
0x14001933c  mov     dword ptr [rbx+58h], 1
0x140019343  jmp     short loc_140019314
0x140019345  mov     rcx, rbx; this
0x140019348  call    ?ClearOSKRowHighlight@COSKScanManager@@AEAAXXZ; COSKScanManager::ClearOSKRowHighlight(void)
0x14001934d  xor     edx, edx; bool
0x14001934f  mov     dword ptr [rbx+88h], 0FFFFFFFFh
0x140019359  mov     rcx, rbx; this
0x14001935c  call    ?SetScanState@COSKScanManager@@AEAAX_N@Z; COSKScanManager::SetScanState(bool)
0x140019361  mov     dword ptr [rbx+74h], 0
0x140019368  jmp     short loc_14001938E
0x14001936a  mov     rcx, rbx; this
0x14001936d  call    ?HighlightBlock@COSKScanManager@@AEAAXXZ; COSKScanManager::HighlightBlock(void)
0x140019372  jmp     short loc_14001937C
0x140019374  mov     rcx, rbx; this
0x140019377  call    ?HighlightRow@COSKScanManager@@AEAAXXZ; COSKScanManager::HighlightRow(void)
0x14001937c  test    dil, dil
0x14001937f  jz      short loc_14001938E
0x140019381  mov     rcx, [rbx]; this
0x140019384  mov     edx, 835h; int
0x140019389  call    ?MakeSound@COSKKeyboardManager@@QEAAXH@Z; COSKKeyboardManager::MakeSound(int)
0x14001938e  mov     byte ptr [rbx+70h], 0
0x140019392  mov     rcx, [rsp+58h+var_18]
0x140019397  xor     rcx, rsp; StackCookie
0x14001939a  call    __security_check_cookie
0x14001939f  mov     rbx, [rsp+58h+arg_8]
0x1400193a4  add     rsp, 50h
0x1400193a8  pop     rdi
0x1400193a9  retn
```
