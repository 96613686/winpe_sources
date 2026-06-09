# RtlpGetNtProductTypeFromRegistry

- ea: `0x18007cd80`
- end: `0x18007cf53`
- name: `RtlpGetNtProductTypeFromRegistry`
- size: `467`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180002c60`

## callees

- `0x18007b1a0`
- `0x18007cd80`
- `0x18015ecc0`
- `0x18015ed20`
- `0x18015edc0`
- `0x180162810`

## string_xrefs

- `0x18007cda0`: `\Registry\Machine\System\CurrentControlSet\Control\ProductOptions`

## pseudocode

```c
__int64 __fastcall RtlpGetNtProductTypeFromRegistry(_DWORD *a1)
{
  int v2; // ebx
  __int64 v4; // r8
  __int64 v5; // r8
  __int64 v6; // r8
  int v7; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-C8h] BYREF
  _WORD v9[2]; // [rsp+40h] [rbp-C0h] BYREF
  int v10; // [rsp+44h] [rbp-BCh]
  int *v11; // [rsp+48h] [rbp-B8h]
  _QWORD v12[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v13[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v14[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v15[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v16[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v17[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v18; // [rsp+C0h] [rbp-40h]
  _BYTE v19[4]; // [rsp+D0h] [rbp-30h] BYREF
  int v20; // [rsp+D4h] [rbp-2Ch]
  unsigned int v21; // [rsp+D8h] [rbp-28h]
  int v22; // [rsp+DCh] [rbp-24h] BYREF

  v17[0] = 48;
  v12[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\ProductOptions";
  v17[3] = 576;
  v13[1] = L"ProductType";
  v12[0] = 8650882;
  v15[1] = L"LanmanNt";
  v7 = 0;
  v16[1] = L"ServerNt";
  v10 = 0;
  v14[1] = L"WinNt";
  v13[0] = 1572886;
  v17[2] = v12;
  v15[0] = 1179664;
  v16[0] = 1179664;
  v14[0] = 786442;
  Handle = 0;
  v17[1] = 0;
  v18 = 0;
  v2 = NtOpenKey(&Handle, 1, v17);
  if ( v2 >= 0 )
  {
    v2 = NtQueryValueKey(Handle, v13, 2, v19, 36, &v7);
    if ( v2 >= 0 )
    {
      if ( v20 != 1 || v21 < 2 )
      {
LABEL_12:
        v2 = -1073739509;
        goto LABEL_2;
      }
      v9[1] = v21;
      v11 = &v22;
      LOBYTE(v4) = 1;
      v9[0] = v21 - 2;
      if ( (unsigned __int8)RtlEqualUnicodeString(v9, v14, v4) )
      {
        *a1 = 1;
      }
      else
      {
        LOBYTE(v5) = 1;
        if ( !(unsigned __int8)RtlEqualUnicodeString(v9, v15, v5) )
        {
          LOBYTE(v6) = 1;
          if ( (unsigned __int8)RtlEqualUnicodeString(v9, v16, v6) )
          {
            *a1 = 3;
            goto LABEL_2;
          }
          goto LABEL_12;
        }
        *a1 = 2;
      }
    }
  }
LABEL_2:
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18007cd80  push    rbp
0x18007cd82  push    rbx
0x18007cd83  push    rdi
0x18007cd84  push    r15
0x18007cd86  lea     rbp, [rsp-8]
0x18007cd8b  sub     rsp, 108h
0x18007cd92  mov     rax, cs:__security_cookie
0x18007cd99  xor     rax, rsp
0x18007cd9c  mov     [rbp+20h+var_28], rax
0x18007cda0  lea     rax, aRegistryMachin_9; "\\Registry\\Machine\\System\\CurrentCon"...
0x18007cda7  mov     [rbp+20h+var_80], 30h ; '0'
0x18007cdaf  mov     [rsp+120h+var_C8], rax
0x18007cdb4  lea     r8, [rbp+20h+var_80]
0x18007cdb8  lea     rax, aProducttype; "ProductType"
0x18007cdbf  mov     [rbp+20h+var_68], 240h
0x18007cdc7  mov     [rsp+120h+var_B8], rax
0x18007cdcc  mov     rdi, rcx
0x18007cdcf  lea     rax, aLanmannt; "LanmanNt"
0x18007cdd6  mov     [rsp+120h+var_D0], 840082h
0x18007cddf  mov     [rbp+20h+var_98], rax
0x18007cde3  lea     rcx, [rsp+120h+Handle]
0x18007cde8  lea     rax, aServernt; "ServerNt"
0x18007cdef  mov     [rsp+120h+var_F0], 0
0x18007cdf7  mov     [rbp+20h+var_88], rax
0x18007cdfb  xorps   xmm0, xmm0
0x18007cdfe  lea     rax, aWinnt; "WinNt"
0x18007ce05  mov     [rsp+120h+var_DC], 0
0x18007ce0d  mov     [rsp+120h+var_A8], rax
0x18007ce12  mov     edx, 1
0x18007ce17  lea     rax, [rsp+120h+var_D0]
0x18007ce1c  mov     [rsp+120h+var_C0], 180016h
0x18007ce25  mov     [rbp+20h+var_70], rax
0x18007ce29  mov     [rbp+20h+var_A0], 120010h
0x18007ce31  mov     [rbp+20h+var_90], 120010h
0x18007ce39  mov     [rsp+120h+var_B0], 0C000Ah
0x18007ce42  mov     [rsp+120h+Handle], 0
0x18007ce4b  mov     [rbp+20h+var_78], 0
0x18007ce53  movdqu  [rbp+20h+var_60], xmm0
0x18007ce58  call    NtOpenKey
0x18007ce5d  mov     ebx, eax
0x18007ce5f  test    eax, eax
0x18007ce61  jns     short loc_18007CE8E
0x18007ce63  mov     rcx, [rsp+120h+Handle]; Handle
0x18007ce68  test    rcx, rcx
0x18007ce6b  jz      short loc_18007CE72
0x18007ce6d  call    NtClose
0x18007ce72  mov     eax, ebx
0x18007ce74  mov     rcx, [rbp+20h+var_28]
0x18007ce78  xor     rcx, rsp; StackCookie
0x18007ce7b  call    __security_check_cookie
0x18007ce80  add     rsp, 108h
0x18007ce87  pop     r15
0x18007ce89  pop     rdi
0x18007ce8a  pop     rbx
0x18007ce8b  pop     rbp
0x18007ce8c  retn
0x18007ce8e  mov     rcx, [rsp+120h+Handle]
0x18007ce93  lea     rax, [rsp+120h+var_F0]
0x18007ce98  mov     [rsp+120h+var_F8], rax
0x18007ce9d  lea     r9, [rbp+20h+var_50]
0x18007cea1  mov     r15d, 2
0x18007cea7  mov     [rsp+120h+var_100], 24h ; '$'
0x18007ceaf  mov     r8d, r15d
0x18007ceb2  lea     rdx, [rsp+120h+var_C0]
0x18007ceb7  call    NtQueryValueKey
0x18007cebc  mov     ebx, eax
0x18007cebe  test    eax, eax
0x18007cec0  js      short loc_18007CE63
0x18007cec2  cmp     [rbp+20h+var_4C], 1
0x18007cec6  jnz     short loc_18007CF36
0x18007cec8  mov     rcx, [rbp+20h+var_48]
0x18007cecc  cmp     ecx, r15d
0x18007cecf  jb      short loc_18007CF36
0x18007ced1  lea     rax, [rbp+20h+var_48+4]
0x18007ced5  mov     [rsp+120h+var_DE], cx
0x18007ceda  mov     [rsp+120h+var_D8], rax
0x18007cedf  lea     rdx, [rsp+120h+var_B0]
0x18007cee4  movzx   eax, cx
0x18007cee7  mov     r8b, 1
0x18007ceea  sub     ax, r15w
0x18007ceee  lea     rcx, [rsp+120h+var_E0]
0x18007cef3  mov     [rsp+120h+var_E0], ax
0x18007cef8  call    RtlEqualUnicodeString
0x18007cefd  test    al, al
0x18007ceff  jnz     short loc_18007CF40
0x18007cf01  mov     r8b, 1
0x18007cf04  lea     rdx, [rbp+20h+var_A0]
0x18007cf08  lea     rcx, [rsp+120h+var_E0]
0x18007cf0d  call    RtlEqualUnicodeString
0x18007cf12  test    al, al
0x18007cf14  jnz     short loc_18007CF4B
0x18007cf16  mov     r8b, 1
0x18007cf19  lea     rdx, [rbp+20h+var_90]
0x18007cf1d  lea     rcx, [rsp+120h+var_E0]
0x18007cf22  call    RtlEqualUnicodeString
0x18007cf27  test    al, al
0x18007cf29  jz      short loc_18007CF36
0x18007cf2b  mov     dword ptr [rdi], 3
0x18007cf31  jmp     loc_18007CE63
0x18007cf36  mov     ebx, 0C000090Bh
0x18007cf3b  jmp     loc_18007CE63
0x18007cf40  mov     dword ptr [rdi], 1
0x18007cf46  jmp     loc_18007CE63
0x18007cf4b  mov     [rdi], r15d
0x18007cf4e  jmp     loc_18007CE63
```
