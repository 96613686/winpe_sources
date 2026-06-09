# QuerySystemCredentials(uchar * const,uchar * const)

- ea: `0x1800328dc`
- end: `0x180032a10`
- name: `?QuerySystemCredentials@@YAKQEAE0@Z`
- size: `308`
- prototype: `__int64 __fastcall(unsigned __int8 *const, unsigned __int8 *const)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001aaac`
- `0x180032674`

## callees

- `0x180032898`
- `0x1800328dc`
- `0x180035c58`
- `0x1800367a4`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18003295e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18003295e`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800329e8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800329e8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x18003294b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x18003294b`

## pseudocode

```c
__int64 __fastcall QuerySystemCredentials(unsigned __int8 *const a1, unsigned __int8 *const a2)
{
  unsigned __int16 *v3; // rcx
  NTSTATUS v4; // ebx
  PLSA_UNICODE_STRING v5; // rcx
  unsigned int v6; // ebx
  PWSTR Buffer; // rdx
  __int64 Length; // rdx
  PWSTR v9; // rax
  struct _LSA_UNICODE_STRING KeyName; // [rsp+20h] [rbp-18h] BYREF
  PLSA_UNICODE_STRING PrivateData; // [rsp+40h] [rbp+8h] BYREF
  LSA_HANDLE PolicyHandle; // [rsp+48h] [rbp+10h] BYREF

  PolicyHandle = 0;
  KeyName = 0;
  PrivateData = 0;
  if ( !(unsigned int)WaitOnSAMDatabase() )
    return 258;
  InitLsaString((struct _UNICODE_STRING *)&KeyName, L"DPAPI_SYSTEM");
  if ( OpenPolicy(v3, 4u, &PolicyHandle) < 0 )
    return 87;
  v4 = LsaRetrievePrivateData(PolicyHandle, &KeyName, &PrivateData);
  LsaClose(PolicyHandle);
  if ( v4 == -1073741772 )
    return 2;
  if ( v4 < 0 )
    return 87;
  v5 = PrivateData;
  if ( !PrivateData )
    return 87;
  if ( !PrivateData->Length )
    return 2;
  v6 = 87;
  if ( PrivateData->Length == 44 )
  {
    Buffer = PrivateData->Buffer;
    if ( *(_DWORD *)Buffer == 1 )
    {
      v6 = 0;
      *(_OWORD *)&g_rgbSystemCredMachine = *(_OWORD *)(Buffer + 2);
      dword_18004C7D8 = *((_DWORD *)Buffer + 5);
      *(_OWORD *)&g_rgbSystemCredUser = *(_OWORD *)(Buffer + 12);
      dword_18004C7F0 = *((_DWORD *)Buffer + 10);
    }
  }
  Length = PrivateData->Length;
  v9 = PrivateData->Buffer;
  if ( PrivateData->Length )
  {
    do
    {
      *(_BYTE *)v9 = 0;
      v9 = (PWSTR)((char *)v9 + 1);
      --Length;
    }
    while ( Length );
    v5 = PrivateData;
  }
  LsaFreeMemory(v5);
  return v6;
}

```

## disassembly

```asm
0x1800328dc  mov     rax, rsp
0x1800328df  mov     [rax+18h], rbx
0x1800328e3  mov     [rax+10h], rdx
0x1800328e7  mov     [rax+8], rcx
0x1800328eb  push    rdi
0x1800328ec  sub     rsp, 30h
0x1800328f0  xor     edi, edi
0x1800328f2  xorps   xmm0, xmm0
0x1800328f5  mov     [rax+10h], rdi
0x1800328f9  movups  xmmword ptr [rax-18h], xmm0
0x1800328fd  mov     [rax+8], rdi
0x180032901  call    ?WaitOnSAMDatabase@@YAHXZ; WaitOnSAMDatabase(void)
0x180032906  test    eax, eax
0x180032908  jnz     short loc_180032914
0x18003290a  mov     eax, 102h
0x18003290f  jmp     loc_180032A04
0x180032914  lea     rdx, aDpapiSystem; "DPAPI_SYSTEM"
0x18003291b  lea     rcx, [rsp+38h+KeyName]; struct _UNICODE_STRING *
0x180032920  call    ?InitLsaString@@YAXPEAU_UNICODE_STRING@@PEAG@Z; InitLsaString(_UNICODE_STRING *,ushort *)
0x180032925  lea     r8, [rsp+38h+PolicyHandle]; void **
0x18003292a  mov     edx, 4; unsigned int
0x18003292f  call    ?OpenPolicy@@YAJPEAGKPEAPEAX@Z; OpenPolicy(ushort *,ulong,void * *)
0x180032934  test    eax, eax
0x180032936  js      loc_1800329FF
0x18003293c  mov     rcx, [rsp+38h+PolicyHandle]; PolicyHandle
0x180032941  lea     r8, [rsp+38h+PrivateData]; PrivateData
0x180032946  lea     rdx, [rsp+38h+KeyName]; KeyName
0x18003294b  call    cs:__imp_LsaRetrievePrivateData
0x180032952  nop     dword ptr [rax+rax+00h]
0x180032957  mov     rcx, [rsp+38h+PolicyHandle]; ObjectHandle
0x18003295c  mov     ebx, eax
0x18003295e  call    cs:__imp_LsaClose
0x180032965  nop     dword ptr [rax+rax+00h]
0x18003296a  cmp     ebx, 0C0000034h
0x180032970  jz      loc_1800329F8
0x180032976  test    ebx, ebx
0x180032978  js      loc_1800329FF
0x18003297e  mov     rcx, [rsp+38h+PrivateData]
0x180032983  test    rcx, rcx
0x180032986  jz      short loc_1800329FF
0x180032988  cmp     [rcx], di
0x18003298b  jz      short loc_1800329F8
0x18003298d  cmp     word ptr [rcx], 2Ch ; ','
0x180032991  mov     ebx, 57h ; 'W'
0x180032996  jnz     short loc_1800329CB
0x180032998  mov     rdx, [rcx+8]
0x18003299c  cmp     dword ptr [rdx], 1
0x18003299f  jnz     short loc_1800329CB
0x1800329a1  movups  xmm0, xmmword ptr [rdx+4]
0x1800329a5  mov     ebx, edi
0x1800329a7  movups  cs:?g_rgbSystemCredMachine@@3PAEA, xmm0; uchar near * g_rgbSystemCredMachine
0x1800329ae  mov     eax, [rdx+14h]
0x1800329b1  mov     cs:dword_18004C7D8, eax
0x1800329b7  movups  xmm0, xmmword ptr [rdx+18h]
0x1800329bb  movups  cs:?g_rgbSystemCredUser@@3PAEA, xmm0; uchar near * g_rgbSystemCredUser
0x1800329c2  mov     eax, [rdx+28h]
0x1800329c5  mov     cs:dword_18004C7F0, eax
0x1800329cb  movzx   edx, word ptr [rcx]
0x1800329ce  mov     rax, [rcx+8]
0x1800329d2  test    rdx, rdx
0x1800329d5  jz      short loc_1800329E8
0x1800329d7  mov     [rax], dil
0x1800329da  inc     rax
0x1800329dd  sub     rdx, 1
0x1800329e1  jnz     short loc_1800329D7
0x1800329e3  mov     rcx, [rsp+38h+PrivateData]; Buffer
0x1800329e8  call    cs:__imp_LsaFreeMemory
0x1800329ef  nop     dword ptr [rax+rax+00h]
0x1800329f4  mov     eax, ebx
0x1800329f6  jmp     short loc_180032A04
0x1800329f8  mov     eax, 2
0x1800329fd  jmp     short loc_180032A04
0x1800329ff  mov     eax, 57h ; 'W'
0x180032a04  mov     rbx, [rsp+38h+arg_10]
0x180032a09  add     rsp, 30h
0x180032a0d  pop     rdi
0x180032a0e  retn
```
