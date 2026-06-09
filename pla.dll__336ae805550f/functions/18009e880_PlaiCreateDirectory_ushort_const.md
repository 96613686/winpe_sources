# PlaiCreateDirectory(ushort const *)

- ea: `0x18009e880`
- end: `0x18009ed46`
- name: `?PlaiCreateDirectory@@YAJPEBG@Z`
- size: `1222`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bb9f0`
- `0x1800cb2c0`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x1800123d4`
- `0x180012ef0`
- `0x18002b3a0`
- `0x18009e880`
- `0x1800db5d0`
- `0x18013aee0`

## import_xrefs

- `msvcrt!wcschr` at `0x18009eb6a`
- `msvcrt!wcschr` at `0x18009eb7c`
- `msvcrt!wcschr` at `0x18009ec55`
- `msvcrt!wcschr` at `0x18009eb6a`
- `msvcrt!wcschr` at `0x18009eb7c`
- `msvcrt!wcschr` at `0x18009ec55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ec7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ec7c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18009ec72`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18009ec72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ed1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009ed1b`

## string_xrefs

- `0x18009e9b0`: `PlaiCreateDirectory`
- `0x18009ea70`: `PlaiCreateDirectory`
- `0x18009ec0c`: `PlaiCreateDirectory`

## pseudocode

```c
__int64 __fastcall PlaiCreateDirectory(const unsigned __int16 *a1)
{
  __int64 v2; // rdi
  unsigned __int64 v3; // rax
  unsigned __int16 *v4; // r14
  unsigned int v5; // ebx
  int v6; // eax
  unsigned __int64 v7; // rdx
  int v8; // eax
  wchar_t *v9; // rax
  wchar_t *v10; // rsi
  wchar_t *v11; // rax
  DWORD LastError; // eax
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+70h] [rbp-90h] BYREF
  int v17; // [rsp+78h] [rbp-88h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v19[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v20[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v21[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v22[64]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v23[64]; // [rsp+2A0h] [rbp+1A0h] BYREF

  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( !a1 )
    goto LABEL_51;
  if ( !*a1 )
    goto LABEL_51;
  v2 = -1;
  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  if ( v3 < 4 )
  {
LABEL_51:
    v5 = 0;
    goto LABEL_52;
  }
  v4 = (unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, byte_180147320, v15);
  if ( v4 )
  {
    v6 = PlaiCreateSecurityDescriptor(3u, &SecurityAttributes);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v8 = PlaiExpandVariables(v4, v7, a1);
      v5 = v8;
      if ( v8 >= 0 )
      {
        if ( *v4 != 92 || v4[1] != 92 )
        {
          v10 = v4 + 2;
          goto LABEL_38;
        }
        v9 = wcschr(v4 + 2, 0x5Cu);
        if ( v9 && (v10 = wcschr(v9 + 1, 0x5Cu)) != 0 )
        {
          while ( 1 )
          {
LABEL_38:
            v11 = wcschr(v10 + 1, 0x5Cu);
            v10 = v11;
            if ( !v11 )
            {
              v5 = 0;
              goto LABEL_50;
            }
            *v11 = 0;
            if ( !CreateDirectoryW(v4, &SecurityAttributes) )
            {
              LastError = GetLastError();
              v13 = PlaiHResultFromWin32(LastError);
              v5 = v13;
              if ( v13 < 0 && v13 != -2147024713 )
                break;
            }
            *v10 = 92;
          }
          v17 = 0;
          v16 = v13;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_50;
          }
          PlaiWhoAmI(v23, 0x4000000000000800uLL);
          do
            ++v2;
          while ( v23[v2] );
        }
        else
        {
          v5 = -2147024735;
          v16 = -2147024735;
          v17 = 0;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_50;
          }
          PlaiWhoAmI(v22, 0x4000000000000800uLL);
          do
            ++v2;
          while ( v22[v2] );
        }
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v16, 4, byte_180147320, 1, &v17, 4);
LABEL_50:
        PlaiFree(v4, 1);
        goto LABEL_52;
      }
      v17 = 0;
      v16 = v8;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_50;
      }
      PlaiWhoAmI(v21, 0x4000000000000800uLL);
      do
        ++v2;
      while ( v21[v2] );
    }
    else
    {
      v17 = 0;
      v16 = v6;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_50;
      }
      PlaiWhoAmI(v20, 0x4000000000000800uLL);
      do
        ++v2;
      while ( v20[v2] );
    }
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v16, 4, byte_180147320, 1, &v17, 4);
    goto LABEL_50;
  }
  v5 = -2147024882;
  v17 = -2147024882;
  v16 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v19, 0x4000000000000800uLL);
    do
      ++v2;
    while ( v19[v2] );
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v17, 4, byte_180147320, 1, &v16, 4);
  }
LABEL_52:
  if ( SecurityAttributes.lpSecurityDescriptor )
    LocalFree(SecurityAttributes.lpSecurityDescriptor);
  return v5;
}

```

## disassembly

```asm
0x18009e880  push    rbp
0x18009e882  push    rbx
0x18009e883  push    rsi
0x18009e884  push    rdi
0x18009e885  push    r12
0x18009e887  push    r13
0x18009e889  push    r14
0x18009e88b  push    r15
0x18009e88d  lea     rbp, [rsp-238h]
0x18009e895  sub     rsp, 338h
0x18009e89c  mov     rax, cs:__security_cookie
0x18009e8a3  xor     rax, rsp
0x18009e8a6  mov     [rbp+270h+var_50], rax
0x18009e8ad  xor     r15d, r15d
0x18009e8b0  xorps   xmm0, xmm0
0x18009e8b3  mov     qword ptr [rbp+270h+SecurityAttributes.nLength], r15
0x18009e8b7  mov     rsi, rcx
0x18009e8ba  movdqu  xmmword ptr [rbp+270h+SecurityAttributes.lpSecurityDescriptor], xmm0
0x18009e8bf  test    rcx, rcx
0x18009e8c2  jz      loc_18009ED0F
0x18009e8c8  cmp     r15w, [rcx]
0x18009e8cc  jz      loc_18009ED0F
0x18009e8d2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18009e8d6  mov     rax, rdi
0x18009e8d9  inc     rax
0x18009e8dc  cmp     [rcx+rax*2], r15w
0x18009e8e1  jnz     short loc_18009E8D9
0x18009e8e3  mov     r13d, 4
0x18009e8e9  cmp     rax, r13
0x18009e8ec  jb      loc_18009ED0F
0x18009e8f2  lea     r12, byte_180147320
0x18009e8f9  xor     r8d, r8d; int
0x18009e8fc  mov     r9, r12; char *
0x18009e8ff  lea     edx, [r13-3]; int
0x18009e903  mov     ecx, 800h; dwBytes
0x18009e908  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x18009e90d  mov     r14, rax
0x18009e910  test    rax, rax
0x18009e913  jnz     loc_18009E9E8
0x18009e919  cmp     dword ptr cs:xmmword_180169738, r15d
0x18009e920  mov     ebx, 8007000Eh
0x18009e925  mov     [rsp+370h+var_2F8], ebx
0x18009e929  mov     [rsp+370h+var_300], r15d
0x18009e92e  jz      loc_18009ED12
0x18009e934  mov     rdx, 4000000000000800h; unsigned __int64
0x18009e93e  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009e945  jz      loc_18009ED12
0x18009e94b  mov     rax, cs:qword_180169748
0x18009e952  and     rax, rdx
0x18009e955  cmp     cs:qword_180169748, rax
0x18009e95c  jnz     loc_18009ED12
0x18009e962  lea     rcx, [rbp+270h+var_2D0]; unsigned __int16 *
0x18009e966  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009e96b  lea     rax, [rbp+270h+var_2D0]
0x18009e96f  inc     rdi
0x18009e972  cmp     [rax+rdi*2], r15w
0x18009e977  jnz     short loc_18009E96F
0x18009e979  lea     rax, [rbp+270h+var_2D0]
0x18009e97d  mov     r8d, 5
0x18009e983  lea     ecx, [rdi+rdi]
0x18009e986  add     rcx, 2
0x18009e98a  lea     r9, [rsp+370h+var_2F8]
0x18009e98f  mov     [rsp+370h+var_310], rcx
0x18009e994  lea     rdx, PLA_EVENT_ERROR
0x18009e99b  mov     [rsp+370h+var_318], rax
0x18009e9a0  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18009e9a7  mov     [rsp+370h+var_320], 14h
0x18009e9b0  lea     rax, aPlaicreatedire; "PlaiCreateDirectory"
0x18009e9b7  mov     [rsp+370h+var_328], rax
0x18009e9bc  lea     rax, [rsp+370h+var_300]
0x18009e9c1  mov     [rsp+370h+var_330], r13
0x18009e9c6  mov     [rsp+370h+var_338], rax
0x18009e9cb  mov     [rsp+370h+var_340], 1
0x18009e9d4  mov     [rsp+370h+var_348], r12
0x18009e9d9  mov     [rsp+370h+var_350], r13
0x18009e9de  call    EventingWriteEvent
0x18009e9e3  jmp     loc_18009ED12
0x18009e9e8  lea     rdx, [rbp+270h+SecurityAttributes]; struct _SECURITY_ATTRIBUTES *
0x18009e9ec  mov     ecx, 3; unsigned int
0x18009e9f1  call    ?PlaiCreateSecurityDescriptor@@YAJKPEAU_SECURITY_ATTRIBUTES@@@Z; PlaiCreateSecurityDescriptor(ulong,_SECURITY_ATTRIBUTES *)
0x18009e9f6  mov     ebx, eax
0x18009e9f8  test    eax, eax
0x18009e9fa  jns     loc_18009EACA
0x18009ea00  cmp     dword ptr cs:xmmword_180169738, r15d
0x18009ea07  mov     [rsp+370h+var_2F8], r15d
0x18009ea0c  mov     [rsp+370h+var_300], eax
0x18009ea10  jz      loc_18009ED00
0x18009ea16  mov     rdx, 4000000000000800h; unsigned __int64
0x18009ea20  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009ea27  jz      loc_18009ED00
0x18009ea2d  mov     rax, cs:qword_180169748
0x18009ea34  and     rax, rdx
0x18009ea37  cmp     cs:qword_180169748, rax
0x18009ea3e  jnz     loc_18009ED00
0x18009ea44  lea     rcx, [rbp+270h+var_250]; unsigned __int16 *
0x18009ea48  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009ea4d  lea     rax, [rbp+270h+var_250]
0x18009ea51  inc     rdi
0x18009ea54  cmp     [rax+rdi*2], r15w
0x18009ea59  jnz     short loc_18009EA51
0x18009ea5b  lea     rax, [rbp+270h+var_250]
0x18009ea5f  lea     ecx, [rdi+rdi]
0x18009ea62  add     rcx, 2
0x18009ea66  mov     [rsp+370h+var_310], rcx
0x18009ea6b  mov     [rsp+370h+var_318], rax
0x18009ea70  lea     rax, aPlaicreatedire; "PlaiCreateDirectory"
0x18009ea77  mov     [rsp+370h+var_320], 14h
0x18009ea80  mov     [rsp+370h+var_328], rax
0x18009ea85  lea     rax, [rsp+370h+var_2F8]
0x18009ea8a  mov     [rsp+370h+var_330], r13
0x18009ea8f  mov     [rsp+370h+var_338], rax
0x18009ea94  mov     [rsp+370h+var_340], 1
0x18009ea9d  mov     [rsp+370h+var_348], r12
0x18009eaa2  lea     r9, [rsp+370h+var_300]
0x18009eaa7  mov     [rsp+370h+var_350], r13
0x18009eaac  mov     r8d, 5
0x18009eab2  lea     rdx, PLA_EVENT_ERROR
0x18009eab9  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18009eac0  call    EventingWriteEvent
0x18009eac5  jmp     loc_18009ED00
0x18009eaca  mov     r8, rsi; unsigned __int16 *
0x18009eacd  mov     rcx, r14; unsigned __int16 *
0x18009ead0  call    ?PlaiExpandVariables@@YAJPEAG_KPEBG@Z; PlaiExpandVariables(ushort *,unsigned __int64,ushort const *)
0x18009ead5  mov     ebx, eax
0x18009ead7  test    eax, eax
0x18009ead9  jns     short loc_18009EB48
0x18009eadb  cmp     dword ptr cs:xmmword_180169738, r15d
0x18009eae2  mov     [rsp+370h+var_2F8], r15d
0x18009eae7  mov     [rsp+370h+var_300], eax
0x18009eaeb  jz      loc_18009ED00
0x18009eaf1  mov     rdx, 4000000000000800h; unsigned __int64
0x18009eafb  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009eb02  jz      loc_18009ED00
0x18009eb08  mov     rax, cs:qword_180169748
0x18009eb0f  and     rax, rdx
0x18009eb12  cmp     cs:qword_180169748, rax
0x18009eb19  jnz     loc_18009ED00
0x18009eb1f  lea     rcx, [rbp+270h+var_1D0]; unsigned __int16 *
0x18009eb26  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009eb2b  lea     rax, [rbp+270h+var_1D0]
0x18009eb32  inc     rdi
0x18009eb35  cmp     [rax+rdi*2], r15w
0x18009eb3a  jnz     short loc_18009EB32
0x18009eb3c  lea     rax, [rbp+270h+var_1D0]
0x18009eb43  jmp     loc_18009EA5F
0x18009eb48  mov     r12d, 5Ch ; '\'
0x18009eb4e  cmp     r12w, [r14]
0x18009eb52  jnz     loc_18009EC4A
0x18009eb58  cmp     r12w, [r14+2]
0x18009eb5d  jnz     loc_18009EC4A
0x18009eb63  mov     edx, r12d; Ch
0x18009eb66  lea     rcx, [r14+4]; Str
0x18009eb6a  call    cs:__imp_wcschr
0x18009eb70  test    rax, rax
0x18009eb73  jz      short loc_18009EB8E
0x18009eb75  mov     edx, r12d; Ch
0x18009eb78  lea     rcx, [rax+2]; Str
0x18009eb7c  call    cs:__imp_wcschr
0x18009eb82  mov     rsi, rax
0x18009eb85  test    rax, rax
0x18009eb88  jnz     loc_18009EC4E
0x18009eb8e  cmp     dword ptr cs:xmmword_180169738, r15d
0x18009eb95  mov     ebx, 800700A1h
0x18009eb9a  mov     [rsp+370h+var_300], ebx
0x18009eb9e  mov     [rsp+370h+var_2F8], r15d
0x18009eba3  jz      loc_18009ED00
0x18009eba9  mov     rdx, 4000000000000800h; unsigned __int64
0x18009ebb3  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009ebba  jz      loc_18009ED00
0x18009ebc0  mov     rax, cs:qword_180169748
0x18009ebc7  and     rax, rdx
0x18009ebca  cmp     cs:qword_180169748, rax
0x18009ebd1  jnz     loc_18009ED00
0x18009ebd7  lea     rcx, [rbp+270h+var_150]; unsigned __int16 *
0x18009ebde  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009ebe3  lea     rax, [rbp+270h+var_150]
0x18009ebea  inc     rdi
0x18009ebed  cmp     [rax+rdi*2], r15w
0x18009ebf2  jnz     short loc_18009EBEA
0x18009ebf4  lea     rax, [rbp+270h+var_150]
0x18009ebfb  lea     ecx, [rdi+rdi]
0x18009ebfe  add     rcx, 2
0x18009ec02  mov     [rsp+370h+var_310], rcx
0x18009ec07  mov     [rsp+370h+var_318], rax
0x18009ec0c  lea     rax, aPlaicreatedire; "PlaiCreateDirectory"
0x18009ec13  mov     [rsp+370h+var_320], 14h
0x18009ec1c  mov     [rsp+370h+var_328], rax
0x18009ec21  lea     rax, [rsp+370h+var_2F8]
0x18009ec26  mov     [rsp+370h+var_330], r13
0x18009ec2b  mov     [rsp+370h+var_338], rax
0x18009ec30  lea     rax, byte_180147320
0x18009ec37  mov     [rsp+370h+var_340], 1
0x18009ec40  mov     [rsp+370h+var_348], rax
0x18009ec45  jmp     loc_18009EAA2
0x18009ec4a  lea     rsi, [r14+4]
0x18009ec4e  mov     edx, r12d; Ch
0x18009ec51  lea     rcx, [rsi+2]; Str
0x18009ec55  call    cs:__imp_wcschr
0x18009ec5b  mov     rsi, rax
0x18009ec5e  test    rax, rax
0x18009ec61  jz      loc_18009ECFD
0x18009ec67  lea     rdx, [rbp+270h+SecurityAttributes]; lpSecurityAttributes
0x18009ec6b  mov     [rax], r15w
0x18009ec6f  mov     rcx, r14; lpPathName
0x18009ec72  call    cs:__imp_CreateDirectoryW
0x18009ec78  test    eax, eax
0x18009ec7a  jnz     short loc_18009EC96
0x18009ec7c  call    cs:__imp_GetLastError
0x18009ec82  mov     ecx, eax; unsigned int
0x18009ec84  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18009ec89  mov     ebx, eax
0x18009ec8b  test    eax, eax
0x18009ec8d  jns     short loc_18009EC96
0x18009ec8f  cmp     eax, 800700B7h
0x18009ec94  jnz     short loc_18009EC9C
0x18009ec96  mov     [rsi], r12w
0x18009ec9a  jmp     short loc_18009EC4E
0x18009ec9c  cmp     dword ptr cs:xmmword_180169738, r15d
0x18009eca3  mov     [rsp+370h+var_2F8], r15d
0x18009eca8  mov     [rsp+370h+var_300], eax
0x18009ecac  jz      short loc_18009ED00
0x18009ecae  mov     rdx, 4000000000000800h; unsigned __int64
0x18009ecb8  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009ecbf  jz      short loc_18009ED00
0x18009ecc1  mov     rax, cs:qword_180169748
0x18009ecc8  and     rax, rdx
0x18009eccb  cmp     cs:qword_180169748, rax
0x18009ecd2  jnz     short loc_18009ED00
0x18009ecd4  lea     rcx, [rbp+270h+var_D0]; unsigned __int16 *
0x18009ecdb  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009ece0  lea     rax, [rbp+270h+var_D0]
0x18009ece7  inc     rdi
0x18009ecea  cmp     [rax+rdi*2], r15w
0x18009ecef  jnz     short loc_18009ECE7
0x18009ecf1  lea     rax, [rbp+270h+var_D0]
0x18009ecf8  jmp     loc_18009EBFB
0x18009ecfd  mov     ebx, r15d
0x18009ed00  mov     edx, 1; int
0x18009ed05  mov     rcx, r14; lpMem
0x18009ed08  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x18009ed0d  jmp     short loc_18009ED12
0x18009ed0f  mov     ebx, r15d
0x18009ed12  mov     rcx, [rbp+270h+SecurityAttributes.lpSecurityDescriptor]; hMem
0x18009ed16  test    rcx, rcx
0x18009ed19  jz      short loc_18009ED21
0x18009ed1b  call    cs:__imp_LocalFree
0x18009ed21  mov     eax, ebx
0x18009ed23  mov     rcx, [rbp+270h+var_50]
0x18009ed2a  xor     rcx, rsp; StackCookie
0x18009ed2d  call    __security_check_cookie
0x18009ed32  add     rsp, 338h
0x18009ed39  pop     r15
0x18009ed3b  pop     r14
0x18009ed3d  pop     r13
0x18009ed3f  pop     r12
0x18009ed41  pop     rdi
0x18009ed42  pop     rsi
0x18009ed43  pop     rbx
0x18009ed44  pop     rbp
0x18009ed45  retn
```
