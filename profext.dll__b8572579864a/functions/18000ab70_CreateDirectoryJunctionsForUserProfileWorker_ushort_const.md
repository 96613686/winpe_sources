# CreateDirectoryJunctionsForUserProfileWorker(ushort const *)

- ea: `0x18000ab70`
- end: `0x18000ad71`
- name: `?CreateDirectoryJunctionsForUserProfileWorker@@YAJPEBG@Z`
- size: `513`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180004594`
- `0x18000ab70`
- `0x18000ad78`
- `0x18000b7e0`
- `0x18000c440`
- `0x18000eed0`
- `0x18000f8b0`
- `0x18000f8e4`
- `0x18000f9f8`
- `0x18001b914`
- `0x18001cdac`

## string_xrefs

- `0x18000aca6`: `onecore\ds\security\gina\profile\profext\dirjunc.cpp`
- `0x18000acf3`: `onecore\ds\security\gina\profile\profext\dirjunc.cpp`
- `0x18000ad2a`: `onecore\ds\security\gina\profile\profext\dirjunc.cpp`
- `0x18000ad4c`: `onecore\ds\security\gina\profile\profext\dirjunc.cpp`

## pseudocode

```c
__int64 __fastcall CreateDirectoryJunctionsForUserProfileWorker(const unsigned __int16 *a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  unsigned int i; // ebx
  __int64 v5; // r14
  int v6; // esi
  int v7; // eax
  unsigned __int16 *v8; // rsi
  char *v9; // r14
  int DirectoryJunction; // eax
  __int64 v12; // rdx
  int v13; // [rsp+20h] [rbp-39h]
  int v14; // [rsp+20h] [rbp-39h]
  char *v15[3]; // [rsp+30h] [rbp-29h] BYREF
  unsigned __int16 *v16[3]; // [rsp+48h] [rbp-11h] BYREF
  char v17[8]; // [rsp+60h] [rbp+7h] BYREF
  char v18[72]; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  CUserACLApplicator::CUserACLApplicator((CUserACLApplicator *)v17);
  v2 = CUserACLApplicator::Init((CUserACLApplicator *)v17);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\dirjunc.cpp",
      (const char *)(unsigned int)v2,
      v13);
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= 0x12 )
      {
        v3 = 0;
        goto LABEL_17;
      }
      memset(v15, 0, sizeof(v15));
      v5 = 4LL * i;
      v6 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
             v15,
             L"%s%s",
             a1,
             (&off_180025BE8)[v5]);
      if ( v6 < 0 )
        break;
      if ( LODWORD(qword_180025BF0[v5]) )
      {
        v6 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Concat(
               v15,
               &_ImageBase);
        if ( v6 < 0 )
        {
          v12 = 258;
          goto LABEL_23;
        }
      }
      memset(v16, 0, sizeof(v16));
      v7 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
             v16,
             L"%s%s",
             a1,
             (&off_180025BF8)[v5]);
      v6 = v7;
      if ( v7 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x106,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\dirjunc.cpp",
          (const char *)(unsigned int)v7,
          v13);
        Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v16);
        goto LABEL_24;
      }
      v14 = qword_180025BE0[v5];
      v8 = v16[0];
      v9 = v15[0];
      DirectoryJunction = CreateDirectoryJunction(
                            v15[0],
                            v16[0],
                            v16[0],
                            (const struct CAACLApplicator *)v17,
                            v14,
                            &FOLDERID_UserProfiles);
      if ( DirectoryJunction != -2147024893 && DirectoryJunction != -2147024713 && DirectoryJunction < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x10C,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\dirjunc.cpp",
          (const char *)(unsigned int)DirectoryJunction,
          v13);
      if ( v8 )
        Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v8);
      if ( v9 )
        Windows::Internal::ProcessHeapMemPolicy<unsigned short>::Free(v9);
    }
    v12 = 254;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\dirjunc.cpp",
      (const char *)(unsigned int)v6,
      v13);
LABEL_24:
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v15);
    v3 = v6;
  }
LABEL_17:
  wil::unique_any_array_ptr<unsigned char,std::default_delete<unsigned char [0]>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<unsigned char,std::default_delete<unsigned char [0]>,wil::empty_deleter,unsigned __int64>(v18);
  return v3;
}

```

## disassembly

```asm
0x18000ab70  push    rbp
0x18000ab72  push    rbx
0x18000ab73  push    rsi
0x18000ab74  push    r13
0x18000ab76  push    r14
0x18000ab78  push    r15
0x18000ab7a  lea     rbp, [rsp-2Fh]
0x18000ab7f  sub     rsp, 88h
0x18000ab86  mov     r15, rcx
0x18000ab89  lea     rcx, [rbp+57h+var_50]; this
0x18000ab8d  call    ??0CUserACLApplicator@@QEAA@XZ; CUserACLApplicator::CUserACLApplicator(void)
0x18000ab92  nop
0x18000ab93  lea     rcx, [rbp+57h+var_50]; this
0x18000ab97  call    ?Init@CUserACLApplicator@@UEAAJXZ; CUserACLApplicator::Init(void)
0x18000ab9c  mov     ebx, eax
0x18000ab9e  test    eax, eax
0x18000aba0  js      loc_18000ACEC
0x18000aba6  xor     ebx, ebx
0x18000aba8  lea     r13, __ImageBase
0x18000abaf  cmp     ebx, 12h
0x18000abb2  jnb     loc_18000ACCD
0x18000abb8  mov     [rbp+57h+var_80], 0
0x18000abc0  mov     [rbp+57h+var_78], 0
0x18000abc8  mov     [rbp+57h+var_70], 0
0x18000abd0  mov     r14d, ebx
0x18000abd3  shl     r14, 5
0x18000abd7  mov     r9, [r14+r13+25BE8h]
0x18000abdf  mov     r8, r15
0x18000abe2  lea     rdx, aSS_0; "%s%s"
0x18000abe9  lea     rcx, [rbp+57h+var_80]
0x18000abed  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000abf2  mov     esi, eax
0x18000abf4  test    eax, eax
0x18000abf6  js      loc_18000AD47
0x18000abfc  mov     r8d, [r14+r13+25BF0h]
0x18000ac04  test    r8d, r8d
0x18000ac07  jnz     loc_18000AD06
0x18000ac0d  mov     [rbp+57h+var_68], 0
0x18000ac15  mov     [rbp+57h+var_60], 0
0x18000ac1d  mov     [rbp+57h+var_58], 0
0x18000ac25  mov     r9, [r14+r13+25BF8h]
0x18000ac2d  mov     r8, r15
0x18000ac30  lea     rdx, aSS_0; "%s%s"
0x18000ac37  lea     rcx, [rbp+57h+var_68]
0x18000ac3b  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18000ac40  mov     esi, eax
0x18000ac42  test    eax, eax
0x18000ac44  js      loc_18000AD23
0x18000ac4a  lea     rax, FOLDERID_UserProfiles
0x18000ac51  mov     [rsp+0B0h+var_88], rax; struct _GUID *
0x18000ac56  mov     eax, [r14+r13+25BE0h]
0x18000ac5e  mov     [rsp+0B0h+var_90], eax; int
0x18000ac62  lea     r9, [rbp+57h+var_50]; struct CAACLApplicator *
0x18000ac66  mov     rsi, [rbp+57h+var_68]
0x18000ac6a  mov     r8, rsi; unsigned __int16 *
0x18000ac6d  mov     rdx, rsi; unsigned __int16 *
0x18000ac70  mov     r14, [rbp+57h+var_80]
0x18000ac74  mov     rcx, r14; char *
0x18000ac77  call    ?CreateDirectoryJunction@@YAJPEBG00AEBVCAACLApplicator@@HAEBU_GUID@@@Z; CreateDirectoryJunction(ushort const *,ushort const *,ushort const *,CAACLApplicator const &,int,_GUID const &)
0x18000ac7c  cmp     eax, 80070003h
0x18000ac81  jnz     short loc_18000AC94
0x18000ac83  test    rsi, rsi
0x18000ac86  jnz     short loc_18000ACB9
0x18000ac88  test    r14, r14
0x18000ac8b  jnz     short loc_18000ACC3
0x18000ac8d  inc     ebx
0x18000ac8f  jmp     loc_18000ABAF
0x18000ac94  cmp     eax, 800700B7h
0x18000ac99  jz      short loc_18000AC83
0x18000ac9b  mov     rcx, [rbp+5Fh]; this
0x18000ac9f  test    eax, eax
0x18000aca1  jns     short loc_18000AC83
0x18000aca3  mov     r9d, eax; char *
0x18000aca6  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000acad  mov     edx, 10Ch; void *
0x18000acb2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000acb7  jmp     short loc_18000AC83
0x18000acb9  mov     rcx, rsi
0x18000acbc  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18000acc1  jmp     short loc_18000AC88
0x18000acc3  mov     rcx, r14
0x18000acc6  call    ?Free@?$ProcessHeapMemPolicy@G@Internal@Windows@@SAXPEAG@Z; Windows::Internal::ProcessHeapMemPolicy<ushort>::Free(ushort *)
0x18000accb  jmp     short loc_18000AC8D
0x18000accd  xor     ebx, ebx
0x18000accf  lea     rcx, [rbp+57h+var_48]
0x18000acd3  call    ??1?$unique_any_array_ptr@EU?$default_delete@$$BY0A@E@std@@Uempty_deleter@wil@@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<uchar,std::default_delete<uchar [0]>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<uchar,std::default_delete<uchar [0]>,wil::empty_deleter,unsigned __int64>(void)
0x18000acd8  mov     eax, ebx
0x18000acda  add     rsp, 88h
0x18000ace1  pop     r15
0x18000ace3  pop     r14
0x18000ace5  pop     r13
0x18000ace7  pop     rsi
0x18000ace8  pop     rbx
0x18000ace9  pop     rbp
0x18000acea  retn
0x18000acec  mov     rcx, [rbp+5Fh]; this
0x18000acf0  mov     r9d, eax; char *
0x18000acf3  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000acfa  mov     edx, 0F9h; void *
0x18000acff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ad04  jmp     short loc_18000ACCF
0x18000ad06  mov     rdx, r13
0x18000ad09  lea     rcx, [rbp+57h+var_80]
0x18000ad0d  call    ?Concat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Concat(HINSTANCE__ *,uint,ushort)
0x18000ad12  mov     esi, eax
0x18000ad14  test    eax, eax
0x18000ad16  jns     loc_18000AC0D
0x18000ad1c  mov     edx, 102h
0x18000ad21  jmp     short loc_18000AD4C
0x18000ad23  mov     rcx, [rbp+5Fh]; this
0x18000ad27  mov     r9d, esi; char *
0x18000ad2a  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000ad31  mov     edx, 106h; void *
0x18000ad36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ad3b  nop
0x18000ad3c  lea     rcx, [rbp+57h+var_68]
0x18000ad40  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000ad45  jmp     short loc_18000AD60
0x18000ad47  mov     edx, 0FEh; void *
0x18000ad4c  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000ad53  mov     r9d, esi; char *
0x18000ad56  mov     rcx, [rbp+5Fh]; this
0x18000ad5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ad5f  nop
0x18000ad60  lea     rcx, [rbp+57h+var_80]
0x18000ad64  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000ad69  mov     ebx, esi
0x18000ad6b  jmp     loc_18000ACCF
```
