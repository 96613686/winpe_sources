# CLTPartitionUsers::PopulateCache(void)

- ea: `0x18004e700`
- end: `0x18004ea5a`
- name: `?PopulateCache@CLTPartitionUsers@@UEAAJXZ`
- size: `858`
- prototype: `__int64 __fastcall(CLTPartitionUsers *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180014ec8`
- `0x18004e700`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e9c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ea0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e9c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ea0c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18004e91e`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x18004e91e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004e974`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004e974`

## pseudocode

```c
__int64 __fastcall CLTPartitionUsers::PopulateCache(CLTPartitionUsers *this)
{
  int v2; // ebx
  int v3; // eax
  __int64 v4; // rcx
  PSID v5; // r14
  WCHAR *v6; // r9
  unsigned int v8; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v9; // [rsp+58h] [rbp-A8h]
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  PSID Sid; // [rsp+68h] [rbp-98h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchReferencedDomainName; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cchName; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ReferencedDomainName[280]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v9 = 0;
  StringSid = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int128 *, __int64 *))(**((_QWORD **)this + 10) + 24LL))(
         *((_QWORD *)this + 10),
         &didCOMSERVICES,
         &tidCOMSERVICES_PARTITION_USERS);
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
    if ( v2 >= 0 )
    {
      v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 32LL))(v9);
      if ( v2 >= 0 )
      {
        v2 = (*(__int64 (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 1) + 32LL))((char *)this + 8, 0);
        if ( v2 >= 0 )
        {
          while ( 1 )
          {
            v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 40LL))(v9);
            if ( v3 )
              break;
            v4 = *((_QWORD *)this + 9);
            peUse = 0;
            v8 = 0;
            cchName = 256;
            cchReferencedDomainName = 15;
            Sid = 0;
            v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 120LL))(v4);
            if ( v2 < 0 )
              goto LABEL_26;
            v2 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *, PSID *))(*(_QWORD *)v9 + 64LL))(
                   v9,
                   3,
                   0,
                   &v8,
                   &Sid);
            if ( v2 < 0 )
              goto LABEL_26;
            v2 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, PSID))(**((_QWORD **)this + 9) + 160LL))(
                   *((_QWORD *)this + 9),
                   2,
                   0,
                   Sid);
            if ( v2 < 0 )
              goto LABEL_26;
            v2 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned int *, PSID *))(*(_QWORD *)v9 + 64LL))(
                   v9,
                   0,
                   0,
                   &v8,
                   &Sid);
            if ( v2 < 0 )
              goto LABEL_26;
            v5 = Sid;
            v2 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, PSID))(**((_QWORD **)this + 9) + 160LL))(
                   *((_QWORD *)this + 9),
                   1,
                   v8,
                   Sid);
            if ( v2 < 0 )
              goto LABEL_26;
            if ( LookupAccountSidLocalW(v5, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
            {
              v2 = StringCchCatW(ReferencedDomainName, 0x111u, L"\\");
              if ( v2 < 0 )
                goto LABEL_26;
              v2 = StringCchCatW(ReferencedDomainName, 0x111u, Name);
              if ( v2 < 0 )
                goto LABEL_26;
              v6 = ReferencedDomainName;
            }
            else
            {
              if ( !ConvertSidToStringSidW(v5, &StringSid) )
              {
                v2 = -2147024882;
                goto LABEL_26;
              }
              v6 = StringSid;
            }
            v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, WCHAR *))(**((_QWORD **)this + 9) + 160LL))(
                   *((_QWORD *)this + 9),
                   0,
                   0,
                   v6);
            if ( v2 < 0 )
              goto LABEL_26;
            v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 9) + 144LL))(*((_QWORD *)this + 9));
            if ( v2 < 0 )
              goto LABEL_26;
            if ( StringSid )
            {
              LocalFree(StringSid);
              StringSid = 0;
            }
          }
          v2 = 0;
          if ( v3 != -2146367487 )
            v2 = v3;
          if ( v2 >= 0 )
            v2 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 1) + 40LL))((char *)this + 8);
        }
      }
    }
  }
LABEL_26:
  if ( StringSid )
  {
    LocalFree(StringSid);
    StringSid = 0;
  }
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18004e700  mov     [rsp-8+arg_8], rbx
0x18004e705  mov     [rsp-8+arg_10], rsi
0x18004e70a  push    rbp
0x18004e70b  push    rdi
0x18004e70c  push    r14
0x18004e70e  lea     rbp, [rsp-3D0h]
0x18004e716  sub     rsp, 4D0h
0x18004e71d  mov     rax, cs:__security_cookie
0x18004e724  xor     rax, rsp
0x18004e727  mov     [rbp+3E0h+var_20], rax
0x18004e72e  xor     edx, edx
0x18004e730  mov     [rsp+4E0h+var_488], 0
0x18004e739  mov     rdi, rcx
0x18004e73c  mov     [rsp+4E0h+StringSid], 0
0x18004e745  mov     rcx, [rcx+50h]
0x18004e749  lea     r8, [rsp+4E0h+var_488]
0x18004e74e  mov     [rsp+4E0h+var_4A8], r8
0x18004e753  lea     r8, tidCOMSERVICES_PARTITION_USERS
0x18004e75a  mov     [rsp+4E0h+var_4B0], 1
0x18004e762  mov     r9, [rdi+28h]
0x18004e766  mov     rax, [rcx]
0x18004e769  test    r9, r9
0x18004e76c  mov     dword ptr [rsp+4E0h+peUse], 1
0x18004e774  setnz   dl
0x18004e777  mov     [rsp+4E0h+cchReferencedDomainName], rdx
0x18004e77c  lea     rdx, didCOMSERVICES
0x18004e783  mov     rax, [rax+18h]
0x18004e787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e78c  mov     ebx, eax
0x18004e78e  test    eax, eax
0x18004e790  js      loc_18004EA02
0x18004e796  mov     rcx, [rsp+4E0h+var_488]
0x18004e79b  mov     rax, [rcx]
0x18004e79e  mov     rax, [rax+18h]
0x18004e7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e7a7  mov     ebx, eax
0x18004e7a9  test    eax, eax
0x18004e7ab  js      loc_18004EA02
0x18004e7b1  mov     rcx, [rsp+4E0h+var_488]
0x18004e7b6  mov     rax, [rcx]
0x18004e7b9  mov     rax, [rax+20h]
0x18004e7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e7c2  mov     ebx, eax
0x18004e7c4  test    eax, eax
0x18004e7c6  js      loc_18004EA02
0x18004e7cc  lea     rsi, [rdi+8]
0x18004e7d0  xor     edx, edx
0x18004e7d2  mov     rax, [rsi]
0x18004e7d5  mov     rcx, rsi
0x18004e7d8  mov     rax, [rax+20h]
0x18004e7dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e7e1  mov     ebx, eax
0x18004e7e3  test    eax, eax
0x18004e7e5  js      loc_18004EA02
0x18004e7eb  mov     rcx, [rsp+4E0h+var_488]
0x18004e7f0  mov     rax, [rcx]
0x18004e7f3  mov     rax, [rax+28h]
0x18004e7f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e7fc  test    eax, eax
0x18004e7fe  jnz     loc_18004E9E3
0x18004e804  mov     rcx, [rdi+48h]
0x18004e808  mov     [rsp+4E0h+var_470], eax
0x18004e80c  mov     [rsp+4E0h+var_490], eax
0x18004e810  mov     [rsp+4E0h+cchName], 100h
0x18004e818  mov     [rsp+4E0h+var_46C], 0Fh
0x18004e820  mov     [rsp+4E0h+Sid], 0
0x18004e829  mov     rax, [rcx]
0x18004e82c  mov     rax, [rax+78h]
0x18004e830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e835  mov     ebx, eax
0x18004e837  test    eax, eax
0x18004e839  js      loc_18004EA02
0x18004e83f  mov     rcx, [rsp+4E0h+var_488]
0x18004e844  lea     rdx, [rsp+4E0h+Sid]
0x18004e849  xor     r8d, r8d
0x18004e84c  mov     [rsp+4E0h+cchReferencedDomainName], rdx
0x18004e851  lea     r9, [rsp+4E0h+var_490]
0x18004e856  mov     rax, [rcx]
0x18004e859  lea     edx, [r8+3]
0x18004e85d  mov     rax, [rax+40h]
0x18004e861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e866  mov     ebx, eax
0x18004e868  test    eax, eax
0x18004e86a  js      loc_18004EA02
0x18004e870  mov     rcx, [rdi+48h]
0x18004e874  xor     r8d, r8d
0x18004e877  mov     r9, [rsp+4E0h+Sid]
0x18004e87c  mov     rax, [rcx]
0x18004e87f  lea     edx, [r8+2]
0x18004e883  mov     rax, [rax+0A0h]
0x18004e88a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e88f  mov     ebx, eax
0x18004e891  test    eax, eax
0x18004e893  js      loc_18004EA02
0x18004e899  mov     rcx, [rsp+4E0h+var_488]
0x18004e89e  lea     rdx, [rsp+4E0h+Sid]
0x18004e8a3  mov     [rsp+4E0h+cchReferencedDomainName], rdx
0x18004e8a8  lea     r9, [rsp+4E0h+var_490]
0x18004e8ad  xor     r8d, r8d
0x18004e8b0  xor     edx, edx
0x18004e8b2  mov     rax, [rcx]
0x18004e8b5  mov     rax, [rax+40h]
0x18004e8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e8be  mov     ebx, eax
0x18004e8c0  test    eax, eax
0x18004e8c2  js      loc_18004EA02
0x18004e8c8  mov     rcx, [rdi+48h]
0x18004e8cc  mov     edx, 1
0x18004e8d1  mov     r14, [rsp+4E0h+Sid]
0x18004e8d6  mov     r8d, [rsp+4E0h+var_490]
0x18004e8db  mov     r9, r14
0x18004e8de  mov     rax, [rcx]
0x18004e8e1  mov     rax, [rax+0A0h]
0x18004e8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e8ed  mov     ebx, eax
0x18004e8ef  test    eax, eax
0x18004e8f1  js      loc_18004EA02
0x18004e8f7  lea     rax, [rsp+4E0h+var_470]
0x18004e8fc  mov     rcx, r14; Sid
0x18004e8ff  mov     [rsp+4E0h+peUse], rax; peUse
0x18004e904  lea     r9, [rbp+3E0h+ReferencedDomainName]; ReferencedDomainName
0x18004e908  lea     rax, [rsp+4E0h+var_46C]
0x18004e90d  lea     r8, [rsp+4E0h+cchName]; cchName
0x18004e912  mov     [rsp+4E0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18004e917  lea     rdx, [rbp+3E0h+Name]; Name
0x18004e91e  call    cs:__imp_LookupAccountSidLocalW
0x18004e924  test    eax, eax
0x18004e926  jz      short loc_18004E96C
0x18004e928  lea     r8, asc_180061B34; "\\"
0x18004e92f  mov     edx, 111h; unsigned __int64
0x18004e934  lea     rcx, [rbp+3E0h+ReferencedDomainName]; unsigned __int16 *
0x18004e938  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004e93d  mov     ebx, eax
0x18004e93f  test    eax, eax
0x18004e941  js      loc_18004EA02
0x18004e947  lea     r8, [rbp+3E0h+Name]; unsigned __int16 *
0x18004e94e  mov     edx, 111h; unsigned __int64
0x18004e953  lea     rcx, [rbp+3E0h+ReferencedDomainName]; unsigned __int16 *
0x18004e957  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004e95c  mov     ebx, eax
0x18004e95e  test    eax, eax
0x18004e960  js      loc_18004EA02
0x18004e966  lea     r9, [rbp+3E0h+ReferencedDomainName]
0x18004e96a  jmp     short loc_18004E983
0x18004e96c  lea     rdx, [rsp+4E0h+StringSid]; StringSid
0x18004e971  mov     rcx, r14; Sid
0x18004e974  call    cs:__imp_ConvertSidToStringSidW
0x18004e97a  test    eax, eax
0x18004e97c  jz      short loc_18004E9DC
0x18004e97e  mov     r9, [rsp+4E0h+StringSid]
0x18004e983  mov     rcx, [rdi+48h]
0x18004e987  xor     r8d, r8d
0x18004e98a  xor     edx, edx
0x18004e98c  mov     rax, [rcx]
0x18004e98f  mov     rax, [rax+0A0h]
0x18004e996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e99b  mov     ebx, eax
0x18004e99d  test    eax, eax
0x18004e99f  js      short loc_18004EA02
0x18004e9a1  mov     rcx, [rdi+48h]
0x18004e9a5  mov     rax, [rcx]
0x18004e9a8  mov     rax, [rax+90h]
0x18004e9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e9b4  mov     ebx, eax
0x18004e9b6  test    eax, eax
0x18004e9b8  js      short loc_18004EA02
0x18004e9ba  mov     rcx, [rsp+4E0h+StringSid]; hMem
0x18004e9bf  test    rcx, rcx
0x18004e9c2  jz      loc_18004E7EB
0x18004e9c8  call    cs:__imp_LocalFree
0x18004e9ce  mov     [rsp+4E0h+StringSid], 0
0x18004e9d7  jmp     loc_18004E7EB
0x18004e9dc  mov     ebx, 8007000Eh
0x18004e9e1  jmp     short loc_18004EA02
0x18004e9e3  xor     ebx, ebx
0x18004e9e5  cmp     eax, 80110801h
0x18004e9ea  cmovnz  ebx, eax
0x18004e9ed  test    ebx, ebx
0x18004e9ef  js      short loc_18004EA02
0x18004e9f1  mov     rax, [rsi]
0x18004e9f4  mov     rcx, rsi
0x18004e9f7  mov     rax, [rax+28h]
0x18004e9fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea00  mov     ebx, eax
0x18004ea02  mov     rcx, [rsp+4E0h+StringSid]; hMem
0x18004ea07  test    rcx, rcx
0x18004ea0a  jz      short loc_18004EA1B
0x18004ea0c  call    cs:__imp_LocalFree
0x18004ea12  mov     [rsp+4E0h+StringSid], 0
0x18004ea1b  mov     rcx, [rsp+4E0h+var_488]
0x18004ea20  test    rcx, rcx
0x18004ea23  jz      short loc_18004EA31
0x18004ea25  mov     rax, [rcx]
0x18004ea28  mov     rax, [rax+10h]
0x18004ea2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ea31  mov     eax, ebx
0x18004ea33  mov     rcx, [rbp+3E0h+var_20]
0x18004ea3a  xor     rcx, rsp; StackCookie
0x18004ea3d  call    __security_check_cookie
0x18004ea42  lea     r11, [rsp+4E0h+var_10]
0x18004ea4a  mov     rbx, [r11+28h]
0x18004ea4e  mov     rsi, [r11+30h]
0x18004ea52  mov     rsp, r11
0x18004ea55  pop     r14
0x18004ea57  pop     rdi
0x18004ea58  pop     rbp
0x18004ea59  retn
```
