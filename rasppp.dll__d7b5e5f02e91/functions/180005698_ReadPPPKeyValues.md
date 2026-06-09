# ReadPPPKeyValues

- ea: `0x180005698`
- end: `0x1800058ff`
- name: `ReadPPPKeyValues`
- size: `615`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005908`
- `0x1800152d0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x180005698`
- `0x18002b0dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180005723`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180005723`
- `rtutils!RouterLogEventA` at `0x180005798`
- `rtutils!RouterLogEventA` at `0x18000582b`
- `rtutils!RouterLogEventA` at `0x180005798`
- `rtutils!RouterLogEventA` at `0x18000582b`

## string_xrefs

- `0x180005842`: `Cannot access registry key values %d.`
- `0x1800057b4`: `Using the default value for Registry parameter %hs because the value given is not in the legal range for the parameter. %d`

## pseudocode

```c
__int64 __fastcall ReadPPPKeyValues(HKEY hKey)
{
  __int64 i; // rsi
  const CHAR *v3; // rdx
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  CHAR *v6; // r8
  __int64 result; // rax
  int v8; // eax
  int v9; // ecx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  LPSTR plpszSubStringArray; // [rsp+38h] [rbp-C8h] BYREF
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v13 = 0;
  Type = 0;
  memset_0(v14, 0, sizeof(v14));
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v3 = (&PppRegParams)[3 * i];
    if ( !v3 )
      break;
    cbData = 4;
    v4 = RegQueryValueExA(hKey, v3, 0, &Type, (LPBYTE)(&PppRegParams)[3 * i + 1], &cbData);
    v5 = v4;
    if ( v4 )
    {
      if ( v4 != 2 )
      {
        if ( dword_18004DA20 )
          RouterLogEventA(hLogHandle, 1u, 0x4E22u, 0, 0, v4);
        if ( byte_18004DF33 < 0 )
        {
          LOWORD(v13) = 0;
          FormatRRASErrorString((wchar_t *)&v13, L"Cannot access registry key values %d.", v5);
          if ( byte_18004DF33 < 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v13);
        }
        return 1015;
      }
      goto LABEL_13;
    }
    if ( Type != 4 || *(_DWORD *)(&PppRegParams)[3 * i + 1] > LODWORD((&PppRegParams)[3 * i + 2]) )
    {
      v6 = (&PppRegParams)[3 * i];
      plpszSubStringArray = v6;
      if ( (unsigned int)dword_18004DA20 > 1 )
      {
        RouterLogEventA(hLogHandle, 2u, 0x4E85u, 1u, &plpszSubStringArray, 0);
        v6 = plpszSubStringArray;
      }
      if ( byte_18004DF33 < 0 )
      {
        LOWORD(v13) = 0;
        FormatRRASErrorString(
          (wchar_t *)&v13,
          L"Using the default value for Registry parameter %hs because the value given is not in the legal range for the parameter. %d",
          v6,
          v5);
        if ( byte_18004DF33 < 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v13);
      }
LABEL_13:
      *(_DWORD *)(&PppRegParams)[3 * i + 1] = *((_DWORD *)&PppRegParams + 6 * i + 5);
      continue;
    }
  }
  v8 = dword_18004D9F4;
  if ( !dword_18004D9F4 )
    v8 = 2;
  if ( !dword_18004D9FC )
    dword_18004D9FC = 5;
  v9 = dword_18004D9F8;
  if ( !dword_18004D9F8 )
    v9 = 10;
  if ( !dword_18004DA00 )
    dword_18004DA00 = 5;
  dword_18004D9F4 = v8 - 1;
  result = 0;
  dword_18004D9F8 = v9 - 1;
  return result;
}

```

## disassembly

```asm
0x180005698  push    rbp
0x18000569a  push    rbx
0x18000569b  push    rsi
0x18000569c  push    rdi
0x18000569d  push    r12
0x18000569f  push    r14
0x1800056a1  lea     rbp, [rsp-758h]
0x1800056a9  sub     rsp, 858h
0x1800056b0  mov     rax, cs:__security_cookie
0x1800056b7  xor     rax, rsp
0x1800056ba  mov     [rbp+780h+var_40], rax
0x1800056c1  mov     r14, rcx
0x1800056c4  xor     eax, eax
0x1800056c6  xor     ebx, ebx
0x1800056c8  mov     [rsp+880h+var_840], eax
0x1800056cc  lea     rcx, [rsp+880h+var_83C]; void *
0x1800056d1  mov     [rsp+880h+Type], ebx
0x1800056d5  xor     edx, edx; Val
0x1800056d7  mov     r8d, 7FCh; Size
0x1800056dd  call    memset_0
0x1800056e2  xor     esi, esi
0x1800056e4  lea     r12, PppRegParams
0x1800056eb  lea     rdi, [rsi+rsi*2]
0x1800056ef  mov     rdx, [r12+rdi*8]; lpValueName
0x1800056f3  test    rdx, rdx
0x1800056f6  jz      loc_18000587E
0x1800056fc  lea     rax, [rsp+880h+cbData]
0x180005701  mov     [rsp+880h+cbData], 4
0x180005709  mov     [rsp+880h+lpcbData], rax; lpcbData
0x18000570e  lea     r9, [rsp+880h+Type]; lpType
0x180005713  mov     rax, [r12+rdi*8+8]
0x180005718  xor     r8d, r8d; lpReserved
0x18000571b  mov     rcx, r14; hKey
0x18000571e  mov     [rsp+880h+lpData], rax; lpData
0x180005723  call    cs:__imp_RegQueryValueExA
0x18000572a  nop     dword ptr [rax+rax+00h]
0x18000572f  mov     ebx, eax
0x180005731  test    eax, eax
0x180005733  jz      short loc_180005745
0x180005735  cmp     eax, 2
0x180005738  jnz     loc_180005801
0x18000573e  xor     ebx, ebx
0x180005740  jmp     loc_1800057EE
0x180005745  cmp     [rsp+880h+Type], 4
0x18000574a  jnz     short loc_18000575E
0x18000574c  mov     rcx, [r12+rdi*8+8]
0x180005751  mov     eax, [r12+rdi*8+10h]
0x180005756  cmp     [rcx], eax
0x180005758  jbe     loc_1800057FA
0x18000575e  cmp     cs:dword_18004DA20, 1
0x180005765  mov     r8, [r12+rdi*8]
0x180005769  mov     [rsp+880h+plpszSubStringArray], r8
0x18000576e  jbe     short loc_1800057A9
0x180005770  mov     rcx, cs:hLogHandle; hLogHandle
0x180005777  lea     rax, [rsp+880h+plpszSubStringArray]
0x18000577c  mov     edx, 2; dwEventType
0x180005781  mov     dword ptr [rsp+880h+lpcbData], 0; dwErrorCode
0x180005789  mov     r8d, 4E85h; dwMessageId
0x18000578f  mov     [rsp+880h+lpData], rax; plpszSubStringArray
0x180005794  lea     r9d, [rdx-1]; dwSubStringCount
0x180005798  call    cs:__imp_RouterLogEventA
0x18000579f  nop     dword ptr [rax+rax+00h]
0x1800057a4  mov     r8, [rsp+880h+plpszSubStringArray]
0x1800057a9  cmp     cs:byte_18004DF33, 0
0x1800057b0  jge     short loc_1800057EE
0x1800057b2  xor     eax, eax
0x1800057b4  lea     rdx, aUsingTheDefaul; "Using the default value for Registry pa"...
0x1800057bb  mov     r9d, ebx
0x1800057be  mov     word ptr [rsp+880h+var_840], ax
0x1800057c3  lea     rcx, [rsp+880h+var_840]
0x1800057c8  call    FormatRRASErrorString
0x1800057cd  cmp     cs:byte_18004DF33, 0
0x1800057d4  jge     short loc_1800057EE
0x1800057d6  lea     r8, [rsp+880h+var_840]
0x1800057db  lea     rdx, RasPppTraceError
0x1800057e2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800057e9  call    McTemplateU0z_EventWriteTransfer
0x1800057ee  mov     rcx, [r12+rdi*8+8]
0x1800057f3  mov     eax, [r12+rdi*8+14h]
0x1800057f8  mov     [rcx], eax
0x1800057fa  inc     esi
0x1800057fc  jmp     loc_1800056EB
0x180005801  cmp     cs:dword_18004DA20, 0
0x180005808  jbe     short loc_180005837
0x18000580a  mov     rcx, cs:hLogHandle; hLogHandle
0x180005811  xor     r9d, r9d; dwSubStringCount
0x180005814  mov     dword ptr [rsp+880h+lpcbData], ebx; dwErrorCode
0x180005818  mov     r8d, 4E22h; dwMessageId
0x18000581e  mov     [rsp+880h+lpData], 0; plpszSubStringArray
0x180005827  lea     edx, [r9+1]; dwEventType
0x18000582b  call    cs:__imp_RouterLogEventA
0x180005832  nop     dword ptr [rax+rax+00h]
0x180005837  cmp     cs:byte_18004DF33, 0
0x18000583e  jge     short loc_180005882
0x180005840  xor     eax, eax
0x180005842  lea     rdx, aCannotAccessRe; "Cannot access registry key values %d."
0x180005849  mov     r8d, ebx
0x18000584c  mov     word ptr [rsp+880h+var_840], ax
0x180005851  lea     rcx, [rsp+880h+var_840]
0x180005856  call    FormatRRASErrorString
0x18000585b  cmp     cs:byte_18004DF33, 0
0x180005862  jge     short loc_180005882
0x180005864  lea     r8, [rsp+880h+var_840]
0x180005869  lea     rdx, RasPppTraceError
0x180005870  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005877  call    McTemplateU0z_EventWriteTransfer
0x18000587c  jmp     short loc_180005882
0x18000587e  test    ebx, ebx
0x180005880  jz      short loc_180005889
0x180005882  mov     eax, 3F7h
0x180005887  jmp     short loc_1800058DF
0x180005889  mov     eax, cs:dword_18004D9F4
0x18000588f  test    eax, eax
0x180005891  jnz     short loc_180005898
0x180005893  mov     eax, 2
0x180005898  cmp     cs:dword_18004D9FC, 0
0x18000589f  mov     edx, 5
0x1800058a4  jnz     short loc_1800058AC
0x1800058a6  mov     cs:dword_18004D9FC, edx
0x1800058ac  mov     ecx, cs:dword_18004D9F8
0x1800058b2  test    ecx, ecx
0x1800058b4  jnz     short loc_1800058BB
0x1800058b6  mov     ecx, 0Ah
0x1800058bb  cmp     cs:dword_18004DA00, 0
0x1800058c2  jnz     short loc_1800058CA
0x1800058c4  mov     cs:dword_18004DA00, edx
0x1800058ca  or      edx, 0FFFFFFFFh
0x1800058cd  add     eax, edx
0x1800058cf  add     ecx, edx
0x1800058d1  mov     cs:dword_18004D9F4, eax
0x1800058d7  xor     eax, eax
0x1800058d9  mov     cs:dword_18004D9F8, ecx
0x1800058df  mov     rcx, [rbp+780h+var_40]
0x1800058e6  xor     rcx, rsp; StackCookie
0x1800058e9  call    __security_check_cookie
0x1800058ee  add     rsp, 858h
0x1800058f5  pop     r14
0x1800058f7  pop     r12
0x1800058f9  pop     rdi
0x1800058fa  pop     rsi
0x1800058fb  pop     rbx
0x1800058fc  pop     rbp
0x1800058fd  retn
```
