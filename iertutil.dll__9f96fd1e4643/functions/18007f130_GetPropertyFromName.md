# GetPropertyFromName

- ea: `0x18007f130`
- end: `0x18007f38f`
- name: `GetPropertyFromName`
- size: `607`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18007f130`
- `0x180083bda`

## string_xrefs

- `0x18007f172`: `Uri_PROPERTY_AUTHORITY`
- `0x18007f158`: `Uri_PROPERTY_ABSOLUTE_URI`
- `0x18007f1a8`: `Uri_PROPERTY_DOMAIN`
- `0x18007f18d`: `Uri_PROPERTY_DISPLAY_URI`
- `0x18007f1de`: `Uri_PROPERTY_FRAGMENT`
- `0x18007f1c3`: `Uri_PROPERTY_EXTENSION`
- `0x18007f21a`: `Uri_PROPERTY_PASSWORD`
- `0x18007f1fc`: `Uri_PROPERTY_HOST`
- `0x18007f256`: `Uri_PROPERTY_PATH_AND_QUERY`
- `0x18007f238`: `Uri_PROPERTY_PATH`
- `0x18007f292`: `Uri_PROPERTY_RAW_URI`
- `0x18007f274`: `Uri_PROPERTY_QUERY`
- `0x18007f2ce`: `Uri_PROPERTY_USER_INFO`
- `0x18007f2b0`: `Uri_PROPERTY_SCHEME_NAME`
- `0x18007f30a`: `Uri_PROPERTY_HOST_TYPE`
- `0x18007f2ec`: `Uri_PROPERTY_USER_NAME`
- `0x18007f346`: `Uri_PROPERTY_SCHEME`
- `0x18007f328`: `Uri_PROPERTY_PORT`
- `0x18007f364`: `Uri_PROPERTY_ZONE`

## pseudocode

```c
__int64 __fastcall GetPropertyFromName(wchar_t *String1, _DWORD *a2)
{
  if ( a2 )
  {
    *a2 = 0;
    if ( String1 )
    {
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_ABSOLUTE_URI") )
        return 1;
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_AUTHORITY") )
      {
        *a2 = 1;
        return 1;
      }
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_DISPLAY_URI") )
      {
        *a2 = 2;
        return 1;
      }
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_DOMAIN") )
      {
        *a2 = 3;
        return 1;
      }
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_EXTENSION") )
      {
        *a2 = 4;
        return 1;
      }
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_FRAGMENT") )
      {
        *a2 = 5;
        return 1;
      }
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_HOST") )
      {
        *a2 = 6;
        return 1;
      }
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_PASSWORD") )
      {
        *a2 = 7;
        return 1;
      }
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_PATH") )
      {
        *a2 = 8;
        return 1;
      }
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_PATH_AND_QUERY") )
      {
        *a2 = 9;
        return 1;
      }
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_QUERY") )
      {
        *a2 = 10;
        return 1;
      }
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_RAW_URI") )
      {
        *a2 = 11;
        return 1;
      }
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_SCHEME_NAME") )
      {
        *a2 = 12;
        return 1;
      }
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_USER_INFO") )
      {
        *a2 = 13;
        return 1;
      }
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_USER_NAME") )
      {
        *a2 = 14;
        return 1;
      }
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_HOST_TYPE") )
      {
        *a2 = 15;
        return 1;
      }
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_PORT") )
      {
        *a2 = 16;
        return 1;
      }
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_SCHEME") )
      {
        *a2 = 17;
        return 1;
      }
      if ( !wcscmp_0(String1, L"Uri_PROPERTY_ZONE") )
      {
        *a2 = 18;
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18007f130  mov     [rsp+arg_0], rbx
0x18007f135  push    rdi
0x18007f136  sub     rsp, 20h
0x18007f13a  mov     rbx, rdx
0x18007f13d  mov     rdi, rcx
0x18007f140  test    rdx, rdx
0x18007f143  jz      loc_18007F382
0x18007f149  mov     dword ptr [rdx], 0
0x18007f14f  test    rcx, rcx
0x18007f152  jz      loc_18007F382
0x18007f158  lea     rdx, aUriPropertyAbs; "Uri_PROPERTY_ABSOLUTE_URI"
0x18007f15f  call    wcscmp_0
0x18007f164  test    eax, eax
0x18007f166  jnz     short loc_18007F172
0x18007f168  mov     eax, 1
0x18007f16d  jmp     loc_18007F384
0x18007f172  lea     rdx, aUriPropertyAut; "Uri_PROPERTY_AUTHORITY"
0x18007f179  mov     rcx, rdi; String1
0x18007f17c  call    wcscmp_0
0x18007f181  test    eax, eax
0x18007f183  jnz     short loc_18007F18D
0x18007f185  mov     dword ptr [rbx], 1
0x18007f18b  jmp     short loc_18007F168
0x18007f18d  lea     rdx, aUriPropertyDis; "Uri_PROPERTY_DISPLAY_URI"
0x18007f194  mov     rcx, rdi; String1
0x18007f197  call    wcscmp_0
0x18007f19c  test    eax, eax
0x18007f19e  jnz     short loc_18007F1A8
0x18007f1a0  mov     dword ptr [rbx], 2
0x18007f1a6  jmp     short loc_18007F168
0x18007f1a8  lea     rdx, aUriPropertyDom; "Uri_PROPERTY_DOMAIN"
0x18007f1af  mov     rcx, rdi; String1
0x18007f1b2  call    wcscmp_0
0x18007f1b7  test    eax, eax
0x18007f1b9  jnz     short loc_18007F1C3
0x18007f1bb  mov     dword ptr [rbx], 3
0x18007f1c1  jmp     short loc_18007F168
0x18007f1c3  lea     rdx, aUriPropertyExt; "Uri_PROPERTY_EXTENSION"
0x18007f1ca  mov     rcx, rdi; String1
0x18007f1cd  call    wcscmp_0
0x18007f1d2  test    eax, eax
0x18007f1d4  jnz     short loc_18007F1DE
0x18007f1d6  mov     dword ptr [rbx], 4
0x18007f1dc  jmp     short loc_18007F168
0x18007f1de  lea     rdx, aUriPropertyFra; "Uri_PROPERTY_FRAGMENT"
0x18007f1e5  mov     rcx, rdi; String1
0x18007f1e8  call    wcscmp_0
0x18007f1ed  test    eax, eax
0x18007f1ef  jnz     short loc_18007F1FC
0x18007f1f1  mov     dword ptr [rbx], 5
0x18007f1f7  jmp     loc_18007F168
0x18007f1fc  lea     rdx, aUriPropertyHos_0; "Uri_PROPERTY_HOST"
0x18007f203  mov     rcx, rdi; String1
0x18007f206  call    wcscmp_0
0x18007f20b  test    eax, eax
0x18007f20d  jnz     short loc_18007F21A
0x18007f20f  mov     dword ptr [rbx], 6
0x18007f215  jmp     loc_18007F168
0x18007f21a  lea     rdx, aUriPropertyPas; "Uri_PROPERTY_PASSWORD"
0x18007f221  mov     rcx, rdi; String1
0x18007f224  call    wcscmp_0
0x18007f229  test    eax, eax
0x18007f22b  jnz     short loc_18007F238
0x18007f22d  mov     dword ptr [rbx], 7
0x18007f233  jmp     loc_18007F168
0x18007f238  lea     rdx, aUriPropertyPat_0; "Uri_PROPERTY_PATH"
0x18007f23f  mov     rcx, rdi; String1
0x18007f242  call    wcscmp_0
0x18007f247  test    eax, eax
0x18007f249  jnz     short loc_18007F256
0x18007f24b  mov     dword ptr [rbx], 8
0x18007f251  jmp     loc_18007F168
0x18007f256  lea     rdx, aUriPropertyPat; "Uri_PROPERTY_PATH_AND_QUERY"
0x18007f25d  mov     rcx, rdi; String1
0x18007f260  call    wcscmp_0
0x18007f265  test    eax, eax
0x18007f267  jnz     short loc_18007F274
0x18007f269  mov     dword ptr [rbx], 9
0x18007f26f  jmp     loc_18007F168
0x18007f274  lea     rdx, aUriPropertyQue; "Uri_PROPERTY_QUERY"
0x18007f27b  mov     rcx, rdi; String1
0x18007f27e  call    wcscmp_0
0x18007f283  test    eax, eax
0x18007f285  jnz     short loc_18007F292
0x18007f287  mov     dword ptr [rbx], 0Ah
0x18007f28d  jmp     loc_18007F168
0x18007f292  lea     rdx, aUriPropertyRaw; "Uri_PROPERTY_RAW_URI"
0x18007f299  mov     rcx, rdi; String1
0x18007f29c  call    wcscmp_0
0x18007f2a1  test    eax, eax
0x18007f2a3  jnz     short loc_18007F2B0
0x18007f2a5  mov     dword ptr [rbx], 0Bh
0x18007f2ab  jmp     loc_18007F168
0x18007f2b0  lea     rdx, aUriPropertySch; "Uri_PROPERTY_SCHEME_NAME"
0x18007f2b7  mov     rcx, rdi; String1
0x18007f2ba  call    wcscmp_0
0x18007f2bf  test    eax, eax
0x18007f2c1  jnz     short loc_18007F2CE
0x18007f2c3  mov     dword ptr [rbx], 0Ch
0x18007f2c9  jmp     loc_18007F168
0x18007f2ce  lea     rdx, aUriPropertyUse_0; "Uri_PROPERTY_USER_INFO"
0x18007f2d5  mov     rcx, rdi; String1
0x18007f2d8  call    wcscmp_0
0x18007f2dd  test    eax, eax
0x18007f2df  jnz     short loc_18007F2EC
0x18007f2e1  mov     dword ptr [rbx], 0Dh
0x18007f2e7  jmp     loc_18007F168
0x18007f2ec  lea     rdx, aUriPropertyUse; "Uri_PROPERTY_USER_NAME"
0x18007f2f3  mov     rcx, rdi; String1
0x18007f2f6  call    wcscmp_0
0x18007f2fb  test    eax, eax
0x18007f2fd  jnz     short loc_18007F30A
0x18007f2ff  mov     dword ptr [rbx], 0Eh
0x18007f305  jmp     loc_18007F168
0x18007f30a  lea     rdx, aUriPropertyHos; "Uri_PROPERTY_HOST_TYPE"
0x18007f311  mov     rcx, rdi; String1
0x18007f314  call    wcscmp_0
0x18007f319  test    eax, eax
0x18007f31b  jnz     short loc_18007F328
0x18007f31d  mov     dword ptr [rbx], 0Fh
0x18007f323  jmp     loc_18007F168
0x18007f328  lea     rdx, aUriPropertyPor; "Uri_PROPERTY_PORT"
0x18007f32f  mov     rcx, rdi; String1
0x18007f332  call    wcscmp_0
0x18007f337  test    eax, eax
0x18007f339  jnz     short loc_18007F346
0x18007f33b  mov     dword ptr [rbx], 10h
0x18007f341  jmp     loc_18007F168
0x18007f346  lea     rdx, aUriPropertySch_0; "Uri_PROPERTY_SCHEME"
0x18007f34d  mov     rcx, rdi; String1
0x18007f350  call    wcscmp_0
0x18007f355  test    eax, eax
0x18007f357  jnz     short loc_18007F364
0x18007f359  mov     dword ptr [rbx], 11h
0x18007f35f  jmp     loc_18007F168
0x18007f364  lea     rdx, aUriPropertyZon; "Uri_PROPERTY_ZONE"
0x18007f36b  mov     rcx, rdi; String1
0x18007f36e  call    wcscmp_0
0x18007f373  test    eax, eax
0x18007f375  jnz     short loc_18007F382
0x18007f377  mov     dword ptr [rbx], 12h
0x18007f37d  jmp     loc_18007F168
0x18007f382  xor     eax, eax
0x18007f384  mov     rbx, [rsp+28h+arg_0]
0x18007f389  add     rsp, 20h
0x18007f38d  pop     rdi
0x18007f38e  retn
```
