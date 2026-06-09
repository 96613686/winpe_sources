# StorePrivateData(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x1800273e0`
- end: `0x1800275cc`
- name: `?StorePrivateData@@YAJPEBG00K@Z`
- size: `492`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180026a30`

## callees

- `0x180015594`
- `0x1800273e0`
- `0x1800275d4`
- `0x18005582e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002749f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800274e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027561`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027589`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002749f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800274e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027561`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027589`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002745d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800274bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002745d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800274bd`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180027599`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180027599`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x180027538`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x180027538`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180027521`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180027521`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StorePrivateData(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4)
{
  SIZE_T v4; // rbx
  __int16 v7; // ax
  __int16 v8; // r8
  void *v9; // rax
  int v11; // edi
  WCHAR *v12; // rax
  __int64 v13; // rax
  _BYTE *v14; // rcx
  struct _LSA_UNICODE_STRING *p_PrivateData; // rdi
  NTSTATUS v16; // ebx
  _BYTE *v17; // rcx
  __int64 v18; // rax
  PWSTR Buffer; // rcx
  __int64 Length; // rax
  LPVOID pv[2]; // [rsp+30h] [rbp-50h] BYREF
  struct _LSA_UNICODE_STRING PrivateData; // [rsp+40h] [rbp-40h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  PVOID PolicyHandle; // [rsp+A0h] [rbp+20h] BYREF

  v4 = a4;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  PolicyHandle = 0;
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
  if ( v11 >= 0 )
  {
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
          v14 = pv[1];
        }
        CoTaskMemFree(v14);
        return 2147942414LL;
      }
      memcpy_0(v12, a3, v4);
      p_PrivateData = &PrivateData;
    }
    else
    {
      p_PrivateData = 0;
    }
    ObjectAttributes.Length = 48;
    v16 = LsaOpenPolicy(0, &ObjectAttributes, 0x20u, &PolicyHandle);
    if ( !v16 )
      v16 = LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)pv, p_PrivateData);
    v17 = pv[1];
    if ( pv[1] )
    {
      v18 = LOWORD(pv[0]);
      if ( LOWORD(pv[0]) )
      {
        do
        {
          *v17++ = 0;
          --v18;
        }
        while ( v18 );
        v17 = pv[1];
      }
      CoTaskMemFree(v17);
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
    if ( v16 )
    {
      if ( v16 > 0 )
        return (unsigned __int16)v16 | 0x80070000;
      return (unsigned int)v16;
    }
    else
    {
      return 0;
    }
  }
  else
  {
    CoTaskMemFree(pv[1]);
    return (unsigned int)v11;
  }
}

```

## disassembly

```asm
0x1800273e0  mov     [rsp-18h+arg_8], rbx
0x1800273e5  mov     [rsp-18h+arg_10], rsi
0x1800273ea  mov     [rsp-18h+PolicyHandle], rcx
0x1800273ef  push    rbp
0x1800273f0  push    rdi
0x1800273f1  push    r15
0x1800273f3  mov     rbp, rsp
0x1800273f6  sub     rsp, 80h
0x1800273fd  mov     ebx, r9d
0x180027400  mov     rsi, r8
0x180027403  mov     rdi, rdx
0x180027406  xorps   xmm0, xmm0
0x180027409  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18002740d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180027411  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180027415  mov     [rbp+PolicyHandle], 0
0x18002741d  movups  xmmword ptr [rbp+pv], xmm0
0x180027421  xorps   xmm1, xmm1
0x180027424  movups  xmmword ptr [rbp+PrivateData.Length], xmm1
0x180027428  mov     rcx, rdx; unsigned __int16 *
0x18002742b  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180027430  mov     r8d, eax
0x180027433  lea     rcx, aScm; "SCM:"
0x18002743a  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18002743f  add     r8w, ax
0x180027443  mov     r15d, 1
0x180027449  add     r8w, r15w
0x18002744d  add     r8w, r8w
0x180027451  movzx   ecx, r8w; cb
0x180027455  mov     word ptr [rbp+pv], cx
0x180027459  mov     word ptr [rbp+pv+2], cx
0x18002745d  call    cs:__imp_CoTaskMemAlloc
0x180027463  mov     [rbp+pv+8], rax
0x180027467  test    rax, rax
0x18002746a  jnz     short loc_180027476
0x18002746c  mov     eax, 8007000Eh
0x180027471  jmp     loc_1800275B4
0x180027476  movzx   edx, word ptr [rbp+pv]; unsigned __int64
0x18002747a  mov     [rsp+80h+var_60], rdi
0x18002747f  lea     r9, aScm; "SCM:"
0x180027486  lea     r8, aSS_1; "%s%s"
0x18002748d  mov     rcx, rax; unsigned __int16 *
0x180027490  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027495  mov     edi, eax
0x180027497  test    eax, eax
0x180027499  jns     short loc_1800274AD
0x18002749b  mov     rcx, [rbp+pv+8]; pv
0x18002749f  call    cs:__imp_CoTaskMemFree
0x1800274a5  nop
0x1800274a6  mov     eax, edi
0x1800274a8  jmp     loc_1800275B4
0x1800274ad  test    rsi, rsi
0x1800274b0  jz      short loc_180027508
0x1800274b2  mov     [rbp+PrivateData.Length], bx
0x1800274b6  mov     [rbp+PrivateData.MaximumLength], bx
0x1800274ba  mov     rcx, rbx; cb
0x1800274bd  call    cs:__imp_CoTaskMemAlloc
0x1800274c3  mov     [rbp+PrivateData.Buffer], rax
0x1800274c7  test    rax, rax
0x1800274ca  jnz     short loc_1800274F4
0x1800274cc  movzx   eax, word ptr [rbp+pv]
0x1800274d0  mov     rcx, [rbp+pv+8]
0x1800274d4  test    rax, rax
0x1800274d7  jz      short loc_1800274E8
0x1800274d9  mov     byte ptr [rcx], 0
0x1800274dc  add     rcx, r15
0x1800274df  sub     rax, r15
0x1800274e2  jnz     short loc_1800274D9
0x1800274e4  mov     rcx, [rbp+pv+8]; pv
0x1800274e8  call    cs:__imp_CoTaskMemFree
0x1800274ee  nop
0x1800274ef  jmp     loc_18002746C
0x1800274f4  mov     r8, rbx; Size
0x1800274f7  mov     rdx, rsi; Src
0x1800274fa  mov     rcx, rax; void *
0x1800274fd  call    memcpy_0
0x180027502  lea     rdi, [rbp+PrivateData]
0x180027506  jmp     short loc_18002750A
0x180027508  xor     edi, edi
0x18002750a  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180027511  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x180027515  mov     r8d, 20h ; ' '; DesiredAccess
0x18002751b  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18002751f  xor     ecx, ecx; SystemName
0x180027521  call    cs:__imp_LsaOpenPolicy
0x180027527  mov     ebx, eax
0x180027529  test    eax, eax
0x18002752b  jnz     short loc_180027540
0x18002752d  mov     r8, rdi; PrivateData
0x180027530  lea     rdx, [rbp+pv]; KeyName
0x180027534  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x180027538  call    cs:__imp_LsaStorePrivateData
0x18002753e  mov     ebx, eax
0x180027540  mov     rcx, [rbp+pv+8]
0x180027544  test    rcx, rcx
0x180027547  jz      short loc_180027568
0x180027549  movzx   eax, word ptr [rbp+pv]
0x18002754d  test    rax, rax
0x180027550  jz      short loc_180027561
0x180027552  mov     byte ptr [rcx], 0
0x180027555  add     rcx, r15
0x180027558  sub     rax, r15
0x18002755b  jnz     short loc_180027552
0x18002755d  mov     rcx, [rbp+pv+8]; pv
0x180027561  call    cs:__imp_CoTaskMemFree
0x180027567  nop
0x180027568  mov     rcx, [rbp+PrivateData.Buffer]
0x18002756c  test    rcx, rcx
0x18002756f  jz      short loc_180027590
0x180027571  movzx   eax, [rbp+PrivateData.Length]
0x180027575  test    rax, rax
0x180027578  jz      short loc_180027589
0x18002757a  mov     byte ptr [rcx], 0
0x18002757d  add     rcx, r15
0x180027580  sub     rax, r15
0x180027583  jnz     short loc_18002757A
0x180027585  mov     rcx, [rbp+PrivateData.Buffer]; pv
0x180027589  call    cs:__imp_CoTaskMemFree
0x18002758f  nop
0x180027590  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x180027594  test    rcx, rcx
0x180027597  jz      short loc_18002759F
0x180027599  call    cs:__imp_LsaClose
0x18002759f  test    ebx, ebx
0x1800275a1  jz      short loc_1800275B2
0x1800275a3  jle     short loc_1800275AE
0x1800275a5  movzx   ebx, bx
0x1800275a8  or      ebx, 80070000h
0x1800275ae  mov     eax, ebx
0x1800275b0  jmp     short loc_1800275B4
0x1800275b2  xor     eax, eax
0x1800275b4  lea     r11, [rsp+80h+var_s0]
0x1800275bc  mov     rbx, [r11+28h]
0x1800275c0  mov     rsi, [r11+30h]
0x1800275c4  mov     rsp, r11
0x1800275c7  pop     r15
0x1800275c9  pop     rdi
0x1800275ca  pop     rbp
0x1800275cb  retn
```
