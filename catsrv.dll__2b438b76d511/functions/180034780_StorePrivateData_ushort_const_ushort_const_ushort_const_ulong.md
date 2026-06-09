# StorePrivateData(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x180034780`
- end: `0x180034963`
- name: `?StorePrivateData@@YAJPEBG00K@Z`
- size: `483`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180033df0`

## callees

- `0x18001a6c8`
- `0x180027418`
- `0x180034780`
- `0x18005550e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003487b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800348f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003491c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003487b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800348f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003491c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800347fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003484b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800347fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003484b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800348b5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800348b5`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18003492b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18003492b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800348cc`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800348cc`

## pseudocode

```c
__int64 __fastcall StorePrivateData(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  SIZE_T v4; // rdi
  __int16 v7; // ax
  __int16 v8; // r8
  void *v9; // rax
  NTSTATUS v11; // ebx
  WCHAR *v12; // rax
  __int64 v13; // rax
  _BYTE *v14; // rcx
  struct _LSA_UNICODE_STRING *p_PrivateData; // rdi
  _BYTE *v16; // rcx
  __int64 v17; // rax
  PWSTR Buffer; // rcx
  __int64 Length; // rax
  LPVOID pv[2]; // [rsp+30h] [rbp-50h] BYREF
  struct _LSA_UNICODE_STRING PrivateData; // [rsp+40h] [rbp-40h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  PVOID PolicyHandle; // [rsp+A0h] [rbp+20h] BYREF

  v4 = a4;
  PolicyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  HIDWORD(pv[0]) = 0;
  PrivateData = 0;
  safe_lstrlenW(a2);
  v7 = safe_lstrlenW(L"SCM:");
  LOWORD(pv[0]) = 2 * (v7 + v8 + 1);
  WORD1(pv[0]) = pv[0];
  v9 = CoTaskMemAlloc(LOWORD(pv[0]));
  pv[1] = v9;
  if ( !v9 )
    return 2147942414LL;
  v11 = StringCbPrintfW((unsigned __int16 *)v9, LOWORD(pv[0]), L"%s%s", L"SCM:", a2);
  if ( v11 < 0 )
    goto LABEL_9;
  if ( a3 )
  {
    PrivateData.Length = v4;
    PrivateData.MaximumLength = v4;
    v12 = (WCHAR *)CoTaskMemAlloc(v4);
    PrivateData.Buffer = v12;
    if ( !v12 )
    {
      v13 = LOWORD(pv[0]);
      v14 = pv[1];
      if ( LOWORD(pv[0]) )
      {
        do
        {
          *v14++ = 0;
          --v13;
        }
        while ( v13 );
      }
      v11 = -2147024882;
LABEL_9:
      CoTaskMemFree(pv[1]);
      return (unsigned int)v11;
    }
    memcpy_0(v12, a3, v4);
    p_PrivateData = &PrivateData;
  }
  else
  {
    p_PrivateData = 0;
  }
  ObjectAttributes.Length = 48;
  v11 = LsaOpenPolicy(0, &ObjectAttributes, 0x20u, &PolicyHandle);
  if ( !v11 )
    v11 = LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)pv, p_PrivateData);
  v16 = pv[1];
  if ( pv[1] )
  {
    v17 = LOWORD(pv[0]);
    if ( LOWORD(pv[0]) )
    {
      do
      {
        *v16++ = 0;
        --v17;
      }
      while ( v17 );
      v16 = pv[1];
    }
    CoTaskMemFree(v16);
  }
  Buffer = PrivateData.Buffer;
  if ( PrivateData.Buffer )
  {
    Length = PrivateData.Length;
    if ( PrivateData.Length )
    {
      do
      {
        *(_BYTE *)Buffer = 0;
        Buffer = (PWSTR)((char *)Buffer + 1);
        --Length;
      }
      while ( Length );
      Buffer = PrivateData.Buffer;
    }
    CoTaskMemFree(Buffer);
  }
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  if ( v11 )
  {
    if ( v11 > 0 )
      return (unsigned __int16)v11 | 0x80070000;
    return (unsigned int)v11;
  }
  return 0;
}

```

## disassembly

```asm
0x180034780  mov     [rsp-18h+arg_8], rbx
0x180034785  mov     [rsp-18h+arg_10], rsi
0x18003478a  mov     [rsp-18h+PolicyHandle], rcx
0x18003478f  push    rbp
0x180034790  push    rdi
0x180034791  push    r15
0x180034793  mov     rbp, rsp
0x180034796  sub     rsp, 80h
0x18003479d  xorps   xmm0, xmm0
0x1800347a0  mov     edi, r9d
0x1800347a3  xorps   xmm1, xmm1
0x1800347a6  mov     [rbp+PolicyHandle], 0
0x1800347ae  mov     rcx, rdx; unsigned __int16 *
0x1800347b1  mov     rsi, r8
0x1800347b4  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800347b8  mov     rbx, rdx
0x1800347bb  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800347bf  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800347c3  movups  xmmword ptr [rbp+pv], xmm0
0x1800347c7  movups  xmmword ptr [rbp+PrivateData.Length], xmm1
0x1800347cb  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x1800347d0  lea     rcx, aScm; "SCM:"
0x1800347d7  mov     r8d, eax
0x1800347da  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x1800347df  add     r8w, ax
0x1800347e3  mov     r15d, 1
0x1800347e9  add     r8w, r15w
0x1800347ed  add     r8w, r8w
0x1800347f1  movzx   ecx, r8w; cb
0x1800347f5  mov     word ptr [rbp+pv], cx
0x1800347f9  mov     word ptr [rbp+pv+2], cx
0x1800347fd  call    cs:__imp_CoTaskMemAlloc
0x180034803  mov     [rbp+pv+8], rax
0x180034807  test    rax, rax
0x18003480a  jnz     short loc_180034816
0x18003480c  mov     eax, 8007000Eh
0x180034811  jmp     loc_18003494B
0x180034816  movzx   edx, word ptr [rbp+pv]; unsigned __int64
0x18003481a  lea     r9, aScm; "SCM:"
0x180034821  lea     r8, aSS_0; "%s%s"
0x180034828  mov     [rsp+80h+var_60], rbx
0x18003482d  mov     rcx, rax; unsigned __int16 *
0x180034830  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180034835  mov     ebx, eax
0x180034837  test    eax, eax
0x180034839  js      short loc_180034877
0x18003483b  test    rsi, rsi
0x18003483e  jz      short loc_18003489C
0x180034840  mov     rcx, rdi; cb
0x180034843  mov     [rbp+PrivateData.Length], di
0x180034847  mov     [rbp+PrivateData.MaximumLength], di
0x18003484b  call    cs:__imp_CoTaskMemAlloc
0x180034851  mov     [rbp+PrivateData.Buffer], rax
0x180034855  test    rax, rax
0x180034858  jnz     short loc_180034888
0x18003485a  movzx   eax, word ptr [rbp+pv]
0x18003485e  mov     rcx, [rbp+pv+8]
0x180034862  test    rax, rax
0x180034865  jz      short loc_180034872
0x180034867  mov     byte ptr [rcx], 0
0x18003486a  add     rcx, r15
0x18003486d  sub     rax, r15
0x180034870  jnz     short loc_180034867
0x180034872  mov     ebx, 8007000Eh
0x180034877  mov     rcx, [rbp+pv+8]; pv
0x18003487b  call    cs:__imp_CoTaskMemFree
0x180034881  mov     eax, ebx
0x180034883  jmp     loc_18003494B
0x180034888  mov     r8, rdi; Size
0x18003488b  mov     rdx, rsi; Src
0x18003488e  mov     rcx, rax; void *
0x180034891  call    memcpy_0
0x180034896  lea     rdi, [rbp+PrivateData]
0x18003489a  jmp     short loc_18003489E
0x18003489c  xor     edi, edi
0x18003489e  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x1800348a2  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800348a9  mov     r8d, 20h ; ' '; DesiredAccess
0x1800348af  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x1800348b3  xor     ecx, ecx; SystemName
0x1800348b5  call    cs:__imp_LsaOpenPolicy
0x1800348bb  mov     ebx, eax
0x1800348bd  test    eax, eax
0x1800348bf  jnz     short loc_1800348D4
0x1800348c1  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x1800348c5  lea     rdx, [rbp+pv]; KeyName
0x1800348c9  mov     r8, rdi; PrivateData
0x1800348cc  call    cs:__imp_LsaStorePrivateData
0x1800348d2  mov     ebx, eax
0x1800348d4  mov     rcx, [rbp+pv+8]
0x1800348d8  test    rcx, rcx
0x1800348db  jz      short loc_1800348FB
0x1800348dd  movzx   eax, word ptr [rbp+pv]
0x1800348e1  test    rax, rax
0x1800348e4  jz      short loc_1800348F5
0x1800348e6  mov     byte ptr [rcx], 0
0x1800348e9  add     rcx, r15
0x1800348ec  sub     rax, r15
0x1800348ef  jnz     short loc_1800348E6
0x1800348f1  mov     rcx, [rbp+pv+8]; pv
0x1800348f5  call    cs:__imp_CoTaskMemFree
0x1800348fb  mov     rcx, [rbp+PrivateData.Buffer]
0x1800348ff  test    rcx, rcx
0x180034902  jz      short loc_180034922
0x180034904  movzx   eax, [rbp+PrivateData.Length]
0x180034908  test    rax, rax
0x18003490b  jz      short loc_18003491C
0x18003490d  mov     byte ptr [rcx], 0
0x180034910  add     rcx, r15
0x180034913  sub     rax, r15
0x180034916  jnz     short loc_18003490D
0x180034918  mov     rcx, [rbp+PrivateData.Buffer]; pv
0x18003491c  call    cs:__imp_CoTaskMemFree
0x180034922  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180034926  test    rcx, rcx
0x180034929  jz      short loc_180034931
0x18003492b  call    cs:__imp_LsaClose
0x180034931  test    ebx, ebx
0x180034933  jz      short loc_180034949
0x180034935  jle     loc_180034881
0x18003493b  movzx   ebx, bx
0x18003493e  or      ebx, 80070000h
0x180034944  jmp     loc_180034881
0x180034949  xor     eax, eax
0x18003494b  lea     r11, [rsp+80h+var_s0]
0x180034953  mov     rbx, [r11+28h]
0x180034957  mov     rsi, [r11+30h]
0x18003495b  mov     rsp, r11
0x18003495e  pop     r15
0x180034960  pop     rdi
0x180034961  pop     rbp
0x180034962  retn
```
