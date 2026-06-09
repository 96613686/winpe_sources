# ShortcutSerialization::s_PopulateV2Properties(IShellLinkW * const,_CONSOLE_STATE_INFO *)

- ea: `0x180017e50`
- end: `0x180018009`
- name: `?s_PopulateV2Properties@ShortcutSerialization@@CAJQEAUIShellLinkW@@PEAU_CONSOLE_STATE_INFO@@@Z`
- size: `441`
- prototype: `__int64 __fastcall(struct IShellLinkW *const, struct _CONSOLE_STATE_INFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800178fc`

## callees

- `0x180017b18`
- `0x180017b70`
- `0x180017c00`
- `0x180017e50`
- `0x18001a010`

## pseudocode

```c
__int64 __fastcall ShortcutSerialization::s_PopulateV2Properties(
        struct IShellLinkW *const a1,
        struct _CONSOLE_STATE_INFO *a2)
{
  struct IShellLinkWVtbl *lpVtbl; // rax
  int PropertyBoolValue; // ebx
  const struct _tagpropertykey *v5; // rdx
  struct IPropertyStore *v6; // rcx
  unsigned int v8; // [rsp+30h] [rbp+10h] BYREF
  struct IPropertyStore *v9; // [rsp+40h] [rbp+20h] BYREF

  lpVtbl = a1->lpVtbl;
  v9 = 0;
  PropertyBoolValue = ((__int64 (__fastcall *)(struct IShellLinkW *const, GUID *, struct IPropertyStore **))lpVtbl->QueryInterface)(
                        a1,
                        &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                        &v9);
  if ( PropertyBoolValue >= 0 )
  {
    PropertyBoolValue = ShortcutSerialization::s_GetPropertyBoolValue(v9, &PKEY_Console_WrapText, (int *const)a2 + 54);
    if ( PropertyBoolValue >= 0 )
    {
      PropertyBoolValue = ShortcutSerialization::s_GetPropertyBoolValue(
                            v9,
                            &PKEY_Console_FilterOnPaste,
                            (int *const)a2 + 55);
      if ( PropertyBoolValue >= 0 )
      {
        PropertyBoolValue = ShortcutSerialization::s_GetPropertyBoolValue(
                              v9,
                              &PKEY_Console_CtrlKeyShortcutsDisabled,
                              (int *const)a2 + 56);
        if ( PropertyBoolValue >= 0 )
        {
          PropertyBoolValue = ShortcutSerialization::s_GetPropertyBoolValue(
                                v9,
                                &PKEY_Console_LineSelection,
                                (int *const)a2 + 57);
          if ( PropertyBoolValue >= 0 )
          {
            PropertyBoolValue = ShortcutSerialization::s_GetPropertyByteValue(v9, v5, (unsigned __int8 *const)a2 + 232);
            if ( PropertyBoolValue >= 0 )
            {
              v8 = 0;
              PropertyBoolValue = ShortcutSerialization::s_GetPropertyDwordValue(v9, &PKEY_Console_CursorType, &v8);
              if ( PropertyBoolValue >= 0 )
              {
                v6 = v9;
                *((_DWORD *)a2 + 60) = v8;
                PropertyBoolValue = ShortcutSerialization::s_GetPropertyDwordValue(
                                      v6,
                                      &PKEY_Console_CursorColor,
                                      (unsigned int *const)a2 + 61);
                if ( PropertyBoolValue >= 0 )
                {
                  PropertyBoolValue = ShortcutSerialization::s_GetPropertyBoolValue(
                                        v9,
                                        &PKEY_Console_InterceptCopyPaste,
                                        (int *const)a2 + 62);
                  if ( PropertyBoolValue >= 0 )
                  {
                    PropertyBoolValue = ShortcutSerialization::s_GetPropertyDwordValue(
                                          v9,
                                          &PKEY_Console_DefaultForeground,
                                          (unsigned int *const)a2 + 63);
                    if ( PropertyBoolValue >= 0 )
                    {
                      PropertyBoolValue = ShortcutSerialization::s_GetPropertyDwordValue(
                                            v9,
                                            &PKEY_Console_DefaultBackground,
                                            (unsigned int *const)a2 + 64);
                      if ( PropertyBoolValue >= 0 )
                        PropertyBoolValue = ShortcutSerialization::s_GetPropertyBoolValue(
                                              v9,
                                              &PKEY_Console_TerminalScrolling,
                                              (int *const)a2 + 65);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    ((void (__fastcall *)(struct IPropertyStore *))v9->lpVtbl->Release)(v9);
  }
  return (unsigned int)PropertyBoolValue;
}

```

## disassembly

```asm
0x180017e50  mov     [rsp-8+arg_8], rbx
0x180017e55  mov     [rsp-8+arg_18], rdi
0x180017e5a  push    rbp
0x180017e5b  mov     rbp, rsp
0x180017e5e  sub     rsp, 20h
0x180017e62  mov     rax, [rcx]
0x180017e65  lea     r8, [rbp+arg_10]
0x180017e69  mov     rdi, rdx
0x180017e6c  mov     [rbp+arg_10], 0
0x180017e74  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180017e7b  mov     rax, [rax]
0x180017e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e83  mov     ebx, eax
0x180017e85  test    eax, eax
0x180017e87  js      loc_180017FF6
0x180017e8d  mov     rcx, [rbp+arg_10]; struct IPropertyStore *
0x180017e91  lea     r8, [rdi+0D8h]; int *
0x180017e98  lea     rdx, PKEY_Console_WrapText; struct _tagpropertykey *
0x180017e9f  call    ?s_GetPropertyBoolValue@ShortcutSerialization@@CAJQEAUIPropertyStore@@AEBU_tagpropertykey@@QEAH@Z; ShortcutSerialization::s_GetPropertyBoolValue(IPropertyStore * const,_tagpropertykey const &,int * const)
0x180017ea4  mov     ebx, eax
0x180017ea6  test    eax, eax
0x180017ea8  js      loc_180017FE6
0x180017eae  mov     rcx, [rbp+arg_10]; struct IPropertyStore *
0x180017eb2  lea     r8, [rdi+0DCh]; int *
0x180017eb9  lea     rdx, PKEY_Console_FilterOnPaste; struct _tagpropertykey *
0x180017ec0  call    ?s_GetPropertyBoolValue@ShortcutSerialization@@CAJQEAUIPropertyStore@@AEBU_tagpropertykey@@QEAH@Z; ShortcutSerialization::s_GetPropertyBoolValue(IPropertyStore * const,_tagpropertykey const &,int * const)
0x180017ec5  mov     ebx, eax
0x180017ec7  test    eax, eax
0x180017ec9  js      loc_180017FE6
0x180017ecf  mov     rcx, [rbp+arg_10]; struct IPropertyStore *
0x180017ed3  lea     r8, [rdi+0E0h]; int *
0x180017eda  lea     rdx, PKEY_Console_CtrlKeyShortcutsDisabled; struct _tagpropertykey *
0x180017ee1  call    ?s_GetPropertyBoolValue@ShortcutSerialization@@CAJQEAUIPropertyStore@@AEBU_tagpropertykey@@QEAH@Z; ShortcutSerialization::s_GetPropertyBoolValue(IPropertyStore * const,_tagpropertykey const &,int * const)
0x180017ee6  mov     ebx, eax
0x180017ee8  test    eax, eax
0x180017eea  js      loc_180017FE6
0x180017ef0  mov     rcx, [rbp+arg_10]; struct IPropertyStore *
0x180017ef4  lea     r8, [rdi+0E4h]; int *
0x180017efb  lea     rdx, PKEY_Console_LineSelection; struct _tagpropertykey *
0x180017f02  call    ?s_GetPropertyBoolValue@ShortcutSerialization@@CAJQEAUIPropertyStore@@AEBU_tagpropertykey@@QEAH@Z; ShortcutSerialization::s_GetPropertyBoolValue(IPropertyStore * const,_tagpropertykey const &,int * const)
0x180017f07  mov     ebx, eax
0x180017f09  test    eax, eax
0x180017f0b  js      loc_180017FE6
0x180017f11  mov     rcx, [rbp+arg_10]; struct IPropertyStore *
0x180017f15  lea     r8, [rdi+0E8h]; unsigned __int8 *
0x180017f1c  call    ?s_GetPropertyByteValue@ShortcutSerialization@@CAJQEAUIPropertyStore@@AEBU_tagpropertykey@@QEAE@Z; ShortcutSerialization::s_GetPropertyByteValue(IPropertyStore * const,_tagpropertykey const &,uchar * const)
0x180017f21  mov     ebx, eax
0x180017f23  test    eax, eax
0x180017f25  js      loc_180017FE6
0x180017f2b  mov     rcx, [rbp+arg_10]; struct IPropertyStore *
0x180017f2f  lea     r8, [rbp+arg_0]; unsigned int *
0x180017f33  lea     rdx, PKEY_Console_CursorType; struct _tagpropertykey *
0x180017f3a  mov     [rbp+arg_0], 0
0x180017f41  call    ?s_GetPropertyDwordValue@ShortcutSerialization@@CAJQEAUIPropertyStore@@AEBU_tagpropertykey@@QEAK@Z; ShortcutSerialization::s_GetPropertyDwordValue(IPropertyStore * const,_tagpropertykey const &,ulong * const)
0x180017f46  mov     ebx, eax
0x180017f48  test    eax, eax
0x180017f4a  js      loc_180017FE6
0x180017f50  mov     eax, [rbp+arg_0]
0x180017f53  lea     r8, [rdi+0F4h]; unsigned int *
0x180017f5a  mov     rcx, [rbp+arg_10]; struct IPropertyStore *
0x180017f5e  lea     rdx, PKEY_Console_CursorColor; struct _tagpropertykey *
0x180017f65  mov     [rdi+0F0h], eax
0x180017f6b  call    ?s_GetPropertyDwordValue@ShortcutSerialization@@CAJQEAUIPropertyStore@@AEBU_tagpropertykey@@QEAK@Z; ShortcutSerialization::s_GetPropertyDwordValue(IPropertyStore * const,_tagpropertykey const &,ulong * const)
0x180017f70  mov     ebx, eax
0x180017f72  test    eax, eax
0x180017f74  js      short loc_180017FE6
0x180017f76  mov     rcx, [rbp+arg_10]; struct IPropertyStore *
0x180017f7a  lea     r8, [rdi+0F8h]; int *
0x180017f81  lea     rdx, PKEY_Console_InterceptCopyPaste; struct _tagpropertykey *
0x180017f88  call    ?s_GetPropertyBoolValue@ShortcutSerialization@@CAJQEAUIPropertyStore@@AEBU_tagpropertykey@@QEAH@Z; ShortcutSerialization::s_GetPropertyBoolValue(IPropertyStore * const,_tagpropertykey const &,int * const)
0x180017f8d  mov     ebx, eax
0x180017f8f  test    eax, eax
0x180017f91  js      short loc_180017FE6
0x180017f93  mov     rcx, [rbp+arg_10]; struct IPropertyStore *
0x180017f97  lea     r8, [rdi+0FCh]; unsigned int *
0x180017f9e  lea     rdx, PKEY_Console_DefaultForeground; struct _tagpropertykey *
0x180017fa5  call    ?s_GetPropertyDwordValue@ShortcutSerialization@@CAJQEAUIPropertyStore@@AEBU_tagpropertykey@@QEAK@Z; ShortcutSerialization::s_GetPropertyDwordValue(IPropertyStore * const,_tagpropertykey const &,ulong * const)
0x180017faa  mov     ebx, eax
0x180017fac  test    eax, eax
0x180017fae  js      short loc_180017FE6
0x180017fb0  mov     rcx, [rbp+arg_10]; struct IPropertyStore *
0x180017fb4  lea     r8, [rdi+100h]; unsigned int *
0x180017fbb  lea     rdx, PKEY_Console_DefaultBackground; struct _tagpropertykey *
0x180017fc2  call    ?s_GetPropertyDwordValue@ShortcutSerialization@@CAJQEAUIPropertyStore@@AEBU_tagpropertykey@@QEAK@Z; ShortcutSerialization::s_GetPropertyDwordValue(IPropertyStore * const,_tagpropertykey const &,ulong * const)
0x180017fc7  mov     ebx, eax
0x180017fc9  test    eax, eax
0x180017fcb  js      short loc_180017FE6
0x180017fcd  mov     rcx, [rbp+arg_10]; struct IPropertyStore *
0x180017fd1  lea     r8, [rdi+104h]; int *
0x180017fd8  lea     rdx, PKEY_Console_TerminalScrolling; struct _tagpropertykey *
0x180017fdf  call    ?s_GetPropertyBoolValue@ShortcutSerialization@@CAJQEAUIPropertyStore@@AEBU_tagpropertykey@@QEAH@Z; ShortcutSerialization::s_GetPropertyBoolValue(IPropertyStore * const,_tagpropertykey const &,int * const)
0x180017fe4  mov     ebx, eax
0x180017fe6  mov     rcx, [rbp+arg_10]
0x180017fea  mov     rax, [rcx]
0x180017fed  mov     rax, [rax+10h]
0x180017ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ff6  mov     rdi, [rsp+20h+arg_18]
0x180017ffb  mov     eax, ebx
0x180017ffd  mov     rbx, [rsp+20h+arg_8]
0x180018002  add     rsp, 20h
0x180018006  pop     rbp
0x180018007  retn
```
