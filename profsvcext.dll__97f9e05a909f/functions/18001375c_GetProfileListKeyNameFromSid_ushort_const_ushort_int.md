# GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)

- ea: `0x18001375c`
- end: `0x1800138a3`
- name: `?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z`
- size: `327`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, int *)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180016ef8`
- `0x180016ff8`
- `0x180019f14`
- `0x18001a1e4`

## callees

- `0x180005424`
- `0x180006a9c`
- `0x180012d70`
- `0x180012e0c`
- `0x18001375c`
- `0x180013938`
- `0x180015534`
- `0x1800167e0`

## string_xrefs

- `0x18001385d`: `onecore\internal\ds\inc\profiles\sid.h`

## pseudocode

```c
__int64 __fastcall GetProfileListKeyNameFromSid(const unsigned __int16 *a1, unsigned __int16 **a2, int *a3)
{
  int *v5; // rdx
  int UserProfileListRootKeyName; // eax
  unsigned int v7; // ebx
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  int v10; // eax
  unsigned __int16 *v12; // [rsp+20h] [rbp-28h] BYREF
  __int64 v13; // [rsp+28h] [rbp-20h]
  __int64 v14; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a2 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  if ( StringIsEqual(a1, L"S-1-5-18")
    || StringIsEqual(a1, L"S-1-5-19")
    || StringIsEqual(a1, L"S-1-5-20")
    || StringIsEqual(a1, L"S-1-5-93-2-1")
    || StringIsEqual(a1, L"S-1-5-93-2-2") )
  {
    UserProfileListRootKeyName = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Initialize(
                                   &v12,
                                   L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
                                   -1);
  }
  else
  {
    Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64 *)&v12);
    v13 = -1;
    v14 = -1;
    UserProfileListRootKeyName = GetUserProfileListRootKeyName(&v12, v5);
  }
  v7 = UserProfileListRootKeyName;
  if ( UserProfileListRootKeyName >= 0 )
  {
    v10 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
            &v12,
            L"\\%s",
            a1);
    v7 = v10;
    if ( v10 >= 0 )
    {
      v10 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::CopyTo(
              (__int64 *)&v12,
              a2);
      v7 = v10;
      if ( v10 >= 0 )
      {
        v7 = 0;
        goto LABEL_17;
      }
      v9 = 130;
    }
    else
    {
      v9 = 129;
    }
    v8 = (unsigned int)v10;
  }
  else
  {
    v8 = (unsigned int)UserProfileListRootKeyName;
    v9 = 128;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\internal\\ds\\inc\\profiles\\sid.h",
    (const char *)v8,
    (int)v12);
LABEL_17:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64 *)&v12);
  return v7;
}

```

## disassembly

```asm
0x18001375c  mov     rax, rsp
0x18001375f  mov     [rax+8], rbx
0x180013763  mov     [rax+10h], rsi
0x180013767  push    rdi
0x180013768  sub     rsp, 40h
0x18001376c  mov     rsi, rdx
0x18001376f  mov     rdi, rcx
0x180013772  mov     qword ptr [rdx], 0
0x180013779  mov     qword ptr [rax-28h], 0
0x180013781  mov     qword ptr [rax-20h], 0
0x180013789  mov     qword ptr [rax-18h], 0
0x180013791  lea     rdx, aS1518; "S-1-5-18"
0x180013798  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x18001379d  test    eax, eax
0x18001379f  jnz     short loc_180013811
0x1800137a1  lea     rdx, aS1519; "S-1-5-19"
0x1800137a8  mov     rcx, rdi; unsigned __int16 *
0x1800137ab  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x1800137b0  test    eax, eax
0x1800137b2  jnz     short loc_180013811
0x1800137b4  lea     rdx, aS1520; "S-1-5-20"
0x1800137bb  mov     rcx, rdi; unsigned __int16 *
0x1800137be  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x1800137c3  test    eax, eax
0x1800137c5  jnz     short loc_180013811
0x1800137c7  lea     rdx, aS159321; "S-1-5-93-2-1"
0x1800137ce  mov     rcx, rdi; unsigned __int16 *
0x1800137d1  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x1800137d6  test    eax, eax
0x1800137d8  jnz     short loc_180013811
0x1800137da  lea     rdx, aS159322; "S-1-5-93-2-2"
0x1800137e1  mov     rcx, rdi; unsigned __int16 *
0x1800137e4  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x1800137e9  test    eax, eax
0x1800137eb  jnz     short loc_180013811
0x1800137ed  lea     rcx, [rsp+48h+var_28]
0x1800137f2  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800137f7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800137fb  mov     [rsp+48h+var_20], r8
0x180013800  mov     [rsp+48h+var_18], r8
0x180013805  lea     rcx, [rsp+48h+var_28]; unsigned __int16 **
0x18001380a  call    ?GetUserProfileListRootKeyName@@YAJPEAPEAGPEAH@Z; GetUserProfileListRootKeyName(ushort * *,int *)
0x18001380f  jmp     short loc_180013826
0x180013811  or      r8, 0FFFFFFFFFFFFFFFFh
0x180013815  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001381c  lea     rcx, [rsp+48h+var_28]
0x180013821  call    ?_Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180013826  mov     ebx, eax
0x180013828  test    eax, eax
0x18001382a  jns     short loc_180013836
0x18001382c  mov     r9d, eax
0x18001382f  mov     edx, 80h
0x180013834  jmp     short loc_180013858
0x180013836  mov     r8, rdi
0x180013839  lea     rdx, aS_0; "\\%s"
0x180013840  lea     rcx, [rsp+48h+var_28]
0x180013845  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x18001384a  mov     ebx, eax
0x18001384c  test    eax, eax
0x18001384e  jns     short loc_18001386B
0x180013850  mov     edx, 81h; void *
0x180013855  mov     r9d, eax; char *
0x180013858  mov     rcx, [rsp+48h]; this
0x18001385d  lea     r8, aOnecoreInterna_4; "onecore\\internal\\ds\\inc\\profiles\\s"...
0x180013864  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013869  jmp     short loc_180013887
0x18001386b  mov     rdx, rsi
0x18001386e  lea     rcx, [rsp+48h+var_28]
0x180013873  call    ?CopyTo@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAJPEAPEAG@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::CopyTo(ushort * *)
0x180013878  mov     ebx, eax
0x18001387a  test    eax, eax
0x18001387c  jns     short loc_180013885
0x18001387e  mov     edx, 82h
0x180013883  jmp     short loc_180013855
0x180013885  xor     ebx, ebx
0x180013887  lea     rcx, [rsp+48h+var_28]
0x18001388c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180013891  mov     eax, ebx
0x180013893  mov     rbx, [rsp+48h+arg_0]
0x180013898  mov     rsi, [rsp+48h+arg_8]
0x18001389d  add     rsp, 40h
0x1800138a1  pop     rdi
0x1800138a2  retn
```
