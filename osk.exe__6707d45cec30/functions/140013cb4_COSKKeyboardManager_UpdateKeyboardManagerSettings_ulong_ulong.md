# COSKKeyboardManager::UpdateKeyboardManagerSettings(ulong,ulong)

- ea: `0x140013cb4`
- end: `0x140013dfa`
- name: `?UpdateKeyboardManagerSettings@COSKKeyboardManager@@AEAAXKK@Z`
- size: `326`
- prototype: `void __fastcall(COSKKeyboardManager *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140012780`

## callees

- `0x1400114f8`
- `0x140013004`
- `0x140013b1c`
- `0x140013cb4`
- `0x140013eac`

## pseudocode

```c
void __fastcall COSKKeyboardManager::UpdateKeyboardManagerSettings(COSKKeyboardManager *this, int a2, int a3)
{
  COSKKeyboardManager *v3; // rbx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx

  v3 = COSKKeyboardManager::s_pCOSKKeyboardManager;
  LOBYTE(this) = a3 != 0;
  if ( (unsigned int)(a2 - 2) <= 1 )
  {
    COSKKeyboardManager::ResizeKeyboards(COSKKeyboardManager::s_pCOSKKeyboardManager);
  }
  else
  {
    switch ( a2 )
    {
      case 12:
        if ( *((_QWORD *)COSKKeyboardManager::s_pCOSKKeyboardManager + 29)
          && *((_BYTE *)COSKKeyboardManager::s_pCOSKKeyboardManager + 223) != (_BYTE)this )
        {
          *((_BYTE *)COSKKeyboardManager::s_pCOSKKeyboardManager + 223) = (_BYTE)this;
LABEL_16:
          COSKKeyboardManager::HandleUpdateKeyboardUI(v3);
        }
        break;
      case 14:
        if ( *((_BYTE *)COSKKeyboardManager::s_pCOSKKeyboardManager + 221) == (_BYTE)this )
          return;
        *((_BYTE *)COSKKeyboardManager::s_pCOSKKeyboardManager + 221) = (_BYTE)this;
        if ( (Microsoft_Windows_oskEnableBits & 1) != 0 )
          McTemplateU0d_EventWriteTransfer(this, SetNumpadVisibility, (unsigned __int8)this);
        goto LABEL_16;
      case 18:
        if ( *((_BYTE *)COSKKeyboardManager::s_pCOSKKeyboardManager + 243) == (_BYTE)this )
          return;
        *((_BYTE *)COSKKeyboardManager::s_pCOSKKeyboardManager + 243) = (_BYTE)this;
        goto LABEL_16;
      case 15:
        if ( *((_BYTE *)COSKKeyboardManager::s_pCOSKKeyboardManager + 241) == (_BYTE)this )
          return;
        *((_BYTE *)COSKKeyboardManager::s_pCOSKKeyboardManager + 241) = (_BYTE)this;
        goto LABEL_16;
      default:
        v4 = a2 - 4;
        if ( v4 )
        {
          v5 = v4 - 1;
          if ( v5 )
          {
            v6 = v5 - 1;
            if ( v6 )
            {
              v7 = v6 - 1;
              if ( v7 )
              {
                v8 = v7 - 1;
                if ( v8 )
                {
                  v9 = v8 - 1;
                  if ( v9 )
                  {
                    v10 = v9 - 1;
                    if ( v10 )
                    {
                      if ( v10 == 1 )
                        *((_DWORD *)COSKKeyboardManager::s_pCOSKKeyboardManager + 47) = a3;
                    }
                    else
                    {
                      *((_DWORD *)COSKKeyboardManager::s_pCOSKKeyboardManager + 46) = (unsigned __int8)this;
                    }
                  }
                  else
                  {
                    *((_DWORD *)COSKKeyboardManager::s_pCOSKKeyboardManager + 45) = (unsigned __int8)this;
                  }
                }
                else
                {
                  *((_DWORD *)COSKKeyboardManager::s_pCOSKKeyboardManager + 44) = (unsigned __int8)this;
                }
              }
              else
              {
                *((_DWORD *)COSKKeyboardManager::s_pCOSKKeyboardManager + 43) = a3;
              }
            }
            else
            {
              *((_DWORD *)COSKKeyboardManager::s_pCOSKKeyboardManager + 42) = a3;
            }
          }
          else
          {
            *((_DWORD *)COSKKeyboardManager::s_pCOSKKeyboardManager + 41) = a3;
          }
        }
        else
        {
          *((_DWORD *)COSKKeyboardManager::s_pCOSKKeyboardManager + 40) = (unsigned __int8)this;
        }
        COSKKeyboardManager::UpdateHostedKeyboardSettings(v3);
        break;
    }
  }
}

```

## disassembly

```asm
0x140013cb4  push    rbx
0x140013cb6  sub     rsp, 20h
0x140013cba  mov     rbx, cs:?s_pCOSKKeyboardManager@COSKKeyboardManager@@0PEAV1@EA; COSKKeyboardManager * COSKKeyboardManager::s_pCOSKKeyboardManager
0x140013cc1  lea     eax, [rdx-2]
0x140013cc4  test    r8d, r8d
0x140013cc7  setnz   cl
0x140013cca  cmp     eax, 1
0x140013ccd  jbe     loc_140013DEC
0x140013cd3  cmp     edx, 0Ch
0x140013cd6  jnz     short loc_140013CFA
0x140013cd8  cmp     qword ptr [rbx+0E8h], 0
0x140013ce0  jz      loc_140013DF4
0x140013ce6  cmp     [rbx+0DFh], cl
0x140013cec  jz      loc_140013DF4
0x140013cf2  mov     [rbx+0DFh], cl
0x140013cf8  jmp     short loc_140013D5C
0x140013cfa  cmp     edx, 0Eh
0x140013cfd  jnz     short loc_140013D2C
0x140013cff  cmp     [rbx+0DDh], cl
0x140013d05  jz      loc_140013DF4
0x140013d0b  mov     [rbx+0DDh], cl
0x140013d11  test    cs:Microsoft_Windows_oskEnableBits, 1
0x140013d18  jz      short loc_140013D5C
0x140013d1a  movzx   r8d, cl
0x140013d1e  lea     rdx, SetNumpadVisibility
0x140013d25  call    McTemplateU0d_EventWriteTransfer
0x140013d2a  jmp     short loc_140013D5C
0x140013d2c  cmp     edx, 12h
0x140013d2f  jnz     short loc_140013D45
0x140013d31  cmp     [rbx+0F3h], cl
0x140013d37  jz      loc_140013DF4
0x140013d3d  mov     [rbx+0F3h], cl
0x140013d43  jmp     short loc_140013D5C
0x140013d45  cmp     edx, 0Fh
0x140013d48  jnz     short loc_140013D69
0x140013d4a  cmp     [rbx+0F1h], cl
0x140013d50  jz      loc_140013DF4
0x140013d56  mov     [rbx+0F1h], cl
0x140013d5c  mov     rcx, rbx; this
0x140013d5f  add     rsp, 20h
0x140013d63  pop     rbx
0x140013d64  jmp     ?HandleUpdateKeyboardUI@COSKKeyboardManager@@AEAAXXZ; COSKKeyboardManager::HandleUpdateKeyboardUI(void)
0x140013d69  sub     edx, 4
0x140013d6c  jz      short loc_140013DD6
0x140013d6e  sub     edx, 1
0x140013d71  jz      short loc_140013DCD
0x140013d73  sub     edx, 1
0x140013d76  jz      short loc_140013DC4
0x140013d78  sub     edx, 1
0x140013d7b  jz      short loc_140013DBB
0x140013d7d  sub     edx, 1
0x140013d80  jz      short loc_140013DB0
0x140013d82  sub     edx, 1
0x140013d85  jz      short loc_140013DA5
0x140013d87  sub     edx, 1
0x140013d8a  jz      short loc_140013D9A
0x140013d8c  cmp     edx, 1
0x140013d8f  jnz     short loc_140013DDF
0x140013d91  mov     [rbx+0BCh], r8d
0x140013d98  jmp     short loc_140013DDF
0x140013d9a  movzx   eax, cl
0x140013d9d  mov     [rbx+0B8h], eax
0x140013da3  jmp     short loc_140013DDF
0x140013da5  movzx   eax, cl
0x140013da8  mov     [rbx+0B4h], eax
0x140013dae  jmp     short loc_140013DDF
0x140013db0  movzx   eax, cl
0x140013db3  mov     [rbx+0B0h], eax
0x140013db9  jmp     short loc_140013DDF
0x140013dbb  mov     [rbx+0ACh], r8d
0x140013dc2  jmp     short loc_140013DDF
0x140013dc4  mov     [rbx+0A8h], r8d
0x140013dcb  jmp     short loc_140013DDF
0x140013dcd  mov     [rbx+0A4h], r8d
0x140013dd4  jmp     short loc_140013DDF
0x140013dd6  movzx   eax, cl
0x140013dd9  mov     [rbx+0A0h], eax
0x140013ddf  mov     rcx, rbx; this
0x140013de2  add     rsp, 20h
0x140013de6  pop     rbx
0x140013de7  jmp     ?UpdateHostedKeyboardSettings@COSKKeyboardManager@@AEAAJXZ; COSKKeyboardManager::UpdateHostedKeyboardSettings(void)
0x140013dec  mov     rcx, rbx; this
0x140013def  call    ?ResizeKeyboards@COSKKeyboardManager@@AEAAXXZ; COSKKeyboardManager::ResizeKeyboards(void)
0x140013df4  add     rsp, 20h
0x140013df8  pop     rbx
0x140013df9  retn
```
