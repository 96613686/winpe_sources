# CUserProfileManager::RetrieveRegKeyHandlesForUser(ushort const *,void * *,void * *)

- ea: `0x1800277fc`
- end: `0x180027933`
- name: `?RetrieveRegKeyHandlesForUser@CUserProfileManager@@QEAAJPEBGPEAPEAX1@Z`
- size: `311`
- prototype: `int(CUserProfileManager *__hidden this, const unsigned __int16 *, void **, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180008fa0`

## callees

- `0x1800277fc`
- `0x18002793c`
- `0x18002df48`
- `0x180054128`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027881`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180027881`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002790d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002790d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800278a7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800278a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002786b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002786b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180027839`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180027839`

## string_xrefs

- `0x18002784e`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfileManager::RetrieveRegKeyHandlesForUser(
        CUserProfileManager *this,
        const unsigned __int16 *a2,
        void **a3,
        void **a4)
{
  PSRWLOCK v4; // rbx
  const char *v7; // r9
  unsigned int LastError; // ebx
  unsigned int i; // esi
  __int64 v11; // r14
  unsigned __int64 Ptr; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  PSID Sid; // [rsp+60h] [rbp+8h] BYREF

  v4 = g_pProfMgr;
  *a3 = 0;
  *a4 = 0;
  Sid = 0;
  if ( ConvertStringSidToSidW(a2, &Sid) )
  {
    AcquireSRWLockExclusive(v4);
    for ( i = 0; (PVOID)i < v4[2].Ptr; ++i )
    {
      v11 = 88LL * i;
      if ( EqualSid(Sid, (char *)v4[1].Ptr + v11) )
      {
        *a3 = *(void **)((char *)v4[1].Ptr + v11 + 72);
        *a4 = *(void **)((char *)v4[1].Ptr + v11 + 80);
        Ptr = (unsigned __int64)v4[2].Ptr;
        if ( i < Ptr )
        {
          if ( i != Ptr - 1 )
            memmove_0((char *)v4[1].Ptr + v11, (char *)v4[1].Ptr + v11 + 88, 88 * (Ptr - i) - 88);
          --v4[2].Ptr;
        }
        break;
      }
    }
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
    return 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xC2,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
                  v7);
    if ( Sid )
      LocalFree(Sid);
    return LastError;
  }
}

```

## disassembly

```asm
0x1800277fc  mov     [rsp+Sid], rcx
0x180027801  push    rbx
0x180027802  push    rbp
0x180027803  push    rsi
0x180027804  push    rdi
0x180027805  push    r14
0x180027807  push    r15
0x180027809  sub     rsp, 28h
0x18002780d  mov     rbx, cs:?g_pProfMgr@@3PEAVCUserProfileManager@@EA; CUserProfileManager * g_pProfMgr
0x180027814  mov     rcx, rdx; StringSid
0x180027817  mov     qword ptr [r8], 0
0x18002781e  lea     rdx, [rsp+58h+Sid]; Sid
0x180027823  mov     r15, r9
0x180027826  mov     qword ptr [r9], 0
0x18002782d  mov     rbp, r8
0x180027830  mov     [rsp+58h+Sid], 0
0x180027839  call    cs:__imp_ConvertStringSidToSidW
0x180027840  nop     dword ptr [rax+rax+00h]
0x180027845  test    eax, eax
0x180027847  jnz     short loc_18002787E
0x180027849  mov     rcx, [rsp+58h]; this
0x18002784e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180027855  mov     edx, 0C2h; void *
0x18002785a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002785f  mov     rcx, [rsp+58h+Sid]; hMem
0x180027864  mov     ebx, eax
0x180027866  test    rcx, rcx
0x180027869  jz      short loc_180027877
0x18002786b  call    cs:__imp_LocalFree
0x180027872  nop     dword ptr [rax+rax+00h]
0x180027877  mov     eax, ebx
0x180027879  jmp     loc_180027925
0x18002787e  mov     rcx, rbx; SRWLock
0x180027881  call    cs:__imp_AcquireSRWLockExclusive
0x180027888  nop     dword ptr [rax+rax+00h]
0x18002788d  xor     esi, esi
0x18002788f  mov     edi, esi
0x180027891  cmp     rdi, [rbx+10h]
0x180027895  jnb     short loc_180027905
0x180027897  mov     rdx, [rbx+8]
0x18002789b  mov     rcx, [rsp+58h+Sid]; pSid1
0x1800278a0  imul    r14, rdi, 58h ; 'X'
0x1800278a4  add     rdx, r14; pSid2
0x1800278a7  call    cs:__imp_EqualSid
0x1800278ae  nop     dword ptr [rax+rax+00h]
0x1800278b3  test    eax, eax
0x1800278b5  jnz     short loc_1800278BB
0x1800278b7  inc     esi
0x1800278b9  jmp     short loc_18002788F
0x1800278bb  mov     rax, [rbx+8]
0x1800278bf  mov     rcx, [r14+rax+48h]
0x1800278c4  mov     [rbp+0], rcx
0x1800278c8  mov     rax, [rbx+8]
0x1800278cc  mov     rcx, [r14+rax+50h]
0x1800278d1  mov     [r15], rcx
0x1800278d4  mov     rdx, [rbx+10h]
0x1800278d8  cmp     rdi, rdx
0x1800278db  jnb     short loc_180027905
0x1800278dd  lea     rax, [rdx-1]
0x1800278e1  cmp     rdi, rax
0x1800278e4  jz      short loc_180027901
0x1800278e6  mov     rcx, [rbx+8]
0x1800278ea  sub     rdx, rdi
0x1800278ed  imul    r8, rdx, 58h ; 'X'
0x1800278f1  add     rcx, r14; void *
0x1800278f4  sub     r8, 58h ; 'X'; Size
0x1800278f8  lea     rdx, [rcx+58h]; Src
0x1800278fc  call    memmove_0
0x180027901  dec     qword ptr [rbx+10h]
0x180027905  test    rbx, rbx
0x180027908  jz      short loc_180027919
0x18002790a  mov     rcx, rbx; SRWLock
0x18002790d  call    cs:__imp_ReleaseSRWLockExclusive
0x180027914  nop     dword ptr [rax+rax+00h]
0x180027919  lea     rcx, [rsp+58h+Sid]
0x18002791e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180027923  xor     eax, eax
0x180027925  add     rsp, 28h
0x180027929  pop     r15
0x18002792b  pop     r14
0x18002792d  pop     rdi
0x18002792e  pop     rsi
0x18002792f  pop     rbp
0x180027930  pop     rbx
0x180027931  retn
```
