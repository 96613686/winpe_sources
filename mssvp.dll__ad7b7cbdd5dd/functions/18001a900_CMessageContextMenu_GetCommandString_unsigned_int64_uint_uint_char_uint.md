# CMessageContextMenu::GetCommandString(unsigned __int64,uint,uint *,char *,uint)

- ea: `0x18001a900`
- end: `0x18001abea`
- name: `?GetCommandString@CMessageContextMenu@@UEAAJ_KIPEAIPEADI@Z`
- size: `746`
- prototype: `__int64 __fastcall(CMessageContextMenu *__hidden this, unsigned __int64, unsigned int, unsigned int *, LPWSTR lpBuffer, unsigned int cchBufferMax)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004080`
- `0x180008a0c`
- `0x18001a900`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001aac6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18001aac6`

## string_xrefs

- `0x18001ab91`: `delete`
- `0x18001abbe`: `movetofolder`
- `0x18001ab0d`: `delete`
- `0x18001abb5`: `copytofolder`
- `0x18001ab46`: `movetofolder`
- `0x18001ab3d`: `copytofolder`

## pseudocode

```c
__int64 __fastcall CMessageContextMenu::GetCommandString(
        CMessageContextMenu *this,
        unsigned __int64 a2,
        int a3,
        unsigned int *a4,
        char *lpBuffer,
        unsigned int cchBufferMax)
{
  unsigned int v7; // ebx
  int v8; // r8d
  int v9; // r8d
  int v10; // eax
  UINT v11; // edx
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rdx
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rdx
  unsigned __int64 v21; // rdx
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rdx
  const wchar_t *v29; // r8
  unsigned __int64 v31; // rdx
  unsigned __int64 v32; // rdx
  unsigned __int64 v33; // rdx
  unsigned __int64 v34; // rdx
  unsigned __int64 v35; // rdx
  unsigned __int64 v36; // rdx
  unsigned __int64 v37; // rdx
  const char *v38; // r8

  if ( !lpBuffer )
    return 2147500035LL;
  v7 = -2147024809;
  if ( !a3 )
  {
    v31 = a2 - 1;
    if ( v31 )
    {
      v32 = v31 - 1;
      if ( v32 )
      {
        v33 = v32 - 1;
        if ( v33 )
        {
          v34 = v33 - 1;
          if ( v34 )
          {
            v35 = v34 - 1;
            if ( v35 )
            {
              v36 = v35 - 1;
              if ( v36 )
              {
                v37 = v36 - 1;
                if ( v37 )
                {
                  if ( v37 != 92 )
                    return v7;
                  v38 = "delete";
                }
                else
                {
                  v38 = "forward";
                }
              }
              else
              {
                v38 = "replyall";
              }
            }
            else
            {
              v38 = "reply";
            }
          }
          else
          {
            v38 = "copytofolder";
          }
        }
        else
        {
          v38 = "movetofolder";
        }
      }
      else
      {
        v38 = "print";
      }
    }
    else
    {
      v38 = "open";
    }
    return (unsigned int)StringCchCopyA(lpBuffer, cchBufferMax, v38);
  }
  v8 = a3 - 4;
  if ( !v8 )
  {
    v22 = a2 - 1;
    if ( v22 )
    {
      v23 = v22 - 1;
      if ( v23 )
      {
        v24 = v23 - 1;
        if ( v24 )
        {
          v25 = v24 - 1;
          if ( v25 )
          {
            v26 = v25 - 1;
            if ( v26 )
            {
              v27 = v26 - 1;
              if ( v27 )
              {
                v28 = v27 - 1;
                if ( v28 )
                {
                  if ( v28 != 92 )
                    return v7;
                  v29 = L"delete";
                }
                else
                {
                  v29 = L"forward";
                }
              }
              else
              {
                v29 = L"replyall";
              }
            }
            else
            {
              v29 = L"reply";
            }
          }
          else
          {
            v29 = L"copytofolder";
          }
        }
        else
        {
          v29 = L"movetofolder";
        }
      }
      else
      {
        v29 = L"print";
      }
    }
    else
    {
      v29 = L"open";
    }
    return (unsigned int)StringCchCopyW((wchar_t *)lpBuffer, cchBufferMax, v29);
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v10 = *((_DWORD *)this + 24);
    switch ( v10 )
    {
      case 1001:
        if ( a2 != 1 )
          return v7;
        v11 = *((_DWORD *)this + 25) != 0 ? 121 : 106;
        goto LABEL_53;
      case 1007:
        if ( a2 != 1 )
          return v7;
        v11 = 140;
        goto LABEL_53;
      case 1000:
        if ( a2 <= 6 )
        {
          if ( a2 == 6 )
          {
            v11 = 103;
          }
          else
          {
            v12 = a2 - 1;
            if ( v12 )
            {
              v13 = v12 - 1;
              if ( v13 )
              {
                v14 = v13 - 1;
                if ( v14 )
                {
                  v15 = v14 - 1;
                  if ( v15 )
                  {
                    if ( v15 != 1 )
                      return v7;
                    v11 = 102;
                  }
                  else
                  {
                    v11 = 124;
                  }
                }
                else
                {
                  v11 = 122;
                }
              }
              else
              {
                v11 = 105;
              }
            }
            else
            {
              v11 = 101;
            }
          }
          goto LABEL_53;
        }
        v16 = a2 - 7;
        if ( !v16 )
        {
          v11 = 104;
          goto LABEL_53;
        }
        v17 = v16 - 1;
        if ( v17 )
        {
          v18 = v17 - 1;
          if ( v18 )
          {
            v19 = v18 - 1;
            if ( v19 )
            {
              if ( v19 != 89 )
                return v7;
              v11 = 123;
            }
            else
            {
              v11 = 132;
            }
          }
          else
          {
            v11 = 131;
          }
          goto LABEL_53;
        }
        goto LABEL_47;
    }
    switch ( a2 )
    {
      case 1uLL:
        v11 = 118;
        goto LABEL_53;
      case 2uLL:
        v11 = 119;
        goto LABEL_53;
      case 0x63uLL:
        v11 = 129;
        goto LABEL_53;
    }
    if ( v10 == 1005 )
    {
      v20 = a2 - 4;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( v21 )
        {
          if ( v21 != 1 )
            return v7;
LABEL_47:
          v11 = 137;
          goto LABEL_53;
        }
        v11 = 134;
      }
      else
      {
        v11 = 133;
      }
    }
    else
    {
      if ( v10 != 1002 || a2 != 4 )
        return v7;
      v11 = 136;
    }
LABEL_53:
    if ( !LoadStringW(hInstance, v11, (LPWSTR)lpBuffer, cchBufferMax) )
      return v7;
    return 0;
  }
  if ( v9 == 1 )
    return 0;
  return v7;
}

```

## disassembly

```asm
0x18001a900  push    rbx
0x18001a902  sub     rsp, 20h
0x18001a906  mov     r9, rcx
0x18001a909  mov     rcx, [rsp+28h+lpBuffer]; char *
0x18001a90e  test    rcx, rcx
0x18001a911  jnz     short loc_18001A91D
0x18001a913  mov     eax, 80004003h
0x18001a918  jmp     loc_18001ABE4
0x18001a91d  mov     ebx, 80070057h
0x18001a922  test    r8d, r8d
0x18001a925  jz      loc_18001AB61
0x18001a92b  sub     r8d, 4
0x18001a92f  jz      loc_18001AAD9
0x18001a935  sub     r8d, 1
0x18001a939  jz      short loc_18001A94C
0x18001a93b  cmp     r8d, 1
0x18001a93f  jnz     loc_18001ABE2
0x18001a945  xor     ebx, ebx
0x18001a947  jmp     loc_18001ABE2
0x18001a94c  mov     eax, [r9+60h]
0x18001a950  cmp     eax, 3E9h
0x18001a955  jnz     short loc_18001A974
0x18001a957  cmp     rdx, 1
0x18001a95b  jnz     loc_18001ABE2
0x18001a961  mov     eax, [r9+64h]
0x18001a965  neg     eax
0x18001a967  sbb     edx, edx
0x18001a969  and     edx, 0Fh
0x18001a96c  add     edx, 6Ah ; 'j'
0x18001a96f  jmp     loc_18001AAB7
0x18001a974  cmp     eax, 3EFh
0x18001a979  jnz     short loc_18001A98F
0x18001a97b  cmp     rdx, 1
0x18001a97f  jnz     loc_18001ABE2
0x18001a985  mov     edx, 8Ch
0x18001a98a  jmp     loc_18001AAB7
0x18001a98f  cmp     eax, 3E8h
0x18001a994  jnz     loc_18001AA44
0x18001a99a  cmp     rdx, 6
0x18001a99e  ja      short loc_18001AA00
0x18001a9a0  jz      short loc_18001A9F6
0x18001a9a2  sub     rdx, 1
0x18001a9a6  jz      short loc_18001A9EC
0x18001a9a8  sub     rdx, 1
0x18001a9ac  jz      short loc_18001A9E2
0x18001a9ae  sub     rdx, 1
0x18001a9b2  jz      short loc_18001A9D8
0x18001a9b4  sub     rdx, 1
0x18001a9b8  jz      short loc_18001A9CE
0x18001a9ba  cmp     rdx, 1
0x18001a9be  jnz     loc_18001ABE2
0x18001a9c4  mov     edx, 66h ; 'f'
0x18001a9c9  jmp     loc_18001AAB7
0x18001a9ce  mov     edx, 7Ch ; '|'
0x18001a9d3  jmp     loc_18001AAB7
0x18001a9d8  mov     edx, 7Ah ; 'z'
0x18001a9dd  jmp     loc_18001AAB7
0x18001a9e2  mov     edx, 69h ; 'i'
0x18001a9e7  jmp     loc_18001AAB7
0x18001a9ec  mov     edx, 65h ; 'e'
0x18001a9f1  jmp     loc_18001AAB7
0x18001a9f6  mov     edx, 67h ; 'g'
0x18001a9fb  jmp     loc_18001AAB7
0x18001aa00  sub     rdx, 7
0x18001aa04  jz      short loc_18001AA3D
0x18001aa06  sub     rdx, 1
0x18001aa0a  jz      short loc_18001AA88
0x18001aa0c  sub     rdx, 1
0x18001aa10  jz      short loc_18001AA36
0x18001aa12  sub     rdx, 1
0x18001aa16  jz      short loc_18001AA2C
0x18001aa18  cmp     rdx, 59h ; 'Y'
0x18001aa1c  jnz     loc_18001ABE2
0x18001aa22  mov     edx, 7Bh ; '{'
0x18001aa27  jmp     loc_18001AAB7
0x18001aa2c  mov     edx, 84h
0x18001aa31  jmp     loc_18001AAB7
0x18001aa36  mov     edx, 83h
0x18001aa3b  jmp     short loc_18001AAB7
0x18001aa3d  mov     edx, 68h ; 'h'
0x18001aa42  jmp     short loc_18001AAB7
0x18001aa44  cmp     rdx, 1
0x18001aa48  jnz     short loc_18001AA51
0x18001aa4a  mov     edx, 76h ; 'v'
0x18001aa4f  jmp     short loc_18001AAB7
0x18001aa51  cmp     rdx, 2
0x18001aa55  jnz     short loc_18001AA5E
0x18001aa57  mov     edx, 77h ; 'w'
0x18001aa5c  jmp     short loc_18001AAB7
0x18001aa5e  cmp     rdx, 63h ; 'c'
0x18001aa62  jnz     short loc_18001AA6B
0x18001aa64  mov     edx, 81h
0x18001aa69  jmp     short loc_18001AAB7
0x18001aa6b  cmp     eax, 3EDh
0x18001aa70  jnz     short loc_18001AA9D
0x18001aa72  sub     rdx, 4
0x18001aa76  jz      short loc_18001AA96
0x18001aa78  sub     rdx, 1
0x18001aa7c  jz      short loc_18001AA8F
0x18001aa7e  cmp     rdx, 1
0x18001aa82  jnz     loc_18001ABE2
0x18001aa88  mov     edx, 89h
0x18001aa8d  jmp     short loc_18001AAB7
0x18001aa8f  mov     edx, 86h
0x18001aa94  jmp     short loc_18001AAB7
0x18001aa96  mov     edx, 85h
0x18001aa9b  jmp     short loc_18001AAB7
0x18001aa9d  cmp     eax, 3EAh
0x18001aaa2  jnz     loc_18001ABE2
0x18001aaa8  cmp     rdx, 4
0x18001aaac  jnz     loc_18001ABE2
0x18001aab2  mov     edx, 88h; uID
0x18001aab7  mov     r9d, [rsp+28h+cchBufferMax]; cchBufferMax
0x18001aabc  mov     r8, rcx; lpBuffer
0x18001aabf  mov     rcx, cs:hInstance; hInstance
0x18001aac6  call    cs:__imp_LoadStringW
0x18001aacc  test    eax, eax
0x18001aace  jz      loc_18001ABE2
0x18001aad4  jmp     loc_18001A945
0x18001aad9  sub     rdx, 1
0x18001aadd  jz      short loc_18001AB58
0x18001aadf  sub     rdx, 1
0x18001aae3  jz      short loc_18001AB4F
0x18001aae5  sub     rdx, 1
0x18001aae9  jz      short loc_18001AB46
0x18001aaeb  sub     rdx, 1
0x18001aaef  jz      short loc_18001AB3D
0x18001aaf1  sub     rdx, 1
0x18001aaf5  jz      short loc_18001AB34
0x18001aaf7  sub     rdx, 1
0x18001aafb  jz      short loc_18001AB2B
0x18001aafd  sub     rdx, 1
0x18001ab01  jz      short loc_18001AB22
0x18001ab03  cmp     rdx, 5Ch ; '\'
0x18001ab07  jnz     loc_18001ABE2
0x18001ab0d  lea     r8, aDelete_0; "delete"
0x18001ab14  mov     edx, [rsp+28h+cchBufferMax]; unsigned __int64
0x18001ab18  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001ab1d  jmp     loc_18001ABE0
0x18001ab22  lea     r8, aForward_1; "forward"
0x18001ab29  jmp     short loc_18001AB14
0x18001ab2b  lea     r8, aReplyall; "replyall"
0x18001ab32  jmp     short loc_18001AB14
0x18001ab34  lea     r8, aReply_1; "reply"
0x18001ab3b  jmp     short loc_18001AB14
0x18001ab3d  lea     r8, aCopytofolder_0; "copytofolder"
0x18001ab44  jmp     short loc_18001AB14
0x18001ab46  lea     r8, aMovetofolder; "movetofolder"
0x18001ab4d  jmp     short loc_18001AB14
0x18001ab4f  lea     r8, aPrint_0; "print"
0x18001ab56  jmp     short loc_18001AB14
0x18001ab58  lea     r8, aOpen; "open"
0x18001ab5f  jmp     short loc_18001AB14
0x18001ab61  sub     rdx, 1
0x18001ab65  jz      short loc_18001ABD0
0x18001ab67  sub     rdx, 1
0x18001ab6b  jz      short loc_18001ABC7
0x18001ab6d  sub     rdx, 1
0x18001ab71  jz      short loc_18001ABBE
0x18001ab73  sub     rdx, 1
0x18001ab77  jz      short loc_18001ABB5
0x18001ab79  sub     rdx, 1
0x18001ab7d  jz      short loc_18001ABAC
0x18001ab7f  sub     rdx, 1
0x18001ab83  jz      short loc_18001ABA3
0x18001ab85  sub     rdx, 1
0x18001ab89  jz      short loc_18001AB9A
0x18001ab8b  cmp     rdx, 5Ch ; '\'
0x18001ab8f  jnz     short loc_18001ABE2
0x18001ab91  lea     r8, aDelete_1; "delete"
0x18001ab98  jmp     short loc_18001ABD7
0x18001ab9a  lea     r8, aForward_0; "forward"
0x18001aba1  jmp     short loc_18001ABD7
0x18001aba3  lea     r8, aReplyall_1; "replyall"
0x18001abaa  jmp     short loc_18001ABD7
0x18001abac  lea     r8, aReply_0; "reply"
0x18001abb3  jmp     short loc_18001ABD7
0x18001abb5  lea     r8, aCopytofolder; "copytofolder"
0x18001abbc  jmp     short loc_18001ABD7
0x18001abbe  lea     r8, aMovetofolder_0; "movetofolder"
0x18001abc5  jmp     short loc_18001ABD7
0x18001abc7  lea     r8, aPrint; "print"
0x18001abce  jmp     short loc_18001ABD7
0x18001abd0  lea     r8, aOpen_0; "open"
0x18001abd7  mov     edx, [rsp+28h+cchBufferMax]; unsigned __int64
0x18001abdb  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18001abe0  mov     ebx, eax
0x18001abe2  mov     eax, ebx
0x18001abe4  add     rsp, 20h
0x18001abe8  pop     rbx
0x18001abe9  retn
```
