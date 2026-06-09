# PackageEnroller::Unenroll(void)

- ea: `0x18002cbf4`
- end: `0x18002cd30`
- name: `?Unenroll@PackageEnroller@@QEAAXXZ`
- size: `316`
- prototype: `void __fastcall(PackageEnroller *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016d64`

## callees

- `0x180002300`
- `0x18001b388`
- `0x18002be50`
- `0x18002c040`
- `0x18002cbf4`
- `0x18002cd38`
- `0x180033ed0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18002cc50`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18002cc50`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ccdc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002ccdc`

## pseudocode

```c
void __fastcall PackageEnroller::Unenroll(HKEY *this)
{
  bool v2; // cf
  char *v3; // rcx
  HRESULT v4; // eax
  __int64 v5; // r8
  __int64 v6; // r9
  _QWORD *v7; // rbx
  char *v8; // rax
  _QWORD *v9; // rax
  const WCHAR *v10; // rdx
  _WORD *v11; // rcx
  int v12; // [rsp+20h] [rbp-48h]
  char *v13; // [rsp+30h] [rbp-38h] BYREF
  _QWORD *v14; // [rsp+38h] [rbp-30h] BYREF
  GUID iid; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( PackageEnroller::IsEnrolled((PackageEnroller *)this) )
  {
    PackageEnroller::InitEnrollEngineIfNecessary((PackageEnroller *)this);
    v2 = this[8] != 0;
    iid = 0;
    v3 = (char *)this + (v2 ? 48LL : 16LL);
    if ( *((_QWORD *)v3 + 3) >= 8u )
      v3 = *(char **)v3;
    v4 = IIDFromString((LPCOLESTR)v3, &iid);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9A,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageenroller.cpp",
        (const char *)(unsigned int)v4,
        v12);
    PackageEnroller::UnenrollById(&iid, (struct IEnrollEngine *)*this);
    if ( *(_DWORD *)g_hProvTraceProvider <= 5u )
    {
      v7 = this + 6;
    }
    else
    {
      v7 = this + 6;
      if ( (unsigned __int64)this[9] < 8 )
        v8 = (char *)(this + 6);
      else
        v8 = (char *)*v7;
      v13 = v8;
      v9 = this + 2;
      if ( (unsigned __int64)this[5] >= 8 )
        v9 = (_QWORD *)*v9;
      v14 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        g_hProvTraceProvider,
        (__int64)word_18004193A,
        v5,
        v6,
        &v14,
        &v13);
    }
    v10 = (const WCHAR *)(this + 2);
    if ( (unsigned __int64)this[5] >= 8 )
      v10 = *(const WCHAR **)v10;
    RegDeleteValueW(this[1], v10);
    if ( v7[3] < 8u )
      v11 = v7;
    else
      v11 = (_WORD *)*v7;
    v7[2] = 0;
    *v11 = 0;
  }
}

```

## disassembly

```asm
0x18002cbf4  mov     [rsp+arg_8], rbx
0x18002cbf9  push    rdi
0x18002cbfa  sub     rsp, 60h
0x18002cbfe  mov     rax, cs:__security_cookie
0x18002cc05  xor     rax, rsp
0x18002cc08  mov     [rsp+68h+var_18], rax
0x18002cc0d  mov     rdi, rcx
0x18002cc10  call    ?IsEnrolled@PackageEnroller@@QEBA_NXZ; PackageEnroller::IsEnrolled(void)
0x18002cc15  test    al, al
0x18002cc17  jz      loc_18002CCFE
0x18002cc1d  mov     rcx, rdi; this
0x18002cc20  call    ?InitEnrollEngineIfNecessary@PackageEnroller@@AEAAXXZ; PackageEnroller::InitEnrollEngineIfNecessary(void)
0x18002cc25  mov     rax, [rdi+40h]
0x18002cc29  xorps   xmm0, xmm0
0x18002cc2c  neg     rax
0x18002cc2f  movups  xmmword ptr [rsp+68h+iid.Data1], xmm0
0x18002cc34  sbb     rcx, rcx
0x18002cc37  and     ecx, 20h
0x18002cc3a  add     rcx, 10h
0x18002cc3e  add     rcx, rdi
0x18002cc41  cmp     qword ptr [rcx+18h], 8
0x18002cc46  jb      short loc_18002CC4B
0x18002cc48  mov     rcx, [rcx]; lpsz
0x18002cc4b  lea     rdx, [rsp+68h+iid]; lpiid
0x18002cc50  call    cs:__imp_IIDFromString
0x18002cc56  test    eax, eax
0x18002cc58  js      loc_18002CD16
0x18002cc5e  mov     rdx, [rdi]; struct IEnrollEngine *
0x18002cc61  lea     rcx, [rsp+68h+iid]; struct _GUID *
0x18002cc66  call    ?UnenrollById@PackageEnroller@@SAXAEBU_GUID@@PEAUIEnrollEngine@@@Z; PackageEnroller::UnenrollById(_GUID const &,IEnrollEngine *)
0x18002cc6b  mov     rcx, cs:g_hProvTraceProvider
0x18002cc72  mov     eax, [rcx]
0x18002cc74  cmp     eax, 5
0x18002cc77  jbe     short loc_18002CCC6
0x18002cc79  lea     rbx, [rdi+30h]
0x18002cc7d  cmp     qword ptr [rbx+18h], 8
0x18002cc82  jb      short loc_18002CC89
0x18002cc84  mov     rax, [rbx]
0x18002cc87  jmp     short loc_18002CC8C
0x18002cc89  mov     rax, rbx
0x18002cc8c  mov     [rsp+68h+var_38], rax
0x18002cc91  lea     rax, [rdi+10h]
0x18002cc95  cmp     qword ptr [rax+18h], 8
0x18002cc9a  jb      short loc_18002CC9F
0x18002cc9c  mov     rax, [rax]
0x18002cc9f  mov     [rsp+68h+var_30], rax
0x18002cca4  lea     rdx, word_18004193A
0x18002ccab  lea     rax, [rsp+68h+var_38]
0x18002ccb0  mov     [rsp+68h+var_40], rax
0x18002ccb5  lea     rax, [rsp+68h+var_30]
0x18002ccba  mov     [rsp+68h+var_48], rax
0x18002ccbf  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18002ccc4  jmp     short loc_18002CCCA
0x18002ccc6  lea     rbx, [rdi+30h]
0x18002ccca  lea     rdx, [rdi+10h]
0x18002ccce  cmp     qword ptr [rdx+18h], 8
0x18002ccd3  jb      short loc_18002CCD8
0x18002ccd5  mov     rdx, [rdx]; lpValueName
0x18002ccd8  mov     rcx, [rdi+8]; hKey
0x18002ccdc  call    cs:__imp_RegDeleteValueW
0x18002cce2  cmp     qword ptr [rbx+18h], 8
0x18002cce7  jb      short loc_18002CCEE
0x18002cce9  mov     rcx, [rbx]
0x18002ccec  jmp     short loc_18002CCF1
0x18002ccee  mov     rcx, rbx
0x18002ccf1  xor     eax, eax
0x18002ccf3  mov     qword ptr [rbx+10h], 0
0x18002ccfb  mov     [rcx], ax
0x18002ccfe  mov     rcx, [rsp+68h+var_18]
0x18002cd03  xor     rcx, rsp; StackCookie
0x18002cd06  call    __security_check_cookie
0x18002cd0b  mov     rbx, [rsp+68h+arg_8]
0x18002cd10  add     rsp, 60h
0x18002cd14  pop     rdi
0x18002cd15  retn
0x18002cd16  mov     rcx, [rsp+68h]; this
0x18002cd1b  lea     r8, aOnecoreuapAdmi_10; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x18002cd22  mov     r9d, eax; char *
0x18002cd25  mov     edx, 9Ah; void *
0x18002cd2a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
