# GetParentAppContainerMoniker

- ea: `0x18001c9ac`
- end: `0x18001cd42`
- name: `GetParentAppContainerMoniker`
- size: `918`
- prototype: `__int64 __fastcall(PSID Sid, PSID)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c2dc`

## callees

- `0x18001c9ac`
- `0x18001d438`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18001ca2d`
- `ntdll!NtQueryInformationToken` at `0x18001ca2d`
- `ntdll!RtlFreeUnicodeString` at `0x18001cd03`
- `ntdll!RtlFreeUnicodeString` at `0x18001cd0e`
- `ntdll!RtlFreeUnicodeString` at `0x18001cd19`
- `ntdll!RtlFreeUnicodeString` at `0x18001cd03`
- `ntdll!RtlFreeUnicodeString` at `0x18001cd0e`
- `ntdll!RtlFreeUnicodeString` at `0x18001cd19`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18001ca47`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18001cb26`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18001cbff`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18001ca47`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18001cb26`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18001cbff`
- `ntdll!RtlAllocateHeap` at `0x18001cc92`
- `ntdll!RtlAllocateHeap` at `0x18001cc92`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cc5e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cce4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cc5e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001cce4`

## pseudocode

```c
NTSTATUS __fastcall GetParentAppContainerMoniker(PSID Sid, PSID a2, PVOID *a3)
{
  NTSTATUS result; // eax
  NTSTATUS v7; // ebx
  __int64 v8; // rdx
  WCHAR *v9; // rax
  __int64 v10; // r8
  const wchar_t *v11; // rcx
  __int64 v12; // rdi
  bool v13; // zf
  __int64 v14; // rdx
  WCHAR *v15; // r8
  __int64 v16; // rax
  WCHAR *v17; // rcx
  __int64 v18; // rdx
  WCHAR *v19; // rax
  __int64 v20; // r8
  const wchar_t *v21; // rax
  WCHAR *v22; // r10
  __int64 v23; // r9
  WCHAR *v24; // rcx
  LSTATUS ValueW; // eax
  PVOID Heap; // rax
  LSTATUS v27; // eax
  int v28; // ecx
  ULONG ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING v31; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING v32; // [rsp+68h] [rbp-98h] BYREF
  PSID TokenInformation[12]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SubKey[520]; // [rsp+E0h] [rbp-20h] BYREF

  UnicodeString = 0;
  v32 = 0;
  v31 = 0;
  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 0;
  SubKey[0] = 0;
  result = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, TokenInformation, 0x58u, &ReturnLength);
  if ( result >= 0 )
  {
    result = RtlConvertSidToUnicodeString(&UnicodeString, TokenInformation[0], 1u);
    if ( result >= 0 )
    {
      v7 = RtlStringCchCatW(SubKey, 520, UnicodeString.Buffer);
      if ( v7 >= 0 )
      {
        v8 = 520;
        v9 = SubKey;
        do
        {
          if ( !*v9 )
            break;
          ++v9;
          --v8;
        }
        while ( v8 );
        v7 = v8 == 0 ? 0xC000000D : 0;
        v10 = (520 - v8) & -(__int64)(v8 != 0);
        if ( v8 )
        {
          v11 = L"\\Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppContainer\\Mappings\\";
          v12 = 2147483646;
          v14 = 520 - v10;
          v13 = v10 == 520;
          v15 = &SubKey[v10];
          v16 = 2147483646;
          if ( !v13 )
          {
            do
            {
              if ( !v16 )
                break;
              if ( !*v11 )
                break;
              *v15++ = *v11++;
              --v16;
              --v14;
            }
            while ( v14 );
          }
          v17 = v15 - 1;
          v7 = v14 == 0 ? 0x80000005 : 0;
          if ( v14 )
            v17 = v15;
          *v17 = 0;
          if ( v14 )
          {
            v7 = RtlConvertSidToUnicodeString(&v31, a2, 1u);
            if ( v7 >= 0 )
            {
              v7 = RtlStringCchCatW(SubKey, 520, v31.Buffer);
              if ( v7 >= 0 )
              {
                v18 = 520;
                v19 = SubKey;
                do
                {
                  if ( !*v19 )
                    break;
                  ++v19;
                  --v18;
                }
                while ( v18 );
                v7 = v18 == 0 ? 0xC000000D : 0;
                v20 = (520 - v18) & -(__int64)(v18 != 0);
                if ( v18 )
                {
                  v21 = L"\\Children\\";
                  v22 = &SubKey[v20];
                  v23 = 520 - v20;
                  if ( v20 != 520 )
                  {
                    do
                    {
                      if ( !v12 )
                        break;
                      if ( !*v21 )
                        break;
                      *v22++ = *v21++;
                      --v12;
                      --v23;
                    }
                    while ( v23 );
                  }
                  v24 = v22 - 1;
                  v7 = v23 == 0 ? 0x80000005 : 0;
                  if ( v23 )
                    v24 = v22;
                  *v24 = 0;
                  if ( v23 )
                  {
                    v7 = RtlConvertSidToUnicodeString(&v32, Sid, 1u);
                    if ( v7 >= 0 )
                    {
                      v7 = RtlStringCchCatW(SubKey, 520, v32.Buffer);
                      if ( v7 >= 0 )
                      {
                        ReturnLength = 0;
                        ValueW = RegGetValueW(HKEY_USERS, SubKey, L"ParentMoniker", 2u, 0, 0, &ReturnLength);
                        if ( ValueW )
                        {
                          v7 = -1073741809;
                          if ( ValueW != 2 )
                            v7 = -1073741823;
                        }
                        else
                        {
                          Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2LL * ReturnLength);
                          *a3 = Heap;
                          if ( Heap )
                          {
                            memset_0(Heap, 0, 2LL * ReturnLength);
                            v27 = RegGetValueW(HKEY_USERS, SubKey, L"ParentMoniker", 2u, 0, *a3, &ReturnLength);
                            if ( v27 )
                            {
                              v28 = -1073741823;
                              if ( v27 == 2 )
                                v28 = -1073741809;
                              v7 = v28;
                            }
                          }
                          else
                          {
                            v7 = -1073741801;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      RtlFreeUnicodeString(&UnicodeString);
      RtlFreeUnicodeString(&v31);
      RtlFreeUnicodeString(&v32);
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001c9ac  push    rbp
0x18001c9ae  push    rbx
0x18001c9af  push    rsi
0x18001c9b0  push    rdi
0x18001c9b1  push    r12
0x18001c9b3  push    r14
0x18001c9b5  push    r15
0x18001c9b7  lea     rbp, [rsp-400h]
0x18001c9bf  sub     rsp, 500h
0x18001c9c6  mov     rax, cs:__security_cookie
0x18001c9cd  xor     rax, rsp
0x18001c9d0  mov     [rbp+430h+var_40], rax
0x18001c9d7  xorps   xmm0, xmm0
0x18001c9da  mov     r14, r8
0x18001c9dd  mov     rsi, rdx
0x18001c9e0  mov     r15, rcx
0x18001c9e3  xorps   xmm1, xmm1
0x18001c9e6  lea     rcx, [rbp+430h+TokenInformation]; void *
0x18001c9ea  mov     ebx, 58h ; 'X'
0x18001c9ef  xor     edx, edx; Val
0x18001c9f1  mov     r8d, ebx; Size
0x18001c9f4  movups  xmmword ptr [rsp+530h+UnicodeString.Length], xmm0
0x18001c9f9  movups  xmmword ptr [rsp+530h+var_4C8.Length], xmm1
0x18001c9fe  movups  xmmword ptr [rsp+530h+var_4D8.Length], xmm0
0x18001ca03  call    memset_0
0x18001ca08  lea     rax, [rsp+530h+var_4F0]
0x18001ca0d  xor     r12d, r12d
0x18001ca10  mov     r9d, ebx; TokenInformationLength
0x18001ca13  mov     [rsp+530h+ReturnLength], rax; ReturnLength
0x18001ca18  lea     r8, [rbp+430h+TokenInformation]; TokenInformation
0x18001ca1c  mov     [rsp+530h+var_4F0], r12d
0x18001ca21  lea     edx, [rbx-57h]; TokenInformationClass
0x18001ca24  mov     [rbp+430h+SubKey], r12w
0x18001ca29  lea     rcx, [rbx-5Eh]; TokenHandle
0x18001ca2d  call    cs:__imp_NtQueryInformationToken
0x18001ca33  test    eax, eax
0x18001ca35  js      loc_18001CD21
0x18001ca3b  mov     rdx, [rbp+430h+TokenInformation]; Sid
0x18001ca3f  lea     rcx, [rsp+530h+UnicodeString]; UnicodeString
0x18001ca44  mov     r8b, 1; AllocateDestinationString
0x18001ca47  call    cs:__imp_RtlConvertSidToUnicodeString
0x18001ca4d  test    eax, eax
0x18001ca4f  js      loc_18001CD21
0x18001ca55  mov     r8, [rsp+530h+UnicodeString.Buffer]
0x18001ca5a  lea     rcx, [rbp+430h+SubKey]
0x18001ca5e  mov     edi, 208h
0x18001ca63  mov     edx, edi
0x18001ca65  call    RtlStringCchCatW
0x18001ca6a  mov     ebx, eax
0x18001ca6c  test    eax, eax
0x18001ca6e  js      loc_18001CCFE
0x18001ca74  mov     edx, edi
0x18001ca76  lea     rax, [rbp+430h+SubKey]
0x18001ca7a  cmp     [rax], r12w
0x18001ca7e  jz      short loc_18001CA8A
0x18001ca80  add     rax, 2
0x18001ca84  sub     rdx, 1
0x18001ca88  jnz     short loc_18001CA7A
0x18001ca8a  mov     rax, rdx
0x18001ca8d  mov     rcx, rdi
0x18001ca90  neg     rax
0x18001ca93  mov     rax, rdx
0x18001ca96  sbb     ebx, ebx
0x18001ca98  sub     rcx, rdx
0x18001ca9b  not     ebx
0x18001ca9d  and     ebx, 0C000000Dh
0x18001caa3  neg     rax
0x18001caa6  sbb     r8, r8
0x18001caa9  and     r8, rcx
0x18001caac  test    rdx, rdx
0x18001caaf  jz      loc_18001CCFE
0x18001cab5  mov     edx, 208h
0x18001caba  lea     rcx, aSoftwareClasse; "\\Software\\Classes\\Local Settings\\So"...
0x18001cac1  mov     edi, 7FFFFFFEh
0x18001cac6  sub     rdx, r8
0x18001cac9  lea     r8, [rbp+r8*2+430h+SubKey]
0x18001cace  mov     eax, edi
0x18001cad0  jz      short loc_18001CAF6
0x18001cad2  test    rax, rax
0x18001cad5  jz      short loc_18001CAF6
0x18001cad7  movzx   r9d, word ptr [rcx]
0x18001cadb  test    r9w, r9w
0x18001cadf  jz      short loc_18001CAF6
0x18001cae1  mov     [r8], r9w
0x18001cae5  add     rcx, 2
0x18001cae9  add     r8, 2
0x18001caed  dec     rax
0x18001caf0  sub     rdx, 1
0x18001caf4  jnz     short loc_18001CAD2
0x18001caf6  mov     rax, rdx
0x18001caf9  lea     rcx, [r8-2]
0x18001cafd  neg     rax
0x18001cb00  sbb     ebx, ebx
0x18001cb02  not     ebx
0x18001cb04  and     ebx, 80000005h
0x18001cb0a  test    rdx, rdx
0x18001cb0d  cmovnz  rcx, r8
0x18001cb11  mov     [rcx], r12w
0x18001cb15  jz      loc_18001CCFE
0x18001cb1b  mov     r8b, 1; AllocateDestinationString
0x18001cb1e  lea     rcx, [rsp+530h+var_4D8]; UnicodeString
0x18001cb23  mov     rdx, rsi; Sid
0x18001cb26  call    cs:__imp_RtlConvertSidToUnicodeString
0x18001cb2c  mov     ebx, eax
0x18001cb2e  test    eax, eax
0x18001cb30  js      loc_18001CCFE
0x18001cb36  mov     r8, [rsp+530h+var_4D8.Buffer]
0x18001cb3b  lea     rcx, [rbp+430h+SubKey]
0x18001cb3f  mov     esi, 208h
0x18001cb44  mov     edx, esi
0x18001cb46  call    RtlStringCchCatW
0x18001cb4b  mov     ebx, eax
0x18001cb4d  test    eax, eax
0x18001cb4f  js      loc_18001CCFE
0x18001cb55  mov     edx, esi
0x18001cb57  lea     rax, [rbp+430h+SubKey]
0x18001cb5b  cmp     [rax], r12w
0x18001cb5f  jz      short loc_18001CB6B
0x18001cb61  add     rax, 2
0x18001cb65  sub     rdx, 1
0x18001cb69  jnz     short loc_18001CB5B
0x18001cb6b  mov     rax, rdx
0x18001cb6e  mov     rcx, rsi
0x18001cb71  neg     rax
0x18001cb74  mov     rax, rdx
0x18001cb77  sbb     ebx, ebx
0x18001cb79  sub     rcx, rdx
0x18001cb7c  not     ebx
0x18001cb7e  and     ebx, 0C000000Dh
0x18001cb84  neg     rax
0x18001cb87  sbb     r8, r8
0x18001cb8a  and     r8, rcx
0x18001cb8d  test    rdx, rdx
0x18001cb90  jz      loc_18001CCFE
0x18001cb96  mov     r9, rsi
0x18001cb99  lea     r10, [rbp+430h+SubKey]
0x18001cb9d  lea     rax, aChildren; "\\Children\\"
0x18001cba4  lea     r10, [r10+r8*2]
0x18001cba8  sub     r9, r8
0x18001cbab  jz      short loc_18001CBCF
0x18001cbad  test    rdi, rdi
0x18001cbb0  jz      short loc_18001CBCF
0x18001cbb2  movzx   ecx, word ptr [rax]
0x18001cbb5  test    cx, cx
0x18001cbb8  jz      short loc_18001CBCF
0x18001cbba  mov     [r10], cx
0x18001cbbe  add     rax, 2
0x18001cbc2  add     r10, 2
0x18001cbc6  dec     rdi
0x18001cbc9  sub     r9, 1
0x18001cbcd  jnz     short loc_18001CBAD
0x18001cbcf  mov     rax, r9
0x18001cbd2  lea     rcx, [r10-2]
0x18001cbd6  neg     rax
0x18001cbd9  sbb     ebx, ebx
0x18001cbdb  not     ebx
0x18001cbdd  and     ebx, 80000005h
0x18001cbe3  test    r9, r9
0x18001cbe6  cmovnz  rcx, r10
0x18001cbea  mov     [rcx], r12w
0x18001cbee  jz      loc_18001CCFE
0x18001cbf4  mov     r8b, 1; AllocateDestinationString
0x18001cbf7  lea     rcx, [rsp+530h+var_4C8]; UnicodeString
0x18001cbfc  mov     rdx, r15; Sid
0x18001cbff  call    cs:__imp_RtlConvertSidToUnicodeString
0x18001cc05  mov     ebx, eax
0x18001cc07  test    eax, eax
0x18001cc09  js      loc_18001CCFE
0x18001cc0f  mov     r8, [rsp+530h+var_4C8.Buffer]
0x18001cc14  lea     rcx, [rbp+430h+SubKey]
0x18001cc18  mov     rdx, rsi
0x18001cc1b  call    RtlStringCchCatW
0x18001cc20  mov     ebx, eax
0x18001cc22  test    eax, eax
0x18001cc24  js      loc_18001CCFE
0x18001cc2a  lea     rax, [rsp+530h+var_4F0]
0x18001cc2f  mov     [rsp+530h+var_4F0], r12d
0x18001cc34  mov     [rsp+530h+pcbData], rax; pcbData
0x18001cc39  lea     r8, Value; "ParentMoniker"
0x18001cc40  mov     rdi, 0FFFFFFFF80000003h
0x18001cc47  mov     [rsp+530h+pvData], r12; pvData
0x18001cc4c  mov     r9d, 2; dwFlags
0x18001cc52  mov     [rsp+530h+ReturnLength], r12; pdwType
0x18001cc57  lea     rdx, [rbp+430h+SubKey]; lpSubKey
0x18001cc5b  mov     rcx, rdi; hkey
0x18001cc5e  call    cs:__imp_RegGetValueW
0x18001cc64  test    eax, eax
0x18001cc66  jz      short loc_18001CC7B
0x18001cc68  mov     ebx, 0C000000Fh
0x18001cc6d  cmp     eax, 2
0x18001cc70  lea     ecx, [rbx-0Eh]
0x18001cc73  cmovnz  ebx, ecx
0x18001cc76  jmp     loc_18001CCFE
0x18001cc7b  mov     rcx, gs:60h
0x18001cc84  xor     edx, edx; Flags
0x18001cc86  mov     r8d, [rsp+530h+var_4F0]
0x18001cc8b  add     r8, r8; Size
0x18001cc8e  mov     rcx, [rcx+30h]; HeapHandle
0x18001cc92  call    cs:__imp_RtlAllocateHeap
0x18001cc98  mov     [r14], rax
0x18001cc9b  test    rax, rax
0x18001cc9e  jnz     short loc_18001CCA7
0x18001cca0  mov     ebx, 0C0000017h
0x18001cca5  jmp     short loc_18001CCFE
0x18001cca7  mov     r8d, [rsp+530h+var_4F0]
0x18001ccac  xor     edx, edx; Val
0x18001ccae  add     r8, r8; Size
0x18001ccb1  mov     rcx, rax; void *
0x18001ccb4  call    memset_0
0x18001ccb9  lea     rax, [rsp+530h+var_4F0]
0x18001ccbe  mov     r9d, 2; dwFlags
0x18001ccc4  mov     [rsp+530h+pcbData], rax; pcbData
0x18001ccc9  lea     r8, Value; "ParentMoniker"
0x18001ccd0  mov     rax, [r14]
0x18001ccd3  lea     rdx, [rbp+430h+SubKey]; lpSubKey
0x18001ccd7  mov     [rsp+530h+pvData], rax; pvData
0x18001ccdc  mov     rcx, rdi; hkey
0x18001ccdf  mov     [rsp+530h+ReturnLength], r12; pdwType
0x18001cce4  call    cs:__imp_RegGetValueW
0x18001ccea  test    eax, eax
0x18001ccec  jz      short loc_18001CCFE
0x18001ccee  mov     ecx, 0C0000001h
0x18001ccf3  cmp     eax, 2
0x18001ccf6  lea     ebx, [rcx+0Eh]
0x18001ccf9  cmovz   ecx, ebx
0x18001ccfc  mov     ebx, ecx
0x18001ccfe  lea     rcx, [rsp+530h+UnicodeString]; UnicodeString
0x18001cd03  call    cs:__imp_RtlFreeUnicodeString
0x18001cd09  lea     rcx, [rsp+530h+var_4D8]; UnicodeString
0x18001cd0e  call    cs:__imp_RtlFreeUnicodeString
0x18001cd14  lea     rcx, [rsp+530h+var_4C8]; UnicodeString
0x18001cd19  call    cs:__imp_RtlFreeUnicodeString
0x18001cd1f  mov     eax, ebx
0x18001cd21  mov     rcx, [rbp+430h+var_40]
0x18001cd28  xor     rcx, rsp; StackCookie
0x18001cd2b  call    __security_check_cookie
0x18001cd30  add     rsp, 500h
0x18001cd37  pop     r15
0x18001cd39  pop     r14
0x18001cd3b  pop     r12
0x18001cd3d  pop     rdi
0x18001cd3e  pop     rsi
0x18001cd3f  pop     rbx
0x18001cd40  pop     rbp
0x18001cd41  retn
```
