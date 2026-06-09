# OneCore::Base::Telemetry::OneSettingsQuery::HaveQueryParametersChanged(bool &)

- ea: `0x180004358`
- end: `0x1800046ef`
- name: `?HaveQueryParametersChanged@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJAEA_N@Z`
- size: `919`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180007504`

## callees

- `0x1800042ac`
- `0x180004358`
- `0x180007b54`
- `0x1800191ba`
- `0x1800191f0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800046b0`
- `ADVAPI32!RegCloseKey` at `0x1800046b0`
- `ADVAPI32!RegEnumValueW` at `0x18000455f`
- `ADVAPI32!RegEnumValueW` at `0x18000455f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000448c`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000448c`
- `ADVAPI32!RegOpenKeyExW` at `0x180004417`
- `ADVAPI32!RegOpenKeyExW` at `0x180004417`
- `KERNEL32!HeapAlloc` at `0x1800044ce`
- `KERNEL32!HeapAlloc` at `0x1800044fa`
- `KERNEL32!HeapAlloc` at `0x1800044ce`
- `KERNEL32!HeapAlloc` at `0x1800044fa`
- `KERNEL32!GetProcessHeap` at `0x1800044b9`
- `KERNEL32!GetProcessHeap` at `0x1800044ea`
- `KERNEL32!GetProcessHeap` at `0x18000467a`
- `KERNEL32!GetProcessHeap` at `0x180004693`
- `KERNEL32!GetProcessHeap` at `0x1800044b9`
- `KERNEL32!GetProcessHeap` at `0x1800044ea`
- `KERNEL32!GetProcessHeap` at `0x18000467a`
- `KERNEL32!GetProcessHeap` at `0x180004693`
- `KERNEL32!HeapFree` at `0x180004688`
- `KERNEL32!HeapFree` at `0x1800046a1`
- `KERNEL32!HeapFree` at `0x180004688`
- `KERNEL32!HeapFree` at `0x1800046a1`

## pseudocode

```c
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::HaveQueryParametersChanged(
        OneCore::Base::Telemetry::OneSettingsQuery *this,
        bool *a2)
{
  char v2; // r12
  signed int v5; // ebx
  LSTATUS v6; // eax
  bool v7; // cc
  SIZE_T v8; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v10; // rsi
  __int64 v11; // rbx
  HANDLE v12; // rax
  BYTE *v13; // r14
  DWORD v14; // r13d
  LSTATUS v15; // eax
  const unsigned __int16 *Value; // rax
  BYTE *v17; // rcx
  signed __int64 v18; // rax
  int v19; // r8d
  int v20; // edx
  const unsigned __int16 *v21; // rax
  BYTE *v22; // rcx
  signed __int64 v23; // rax
  int v24; // r8d
  int v25; // edx
  const wchar_t *v26; // rax
  bool v27; // al
  HANDLE v28; // rax
  HANDLE v29; // rax
  char v31; // [rsp+60h] [rbp-A0h]
  DWORD cValues; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxValueLen; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchValueName; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD Type; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF

  v2 = 0;
  cValues = 0;
  cchValueName = 0;
  cbData = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  Type = 0;
  hKey = 0;
  v5 = StringCchPrintfW(
         SubKey,
         0x104u,
         L"%ls\\%ls\\%ls\\%ls",
         (char *)this + 1080,
         (char *)this + 40,
         (char *)this + 560,
         L"QueryParameters");
  if ( v5 < 0 )
    goto LABEL_43;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v5 = v6;
  if ( v6 )
  {
    if ( v6 == 2 )
    {
LABEL_4:
      *a2 = 1;
      v5 = 0;
      goto LABEL_43;
    }
    v7 = v6 <= 0;
    goto LABEL_6;
  }
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  v5 = v6;
  v7 = v6 <= 0;
  if ( v6 )
  {
LABEL_6:
    if ( !v7 )
      v5 = (unsigned __int16)v6 | 0x80070000;
    goto LABEL_43;
  }
  if ( *((_DWORD *)this + 418) + *((_DWORD *)this + 430) != cValues )
    goto LABEL_4;
  v8 = 2LL * (cbMaxValueNameLen + 1);
  ProcessHeap = GetProcessHeap();
  v10 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v8);
  if ( v10 )
  {
    v11 = cbMaxValueLen;
    v12 = GetProcessHeap();
    v13 = (BYTE *)HeapAlloc(v12, 8u, v11 + 2);
    if ( v13 )
    {
      v14 = 0;
      if ( cValues )
      {
        while ( 1 )
        {
          cchValueName = cbMaxValueNameLen + 1;
          cbData = cbMaxValueLen;
          v15 = RegEnumValueW(hKey, v14, v10, &cchValueName, 0, &Type, v13, &cbData);
          v5 = v15;
          if ( v15 )
            break;
          *(_WORD *)&v13[2 * ((unsigned __int64)cbData >> 1)] = 0;
          if ( Type != 1 )
            goto LABEL_36;
          if ( !RtlNameValueArray::GetValue((OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1656), v10) )
            goto LABEL_22;
          Value = RtlNameValueArray::GetValue((OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1656), v10);
          v17 = v13;
          v18 = (char *)Value - (char *)v13;
          do
          {
            v19 = *(unsigned __int16 *)&v17[v18];
            v20 = *(unsigned __int16 *)v17 - v19;
            if ( v20 )
              break;
            v17 += 2;
          }
          while ( v19 );
          v31 = 1;
          if ( v20 )
LABEL_22:
            v31 = 0;
          if ( RtlNameValueArray::GetValue((OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1704), v10) )
          {
            v21 = RtlNameValueArray::GetValue((OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1704), v10);
            v22 = v13;
            v23 = (char *)v21 - (char *)v13;
            do
            {
              v24 = *(unsigned __int16 *)&v22[v23];
              v25 = *(unsigned __int16 *)v22 - v24;
              if ( v25 )
                break;
              v22 += 2;
            }
            while ( v24 );
            if ( !v25 )
              v2 = 1;
          }
          v27 = 0;
          if ( RtlNameValueArray::GetValue((OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1704), v10) )
          {
            v26 = RtlNameValueArray::GetValue((OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1704), v10);
            if ( !wcscmp_0(L"FALSE", v26) )
              v27 = 1;
          }
          if ( v31 || v2 )
          {
            v2 = 0;
          }
          else
          {
            v2 = 0;
            if ( !v27 )
            {
LABEL_36:
              *a2 = 1;
              goto LABEL_40;
            }
          }
          if ( ++v14 >= cValues )
            goto LABEL_39;
        }
        if ( v15 > 0 )
          v5 = (unsigned __int16)v15 | 0x80070000;
      }
      else
      {
LABEL_39:
        *a2 = 0;
LABEL_40:
        v5 = 0;
      }
    }
    else
    {
      v5 = -2147024882;
    }
    v28 = GetProcessHeap();
    HeapFree(v28, 0, v10);
    if ( v13 )
    {
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v13);
    }
  }
  else
  {
    v5 = -2147024882;
  }
LABEL_43:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180004358  mov     [rsp-8+arg_10], rbx
0x18000435d  push    rbp
0x18000435e  push    rsi
0x18000435f  push    rdi
0x180004360  push    r12
0x180004362  push    r13
0x180004364  push    r14
0x180004366  push    r15
0x180004368  lea     rbp, [rsp-1B0h]
0x180004370  sub     rsp, 2B0h
0x180004377  mov     rax, cs:__security_cookie
0x18000437e  xor     rax, rsp
0x180004381  mov     [rbp+1E0h+var_40], rax
0x180004388  xor     r12d, r12d
0x18000438b  lea     rax, [rcx+230h]
0x180004392  mov     r15, rcx
0x180004395  mov     [rsp+2E0h+cValues], r12d
0x18000439a  mov     rdi, rdx
0x18000439d  mov     [rsp+2E0h+cchValueName], r12d
0x1800043a2  add     rcx, 28h ; '('
0x1800043a6  mov     [rsp+2E0h+cbData], r12d
0x1800043ab  lea     rdx, aQueryparameter; "QueryParameters"
0x1800043b2  mov     [rsp+2E0h+cbMaxValueNameLen], r12d
0x1800043b7  mov     [rsp+2E0h+lpcbMaxClassLen], rdx
0x1800043bc  lea     r9, [r15+438h]
0x1800043c3  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rax
0x1800043c8  lea     r8, aLsLsLsLs; "%ls\\%ls\\%ls\\%ls"
0x1800043cf  mov     [rsp+2E0h+phkResult], rcx
0x1800043d4  mov     edx, 104h; unsigned __int64
0x1800043d9  lea     rcx, [rbp+1E0h+SubKey]; unsigned __int16 *
0x1800043dd  mov     [rsp+2E0h+cbMaxValueLen], r12d
0x1800043e2  mov     [rsp+2E0h+Type], r12d
0x1800043e7  mov     [rbp+1E0h+hKey], r12
0x1800043eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800043f0  mov     ebx, eax
0x1800043f2  test    eax, eax
0x1800043f4  js      loc_1800046A7
0x1800043fa  lea     rax, [rbp+1E0h+hKey]
0x1800043fe  mov     r9d, 20019h; samDesired
0x180004404  xor     r8d, r8d; ulOptions
0x180004407  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18000440c  lea     rdx, [rbp+1E0h+SubKey]; lpSubKey
0x180004410  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004417  call    cs:__imp_RegOpenKeyExW
0x18000441d  mov     ebx, eax
0x18000441f  test    eax, eax
0x180004421  jz      short loc_180004449
0x180004423  cmp     eax, 2
0x180004426  jnz     short loc_180004433
0x180004428  mov     byte ptr [rdi], 1
0x18000442b  mov     ebx, r12d
0x18000442e  jmp     loc_1800046A7
0x180004433  test    eax, eax
0x180004435  jle     loc_1800046A7
0x18000443b  movzx   ebx, ax
0x18000443e  or      ebx, 80070000h
0x180004444  jmp     loc_1800046A7
0x180004449  mov     rcx, [rbp+1E0h+hKey]; hKey
0x18000444d  lea     rax, [rsp+2E0h+cbMaxValueLen]
0x180004452  mov     [rsp+2E0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180004457  xor     r9d, r9d; lpReserved
0x18000445a  mov     [rsp+2E0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18000445f  xor     r8d, r8d; lpcchClass
0x180004462  mov     [rsp+2E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180004467  xor     edx, edx; lpClass
0x180004469  lea     rax, [rsp+2E0h+cbMaxValueNameLen]
0x18000446e  mov     [rsp+2E0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180004473  lea     rax, [rsp+2E0h+cValues]
0x180004478  mov     [rsp+2E0h+lpcValues], rax; lpcValues
0x18000447d  mov     [rsp+2E0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180004482  mov     [rsp+2E0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180004487  mov     [rsp+2E0h+phkResult], r12; lpcSubKeys
0x18000448c  call    cs:__imp_RegQueryInfoKeyW
0x180004492  mov     ebx, eax
0x180004494  test    eax, eax
0x180004496  jnz     short loc_180004435
0x180004498  mov     eax, [r15+6B8h]
0x18000449f  add     eax, [r15+688h]
0x1800044a6  cmp     eax, [rsp+2E0h+cValues]
0x1800044aa  jnz     loc_180004428
0x1800044b0  mov     ebx, [rsp+2E0h+cbMaxValueNameLen]
0x1800044b4  inc     ebx
0x1800044b6  add     rbx, rbx
0x1800044b9  call    cs:__imp_GetProcessHeap
0x1800044bf  mov     r14d, 8
0x1800044c5  mov     r8, rbx; dwBytes
0x1800044c8  mov     edx, r14d; dwFlags
0x1800044cb  mov     rcx, rax; hHeap
0x1800044ce  call    cs:__imp_HeapAlloc
0x1800044d4  mov     rsi, rax
0x1800044d7  test    rax, rax
0x1800044da  jnz     short loc_1800044E6
0x1800044dc  mov     ebx, 8007000Eh
0x1800044e1  jmp     loc_1800046A7
0x1800044e6  mov     ebx, [rsp+2E0h+cbMaxValueLen]
0x1800044ea  call    cs:__imp_GetProcessHeap
0x1800044f0  lea     r8, [rbx+2]; dwBytes
0x1800044f4  mov     edx, r14d; dwFlags
0x1800044f7  mov     rcx, rax; hHeap
0x1800044fa  call    cs:__imp_HeapAlloc
0x180004500  mov     r14, rax
0x180004503  test    rax, rax
0x180004506  jnz     short loc_180004512
0x180004508  mov     ebx, 8007000Eh
0x18000450d  jmp     loc_18000467A
0x180004512  mov     r13d, r12d
0x180004515  cmp     [rsp+2E0h+cValues], r12d
0x18000451a  jbe     loc_180004674
0x180004520  mov     eax, [rsp+2E0h+cbMaxValueNameLen]
0x180004524  lea     r9, [rsp+2E0h+cchValueName]; lpcchValueName
0x180004529  mov     rcx, [rbp+1E0h+hKey]; hKey
0x18000452d  inc     eax
0x18000452f  mov     [rsp+2E0h+cchValueName], eax
0x180004533  mov     r8, rsi; lpValueName
0x180004536  mov     eax, [rsp+2E0h+cbMaxValueLen]
0x18000453a  mov     edx, r13d; dwIndex
0x18000453d  mov     [rsp+2E0h+cbData], eax
0x180004541  lea     rax, [rsp+2E0h+cbData]
0x180004546  mov     [rsp+2E0h+lpcValues], rax; lpcbData
0x18000454b  lea     rax, [rsp+2E0h+Type]
0x180004550  mov     [rsp+2E0h+lpcbMaxClassLen], r14; lpData
0x180004555  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rax; lpType
0x18000455a  mov     [rsp+2E0h+phkResult], r12; lpReserved
0x18000455f  call    cs:__imp_RegEnumValueW
0x180004565  mov     ebx, eax
0x180004567  test    eax, eax
0x180004569  jnz     loc_1800046E2
0x18000456f  mov     ecx, [rsp+2E0h+cbData]
0x180004573  shr     rcx, 1
0x180004576  mov     [r14+rcx*2], r12w
0x18000457b  cmp     [rsp+2E0h+Type], 1
0x180004580  jnz     loc_18000465E
0x180004586  lea     rbx, [r15+678h]
0x18000458d  mov     rdx, rsi; unsigned __int16 *
0x180004590  mov     rcx, rbx; this
0x180004593  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG@Z; RtlNameValueArray::GetValue(ushort const *)
0x180004598  test    rax, rax
0x18000459b  jz      short loc_1800045CD
0x18000459d  mov     rdx, rsi; unsigned __int16 *
0x1800045a0  mov     rcx, rbx; this
0x1800045a3  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG@Z; RtlNameValueArray::GetValue(ushort const *)
0x1800045a8  mov     rcx, r14
0x1800045ab  sub     rax, r14
0x1800045ae  movzx   edx, word ptr [rcx]
0x1800045b1  movzx   r8d, word ptr [rcx+rax]
0x1800045b6  sub     edx, r8d
0x1800045b9  jnz     short loc_1800045C4
0x1800045bb  add     rcx, 2
0x1800045bf  test    r8d, r8d
0x1800045c2  jnz     short loc_1800045AE
0x1800045c4  mov     [rsp+2E0h+var_280], 1
0x1800045c9  test    edx, edx
0x1800045cb  jz      short loc_1800045D2
0x1800045cd  mov     [rsp+2E0h+var_280], r12b
0x1800045d2  lea     rbx, [r15+6A8h]
0x1800045d9  mov     rdx, rsi; unsigned __int16 *
0x1800045dc  mov     rcx, rbx; this
0x1800045df  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG@Z; RtlNameValueArray::GetValue(ushort const *)
0x1800045e4  test    rax, rax
0x1800045e7  jz      short loc_180004617
0x1800045e9  mov     rdx, rsi; unsigned __int16 *
0x1800045ec  mov     rcx, rbx; this
0x1800045ef  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG@Z; RtlNameValueArray::GetValue(ushort const *)
0x1800045f4  mov     rcx, r14
0x1800045f7  sub     rax, r14
0x1800045fa  movzx   edx, word ptr [rcx]
0x1800045fd  movzx   r8d, word ptr [rcx+rax]
0x180004602  sub     edx, r8d
0x180004605  jnz     short loc_180004610
0x180004607  add     rcx, 2
0x18000460b  test    r8d, r8d
0x18000460e  jnz     short loc_1800045FA
0x180004610  test    edx, edx
0x180004612  jnz     short loc_180004617
0x180004614  mov     r12b, 1
0x180004617  mov     rdx, rsi; unsigned __int16 *
0x18000461a  mov     rcx, rbx; this
0x18000461d  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG@Z; RtlNameValueArray::GetValue(ushort const *)
0x180004622  test    rax, rax
0x180004625  jz      short loc_180004649
0x180004627  mov     rdx, rsi; unsigned __int16 *
0x18000462a  mov     rcx, rbx; this
0x18000462d  call    ?GetValue@RtlNameValueArray@@QEBAPEBGPEBG@Z; RtlNameValueArray::GetValue(ushort const *)
0x180004632  mov     rdx, rax; String2
0x180004635  lea     rcx, aFalse_0; "FALSE"
0x18000463c  call    wcscmp_0
0x180004641  test    eax, eax
0x180004643  jnz     short loc_180004649
0x180004645  mov     al, 1
0x180004647  jmp     short loc_18000464B
0x180004649  xor     al, al
0x18000464b  cmp     [rsp+2E0h+var_280], 0
0x180004650  jnz     short loc_180004663
0x180004652  test    r12b, r12b
0x180004655  jnz     short loc_180004663
0x180004657  xor     r12d, r12d
0x18000465a  test    al, al
0x18000465c  jnz     short loc_180004666
0x18000465e  mov     byte ptr [rdi], 1
0x180004661  jmp     short loc_180004677
0x180004663  xor     r12d, r12d
0x180004666  inc     r13d
0x180004669  cmp     r13d, [rsp+2E0h+cValues]
0x18000466e  jb      loc_180004520
0x180004674  mov     [rdi], r12b
0x180004677  mov     ebx, r12d
0x18000467a  call    cs:__imp_GetProcessHeap
0x180004680  mov     r8, rsi; lpMem
0x180004683  xor     edx, edx; dwFlags
0x180004685  mov     rcx, rax; hHeap
0x180004688  call    cs:__imp_HeapFree
0x18000468e  test    r14, r14
0x180004691  jz      short loc_1800046A7
0x180004693  call    cs:__imp_GetProcessHeap
0x180004699  mov     r8, r14; lpMem
0x18000469c  xor     edx, edx; dwFlags
0x18000469e  mov     rcx, rax; hHeap
0x1800046a1  call    cs:__imp_HeapFree
0x1800046a7  mov     rcx, [rbp+1E0h+hKey]; hKey
0x1800046ab  test    rcx, rcx
0x1800046ae  jz      short loc_1800046B6
0x1800046b0  call    cs:__imp_RegCloseKey
0x1800046b6  mov     eax, ebx
0x1800046b8  mov     rcx, [rbp+1E0h+var_40]
0x1800046bf  xor     rcx, rsp; StackCookie
0x1800046c2  call    __security_check_cookie
0x1800046c7  mov     rbx, [rsp+2E0h+arg_10]
0x1800046cf  add     rsp, 2B0h
0x1800046d6  pop     r15
0x1800046d8  pop     r14
0x1800046da  pop     r13
0x1800046dc  pop     r12
0x1800046de  pop     rdi
0x1800046df  pop     rsi
0x1800046e0  pop     rbp
0x1800046e1  retn
0x1800046e2  jle     short loc_18000467A
0x1800046e4  movzx   ebx, ax
0x1800046e7  or      ebx, 80070000h
0x1800046ed  jmp     short loc_18000467A
```
