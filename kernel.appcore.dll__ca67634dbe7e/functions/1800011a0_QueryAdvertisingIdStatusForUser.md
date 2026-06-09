# QueryAdvertisingIdStatusForUser

- ea: `0x1800011a0`
- end: `0x18000136c`
- name: `QueryAdvertisingIdStatusForUser`
- size: `460`
- prototype: `__int64 __fastcall(LPCWSTR StringSid)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800011a0`
- `0x180001610`
- `0x180001920`
- `0x180001af0`
- `0x180001d20`
- `0x180006324`

## import_xrefs

- `api-ms-win-privacy-coreprivacysettingsstore-l1-1-0!CPSSGetDwordSetting` at `0x180001260`
- `api-ms-win-privacy-coreprivacysettingsstore-l1-1-0!CPSSGetDwordSetting` at `0x180001260`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000123e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000123e`

## pseudocode

```c
__int64 __fastcall QueryAdvertisingIdStatusForUser(WCHAR *StringSid, bool *a2, int *a3)
{
  int v4; // edi
  int v7; // eax
  bool *v8; // rdx
  unsigned int v9; // ebx
  int v10; // eax
  bool *v11; // rdx
  int v12; // eax
  PSID v13; // rdx
  int v14; // eax
  const unsigned __int16 *v15; // rdx
  int v16; // esi
  int v17; // eax
  int v19; // [rsp+20h] [rbp-38h]
  char v20; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v21[3]; // [rsp+31h] [rbp-27h] BYREF
  int v22; // [rsp+34h] [rbp-24h] BYREF
  PSID Sid; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  char v25; // [rsp+78h] [rbp+20h] BYREF

  v25 = 0;
  v4 = 1;
  v20 = 0;
  v22 = 1;
  v21[0] = 0;
  v7 = AdvertisingIdHelpers::CheckGroupPolicy((AdvertisingIdHelpers *)&v25, a2);
  v9 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x231,
      (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
      (const char *)(unsigned int)v7,
      v19);
  }
  else
  {
    if ( v25 )
    {
      v16 = 2;
    }
    else
    {
      v10 = AdvertisingIdHelpers::CheckChildAccount((AdvertisingIdHelpers *)&v20, v8);
      v9 = v10;
      if ( v10 == -2147221164 )
        goto LABEL_4;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x242,
          (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
          (const char *)(unsigned int)v10,
          v19);
        return v9;
      }
      if ( !v20 )
      {
LABEL_4:
        v12 = AdvertisingIdHelpers::CheckMsaChildAccount((AdvertisingIdHelpers *)v21, v11);
        v9 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x24C,
            (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
            (const char *)(unsigned int)v12,
            v19);
          return v9;
        }
        if ( v21[0] )
        {
          v16 = 2;
          v4 = 2;
        }
        else
        {
          v13 = 0;
          Sid = 0;
          if ( StringSid )
          {
            ConvertStringSidToSidW(StringSid, &Sid);
            v13 = Sid;
          }
          v14 = CPSSGetDwordSetting(1, v13, L"AdvertisingInfo", &v22);
          v9 = v14;
          if ( v14 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x263,
              (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
              (const char *)(unsigned int)v14,
              0);
            return v9;
          }
          v4 = 0;
          v16 = v22 != 0;
          v17 = AdvertisingIdHelpers::EnsureAdvertisingIdAcl(StringSid, v15);
          if ( v17 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x273,
              (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
              (const char *)(unsigned int)v17,
              0);
          v9 = 0;
        }
      }
      else
      {
        v16 = 2;
        v4 = 2;
      }
    }
    *(_DWORD *)a2 = v16;
    if ( a3 )
      *a3 = v4;
  }
  return v9;
}

```

## disassembly

```asm
0x1800011a0  mov     rax, rsp
0x1800011a3  mov     [rax+10h], rbx
0x1800011a7  mov     [rax+18h], rbp
0x1800011ab  push    rdi
0x1800011ac  push    r14
0x1800011ae  push    r15
0x1800011b0  sub     rsp, 40h
0x1800011b4  mov     rbp, rcx
0x1800011b7  mov     byte ptr [rax+20h], 0
0x1800011bb  mov     edi, 1
0x1800011c0  mov     byte ptr [rax-28h], 0
0x1800011c4  lea     rcx, [rax+20h]; this
0x1800011c8  mov     [rax-24h], edi
0x1800011cb  mov     r14, r8
0x1800011ce  mov     byte ptr [rax-27h], 0
0x1800011d2  mov     r15, rdx
0x1800011d5  call    ?CheckGroupPolicy@AdvertisingIdHelpers@@YAJPEA_N@Z; AdvertisingIdHelpers::CheckGroupPolicy(bool *)
0x1800011da  mov     ebx, eax
0x1800011dc  test    eax, eax
0x1800011de  js      loc_1800012DC
0x1800011e4  cmp     [rsp+58h+arg_18], 0
0x1800011e9  mov     [rsp+58h+arg_0], rsi
0x1800011ee  jnz     loc_180001290
0x1800011f4  lea     rcx, [rsp+58h+var_28]; this
0x1800011f9  call    ?CheckChildAccount@AdvertisingIdHelpers@@YAJPEA_N@Z; AdvertisingIdHelpers::CheckChildAccount(bool *)
0x1800011fe  mov     ebx, eax
0x180001200  cmp     eax, 80040154h
0x180001205  jnz     loc_1800012BB
0x18000120b  lea     rcx, [rsp+58h+var_27]; this
0x180001210  call    ?CheckMsaChildAccount@AdvertisingIdHelpers@@YAJPEA_N@Z; AdvertisingIdHelpers::CheckMsaChildAccount(bool *)
0x180001215  mov     ebx, eax
0x180001217  test    eax, eax
0x180001219  js      loc_180001312
0x18000121f  cmp     [rsp+58h+var_27], 0
0x180001224  jnz     loc_1800012D3
0x18000122a  xor     edx, edx
0x18000122c  mov     [rsp+58h+Sid], rdx
0x180001231  test    rbp, rbp
0x180001234  jz      short loc_180001249
0x180001236  lea     rdx, [rsp+58h+Sid]; Sid
0x18000123b  mov     rcx, rbp; StringSid
0x18000123e  call    cs:__imp_ConvertStringSidToSidW
0x180001244  mov     rdx, [rsp+58h+Sid]
0x180001249  lea     r9, [rsp+58h+var_24]
0x18000124e  mov     qword ptr [rsp+58h+var_38], 0; int
0x180001257  lea     r8, aAdvertisinginf; "AdvertisingInfo"
0x18000125e  mov     ecx, edi
0x180001260  call    cs:__imp_CPSSGetDwordSetting
0x180001266  mov     ebx, eax
0x180001268  test    eax, eax
0x18000126a  js      loc_180001330
0x180001270  xor     esi, esi
0x180001272  xor     edi, edi
0x180001274  cmp     [rsp+58h+var_24], esi
0x180001278  mov     rcx, rbp; this
0x18000127b  setnz   sil
0x18000127f  call    ?EnsureAdvertisingIdAcl@AdvertisingIdHelpers@@YAJPEBG@Z; AdvertisingIdHelpers::EnsureAdvertisingIdAcl(ushort const *)
0x180001284  test    eax, eax
0x180001286  js      loc_18000134E
0x18000128c  xor     ebx, ebx
0x18000128e  jmp     short loc_180001295
0x180001290  mov     esi, 2
0x180001295  mov     [r15], esi
0x180001298  test    r14, r14
0x18000129b  jz      short loc_1800012A0
0x18000129d  mov     [r14], edi
0x1800012a0  mov     rsi, [rsp+58h+arg_0]
0x1800012a5  mov     rbp, [rsp+58h+arg_10]
0x1800012aa  mov     eax, ebx
0x1800012ac  mov     rbx, [rsp+58h+arg_8]
0x1800012b1  add     rsp, 40h
0x1800012b5  pop     r15
0x1800012b7  pop     r14
0x1800012b9  pop     rdi
0x1800012ba  retn
0x1800012bb  test    ebx, ebx
0x1800012bd  js      short loc_1800012F7
0x1800012bf  cmp     [rsp+58h+var_28], 0
0x1800012c4  jz      loc_18000120B
0x1800012ca  mov     esi, 2
0x1800012cf  mov     edi, esi
0x1800012d1  jmp     short loc_180001295
0x1800012d3  mov     esi, 2
0x1800012d8  mov     edi, esi
0x1800012da  jmp     short loc_180001295
0x1800012dc  mov     rcx, [rsp+58h]; this
0x1800012e1  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x1800012e8  mov     r9d, ebx; char *
0x1800012eb  mov     edx, 231h; void *
0x1800012f0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800012f5  jmp     short loc_1800012A5
0x1800012f7  mov     rcx, [rsp+58h]; this
0x1800012fc  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x180001303  mov     r9d, ebx; char *
0x180001306  mov     edx, 242h; void *
0x18000130b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180001310  jmp     short loc_1800012A0
0x180001312  mov     rcx, [rsp+58h]; this
0x180001317  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x18000131e  mov     r9d, ebx; char *
0x180001321  mov     edx, 24Ch; void *
0x180001326  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000132b  jmp     loc_1800012A0
0x180001330  mov     rcx, [rsp+58h]; this
0x180001335  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x18000133c  mov     r9d, ebx; char *
0x18000133f  mov     edx, 263h; void *
0x180001344  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180001349  jmp     loc_1800012A0
0x18000134e  mov     rcx, [rsp+58h]; this
0x180001353  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x18000135a  mov     r9d, eax; char *
0x18000135d  mov     edx, 273h; void *
0x180001362  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180001367  jmp     loc_18000128C
```
