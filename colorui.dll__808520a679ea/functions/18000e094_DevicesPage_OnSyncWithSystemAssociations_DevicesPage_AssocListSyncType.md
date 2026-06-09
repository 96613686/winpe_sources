# DevicesPage::OnSyncWithSystemAssociations(DevicesPage::AssocListSyncType)

- ea: `0x18000e094`
- end: `0x18000e13b`
- name: `?OnSyncWithSystemAssociations@DevicesPage@@AEAAJW4AssocListSyncType@1@@Z`
- size: `167`
- prototype: `__int64 __fastcall(HWND **, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cd90`
- `0x18000e9d8`

## callees

- `0x18000cd08`
- `0x18000e094`
- `0x18000e558`

## import_xrefs

- `mscms!ColorCplResetSystemWideAssociationListChangedWarning` at `0x18000e0e1`
- `mscms!ColorCplResetSystemWideAssociationListChangedWarning` at `0x18000e0e1`
- `mscms!ColorCplMergeAssociationLists` at `0x18000e107`
- `mscms!ColorCplMergeAssociationLists` at `0x18000e107`
- `mscms!ColorCplOverwritePerUserAssociationList` at `0x18000e0f4`
- `mscms!ColorCplOverwritePerUserAssociationList` at `0x18000e0f4`

## pseudocode

```c
__int64 __fastcall DevicesPage::OnSyncWithSystemAssociations(HWND **a1, int a2)
{
  __int64 result; // rax
  unsigned int v5; // r8d
  int v6; // eax
  unsigned int *v7; // [rsp+30h] [rbp+8h] BYREF

  v7 = 0;
  result = Combo<Device>::GetSelectedLParam(a1[11], (LRESULT *)&v7);
  v5 = result;
  if ( (int)result >= 0 )
  {
    if ( (_DWORD)result == 1 )
      return 0;
    if ( a2 )
    {
      if ( a2 == 1 )
      {
        v6 = ColorCplOverwritePerUserAssociationList(v7 + 1, *v7, (unsigned int)result);
      }
      else
      {
        if ( a2 != 2 )
        {
LABEL_10:
          if ( a2 != 2 )
          {
            result = DevicesPage::UpdateProfileListView((DevicesPage *)a1);
            v5 = result;
            if ( (int)result < 0 )
              return result;
          }
          return v5;
        }
        v6 = ColorCplResetSystemWideAssociationListChangedWarning(v7 + 1, *v7, (unsigned int)result);
      }
    }
    else
    {
      v6 = ColorCplMergeAssociationLists(v7 + 1, *v7, (unsigned int)result);
    }
    v5 = v6;
    if ( v6 < 0 )
      return v5;
    goto LABEL_10;
  }
  return result;
}

```

## disassembly

```asm
0x18000e094  mov     [rsp+arg_8], rbx
0x18000e099  push    rdi
0x18000e09a  sub     rsp, 20h
0x18000e09e  mov     ebx, edx
0x18000e0a0  mov     [rsp+28h+arg_0], 0
0x18000e0a9  mov     rdi, rcx
0x18000e0ac  lea     rdx, [rsp+28h+arg_0]
0x18000e0b1  mov     rcx, [rcx+58h]
0x18000e0b5  call    ?GetSelectedLParam@?$Combo@UDevice@@@@QEBAJPEAPEAUDevice@@@Z; Combo<Device>::GetSelectedLParam(Device * *)
0x18000e0ba  mov     r8d, eax
0x18000e0bd  test    eax, eax
0x18000e0bf  js      short loc_18000E130
0x18000e0c1  cmp     eax, 1
0x18000e0c4  jz      short loc_18000E12A
0x18000e0c6  mov     ecx, ebx
0x18000e0c8  test    ebx, ebx
0x18000e0ca  jz      short loc_18000E0FC
0x18000e0cc  sub     ecx, 1
0x18000e0cf  jz      short loc_18000E0E9
0x18000e0d1  cmp     ecx, 1
0x18000e0d4  jnz     short loc_18000E114
0x18000e0d6  mov     rdx, [rsp+28h+arg_0]
0x18000e0db  lea     rcx, [rdx+4]
0x18000e0df  mov     edx, [rdx]
0x18000e0e1  call    cs:__imp_ColorCplResetSystemWideAssociationListChangedWarning
0x18000e0e7  jmp     short loc_18000E10D
0x18000e0e9  mov     rdx, [rsp+28h+arg_0]
0x18000e0ee  lea     rcx, [rdx+4]
0x18000e0f2  mov     edx, [rdx]
0x18000e0f4  call    cs:__imp_ColorCplOverwritePerUserAssociationList
0x18000e0fa  jmp     short loc_18000E10D
0x18000e0fc  mov     rdx, [rsp+28h+arg_0]
0x18000e101  lea     rcx, [rdx+4]
0x18000e105  mov     edx, [rdx]
0x18000e107  call    cs:__imp_ColorCplMergeAssociationLists
0x18000e10d  mov     r8d, eax
0x18000e110  test    eax, eax
0x18000e112  js      short loc_18000E12D
0x18000e114  cmp     ebx, 2
0x18000e117  jz      short loc_18000E12D
0x18000e119  mov     rcx, rdi; this
0x18000e11c  call    ?UpdateProfileListView@DevicesPage@@AEAAJXZ; DevicesPage::UpdateProfileListView(void)
0x18000e121  mov     r8d, eax
0x18000e124  test    eax, eax
0x18000e126  jns     short loc_18000E12D
0x18000e128  jmp     short loc_18000E130
0x18000e12a  xor     r8d, r8d
0x18000e12d  mov     eax, r8d
0x18000e130  mov     rbx, [rsp+28h+arg_8]
0x18000e135  add     rsp, 20h
0x18000e139  pop     rdi
0x18000e13a  retn
```
