# CSiteRestriction::InitNew(CSiteRestrCollection *,TLMString<192,64,32767> const &,int,IUrlConverter *)

- ea: `0x1801e00ac`
- end: `0x1801e03ca`
- name: `?InitNew@CSiteRestriction@@QEAAJPEAVCSiteRestrCollection@@AEBV?$TLMString@$0MA@$0EA@$0HPPP@@@HPEAUIUrlConverter@@@Z`
- size: `798`
- prototype: `__int64 __usercall@<rax>(struct CSiteRestriction *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801df0f0`

## callees

- `0x18000e628`
- `0x180049f2c`
- `0x180050ac4`
- `0x180051fe4`
- `0x1800800f4`
- `0x1800904ec`
- `0x1800a1700`
- `0x1800b500c`
- `0x1801010c4`
- `0x180122c78`
- `0x1801244c0`
- `0x180124d80`
- `0x1801decac`
- `0x1801e00ac`
- `0x1801e0bd8`
- `0x1801e0d10`
- `0x1801e0da4`
- `0x180207d48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e01b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e0212`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e01b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e0212`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801e0386`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801e0386`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1801e0360`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1801e0360`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1801e0351`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1801e0351`

## string_xrefs

- `0x1801e01ff`: `Paths`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
signed int __fastcall CSiteRestriction::InitNew(
        struct CSiteRestriction *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        struct IUrlConverter *a5)
{
  signed int result; // eax
  _DWORD *v10; // r15
  void *v11; // rax
  CHostExpression *v12; // rax
  unsigned int v13; // r9d
  struct PConfigNode **v14; // r12
  const wchar_t *v15; // r9
  int v16; // esi
  CAccessControlImpl *v17; // rdi
  __int64 v18; // rdx
  _WORD *v19; // rcx
  __int64 v20; // rax
  PSID Sid[2]; // [rsp+30h] [rbp-138h] BYREF
  struct IUrlConverter *v22; // [rsp+40h] [rbp-128h]
  struct CSiteRestriction *v23; // [rsp+48h] [rbp-120h]
  __int64 v24; // [rsp+50h] [rbp-118h]
  __int64 v25; // [rsp+60h] [rbp-108h]
  __int64 v26; // [rsp+70h] [rbp-F8h] BYREF
  void **v27; // [rsp+80h] [rbp-E8h] BYREF
  LPCWSTR StringSid; // [rsp+88h] [rbp-E0h]
  __int64 v29; // [rsp+90h] [rbp-D8h]
  __int16 v30; // [rsp+98h] [rbp-D0h] BYREF

  v23 = a1;
  v24 = a2;
  v25 = a3;
  LODWORD(Sid[0]) = a4;
  v22 = a5;
  if ( !a2 )
    return -2147467261;
  v10 = (_DWORD *)(a3 + 20);
  v26 = a3 + 20;
  if ( !*(_DWORD *)(a3 + 20) )
    return -2147024809;
  TComNoUnkPointer<CPlugin>::operator=((char *)a1 + 1216, a2);
  v11 = operator new(0x208u, (const struct std::nothrow_t *)&std::nothrow);
  Sid[1] = v11;
  if ( v11 )
    v12 = CHostExpression::CHostExpression((CHostExpression *)v11, *(const wchar_t **)(a3 + 8));
  else
    v12 = 0;
  *((_QWORD *)a1 + 151) = v12;
  if ( !v12 )
    return -2147024882;
  if ( (unsigned int)CConfigNode::CreateSubKey((CConfigNode *)(a2 + 64), *(const wchar_t **)(a3 + 8)) )
  {
    v14 = (struct PConfigNode **)((char *)a1 + 56);
    result = CConfigNode::Init(
               (struct CSiteRestriction *)((char *)a1 + 56),
               (struct CConfigNode *)(a2 + 64),
               *(const wchar_t **)(a3 + 8),
               v13);
    if ( result >= 0 )
    {
      TLMString<192,64,32767>::operator=((char *)a1 + 184, a3);
      if ( (unsigned int)CConfigNode::CreateSubKey((struct CSiteRestriction *)((char *)a1 + 56), L"Paths") )
      {
        result = CSitePathCollection::Init(
                   (struct CSiteRestriction *)((char *)a1 + 968),
                   (const wchar_t *)&cchOriginalDestLength,
                   a1,
                   v15,
                   v22);
        if ( result >= 0 )
        {
          v16 = CSiteRestriction::SetIncluded(a1, a4);
          if ( v16 >= 0 )
          {
            v16 = CSiteRestriction::SetFollowComplexUrls(a1, 0);
            if ( v16 >= 0 )
            {
              v16 = CSiteRestriction::SetApplyToDavHref(a1, 1);
              if ( v16 >= 0 )
              {
                v17 = (struct CSiteRestriction *)((char *)a1 + 696);
                v16 = CAccessControlImpl::Init(v17, *v14, 0, 0);
                if ( v16 >= 0 )
                {
                  StringSid = (LPCWSTR)&v30;
                  v29 = 65;
                  v30 = 0;
                  v27 = &TLMString<64,64,1048576>::`vftable';
                  if ( *v10 > 2u
                    && (v19 = *(_WORD **)(a3 + 8), *v19 == 123)
                    && (v18 = (unsigned int)(*v10 - 1), v19[v18] == 125) )
                  {
                    v20 = CLMString::Mid(a3, &v26, 1);
                    CLMString::operator=(&v27, v20);
                    Sid[0] = 0;
                    if ( ConvertStringSidToSidW(StringSid, Sid) && IsValidSid(Sid[0]) )
                      v16 = CAccessControlImpl::InitFromSid(v17, StringSid);
                    if ( Sid[0] )
                      LocalFree(Sid[0]);
                  }
                  else
                  {
                    CAccessControlImpl::AddPermissionToEveryone(v17, v18);
                  }
                  TLMString<64,64,1048576>::~TLMString<64,64,1048576>(&v27);
                }
              }
            }
          }
          return v16;
        }
      }
      else
      {
        result = GetLastError();
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
      }
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    if ( result == -2147024890 )
      return -2147218172;
  }
  return result;
}

```

## disassembly

```asm
0x1801e00ac  push    rbx
0x1801e00ae  push    rsi
0x1801e00af  push    rdi
0x1801e00b0  push    r12
0x1801e00b2  push    r13
0x1801e00b4  push    r14
0x1801e00b6  push    r15
0x1801e00b8  sub     rsp, 130h
0x1801e00bf  mov     rax, cs:__security_cookie
0x1801e00c6  xor     rax, rsp
0x1801e00c9  mov     [rsp+168h+var_48], rax
0x1801e00d1  mov     r13d, r9d
0x1801e00d4  mov     r14, r8
0x1801e00d7  mov     rsi, rdx
0x1801e00da  mov     rdi, rcx
0x1801e00dd  mov     [rsp+168h+var_120], rcx
0x1801e00e2  mov     [rsp+168h+var_118], rdx
0x1801e00e7  mov     [rsp+168h+var_108], r8
0x1801e00ec  mov     dword ptr [rsp+168h+Sid], r9d
0x1801e00f1  mov     r12, [rsp+168h+arg_20]
0x1801e00f9  mov     [rsp+168h+var_128], r12
0x1801e00fe  xor     ebx, ebx
0x1801e0100  test    rdx, rdx
0x1801e0103  jnz     short loc_1801E010F
0x1801e0105  mov     eax, 80004003h
0x1801e010a  jmp     loc_1801E03A6
0x1801e010f  lea     r15, [r8+14h]
0x1801e0113  mov     [rsp+168h+var_F8], r15
0x1801e0118  cmp     [r15], ebx
0x1801e011b  jnz     short loc_1801E0127
0x1801e011d  mov     eax, 80070057h
0x1801e0122  jmp     loc_1801E03A6
0x1801e0127  add     rcx, 4C0h
0x1801e012e  call    ??4?$TComNoUnkPointer@VCPlugin@@@@QEAAPEAVCPlugin@@PEAV1@@Z; TComNoUnkPointer<CPlugin>::operator=(CPlugin *)
0x1801e0133  nop
0x1801e0134  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801e013b  mov     ecx, 208h; unsigned __int64
0x1801e0140  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801e0145  mov     [rsp+168h+var_130], rax
0x1801e014a  test    rax, rax
0x1801e014d  jz      short loc_1801E015D
0x1801e014f  mov     rdx, [r14+8]; wchar_t *
0x1801e0153  mov     rcx, rax; this
0x1801e0156  call    ??0CHostExpression@@QEAA@PEB_W@Z; CHostExpression::CHostExpression(wchar_t const *)
0x1801e015b  jmp     short loc_1801E0160
0x1801e015d  mov     rax, rbx
0x1801e0160  mov     [rdi+4B8h], rax
0x1801e0167  test    rax, rax
0x1801e016a  jnz     short loc_1801E0176
0x1801e016c  mov     eax, 8007000Eh
0x1801e0171  jmp     loc_1801E03A6
0x1801e0176  jmp     short loc_1801E019F
0x1801e0178  mov     eax, dword ptr [rsp+168h+var_130]
0x1801e017c  xor     ebx, ebx
0x1801e017e  test    eax, eax
0x1801e0180  js      loc_1801E03A6
0x1801e0186  mov     rdi, [rsp+168h+var_120]
0x1801e018b  mov     rsi, [rsp+168h+var_118]
0x1801e0190  mov     r14, [rsp+168h+var_108]
0x1801e0195  mov     r13d, dword ptr [rsp+168h+Sid]
0x1801e019a  mov     r15, [rsp+168h+var_F8]
0x1801e019f  mov     rdx, [r14+8]; wchar_t *
0x1801e01a3  lea     rcx, [rsi+40h]; this
0x1801e01a7  call    ?CreateSubKey@CConfigNode@@QEAAHPEB_W@Z; CConfigNode::CreateSubKey(wchar_t const *)
0x1801e01ac  test    eax, eax
0x1801e01ae  jnz     short loc_1801E01D4
0x1801e01b0  call    cs:__imp_GetLastError
0x1801e01b6  test    eax, eax
0x1801e01b8  jle     short loc_1801E01C2
0x1801e01ba  movzx   eax, ax
0x1801e01bd  or      eax, 80070000h
0x1801e01c2  mov     ecx, 80040D04h
0x1801e01c7  cmp     eax, 80070006h
0x1801e01cc  cmovz   eax, ecx
0x1801e01cf  jmp     loc_1801E03A6
0x1801e01d4  lea     r12, [rdi+38h]
0x1801e01d8  mov     r8, [r14+8]; wchar_t *
0x1801e01dc  lea     rdx, [rsi+40h]; struct CConfigNode *
0x1801e01e0  mov     rcx, r12; this
0x1801e01e3  call    ?Init@CConfigNode@@QEAAJPEAV1@PEB_WK@Z; CConfigNode::Init(CConfigNode *,wchar_t const *,ulong)
0x1801e01e8  test    eax, eax
0x1801e01ea  js      loc_1801E03A6
0x1801e01f0  lea     rcx, [rdi+0B8h]
0x1801e01f7  mov     rdx, r14
0x1801e01fa  call    ??4?$TLMString@$0MA@$0EA@$0HPPP@@@QEAAXAEBV0@@Z; TLMString<192,64,32767>::operator=(TLMString<192,64,32767> const &)
0x1801e01ff  lea     rdx, aPaths; "Paths"
0x1801e0206  mov     rcx, r12; this
0x1801e0209  call    ?CreateSubKey@CConfigNode@@QEAAHPEB_W@Z; CConfigNode::CreateSubKey(wchar_t const *)
0x1801e020e  test    eax, eax
0x1801e0210  jnz     short loc_1801E022D
0x1801e0212  call    cs:__imp_GetLastError
0x1801e0218  test    eax, eax
0x1801e021a  jle     loc_1801E03A6
0x1801e0220  movzx   eax, ax
0x1801e0223  or      eax, 80070000h
0x1801e0228  jmp     loc_1801E03A6
0x1801e022d  lea     rcx, [rdi+3C8h]; this
0x1801e0234  mov     rax, [rsp+168h+var_128]
0x1801e0239  mov     [rsp+168h+var_148], rax; struct IUrlConverter *
0x1801e023e  mov     r8, rdi; struct CSiteRestriction *
0x1801e0241  lea     rdx, cchOriginalDestLength; wchar_t *
0x1801e0248  call    ?Init@CSitePathCollection@@QEAAJPEB_WPEAVCSiteRestriction@@0PEAUIUrlConverter@@@Z; CSitePathCollection::Init(wchar_t const *,CSiteRestriction *,wchar_t const *,IUrlConverter *)
0x1801e024d  test    eax, eax
0x1801e024f  js      loc_1801E03A6
0x1801e0255  mov     edx, r13d; int
0x1801e0258  mov     rcx, rdi; this
0x1801e025b  call    ?SetIncluded@CSiteRestriction@@QEAAJH@Z; CSiteRestriction::SetIncluded(int)
0x1801e0260  mov     esi, eax
0x1801e0262  test    eax, eax
0x1801e0264  js      loc_1801E03A4
0x1801e026a  xor     edx, edx; int
0x1801e026c  mov     rcx, rdi; this
0x1801e026f  call    ?SetFollowComplexUrls@CSiteRestriction@@QEAAJH@Z; CSiteRestriction::SetFollowComplexUrls(int)
0x1801e0274  mov     esi, eax
0x1801e0276  test    eax, eax
0x1801e0278  js      loc_1801E03A4
0x1801e027e  mov     r13d, 1
0x1801e0284  mov     edx, r13d; int
0x1801e0287  mov     rcx, rdi; this
0x1801e028a  call    ?SetApplyToDavHref@CSiteRestriction@@QEAAJH@Z; CSiteRestriction::SetApplyToDavHref(int)
0x1801e028f  mov     esi, eax
0x1801e0291  test    eax, eax
0x1801e0293  js      loc_1801E03A4
0x1801e0299  add     rdi, 2B8h
0x1801e02a0  xor     r9d, r9d; struct ISearchAccessListSite *
0x1801e02a3  xor     r8d, r8d; unsigned int
0x1801e02a6  mov     rdx, [r12]; struct PConfigNode *
0x1801e02aa  mov     rcx, rdi; this
0x1801e02ad  call    ?Init@CAccessControlImpl@@QEAAJPEAVPConfigNode@@KPEAUISearchAccessListSite@@@Z; CAccessControlImpl::Init(PConfigNode *,ulong,ISearchAccessListSite *)
0x1801e02b2  mov     esi, eax
0x1801e02b4  test    eax, eax
0x1801e02b6  js      loc_1801E03A4
0x1801e02bc  lea     rax, [rsp+168h+var_D0]
0x1801e02c4  mov     [rsp+168h+StringSid], rax
0x1801e02cc  mov     [rsp+168h+var_D8], 41h ; 'A'
0x1801e02d8  mov     [rsp+168h+var_D0], bx
0x1801e02e0  lea     rax, ??_7?$TLMString@$0EA@$0EA@$0BAAAAA@@@6B@; const TLMString<64,64,1048576>::`vftable'
0x1801e02e7  mov     [rsp+168h+var_E8], rax
0x1801e02ef  mov     r9d, [r15]
0x1801e02f2  cmp     r9d, 2
0x1801e02f6  jbe     loc_1801E038E
0x1801e02fc  mov     rcx, [r14+8]
0x1801e0300  lea     eax, [r13+7Ah]
0x1801e0304  cmp     ax, [rcx]
0x1801e0307  jnz     loc_1801E038E
0x1801e030d  lea     edx, [r9-1]
0x1801e0311  lea     eax, [r13+7Ch]
0x1801e0315  cmp     ax, [rcx+rdx*2]
0x1801e0319  jnz     short loc_1801E038E
0x1801e031b  add     r9d, 0FFFFFFFEh
0x1801e031f  mov     r8d, r13d
0x1801e0322  lea     rdx, [rsp+168h+var_F8]
0x1801e0327  mov     rcx, r14
0x1801e032a  call    ?Mid@CLMString@@QEBA?AVCLMSubStr@@II@Z; CLMString::Mid(uint,uint)
0x1801e032f  mov     rdx, rax
0x1801e0332  lea     rcx, [rsp+168h+var_E8]
0x1801e033a  call    ??4CLMString@@QEAAXAEBVCLMSubStr@@@Z; CLMString::operator=(CLMSubStr const &)
0x1801e033f  mov     [rsp+168h+Sid], rbx
0x1801e0344  lea     rdx, [rsp+168h+Sid]; Sid
0x1801e0349  mov     rcx, [rsp+168h+StringSid]; StringSid
0x1801e0351  call    cs:__imp_ConvertStringSidToSidW
0x1801e0357  test    eax, eax
0x1801e0359  jz      short loc_1801E037C
0x1801e035b  mov     rcx, [rsp+168h+Sid]; pSid
0x1801e0360  call    cs:__imp_IsValidSid
0x1801e0366  test    eax, eax
0x1801e0368  jz      short loc_1801E037C
0x1801e036a  mov     rdx, [rsp+168h+StringSid]; wchar_t *
0x1801e0372  mov     rcx, rdi; this
0x1801e0375  call    ?InitFromSid@CAccessControlImpl@@QEAAJPEB_W@Z; CAccessControlImpl::InitFromSid(wchar_t const *)
0x1801e037a  mov     esi, eax
0x1801e037c  mov     rcx, [rsp+168h+Sid]; hMem
0x1801e0381  test    rcx, rcx
0x1801e0384  jz      short loc_1801E0397
0x1801e0386  call    cs:__imp_LocalFree
0x1801e038c  jmp     short loc_1801E0397
0x1801e038e  mov     rcx, rdi; this
0x1801e0391  call    ?AddPermissionToEveryone@CAccessControlImpl@@QEAAXK@Z; CAccessControlImpl::AddPermissionToEveryone(ulong)
0x1801e0396  nop
0x1801e0397  lea     rcx, [rsp+168h+var_E8]
0x1801e039f  call    ??1?$TLMString@$0EA@$0EA@$0BAAAAA@@@UEAA@XZ; TLMString<64,64,1048576>::~TLMString<64,64,1048576>(void)
0x1801e03a4  mov     eax, esi
0x1801e03a6  mov     rcx, [rsp+168h+var_48]
0x1801e03ae  xor     rcx, rsp; StackCookie
0x1801e03b1  call    __security_check_cookie
0x1801e03b6  add     rsp, 130h
0x1801e03bd  pop     r15
0x1801e03bf  pop     r14
0x1801e03c1  pop     r13
0x1801e03c3  pop     r12
0x1801e03c5  pop     rdi
0x1801e03c6  pop     rsi
0x1801e03c7  pop     rbx
0x1801e03c8  retn
```
