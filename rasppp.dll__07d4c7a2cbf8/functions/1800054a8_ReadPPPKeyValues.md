# ReadPPPKeyValues

- ea: `0x1800054a8`
- end: `0x1800056fc`
- name: `ReadPPPKeyValues`
- size: `596`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005704`
- `0x180014bb0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x1800054a8`
- `0x18002a138`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180005533`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180005533`
- `rtutils!RouterLogEventA` at `0x1800055a2`
- `rtutils!RouterLogEventA` at `0x18000562f`
- `rtutils!RouterLogEventA` at `0x1800055a2`
- `rtutils!RouterLogEventA` at `0x18000562f`

## string_xrefs

- `0x180005640`: `Cannot access registry key values %d.`
- `0x1800055b8`: `Using the default value for Registry parameter %hs because the value given is not in the legal range for the parameter. %d`

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
        if ( dword_18004CA20 )
          RouterLogEventA(hLogHandle, 1u, 0x4E22u, 0, 0, v4);
        if ( byte_18004CF33 < 0 )
        {
          LOWORD(v13) = 0;
          FormatRRASErrorString(&v13, L"Cannot access registry key values %d.", v5);
          if ( byte_18004CF33 < 0 )
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
      if ( (unsigned int)dword_18004CA20 > 1 )
      {
        RouterLogEventA(hLogHandle, 2u, 0x4E85u, 1u, &plpszSubStringArray, 0);
        v6 = plpszSubStringArray;
      }
      if ( byte_18004CF33 < 0 )
      {
        LOWORD(v13) = 0;
        FormatRRASErrorString(
          &v13,
          L"Using the default value for Registry parameter %hs because the value given is not in the legal range for the parameter. %d",
          v6,
          v5);
        if ( byte_18004CF33 < 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v13);
      }
LABEL_13:
      *(_DWORD *)(&PppRegParams)[3 * i + 1] = *((_DWORD *)&PppRegParams + 6 * i + 5);
      continue;
    }
  }
  v8 = dword_18004C9F4;
  if ( !dword_18004C9F4 )
    v8 = 2;
  if ( !dword_18004C9FC )
    dword_18004C9FC = 5;
  v9 = dword_18004C9F8;
  if ( !dword_18004C9F8 )
    v9 = 10;
  if ( !dword_18004CA00 )
    dword_18004CA00 = 5;
  dword_18004C9F4 = v8 - 1;
  result = 0;
  dword_18004C9F8 = v9 - 1;
  return result;
}

```

## disassembly

```asm
0x1800054a8  push    rbp
0x1800054aa  push    rbx
0x1800054ab  push    rsi
0x1800054ac  push    rdi
0x1800054ad  push    r12
0x1800054af  push    r14
0x1800054b1  lea     rbp, [rsp-758h]
0x1800054b9  sub     rsp, 858h
0x1800054c0  mov     rax, cs:__security_cookie
0x1800054c7  xor     rax, rsp
0x1800054ca  mov     [rbp+780h+var_40], rax
0x1800054d1  mov     r14, rcx
0x1800054d4  xor     eax, eax
0x1800054d6  xor     ebx, ebx
0x1800054d8  mov     [rsp+880h+var_840], eax
0x1800054dc  lea     rcx, [rsp+880h+var_83C]; void *
0x1800054e1  mov     [rsp+880h+Type], ebx
0x1800054e5  xor     edx, edx; Val
0x1800054e7  mov     r8d, 7FCh; Size
0x1800054ed  call    memset_0
0x1800054f2  xor     esi, esi
0x1800054f4  lea     r12, PppRegParams
0x1800054fb  lea     rdi, [rsi+rsi*2]
0x1800054ff  mov     rdx, [r12+rdi*8]; lpValueName
0x180005503  test    rdx, rdx
0x180005506  jz      loc_18000567C
0x18000550c  lea     rax, [rsp+880h+cbData]
0x180005511  mov     [rsp+880h+cbData], 4
0x180005519  mov     [rsp+880h+lpcbData], rax; lpcbData
0x18000551e  lea     r9, [rsp+880h+Type]; lpType
0x180005523  mov     rax, [r12+rdi*8+8]
0x180005528  xor     r8d, r8d; lpReserved
0x18000552b  mov     rcx, r14; hKey
0x18000552e  mov     [rsp+880h+lpData], rax; lpData
0x180005533  call    cs:__imp_RegQueryValueExA
0x180005539  mov     ebx, eax
0x18000553b  test    eax, eax
0x18000553d  jz      short loc_18000554F
0x18000553f  cmp     eax, 2
0x180005542  jnz     loc_180005605
0x180005548  xor     ebx, ebx
0x18000554a  jmp     loc_1800055F2
0x18000554f  cmp     [rsp+880h+Type], 4
0x180005554  jnz     short loc_180005568
0x180005556  mov     rcx, [r12+rdi*8+8]
0x18000555b  mov     eax, [r12+rdi*8+10h]
0x180005560  cmp     [rcx], eax
0x180005562  jbe     loc_1800055FE
0x180005568  cmp     cs:dword_18004CA20, 1
0x18000556f  mov     r8, [r12+rdi*8]
0x180005573  mov     [rsp+880h+plpszSubStringArray], r8
0x180005578  jbe     short loc_1800055AD
0x18000557a  mov     rcx, cs:hLogHandle; hLogHandle
0x180005581  lea     rax, [rsp+880h+plpszSubStringArray]
0x180005586  mov     edx, 2; dwEventType
0x18000558b  mov     dword ptr [rsp+880h+lpcbData], 0; dwErrorCode
0x180005593  mov     r8d, 4E85h; dwMessageId
0x180005599  mov     [rsp+880h+lpData], rax; plpszSubStringArray
0x18000559e  lea     r9d, [rdx-1]; dwSubStringCount
0x1800055a2  call    cs:__imp_RouterLogEventA
0x1800055a8  mov     r8, [rsp+880h+plpszSubStringArray]
0x1800055ad  cmp     cs:byte_18004CF33, 0
0x1800055b4  jge     short loc_1800055F2
0x1800055b6  xor     eax, eax
0x1800055b8  lea     rdx, aUsingTheDefaul; "Using the default value for Registry pa"...
0x1800055bf  mov     r9d, ebx
0x1800055c2  mov     word ptr [rsp+880h+var_840], ax
0x1800055c7  lea     rcx, [rsp+880h+var_840]
0x1800055cc  call    FormatRRASErrorString
0x1800055d1  cmp     cs:byte_18004CF33, 0
0x1800055d8  jge     short loc_1800055F2
0x1800055da  lea     r8, [rsp+880h+var_840]
0x1800055df  lea     rdx, RasPppTraceError
0x1800055e6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800055ed  call    McTemplateU0z_EventWriteTransfer
0x1800055f2  mov     rcx, [r12+rdi*8+8]
0x1800055f7  mov     eax, [r12+rdi*8+14h]
0x1800055fc  mov     [rcx], eax
0x1800055fe  inc     esi
0x180005600  jmp     loc_1800054FB
0x180005605  cmp     cs:dword_18004CA20, 0
0x18000560c  jbe     short loc_180005635
0x18000560e  mov     rcx, cs:hLogHandle; hLogHandle
0x180005615  xor     r9d, r9d; dwSubStringCount
0x180005618  mov     dword ptr [rsp+880h+lpcbData], ebx; dwErrorCode
0x18000561c  mov     r8d, 4E22h; dwMessageId
0x180005622  mov     [rsp+880h+lpData], 0; plpszSubStringArray
0x18000562b  lea     edx, [r9+1]; dwEventType
0x18000562f  call    cs:__imp_RouterLogEventA
0x180005635  cmp     cs:byte_18004CF33, 0
0x18000563c  jge     short loc_180005680
0x18000563e  xor     eax, eax
0x180005640  lea     rdx, aCannotAccessRe; "Cannot access registry key values %d."
0x180005647  mov     r8d, ebx
0x18000564a  mov     word ptr [rsp+880h+var_840], ax
0x18000564f  lea     rcx, [rsp+880h+var_840]
0x180005654  call    FormatRRASErrorString
0x180005659  cmp     cs:byte_18004CF33, 0
0x180005660  jge     short loc_180005680
0x180005662  lea     r8, [rsp+880h+var_840]
0x180005667  lea     rdx, RasPppTraceError
0x18000566e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180005675  call    McTemplateU0z_EventWriteTransfer
0x18000567a  jmp     short loc_180005680
0x18000567c  test    ebx, ebx
0x18000567e  jz      short loc_180005687
0x180005680  mov     eax, 3F7h
0x180005685  jmp     short loc_1800056DD
0x180005687  mov     eax, cs:dword_18004C9F4
0x18000568d  test    eax, eax
0x18000568f  jnz     short loc_180005696
0x180005691  mov     eax, 2
0x180005696  cmp     cs:dword_18004C9FC, 0
0x18000569d  mov     edx, 5
0x1800056a2  jnz     short loc_1800056AA
0x1800056a4  mov     cs:dword_18004C9FC, edx
0x1800056aa  mov     ecx, cs:dword_18004C9F8
0x1800056b0  test    ecx, ecx
0x1800056b2  jnz     short loc_1800056B9
0x1800056b4  mov     ecx, 0Ah
0x1800056b9  cmp     cs:dword_18004CA00, 0
0x1800056c0  jnz     short loc_1800056C8
0x1800056c2  mov     cs:dword_18004CA00, edx
0x1800056c8  or      edx, 0FFFFFFFFh
0x1800056cb  add     eax, edx
0x1800056cd  add     ecx, edx
0x1800056cf  mov     cs:dword_18004C9F4, eax
0x1800056d5  xor     eax, eax
0x1800056d7  mov     cs:dword_18004C9F8, ecx
0x1800056dd  mov     rcx, [rbp+780h+var_40]
0x1800056e4  xor     rcx, rsp; StackCookie
0x1800056e7  call    __security_check_cookie
0x1800056ec  add     rsp, 858h
0x1800056f3  pop     r14
0x1800056f5  pop     r12
0x1800056f7  pop     rdi
0x1800056f8  pop     rsi
0x1800056f9  pop     rbx
0x1800056fa  pop     rbp
0x1800056fb  retn
```
