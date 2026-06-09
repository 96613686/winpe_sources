# COSKKeyboardManager::CreateKeyboards(void)

- ea: `0x140010120`
- end: `0x140010256`
- name: `?CreateKeyboards@COSKKeyboardManager@@AEAAJXZ`
- size: `310`
- prototype: `__int64 __fastcall(COSKKeyboardManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400118d0`

## callees

- `0x14000fe10`
- `0x140010120`
- `0x14001025c`

## import_xrefs

- `USER32!GetKeyboardLayout` at `0x14001012f`
- `USER32!GetKeyboardLayout` at `0x14001012f`

## pseudocode

```c
__int64 __fastcall COSKKeyboardManager::CreateKeyboards(COSKKeyboardManager *this)
{
  int Keyboard; // r8d
  __int64 v3; // rdx
  __int64 v4; // rcx

  *((_QWORD *)this + 18) = GetKeyboardLayout(0);
  Keyboard = COSKKeyboardManager::CreateKeyboard(
               (DirectUI::Element **)this,
               L"SoftKeyboardMain",
               (OLECHAR *)L"\\Main",
               (struct IAccSoftKeyboardUI **)this + 3);
  if ( Keyboard >= 0 )
  {
    Keyboard = COSKKeyboardManager::CreateKeyboard(
                 (DirectUI::Element **)this,
                 L"SoftKeyboardAux",
                 (OLECHAR *)L"\\auxpad",
                 (struct IAccSoftKeyboardUI **)this + 4);
    if ( Keyboard >= 0 )
    {
      Keyboard = COSKKeyboardManager::CreateKeyboard(
                   (DirectUI::Element **)this,
                   L"SoftKeyboardNav",
                   (OLECHAR *)L"\\osknav",
                   (struct IAccSoftKeyboardUI **)this + 8);
      if ( Keyboard >= 0 )
      {
        Keyboard = COSKKeyboardManager::CreateKeyboard(
                     (DirectUI::Element **)this,
                     L"SoftKeyboardClearUI",
                     (OLECHAR *)L"\\oskclearui",
                     (struct IAccSoftKeyboardUI **)this + 9);
        if ( Keyboard >= 0 )
        {
          Keyboard = COSKKeyboardManager::CreateKeyboard(
                       (DirectUI::Element **)this,
                       L"SoftKeyboardNumPad",
                       (OLECHAR *)L"\\osknumpad",
                       (struct IAccSoftKeyboardUI **)this + 7);
          if ( Keyboard >= 0 )
          {
            Keyboard = COSKKeyboardManager::CreateMenuKeyboard(
                         (DirectUI::Element **)this,
                         (struct IAccSoftKeyboardUI **)this + 5);
            if ( Keyboard >= 0 )
            {
              if ( *((_QWORD *)this + 29) )
              {
                Keyboard = COSKKeyboardManager::CreateKeyboard(
                             (DirectUI::Element **)this,
                             L"SoftKeyboardPred",
                             (OLECHAR *)L"\\oskpred",
                             (struct IAccSoftKeyboardUI **)this + 6);
                if ( Keyboard >= 0 )
                {
                  v3 = *((_QWORD *)this + 29);
                  v4 = *((_QWORD *)this + 6);
                  *(_QWORD *)(v3 + 16) = *((_QWORD *)this + 18);
                  *(_QWORD *)(v3 + 296) = v4;
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)Keyboard;
}

```

## disassembly

```asm
0x140010120  mov     [rsp+arg_0], rbx
0x140010125  push    rdi
0x140010126  sub     rsp, 20h
0x14001012a  mov     rbx, rcx
0x14001012d  xor     ecx, ecx; idThread
0x14001012f  call    cs:__imp_GetKeyboardLayout
0x140010135  lea     r9, [rbx+18h]; struct IAccSoftKeyboardUI **
0x140010139  mov     rcx, rbx; this
0x14001013c  lea     r8, psz; "\\Main"
0x140010143  mov     [rbx+90h], rax
0x14001014a  lea     rdx, aSoftkeyboardma; "SoftKeyboardMain"
0x140010151  call    ?CreateKeyboard@COSKKeyboardManager@@AEAAJPEBG0PEAPEAUIAccSoftKeyboardUI@@@Z; COSKKeyboardManager::CreateKeyboard(ushort const *,ushort const *,IAccSoftKeyboardUI * *)
0x140010156  mov     r8d, eax
0x140010159  test    eax, eax
0x14001015b  js      loc_140010248
0x140010161  lea     r9, [rbx+20h]; struct IAccSoftKeyboardUI **
0x140010165  mov     rcx, rbx; this
0x140010168  lea     r8, aAuxpad; "\\auxpad"
0x14001016f  lea     rdx, aSoftkeyboardau; "SoftKeyboardAux"
0x140010176  call    ?CreateKeyboard@COSKKeyboardManager@@AEAAJPEBG0PEAPEAUIAccSoftKeyboardUI@@@Z; COSKKeyboardManager::CreateKeyboard(ushort const *,ushort const *,IAccSoftKeyboardUI * *)
0x14001017b  mov     r8d, eax
0x14001017e  test    eax, eax
0x140010180  js      loc_140010248
0x140010186  lea     r9, [rbx+40h]; struct IAccSoftKeyboardUI **
0x14001018a  mov     rcx, rbx; this
0x14001018d  lea     r8, aOsknav; "\\osknav"
0x140010194  lea     rdx, aSoftkeyboardna; "SoftKeyboardNav"
0x14001019b  call    ?CreateKeyboard@COSKKeyboardManager@@AEAAJPEBG0PEAPEAUIAccSoftKeyboardUI@@@Z; COSKKeyboardManager::CreateKeyboard(ushort const *,ushort const *,IAccSoftKeyboardUI * *)
0x1400101a0  mov     r8d, eax
0x1400101a3  test    eax, eax
0x1400101a5  js      loc_140010248
0x1400101ab  lea     r9, [rbx+48h]; struct IAccSoftKeyboardUI **
0x1400101af  mov     rcx, rbx; this
0x1400101b2  lea     r8, aOskclearui; "\\oskclearui"
0x1400101b9  lea     rdx, aSoftkeyboardcl; "SoftKeyboardClearUI"
0x1400101c0  call    ?CreateKeyboard@COSKKeyboardManager@@AEAAJPEBG0PEAPEAUIAccSoftKeyboardUI@@@Z; COSKKeyboardManager::CreateKeyboard(ushort const *,ushort const *,IAccSoftKeyboardUI * *)
0x1400101c5  mov     r8d, eax
0x1400101c8  test    eax, eax
0x1400101ca  js      short loc_140010248
0x1400101cc  lea     r9, [rbx+38h]; struct IAccSoftKeyboardUI **
0x1400101d0  mov     rcx, rbx; this
0x1400101d3  lea     r8, aOsknumpad; "\\osknumpad"
0x1400101da  lea     rdx, aSoftkeyboardnu; "SoftKeyboardNumPad"
0x1400101e1  call    ?CreateKeyboard@COSKKeyboardManager@@AEAAJPEBG0PEAPEAUIAccSoftKeyboardUI@@@Z; COSKKeyboardManager::CreateKeyboard(ushort const *,ushort const *,IAccSoftKeyboardUI * *)
0x1400101e6  mov     r8d, eax
0x1400101e9  test    eax, eax
0x1400101eb  js      short loc_140010248
0x1400101ed  lea     rdx, [rbx+28h]; struct IAccSoftKeyboardUI **
0x1400101f1  mov     rcx, rbx; this
0x1400101f4  call    ?CreateMenuKeyboard@COSKKeyboardManager@@AEAAJPEAPEAUIAccSoftKeyboardUI@@@Z; COSKKeyboardManager::CreateMenuKeyboard(IAccSoftKeyboardUI * *)
0x1400101f9  mov     r8d, eax
0x1400101fc  test    eax, eax
0x1400101fe  js      short loc_140010248
0x140010200  cmp     qword ptr [rbx+0E8h], 0
0x140010208  jz      short loc_140010248
0x14001020a  lea     r9, [rbx+30h]; struct IAccSoftKeyboardUI **
0x14001020e  mov     rcx, rbx; this
0x140010211  lea     r8, aOskpred; "\\oskpred"
0x140010218  lea     rdx, aSoftkeyboardpr; "SoftKeyboardPred"
0x14001021f  call    ?CreateKeyboard@COSKKeyboardManager@@AEAAJPEBG0PEAPEAUIAccSoftKeyboardUI@@@Z; COSKKeyboardManager::CreateKeyboard(ushort const *,ushort const *,IAccSoftKeyboardUI * *)
0x140010224  mov     r8d, eax
0x140010227  test    eax, eax
0x140010229  js      short loc_140010248
0x14001022b  mov     rdx, [rbx+0E8h]
0x140010232  mov     rcx, [rbx+30h]
0x140010236  mov     rax, [rbx+90h]
0x14001023d  mov     [rdx+10h], rax
0x140010241  mov     [rdx+128h], rcx
0x140010248  mov     rbx, [rsp+28h+arg_0]
0x14001024d  mov     eax, r8d
0x140010250  add     rsp, 20h
0x140010254  pop     rdi
0x140010255  retn
```
