# ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)

- ea: `0x180011504`
- end: `0x180011c0c`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z`
- size: `1800`
- prototype: `__int64 __usercall@<rax>(ATL::CRegParser *__hidden this@<rcx>, wchar_t *@<rdx>, HKEY@<r8>, int@<r9d>, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x180011168`
- `0x180011504`

## callees

- `0x18000aa00`
- `0x18000be24`
- `0x18000c2fc`
- `0x18000c948`
- `0x18000cb08`
- `0x18000e35c`
- `0x18000f0d4`
- `0x18000f158`
- `0x18000fe18`
- `0x180010074`
- `0x180011038`
- `0x180011504`
- `0x180012470`
- `0x180012534`
- `0x180012ae8`
- `0x1800273b0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x180011595`
- `KERNEL32!lstrcmpiW` at `0x1800115a8`
- `KERNEL32!lstrcmpiW` at `0x180011675`
- `KERNEL32!lstrcmpiW` at `0x1800116a3`
- `KERNEL32!lstrcmpiW` at `0x1800118b9`
- `KERNEL32!lstrcmpiW` at `0x180011595`
- `KERNEL32!lstrcmpiW` at `0x1800115a8`
- `KERNEL32!lstrcmpiW` at `0x180011675`
- `KERNEL32!lstrcmpiW` at `0x1800116a3`
- `KERNEL32!lstrcmpiW` at `0x1800118b9`
- `KERNEL32!lstrcpynW` at `0x1800119df`
- `KERNEL32!lstrcpynW` at `0x1800119df`
- `ADVAPI32!RegDeleteValueW` at `0x180011772`
- `ADVAPI32!RegDeleteValueW` at `0x180011772`
- `ADVAPI32!RegCreateKeyExW` at `0x18001186c`
- `ADVAPI32!RegCreateKeyExW` at `0x18001186c`

## string_xrefs

- `0x18001159e`: `ForceRemove`
- `0x18001166b`: `NoRemove`
- `0x18001158b`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(ATL::CRegParser *this, wchar_t *a2, HKEY a3, int a4, int a5)
{
  HKEY v7; // r15
  signed int Token; // ebx
  int *v9; // r13
  int v10; // r12d
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // r14d
  int v14; // eax
  LSTATUS v15; // eax
  int v16; // eax
  unsigned __int64 v18; // rdx
  HKEY v19; // rbx
  bool v20; // r14
  int v21; // eax
  __int64 v22; // rax
  HKEY v23; // r14
  void *v24; // rsp
  ATL::CRegParser *v25; // rcx
  ATL::CRegParser *v26; // rcx
  ATL::CRegParser *v27; // rcx
  ATL::CRegParser *v28; // rcx
  DWORD dwOptions; // [rsp+20h] [rbp-30h]
  int v30; // [rsp+50h] [rbp+0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+8h] BYREF
  __int64 v32; // [rsp+60h] [rbp+10h]
  __int64 v33; // [rsp+68h] [rbp+18h]
  _QWORD v34[3]; // [rsp+70h] [rbp+20h] BYREF
  HKEY v35; // [rsp+88h] [rbp+38h]
  int v36; // [rsp+90h] [rbp+40h]
  DWORD dwDisposition; // [rsp+94h] [rbp+44h] BYREF
  int v38; // [rsp+98h] [rbp+48h]
  HKEY phkResult; // [rsp+A0h] [rbp+50h] BYREF
  __int64 v40; // [rsp+A8h] [rbp+58h] BYREF
  WCHAR ValueName[264]; // [rsp+B0h] [rbp+60h] BYREF

  v30 = a4;
  v35 = a3;
  v40 = 0;
  v7 = 0;
  memset(v34, 0, sizeof(v34));
  Token = ATL::CRegParser::NextToken(this, a2);
  if ( Token >= 0 )
  {
    v9 = 0;
    v36 = 1;
    v10 = a5;
    v38 = a5;
    while ( *a2 != 125 )
    {
      v11 = lstrcmpiW(a2, L"Delete");
      if ( lstrcmpiW(a2, L"ForceRemove") && v11 )
        goto LABEL_16;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        break;
      if ( !v30 )
        goto LABEL_16;
      hKey = 0;
      v32 = 0;
      v33 = 0;
      if ( ATL::CRegParser::StrChrW(a2, 0x5Cu) )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
        ATL::CRegKey::Close((ATL::CRegKey *)v34);
        goto LABEL_84;
      }
      if ( ATL::CRegParser::CanForceRemoveKey(v12, a2) )
      {
        hKey = v35;
        ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, a2);
        hKey = 0;
      }
      if ( v11 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_16:
        if ( !lstrcmpiW(a2, L"NoRemove") )
        {
          v36 = 0;
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            break;
        }
        if ( lstrcmpiW(a2, L"Val") )
        {
          if ( ATL::CRegParser::StrChrW(a2, 0x5Cu) )
            goto LABEL_39;
          if ( v30 )
          {
            v19 = v35;
            v20 = 0;
            if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, v35, a2, 0xF003Fu, dwOptions)
              && (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, v19, a2, 0x20019u, dwOptions) )
            {
              dwDisposition = 0;
              phkResult = 0;
              if ( RegCreateKeyExW(v19, a2, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition) )
                goto LABEL_39;
              v21 = ATL::CRegKey::Close((ATL::CRegKey *)v34);
              v7 = phkResult;
              v34[0] = phkResult;
              if ( v21 )
                goto LABEL_39;
            }
            else
            {
              v7 = (HKEY)v34[0];
            }
            if ( ((*a2 - 76) & 0xFFDF) == 0 )
              v20 = lstrcmpiW(a2, L"LocalServer32") == 0;
            Token = ATL::CRegParser::NextToken(this, a2);
            if ( Token < 0 )
              break;
            if ( *a2 == 61 )
            {
              Token = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)v34, 0, a2, v20);
              if ( Token < 0 )
                break;
            }
            goto LABEL_46;
          }
          v23 = v35;
          if ( !v10 )
          {
            v10 = ATL::CRegKey::Open((ATL::CRegKey *)v34, v35, a2, 0x20019u, dwOptions) != 0;
            v7 = (HKEY)v34[0];
          }
          if ( !v9 )
          {
            if ( ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)0x208, v18) )
            {
              v24 = alloca(528);
              v9 = &v30;
            }
            else
            {
              v9 = (int *)ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(
                            &v40,
                            520);
            }
            if ( !v9 )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)v34);
              Token = -2147024882;
              goto LABEL_32;
            }
          }
          lstrcpynW((LPWSTR)v9, a2, 260);
          if ( v10 || ATL::CRegParser::HasSubKeys(v25, v7) || ATL::CRegParser::HasValues(v26, v7) )
          {
            Token = ATL::CRegParser::NextToken(this, a2);
            if ( Token < 0 )
              break;
            Token = ATL::CRegParser::SkipAssignment(this, a2);
            if ( Token < 0 )
              break;
            if ( *a2 == 123 )
            {
              Token = ATL::CRegParser::RegisterSubkeys(this, a2, v7, 0, v10);
              if ( Token < 0 )
                break;
              if ( !v10 )
              {
LABEL_72:
                if ( ATL::CRegParser::HasSubKeys(v27, v7) )
                {
                  if ( ATL::CRegParser::CanForceRemoveKey(v28, (const wchar_t *)v9) )
                  {
                    ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v34, (const wchar_t *)v9);
                    v7 = (HKEY)v34[0];
                  }
LABEL_52:
                  v16 = ATL::CRegParser::NextToken(this, a2);
                  goto LABEL_30;
                }
                goto LABEL_75;
              }
              Token = ATL::CRegParser::NextToken(this, a2);
              if ( Token < 0 )
                break;
              Token = ATL::CRegParser::SkipAssignment(this, a2);
              if ( Token < 0 )
                break;
              v10 = v38;
            }
            else if ( !v10 )
            {
              goto LABEL_72;
            }
          }
          else
          {
LABEL_75:
            if ( (unsigned int)ATL::CRegKey::Close((ATL::CRegKey *)v34) )
              goto LABEL_39;
            if ( v36 )
            {
              v32 = 0;
              v33 = 0;
              hKey = v23;
              ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, (const wchar_t *)v9);
              hKey = 0;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
            Token = ATL::CRegParser::NextToken(this, a2);
            if ( Token < 0 )
              break;
            Token = ATL::CRegParser::SkipAssignment(this, a2);
            if ( Token < 0 )
              break;
            v7 = (HKEY)v34[0];
          }
        }
        else
        {
          Token = ATL::CRegParser::NextToken(this, ValueName);
          if ( Token < 0 )
            break;
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            break;
          if ( *a2 != 61 )
          {
LABEL_39:
            ATL::CRegKey::Close((ATL::CRegKey *)v34);
LABEL_84:
            Token = -2147352567;
            goto LABEL_32;
          }
          v13 = v30;
          if ( v30 )
          {
            v32 = 0;
            v33 = 0;
            hKey = v35;
            Token = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)&hKey, ValueName, a2, 0);
            hKey = 0;
            if ( Token < 0 )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
              ATL::CRegKey::Close((ATL::CRegKey *)v34);
              goto LABEL_32;
            }
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            goto LABEL_47;
          }
          if ( !v10 )
          {
            hKey = 0;
            v32 = 0;
            v33 = 0;
            v14 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, v35, 0, 0x20006u, dwOptions);
            Token = v14;
            if ( v14 )
            {
              if ( v14 > 0 )
                Token = (unsigned __int16)v14 | 0x80070000;
              goto LABEL_91;
            }
            v15 = RegDeleteValueW(hKey, ValueName);
            Token = v15;
            if ( (v15 & 0xFFFFFFFD) != 0 )
            {
              if ( v15 > 0 )
                Token = (unsigned __int16)v15 | 0x80070000;
LABEL_91:
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
              break;
            }
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
          v16 = ATL::CRegParser::SkipAssignment(this, a2);
LABEL_30:
          Token = v16;
          if ( v16 < 0 )
            break;
        }
      }
      else
      {
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_91;
        Token = ATL::CRegParser::SkipAssignment(this, a2);
        if ( Token < 0 )
          goto LABEL_91;
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_46:
        v13 = v30;
LABEL_47:
        if ( *a2 == 123 )
        {
          v22 = -1;
          do
            ++v22;
          while ( a2[v22] );
          if ( v22 == 1 )
          {
            Token = ATL::CRegParser::RegisterSubkeys(this, a2, v7, v13, 0);
            if ( Token < 0 )
              break;
            goto LABEL_52;
          }
        }
      }
    }
  }
  ATL::CRegKey::Close((ATL::CRegKey *)v34);
LABEL_32:
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v40);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x180011504  push    rbp
0x180011506  push    rbx
0x180011507  push    rsi
0x180011508  push    rdi
0x180011509  push    r12
0x18001150b  push    r13
0x18001150d  push    r14
0x18001150f  push    r15
0x180011511  sub     rsp, 2D8h
0x180011518  lea     rbp, [rsp+50h]
0x18001151d  mov     rax, cs:__security_cookie
0x180011524  xor     rax, rbp
0x180011527  mov     [rbp+2C0h+var_50], rax
0x18001152e  mov     [rbp+2C0h+var_2C0], r9d
0x180011532  mov     [rbp+2C0h+var_288], r8
0x180011536  mov     rdi, rdx
0x180011539  mov     rsi, rcx
0x18001153c  xor     r14d, r14d
0x18001153f  mov     [rbp+2C0h+var_268], r14
0x180011543  mov     r15d, r14d
0x180011546  mov     [rbp+2C0h+var_2A0], r14
0x18001154a  mov     [rbp+2C0h+var_298], r14
0x18001154e  mov     [rbp+2C0h+var_290], r14
0x180011552  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180011557  mov     ebx, eax
0x180011559  test    eax, eax
0x18001155b  jns     short loc_18001156C
0x18001155d  lea     rcx, [rbp+2C0h+var_2A0]; this
0x180011561  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180011566  nop
0x180011567  jmp     loc_1800117AE
0x18001156c  mov     r13, r14
0x18001156f  mov     [rbp+2C0h+var_280], 1
0x180011576  mov     r12d, [rbp+2C0h+arg_20]
0x18001157d  mov     [rbp+2C0h+var_278], r12d
0x180011581  cmp     word ptr [rdi], 7Dh ; '}'
0x180011585  jz      loc_1800117A4
0x18001158b  lea     rdx, aDelete; "Delete"
0x180011592  mov     rcx, rdi; lpString1
0x180011595  call    cs:__imp_lstrcmpiW
0x18001159b  mov     r14d, eax
0x18001159e  lea     rdx, aForceremove; "ForceRemove"
0x1800115a5  mov     rcx, rdi; lpString1
0x1800115a8  call    cs:__imp_lstrcmpiW
0x1800115ae  xor     ebx, ebx
0x1800115b0  test    eax, eax
0x1800115b2  jz      short loc_1800115BD
0x1800115b4  test    r14d, r14d
0x1800115b7  jnz     loc_18001166B
0x1800115bd  mov     rdx, rdi; wchar_t *
0x1800115c0  mov     rcx, rsi; this
0x1800115c3  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800115c8  mov     ebx, eax
0x1800115ca  test    eax, eax
0x1800115cc  js      loc_1800117A4
0x1800115d2  xor     ebx, ebx
0x1800115d4  cmp     [rbp+2C0h+var_2C0], ebx
0x1800115d7  jz      loc_18001166B
0x1800115dd  mov     [rbp+2C0h+hKey], rbx
0x1800115e1  mov     [rbp+2C0h+var_2B0], rbx
0x1800115e5  mov     [rbp+2C0h+var_2A8], rbx
0x1800115e9  lea     edx, [rbx+5Ch]; wchar_t
0x1800115ec  mov     rcx, rdi; lpsz
0x1800115ef  call    ?StrChrW@CRegParser@ATL@@KAPEB_WPEB_W_W@Z; ATL::CRegParser::StrChrW(wchar_t const *,wchar_t)
0x1800115f4  test    rax, rax
0x1800115f7  jnz     loc_180011B60
0x1800115fd  mov     rdx, rdi; wchar_t *
0x180011600  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEB_W@Z; ATL::CRegParser::CanForceRemoveKey(wchar_t const *)
0x180011605  test    eax, eax
0x180011607  jz      short loc_180011621
0x180011609  mov     rax, [rbp+2C0h+var_288]
0x18001160d  mov     [rbp+2C0h+hKey], rax
0x180011611  mov     rdx, rdi; wchar_t *
0x180011614  lea     rcx, [rbp+2C0h+hKey]; this
0x180011618  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x18001161d  mov     [rbp+2C0h+hKey], rbx
0x180011621  test    r14d, r14d
0x180011624  jnz     short loc_180011661
0x180011626  mov     rdx, rdi; wchar_t *
0x180011629  mov     rcx, rsi; this
0x18001162c  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180011631  mov     ebx, eax
0x180011633  test    eax, eax
0x180011635  js      loc_180011B51
0x18001163b  mov     rdx, rdi; wchar_t *
0x18001163e  mov     rcx, rsi; this
0x180011641  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x180011646  mov     ebx, eax
0x180011648  test    eax, eax
0x18001164a  js      loc_180011B42
0x180011650  lea     rcx, [rbp+2C0h+hKey]; this
0x180011654  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180011659  nop
0x18001165a  xor     ecx, ecx
0x18001165c  jmp     loc_18001190E
0x180011661  lea     rcx, [rbp+2C0h+hKey]; this
0x180011665  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001166a  nop
0x18001166b  lea     rdx, aNoremove; "NoRemove"
0x180011672  mov     rcx, rdi; lpString1
0x180011675  call    cs:__imp_lstrcmpiW
0x18001167b  test    eax, eax
0x18001167d  jnz     short loc_180011699
0x18001167f  mov     [rbp+2C0h+var_280], ebx
0x180011682  mov     rdx, rdi; wchar_t *
0x180011685  mov     rcx, rsi; this
0x180011688  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18001168d  mov     ebx, eax
0x18001168f  test    eax, eax
0x180011691  js      loc_1800117A4
0x180011697  xor     ebx, ebx
0x180011699  lea     rdx, aVal; "Val"
0x1800116a0  mov     rcx, rdi; lpString1
0x1800116a3  call    cs:__imp_lstrcmpiW
0x1800116a9  test    eax, eax
0x1800116ab  jnz     loc_1800117DC
0x1800116b1  lea     rdx, [rbp+2C0h+ValueName]; wchar_t *
0x1800116b5  mov     rcx, rsi; this
0x1800116b8  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800116bd  mov     ebx, eax
0x1800116bf  test    eax, eax
0x1800116c1  js      loc_1800117A4
0x1800116c7  mov     rdx, rdi; wchar_t *
0x1800116ca  mov     rcx, rsi; this
0x1800116cd  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800116d2  mov     ebx, eax
0x1800116d4  xor     ecx, ecx
0x1800116d6  test    eax, eax
0x1800116d8  js      loc_1800117A4
0x1800116de  cmp     word ptr [rdi], 3Dh ; '='
0x1800116e2  jnz     loc_180011BCD
0x1800116e8  mov     r14d, [rbp+2C0h+var_2C0]
0x1800116ec  test    r14d, r14d
0x1800116ef  jz      short loc_180011739
0x1800116f1  mov     [rbp+2C0h+var_2B0], rcx
0x1800116f5  mov     [rbp+2C0h+var_2A8], rcx
0x1800116f9  mov     rax, [rbp+2C0h+var_288]
0x1800116fd  mov     [rbp+2C0h+hKey], rax
0x180011701  mov     byte ptr [rsp+310h+dwOptions], cl; bool
0x180011705  mov     r9, rdi; wchar_t *
0x180011708  lea     r8, [rbp+2C0h+ValueName]; wchar_t *
0x18001170c  lea     rdx, [rbp+2C0h+hKey]; struct ATL::CRegKey *
0x180011710  mov     rcx, rsi; this
0x180011713  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *,bool)
0x180011718  mov     ebx, eax
0x18001171a  xor     eax, eax
0x18001171c  mov     [rbp+2C0h+hKey], rax
0x180011720  test    ebx, ebx
0x180011722  js      loc_180011B7E
0x180011728  lea     rcx, [rbp+2C0h+hKey]; this
0x18001172c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180011731  nop
0x180011732  xor     ecx, ecx
0x180011734  jmp     loc_180011912
0x180011739  test    r12d, r12d
0x18001173c  jnz     short loc_18001178F
0x18001173e  mov     [rbp+2C0h+hKey], rcx
0x180011742  mov     [rbp+2C0h+var_2B0], rcx
0x180011746  mov     [rbp+2C0h+var_2A8], rcx
0x18001174a  mov     r9d, 20006h; unsigned int
0x180011750  xor     r8d, r8d; lpSubKey
0x180011753  mov     rdx, [rbp+2C0h+var_288]; hKey
0x180011757  lea     rcx, [rbp+2C0h+hKey]; this
0x18001175b  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WKK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong,ulong)
0x180011760  mov     ebx, eax
0x180011762  test    eax, eax
0x180011764  jnz     loc_180011BB3
0x18001176a  lea     rdx, [rbp+2C0h+ValueName]; lpValueName
0x18001176e  mov     rcx, [rbp+2C0h+hKey]; hKey
0x180011772  call    cs:__imp_RegDeleteValueW
0x180011778  mov     ebx, eax
0x18001177a  test    eax, 0FFFFFFFDh
0x18001177f  jnz     loc_180011B97
0x180011785  lea     rcx, [rbp+2C0h+hKey]; this
0x180011789  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001178e  nop
0x18001178f  mov     rdx, rdi; wchar_t *
0x180011792  mov     rcx, rsi; this
0x180011795  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::SkipAssignment(wchar_t *)
0x18001179a  mov     ebx, eax
0x18001179c  test    eax, eax
0x18001179e  jns     loc_180011581
0x1800117a4  lea     rcx, [rbp+2C0h+var_2A0]; this
0x1800117a8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800117ad  nop
0x1800117ae  lea     rcx, [rbp+2C0h+var_268]
0x1800117b2  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x1800117b7  mov     eax, ebx
0x1800117b9  mov     rcx, [rbp+2C0h+var_50]
0x1800117c0  xor     rcx, rbp; StackCookie
0x1800117c3  call    __security_check_cookie
0x1800117c8  lea     rsp, [rbp+288h]
0x1800117cf  pop     r15
0x1800117d1  pop     r14
0x1800117d3  pop     r13
0x1800117d5  pop     r12
0x1800117d7  pop     rdi
0x1800117d8  pop     rsi
0x1800117d9  pop     rbx
0x1800117da  pop     rbp
0x1800117db  retn
0x1800117dc  mov     edx, 5Ch ; '\'; wchar_t
0x1800117e1  mov     rcx, rdi; lpsz
0x1800117e4  call    ?StrChrW@CRegParser@ATL@@KAPEB_WPEB_W_W@Z; ATL::CRegParser::StrChrW(wchar_t const *,wchar_t)
0x1800117e9  test    rax, rax
0x1800117ec  jnz     loc_180011BFC
0x1800117f2  cmp     [rbp+2C0h+var_2C0], ebx
0x1800117f5  jz      loc_180011962
0x1800117fb  mov     r9d, 0F003Fh; unsigned int
0x180011801  mov     r8, rdi; lpSubKey
0x180011804  mov     rbx, [rbp+2C0h+var_288]
0x180011808  mov     rdx, rbx; hKey
0x18001180b  lea     rcx, [rbp+2C0h+var_2A0]; this
0x18001180f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WKK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong,ulong)
0x180011814  xor     r14d, r14d
0x180011817  test    eax, eax
0x180011819  jz      short loc_18001189A
0x18001181b  mov     r9d, 20019h; unsigned int
0x180011821  mov     r8, rdi; lpSubKey
0x180011824  mov     rdx, rbx; hKey
0x180011827  lea     rcx, [rbp+2C0h+var_2A0]; this
0x18001182b  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEB_WKK@Z; ATL::CRegKey::Open(HKEY__ *,wchar_t const *,ulong,ulong)
0x180011830  test    eax, eax
0x180011832  jz      short loc_18001189A
0x180011834  mov     [rbp+2C0h+dwDisposition], r14d
0x180011838  mov     [rbp+2C0h+var_270], r14
0x18001183c  lea     rax, [rbp+2C0h+dwDisposition]
0x180011840  mov     [rsp+310h+lpdwDisposition], rax; lpdwDisposition
0x180011845  lea     rax, [rbp+2C0h+var_270]
0x180011849  mov     [rsp+310h+phkResult], rax; phkResult
0x18001184e  mov     [rsp+310h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180011853  mov     [rsp+310h+samDesired], 2001Fh; samDesired
0x18001185b  mov     [rsp+310h+dwOptions], r14d; dwOptions
0x180011860  xor     r9d, r9d; lpClass
0x180011863  xor     r8d, r8d; Reserved
0x180011866  mov     rdx, rdi; lpSubKey
0x180011869  mov     rcx, rbx; hKey
0x18001186c  call    cs:__imp_RegCreateKeyExW
0x180011872  test    eax, eax
0x180011874  jnz     short loc_18001188B
0x180011876  lea     rcx, [rbp+2C0h+var_2A0]; this
0x18001187a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001187f  mov     r15, [rbp+2C0h+var_270]
0x180011883  mov     [rbp+2C0h+var_2A0], r15
0x180011887  test    eax, eax
0x180011889  jz      short loc_18001189E
0x18001188b  lea     rcx, [rbp+2C0h+var_2A0]; this
0x18001188f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180011894  nop
0x180011895  jmp     loc_180011B74
0x18001189a  mov     r15, [rbp+2C0h+var_2A0]
0x18001189e  movzx   eax, word ptr [rdi]
0x1800118a1  sub     ax, 4Ch ; 'L'
0x1800118a5  mov     ecx, 0FFDFh
0x1800118aa  test    cx, ax
0x1800118ad  jnz     short loc_1800118CE
0x1800118af  lea     rdx, aLocalserver32; "LocalServer32"
0x1800118b6  mov     rcx, rdi; lpString1
0x1800118b9  call    cs:__imp_lstrcmpiW
0x1800118bf  movzx   r14d, r14b
0x1800118c3  test    eax, eax
0x1800118c5  mov     eax, 1
0x1800118ca  cmovz   r14d, eax
0x1800118ce  mov     rdx, rdi; wchar_t *
0x1800118d1  mov     rcx, rsi; this
0x1800118d4  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x1800118d9  mov     ebx, eax
0x1800118db  xor     ecx, ecx
0x1800118dd  test    eax, eax
0x1800118df  js      loc_1800117A4
0x1800118e5  cmp     word ptr [rdi], 3Dh ; '='
0x1800118e9  jnz     short loc_18001190E
0x1800118eb  mov     byte ptr [rsp+310h+dwOptions], r14b; bool
0x1800118f0  mov     r9, rdi; wchar_t *
0x1800118f3  xor     r8d, r8d; wchar_t *
0x1800118f6  lea     rdx, [rbp+2C0h+var_2A0]; struct ATL::CRegKey *
0x1800118fa  mov     rcx, rsi; this
0x1800118fd  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W_N@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *,bool)
0x180011902  mov     ebx, eax
0x180011904  xor     ecx, ecx
0x180011906  test    eax, eax
0x180011908  js      loc_1800117A4
0x18001190e  mov     r14d, [rbp+2C0h+var_2C0]
0x180011912  cmp     word ptr [rdi], 7Bh ; '{'
0x180011916  jnz     loc_180011581
0x18001191c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011920  inc     rax
0x180011923  cmp     [rdi+rax*2], cx
0x180011927  jnz     short loc_180011920
0x180011929  cmp     rax, 1
0x18001192d  jnz     loc_180011581
0x180011933  mov     [rsp+310h+dwOptions], ecx; unsigned int
0x180011937  mov     r9d, r14d; int
0x18001193a  mov     r8, r15; HKEY
0x18001193d  mov     rdx, rdi; wchar_t *
0x180011940  mov     rcx, rsi; this
0x180011943  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEA_WPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(wchar_t *,HKEY__ *,int,int)
0x180011948  mov     ebx, eax
0x18001194a  test    eax, eax
0x18001194c  js      loc_1800117A4
  ... truncated ...
```
