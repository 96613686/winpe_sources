# CreateApiEventSecurityDescriptor

- ea: `0x18000fdc4`
- end: `0x18001014c`
- name: `CreateApiEventSecurityDescriptor`
- size: `904`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006000`

## callees

- `0x180002ec0`
- `0x1800048c0`
- `0x18000514a`
- `0x180005162`
- `0x18000fdc4`
- `0x180010154`
- `0x180010aac`
- `0x180011060`
- `0x180011ec4`
- `0x180012a00`
- `0x180012b80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800100b4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800100ce`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800100b4`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800100ce`
- `ntdll!RtlDeleteSecurityObject` at `0x180010100`
- `ntdll!RtlDeleteSecurityObject` at `0x180010100`
- `ntdll!RtlNewSecurityObject` at `0x180010020`
- `ntdll!RtlNewSecurityObject` at `0x180010020`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000ffec`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000ffec`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001003c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18001003c`

## pseudocode

```c
__int64 __fastcall CreateApiEventSecurityDescriptor(__int64 a1)
{
  char v1; // al
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int v4; // eax
  DWORD SecurityDescriptorLength; // eax
  size_t v6; // rbx
  unsigned int v7; // ebx
  PSECURITY_DESCRIPTOR v8; // rdi
  unsigned int *v9; // rax
  PSECURITY_DESCRIPTOR NewDescriptor[2]; // [rsp+30h] [rbp-118h] BYREF
  _QWORD SecurityDescriptor[5]; // [rsp+40h] [rbp-108h] BYREF
  _ACL Dacl; // [rsp+68h] [rbp-E0h] BYREF
  int v14; // [rsp+70h] [rbp-D8h]
  int v15; // [rsp+74h] [rbp-D4h]
  int v16; // [rsp+78h] [rbp-D0h]
  int v17; // [rsp+7Ch] [rbp-CCh]
  int v18; // [rsp+80h] [rbp-C8h]
  int v19; // [rsp+84h] [rbp-C4h]
  int v20; // [rsp+88h] [rbp-C0h]
  int v21; // [rsp+8Ch] [rbp-BCh]
  int v22; // [rsp+90h] [rbp-B8h]
  int v23; // [rsp+94h] [rbp-B4h]
  int v24; // [rsp+98h] [rbp-B0h]
  int v25; // [rsp+9Ch] [rbp-ACh]
  int v26; // [rsp+A0h] [rbp-A8h]
  int v27; // [rsp+A4h] [rbp-A4h]
  int v28; // [rsp+A8h] [rbp-A0h]
  int v29; // [rsp+ACh] [rbp-9Ch]
  int v30; // [rsp+B0h] [rbp-98h]
  int v31; // [rsp+B4h] [rbp-94h]
  int v32; // [rsp+B8h] [rbp-90h]
  int v33; // [rsp+BCh] [rbp-8Ch]
  int v34; // [rsp+C0h] [rbp-88h]
  int v35; // [rsp+C4h] [rbp-84h]
  int v36; // [rsp+C8h] [rbp-80h]
  int v37; // [rsp+CCh] [rbp-7Ch]
  int v38; // [rsp+D0h] [rbp-78h]
  int v39; // [rsp+D4h] [rbp-74h]
  int v40; // [rsp+D8h] [rbp-70h]
  int v41; // [rsp+DCh] [rbp-6Ch]
  int v42; // [rsp+E0h] [rbp-68h]
  int v43; // [rsp+E4h] [rbp-64h]
  int v44; // [rsp+E8h] [rbp-60h]
  int v45; // [rsp+ECh] [rbp-5Ch]
  int v46; // [rsp+F0h] [rbp-58h]
  int v47; // [rsp+F4h] [rbp-54h]
  int v48; // [rsp+F8h] [rbp-50h]
  int v49; // [rsp+FCh] [rbp-4Ch]
  int v50; // [rsp+100h] [rbp-48h]
  int v51; // [rsp+104h] [rbp-44h]
  int v52; // [rsp+108h] [rbp-40h]

  SecurityDescriptor[0] = 262145;
  memset(&SecurityDescriptor[1], 0, 32);
  *(_DWORD *)&Dacl.AclRevision = 10747906;
  *(_DWORD *)&Dacl.AceCount = 7;
  v14 = 1310720;
  v15 = 0x1FFFFF;
  v16 = 257;
  v17 = 83886080;
  v18 = 18;
  v19 = 1572864;
  v20 = 0x1FFFFF;
  v21 = 513;
  v22 = 83886080;
  v23 = 32;
  v24 = 544;
  v25 = 1572864;
  v26 = 0x1FFFFF;
  v27 = 513;
  v28 = 83886080;
  v29 = 32;
  v30 = 547;
  v31 = 1310720;
  v32 = 0x1FFFFF;
  v33 = 257;
  v34 = 83886080;
  v35 = 19;
  v36 = 1310720;
  v37 = 0x1FFFFF;
  v38 = 257;
  v39 = 83886080;
  v40 = 20;
  v41 = 1572864;
  v42 = 0x1FFFFF;
  v43 = 513;
  v44 = 83886080;
  v45 = 32;
  v46 = 556;
  v47 = 1572864;
  v48 = 1;
  v49 = 513;
  v50 = 83886080;
  v51 = 32;
  v52 = 545;
  NewDescriptor[0] = 0;
  v1 = xmmword_18001E1E0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    WPP_SF_qq(a1, 10, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids, &GenericMapping, &qword_18001E230);
    v1 = xmmword_18001E1E0;
  }
  qword_18001E230 = 0;
  if ( (v1 & 0x10) != 0 )
    WPP_SF_(1028, 11, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids);
  v2 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, &Dacl, 0);
  v3 = Win32FromNTSTATUS(v2);
  if ( !v3 )
  {
    v4 = RtlNewSecurityObject(0, SecurityDescriptor, NewDescriptor, 0, (HANDLE)0xFFFFFFFFFFFFFFFCLL, &GenericMapping);
    v3 = Win32FromNTSTATUS(v4);
    if ( !v3 )
    {
      SecurityDescriptorLength = GetSecurityDescriptorLength(NewDescriptor[0]);
      v6 = SecurityDescriptorLength;
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
        WPP_SF_dd(1028, 12, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids, SecurityDescriptorLength, 340);
      if ( !(_DWORD)v6 )
        goto LABEL_10;
      v8 = NewDescriptor[0];
      if ( NewDescriptor[0] && (unsigned int)v6 <= 0x154 )
      {
        memcpy_0(qword_18001E240, NewDescriptor[0], v6);
LABEL_10:
        v7 = 0;
        goto LABEL_20;
      }
      memset_0(qword_18001E240, 0, 0x154u);
      if ( v8 )
      {
        if ( (unsigned int)v6 <= 0x154 )
        {
          v7 = 22;
LABEL_20:
          v3 = Win32FromErrno(v7);
          if ( !v3 )
            qword_18001E230 = (__int64)qword_18001E240;
          goto LABEL_22;
        }
        v9 = (unsigned int *)_o__errno();
        v7 = 34;
      }
      else
      {
        v9 = (unsigned int *)_o__errno();
        v7 = 22;
      }
      *v9 = v7;
      invalid_parameter_noinfo();
      goto LABEL_20;
    }
  }
LABEL_22:
  if ( NewDescriptor[0] )
  {
    RtlDeleteSecurityObject(NewDescriptor);
    NewDescriptor[0] = 0;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 13, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18000fdc4  mov     r11, rsp
0x18000fdc7  push    rbx
0x18000fdc8  push    rsi
0x18000fdc9  push    rdi
0x18000fdca  push    r15
0x18000fdcc  sub     rsp, 128h
0x18000fdd3  mov     rax, cs:__security_cookie
0x18000fdda  xor     rax, rsp
0x18000fddd  mov     [rsp+148h+var_38], rax
0x18000fde5  mov     [rsp+148h+SecurityDescriptor], 40001h
0x18000fdee  xor     esi, esi
0x18000fdf0  mov     [rsp+148h+var_100], rsi
0x18000fdf5  mov     [rsp+148h+var_F8], rsi
0x18000fdfa  mov     [rsp+148h+var_F0], rsi
0x18000fdff  mov     [rsp+148h+var_E8], rsi
0x18000fe04  mov     dword ptr [rsp+148h+Dacl.AclRevision], 0A40002h
0x18000fe0c  mov     dword ptr [rsp+148h+Dacl.AceCount], 7
0x18000fe14  mov     [rsp+148h+var_D8], 140000h
0x18000fe1c  mov     [rsp+148h+var_D4], 1FFFFFh
0x18000fe24  mov     [rsp+148h+var_D0], 101h
0x18000fe2c  mov     [rsp+148h+var_CC], 5000000h
0x18000fe34  mov     [rsp+148h+var_C8], 12h
0x18000fe3f  mov     [rsp+148h+var_C4], 180000h
0x18000fe4a  mov     [rsp+148h+var_C0], 1FFFFFh
0x18000fe55  mov     [rsp+148h+var_BC], 201h
0x18000fe60  mov     [rsp+148h+var_B8], 5000000h
0x18000fe6b  mov     [rsp+148h+var_B4], 20h ; ' '
0x18000fe76  mov     [rsp+148h+var_B0], 220h
0x18000fe81  mov     [rsp+148h+var_AC], 180000h
0x18000fe8c  mov     [rsp+148h+var_A8], 1FFFFFh
0x18000fe97  mov     [rsp+148h+var_A4], 201h
0x18000fea2  mov     [rsp+148h+var_A0], 5000000h
0x18000fead  mov     [rsp+148h+var_9C], 20h ; ' '
0x18000feb8  mov     [rsp+148h+var_98], 223h
0x18000fec3  mov     [rsp+148h+var_94], 140000h
0x18000fece  mov     [rsp+148h+var_90], 1FFFFFh
0x18000fed9  mov     [rsp+148h+var_8C], 101h
0x18000fee4  mov     [rsp+148h+var_88], 5000000h
0x18000feef  mov     [rsp+148h+var_84], 13h
0x18000fefa  mov     dword ptr [r11-80h], 140000h
0x18000ff02  mov     dword ptr [r11-7Ch], 1FFFFFh
0x18000ff0a  mov     dword ptr [r11-78h], 101h
0x18000ff12  mov     dword ptr [r11-74h], 5000000h
0x18000ff1a  mov     dword ptr [r11-70h], 14h
0x18000ff22  mov     dword ptr [r11-6Ch], 180000h
0x18000ff2a  mov     dword ptr [r11-68h], 1FFFFFh
0x18000ff32  mov     dword ptr [r11-64h], 201h
0x18000ff3a  mov     dword ptr [r11-60h], 5000000h
0x18000ff42  mov     dword ptr [r11-5Ch], 20h ; ' '
0x18000ff4a  mov     dword ptr [r11-58h], 22Ch
0x18000ff52  mov     dword ptr [r11-54h], 180000h
0x18000ff5a  mov     dword ptr [r11-50h], 1
0x18000ff62  mov     dword ptr [r11-4Ch], 201h
0x18000ff6a  mov     dword ptr [r11-48h], 5000000h
0x18000ff72  mov     dword ptr [r11-44h], 20h ; ' '
0x18000ff7a  mov     dword ptr [r11-40h], 221h
0x18000ff82  mov     [rsp+148h+NewDescriptor], rsi
0x18000ff87  mov     al, byte ptr cs:xmmword_18001E1E0
0x18000ff8d  lea     rdi, GenericMapping
0x18000ff94  test    al, 10h
0x18000ff96  jz      short loc_18000FFBC
0x18000ff98  lea     rax, qword_18001E230
0x18000ff9f  mov     r9, rdi
0x18000ffa2  lea     edx, [rsi+0Ah]
0x18000ffa5  mov     [rsp+148h+Token], rax
0x18000ffaa  lea     r8, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids
0x18000ffb1  call    WPP_SF_qq
0x18000ffb6  mov     al, byte ptr cs:xmmword_18001E1E0
0x18000ffbc  mov     cs:qword_18001E230, rsi
0x18000ffc3  test    al, 10h
0x18000ffc5  jz      short loc_18000FFDD
0x18000ffc7  mov     edx, 0Bh
0x18000ffcc  lea     r8, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids
0x18000ffd3  mov     ecx, 404h
0x18000ffd8  call    WPP_SF_
0x18000ffdd  xor     r9d, r9d; DaclDefaulted
0x18000ffe0  lea     r8, [rsp+148h+Dacl]; Dacl
0x18000ffe5  mov     dl, 1; DaclPresent
0x18000ffe7  lea     rcx, [rsp+148h+SecurityDescriptor]; SecurityDescriptor
0x18000ffec  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18000fff2  mov     ecx, eax
0x18000fff4  call    Win32FromNTSTATUS
0x18000fff9  mov     ebx, eax
0x18000fffb  test    eax, eax
0x18000fffd  jnz     loc_1800100F4
0x180010003  mov     [rsp+148h+GenericMapping], rdi; GenericMapping
0x180010008  lea     r8, [rsp+148h+NewDescriptor]; NewDescriptor
0x18001000d  xor     r9d, r9d; IsDirectoryObject
0x180010010  mov     [rsp+148h+Token], 0FFFFFFFFFFFFFFFCh; Token
0x180010019  lea     rdx, [rsp+148h+SecurityDescriptor]; CreatorDescriptor
0x18001001e  xor     ecx, ecx; ParentDescriptor
0x180010020  call    cs:__imp_RtlNewSecurityObject
0x180010026  mov     ecx, eax
0x180010028  call    Win32FromNTSTATUS
0x18001002d  mov     ebx, eax
0x18001002f  test    eax, eax
0x180010031  jnz     loc_1800100F4
0x180010037  mov     rcx, [rsp+148h+NewDescriptor]; pSecurityDescriptor
0x18001003c  call    cs:__imp_GetSecurityDescriptorLength
0x180010042  mov     ebx, eax
0x180010044  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18001004b  jz      short loc_18001006E
0x18001004d  mov     edx, 0Ch
0x180010052  mov     dword ptr [rsp+148h+Token], 154h
0x18001005a  mov     ecx, 404h
0x18001005f  lea     r8, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids
0x180010066  mov     r9d, ebx
0x180010069  call    WPP_SF_dd
0x18001006e  lea     r15, qword_18001E240
0x180010075  test    ebx, ebx
0x180010077  jnz     short loc_18001007D
0x180010079  mov     ebx, esi
0x18001007b  jmp     short loc_1800100E0
0x18001007d  mov     rdi, [rsp+148h+NewDescriptor]
0x180010082  test    rdi, rdi
0x180010085  jz      short loc_18001009F
0x180010087  cmp     ebx, 154h
0x18001008d  ja      short loc_18001009F
0x18001008f  mov     r8, rbx; Size
0x180010092  mov     rdx, rdi; Src
0x180010095  mov     rcx, r15; void *
0x180010098  call    memcpy_0
0x18001009d  jmp     short loc_180010079
0x18001009f  xor     edx, edx; Val
0x1800100a1  mov     r8d, 154h; Size
0x1800100a7  mov     rcx, r15; void *
0x1800100aa  call    memset_0
0x1800100af  test    rdi, rdi
0x1800100b2  jnz     short loc_1800100C6
0x1800100b4  call    cs:__imp__o__errno
0x1800100ba  lea     ebx, [rdi+16h]
0x1800100bd  mov     [rax], ebx
0x1800100bf  call    _invalid_parameter_noinfo
0x1800100c4  jmp     short loc_1800100E0
0x1800100c6  cmp     ebx, 154h
0x1800100cc  jbe     short loc_1800100DB
0x1800100ce  call    cs:__imp__o__errno
0x1800100d4  mov     ebx, 22h ; '"'
0x1800100d9  jmp     short loc_1800100BD
0x1800100db  mov     ebx, 16h
0x1800100e0  mov     ecx, ebx
0x1800100e2  call    Win32FromErrno
0x1800100e7  mov     ebx, eax
0x1800100e9  test    eax, eax
0x1800100eb  jnz     short loc_1800100F4
0x1800100ed  mov     cs:qword_18001E230, r15
0x1800100f4  cmp     [rsp+148h+NewDescriptor], rsi
0x1800100f9  jz      short loc_18001010B
0x1800100fb  lea     rcx, [rsp+148h+NewDescriptor]; ObjectDescriptor
0x180010100  call    cs:__imp_RtlDeleteSecurityObject
0x180010106  mov     [rsp+148h+NewDescriptor], rsi
0x18001010b  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180010112  jz      short loc_18001012D
0x180010114  mov     edx, 0Dh
0x180010119  lea     r8, WPP_b20fc9e0e0bb33b8827dda2f53003728_Traceguids
0x180010120  mov     ecx, 404h
0x180010125  mov     r9d, ebx
0x180010128  call    WPP_SF_d
0x18001012d  mov     eax, ebx
0x18001012f  mov     rcx, [rsp+148h+var_38]
0x180010137  xor     rcx, rsp; StackCookie
0x18001013a  call    __security_check_cookie
0x18001013f  add     rsp, 128h
0x180010146  pop     r15
0x180010148  pop     rdi
0x180010149  pop     rsi
0x18001014a  pop     rbx
0x18001014b  retn
```
