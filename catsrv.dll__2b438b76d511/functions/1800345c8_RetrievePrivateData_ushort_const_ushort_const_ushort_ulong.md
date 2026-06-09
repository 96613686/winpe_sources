# RetrievePrivateData(ushort const *,ushort const *,ushort * *,ulong *)

- ea: `0x1800345c8`
- end: `0x18003477a`
- name: `?RetrievePrivateData@@YAJPEBG0PEAPEAGPEAK@Z`
- size: `434`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180033b94`

## callees

- `0x18001a6c8`
- `0x180027418`
- `0x1800345c8`
- `0x18005550e`
- `0x180055550`
- `0x180055610`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034707`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034707`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800346a2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800346a2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x1800346cb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x1800346cb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800346db`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180034759`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800346db`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180034759`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18003474f`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18003474f`

## pseudocode

```c
NTSTATUS __fastcall RetrievePrivateData(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned int *a4)
{
  __int16 v7; // ax
  __int16 v8; // r8
  USHORT v9; // r8
  unsigned __int64 v10; // rax
  void *v11; // rsp
  NTSTATUS result; // eax
  NTSTATUS v13; // edi
  NTSTATUS v14; // ebx
  SIZE_T Length; // rcx
  unsigned __int16 *v16; // rax
  PLSA_UNICODE_STRING v17; // rcx
  __int64 v18; // rdx
  PWSTR Buffer; // rax
  PLSA_UNICODE_STRING PrivateData; // [rsp+30h] [rbp+0h] BYREF
  PVOID PolicyHandle; // [rsp+38h] [rbp+8h] BYREF
  struct _LSA_UNICODE_STRING KeyName; // [rsp+40h] [rbp+10h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp+20h] BYREF

  PolicyHandle = 0;
  PrivateData = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  KeyName = 0;
  safe_lstrlenW(a1);
  v7 = safe_lstrlenW(a2);
  v9 = 2 * (v7 + v8 + 1);
  KeyName.Length = v9;
  KeyName.MaximumLength = v9;
  v10 = v9 + 15LL;
  if ( v10 <= v9 )
    v10 = 0xFFFFFFFFFFFFFF0LL;
  v11 = alloca(v10 & 0xFFFFFFFFFFFFFFF0uLL);
  KeyName.Buffer = (PWSTR)&PrivateData;
  result = StringCbPrintfW((unsigned __int16 *)&PrivateData, v9, L"%s%s");
  v13 = result;
  if ( result >= 0 )
  {
    ObjectAttributes.Length = 48;
    result = LsaOpenPolicy(0, &ObjectAttributes, 4u, &PolicyHandle);
    if ( result )
    {
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
    else
    {
      v14 = LsaRetrievePrivateData(PolicyHandle, &KeyName, &PrivateData);
      if ( v14 )
      {
        LsaClose(PolicyHandle);
        if ( v14 > 0 )
          return (unsigned __int16)v14 | 0x80070000;
        return v14;
      }
      else
      {
        if ( PrivateData )
        {
          Length = PrivateData->Length;
          *a4 = Length;
          v16 = (unsigned __int16 *)CoTaskMemAlloc(Length);
          *a3 = v16;
          if ( v16 )
            memcpy_0(v16, PrivateData->Buffer, PrivateData->Length);
          else
            v13 = -2147024882;
          v17 = PrivateData;
          v18 = PrivateData->Length;
          Buffer = PrivateData->Buffer;
          if ( PrivateData->Length )
          {
            do
            {
              *(_BYTE *)Buffer = 0;
              Buffer = (PWSTR)((char *)Buffer + 1);
              --v18;
            }
            while ( v18 );
            v17 = PrivateData;
          }
          LsaFreeMemory(v17);
        }
        else
        {
          v13 = -2147418113;
        }
        LsaClose(PolicyHandle);
        return v13;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800345c8  push    rbp
0x1800345ca  push    rbx
0x1800345cb  push    rsi
0x1800345cc  push    rdi
0x1800345cd  push    r12
0x1800345cf  push    r14
0x1800345d1  sub     rsp, 98h
0x1800345d8  lea     rbp, [rsp+30h]
0x1800345dd  mov     rax, cs:__security_cookie
0x1800345e4  xor     rax, rbp
0x1800345e7  mov     [rbp+90h+var_40], rax
0x1800345eb  xorps   xmm0, xmm0
0x1800345ee  mov     [rbp+90h+PolicyHandle], 0
0x1800345f6  mov     rsi, r9
0x1800345f9  mov     [rbp+90h+PrivateData], 0
0x180034601  movups  xmmword ptr [rbp+90h+ObjectAttributes.Length], xmm0
0x180034605  mov     r14, r8
0x180034608  mov     rbx, rdx
0x18003460b  movups  xmmword ptr [rbp+90h+ObjectAttributes.ObjectName], xmm0
0x18003460f  mov     r9, rcx
0x180034612  movups  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x180034616  movups  xmmword ptr [rbp+90h+KeyName.Length], xmm0
0x18003461a  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18003461f  mov     rcx, rbx; unsigned __int16 *
0x180034622  mov     r8d, eax
0x180034625  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18003462a  add     r8w, ax
0x18003462e  mov     r12d, 1
0x180034634  add     r8w, r12w
0x180034638  add     r8w, r8w
0x18003463c  movzx   edx, r8w
0x180034640  mov     [rbp+90h+KeyName.Length], dx
0x180034644  mov     [rbp+90h+KeyName.MaximumLength], dx
0x180034648  lea     rax, [rdx+0Fh]
0x18003464c  cmp     rax, rdx
0x18003464f  ja      short loc_18003465B
0x180034651  mov     rax, 0FFFFFFFFFFFFFF0h
0x18003465b  and     rax, 0FFFFFFFFFFFFFFF0h
0x18003465f  call    _alloca_probe
0x180034664  sub     rsp, rax
0x180034667  lea     r8, aSS_0; "%s%s"
0x18003466e  lea     rcx, [rsp+0C0h+PrivateData]; unsigned __int16 *
0x180034673  mov     [rsp+0C0h+var_A0], rbx
0x180034678  mov     [rbp+90h+KeyName.Buffer], rcx
0x18003467c  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180034681  mov     edi, eax
0x180034683  test    eax, eax
0x180034685  js      loc_180034761
0x18003468b  lea     r9, [rbp+90h+PolicyHandle]; PolicyHandle
0x18003468f  mov     [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x180034696  mov     r8d, 4; DesiredAccess
0x18003469c  lea     rdx, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x1800346a0  xor     ecx, ecx; SystemName
0x1800346a2  call    cs:__imp_LsaOpenPolicy
0x1800346a8  test    eax, eax
0x1800346aa  jz      short loc_1800346BF
0x1800346ac  jle     loc_180034761
0x1800346b2  movzx   eax, ax
0x1800346b5  or      eax, 80070000h
0x1800346ba  jmp     loc_180034761
0x1800346bf  mov     rcx, [rbp+90h+PolicyHandle]; PolicyHandle
0x1800346c3  lea     r8, [rbp+90h+PrivateData]; PrivateData
0x1800346c7  lea     rdx, [rbp+90h+KeyName]; KeyName
0x1800346cb  call    cs:__imp_LsaRetrievePrivateData
0x1800346d1  mov     ebx, eax
0x1800346d3  test    eax, eax
0x1800346d5  jz      short loc_1800346F2
0x1800346d7  mov     rcx, [rbp+90h+PolicyHandle]; ObjectHandle
0x1800346db  call    cs:__imp_LsaClose
0x1800346e1  test    ebx, ebx
0x1800346e3  jle     short loc_1800346EE
0x1800346e5  movzx   ebx, bx
0x1800346e8  or      ebx, 80070000h
0x1800346ee  mov     eax, ebx
0x1800346f0  jmp     short loc_180034761
0x1800346f2  mov     rax, [rbp+90h+PrivateData]
0x1800346f6  test    rax, rax
0x1800346f9  jnz     short loc_180034702
0x1800346fb  mov     edi, 8000FFFFh
0x180034700  jmp     short loc_180034755
0x180034702  movzx   ecx, word ptr [rax]; cb
0x180034705  mov     [rsi], ecx
0x180034707  call    cs:__imp_CoTaskMemAlloc
0x18003470d  mov     [r14], rax
0x180034710  test    rax, rax
0x180034713  jz      short loc_18003472B
0x180034715  mov     rdx, [rbp+90h+PrivateData]
0x180034719  mov     rcx, rax; void *
0x18003471c  movzx   r8d, word ptr [rdx]; Size
0x180034720  mov     rdx, [rdx+8]; Src
0x180034724  call    memcpy_0
0x180034729  jmp     short loc_180034730
0x18003472b  mov     edi, 8007000Eh
0x180034730  mov     rcx, [rbp+90h+PrivateData]
0x180034734  movzx   edx, word ptr [rcx]
0x180034737  mov     rax, [rcx+8]
0x18003473b  test    rdx, rdx
0x18003473e  jz      short loc_18003474F
0x180034740  mov     byte ptr [rax], 0
0x180034743  add     rax, r12
0x180034746  sub     rdx, r12
0x180034749  jnz     short loc_180034740
0x18003474b  mov     rcx, [rbp+90h+PrivateData]; Buffer
0x18003474f  call    cs:__imp_LsaFreeMemory
0x180034755  mov     rcx, [rbp+90h+PolicyHandle]; ObjectHandle
0x180034759  call    cs:__imp_LsaClose
0x18003475f  mov     eax, edi
0x180034761  mov     rcx, [rbp+90h+var_40]
0x180034765  xor     rcx, rbp; StackCookie
0x180034768  call    __security_check_cookie
0x18003476d  lea     rsp, [rbp+68h]
0x180034771  pop     r14
0x180034773  pop     r12
0x180034775  pop     rdi
0x180034776  pop     rsi
0x180034777  pop     rbx
0x180034778  pop     rbp
0x180034779  retn
```
