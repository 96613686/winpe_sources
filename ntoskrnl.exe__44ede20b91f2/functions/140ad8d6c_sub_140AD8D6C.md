# sub_140AD8D6C

- ea: `0x140ad8d6c`
- end: `0x140ad949d`
- name: `sub_140AD8D6C`
- size: `1841`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x14076bbe0`
- `0x14076bcc0`

## callees

- `0x1403f2d50`
- `0x1404c21c0`
- `0x14053cf40`
- `0x14053e920`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406f4480`
- `0x1408b9700`
- `0x1408ba060`
- `0x14095c4f0`
- `0x14096c1c0`
- `0x14097499c`
- `0x1409b4a70`
- `0x140a719bc`
- `0x140ad8d6c`
- `0x140bae410`
- `0x140bae8c0`
- `0x140bae8e0`

## string_xrefs

- `0x140ad8fec`: `\Registry\Machine\HARDWARE`
- `0x140ad9038`: `KeyPath`
- `0x140ad8fb0`: `\Registry\Machine\SYSTEM`
- `0x140ad8fcc`: `\Registry\Machine\SOFTWARE`

## pseudocode

```c
__int64 __fastcall sub_140AD8D6C(_QWORD *a1, void *a2, _QWORD *a3)
{
  void *v5; // r12
  int v6; // ebx
  unsigned int v7; // esi
  const wchar_t *v8; // rbx
  wchar_t **v9; // rdi
  int v10; // ecx
  int v11; // r8d
  __int64 v12; // rdx
  unsigned int v13; // edi
  int v14; // eax
  int v15; // eax
  const WCHAR *v16; // rsi
  int v17; // eax
  wchar_t *v18; // rax
  int v19; // eax
  const wchar_t *v20; // rsi
  wchar_t *v21; // rax
  int v22; // r15d
  unsigned int v23; // r13d
  _WORD *v24; // r12
  wchar_t *v25; // rax
  wchar_t *v26; // rsi
  __int64 v27; // rdi
  int v28; // edi
  char *v29; // r15
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rdi
  __int64 v33; // rax
  PVOID v34; // rcx
  __int64 v36; // rax
  unsigned int v37; // ebx
  wchar_t *v38; // rsi
  _WORD *v39; // r13
  unsigned int v40; // r12d
  wchar_t *v41; // rax
  wchar_t *v42; // r15
  __int64 v43; // rdi
  unsigned int v44; // edi
  wchar_t *v45; // r9
  __int64 v46; // rdx
  __int64 v47; // rdi
  wchar_t *v48; // r15
  __int64 v49; // rax
  bool v50; // zf
  UNICODE_STRING v51; // xmm0
  HANDLE v52; // rax
  int v53; // [rsp+40h] [rbp-C0h]
  unsigned int v54; // [rsp+40h] [rbp-C0h]
  PVOID P; // [rsp+48h] [rbp-B8h]
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v57; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  PVOID Pool2; // [rsp+70h] [rbp-90h]
  int v60; // [rsp+78h] [rbp-88h] BYREF
  int v61; // [rsp+7Ch] [rbp-84h] BYREF
  HANDLE v62; // [rsp+80h] [rbp-80h] BYREF
  void *v63; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *Str; // [rsp+90h] [rbp-70h]
  UNICODE_STRING v65; // [rsp+A0h] [rbp-60h]
  _QWORD *v66; // [rsp+B0h] [rbp-50h]
  _QWORD *v67; // [rsp+B8h] [rbp-48h]
  _BYTE v68[76]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v69; // [rsp+10Ch] [rbp+Ch]

  v67 = a3;
  *a3 = 0;
  v66 = a1;
  v53 = 0;
  v65.MaximumLength = 0;
  *(_DWORD *)(&v65.MaximumLength + 1) = 0;
  Handle = 0;
  v63 = 0;
  DestinationString = 0;
  v62 = 0;
  v5 = 0;
  v60 = 0;
  v61 = 0;
  v6 = sub_14097499C(a2);
  if ( v6 >= 0 )
  {
    if ( !(unsigned __int8)sub_1404C21C0(0) )
    {
LABEL_3:
      v6 = -1073741823;
      goto LABEL_67;
    }
    v7 = 0;
    v8 = (const wchar_t *)MEMORY[8];
    Pool2 = 0;
    while ( 1 )
    {
      if ( v7 >= 7 )
        goto LABEL_22;
      v9 = &(&off_140B7B3B0)[4 * v7];
      if ( !wcsicmp(*v9, v8) )
        break;
      ++v7;
    }
    if ( v9 )
    {
      v11 = *((_DWORD *)v9 + 4);
      v12 = *a1;
      if ( !v11 )
      {
        v15 = *((_DWORD *)v9 + 3);
        if ( !v15 )
        {
          v6 = -1073741595;
          goto LABEL_67;
        }
        if ( v15 == 7 )
        {
          v60 = 78;
          v6 = sub_1408B9700(
                 qword_140E4C568,
                 *(_QWORD *)(v12 + 48),
                 0,
                 9,
                 (__int64)&v61,
                 (__int64)v68,
                 (__int64)&v60,
                 0);
          if ( v6 < 0 )
            goto LABEL_67;
          if ( v61 != 1 )
            goto LABEL_3;
          v69 = 0;
          v16 = (const WCHAR *)v68;
        }
        else
        {
          v16 = v9[3];
        }
        v17 = sub_14095C4F0(v10, *((_DWORD *)v9 + 3), v11, 131097, (__int64)&Handle);
        v13 = 0;
        v6 = v17;
        if ( v17 < 0 )
          goto LABEL_67;
        if ( v16 )
        {
          RtlInitUnicodeString(&DestinationString, v16);
          v6 = sub_14096C1C0(&v63, Handle, &DestinationString, 131097);
          if ( v6 < 0 )
            goto LABEL_67;
          ZwClose(Handle);
          Handle = v63;
        }
LABEL_31:
        ExFreePoolWithTag(0, 0);
        v19 = sub_14097499C(a2);
        v6 = v19;
        if ( v19 < 0 )
        {
          if ( v19 != -1073741772 )
            goto LABEL_67;
          v52 = Handle;
          v6 = 0;
          v62 = Handle;
          Handle = 0;
        }
        else
        {
          if ( !(unsigned __int8)sub_1404C21C0(0) )
            goto LABEL_3;
          Str = (wchar_t *)MEMORY[8];
          v20 = (const wchar_t *)MEMORY[8];
          v21 = wcschr((const wchar_t *)MEMORY[8], 0x24u);
          if ( !v21 )
            goto LABEL_104;
          do
          {
            ++v13;
            v21 = wcschr(v21 + 1, 0x24u);
          }
          while ( v21 );
          v57 = v13;
          if ( v13 )
          {
            Pool2 = (PVOID)ExAllocatePool2(256, 8LL * v13, 1667526736);
            if ( !Pool2 )
            {
              v6 = -1073741670;
              goto LABEL_67;
            }
            v22 = 0;
            v23 = 0;
            while ( 1 )
            {
              v24 = v20;
              if ( !*v20 || v23 >= v13 )
                break;
              v25 = wcschr(v20, 0x5Cu);
              v26 = v25;
              if ( v25 )
              {
                *v25 = 0;
                v27 = v25 - v24;
              }
              else
              {
                v27 = -1;
                do
                  ++v27;
                while ( v24[v27] );
              }
              v28 = 2 * v27;
              if ( *v24 == 36 )
              {
                v29 = (char *)Pool2 + 8 * v23;
                v30 = sub_1409B4A70(v66, v24 + 1, v29);
                v6 = v30;
                if ( v30 < 0 )
                {
                  if ( v30 != -1073741772 )
                    goto LABEL_65;
                  v6 = 0;
                }
                else
                {
                  v31 = *(_QWORD *)v29;
                  if ( *(_DWORD *)(*(_QWORD *)v29 + 32LL) == 1 || *(_DWORD *)(*(_QWORD *)v29 + 32LL) == 2 )
                  {
                    v28 = *(_DWORD *)(v31 + 36) - 2;
                  }
                  else if ( *(_DWORD *)(*(_QWORD *)v29 + 32LL) == 7 )
                  {
                    v32 = -1;
                    do
                      ++v32;
                    while ( *(_WORD *)(*(_QWORD *)(v31 + 40) + 2 * v32) );
                    v28 = 2 * v32;
                  }
                }
                v22 = v53;
                ++v23;
              }
              if ( (unsigned __int64)(v28 + (unsigned int)(unsigned __int16)v22) + 2 >= 0xFFFE )
              {
                v6 = -2147483643;
LABEL_65:
                v34 = Pool2;
                goto LABEL_66;
              }
              LOWORD(v22) = v28 + 2 + v22;
              v53 = v22;
              v65.MaximumLength = v22;
              if ( v26 )
              {
                *v26 = 92;
                v20 = v26 + 1;
              }
              else
              {
                v33 = -1;
                do
                  ++v33;
                while ( v24[v33] );
                v20 = &v24[v33];
              }
              v13 = v57;
            }
            if ( v6 < 0 )
              goto LABEL_65;
            v65.Length = v22 - 2;
            v36 = ExAllocatePool2(256, (unsigned __int16)v22, 1667526736);
            v37 = 0;
            P = (PVOID)v36;
            v65.Buffer = (wchar_t *)v36;
            if ( !v36 )
            {
              v6 = -1073741670;
LABEL_73:
              v5 = P;
LABEL_111:
              if ( v5 )
                ExFreePool(v5);
              v34 = Pool2;
              if ( Pool2 )
LABEL_66:
                ExFreePoolWithTag(v34, 0);
              goto LABEL_67;
            }
            v38 = Str;
            v39 = (_WORD *)v36;
            v40 = (unsigned __int16)v22;
            v54 = 0;
            while ( *v38 && v37 < v57 )
            {
              v41 = wcschr(v38, 0x5Cu);
              v42 = v41;
              if ( v41 )
              {
                *v41 = 0;
                v43 = v41 - v38;
              }
              else
              {
                v43 = -1;
                do
                  ++v43;
                while ( v38[v43] );
              }
              if ( v38 != Str )
              {
                if ( v40 <= 2 )
                  goto LABEL_100;
                *v39++ = 92;
                v40 -= 2;
              }
              v44 = 2 * v43;
              v45 = v38;
              if ( *v38 == 36 )
              {
                v54 = v37 + 1;
                v46 = *((_QWORD *)Pool2 + v37);
                if ( v46 )
                {
                  if ( *(_DWORD *)(v46 + 32) == 1 || *(_DWORD *)(v46 + 32) == 2 )
                  {
                    v45 = *(wchar_t **)(v46 + 40);
                    v44 = *(_DWORD *)(v46 + 36) - 2;
                  }
                  else if ( *(_DWORD *)(v46 + 32) == 7 )
                  {
                    v45 = *(wchar_t **)(v46 + 40);
                    v47 = -1;
                    do
                      ++v47;
                    while ( v45[v47] );
                    v44 = 2 * v47;
                  }
                }
              }
              if ( v40 <= v44 )
              {
LABEL_100:
                v6 = -1073741823;
                goto LABEL_73;
              }
              memmove(v39, v45, v44);
              v40 -= v44;
              v39 += (unsigned __int64)v44 >> 1;
              if ( v42 )
              {
                *v42 = 92;
                v48 = v42 + 1;
              }
              else
              {
                v49 = -1;
                do
                  ++v49;
                while ( v38[v49] );
                v48 = &v38[v49];
              }
              v37 = v54;
              v38 = v48;
            }
            v50 = v40 == 2;
            v5 = P;
            if ( !v50 )
            {
              v6 = -1073741823;
              goto LABEL_111;
            }
            v51 = v65;
            *v39 = 0;
            DestinationString = v51;
          }
          else
          {
LABEL_104:
            v57 = 0;
            sub_140A719BC(MEMORY[8], MEMORY[0xC], &v57);
            DestinationString.Length = v57;
            DestinationString.MaximumLength = MEMORY[0xC];
            DestinationString.Buffer = (wchar_t *)MEMORY[8];
          }
          v6 = sub_14096C1C0(&v62, Handle, &DestinationString, 131097);
          if ( v6 < 0 )
            goto LABEL_111;
          v52 = v62;
        }
        *v67 = v52;
        goto LABEL_111;
      }
      v13 = 0;
      v14 = sub_1408BA060(*(__int64 *)&qword_140E4C568, *(_QWORD *)(v12 + 48), v11, 0, 131097, 0, (__int64)&Handle, 0);
    }
    else
    {
LABEL_22:
      v13 = 0;
      if ( wcsicmp(v8, L"SYSTEM") )
      {
        if ( wcsicmp(v8, L"SOFTWARE") )
        {
          if ( wcsicmp(v8, L"HARDWARE") )
          {
            v6 = -1073741772;
            goto LABEL_111;
          }
          v18 = L"\\Registry\\Machine\\HARDWARE";
        }
        else
        {
          v18 = L"\\Registry\\Machine\\SOFTWARE";
        }
        *(_DWORD *)&DestinationString.Length = 3538996;
      }
      else
      {
        *(_DWORD *)&DestinationString.Length = 3276848;
        v18 = L"\\Registry\\Machine\\SYSTEM";
      }
      DestinationString.Buffer = v18;
      v14 = sub_14096C1C0(&Handle, 0, &DestinationString, 131097);
    }
    v6 = v14;
    if ( v14 < 0 )
      goto LABEL_67;
    goto LABEL_31;
  }
LABEL_67:
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140ad8d6c  mov     [rsp-8+arg_18], rbx
0x140ad8d71  push    rbp
0x140ad8d72  push    rsi
0x140ad8d73  push    rdi
0x140ad8d74  push    r12
0x140ad8d76  push    r13
0x140ad8d78  push    r14
0x140ad8d7a  push    r15
0x140ad8d7c  lea     rbp, [rsp-20h]
0x140ad8d81  sub     rsp, 120h
0x140ad8d88  mov     rax, cs:__security_cookie
0x140ad8d8f  xor     rax, rsp
0x140ad8d92  mov     [rbp+50h+var_40], rax
0x140ad8d96  xor     edi, edi
0x140ad8d98  mov     [rbp+50h+var_98], r8
0x140ad8d9c  mov     eax, edi
0x140ad8d9e  mov     [r8], rdi
0x140ad8da1  mov     r15, rdx
0x140ad8da4  mov     [rbp+50h+var_A0], rcx
0x140ad8da8  mov     r13, rcx
0x140ad8dab  mov     [rsp+150h+var_110], eax
0x140ad8daf  xorps   xmm0, xmm0
0x140ad8db2  mov     word ptr [rbp+50h+var_B0+2], ax
0x140ad8db6  xor     r8d, r8d
0x140ad8db9  mov     dword ptr [rbp+50h+var_B0+4], eax
0x140ad8dbc  lea     r9, [rsp+150h+P]
0x140ad8dc1  mov     [rsp+150h+P], rdi
0x140ad8dc6  lea     rdx, aKeyroot; "KeyRoot"
0x140ad8dcd  mov     [rsp+150h+Handle], rdi
0x140ad8dd2  mov     rcx, r15; KeyHandle
0x140ad8dd5  mov     [rbp+50h+var_C8], rdi
0x140ad8dd9  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x140ad8dde  mov     [rbp+50h+var_D0], rdi
0x140ad8de2  mov     r12d, edi
0x140ad8de5  mov     [rsp+150h+var_D8], edi
0x140ad8de9  mov     [rsp+150h+var_D4], edi
0x140ad8ded  call    sub_14097499C
0x140ad8df2  mov     r14, [rsp+150h+P]
0x140ad8df7  mov     ebx, eax
0x140ad8df9  test    eax, eax
0x140ad8dfb  js      loc_140AD9217
0x140ad8e01  mov     rcx, r14
0x140ad8e04  call    sub_1404C21C0
0x140ad8e09  test    al, al
0x140ad8e0b  jnz     short loc_140AD8E17
0x140ad8e0d  mov     ebx, 0C0000001h
0x140ad8e12  jmp     loc_140AD9217
0x140ad8e17  mov     ebx, [r14+8]
0x140ad8e1b  mov     esi, edi
0x140ad8e1d  add     rbx, r14
0x140ad8e20  mov     [rsp+150h+var_E0], rdi
0x140ad8e25  cmp     esi, 7
0x140ad8e28  jnb     loc_140AD8F93
0x140ad8e2e  lea     rcx, off_140B7B3B0; "Device"
0x140ad8e35  mov     edi, esi
0x140ad8e37  shl     rdi, 5
0x140ad8e3b  mov     rdx, rbx; Str2
0x140ad8e3e  add     rdi, rcx
0x140ad8e41  mov     rcx, [rdi]; Str1
0x140ad8e44  call    _wcsicmp
0x140ad8e49  test    eax, eax
0x140ad8e4b  jz      short loc_140AD8E51
0x140ad8e4d  inc     esi
0x140ad8e4f  jmp     short loc_140AD8E25
0x140ad8e51  xor     esi, esi
0x140ad8e53  test    rdi, rdi
0x140ad8e56  jz      loc_140AD8F93
0x140ad8e5c  mov     r8d, [rdi+10h]
0x140ad8e60  mov     rdx, [r13+0]
0x140ad8e64  test    r8d, r8d
0x140ad8e67  jz      short loc_140AD8E9F
0x140ad8e69  mov     rdx, [rdx+30h]
0x140ad8e6d  lea     rax, [rsp+150h+Handle]
0x140ad8e72  mov     rcx, cs:qword_140E4C568
0x140ad8e79  xor     edi, edi
0x140ad8e7b  mov     [rsp+150h+var_118], rdi
0x140ad8e80  xor     r9d, r9d
0x140ad8e83  mov     [rsp+150h+var_120], rax
0x140ad8e88  mov     byte ptr [rsp+150h+var_128], dil
0x140ad8e8d  mov     dword ptr [rsp+150h+var_130], 20019h
0x140ad8e95  call    sub_1408BA060
0x140ad8e9a  jmp     loc_140AD9017
0x140ad8e9f  mov     eax, [rdi+0Ch]
0x140ad8ea2  test    eax, eax
0x140ad8ea4  jz      loc_140AD8F89
0x140ad8eaa  cmp     eax, 7
0x140ad8ead  jz      short loc_140AD8EB5
0x140ad8eaf  mov     rsi, [rdi+18h]
0x140ad8eb3  jmp     short loc_140AD8F14
0x140ad8eb5  mov     rcx, cs:qword_140E4C568
0x140ad8ebc  lea     rax, [rsp+150h+var_D8]
0x140ad8ec1  mov     dword ptr [rsp+150h+var_118], esi
0x140ad8ec5  mov     r9d, 9
0x140ad8ecb  mov     [rsp+150h+var_120], rax
0x140ad8ed0  xor     r8d, r8d
0x140ad8ed3  lea     rax, [rbp+50h+var_90]
0x140ad8ed7  mov     [rsp+150h+var_D8], 4Eh ; 'N'
0x140ad8edf  mov     rdx, [rdx+30h]
0x140ad8ee3  mov     [rsp+150h+var_128], rax
0x140ad8ee8  lea     rax, [rsp+150h+var_D4]
0x140ad8eed  mov     [rsp+150h+var_130], rax
0x140ad8ef2  call    sub_1408B9700
0x140ad8ef7  mov     ebx, eax
0x140ad8ef9  test    eax, eax
0x140ad8efb  js      loc_140AD9217
0x140ad8f01  cmp     [rsp+150h+var_D4], 1
0x140ad8f06  jnz     loc_140AD8E0D
0x140ad8f0c  mov     [rbp+50h+var_44], si
0x140ad8f10  lea     rsi, [rbp+50h+var_90]
0x140ad8f14  mov     edx, [rdi+0Ch]
0x140ad8f17  lea     rax, [rsp+150h+Handle]
0x140ad8f1c  mov     r9d, 20019h
0x140ad8f22  mov     [rsp+150h+var_130], rax
0x140ad8f27  call    sub_14095C4F0
0x140ad8f2c  xor     edi, edi
0x140ad8f2e  mov     ebx, eax
0x140ad8f30  test    eax, eax
0x140ad8f32  js      loc_140AD9217
0x140ad8f38  test    rsi, rsi
0x140ad8f3b  jz      loc_140AD9021
0x140ad8f41  mov     rdx, rsi; SourceString
0x140ad8f44  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x140ad8f49  call    RtlInitUnicodeString
0x140ad8f4e  mov     rdx, [rsp+150h+Handle]
0x140ad8f53  lea     r8, [rsp+150h+DestinationString]
0x140ad8f58  mov     r9d, 20019h
0x140ad8f5e  lea     rcx, [rbp+50h+var_C8]
0x140ad8f62  call    sub_14096C1C0
0x140ad8f67  mov     ebx, eax
0x140ad8f69  test    eax, eax
0x140ad8f6b  js      loc_140AD9217
0x140ad8f71  mov     rcx, [rsp+150h+Handle]; Handle
0x140ad8f76  call    ZwClose
0x140ad8f7b  mov     rax, [rbp+50h+var_C8]
0x140ad8f7f  mov     [rsp+150h+Handle], rax
0x140ad8f84  jmp     loc_140AD9021
0x140ad8f89  mov     ebx, 0C00000E5h
0x140ad8f8e  jmp     loc_140AD9217
0x140ad8f93  lea     rdx, aSystem; "SYSTEM"
0x140ad8f9a  mov     rcx, rbx; Str1
0x140ad8f9d  call    _wcsicmp
0x140ad8fa2  xor     edi, edi
0x140ad8fa4  test    eax, eax
0x140ad8fa6  jnz     short loc_140AD8FB9
0x140ad8fa8  mov     dword ptr [rsp+150h+DestinationString.Length], 320030h
0x140ad8fb0  lea     rax, aRegistryMachin_136; "\\Registry\\Machine\\SYSTEM"
0x140ad8fb7  jmp     short loc_140AD8FFB
0x140ad8fb9  lea     rdx, aSoftware; "SOFTWARE"
0x140ad8fc0  mov     rcx, rbx; Str1
0x140ad8fc3  call    _wcsicmp
0x140ad8fc8  test    eax, eax
0x140ad8fca  jnz     short loc_140AD8FD5
0x140ad8fcc  lea     rax, aRegistryMachin_137; "\\Registry\\Machine\\SOFTWARE"
0x140ad8fd3  jmp     short loc_140AD8FF3
0x140ad8fd5  lea     rdx, aHardware; "HARDWARE"
0x140ad8fdc  mov     rcx, rbx; Str1
0x140ad8fdf  call    _wcsicmp
0x140ad8fe4  test    eax, eax
0x140ad8fe6  jnz     loc_140AD9478
0x140ad8fec  lea     rax, aRegistryMachin_138; "\\Registry\\Machine\\HARDWARE"
0x140ad8ff3  mov     dword ptr [rsp+150h+DestinationString.Length], 360034h
0x140ad8ffb  mov     r9d, 20019h
0x140ad9001  mov     [rsp+150h+DestinationString.Buffer], rax
0x140ad9006  lea     r8, [rsp+150h+DestinationString]
0x140ad900b  xor     edx, edx
0x140ad900d  lea     rcx, [rsp+150h+Handle]
0x140ad9012  call    sub_14096C1C0
0x140ad9017  mov     ebx, eax
0x140ad9019  test    eax, eax
0x140ad901b  js      loc_140AD9217
0x140ad9021  xor     edx, edx; Tag
0x140ad9023  mov     rcx, r14; P
0x140ad9026  call    ExFreePoolWithTag
0x140ad902b  lea     r9, [rsp+150h+P]
0x140ad9030  mov     [rsp+150h+P], rdi
0x140ad9035  xor     r8d, r8d
0x140ad9038  lea     rdx, aKeypath; "KeyPath"
0x140ad903f  mov     rcx, r15; KeyHandle
0x140ad9042  call    sub_14097499C
0x140ad9047  mov     r14, [rsp+150h+P]
0x140ad904c  mov     ebx, eax
0x140ad904e  test    eax, eax
0x140ad9050  js      loc_140AD9454
0x140ad9056  mov     rcx, r14
0x140ad9059  call    sub_1404C21C0
0x140ad905e  test    al, al
0x140ad9060  jz      loc_140AD8E0D
0x140ad9066  mov     esi, [r14+8]
0x140ad906a  mov     r15d, 24h ; '$'
0x140ad9070  add     rsi, r14
0x140ad9073  mov     edx, r15d; Ch
0x140ad9076  mov     rcx, rsi; Str
0x140ad9079  mov     [rbp+50h+Str], rsi
0x140ad907d  call    wcschr
0x140ad9082  test    rax, rax
0x140ad9085  jz      loc_140AD93F4
0x140ad908b  mov     edx, r15d; Ch
0x140ad908e  lea     rcx, [rax+2]; Str
0x140ad9092  inc     edi
0x140ad9094  call    wcschr
0x140ad9099  test    rax, rax
0x140ad909c  jnz     short loc_140AD908B
0x140ad909e  mov     r14, [rsp+150h+P]
0x140ad90a3  mov     [rsp+150h+var_F8], edi
0x140ad90a7  test    edi, edi
0x140ad90a9  jz      loc_140AD93F4
0x140ad90af  mov     edx, edi
0x140ad90b1  mov     ecx, 100h
0x140ad90b6  shl     rdx, 3
0x140ad90ba  mov     r8d, 63647050h
0x140ad90c0  call    ExAllocatePool2
0x140ad90c5  mov     [rsp+150h+var_E0], rax
0x140ad90ca  test    rax, rax
0x140ad90cd  jnz     short loc_140AD90D9
0x140ad90cf  mov     ebx, 0C000009Ah
0x140ad90d4  jmp     loc_140AD9217
0x140ad90d9  mov     r15d, [rsp+150h+var_110]
0x140ad90de  xor     edx, edx
0x140ad90e0  mov     r13d, edx
0x140ad90e3  lea     eax, [rdx+5Ch]
0x140ad90e6  lea     r8d, [rdx+2]
0x140ad90ea  mov     r12, rsi
0x140ad90ed  cmp     [rsi], dx
0x140ad90f0  jz      loc_140AD925F
0x140ad90f6  cmp     r13d, edi
0x140ad90f9  jnb     loc_140AD925F
0x140ad90ff  mov     edx, eax; Ch
0x140ad9101  mov     rcx, rsi; Str
0x140ad9104  call    wcschr
0x140ad9109  xor     edx, edx
0x140ad910b  mov     rsi, rax
0x140ad910e  test    rax, rax
0x140ad9111  jz      short loc_140AD9121
0x140ad9113  mov     rdi, rax
0x140ad9116  mov     [rax], dx
0x140ad9119  sub     rdi, r12
0x140ad911c  sar     rdi, 1
0x140ad911f  jmp     short loc_140AD912F
0x140ad9121  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140ad9125  inc     rdi
0x140ad9128  cmp     [r12+rdi*2], dx
0x140ad912d  jnz     short loc_140AD9125
0x140ad912f  add     edi, edi
0x140ad9131  mov     eax, 24h ; '$'
0x140ad9136  cmp     [r12], ax
0x140ad913b  jnz     short loc_140AD91AB
0x140ad913d  mov     rcx, [rsp+150h+var_E0]
0x140ad9142  lea     rdx, [r12+2]
0x140ad9147  mov     eax, r13d
0x140ad914a  lea     r15, [rcx+rax*8]
0x140ad914e  mov     rcx, [rbp+50h+var_A0]
0x140ad9152  mov     r8, r15
0x140ad9155  call    sub_1409B4A70
0x140ad915a  xor     edx, edx
0x140ad915c  mov     ebx, eax
0x140ad915e  test    eax, eax
0x140ad9160  js      short loc_140AD919A
0x140ad9162  mov     rdx, [r15]
0x140ad9165  mov     ecx, [rdx+20h]
0x140ad9168  sub     ecx, 1
0x140ad916b  jz      short loc_140AD9192
0x140ad916d  sub     ecx, 1
0x140ad9170  jz      short loc_140AD9192
0x140ad9172  cmp     ecx, 5
0x140ad9175  jz      short loc_140AD917B
0x140ad9177  xor     edx, edx
0x140ad9179  jmp     short loc_140AD91A3
0x140ad917b  mov     rax, [rdx+28h]
0x140ad917f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140ad9183  xor     edx, edx
0x140ad9185  inc     rdi
0x140ad9188  cmp     [rax+rdi*2], dx
0x140ad918c  jnz     short loc_140AD9185
0x140ad918e  add     edi, edi
0x140ad9190  jmp     short loc_140AD91A3
0x140ad9192  mov     edi, [rdx+24h]
0x140ad9195  sub     edi, 2
0x140ad9198  jmp     short loc_140AD9177
0x140ad919a  cmp     eax, 0C0000034h
0x140ad919f  jnz     short loc_140AD920B
0x140ad91a1  mov     ebx, edx
0x140ad91a3  mov     r15d, [rsp+150h+var_110]
0x140ad91a8  inc     r13d
0x140ad91ab  movzx   ecx, r15w
0x140ad91af  mov     r8d, 2
0x140ad91b5  add     ecx, edi
0x140ad91b7  add     rcx, r8
0x140ad91ba  cmp     rcx, 0FFFEh
0x140ad91c1  jnb     short loc_140AD9206
0x140ad91c3  add     di, r8w
0x140ad91c7  add     r15w, di
0x140ad91cb  mov     [rsp+150h+var_110], r15d
0x140ad91d0  mov     word ptr [rbp+50h+var_B0+2], r15w
0x140ad91d5  test    rsi, rsi
0x140ad91d8  jz      short loc_140AD91E6
0x140ad91da  lea     eax, [r8+5Ah]
0x140ad91de  mov     [rsi], ax
0x140ad91e1  add     rsi, r8
0x140ad91e4  jmp     short loc_140AD91FD
0x140ad91e6  or      rax, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
