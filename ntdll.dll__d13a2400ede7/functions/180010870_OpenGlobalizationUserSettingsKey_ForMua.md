# OpenGlobalizationUserSettingsKey_ForMua

- ea: `0x180010870`
- end: `0x180010b7a`
- name: `OpenGlobalizationUserSettingsKey_ForMua`
- size: `778`
- prototype: ``
- caller_count: `5`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, registry_config`

## callers

- `0x180010eb0`
- `0x180011c70`
- `0x180011d10`
- `0x180071960`
- `0x1800d9560`

## callees

- `0x180010870`
- `0x180010b80`
- `0x180015710`
- `0x180016bc0`
- `0x18001d490`
- `0x18002a5b0`
- `0x180036fa0`
- `0x1800773d0`
- `0x18009d830`
- `0x18015ecc0`
- `0x18015ed20`
- `0x18015ef00`
- `0x180162810`
- `0x180164280`

## string_xrefs

- `0x180010a05`: `TargetNtPath`
- `0x1800109ea`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\International`

## pseudocode

```c
__int64 __fastcall OpenGlobalizationUserSettingsKey_ForMua(unsigned int a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  unsigned int v4; // edi
  __int64 v6; // r15
  __int64 v7; // rsi
  NTSTATUS InformationToken; // ebx
  __int64 v9; // rcx
  _DWORD *v11; // rdx
  unsigned __int8 v12; // al
  int v13; // r12d
  unsigned __int16 v14; // bx
  __int64 v15; // rax
  __int64 v16; // rdi
  __int16 v17; // r15
  unsigned __int64 v18; // rbx
  void *v19; // r13
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h]
  __int64 v23; // [rsp+58h] [rbp-A8h]
  HANDLE Handle[2]; // [rsp+60h] [rbp-A0h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[48]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE Src[528]; // [rsp+B0h] [rbp-50h] BYREF

  v23 = a3;
  v4 = a1;
  v6 = a3;
  UnicodeString = 0;
  memset(v26, 0, 44);
  v7 = IdnaMemAlloc(84);
  if ( v7 )
  {
    LODWORD(Handle[0]) = 0;
    InformationToken = NtQueryInformationToken(-6, 1, v7, 84, Handle);
    if ( InformationToken < 0 )
      goto LABEL_10;
    v11 = *(_DWORD **)v7;
    v12 = *(_BYTE *)(*(_QWORD *)v7 + 1LL);
    if ( v12 < 2u || (v13 = 0, v12 == 5) && v11[2] == 21 && v11[6] == 503 )
    {
      *a4 = 0;
      goto LABEL_9;
    }
    InformationToken = RtlConvertSidToUnicodeString(&UnicodeString, v11, 1u);
    if ( InformationToken < 0 )
    {
LABEL_8:
      if ( !v13 )
      {
LABEL_10:
        RtlpSysVolFree(v7);
        return (unsigned int)InformationToken;
      }
LABEL_9:
      InformationToken = OpenGlobalizationUserSettingsKey_ForSingleUserModel(v4, v6);
      goto LABEL_10;
    }
    LODWORD(Handle[0]) = 0;
    InformationToken = RtlGetPersistedStateLocation((wchar_t *)L"GlobalizationUserSettings", Src, 520, (__int64)Handle);
    if ( InformationToken < 0 )
    {
LABEL_6:
      if ( UnicodeString.Buffer )
        RtlpSysVolFree(UnicodeString.Buffer);
      goto LABEL_8;
    }
    v14 = LOWORD(Handle[0]) + UnicodeString.Length + 4;
    v15 = IdnaMemAlloc(v14);
    v16 = v15;
    if ( !v15 )
    {
      InformationToken = -1073741801;
      goto LABEL_5;
    }
    v21 = 0;
    WORD1(v21) = v14;
    v22 = v15;
    *(_OWORD *)Handle = 0;
    if ( (int)RtlInitUnicodeStringEx(Handle, Src) >= 0 )
    {
      v17 = (__int16)Handle[0];
      if ( LOWORD(Handle[0]) + (unsigned int)(unsigned __int16)v21 <= WORD1(v21) )
      {
        v18 = LOWORD(Handle[0]);
        v19 = (void *)(v22 + 2 * ((unsigned __int64)(unsigned __int16)v21 >> 1));
        memmove(v19, Src, LOWORD(Handle[0]));
        LOWORD(v21) = v17 + v21;
        if ( (unsigned int)(unsigned __int16)v21 + 1 < WORD1(v21) )
          *((_WORD *)v19 + (v18 >> 1)) = 0;
        InformationToken = RtlAppendUnicodeToString(&v21, L"\\");
        if ( InformationToken >= 0 )
        {
          InformationToken = RtlAppendUnicodeStringToString(&v21, &UnicodeString);
          if ( InformationToken >= 0 )
          {
            *(_DWORD *)v26 = 48;
            *(_QWORD *)&v26[16] = &v21;
            *(_QWORD *)&v26[8] = 0;
            *(_DWORD *)&v26[24] = 576;
            Handle[0] = 0;
            *(_OWORD *)&v26[32] = 0;
            if ( (int)NtOpenKey(Handle, 131097, v26) >= 0 )
            {
              NtClose(Handle[0]);
              v6 = v23;
              v9 = v23;
              *a4 = 2;
              InformationToken = NtOpenKey(v9, a1, v26);
LABEL_4:
              RtlpSysVolFree(v16);
LABEL_5:
              v4 = a1;
              goto LABEL_6;
            }
            *a4 = 1;
            v13 = 1;
          }
        }
        v6 = v23;
        goto LABEL_4;
      }
      v6 = v23;
    }
    InformationToken = -1073741789;
    goto LABEL_4;
  }
  return (unsigned int)-1073741801;
}

```

## disassembly

```asm
0x180010870  mov     [rsp-8+arg_8], rbx
0x180010875  push    rbp
0x180010876  push    rsi
0x180010877  push    rdi
0x180010878  push    r12
0x18001087a  push    r13
0x18001087c  push    r14
0x18001087e  push    r15
0x180010880  lea     rbp, [rsp-1D0h]
0x180010888  sub     rsp, 2D0h
0x18001088f  mov     rax, cs:__security_cookie
0x180010896  xor     rax, rsp
0x180010899  mov     [rbp+200h+var_40], rax
0x1800108a0  xorps   xmm0, xmm0
0x1800108a3  mov     [rsp+300h+var_2C0], ecx
0x1800108a7  xor     eax, eax
0x1800108a9  mov     [rsp+300h+var_2A8], r8
0x1800108ae  mov     edi, ecx
0x1800108b0  mov     r14, r9
0x1800108b3  movups  [rbp+200h+var_270], xmm0
0x1800108b7  mov     r15, r8
0x1800108ba  lea     ebx, [rax+54h]
0x1800108bd  mov     ecx, ebx
0x1800108bf  movups  xmmword ptr [rsp+300h+UnicodeString.Length], xmm0
0x1800108c4  movups  [rbp+200h+var_280], xmm0
0x1800108c8  movups  [rbp+200h+var_270+0Ch], xmm0
0x1800108cc  call    IdnaMemAlloc
0x1800108d1  xor     r13d, r13d
0x1800108d4  mov     rsi, rax
0x1800108d7  test    rax, rax
0x1800108da  jnz     loc_180010970
0x1800108e0  mov     ebx, 0C0000017h
0x1800108e5  jmp     short loc_180010943
0x1800108e7  mov     rcx, [rsp+300h+Handle]; Handle
0x1800108ec  call    NtClose
0x1800108f1  mov     r15, [rsp+300h+var_2A8]
0x1800108f6  lea     r8, [rbp+200h+var_280]
0x1800108fa  mov     edx, [rsp+300h+var_2C0]
0x1800108fe  mov     rcx, r15
0x180010901  mov     dword ptr [r14], 2
0x180010908  call    NtOpenKey
0x18001090d  mov     ebx, eax
0x18001090f  mov     rcx, rdi
0x180010912  call    RtlpSysVolFree
0x180010917  mov     edi, [rsp+300h+var_2C0]
0x18001091b  mov     rcx, [rsp+300h+UnicodeString.Buffer]
0x180010920  test    rcx, rcx
0x180010923  jz      short loc_18001092A
0x180010925  call    RtlpSysVolFree
0x18001092a  test    r12d, r12d
0x18001092d  jz      short loc_18001093B
0x18001092f  mov     rdx, r15
0x180010932  mov     ecx, edi
0x180010934  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x180010939  mov     ebx, eax
0x18001093b  mov     rcx, rsi
0x18001093e  call    RtlpSysVolFree
0x180010943  mov     eax, ebx
0x180010945  mov     rcx, [rbp+200h+var_40]
0x18001094c  xor     rcx, rsp; StackCookie
0x18001094f  call    __security_check_cookie
0x180010954  mov     rbx, [rsp+300h+arg_8]
0x18001095c  add     rsp, 2D0h
0x180010963  pop     r15
0x180010965  pop     r14
0x180010967  pop     r13
0x180010969  pop     r12
0x18001096b  pop     rdi
0x18001096c  pop     rsi
0x18001096d  pop     rbp
0x18001096e  retn
0x180010970  lea     rax, [rsp+300h+Handle]
0x180010975  mov     dword ptr [rsp+300h+Handle], r13d
0x18001097a  mov     r9d, ebx
0x18001097d  mov     [rsp+300h+var_2E0], rax
0x180010982  mov     r8, rsi
0x180010985  mov     edx, 1
0x18001098a  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x180010991  call    NtQueryInformationToken
0x180010996  mov     ebx, eax
0x180010998  test    eax, eax
0x18001099a  js      short loc_18001093B
0x18001099c  mov     rdx, [rsi]; Sid
0x18001099f  mov     al, [rdx+1]
0x1800109a2  cmp     al, 2
0x1800109a4  jb      short loc_1800109BC
0x1800109a6  mov     r12d, r13d
0x1800109a9  cmp     al, 5
0x1800109ab  jnz     short loc_1800109C4
0x1800109ad  cmp     dword ptr [rdx+8], 15h
0x1800109b1  jnz     short loc_1800109C4
0x1800109b3  cmp     dword ptr [rdx+18h], 1F7h
0x1800109ba  jnz     short loc_1800109C4
0x1800109bc  mov     [r14], r13d
0x1800109bf  jmp     loc_18001092F
0x1800109c4  mov     r8b, 1; AllocateDestinationString
0x1800109c7  lea     rcx, [rsp+300h+UnicodeString]; UnicodeString
0x1800109cc  call    RtlConvertSidToUnicodeString
0x1800109d1  mov     ebx, eax
0x1800109d3  test    eax, eax
0x1800109d5  js      loc_18001092A
0x1800109db  lea     rax, [rsp+300h+Handle]
0x1800109e0  mov     dword ptr [rsp+300h+Handle], r13d
0x1800109e5  mov     [rsp+300h+var_2D0], rax; __int64
0x1800109ea  lea     r8, aRegistryMachin_33; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x1800109f1  lea     rax, [rbp+200h+Src]
0x1800109f5  mov     [rsp+300h+var_2D8], 208h; int
0x1800109fd  xor     r9d, r9d
0x180010a00  mov     [rsp+300h+var_2E0], rax; void *
0x180010a05  lea     rdx, aTargetntpath; "TargetNtPath"
0x180010a0c  lea     rcx, aGlobalizationu; "GlobalizationUserSettings"
0x180010a13  call    RtlGetPersistedStateLocation
0x180010a18  mov     ebx, eax
0x180010a1a  test    eax, eax
0x180010a1c  js      loc_18001091B
0x180010a22  movzx   eax, [rsp+300h+UnicodeString.Length]
0x180010a27  add     ax, 4
0x180010a2b  add     ax, word ptr [rsp+300h+Handle]
0x180010a30  movzx   ebx, ax
0x180010a33  mov     ecx, ebx
0x180010a35  call    IdnaMemAlloc
0x180010a3a  mov     rdi, rax
0x180010a3d  test    rax, rax
0x180010a40  jz      loc_180010B61
0x180010a46  xorps   xmm0, xmm0
0x180010a49  lea     rdx, [rbp+200h+Src]
0x180010a4d  movups  [rsp+300h+var_2B8], xmm0
0x180010a52  lea     rcx, [rsp+300h+Handle]
0x180010a57  mov     word ptr [rsp+300h+var_2B8+2], bx
0x180010a5c  mov     qword ptr [rsp+300h+var_2B8+8], rax
0x180010a61  movups  xmmword ptr [rsp+300h+Handle], xmm0
0x180010a66  call    RtlInitUnicodeStringEx
0x180010a6b  test    eax, eax
0x180010a6d  js      loc_180010B70
0x180010a73  movzx   r15d, word ptr [rsp+300h+Handle]
0x180010a79  movzx   ecx, word ptr [rsp+300h+var_2B8]
0x180010a7e  movzx   eax, word ptr [rsp+300h+var_2B8+2]
0x180010a83  add     ecx, r15d
0x180010a86  cmp     ecx, eax
0x180010a88  ja      loc_180010B6B
0x180010a8e  movzx   ecx, word ptr [rsp+300h+var_2B8]
0x180010a93  lea     rdx, [rbp+200h+Src]; Src
0x180010a97  mov     rax, qword ptr [rsp+300h+var_2B8+8]
0x180010a9c  mov     r8d, r15d; Size
0x180010a9f  shr     rcx, 1
0x180010aa2  mov     ebx, r15d
0x180010aa5  lea     r13, [rax+rcx*2]
0x180010aa9  mov     rcx, r13; void *
0x180010aac  call    memmove
0x180010ab1  movzx   eax, word ptr [rsp+300h+var_2B8]
0x180010ab6  add     ax, r15w
0x180010aba  mov     r15d, 1
0x180010ac0  movzx   ecx, ax
0x180010ac3  mov     word ptr [rsp+300h+var_2B8], ax
0x180010ac8  add     ecx, r15d
0x180010acb  movzx   eax, word ptr [rsp+300h+var_2B8+2]
0x180010ad0  cmp     ecx, eax
0x180010ad2  jnb     short loc_180010ADF
0x180010ad4  shr     rbx, 1
0x180010ad7  xor     eax, eax
0x180010ad9  mov     [r13+rbx*2+0], ax
0x180010adf  lea     rdx, asc_180178554; "\\"
0x180010ae6  lea     rcx, [rsp+300h+var_2B8]
0x180010aeb  call    RtlAppendUnicodeToString
0x180010af0  xor     r13d, r13d
0x180010af3  mov     ebx, eax
0x180010af5  test    eax, eax
0x180010af7  js      short loc_180010B57
0x180010af9  lea     rdx, [rsp+300h+UnicodeString]
0x180010afe  lea     rcx, [rsp+300h+var_2B8]
0x180010b03  call    RtlAppendUnicodeStringToString
0x180010b08  mov     ebx, eax
0x180010b0a  test    eax, eax
0x180010b0c  js      short loc_180010B57
0x180010b0e  lea     rax, [rsp+300h+var_2B8]
0x180010b13  mov     dword ptr [rbp+200h+var_280], 30h ; '0'
0x180010b1a  xorps   xmm0, xmm0
0x180010b1d  mov     qword ptr [rbp+200h+var_270], rax
0x180010b21  lea     r8, [rbp+200h+var_280]
0x180010b25  mov     qword ptr [rbp+200h+var_280+8], r13
0x180010b29  mov     edx, 20019h
0x180010b2e  mov     dword ptr [rbp+200h+var_270+8], 240h
0x180010b35  lea     rcx, [rsp+300h+Handle]
0x180010b3a  mov     [rsp+300h+Handle], r13
0x180010b3f  movdqu  [rbp+200h+var_260], xmm0
0x180010b44  call    NtOpenKey
0x180010b49  test    eax, eax
0x180010b4b  jns     loc_1800108E7
0x180010b51  mov     [r14], r15d
0x180010b54  mov     r12d, r15d
0x180010b57  mov     r15, [rsp+300h+var_2A8]
0x180010b5c  jmp     loc_18001090F
0x180010b61  mov     ebx, 0C0000017h
0x180010b66  jmp     loc_180010917
0x180010b6b  mov     r15, [rsp+300h+var_2A8]
0x180010b70  mov     ebx, 0C0000023h
0x180010b75  jmp     loc_18001090F
```
