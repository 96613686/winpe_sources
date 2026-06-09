# IntfHlpGetFriendlyNameFromGUID(_GUID const *,ushort *,ulong)

- ea: `0x1800280e0`
- end: `0x180028213`
- name: `?IntfHlpGetFriendlyNameFromGUID@@YAKPEBU_GUID@@PEAGK@Z`
- size: `307`
- prototype: `__int64 __fastcall(const struct _GUID *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018764`
- `0x18001ae7c`

## callees

- `0x1800025f0`
- `0x180003114`
- `0x180008c38`
- `0x180027f88`
- `0x1800280e0`
- `0x18002821c`

## import_xrefs

- `MobileNetworking!AcquireReadLock` at `0x18002813a`
- `MobileNetworking!AcquireReadLock` at `0x18002813a`
- `MobileNetworking!ReleaseReadLock` at `0x1800281d0`
- `MobileNetworking!ReleaseReadLock` at `0x1800281d0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180028190`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180028190`

## pseudocode

```c
__int64 __fastcall IntfHlpGetFriendlyNameFromGUID(const struct _GUID *a1, unsigned __int16 *a2)
{
  int i; // ebp
  unsigned int AdapterAddressesInfo; // edi
  PIP_ADAPTER_ADDRESSES j; // rbx
  PCHAR AdapterName; // rsi
  OLECHAR *k; // rcx
  char v9; // al
  __int64 v10; // rax
  GUID pclsid; // [rsp+20h] [rbp-128h] BYREF
  OLECHAR sz[99]; // [rsp+30h] [rbp-118h] BYREF
  OLECHAR v14[5]; // [rsp+F6h] [rbp-52h] BYREF

  pclsid = 0;
  if ( a1 && a2 )
  {
    for ( i = 0; ; i = 1 )
    {
      AdapterAddressesInfo = GetAdapterAddressesInfo();
      if ( AdapterAddressesInfo )
        break;
      AcquireReadLock(qword_180052DF0);
      for ( j = Block; j; j = j->Next )
      {
        AdapterName = j->AdapterName;
        memset_0(sz, 0, 0xC8u);
        for ( k = sz; *AdapterName && k < v14; ++k )
        {
          v9 = *AdapterName++;
          *(_BYTE *)k = v9;
        }
        if ( CLSIDFromString(sz, &pclsid) >= 0 )
        {
          v10 = *(_QWORD *)&pclsid.Data1 - *(_QWORD *)&a1->Data1;
          if ( *(_QWORD *)&pclsid.Data1 == *(_QWORD *)&a1->Data1 )
            v10 = *(_QWORD *)pclsid.Data4 - *(_QWORD *)a1->Data4;
          if ( !v10 )
          {
            StringCchCopyW(a2, 0x100u, j->FriendlyName);
            break;
          }
        }
      }
      ReleaseReadLock(qword_180052DF0);
      if ( j || i )
        break;
      ResetAdapterAddressesInfo();
    }
  }
  else
  {
    return 87;
  }
  return AdapterAddressesInfo;
}

```

## disassembly

```asm
0x1800280e0  push    rbx
0x1800280e2  push    rbp
0x1800280e3  push    rsi
0x1800280e4  push    rdi
0x1800280e5  push    r14
0x1800280e7  push    r15
0x1800280e9  sub     rsp, 118h
0x1800280f0  mov     rax, cs:__security_cookie
0x1800280f7  xor     rax, rsp
0x1800280fa  mov     [rsp+148h+var_48], rax
0x180028102  xorps   xmm0, xmm0
0x180028105  mov     r15, rdx
0x180028108  mov     r14, rcx
0x18002810b  movups  xmmword ptr [rsp+148h+pclsid.Data1], xmm0
0x180028110  test    rcx, rcx
0x180028113  jz      loc_1800281EC
0x180028119  test    rdx, rdx
0x18002811c  jz      loc_1800281EC
0x180028122  xor     ebp, ebp
0x180028124  call    ?GetAdapterAddressesInfo@@YAKXZ; GetAdapterAddressesInfo(void)
0x180028129  mov     edi, eax
0x18002812b  test    eax, eax
0x18002812d  jnz     loc_1800281F1
0x180028133  lea     rcx, qword_180052DF0
0x18002813a  call    cs:__imp_AcquireReadLock
0x180028140  mov     rbx, cs:Block
0x180028147  test    rbx, rbx
0x18002814a  jz      short loc_1800281C9
0x18002814c  mov     rsi, [rbx+10h]
0x180028150  lea     rcx, [rsp+148h+sz]; void *
0x180028155  xor     edx, edx; Val
0x180028157  mov     r8d, 0C8h; Size
0x18002815d  call    memset_0
0x180028162  lea     rcx, [rsp+148h+sz]
0x180028167  jmp     short loc_180028181
0x180028169  lea     rax, [rsp+148h+var_52]
0x180028171  cmp     rcx, rax
0x180028174  jnb     short loc_180028186
0x180028176  mov     al, [rsi]
0x180028178  inc     rsi
0x18002817b  mov     [rcx], al
0x18002817d  add     rcx, 2
0x180028181  cmp     byte ptr [rsi], 0
0x180028184  jnz     short loc_180028169
0x180028186  lea     rdx, [rsp+148h+pclsid]; pclsid
0x18002818b  lea     rcx, [rsp+148h+sz]; lpsz
0x180028190  call    cs:__imp_CLSIDFromString
0x180028196  test    eax, eax
0x180028198  js      short loc_1800281B2
0x18002819a  mov     rax, qword ptr [rsp+148h+pclsid.Data1]
0x18002819f  sub     rax, [r14]
0x1800281a2  jnz     short loc_1800281AD
0x1800281a4  mov     rax, qword ptr [rsp+148h+pclsid.Data4]
0x1800281a9  sub     rax, [r14+8]
0x1800281ad  test    rax, rax
0x1800281b0  jz      short loc_1800281B8
0x1800281b2  mov     rbx, [rbx+8]
0x1800281b6  jmp     short loc_180028147
0x1800281b8  mov     r8, [rbx+48h]; unsigned __int16 *
0x1800281bc  mov     edx, 100h; unsigned __int64
0x1800281c1  mov     rcx, r15; unsigned __int16 *
0x1800281c4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800281c9  lea     rcx, qword_180052DF0
0x1800281d0  call    cs:__imp_ReleaseReadLock
0x1800281d6  test    rbx, rbx
0x1800281d9  jnz     short loc_1800281F1
0x1800281db  test    ebp, ebp
0x1800281dd  jnz     short loc_1800281F1
0x1800281df  lea     ebp, [rbx+1]
0x1800281e2  call    ?ResetAdapterAddressesInfo@@YAXXZ; ResetAdapterAddressesInfo(void)
0x1800281e7  jmp     loc_180028124
0x1800281ec  mov     edi, 57h ; 'W'
0x1800281f1  mov     eax, edi
0x1800281f3  mov     rcx, [rsp+148h+var_48]
0x1800281fb  xor     rcx, rsp; StackCookie
0x1800281fe  call    __security_check_cookie
0x180028203  add     rsp, 118h
0x18002820a  pop     r15
0x18002820c  pop     r14
0x18002820e  pop     rdi
0x18002820f  pop     rsi
0x180028210  pop     rbp
0x180028211  pop     rbx
0x180028212  retn
```
