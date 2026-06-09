# CRegNode::MoveToDescendantOr(ulong,ushort const *,ushort const *)

- ea: `0x1800540b4`
- end: `0x180054500`
- name: `?MoveToDescendantOr@CRegNode@@AEAAJKPEBG0@Z`
- size: `1100`
- prototype: `int(CRegNode *__hidden this, unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180053dec`
- `0x180053f40`
- `0x180054510`
- `0x180054530`
- `0x180054550`
- `0x180054570`
- `0x1800546e0`

## callees

- `0x180009ee0`
- `0x18001ec1c`
- `0x180053288`
- `0x180053888`
- `0x180053eb0`
- `0x1800540b4`
- `0x1800546f8`
- `0x180054718`
- `0x180054764`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180054202`
- `msvcrt!wcsrchr` at `0x180054202`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180054210`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180054210`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005414a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005438c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005414a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005438c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005435b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005435b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800543be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054428`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005445c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054489`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800544e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800543be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054428`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005445c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054489`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800544e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800541a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800541a4`

## pseudocode

```c
__int64 __fastcall CRegNode::MoveToDescendantOr(
        CRegNode *this,
        int a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  const WCHAR *v4; // rax
  bool v7; // zf
  int v8; // r15d
  unsigned __int16 *v9; // rsi
  LPWSTR v10; // r12
  const WCHAR *v11; // r14
  LSTATUS v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // r14
  unsigned __int16 *v17; // rax
  int v19; // ebx
  wchar_t *v20; // rax
  unsigned int v21; // r8d
  _QWORD *v22; // rbx
  int v23; // eax
  unsigned __int16 *v24; // r9
  HKEY v25; // rcx
  int v26; // eax
  int v27; // eax
  CHkeyCache *v28; // rcx
  void *v29; // rcx
  HKEY *v30; // r14
  unsigned __int16 **v31; // rbx
  void *v32; // rcx
  HKEY v33; // rax
  _QWORD *v34; // rbx
  void *v35; // rcx
  unsigned int lpData; // [rsp+20h] [rbp-50h]
  struct _SECURITY_ATTRIBUTES *v37; // [rsp+30h] [rbp-40h]
  DWORD Type; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v39; // [rsp+54h] [rbp-1Ch] BYREF
  BOOL v40; // [rsp+58h] [rbp-18h]
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  LPCWSTR lpValueName; // [rsp+68h] [rbp-8h]
  DWORD cbData; // [rsp+C0h] [rbp+50h] BYREF
  unsigned __int16 *v45; // [rsp+C8h] [rbp+58h]

  v45 = a4;
  v4 = 0;
  v39 = 2;
  hKey = 0;
  Type = 0;
  cbData = 0;
  v7 = *a4 == 92;
  v8 = 0;
  if ( *a4 != 92 )
    v4 = a4;
  lpValueName = v4;
  v40 = !v7;
  if ( *a3 == 92 )
  {
    v9 = 0;
    v10 = (LPWSTR)*((_QWORD *)this + 5);
    hKey = (HKEY)*((_QWORD *)this + 3);
    goto LABEL_5;
  }
  v13 = *((_QWORD *)this + 4);
  if ( v13 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v13 + 2 * v14) );
  }
  else
  {
    v14 = 0;
  }
  v15 = -1;
  do
    ++v15;
  while ( a3[v15] );
  v16 = v15 + v14 + 2;
  v17 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v16, 2u));
  v9 = v17;
  if ( !v17 )
    return 2147942414LL;
  *v17 = 0;
  if ( *((_QWORD *)this + 4) )
  {
    v19 = StringCchPrintfW(v17, v16, L"%s\\");
    if ( v19 < 0 )
      goto LABEL_83;
  }
  v19 = StringCchCatW(v9, v16, a3);
  if ( v19 < 0 )
    goto LABEL_83;
  v20 = wcsrchr(v9, 0x5Cu);
  if ( v20 )
    v10 = CharNextW(v20);
  else
    v10 = v9;
  v22 = (_QWORD *)*((_QWORD *)this + 9);
  if ( v22 && (v23 = CHkeyCache::Find(*((CHkeyCache **)this + 9), v9), v23 > -1) )
  {
    v25 = *(HKEY *)(*v22 + 16LL * v23 + 8);
    v26 = 0;
    hKey = v25;
    v8 = 1;
  }
  else
  {
    v26 = RegSafeOpenKeyEx(*((HKEY *)this + 3), a3, v21, *((_DWORD *)this + 16), &hKey);
  }
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      if ( v26 == 2 )
      {
        v19 = 1;
        goto LABEL_83;
      }
    }
    else
    {
      if ( a2 != 2 )
      {
        v19 = -2147418113;
LABEL_83:
        CoTaskMemFree(v9);
        return (unsigned int)v19;
      }
      if ( v26 == 2 )
      {
        v27 = RegSafeCreateKeyEx(*((HKEY *)this + 3), a3, v21, v24, lpData, *((_DWORD *)this + 16), v37, &hKey, &v39);
        if ( v27 )
        {
          if ( v27 != 1314 && v27 != 5 )
          {
            v19 = -2146369503;
            goto LABEL_83;
          }
LABEL_41:
          v19 = -2146367453;
          goto LABEL_83;
        }
        goto LABEL_5;
      }
    }
  }
  if ( v26 )
  {
    if ( v26 != 1314 && v26 != 5 )
    {
      v19 = -2146369487;
      goto LABEL_83;
    }
    goto LABEL_41;
  }
LABEL_5:
  v11 = lpValueName;
  cbData = 256;
  v12 = RegQueryValueExW(hKey, lpValueName, 0, &Type, (LPBYTE)this + 88, &cbData);
  if ( !v12 )
  {
    *((_DWORD *)this + 21) = 1;
    goto LABEL_47;
  }
  *((_DWORD *)this + 21) = 0;
  if ( v12 == 234 )
    goto LABEL_46;
  if ( v12 == 2 && !v11 )
  {
    Type = 0;
    cbData = 0;
LABEL_46:
    v12 = 0;
  }
LABEL_47:
  v19 = -2146369497;
  if ( a2 == 1 )
  {
    if ( v12 == 2 )
    {
      v19 = 1;
      goto LABEL_54;
    }
  }
  else if ( a2 == 2 && v12 == 2 )
  {
    if ( RegSetValueExW(hKey, v11, 0, 0, 0, 0) )
    {
      v19 = -2146369496;
LABEL_54:
      if ( *((HKEY *)this + 3) != hKey && !v8 )
      {
        RegSafeCloseKey(hKey);
        if ( !v9 )
          return (unsigned int)v19;
        CoTaskMemFree(v9);
        v9 = 0;
      }
      goto LABEL_82;
    }
    v12 = RegQueryValueExW(hKey, v11, 0, &Type, 0, &cbData);
  }
  if ( v12 )
    goto LABEL_54;
  *((_DWORD *)this + 2) &= 0xFFFFFFFC;
  *((_DWORD *)this + 2) |= v40;
  if ( *a3 != 92 )
  {
    v28 = (CHkeyCache *)*((_QWORD *)this + 9);
    if ( v28 )
    {
      if ( !v8 )
      {
        if ( v9 )
        {
          v19 = CHkeyCache::Append(v28, v9, hKey);
          if ( v19 < 0 )
            goto LABEL_83;
        }
      }
      if ( *((_DWORD *)this + 20) )
      {
        v29 = (void *)*((_QWORD *)this + 4);
        if ( v29 )
        {
          CoTaskMemFree(v29);
          *((_QWORD *)this + 4) = 0;
        }
      }
      *((_DWORD *)this + 20) = v8;
      v30 = (HKEY *)((char *)this + 24);
      v31 = (unsigned __int16 **)((char *)this + 32);
    }
    else
    {
      v30 = (HKEY *)((char *)this + 24);
      RegSafeCloseKey(*((HKEY *)this + 3));
      v31 = (unsigned __int16 **)((char *)this + 32);
      v32 = (void *)*((_QWORD *)this + 4);
      if ( v32 )
      {
        CoTaskMemFree(v32);
        *v31 = 0;
      }
    }
    v33 = hKey;
    *v31 = v9;
    v9 = 0;
    *v30 = v33;
    *((_QWORD *)this + 5) = v10;
  }
  v34 = (_QWORD *)((char *)this + 48);
  v35 = (void *)*((_QWORD *)this + 6);
  if ( v35 )
  {
    CoTaskMemFree(v35);
    *v34 = 0;
  }
  if ( *v45 == 92 )
  {
    *v34 = 0;
  }
  else
  {
    v19 = LocalCopyString(v45, (unsigned __int16 **)this + 6);
    if ( v19 < 0 )
      goto LABEL_82;
  }
  *((_DWORD *)this + 14) = Type;
  *((_DWORD *)this + 15) = cbData;
  if ( a2 == 2 && v39 == 1 )
    v19 = 1114114;
  else
    v19 = 0;
LABEL_82:
  if ( v9 )
    goto LABEL_83;
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1800540b4  mov     [rsp-38h+arg_0], rbx
0x1800540b9  mov     [rsp-38h+arg_18], r9
0x1800540be  mov     [rsp-38h+arg_8], edx
0x1800540c2  push    rbp
0x1800540c3  push    rsi
0x1800540c4  push    rdi
0x1800540c5  push    r12
0x1800540c7  push    r13
0x1800540c9  push    r14
0x1800540cb  push    r15
0x1800540cd  mov     rbp, rsp
0x1800540d0  sub     rsp, 70h
0x1800540d4  xor     ebx, ebx
0x1800540d6  mov     edx, 2
0x1800540db  mov     eax, ebx
0x1800540dd  mov     [rbp+var_1C], edx
0x1800540e0  mov     r13, r8
0x1800540e3  mov     [rbp+hKey], rbx
0x1800540e7  mov     rdi, rcx
0x1800540ea  mov     [rbp+Type], ebx
0x1800540ed  lea     r12d, [rdx+5Ah]
0x1800540f1  mov     [rbp+cbData], ebx
0x1800540f4  cmp     r12w, [r9]
0x1800540f8  mov     r15d, ebx
0x1800540fb  cmovnz  rax, r9
0x1800540ff  mov     [rbp+lpValueName], rax
0x180054103  mov     eax, ebx
0x180054105  setnz   al
0x180054108  mov     [rbp+var_18], eax
0x18005410b  cmp     r12w, [r8]
0x18005410f  jnz     short loc_180054164
0x180054111  mov     rax, [rcx+18h]
0x180054115  mov     esi, ebx
0x180054117  mov     r12, [rcx+28h]
0x18005411b  mov     [rbp+hKey], rax
0x18005411f  mov     r14, [rbp+lpValueName]
0x180054123  lea     rcx, [rbp+cbData]
0x180054127  mov     [rsp+70h+lpcbData], rcx; lpcbData
0x18005412c  lea     rax, [rdi+58h]
0x180054130  mov     rcx, [rbp+hKey]; hKey
0x180054134  lea     r9, [rbp+Type]; lpType
0x180054138  xor     r8d, r8d; lpReserved
0x18005413b  mov     [rbp+cbData], 100h
0x180054142  mov     rdx, r14; lpValueName
0x180054145  mov     [rsp+70h+lpData], rax; lpData
0x18005414a  call    cs:__imp_RegQueryValueExW
0x180054150  test    eax, eax
0x180054152  jnz     loc_180054306
0x180054158  mov     dword ptr [rdi+54h], 1
0x18005415f  jmp     loc_180054322
0x180054164  mov     rcx, [rcx+20h]
0x180054168  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005416c  test    rcx, rcx
0x18005416f  jz      short loc_18005417F
0x180054171  mov     rax, r8
0x180054174  inc     rax
0x180054177  cmp     [rcx+rax*2], bx
0x18005417b  jnz     short loc_180054174
0x18005417d  jmp     short loc_180054182
0x18005417f  mov     rax, rbx
0x180054182  mov     rcx, r8
0x180054185  inc     rcx
0x180054188  cmp     [r13+rcx*2+0], bx
0x18005418e  jnz     short loc_180054185
0x180054190  lea     r14, [rax+2]
0x180054194  mov     rax, rdx
0x180054197  add     r14, rcx
0x18005419a  mul     r14
0x18005419d  cmovb   rax, r8
0x1800541a1  mov     rcx, rax; cb
0x1800541a4  call    cs:__imp_CoTaskMemAlloc
0x1800541aa  mov     rsi, rax
0x1800541ad  test    rax, rax
0x1800541b0  jnz     short loc_1800541BC
0x1800541b2  mov     eax, 8007000Eh
0x1800541b7  jmp     loc_1800544E8
0x1800541bc  mov     [rax], bx
0x1800541bf  mov     r9, [rdi+20h]
0x1800541c3  test    r9, r9
0x1800541c6  jz      short loc_1800541E4
0x1800541c8  lea     r8, aS_2; "%s\\"
0x1800541cf  mov     rdx, r14; unsigned __int64
0x1800541d2  mov     rcx, rsi; unsigned __int16 *
0x1800541d5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800541da  mov     ebx, eax
0x1800541dc  test    eax, eax
0x1800541de  js      loc_1800544DD
0x1800541e4  mov     r8, r13; unsigned __int16 *
0x1800541e7  mov     rdx, r14; unsigned __int64
0x1800541ea  mov     rcx, rsi; unsigned __int16 *
0x1800541ed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800541f2  mov     ebx, eax
0x1800541f4  test    eax, eax
0x1800541f6  js      loc_1800544DD
0x1800541fc  mov     edx, r12d; Ch
0x1800541ff  mov     rcx, rsi; Str
0x180054202  call    cs:__imp_wcsrchr
0x180054208  test    rax, rax
0x18005420b  jz      short loc_18005421B
0x18005420d  mov     rcx, rax; lpsz
0x180054210  call    cs:__imp_CharNextW
0x180054216  mov     r12, rax
0x180054219  jmp     short loc_18005421E
0x18005421b  mov     r12, rsi
0x18005421e  mov     rbx, [rdi+48h]
0x180054222  test    rbx, rbx
0x180054225  jz      short loc_180054253
0x180054227  mov     rdx, rsi; unsigned __int16 *
0x18005422a  mov     rcx, rbx; this
0x18005422d  call    ?Find@CHkeyCache@@AEAAJPEBG@Z; CHkeyCache::Find(ushort const *)
0x180054232  cmp     eax, 0FFFFFFFFh
0x180054235  jle     short loc_180054253
0x180054237  movsxd  rcx, eax
0x18005423a  mov     rax, [rbx]
0x18005423d  add     rcx, rcx
0x180054240  xor     ebx, ebx
0x180054242  mov     rcx, [rax+rcx*8+8]
0x180054247  mov     eax, ebx
0x180054249  mov     [rbp+hKey], rcx
0x18005424d  lea     r15d, [rbx+1]
0x180054251  jmp     short loc_18005426E
0x180054253  mov     r9d, [rdi+40h]; unsigned int
0x180054257  lea     rax, [rbp+hKey]
0x18005425b  mov     rcx, [rdi+18h]; HKEY
0x18005425f  xor     ebx, ebx
0x180054261  mov     rdx, r13; unsigned __int16 *
0x180054264  mov     [rsp+70h+lpData], rax; unsigned int
0x180054269  call    ?RegSafeOpenKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; RegSafeOpenKeyEx(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18005426e  mov     ecx, [rbp+arg_8]
0x180054271  test    ecx, ecx
0x180054273  jz      short loc_1800542DE
0x180054275  sub     ecx, 1
0x180054278  jz      short loc_1800542D1
0x18005427a  cmp     ecx, 1
0x18005427d  jz      short loc_180054289
0x18005427f  mov     ebx, 8000FFFFh
0x180054284  jmp     loc_1800544DD
0x180054289  cmp     eax, 2
0x18005428c  jnz     short loc_1800542DE
0x18005428e  mov     rcx, [rdi+18h]; HKEY
0x180054292  lea     rax, [rbp+var_1C]
0x180054296  mov     [rsp+70h+var_30], rax; unsigned int *
0x18005429b  mov     rdx, r13; unsigned __int16 *
0x18005429e  lea     rax, [rbp+hKey]
0x1800542a2  mov     [rsp+70h+var_38], rax; HKEY *
0x1800542a7  mov     eax, [rdi+40h]
0x1800542aa  mov     dword ptr [rsp+70h+lpcbData], eax; unsigned int
0x1800542ae  call    ?RegSafeCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; RegSafeCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x1800542b3  test    eax, eax
0x1800542b5  jz      loc_18005411F
0x1800542bb  cmp     eax, 522h
0x1800542c0  jz      short loc_1800542FC
0x1800542c2  cmp     eax, 5
0x1800542c5  jz      short loc_1800542FC
0x1800542c7  mov     ebx, 80110021h
0x1800542cc  jmp     loc_1800544DD
0x1800542d1  cmp     eax, 2
0x1800542d4  jnz     short loc_1800542DE
0x1800542d6  lea     ebx, [rax-1]
0x1800542d9  jmp     loc_1800544DD
0x1800542de  test    eax, eax
0x1800542e0  jz      loc_18005411F
0x1800542e6  cmp     eax, 522h
0x1800542eb  jz      short loc_1800542FC
0x1800542ed  cmp     eax, 5
0x1800542f0  jz      short loc_1800542FC
0x1800542f2  mov     ebx, 80110031h
0x1800542f7  jmp     loc_1800544DD
0x1800542fc  mov     ebx, 80110823h
0x180054301  jmp     loc_1800544DD
0x180054306  mov     [rdi+54h], ebx
0x180054309  cmp     eax, 0EAh
0x18005430e  jz      short loc_180054320
0x180054310  cmp     eax, 2
0x180054313  jnz     short loc_180054322
0x180054315  test    r14, r14
0x180054318  jnz     short loc_180054322
0x18005431a  mov     [rbp+Type], ebx
0x18005431d  mov     [rbp+cbData], ebx
0x180054320  mov     eax, ebx
0x180054322  mov     ecx, [rbp+arg_8]
0x180054325  mov     ebx, 80110027h
0x18005432a  sub     ecx, 1
0x18005432d  jz      loc_1800543CB
0x180054333  cmp     ecx, 1
0x180054336  jnz     short loc_180054392
0x180054338  cmp     eax, 2
0x18005433b  jnz     short loc_180054392
0x18005433d  mov     rcx, [rbp+hKey]; hKey
0x180054341  xor     r9d, r9d; dwType
0x180054344  mov     dword ptr [rsp+70h+lpcbData], 0; cbData
0x18005434c  xor     r8d, r8d; Reserved
0x18005434f  mov     rdx, r14; lpValueName
0x180054352  mov     [rsp+70h+lpData], 0; lpData
0x18005435b  call    cs:__imp_RegSetValueExW
0x180054361  test    eax, eax
0x180054363  jz      short loc_18005436C
0x180054365  mov     ebx, 80110028h
0x18005436a  jmp     short loc_180054396
0x18005436c  mov     rcx, [rbp+hKey]; hKey
0x180054370  lea     rax, [rbp+cbData]
0x180054374  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180054379  lea     r9, [rbp+Type]; lpType
0x18005437d  xor     r8d, r8d; lpReserved
0x180054380  mov     [rsp+70h+lpData], 0; lpData
0x180054389  mov     rdx, r14; lpValueName
0x18005438c  call    cs:__imp_RegQueryValueExW
0x180054392  test    eax, eax
0x180054394  jz      short loc_1800543D5
0x180054396  mov     rcx, [rbp+hKey]; HKEY
0x18005439a  cmp     [rdi+18h], rcx
0x18005439e  jz      loc_1800544D8
0x1800543a4  test    r15d, r15d
0x1800543a7  jnz     loc_1800544D8
0x1800543ad  call    ?RegSafeCloseKey@@YAJPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ *)
0x1800543b2  test    rsi, rsi
0x1800543b5  jz      loc_1800544E6
0x1800543bb  mov     rcx, rsi; pv
0x1800543be  call    cs:__imp_CoTaskMemFree
0x1800543c4  xor     esi, esi
0x1800543c6  jmp     loc_1800544D8
0x1800543cb  cmp     eax, 2
0x1800543ce  jnz     short loc_180054392
0x1800543d0  lea     ebx, [rax-1]
0x1800543d3  jmp     short loc_180054396
0x1800543d5  and     dword ptr [rdi+8], 0FFFFFFFCh
0x1800543d9  mov     r14d, 5Ch ; '\'
0x1800543df  mov     eax, [rbp+var_18]
0x1800543e2  or      [rdi+8], eax
0x1800543e5  cmp     r14w, [r13+0]
0x1800543ea  jz      loc_18005447D
0x1800543f0  mov     rcx, [rdi+48h]; this
0x1800543f4  test    rcx, rcx
0x1800543f7  jz      short loc_180054444
0x1800543f9  test    r15d, r15d
0x1800543fc  jnz     short loc_180054419
0x1800543fe  test    rsi, rsi
0x180054401  jz      short loc_180054419
0x180054403  mov     r8, [rbp+hKey]; HKEY
0x180054407  mov     rdx, rsi; unsigned __int16 *
0x18005440a  call    ?Append@CHkeyCache@@QEAAJPEBGPEAUHKEY__@@@Z; CHkeyCache::Append(ushort const *,HKEY__ *)
0x18005440f  mov     ebx, eax
0x180054411  test    eax, eax
0x180054413  js      loc_1800544DD
0x180054419  cmp     dword ptr [rdi+50h], 0
0x18005441d  jz      short loc_180054436
0x18005441f  mov     rcx, [rdi+20h]; pv
0x180054423  test    rcx, rcx
0x180054426  jz      short loc_180054436
0x180054428  call    cs:__imp_CoTaskMemFree
0x18005442e  mov     qword ptr [rdi+20h], 0
0x180054436  mov     [rdi+50h], r15d
0x18005443a  lea     r14, [rdi+18h]
0x18005443e  lea     rbx, [rdi+20h]
0x180054442  jmp     short loc_180054469
0x180054444  lea     r14, [rdi+18h]
0x180054448  mov     rcx, [r14]; HKEY
0x18005444b  call    ?RegSafeCloseKey@@YAJPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ *)
0x180054450  lea     rbx, [rdi+20h]
0x180054454  mov     rcx, [rbx]; pv
0x180054457  test    rcx, rcx
0x18005445a  jz      short loc_180054469
0x18005445c  call    cs:__imp_CoTaskMemFree
0x180054462  mov     qword ptr [rbx], 0
0x180054469  mov     rax, [rbp+hKey]
0x18005446d  mov     [rbx], rsi
0x180054470  xor     esi, esi
0x180054472  mov     [r14], rax
0x180054475  mov     [rdi+28h], r12
0x180054479  lea     r14d, [rsi+5Ch]
0x18005447d  lea     rbx, [rdi+30h]
0x180054481  mov     rcx, [rbx]; pv
0x180054484  test    rcx, rcx
0x180054487  jz      short loc_180054496
0x180054489  call    cs:__imp_CoTaskMemFree
0x18005448f  mov     qword ptr [rbx], 0
0x180054496  mov     rcx, [rbp+arg_18]; unsigned __int16 *
0x18005449a  cmp     r14w, [rcx]
0x18005449e  jz      short loc_1800544B0
0x1800544a0  mov     rdx, rbx; unsigned __int16 **
0x1800544a3  call    ?LocalCopyString@@YAJPEBGPEAPEAG@Z; LocalCopyString(ushort const *,ushort * *)
0x1800544a8  mov     ebx, eax
0x1800544aa  test    eax, eax
0x1800544ac  js      short loc_1800544D8
0x1800544ae  jmp     short loc_1800544B7
0x1800544b0  mov     qword ptr [rbx], 0
0x1800544b7  cmp     [rbp+arg_8], 2
0x1800544bb  mov     eax, [rbp+Type]
0x1800544be  mov     [rdi+38h], eax
0x1800544c1  mov     eax, [rbp+cbData]
0x1800544c4  mov     [rdi+3Ch], eax
0x1800544c7  jnz     short loc_1800544D6
0x1800544c9  cmp     [rbp+var_1C], 1
0x1800544cd  jnz     short loc_1800544D6
0x1800544cf  mov     ebx, 110002h
0x1800544d4  jmp     short loc_1800544D8
0x1800544d6  xor     ebx, ebx
0x1800544d8  test    rsi, rsi
0x1800544db  jz      short loc_1800544E6
0x1800544dd  mov     rcx, rsi; pv
  ... truncated ...
```
