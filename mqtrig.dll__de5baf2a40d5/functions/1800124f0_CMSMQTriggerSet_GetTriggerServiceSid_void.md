# CMSMQTriggerSet::GetTriggerServiceSid(void * *)

- ea: `0x1800124f0`
- end: `0x1800126bd`
- name: `?GetTriggerServiceSid@CMSMQTriggerSet@@AEAAJPEAPEAX@Z`
- size: `461`
- prototype: `__int64 __fastcall(CMSMQTriggerSet *__hidden this, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x180012d10`

## callees

- `0x1800124f0`
- `0x180012c84`
- `0x180013b2c`
- `0x180014ae8`
- `0x18001e35a`
- `0x18001e380`

## import_xrefs

- `msvcrt!free` at `0x180012576`
- `msvcrt!free` at `0x180012629`
- `msvcrt!free` at `0x180012633`
- `msvcrt!free` at `0x18001264d`
- `msvcrt!free` at `0x180012656`
- `msvcrt!free` at `0x180012664`
- `msvcrt!free` at `0x18001266e`
- `msvcrt!free` at `0x18001267c`
- `msvcrt!free` at `0x180012688`
- `msvcrt!free` at `0x180012576`
- `msvcrt!free` at `0x180012629`
- `msvcrt!free` at `0x180012633`
- `msvcrt!free` at `0x18001264d`
- `msvcrt!free` at `0x180012656`
- `msvcrt!free` at `0x180012664`
- `msvcrt!free` at `0x18001266e`
- `msvcrt!free` at `0x18001267c`
- `msvcrt!free` at `0x180012688`
- `KERNEL32!GetLastError` at `0x180012603`
- `KERNEL32!GetLastError` at `0x180012603`
- `ADVAPI32!LookupAccountNameW` at `0x1800125fa`
- `ADVAPI32!LookupAccountNameW` at `0x1800125fa`

## string_xrefs

- `0x180012534`: `NT SERVICE\%s`

## pseudocode

```c
__int64 __fastcall CMSMQTriggerSet::GetTriggerServiceSid(CMSMQTriggerSet *this, void **a2)
{
  __int64 result; // rax
  void *v4; // rbx
  void *ReferencedDomainName; // rsi
  BOOL v6; // r14d
  signed int LastError; // eax
  unsigned int v8; // edi
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-1D8h] BYREF
  DWORD cbSid; // [rsp+44h] [rbp-1D4h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-1D0h] BYREF
  void *Block; // [rsp+50h] [rbp-1C8h] BYREF
  void *v13; // [rsp+58h] [rbp-1C0h]
  WCHAR AccountName[200]; // [rsp+60h] [rbp-1B8h] BYREF

  memset_0(AccountName, 0, sizeof(AccountName));
  result = StringCchPrintfW(AccountName, 0xC8u, L"NT SERVICE\\%s", &String1);
  if ( (int)result >= 0 )
  {
    v4 = 0;
    cbSid = 128;
    Block = 0;
    cchReferencedDomainName = 128;
    peUse = 0;
    do
    {
      v13 = 0;
      free(v4);
      AP<wchar_t>::free(&Block);
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        v4 = MmAllocate(cbSid);
        v13 = v4;
        ReferencedDomainName = MmAllocate(saturated_mul(cchReferencedDomainName, 2u));
        Block = ReferencedDomainName;
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180012677);
          free(Block);
          free(v13);
          return 3222143015LL;
        }
      }
      if ( !v4 || !ReferencedDomainName )
      {
        free(ReferencedDomainName);
        free(v4);
        return 3222143015LL;
      }
      v6 = LookupAccountNameW(
             0,
             AccountName,
             v4,
             &cbSid,
             (LPWSTR)ReferencedDomainName,
             &cchReferencedDomainName,
             &peUse);
      LastError = GetLastError();
      v8 = LastError;
    }
    while ( LastError == 122 );
    if ( v6 )
    {
      v13 = 0;
      *a2 = v4;
      free(ReferencedDomainName);
      free(0);
      return 0;
    }
    else
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      free(ReferencedDomainName);
      free(v4);
      return v8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800124f0  mov     [rsp+arg_0], rbx
0x1800124f5  mov     [rsp+arg_10], rsi
0x1800124fa  push    rdi
0x1800124fb  push    r14
0x1800124fd  push    r15
0x1800124ff  sub     rsp, 200h
0x180012506  mov     rax, cs:__security_cookie
0x18001250d  xor     rax, rsp
0x180012510  mov     [rsp+218h+var_28], rax
0x180012518  mov     r15, rdx
0x18001251b  xor     edx, edx; Val
0x18001251d  mov     r8d, 190h; Size
0x180012523  lea     rcx, [rsp+218h+AccountName]; void *
0x180012528  call    memset_0
0x18001252d  lea     r9, String1
0x180012534  lea     r8, aNtServiceS; "NT SERVICE\\%s"
0x18001253b  mov     edx, 0C8h; unsigned __int64
0x180012540  lea     rcx, [rsp+218h+AccountName]; wchar_t *
0x180012545  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001254a  test    eax, eax
0x18001254c  js      loc_180012694
0x180012552  xor     ebx, ebx
0x180012554  mov     eax, 80h
0x180012559  mov     [rsp+218h+cbSid], eax
0x18001255d  mov     [rsp+218h+Block], rbx
0x180012562  mov     [rsp+218h+var_1D8], eax
0x180012566  mov     [rsp+218h+var_1D0], ebx
0x18001256a  mov     [rsp+218h+var_1C0], 0
0x180012573  mov     rcx, rbx; Block
0x180012576  call    cs:__imp_free
0x18001257c  nop
0x18001257d  lea     rcx, [rsp+218h+Block]
0x180012582  call    ?free@?$AP@_W@@QEAAXXZ; AP<wchar_t>::free(void)
0x180012587  nop
0x180012588  mov     ecx, [rsp+218h+cbSid]; unsigned __int64
0x18001258c  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180012591  mov     rbx, rax
0x180012594  mov     [rsp+218h+var_1C0], rax
0x180012599  mov     ecx, [rsp+218h+var_1D8]
0x18001259d  mov     eax, 2
0x1800125a2  mul     rcx
0x1800125a5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800125ac  cmovb   rax, rcx
0x1800125b0  mov     rcx, rax; unsigned __int64
0x1800125b3  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800125b8  mov     rsi, rax
0x1800125bb  mov     [rsp+218h+Block], rax
0x1800125c0  test    rbx, rbx
0x1800125c3  jz      loc_180012661
0x1800125c9  test    rsi, rsi
0x1800125cc  jz      loc_180012661
0x1800125d2  lea     rax, [rsp+218h+var_1D0]
0x1800125d7  mov     [rsp+218h+peUse], rax; peUse
0x1800125dc  lea     rax, [rsp+218h+var_1D8]
0x1800125e1  mov     [rsp+218h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800125e6  mov     [rsp+218h+ReferencedDomainName], rsi; ReferencedDomainName
0x1800125eb  lea     r9, [rsp+218h+cbSid]; cbSid
0x1800125f0  mov     r8, rbx; Sid
0x1800125f3  lea     rdx, [rsp+218h+AccountName]; lpAccountName
0x1800125f8  xor     ecx, ecx; lpSystemName
0x1800125fa  call    cs:__imp_LookupAccountNameW
0x180012600  mov     r14d, eax
0x180012603  call    cs:__imp_GetLastError
0x180012609  mov     edi, eax
0x18001260b  cmp     eax, 7Ah ; 'z'
0x18001260e  jz      loc_18001256A
0x180012614  test    r14d, r14d
0x180012617  jnz     short loc_18001263E
0x180012619  test    eax, eax
0x18001261b  jle     short loc_180012626
0x18001261d  movzx   edi, ax
0x180012620  or      edi, 80070000h
0x180012626  mov     rcx, rsi; Block
0x180012629  call    cs:__imp_free
0x18001262f  nop
0x180012630  mov     rcx, rbx; Block
0x180012633  call    cs:__imp_free
0x180012639  nop
0x18001263a  mov     eax, edi
0x18001263c  jmp     short loc_180012694
0x18001263e  mov     [rsp+218h+var_1C0], 0
0x180012647  mov     [r15], rbx
0x18001264a  mov     rcx, rsi; Block
0x18001264d  call    cs:__imp_free
0x180012653  nop
0x180012654  xor     ecx, ecx; Block
0x180012656  call    cs:__imp_free
0x18001265c  nop
0x18001265d  xor     eax, eax
0x18001265f  jmp     short loc_180012694
0x180012661  mov     rcx, rsi; Block
0x180012664  call    cs:__imp_free
0x18001266a  nop
0x18001266b  mov     rcx, rbx; Block
0x18001266e  call    cs:__imp_free
0x180012674  nop
0x180012675  jmp     short loc_18001268F
0x180012677  mov     rcx, [rsp+218h+Block]; Block
0x18001267c  call    cs:__imp_free
0x180012682  nop
0x180012683  mov     rcx, [rsp+218h+var_1C0]; Block
0x180012688  call    cs:__imp_free
0x18001268e  nop
0x18001268f  mov     eax, 0C00E0027h
0x180012694  mov     rcx, [rsp+218h+var_28]
0x18001269c  xor     rcx, rsp; StackCookie
0x18001269f  call    __security_check_cookie
0x1800126a4  lea     r11, [rsp+218h+var_18]
0x1800126ac  mov     rbx, [r11+20h]
0x1800126b0  mov     rsi, [r11+30h]
0x1800126b4  mov     rsp, r11
0x1800126b7  pop     r15
0x1800126b9  pop     r14
0x1800126bb  pop     rdi
0x1800126bc  retn
```
