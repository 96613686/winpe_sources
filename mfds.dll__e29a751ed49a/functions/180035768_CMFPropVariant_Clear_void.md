# CMFPropVariant::Clear(void)

- ea: `0x180035768`
- end: `0x18003596e`
- name: `?Clear@CMFPropVariant@@QEAAJXZ`
- size: `518`
- prototype: `__int64 __fastcall(CMFPropVariant *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033ce0`
- `0x180034274`
- `0x180035b84`
- `0x1800552bc`

## callees

- `0x180035768`
- `0x180051ce4`
- `0x180052474`
- `0x1800552bc`
- `0x18005b0fc`
- `0x180074160`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x18003593d`
- `api-ms-win-crt-string-l1-1-0!memset` at `0x18003593d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003581a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035922`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003581a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035922`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800357c0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800357c0`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::Clear(PROPVARIANT *this)
{
  unsigned int v1; // ebp
  int v3; // ecx
  int v4; // ecx
  __int64 v5; // rdx
  unsigned int i; // r14d
  BYTE *pData; // rbx
  __int64 v8; // rdi
  __int64 j; // rbx
  __int64 v10; // rcx
  unsigned int k; // ebx
  struct tagPROPVARIANT v13; // [rsp+30h] [rbp-38h] BYREF

  v1 = 0;
  if ( !this->vt )
    return v1;
  v3 = this->vt - 4108;
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 != 52 )
      {
        v1 = PropVariantClear(this);
        if ( (v1 & 0x80000000) == 0 )
          return v1;
        goto LABEL_25;
      }
      if ( !this->bstrblobVal.pData )
      {
        v1 = -2147467261;
        if ( !g_wppLevels )
          return v1;
        v5 = 10;
        goto LABEL_24;
      }
      for ( i = 0; this->lVal > i; *(_QWORD *)&pData[8 * v8 + 8] = 0 )
      {
        pData = this->bstrblobVal.pData;
        v8 = 2LL * i;
        CoTaskMemFree(*(LPVOID *)&pData[16 * i++ + 8]);
      }
LABEL_29:
      CoTaskMemFree(this->bstrblobVal.pData);
      this->bstrblobVal.pData = 0;
      memset(this, 0, sizeof(PROPVARIANT));
      return v1;
    }
    if ( this->bstrblobVal.pData )
    {
      for ( j = 0; this->lVal > (unsigned int)j; j = (unsigned int)(j + 1) )
      {
        v10 = *(_QWORD *)&this->bstrblobVal.pData[8 * j];
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      goto LABEL_29;
    }
    v1 = -2147467261;
    if ( !g_wppLevels )
      return v1;
    v5 = 12;
  }
  else
  {
    if ( this->bstrblobVal.pData )
    {
      for ( k = 0; this->lVal > k; ++k )
      {
        CMFPropVariant::Init((CMFPropVariant *)&v13);
        CMFPropVariant::GetElementDataAsVariant((CMFPropVariant *)this, k, &v13);
        CMFPropVariant::~CMFPropVariant((CMFPropVariant *)&v13);
      }
      goto LABEL_29;
    }
    v1 = -2147467261;
    if ( !g_wppLevels )
      return v1;
    v5 = 11;
  }
LABEL_24:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, this, -2147467261);
LABEL_25:
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, this, v1);
  return v1;
}

```

## disassembly

```asm
0x180035768  mov     [rsp+arg_8], rbx
0x18003576d  mov     [rsp+arg_10], rbp
0x180035772  push    rsi
0x180035773  push    rdi
0x180035774  push    r14
0x180035776  sub     rsp, 50h
0x18003577a  mov     rax, cs:__security_cookie
0x180035781  xor     rax, rsp
0x180035784  mov     [rsp+68h+var_20], rax
0x180035789  xor     ebp, ebp
0x18003578b  xor     eax, eax
0x18003578d  mov     rsi, rcx
0x180035790  cmp     ax, [rcx]
0x180035793  jz      loc_180035949
0x180035799  movzx   ecx, word ptr [rcx]
0x18003579c  lea     rbx, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x1800357a3  sub     ecx, 100Ch
0x1800357a9  jz      loc_18003588A
0x1800357af  sub     ecx, 1
0x1800357b2  jz      loc_180035839
0x1800357b8  cmp     ecx, 34h ; '4'
0x1800357bb  jz      short loc_1800357DB
0x1800357bd  mov     rcx, rsi; pvar
0x1800357c0  call    cs:__imp_PropVariantClear
0x1800357c7  nop     dword ptr [rax+rax+00h]
0x1800357cc  mov     ebp, eax
0x1800357ce  test    eax, eax
0x1800357d0  js      loc_1800358C3
0x1800357d6  jmp     loc_180035949
0x1800357db  cmp     [rsi+10h], rax
0x1800357df  jnz     short loc_1800357FF
0x1800357e1  mov     eax, 80004003h
0x1800357e6  mov     ebp, eax
0x1800357e8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800357ef  jb      loc_180035949
0x1800357f5  mov     edx, 0Ah
0x1800357fa  jmp     loc_1800358A9
0x1800357ff  xor     r14d, r14d
0x180035802  cmp     [rsi+8], eax
0x180035805  jbe     loc_18003591E
0x18003580b  mov     rbx, [rsi+10h]
0x18003580f  mov     edi, r14d
0x180035812  add     rdi, rdi
0x180035815  mov     rcx, [rbx+rdi*8+8]; pv
0x18003581a  call    cs:__imp_CoTaskMemFree
0x180035821  nop     dword ptr [rax+rax+00h]
0x180035826  inc     r14d
0x180035829  mov     [rbx+rdi*8+8], rbp
0x18003582e  cmp     [rsi+8], r14d
0x180035832  ja      short loc_18003580B
0x180035834  jmp     loc_18003591E
0x180035839  cmp     [rsi+10h], rax
0x18003583d  jnz     short loc_18003585A
0x18003583f  mov     eax, 80004003h
0x180035844  mov     ebp, eax
0x180035846  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003584d  jb      loc_180035949
0x180035853  mov     edx, 0Ch
0x180035858  jmp     short loc_1800358A9
0x18003585a  xor     ebx, ebx
0x18003585c  cmp     [rsi+8], eax
0x18003585f  jbe     loc_18003591E
0x180035865  mov     rax, [rsi+10h]
0x180035869  mov     rcx, [rax+rbx*8]
0x18003586d  test    rcx, rcx
0x180035870  jz      short loc_18003587E
0x180035872  mov     rax, [rcx]
0x180035875  mov     rax, [rax+10h]
0x180035879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003587e  inc     ebx
0x180035880  cmp     [rsi+8], ebx
0x180035883  ja      short loc_180035865
0x180035885  jmp     loc_18003591E
0x18003588a  cmp     [rsi+10h], rax
0x18003588e  jnz     short loc_1800358ED
0x180035890  mov     eax, 80004003h
0x180035895  mov     ebp, eax
0x180035897  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003589e  jb      loc_180035949
0x1800358a4  mov     edx, 0Bh
0x1800358a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800358b0  mov     r9, rsi
0x1800358b3  mov     r8, rbx
0x1800358b6  mov     [rsp+68h+var_48], eax
0x1800358ba  mov     rcx, [rcx+10h]
0x1800358be  call    WPP_SF_qD
0x1800358c3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800358ca  jb      short loc_180035949
0x1800358cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800358d3  mov     edx, 0Dh
0x1800358d8  mov     r9, rsi
0x1800358db  mov     [rsp+68h+var_48], ebp
0x1800358df  mov     r8, rbx
0x1800358e2  mov     rcx, [rcx+10h]
0x1800358e6  call    WPP_SF_qD
0x1800358eb  jmp     short loc_180035949
0x1800358ed  xor     ebx, ebx
0x1800358ef  cmp     [rsi+8], eax
0x1800358f2  jbe     short loc_18003591E
0x1800358f4  lea     rcx, [rsp+68h+var_38]; this
0x1800358f9  call    ?Init@CMFPropVariant@@QEAAXXZ; CMFPropVariant::Init(void)
0x1800358fe  lea     r8, [rsp+68h+var_38]; struct tagPROPVARIANT *
0x180035903  mov     edx, ebx; unsigned int
0x180035905  mov     rcx, rsi; this
0x180035908  call    ?GetElementDataAsVariant@CMFPropVariant@@IEBAJKPEAUtagPROPVARIANT@@@Z; CMFPropVariant::GetElementDataAsVariant(ulong,tagPROPVARIANT *)
0x18003590d  lea     rcx, [rsp+68h+var_38]; this
0x180035912  call    ??1CMFPropVariant@@QEAA@XZ; CMFPropVariant::~CMFPropVariant(void)
0x180035917  inc     ebx
0x180035919  cmp     [rsi+8], ebx
0x18003591c  ja      short loc_1800358F4
0x18003591e  mov     rcx, [rsi+10h]; pv
0x180035922  call    cs:__imp_CoTaskMemFree
0x180035929  nop     dword ptr [rax+rax+00h]
0x18003592e  mov     r8d, 18h; Size
0x180035934  mov     [rsi+10h], rbp
0x180035938  xor     edx, edx; Val
0x18003593a  mov     rcx, rsi; void *
0x18003593d  call    cs:__imp_memset
0x180035944  nop     dword ptr [rax+rax+00h]
0x180035949  mov     eax, ebp
0x18003594b  mov     rcx, [rsp+68h+var_20]
0x180035950  xor     rcx, rsp; StackCookie
0x180035953  call    __security_check_cookie
0x180035958  lea     r11, [rsp+68h+var_18]
0x18003595d  mov     rbx, [r11+28h]
0x180035961  mov     rbp, [r11+30h]
0x180035965  mov     rsp, r11
0x180035968  pop     r14
0x18003596a  pop     rdi
0x18003596b  pop     rsi
0x18003596c  retn
```
