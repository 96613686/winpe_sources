# RegPreDeleteValueKey

- ea: `0x1400390b0`
- end: `0x140039259`
- name: `RegPreDeleteValueKey`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140033020`

## callees

- `0x140011650`
- `0x1400337d8`
- `0x14003410c`
- `0x140034b14`
- `0x140034ca0`
- `0x14003588c`
- `0x1400358c0`
- `0x1400390b0`

## import_xrefs

- `ntoskrnl!CmCallbackReleaseKeyObjectIDEx` at `0x140039208`
- `ntoskrnl!CmCallbackReleaseKeyObjectIDEx` at `0x140039208`
- `ntoskrnl!CmCallbackGetKeyObjectIDEx` at `0x14003911d`
- `ntoskrnl!CmCallbackGetKeyObjectIDEx` at `0x14003911d`

## pseudocode

```c
__int64 __fastcall RegPreDeleteValueKey(_QWORD *a1)
{
  int KeyObjectIDEx; // ebx
  int v3; // eax
  PSLIST_ENTRY v4; // rax
  PVOID P; // [rsp+30h] [rbp-30h] BYREF
  __int64 v7; // [rsp+38h] [rbp-28h] BYREF
  struct _SLIST_ENTRY *v8; // [rsp+40h] [rbp-20h] BYREF
  ULONG v9; // [rsp+48h] [rbp-18h] BYREF

  KeyObjectIDEx = 0;
  v7 = 0;
  P = 0;
  v8 = 0;
  v9 = 0;
  if ( !a1 )
    return (unsigned int)-1073741811;
  if ( (xmmword_14001B740 & 0x40000) == 0 )
    return (unsigned int)KeyObjectIDEx;
  KeyObjectIDEx = CmCallbackGetKeyObjectIDEx((char *)RegData + 8, *a1, 0, &v7, 0);
  if ( KeyObjectIDEx >= 0 && (xmmword_14001B740 & 0x40000) != 0 )
  {
    KeyObjectIDEx = RegMatchData(v7, a1[1], 512, &P);
    if ( KeyObjectIDEx < 0 )
    {
      v3 = 0;
      if ( KeyObjectIDEx != -1073741198 )
        v3 = KeyObjectIDEx;
      KeyObjectIDEx = v3;
      goto LABEL_19;
    }
    if ( P )
    {
      if ( *((_BYTE *)P + 16) == 1 )
      {
        KeyObjectIDEx = RegpQueryValueKeyByPointer((void *)*a1, (struct _UNICODE_STRING *)a1[1], &v9, &v8);
        if ( (int)(KeyObjectIDEx + 0x80000000) >= 0 && KeyObjectIDEx != -1073741772 )
          goto LABEL_19;
        KeyObjectIDEx = 0;
      }
      v4 = MpRegpAllocDeleteValueContext();
      if ( v4 )
      {
        *((_QWORD *)&v4[3].Next + 1) = P;
        P = 0;
        *((_QWORD *)&v4[2].Next + 1) = v7;
        v7 = 0;
        v4[3].Next = v8;
        v8 = 0;
        MpRegpInsertCallContext(v4);
      }
      else
      {
        KeyObjectIDEx = -1073741670;
      }
    }
    else
    {
      KeyObjectIDEx = -1073741823;
    }
  }
LABEL_19:
  if ( v7 )
    CmCallbackReleaseKeyObjectIDEx();
  if ( v8 )
  {
    RegpFreeValueData();
    v8 = 0;
  }
  if ( P )
    RegFreeMatchingInfo(P);
  return (unsigned int)KeyObjectIDEx;
}

```

## disassembly

```asm
0x1400390b0  mov     [rsp-8+arg_8], rbx
0x1400390b5  mov     [rsp-8+arg_10], rdi
0x1400390ba  push    rbp
0x1400390bb  mov     rbp, rsp
0x1400390be  sub     rsp, 60h
0x1400390c2  mov     rax, cs:__security_cookie
0x1400390c9  xor     rax, rsp
0x1400390cc  mov     [rbp+var_10], rax
0x1400390d0  xor     ebx, ebx
0x1400390d2  mov     rdi, rcx
0x1400390d5  mov     [rbp+var_28], rbx
0x1400390d9  mov     [rbp+P], rbx
0x1400390dd  mov     [rbp+var_20], rbx
0x1400390e1  mov     [rbp+var_18], ebx
0x1400390e4  test    rcx, rcx
0x1400390e7  jnz     short loc_1400390F3
0x1400390e9  mov     ebx, 0C000000Dh
0x1400390ee  jmp     loc_140039238
0x1400390f3  test    qword ptr cs:xmmword_14001B740, 40000h
0x1400390fe  jz      loc_140039238
0x140039104  mov     rcx, cs:RegData
0x14003910b  lea     r9, [rbp+var_28]
0x14003910f  mov     rdx, [rdi]
0x140039112  add     rcx, 8
0x140039116  xor     r8d, r8d
0x140039119  mov     [rsp+60h+var_40], ebx
0x14003911d  call    cs:__imp_CmCallbackGetKeyObjectIDEx
0x140039124  nop     dword ptr [rax+rax+00h]
0x140039129  mov     ebx, eax
0x14003912b  test    eax, eax
0x14003912d  js      loc_1400391FF
0x140039133  test    qword ptr cs:xmmword_14001B740, 40000h
0x14003913e  jz      loc_1400391FF
0x140039144  mov     rdx, [rdi+8]
0x140039148  lea     r9, [rbp+P]
0x14003914c  mov     rcx, [rbp+var_28]
0x140039150  mov     r8d, 200h
0x140039156  call    RegMatchData
0x14003915b  mov     ebx, eax
0x14003915d  test    eax, eax
0x14003915f  jns     short loc_140039173
0x140039161  xor     eax, eax
0x140039163  cmp     ebx, 0C0000272h
0x140039169  cmovnz  eax, ebx
0x14003916c  mov     ebx, eax
0x14003916e  jmp     loc_1400391FF
0x140039173  cmp     [rbp+P], 0
0x140039178  jnz     short loc_140039181
0x14003917a  mov     ebx, 0C0000001h
0x14003917f  jmp     short loc_1400391FF
0x140039181  mov     rax, [rbp+P]
0x140039185  cmp     byte ptr [rax+10h], 1
0x140039189  jnz     short loc_1400391B6
0x14003918b  mov     rdx, [rdi+8]
0x14003918f  lea     r9, [rbp+var_20]
0x140039193  mov     rcx, [rdi]
0x140039196  lea     r8, [rbp+var_18]
0x14003919a  call    RegpQueryValueKeyByPointer
0x14003919f  mov     ecx, 80000000h
0x1400391a4  mov     ebx, eax
0x1400391a6  add     eax, ecx
0x1400391a8  test    ecx, eax
0x1400391aa  jnz     short loc_1400391B4
0x1400391ac  cmp     ebx, 0C0000034h
0x1400391b2  jnz     short loc_1400391FF
0x1400391b4  xor     ebx, ebx
0x1400391b6  call    MpRegpAllocDeleteValueContext
0x1400391bb  mov     rcx, rax
0x1400391be  test    rax, rax
0x1400391c1  jnz     short loc_1400391CA
0x1400391c3  mov     ebx, 0C000009Ah
0x1400391c8  jmp     short loc_1400391FF
0x1400391ca  mov     rax, [rbp+P]
0x1400391ce  mov     [rcx+38h], rax
0x1400391d2  mov     rax, [rbp+var_28]
0x1400391d6  mov     [rbp+P], 0
0x1400391de  mov     [rcx+28h], rax
0x1400391e2  mov     rax, [rbp+var_20]
0x1400391e6  mov     [rbp+var_28], 0
0x1400391ee  mov     [rcx+30h], rax
0x1400391f2  mov     [rbp+var_20], 0
0x1400391fa  call    MpRegpInsertCallContext
0x1400391ff  mov     rcx, [rbp+var_28]
0x140039203  test    rcx, rcx
0x140039206  jz      short loc_140039214
0x140039208  call    cs:__imp_CmCallbackReleaseKeyObjectIDEx
0x14003920f  nop     dword ptr [rax+rax+00h]
0x140039214  mov     rcx, [rbp+var_20]
0x140039218  test    rcx, rcx
0x14003921b  jz      short loc_14003922A
0x14003921d  call    RegpFreeValueData
0x140039222  mov     [rbp+var_20], 0
0x14003922a  mov     rcx, [rbp+P]; P
0x14003922e  test    rcx, rcx
0x140039231  jz      short loc_140039238
0x140039233  call    RegFreeMatchingInfo
0x140039238  mov     eax, ebx
0x14003923a  mov     rcx, [rbp+var_10]
0x14003923e  xor     rcx, rsp; StackCookie
0x140039241  call    __security_check_cookie
0x140039246  lea     r11, [rsp+60h+var_s0]
0x14003924b  mov     rbx, [r11+18h]
0x14003924f  mov     rdi, [r11+20h]
0x140039253  mov     rsp, r11
0x140039256  pop     rbp
0x140039257  retn
```
