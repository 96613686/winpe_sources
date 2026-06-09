# NLregC::CSgetGeneralFlagProperty(ulong,wchar_t * const,ulong,ulong *)

- ea: `0x1801a7020`
- end: `0x1801a7370`
- name: `?CSgetGeneralFlagProperty@NLregC@@QEAAJKQEA_WKPEAK@Z`
- size: `848`
- prototype: `__int64 __fastcall(NLregC *__hidden this, unsigned int, wchar_t *const, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801a7740`

## callees

- `0x180003d80`
- `0x180013360`
- `0x1801a7020`
- `0x1801a75b0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1801a71f3`
- `ADVAPI32!RegOpenKeyExW` at `0x1801a7279`
- `ADVAPI32!RegOpenKeyExW` at `0x1801a71f3`
- `ADVAPI32!RegOpenKeyExW` at `0x1801a7279`
- `ADVAPI32!RegCloseKey` at `0x1801a7318`
- `ADVAPI32!RegCloseKey` at `0x1801a734f`
- `ADVAPI32!RegCloseKey` at `0x1801a7318`
- `ADVAPI32!RegCloseKey` at `0x1801a734f`

## pseudocode

```c
__int64 __fastcall NLregC::CSgetGeneralFlagProperty(
        NLregC *this,
        unsigned int a2,
        wchar_t *const a3,
        int a4,
        unsigned int *a5)
{
  HKEY v5; // rdi
  int v9; // eax
  unsigned int Value; // ebx
  __int64 v11; // rcx
  WCHAR *v12; // rax
  __int64 v13; // rax
  WCHAR *v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rax
  char *v18; // r10
  WCHAR v19; // r8
  WCHAR *v20; // rax
  __int64 v21; // rcx
  WCHAR *v22; // rax
  __int64 v23; // rax
  WCHAR *v24; // rcx
  __int64 v25; // rdx
  char *v26; // r8
  WCHAR v27; // ax
  WCHAR *v28; // rax
  HKEY v29; // rsi
  const wchar_t *v31; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v32; // [rsp+40h] [rbp-C8h]
  unsigned int *v33; // [rsp+48h] [rbp-C0h]
  HKEY hKey; // [rsp+50h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t SubKey[256]; // [rsp+68h] [rbp-A0h] BYREF

  v5 = 0;
  phkResult = 0;
  if ( a3 && (unsigned int)(a4 - 1) > 0x1FF )
    goto LABEL_48;
  if ( *(_WORD *)this == 8 )
  {
    v9 = StringCchPrintfW(SubKey, 0x100u, L"SOFTWARE\\Microsoft\\MSSQLServer\\Client\\SuperSocketNetLib");
    goto LABEL_7;
  }
  if ( *(_WORD *)this <= 8u )
  {
LABEL_48:
    Value = 87;
    goto LABEL_49;
  }
  _mm_lfence();
  v9 = StringCchPrintfW(SubKey, 0x100u, L"SOFTWARE\\Microsoft\\MSSQLServer\\Client\\SNI%d.0", *(unsigned __int16 *)this);
LABEL_7:
  Value = (v9 >> 31) & 0x7A;
  if ( Value )
    goto LABEL_49;
  v11 = 256;
  v12 = SubKey;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = 256 - v11;
  if ( !v11 )
    goto LABEL_48;
  v14 = &SubKey[v13];
  v15 = 2147483646;
  v16 = 256 - v13;
  if ( v13 != 256 )
  {
    v17 = 2147483646;
    v18 = (char *)((char *)L"\\" - (char *)v14);
    do
    {
      if ( !v17 )
        break;
      v19 = *(WCHAR *)((char *)v14 + (_QWORD)v18);
      if ( !v19 )
        break;
      *v14 = v19;
      --v17;
      ++v14;
      --v16;
    }
    while ( v16 );
  }
  v20 = v14 - 1;
  if ( v16 )
    v20 = v14;
  *v20 = 0;
  if ( !v16 )
    goto LABEL_48;
  v21 = 256;
  v22 = SubKey;
  do
  {
    if ( !*v22 )
      break;
    ++v22;
    --v21;
  }
  while ( v21 );
  v23 = 256 - v21;
  if ( !v21 )
    goto LABEL_48;
  v24 = &SubKey[v23];
  v25 = 256 - v23;
  if ( v23 != 256 )
  {
    v26 = (char *)((char *)L"GeneralFlags" - (char *)v24);
    do
    {
      if ( !v15 )
        break;
      v27 = *(WCHAR *)((char *)v24 + (_QWORD)v26);
      if ( !v27 )
        break;
      *v24 = v27;
      --v15;
      ++v24;
      --v25;
    }
    while ( v25 );
  }
  v28 = v24 - 1;
  if ( v25 )
    v28 = v24;
  *v28 = 0;
  if ( !v25 )
    goto LABEL_48;
  Value = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &phkResult);
  if ( !Value )
  {
    if ( a3 )
      *a3 = 0;
    v29 = phkResult;
    Value = 0;
    hKey = 0;
    if ( !phkResult || a3 && (unsigned int)(a4 - 1) > 0x1FF )
    {
      Value = 87;
    }
    else
    {
      if ( (int)StringCchPrintfW(SubKey, 0x100u, L"Flag%d", a2) >= 0 )
      {
        Value = RegOpenKeyExW(v29, SubKey, 0, 1u, &hKey);
        if ( !Value )
        {
          if ( !a3
            || *a3
            || (v31 = L"Label",
                LODWORD(v32) = 1,
                v33 = (unsigned int *)a3,
                HIDWORD(v32) = a4,
                (Value = CS_VALUE::GetValue((CS_VALUE *)&v31, hKey)) == 0) )
          {
            v31 = L"Value";
            v33 = a5;
            v32 = 0x400000004LL;
            Value = CS_VALUE::GetValue((CS_VALUE *)&v31, hKey);
          }
        }
      }
      v5 = hKey;
    }
    if ( v5 )
      RegCloseKey(v5);
  }
LABEL_49:
  if ( phkResult )
    RegCloseKey(phkResult);
  return Value;
}

```

## disassembly

```asm
0x1801a7020  mov     r11, rsp
0x1801a7023  push    rbp
0x1801a7024  push    rbx
0x1801a7025  lea     rbp, [r11-1A8h]
0x1801a702c  sub     rsp, 298h
0x1801a7033  mov     rax, cs:__security_cookie
0x1801a703a  xor     rax, rsp
0x1801a703d  mov     [rbp+1A0h+var_40], rax
0x1801a7044  mov     [r11-20h], rdi
0x1801a7048  xor     edi, edi
0x1801a704a  mov     [r11-28h], r12
0x1801a704e  mov     r12d, edx
0x1801a7051  mov     [r11-30h], r14
0x1801a7055  mov     r14, r8
0x1801a7058  mov     [r11-38h], r15
0x1801a705c  mov     r15d, r9d
0x1801a705f  mov     [rsp+2A0h+phkResult], rdi
0x1801a7064  test    r8, r8
0x1801a7067  jz      short loc_1801A7078
0x1801a7069  lea     eax, [r9-1]
0x1801a706d  cmp     eax, 1FFh
0x1801a7072  ja      loc_1801A7320
0x1801a7078  movzx   eax, word ptr [rcx]
0x1801a707b  mov     ecx, 8
0x1801a7080  cmp     cx, ax
0x1801a7083  jnz     short loc_1801A709D
0x1801a7085  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\MSSQLServer\\Clien"...
0x1801a708c  mov     edx, 100h; unsigned __int64
0x1801a7091  lea     rcx, [rsp+2A0h+SubKey]; Buffer
0x1801a7096  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801a709b  jmp     short loc_1801A70BF
0x1801a709d  jnb     loc_1801A7320
0x1801a70a3  lfence
0x1801a70a6  mov     r9d, eax
0x1801a70a9  lea     r8, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\MSSQLServer\\Clien"...
0x1801a70b0  mov     edx, 100h; unsigned __int64
0x1801a70b5  lea     rcx, [rsp+2A0h+SubKey]; Buffer
0x1801a70ba  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801a70bf  mov     ebx, eax
0x1801a70c1  sar     ebx, 1Fh
0x1801a70c4  and     ebx, 7Ah
0x1801a70c7  jnz     loc_1801A7325
0x1801a70cd  mov     ecx, 100h
0x1801a70d2  lea     rax, [rsp+2A0h+SubKey]
0x1801a70d7  cmp     [rax], di
0x1801a70da  jz      short loc_1801A70E6
0x1801a70dc  add     rax, 2
0x1801a70e0  sub     rcx, 1
0x1801a70e4  jnz     short loc_1801A70D7
0x1801a70e6  mov     eax, 100h
0x1801a70eb  sub     rax, rcx
0x1801a70ee  test    rcx, rcx
0x1801a70f1  cmovz   rax, rdi
0x1801a70f5  jz      loc_1801A7320
0x1801a70fb  mov     edx, 100h
0x1801a7100  lea     rcx, [rsp+2A0h+SubKey]
0x1801a7105  lea     rcx, [rcx+rax*2]
0x1801a7109  mov     r9d, 7FFFFFFEh
0x1801a710f  sub     rdx, rax
0x1801a7112  jz      short loc_1801A7142
0x1801a7114  lea     r10, asc_1801E51B0; "\\"
0x1801a711b  mov     eax, r9d
0x1801a711e  sub     r10, rcx
0x1801a7121  test    rax, rax
0x1801a7124  jz      short loc_1801A7142
0x1801a7126  movzx   r8d, word ptr [r10+rcx]
0x1801a712b  test    r8w, r8w
0x1801a712f  jz      short loc_1801A7142
0x1801a7131  mov     [rcx], r8w
0x1801a7135  dec     rax
0x1801a7138  add     rcx, 2
0x1801a713c  sub     rdx, 1
0x1801a7140  jnz     short loc_1801A7121
0x1801a7142  test    rdx, rdx
0x1801a7145  lea     rax, [rcx-2]
0x1801a7149  cmovnz  rax, rcx
0x1801a714d  mov     [rax], di
0x1801a7150  jz      loc_1801A7320
0x1801a7156  mov     ecx, 100h
0x1801a715b  lea     rax, [rsp+2A0h+SubKey]
0x1801a7160  cmp     [rax], di
0x1801a7163  jz      short loc_1801A716F
0x1801a7165  add     rax, 2
0x1801a7169  sub     rcx, 1
0x1801a716d  jnz     short loc_1801A7160
0x1801a716f  mov     eax, 100h
0x1801a7174  sub     rax, rcx
0x1801a7177  test    rcx, rcx
0x1801a717a  cmovz   rax, rdi
0x1801a717e  jz      loc_1801A7320
0x1801a7184  mov     edx, 100h
0x1801a7189  lea     rcx, [rsp+2A0h+SubKey]
0x1801a718e  lea     rcx, [rcx+rax*2]
0x1801a7192  sub     rdx, rax
0x1801a7195  jz      short loc_1801A71C0
0x1801a7197  lea     r8, aGeneralflags; "GeneralFlags"
0x1801a719e  sub     r8, rcx
0x1801a71a1  test    r9, r9
0x1801a71a4  jz      short loc_1801A71C0
0x1801a71a6  movzx   eax, word ptr [r8+rcx]
0x1801a71ab  test    ax, ax
0x1801a71ae  jz      short loc_1801A71C0
0x1801a71b0  mov     [rcx], ax
0x1801a71b3  dec     r9
0x1801a71b6  add     rcx, 2
0x1801a71ba  sub     rdx, 1
0x1801a71be  jnz     short loc_1801A71A1
0x1801a71c0  test    rdx, rdx
0x1801a71c3  lea     rax, [rcx-2]
0x1801a71c7  cmovnz  rax, rcx
0x1801a71cb  mov     [rax], di
0x1801a71ce  jz      loc_1801A7320
0x1801a71d4  lea     rax, [rsp+2A0h+phkResult]
0x1801a71d9  mov     r9d, 1; samDesired
0x1801a71df  xor     r8d, r8d; ulOptions
0x1801a71e2  mov     [rsp+20h], rax; phkResult
0x1801a71e7  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x1801a71ec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801a71f3  call    cs:__imp_RegOpenKeyExW
0x1801a71f9  mov     ebx, eax
0x1801a71fb  test    eax, eax
0x1801a71fd  jnz     loc_1801A7325
0x1801a7203  mov     [rsp+290h], rsi
0x1801a720b  test    r14, r14
0x1801a720e  jz      short loc_1801A7214
0x1801a7210  mov     [r14], di
0x1801a7214  mov     rsi, [rsp+2A0h+phkResult]
0x1801a7219  mov     ebx, edi
0x1801a721b  mov     [rsp+2A0h+hKey], rdi
0x1801a7220  test    rsi, rsi
0x1801a7223  jz      loc_1801A7303
0x1801a7229  test    r14, r14
0x1801a722c  jz      short loc_1801A723D
0x1801a722e  lea     eax, [r15-1]
0x1801a7232  cmp     eax, 1FFh
0x1801a7237  ja      loc_1801A7303
0x1801a723d  mov     r9d, r12d
0x1801a7240  lea     r8, aFlagD; "Flag%d"
0x1801a7247  mov     edx, 100h; unsigned __int64
0x1801a724c  lea     rcx, [rsp+2A0h+SubKey]; Buffer
0x1801a7251  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801a7256  test    eax, eax
0x1801a7258  js      loc_1801A72FC
0x1801a725e  lea     rax, [rsp+2A0h+hKey]
0x1801a7263  mov     r9d, 1; samDesired
0x1801a7269  xor     r8d, r8d; ulOptions
0x1801a726c  mov     [rsp+20h], rax; phkResult
0x1801a7271  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x1801a7276  mov     rcx, rsi; hKey
0x1801a7279  call    cs:__imp_RegOpenKeyExW
0x1801a727f  mov     ebx, eax
0x1801a7281  test    eax, eax
0x1801a7283  jnz     short loc_1801A72FC
0x1801a7285  test    r14, r14
0x1801a7288  jz      short loc_1801A72C3
0x1801a728a  cmp     [r14], di
0x1801a728e  jnz     short loc_1801A72C3
0x1801a7290  mov     rdx, [rsp+2A0h+hKey]; HKEY
0x1801a7295  lea     rax, aLabel; "Label"
0x1801a729c  lea     rcx, [rsp+2A0h+var_270]; this
0x1801a72a1  mov     qword ptr [rsp+2A0h+var_270], rax
0x1801a72a6  mov     dword ptr [rsp+2A0h+var_268], 1
0x1801a72ae  mov     [rsp+2A0h+var_260], r14
0x1801a72b3  mov     dword ptr [rsp+2A0h+var_268+4], r15d
0x1801a72b8  call    ?GetValue@CS_VALUE@@AEAAJPEAUHKEY__@@@Z; CS_VALUE::GetValue(HKEY__ *)
0x1801a72bd  mov     ebx, eax
0x1801a72bf  test    eax, eax
0x1801a72c1  jnz     short loc_1801A72FC
0x1801a72c3  mov     rdx, [rsp+2A0h+hKey]; HKEY
0x1801a72c8  lea     rax, aValue; "Value"
0x1801a72cf  mov     qword ptr [rsp+2A0h+var_270], rax
0x1801a72d4  lea     rcx, [rsp+2A0h+var_270]; this
0x1801a72d9  mov     rax, [rbp+1A0h+arg_20]
0x1801a72e0  mov     [rsp+2A0h+var_260], rax
0x1801a72e5  mov     dword ptr [rsp+2A0h+var_268], 4
0x1801a72ed  mov     dword ptr [rsp+2A0h+var_268+4], 4
0x1801a72f5  call    ?GetValue@CS_VALUE@@AEAAJPEAUHKEY__@@@Z; CS_VALUE::GetValue(HKEY__ *)
0x1801a72fa  mov     ebx, eax
0x1801a72fc  mov     rdi, [rsp+2A0h+hKey]
0x1801a7301  jmp     short loc_1801A7308
0x1801a7303  mov     ebx, 57h ; 'W'
0x1801a7308  mov     rsi, [rsp+290h]
0x1801a7310  test    rdi, rdi
0x1801a7313  jz      short loc_1801A7325
0x1801a7315  mov     rcx, rdi; hKey
0x1801a7318  call    cs:__imp_RegCloseKey
0x1801a731e  jmp     short loc_1801A7325
0x1801a7320  mov     ebx, 57h ; 'W'
0x1801a7325  mov     rcx, [rsp+2A0h+phkResult]; hKey
0x1801a732a  mov     r15, [rsp+2A0h+var_30]
0x1801a7332  mov     r14, [rsp+2A0h+var_28]
0x1801a733a  mov     r12, [rsp+2A0h+var_20]
0x1801a7342  mov     rdi, [rsp+2A0h+var_18]
0x1801a734a  test    rcx, rcx
0x1801a734d  jz      short loc_1801A7355
0x1801a734f  call    cs:__imp_RegCloseKey
0x1801a7355  mov     eax, ebx
0x1801a7357  mov     rcx, [rbp+1A0h+var_40]
0x1801a735e  xor     rcx, rsp; StackCookie
0x1801a7361  call    __security_check_cookie
0x1801a7366  add     rsp, 298h
0x1801a736d  pop     rbx
0x1801a736e  pop     rbp
0x1801a736f  retn
```
