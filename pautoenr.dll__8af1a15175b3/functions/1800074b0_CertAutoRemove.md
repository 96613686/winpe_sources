# CertAutoRemove

- ea: `0x1800074b0`
- end: `0x180007653`
- name: `CertAutoRemove`
- size: `419`
- prototype: `__int64 __fastcall(int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180004630`
- `0x180005040`
- `0x1800066b4`
- `0x1800074b0`
- `0x180007d20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007560`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000761f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000761f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007556`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007556`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180007538`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180007538`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000756b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000756b`
- `CRYPT32!CertOpenStore` at `0x18000759e`
- `CRYPT32!CertOpenStore` at `0x18000759e`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800075c6`
- `CRYPT32!CertEnumCertificatesInStore` at `0x1800075c6`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x1800075ba`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x1800075ba`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800075b1`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800075b1`
- `CRYPT32!CertCloseStore` at `0x1800075d9`
- `CRYPT32!CertCloseStore` at `0x180007613`
- `CRYPT32!CertCloseStore` at `0x1800075d9`
- `CRYPT32!CertCloseStore` at `0x180007613`

## string_xrefs

- `0x1800075ea`: `SOFTWARE\Microsoft\Cryptography\AutoEnrollment\AEDirectoryCache`
- `0x1800075f6`: `SOFTWARE\Microsoft\Cryptography\CertificateTemplateCache`

## pseudocode

```c
__int64 __fastcall CertAutoRemove(int a1)
{
  int LastError; // ebx
  unsigned int v2; // r10d
  HANDLE v3; // rax
  void *v4; // rdi
  const CERT_CONTEXT *v5; // rbx
  __int64 i; // rsi
  HCERTSTORE v7; // rdi
  const CERT_CONTEXT *v8; // rax
  const CERT_CONTEXT *v9; // rax
  unsigned int v10; // eax
  WCHAR Name[64]; // [rsp+30h] [rbp-98h] BYREF

  if ( a1 == 1 )
  {
    v5 = 0;
    for ( i = 0; i != 3; ++i )
    {
      v7 = CertOpenStore((LPCSTR)0xD, 0, 0, 0x90000u, *(&g_rgStoreInfo + 2 * i));
      if ( v7 )
      {
        while ( 1 )
        {
          v9 = CertEnumCertificatesInStore(v7, v5);
          v5 = v9;
          if ( !v9 )
            break;
          v8 = CertDuplicateCertificateContext(v9);
          CertDeleteCertificateFromStore(v8);
        }
        CertCloseStore(v7, 0);
        v7 = 0;
      }
    }
    LastError = AERemoveRegKey(L"SOFTWARE\\Microsoft\\Cryptography\\AutoEnrollment\\AEDirectoryCache");
    v10 = AERemoveRegKey(L"SOFTWARE\\Microsoft\\Cryptography\\CertificateTemplateCache");
    if ( !LastError )
      LastError = v10;
    if ( v7 )
      CertCloseStore(v7, 0);
  }
  else
  {
    if ( a1 != 2 )
    {
      LastError = 87;
LABEL_23:
      SetLastError(LastError);
      return 0;
    }
    LastError = StringCchCopyW(Name, 0x40u, L"Global\\");
    if ( LastError )
      goto LABEL_23;
    LastError = StringCchCatW(Name, v2, L"AUTOENRL:TriggerMachineEnrollment");
    if ( LastError )
      goto LABEL_23;
    v3 = OpenEventW(2u, 0, Name);
    v4 = v3;
    if ( v3 )
    {
      if ( !SetEvent(v3) )
        LastError = GetLastError();
      CloseHandle(v4);
    }
    else
    {
      LastError = GetLastError();
    }
  }
  if ( LastError )
    goto LABEL_23;
  return 1;
}

```

## disassembly

```asm
0x1800074b0  mov     [rsp+arg_0], rbx
0x1800074b5  mov     [rsp+arg_8], rsi
0x1800074ba  push    rdi
0x1800074bb  sub     rsp, 0C0h
0x1800074c2  mov     rax, cs:__security_cookie
0x1800074c9  xor     rax, rsp
0x1800074cc  mov     [rsp+0C8h+var_18], rax
0x1800074d4  cmp     ecx, 1
0x1800074d7  jz      loc_180007576
0x1800074dd  cmp     ecx, 2
0x1800074e0  jz      short loc_1800074EC
0x1800074e2  mov     ebx, 57h ; 'W'
0x1800074e7  jmp     loc_18000761D
0x1800074ec  mov     r10d, 40h ; '@'
0x1800074f2  lea     r8, aGlobal; "Global\\"
0x1800074f9  mov     edx, r10d; unsigned __int64
0x1800074fc  lea     rcx, [rsp+0C8h+Name]; unsigned __int16 *
0x180007501  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007506  mov     ebx, eax
0x180007508  test    eax, eax
0x18000750a  jnz     loc_18000761D
0x180007510  lea     r8, aAutoenrlTrigge; "AUTOENRL:TriggerMachineEnrollment"
0x180007517  mov     edx, r10d; unsigned __int64
0x18000751a  lea     rcx, [rsp+0C8h+Name]; unsigned __int16 *
0x18000751f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007524  mov     ebx, eax
0x180007526  test    eax, eax
0x180007528  jnz     loc_18000761D
0x18000752e  lea     r8, [rsp+0C8h+Name]; lpName
0x180007533  xor     edx, edx; bInheritHandle
0x180007535  lea     ecx, [rax+2]; dwDesiredAccess
0x180007538  call    cs:__imp_OpenEventW
0x18000753e  mov     rdi, rax
0x180007541  test    rax, rax
0x180007544  jnz     short loc_180007553
0x180007546  call    cs:__imp_GetLastError
0x18000754c  mov     ebx, eax
0x18000754e  jmp     loc_180007619
0x180007553  mov     rcx, rdi; hEvent
0x180007556  call    cs:__imp_SetEvent
0x18000755c  test    eax, eax
0x18000755e  jnz     short loc_180007568
0x180007560  call    cs:__imp_GetLastError
0x180007566  mov     ebx, eax
0x180007568  mov     rcx, rdi; hObject
0x18000756b  call    cs:__imp_CloseHandle
0x180007571  jmp     loc_180007619
0x180007576  xor     ebx, ebx
0x180007578  xor     esi, esi
0x18000757a  lea     rcx, ?g_rgStoreInfo@@3PAU_AE_STORE_INFO_@@A; _AE_STORE_INFO_ near * g_rgStoreInfo
0x180007581  xor     edx, edx; dwEncodingType
0x180007583  mov     rax, rsi
0x180007586  mov     r9d, 90000h; dwFlags
0x18000758c  add     rax, rax
0x18000758f  xor     r8d, r8d; hCryptProv
0x180007592  mov     rax, [rcx+rax*8]
0x180007596  lea     ecx, [rdx+0Dh]; lpszStoreProvider
0x180007599  mov     [rsp+0C8h+pvPara], rax; pvPara
0x18000759e  call    cs:__imp_CertOpenStore
0x1800075a4  mov     rdi, rax
0x1800075a7  test    rax, rax
0x1800075aa  jz      short loc_1800075E1
0x1800075ac  jmp     short loc_1800075C0
0x1800075ae  mov     rcx, rbx; pCertContext
0x1800075b1  call    cs:__imp_CertDuplicateCertificateContext
0x1800075b7  mov     rcx, rax; pCertContext
0x1800075ba  call    cs:__imp_CertDeleteCertificateFromStore
0x1800075c0  mov     rdx, rbx; pPrevCertContext
0x1800075c3  mov     rcx, rdi; hCertStore
0x1800075c6  call    cs:__imp_CertEnumCertificatesInStore
0x1800075cc  mov     rbx, rax
0x1800075cf  test    rax, rax
0x1800075d2  jnz     short loc_1800075AE
0x1800075d4  xor     edx, edx; dwFlags
0x1800075d6  mov     rcx, rdi; hCertStore
0x1800075d9  call    cs:__imp_CertCloseStore
0x1800075df  xor     edi, edi
0x1800075e1  inc     rsi
0x1800075e4  cmp     rsi, 3
0x1800075e8  jnz     short loc_18000757A
0x1800075ea  lea     rcx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Cryptography\\Auto"...
0x1800075f1  call    ?AERemoveRegKey@@YAKPEAG@Z; AERemoveRegKey(ushort *)
0x1800075f6  lea     rcx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Cryptography\\Cert"...
0x1800075fd  mov     ebx, eax
0x1800075ff  call    ?AERemoveRegKey@@YAKPEAG@Z; AERemoveRegKey(ushort *)
0x180007604  test    ebx, ebx
0x180007606  cmovz   ebx, eax
0x180007609  test    rdi, rdi
0x18000760c  jz      short loc_180007619
0x18000760e  xor     edx, edx; dwFlags
0x180007610  mov     rcx, rdi; hCertStore
0x180007613  call    cs:__imp_CertCloseStore
0x180007619  test    ebx, ebx
0x18000761b  jz      short loc_180007629
0x18000761d  mov     ecx, ebx; dwErrCode
0x18000761f  call    cs:__imp_SetLastError
0x180007625  xor     eax, eax
0x180007627  jmp     short loc_18000762E
0x180007629  mov     eax, 1
0x18000762e  mov     rcx, [rsp+0C8h+var_18]
0x180007636  xor     rcx, rsp; StackCookie
0x180007639  call    __security_check_cookie
0x18000763e  lea     r11, [rsp+0C8h+var_8]
0x180007646  mov     rbx, [r11+10h]
0x18000764a  mov     rsi, [r11+18h]
0x18000764e  mov     rsp, r11
0x180007651  pop     rdi
0x180007652  retn
```
