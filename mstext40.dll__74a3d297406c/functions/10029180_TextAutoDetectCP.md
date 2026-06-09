# TextAutoDetectCP

- ea: `0x10029180`
- end: `0x10029518`
- name: `TextAutoDetectCP`
- size: `920`
- prototype: `int __stdcall(LPCWSTR lpFileName, int, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x10029870`

## callees

- `0x1000b070`
- `0x1000b200`
- `0x1000b3f0`
- `0x1000b9b0`
- `0x10029180`
- `0x1002b81a`
- `0x1002c490`
- `0x1002cce0`
- `0x1002db50`
- `0x1002deda`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1002921d`
- `KERNEL32!ReadFile` at `0x1002921d`
- `KERNEL32!GetOEMCP` at `0x100294da`
- `KERNEL32!GetOEMCP` at `0x100294da`
- `KERNEL32!MultiByteToWideChar` at `0x100293fb`
- `KERNEL32!MultiByteToWideChar` at `0x100293fb`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10029409`
- `OLEAUT32!__imp__SysAllocString@4` at `0x10029409`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1002943b`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1002943b`

## pseudocode

```c
int __stdcall TextAutoDetectCP(LPCWSTR lpFileName, UINT *a2, int a3)
{
  int v3; // edi
  int v4; // ebp
  int v5; // eax
  int v6; // ecx
  int result; // eax
  int v8; // ebx
  unsigned int v9; // ecx
  char *p_Buffer; // edx
  char *v11; // ebp
  char *v12; // esi
  int v13; // eax
  _BYTE *v14; // esi
  int v15; // eax
  int v16; // eax
  CHAR *v17; // esi
  int v18; // eax
  CHAR i; // al
  BSTR v20; // eax
  OLECHAR *v21; // esi
  _DWORD *v22; // edi
  int v23; // eax
  int v24; // edx
  int *v25; // ecx
  int v26; // [esp+28h] [ebp-1208h] BYREF
  DWORD NumberOfBytesRead; // [esp+2Ch] [ebp-1204h] BYREF
  _DWORD *v28; // [esp+30h] [ebp-1200h]
  HANDLE hFile; // [esp+34h] [ebp-11FCh] BYREF
  int v30; // [esp+38h] [ebp-11F8h]
  char v31[4]; // [esp+3Ch] [ebp-11F4h] BYREF
  UINT v32; // [esp+40h] [ebp-11F0h]
  CHAR MultiByteStr[128]; // [esp+A8h] [ebp-1188h] BYREF
  WCHAR WideCharStr[128]; // [esp+128h] [ebp-1108h] BYREF
  char Buffer; // [esp+228h] [ebp-1008h] BYREF
  char v36; // [esp+229h] [ebp-1007h]

  v3 = 0;
  v26 = 100;
  v28 = 0;
  v4 = 0;
  *a2 = 0;
  v5 = DOSOpenFile(lpFileName, 16, (int)&hFile);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 == -4 )
      return -1807;
    if ( v5 == -2 )
      return -1811;
    result = -1032;
    if ( v6 == -3 )
      return -1023;
    return result;
  }
  if ( ReadFile(hFile, &Buffer, 0x1000u, &NumberOfBytesRead, 0) )
  {
    v9 = NumberOfBytesRead;
    if ( !NumberOfBytesRead )
    {
      v8 = -5015;
      goto LABEL_60;
    }
    if ( Buffer == -1 )
    {
      if ( v36 == -2 )
      {
        *a2 = 1200;
        v8 = 0;
        goto LABEL_60;
      }
    }
    else if ( Buffer == -2 && v36 == -1 )
    {
      *a2 = 1201;
      v8 = 0;
      goto LABEL_60;
    }
    do
    {
      if ( *(&Buffer + v9 - 1) )
        break;
      --v9;
    }
    while ( v9 );
    NumberOfBytesRead = v9;
    if ( v9 > 1 )
    {
      p_Buffer = &Buffer;
      while ( p_Buffer[1] || !*p_Buffer )
      {
        p_Buffer += 2;
        if ( (unsigned int)&p_Buffer[1 - (_DWORD)&Buffer] >= v9 )
          goto LABEL_26;
      }
      *a2 = 1200;
      goto LABEL_59;
    }
LABEL_26:
    v30 = 0;
    if ( a3 == 3 && v9 )
    {
      v11 = strstr(&Buffer, "<META");
      if ( v11 || (v11 = strstr(&Buffer, "<meta")) != 0 )
      {
        v12 = strstr(v11, "charset");
        if ( v12 || (v12 = strstr(v11, "CHARSET")) != 0 )
        {
          v13 = v12[7];
          v14 = v12 + 7;
          if ( isspace(v13) > 0 )
          {
            do
              v15 = (char)*++v14;
            while ( isspace(v15) > 0 );
          }
          if ( *v14 == 61 )
          {
            v16 = (char)v14[1];
            v17 = v14 + 1;
            if ( isspace(v16) > 0 )
            {
              do
                v18 = *++v17;
              while ( isspace(v18) > 0 );
            }
            for ( i = *v17; *v17 != 59; i = *v17 )
            {
              if ( i == 62 )
                break;
              if ( i == 34 )
                break;
              if ( !i )
                break;
              ++v17;
              MultiByteStr[v3++] = i;
            }
            MultiByteStr[v3] = 0;
            MultiByteToWideChar(0, 0, MultiByteStr, strlen(MultiByteStr) + 1, WideCharStr, 128);
            v20 = SysAllocString(WideCharStr);
            v21 = v20;
            if ( v20 )
            {
              if ( !(*(int (__stdcall **)(int, BSTR, char *))(*(_DWORD *)pML2 + 28))(pML2, v20, v31) )
              {
                *a2 = v32;
                v30 = 1;
              }
              SysFreeString(v21);
              if ( v30 )
              {
LABEL_57:
                if ( *a2 == 20127 )
                  *a2 = GetOEMCP();
LABEL_59:
                v8 = 0;
                goto LABEL_60;
              }
            }
          }
        }
      }
      v4 = 0;
    }
    v22 = (_DWORD *)MemAllocate(16 * v26);
    v28 = v22;
    if ( !v22 )
    {
      v8 = -1011;
      goto LABEL_60;
    }
    memset(v22, 0, 16 * v26);
    v23 = (*(int (__stdcall **)(int, int, _DWORD, char *, DWORD *, _DWORD *, int *))(*(_DWORD *)pML2 + 88))(
            pML2,
            4,
            0,
            &Buffer,
            &NumberOfBytesRead,
            v22,
            &v26);
    v24 = v26;
    if ( v23 )
      v24 = 0;
    v26 = v24;
    if ( v24 > 0 )
    {
      v25 = v22 + 3;
      do
      {
        if ( *v25 > v4 )
        {
          *a2 = *(v25 - 2);
          v4 = *v25;
        }
        v25 += 4;
        --v24;
      }
      while ( v24 );
    }
    goto LABEL_57;
  }
  v8 = -1022;
LABEL_60:
  DOSCloseFile(hFile);
  if ( v28 )
    MemFree(v28);
  return v8;
}

```

## disassembly

```asm
0x10029180  mov     eax, 1208h
0x10029185  call    __chkstk
0x1002918a  mov     eax, ___security_cookie
0x1002918f  xor     eax, esp
0x10029191  mov     [esp+1208h+var_4], eax
0x10029198  mov     eax, [esp+1208h+lpFileName]
0x1002919f  lea     ecx, [esp+1208h+hFile]
0x100291a3  push    ebx
0x100291a4  mov     ebx, [esp+120Ch+arg_4]
0x100291ab  push    ebp
0x100291ac  push    edi
0x100291ad  push    ecx; int
0x100291ae  push    10h; int
0x100291b0  xor     edi, edi
0x100291b2  mov     [esp+121Ch+var_1208], 64h ; 'd'
0x100291ba  push    eax; lpFileName
0x100291bb  mov     [esp+1220h+var_1200], 0
0x100291c3  xor     ebp, ebp
0x100291c5  mov     [ebx], edi
0x100291c7  call    _DOSOpenFile@12; DOSOpenFile(x,x,x)
0x100291cc  mov     ecx, eax
0x100291ce  test    ecx, ecx
0x100291d0  jz      short loc_10029205
0x100291d2  cmp     ecx, 0FFFFFFFCh
0x100291d5  jnz     short loc_100291E1
0x100291d7  mov     eax, 0FFFFF8F1h
0x100291dc  jmp     loc_100294FE
0x100291e1  cmp     ecx, 0FFFFFFFEh
0x100291e4  jnz     short loc_100291F0
0x100291e6  mov     eax, 0FFFFF8EDh
0x100291eb  jmp     loc_100294FE
0x100291f0  cmp     ecx, 0FFFFFFFDh
0x100291f3  mov     eax, 0FFFFFBF8h
0x100291f8  mov     edx, 0FFFFFC01h
0x100291fd  cmovz   eax, edx
0x10029200  jmp     loc_100294FE
0x10029205  push    0; lpOverlapped
0x10029207  lea     eax, [esp+1218h+NumberOfBytesRead]
0x1002920b  push    eax; lpNumberOfBytesRead
0x1002920c  push    1000h; nNumberOfBytesToRead
0x10029211  lea     eax, [esp+1220h+Buffer]
0x10029218  push    eax; lpBuffer
0x10029219  push    [esp+1224h+hFile]; hFile
0x1002921d  call    ds:__imp__ReadFile@20; ReadFile(x,x,x,x,x)
0x10029223  test    eax, eax
0x10029225  jnz     short loc_10029231
0x10029227  mov     ebx, 0FFFFFC02h
0x1002922c  jmp     loc_100294E5
0x10029231  mov     ecx, [esp+1214h+NumberOfBytesRead]
0x10029235  test    ecx, ecx
0x10029237  jnz     short loc_10029243
0x10029239  mov     ebx, 0FFFFEC69h
0x1002923e  jmp     loc_100294E5
0x10029243  mov     al, [esp+1214h+Buffer]
0x1002924a  cmp     al, 0FFh
0x1002924c  jnz     short loc_10029265
0x1002924e  cmp     [esp+1214h+var_1007], 0FEh
0x10029256  jnz     short loc_10029280
0x10029258  mov     dword ptr [ebx], 4B0h
0x1002925e  xor     ebx, ebx
0x10029260  jmp     loc_100294E5
0x10029265  cmp     al, 0FEh
0x10029267  jnz     short loc_10029280
0x10029269  cmp     [esp+1214h+var_1007], 0FFh
0x10029271  jnz     short loc_10029280
0x10029273  mov     dword ptr [ebx], 4B1h
0x10029279  xor     ebx, ebx
0x1002927b  jmp     loc_100294E5
0x10029280  lea     eax, [esp+1214h+Buffer]
0x10029287  cmp     byte ptr [eax+ecx-1], 0
0x1002928c  jnz     short loc_10029291
0x1002928e  dec     ecx
0x1002928f  jnz     short loc_10029287
0x10029291  mov     [esp+1214h+NumberOfBytesRead], ecx
0x10029295  push    esi
0x10029296  cmp     ecx, 1
0x10029299  jbe     short loc_100292C9
0x1002929b  lea     edx, [esp+1218h+Buffer]
0x100292a2  mov     esi, 1
0x100292a7  mov     eax, edx
0x100292a9  sub     esi, eax
0x100292ab  jmp     short loc_100292B0
0x100292b0  cmp     byte ptr [edx+1], 0
0x100292b4  jnz     short loc_100292BF
0x100292b6  cmp     byte ptr [edx], 0
0x100292b9  jnz     loc_1002946C
0x100292bf  add     edx, 2
0x100292c2  lea     eax, [esi+edx]
0x100292c5  cmp     eax, ecx
0x100292c7  jb      short loc_100292B0
0x100292c9  cmp     [esp+1218h+arg_8], 3
0x100292d1  mov     [esp+1218h+var_11F8], edi
0x100292d5  jnz     loc_1002944E
0x100292db  test    ecx, ecx
0x100292dd  jz      loc_1002944E
0x100292e3  lea     eax, [esp+1218h+Buffer]
0x100292ea  push    offset aMeta; "<META"
0x100292ef  push    eax; Str
0x100292f0  call    _strstr
0x100292f5  mov     ebp, eax
0x100292f7  add     esp, 8
0x100292fa  test    ebp, ebp
0x100292fc  jnz     short loc_1002931D
0x100292fe  lea     eax, [esp+1218h+Buffer]
0x10029305  push    offset aMeta_0; "<meta"
0x1002930a  push    eax; Str
0x1002930b  call    _strstr
0x10029310  mov     ebp, eax
0x10029312  add     esp, 8
0x10029315  test    ebp, ebp
0x10029317  jz      loc_1002944C
0x1002931d  push    offset aCharset_1; "charset"
0x10029322  push    ebp; Str
0x10029323  call    _strstr
0x10029328  mov     esi, eax
0x1002932a  add     esp, 8
0x1002932d  test    esi, esi
0x1002932f  jnz     short loc_10029349
0x10029331  push    offset aCharset; "CHARSET"
0x10029336  push    ebp; Str
0x10029337  call    _strstr
0x1002933c  mov     esi, eax
0x1002933e  add     esp, 8
0x10029341  test    esi, esi
0x10029343  jz      loc_1002944C
0x10029349  movsx   eax, byte ptr [esi+7]
0x1002934d  add     esi, 7
0x10029350  push    eax; C
0x10029351  call    _isspace
0x10029356  add     esp, 4
0x10029359  test    eax, eax
0x1002935b  jle     short loc_10029372
0x1002935d  lea     ecx, [ecx+0]
0x10029360  movsx   eax, byte ptr [esi+1]
0x10029364  inc     esi
0x10029365  push    eax; C
0x10029366  call    _isspace
0x1002936b  add     esp, 4
0x1002936e  test    eax, eax
0x10029370  jg      short loc_10029360
0x10029372  cmp     byte ptr [esi], 3Dh ; '='
0x10029375  jnz     loc_1002944C
0x1002937b  movsx   eax, byte ptr [esi+1]
0x1002937f  inc     esi
0x10029380  push    eax; C
0x10029381  call    _isspace
0x10029386  add     esp, 4
0x10029389  test    eax, eax
0x1002938b  jle     short loc_100293A2
0x1002938d  lea     ecx, [ecx+0]
0x10029390  movsx   eax, byte ptr [esi+1]
0x10029394  inc     esi
0x10029395  push    eax; C
0x10029396  call    _isspace
0x1002939b  add     esp, 4
0x1002939e  test    eax, eax
0x100293a0  jg      short loc_10029390
0x100293a2  mov     al, [esi]
0x100293a4  cmp     al, 3Bh ; ';'
0x100293a6  jz      short loc_100293C3
0x100293a8  cmp     al, 3Eh ; '>'
0x100293aa  jz      short loc_100293C3
0x100293ac  cmp     al, 22h ; '"'
0x100293ae  jz      short loc_100293C3
0x100293b0  test    al, al
0x100293b2  jz      short loc_100293C3
0x100293b4  inc     esi
0x100293b5  mov     [esp+edi+1218h+MultiByteStr], al
0x100293bc  inc     edi
0x100293bd  mov     al, [esi]
0x100293bf  cmp     al, 3Bh ; ';'
0x100293c1  jnz     short loc_100293A8
0x100293c3  lea     ecx, [esp+1218h+MultiByteStr]
0x100293ca  mov     [esp+edi+1218h+MultiByteStr], 0
0x100293d2  lea     edx, [ecx+1]
0x100293d5  mov     al, [ecx]
0x100293d7  inc     ecx
0x100293d8  test    al, al
0x100293da  jnz     short loc_100293D5
0x100293dc  push    80h; cchWideChar
0x100293e1  sub     ecx, edx
0x100293e3  lea     eax, [esp+121Ch+WideCharStr]
0x100293ea  push    eax; lpWideCharStr
0x100293eb  lea     eax, [ecx+1]
0x100293ee  push    eax; cbMultiByte
0x100293ef  lea     eax, [esp+1224h+MultiByteStr]
0x100293f6  push    eax; lpMultiByteStr
0x100293f7  push    0; dwFlags
0x100293f9  push    0; CodePage
0x100293fb  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x10029401  lea     eax, [esp+1218h+WideCharStr]
0x10029408  push    eax; psz
0x10029409  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x1002940f  mov     esi, eax
0x10029411  test    esi, esi
0x10029413  jz      short loc_1002944C
0x10029415  mov     eax, _pML2
0x1002941a  lea     edx, [esp+1218h+var_11F4]
0x1002941e  push    edx
0x1002941f  push    esi
0x10029420  push    eax
0x10029421  mov     ecx, [eax]
0x10029423  mov     eax, [ecx+1Ch]
0x10029426  call    eax
0x10029428  test    eax, eax
0x1002942a  jnz     short loc_1002943A
0x1002942c  mov     eax, [esp+1218h+var_11F0]
0x10029430  mov     [ebx], eax
0x10029432  mov     [esp+1218h+var_11F8], 1
0x1002943a  push    esi; bstrString
0x1002943b  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x10029441  cmp     [esp+1218h+var_11F8], 0
0x10029446  jnz     loc_100294D2
0x1002944c  xor     ebp, ebp
0x1002944e  mov     eax, [esp+1218h+var_1208]
0x10029452  shl     eax, 4
0x10029455  push    eax; Size
0x10029456  call    _MemAllocate@4; MemAllocate(x)
0x1002945b  mov     edi, eax
0x1002945d  mov     [esp+1218h+var_1200], edi
0x10029461  test    edi, edi
0x10029463  jnz     short loc_10029474
0x10029465  mov     ebx, 0FFFFFC0Dh
0x1002946a  jmp     short loc_100294E4
0x1002946c  mov     dword ptr [ebx], 4B0h
0x10029472  jmp     short loc_100294E2
0x10029474  mov     eax, [esp+1218h+var_1208]
0x10029478  shl     eax, 4
0x1002947b  push    eax; Size
0x1002947c  push    0; Val
0x1002947e  push    edi; void *
0x1002947f  call    _memset
0x10029484  mov     eax, _pML2
0x10029489  lea     edx, [esp+1224h+var_1208]
0x1002948d  add     esp, 0Ch
0x10029490  mov     ecx, [eax]
0x10029492  push    edx
0x10029493  push    edi
0x10029494  lea     edx, [esp+1220h+NumberOfBytesRead]
0x10029498  push    edx
0x10029499  lea     edx, [esp+1224h+Buffer]
0x100294a0  push    edx
0x100294a1  push    0
0x100294a3  push    4
0x100294a5  push    eax
0x100294a6  mov     eax, [ecx+58h]
0x100294a9  call    eax
0x100294ab  mov     edx, [esp+1218h+var_1208]
0x100294af  xor     ecx, ecx
0x100294b1  test    eax, eax
0x100294b3  cmovnz  edx, ecx
0x100294b6  mov     [esp+1218h+var_1208], edx
0x100294ba  test    edx, edx
0x100294bc  jle     short loc_100294D2
0x100294be  lea     ecx, [edi+0Ch]
0x100294c1  cmp     [ecx], ebp
0x100294c3  jle     short loc_100294CC
0x100294c5  mov     eax, [ecx-8]
0x100294c8  mov     [ebx], eax
0x100294ca  mov     ebp, [ecx]
0x100294cc  add     ecx, 10h
0x100294cf  dec     edx
0x100294d0  jnz     short loc_100294C1
0x100294d2  cmp     dword ptr [ebx], 4E9Fh
0x100294d8  jnz     short loc_100294E2
0x100294da  call    ds:__imp__GetOEMCP@0; GetOEMCP()
0x100294e0  mov     [ebx], eax
0x100294e2  xor     ebx, ebx
0x100294e4  pop     esi
0x100294e5  push    [esp+1214h+hFile]; hObject
0x100294e9  call    _DOSCloseFile@4; DOSCloseFile(x)
0x100294ee  mov     eax, [esp+1214h+var_1200]
0x100294f2  test    eax, eax
0x100294f4  jz      short loc_100294FC
0x100294f6  push    eax
0x100294f7  call    _MemFree@4; MemFree(x)
0x100294fc  mov     eax, ebx
0x100294fe  mov     ecx, [esp+1214h+var_4]
0x10029505  pop     edi
0x10029506  pop     ebp
0x10029507  pop     ebx
0x10029508  xor     ecx, esp; StackCookie
0x1002950a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002950f  add     esp, 1208h
0x10029515  retn    0Ch
```
