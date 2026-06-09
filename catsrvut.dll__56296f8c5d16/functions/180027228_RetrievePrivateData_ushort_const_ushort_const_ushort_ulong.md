# RetrievePrivateData(ushort const *,ushort const *,ushort * *,ulong *)

- ea: `0x180027228`
- end: `0x1800273da`
- name: `?RetrievePrivateData@@YAJPEBG0PEAPEAGPEAK@Z`
- size: `434`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800267d4`

## callees

- `0x180015594`
- `0x180027228`
- `0x1800275d4`
- `0x18005582e`
- `0x180055880`
- `0x180055940`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027367`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027367`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002733b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800273b9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18002733b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800273b9`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800273af`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800273af`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x18002732b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x18002732b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180027302`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180027302`

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
0x180027228  push    rbp
0x18002722a  push    rbx
0x18002722b  push    rsi
0x18002722c  push    rdi
0x18002722d  push    r12
0x18002722f  push    r14
0x180027231  sub     rsp, 98h
0x180027238  lea     rbp, [rsp+30h]
0x18002723d  mov     rax, cs:__security_cookie
0x180027244  xor     rax, rbp
0x180027247  mov     [rbp+90h+var_40], rax
0x18002724b  xorps   xmm0, xmm0
0x18002724e  mov     [rbp+90h+PolicyHandle], 0
0x180027256  mov     rsi, r9
0x180027259  mov     [rbp+90h+PrivateData], 0
0x180027261  movups  xmmword ptr [rbp+90h+ObjectAttributes.Length], xmm0
0x180027265  mov     r14, r8
0x180027268  mov     rbx, rdx
0x18002726b  movups  xmmword ptr [rbp+90h+ObjectAttributes.ObjectName], xmm0
0x18002726f  mov     r9, rcx
0x180027272  movups  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x180027276  movups  xmmword ptr [rbp+90h+KeyName.Length], xmm0
0x18002727a  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18002727f  mov     rcx, rbx; unsigned __int16 *
0x180027282  mov     r8d, eax
0x180027285  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18002728a  add     r8w, ax
0x18002728e  mov     r12d, 1
0x180027294  add     r8w, r12w
0x180027298  add     r8w, r8w
0x18002729c  movzx   edx, r8w
0x1800272a0  mov     [rbp+90h+KeyName.Length], dx
0x1800272a4  mov     [rbp+90h+KeyName.MaximumLength], dx
0x1800272a8  lea     rax, [rdx+0Fh]
0x1800272ac  cmp     rax, rdx
0x1800272af  ja      short loc_1800272BB
0x1800272b1  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800272bb  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800272bf  call    _alloca_probe
0x1800272c4  sub     rsp, rax
0x1800272c7  lea     r8, aSS_1; "%s%s"
0x1800272ce  lea     rcx, [rsp+0C0h+PrivateData]; unsigned __int16 *
0x1800272d3  mov     [rsp+0C0h+var_A0], rbx
0x1800272d8  mov     [rbp+90h+KeyName.Buffer], rcx
0x1800272dc  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800272e1  mov     edi, eax
0x1800272e3  test    eax, eax
0x1800272e5  js      loc_1800273C1
0x1800272eb  lea     r9, [rbp+90h+PolicyHandle]; PolicyHandle
0x1800272ef  mov     [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x1800272f6  mov     r8d, 4; DesiredAccess
0x1800272fc  lea     rdx, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x180027300  xor     ecx, ecx; SystemName
0x180027302  call    cs:__imp_LsaOpenPolicy
0x180027308  test    eax, eax
0x18002730a  jz      short loc_18002731F
0x18002730c  jle     loc_1800273C1
0x180027312  movzx   eax, ax
0x180027315  or      eax, 80070000h
0x18002731a  jmp     loc_1800273C1
0x18002731f  mov     rcx, [rbp+90h+PolicyHandle]; PolicyHandle
0x180027323  lea     r8, [rbp+90h+PrivateData]; PrivateData
0x180027327  lea     rdx, [rbp+90h+KeyName]; KeyName
0x18002732b  call    cs:__imp_LsaRetrievePrivateData
0x180027331  mov     ebx, eax
0x180027333  test    eax, eax
0x180027335  jz      short loc_180027352
0x180027337  mov     rcx, [rbp+90h+PolicyHandle]; ObjectHandle
0x18002733b  call    cs:__imp_LsaClose
0x180027341  test    ebx, ebx
0x180027343  jle     short loc_18002734E
0x180027345  movzx   ebx, bx
0x180027348  or      ebx, 80070000h
0x18002734e  mov     eax, ebx
0x180027350  jmp     short loc_1800273C1
0x180027352  mov     rax, [rbp+90h+PrivateData]
0x180027356  test    rax, rax
0x180027359  jnz     short loc_180027362
0x18002735b  mov     edi, 8000FFFFh
0x180027360  jmp     short loc_1800273B5
0x180027362  movzx   ecx, word ptr [rax]; cb
0x180027365  mov     [rsi], ecx
0x180027367  call    cs:__imp_CoTaskMemAlloc
0x18002736d  mov     [r14], rax
0x180027370  test    rax, rax
0x180027373  jz      short loc_18002738B
0x180027375  mov     rdx, [rbp+90h+PrivateData]
0x180027379  mov     rcx, rax; void *
0x18002737c  movzx   r8d, word ptr [rdx]; Size
0x180027380  mov     rdx, [rdx+8]; Src
0x180027384  call    memcpy_0
0x180027389  jmp     short loc_180027390
0x18002738b  mov     edi, 8007000Eh
0x180027390  mov     rcx, [rbp+90h+PrivateData]
0x180027394  movzx   edx, word ptr [rcx]
0x180027397  mov     rax, [rcx+8]
0x18002739b  test    rdx, rdx
0x18002739e  jz      short loc_1800273AF
0x1800273a0  mov     byte ptr [rax], 0
0x1800273a3  add     rax, r12
0x1800273a6  sub     rdx, r12
0x1800273a9  jnz     short loc_1800273A0
0x1800273ab  mov     rcx, [rbp+90h+PrivateData]; Buffer
0x1800273af  call    cs:__imp_LsaFreeMemory
0x1800273b5  mov     rcx, [rbp+90h+PolicyHandle]; ObjectHandle
0x1800273b9  call    cs:__imp_LsaClose
0x1800273bf  mov     eax, edi
0x1800273c1  mov     rcx, [rbp+90h+var_40]
0x1800273c5  xor     rcx, rbp; StackCookie
0x1800273c8  call    __security_check_cookie
0x1800273cd  lea     rsp, [rbp+68h]
0x1800273d1  pop     r14
0x1800273d3  pop     r12
0x1800273d5  pop     rdi
0x1800273d6  pop     rsi
0x1800273d7  pop     rbx
0x1800273d8  pop     rbp
0x1800273d9  retn
```
