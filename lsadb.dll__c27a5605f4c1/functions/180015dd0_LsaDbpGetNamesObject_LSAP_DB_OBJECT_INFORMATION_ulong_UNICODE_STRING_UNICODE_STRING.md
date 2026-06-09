# LsaDbpGetNamesObject(_LSAP_DB_OBJECT_INFORMATION *,ulong,_UNICODE_STRING,_UNICODE_STRING *)

- ea: `0x180015dd0`
- end: `0x180015fe9`
- name: `?LsaDbpGetNamesObject@@YAJPEAU_LSAP_DB_OBJECT_INFORMATION@@KU_UNICODE_STRING@@PEAU2@@Z`
- size: `537`
- prototype: `__int64 __fastcall(struct _LSAP_DB_OBJECT_INFORMATION *, unsigned int, struct _UNICODE_STRING *__struct_ptr, struct _UNICODE_STRING *)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x180015dd0`
- `0x18001f890`
- `0x18003ad30`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180015ebb`
- `RPCRT4!UuidCreate` at `0x180015ebb`
- `RPCRT4!UuidToStringW` at `0x180015ed8`
- `RPCRT4!UuidToStringW` at `0x180015ed8`
- `RPCRT4!RpcStringFreeW` at `0x180015f94`
- `RPCRT4!RpcStringFreeW` at `0x180015f94`
- `LSASRV!LsapTruncateUnicodeString` at `0x180015e80`
- `LSASRV!LsapTruncateUnicodeString` at `0x180015f10`
- `LSASRV!LsapTruncateUnicodeString` at `0x180015e80`
- `LSASRV!LsapTruncateUnicodeString` at `0x180015f10`
- `LSASRV!LsapAllocateLsaHeap` at `0x180015e2a`
- `LSASRV!LsapAllocateLsaHeap` at `0x180015f35`
- `LSASRV!LsapAllocateLsaHeap` at `0x180015e2a`
- `LSASRV!LsapAllocateLsaHeap` at `0x180015f35`
- `LSASRV!LsapFreeLsaHeap` at `0x180015f5f`
- `LSASRV!LsapFreeLsaHeap` at `0x180015fbd`
- `LSASRV!LsapFreeLsaHeap` at `0x180015f5f`
- `LSASRV!LsapFreeLsaHeap` at `0x180015fbd`
- `ntdll!RtlInitUnicodeString` at `0x180015e18`
- `ntdll!RtlInitUnicodeString` at `0x180015e18`

## pseudocode

```c
__int64 __fastcall LsaDbpGetNamesObject(
        struct _LSAP_DB_OBJECT_INFORMATION *a1,
        char a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  __int64 MaximumLength; // rcx
  WCHAR *LsaHeap; // rax
  int PhysicalObjectName; // ebx
  PWSTR Buffer; // rdx
  int v12; // esi
  unsigned int v13; // edi
  __int64 v14; // rdx
  __int64 v15; // r8
  RPC_STATUS v16; // eax
  __int64 v17; // rbx
  size_t v18; // r15
  __int64 v19; // rsi
  WCHAR *v20; // rax
  WCHAR *v21; // r14
  __int64 v22; // rdx
  __int64 v23; // r8
  bool v25; // [rsp+20h] [rbp-40h]
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-38h] BYREF
  RPC_WSTR StringUuid; // [rsp+38h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+40h] [rbp-20h] BYREF

  StringUuid = 0;
  Uuid = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  DestinationString.MaximumLength = a3->MaximumLength;
  MaximumLength = DestinationString.MaximumLength;
  a4->Buffer = 0;
  LsaHeap = (WCHAR *)LsapAllocateLsaHeap(MaximumLength);
  DestinationString.Buffer = LsaHeap;
  if ( LsaHeap )
  {
    memset_0(LsaHeap, 0, DestinationString.MaximumLength);
    Buffer = a3->Buffer;
    DestinationString.Length = a3->Length;
    memcpy_0(DestinationString.Buffer, Buffer, DestinationString.Length);
    v12 = a2 & 2;
    v13 = 256;
    v25 = v12 == 0;
    if ( v12 )
      LsapTruncateUnicodeString(&DestinationString, 256);
    PhysicalObjectName = LsaDbpDsGetPhysicalObjectName(a1, v12 == 0, &DestinationString, a4);
    if ( PhysicalObjectName != -1073741771 )
      goto LABEL_25;
    if ( *(_DWORD *)a1 != 6 )
      goto LABEL_25;
    if ( !v12 )
      goto LABEL_25;
    v16 = UuidCreate(&Uuid);
    if ( v16 )
    {
      if ( v16 != 1824 )
        goto LABEL_25;
    }
    if ( UuidToStringW(&Uuid, &StringUuid) )
    {
      PhysicalObjectName = -1073741773;
LABEL_25:
      LsapFreeLsaHeap(DestinationString.Buffer, v14, v15);
      return (unsigned int)PhysicalObjectName;
    }
    v17 = -1;
    do
      ++v17;
    while ( StringUuid[v17] );
    v18 = (unsigned int)v17;
    if ( (unsigned int)v17 + ((unsigned __int64)DestinationString.Length >> 1) < 0x100 )
    {
      v19 = DestinationString.Length >> 1;
      v13 = v19 + v17;
    }
    else
    {
      LsapTruncateUnicodeString(&DestinationString, 256);
      v19 = (unsigned int)(256 - v17);
    }
    if ( v13 <= DestinationString.MaximumLength >> 1 )
    {
      v21 = DestinationString.Buffer;
    }
    else
    {
      v20 = (WCHAR *)LsapAllocateLsaHeap(2LL * (v13 + 1));
      v21 = v20;
      if ( !v20 )
      {
        PhysicalObjectName = -1073741670;
        goto LABEL_22;
      }
      memcpy_0(v20, DestinationString.Buffer, DestinationString.Length);
      LsapFreeLsaHeap(DestinationString.Buffer, v22, v23);
      DestinationString.Buffer = v21;
      DestinationString.Length = 2 * v13;
      DestinationString.MaximumLength = 2 * v13 + 2;
    }
    PhysicalObjectName = 0;
    memcpy_0(&v21[v19], StringUuid, v18);
LABEL_22:
    RpcStringFreeW(&StringUuid);
    if ( PhysicalObjectName >= 0 )
      PhysicalObjectName = LsaDbpDsGetPhysicalObjectName(a1, v25, &DestinationString, a4);
    goto LABEL_25;
  }
  return (unsigned int)-1073741670;
}

```

## disassembly

```asm
0x180015dd0  mov     [rsp-38h+arg_0], rbx
0x180015dd5  push    rbp
0x180015dd6  push    rsi
0x180015dd7  push    rdi
0x180015dd8  push    r12
0x180015dda  push    r13
0x180015ddc  push    r14
0x180015dde  push    r15
0x180015de0  mov     rbp, rsp
0x180015de3  sub     rsp, 60h
0x180015de7  mov     rax, cs:__security_cookie
0x180015dee  xor     rax, rsp
0x180015df1  mov     [rbp+var_10], rax
0x180015df5  xorps   xmm0, xmm0
0x180015df8  mov     esi, edx
0x180015dfa  mov     r12, rcx
0x180015dfd  xor     r14d, r14d
0x180015e00  xor     edx, edx; SourceString
0x180015e02  mov     [rbp+StringUuid], r14
0x180015e06  lea     rcx, [rbp+DestinationString]; DestinationString
0x180015e0a  mov     r13, r9
0x180015e0d  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180015e11  mov     rbx, r8
0x180015e14  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180015e18  call    cs:__imp_RtlInitUnicodeString
0x180015e1e  movzx   ecx, word ptr [rbx+2]
0x180015e22  mov     [rbp+DestinationString.MaximumLength], cx
0x180015e26  mov     [r13+8], r14
0x180015e2a  call    cs:__imp_LsapAllocateLsaHeap
0x180015e30  mov     [rbp+DestinationString.Buffer], rax
0x180015e34  test    rax, rax
0x180015e37  jnz     short loc_180015E43
0x180015e39  mov     ebx, 0C000009Ah
0x180015e3e  jmp     loc_180015FC3
0x180015e43  movzx   r8d, [rbp+DestinationString.MaximumLength]; Size
0x180015e48  xor     edx, edx; Val
0x180015e4a  mov     rcx, rax; void *
0x180015e4d  call    memset_0
0x180015e52  movzx   r8d, word ptr [rbx]; Size
0x180015e56  mov     rdx, [rbx+8]; Src
0x180015e5a  mov     rcx, [rbp+DestinationString.Buffer]; void *
0x180015e5e  mov     [rbp+DestinationString.Length], r8w
0x180015e63  call    memcpy_0
0x180015e68  and     esi, 2
0x180015e6b  mov     edi, 100h
0x180015e70  setz    bl
0x180015e73  mov     [rbp+var_40], bl
0x180015e76  test    esi, esi
0x180015e78  jz      short loc_180015E86
0x180015e7a  mov     edx, edi
0x180015e7c  lea     rcx, [rbp+DestinationString]
0x180015e80  call    cs:__imp_LsapTruncateUnicodeString
0x180015e86  mov     r9, r13; struct _UNICODE_STRING *
0x180015e89  lea     r8, [rbp+DestinationString]; struct _UNICODE_STRING *
0x180015e8d  mov     dl, bl; unsigned __int8
0x180015e8f  mov     rcx, r12; struct _LSAP_DB_OBJECT_INFORMATION *
0x180015e92  call    ?LsaDbpDsGetPhysicalObjectName@@YAJPEAU_LSAP_DB_OBJECT_INFORMATION@@EPEAU_UNICODE_STRING@@1@Z; LsaDbpDsGetPhysicalObjectName(_LSAP_DB_OBJECT_INFORMATION *,uchar,_UNICODE_STRING *,_UNICODE_STRING *)
0x180015e97  mov     ebx, eax
0x180015e99  cmp     eax, 0C0000035h
0x180015e9e  jnz     loc_180015FB9
0x180015ea4  cmp     dword ptr [r12], 6
0x180015ea9  jnz     loc_180015FB9
0x180015eaf  test    esi, esi
0x180015eb1  jz      loc_180015FB9
0x180015eb7  lea     rcx, [rbp+Uuid]; Uuid
0x180015ebb  call    cs:__imp_UuidCreate
0x180015ec1  test    eax, eax
0x180015ec3  jz      short loc_180015ED0
0x180015ec5  cmp     eax, 720h
0x180015eca  jnz     loc_180015FB9
0x180015ed0  lea     rdx, [rbp+StringUuid]; StringUuid
0x180015ed4  lea     rcx, [rbp+Uuid]; Uuid
0x180015ed8  call    cs:__imp_UuidToStringW
0x180015ede  test    eax, eax
0x180015ee0  jnz     loc_180015FB4
0x180015ee6  mov     rax, [rbp+StringUuid]
0x180015eea  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015eee  inc     rbx
0x180015ef1  cmp     [rax+rbx*2], r14w
0x180015ef6  jnz     short loc_180015EEE
0x180015ef8  movzx   eax, [rbp+DestinationString.Length]
0x180015efc  shr     rax, 1
0x180015eff  mov     r15d, ebx
0x180015f02  add     rax, r15
0x180015f05  cmp     rax, rdi
0x180015f08  jb      short loc_180015F1C
0x180015f0a  mov     edx, edi
0x180015f0c  lea     rcx, [rbp+DestinationString]
0x180015f10  call    cs:__imp_LsapTruncateUnicodeString
0x180015f16  mov     esi, edi
0x180015f18  sub     esi, ebx
0x180015f1a  jmp     short loc_180015F25
0x180015f1c  movzx   esi, [rbp+DestinationString.Length]
0x180015f20  shr     esi, 1
0x180015f22  lea     edi, [rsi+rbx]
0x180015f25  movzx   eax, [rbp+DestinationString.MaximumLength]
0x180015f29  shr     eax, 1
0x180015f2b  cmp     edi, eax
0x180015f2d  jbe     short loc_180015F7A
0x180015f2f  lea     ecx, [rdi+1]
0x180015f32  add     rcx, rcx
0x180015f35  call    cs:__imp_LsapAllocateLsaHeap
0x180015f3b  mov     r14, rax
0x180015f3e  test    rax, rax
0x180015f41  jnz     short loc_180015F4A
0x180015f43  mov     ebx, 0C000009Ah
0x180015f48  jmp     short loc_180015F90
0x180015f4a  movzx   r8d, [rbp+DestinationString.Length]; Size
0x180015f4f  mov     rcx, r14; void *
0x180015f52  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x180015f56  call    memcpy_0
0x180015f5b  mov     rcx, [rbp+DestinationString.Buffer]
0x180015f5f  call    cs:__imp_LsapFreeLsaHeap
0x180015f65  add     di, di
0x180015f68  mov     [rbp+DestinationString.Buffer], r14
0x180015f6c  mov     [rbp+DestinationString.Length], di
0x180015f70  add     di, 2
0x180015f74  mov     [rbp+DestinationString.MaximumLength], di
0x180015f78  jmp     short loc_180015F7E
0x180015f7a  mov     r14, [rbp+DestinationString.Buffer]
0x180015f7e  mov     rdx, [rbp+StringUuid]; Src
0x180015f82  lea     rcx, [r14+rsi*2]; void *
0x180015f86  xor     ebx, ebx
0x180015f88  mov     r8, r15; Size
0x180015f8b  call    memcpy_0
0x180015f90  lea     rcx, [rbp+StringUuid]; String
0x180015f94  call    cs:__imp_RpcStringFreeW
0x180015f9a  test    ebx, ebx
0x180015f9c  js      short loc_180015FB9
0x180015f9e  mov     dl, [rbp+var_40]; unsigned __int8
0x180015fa1  lea     r8, [rbp+DestinationString]; struct _UNICODE_STRING *
0x180015fa5  mov     r9, r13; struct _UNICODE_STRING *
0x180015fa8  mov     rcx, r12; struct _LSAP_DB_OBJECT_INFORMATION *
0x180015fab  call    ?LsaDbpDsGetPhysicalObjectName@@YAJPEAU_LSAP_DB_OBJECT_INFORMATION@@EPEAU_UNICODE_STRING@@1@Z; LsaDbpDsGetPhysicalObjectName(_LSAP_DB_OBJECT_INFORMATION *,uchar,_UNICODE_STRING *,_UNICODE_STRING *)
0x180015fb0  mov     ebx, eax
0x180015fb2  jmp     short loc_180015FB9
0x180015fb4  mov     ebx, 0C0000033h
0x180015fb9  mov     rcx, [rbp+DestinationString.Buffer]
0x180015fbd  call    cs:__imp_LsapFreeLsaHeap
0x180015fc3  mov     eax, ebx
0x180015fc5  mov     rcx, [rbp+var_10]
0x180015fc9  xor     rcx, rsp; StackCookie
0x180015fcc  call    __security_check_cookie
0x180015fd1  mov     rbx, [rsp+60h+arg_0]
0x180015fd9  add     rsp, 60h
0x180015fdd  pop     r15
0x180015fdf  pop     r14
0x180015fe1  pop     r13
0x180015fe3  pop     r12
0x180015fe5  pop     rdi
0x180015fe6  pop     rsi
0x180015fe7  pop     rbp
0x180015fe8  retn
```
