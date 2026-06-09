# DefaultActivityContextStore::StoreContext(ActivityContext &)

- ea: `0x18003ec40`
- end: `0x18003efbb`
- name: `?StoreContext@DefaultActivityContextStore@@UEAAJAEAVActivityContext@@@Z`
- size: `891`
- prototype: `__int64 __fastcall(DefaultActivityContextStore *__hidden this, struct ActivityContext *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800026d0`
- `0x18000bd7c`
- `0x18003cd7c`
- `0x18003d3ec`
- `0x18003ec40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ef86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ef86`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003eea9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003eef9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ef2e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003eea9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003eef9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003ef2e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003ee51`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003ee51`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ee16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ee16`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003eca5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18003eca5`

## string_xrefs

- `0x18003eed6`: `AttemptCounter`
- `0x18003ef0b`: `Rollback`

## pseudocode

```c
__int64 __fastcall DefaultActivityContextStore::StoreContext(
        DefaultActivityContextStore *this,
        struct ActivityContext *a2)
{
  __int64 v3; // rcx
  OLECHAR *p_sz; // rax
  unsigned int v5; // edi
  __int64 v6; // rax
  char *v7; // rcx
  __int64 v8; // rdx
  _WORD *v9; // r8
  _WORD *v10; // rcx
  __int64 v11; // rcx
  _WORD *v12; // rax
  __int64 v13; // rdx
  const unsigned __int16 *EnrollmentsRootKey; // rax
  LSTATUS Key; // eax
  HKEY v16; // rbx
  LSTATUS v17; // eax
  BYTE *v18; // r8
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v21[4]; // [rsp+54h] [rbp-ACh] BYREF
  BYTE v22[8]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey[2]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v24[40]; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR sz; // [rsp+C0h] [rbp-40h] BYREF
  char v26; // [rsp+C2h] [rbp-3Eh] BYREF
  WCHAR SubKey[264]; // [rsp+110h] [rbp+10h] BYREF

  *(_DWORD *)Data = 32;
  *(_DWORD *)v21 = 0;
  *(_DWORD *)v22 = 0;
  hKey[0] = 0;
  SubKey[0] = 0;
  v24[0] = 0;
  sz = 0;
  if ( StringFromGUID2((const GUID *const)((char *)a2 + 8), &sz, 39) != 39 )
    return (unsigned int)-2147418113;
  v3 = 39;
  p_sz = &sz;
  do
  {
    if ( !*p_sz )
      break;
    ++p_sz;
    --v3;
  }
  while ( v3 );
  v5 = v3 == 0 ? 0x80070057 : 0;
  if ( !v3 )
    return v5;
  if ( (unsigned __int64)(37 - v3) > 0x24 )
    return (unsigned int)-2147418113;
  v6 = 2147483646;
  v7 = &v26;
  v8 = 39;
  v9 = v24;
  do
  {
    if ( !v6 )
      break;
    if ( !*(_WORD *)v7 )
      break;
    *v9 = *(_WORD *)v7;
    v7 += 2;
    ++v9;
    --v6;
    --v8;
  }
  while ( v8 );
  v10 = v9 - 1;
  v5 = v8 == 0 ? 0x8007007A : 0;
  if ( v8 )
    v10 = v9;
  *v10 = 0;
  if ( v8 )
  {
    v11 = 39;
    v12 = v24;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v11;
    }
    while ( v11 );
    v5 = v11 == 0 ? 0x80070057 : 0;
    v13 = (39 - v11) & ((unsigned __int128)-(__int128)(unsigned __int64)v11 >> 64);
    if ( v11 )
    {
      if ( (unsigned __int64)(v13 - 2) <= 0x24 )
      {
        *((_WORD *)&hKey[1] + v13 + 3) = 0;
        EnrollmentsRootKey = EEDBManager::GetEnrollmentsRootKey();
        v5 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\%s", EnrollmentsRootKey, L"Context", v24);
        if ( (v5 & 0x80000000) == 0 )
        {
          Key = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, hKey);
          if ( Key == 2 )
            Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, hKey, 0);
          if ( Key )
          {
            if ( Key > 0 )
              return (unsigned __int16)Key | 0x80070000;
            else
              return (unsigned int)Key;
          }
          else
          {
            v16 = hKey[0];
            *(_DWORD *)Data = *((_DWORD *)a2 + 8);
            v17 = RegSetValueExW(hKey[0], L"ActivityType", 0, 4u, Data, 4u);
            if ( v17 )
            {
              if ( v17 > 0 )
                v5 = (unsigned __int16)v17 | 0x80070000;
              else
                v5 = v17;
            }
            else
            {
              *(_DWORD *)v21 = *((_DWORD *)a2 + 242);
              RegSetValueExW(v16, L"AttemptCounter", 0, 4u, v21, 4u);
              *(_DWORD *)v22 = *((_DWORD *)a2 + 108);
              RegSetValueExW(v16, L"Rollback", 0, 4u, v22, 4u);
              if ( a2 != (struct ActivityContext *)-448LL )
                v5 = WriteStringToRegistry(v16, L"OrchestratorType", (BYTE *)a2 + 448);
              v18 = (BYTE *)(&off_180070118)[2 * *(int *)Data];
              if ( v18 )
                WriteStringToRegistry(v16, L"ActivityTypeName", v18);
            }
            if ( v16 )
              RegCloseKey(v16);
          }
        }
        return v5;
      }
      return (unsigned int)-2147418113;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18003ec40  push    rbp
0x18003ec42  push    rbx
0x18003ec43  push    rsi
0x18003ec44  push    rdi
0x18003ec45  push    r14
0x18003ec47  push    r15
0x18003ec49  lea     rbp, [rsp-238h]
0x18003ec51  sub     rsp, 338h
0x18003ec58  mov     rax, cs:__security_cookie
0x18003ec5f  xor     rax, rsp
0x18003ec62  mov     [rbp+260h+var_40], rax
0x18003ec69  xor     r14d, r14d
0x18003ec6c  mov     dword ptr [rsp+360h+Data], 20h ; ' '
0x18003ec74  mov     rsi, rdx
0x18003ec77  mov     dword ptr [rsp+360h+var_30C], r14d
0x18003ec7c  lea     rcx, [rdx+8]; rguid
0x18003ec80  mov     dword ptr [rsp+360h+var_308], r14d
0x18003ec85  lea     rdx, [rbp+260h+sz]; lpsz
0x18003ec89  mov     [rsp+360h+hKey], r14
0x18003ec8e  lea     ebx, [r14+27h]
0x18003ec92  mov     [rbp+260h+SubKey], r14w
0x18003ec97  mov     r8d, ebx; cchMax
0x18003ec9a  mov     [rsp+360h+var_2F0], r14w
0x18003eca0  mov     [rbp+260h+sz], r14w
0x18003eca5  call    cs:__imp_StringFromGUID2
0x18003ecac  nop     dword ptr [rax+rax+00h]
0x18003ecb1  cmp     eax, ebx
0x18003ecb3  jnz     loc_18003EF94
0x18003ecb9  mov     ecx, ebx
0x18003ecbb  lea     rax, [rbp+260h+sz]
0x18003ecbf  cmp     [rax], r14w
0x18003ecc3  jz      short loc_18003ECCF
0x18003ecc5  add     rax, 2
0x18003ecc9  sub     rcx, 1
0x18003eccd  jnz     short loc_18003ECBF
0x18003eccf  mov     rax, rcx
0x18003ecd2  mov     r10d, 80070057h
0x18003ecd8  neg     rax
0x18003ecdb  sbb     edi, edi
0x18003ecdd  not     edi
0x18003ecdf  and     edi, r10d
0x18003ece2  test    rcx, rcx
0x18003ece5  jz      loc_18003EF99
0x18003eceb  mov     eax, 25h ; '%'
0x18003ecf0  mov     rdx, 0FFFFFFFFFFFFFFFEh
0x18003ecf7  sub     rax, rcx
0x18003ecfa  test    rcx, rcx
0x18003ecfd  cmovz   rax, rdx
0x18003ed01  cmp     rax, 24h ; '$'
0x18003ed05  ja      loc_18003EF94
0x18003ed0b  mov     eax, 7FFFFFFEh
0x18003ed10  lea     rcx, [rbp+260h+var_29E]
0x18003ed14  mov     rdx, rbx
0x18003ed17  lea     r8, [rsp+360h+var_2F0]
0x18003ed1c  test    rax, rax
0x18003ed1f  jz      short loc_18003ED40
0x18003ed21  movzx   r9d, word ptr [rcx]
0x18003ed25  test    r9w, r9w
0x18003ed29  jz      short loc_18003ED40
0x18003ed2b  mov     [r8], r9w
0x18003ed2f  add     rcx, 2
0x18003ed33  add     r8, 2
0x18003ed37  dec     rax
0x18003ed3a  sub     rdx, 1
0x18003ed3e  jnz     short loc_18003ED1C
0x18003ed40  mov     rax, rdx
0x18003ed43  lea     rcx, [r8-2]
0x18003ed47  neg     rax
0x18003ed4a  sbb     edi, edi
0x18003ed4c  not     edi
0x18003ed4e  and     edi, 8007007Ah
0x18003ed54  test    rdx, rdx
0x18003ed57  cmovnz  rcx, r8
0x18003ed5b  mov     [rcx], r14w
0x18003ed5f  jz      loc_18003EF99
0x18003ed65  mov     rcx, rbx
0x18003ed68  lea     rax, [rsp+360h+var_2F0]
0x18003ed6d  cmp     [rax], r14w
0x18003ed71  jz      short loc_18003ED7D
0x18003ed73  add     rax, 2
0x18003ed77  sub     rcx, 1
0x18003ed7b  jnz     short loc_18003ED6D
0x18003ed7d  mov     rax, rcx
0x18003ed80  neg     rax
0x18003ed83  mov     rax, rcx
0x18003ed86  sbb     edi, edi
0x18003ed88  sub     rbx, rcx
0x18003ed8b  not     edi
0x18003ed8d  and     edi, r10d
0x18003ed90  neg     rax
0x18003ed93  sbb     rdx, rdx
0x18003ed96  and     rdx, rbx
0x18003ed99  test    rcx, rcx
0x18003ed9c  jz      loc_18003EF99
0x18003eda2  lea     rax, [rdx-2]
0x18003eda6  cmp     rax, 24h ; '$'
0x18003edaa  ja      loc_18003EF94
0x18003edb0  mov     [rsp+rdx*2+360h+var_2F2], r14w
0x18003edb6  call    ?GetEnrollmentsRootKey@EEDBManager@@SAPEBGXZ; EEDBManager::GetEnrollmentsRootKey(void)
0x18003edbb  lea     rcx, [rsp+360h+var_2F0]
0x18003edc0  mov     r9, rax
0x18003edc3  mov     qword ptr [rsp+360h+samDesired], rcx
0x18003edc8  lea     r8, aSSS; "%s\\%s\\%s"
0x18003edcf  lea     rcx, aContext_0; "Context"
0x18003edd6  mov     edx, 104h; unsigned __int64
0x18003eddb  mov     [rsp+360h+phkResult], rcx
0x18003ede0  lea     rcx, [rbp+260h+SubKey]; unsigned __int16 *
0x18003ede4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003ede9  mov     edi, eax
0x18003edeb  test    eax, eax
0x18003eded  js      loc_18003EF99
0x18003edf3  lea     rax, [rsp+360h+hKey]
0x18003edf8  mov     ebx, 0F003Fh
0x18003edfd  mov     r15, 0FFFFFFFF80000002h
0x18003ee04  mov     [rsp+360h+phkResult], rax; phkResult
0x18003ee09  mov     r9d, ebx; samDesired
0x18003ee0c  lea     rdx, [rbp+260h+SubKey]; lpSubKey
0x18003ee10  mov     rcx, r15; hKey
0x18003ee13  xor     r8d, r8d; ulOptions
0x18003ee16  call    cs:__imp_RegOpenKeyExW
0x18003ee1d  nop     dword ptr [rax+rax+00h]
0x18003ee22  cmp     eax, 2
0x18003ee25  jnz     short loc_18003EE5D
0x18003ee27  mov     [rsp+360h+lpdwDisposition], r14; lpdwDisposition
0x18003ee2c  lea     rax, [rsp+360h+hKey]
0x18003ee31  mov     [rsp+360h+var_328], rax; phkResult
0x18003ee36  lea     rdx, [rbp+260h+SubKey]; lpSubKey
0x18003ee3a  mov     [rsp+360h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18003ee3f  xor     r9d, r9d; lpClass
0x18003ee42  mov     [rsp+360h+samDesired], ebx; samDesired
0x18003ee46  xor     r8d, r8d; Reserved
0x18003ee49  mov     rcx, r15; hKey
0x18003ee4c  mov     dword ptr [rsp+360h+phkResult], r14d; dwOptions
0x18003ee51  call    cs:__imp_RegCreateKeyExW
0x18003ee58  nop     dword ptr [rax+rax+00h]
0x18003ee5d  test    eax, eax
0x18003ee5f  jz      short loc_18003EE78
0x18003ee61  jg      short loc_18003EE6A
0x18003ee63  mov     edi, eax
0x18003ee65  jmp     loc_18003EF99
0x18003ee6a  movzx   edi, ax
0x18003ee6d  or      edi, 80070000h
0x18003ee73  jmp     loc_18003EF99
0x18003ee78  mov     eax, [rsi+20h]
0x18003ee7b  lea     rdx, aActivitytype; "ActivityType"
0x18003ee82  mov     rbx, [rsp+360h+hKey]
0x18003ee87  mov     r15d, 4
0x18003ee8d  mov     dword ptr [rsp+360h+Data], eax
0x18003ee91  mov     r9d, r15d; dwType
0x18003ee94  lea     rax, [rsp+360h+Data]
0x18003ee99  mov     [rsp+360h+samDesired], r15d; cbData
0x18003ee9e  xor     r8d, r8d; Reserved
0x18003eea1  mov     [rsp+360h+phkResult], rax; lpData
0x18003eea6  mov     rcx, rbx; hKey
0x18003eea9  call    cs:__imp_RegSetValueExW
0x18003eeb0  nop     dword ptr [rax+rax+00h]
0x18003eeb5  test    eax, eax
0x18003eeb7  jz      short loc_18003EED0
0x18003eeb9  jg      short loc_18003EEC2
0x18003eebb  mov     edi, eax
0x18003eebd  jmp     loc_18003EF7E
0x18003eec2  movzx   edi, ax
0x18003eec5  or      edi, 80070000h
0x18003eecb  jmp     loc_18003EF7E
0x18003eed0  mov     eax, [rsi+3C8h]
0x18003eed6  lea     rdx, aAttemptcounter; "AttemptCounter"
0x18003eedd  mov     dword ptr [rsp+360h+var_30C], eax
0x18003eee1  mov     r9d, r15d; dwType
0x18003eee4  lea     rax, [rsp+360h+var_30C]
0x18003eee9  mov     [rsp+360h+samDesired], r15d; cbData
0x18003eeee  xor     r8d, r8d; Reserved
0x18003eef1  mov     [rsp+360h+phkResult], rax; lpData
0x18003eef6  mov     rcx, rbx; hKey
0x18003eef9  call    cs:__imp_RegSetValueExW
0x18003ef00  nop     dword ptr [rax+rax+00h]
0x18003ef05  mov     eax, [rsi+1B0h]
0x18003ef0b  lea     rdx, aRollback; "Rollback"
0x18003ef12  mov     dword ptr [rsp+360h+var_308], eax
0x18003ef16  mov     r9d, r15d; dwType
0x18003ef19  lea     rax, [rsp+360h+var_308]
0x18003ef1e  mov     [rsp+360h+samDesired], r15d; cbData
0x18003ef23  xor     r8d, r8d; Reserved
0x18003ef26  mov     [rsp+360h+phkResult], rax; lpData
0x18003ef2b  mov     rcx, rbx; hKey
0x18003ef2e  call    cs:__imp_RegSetValueExW
0x18003ef35  nop     dword ptr [rax+rax+00h]
0x18003ef3a  lea     r8, [rsi+1C0h]; lpData
0x18003ef41  test    r8, r8
0x18003ef44  jz      short loc_18003EF57
0x18003ef46  lea     rdx, aOrchestratorty; "OrchestratorType"
0x18003ef4d  mov     rcx, rbx; hKey
0x18003ef50  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003ef55  mov     edi, eax
0x18003ef57  movsxd  rax, dword ptr [rsp+360h+Data]
0x18003ef5c  lea     r8, off_180070118; "AT_MDM_RENEWAL_DISCOVERY"
0x18003ef63  add     rax, rax
0x18003ef66  mov     r8, [r8+rax*8]; lpData
0x18003ef6a  test    r8, r8
0x18003ef6d  jz      short loc_18003EF7E
0x18003ef6f  lea     rdx, aActivitytypena; "ActivityTypeName"
0x18003ef76  mov     rcx, rbx; hKey
0x18003ef79  call    ?WriteStringToRegistry@@YAJPEAUHKEY__@@PEBG1@Z; WriteStringToRegistry(HKEY__ *,ushort const *,ushort const *)
0x18003ef7e  test    rbx, rbx
0x18003ef81  jz      short loc_18003EF99
0x18003ef83  mov     rcx, rbx; hKey
0x18003ef86  call    cs:__imp_RegCloseKey
0x18003ef8d  nop     dword ptr [rax+rax+00h]
0x18003ef92  jmp     short loc_18003EF99
0x18003ef94  mov     edi, 8000FFFFh
0x18003ef99  mov     eax, edi
0x18003ef9b  mov     rcx, [rbp+260h+var_40]
0x18003efa2  xor     rcx, rsp; StackCookie
0x18003efa5  call    __security_check_cookie
0x18003efaa  add     rsp, 338h
0x18003efb1  pop     r15
0x18003efb3  pop     r14
0x18003efb5  pop     rdi
0x18003efb6  pop     rsi
0x18003efb7  pop     rbx
0x18003efb8  pop     rbp
0x18003efb9  retn
```
