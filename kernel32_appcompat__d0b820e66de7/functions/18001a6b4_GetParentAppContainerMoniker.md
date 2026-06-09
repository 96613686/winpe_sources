# GetParentAppContainerMoniker

- ea: `0x18001a6b4`
- end: `0x18001aa87`
- name: `GetParentAppContainerMoniker`
- size: `979`
- prototype: `__int64 __fastcall(PSID Sid, PSID)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019efc`

## callees

- `0x18001a6b4`
- `0x18001b1cc`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18001a735`
- `ntdll!NtQueryInformationToken` at `0x18001a735`
- `ntdll!RtlFreeUnicodeString` at `0x18001aa35`
- `ntdll!RtlFreeUnicodeString` at `0x18001aa46`
- `ntdll!RtlFreeUnicodeString` at `0x18001aa57`
- `ntdll!RtlFreeUnicodeString` at `0x18001aa35`
- `ntdll!RtlFreeUnicodeString` at `0x18001aa46`
- `ntdll!RtlFreeUnicodeString` at `0x18001aa57`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18001a755`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18001a83a`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18001a919`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18001a755`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18001a83a`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18001a919`
- `ntdll!RtlAllocateHeap` at `0x18001a9b8`
- `ntdll!RtlAllocateHeap` at `0x18001a9b8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a97e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001aa10`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a97e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001aa10`

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
0x18001a6b4  push    rbp
0x18001a6b6  push    rbx
0x18001a6b7  push    rsi
0x18001a6b8  push    rdi
0x18001a6b9  push    r12
0x18001a6bb  push    r14
0x18001a6bd  push    r15
0x18001a6bf  lea     rbp, [rsp-400h]
0x18001a6c7  sub     rsp, 500h
0x18001a6ce  mov     rax, cs:__security_cookie
0x18001a6d5  xor     rax, rsp
0x18001a6d8  mov     [rbp+430h+var_40], rax
0x18001a6df  xorps   xmm0, xmm0
0x18001a6e2  mov     r14, r8
0x18001a6e5  mov     rsi, rdx
0x18001a6e8  mov     r15, rcx
0x18001a6eb  xorps   xmm1, xmm1
0x18001a6ee  lea     rcx, [rbp+430h+TokenInformation]; void *
0x18001a6f2  mov     ebx, 58h ; 'X'
0x18001a6f7  xor     edx, edx; Val
0x18001a6f9  mov     r8d, ebx; Size
0x18001a6fc  movups  xmmword ptr [rsp+530h+UnicodeString.Length], xmm0
0x18001a701  movups  xmmword ptr [rsp+530h+var_4C8.Length], xmm1
0x18001a706  movups  xmmword ptr [rsp+530h+var_4D8.Length], xmm0
0x18001a70b  call    memset_0
0x18001a710  lea     rax, [rsp+530h+var_4F0]
0x18001a715  xor     r12d, r12d
0x18001a718  mov     r9d, ebx; TokenInformationLength
0x18001a71b  mov     [rsp+530h+ReturnLength], rax; ReturnLength
0x18001a720  lea     r8, [rbp+430h+TokenInformation]; TokenInformation
0x18001a724  mov     [rsp+530h+var_4F0], r12d
0x18001a729  lea     edx, [rbx-57h]; TokenInformationClass
0x18001a72c  mov     [rbp+430h+SubKey], r12w
0x18001a731  lea     rcx, [rbx-5Eh]; TokenHandle
0x18001a735  call    cs:__imp_NtQueryInformationToken
0x18001a73c  nop     dword ptr [rax+rax+00h]
0x18001a741  test    eax, eax
0x18001a743  js      loc_18001AA65
0x18001a749  mov     rdx, [rbp+430h+TokenInformation]; Sid
0x18001a74d  lea     rcx, [rsp+530h+UnicodeString]; UnicodeString
0x18001a752  mov     r8b, 1; AllocateDestinationString
0x18001a755  call    cs:__imp_RtlConvertSidToUnicodeString
0x18001a75c  nop     dword ptr [rax+rax+00h]
0x18001a761  test    eax, eax
0x18001a763  js      loc_18001AA65
0x18001a769  mov     r8, [rsp+530h+UnicodeString.Buffer]
0x18001a76e  lea     rcx, [rbp+430h+SubKey]
0x18001a772  mov     edi, 208h
0x18001a777  mov     edx, edi
0x18001a779  call    RtlStringCchCatW
0x18001a77e  mov     ebx, eax
0x18001a780  test    eax, eax
0x18001a782  js      loc_18001AA30
0x18001a788  mov     edx, edi
0x18001a78a  lea     rax, [rbp+430h+SubKey]
0x18001a78e  cmp     [rax], r12w
0x18001a792  jz      short loc_18001A79E
0x18001a794  add     rax, 2
0x18001a798  sub     rdx, 1
0x18001a79c  jnz     short loc_18001A78E
0x18001a79e  mov     rax, rdx
0x18001a7a1  mov     rcx, rdi
0x18001a7a4  neg     rax
0x18001a7a7  mov     rax, rdx
0x18001a7aa  sbb     ebx, ebx
0x18001a7ac  sub     rcx, rdx
0x18001a7af  not     ebx
0x18001a7b1  and     ebx, 0C000000Dh
0x18001a7b7  neg     rax
0x18001a7ba  sbb     r8, r8
0x18001a7bd  and     r8, rcx
0x18001a7c0  test    rdx, rdx
0x18001a7c3  jz      loc_18001AA30
0x18001a7c9  mov     edx, 208h
0x18001a7ce  lea     rcx, aSoftwareClasse; "\\Software\\Classes\\Local Settings\\So"...
0x18001a7d5  mov     edi, 7FFFFFFEh
0x18001a7da  sub     rdx, r8
0x18001a7dd  lea     r8, [rbp+r8*2+430h+SubKey]
0x18001a7e2  mov     eax, edi
0x18001a7e4  jz      short loc_18001A80A
0x18001a7e6  test    rax, rax
0x18001a7e9  jz      short loc_18001A80A
0x18001a7eb  movzx   r9d, word ptr [rcx]
0x18001a7ef  test    r9w, r9w
0x18001a7f3  jz      short loc_18001A80A
0x18001a7f5  mov     [r8], r9w
0x18001a7f9  add     rcx, 2
0x18001a7fd  add     r8, 2
0x18001a801  dec     rax
0x18001a804  sub     rdx, 1
0x18001a808  jnz     short loc_18001A7E6
0x18001a80a  mov     rax, rdx
0x18001a80d  lea     rcx, [r8-2]
0x18001a811  neg     rax
0x18001a814  sbb     ebx, ebx
0x18001a816  not     ebx
0x18001a818  and     ebx, 80000005h
0x18001a81e  test    rdx, rdx
0x18001a821  cmovnz  rcx, r8
0x18001a825  mov     [rcx], r12w
0x18001a829  jz      loc_18001AA30
0x18001a82f  mov     r8b, 1; AllocateDestinationString
0x18001a832  lea     rcx, [rsp+530h+var_4D8]; UnicodeString
0x18001a837  mov     rdx, rsi; Sid
0x18001a83a  call    cs:__imp_RtlConvertSidToUnicodeString
0x18001a841  nop     dword ptr [rax+rax+00h]
0x18001a846  mov     ebx, eax
0x18001a848  test    eax, eax
0x18001a84a  js      loc_18001AA30
0x18001a850  mov     r8, [rsp+530h+var_4D8.Buffer]
0x18001a855  lea     rcx, [rbp+430h+SubKey]
0x18001a859  mov     esi, 208h
0x18001a85e  mov     edx, esi
0x18001a860  call    RtlStringCchCatW
0x18001a865  mov     ebx, eax
0x18001a867  test    eax, eax
0x18001a869  js      loc_18001AA30
0x18001a86f  mov     edx, esi
0x18001a871  lea     rax, [rbp+430h+SubKey]
0x18001a875  cmp     [rax], r12w
0x18001a879  jz      short loc_18001A885
0x18001a87b  add     rax, 2
0x18001a87f  sub     rdx, 1
0x18001a883  jnz     short loc_18001A875
0x18001a885  mov     rax, rdx
0x18001a888  mov     rcx, rsi
0x18001a88b  neg     rax
0x18001a88e  mov     rax, rdx
0x18001a891  sbb     ebx, ebx
0x18001a893  sub     rcx, rdx
0x18001a896  not     ebx
0x18001a898  and     ebx, 0C000000Dh
0x18001a89e  neg     rax
0x18001a8a1  sbb     r8, r8
0x18001a8a4  and     r8, rcx
0x18001a8a7  test    rdx, rdx
0x18001a8aa  jz      loc_18001AA30
0x18001a8b0  mov     r9, rsi
0x18001a8b3  lea     r10, [rbp+430h+SubKey]
0x18001a8b7  lea     rax, aChildren; "\\Children\\"
0x18001a8be  lea     r10, [r10+r8*2]
0x18001a8c2  sub     r9, r8
0x18001a8c5  jz      short loc_18001A8E9
0x18001a8c7  test    rdi, rdi
0x18001a8ca  jz      short loc_18001A8E9
0x18001a8cc  movzx   ecx, word ptr [rax]
0x18001a8cf  test    cx, cx
0x18001a8d2  jz      short loc_18001A8E9
0x18001a8d4  mov     [r10], cx
0x18001a8d8  add     rax, 2
0x18001a8dc  add     r10, 2
0x18001a8e0  dec     rdi
0x18001a8e3  sub     r9, 1
0x18001a8e7  jnz     short loc_18001A8C7
0x18001a8e9  mov     rax, r9
0x18001a8ec  lea     rcx, [r10-2]
0x18001a8f0  neg     rax
0x18001a8f3  sbb     ebx, ebx
0x18001a8f5  not     ebx
0x18001a8f7  and     ebx, 80000005h
0x18001a8fd  test    r9, r9
0x18001a900  cmovnz  rcx, r10
0x18001a904  mov     [rcx], r12w
0x18001a908  jz      loc_18001AA30
0x18001a90e  mov     r8b, 1; AllocateDestinationString
0x18001a911  lea     rcx, [rsp+530h+var_4C8]; UnicodeString
0x18001a916  mov     rdx, r15; Sid
0x18001a919  call    cs:__imp_RtlConvertSidToUnicodeString
0x18001a920  nop     dword ptr [rax+rax+00h]
0x18001a925  mov     ebx, eax
0x18001a927  test    eax, eax
0x18001a929  js      loc_18001AA30
0x18001a92f  mov     r8, [rsp+530h+var_4C8.Buffer]
0x18001a934  lea     rcx, [rbp+430h+SubKey]
0x18001a938  mov     rdx, rsi
0x18001a93b  call    RtlStringCchCatW
0x18001a940  mov     ebx, eax
0x18001a942  test    eax, eax
0x18001a944  js      loc_18001AA30
0x18001a94a  lea     rax, [rsp+530h+var_4F0]
0x18001a94f  mov     [rsp+530h+var_4F0], r12d
0x18001a954  mov     [rsp+530h+pcbData], rax; pcbData
0x18001a959  lea     r8, Value; "ParentMoniker"
0x18001a960  mov     rdi, 0FFFFFFFF80000003h
0x18001a967  mov     [rsp+530h+pvData], r12; pvData
0x18001a96c  mov     r9d, 2; dwFlags
0x18001a972  mov     [rsp+530h+ReturnLength], r12; pdwType
0x18001a977  lea     rdx, [rbp+430h+SubKey]; lpSubKey
0x18001a97b  mov     rcx, rdi; hkey
0x18001a97e  call    cs:__imp_RegGetValueW
0x18001a985  nop     dword ptr [rax+rax+00h]
0x18001a98a  test    eax, eax
0x18001a98c  jz      short loc_18001A9A1
0x18001a98e  mov     ebx, 0C000000Fh
0x18001a993  cmp     eax, 2
0x18001a996  lea     ecx, [rbx-0Eh]
0x18001a999  cmovnz  ebx, ecx
0x18001a99c  jmp     loc_18001AA30
0x18001a9a1  mov     rcx, gs:60h
0x18001a9aa  xor     edx, edx; Flags
0x18001a9ac  mov     r8d, [rsp+530h+var_4F0]
0x18001a9b1  add     r8, r8; Size
0x18001a9b4  mov     rcx, [rcx+30h]; HeapHandle
0x18001a9b8  call    cs:__imp_RtlAllocateHeap
0x18001a9bf  nop     dword ptr [rax+rax+00h]
0x18001a9c4  mov     [r14], rax
0x18001a9c7  test    rax, rax
0x18001a9ca  jnz     short loc_18001A9D3
0x18001a9cc  mov     ebx, 0C0000017h
0x18001a9d1  jmp     short loc_18001AA30
0x18001a9d3  mov     r8d, [rsp+530h+var_4F0]
0x18001a9d8  xor     edx, edx; Val
0x18001a9da  add     r8, r8; Size
0x18001a9dd  mov     rcx, rax; void *
0x18001a9e0  call    memset_0
0x18001a9e5  lea     rax, [rsp+530h+var_4F0]
0x18001a9ea  mov     r9d, 2; dwFlags
0x18001a9f0  mov     [rsp+530h+pcbData], rax; pcbData
0x18001a9f5  lea     r8, Value; "ParentMoniker"
0x18001a9fc  mov     rax, [r14]
0x18001a9ff  lea     rdx, [rbp+430h+SubKey]; lpSubKey
0x18001aa03  mov     [rsp+530h+pvData], rax; pvData
0x18001aa08  mov     rcx, rdi; hkey
0x18001aa0b  mov     [rsp+530h+ReturnLength], r12; pdwType
0x18001aa10  call    cs:__imp_RegGetValueW
0x18001aa17  nop     dword ptr [rax+rax+00h]
0x18001aa1c  test    eax, eax
0x18001aa1e  jz      short loc_18001AA30
0x18001aa20  mov     ecx, 0C0000001h
0x18001aa25  cmp     eax, 2
0x18001aa28  lea     ebx, [rcx+0Eh]
0x18001aa2b  cmovz   ecx, ebx
0x18001aa2e  mov     ebx, ecx
0x18001aa30  lea     rcx, [rsp+530h+UnicodeString]; UnicodeString
0x18001aa35  call    cs:__imp_RtlFreeUnicodeString
0x18001aa3c  nop     dword ptr [rax+rax+00h]
0x18001aa41  lea     rcx, [rsp+530h+var_4D8]; UnicodeString
0x18001aa46  call    cs:__imp_RtlFreeUnicodeString
0x18001aa4d  nop     dword ptr [rax+rax+00h]
0x18001aa52  lea     rcx, [rsp+530h+var_4C8]; UnicodeString
0x18001aa57  call    cs:__imp_RtlFreeUnicodeString
0x18001aa5e  nop     dword ptr [rax+rax+00h]
0x18001aa63  mov     eax, ebx
0x18001aa65  mov     rcx, [rbp+430h+var_40]
0x18001aa6c  xor     rcx, rsp; StackCookie
0x18001aa6f  call    __security_check_cookie
0x18001aa74  add     rsp, 500h
0x18001aa7b  pop     r15
0x18001aa7d  pop     r14
0x18001aa7f  pop     r12
0x18001aa81  pop     rdi
0x18001aa82  pop     rsi
0x18001aa83  pop     rbx
0x18001aa84  pop     rbp
0x18001aa85  retn
```
